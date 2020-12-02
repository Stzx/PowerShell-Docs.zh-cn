---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: b6147b35a8818cf448b1e23f5458550d1c6e5c50
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2020
ms.locfileid: "93199194"
---
# Start-Process

## 摘要
启动本地计算机上的一个或多个进程。

## SYNTAX

### Default（默认值）

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [<CommonParameters>]
```

### UseShellExecute

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [<CommonParameters>]
```

## DESCRIPTION

`Start-Process`Cmdlet 启动本地计算机上的一个或多个进程。 默认情况下， `Start-Process` 将创建一个新进程，该进程继承在当前进程中定义的所有环境变量。

若要指定在进程中运行的程序，请输入可执行文件或脚本文件，或者可使用计算机上的程序打开的文件。 如果指定不可执行文件，则将 `Start-Process` 启动与该文件关联的程序，类似于 `Invoke-Item` cmdlet。

您可以使用的参数 `Start-Process` 指定选项，例如加载用户配置文件、在新窗口中启动进程或使用备用凭据。

## 示例

### 示例 1：启动使用默认值的进程

此示例将启动一个进程，该进程使用 `Sort.exe` 当前文件夹中的文件。 此命令使用所有默认值，包括默认窗口样式、工作文件夹和凭据。

```powershell
Start-Process -FilePath "sort.exe"
```

### 示例 2：打印文本文件

此示例启动打印文件的进程 `C:\PS-Test\MyFile.txt` 。

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### 示例 3：启动一个进程，以对项进行排序并返回到新文件

此示例启动一个进程，该进程对文件中的项进行排序 `Testsort.txt` ，并返回文件中的已排序项 `Sorted.txt` 。 任何错误都将写入 `SortError.txt` 文件。

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

**UseNewEnvironment** 参数指定进程以其自己的环境变量运行。

### 示例 4：在最大化窗口中启动进程

此示例将启动 `Notepad.exe` 进程。 它将最大化窗口并在该进程完成之前一直保留该窗口。

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### 示例5：以管理员身份启动 PowerShell

此示例使用 "以 **管理员身份运行** " 选项启动 PowerShell。

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### 示例 6：使用不同动词来启动进程

此示例显示了如何查找启动进程时可以使用的谓词。 可用谓词由进程中运行的文件的文件扩展名确定。

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

该示例使用 `New-Object` 为 **PowerShell.exe**（在 PowerShell 进程中运行的文件）创建 **ProcessStartInfo** 对象。 **ProcessStartInfo** 对象的 **谓词** 属性显示，您可以将 **Open** 和 **RunAs** 谓词与一起使用 `PowerShell.exe` ，也可以与运行文件的任何进程一起使用 `.exe` 。

### 示例7：指定进程的参数

这两个命令都启动 Windows 命令解释器，并对 `dir` 该文件夹发出命令 `Program Files` 。 由于此文件夹名包含空格，因此值需要用转义引号括起来。
请注意，第一个命令将字符串指定为 **ArgumentList**。 第二个命令是字符串数组。

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## PARAMETERS

### -ArgumentList

指定此 cmdlet 启动进程时要使用的参数或参数值。 参数可以作为单个字符串接受，其中的参数由空格分隔，或者作为以逗号分隔的字符串数组。

如果参数或参数值包含空格，则必须用转义双引号将其引起来。 有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

指定有权执行此操作的用户帐户。 默认情况下，该 cmdlet 使用当前用户的凭据。

键入用户名（如 **User01** 或 **Domain01\User01**），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。 如果键入用户名，系统会提示输入密码。

凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。

> [!NOTE]
> 有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

指定在进程中运行的程序的可选路径和文件名。 输入 `.txt` `.doc` 与计算机上的程序相关联的可执行文件或文档（如或文件）的名称。 此参数是必需的。

如果仅指定文件名，请使用 **WorkingDirectory** 参数来指定路径。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadUserProfile

指示此 cmdlet 为当前用户加载存储在注册表项中的 Windows 用户配置文件 `HKEY_USERS` 。

此参数不会影响 PowerShell 配置文件。 有关详细信息，请参阅 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoNewWindow

在当前控制台窗口中启动新进程。 默认情况下，PowerShell 会打开一个新窗口。

不能在同一命令中使用 **NoNewWindow** 参数和 **WindowStyle** 参数。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

为 cmdlet 启动的每个进程返回一个进程对象。 默认情况下，此 cmdlet 将不产生任何输出。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardError

指定文件。 此 cmdlet 将进程产生的所有错误发送给指定的文件。
输入路径和文件名。 默认情况下，在控制台中显示这些错误。

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardInput

指定文件。 此 cmdlet 从指定文件读取输入。 输入输入文件的路径和文件名。 默认情况下，进程从键盘获取其输入。

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectStandardOutput

指定文件。 此 cmdlet 将进程产生的输出发送给指定的文件。
输入路径和文件名。 默认情况下，在控制台中显示该输出。

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseNewEnvironment

指示此 cmdlet 使用为进程指定的新环境变量。 默认情况下，启动的进程使用继承自父进程的环境变量运行。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Verb

指定此 cmdlet 启动进程时要使用的动词。 可用的动词取决于进程中运行的文件的文件扩展名。

下表列出了适用于某些常用进程文件类型的动词。

| 文件类型 |                动词                |
| --------- | ----------------------------------- |
| .cmd      | Edit、Open、Print、RunAs、RunAsUser |
| .exe      | Open、RunAs、RunAsUser              |
| .txt      | Open、Print、PrintTo                |
| .wav      | 打开、播放                          |

若要查找可用于进程中运行的文件的谓词，请使用 `New-Object` cmdlet 为该文件创建 **ProcessStartInfo** 对象。 可用谓词位于 **ProcessStartInfo** 对象的 **谓词** 属性中。 有关详细信息，请参阅示例。

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait

指示此 cmdlet 等待指定的进程及其子代完成，然后再接受更多输入。 此参数禁止显示命令提示符，或在进程完成之前一直保留窗口。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WindowStyle

指定用于新进程的窗口的状态。 此参数可接受的值包括： **普通**、 **隐藏**、 **最小化** 和 **最大化**。 默认值为 " **正常**"。

不能在同一命令中使用 **WindowStyle** 参数和 **NoNewWindow** 参数。

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkingDirectory

指定新进程的开始位置。 默认值是要启动的可执行文件或文档的位置。 不支持通配符。 路径名不能包含将解释为通配符的字符。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将输入传递给此 cmdlet。

## 输出

### 无、System.Diagnostics.Process

如果指定 PassThru 参数，则此 cmdlet 会生成 **System.Diagnostics.Process**。 否则，此 cmdlet 不返回任何输出。

## 注释

- 此 cmdlet 通过使用 system.exception 类的 **Start** 方法来实现 **。** 有关此方法的详细信息，请参阅 [Process： Start 方法](/dotnet/api/system.diagnostics.process.start#overloads)。

- 在 Windows 上，当你使用 **UseNewEnvironment** 时，新进程将仅开始包含为 **计算机** 范围定义的默认环境变量。 这会影响 `$env:USERNAME` 设置为 **SYSTEM**。 不包含 **用户** 范围中的任何变量。

## 相关链接

[about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[Debug-Process](Debug-Process.md)

[Get-Process](Get-Process.md)

[Start-Service](Start-Service.md)

[Stop-Process](Stop-Process.md)

[Wait-Process](Wait-Process.md)
