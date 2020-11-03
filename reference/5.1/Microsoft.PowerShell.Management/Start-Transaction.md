---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198028"
---
# Start-Transaction

## 摘要
启动事务。

## SYNTAX

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**启动事务** cmdlet 启动事务，事务是作为一个单元进行管理的一系列命令。
可以完成或提交事务。
另外，还可以完全撤消或回滚，以使事务更改的所有数据还原为其原始状态。
由于事务中的命令作为一个单元进行管理，因此所有命令不是全部提交就是全部回滚。

默认情况下，如果事务中的任何命令生成错误，将自动回滚事务。
可以使用 *RollbackPreference* 参数更改此行为。

事务中使用的 cmdlet 必须设计为支持事务。
支持事务的 cmdlet 具有 *UseTransaction* 参数。
若要通过提供程序执行事务，则该提供程序必须支持事务。
Windows Vista 和更高版本的 windows 操作系统中的 Windows PowerShell 注册表提供程序支持事务。
你还可以使用 **TransactedString** 类在支持 windows PowerShell 的任意版本的 windows 系统上的事务中包含表达式。
其他 Windows PowerShell 提供程序也可以支持事务。

一次只能有一个事务处于活动状态。
如果在事务正在进行的过程中启动一个新的独立事务，则新事务将成为活动事务，并且必须在对原始事务进行任何更改之前提交或回滚新事务。

**启动-Transaction** cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。
有关详细信息，请参阅 about_Transactions。

## 示例

### 示例1：启动和回滚事务

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

这些命令先启动事务，然后回滚事务。
由于回滚了事务，因此未对注册表进行更改。

### 示例2：启动并完成事务

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

这些命令先启动事务，然后完成事务。
在使用 **完整事务** 命令之前，不会对注册表进行任何更改。

### 示例3：使用不同的回滚首选项

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

此示例演示了更改 *RollbackPreference* 参数值的效果。

在第一组命令中， **Start-Transaction** 不使用 *RollbackPreference* 。
因此，会使用 (错误) 默认值。
当事务命令中发生错误（即，指定的路径不存在）时，将自动回滚该事务。

在第二组命令中， **Start-Transaction** 使用值为 "Never" 的 *RollbackPreference* 。
因此当事务命令发生错误时，事务仍处于活动状态并且可以成功完成。

由于大多数事务都必须在没有错误的情况下执行，因此 *RollbackPreference* 的默认值通常是首选值。

### 示例4：在事务正在进行时使用此 cmdlet

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

此示例显示了在事务正在进行时使用 **启动事务** 的效果。
这与加入正在执行的事务的效果非常类似。

尽管这是一个简化的命令，但当事务涉及到运行包含完整事务的脚本时，通常会发生这种情况。

第一个 **启动事务** 命令启动事务。
第一个 **新项** 命令是事务的一部分。

第二个 **启动事务** 命令向事务中添加新的订阅服务器。
现在， **获取事务** 命令返回的事务的订户计数为2。
第二个 **新项** 命令是同一事务的一部分。

在整个事务完成之前，不会对注册表进行任何更改。
若要完成事务，必须输入两个 **完整事务** 的命令，每个订阅服务器一个。
如果要回滚事务，则所有事务都将回滚到这两个订阅服务器。

### 示例5：启动一个独立的事务，而另一个事务正在进行

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

此示例显示了在另一个事务正在进行时使用 **启动事务** 的 *独立* 参数启动事务的效果。
在本例中，将回滚新事务，而不影响原来的事务。

虽然事务在逻辑上是独立的，但由于一次只能有一个事务处于活动状态，因此你必须回滚或提交最新事务，然后才能继续处理原来的事务。

第一组命令启动一个事务。
**新项** 命令是第一个事务的一部分。

在第二组命令中， **Start Transaction** 命令使用 *独立* 参数。
下面的 **Get Transaction** 命令显示活动事务的事务对象，这是最新的事务。
订阅者计数等于1，表明事务不相关。

当使用 **Undo transaction** 命令回滚活动事务时，原来的事务将再次变为活动状态。

**Set-itemproperty** 命令（它是原始事务的一部分）完成时不会出错，并且可以通过使用 **Complete transaction** 命令完成原始事务。
因此注册表会发生更改。

### 示例6：运行不属于事务的命令

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

此示例演示了在事务正在执行时提交的命令可以包含在事务中，也可以不包含在事务中。
只有使用 *UseTransaction* 参数的命令才包含在事务中。

第一个和第三个 **新项** 命令使用 *UseTransaction* 参数。
这两个命令都包含在事务中。
因为第二个 **新项** 命令不使用 *UseTransaction* 参数，所以它不是事务的一部分。

第一个 dir 命令显示了效果。
第二个 **新项** 命令将立即完成，但在提交事务之前，第一个和第三个 **新的** 命令将不会生效。

**Complete transaction** 命令提交事务。
因此，第二个 dir 命令显示已将所有新项添加到注册表中。

### 示例7：回滚在指定时间内未完成的事务

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

此命令使用 **Start transaction** 的 *Timeout* 参数启动必须在两分钟内完成的事务。
如果在超时过期后事务未完成，则会自动回滚。

当超时到期时，你不会收到通知，但事务对象的 **Status** 属性将设置为 RolledBack，并且使用 *UseTransaction* 参数的命令将失败。

## PARAMETERS

### -Independent
指示此 cmdlet 启动独立于正在进行的事务的事务。
默认情况下，如果在另一个事务正在进行时使用 **启动事务** ，则会向正在进行的事务中添加新的订阅服务器。
仅当会话中已经在执行某项事务时，此参数才有效。

默认情况下，如果在事务正在进行时使用 **Start transaction** ，将重用现有事务对象，并且订阅者计数将递增。
这与加入原来事务的效果非常类似。
Undo-Transaction 命令将回滚整个事务。
若要完成事务，则必须为每个订阅者输入一个 Complete-Transaction 命令。
因为同时执行的多数事务都是相关的，所以默认设置可满足大多数用途的要求。

如果指定 *独立* 参数，则此 cmdlet 会创建一个新事务，该事务可在不影响原始事务的情况下完成或撤消。
但是，由于一次只能有一个事务处于活动状态，因此必须完成或回滚新事务，然后才能继续处理原来的事务。

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

### -RollbackPreference
指定自动回滚事务的条件。
此参数的可接受值为：

- 错误。
当发生终止错误或非终止错误时，自动回滚事务。
- TerminatingError.
当发生终止错误时，自动回滚事务。
- 从不。
从不自动回滚事务。

默认值为 "错误"。

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timeout
指定事务处于活动状态的最长时间，以分钟为单位。
当该超时到期时，将自动回滚事务。

默认情况下，在命令行启动的事务没有超时值。
如果事务由脚本启动，则默认超时值为 30 分钟。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

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

### 无
不能通过管道将输入传递给此 cmdlet。

## 输出

### 无
此 cmdlet 将不生成任何输出。

## 注释

## 相关链接

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)
