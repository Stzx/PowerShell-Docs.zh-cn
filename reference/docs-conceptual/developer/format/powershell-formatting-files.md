---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell 格式设置文件
description: Windows PowerShell 格式设置文件
ms.openlocfilehash: 7fa58a3463dc4b2a23d38d161d83387744334d44
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666359"
---
# <a name="windows-powershell-formatting-files"></a>Windows PowerShell 格式设置文件

Windows PowerShell 提供多个格式化文件 ( # B0 xml) 位于安装目录中 (`$pshome`) 。 其中每个文件定义一组特定 .NET 对象的默认显示。 永远不应更改这些文件。 但是，可以将它们用作创建自己的自定义格式设置文件的参考。

`Certificate.Format.ps1xml` 定义证书存储区中的对象的显示方式，如 x.509 证书和证书存储。

`DotNetTypes.Format.ps1xml` 定义杂项 .NET 对象的显示，例如 CultureInfo、FileVersionInfo 和 EventLogEntry 对象。

`FileSystem.Format.ps1xml` 定义文件系统对象（如文件和目录对象）的显示。

`Help.Format.ps1xml` 定义 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet 使用的不同视图，例如详细、完整、参数和示例视图。

`PowerShellCore.Format.ps1xml` 定义由 Windows PowerShell 核心 cmdlet 生成的对象的显示，例如，由 " [获取成员](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) " 和 " [历史记录](/powershell/module/Microsoft.PowerShell.Core/Get-History) " cmdlet 返回的对象。

`PowerShellTrace.Format.ps1xml` 定义跟踪对象的显示，如 [trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) cmdlet 生成的对象。

`Registry.Format.ps1xml` 定义注册表对象（如 key 和 entry 对象）的显示。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](../cmdlet/writing-a-windows-powershell-cmdlet.md)
