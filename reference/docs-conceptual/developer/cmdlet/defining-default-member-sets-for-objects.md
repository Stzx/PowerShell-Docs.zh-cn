---
title: 定义对象的默认成员集 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 80e1f54890d3aac1702414699ead16fcf38271e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774620"
---
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="4828c-102">定义对象的默认成员集</span><span class="sxs-lookup"><span data-stu-id="4828c-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="4828c-103">Windows PowerShell 使用 PSStandardMembers 成员集来定义对象的默认属性集。</span><span class="sxs-lookup"><span data-stu-id="4828c-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="4828c-104">诸如格式设置 cmdlet 这样的命令可以使用默认属性集来仅显示由属性集定义的属性。</span><span class="sxs-lookup"><span data-stu-id="4828c-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="4828c-105">默认属性集包括 DefaultDisplayProperty、使用 defaultdisplaypropertyset 和 DefaultKeyPropertySet。</span><span class="sxs-lookup"><span data-stu-id="4828c-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="4828c-106">Windows PowerShell 将忽略所有其他成员集以及添加到 PSStandardMembers 成员集的任何其他属性集。</span><span class="sxs-lookup"><span data-stu-id="4828c-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="4828c-107">用于 system.exception 的成员集</span><span class="sxs-lookup"><span data-stu-id="4828c-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="4828c-108">在下面的示例中，PSStandardMembers 成员集定义了使用 defaultdisplaypropertyset 属性[集。](/dotnet/api/System.Diagnostics.Process)</span><span class="sxs-lookup"><span data-stu-id="4828c-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="4828c-109">此属性集由[格式列表](/powershell/module/Microsoft.PowerShell.Utility/Format-List)cmdlet 使用。</span><span class="sxs-lookup"><span data-stu-id="4828c-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

```xml
<Type>
  <Name>System.Diagnostics.Process</Name>
  <Members>
    <MemberSet>
     <Name>PSStandardMembers</Name>
     <Members>
       <PropertySet>
         <Name>DefaultDisplayPropertySet</Name>
         <ReferencedProperties>
           <Name>Id</Name>
           <Name>Handles</Name>
           <Name>CPU</Name>
           <Name>Name</Name>
         </ReferencedProperties>
      </PropertySet>
    </Members>
  </MemberSet>
```

<span data-ttu-id="4828c-110">以下输出显示了由[格式列表](/powershell/module/Microsoft.PowerShell.Utility/Format-List)cmdlet 返回的默认属性。</span><span class="sxs-lookup"><span data-stu-id="4828c-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="4828c-111">只 `Id` `Handles` `CPU` `Name` 为每个进程对象返回、、和属性。</span><span class="sxs-lookup"><span data-stu-id="4828c-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

```powershell
Get-Process | format-list
```

```output
Id      : 2036
Handles : 27
CPU     :
Name    : AEADISRV

Id      : 272
Handles : 38
CPU     :
Name    : agrsmsvc
...
```

## <a name="see-also"></a><span data-ttu-id="4828c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4828c-112">See Also</span></span>

[<span data-ttu-id="4828c-113">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4828c-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
