---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "93198928"
---
# Invoke-WmiMethod

## 摘要
调用 WMI 方法。

## SYNTAX

### class（默认值）

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 对象 (object)

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### path

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### query

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### list

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-WmiMethod`Cmdlet 将调用 Windows Management Instrumentation 的方法 (WMI) 对象。

Windows PowerShell 3.0 中引入的新通用信息模型 (CIM) cmdlet 执行与 WMI cmdlet 相同的任务。 CIM cmdlet 符合 WS-Management (WSMan) 标准以及 CIM 标准，这使 cmdlet 能够使用相同的技术来管理 Windows 计算机和运行其他操作系统的计算机。 请不要使用 `Invoke-WmiMethod` ，而应考虑使用 [invoke-cimmethod](../cimcmdlets/invoke-cimmethod.md)。

## 示例

### 示例1：列出 WMI 对象的所需顺序

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

此命令按所需的顺序列出对象。 若要在 PowerShell 3.0 中调用 WMI，则与备用方法不同，并要求对象值以特定的顺序输入。

### 示例2：启动应用程序的实例

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

此命令通过调用 Win32_Process 类的方法来启动记事本的实例 `Create` 。 **Win32_Process**

使用0填充 **ReturnValue** 属性，并使用一个 (整数填充 **ProcessId** 属性，如果该命令已完成，则) 下一个进程 ID 号。

### 示例3：重命名文件

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

此命令重命名文件。 它使用 **Path** 参数来引用 **CIM_DataFile** 类的实例。 然后，它将 Rename 方法应用于该特定实例。

如果命令完成，则使用0填充 **ReturnValue** 属性。

### 示例4：使用传递值数组 `-ArgumentList`

使用后跟值的对象数组的示例 `$binSD` `$null` 。

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## PARAMETERS

### -ArgumentList

指定要传递给被调用方法的参数。 此参数的值必须是对象的数组，并且必须以所调用方法所需的顺序出现。 `Invoke-CimCommand`Cmdlet 没有这些限制。

若要确定这些对象的列出顺序，请运行 `GetMethodParameters()` WMI 类上的方法，如本主题末尾附近的示例1中所示。

> [!IMPORTANT]
> 如果第一个值为包含多个元素的数组，则要求第二个值为 $null。 否则，该命令将生成一个错误，例如“Unable to cast object of type 'System.Byte' to type 'System.Array'.”。 请参阅上面的示例4。

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob

指示此 cmdlet 将命令作为后台作业运行。 使用此参数可运行需要较长时间才能完成的命令。

使用 **AsJob** 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。 当作业完成时，你可以继续在此会话中工作。 如果 `Invoke-WmiMethod` 对远程计算机使用，则在本地计算机上创建作业，远程计算机的结果将自动返回到本地计算机。 若要管理作业，请使用包含 Job 名词的 cmdlet (Job cmdlet)。 若要获取作业结果，请使用 Receive-Job cmdlet。

若要将此参数用于远程计算机，必须为本地和远程计算机配置远程处理。 此外，您必须使用 Windows Vista 和更高版本的 Windows 中的 "以管理员身份运行" 选项启动 Windows PowerShell。 有关详细信息，请参阅 about_Remote_Requirements。

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

指定用于 WMI 连接的身份验证级别。 此参数的可接受值为：

- -1：Unchanged
- 0：Default
- 1：None（不执行身份验证。）
- 2：Connect（仅当客户端与应用程序建立了关系时才执行身份验证。）
- 3：Call（应用程序收到请求时只在每次调用的开始执行身份验证。）
- 4：Packet（对从客户端收到的所有数据执行身份验证。）
- 5： PacketIntegrity (在客户端和应用程序之间传输的所有数据都经过身份验证和验证。 ) 
- 6：PacketPrivacy（使用其他身份验证等级的属性，并且所有数据都加密。）

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

指定用于对 WMI 连接进行身份验证的授权机构。 可以指定标准的 Windows NT LAN 管理器 (NTLM) 或 Kerberos 身份验证。 若要使用 NTLM，请将授权机构设置设为“ntlmdomain:\<DomainName\>”，其中 \<DomainName\> 标识有效的 NTLM 域名。 若要使用 Kerberos，请指定 kerberos:\<DomainName\ServerName\>。 连接到本地计算机时不能包含授权机构设置。

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

指定包含要调用的静态方法的 WMI 类。

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

以字符串数组的形式指定此 cmdlet 在其上运行命令的计算机。 默认为本地计算机。

键入一台或多台计算机的 NetBIOS 名称、IP 地址或完全限定的域名。 若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。

此参数不依赖于 Windows PowerShell 远程处理。 即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。

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

指定有权执行此操作的用户帐户。 默认为当前用户。 键入用户名，如 `User01` 、 `Domain01\User01` 或 `User@Contoso.com` 。 或者输入 **PSCredential** 对象，例如 Get-Credential cmdlet 返回的对象。 键入用户名时，将会提示你输入密码。

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

指示在命令进行 WMI 调用之前，此 cmdlet 将启用当前用户的所有权限。

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

指定要使用的模拟级别。 此参数的可接受值为：

- 0：Default（读取本地注册表的默认模拟级别，通常设置为“3：模拟”。）
- 1：Anonymous（隐藏调用方的凭据。）
- 2：Identify（允许对象查询调用方的凭据。）
- 3：Impersonate（允许对象使用调用方的凭据。）
- 4：Delegate（允许对象允许其他对象使用调用方的凭据。）

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

指定要用作输入的 **system.management.managementobject** 对象。 使用此参数时，将忽略除 **Flag** 和 **Argument** 参数之外的所有其他参数。

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

指定 WMI 对象的首选区域设置。 按首选顺序将 **Locale** 参数的值指定为格式的数组 `MS_<LCID>` 。

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

### -Name

指定要调用的方法的名称。 此参数是必需的，不能为 null 或为空。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

与 **Class** 参数一起使用时，此参数将指定引用的 wmi 类或对象所在的 wmi 存储库命名空间。

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

指定 WMI 类的 WMI 对象路径，或指定 WMI 类实例的 WMI 对象路径。 指定的类或实例必须包含 **Name** 参数中指定的方法。

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

### -ThrottleLimit

指定可同时执行的 WMI 操作数的限制值。
此参数与 **AsJob** 参数一起使用。 节流限制仅适用于当前命令，而不适用于会话或计算机。

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

### 无

此 cmdlet 不接受任何输入。

## 输出

### 无

此 cmdlet 将不生成任何输出。

## 注释

## 相关链接

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[Get-WmiObject](Get-WmiObject.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)
