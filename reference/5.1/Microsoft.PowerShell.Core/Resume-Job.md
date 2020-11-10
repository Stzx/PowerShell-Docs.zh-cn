---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/resume-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resume-Job
ms.openlocfilehash: 6d08d9053e100cb53d37a6e4931d118f90c35a6a
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388529"
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

`Resume-Job`Cmdlet 可恢复已挂起的工作流作业，例如通过使用 `Suspend-Job` cmdlet 或[about_Suspend-workflow](../PSWorkflow/about/about_Suspend-Workflow.md)活动。 工作流作业恢复后，作业引擎将从已保存的资源（如检查点）重新构建状态、元数据和输出。 在不丢失任何状态或数据的情况下重新启动作业。
作业状态将从 **Suspended** 更改为 **Running** 。

使用的参数 `Resume-Job` 可按名称、id、实例 ID 或管道将作业对象（如 cmdlet 返回的作业对象）选择 `Get-Job` 为 `Resume-Job` 。 还可以使用属性筛选器来选择要恢复的作业。

默认情况下， `Resume-Job` 即使可能尚未恢复所有作业，也会立即返回。 若要在恢复所有指定的作业之前禁止显示命令提示符，请使用 **Wait** 参数。

此 `Resume-Job` cmdlet 仅适用于自定义作业类型，例如工作流作业。 它不适用于标准后台作业，如使用 cmdlet 启动的作业 `Start-Job` 。 如果提交的作业的类型不受支持，则会 `Resume-Job` 生成一个终止错误并停止运行。

若要标识工作流作业，请查找该作业的 **PSWorkflowJob** 属性中的 **PSJobTypeName** 值。 若要确定某个特定的自定义作业类型是否支持该 `Resume-Job` cmdlet，请参阅自定义作业类型的帮助主题。

在自定义作业类型上使用 Job cmdlet 之前，请使用 `Import-Module` cmdlet 或获取或使用模块中的 cmdlet 导入支持该自定义作业类型的模块。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：按 ID 恢复作业

此示例中的命令将验证该作业是否为挂起的工作流作业，然后恢复该作业。 第一个命令使用 `Get-Job` cmdlet 来获取作业。 该输出显示该作业是挂起的工作流作业。 第二个命令使用 cmdlet 的 **id** 参数 `Resume-Job` 恢复 **id** 值为4的作业。

```
PS C:\> Get-Job EventJob
Id     Name            PSJobTypeName   State         HasMoreData     Location   Command
--     ----            -------------   -----         -----------     --------   -------
4      EventJob        PSWorkflowJob   Suspended     True            Server01   \\Script\Share\Event.ps1

PS C:\> Resume-Job -Id 4
```

### 示例 2：按名称恢复作业

此命令使用 **Name** 参数来恢复本地计算机上的多个工作流作业。

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest*
```

### 示例 3：使用自定义属性值

此命令使用自定义属性的值来标识要恢复的工作流作业。 它使用 **Filter** 参数来按其 **CustomID** 属性标识工作流作业。 它还使用 **State** 参数来验证在尝试恢复工作流作业之前，工作流作业是否已挂起。

```
PS C:\> Resume-Job -Filter @{CustomID="T091291"} -State Suspended
```

### 示例 4：恢复远程计算机上所有挂起的作业

此命令将恢复 Srv01 远程计算机上所有挂起的作业。

```
PS C:\> Invoke-Command -ComputerName Srv01 -ScriptBlock {Get-Job -State Suspended | Resume-Job}
```

该命令使用 `Invoke-Command` cmdlet 在 Srv01 计算机上运行命令。 远程命令使用 cmdlet 的 **State** 参数 `Get-Job` 获取计算机上所有挂起的作业。 管道运算符 (`|`) 将挂起的作业发送到 `Resume-Job` cmdlet，这会恢复它们。

### 示例5：等待作业恢复

此命令使用 **Wait** 参数定向 `Resume-Job` 到仅在恢复所有指定作业后返回。 **Wait** 参数在假定已在脚本继续运行之前恢复作业的脚本中尤其有用。

```
PS C:\> Resume-Job -Name WorkflowJob, InventoryWorkflow, WFTest* -Wait
```

### 示例6：恢复挂起自身的工作流

此代码示例显示 `Suspend-Workflow` 工作流中的活动。

`Test-Suspend`Server01 计算机上的工作流。 运行工作流时，工作流将运行 `Get-Date` 活动，并将结果存储在 `$a` 变量中。 然后运行 `Suspend-Workflow` 活动。 该工作流会采用一个检查点、挂起该工作流，并返回一个工作流作业对象来作为回复。 `Suspend-Workflow` 返回工作流作业对象，即使工作流不是作为作业显式运行。

`Resume-Job` 恢复 `Test-Suspend` Job8 中的工作流。 它使用 **Wait** 参数来保留命令提示符，直至作业恢复。

`Receive-Job`Cmdlet 将获取工作流的结果 `Test-Suspend` 。 工作流中的最后一个命令将返回一个 **TimeSpan** 对象，该对象表示当前日期和时间与在 `$a` 挂起工作流之前保存在变量中的日期和时间之间的时间间隔。

```
#SampleWorkflow
Workflow Test-Suspend
{
    $a = Get-Date
    Suspend-Workflow
    (Get-Date)- $a
}

PS C:\> Test-Suspend -PSComputerName Server01
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Suspended     True            Server01             Test-Suspend

PS C:\> Resume-Job -Name "Job8" -Wait
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
8      Job8            PSWorkflowJob   Running       True            Server01             Test-Suspend

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

`Resume-Job`Cmdlet 可让你恢复使用活动挂起的工作流作业 `Suspend-Workflow` 。 此活动将从工作流内部挂起工作流。 它仅在工作流中有效。

有关的信息 `Suspend-Workflow` ，请参阅 about_Suspend-Workflow] (。/PSWorkflow/about/about_Suspend) 。

## PARAMETERS

### -Filter

指定条件的哈希表。 此 cmdlet 将恢复满足哈希表中所有条件的作业。 输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。

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

ID 是一个整数，用于唯一标识当前会话中的作业。 它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。 你可以键入一个或多个 Id （以逗号分隔）。 若要查找作业的 ID，请运行 `Get-Job` 。

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

指定此 cmdlet 恢复的作业的实例 Id 的数组。 默认值为所有作业。

实例 ID 是一个 GUID，用于在计算机上唯一标识作业。 若要查找作业的实例 ID，请运行 `Get-Job` 。

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

指定要恢复的作业。 请输入一个包含作业的变量，或一个可获取作业的命令。 还可以通过管道将作业传递给 `Resume-Job` cmdlet。

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

指定此 cmdlet 恢复的作业的友好名称数组。 输入一个或多个作业名称。
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

指定要恢复的作业的状态。 此参数的可接受值为：

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

有关作业状态的详细信息，请参阅 [JobState 枚举](/dotnet/api/system.management.automation.jobstate)。

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

指示此 cmdlet 禁止显示命令提示符，直到重新启动所有作业结果。 默认情况下，此 cmdlet 会立即返回可用的结果。

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

显示运行该 cmdlet 时会发生什么情况。 此 cmdlet 未运行。

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

可以通过管道将所有类型的作业传递给此 cmdlet。 如果 `Resume-Job` 获取不受支持的类型的作业，它将返回终止错误。

## 输出

### 无、管理系统

如果使用 **PassThru** 参数，则此 cmdlet 将返回尝试恢复的作业。
否则，此 cmdlet 将不生成任何输出。

## 注释

- `Resume-Job` 只能恢复挂起的作业。 如果提交处于不同状态的作业，则 `Resume-Job` 对作业运行恢复操作，但是会生成一个警告，通知你无法恢复作业。 若要禁止显示警告，请使用值为 SilentlyContinue 的 **WarningAction** 通用参数。
- 如果作业不是支持恢复的类型（如工作流作业 ( **PSWorkflowJob** ) ），则 `Resume-Job` 返回终止错误。
- 根据作业类型，保存挂起作业的机制和位置可能有所不同。 例如，挂起的工作流作业默认保存在平面文件存储中，但是也可能保存在 SQL 数据库中。
- 恢复作业后，作业状态将从 **Suspended** 更改为 **Running** 。 若要查找正在运行的作业，包括已由此 cmdlet 恢复的作业，请使用 cmdlet 的 **State** 参数 `Get-Job` 获取处于 **运行** 状态的作业。
- 某些作业类型具有可阻止 Windows PowerShell 挂起作业的选项或属性。
  如果挂起作业的尝试失败，请验证作业选项和属性是否允许挂起。

## 相关链接

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
