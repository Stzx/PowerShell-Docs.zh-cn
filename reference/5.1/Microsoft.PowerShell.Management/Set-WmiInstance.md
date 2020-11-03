---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198033"
---
# Set-WmiInstance

## 摘要
创建或更新现有 Windows Management Instrumentation (WMI) 类的实例。

## SYNTAX

### class（默认值）

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 对象 (object)

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### query

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
`Set-WmiInstance`Cmdlet 可创建或更新现有 Windows Management Instrumentation (WMI) 类的实例。
创建或更新的实例将写入 WMI 存储库。

Windows PowerShell 3.0 中引入的新 CIM cmdlet 执行与 WMI cmdlet 相同的任务。
CIM cmdlet 符合 WS-Management (WSMan) 标准和通用信息模型 (CIM) 标准。
这使 cmdlet 可以使用相同的技术来管理基于 Windows 的计算机和运行其他操作系统的计算机。
请 `Set-WmiInstance` 考虑使用 [CimInstance](/powershell/module/cimcmdlets/set-ciminstance) 或 [CimInstance](/powershell/module/cimcmdlets/new-ciminstance) cmdlet，而不是使用。

## 示例

### 示例1：设置 WMI 日志记录级别

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

此命令将 WMI 日志记录级别设置为 2。
命令传递要设置的属性，并将值（在参数参数中被视为值对）传递。
此参数接受由 @{property = value} 结构定义的哈希表。
返回的类信息将反映出新值。

### 示例2：创建环境变量及其值

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

此命令创建 testvar 环境变量，该变量的值为 testvalue。
它通过创建 **Win32_Environment** WMI 类的新实例来实现此功能。
此操作需要适当的凭据，并且你可能需要重新启动 Windows PowerShell 才能查看新的环境变量。

### 示例3：为多台远程计算机设置 WMI 日志记录级别

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

此命令将 WMI 日志记录级别设置为 2。
命令传递要设置的属性，并将值（在参数参数中被视为值对）传递。
此参数接受由 @{property = value} 结构定义的哈希表。
返回的类信息将反映出新值。

## PARAMETERS

### -Arguments
指定要更改的属性的名称，以及该属性的新值。
名称和值必须是名称/值对。
名称-值对作为哈希表传递到命令行。
例如：

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
指示此 cmdket 作为后台作业运行。
使用此参数可运行需要较长时间才能完成的命令。

指定 *AsJob* 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。
当作业完成时，你可以继续在此会话中工作。
如果 **将 set-wmiinstance** 用于远程计算机，则会在本地计算机上创建作业，远程计算机的结果将自动返回到本地计算机。
若要 **管理作业，** 请使用包含 **job 名词)  (的 cmdlet** 。
若要获取作业结果，请使用 Receive-Job cmdlet。

若要将此参数与远程计算机一起使用，必须为本地和远程计算机配置远程处理。
此外，您必须使用 Windows Vista 和更高版本的 Windows 操作系统中的 "以管理员身份运行" 选项启动 Windows PowerShell。
有关详细信息，请参阅 about_Remote_Requirements。

有关 Windows PowerShell 后台作业的详细信息，请参阅 about_Jobs 和 about_Remote_Jobs。

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

### -Authentication
指定必须用于 WMI 连接的身份验证级别。
此参数的可接受值为：

- -1：保持不变。
- 0：Default。
- 1：无。
未执行任何身份验证。
- 2：连接。
仅当客户端与应用程序建立了关系时才执行身份验证。
- 3：调用。
仅当应用程序接收到请求时，才会在每次调用开始时执行身份验证。
- 4：数据包。
对从客户端收到的所有数据执行身份验证。
- 5： PacketIntegrity。
在客户端和应用程序之间传输的所有数据都经过身份验证和验证。
- 6： PacketPrivacy。
使用其他身份验证级别的属性，并对所有数据进行加密。

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authority
指定用于对 WMI 连接进行身份验证的授权机构。
可以指定标准 NTLM 或 Kerberos 身份验证。
若要使用 NTLM，请将授权机构设置设为“ntlmdomain:\<DomainName\>”，其中 \<DomainName\> 标识有效的 NTLM 域名。
若要使用 Kerberos，请指定 kerberos： \<DomainName\> \\ \<ServerName\> 。
连接到本地计算机时不能包含授权机构设置。

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Class
指定 WMI 类的名称。

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
指定在其上运行此 cmdlet 的计算机的名称。
默认为本地计算机。

键入一台或多台计算机的 NetBIOS 名称、IP 地址或完全限定的域名。
若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。

此参数不依赖于 Windows PowerShell 远程处理。
即使你的计算机未配置为运行远程命令，你也可以使用 *ComputerName* 参数。

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
指定有权执行此操作的用户帐户。
默认为当前用户。

键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如 Get-Credential cmdlet 生成的一个 **PSCredential** 对象。
如果键入用户名，则此 cmdlet 会提示输入密码。

随 Windows PowerShell 一起安装的任何提供程序都不支持使用参数安装的任何提供程序支持此参数。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAllPrivileges
指示此 cmdlet 在执行 WMI 调用的命令之前启用当前用户的所有权限。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Impersonation
指定要使用的模拟级别。
此参数的可接受值为：

- 0：Default。
读取默认模拟级别的本地注册表，通常设置为 "3：模拟"。
- 1：Anonymous。
隐藏调用方的凭据。
- 2：Identify。
允许对象查询调用方的凭据。
- 3：Impersonate。
允许对象使用调用方的凭据。
- 4：Delegate。
允许对象允许其他对象使用调用方的凭据。

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
指定要用作输入的 **system.management.managementobject** 对象。
使用此参数时，将忽略除 *Arguments* 参数之外的所有其他参数。

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Locale
指定 WMI 对象的首选区域设置。
*区域设置* 参数在数组中按首选顺序由 MS_ \<LCID\> 格式指定。

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace
指定在与 *class* 参数一起使用时所引用的 wmi 类所在的 wmi 存储库命名空间。

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
指定要创建或更新的实例的 WMI 对象路径。

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PutType
指示是否创建或更新 WMI 实例。
此参数的可接受值为：

- UpdateOnly.
更新现有的 WMI 实例。
- CreateOnly.
创建新的 WMI 实例。
- UpdateOrCreate.
如果 WMI 实例存在，则更新该实例；如果实例不存在，则创建一个新实例。

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
指定为运行此命令可建立的并发连接的最大数目。
此参数与 *AsJob* 参数一起使用。
节流限制仅适用于当前命令，而不适用于会话或计算机。

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

### 无
此 cmdlet 不接受输入。

## 输出

### 无
此 cmdlet 将不产生输出。

## 注释

## 相关链接

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)
