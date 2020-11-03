---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198015"
---
# Undo-Transaction

## 摘要
回滚活动事务。

## SYNTAX

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Undo-Transaction** cmdlet 回滚活动事务。
回滚事务时，事务中的命令所做的更改将被丢弃，数据将还原到其原始格式。

如果事务包含多个订阅服务器，则 **Undo transaction** 命令将回滚所有订阅服务器的整个事务。

默认情况下，如果事务中的任何命令发生错误，事务都会自动回滚。
但是，可以使用不同的回滚首选项启动事务，并且你可以使用此 cmdlet 随时回滚活动事务。

**Undo Transaction** cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。
有关详细信息，请参阅 about_Transactions。

## 示例

### 示例1：回滚当前事务

```
PS C:\> Undo-Transaction
```

此命令回滚当前的活动事务。

### 示例2：启动和回滚事务

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

此示例将启动一个事务，然后将其回滚。
因此未对注册表进行更改。

### 示例3：回滚所有订阅服务器的事务

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

此示例演示当任何订阅者回滚事务时，将回滚所有订阅服务器的整个事务。

第一条命令将位置更改为 HKCU:\Software 注册表项。

第二条命令启动事务。

第三条命令使用 New-Item cmdlet 创建新的注册表项。
该命令使用 *UseTransaction* 参数将更改包含在事务中。

第四条命令使用 Get-Transaction cmdlet 获取活动事务。
你会看到状态为 Active，订阅者计数为 1。

第五条命令同样使用 Start-Transaction 命令。
通常，当一个事务正在运行时，如果主事务使用的脚本包含其自己的完整事务，则会启动另一个事务。
此示例以交互方式执行，以便你可以分阶段检查。
当你在另一个事务正在进行时运行 **Start Transaction** 命令时，这些命令会将现有事务作为新的订阅者加入，并递增订阅者计数。

第六个命令使用 **获取事务** cmdlet 获取活动事务。
你会看到此时订阅者计数为 2。

第七个命令使用 **Undo-transaction** 回滚事务。
此命令不返回任何对象。

最后一个命令是获取活动的（在本例中为最近活动的事务）的 **Get Transaction** 命令。
结果显示事务已回滚并且订阅者计数为 0，这表明已为所有订阅者回滚事务。

## PARAMETERS

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

### 无
不能通过管道将输入传递给此 cmdlet。

## 输出

### 无
此 cmdlet 不返回任何输出。

## 注释

* 不能回滚已提交的事务。

  不能回滚活动事务之外的任何事务。
若要回滚其他独立事务，则必须先提交或回滚活动事务。

  回滚事务将会终止该事务。
若要再次使用事务，则必须启动新事务。

## 相关链接

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Use-Transaction](Use-Transaction.md)
