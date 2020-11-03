---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198034"
---
# Set-Service

## 摘要
启动、停止和挂起服务并更改服务的属性。

## SYNTAX

### Name（默认值）

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-Service`Cmdlet 更改服务的属性，如 **状态** 、 **说明** 、 **DisplayName** 和 **StartupType** 。 `Set-Service` 可以启动、停止、挂起或暂停服务。 若要标识服务，请输入其服务名称或提交服务对象。 或者，将服务名称或服务对象向下发送到 `Set-Service` 。

## 示例

### 示例1：更改显示名称

在此示例中，将更改服务的显示名称。 若要查看原始显示名称，请使用 `Get-Service` 。

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

`Set-Service` 使用 **name** 参数来指定服务的名称， **LanmanWorkstation** 。 **DisplayName** 参数指定新的显示名称 " **LanMan Workstation** "。

### 示例2：更改服务的启动类型

此示例演示如何更改服务的启动类型。

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

`Set-Service` 使用 **name** 参数来指定服务的名称， **位** 。 **StartupType** 参数将服务设置为 **自动** 。

`Get-Service` 使用 **Name** 参数指定 **BITS** 服务，并沿管道向下发送对象。 `Select-Object` 使用 **属性** 参数显示 **BITS** 服务的状态。

### 示例3：更改服务的描述

此示例更改 BITS 服务的说明并显示结果。

`Get-CimInstance`使用 cmdlet 的原因是它将返回一个包含服务 **说明** 的 **Win32_Service** 对象。

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

`Get-CimInstance` 将对象向下发送到管道， `Format-List` 并显示服务的名称和说明。 出于比较目的，将在更新说明之前和之后运行该命令。

`Set-Service` 使用 **Name** 参数指定 **BITS** 服务。 **Description** 参数指定服务说明的更新文本。

### 示例4：启动服务

在此示例中，启动了服务。

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

`Set-Service` 使用 **Name** 参数来指定服务 **WinRM** 。 **Status** 参数使用 **运行** 的值来启动服务。 **PassThru** 参数输出显示结果的 **ServiceController** 对象。

### 示例5：挂起服务

此示例使用管道暂停到服务。

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

`Get-Service` 使用 **Name** 参数指定 **计划** 服务，并沿管道向下发送对象。 `Set-Service` 使用 **Status** 参数将服务设置为 "已 **暂停** "。

### 示例6：停止服务

此示例使用变量来停止服务。

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

`Get-Service` 使用 **Name** 参数来指定服务的 **计划** 。 对象存储在变量中 `$S` 。 `Set-Service` 使用 **InputObject** 参数，并指定存储的对象 `$S` 。 **Status** 参数将服务设置为 " **已停止** "。

## PARAMETERS

### -ComputerName

指定一台或多台计算机。 对于远程计算机，请键入 NetBIOS 名称、IP 地址或完全限定的域名。 如果未指定 **ComputerName** 参数，此命令将在本地计算机上运行。

此参数不依赖于 PowerShell 远程处理。 即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm

在运行之前提示你进行确认 `Set-Service` 。

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

### -Description

指定服务的新说明。

服务说明出现在 **"计算机管理，服务** " 中。 **说明** 不是 `Get-Service` **ServiceController** 对象的属性。 若要查看服务说明，请使用 `Get-CimInstance` ，它将返回表示服务的 **Win32_Service** 对象。

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

### -DisplayName

指定服务的新显示名称。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

指定表示要更改的服务的 **ServiceController** 对象。 输入包含该对象的变量，或键入获取该对象的命令或表达式（如 `Get-Service` 命令）。 您可以使用管道将服务对象发送到 `Set-Service` 。

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name

指定要更改的服务的服务名称。 不允许使用通配符。 您可以使用管道将服务名称发送到 `Set-Service` 。

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PassThru

返回表示已更改的服务的 **ServiceController** 对象。 默认情况下， `Set-Service` 不会生成任何输出。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupType

设置服务的启动类型。 此参数的可接受值为：

- **自动** -服务已启动或由操作系统在系统启动时启动。
  如果一个自动启动的服务依赖于手动启动的服务，则该手动启动的服务也会在系统启动时自动启动。
- **已禁用** -服务已禁用，无法由用户或应用程序启动。
- **手动** -服务仅通过用户、使用服务控制管理器或应用程序手动启动。
- **启动** -表示服务是由系统加载程序启动的设备驱动程序。 此值仅对设备驱动程序有效。
- **系统** -指示服务是由 "IOInitSystem ( # A1" 函数启动的设备驱动程序。 此值仅对设备驱动程序有效。

 默认值为 " **自动** "。

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

指定服务的状态。

此参数可接受的值如下所示：

- 已 **暂停** 。 挂起服务。
- **正在运行** 。 启动服务。
- **已停止** 。 停止服务。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

显示运行时将发生 `Set-Service` 的情况。 cmdlet 未运行。

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

### System.ServiceProcess.ServiceController、System.String

您可以使用管道将服务对象或包含服务名称的字符串发送到 `Set-Service` 。

## 输出

### System.ServiceProcess.ServiceController

默认情况下， `Set-Service` 不返回任何对象。 使用 **PassThru** 参数输出 **ServiceController** 对象。

## 注释

`Set-Service` 需要提升的权限。 使用 "以 **管理员身份运行** " 选项。

`Set-Service` 仅当当前用户有权管理服务时，才能控制服务。 如果某个命令不能正常工作，则可能没有所需的权限。

若要查找服务的服务名称或显示名称，请使用 `Get-Service` 。 服务名称在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。

## 相关链接

[Get-Service](Get-Service.md)

[New-Service](New-Service.md)

[Restart-Service](Restart-Service.md)

[Resume-Service](Resume-Service.md)

[Start-Service](Start-Service.md)

[Stop-Service](Stop-Service.md)

[Suspend-Service](Suspend-Service.md)
