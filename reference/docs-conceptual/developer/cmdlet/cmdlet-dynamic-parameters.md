---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 动态参数
description: Cmdlet 动态参数
ms.openlocfilehash: b44dda2354e8b689e419c7bf4deefadfc4edcb07
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653427"
---
# <a name="cmdlet-dynamic-parameters"></a>Cmdlet 动态参数

Cmdlet 可以定义在特殊条件下可用于用户的参数，如其他参数的参数是特定值时。 这些参数是在运行时添加的，它们被称为动态参数，因为它们仅在需要时才添加。 例如，你可以设计仅在指定了特定交换机参数时添加多个参数的 cmdlet。

> [!NOTE]
> 提供程序和 PowerShell 函数也可以定义动态参数。

## <a name="dynamic-parameters-in-powershell-cmdlets"></a>PowerShell cmdlet 中的动态参数

PowerShell 在其提供程序 cmdlet 中使用动态参数。 例如， `Get-Item` `Get-ChildItem` 当 **Path** 参数指定了 **证书** 提供程序路径时，和 Cmdlet 会在运行时添加 **CodeSigningCert** 参数。 如果 **path** 参数指定了不同提供程序的路径，则 **CodeSigningCert** 参数不可用。

下面的示例演示如何在运行时在运行时添加 **CodeSigningCert** 参数 `Get-Item` 。

在此示例中，PowerShell 运行时添加了参数，且 cmdlet 成功。

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

在此示例中，指定了一个 **FileSystem** 驱动器并返回错误。 错误消息指示找不到 **CodeSigningCert** 参数。

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a>支持动态参数

若要支持动态参数，必须在 cmdlet 代码中包含以下元素。

### <a name="interface"></a>接口

[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters)）。
此接口提供检索动态参数的方法。

例如：

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a>方法

[IDynamicParameters. GetDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)。
此方法检索包含动态参数定义的对象。

例如：

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

### <a name="class"></a>类

定义要添加的动态参数的类。 此类必须包括每个参数的 **参数** 属性以及 cmdlet 所需的任何可选 **别名** 和 **验证** 属性。

例如：

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

有关支持动态参数的 cmdlet 的完整示例，请参阅 [如何声明动态参数](./how-to-declare-dynamic-parameters.md)。

## <a name="see-also"></a>请参阅

[System.web. IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters)

[IDynamicParameters. GetDynamicParameters。](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[如何声明动态参数](./how-to-declare-dynamic-parameters.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
