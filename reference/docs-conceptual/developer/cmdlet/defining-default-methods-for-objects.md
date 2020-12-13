---
ms.date: 09/13/2016
ms.topic: reference
title: 定义对象的默认方法
description: 定义对象的默认方法
ms.openlocfilehash: c65ca91a7038f32d8c3ef62cfe7881e5ad4dba5a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355521"
---
# <a name="defining-default-methods-for-objects"></a>定义对象的默认方法

扩展 .NET Framework 对象时，可以将代码方法和脚本方法添加到对象。
以下各节介绍了用于定义这些方法的 XML。

> [!NOTE]
> 以下部分中的示例来自 `Types.ps1xml` Windows PowerShell 安装目录中的类型文件 (`$PSHOME`) 。 有关详细信息，请参阅 [关于 Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)。

## <a name="code-methods"></a>代码方法

代码方法引用 .NET Framework 对象的静态方法。

在下面的示例中，将 **ToString** 方法添加到 [System.Xml.Xml节点](/dotnet/api/System.Xml.XmlNode) 类型。 [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)元素将扩展方法定义为代码方法。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name)元素指定扩展方法的名称。 [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference#System_Management_Automation_PSCodeMethod_CodeReference)元素指定静态方法。 还可以将 [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod) 元素添加到 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) 元素的成员。

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodeMethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a>脚本方法

脚本方法定义一个方法，其值为脚本的输出。 在下面的示例中，将 **ConvertToDateTime** 方法添加到 [system.management.managementobject](/dotnet/api/System.Management.ManagementObject) 类型。 [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod)元素将扩展方法定义为脚本方法。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name#System_Management_Automation_PSMemberInfo_Name)元素指定扩展方法的名称。 [脚本](/dotnet/api/system.management.automation.psscriptmethod.script#System_Management_Automation_PSScriptMethod_Script)元素指定生成方法值的脚本。 还可以将 [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod) 元素添加到 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset) 元素的成员。

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a>请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
