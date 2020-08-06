---
title: 非终止错误 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d74c248e6ef54151400b8060d76524e89d87352c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786554"
---
# <a name="non-terminating-errors"></a>非终止错误

本主题讨论用于报告非终止错误的方法。 还介绍了如何从 cmdlet 内调用方法。

当发生非终止错误时，此 cmdlet 应通过调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法报告此错误。 当 cmdlet 报告非终止错误时，该 cmdlet 可以继续对该输入对象和其他传入管道对象执行操作。 如果该 cmdlet 调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法，则该 cmdlet 可以编写一个错误记录，用于描述导致非终止错误的情况。 有关错误记录的详细信息，请参阅[Windows PowerShell 错误记录](./windows-powershell-error-records.md)。

Cmdlet 可以根据需要从其输入处理方法中调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 。 但是，cmdlet 只能从名为 BeginProcessing、ProcessRecord[或](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)输入处理方法的线程调用[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)（可能为一个类型为[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)的方法）的类型的调用程序中的方法的调用程序。 不要从另一个线程调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) ，则为。 而是将错误传递回主线程。

## <a name="see-also"></a>另请参阅

["WriteError"。](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

["BeginProcessing"。](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

["ProcessRecord"。](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.web. EndProcessing. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[Windows PowerShell 错误记录](./windows-powershell-error-records.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
