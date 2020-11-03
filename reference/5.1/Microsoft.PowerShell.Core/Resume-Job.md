---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 85cbfad2a4866bf18e69fb99afb8698e233c4c80
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197624"
---
# Resume-Job

## 摘要
重新启动挂起的作业。

## SYNTAX

### SessionIdParameterSet（默认值）

```
Resume-Job [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### JobParameterSet

```
Resume-Job [-Job] <Job[]> [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameParameterSet

```
Resume-Job [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Resume-Job [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StateParameterSet

```
Resume-Job [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilterParameterSet

```
Resume-Job [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Resume-Job** cmdlet 允许恢复已挂起的工作流作业，例如通过使用 Suspend-Job cmdlet 或 about_Suspend-Workflow 挂起的工作流作业。
工作流作业恢复后，作业引擎将从已保存的资源（如检查点）重新构建状态、元数据和输出。
在不丢失任何状态或数据的情况下重新启动作业。
作业状态将从 **Suspended** 更改为 **Running** 。

使用 **Resume-Job** 的参数按名称 ID、实例 ID 选择作业，或者通过管道将作业对象（例如由 Get-Job cmdlet 返回的作业对象）返回到 **Resume-Job** 。
还可以使用属性筛选器来选择要恢复的作业。

默认情况下，即使可能尚未恢复所有作业， **Resume-Job** 也将立即返回。
若要在恢复所有指定的作业之前禁止显示命令提示符，请使用 *Wait* 参数。

**Resume-Job** cmdlet 仅适用于自定义作业类型，例如工作流作业。
它不适用于标准后台作业，例如通过使用 Start-Job cmdlet 启动的作业。
如果你提交了一个类型不受支持的作业，则 **Resume-Job** 将生成一个终止错误并停止运行。

若要标识工作流作业，请查找该作业的 **PSWorkflowJob** 属性中的 **PSJobTypeName** 值。
若要确定某个特定的自定义作业类型是否支持 **Resume-Job** cmdlet，请参阅自定义作业类型的帮助主题。

在自定义作业类型上使用 Job cmdlet 之前，请使用 Import-Module cmdlet 或者获取或使用模块中的 cmdlet 导入支持该自定义作业类型的模块。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：按 ID 恢复作业

```
The first command uses the **Get-Job** cmdlet to get the job. The output shows that the job is a suspended workflow job.
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

The second command uses the *Id* parameter of the **Resume-Job** cmdlet to resume the job with an *Id* value of 4.
PS C:\> Resume-Job -Id 4
```

此示例中的命令将验证该作业是否为挂起的工作流作业，然后恢复该作业。

### 示例 2：按名称恢复作业

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

此命令使用 *Name* 参数来恢复本地计算机上的多个工作流作业。

### 示例 3：使用自定义属性值

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

此命令使用自定义属性的值来标识要恢复的工作流作业。
它使用 *Filter* 参数来按其 **CustomID** 属性标识工作流作业。
它还使用 *State* 参数来验证在尝试恢复工作流作业之前，工作流作业是否已挂起。

### 示例 4：恢复远程计算机上所有挂起的作业

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

此命令将恢复 Srv01 远程计算机上所有挂起的作业。

该命令使用 Invoke-Command cmdlet 在 Srv01 计算机上运行命令。
远程命令使用 **get-help** Cmdlet 的 *State* 参数获取计算机上所有挂起的作业。
管道运算符 (|) 将挂起的作业发送到 **Resume-Job** cmdlet，后者将恢复它们。

### 示例5：等待作业恢复

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

此命令使用 *Wait* 参数定向到仅在恢复所有指定作业后返回 **的 Resume 作业** 。
*Wait* 参数在假定已在脚本继续运行之前恢复作业的脚本中尤其有用。

### 示例6：恢复挂起自身的工作流

```
This code sample shows the **Suspend-Workflow** activity in a workflow.
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

The following command runs the Test-Suspend workflow on the Server01 computer.When you run the workflow, the workflow runs the Get-Date activity and stores the result in the $a variable. Then it runs the Suspend-Workflow activity. In response, it takes a checkpoint, suspends the workflow, and returns a workflow job object.  Suspend-Workflow returns a workflow job object even if the workflow is not explicitly run as a job.
PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

The following command resumes the Test-Suspend workflow in Job8. It uses the *Wait* parameter to hold the command prompt until the job is resumed.
PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command

--     ----            -------------   -----         -----------     --------             -------

8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

This command uses the **Receive-Job** cmdlet to get the results of the Test-Suspend workflow. The final command in the workflow returns a **TimeSpan** object that represents the elapsed time between the current date and time and the date and time that was saved in the $a variable before the workflow was suspended.
PS C:\> Receive-Job -Name Job8
        Days              : 0
        Hours             : 0
        Minutes           : 0
        Seconds           : 19
        Milliseconds      : 823
        Ticks             : 198230041
        TotalDays         : 0.000229432917824074
        TotalHours        : 0.00550639002777778
        TotalMinutes      : 0.330383401666667
        TotalSeconds      : 19.8230041
        TotalMilliseconds : 19823.0041
        PSComputerName    : Server01
```

使用 **resume-Job** cmdlet 可以恢复使用 **挂起工作流** 活动挂起的工作流作业。
此活动将从工作流内部挂起工作流。
它仅在工作流中有效。

若要了解 Suspend-Workflow，请参阅 about_Suspend-Workflow。

## PARAMETERS

### -Filter
指定条件的哈希表。
此 cmdlet 将恢复满足哈希表中所有条件的作业。
输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Id
指定此 cmdlet 恢复的作业的 Id 数组。

ID 是一个整数，用于唯一标识当前会话中的作业。
它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。
你可以键入一个或多个 Id （以逗号分隔）。
若要查找作业的 ID，请运行 " **获取作业** "。

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId
指定此 cmdlet 恢复的作业的实例 Id 的数组。
默认值为所有作业。

实例 ID 是一个 GUID，用于在计算机上唯一标识作业。
若要查找作业的实例 ID，请运行 " **获取作业** "。

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Job
指定要恢复的作业。
请输入一个包含作业的变量，或一个可获取作业的命令。
还可以通过管道将作业传递给 **Resume-Job** cmdlet。

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
指定此 cmdlet 恢复的作业的友好名称数组。
输入一个或多个作业名称。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
指定要恢复的作业的状态。
此参数的可接受值为：

- NotStarted
- 正在运行
- 已完成
- 已失败
- 已停止
- 已阻止
- Suspended
- 已断开连接
- 正在暂停
- 正在停止

此 cmdlet 仅恢复处于 **挂起** 状态的作业。

有关作业状态的详细信息，请参阅 MSDN 库中的 [JobState 枚举](https://msdn.microsoft.com/library/system.management.automation.jobstate) 。

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait
指示此 cmdlet 禁止显示命令提示符，直到重新启动所有作业结果。
默认情况下，此 cmdlet 会立即返回可用的结果。

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

### -WhatIf
显示运行该 cmdlet 时会发生什么情况。
此 cmdlet 未运行。

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

### System.Management.Automation.Job
可以通过管道将所有类型的作业传递给此 cmdlet。
如果 **Resume 作业** 获取不受支持的类型的作业，它将返回终止错误。

## 输出

### 无、管理系统
如果使用 *PassThru* 参数，则此 cmdlet 将返回尝试恢复的作业。
否则，此 cmdlet 将不生成任何输出。

## 注释

* **Resume-Job** 仅可恢复已挂起的作业。 如果你提交了处于其他状态的作业，则 **Resume-Job** 将在该作业上运行恢复操作，但是会生成一个警告，提示你无法恢复该作业。 若要禁止显示警告，请使用值为 SilentlyContinue 的 *WarningAction* 通用参数。
* 如果作业的类型不是支持恢复的类型（如工作流作业 ( **PSWorkflowJob** ) ），则 **恢复作业** 将返回终止错误。
* 根据作业类型，保存挂起作业的机制和位置可能有所不同。 例如，挂起的工作流作业默认保存在平面文件存储中，但是也可能保存在 SQL 数据库中。
* 恢复作业后，作业状态将从 **Suspended** 更改为 **Running** 。 若要查找正在运行的作业，包括已由此 cmdlet 恢复的作业，请使用 **get-help** Cmdlet 的 *State* 参数获取处于 **运行** 状态的作业。
* 某些作业类型具有可阻止 Windows PowerShell 挂起作业的选项或属性。 如果挂起作业的尝试失败，请验证作业选项和属性是否允许挂起。

## 相关链接

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
