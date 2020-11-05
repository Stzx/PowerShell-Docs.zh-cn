---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 使用 Windows PowerShell 2.0 引擎
description: Windows PowerShell 2.0 引擎仅在当前脚本或主机程序无法运行时使用，因为必须在进行修改后，为 Windows PowerShell 2.0 编写并通过 CLR 2.0 编译的主机程序才能运行。
ms.openlocfilehash: 214b87b7314f31974801bb07f98ddea3b68008f0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664001"
---
# <a name="using-the-windows-powershell-20-engine"></a>使用 Windows PowerShell 2.0 引擎

Windows PowerShell 旨在能够与早期版本向后兼容。 为 Windows PowerShell 2.0 编写的 cmdlet、提供程序、管理单元、模块以及脚本无需更改，即可在较新版本 Windows PowerShell 中运行。 但 Microsoft .NET Framework 4 更改了运行时激活策略。
必须在通过 CLR 4.0（或更高版本）编译的新版本 Windows PowerShell 中进行修改后，为 Windows PowerShell 2.0 编写并通过公共语言运行时 (CLR) 2.0 编译的 Windows PowerShell 主机程序才能运行。

Windows PowerShell 2.0 引擎仅在当前脚本或主机程序无法运行时使用，因为它与 Windows PowerShell 5.1 不兼容。 这种情况的示例包括早期版本的 Exchange 或 SQL Server 模块。 这种情况很少见。

许多需要 Windows PowerShell 2.0 引擎的程序将自动启动。 这些说明适用于极少数需要手动启动该引擎的情况。

## <a name="deprecation-and-security-concerns"></a>弃用和安全问题

Windows PowerShell 2.0 在 2017 年 8 月已弃用。 有关详细信息，请参阅 PowerShell 博客上的[公告][]。

Windows PowerShell 2.0 缺少版本 3、4 和 5 中新增的大量增强功能和安全功能。 我们强烈建议用户在可以提供帮助的情况下不要使用它。 有关详细信息，请参阅 [Shell 和脚本语言安全性比较][]和 [PowerShell ♥ 蓝队][blueteam]。

## <a name="installing-and-enabling-required-programs"></a>安装和启用必需程序

启动 Windows PowerShell 2.0 引擎之前，请先启用 Windows PowerShell 2.0 引擎和具有 Service Pack 1 的 Microsoft.NET Framework 3.5。 有关说明，请参阅[安装 Windows PowerShell][]。

安装了 Windows Management Framework 3.0 或更高版本的系统上具备所有必需组件。 无需进行任何其他配置。 有关安装 Windows Management Framework 的信息，请参阅[安装和配置 WMF][]。

## <a name="how-to-start-the-windows-powershell-20-engine"></a>如何启动 Windows PowerShell 2.0 引擎

启动 Windows PowerShell 时，默认启动最新版本。 要使用 Windows PowerShell 2.0 引擎启动 Windows PowerShell，请使用 `PowerShell.exe` 的版本参数。 你可以在任何命令提示符（包括 Windows PowerShell 和 Cmd.exe）处运行该命令。

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a>如何使用 Windows PowerShell 2.0 引擎启动远程会话

要在远程会话中运行 Windows PowerShell 2.0 引擎，请在加载 Windows PowerShell 2.0 引擎的远程计算机上创建会话配置（也称为“终结点”）。 会话配置保存在远程计算机上，并且任何已获得授权的用户都可以将其用于创建使用 Windows PowerShell 2.0 引擎的会话。

这是一项高级任务，通常由系统管理员执行。

以下过程使用 [Register-PSSessionConfiguration][] cmdlet 的 **PSVersion** 参数来创建使用 Windows PowerShell 2.0 引擎的会话配置。 你还可以使用 [New-PSSessionConfigurationFile][] cmdlet 的 **PowerShellVersion** 参数为加载 Windows PowerShell 2.0 引擎的会话创建会话配置文件，此外，你可以使用 [Set-PSSessionConfiguration][] 参数的 **PSVersion** 参数将会话配置更改为使用 Windows PowerShell 2.0 引擎。

有关会话配置文件的详细信息，请参阅 [about_Session_Configuration_Files][]。
有关设置和安全性等会话配置的信息，请参阅 [about_Session_Configurations][]。

### <a name="to-start-a-remote-windows-powershell-20-session"></a>启动远程 Windows PowerShell 2.0 会话

1. 要创建需要 Windows PowerShell 2.0 引擎的会话配置，请使用 `Register-PSSessionConfiguration` cmdlet 的 PSVersion 参数，其值为 `2.0`。
   在计算机上的连接的“服务器端”或接收端运行此命令。

   下面的示例命令在 Server01 计算机上创建 PS2 会话配置。 要运行此命令，请使用“以管理员身份运行”选项启动 Windows PowerShell。

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. 要在使用 PS2 会话配置的 Server01 计算机上创建会话，请使用创建远程会话的 cmdlet（例如 `New-PSSession cmdlet）的 ConfigurationName 参数。

   使用会话配置的会话启动时，Windows PowerShell 2.0 引擎会自动加载到该会话中。

   下面的命令在使用 PS2 会话配置的 Server01 计算机上启动一个会话。 该命令将该会话保存在 `$s` 变量中。

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a>如何使用 Windows PowerShell 2.0 引擎启动后台作业

若要使用 Windows PowerShell 2.0 引擎启动后台作业，请使用 [Start-Job][] cmdlet 的 **PSVersion** 参数。

下面的命令使用 Windows PowerShell 2.0 引擎启动后台作业

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

有关后台作业的详细信息，请参阅 [about_Jobs][]。

<!-- link references -->
[公告]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[Shell 和脚本语言安全性比较]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[安装 Windows PowerShell]: install/Installing-Windows-PowerShell.md
[安装和配置 WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfigurationFile
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
