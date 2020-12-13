---
ms.date: 09/13/2016
ms.topic: reference
title: 错误报告概念
description: 错误报告概念
ms.openlocfilehash: 353e628c63667a2db010556b2ed9169809b742f4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653037"
---
# <a name="error-reporting-concepts"></a>错误报告概念

Windows PowerShell 提供了两种用于报告错误的机制：一种用于 *终止错误* 的机制，另一种机制用于 *非终止错误*。 你的 cmdlet 正确报告错误，以便运行 cmdlet 的主机应用程序能够以适当的方式做出反应，这一点很重要。

当发生不是或不应允许 cmdlet 继续处理其输入对象的错误时，你的 cmdlet 应调用 [Throwterminatingerror *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) 方法。 当 cmdlet 可以继续处理输入对象时，你的 cmdlet 应调用 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 方法来报告非终止错误。 这两种方法都提供了一个错误记录，主机应用程序可以使用这些错误记录来调查错误的原因。

使用以下准则来确定错误是终止还是非终止错误。

- 错误是终止错误，如果它阻止你的 cmdlet 继续处理当前对象，或不能成功处理任何其他输入对象，而不管它们的内容如何。

- 如果你不希望 cmdlet 继续处理当前对象或任何其他输入对象，而不考虑它们的内容，则会出现错误。

- 如果错误发生在不接受或返回对象的 cmdlet 中，或者出现在接受或仅接受一个对象的 cmdlet 中，则会出现错误。

- 如果你希望 cmdlet 继续处理当前对象和任何其他输入对象，则错误为非终止错误。

- 如果错误是与特定输入对象或输入对象的子集相关，则该错误为非终止错误。

## <a name="see-also"></a>另请参阅

[Throwterminatingerror * 的 *](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

["WriteError"。](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Windows PowerShell 错误记录](./windows-powershell-error-records.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
