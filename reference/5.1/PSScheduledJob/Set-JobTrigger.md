---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-JobTrigger
ms.openlocfilehash: 8d1b12b67ccf695e1c4b948e6eeecf292c588af4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197780"
---
# Set-JobTrigger

## 摘要
更改计划作业的作业触发器。

## SYNTAX

```
Set-JobTrigger [-InputObject] <ScheduledJobTrigger[]> [-DaysInterval <Int32>] [-WeeksInterval <Int32>]
 [-RandomDelay <TimeSpan>] [-At <DateTime>] [-User <String>] [-DaysOfWeek <DayOfWeek[]>] [-AtStartup]
 [-AtLogOn] [-Once] [-RepetitionInterval <TimeSpan>] [-RepetitionDuration <TimeSpan>] [-RepeatIndefinitely]
 [-Daily] [-Weekly] [-PassThru] [<CommonParameters>]
```

## DESCRIPTION
**Set-JobTrigger** cmdlet 可更改计划作业的作业触发器的属性。
它可用于更改作业启动的时间或频率，还可用于将计划从基于时间的计划更改为登录或启动时触发的计划。

作业触发器定义用于启动计划作业的循环计划或条件。
虽然作业触发器不保存到磁盘，但你可以更改计划作业的作业触发器，这些触发器可保存到磁盘。

若要更改计划作业的作业触发器，应首先使用 Get-JobTrigger cmdlet 来获取计划作业的作业触发器。
然后，通过管道将触发器传递给 **Set-JobTrigger** 或将其保存在某个变量中，并且使用 *Set-JobTrigger* cmdlet 的 **InputObject** 参数来标识触发器。
使用 **Set-JobTrigger** 的剩余参数来更改作业触发器。

更改作业触发器的类型（例如将作业触发器从每日或每周触发器更改为 *AtLogon* 触发器）时，将删除原始触发器属性。
但是，如果更改触发器的值而非其类型（例如在每周触发器中更改日期），则仅更改指定的属性。
保留原始作业触发器的所有其他属性。

**et-JobTrigger** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：更改作业触发器中的星期几名称

```
PS C:\> Get-JobTrigger -Name "DeployPackage"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Saturday}   True

The second command uses the Get-JobTrigger cmdlet to get the job trigger of the DeployPackage scheduled job. A pipeline operator (|) sends the trigger to the **Set-JobTrigger** cmdlet, which changes the job trigger so that it starts the DeployPackage job on Wednesdays and Sundays. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "DeployPackage" | Set-JobTrigger -DaysOfWeek "Wednesday", "Sunday" -Passthru
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Weekly          9/29/2011 12:00:00 AM  {Wednesday, Sunday}     True
```

此示例显示了如何更改每周作业触发器中的星期几名称。

第一个命令使用 Get-JobTrigger cmdlet 来获取 DeployPackage 计划作业的作业触发器。
该输出显示触发器在星期三和星期六的午夜启动作业。

此命令不是必需的；包含它只是为了显示触发器更改的效果。

### 示例 2：更改作业触发器类型

```
PS C:\> Get-JobTrigger -Name "Inventory"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          AtStartup                                                      True

The second command uses the **Get-JobTrigger** cmdlet to get the *AtStartup* job trigger of the Inventory job. The command uses the *TriggerID* parameter to identify the job trigger. A pipeline operator (|) sends the job trigger to the **Set-JobTrigger** cmdlet, which changes it to a weekly job trigger that runs every four weeks on Monday at midnight. The command uses the *Passthru* parameter to return the trigger after the change.
PS C:\> Get-JobTrigger -Name "Inventory" -TriggerID 2 | Set-JobTrigger -Weekly -WeeksInterval 4 -DaysOfWeek Monday -At "12:00 AM"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           9/27/2011 11:00:00 PM                          True
2          Weekly          10/31/2011 12:00:00 AM {Monday}                True
```

此示例显示了如何更改用于启动作业的作业触发器的类型。
此示例中的命令将 AtStartup 作业触发器替换为每周触发器。

第一个命令使用 Get-JobTrigger cmdlet 获取清单计划作业的作业触发器。
此输出显示，作业有两个触发器，即每日触发器和 *AtStartup* 触发器。

此命令不是必需的；包含它只是为了显示触发器更改的效果。

### 示例 3：更改远程作业触发器上的用户

```
PS C:\> Invoke-Command -ComputerName "Server01" -ScriptBlock {Get-ScheduledJob | Get-JobTrigger | Where-Object {$_.User} | Set-JobTrigger -User "Domain01/Admin02"}
```

此命令更改 Server01 计算机上计划作业的所有 *AtLogon* 作业触发器中的用户。

该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。

远程命令以获取计算机上所有计划作业的 Get-ScheduledJob 命令开头。
计划作业通过管道传递给 Get-JobTrigger cmdlet，此 cmdlet 将获取这些计划作业的作业触发器。
每个作业触发器都包含 JobDefinition 属性，该属性包括计划作业，因此触发器与计划作业保持关联，即使该作业出现更改也是如此。

作业触发器通过管道传输到 Where-Object cmdlet，该 cmdlet 将获取具有 User 属性的作业触发器。
通过管道将选定的作业触发器传递给 **Set-JobTrigger** cmdlet，此 cmdlet 可将用户更改为 Domain01\Admin02。

### 示例 4：更改许多作业触发器中的一个

```
PS C:\> Get-JobTrigger -Name "SecurityCheck"
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
1          Daily           4/24/2013 3:00:00 AM                           True
2          Weekly          4/24/2013 4:00:00 PM   {Sunday}                True
3          Once            4/24/2013 4:00:00 PM                           True

The second command uses the **TriggerID** parameter of the **Get-JobTrigger** cmdlet to get the *Once* trigger of the SecurityCheck scheduled job. The command pipes the trigger to the Format-List cmdlet, which displays all of the properties of the *Once* job trigger.The output shows that the trigger starts the job once every hour (RepetitionInterval = 1 hour) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:00:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition

The third command changes the repetition interval of the job trigger from one hour to 90 minutes. The command does not return any output.
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerId 3 | Set-JobTrigger -RepetitionInterval (New-TimeSpan -Minutes 90)

The fourth command displays the effect of the change.The output shows that the trigger starts the job once every 90 minutes (RepetitionInterval = 1 hour, 30 minutes) for one day (RepetitionDuration = 1 day).
PS C:\> Get-JobTrigger -Name "SecurityCheck" -TriggerID 3 | Format-List -Property *
At                 : 4/24/2012 4:00:00 PM
DaysOfWeek         :
Interval           : 1
Frequency          : Once
RandomDelay        : 00:00:00
RepetitionInterval : 01:30:00
RepetitionDuration : 1.00:00:00
User               :
Id                 : 3
Enabled            : True
JobDefinition      : Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
```

此示例中的命令将 SecurityCheck 计划作业的 *Once* 作业触发器的重复间隔时间从每 60 分钟更改为每 90 分钟。
SecurityCheck 计划作业具有三个作业触发器，因此该命令使用 Get-JobTrigger cmdlet 的 *TriggerId* 参数标识所更改的作业触发器。

第一个命令使用 **Get-JobTrigger** cmdlet 来获取 SecurityCheck 计划作业的所有作业触发器。
用于显示作业触发器的 ID 的输出可显示 ID 为 3 的 *Once* 作业触发器。

## PARAMETERS

### -At
在指定的日期和时间启动作业。
输入一个 **DateTime** 对象（例如 Get-Date cmdlet 返回的对象），或输入一个可转换为时间的字符串（例如“April 19, 2012 15:00”、“12/31/2013 9:00 PM”或“3am”）。

如果未指定 **DateTime** 对象的元素（例如秒），则不会更改作业触发器的元素。
如果原始作业触发器没有包含 **DateTime** 对象，而您省略了某个元素，则将使用当前日期和时间中的相应元素来创建作业触发器。

使用 *Once* 参数时，将 *At* 参数值设置为特定的日期和时间。
由于 **DateTime** 对象中的默认日期为当前日期，因此在没有显式日期的情况下设置当前时间之前的某个时间时，将针对过去的某个时间生成作业触发器。

**DateTime** 对象以及可转换为 **DateTime** 对象的字符串将自动调整为与在“控制面板”的“区域和语言”中为本地计算机选择的日期和时间格式兼容。

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AtStartup
在 Windows 启动时，启动计划作业。

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

### -Daily
指定一个循环的每日作业计划。
使用 *每日* 参数集中的其他参数来指定计划详细信息。

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

### -DaysInterval
指定启动每日计划之间间隔的天数。
例如，值为 3 时将在第 1 天、第 4 天、第 7 天（依此类推）启动计划作业。
默认值为 1。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DaysOfWeek
指定在星期几运行每周计划作业。
输入 "日期名称"，如 "星期一"、"星期四"、"整数 0-6"，其中0表示 "星期日" 或 "星号" (\*) 以表示每天。
在 Weekly 参数集中需要此参数。

在作业触发器中，应将星期几名称转换为其对应的整数值。
在某个命令中将星期几名称括在引号中时，应单独将每个星期几名称括在引号中，例如“Monday”、“Tuesday”。
如果将多个星期几名称括在一对引号中，则应合计相应的整数值。
例如，“Monday, Tuesday”(1, 2) 将生成一个“Wednesday”(3) 值。

```yaml
Type: System.DayOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Sunday, Monday, Tuesday, Wednesday, Thursday, Friday, Saturday

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
指定作业触发器。
输入包含 **ScheduledJobTrigger** 对象的变量，或者键入获取 **ScheduledJobTrigger** 对象的命令或表达式，如 Get-JobTrigger 命令。
还可以通过管道将 **ScheduledJobTrigger** 对象传递给 **Set-JobTrigger** 。

如果指定多个作业触发器，则 **Set-JobTrigger** 将对所有作业触发器做出相同的更改。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Once
指定非循环（一次性）计划。

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

### -PassThru
返回更改的作业触发器。
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

### -RandomDelay
启用从计划开始时间开始的随机延迟，并设置最大延迟值。
针对每次启动以伪随机地方式设置延迟的长度，该长度可从无延迟变化到由此参数值指定的时间。
默认值为零 (00:00:00) 时将禁用随机延迟。

输入 timespan 对象（如 New-TimeSpan cmdlet 返回的对象），或输入 \<hours\> ：： format 形式的值 \<minutes\> ，该对象会 \<seconds\> 自动转换为 timespan 对象。

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
Parameter Sets: (All)
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
例如，如果 **RepetitionInterval** 的值为 5 分钟且 *RepetitionDuration* 的值为 2 小时，将在两小时内每 5 分钟触发一次该作业。

输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。

若要无限期地运行作业，请改为添加 *RepeatIndefinitely* 参数。

若要在作业触发器重复持续时间到期之前停止作业，请将 **RepetitionDuration** 值设置为零 (0)。

若要更改 *Once* 作业触发器的重复持续时间或重复间隔时间，该命令必须包含 **RepetitionInterval** 和 **RepetitionDuration** 参数。
若要更改其他类型的作业触发器的重复持续时间或重复间隔时间，该命令必须包含 *Once* 、 *At* 、 *RepetitionInterval* 和 *RepetitionDuration* 参数。

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

### -RepetitionInterval
在指定的时间间隔重复运行作业。
例如，如果此参数的值是 2 小时，则将每隔两小时触发该作业一次。
默认值为 0 时不重复该作业。

输入一个时间跨度对象（例如 New-TimeSpan cmdlet 返回的一个对象），或者输入一个可转换为时间跨度对象的字符串（例如“1:05:30”）。

若要更改 **Once** 作业触发器的重复持续时间或重复间隔时间，该命令必须包含 **RepetitionInterval** 和 **RepetitionDuration** 参数。
若要更改其他类型的作业触发器的重复持续时间或重复间隔时间，该命令必须包含 **Once** 、 **At** 、 **RepetitionInterval** 和 **RepetitionDuration** 参数。

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

### -User
指定可触发计划作业启动 *AtLogon* 的用户。
输入或格式的用户的名称 \<UserName\> ， \<Domain\Username\> 或输入一个星号 (\*) 以表示所有用户。
默认值为所有用户。

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

### -Weekly
指定一个循环的每周作业计划。
使用 " *每周* " 参数集中的其他参数来指定计划详细信息。

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

### -WeeksInterval
指定启动每周作业计划之间间隔的天数。
例如，值为 3 时将在第 1 周、第 4 周、第 7 周（依此类推）启动计划作业。
默认值为 1。

```yaml
Type: System.Int32
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

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger
可以通过管道将多个作业触发器传递给 **get-jobtrigger** 。

## 输出

### 无或 Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger
当使用 *Passthru* 参数时， **Set-JobTrigger** 将返回已更改的作业触发器。
否则，此 cmdlet 将不生成任何输出。

## 注释

* 作业触发器具有一个将其与计划作业相关联的 JobDefintion 属性。 当更改计划作业的作业触发器时，该作业将发生更改。 无需使用 Set-ScheduledJob 命令即可将更改的触发器应用于计划作业。

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
