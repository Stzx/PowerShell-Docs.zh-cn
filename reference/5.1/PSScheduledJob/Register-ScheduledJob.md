---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/register-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ScheduledJob
ms.openlocfilehash: 89887474142490a71d372577576fb0059b4ff12e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197784"
---
# Register-ScheduledJob

## 摘要
创建计划作业。

## SYNTAX

### ScriptBlock（默认值）

```
Register-ScheduledJob [-ScriptBlock] <ScriptBlock> [-Name] <String>
 [-Trigger <ScheduledJobTrigger[]>] [-InitializationScript <ScriptBlock>] [-RunAs32]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-ScheduledJobOption <ScheduledJobOptions>] [-ArgumentList <Object[]>] [-MaxResultCount <Int32>]
 [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 文件路径

```
Register-ScheduledJob [-FilePath] <String> [-Name] <String> [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-ArgumentList <Object[]>] [-MaxResultCount <Int32>] [-RunNow] [-RunEvery <TimeSpan>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Register-ScheduledJob`Cmdlet 在本地计算机上创建计划作业。

计划作业是 Windows PowerShell 后台作业，可以按一次性或重复计划自动启动。 计划作业存储在磁盘上并在任务计划程序中注册。
可以在任务计划程序中或使用 Windows PowerShell 中的计划作业 cmdlet 来管理作业。

当计划作业启动时，它会创建计划作业的实例。 除了结果保存在磁盘上以外，计划作业实例与 Windows PowerShell 后台作业相同。 使用作业 cmdlet （如 `Start-Job` 、和） `Get-Job` `Receive-Job` 来启动、查看和获取作业实例的结果。

使用 `Register-ScheduledJob` 创建新的计划作业。 若要指定计划作业运行的命令，请使用 **ScriptBlock** 参数。 若要指定作业运行的脚本，请使用 **FilePath** 参数。

Windows PowerShell 计划作业使用与任务计划程序用于计划任务相同的作业触发器和作业选项。

的 **Trigger** 参数 `Register-ScheduledJob` 可添加一个或多个启动作业的作业触发器。 **Trigger** 参数是可选的，因此你可以在创建计划作业时添加触发器，稍后添加作业触发器，添加 **RunNow** 参数以立即启动作业，使用 `Start-Job` cmdlet 立即启动作业，或将存计划作业保存为其他作业的模板。

使用 **Options** 参数可自定义计划作业的选项设置。 **选项** 参数是可选的，因此你可以在创建计划作业时设置作业选项，或者随时对其进行更改。 由于作业选项设置可能会阻止计划作业运行，因此需检查作业选项并小心设置它们。

`Register-ScheduledJob` 是包含在 Windows PowerShell 中的 **PSScheduledJob** 模块中的作业计划 cmdlet 集合之一。

有关计划作业的详细信息，请参阅 **PSScheduledJob** 模块中的相关文章。
导入 **PSScheduledJob** 模块，然后键入： `Get-Help about_Scheduled*` 或查看 [about_Scheduled_Jobs](./about/about_scheduled_jobs.md)。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：创建计划作业

此示例在本地计算机上创建计划作业。

```powershell
Register-ScheduledJob -Name "Archive-Scripts" -ScriptBlock {
  Get-ChildItem $home\*.ps1 -Recurse |
    Copy-Item -Destination "\\Server\Share\PSScriptArchive"
}
```

`Register-ScheduledJob` 使用 **Name** 参数来创建 **存档脚本** 的计划作业。
**ScriptBlock** 参数运行 `Get-ChildItem` ，以 `$home` 递归方式搜索目录中的 `.ps1` 文件。 `Copy-Item`Cmdlet 将文件复制到由 **Destination** 参数指定的目录中。

因为计划作业不包含触发器，所以它不会自动启动。 你可以使用添加作业触发器 `Add-JobTrigger` ，使用 `Start-Job` cmdlet 按需启动作业，或使用计划作业作为其他计划作业的模板。

### 示例2：使用触发器和自定义选项创建计划作业

此示例显示了如何创建具有作业触发器和自定义作业选项的计划作业。

```powershell
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
$path = "\\Srv01\Scripts\UpdateVersion.ps1"
Register-ScheduledJob -Name "UpdateVersion" -FilePath $path -ScheduledJobOption $O -Trigger $T
```

`$O`变量存储 cmdlet 创建的作业选项对象 `New-ScheduledJobOption` 。 选项将启动计划作业，即使计算机未处于空闲状态，也会唤醒计算机以运行作业（如有必要），并允许作业的多个实例在一个序列中运行。

`$T`变量存储 cmdlet 的结果， `New-JobTrigger` 用于创建作业触发器，该触发器在每个星期一的下午9:00 开始作业。

`$path`变量存储 `UpdateVersion.ps1` 脚本文件的路径。

`Register-ScheduledJob` 使用 **Name** 参数创建 **UpdateVersion** 计划作业。
**FilePath** 参数用于 `$path` 指定作业运行的脚本。 **Get-scheduledjoboption** 参数使用中存储的作业选项 `$O` 。 **Trigger** 参数使用存储在中的作业触发器 `$T` 。

### 示例3：使用哈希表指定触发器和计划作业选项

此示例与示例2中的命令具有相同的效果。 它将创建一个计划作业，使用哈希表指定 **Trigger** 和 **get-scheduledjoboption** 参数的值。 `$O` `$T` 在示例2中定义的和变量将替换为哈希表。

```powershell
$T = @{
  Frequency="Weekly"
  At="9:00PM"
  DaysOfWeek="Monday"
  Interval=2
}
$O = @{
  WakeToRun=$true
  StartIfNotIdle=$false
  MultipleInstancePolicy="Queue"
}
Register-ScheduledJob -Trigger $T -ScheduledJobOption $O -Name UpdateVersion -FilePath "\\Srv01\Scripts\Update-Version.ps1"
```

### 示例4：在远程计算机上创建计划作业

在此示例中，将在多台远程计算机上创建 **energydata.ps1** 计划作业。 计划的作业运行一个脚本，该脚本收集原始数据并将其保存在远程计算机上运行的日志中。

```powershell
$Cred = Get-Credential
$O = New-ScheduledJobOption -WakeToRun -StartIfIdle -MultipleInstancePolicy Queue
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Invoke-Command -ComputerName (Get-Content Servers.txt) -Credential $Cred -ScriptBlock {
  $params = @{
      Name = "Get-EnergyData"
      FilePath = "\\Srv01\Scripts\Get-EnergyData.ps1"
      ScheduledJobOption = $using:O
      Trigger = $using:T
  }
  Register-ScheduledJob @params
}
```

`$Cred`变量为有权创建计划作业的用户在 **PSCredential** 对象中存储凭据。 `$O`变量存储用创建的作业选项 `New-ScheduledJobOption` 。 `$T`变量存储用创建的作业触发器 `New-JobTrigger` 。

该 `Invoke-Command` cmdlet 使用 **ComputerName** 参数从文件获取服务器名称的列表 `Servers.txt` 。 **Credential** 参数获取存储在中的凭据对象 `$Cred` 。
**ScriptBlock** 参数在 `Register-ScheduledJob` 文件中的计算机上运行命令 `Servers.txt` 。

的参数 `Register-ScheduledJob` 由定义 `$params` 。 **Name** 参数指定作业在每台远程计算机上都命名为 **energydata.ps1** 。 **FilePath** 提供脚本的位置 `EnergyData.ps1` 。 该脚本位于可用于所有参与的计算机的文件服务器上。作业按照中的作业触发器指定的计划运行 `$T` ，并在中运行作业选项 `$O` 。

`Register-ScheduledJob @params`命令用脚本块中的参数创建计划作业。

### 示例5：创建在远程计算机上运行脚本的计划作业

此示例在本地计算机上创建 **CollectEnergyData** 计划作业。 作业在多台远程计算机上运行。

```powershell
$Admin = Get-Credential
$T = New-JobTrigger -Weekly -At "9:00 PM" -DaysOfWeek Monday -WeeksInterval 2
Register-ScheduledJob -Name "CollectEnergyData" -Trigger $T -MaxResultCount 99 -ScriptBlock {
  $params = @{
    AsJob = $true
    ComputerName = (Get-Content Servers.txt)
    FilePath = '\\Srv01\Scripts\Get-EnergyData.ps1'
    Credential = $using:Admin
    Authentication = 'CredSSP'
  }
  Invoke-Command @params
}
```

`$Admin`变量为有权在 **PSCredential** 对象中运行命令的用户存储凭据。 `$T`变量存储用创建的作业触发器 `New-JobTrigger` 。

`Register-ScheduledJob`Cmdlet 使用 **Name** 参数在本地计算机上创建 **CollectEnergyData** 计划作业。 **Trigger** 参数指定中的作业触发器 `$T` ， **MaxResultCount** 参数会将保存的结果数增加到99。

**ScriptBlock** 参数定义 `Invoke-Command` 参数 `$params` 。 **AsJob** 参数在本地计算机上创建后台作业对象，即使该 `Energydata.ps1` 脚本在远程计算机上运行也是如此。 **ComputerName** 参数从文件中获取服务器名称的列表 `Servers.txt` 。 **Credential** 参数指定有权在远程计算机上运行脚本的用户帐户。 **身份验证** 参数将值 **CredSSP** 指定为允许委托凭据。

`Invoke-Command @params`用脚本块中的参数运行命令。

## PARAMETERS

### -ArgumentList

指定由 **FilePath** 参数指定的脚本的参数值，或者指定由 **ScriptBlock** 参数指定的命令的值。

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication

指定用于对用户的凭据进行身份验证的机制。 默认值为 Default。

此参数的可接受值为：

- 默认
- 基本
- Credssp
- 摘要
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

有关此参数的值的详细信息，请参阅 [system.management.automation.runspaces.authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。

> [!CAUTION]
> 在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。 此机制增加了远程操作的安全风险。 如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

提示你在运行 cmdlet 之前进行确认。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

指定有权运行计划作业的用户帐户。 默认为当前用户。

键入用户名（如 **User01** 或 **Domain01\User01** ）或输入 PSCredential 对象，例如来自 cmdlet 的一个 **PSCredential** 对象 `Get-Credential` 。 如果只输入用户名，系统会提示输入密码。

凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。

> [!NOTE]
> 有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath

指定计划作业运行的脚本。 输入 `.ps1` 本地计算机上的文件的路径。 若要指定脚本参数的默认值，请使用 **ArgumentList** 参数。
每个 `Register-ScheduledJob` 命令都必须使用 **ScriptBlock** 或 **FilePath** 参数。

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitializationScript

指定 () 的 Windows PowerShell 脚本的完全限定路径 `.ps1` 。 在会话中运行针对后台作业而创建的初始化脚本，然后再运行由 **ScriptBlock** 参数指定的命令或由 **FilePath** 参数指定的脚本。 可使用初始化脚本配置会话，例如添加文件、函数或别名、创建目录或者检查必备项。

若要指定用于运行主作业命令的脚本，请使用 **FilePath** 参数。

如果初始化脚本生成错误，甚至是一个非终止错误，则计划作业的当前实例将不运行，并且其状态为 " **失败** "。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxResultCount

指定为计划作业保留的作业结果项数。 默认值为 32。

Windows PowerShell 将计划作业的每个触发实例的执行历史记录和结果都保存在磁盘上。 此参数的值可确定为此计划作业保存的作业实例结果数。 当作业实例结果数超过此值时，Windows PowerShell 将删除最旧的作业实例结果，以便为最新的作业实例结果腾出空间。

作业执行历史记录和作业结果保存在 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\<JobName>\Output\<Timestamp>`
在其上创建作业的计算机上的目录。 若要查看执行历史记录，请使用 `Get-Job` cmdlet。 若要获取作业结果，请使用 `Receive-Job` cmdlet。

**MaxResultCount** 参数设置计划作业的 ExecutionHistoryLength 属性值。

若要删除当前执行历史记录和作业结果，请使用 cmdlet 的 **ClearExecutionHistory** 参数 `Set-ScheduledJob` 。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name

指定计划作业的名称。 该名称也用于计划作业的所有启动实例。 该名称在计算机上必须唯一。 此参数是必需的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAs32

在 32 位进程中运行计划作业。

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

### -RunEvery

用于指定运行作业的频率。 例如，使用此选项可以每隔15分钟运行一次作业。

```yaml
Type: System.TimeSpan
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNow

运行 cmdlet 后立即启动作业 `Register-ScheduledJob` 。 此参数无需触发任务计划程序在注册后立即运行 Windows PowerShell 脚本，并且不需要用户创建指定开始日期和时间的触发器。

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

### -Get-scheduledjoboption

设置计划作业的选项。 输入 **ScheduledJobOptions** 对象（例如使用 cmdlet 创建的对象） `New-ScheduledJobOption` 或哈希表值。

你可以在注册计划作业时设置计划作业的选项，或者使用 `Set-ScheduledJobOption` 或 `Set-ScheduledJob` cmdlet 来更改选项。

许多选项及其默认值都可确定是否运行计划作业以及运行时间。 在计划某个作业之前，务必检查这些选项。 有关计划作业选项（包括默认值）的说明，请参阅 `New-ScheduledJobOption` 。

若要提交哈希表，请使用以下键。 在下列哈希表中，这些键与其默认值一起显示。

`@{StartIfOnBattery=$False; StopIfGoingOnBattery=$True; WakeToRun=$False; StartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False; ShowInTaskScheduler=$True; RunElevated=$False; RunWithoutNetwork=$False; DoNotAllowDemandStart=$False; MultipleInstancePolicy="IgnoreNew"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock

指定计划作业运行的命令。 将命令括在大括号中， (`{}`) 创建脚本块。 若要指定命令参数的默认值，请使用 **ArgumentList** 参数。

每个 `Register-ScheduledJob` 命令都必须使用 **ScriptBlock** 或 **FilePath** 参数。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trigger

指定计划作业的触发器。 输入一个或多个 **ScheduledJobTrigger** 对象（例如 cmdlet 返回的对象 `New-JobTrigger` ），或者输入一个作业触发器键和值的哈希表。

作业触发器启动计划作业。 该触发器可指定一次性或循环计划作业或者事件，例如在用户进行登录或 Windows 启动时。

**Trigger** 参数为可选参数。 你可以在创建计划作业时添加触发器，使用 `Add-JobTrigger` 、 `Set-JobTrigger` 或 `Set-ScheduledJob` cmdlet 稍后添加或更改作业触发器，或者使用 `Start-Job` cmdlet 立即启动计划作业。 你还可以在没有用作模板的触发器的情况下创建和保留计划作业。

若要提交哈希表，请使用以下键：

- **频率** ：每日、每周、AtStartup、AtLogon
- **位置** ：任何有效的时间字符串
- **DaysOfWeek** -日期名称的任意组合
- **间隔** -任何有效的频率间隔
- **RandomDelay** ：任何有效的 timespan 字符串
- **用户** ：任何有效的用户。 仅与 AtLogon frequency 值一起使用

例如：

`@{Frequency="Once"; At="3am"; DaysOfWeek="Monday", "Wednesday"; Interval=2; RandomDelay="30minutes"; User="Domain1\User01"}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

显示运行该 cmdlet 时会发生什么情况。 cmdlet 未运行。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能将输入向下发送到该 cmdlet。

## 输出

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

## 注释

每个计划作业都保存在 `$home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs` 本地计算机上目录的子目录中。
为计划作业命名子目录，并包含计划作业的 XML 文件以及其执行历史记录的记录。 有关磁盘上计划作业的详细信息，请参阅 [about_Scheduled_Jobs_Advanced](./about/about_scheduled_jobs_advanced.md)。

在 Windows PowerShell 中创建的计划作业将显示在 "任务计划程序" `Library\Microsoft\Windows\PowerShell\ScheduledJobs` 文件夹任务计划程序中。 你可以使用任务计划程序查看和编辑计划作业。

你可以使用任务计划程序、 **schtasks.exe** 命令行工具和任务计划程序 cmdlet 来管理你使用计划作业 cmdlet 创建的计划作业。 但是，不能使用计划的作业 cmdlet 来管理在任务计划程序中创建的任务。

如果计划作业命令失败，则 Windows PowerShell 将返回一条错误消息。 但是，如果作业在任务计划程序尝试运行它时失败，则 Windows PowerShell 将无法使用此错误。

如果计划作业没有运行，请使用以下方法来查找原因：

- 验证作业触发器是否设置正确。
  - 验证是否满足作业选项中设置的条件。
- 验证运行作业的用户帐户是否有权运行该作业中的命令或脚本。
- 检查任务计划程序历史记录中是否存在错误。
- 检查任务计划程序事件日志中是否存在错误。

有关详细信息，请参阅 [about_Scheduled_Jobs_Troubleshooting](./about/about_scheduled_jobs_troubleshooting.md)。

## 相关链接

[Add-JobTrigger](Add-JobTrigger.md)

[Disable-JobTrigger](Disable-JobTrigger.md)

[Disable-ScheduledJob](Disable-ScheduledJob.md)

[Enable-JobTrigger](Enable-JobTrigger.md)

[Enable-ScheduledJob](Enable-ScheduledJob.md)

[Get-JobTrigger](Get-JobTrigger.md)

[Get-ScheduledJob](Get-ScheduledJob.md)

[Get-ScheduledJobOption](Get-ScheduledJobOption.md)

[New-JobTrigger](New-JobTrigger.md)

[New-ScheduledJobOption](New-ScheduledJobOption.md)

[Register-ScheduledJob](Register-ScheduledJob.md)

[Remove-JobTrigger](Remove-JobTrigger.md)

[Set-JobTrigger](Set-JobTrigger.md)

[Set-ScheduledJob](Set-ScheduledJob.md)

[Set-ScheduledJobOption](Set-ScheduledJobOption.md)

[Unregister-ScheduledJob](Unregister-ScheduledJob.md)
