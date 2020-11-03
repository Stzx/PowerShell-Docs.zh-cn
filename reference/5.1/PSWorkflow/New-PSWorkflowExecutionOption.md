---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199002"
---
# <span data-ttu-id="ae523-103">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="ae523-103">New-PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="ae523-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ae523-104">SYNOPSIS</span></span>

<span data-ttu-id="ae523-105">创建一个包含用于工作流会话的会话配置选项的对象。</span><span class="sxs-lookup"><span data-stu-id="ae523-105">Creates an object that contains session configuration options for workflow sessions.</span></span>

## <span data-ttu-id="ae523-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ae523-106">SYNTAX</span></span>

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="ae523-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ae523-107">DESCRIPTION</span></span>

<span data-ttu-id="ae523-108">`New-PSWorkflowExecutionOption`Cmdlet 将创建一个对象，该对象包含用于工作流会话配置的高级选项，这是用于运行 Windows PowerShell 工作流工作流的会话配置。</span><span class="sxs-lookup"><span data-stu-id="ae523-108">The `New-PSWorkflowExecutionOption` cmdlet creates an object that contains advanced options for workflow session configurations, that is session configurations designed to run Windows PowerShell Workflow workflows.</span></span>

<span data-ttu-id="ae523-109">你可以使用 **new-psworkflowexecutionoption** 对象，该对象 `New-PSWorkflowExecutionOption` 生成为创建或更改会话配置的 cmdlet 的 **SessionTypeOption** 参数的值，如 `Register-PSSessionConfiguration` 和 `Set-PSSessionConfiguration` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae523-109">You can use the **PSWorkflowExecutionOption** object that `New-PSWorkflowExecutionOption` generates as the value of the **SessionTypeOption** parameter of cmdlets that create or change a session configuration, such as the `Register-PSSessionConfiguration` and `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="ae523-110">Cmdlet 的每个参数都 `New-PSWorkflowExecutionOption` 表示 cmdlet 返回的工作流会话配置选项对象的属性。</span><span class="sxs-lookup"><span data-stu-id="ae523-110">Each parameter of the `New-PSWorkflowExecutionOption` cmdlet represents a property of the workflow session configuration option object that the cmdlet returns.</span></span> <span data-ttu-id="ae523-111">如果省略某个参数，则 cmdlet 将使用该属性的默认值创建对象。</span><span class="sxs-lookup"><span data-stu-id="ae523-111">If you omit a parameter, the cmdlet creates the object with a default value for the property.</span></span>

<span data-ttu-id="ae523-112">`New-PSWorkflowExecutionOption`Cmdlet 是 Windows PowerShell 工作流功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="ae523-112">The `New-PSWorkflowExecutionOption` cmdlet is part of the Windows PowerShell Workflow feature.</span></span>

<span data-ttu-id="ae523-113">你还可以将工作流通用参数添加到此命令。</span><span class="sxs-lookup"><span data-stu-id="ae523-113">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="ae523-114">有关工作流通用参数的详细信息，请参阅 [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ae523-114">For more information about workflow common parameters, see [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span></span>

<span data-ttu-id="ae523-115">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ae523-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="ae523-116">示例</span><span class="sxs-lookup"><span data-stu-id="ae523-116">EXAMPLES</span></span>

### <span data-ttu-id="ae523-117">示例 1：创建工作流选项对象</span><span class="sxs-lookup"><span data-stu-id="ae523-117">Example 1: Create a Workflow Options Object</span></span>

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

<span data-ttu-id="ae523-118">此命令使用 `New-PSWorkflowExecutionOption` cmdlet 将 **MaxSessionsPerWorkflow** 值增加到10，并将 **MaxDisconnectedSessions** 值减小为200。</span><span class="sxs-lookup"><span data-stu-id="ae523-118">This command uses the `New-PSWorkflowExecutionOption` cmdlet to increase the **MaxSessionsPerWorkflow** value to 10 and decrease the **MaxDisconnectedSessions** value to 200.</span></span>

<span data-ttu-id="ae523-119">输出显示了 cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="ae523-119">The output shows the object that the cmdlet returns.</span></span>

### <span data-ttu-id="ae523-120">示例 2：使用工作流选项对象</span><span class="sxs-lookup"><span data-stu-id="ae523-120">Example 2: Using a Workflow Options Object</span></span>

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="ae523-121">前两个命令创建一个新的会话配置对象并对其进行注册。</span><span class="sxs-lookup"><span data-stu-id="ae523-121">The first two commands create a new session configuration object and registers it.</span></span>

<span data-ttu-id="ae523-122">第三个命令使用 `Get-PSSessionConfiguration` cmdlet 来获取 ITWorkflows 会话配置，并使用 `Format-List` 来在列表中显示会话配置的所有属性。此输出显示会话配置中的工作流选项。</span><span class="sxs-lookup"><span data-stu-id="ae523-122">The third command uses the `Get-PSSessionConfiguration` cmdlet to the get the ITWorkflows session configuration and the `Format-List` to display all properties of the session configuration in a list.The output shows that the workflow options in the session configuration.</span></span> <span data-ttu-id="ae523-123">具体来说，会话配置具有值为 10 的 **MaxSessionsPerWorkflow** 属性以及值为 200 的 **MaxDisconnectedSessions** 属性。</span><span class="sxs-lookup"><span data-stu-id="ae523-123">Specifically, the session configuration has a **MaxSessionsPerWorkflow** property with a value of 10 and a **MaxDisconnectedSessions** property with a value of 200.</span></span>

## <span data-ttu-id="ae523-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ae523-124">PARAMETERS</span></span>

### <span data-ttu-id="ae523-125">-ActivityProcessIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="ae523-125">-ActivityProcessIdleTimeoutSec</span></span>

<span data-ttu-id="ae523-126">确定在每个活动主机进程进入空闲状态后，维护该进程所需的时间。</span><span class="sxs-lookup"><span data-stu-id="ae523-126">Determines how long each activity host process is maintained after the process becomes idle.</span></span> <span data-ttu-id="ae523-127">当时间间隔到期时，该进程将关闭。</span><span class="sxs-lookup"><span data-stu-id="ae523-127">When the interval expires, the process closes.</span></span>

<span data-ttu-id="ae523-128">输入一个值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="ae523-128">Enter a value in seconds.</span></span> <span data-ttu-id="ae523-129">默认值为 60。</span><span class="sxs-lookup"><span data-stu-id="ae523-129">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-130">-AllowedActivity</span><span class="sxs-lookup"><span data-stu-id="ae523-130">-AllowedActivity</span></span>

<span data-ttu-id="ae523-131">指定允许在会话中运行的活动。</span><span class="sxs-lookup"><span data-stu-id="ae523-131">Specifies the activities that are permitted to run in the session.</span></span>

<span data-ttu-id="ae523-132">输入命名空间限定的活动名称，例如 `Microsoft.Powershell.HyperV.Activities.*` 。</span><span class="sxs-lookup"><span data-stu-id="ae523-132">Enter namespace-qualified activity names, such as `Microsoft.Powershell.HyperV.Activities.*`.</span></span>
<span data-ttu-id="ae523-133">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ae523-133">Wildcard characters are supported.</span></span> <span data-ttu-id="ae523-134">默认值 **PSDefaultActivities** 包括内置的 Windows Workflow Foundation 活动和表示 Windows PowerShell Core cmdlet 的活动。</span><span class="sxs-lookup"><span data-stu-id="ae523-134">The default value, **PSDefaultActivities** , includes the built-in Windows Workflow Foundation activities and the activities that represent the Windows PowerShell Core cmdlets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-135">-EnableValidation</span><span class="sxs-lookup"><span data-stu-id="ae523-135">-EnableValidation</span></span>

<span data-ttu-id="ae523-136">验证会话中的所有工作流活动均包含在允许的活动列表中。</span><span class="sxs-lookup"><span data-stu-id="ae523-136">Verifies that all workflow activities in the session are included in the allowed activities list.</span></span>

<span data-ttu-id="ae523-137">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="ae523-137">The default value is True.</span></span> <span data-ttu-id="ae523-138">若要禁用验证，请使用以下命令格式：`-EnableValidation:$false`。</span><span class="sxs-lookup"><span data-stu-id="ae523-138">To disable validation, use the following command format: `-EnableValidation:$false`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-139">-MaxActivityProcesses</span><span class="sxs-lookup"><span data-stu-id="ae523-139">-MaxActivityProcesses</span></span>

<span data-ttu-id="ae523-140">指定为支持工作流活动而在会话中创建的最大进程数。</span><span class="sxs-lookup"><span data-stu-id="ae523-140">Specifies the maximum number of processes that can be created in the session to support workflow activities.</span></span> <span data-ttu-id="ae523-141">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="ae523-141">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-142">-MaxConnectedSessions</span><span class="sxs-lookup"><span data-stu-id="ae523-142">-MaxConnectedSessions</span></span>

<span data-ttu-id="ae523-143">指定处于操作状态的最大远程会话数。</span><span class="sxs-lookup"><span data-stu-id="ae523-143">Specifies the maximum number of remote sessions that are in an operational state.</span></span> <span data-ttu-id="ae523-144">此配额适用于连接到所有远程节点（目标计算机）的会话。</span><span class="sxs-lookup"><span data-stu-id="ae523-144">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="ae523-145">默认值为 100。</span><span class="sxs-lookup"><span data-stu-id="ae523-145">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-146">-MaxDisconnectedSessions</span><span class="sxs-lookup"><span data-stu-id="ae523-146">-MaxDisconnectedSessions</span></span>

<span data-ttu-id="ae523-147">指定处于断开连接状态的最大远程会话数。</span><span class="sxs-lookup"><span data-stu-id="ae523-147">Specifies the maximum number of remote sessions that are in a disconnected state.</span></span> <span data-ttu-id="ae523-148">此配额适用于连接到所有远程节点（目标计算机）的会话。</span><span class="sxs-lookup"><span data-stu-id="ae523-148">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="ae523-149">默认值为 1000。</span><span class="sxs-lookup"><span data-stu-id="ae523-149">The default value is 1000.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-150">-MaxPersistenceStoreSizeGB</span><span class="sxs-lookup"><span data-stu-id="ae523-150">-MaxPersistenceStoreSizeGB</span></span>

<span data-ttu-id="ae523-151">指定分配给在会话中运行的工作流的暂留存储的最大大小（以千兆字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ae523-151">Specifies the maximum size, in gigabytes, of the persistence store allocated to workflows that run in the session.</span></span> <span data-ttu-id="ae523-152">超过此大小时，将扩展暂留存储以保存所有永久性数据，但会显示一个警告并向工作流事件日志中写入一条消息。</span><span class="sxs-lookup"><span data-stu-id="ae523-152">When the size is exceeded, the persistence store is expanded to save all persisted data, but a warning is displayed and a message is written to the workflow event log.</span></span> <span data-ttu-id="ae523-153">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="ae523-153">The default value is 10.</span></span>

<span data-ttu-id="ae523-154">暂留存储包含所有工作流作业的数据。</span><span class="sxs-lookup"><span data-stu-id="ae523-154">The persistence store contains data for all workflow jobs.</span></span> <span data-ttu-id="ae523-155">通过存储数据功能，可在不丢失状态的情况下恢复作业。</span><span class="sxs-lookup"><span data-stu-id="ae523-155">The ability to store data allows the jobs to resume without losing state.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-156">-MaxRunningWorkflows</span><span class="sxs-lookup"><span data-stu-id="ae523-156">-MaxRunningWorkflows</span></span>

<span data-ttu-id="ae523-157">指定可在会话中并发运行的最大工作流数。</span><span class="sxs-lookup"><span data-stu-id="ae523-157">Specifies that maximum number of workflows that can run in the session concurrently.</span></span>
<span data-ttu-id="ae523-158">默认值为 30。</span><span class="sxs-lookup"><span data-stu-id="ae523-158">The default value is 30.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-159">-MaxSessionsPerRemoteNode</span><span class="sxs-lookup"><span data-stu-id="ae523-159">-MaxSessionsPerRemoteNode</span></span>

<span data-ttu-id="ae523-160">指定可连接到每个远程节点（目标计算机）的最大会话数。</span><span class="sxs-lookup"><span data-stu-id="ae523-160">Specifies the maximum number of sessions that can be connected to each remote node (target computer).</span></span> <span data-ttu-id="ae523-161">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="ae523-161">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-162">-MaxSessionsPerWorkflow</span><span class="sxs-lookup"><span data-stu-id="ae523-162">-MaxSessionsPerWorkflow</span></span>

<span data-ttu-id="ae523-163">指定为支持每个工作流而创建的最大会话数。</span><span class="sxs-lookup"><span data-stu-id="ae523-163">Specifies the maximum number of session that can be created to support each workflow.</span></span> <span data-ttu-id="ae523-164">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="ae523-164">The default value is 5.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-165">-OutOfProcessActivity</span><span class="sxs-lookup"><span data-stu-id="ae523-165">-OutOfProcessActivity</span></span>

<span data-ttu-id="ae523-166">确定可在进程外运行哪些允许的活动（由 **AllowedActivities** 参数指定）。</span><span class="sxs-lookup"><span data-stu-id="ae523-166">Determines which allowed activities (specified by the **AllowedActivities** parameter) run out-of-process.</span></span> <span data-ttu-id="ae523-167">默认值为 **InlineScript** 。</span><span class="sxs-lookup"><span data-stu-id="ae523-167">The default value is **InlineScript** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-168">-PersistencePath</span><span class="sxs-lookup"><span data-stu-id="ae523-168">-PersistencePath</span></span>

<span data-ttu-id="ae523-169">在磁盘上指定存储工作流状态和数据的位置。</span><span class="sxs-lookup"><span data-stu-id="ae523-169">Specifies the location on disk where workflow state and data are stored.</span></span> <span data-ttu-id="ae523-170">通过存储工作流状态和数据，可挂起和恢复工作流，以及从中断和网络故障中恢复工作流。</span><span class="sxs-lookup"><span data-stu-id="ae523-170">Storing the workflow state and data allows workflows to be suspended and resumed, and to recover from interruptions and network failures.</span></span>

<span data-ttu-id="ae523-171">默认值是 `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`。</span><span class="sxs-lookup"><span data-stu-id="ae523-171">The default value is `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-172">-PersistWithEncryption</span><span class="sxs-lookup"><span data-stu-id="ae523-172">-PersistWithEncryption</span></span>

<span data-ttu-id="ae523-173">指示工作流加密持久性存储区中的数据。</span><span class="sxs-lookup"><span data-stu-id="ae523-173">Indicates that the workflow encrypts the data in the persistence store.</span></span> <span data-ttu-id="ae523-174">将永久性数据存储在网络共享中时，请考虑使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ae523-174">Consider using this feature when storing persistence data in a network share.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-175">-RemoteNodeSessionIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="ae523-175">-RemoteNodeSessionIdleTimeoutSec</span></span>

<span data-ttu-id="ae523-176">指定在连接到远程节点（目标计算机）的会话进入空闲状态后，维护该会话所需的时间。</span><span class="sxs-lookup"><span data-stu-id="ae523-176">Specifies how long a session that is connected to a remote node (target computer) is maintained if it is idle.</span></span>

<span data-ttu-id="ae523-177">输入一个值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="ae523-177">Enter a value in seconds.</span></span> <span data-ttu-id="ae523-178">默认值为 60。</span><span class="sxs-lookup"><span data-stu-id="ae523-178">The default value is 60.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-179">-SessionThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="ae523-179">-SessionThrottleLimit</span></span>

<span data-ttu-id="ae523-180">指定为支持在会话中启动的所有工作流而创建的操作数。</span><span class="sxs-lookup"><span data-stu-id="ae523-180">Specifies how many operations are created to support all workflows started in the session.</span></span> <span data-ttu-id="ae523-181">默认值为 100。</span><span class="sxs-lookup"><span data-stu-id="ae523-181">The default value is 100.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-182">-WorkflowShutdownTimeoutMSec</span><span class="sxs-lookup"><span data-stu-id="ae523-182">-WorkflowShutdownTimeoutMSec</span></span>

<span data-ttu-id="ae523-183">指定在强行挂起会话中的所有工作流后，维护该会话所需的时间。</span><span class="sxs-lookup"><span data-stu-id="ae523-183">Specifies how long the session is maintained after all workflows in the session are forcibly suspended.</span></span> <span data-ttu-id="ae523-184">当超时到期时，Windows PowerShell 将关闭该会话，即使尚未挂起所有工作流也是如此。</span><span class="sxs-lookup"><span data-stu-id="ae523-184">When the timeout expires, Windows PowerShell closes the session, even if all workflows are not yet suspended.</span></span>

<span data-ttu-id="ae523-185">输入一个值（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="ae523-185">Enter a value in milliseconds.</span></span>
<span data-ttu-id="ae523-186">默认值为 500。</span><span class="sxs-lookup"><span data-stu-id="ae523-186">The default value is 500.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae523-187">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ae523-187">CommonParameters</span></span>

<span data-ttu-id="ae523-188">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ae523-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ae523-189">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ae523-189">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ae523-190">输入</span><span class="sxs-lookup"><span data-stu-id="ae523-190">INPUTS</span></span>

### <span data-ttu-id="ae523-191">无</span><span class="sxs-lookup"><span data-stu-id="ae523-191">None</span></span>

<span data-ttu-id="ae523-192">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae523-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="ae523-193">输出</span><span class="sxs-lookup"><span data-stu-id="ae523-193">OUTPUTS</span></span>

### <span data-ttu-id="ae523-194">Microsoft.PowerShell.Commands.PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="ae523-194">Microsoft.PowerShell.Commands.PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="ae523-195">注释</span><span class="sxs-lookup"><span data-stu-id="ae523-195">NOTES</span></span>

<span data-ttu-id="ae523-196">当超过由某个选项设置的最大值时，除非参数说明中另有说明，否则用于在该会话中创建另一个实例的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="ae523-196">When the maximum value set by an option is exceeded, the command to create another instance in the session fails, unless noted in the parameter description.</span></span> <span data-ttu-id="ae523-197">例如，如果 **MaxConnectedSessions** 的值为 100，</span><span class="sxs-lookup"><span data-stu-id="ae523-197">For example, if the value of **MaxConnectedSessions** is 100.</span></span> <span data-ttu-id="ae523-198">用于向远程节点（目标计算机）创建第 101 个会话的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="ae523-198">The command to create the 101st session to a remote node (target computer) fails.</span></span>

<span data-ttu-id="ae523-199">会话配置对象的属性会根据为会话配置设置的选项以及这些选项的值而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ae523-199">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="ae523-200">此外，使用会话配置文件的会话配置还具有其他属性。</span><span class="sxs-lookup"><span data-stu-id="ae523-200">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="ae523-201">特别是，包括 **PSWorkflowExecutionOptions** 对象的会话配置的属性会根据工作流选项值而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ae523-201">In particular, the properties of session configurations that include a **PSWorkflowExecutionOptions** object vary based on the workflow option values.</span></span> <span data-ttu-id="ae523-202">例如，如果会话配置包括为 **SessionThrottleLimit** 属性设置了一个非默认值的 **PSWorkflowExecutionOptions** 对象，会话配置将具有 **SessionThrottleLimit** 属性。</span><span class="sxs-lookup"><span data-stu-id="ae523-202">For example, if the session configuration includes a **PSWorkflowExecutionOptions** object that sets a non-default value for the **SessionThrottleLimit** property, the session configuration has a **SessionThrottleLimit** property.</span></span> <span data-ttu-id="ae523-203">否则，它不具有该属性。</span><span class="sxs-lookup"><span data-stu-id="ae523-203">Otherwise, it does not.</span></span>

## <span data-ttu-id="ae523-204">相关链接</span><span class="sxs-lookup"><span data-stu-id="ae523-204">RELATED LINKS</span></span>

[<span data-ttu-id="ae523-205">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="ae523-205">New-PSWorkflowSession</span></span>](New-PSWorkflowSession.md)

[<span data-ttu-id="ae523-206">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="ae523-206">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="ae523-207">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="ae523-207">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
