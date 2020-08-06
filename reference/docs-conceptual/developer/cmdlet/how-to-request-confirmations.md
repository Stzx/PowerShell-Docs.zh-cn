---
title: 如何请求确认 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ebe928724f1b750afc11c1e3c1207375f4ec8e42
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784089"
---
# <a name="how-to-request-confirmations"></a>如何请求确认

此示例演示如何调用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)和[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法，以便在执行操作之前请求从用户确认的确认请求的方法的用户确认。

> [!IMPORTANT]
> 有关 Windows PowerShell 如何处理这些请求的详细信息，请参阅[请求确认](./requesting-confirmation-from-cmdlets.md)。

## <a name="to-request-confirmation"></a>请求确认

1. 确保 `SupportsShouldProcess` 将 Cmdlet 特性的参数设置为 `true` 。 函数 (这是 CmdletBinding 属性的参数。 ) 

    ```csharp
    [Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
            SupportsShouldProcess = true)]
    ```

2. 将 `Force` 参数添加到 cmdlet，以使用户能够覆盖确认请求。

    ```csharp
    [Parameter()]
    public SwitchParameter Force
    {
      get { return force; }
      set { force = value; }
    }
    private bool force;
    ```

3. 添加一 `if` 条语句，该语句使用[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法的返回值来确定是否调用了[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的调用程序。）。

4. 添加第二个 `if` 语句，该语句使用[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的返回值和参数的值 `Force` 来确定是否应执行该操作。

## <a name="example"></a>示例

在下面的代码示例中，将从[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)方法的重写中调用 ShouldContinue 方法，并调用[该方法中](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)的方法来调用[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的方法。 但是，也可以从其他输入处理方法中调用这些方法。

```csharp
protected override void ProcessRecord()
{
  if (ShouldProcess("ShouldProcess target"))
  {
    if (Force || ShouldContinue("", ""))
    {
      // Add code that performs the operation.
    }
  }
}
```

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
