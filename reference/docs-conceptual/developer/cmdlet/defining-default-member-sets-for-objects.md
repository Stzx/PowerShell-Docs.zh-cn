---
ms.date: 09/13/2016
ms.topic: reference
title: 定义对象的默认成员集
description: 定义对象的默认成员集
ms.openlocfilehash: 919f7ba65322c6a56a27e046fb211bde151abf7d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653121"
---
# <a name="defining-default-member-sets-for-objects"></a>定义对象的默认成员集

Windows PowerShell 使用 PSStandardMembers 成员集来定义对象的默认属性集。 诸如格式设置 cmdlet 这样的命令可以使用默认属性集来仅显示由属性集定义的属性。 默认属性集包括 DefaultDisplayProperty、使用 defaultdisplaypropertyset 和 DefaultKeyPropertySet。 Windows PowerShell 将忽略所有其他成员集以及添加到 PSStandardMembers 成员集的任何其他属性集。

## <a name="member-set-for-systemdiagnosticsprocess"></a>用于 system.exception 的成员集

在下面的示例中，PSStandardMembers 成员集定义了使用 defaultdisplaypropertyset 属性[集。](/dotnet/api/System.Diagnostics.Process) 此属性集由 [格式列表](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet 使用。

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

以下输出显示了由 [格式列表](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet 返回的默认属性。 只 `Id` `Handles` `CPU` `Name` 为每个进程对象返回、、和属性。

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

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
