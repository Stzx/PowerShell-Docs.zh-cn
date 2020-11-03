---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198252"
---
# Start-DscConfiguration

## 摘要
将配置应用到节点。

## SYNTAX

### ComputerNameAndPathSet (默认值) 

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CimSessionAndPathSet

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ComputerNameAndUseExistingSet

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSessionAndUseExistingSet

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Start-DscConfiguration** cmdlet 将配置应用到节点。
与 *UseExisting* 参数一起使用时，将应用目标计算机上的现有配置。
通过指定计算机名称或通过使用通用信息模型 (CIM) 会话来指定要将配置应用到的计算机。

默认情况下，此 cmdlet 会创建一个作业，并返回 **Job** 对象。
有关后台作业的详细信息，请键入 `Get-Help about_Jobs` 。
若要以交互方式使用此 cmdlet，请指定 *Wait* 参数。

指定 *Verbose* 参数，以查看该 cmdlet 在应用配置设置时所执行的操作的详细信息。

## 示例

### 示例1：应用配置设置

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

此命令将 C:\DSC\Configurations\ 中的配置设置应用到在该文件夹中具有设置的每台计算机。
对于部署到的每个目标节点，该命令将返回 **Job** 对象。

### 示例2：应用配置设置并等待配置完成

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

此命令将 C:\DSC\Configurations\ 中的配置应用到本地计算机。
对于部署到的每个目标节点（在此示例中，仅为本地计算机），该命令将返回 **Job** 对象。
此示例指定 *详细* 参数。
因此，该命令会在控制台继续时向控制台发送消息。
该命令包括 *Wait* 参数。
因此，只有在命令完成所有配置任务后，才能使用控制台。

### 示例3：使用 CIM 会话应用配置设置

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

此示例将配置设置应用到指定的计算机。
该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。
或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。

第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。
该命令会提示你输入密码。
要了解详情，请键入 `Get-Help NewCimSession`。

第二个命令将 C:\DSC\Configurations\ 中的配置设置应用于存储在 $Session 变量中的 **CimSession** 对象所标识的计算机。
在此示例中，$Session 变量包含仅适用于名为 Server01 的计算机的 CIM 会话。
该命令应用此配置。
该命令为每个已配置的计算机创建 **Job** 对象。

## PARAMETERS

### -CimSession
在远程会话中或在远程计算机上运行 cmdlet。
输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。
默认为本地计算机上的当前会话。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
指定一个计算机名称数组。
此参数将 *路径* 参数中具有配置文档的计算机限制为数组中指定的配置文档。

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
针对目标计算机，指定用户名和密码作为 **PSCredential** 对象。
若要获取 **PSCredential** 对象，请使用 Get-Credential cmdlet。
要了解详情，请键入 `Get-Help Get-Credential`。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
停止目标计算机上当前正在运行的配置操作并开始新的 Start-Configuration 操作。
如果本地 Configuration Manager 的 **RefreshMode** 属性设置为 **Pull** ，则指定此参数会将其更改为 **Push** 。

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

### -JobName
为作业指定一个友好名称。
如果指定此参数，则 cmdlet 将作为作业运行，并且它将返回 **Job** 对象。

默认情况下，Windows PowerShell 将名称 JobN，其中 N 为整数。

如果指定 *Wait* 参数，则不指定此参数。

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

### -Path
指定包含配置设置文件的文件夹的文件路径。
此 cmdlet 将这些配置设置发布和应用到在指定路径中具有设置文件的计算机。
每个目标节点必须具有以下格式的设置文件： NetBIOS 名称。

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
指定可为运行 cmdlet 而确立的操作的最大数量。
如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。
该限制仅适用于当前 cmdlet，不适用于会话或计算机。

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

### -UseExisting
指示此 cmdlet 应用现有的配置。
通过制定使用 **start-dscconfiguration** 或使用 Publish-DscConfiguration cmdlet 的发布，可以在目标计算机上存在配置。

为此 cmdlet 指定此参数之前，请查看[Windows PowerShell 5.0 的新增功能](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)中的信息

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Wait
指示该 cmdlet 将阻止控制台，直到它完成所有的配置任务。

如果指定此参数，则不指定 *JobName* 参数。

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

## 输出

## 注释

## 相关链接

[Windows PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/overview)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscConfigurationStatus](Get-DscConfigurationStatus.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Stop-DscConfiguration](Stop-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)

[Update-DscConfiguration](Update-DscConfiguration.md)
