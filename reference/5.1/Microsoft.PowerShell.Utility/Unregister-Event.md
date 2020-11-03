---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unregister-event?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-Event
ms.openlocfilehash: f1f42c1e8831896feac398228e45fc0890136fff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197839"
---
# Unregister-Event

## 摘要
取消事件订阅。

## SYNTAX

### BySource（默认值）

```
Unregister-Event [-SourceIdentifier] <String> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById

```
Unregister-Event [-SubscriptionId] <Int32> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Unregister-Event** cmdlet 可取消使用 Register-EngineEventt、Register-ObjectEvent 或 Register-WmiEvent cmdlet 创建的事件订阅。

取消事件订阅后，将从会话中删除事件订阅服务器，并且不再将订阅的事件添加到事件队列中。
取消使用 New-Event cmdlet 创建的事件订阅后，还将从会话中删除新的事件。

**Unregister-Event** 不会从事件队列中删除事件。
若要删除事件，请使用 Remove-Event cmdlet。

## 示例

### 示例 1：按源标识符取消事件订阅

```
PS C:\> Unregister-Event -SourceIdentifier "ProcessStarted"
```

此命令将取消源标识符为 ProcessStarted 的事件订阅。

若要查找事件的源标识符，请使用 Get-Event cmdlet。
若要查找事件订阅的源标识符，请使用 **Get-EventSubscriber** cmdlet。

### 示例 2：按订阅标识符取消事件订阅

```
PS C:\> Unregister-Event -SubscriptionId 2
```

此命令将取消订阅标识符为 2 的事件订阅。

若要查找事件订阅的订阅标识符，请使用 **Get-EventSubscriber** cmdlet。

### 示例 3：取消所有事件订阅

```
PS C:\> Get-EventSubscriber -Force | Unregister-Event -Force
```

此命令将取消会话中的所有事件订阅。

该命令使用  参数隐藏的订阅服务器。

它使用管道运算符 (|) 将订阅服务器对象发送到 **Unregister-Event** ，后者将它们从会话中删除。
若要完成该任务，还需要在  参数。

## PARAMETERS

### -Force
取消所有事件订阅，包括通过使用  参数隐藏的订阅。

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

### -SourceIdentifier
指定此 cmdlet 取消事件订阅的源标识符。

必须在每个命令中都包含 SourceIdentifier  或 SubscriptionId  参数。

```yaml
Type: System.String
Parameter Sets: BySource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
指定此 cmdlet 取消事件订阅的源标识符 ID。

必须在每个命令中都包含 SourceIdentifier  或 SubscriptionId  参数。

```yaml
Type: System.Int32
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.Management.Automation.PSEventSubscriber
可以通过管道将输出从 Get-EventSubscriber 传递给 **Unregister-Event** 。

## 输出

### 无
此 cmdlet 不返回任何输出。

## 注释

* 事件、事件订阅和事件队列仅存在于当前会话中。 如果关闭当前会话，将丢弃事件队列并取消事件订阅。

  **取消注册-事件** 无法删除使用 New-Event cmdlet 创建的事件，除非你已使用 **register-engineevent** cmdlet 订阅了该事件。
若要从会话中删除自定义事件，必须以编程方式删除事件或关闭会话。

*

## 相关链接

[Get-Event](Get-Event.md)

[Get-EventSubscriber](Get-EventSubscriber.md)

[New-Event](New-Event.md)

[Register-EngineEvent](Register-EngineEvent.md)

[Register-ObjectEvent](Register-ObjectEvent.md)

[Remove-Event](Remove-Event.md)

[Unregister-Event](Unregister-Event.md)

[Wait-Event](Wait-Event.md)
