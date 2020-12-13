---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace03 (C#) 代码示例
description: RunSpace03 (C#) 代码示例
ms.openlocfilehash: cdb08811de13f8bbf5cd91fcbef552c78594b788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653844"
---
# <a name="runspace03-c-code-sample"></a>RunSpace03 (C#) 代码示例

下面是 "创建运行指定脚本的控制台应用程序" 中所述的控制台应用程序的 c # 源代码。 此示例使用 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) 类来执行一个脚本，该脚本通过使用传递到脚本的进程名称列表来检索进程信息。 它演示如何将输入对象传递给脚本，以及如何检索错误对象以及输出对象。

> [!NOTE]
> 您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，下载此示例的 c # 源文件 (runspace03.cs) 。 有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
