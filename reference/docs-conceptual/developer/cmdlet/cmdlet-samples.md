---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 示例
description: Cmdlet 示例
ms.openlocfilehash: 6ee149f611e5af5c45a62363e19e66bf200c0c0a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92668246"
---
# <a name="cmdlet-samples"></a>Cmdlet 示例

本部分介绍了 Windows PowerShell 2.0 SDK 中提供的示例代码。 可以从本部分中的各个主题复制代码，也可以打开随 SDK 一起安装的源文件。 [Windows PowerShell 2.0 软件开发工具包 (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) 提供了每个示例的自述文件、源文件和 Visual Studio 项目文件。 安装 SDK 后，可以在 `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` 文件夹下找到示例。

## <a name="in-this-section"></a>本节内容

[GetProcessSample01 示例](./getprocesssample01-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。

[GetProcessSample02 示例](./getprocesssample02-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。 它提供了 Name 参数，可用于指定要检索的进程。

[GetProcessSample03 示例](./getprocesssample03-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。 它提供了 Name 参数，此参数可以接受管道中的对象，也可以接受属性名与参数名称相同的对象的属性值。

[GetProcessSample04 示例](./getprocesssample04-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。 如果在检索进程时发生错误，则生成一个不可终止的错误。

[GetProcessSample05 示例](./getprocesssample05-sample.md)：此示例展示了 Get-Proc cmdlet 的完整版本。

[StopProcessSample01 示例](./stopprocesssample01-sample.md)：此示例展示了如何编写 cmdlet，以在尝试停止进程之前请求获取用户的反馈，以及如何实现 `PassThru` 参数来指明用户希望此 cmdlet 返回对象。

[StopProcessSample02 示例](./stopprocesssample02-sample.md)：此示例展示了如何编写 cmdlet，以在本地计算机上停止进程时写入调试、详细和警告消息。

[StopProcessSample03 示例](./stopprocesssample03-sample.md)：此示例展示了如何编写其参数有别名且支持通配符的 cmdlet。

[StopProcessSample04 示例](./stopprocesssample04-sample.md)：此示例展示了如何编写 cmdlet，以声明参数集、指定默认参数集并能接受输入对象。

[Events01 示例](./events01-sample.md)：此示例展示了如何创建 cmdlet，以便用户能够注册由 [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher) 引发的事件。 例如，使用此 cmdlet，用户可以注册在特定目录下创建文件时执行的操作。 此示例派生自 [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基类。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
