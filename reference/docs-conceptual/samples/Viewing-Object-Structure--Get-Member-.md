---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 查看对象结构 (Get Member)
description: Get-Member 是一种功能强大的工具，借助它可查看 PowerShell 中对象的类型和结构。
ms.openlocfilehash: 3c294fe47294e2cf8daf125aac55661dd38cf9bb
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501212"
---
# <a name="viewing-object-structure-get-member"></a><span data-ttu-id="3d81f-104">查看对象结构 (Get-Member)</span><span class="sxs-lookup"><span data-stu-id="3d81f-104">Viewing Object Structure (Get-Member)</span></span>

<span data-ttu-id="3d81f-105">由于对象在 Windows PowerShell 中扮演了如此重要的角色，因此存在几个用于处理任意对象类型的本机命令。</span><span class="sxs-lookup"><span data-stu-id="3d81f-105">Because objects play such a central role in Windows PowerShell, there are several native commands designed to work with arbitrary object types.</span></span> <span data-ttu-id="3d81f-106">最重要的一个是 **Get-Member** 命令。</span><span class="sxs-lookup"><span data-stu-id="3d81f-106">The most important one is the **Get-Member** command.</span></span>

<span data-ttu-id="3d81f-107">分析命令返回的对象的最简单方法是通过管道将该命令的输出传递到 **Get-Member** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d81f-107">The simplest technique for analyzing the objects that a command returns is to pipe the output of that command to the **Get-Member** cmdlet.</span></span> <span data-ttu-id="3d81f-108">**Get-Member** cmdlet 向你显示对象类型的正式名称及其成员的完整列表。</span><span class="sxs-lookup"><span data-stu-id="3d81f-108">The **Get-Member** cmdlet shows you the formal name of the object type and a complete listing of its members.</span></span> <span data-ttu-id="3d81f-109">有时返回的元素数目可能非常巨大。</span><span class="sxs-lookup"><span data-stu-id="3d81f-109">The number of elements that are returned can sometimes be overwhelming.</span></span> <span data-ttu-id="3d81f-110">例如，一个进程对象可以拥有 100 多个成员。</span><span class="sxs-lookup"><span data-stu-id="3d81f-110">For example, a process object can have over 100 members.</span></span>

<span data-ttu-id="3d81f-111">若要查看进程对象的所有成员并分页显示输出，以便于你可以全部查看，请键入：</span><span class="sxs-lookup"><span data-stu-id="3d81f-111">To see all the members of a Process object and page the output so you can view all of it, type:</span></span>

```powershell
Get-Process | Get-Member | Out-Host -Paging
```

<span data-ttu-id="3d81f-112">此命令的输出将如下所示：</span><span class="sxs-lookup"><span data-stu-id="3d81f-112">The output from this command will look something like this:</span></span>

```Output
TypeName: System.Diagnostics.Process

Name                           MemberType     Definition
----                           ----------     ----------
Handles                        AliasProperty  Handles = Handlecount
Name                           AliasProperty  Name = ProcessName
NPM                            AliasProperty  NPM = NonpagedSystemMemorySize
PM                             AliasProperty  PM = PagedMemorySize
VM                             AliasProperty  VM = VirtualMemorySize
WS                             AliasProperty  WS = WorkingSet
add_Disposed                   Method         System.Void add_Disposed(Event...
...
```

<span data-ttu-id="3d81f-113">我们可以通过筛选想要查看的元素，让这个冗长的信息列表更易于使用。</span><span class="sxs-lookup"><span data-stu-id="3d81f-113">We can make this long list of information more usable by filtering for elements we want to see.</span></span> <span data-ttu-id="3d81f-114">**Get-Member** 命令仅允许你列出属性成员。</span><span class="sxs-lookup"><span data-stu-id="3d81f-114">The **Get-Member** command lets you list only members that are properties.</span></span> <span data-ttu-id="3d81f-115">属性的形式有数种。</span><span class="sxs-lookup"><span data-stu-id="3d81f-115">There are several forms of properties.</span></span> <span data-ttu-id="3d81f-116">如果将 Get-Member MemberType 参数设置为值属性，则 cmdlet 将显示任何类型的属性  。</span><span class="sxs-lookup"><span data-stu-id="3d81f-116">The cmdlet displays properties of any type if we set the **Get-Member MemberType** parameter to the value **Properties** .</span></span> <span data-ttu-id="3d81f-117">生成的列表仍会很长，但较之前更易于管理：</span><span class="sxs-lookup"><span data-stu-id="3d81f-117">The resulting list is still very long, but a bit more manageable:</span></span>

```
PS> Get-Process | Get-Member -MemberType Properties

   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
...
ExitCode                   Property       System.Int32 ExitCode {get;}
...
Handle                     Property       System.IntPtr Handle {get;}
...
CPU                        ScriptProperty System.Object CPU {get=$this.Total...
...
Path                       ScriptProperty System.Object Path {get=$this.Main...
...
```

> [!NOTE]
> <span data-ttu-id="3d81f-118">MemberType 的允许值有 AliasProperty、CodeProperty、Property、NoteProperty、ScriptProperty、Properties、PropertySet、Method、CodeMethod、ScriptMethod、Methods、ParameterizedProperty、MemberSet 以及 All。</span><span class="sxs-lookup"><span data-stu-id="3d81f-118">The allowed values of MemberType are AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, and All.</span></span>

<span data-ttu-id="3d81f-119">一个进程有 60 多个属性。</span><span class="sxs-lookup"><span data-stu-id="3d81f-119">There are over 60 properties for a process.</span></span> <span data-ttu-id="3d81f-120">对于任何已知的对象，Windows PowerShell 通常仅显示少许属性，这是因为显示所有属性会导致产生无法管理的信息量。</span><span class="sxs-lookup"><span data-stu-id="3d81f-120">The reason Windows PowerShell often shows only a handful of properties for any well-known object is that showing all of them would produce an unmanageable amount of information.</span></span>

> [!NOTE]
> <span data-ttu-id="3d81f-121">Windows PowerShell 通过使用存储在以 .format.ps1xml 结尾的 XML 文件中的信息来决定某种类型的对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="3d81f-121">Windows PowerShell determines how to display an object type by using information stored in XML files that have names ending in .format.ps1xml.</span></span> <span data-ttu-id="3d81f-122">进程对象（即 .NET System.Diagnostics.Process 对象）的格式设置数据存储在 DotNetTypes.format.ps1xml 中。</span><span class="sxs-lookup"><span data-stu-id="3d81f-122">The formatting data for process objects, which are .NET System.Diagnostics.Process objects, is stored in DotNetTypes.format.ps1xml.</span></span>

<span data-ttu-id="3d81f-123">如果需要查看 Windows PowerShell 默认显示的属性之外的属性，则需要自己对输出数据进行格式化。</span><span class="sxs-lookup"><span data-stu-id="3d81f-123">If you need to look at properties other than those that Windows PowerShell displays by default, you will need to format the output data yourself.</span></span> <span data-ttu-id="3d81f-124">这可以通过使用格式 cmdlet 实现。</span><span class="sxs-lookup"><span data-stu-id="3d81f-124">This can be done by using the format cmdlets.</span></span>
