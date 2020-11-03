---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198319"
---
# Complete-Transaction

## 摘要
提交活动事务。

## SYNTAX

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**完整事务** cmdlet 将提交活动事务。
在提交事务时，该事务中的命令将完成，并且受这些命令影响的数据将发生更改。

如果事务包含多个订阅服务器，若要提交事务，则必须为每个 Start-Transaction 命令输入一个 **完整的 transaction** 命令。

**完整事务** cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。
有关详细信息，请参阅 about_Transactions。

## 示例

### 示例1：提交事务

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

此示例显示了使用 **完整事务** cmdlet 提交事务时将发生的情况。

**Start transaction** 命令启动事务。
New-Item 命令使用 *UseTransaction* 参数将命令包含在事务中。

第一个目录 (Get-childitem) 命令显示尚未将新项添加到注册表中。

**Complete transaction** 命令提交事务，这会使注册表更改生效。
因此，第二个 dir 命令显示注册表已更改。

### 示例2：提交具有多个订阅服务器的事务

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

此示例演示如何使用 **完整事务** 来提交具有多个订阅服务器的事务。

若要提交多订户事务，你必须为每个 **开始事务** 命令输入一个 **完整的事务** 命令。
仅当提交最后一个 **完整事务** 命令时，才会更改数据。

出于演示目的，此示例演示了一系列在命令行中输入的命令。
实际上，事务很可能在脚本中运行，其中二级事务由主脚本调用的函数或助手脚本运行。

在此示例中， **启动事务** 命令启动事务。
带有 *UseTransaction* 参数的 **新项** 命令会将 MyCompany 项添加到软件密钥中。
尽管 **新项** cmdlet 返回密钥对象，但注册表中的数据尚未更改。

第二个 **启动事务** 命令向现有事务中添加另一个订阅服务器。
**获取事务** cmdlet 可确认订阅者计数为2。
带有 *UseTransaction* 参数的 New-ItemProperty 命令将一个注册表项添加到新的 MyCompany 项。
该命令再次返回一个值，但注册表未发生更改。

第一个 **完整事务** 命令将订阅服务器计数减少1。
此方法由 **获取事务** 命令确认。
不过，出现不会更改任何数据，因为 dir m * ( **get-childitem** ) 命令。

第二个 **完整事务** 命令将提交整个事务并更改注册表中的数据。
这通过第二个 dir m * 命令来确认，该命令显示了所做的更改。

### 示例3：执行不更改任何数据的事务

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

此示例演示在事务中使用 Get-\* 命令以及不会更改数据的其他命令的值。
在事务中使用 Get-\* 命令时，它将获取属于该事务的对象。
这样，在提交更改之前，可以预览事务中的更改。

在此示例中，将启动一个事务。
带有 *UseTransaction* 参数的 New-Item 命令将新项作为事务的一部分添加到注册表中。

由于在运行 **Complete Transaction** 命令之前不会将新的注册表项添加到注册表中，因此一个简单的目录 ( **get-childitem** ) 命令显示不带新密钥的注册表。

但是，将 *UseTransaction* 参数添加到 dir 命令后，该命令将成为事务的一部分，并且即使尚未将这些项添加到数据中，它也会获取事务中的项。

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
不能通过管道将对象传递给此 cmdlet。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

* 无法回滚已提交的事务，或提交已回滚的事务。

  不能回滚活动事务之外的任何事务。
若要回滚其他事务，必须首先提交或回滚活动事务。

  默认情况下，如果无法提交事务的任何部分（例如，当事务中的某个命令产生错误时），则将回滚整个事务。

*

## 相关链接

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[Get-ChildItem](Get-ChildItem.md)

[New-Item](New-Item.md)

[New-ItemProperty](New-ItemProperty.md)
