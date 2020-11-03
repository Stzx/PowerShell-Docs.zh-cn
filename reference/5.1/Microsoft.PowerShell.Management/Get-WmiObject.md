---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198278"
---
# Get-WmiObject

## 摘要
获取 Windows Management Instrumentation (WMI) 类的实例或可用类的相关信息。

## SYNTAX

### query（默认值）

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### list

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### WQLQuery

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### class

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### path

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## DESCRIPTION

从 PowerShell 3.0 开始，此 cmdlet 已被取代 `Get-CimInstance` 。

`Get-WmiObject`Cmdlet 可获取 wmi 类的实例或有关可用 wmi 类的信息。 若要指定远程计算机，请使用 **ComputerName** 参数。 如果指定了 **List** 参数，则 cmdlet 将获取有关指定的命名空间中可用的 WMI 类的信息。 如果指定了 **Query** 参数，则 cmdlet 将运行 WMI 查询语言 (WQL) 语句。

`Get-WmiObject`Cmdlet 不使用 Windows PowerShell 远程处理来执行远程操作。
**ComputerName** `Get-WmiObject` 即使你的计算机不符合 windows powershell 远程处理的要求，或者没有为 windows powershell 中的远程处理配置，你也可以使用该 cmdlet 的 ComputerName 参数。

从 Windows PowerShell 3.0 开始，返回的对象的 **__Server** 属性 `Get-WmiObject` 具有 **PSComputerName** 的别名。 从而可以更轻松地在输出和报告中包含源计算机名称。

## 示例

### 示例1：获取本地计算机上的进程

此示例将获取本地计算机上的进程。

```powershell
Get-WmiObject -Class Win32_Process
```

### 示例2：获取远程计算机上的服务

此示例获取远程计算机上的服务。 **ComputerName** 参数指定远程计算机的 IP 地址。 默认情况下，当前用户帐户必须是远程计算机上 **Administrators** 组的成员。

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### 示例3：获取本地计算机的根或默认命名空间中的 WMI 类

此示例将获取本地计算机的根或默认命名空间中的 WMI 类。

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### 示例4：在多台计算机上获取命名服务

此示例获取 **ComputerName** 参数值指定的计算机上的 WinRM 服务。

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

管道运算符 (|) 将输出发送给 `Format-List` cmdlet，这会将 **PSComputerName** 属性添加到默认的输出。 **PSComputerName** 是返回的对象的 **__Server** 属性的别名 `Get-WmiObject` 。 此别名是在 PowerShell 3.0 中引入的。

### 示例5：停止远程计算机上的服务

此示例将停止远程计算机上的 WinRM 服务。 `Get-WmiObject` 获取 Server01 上的 WinRM 服务对象的实例。 然后，它调用该对象上 **Win32_Service** WMI 类的 **StopService** 方法。

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

这等效于使用 `Stop-Service` cmdlet。

### 示例6：获取本地计算机上的 BIOS

此示例从本地计算机中获取 BIOS 信息。 Cmdlet 的 **Property** 参数 `Format-List` 用于显示列表中返回的对象的所有属性。 默认情况下，仅显示在配置文件中定义的属性的子集 `Types.ps1xml` 。

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### 示例7：获取远程计算机上的服务

此示例使用 cmdlet 的 **Credential** 参数 `Get-WmiObject` 获取远程计算机上的服务。 **Credential** 参数的值为用户帐户名称。 将提示用户输入密码。

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> 在以本地计算机为目标时不能使用凭据。

## PARAMETERS

### -Amended

获取或设置一个值，该值指示从 WMI 返回的对象是否应包含修正信息。 通常，修正信息是附加到 WMI 对象的可本地化信息，如对象和属性说明。

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

### -AsJob

将命令作为后台作业运行。 使用此参数可运行需要较长时间才能完成的命令。

使用 **AsJob** 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。 当作业完成时，你可以继续在此会话中工作。 如果 `Get-WmiObject` 在远程计算机上使用，则在本地计算机上创建作业，远程计算机的结果将自动返回到本地计算机。 若要管理作业，请使用包含 Job cmdlet 的 cmdlet。 若要获取作业结果，请使用 `Receive-Job` cmdlet。

> [!NOTE]
> 若要将此参数用于远程计算机，必须为本地和远程计算机配置远程处理。 此外，在 Windows Vista 和更高版本的 Windows 中，必须使用“以管理员身份运行”选项启动 Windows PowerShell。 有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md)。

有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md)。

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
有效值是：

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
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authority

指定用于对 WMI 连接进行身份验证的授权机构。 可以指定标准 NTLM 或 Kerberos 身份验证。 若要使用 NTLM，请将权限设置设置为 `ntlmdomain:<DomainName>` ，其中 `<DomainName>` 标识有效的 NTLM 域名。 若要使用 Kerberos，请指定 `kerberos:<DomainName>\<ServerName>` 。 连接到本地计算机时不能包含授权机构设置。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Class

指定 WMI 类的名称。 如果使用此参数，则 cmdlet 将检索 WMI 类的实例。

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName

指定用于管理操作的目标计算机。 输入完全限定的域名 (FQDN) 、NetBIOS 名称或 IP 地址。 当远程计算机与本地计算机处于不同的域中时，必须使用完全限定的域名。

默认为本地计算机。 若要指定本地计算机，例如在计算机名称的列表中，请使用“localhost”、本地计算机名称或句点 (.)。

此参数不依赖于 Windows PowerShell 远程处理，该远程处理使用 WS-Management。 **ComputerName** `Get-WmiObject` 即使你的计算机未配置为运行 WS-Management 远程命令，你也可以使用 ComputerName 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

指定有权执行此操作的用户帐户。 默认为当前用户。 键入用户名，如 "User01"、"Domain01\User01" 或 User@Contoso.com 。 或者输入 **PSCredential** 对象，例如 `Get-Credential` cmdlet 返回的对象。 如果键入用户名，则将提示你输入密码。 在以本地计算机为目标时不能使用凭据。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DirectRead

指定无论其基类或派生类如何，是否都要求指定类直接访问 WMI 提供程序。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableAllPrivileges

在命令进行 WMI 调用之前，启用当前用户的所有权限。

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

### -Filter

指定要用作筛选器的 **Where** 子句。 使用 WMI 查询语言 (WQL) 的语法。

> [!IMPORTANT]
> 请不要在参数的值中包含 **Where** 关键字。 例如，以下命令不使用 **Where** 关键字，仅返回 **DeviceID** 为“c:”的逻辑磁盘和名称为 “WinRM”的服务。

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
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

- 0：Default。 读取默认模拟级别的本地注册表。 通常将默认设置为 " **模拟** "。
- 1：Anonymous。 隐藏调用方的凭据。
- 2：Identify。 允许对象查询调用方的凭据。
- 3：Impersonate。 允许对象使用调用方的凭据。
- 4：Delegate。 允许对象允许其他对象使用调用方的凭据。

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -List

获取由 **Namespace** 参数指定的 WMI 存储库命名空间中的 WMI 类的名称。

如果指定 **列表** 参数，而不是 **命名空间** 参数，则 `Get-WmiObject` 默认情况下使用 **Root\Cimv2** 命名空间。 此 cmdlet 不使用注册表项中的 **默认命名空间** 注册表项 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` 来确定默认命名空间。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Locale

指定 WMI 对象的首选区域设置。
按 MS_\<LCID\> 格式输入一个值。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Namespace

当 **Namespace** 参数与 **Class** 参数一起使用时，它将指定指定的 WMI 类所在的 WMI 存储库命名空间。 当此参数与 **List** 参数一起使用时，它将指定所收集 WMI 类信息的来源命名空间。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Property

指定此 cmdlet 从中获取信息的 WMI 类属性。 输入属性名称。

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Query

运行指定的 WMI 查询语言 (WQL) 语句。 此参数不支持事件查询。

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Recurse

在当前命名空间和所有其他命名空间中搜索 **Class** 参数指定的类名。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

指定可同时执行的最大 WMI 操作数。 仅当命令中使用了 **AsJob** 参数时，此参数才有效。

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

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

不能通过管道将输入传递给 `Get-WmiObject` 。

## 输出

### PSObject 或 System.Management.Automation.RemotingJob

如果使用的是 **AsJob** 参数，则该 cmdlet 返回作业对象。 否则，返回的对象 `Get-WmiObject` 取决于 **Class** 参数的值。

## 注释

若要访问远程计算机上的 WMI 的信息，则 cmdlet 必须在远程计算机上的本地管理员组的成员帐户下运行。 或者，可以更改远程存储库的 WMI 命名空间上的默认访问控制，以授予其他帐户访问权限。

默认情况下，只显示每个 WMI 类的部分属性。 在 Types.ps1xml 配置文件中指定将为每个 WMI 类显示的属性组。 若要获取 WMI 对象的所有属性，请使用 `Get-Member` 或 `Format-List` cmdlet。

## 相关链接

[Invoke-WmiMethod](Invoke-WmiMethod.md)

[Remove-WmiObject](Remove-WmiObject.md)

[Set-WmiInstance](Set-WmiInstance.md)

[Get-WSManInstance](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[Invoke-WSManAction](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[New-WSManInstance](../Microsoft.WsMan.Management/New-WSManInstance.md)

[Remove-WSManInstance](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
