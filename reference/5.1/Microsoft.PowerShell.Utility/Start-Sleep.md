---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 3/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4add39c09b6123aaf8c9302529346a6b1dec391
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197846"
---
# Start-Sleep

## 摘要
在指定的时间段内将脚本或会话中的活动挂起。

## SYNTAX

### Seconds（默认值）

```
Start-Sleep [-Seconds] <Int32> [<CommonParameters>]
```

### 毫秒

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## DESCRIPTION

`Start-Sleep`Cmdlet 将在指定的时间段内将脚本或会话中的活动挂起。
你可以使用它完成许多任务，例如等待操作完成或在重复操作之前暂停。

## 示例

### 示例1：为所有命令休眠15秒

```powershell
Start-Sleep -s 15
```

此命令让会话中的所有命令休眠 15 秒。

### 示例2：睡眠所有命令

```powershell
Start-Sleep -m 500
```

此命令让会话中的所有命令休眠 1/2 秒（500 毫秒）。

## PARAMETERS

### -Milliseconds

指定资源休眠的时间（以毫秒为单位）。
该参数可以缩写为 **m** 。

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Seconds

指定资源休眠的时间（以秒为单位）。
)  ( **秒** ，可以省略参数名称，也可以将其 **缩写为。**

```yaml
Type: System.Int32
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。

## 输入

### System.Int32

可以通过管道将秒数传递给 `Start-Sleep` 。

## 输出

### 无

此 cmdlet 不返回任何输出。

## 注释

- 还可以 `Start-Sleep` 通过其内置别名来引用 `sleep` 。 有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。
- `Ctrl+C` 中断 `Start-Sleep` 。
  - `Ctrl+C` 不会中断 `[Threading.Thread]::Sleep` 。 有关详细信息，请参阅 [Thread 方法](/dotnet/api/system.threading.thread.sleep)。

## 相关链接
