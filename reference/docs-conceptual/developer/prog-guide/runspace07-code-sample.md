---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace07 代码示例
description: RunSpace07 代码示例
ms.openlocfilehash: 6e8c9f48a6e9c5a642ecf93bca8a85003b3cfbf8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647399"
---
# <a name="runspace07-code-sample"></a>RunSpace07 代码示例

下面是 [创建将命令添加到管道的控制台应用程序](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)中所述的 Runspace07 示例的源代码。
此示例应用程序创建运行空间，创建管道，将两个命令添加到管道，然后执行管道。 添加到管道的命令是 `Get-Process` 和 `Measure-Object` cmdlet。

> [!NOTE]
> 您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件 (runspace07.cs) 下载 c # 源文件。 有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
