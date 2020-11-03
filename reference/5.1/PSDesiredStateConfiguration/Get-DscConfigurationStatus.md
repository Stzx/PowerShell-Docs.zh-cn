---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198271"
---
# Get-DscConfigurationStatus

## 摘要
检索有关已完成的配置运行的数据。

## SYNTAX

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
**Get-dscconfigurationstatus** cmdlet 将检索有关系统上已完成的配置运行的详细信息。
默认情况下，它将返回有关上次配置运行的信息。
此 cmdlet 可用于查找有关配置运行的历史信息，如运行配置、运行状态、配置中的资源数，以及成功或失败的资源。

## 示例

### 示例1：获取有关上次配置运行的信息

```
PS C:\> Get-DscConfigurationStatus
```

此命令获取有关上次配置运行的信息。

### 示例2：获取所有配置的信息

```
PS C:\> Get-DscConfigurationStatus -All
```

此命令将获取系统上运行的所有配置的相关信息，包括 Windows PowerShell Desired State Configuration (DSC) 一致性检查。

### 示例3：获取有关在远程计算机上运行的配置的信息

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

此命令获取名为 Server01 的远程计算机的配置运行详细信息。
这将使用 WSMan 传输连接到远程计算机，并要求连接用户是远程计算机上的管理员。

## PARAMETERS

### -All
指示此 cmdlet 检索计算机上运行的所有配置的相关信息，包括配置应用程序和一致性检查。

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
指示此 cmdlet 将命令作为后台作业运行。

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

### -CimSession
在远程会话中或在远程计算机上运行 cmdlet。
输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。
默认为本地计算机上的当前会话。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
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

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

## 输出

## 注释

## 相关链接

[Windows PowerShell Desired State Configuration 概述](/powershell/scripting/dsc/overview/dscforengineers)

[Get-DscConfiguration](Get-DscConfiguration.md)

[Get-DscLocalConfigurationManager](Get-DscLocalConfigurationManager.md)

[Restore-DscConfiguration](Restore-DscConfiguration.md)

[Start-DscConfiguration](Start-DscConfiguration.md)

[Test-DscConfiguration](Test-DscConfiguration.md)
