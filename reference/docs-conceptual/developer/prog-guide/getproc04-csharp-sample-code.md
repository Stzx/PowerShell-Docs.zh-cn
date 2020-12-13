---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc04 (C#) 示例代码
description: GetProc04 (C#) 示例代码
ms.openlocfilehash: 80020b60a7ab34caec0c856b9b7d12021f4276b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654388"
---
# <a name="getproc04-c-sample-code"></a>GetProc04 (C#) 示例代码

下面的代码演示了 `Get-Process` 用于报告非终止错误的 cmdlet 的实现。 此实现将调用 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 方法来报告非终止错误。

> [!NOTE]
> 你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件，为此 Get-Proc cmdlet 下载 c # 源文件 (getprov04.cs) 。 有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample04/GetProcessSample04.cs" range="11-98":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
