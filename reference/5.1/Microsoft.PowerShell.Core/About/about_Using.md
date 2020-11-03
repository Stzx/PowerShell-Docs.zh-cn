---
description: 允许你指示在会话中使用的命名空间。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: ff6b43c3af1deddb5cb1b4c2e2c86a2cc2cac5d4
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200666"
---
# <a name="about-using"></a><span data-ttu-id="734cc-104">关于使用</span><span class="sxs-lookup"><span data-stu-id="734cc-104">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="734cc-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="734cc-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="734cc-106">允许你指示在会话中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="734cc-106">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="734cc-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="734cc-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="734cc-108">`using`语句允许您指定在会话中使用的命名空间。</span><span class="sxs-lookup"><span data-stu-id="734cc-108">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="734cc-109">添加命名空间可简化 .NET 类和成员的使用，并允许你从脚本模块和程序集导入类。</span><span class="sxs-lookup"><span data-stu-id="734cc-109">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="734cc-110">`using`语句必须位于脚本中的任何其他语句之前。</span><span class="sxs-lookup"><span data-stu-id="734cc-110">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="734cc-111">`using`语句不应与 `using:` 变量的作用域修饰符混淆。</span><span class="sxs-lookup"><span data-stu-id="734cc-111">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="734cc-112">有关详细信息，请参阅 [about_Remote_Variables](about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="734cc-112">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="734cc-113">语法</span><span class="sxs-lookup"><span data-stu-id="734cc-113">Syntax</span></span>

<span data-ttu-id="734cc-114">指定要从中解析类型的 .NET 命名空间：</span><span class="sxs-lookup"><span data-stu-id="734cc-114">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="734cc-115">从 PowerShell 模块加载类：</span><span class="sxs-lookup"><span data-stu-id="734cc-115">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="734cc-116">若要预加载 .NET 程序集中的类型：</span><span class="sxs-lookup"><span data-stu-id="734cc-116">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
using assembly <.NET-namespace>
```

<span data-ttu-id="734cc-117">通过指定命名空间，可以更容易地按简称引用类型。</span><span class="sxs-lookup"><span data-stu-id="734cc-117">Specifying a namespace makes it easier to reference types by their short names.</span></span>

<span data-ttu-id="734cc-118">加载程序集时，将从该程序集将 .NET 类型预加载到脚本中的分析时。</span><span class="sxs-lookup"><span data-stu-id="734cc-118">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="734cc-119">这允许你创建新的 PowerShell 类，它们使用预先加载的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="734cc-119">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="734cc-120">在 Windows PowerShell 5.1 中，可以按路径名或名称加载程序集。</span><span class="sxs-lookup"><span data-stu-id="734cc-120">In Windows PowerShell 5.1 you can load the assembly by path name or by name.</span></span> <span data-ttu-id="734cc-121">使用该名称时，PowerShell 会在 .NET 全局程序集缓存中搜索关联程序集的 (GAC) 。</span><span class="sxs-lookup"><span data-stu-id="734cc-121">When you use the name, PowerShell searches the .NET Global Assembly Cache (GAC) for the associated assembly.</span></span>

<span data-ttu-id="734cc-122">如果未创建新的 PowerShell 类，请改用 `Add-Type` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="734cc-122">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="734cc-123">有关详细信息，请参阅 [添加类型](xref:Microsoft.PowerShell.Utility.Add-Type)。</span><span class="sxs-lookup"><span data-stu-id="734cc-123">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="734cc-124">示例</span><span class="sxs-lookup"><span data-stu-id="734cc-124">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="734cc-125">示例 1-为 typename 解析添加命名空间</span><span class="sxs-lookup"><span data-stu-id="734cc-125">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="734cc-126">下面的脚本获取 "Hello World" 字符串的加密哈希。</span><span class="sxs-lookup"><span data-stu-id="734cc-126">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="734cc-127">请注意 `using namespace System.Text` 和如何 `using namespace System.IO` 简化对中 `[UnicodeEncoding]` `System.Text` 和和的引用 `[Stream]` `[MemoryStream]` `System.IO` 。</span><span class="sxs-lookup"><span data-stu-id="734cc-127">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="734cc-128">示例 2-从脚本模块加载类</span><span class="sxs-lookup"><span data-stu-id="734cc-128">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="734cc-129">在此示例中，有一个名为 **CardGames** 的 PowerShell 脚本模块，用于定义以下类：</span><span class="sxs-lookup"><span data-stu-id="734cc-129">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="734cc-130">**CardGames**</span><span class="sxs-lookup"><span data-stu-id="734cc-130">**CardGames.Deck**</span></span>
- <span data-ttu-id="734cc-131">**CardGames 卡**</span><span class="sxs-lookup"><span data-stu-id="734cc-131">**CardGames.Card**</span></span>

<span data-ttu-id="734cc-132">`Import-Module``#requires`语句仅导入模块定义的模块函数、别名和变量。</span><span class="sxs-lookup"><span data-stu-id="734cc-132">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="734cc-133">不导入类。</span><span class="sxs-lookup"><span data-stu-id="734cc-133">Classes are not imported.</span></span> <span data-ttu-id="734cc-134">`using module`命令导入模块，同时加载类定义。</span><span class="sxs-lookup"><span data-stu-id="734cc-134">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="734cc-135">示例 3-从程序集加载类</span><span class="sxs-lookup"><span data-stu-id="734cc-135">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="734cc-136">此示例将加载一个程序集，以便可以使用该程序集的类来创建新的 PowerShell 类。</span><span class="sxs-lookup"><span data-stu-id="734cc-136">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="734cc-137">下面的脚本创建一个派生自 **DirectoryContext** 类的新 PowerShell 类。</span><span class="sxs-lookup"><span data-stu-id="734cc-137">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```