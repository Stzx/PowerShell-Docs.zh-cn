---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/new-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-JobTrigger
ms.openlocfilehash: de49ab937c6f3a8187f5aecd6aafc81425b8cd00
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197786"
---
# New-JobTrigger

## 摘要
为计划作业创建作业触发器。

## SYNTAX

###  (默认值一次) 

```
New-JobTrigger [-RandomDelay <TimeSpan>] -At <DateTime> [-Once] [-RepetitionInterval <TimeSpan>]
 [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely] [<CommonParameters>]
```

### 每日

```
New-JobTrigger [-DaysInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> [-Daily] [<CommonParameters>]
```

### 每周

```
New-JobTrigger [-WeeksInterval <Int32>] [-RandomDelay <TimeSpan>] -At <DateTime> -DaysOfWeek <DayOfWeek[]>
 [-Weekly] [<CommonParameters>]
```

### AtStartup

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-AtStartup] [<CommonParameters>]
```

### AtLogon

```
New-JobTrigger [-RandomDelay <TimeSpan>] [-User <String>] [-AtLogOn] [<CommonParameters>]
```

## DESCRIPTION
**Get-jobtrigger** cmdlet 创建一个作业触发器，该触发器在一次性或循环计划或事件发生时启动计划作业。

你可以使用 **New-JobTrigger** 返回的 **ScheduledJobTrigger** 对象，为新的或现有的计划作业设置作业触发器。
你还可以使用 Get-JobTrigger cmdlet 来创建作业触发器，以获取现有计划作业的作业触发器，或使用哈希表值来表示作业触发器。

创建作业触发器时，请查看 New-ScheduledJobOption cmdlet 指定的选项的默认值。
这些选项具有与 **Task Scheduler** 中相应选项相同的有效值和默认值，这将影响计划作业的计划和时间。

**Get-jobtrigger** 是 Windows PowerShell 中包含的 PSScheduledJob 模块中的作业计划 cmdlet 集合之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：一旦计划

```
PS C:\> New-JobTrigger -Once -At "1/20/2012 3:00 AM"
```

此命令使用 **New-JobTrigger** cmdlet 来创建只能启动计划作业一次的作业触发器。
*At* 参数值是一个可借助 Windows PowerShell 转换为 **DateTime** 对象的字符串。
*At* 参数值包含一个显式日期，而不仅仅是某个时间。
如果省略了日期，将使用当前日期和上午 3:00（这可能表示过去的某个时间）来创建该触发器。

### 示例2：每日计划

```
PS C:\> New-JobTrigger -Daily -At "4:15 AM" -DaysInterval 3
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/21/2012 4:15:00 AM                           True
```

此命令创建可在每隔 3 天的上午 4:15 启动计划作业的作业触发器。

由于 *At* 参数值不包含某个日期，因此当前日期将用作 **DateTime** 对象中的日期值。
如果该日期和时间是过去的日期和时间，则计划作业将在下次开始时间之前启动，开始时间为从 *At* 参数值起第 3 天。

### 示例3：每周计划

```
PS C:\> New-JobTrigger -Weekly -DaysOfWeek Monday, Wednesday, Friday -At "23:00" -WeeksInterval 4
Id Frequency Time                  DaysOfWeek                  Enabled
-- --------- ----                  ----------                  -------
0  Weekly    9/21/2012 11:00:00 PM {Monday, Wednesday, Friday} True
```

此命令创建一个作业触发器，该触发器将在每 4 个星期的星期一、星期三和星期五的 23:00（下午 11:00）启动计划作业。

还可以输入整数中的 *DaysOfWeek* 参数值，例如 `-DaysOfWeek 1, 5` 。

### 示例4：登录计划

```
PS C:\> New-JobTrigger -AtLogOn -User Domain01\Admin01
```

此命令创建一个作业触发器，该触发器将在每次域管理员登录到计算机时启动计划作业。

### 示例5：使用随机延迟

```
PS C:\> New-JobTrigger -Daily -At 1:00 -RandomDelay 00:20:00
```

此命令创建一个作业触发器，该触发器将在每天凌晨 1:00 启动计划作业。
此命令使用 *RandomDelay* 参数将最大延迟设置为 20 分钟。
因此，该作业将以伪随机地方式在每天凌晨 1:00 至凌晨 1:20（随间隔值变化而变化）之间运行。

你可以将随机延迟用于采样、负载平衡以及其他管理任务。
设置延迟值时，请查看 New-ScheduledJobOption cmdlet 的有效和默认值，并将延迟与选项设置进行协调。

### 示例6：为新的计划作业创建作业触发器

```
The first command uses the **New-JobTrigger** cmdlet to create a job trigger that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The command saves the job trigger in the $T variable.
PS C:\> $T = New-JobTrigger -Weekly -DaysOfWeek 1,3,5 -At 12:01AM


The second command uses the Register-ScheduledJob cmdlet to create a scheduled job that starts a job every Monday, Wednesday, and Friday at 12:01 AM. The value of the *Trigger* parameter is the trigger that is stored in the $T variable.
PS C:\> Register-ScheduledJob -Name Test-HelpFiles -FilePath C:\Scripts\Test-HelpFiles.ps1 -Trigger $T
```

以下命令使用作业触发器来创建新的计划作业。

### 示例7：将作业触发器添加到计划作业

```
PS C:\> Add-JobTrigger -Name SynchronizeApps -Trigger (New-JobTrigger -Daily -At 3:10AM)
```

此示例显示了如何将作业触发器添加到现有的计划作业。
你可以将多个作业触发器添加到任何计划作业。

该命令使用 Add-JobTrigger cmdlet 将作业触发器添加到 Synchronizeapps 将计划作业。
*Trigger* 参数值是在每天上午 3:10 运行该作业的 **New-JobTrigger** 命令。

完成此命令后，SynchronizeApps 将是一个在该作业触发器指定的时间运行的计划作业。

### 示例8：创建重复作业触发器

```
PS C:\> New-JobTrigger -Once -At "09/12/2013 1:00:00" -RepetitionInterval (New-TimeSpan -Hours 1) -RepetitionDuration (New-Timespan -Hours 48)
```

此命令创建一个作业触发器，该触发器每隔60分钟运行一次作业，每隔分钟运行一次，48小时从2013上午1:00 的开始。

### 示例9：停止重复作业触发器

```
PS C:\> Get-JobTrigger -Name SecurityCheck | Set-JobTrigger -RepetitionInterval 0:00 -RepetitionDuration 0:00
```

此命令强制停止 SecurityCheck 作业，该作业触发后将在其作业触发器到期之前每 60 分钟运行一次。

若要防止作业重复，此命令使用 Get-JobTrigger 获取 SecurityCheck 作业的作业触发器，并使用 Set-JobTrigger cmdlet 将作业触发器的重复间隔和重复持续时间更改为零 (0) 。

### 示例10：创建每小时作业触发器

```
PS C:\> New-JobTrigger -Once -At "9/21/2012 0am" -RepetitionInterval (New-TimeSpan -Hour 12) -RepetitionDuration ([TimeSpan]::MaxValue)
```

以下命令创建一个作业触发器，该触发器将无限期地每 12 个小时运行计划作业一次。
该计划从明日 (9/21/2012) 午夜（凌晨 0:00）开始运行。

## PARAMETERS

### -At
在指定的日期和时间启动作业。
输入一个 **DateTime** 对象（例如 Get-Date cmdlet 返回的）或一个可以转换为日期和时间的字符串，例如 "April 19，2012 15:00"、"12/31" 或 "3am"。
如果没有指定日期的元素（例如年份），则触发器中的日期将具有当前日期中的相应元素。

使用 *Once* 参数时，应将 *At* 参数值设置为未来某个日期和时间。
由于 **DateTime** 对象中的默认日期为当前日期，因此在没有显式日期的情况下指定当前时间之前的某个时间时，将针对过去的某个时间创建作业触发器。

**DateTime** 对象以及可转换为 **DateTime** 对象的字符串将自动调整为与在“控制面板”的“区域和语言”中为本地计算机选择的日期和时间格式兼容。

```yaml
Type: System.DateTime
Parameter Sets: Once, Daily, Weekly
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtLogOn
在指定的用户登录到计算机时，启动计划作业。
若要指定某个用户，请使用 *User* 参数。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtLogon
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
在 Windows 启动时，启动计划作业。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AtStartup
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Daily
指定一个循环的每日作业计划。
使用 *每日* 参数集中的其他参数来指定计划详细信息。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Daily
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysInterval
指定启动每日计划之间间隔的天数。
例如，值为 3 时将在第 1 天、第 4 天、第 7 天（依此类推）启动计划作业。
默认值为 1。

```yaml
Type: System.Int32
Parameter Sets: Daily
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
指定在星期几运行每周计划作业。
输入星期几名称，例如“Monday”或整数 0-6，其中 0 表示星期天。
在 Weekly 参数集中需要此参数。

在作业触发器中，应将星期几名称转换为其对应的整数值。
在某个命令中将星期几名称括在引号中时，应单独将每个星期几名称括在引号中，例如“Monday”、“Tuesday”。
如果将多个星期几名称括在一对引号中，则应合计相应的整数值。
例如，“Monday, Tuesday”(1, 2) 将生成一个“Wednesday”(3) 值。

```yaml
Type: System.DayOfWeek[]
Parameter Sets: Weekly
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Once
指定非循环（一次性）计划或自定义的重复计划。
若要创建重复计划，请使用 *Once* 参数以及 *RepetitionDuration* 和 *RepetitionInterval* 参数。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomDelay
启用从计划开始时间开始的随机延迟，并设置最大延迟值。
针对每次启动以伪随机地方式设置延迟的长度，该长度可从无延迟变化到由此参数值指定的时间。
默认值为零 (00:00:00) 时将禁用随机延迟。

输入 timespan 对象（如 New-TimeSpan cmdlet 返回的对象），或输入 \<hours\> ：： format 形式的值 \<minutes\> ，该对象会 \<seconds\> 自动转换为 **timespan** 对象。

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

### -RepeatIndefinitely
使用此参数（可在 Windows PowerShell 4.0 中启动），可在不指定 **RepetitionDuration** 参数的 *TimeSpan.MaxValue* 值的情况下无限期重复运行计划作业。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepetitionDuration
重复运行该作业，直到指定时间到期为止。
重复频率由 *RepetitionInterval* 参数值确定。
例如，如果 **RepetitionInterval** 的值为 5 分钟且 **RepetitionDuration** 的值为 2 小时，将在两小时内每 5 分钟触发一次该作业。

输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。

若要无限期地运行作业，请改为添加 *RepeatIndefinitely* 参数。

若要在作业触发器重复持续时间到期之前停止作业，请使用 Set-JobTrigger cmdlet 将 *RepetitionDuration* 值设置为 0 () 。

仅当命令中使用了 *Once* 、 *At* 和 *RepetitionInterval* 参数时，此参数才有效。

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepetitionInterval
在指定的时间间隔重复运行作业。
例如，如果此参数的值是 2 小时，则将每隔两小时触发该作业一次。
默认值为 0 时不重复该作业。

输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。

仅当命令中使用了 *Once* 、 *At* 和 *RepetitionDuration* 参数时，此参数才有效。

```yaml
Type: System.TimeSpan
Parameter Sets: Once
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -User
指定可触发计划作业启动 *AtLogon* 的用户。
输入或格式的用户的名称 \<UserName\> ， \<Domain\Username\> 或输入一个星号 (\*) 以表示所有用户。
默认值为所有用户。

```yaml
Type: System.String
Parameter Sets: AtLogon
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Weekly
指定一个循环的每周作业计划。
使用 Weekly 参数集中的其他参数来指定计划详细信息。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Weekly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeksInterval
指定启动每周作业计划之间间隔的天数。
例如，值为 3 时将在第 1 周、第 4 周、第 7 周（依此类推）启动计划作业。
默认值为 1。

```yaml
Type: System.Int32
Parameter Sets: Weekly
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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger

## 注释

* 作业触发器不会保存到磁盘。 不过，计划作业保存在磁盘上，你可以使用 Get-JobTrigger 获取任何计划作业的作业触发器。
* **Get-jobtrigger** 不会阻止你创建不会运行计划作业的作业触发器，例如过去日期的一次性触发器。
* Register-ScheduledJob cmdlet 接受 ScheduledJobTrigger 对象，如 **get-jobtrigger** 或 Get-JobTrigger cmdlet 返回的对象，或者包含触发器值的哈希表。

  若要提交哈希表，请使用以下键。

  `@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (或任意有效的时间字符串) ; `DaysOfWeek="Monday", "Wednesday"` (或星期名称的任意组合) ; `Interval=2` (或任何有效频率间隔) ; `RandomDelay="30minutes"` (或任意有效的 timespan 字符串) ; `User="Domain1\User01` (或任意有效的用户;仅与 *AtLogon* frequency 值) } 一起使用

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
