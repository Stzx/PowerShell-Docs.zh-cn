---
ms.date: 09/13/2016
ms.topic: reference
title: 请求确认的用户
description: 请求确认的用户
ms.openlocfilehash: 58dbe27635ca38886b728f585fec063645b3597e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646298"
---
# <a name="users-requesting-confirmation"></a>请求确认的用户

`true`为 `SupportsShouldProcess` Cmdlet 特性声明的参数指定值时，用户可以 `Confirm` 在命令提示符处指定参数。

在默认的环境中，用户可以指定 `Confirm` 参数，或在 `"-Confirm:$true` 调用 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 方法时请求进行确认。 这会绕过 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 确认请求，即使对于影响很大的操作也是如此。

如果 `Confirm` 未指定，则当[](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) `$ConfirmPreference` 首选项变量等于或大于 `ConfirmImpact` Cmdlet 或提供程序的设置时，ShouldProcess 调用请求确认。 的默认设置 `$ConfirmPreference` 为 "高"。 因此，在默认环境中，只有指定了影响很大的操作请求确认的 cmdlet 和提供程序。

如果 `Confirm` 为 false 或 `"-Confirm:$false` 指定了，则 [ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) 调用请求从用户处进行确认，并且 `$ConfirmPreference` 忽略 shell 变量。

## <a name="remarks"></a>备注

- 对于指定但不指定（但不会）的 cmdlet 和提供程序， `SupportsShouldProcess` `ConfirmImpact` 这些操作将作为 "中影响" 操作处理，默认情况下不会提示。 其影响级别小于 `$ConfirmPreference` 首选项变量的默认设置。

- 如果用户指定了 `Verbose` 参数，则这些参数会得到通知，即使未提示进行确认。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
