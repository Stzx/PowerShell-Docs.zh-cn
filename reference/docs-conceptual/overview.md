---
ms.date: 05/22/2020
keywords: powershell,cmdlet
title: 什么是 PowerShell？
description: 本文介绍 PowerShell 脚本编写环境及其功能。
ms.openlocfilehash: 91fc580af9a3adf43a24c40b4aaf3f1843882705
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500770"
---
# <a name="what-is-powershell"></a>什么是 PowerShell？

PowerShell 是一种跨平台的任务自动化和配置管理框架，由命令行管理程序和脚本语言组成。 与大多数接受并返回文本的 shell 不同，PowerShell 构建在 .NET 公共语言运行时 (CLR) 的基础之上，接受并返回 .NET 对象。 这一根本上的改变引入了全新的自动化工具和方法。

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a>输出是基于对象的

不同于传统的命令行接口，PowerShell cmdlet 旨在处理对象。
对象是结构化信息，不仅仅是屏幕上出现的字符串。 命令输出会始终包含你在需要时可使用的额外信息。

如果以前使用过文本处理工具来处理数据，那么在 PowerShell 中使用时，会发现它们的行为有所不同。 在大多数情况下，不需要文本或文本处理工具来提取特定信息。 可以使用标准 PowerShell 对象语法直接访问数据的各部分。

## <a name="the-command-family-is-extensible"></a>命令系列是可扩展的

接口（如 `cmd.exe`）不提供可直接扩展内置命令集的方法。 可创建在 `cmd.exe` 中运行的外部命令行工具。 但这些外部工具不包含服务，例如帮助集成。 `cmd.exe` 不会自动知道这些外部工具是有效命令。

PowerShell 中的命令被称为 cmdlet。 可单独使用每个 cmdlet，但只有结合使用它们来执行复杂的任务时，才能发挥它们的作用。 与许多 Shell 类似，可通过 PowerShell 访问计算机上的文件系统。 通过 PowerShell 提供程序，可像访问文件系统一样轻松访问其他数据存储（例如注册表和证书存储）。

可使用编译的代码或脚本自行创建 cmdlet 和函数模块。 模块可以向 shell 添加 cmdlet 和提供程序。 PowerShell 还支持类似于 UNIX shell 脚本和 `cmd.exe` 批处理文件的脚本。

## <a name="support-for-command-aliases"></a>支持命令别名

PowerShell 支持别名以通过备用名称引用命令。 别名允许具有其他 Shell 经验的用户使用其已知的常见命令名称在 PowerShell 中执行类似操作。

别名将新名称与其他命令关联。 例如，PowerShell 具有名为 `Clear-Host` 的内部函数，该函数清空输出窗口。 可以在命令提示符下键入 `cls` 或 `clear` 别名。 PowerShell 解释这些别名并运行 `Clear-Host` 函数。

此功能可帮助用户了解 PowerShell。 首先，大多数 `cmd.exe` 和 Unix 用户都要使用大量命令，用户通过名称已经了解这些命令。 PowerShell 等效项可能不会产生相同的结果。 但是，结果非常接近，用户可以在不知道 PowerShell 命令名称的情况下完成工作。 在学习新的命令 shell 时，“肌肉记忆”是另一个令人沮丧的主要原因。 如果你已使用 `cmd.exe` 多年，则可能会条件反射地键入 `cls` 命令来清除屏幕。 如果没有 `Clear-Host` 的别名，则会收到一条错误消息，并且不知道如何操作才能清除输出。

## <a name="powershell-handles-console-input-and-display"></a>PowerShell 处理控制台输入和显示

当你键入命令时，PowerShell 会始终直接处理命令行输入。 PowerShell 还会对你在屏幕上看到的输出进行格式设置。 这种差异非常重要，因为它减少了每个 cmdlet 必须完成的工作量。 它确保你始终可以使用任何 cmdlet 以相同的方式执行操作。 Cmdlet 开发人员无需编写代码来分析命令行参数或格式化输出。

传统的命令行工具有自己的用于请求和显示帮助的方案。 某些命令行工具使用 `/?` 来触发帮助显示；而其他一些使用 `-?`、`/H`，甚至 `//`。 有些工具会在 GUI 窗口而不是在控制台显示区域显示帮助。 如果你使用的参数有误，该工具可能会忽略你键入的内容并自动开始执行任务。
由于 PowerShell 会自动分析和处理命令行，因此 `-?` 参数始终表示“向我显示此命令的帮助”。

> [!NOTE]
> 如果在 PowerShell 中运行图形应用程序，将随即打开该应用程序的窗口。
> PowerShell 仅会在处理你提供的命令行输入或返回到控制台窗口中的应用程序输出时才会进行干预。 它不会内在地影响应用程序的工作方式。

## <a name="powershell-has-a-pipeline"></a>PowerShell 有一个管道

管道可能是命令行界面中使用的最有价值的概念。 如果使用得当，管道可减少使用复杂命令的工作量，并让你更轻松地查看工作流程。 管道中的每个命令将其输出逐项传递给下一个命令。 命令不必一次处理多个项目。 这样就减少了资源消耗，并能立即获取输出。

用于管道的符号类似于其他 shell 中使用的符号。 初看起来 PowerShell 中管道的不同之处可能并不明显。 尽管你会在屏幕上看到文本，但 PowerShell 通过管道在命令之间传递对象，而不是文本。

例如，如果使用 `Out-Host` cmdlet 来强制逐页显示来自于另一个命令的输出，那么这一输出看起来就像分页显示在屏幕上的普通文本：

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

分页还会降低 CPU 利用率，因为准备好显示完整页面时，会转为处理 `Out-Host` cmdlet。 管道中位于前面的 cmdlet 暂停执行，直到输出的下一页可用。

### <a name="objects-in-the-pipeline"></a>管道中的对象

在 PowerShell 中运行 cmdlet 时，可以看到文本输出，因为必须在控制台窗口中以文本形式表示对象。 文本输出可能不会显示输出的对象的所有属性。

例如，请考虑 `Get-Location` cmdlet。 文本输出是信息摘要，而非 `Get-Location` 返回的对象的完整表示形式。 输出中的标题通过格式化屏幕显示数据的过程添加。

```powershell
Get-Location
```

```Output
Path
----
C:\
```

通过管道将输出传递到 `Get-Member` cmdlet 后，可获得有关 `Get-Location` 返回的对象的信息。

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

`Get-Location` 返回 PathInfo 对象，其中包含当前路径和其他信息。

## <a name="built-in-help-system"></a>内置帮助系统

与 `man` 页面类似，PowerShell 包含了详细的帮助文章，其中解释了 PowerShell 概念和命令语法。 使用 [Get-Help][] cmdlet 在命令提示符下显示这些文章，或在 PowerShell 文档中在线查看这些文章的最近更新版本。

## <a name="next-steps"></a>后续步骤

要详细了解 PowerShell，请查看此网站的“学习 PowerShell”部分。

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help
