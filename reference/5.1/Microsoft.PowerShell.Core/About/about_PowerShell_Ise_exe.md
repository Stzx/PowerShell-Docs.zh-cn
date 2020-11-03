---
description: 介绍如何使用 PowerShell_Ise.exe 命令行工具。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200265"
---
# <a name="about-powershell-iseexe"></a>关于 PowerShell Ise.exe

## <a name="short-description"></a>简短说明

介绍如何使用 PowerShell_Ise.exe 命令行工具。

## <a name="long-description"></a>详细说明

PowerShell_Ise.exe 在 (ISE) 会话中启动 Windows PowerShell 集成脚本环境。 可以在 Cmd.exe 和 Windows PowerShell 中运行。

若要运行 PowerShell_ISE.exe，请键入 PowerShell_ISE.exe、PowerShell_ISE 或 ISE。

## <a name="syntax"></a>SYNTAX

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a>PARAMETERS

### <a name="-file"></a>-File

在 Windows PowerShell ISE 中打开指定的文件。 参数名称 ( "-File" ) 是可选的。 若要列出多个文件，请输入一个用引号引起来的文本字符串。 使用逗号分隔字符串中的文件名。

例如：

PowerShell_ISE 文件 "File1.ps1、File2.ps1 File3.xml"。

文件名称之间的空格允许在 Windows PowerShell 中使用，但可能无法由其他程序（如 Cmd.exe）正确解释。

可以使用此参数打开任何文本文件，包括 Windows PowerShell 脚本文件和 XML 文件。

### <a name="-mta"></a>-Mta

使用多线程单元启动 Windows PowerShell ISE。 此参数是在 Windows PowerShell 3.0 中引入的。 单线程单元 (STA) 是默认值。

### <a name="-noprofile"></a>-NoProfile

不运行 Windows PowerShell 配置文件。 默认情况下，Windows PowerShell 配置文件在每个会话中运行。

编写共享内容（如将在具有不同配置文件的系统上运行的函数和脚本）时，建议使用此参数。
有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。

### <a name="-help---"></a>-Help-?,/？

显示 PowerShell_ISE.exe 的帮助。

## <a name="examples"></a>示例

这些命令启动 Windows PowerShell ISE。 这两个命令是等效的，因此可以互换使用。

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

这些命令将在 Windows PowerShell ISE 中打开 Get-Profile.ps1 脚本。
这两个命令是等效的，因此可以互换使用。

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

此命令打开 Windows PowerShell ISE 中的 Get-Backups.ps1 和 Get-BackupInstance.ps1 脚本。 若要打开多个文件，请使用逗号分隔文件名，并将整个文件名值用引号引起来。

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

此命令启动不带配置文件的 Windows PowerShell ISE。

```
PS C:> ISE -NoProfile
```

此命令获取 PowerShell_ISE.exe 的帮助。

```
PS C:> ISE -help
```

## <a name="see-also"></a>另请参阅

[about_PowerShell.exe](about_PowerShell_exe.md)

[about_Windows_PowerShell_ISE](about_Windows_PowerShell_ISE.md)

[Windows PowerShell 集成脚本环境 (ISE)](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
