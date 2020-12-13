---
ms.date: 09/13/2016
ms.topic: reference
title: 请求 Cmdlet 确认
description: 请求 Cmdlet 确认
ms.openlocfilehash: fd869d50b185cb4d38269640df58ec284a32da50
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646415"
---
# <a name="requesting-confirmation-from-cmdlets"></a>请求 Cmdlet 确认

当 cmdlet 要对 Windows PowerShell 环境之外的系统进行更改时，应请求确认。 例如，如果某个 cmdlet 要添加用户帐户或停止进程，则该 cmdlet 会在继续操作之前要求用户确认。 相反，如果 cmdlet 要更改 Windows PowerShell 变量，则 cmdlet 不需要确认。

为了发出确认请求，该 cmdlet 必须指示它支持确认请求，并且它必须调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 和 [ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) (可选的) 方法来显示确认请求消息，然后才能发出确认请求消息。

## <a name="supporting-confirmation-requests"></a>支持确认请求

为了支持确认请求，cmdlet 必须将 `SupportsShouldProcess` cmdlet 特性的参数设置为 `true` 。 这将启用 `Confirm` `WhatIf` Windows PowerShell 提供的和 cmdlet 参数。 `Confirm`参数允许用户控制是否显示确认请求。 此 `WhatIf` 参数允许用户确定该 cmdlet 是否应显示消息或执行其操作。 不要将 `Confirm` 和参数手动添加 `WhatIf` 到 cmdlet。

下面的示例演示支持确认请求的 Cmdlet 特性声明。

```csharp
[Cmdlet(VerbsDiagnostic.Test, "RequestConfirmationTemplate1",
        SupportsShouldProcess = true)]
```

## <a name="calling-the-confirmation-request-methods"></a>调用确认请求方法

在 cmdlet 代码中，先调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法，然后再执行更改系统的操作。 设计 cmdlet，以便在调用返回的值 `false` 时，不会执行操作，并且该 cmdlet 将处理下一个操作。

## <a name="calling-the-shouldcontinue-method"></a>调用 ShouldContinue 方法

大多数 cmdlet 只请求使用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法进行确认。 但某些情况下，可能需要额外的确认。 对于这些情况，请使用对[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)方法的调用对[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)调用进行补充，从而对其进行补充。 这使 cmdlet 或提供程序可以更好地控制对确认提示的所有响应的 **"是"** 的范围。

如果某个 cmdlet 调用 [ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) 方法，则该 cmdlet 还必须提供一个 `Force` 开关参数。 如果用户在 `Force` 用户调用 cmdlet 时指定了，则该 cmdlet 仍应调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)，但它应绕过对 [ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)的调用，但不会调用。

当从非交互式环境中调用[ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)时，将引发异常，而不会提示用户。 添加 `Force` 参数可确保在非交互式环境中调用命令时仍可执行该命令。

下面的示例演示了如何调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 和 [ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)的情况下出现的情况下。

```csharp
if (ShouldProcess (...) )
{
  if (Force || ShouldContinue(...))
  {
     // Add code that performs the operation.
  }
}
```

[ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)调用的行为可能会有所不同，具体取决于调用该 Cmdlet 时使用的环境。 使用前面的准则有助于确保 cmdlet 与其他 cmdlet 的行为一致，而不考虑主机环境。

有关如何调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法的示例，请参阅 [如何请求确认](./how-to-request-confirmations.md)。

## <a name="specify-the-impact-level"></a>指定影响级别

创建 cmdlet 时，指定影响级别 (更改的严重性) 。 为此，请将 `ConfirmImpact` Cmdlet 属性的参数值设置为 "高"、"中" 或 "低"。 `ConfirmImpact`仅当同时指定 cmdlet 的参数时，才可以指定的值 `SupportsShouldProcess` 。

对于大多数 cmdlet，无需显式指定 `ConfirmImpact` 。  请改用参数的默认设置，即 "中"。 如果将设置 `ConfirmImpact` 为 "高"，则默认情况下将确认操作。 为高度中断操作（如重新格式化硬盘卷）保留此设置。

## <a name="calling-non-confirmation-methods"></a>调用非确认方法

如果 cmdlet 或提供程序必须发送消息但未请求确认，则它可以调用以下三种方法。 避免使用 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 方法发送这些类型的消息，因为 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 输出与 Cmdlet 或提供程序的正常输出混在一起，这会使脚本编写变得很困难。

- 若要警告用户并继续操作，cmdlet 或提供程序可以调用 [WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) 方法来调用。

- 若要提供用户可以使用参数检索的其他信息 `Verbose` ，cmdlet 或提供程序可以调用 [WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) 方法。

- 若要为其他开发人员或产品支持提供调试级别的详细信息，cmdlet 或提供程序可以调用 [WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) 方法。 用户可以使用参数检索此信息 `Debug` 。

Cmdlet 和提供程序在尝试执行更改 Windows PowerShell 之外的系统的操作之前，先调用以下方法来请求确认：

- ["Shouldprocess"。](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)

- [Cmdletprovider. "Shouldprocess"](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.ShouldProcess)

它们通过调用 [Shouldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法来执行此操作，这会提示用户根据用户调用命令的方式确认操作。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
