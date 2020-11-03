---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 99dbdc84430c0a8b5cf505a22b139cd07236e160
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197772"
---
# Set-ScheduledJob

## 摘要
更改计划作业。

## SYNTAX

### ScriptBlock（默认值）

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### 文件路径

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### 执行

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
**Set-ScheduledJob** cmdlet 更改计划作业的属性，例如作业运行的命令或运行该作业时所需的凭据。
它还可用于清除计划作业的执行历史记录。

若要使用此 cmdlet，请首先使用 Get-ScheduledJob cmdlet 来获取计划作业。
然后，通过管道将计划作业传递给 **get-scheduledjob** ，或将作业保存在变量中，并使用 *InputObject* 参数来标识作业。
使用 **Set-ScheduledJob** 的剩余参数，以更改作业属性或清除执行历史记录。

尽管可以使用 **get-scheduledjob** 更改计划作业的触发器和选项，但 Get-jobtrigger、get-jobtrigger 和 Set-ScheduledJobOption cmdlet 提供了更简单的方法来完成这些任务。
若要创建新的计划作业，请使用 Register-ScheduledJob cmdlet。

**Get-scheduledjob** 的 *Trigger* 参数可添加一个或多个启动作业的作业触发器。
*Trigger* 参数是可选的，因此你可以在创建计划作业时添加触发器，稍后添加作业触发器，添加 *RunNow* 参数以立即启动作业，使用 Start-Job cmdlet 随时启动作业，或将存计划作业保存为其他作业的模板。

**Get-scheduledjob** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：更改作业运行的脚本

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

此示例显示了如何更改在计划作业中运行的脚本。

第一个命令使用 Get-ScheduledJob cmdlet 获取清单计划作业。
此输出显示该作业运行 Get-Inventory.ps1 脚本。

此命令不是必需的；包含它只是为了显示脚本更改的效果。

### 示例2：删除计划作业的执行历史记录

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

此命令删除 BackupArchive 计划作业的当前执行历史记录以及保存的作业结果。

该命令使用 Get-ScheduledJob cmdlet 来获取 BackupArchive 计划作业。
管道运算符 (|) 将该作业发送到 **Set-ScheduledJob** cmdlet 以更改它。
**Get-scheduledjob** Cmdlet 使用 *ClearExecutionHistory* 参数来删除执行历史记录和保存的结果。

有关计划作业的执行历史记录和保存的作业结果的详细信息，请参阅 about_Scheduled_Jobs。

### 示例3：更改远程计算机上的计划作业

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

此命令更改 Server01 和 Server02 计算机上所有计划作业中的初始化脚本。

该命令使用 Invoke-Command cmdlet 在 Server01 和 Server02 计算机上运行命令。

远程命令以获取计算机上所有计划作业的 Get-ScheduledJob 命令开头。
计划的作业将通过管道传递给 **get-scheduledjob** cmdlet，该 cmdlet 会将初始化脚本更改为 SetForRun.ps1。

## PARAMETERS

### -ArgumentList
指定由 *FilePath* 参数指定的脚本的参数值，或者指定由 *ScriptBlock* 参数指定的命令的值。

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authentication
指定用于对用户的凭据进行身份验证的机制。
此参数的可接受值为：

- 默认
- 基本
- Credssp
- 摘要
- Kerberos
- Negotiate
- NegotiateWithImplicitCredential

默认值为 Default。
有关此参数的值的详细信息，请参阅 MSDN 库中的 [System.management.automation.runspaces.authenticationmechanism 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 。

警告：凭据安全支持提供程序 (CredSSP) 身份验证，其中用户的凭据将传递给要进行身份验证的远程计算机，其适用于需要在多个资源（例如访问远程网络共享）上进行身份验证的命令。
此机制增加了远程操作的安全风险。
如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClearExecutionHistory
删除计划作业的当前执行历史记录以及保存的结果。

作业执行历史记录和作业结果都将随计划作业一同保存在创建该作业的计算机上的 $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs 目录中。
若要查看执行历史记录，请使用 Get-Job cmdlet。
若要获取作业结果，请使用 Receive-Job cmdlet。

此参数不会影响任务计划程序写入 Windows 事件日志的事件，也不会阻止 Windows PowerShell 保存作业结果。
若要管理保存的作业结果数，请使用 *MaxResultCount* 参数。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
指定有权运行计划作业的用户帐户。
默认为当前用户。

键入用户名（如 User01 或 Domain01\User01）或输入 **PSCredential** 对象，例如 Get-Credential cmdlet 中的一个。
如果仅输入用户名，则将提示你输入密码。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilePath
指定计划作业运行的脚本。
在本地计算机上输入指向 .ps1 文件的路径。
若要指定脚本参数的默认值，请使用 *ArgumentList* 参数。
每个计划作业都必须具有 *ScriptBlock* 或 *FilePath* 值。

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitializationScript
指定指向 Windows PowerShell 脚本 (.ps1) 的完全限定路径。
在会话中运行针对后台作业而创建的初始化脚本，然后再运行由 *ScriptBlock* 参数指定的命令或由 *FilePath* 参数指定的脚本。
可使用初始化脚本配置会话，例如添加文件、函数或别名、创建目录或者检查必备项。

若要指定用于运行主作业命令的脚本，请使用 *FilePath* 参数。

如果初始化脚本生成错误，包括非终止错误，则计划作业的当前实例将不运行，并且其状态为 "失败"。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
指定要更改的计划作业。
输入包含 **ScheduledJobDefinition** 对象的变量，或者键入获取 **ScheduledJobDefinition** 对象的命令或表达式，如 Get-ScheduledJob 命令。
还可以通过管道将 **ScheduledJobDefinition** 对象传递给 **get-scheduledjob** 。

如果指定多个计划作业，则 **Set-ScheduledJob** 将对所有作业做出相同的更改。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxResultCount
指定为计划作业保留的作业结果项数。
默认值为 32。

Windows PowerShell 将计划作业的每个触发实例的执行历史记录和结果都保存在磁盘上。
此参数的值可确定为此计划作业保存的作业实例结果数。
当作业实例结果数超过此值时，Windows PowerShell 将删除最旧的作业实例结果，以便为最新的作业实例结果腾出空间。

作业执行历史记录和作业结果保存在 \\ \<JobName\> \\ \<Timestamp\> 创建该作业的计算机上的 $home \appdata\local\microsoft\windows\powershell\scheduledjobs \Output 目录中。
若要查看执行历史记录，请使用 Get-Job cmdlet。
若要获取作业结果，请使用 Receive-Job cmdlet。

*MaxResultCount* 参数设置计划作业的 ExecutionHistoryLength 属性值。

若要删除当前执行历史记录和作业结果，请使用 *ClearExecutionHistory* 参数。

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
为计划作业及其实例指定新名称。
该名称在本地计算机上必须唯一。

若要确定要更改的计划作业，请使用 *InputObject* 参数或通过管道将计划作业从 Get-ScheduledJob 传递给 **get-scheduledjob** 。

此参数不更改磁盘上作业实例的名称。
它仅影响在此命令完成后启动的作业实例。

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
返回一个代表你所处理的项目的对象。
默认情况下，此 cmdlet 将不产生任何输出。

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

### -RunAs32
在 32 位进程中运行计划作业。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
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
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunNow
在运行 **get-scheduledjob** cmdlet 后立即启动作业。
通过使用此参数，使得触发器任务计划程序无需在注册后立即运行 Windows PowerShell 脚本，而且用户无需创建可指定启动日期和时间的触发器。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Get-scheduledjoboption
设置计划作业的选项。
输入 **ScheduledJobOptions** 对象（例如使用 New-ScheduledJobOption cmdlet 创建的对象）或哈希表值。

你可以在注册计划作业时设置计划作业的选项，或者使用 Set-ScheduledJobOption 或 **get-scheduledjob** cmdlet 来设置或更改选项。

许多选项及其默认值都可确定是否运行计划作业以及运行时间。
在计划某个作业之前，务必检查这些选项。
有关计划作业选项（包括默认值）的说明，请参阅 Get-scheduledjoboption。

若要提交哈希表，请使用以下键。
在下列哈希表中，这些键与其默认值一起显示。

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ScriptBlock
指定计划作业运行的命令。
用大括号 ({ }) 括起命令以形成脚本块。
若要指定命令参数的默认值，请使用 *ArgumentList* 参数。

每个 Register-ScheduledJob 命令都必须使用 *ScriptBlock* 或 *FilePath* 参数。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Trigger
指定计划作业的触发器。
输入一个或多个 **ScheduledJobTrigger** 对象（例如 New-JobTrigger cmdlet 返回的对象），或者输入一个作业触发器键和值的哈希表。

作业触发器在一次性或定期计划或发生事件时自动启动计划作业。

作业触发器是可选的。
你可以在创建计划作业时添加触发器，使用 Add-JobTrigger 或 **get-scheduledjob** cmdlet 稍后添加触发器，或使用 Start-Job cmdlet 立即启动计划的作业。
你还可以创建和保留没有作业触发器的计划作业。

若要提交哈希表，请使用以下键。

`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (或任意有效的时间字符串) ; `DaysOfWeek="Monday", "Wednesday"` (或星期名称的任意组合) ; `Interval=2` (或任何有效频率间隔) ; `RandomDelay="30minutes"` (或任意有效的 timespan 字符串) ; `User="Domain1\User01"` (或任意有效的用户;仅与 AtLogon frequency 值一起使用) 

}

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
你可以通过管道将计划作业传递给 **Set-ScheduledJob** 。

## 输出

### 无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
如果你使用 *Passthru* 参数，则 **Set-ScheduledJob** 将返回已更改的计划作业。
否则，此 cmdlet 将不生成任何输出。

## 注释

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
