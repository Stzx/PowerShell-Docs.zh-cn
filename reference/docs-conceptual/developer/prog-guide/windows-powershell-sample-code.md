---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell 示例代码
description: Windows PowerShell 示例代码
ms.openlocfilehash: da916fa3557f44ecc9126ecef38235109aa391ec
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390127"
---
# <a name="windows-powershell-sample-code"></a>Windows PowerShell 示例代码

Windows PowerShell &reg; 示例通过 Windows SDK 提供。 本部分包含 Windows SDK 示例中包含的示例代码。

> [!NOTE]
> 在安装 Windows SDK 时，将创建一个 **示例** 目录，在该目录中，将提供所有的 Windows PowerShell 示例。 典型的安装目录为 **C:\Program Files\Microsoft SDKs\Windows\v6.0**。 启动 Windows PowerShell 并键入 **"cd Samples\SysMgmt\PowerShell"** 以查找 Windows PowerShell 示例目录。 在本文档中，Windows PowerShell 示例目录称为 **\<PowerShell Samples>** 。

## <a name="sample-code-listing"></a>示例代码列表

|                                    代码示例                                    |                                                                                                                                           描述                                                                                                                                           |
| --------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AccessDbProviderSample01 代码示例](./accessdbprovidersample01-code-sample.md) | 这是 [创建基本 Windows PowerShell 提供程序](./creating-a-basic-windows-powershell-provider.md)中所述的提供程序。                                                                                                                                                            |
| [AccessDbProviderSample02 代码示例](./accessdbprovidersample02-code-sample.md) | 这是 [创建 Windows PowerShell 驱动器提供程序](./creating-a-windows-powershell-drive-provider.md)中所述的提供程序。                                                                                                                                                            |
| [AccessDbProviderSample03 代码示例](./accessdbprovidersample03-code-sample.md) | 这是 [创建 Windows PowerShell 项提供程序](./creating-a-windows-powershell-item-provider.md)中所述的提供程序。                                                                                                                                                              |
| [AccessDbProviderSample04 代码示例](./accessdbprovidersample04-code-sample.md) | 这是 [创建 Windows PowerShell 容器提供程序](./creating-a-windows-powershell-container-provider.md)中所述的提供程序。                                                                                                                                                    |
| [AccessDbProviderSample05 代码示例](./accessdbprovidersample05-code-sample.md) | 这是 [创建 Windows PowerShell 导航提供程序](./creating-a-windows-powershell-navigation-provider.md)中所述的提供程序。                                                                                                                                                  |
| [AccessDbProviderSample06 代码示例](./accessdbprovidersample06-code-sample.md) | 这是 [创建 Windows PowerShell 内容提供程序](./creating-a-windows-powershell-content-provider.md)中所述的提供程序。                                                                                                                                                        |
| [GetProc01 代码示例](./getproc01-code-samples.md)                             | 这是 `Get-Process` [创建第一个 cmdlet](../cmdlet/creating-a-cmdlet-without-parameters.md)中所述的基本 cmdlet 示例。                                                                                                                                                     |
| [GetProc02 代码示例](./getproc02-code-samples.md)                             | 这是 `Get-Process` [添加处理 Command-Line 输入的参数](../cmdlet/adding-parameters-that-process-command-line-input.md)中所述的 cmdlet 示例。                                                                                                                       |
| [GetProc03 代码示例](./getproc03-code-samples.md)                             | 这是 `Get-Process` [添加处理管道输入的参数](../cmdlet/adding-parameters-that-process-pipeline-input.md)中所述的 cmdlet 示例。                                                                                                                               |
| [GetProc04 代码示例](./getproc04-code-samples.md)                             | 这是 `Get-Process` [将非终止错误报告添加到 cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)中所述的 cmdlet 示例。                                                                                                                |
| [GetProc05 代码示例](./getproc05-code-samples.md)                             | 此 `Get-Process` cmdlet 类似于在 [Cmdlet 中添加非终止错误报告](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)中所述的 cmdlet。                                                                                                     |
| [StopProc01 代码示例](./stopproc01-code-samples.md)                           | 这是 `Stop-Process` [创建修改系统的 cmdlet](../cmdlet/creating-a-cmdlet-that-modifies-the-system.md)中所述的 cmdlet 示例。                                                                                                                                    |
| [StopProcessSample04 代码示例](./stopprocesssample04-code-samples.md)         | 这是 `Stop-Process` [将参数集添加到 cmdlet](../cmdlet/adding-parameter-sets-to-a-cmdlet.md)中所述的 cmdlet 示例。                                                                                                                                                      |
| [Runspace01 代码示例](./runspace01-code-samples.md)                           | 下面是 [创建运行指定命令的控制台应用程序](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)中所述的运行空间的代码示例。                                                                                      |
| [Runspace02 代码示例](./runspace02-code-samples.md)                           | 此示例使用 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) 类来 `Get-Process` 同步执行 cmdlet。                                                                                                            |
| [RunSpace03 代码示例](./runspace03-code-samples.md)                           | 下面是 "创建运行指定脚本的控制台应用程序" 中所述的运行空间的代码示例。                                                                                                                                                                         |
| [RunSpace04 代码示例](./runspace04-code-samples.md)                           | 这是一个运行空间的代码示例，它使用 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) 类来执行生成终止错误的脚本。                                                                         |
| [RunSpace05 代码示例](./runspace05-code-sample.md)                             |                                                                                                            |
| [RunSpace06 代码示例](./runspace06-code-sample.md)                             |                                                                                                     |
| [RunSpace07 代码示例](./runspace07-code-sample.md)                             |                                                                                               |
| [RunSpace08 代码示例](./runspace08-code-sample.md)                             |                                                                                              |
| [RunSpace09 代码示例](./runspace09-code-sample.md)                             |                                                                                       |
| [RunSpace10 代码示例](./runspace10-code-sample.md)                             | 这是 Runspace10 示例的源代码，它将 cmdlet 添加到 [Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) ，然后使用修改后的配置信息来创建运行空间。 |

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
