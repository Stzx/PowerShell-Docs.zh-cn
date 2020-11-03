---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 6ab50342e963832d89b3dfc4128a22fc16405926
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197611"
---
# Suspend-Job

## 摘要
暂时停止工作流作业。

## SYNTAX

### SessionIdParameterSet（默认值）

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### JobParameterSet

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameParameterSet

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilterParameterSet

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StateParameterSet

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**挂起作业** cmdlet 将挂起工作流作业。
"挂起" 表示暂时中断或暂停工作流作业。
此 cmdlet 允许运行工作流的用户挂起该工作流。
它补充挂起工作流 https://go.microsoft.com/fwlink/?LinkId=267141 活动，这是工作流中挂起工作流的命令。

**Suspend-Job** cmdlet 仅适用于工作流作业。
它不适用于标准后台作业，例如通过使用 Start-Job cmdlet 启动的作业。

若要标识工作流作业，请查找该作业的 **PSJobTypeName** 属性中的 PSWorkflowJob 值。
若要确定某个特定的自定义作业类型是否支持 **Suspend-Job** cmdlet，请参阅自定义作业类型的帮助主题。

挂起工作流作业时，工作流作业将运行到下一个检查点、挂起，然后立即返回一个工作流作业对象。
若要在获取作业之前等待挂起完成，请使用 *Wait* 参数（属于 **Suspend-Job** ）或 Wait-Job cmdlet.
挂起工作流作业时，将挂起该作业的 **State** 属性的值。

能否正确挂起取决于检查点。
当前作业状态、元数据和输出都保存在检查点中，因此可以在不丢失状态或数据的情况下恢复工作流作业。
如果工作流作业不具有检查点，则无法将其正确挂起。
若要向运行中的工作流添加检查点，请使用 *PSPersist* 工作流通用参数。
您可以使用 *Force* 参数立即挂起任何工作流作业并挂起不具有检查点的工作流作业，但该操作可能会导致状态和数据丢失。

在对自定义作业类型（例如工作流作业 ( **PSWorkflowJob** ）使用作业 cmdlet 之前) 导入支持该自定义作业类型的模块，方法是使用 Import-Module cmdlet 或使用或使用模块中的 cmdlet。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：按名称挂起工作流作业

```
The first command creates the Get-SystemLog workflow. The workflow uses the CheckPoint-Workflow activity to define a checkpoint in the workflow.
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

The second command uses the *AsJob* parameter that is common to all workflows to run the Get-SystemLog workflow as a background job. The command uses the *JobName* workflow common parameter to specify a friendly name for the workflow job.
PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

The third command uses the **Get-Job** cmdlet to get the Get-SystemLogJob workflow job. The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.
PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

The fourth command uses the **Suspend-Job** cmdlet to suspend the Get-SystemLogJob job. The job runs to the checkpoint and then suspends.
PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```

此示例显示了如何挂起工作流作业。

### 示例 2：挂起和恢复工作流作业

```
The first command suspends the LogWorkflowJob job.The command returns immediately. The output shows that the workflow job is still running, even though it is being suspended.
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

The second command uses the **Get-Job** cmdlet to get the LogWorkflowJob job. The output shows that the workflow job suspended successfully.
PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

The third command uses the **Get-Job** cmdlet to get the LogWorkflowJob job and the Resume-Job cmdlet to resume it. The output shows that the workflow job resumed successfully and is now running.
PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```

此示例显示了如何挂起和恢复工作流作业。

### 示例 3：挂起远程计算机上的工作流作业

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

此命令使用 Invoke-Command cmdlet 挂起 Srv01 远程计算机上的工作流作业。
*Filter* 参数的值是指定 CustomID 值的哈希表。
此 **CustomID** 是作业元数据 ( **PSPrivateMetadata** )。

### 示例 4：待工作流作业挂起

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

此命令将挂起 VersionCheck 工作流作业。
该命令使用 *Wait* 参数等待工作流作业挂起。
当工作流作业运行到下一个检查点并被挂起时，该命令完成并返回作业对象。

### 示例 5：强制工作流作业挂起

```
PS C:\> Suspend-Job Maintenance -Force
```

此命令将强制挂起 Maintenance 工作流作业。
维护作业没有检查点。
它无法正确挂起，并且可能无法正确恢复。

## PARAMETERS

### -Filter
指定条件的哈希表。
此 cmdlet 将挂起满足所有条件的作业。
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

### -Force
立即挂起工作流作业。
此操作可能会导致状态和数据丢失。

默认情况下， **Suspend-Job** 允许工作流作业运行到下一个检查点，然后将它挂起。
还可以使用此参数挂起不具有检查点的工作流作业。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
指定此 cmdlet 挂起的作业的 Id。

ID 是一个整数，用于唯一标识当前会话中的作业。
它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。
你可以键入一个或多个 Id （以逗号分隔）。
若要查找某个作业的 ID，请使用 Get-Job cmdlet。

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
指定此 cmdlet 挂起的作业的实例 Id。
默认值为所有作业。

实例 ID 是一个 GUID，用于在计算机上唯一标识作业。
若要查找作业的实例 ID，请使用 **Get-Job** 。

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
指定此 cmdlet 停止的工作流作业。
请输入包含工作流作业的变量或可获取工作流作业的命令。
还可以通过管道将工作流作业传递给 **Suspend-Job** cmdlet。

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
指定此 cmdlet 挂起的作业的友好名称。
输入一个或多个工作流作业名称。
支持使用通配符。

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
指定作业状态。
此 cmdlet 仅停止处于指定状态的作业。
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

**挂起-作业** 仅挂起处于 **运行** 状态的工作流作业。

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
指示此 cmdlet 禁止显示命令提示符，直到工作流作业处于挂起状态。
默认情况下，即使工作流作业尚未处于挂起状态， **挂起作业** 也会立即返回。

*Wait* 参数等效于通过管道将 **挂起作业** 命令传递给 **Wait** cmdlet。

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
但是，如果 **挂起作业** 获取不受支持的类型的作业，它将返回终止错误。

## 输出

### System.Management.Automation.Job
此 cmdlet 将返回它挂起的作业。

## 注释

* 根据作业类型，保存挂起作业的机制和位置可能有所不同。 例如，挂起的工作流作业默认保存在平面文件存储中，但是也可能保存在数据库中。
* 如果提交非 Running 状态的工作流作业，则 **Suspend-Job** 会显示一条警告消息。 若要禁止显示警告，请使用值为 SilentlyContinue 的 *WarningAction* 通用参数。

  如果作业不属于支持挂起的类型，则 **挂起作业** 返回终止错误。

* 若要查找挂起的工作流作业，包括此 cmdlet 挂起的工作流作业，请使用 **get-help** Cmdlet 的 *State* 参数获取处于挂起状态的工作流作业。
* 某些作业类型具有可阻止 Windows PowerShell 挂起作业的选项或属性。 如果挂起作业的尝试失败，请验证作业选项和属性是否允许挂起。

## 相关链接

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
