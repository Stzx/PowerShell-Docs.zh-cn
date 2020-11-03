---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/get-jobtrigger?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-JobTrigger
ms.openlocfilehash: 7a75a5a7e6875ed88fd31ea0f385c19f1991f8d7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197790"
---
# Get-JobTrigger

## 摘要
获取计划作业的作业触发器。

## SYNTAX

### JobDefinition（默认值）

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-InputObject] <ScheduledJobDefinition> [<CommonParameters>]
```

### JobDefinitionId

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Id] <Int32> [<CommonParameters>]
```

### JobDefinitionName

```
Get-JobTrigger [[-TriggerId] <Int32[]>] [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
**Get-JobTrigger** cmdlet 可获取计划作业的作业触发器。
你可以使用此命令检查作业触发器或通过管道将其传递给其他 cmdlet。

作业触发器定义用于启动计划作业的循环计划或条件。
不会单独将作业触发器保存到磁盘，因为它们是计划作业的一部分。
若要获取作业触发器，请指定该触发器启动的计划作业。

使用 **Get-JobTrigger** cmdlet 的参数来标识计划作业。
你可以通过其名称或标识号来标识计划作业，或者通过将 **get-scheduledjob** 对象（如 Get-ScheduledJob cmdlet 返回的对象）输入或管道传递给 **get-jobtrigger** 。

**Get-JobTrigger** 是 PSScheduledJob 模块（包含在 Windows PowerShell 中）中的一系列作业计划 cmdlet 之一。

有关计划作业的详细信息，请参阅 PSScheduledJob 模块中的“关于”主题。
导入 PSScheduledJob 模块，然后键入：`Get-Help about_Scheduled*`，或参阅 about_Scheduled_Jobs。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：按计划作业名称获取作业触发器

```
PS C:\> Get-JobTrigger -Name "BackupJob"
```

该命令使用 **get-jobtrigger** 的 *Name* 参数获取 BackupJob 计划作业的作业触发器。

### 示例 2：按 ID 获取作业触发器

```
The first command uses the Get-ScheduledJob cmdlet to display the scheduled jobs on the local computer. The display includes the IDs of the scheduled jobs.
PS C:\> Get-ScheduledJob
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          ArchiveProjects {1}             \\Server\Share\Archive-Projects.ps1      True
2          Backup          {1,2}           \\Server\Share\Run-Backup.ps1            True
3          Test-HelpFiles  {1}             \\Server\Share\Test-HelpFiles.ps1        True
4          TestJob         {}              \\Server\Share\Run-AllTests.ps1          True

The second command uses the **Get-JobTrigger** cmdlet to get the job trigger for the Test-HelpFiles job (ID = 3)
PS C:\> Get-JobTrigger -ID 3
```

该示例使用 **get-jobtrigger** 的 *ID* 参数来获取计划作业的作业触发器。

### 示例 3：通过管道传递作业以获取作业触发器

```
PS C:\> Get-ScheduledJob -Name *Backup*, *Archive* | Get-JobTrigger
```

此命令获取其名称中包含备份或存档的所有作业的作业触发器。

### 示例 4：获取远程计算机上某个作业的作业触发器

```
PS C:\> Invoke-Command -ComputerName Server01 { Get-ScheduledJob Backup | Get-JobTrigger -TriggerID 2 }
```

此命令获取远程计算机上某个计划作业的两个作业触发器之一。

该命令使用 Invoke-Command cmdlet 在 Server01 计算机上运行命令。
它使用 Get-ScheduledJob cmdlet 获取 Backup 计划作业，该作业将通过管道传递给 **Get-JobTrigger** cmdlet。
它使用 *TriggerID* 参数仅获取第二个触发器。

### 示例 5：获取所有作业触发器

```
PS C:\> Get-ScheduledJob | Get-JobTrigger | Format-Table -Property ID, Frequency, At, DaysOfWeek, Enabled, @{Label="ScheduledJob";Expression={$_.JobDefinition.Name}} -AutoSize
Id Frequency At                    DaysOfWeek Enabled ScheduledJob
-- --------- --                    ---------- ------- ------------
1    Weekly  9/28/2011 3:00:00 AM  {Monday}   True    Backup
1    Daily   9/27/2011 11:00:00 PM            True    Test-HelpFiles
```

此命令获取本地计算机上的所有计划作业的所有作业触发器。

此命令使用 Get-ScheduledJob 获取本地计算机上的计划作业，并通过管道将这些作业传递给 **Get-JobTrigger** ，它将获取每个计划作业的作业触发器（如果有）。

若要将计划作业的名称添加到作业触发器显示中，该命令将使用 Format-Table cmdlet 的计算属性功能。
除了默认情况下显示的作业触发器属性，该命令还会创建一个新的 Get-scheduledjob 属性，用于显示计划作业的名称。

### 示例 6：获取计划作业的作业触发器属性

```
The command uses the Get-ScheduledJob cmdlet to get the Test-HelpFiles scheduled job. Then it uses the dot method (.) to get the JobTriggers property of the Test-HelpFiles scheduled job.
PS C:\> (Get-ScheduledJob Test-HelpFiles).JobTriggers

The second command uses the Get-ScheduledJob cmdlet to get all scheduled jobs on the local computer. It uses the ForEach-Object cmdlet to get the value of the JobTrigger property of each scheduled job.
PS C:\> Get-ScheduledJob | foreach {$_.JobTriggers}
```

计划作业的作业触发器存储在该作业的 JobTriggers 属性中。
此示例显示了使用 **get-jobtrigger** cmdlet 获取作业触发器的替代方法。
结果与使用 **Get-JobTrigger** cmdlet 相同，因此这两项技术可以互换使用。

### 示例 7：比较作业触发器

```
The first command gets the job trigger of the ArchiveProjects scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T1 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name ArchiveProjects | Get-JobTrigger | Tee-Object -Variable T1
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The second command gets the job trigger of the Test-HelpFiles scheduled job. The command pipes the job trigger to the Tee-Object cmdlet, which saves the job trigger in the $T2 variable and displays it at the command line.
PS C:\> Get-ScheduledJob -Name "Test-HelpFiles" | Get-JobTrigger | Tee-Object -Variable T2
Id         Frequency       Time                   DaysOfWeek              Enabled
--         ---------       ----                   ----------              -------
0          Daily           9/26/2011 3:00:00 AM                           True

The third command compares the job triggers in the $t1 and $t2 variables. It uses the Get-Member cmdlet to get the properties of the job trigger in the $t1 variable. It pipes the properties to the ForEach-Object cmdlet, which compares each property to the properties of the job trigger in the $t2 variable by name. The command then pipes the differing properties to the Format-List cmdlet, which displays them in a list.The output indicates that, although the job triggers appear to be the same, the HelpFiles job trigger includes a random delay of three (3) minutes.
PS C:\> $T1 | Get-Member -Type Property | ForEach-Object { Compare-Object $T1 $T2 -Property $_.Name}
RandomDelay                                                 SideIndicator
-----------                                                 -------------
00:00:00                                                    =>
00:03:00                                                    <=
```

此示例显示了如何比较两个计划作业的作业触发器。

## PARAMETERS

### -Id
指定计划作业的标识号。
**Get-JobTrigger** 可获取指定的计划作业的作业触发器。

若要获取本地计算机或远程计算机上的计划作业的标识号，请使用 Get-ScheduledJob cmdlet。

```yaml
Type: System.Int32
Parameter Sets: JobDefinitionId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
指定计划作业。
输入包含  **get-scheduledjob** 对象的变量，或者键入获取 **get-scheduledjob** 对象的命令或表达式，如 Get-ScheduledJob 命令。
还可以通过管道将 **ScheduledJob** 对象传递给 **Get-JobTrigger** 。

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: JobDefinition
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
指定计划作业的名称。
**Get-JobTrigger** 可获取指定的计划作业的作业触发器。
支持通配符。

若要获取本地计算机或远程计算机上的计划作业的名称，请使用 Get-ScheduledJob cmdlet。

```yaml
Type: System.String
Parameter Sets: JobDefinitionName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TriggerId
获取指定的作业触发器。
输入计划作业中一个或多个作业触发器的触发器 ID。
在 *Name* 、 *ID* 或 *InputObject* 参数指定的计划作业有多个作业触发器时使用此参数。

```yaml
Type: System.Int32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
可以通过管道将计划作业从 Get-ScheduledJob 传递到 **Get-JobTrigger** 。

## 输出

### Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger

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
