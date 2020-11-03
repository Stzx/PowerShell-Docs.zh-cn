---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197438"
---
# Get-Job

## 摘要
获取当前会话中正在运行的 PowerShell 后台作业。

## SYNTAX

### SessionIdParameterSet（默认值）

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### CommandParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### NameParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### StateParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### FilterParameterSet

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION

**Get-Job** cmdlet 可获取表示在当前会话中启动的后台作业的对象。
你可以使用 " **获取作业** " 来获取使用 Start-Job cmdlet 或使用任何 Cmdlet 的 *AsJob* 参数启动的作业。

如果没有参数，则 **获取作业** 命令将获取当前会话中的所有作业。
可以使用 **Get-Job** 的参数获取特定作业。

**Get-Job** 返回的作业对象包含有关该作业的有用信息，但不包含作业结果。
若要获取结果，请使用 Receive-Job cmdlet。

Windows PowerShell 后台作业是在后台运行的命令，不与当前会话交互。
通常，可以使用后台作业来运行需要很长时间才能完成的复杂命令。
有关 Windows PowerShell 中的后台作业的详细信息，请参阅 about_Jobs。

从 Windows PowerShell 3.0 开始， **Get-Job** cmdlet 还可获取自定义作业类型，例如工作流作业和计划作业的实例。
若要查找作业的作业类型，请使用该作业的 **PSJobTypeName** 属性。

若要允许 **获取** 自定义作业类型，请在运行 **get job** 命令之前将支持自定义作业类型的模块导入到会话中，方法是使用 Import-Module cmdlet 或使用或在模块中获取 cmdlet。
有关特定的自定义作业类型的信息，请参阅自定义作业类型功能的文档。

## 示例

### 示例1：获取当前会话中启动的所有后台作业

```
PS C:\> Get-Job
```

此命令将获取在当前会话中启动的所有后台作业。
它不包括在其他会话中创建的作业，即使这些作业是在本地计算机上运行的也是如此。

### 示例2：使用实例 ID 停止作业

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

这些命令演示如何获取作业的实例 ID，然后用它来停止作业。
与非唯一的作业名称不同，实例 ID 是唯一的。

### 示例3：获取包含特定命令的作业

```
PS C:\> Get-Job -Command "*get-process*"
```

此命令获取系统中包含 Get-Process 命令的作业。
该命令使用 *Get-Job* 的 **Command** 参数来限制检索的作业。
该命令使用通配符 ( * ) 来获取在命令字符串中的任意位置包含一个 **Get 进程** 命令的作业。

### 示例4：使用管道获取包含特定命令的作业

```
PS C:\> "*get-process*" | Get-Job
```

与上一示例中的命令一样，此命令将获取系统上的作业，其中包含 **获取进程** 命令。
该命令使用管道运算符 (|) 向 **求职** cmdlet 发送字符串（用引号引起来）。
它等效于之前的命令。

### 示例5：获取尚未启动的作业

```
PS C:\> Get-Job -State NotStarted
```

此命令只获取那些已创建的但尚未启动的作业。
这包括计划要在将来运行的作业和尚未计划的作业。

### 示例6：获取未分配名称的作业

```
PS C:\> Get-Job -Name Job*
```

此命令获取作业名称以 job 开头的所有作业。
由于作业 \<number\> 是作业的默认名称，因此此命令将获取没有显式分配的名称的所有作业。

### 示例7：在命令中使用作业对象来表示作业

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

此示例演示如何使用 **Get-Job** 来获取作业对象，然后演示如何在命令中使用作业对象表示作业。

### 示例8：获取所有作业，包括其他方法启动的作业

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

此示例演示了 **get-help** cmdlet 可获取在当前会话中启动的所有作业，即使这些作业是使用不同的方法启动的。

### 示例9：调查失败的作业

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

此命令显示了如何使用 **获取作业** 返回的作业对象来调查作业失败的原因。
此命令还显示了如何获取每个作业的子作业。

### 示例10：获取筛选的结果

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

此示例显示如何使用 *Filter* 参数获取工作流作业。
在 Windows PowerShell 3.0 中引入的 *Filter* 参数仅在自定义作业类型（例如工作流作业和计划作业）上有效。

### 示例11：获取有关子作业的信息

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

此示例显示使用 *Get-Job* cmdlet 的 *IncludeChildJob* 和 **ChildJobState** 参数的效果。

## PARAMETERS

### -After

获取在指定日期和时间后结束完成的作业。
输入一个 DateTime 对象，例如 Get-Date cmdlet 返回的一个 **日期时间** 对象，或一个可转换为 **DateTime** 对象的字符串（例如或） `Dec 1, 2012 2:00 AM` `11/06` 。

此参数仅适用于具有 **EndTime** 属性的自定义作业类型（例如工作流作业和计划作业）。
它不适用于标准后台作业，如使用 **Start-Job** cmdlet 创建的作业。
有关支持此参数的信息，请参阅作业类型的帮助主题。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Before

获取在指定日期和时间前结束前完成的作业。
输入 **DateTime** 对象。

此参数仅适用于具有 **EndTime** 属性的自定义作业类型（例如工作流作业和计划作业）。
它不适用于标准后台作业，如使用 **Start-Job** cmdlet 创建的作业。
有关支持此参数的信息，请参阅作业类型的帮助主题。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChildJobState

只获取具有指定状态的子作业。
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

默认情况下， **Get-Job** 不会获取子作业。
使用 *IncludeChildJob* **参数获取所有** 子作业。
如果使用 *ChildJobState* 参数，则 *IncludeChildJob* 参数将不起作用。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

将命令数组指定为字符串。
此 cmdlet 将获取包含指定命令的作业。
默认值为所有作业。
您可以使用通配符来指定命令模式。

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Filter

指定条件的哈希表。
此 cmdlet 将获取满足所有条件的作业。
输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。

此参数仅适用于自定义作业类型，例如工作流作业和计划作业。
它不适用于标准后台作业，如使用 **Start-Job** cmdlet 创建的作业。
有关支持此参数的信息，请参阅作业类型的帮助主题。

已在 Windows PowerShell 3.0 中引入了此参数。

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

### -HasMoreData

指示此 cmdlet 是否仅获取具有指定的 **HasMoreData** 属性值的作业。
**HasMoreData** 属性指示当前会话中是否已接收所有作业结果。
若要获取具有更多结果的作业，请将值指定为 $True。
若要获取没有更多结果的作业，请将值指定为 $False。

若要获取作业结果，请使用 Receive-Job cmdlet。

当使用 **接收-Job** cmdlet 时，它会将其返回的结果从其内存中的特定于会话的存储中删除。
在当前会话中返回作业的所有结果后，它会将作业的 **HasMoreData** 属性的值设置为 $False) ，以指示它在当前会话中没有更多的作业结果。
使用 *Receive-Job* 的 **Keep** 参数以防止 **Receive-Job** 删除结果和更改 **HasMoreData** 属性的值。
要了解详情，请键入 `Get-Help Receive-Job`。

**HasMoreData** 属性特定于当前会话。
如果自定义作业类型的结果保存在会话之外（例如计划作业类型，它将作业结果保存在磁盘上），则可以在不同的会话中使用 **Receive** cmdlet 来再次获取作业结果，即使 **HasMoreData** 的值 $False。
有关详细信息，请参阅自定义作业类型的帮助主题。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

指定此 cmdlet 获取的作业 Id 的数组。

ID 是一个整数，用于唯一标识当前会话中的作业。
它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。
你可以键入一个或多个 Id （以逗号分隔）。
若要查找作业的 ID，请键入（ `Get-Job` 不带参数）。

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeChildJob

指示除了父作业，此 cmdlet 还将返回子作业。

此参数对于调查工作流作业特别有用，对于该工作流作业， **获取作业** 将返回容器父作业和作业失败，因为失败的原因保存在子作业的属性中。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

指定此 cmdlet 获取的作业的实例 Id 的数组。
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

### -Name

指定此 cmdlet 获取的实例的友好名称的数组。
输入作业名称，或使用通配符输入作业名称模式。
默认情况下， **Get-Job** 获取当前会话中的所有作业。

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Newest

指定要获取的作业数。
此 cmdlet 将获取最近结束的作业。

*Newest* 参数不会按结束时间的顺序对输出进行排序或返回最新的作业。
若要对输出进行排序，请使用 Sort-Object cmdlet。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State

指定作业状态。
此 cmdlet 仅获取处于指定状态的作业。
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

默认情况下， **Get-Job** 获取当前会话中的所有作业。

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

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将输入传递给此 cmdlet。

## 输出

### System.Management.Automation.RemotingJob

此 cmdlet 将返回表示会话中的作业的对象。

## 注释

* 作业的 **PSJobTypeName** 属性指示作业的作业类型。 该属性值由作业类型的作者确定。 以下列表显示了常见作业类型。

  - **BackgroundJob** 。
使用 **启动作业** 启动的本地作业。

  - **RemoteJob** 。
使用 Invoke-Command cmdlet 的 *AsJob* 参数在 **PSSession** 中启动作业。

  - **PSWorkflowJob** 。
通过使用工作流的 *AsJob* 通用参数启动的作业。

## 相关链接

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md)
