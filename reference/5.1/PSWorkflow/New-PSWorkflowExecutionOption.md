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
# New-PSWorkflowExecutionOption

## 摘要

创建一个包含用于工作流会话的会话配置选项的对象。

## SYNTAX

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## DESCRIPTION

`New-PSWorkflowExecutionOption`Cmdlet 将创建一个对象，该对象包含用于工作流会话配置的高级选项，这是用于运行 Windows PowerShell 工作流工作流的会话配置。

你可以使用 **new-psworkflowexecutionoption** 对象，该对象 `New-PSWorkflowExecutionOption` 生成为创建或更改会话配置的 cmdlet 的 **SessionTypeOption** 参数的值，如 `Register-PSSessionConfiguration` 和 `Set-PSSessionConfiguration` cmdlet。

Cmdlet 的每个参数都 `New-PSWorkflowExecutionOption` 表示 cmdlet 返回的工作流会话配置选项对象的属性。 如果省略某个参数，则 cmdlet 将使用该属性的默认值创建对象。

`New-PSWorkflowExecutionOption`Cmdlet 是 Windows PowerShell 工作流功能的一部分。

你还可以将工作流通用参数添加到此命令。 有关工作流通用参数的详细信息，请参阅 [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：创建工作流选项对象

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

此命令使用 `New-PSWorkflowExecutionOption` cmdlet 将 **MaxSessionsPerWorkflow** 值增加到10，并将 **MaxDisconnectedSessions** 值减小为200。

输出显示了 cmdlet 返回的对象。

### 示例 2：使用工作流选项对象

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

前两个命令创建一个新的会话配置对象并对其进行注册。

第三个命令使用 `Get-PSSessionConfiguration` cmdlet 来获取 ITWorkflows 会话配置，并使用 `Format-List` 来在列表中显示会话配置的所有属性。此输出显示会话配置中的工作流选项。 具体来说，会话配置具有值为 10 的 **MaxSessionsPerWorkflow** 属性以及值为 200 的 **MaxDisconnectedSessions** 属性。

## PARAMETERS

### -ActivityProcessIdleTimeoutSec

确定在每个活动主机进程进入空闲状态后，维护该进程所需的时间。 当时间间隔到期时，该进程将关闭。

输入一个值（以秒为单位）。 默认值为 60。

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

### -AllowedActivity

指定允许在会话中运行的活动。

输入命名空间限定的活动名称，例如 `Microsoft.Powershell.HyperV.Activities.*` 。
支持使用通配符。 默认值 **PSDefaultActivities** 包括内置的 Windows Workflow Foundation 活动和表示 Windows PowerShell Core cmdlet 的活动。

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

### -EnableValidation

验证会话中的所有工作流活动均包含在允许的活动列表中。

默认值为 True。 若要禁用验证，请使用以下命令格式：`-EnableValidation:$false`。

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

### -MaxActivityProcesses

指定为支持工作流活动而在会话中创建的最大进程数。 默认值为 5。

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

### -MaxConnectedSessions

指定处于操作状态的最大远程会话数。 此配额适用于连接到所有远程节点（目标计算机）的会话。 默认值为 100。

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

### -MaxDisconnectedSessions

指定处于断开连接状态的最大远程会话数。 此配额适用于连接到所有远程节点（目标计算机）的会话。 默认值为 1000。

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

### -MaxPersistenceStoreSizeGB

指定分配给在会话中运行的工作流的暂留存储的最大大小（以千兆字节为单位）。 超过此大小时，将扩展暂留存储以保存所有永久性数据，但会显示一个警告并向工作流事件日志中写入一条消息。 默认值为 10。

暂留存储包含所有工作流作业的数据。 通过存储数据功能，可在不丢失状态的情况下恢复作业。

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

### -MaxRunningWorkflows

指定可在会话中并发运行的最大工作流数。
默认值为 30。

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

### -MaxSessionsPerRemoteNode

指定可连接到每个远程节点（目标计算机）的最大会话数。 默认值为 5。

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

### -MaxSessionsPerWorkflow

指定为支持每个工作流而创建的最大会话数。 默认值为 5。

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

### -OutOfProcessActivity

确定可在进程外运行哪些允许的活动（由 **AllowedActivities** 参数指定）。 默认值为 **InlineScript** 。

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

### -PersistencePath

在磁盘上指定存储工作流状态和数据的位置。 通过存储工作流状态和数据，可挂起和恢复工作流，以及从中断和网络故障中恢复工作流。

默认值是 `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`。

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

### -PersistWithEncryption

指示工作流加密持久性存储区中的数据。 将永久性数据存储在网络共享中时，请考虑使用此功能。

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

### -RemoteNodeSessionIdleTimeoutSec

指定在连接到远程节点（目标计算机）的会话进入空闲状态后，维护该会话所需的时间。

输入一个值（以秒为单位）。 默认值为 60。

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

### -SessionThrottleLimit

指定为支持在会话中启动的所有工作流而创建的操作数。 默认值为 100。

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

### -WorkflowShutdownTimeoutMSec

指定在强行挂起会话中的所有工作流后，维护该会话所需的时间。 当超时到期时，Windows PowerShell 将关闭该会话，即使尚未挂起所有工作流也是如此。

输入一个值（以毫秒为单位）。
默认值为 500。

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

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### 无

不能通过管道将输入传递给此 cmdlet。

## 输出

### Microsoft.PowerShell.Commands.PSWorkflowExecutionOption

## 注释

当超过由某个选项设置的最大值时，除非参数说明中另有说明，否则用于在该会话中创建另一个实例的命令将失败。 例如，如果 **MaxConnectedSessions** 的值为 100， 用于向远程节点（目标计算机）创建第 101 个会话的命令将失败。

会话配置对象的属性会根据为会话配置设置的选项以及这些选项的值而有所不同。 此外，使用会话配置文件的会话配置还具有其他属性。

特别是，包括 **PSWorkflowExecutionOptions** 对象的会话配置的属性会根据工作流选项值而有所不同。 例如，如果会话配置包括为 **SessionThrottleLimit** 属性设置了一个非默认值的 **PSWorkflowExecutionOptions** 对象，会话配置将具有 **SessionThrottleLimit** 属性。 否则，它不具有该属性。

## 相关链接

[New-PSWorkflowSession](New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
