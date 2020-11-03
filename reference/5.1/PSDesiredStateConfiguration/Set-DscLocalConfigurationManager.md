---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "93198934"
---
# Set-DscLocalConfigurationManager

## 摘要

向节点应用本地 Configuration Manager (LCM) 设置。

## SYNTAX

### ComputerNameSet（默认值）

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CimSessionSet

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Set-DscLocalConfigurationManager`Cmdlet 可将 LCM 设置或元配置应用到节点。 通过指定计算机名称或通过使用通用信息模型 (CIM) 会话来指定计算机。 如果不指定目标计算机，则该 cmdlet 将设置应用到本地计算机。

## 示例

### 示例1：应用 LCM 设置

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

此命令将 LCM 设置从应用 `C:\DSC\Configurations\` 到目标节点。 收到设置后，LCM 会处理它们。

> [!WARNING]
> 如果指定文件夹中存储的同一台计算机有多个元 mof，则只会应用第一个元 mof。

### 示例2：使用 CIM 会话应用 LCM 设置

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

此示例将 LCM 设置应用到计算机，并应用这些设置。 该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。 或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。

第一个命令使用 cmdlet 创建 CIM 会话 `New-CimSession` ，然后将 **CimSession** 对象存储在 `$Session` 变量中。 该命令会提示你输入密码。 要了解详情，请键入 `Get-Help New-CimSession`。

第二个命令将目标节点的 LCM 设置应用于 `C:\DSC\Configurations\` 由变量中存储的 **CimSession** 对象标识的计算机 `$Session` 。 在此示例中， `$Session` 变量只包含一个名为 Server01 的计算机的 CIM 会话。 该命令将应用这些设置。 收到设置后，LCM 会处理它们。

## PARAMETERS

### -CimSession

在远程会话中或在远程计算机上运行 cmdlet。 输入计算机名或会话对象，例如 [CimSession](/powershell/module/CimCmdlets/New-CimSession) 或 [CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet 的输出。
默认为本地计算机上的当前会话。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName

指定一个计算机名称数组。 此参数将 **Path** 参数中包含元配置文档的计算机限制为数组中指定的文档。

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential

针对目标计算机，指定用户名和密码作为 **PSCredential** 对象。 若要获取 **PSCredential** 对象，请使用 Get-Credential cmdlet。 要了解详情，请键入 `Get-Help Get-Credential`。

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

强制运行命令而不要求用户确认。

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

### -Path

指定包含配置设置文件的文件夹的文件路径。 Cmdlet 将这些 LCM 设置发布并应用到在指定路径中具有设置文件的计算机。 每个目标节点必须具有以下格式的设置文件： `NetBIOS Name.meta.mof` 。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

指定可为运行 cmdlet 而确立的操作的最大数量。 如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。 该限制仅适用于当前 cmdlet，不适用于会话或计算机。

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

## 输出

## 注释

## 相关链接

[Windows PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/overview)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)
