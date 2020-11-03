---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pstransportoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSTransportOption
ms.openlocfilehash: 9257c0a1829cc9cc85029f7c6fdc8e61b0ed7e56
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198972"
---
# New-PSTransportOption

## 摘要

创建包含用于会话配置的高级选项的对象。

## SYNTAX

```
New-PSTransportOption [-MaxIdleTimeoutSec <Int32>] [-ProcessIdleTimeoutSec <Int32>] [-MaxSessions <Int32>]
 [-MaxConcurrentCommandsPerSession <Int32>] [-MaxSessionsPerUser <Int32>] [-MaxMemoryPerSessionMB <Int32>]
 [-MaxProcessesPerSession <Int32>] [-MaxConcurrentUsers <Int32>] [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [<CommonParameters>]
```

## DESCRIPTION

**New-PSTransportOption** cmdlet 创建一个对象，它包含会话配置的传输选项。
可将对象用作可创建或更改会话配置的 cmdlet 的 *TransportOption* 参数值，例如 Register-PSSessionConfiguration 和 Set-PSSessionConfiguration cmdlet。

还可以通过编辑 WSMan: 驱动器中会话配置属性的值更改传输选项设置。
有关详细信息，请参阅“WSMan 提供程序”。

会话配置选项表示在服务器端或接收到远程连接时设置的会话值。
当创建会话时，或当客户端从会话断开连接或重新连接到会话时，客户端或发送连接端可以设置会话选项值。
除非另有说明，当设置值冲突时，客户端的值优先。
但是，客户端的值不能与会话配置中设置的最大值和配额发生冲突。

如果没有参数，则 **new-pstransportoption** 将生成一个传输选项对象，该对象的所有选项都具有 null 值。
如果省略一个参数，则该对象具有该参数表示的属性的 null 值。
空值不影响会话配置。

有关会话选项的详细信息，请参阅 New-PSSessionOption。
有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：生成默认传输选项

```
PS C:\> New-PSTransportOption
ProcessIdleTimeoutSec           :
MaxIdleTimeoutSec               :
MaxSessions                     :
MaxConcurrentCommandsPerSession :
MaxSessionsPerUser              :
MaxMemoryPerSessionMB           :
MaxProcessesPerSession          :
MaxConcurrentUsers              :
IdleTimeoutSec                  :
OutputBufferingMode             :
```

此命令运行不带参数的 **new-pstransportoption** 。
输出显示该 cmdlet 将生成一个传输选项对象，该对象的所有属性都具有 null 值。

### 示例2：获取会话配置选项

```
The first command uses the **New-PSTransportOption** cmdlet to create a transport options object, which it saves in the $t variable. The command uses the *MaxSessions* parameter to increase the maximum number of sessions to 40.
PS C:\> $t = New-PSTransportOption -MaxSessions 40

The second command uses the **Register-PSSessionConfiguration** cmdlet create the ITTasks session configuration. The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.
PS C:\> Register-PSSessionConfiguration -Name ITTasks -TransportOption $t

The third command uses the Get-PSSessionConfiguration cmdlet to get the ITTasks session configurations and the Format-List cmdlet to display all of the properties of the session configuration object in a list. The output shows that the value of the **MaxShells** property of the session configuration is 40.
PS C:\> Get-PSSessionConfiguration -Name ITTasks | Format-List -Property *
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITTasks
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 40
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 2
Name                          : ITTasks
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
Enabled                       : True
MaxShellsPerUser              : 25
Permission                    :
```

此示例显示了如何使用传输选项对象来设置会话配置选项。

### 示例3：设置传输选项

```
The first command uses the **New-PSTransportOption** cmdlet to create a transport option object. The command uses the *IdleTimeoutSec* parameter to set the **IdleTimeoutSec** property value of the object to one hour (3600 seconds). The command saves the transport objects object in the $t variable.
PS C:\> $t = New-PSTransportOption -IdleTimeoutSec 3600

The second command uses the Set-PSSessionConfiguration cmdlet to change the transport options of the ITTasks session configuration. The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.
PS C:\> Set-PSSessionConfiguration -Name ITTasks -TransportOption $t

The third command uses the New-PSSession cmdlet to create the MyITTasks session on the local computer. The command uses the **ConfigurationName** property to specify the ITTasks session configuration. The command saves the session in the $s variable.Notice that the command does not use the *SessionOption* parameter of **New-PSSession** to set a custom idle time-out for the session. If it did, the idle time-out value set in the session option would take precedence over the idle time-out set in the session configuration.
PS C:\> $s = New-PSSession -Name MyITTasks -ConfigurationName ITTasks

The fourth command uses the Format-List cmdlet to display all properties of the session in the $s variable in a list. The output shows that the session has an idle time-out of one hour (360,000 milliseconds).
PS C:\> $s | Format-List -Property *
State                  : Opened
IdleTimeout            : 3600000
OutputBufferingMode    : Block
ComputerName           : localhost
ConfigurationName      : ITTasks
InstanceId             : 4110c3f5-68ea-40fa-9bbf-04a433dbb02d
Id                     : 1
Name                   : MyITTasks
Availability           : Available
ApplicationPrivateData : {PSVersionTable}
Runspace               : System.Management.Automation.RemoteRunspace
```

此命令显示在使用会话配置的会话上设置会话配置中的传输选项的效果。

## PARAMETERS

### -IdleTimeoutSec

确定当远程计算机没有从本地计算机接收任何通信时，每个会话保持打开状态的时间。
这包括检测信号信号。
当时间间隔已过时，该会话将关闭。

当用户打算断开连接并重新连接到会话时，空闲超时值非常重要。
仅当会话未超时时，用户才可以重新连接。

*IdleTimeoutSec* 参数对应于会话配置的 **IdleTimeoutMs** 属性。

输入一个值（以秒为单位）。
默认值为 7200（2 小时）。
最小值为 60（1 分钟）。
最大值为 WSMan 配置 () 中 Shell 对象的 **IdleTimeout** 属性的值 `WSMan:\\\<ComputerName\>\Shell\IdleTimeout` 。
默认值为 7200000 毫秒（2 小时）。

如果在会话选项和会话配置中设置空闲超时值，则在会话选项中设置的值优先，但它不能超过会话配置的 **MaxIdleTimeoutMs** 属性的值。
若要设置 **MaxIdleTimeoutMs** 属性的值，请使用 *MaxIdleTimeoutSec* 参数。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxConcurrentCommandsPerSession

将每个会话中可同时运行的命令数限制为指定的值。
默认值为 1000。

*MaxConcurrentCommandsPerSession* 参数对应于会话配置的 **MaxConcurrentCommandsPerShell** 属性。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxConcurrentUsers

将每个会话中可运行命令的用户数限制为指定的值。
默认值为 5。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxIdleTimeoutSec

将每个会话的空闲超时设置限制为指定的值。
默认值为 \[Int\]::MaxValue（大约 25 天）。

当用户打算断开连接并重新连接到会话时，空闲超时值非常重要。
仅当会话未超时时，用户才可以重新连接。

*MaxIdleTimeoutSec* 参数对应于会话配置的 **MaxIdleTimeoutMs** 属性。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxMemoryPerSessionMB

将每个会话使用的内存限制为指定的值。
输入一个值（以兆字节为单位）。
默认值为 1024 兆字节 (1 GB)。

*MaxMemoryPerSessionMB* 参数对应于会话配置的 **MaxMemoryPerShellMB** 属性。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxProcessesPerSession

将在每个会话中运行的进程数限制为指定的值。
默认值为 15。

*MaxProcessesPerSession* 参数对应于会话配置的 **MaxProcessesPerShell** 属性。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxSessions

限制使用会话配置的会话数。
默认值为 25。

*MaxSessions* 参数对应于会话配置的 **MaxShells** 属性。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxSessionsPerUser

将使用会话配置和使用给定用户的凭据运行的会话数限制为指定的值。
默认值为 25。

当你指定此值时，请考虑许多用户可能使用运行方式用户的凭据。

*MaxSessionsPerUser* 参数对应于会话配置的 **MaxShellsPerUser** 属性。

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OutputBufferingMode

当输出缓冲区时已满时，确定如何在断开连接的会话中管理命令输出。
此参数的可接受值为：

- 阻止。
当输出缓冲区已满时，将挂起执行，直到清除此缓冲区。
- 删除。
当输出缓冲区已满时，执行将继续。
由于已保存新的输出，因此将丢弃最早的输出。
- 无。
未指定任何输出缓冲模式。

会话的 **OutputBufferingMode** 属性的默认值为 Block。

```yaml
Type: System.Nullable`1[System.Management.Automation.Runspaces.OutputBufferingMode]
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProcessIdleTimeoutSec

将每个主机进程的超时值限制为指定的值。
默认值为0，表示进程没有超时值。

其他会话配置具有每个进程的超时值。
例如，对于每个进程的超时值为28800秒 (8 小时) **，则为。**

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### Microsoft.PowerShell.Commands.WSManConfigurationOption

## 注释

- 会话配置对象的属性会根据为会话配置设置的选项以及这些选项的值而有所不同。 此外，使用会话配置文件的会话配置还具有其他属性。

## 相关链接

[New-PSSession](New-PSSession.md)

[New-PSSessionOption](New-PSSessionOption.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)
