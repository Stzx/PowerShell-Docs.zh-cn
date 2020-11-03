---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198066"
---
# Remove-WmiObject

## 摘要
删除现有 Windows Management Instrumentation (WMI) 类的实例。

## SYNTAX

### class（默认值）

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### 对象 (object)

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### path

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### WQLQuery

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### query

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### list

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Get-wmiobject** cmdlet 删除现有 WINDOWS MANAGEMENT INSTRUMENTATION (WMI) 类的实例。

## 示例

### 示例1：关闭 Win32 进程的所有实例

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

此示例将关闭 Notepad.exe 的所有实例。

第一条命令启动记事本的实例。

第二个命令使用 Get-WmiObject cmdlet 来检索与 Notepad.exe 对应的 Win32_Process 的实例，然后将它们存储在 $np 变量中。

第三个命令将 $np 变量中的对象传递给 **get-wmiobject** ，后者将删除 Notepad.exe 的所有实例。

### 示例2：删除文件夹

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

此命令删除 C:\Test 文件夹。

第一个命令使用 **get-wmiobject** 查询 C:\Test 文件夹，然后将该对象存储在 $a 变量中。

第二个命令通过管道将 $a 变量传递给 **get-wmiobject** ，后者将删除该文件夹。

## PARAMETERS

### -AsJob
指示此 cmdlet 作为后台作业运行。
使用此参数可运行需要较长时间才能完成的命令。

Windows PowerShell 3.0 中引入的新 CIM cmdlet 执行与 WMI cmdlet 相同的任务。
CIM cmdlet 符合 WS-Management (WSMan) 标准和通用信息模型 (CIM) 标准，这使 cmdlet 能够使用相同的技术来管理运行 Windows 操作系统的计算机和运行其他操作系统的计算机。
建议不要使用 **Remove-WmiObject** ，而考虑使用 Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 cmdlet。

使用 *AsJob* 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。
当作业完成时，你可以继续在此会话中工作。
如果将 **Remove-WmiObject** 用于远程计算机，则会在本地计算机上创建相应作业，并且来自远程计算机的结果将自动返回至本地计算机。
若要 **管理作业，** 请使用包含 **job 名词)  (的 cmdlet** 。
若要获取作业结果，请使用 Receive-Job cmdlet。

若要将此参数用于远程计算机，必须为本地和远程计算机配置远程处理。
使用 "以管理员身份运行" 选项启动 Windows PowerShell。
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
指定用于 WMI 连接的身份验证级别。
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
指定此 cmdlet 删除的 WMI 类的名称。

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
键入用户名时，此 cmdlet 会提示输入密码。

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
使用此参数时，将忽略所有其他参数。

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
按首选顺序将 *Locale* 参数指定为 MS_ 格式的数组 \<LCID\> 。

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
指定 WMI 类的 WMI 对象路径，或指定要删除的 WMI 类实例的 WMI 对象路径。

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

### System.Management.ManagementObject
可以通过管道将管理对象传递给此 cmdlet。

## 输出

### System.management.automation.remotingjob （无）
如果指定 *AsJob* 参数，则此 cmdlet 将返回一个作业对象。
否则，将不生成任何输出。

## 注释

## 相关链接

[Get-WmiObject](Get-WmiObject.md)

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Set-WmiInstance](Set-WmiInstance.md)
