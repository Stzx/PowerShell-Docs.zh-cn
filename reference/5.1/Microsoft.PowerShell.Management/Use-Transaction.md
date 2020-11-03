---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198019"
---
# Use-Transaction

## 摘要
将脚本块添加到活动事务中。

## SYNTAX

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## DESCRIPTION
**使用事务** cmdlet 可将脚本块添加到活动事务中。
这允许使用支持事务的 Microsoft .NET Framework 对象编写事务处理脚本。
该脚本块只能包含支持事务的 .NET Framework 对象，如 Microsoft.PowerShell.Commands.Management.TransactedString 类的实例。

使用此 cmdlet 时，需要使用 UseTransaction  参数，此参数对于大多数 cmdlet 是可选的。

**Use-Transaction** 是 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。
有关详细信息，请参阅 about_Transactions。

## 示例

### 示例 1：使用支持事务的对象编写脚本

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

此示例演示了如何使用 **Use-Transaction** 为支持事务的 .NET Framework 对象编写脚本。
在这种情况下，对象是 **TransactedString** 对象。

第一条命令使用 Start-Transaction cmdlet 启动事务。

第二个命令使用 New-Object 命令创建 **TransactedString** 对象。
它将该对象存储在 $TransactedString 变量中。

第三个和第四个命令均使用 **TransactedString** 对象的 **Append** 方法将文本添加到 $TransactedString 的值。
其中一条命令包含在事务中。
另一条命令则不包含在事务中。

第三个命令使用事务处理字符串的 **Append** 方法将 Hello 添加到 $TransactedString 的值。
由于该命令未包含在事务中，因此会立即应用所做更改。

第四条命令使用 **Use-Transaction** 将文本添加到事务的字符串中。
该命令使用 **Append** 方法将 "，World" 添加到 $TransactedString 的值。
命令括在大括号中， ( {} ) 使其成为脚本块。
在此命令中， *UseTransaction* 参数是必需的。

第五个和第六个命令使用 **TransactedString** 对象的 **ToString** 方法将 **TransactedString** 的值显示为字符串。
同样，其中一条命令包含在事务中。
另一条则不是如此。

第五个命令使用 **ToString** 方法显示 $TransactedString 变量的当前值。
因为它未包含在事务中，所以它仅显示字符串的当前状态。

第六条命令使用 **Use-Transaction** 在事务中运行同一命令。
由于该命令包含在事务中，因此它会显示事务中字符串的当前值，这与预览事务更改非常类似。

第七条命令使用 Complete-Transaction cmdlet 提交事务。

最后一条命令使用 **ToString** 方法将变量的结果值显示为字符串。

### 示例 2：回滚事务

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

此示例显示回滚包含 **使用事务** 命令的事务的效果。
与事务中的所有命令一样，当事务回滚后，事务型更改将被丢弃，而数据保持不变。

第一条命令使用 **Start-Transaction** 启动事务。

第二条命令使用 **New-Object** 创建 **TransactedString** 对象。
它将该对象存储在 $TransactedString 变量中。

第三个命令（不是事务的一部分）使用 **Append** 方法将 "Hello" 添加到 $TransactedString 的值。

第四条命令使用 **Use-Transaction** 运行在事务中使用 **Append** 方法的另一个命令。
该命令使用 **Append** 方法将 "，World" 添加到 $TransactedString 的值。

第五条命令使用 Undo-Transaction cmdlet 回滚事务。
因此，在事务中执行的所有命令都将被恢复。

最后一条命令使用 **ToString** 方法将 $TransactedString 的结果值显示为字符串。
结果显示，只有在事务外部所做的更改才被应用于对象。

## PARAMETERS

### -TransactedScript
指定在事务中运行的脚本块。
可输入用大括号 ( { } ) 括起的任何有效脚本块。
此参数是必需的。

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction
在活动事务中使用该命令。
仅当正在执行事务时，此参数才有效。
有关详细信息，请参阅 about_transactions。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

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

### PSObject
此 cmdlet 返回事务结果。

## 注释

* *UseTransaction* 参数将命令包含在活动事务中。 由于 **使用事务** cmdlet 始终用在事务中，因此需要使用此参数才能使任何 **使用-transaction** 命令生效。

*

## 相关链接

[Complete-Transaction](Complete-Transaction.md)

[Get-Transaction](Get-Transaction.md)

[Start-Transaction](Start-Transaction.md)

[Undo-Transaction](Undo-Transaction.md)
