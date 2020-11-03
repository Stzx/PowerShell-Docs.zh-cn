---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198281"
---
# Get-Service

## 摘要
获取本地或远程计算机上的服务。

## SYNTAX

### Default（默认值）

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### DisplayName

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### InputObject

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## DESCRIPTION

**Get-help** cmdlet 获取表示本地计算机或远程计算机上的服务（包括正在运行和已停止的服务）的对象。

可以通过指定服务的服务名称或显示名称来指示此 cmdlet 仅获取特定服务，也可以通过管道将服务对象传递给此 cmdlet。

## 示例

### 示例1：获取计算机上的所有服务

```powershell
Get-Service
```

此命令获取计算机上的所有服务。
它的行为如同你键入 `Get-Service *` 的一样。
默认显示将显示每个服务的状态、服务名称和显示名称。

### 示例2：获取以搜索字符串开头的服务

```powershell
Get-Service "wmi*"
```

此命令检索服务名称以 WMI 开头 (Windows Management Instrumentation) 首字母缩写的服务。

### 示例3：显示包含搜索字符串的服务

```powershell
Get-Service -Displayname "*network*"
```

此命令显示显示名称包括 "网络" 的服务。
搜索显示名称可以在服务名称不包含“Net”的情况下查找与网络相关的服务，例如 xmlprov（网络提供服务）。

### 示例4：获取以搜索字符串开头的服务和排除项

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

这些命令只获取服务名称以 "win" 开头的服务（WinRM 服务除外）。

### 示例5：显示当前处于活动状态的服务

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

此命令仅显示当前处于活动状态的服务。
它使用 **get-help** cmdlet 获取计算机上的所有服务。
管道运算符 (|) 将结果传递给 Where-Object cmdlet，该 cmdlet 只选择状态属性等于 "正在运行" 的服务。

Status 是服务对象的唯一属性。
若要查看所有属性，请键入 `Get-Service | Get-Member` 。

### 示例6：获取远程计算机上的服务

```powershell
Get-Service -ComputerName "Server02"
```

此命令获取 Server02 远程计算机上的服务。

因为 **get-help** 的 *ComputerName* 参数不使用 windows powershell 远程处理，所以即使未将计算机配置为在 Windows powershell 中进行远程处理，也可以使用此参数。

### 示例7：列出本地计算机上具有依赖服务的服务

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

第一个命令使用 **get-help** cmdlet 来获取计算机上的服务。
管道运算符 (|) 将服务发送到 **对象** cmdlet，后者将选择其 **DependentServices** 属性不为 null 的服务。

另一个管道运算符将结果发送给 Format-List cmdlet。
该命令使用其 *Property* 参数来显示服务名称、依赖服务的名称以及显示每个服务具有的依赖服务数目的计算属性。

### 示例8：按属性值排序服务

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

此命令显示当你按其 **Status** 属性值以升序对服务进行排序时，已停止的服务将出现在运行服务之前。
出现这种情况的原因是，Status 的值是一个枚举，其中，已停止的值为1，并且运行的值为4。

若要首先列出正在运行的服务，请使用 Sort-Object cmdlet 的 *降序* 参数。

### 示例9：获取多台计算机上的服务

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

此命令使用 **get-help** cmdlet 在两台远程计算机和本地计算机 ( "localhost" ) 上运行 Get-Service Winrm 命令。

此命令在远程计算机上运行，并将结果返回到本地计算机。
管道运算符 (|) 将结果发送到 **格式表** cmdlet，该 cmdlet 将服务格式设置为表。
**Format-Table** 命令使用 *Property* 参数来指定表中显示的属性，包括 **MachineName** 属性。

### 示例10：获取服务的依赖服务

```powershell
Get-Service "WinRM" -RequiredServices
```

此命令获取 WinRM 服务所需的服务。

命令返回服务的 **ServicesDependedOn** 属性的值。

### 示例11：通过管道运算符获取服务

```powershell
"WinRM" | Get-Service
```

此命令获取本地计算机上的 WinRM 服务。
此示例显示你可以通过管道将服务名称字符串（ (用引号引起来) 发送到 **服务）** 。

## PARAMETERS

### -ComputerName

获取指定计算机上运行的服务。
默认为本地计算机。

键入远程计算机的 FQDN)  (的 NetBIOS 名称、IP 地址或完全限定的域名。
若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。

此参数不依赖于 Windows PowerShell 远程处理。
即使你的计算机未配置为运行远程命令，你也可以使用 **get-help** 的 *ComputerName* 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DependentServices

指示此 cmdlet 仅获取依赖于指定服务的服务。

默认情况下，此 cmdlet 将获取所有服务。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName

指定作为字符串数组，要检索的服务的显示名称。
允许使用通配符。
默认情况下，此 cmdlet 将获取计算机上的所有服务。

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Exclude

指定为字符串数组、此 cmdlet 从操作中排除的一个或一组服务。
此参数值使 *Name* 参数有效。
请输入名称元素或模式，例如“s*”。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Include

指定为字符串数组、此 cmdlet 包含在操作中的一个或一项服务。
此参数值使 *Name* 参数有效。
请输入名称元素或模式，例如“s*”。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -InputObject

指定表示要检索的服务的 **ServiceController** 对象。
输入一个包含对象的变量，或键入可获取对象的命令或表达式。
还可以通过管道将服务对象传递给此 cmdlet。

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

指定要检索的服务的名称。
允许使用通配符。
默认情况下，此 cmdlet 将获取计算机上的所有服务。

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -RequiredServices

指示此 cmdlet 仅获取此服务所需的服务。

此参数获取服务的 **ServicesDependedOn** 属性的值。
默认情况下，此 cmdlet 将获取所有服务。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.ServiceProcess.ServiceController、System.String

可以通过管道将服务对象或服务名称传递给此 cmdlet。

## 输出

### System.ServiceProcess.ServiceController

此 cmdlet 将返回表示计算机上的服务的对象。

## 注释

还可以通过其内置别名 "gsv" 来对 **其进行引用** 。 有关详细信息，请参阅 about_Aliases。

此 cmdlet 只能在当前用户有权查看服务时显示服务。
如果此 cmdlet 未显示服务，则你可能没有查看它们的权限。

若要在系统中查找每个服务的服务名称和显示名称，请键入 `Get-Service` 。
服务名称显示在 Name 列中，显示名称显示在 DisplayName 列中。

当按状态值以升序排序时，“Stopped”服务将出现在“Running”服务之前。
服务的 Status 属性是一个枚举值，其中状态的名称表示整数值。
该排序是基于整数值进行的，而非名称。
“Running”出现在“Stopped”之前的原因在于“Stopped”的值为“1”，而“Running”的值为“4”。

## 相关链接

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Set-Service](Set-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
