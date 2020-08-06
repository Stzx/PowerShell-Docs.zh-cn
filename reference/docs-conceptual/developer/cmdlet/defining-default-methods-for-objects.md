---
title: 定义对象的默认方法 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 10917de9e897fc1eed362430d63ff5b9cb7e813d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774586"
---
# <a name="defining-default-methods-for-objects"></a>定义对象的默认方法

扩展 .NET Framework 对象时，可以将代码方法和脚本方法添加到对象。
以下各节介绍了用于定义这些方法的 XML。

> [!NOTE]
> 以下部分中的示例来自 `Types.ps1xml` Windows PowerShell 安装目录中的类型文件 (`$PSHOME`) 。 有关详细信息，请参阅[关于 Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)。

## <a name="code-methods"></a>代码方法

代码方法引用 .NET Framework 对象的静态方法。

在下面的示例中，将**ToString**方法添加到[System.Xml.Xml节点](/dotnet/api/System.Xml.XmlNode)类型。 [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)元素将扩展方法定义为代码方法。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)元素指定扩展方法的名称。 [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference)元素指定静态方法。 还可以将[PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)元素添加到[PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)元素的成员。

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

脚本方法定义一个方法，其值为脚本的输出。 在下面的示例中，将**ConvertToDateTime**方法添加到[system.management.managementobject](/dotnet/api/System.Management.ManagementObject)类型。 [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)元素将扩展方法定义为脚本方法。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)元素指定扩展方法的名称。 [脚本](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script)元素指定生成方法值的脚本。 还可以将[PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)元素添加到[PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)元素的成员。

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

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
