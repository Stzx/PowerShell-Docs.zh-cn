---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93194638"
---
# Get-Transaction

## 摘要
获取当前（活动）事务。

## SYNTAX

```
Get-Transaction [<CommonParameters>]
```

## DESCRIPTION
**获取事务** cmdlet 获取表示会话中的当前事务的对象。

此 cmdlet 从不返回多个对象，原因是同一时间只有一个事务处于活动状态。
如果通过使用启动事务) 的独立参数来启动一个或多个独立的事务 (，则最近启动的事务处于活动状态，这是 **获取事务** 的事务。

当所有活动事务都已回滚或提交时，此 cmdlet 将显示会话中最近处于活动状态的事务。

此 cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。
有关详细信息，请参阅 about_Transactions。

## 示例

### 示例1：获取当前事务

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

此命令使用 Get-Transaction cmdlet 来获取当前事务。

### 示例2：显示 transaction 对象的属性和方法

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

此命令使用 Get-Member cmdlet 来显示事务对象的属性和方法。

### 示例3：显示已回滚事务的属性值

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

此命令显示已回滚事务的事务对象属性值。

### 示例4：显示已提交事务的属性值

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

此命令显示已提交事务的事务对象属性值。

### 示例5：启动事务，而另一个事务正在进行

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

此示例演示当一个事务正在运行时，启动另一个事务对事务对象的影响。
通常，当运行事务的脚本包括函数或调用包含其他完整事务的脚本时，会发生这种情况。

除非第二个 **启动事务** 命令包含 *独立* 的参数，否则 **Start transaction** 不会创建新的事务。
它会将第二个订阅者添加到原始事务中。

第一个 **启动事务** 命令启动事务。
带有 *UseTransaction* 参数的 New-Item 命令是事务的一部分。

第二个 **开始事务** 命令将订阅服务器添加到事务。
下一条 New-Item 命令也是该事务的一部分。

第一个 **Get transaction** 命令显示多订阅服务器事务。
请注意，订阅者计数为 2。

第一条 Complete-Transaction 命令不会提交事务，但它会将订阅者计数减少到 1。

第二个 **完整事务** 命令提交事务。

### 示例6：启动独立事务，而另一个事务正在进行

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

此示例演示当一个事务正在运行时，启动另一个独立事务对事务对象的影响。

第一个 **启动事务** 命令启动事务。
带有 *UseTransaction* 参数的 **新项** 命令是事务的一部分。

第二个 **开始事务** 命令将订阅服务器添加到事务。
下一个 **新项** 命令也是该事务的一部分。

第一个 **Get transaction** 命令显示多订阅服务器事务。
请注意，订阅者计数为 2。

**Complete Transaction** 命令将订阅服务器计数减少到1，但它不提交事务。

第二个 **完整事务** 命令提交事务。

## PARAMETERS

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无
不能通过管道将对象传递给此 cmdlet。

## 输出

### System.Management.Automation.PSTransaction
此 cmdlet 将返回一个表示当前事务的对象。

## 注释

## 相关链接

[Complete-Transaction](Complete-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)

[Use-Transaction](Use-Transaction.md)

[New-Item](New-Item.md)
