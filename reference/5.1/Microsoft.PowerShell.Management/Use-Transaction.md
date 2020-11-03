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
# <span data-ttu-id="8030b-103">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="8030b-103">Use-Transaction</span></span>

## <span data-ttu-id="8030b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8030b-104">SYNOPSIS</span></span>
<span data-ttu-id="8030b-105">将脚本块添加到活动事务中。</span><span class="sxs-lookup"><span data-stu-id="8030b-105">Adds the script block to the active transaction.</span></span>

## <span data-ttu-id="8030b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8030b-106">SYNTAX</span></span>

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="8030b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8030b-107">DESCRIPTION</span></span>
<span data-ttu-id="8030b-108">**使用事务** cmdlet 可将脚本块添加到活动事务中。</span><span class="sxs-lookup"><span data-stu-id="8030b-108">The **Use-Transaction** cmdlet adds a script block to an active transaction.</span></span>
<span data-ttu-id="8030b-109">这允许使用支持事务的 Microsoft .NET Framework 对象编写事务处理脚本。</span><span class="sxs-lookup"><span data-stu-id="8030b-109">This enables you to do transacted scripting by using transaction-enabled Microsoft .NET Framework objects.</span></span>
<span data-ttu-id="8030b-110">该脚本块只能包含支持事务的 .NET Framework 对象，如 Microsoft.PowerShell.Commands.Management.TransactedString 类的实例。</span><span class="sxs-lookup"><span data-stu-id="8030b-110">The script block can contain only transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="8030b-111">使用此 cmdlet 时，需要使用 UseTransaction  参数，此参数对于大多数 cmdlet 是可选的。</span><span class="sxs-lookup"><span data-stu-id="8030b-111">The *UseTransaction* parameter, which is optional for most cmdlets, is required when you use this cmdlet.</span></span>

<span data-ttu-id="8030b-112">**Use-Transaction** 是 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="8030b-112">**Use-Transaction** is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="8030b-113">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="8030b-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="8030b-114">示例</span><span class="sxs-lookup"><span data-stu-id="8030b-114">EXAMPLES</span></span>

### <span data-ttu-id="8030b-115">示例 1：使用支持事务的对象编写脚本</span><span class="sxs-lookup"><span data-stu-id="8030b-115">Example 1: Script by using a transaction-enabled object</span></span>

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

<span data-ttu-id="8030b-116">此示例演示了如何使用 **Use-Transaction** 为支持事务的 .NET Framework 对象编写脚本。</span><span class="sxs-lookup"><span data-stu-id="8030b-116">This example shows how to use **Use-Transaction** to script against a transaction-enabled .NET Framework object.</span></span>
<span data-ttu-id="8030b-117">在这种情况下，对象是 **TransactedString** 对象。</span><span class="sxs-lookup"><span data-stu-id="8030b-117">In this case, the object is a **TransactedString** object.</span></span>

<span data-ttu-id="8030b-118">第一条命令使用 Start-Transaction cmdlet 启动事务。</span><span class="sxs-lookup"><span data-stu-id="8030b-118">The first command uses the Start-Transaction cmdlet to start a transaction.</span></span>

<span data-ttu-id="8030b-119">第二个命令使用 New-Object 命令创建 **TransactedString** 对象。</span><span class="sxs-lookup"><span data-stu-id="8030b-119">The second command uses the New-Object command to create a **TransactedString** object.</span></span>
<span data-ttu-id="8030b-120">它将该对象存储在 $TransactedString 变量中。</span><span class="sxs-lookup"><span data-stu-id="8030b-120">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="8030b-121">第三个和第四个命令均使用 **TransactedString** 对象的 **Append** 方法将文本添加到 $TransactedString 的值。</span><span class="sxs-lookup"><span data-stu-id="8030b-121">The third and fourth commands both use the **Append** method of the **TransactedString** object to add text to the value of $TransactedString.</span></span>
<span data-ttu-id="8030b-122">其中一条命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="8030b-122">One command is part of the transaction.</span></span>
<span data-ttu-id="8030b-123">另一条命令则不包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="8030b-123">The other command is not.</span></span>

<span data-ttu-id="8030b-124">第三个命令使用事务处理字符串的 **Append** 方法将 Hello 添加到 $TransactedString 的值。</span><span class="sxs-lookup"><span data-stu-id="8030b-124">The third command uses the **Append** method of the transacted string to add Hello to the value of $TransactedString.</span></span>
<span data-ttu-id="8030b-125">由于该命令未包含在事务中，因此会立即应用所做更改。</span><span class="sxs-lookup"><span data-stu-id="8030b-125">Because the command is not part of the transaction, the change is applied immediately.</span></span>

<span data-ttu-id="8030b-126">第四条命令使用 **Use-Transaction** 将文本添加到事务的字符串中。</span><span class="sxs-lookup"><span data-stu-id="8030b-126">The fourth command uses **Use-Transaction** to add text to the string in the transaction.</span></span>
<span data-ttu-id="8030b-127">该命令使用 **Append** 方法将 "，World" 添加到 $TransactedString 的值。</span><span class="sxs-lookup"><span data-stu-id="8030b-127">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>
<span data-ttu-id="8030b-128">命令括在大括号中， ( {} ) 使其成为脚本块。</span><span class="sxs-lookup"><span data-stu-id="8030b-128">The command is enclosed in braces ( {} ) to make it a script block.</span></span>
<span data-ttu-id="8030b-129">在此命令中， *UseTransaction* 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="8030b-129">The *UseTransaction* parameter is required in this command.</span></span>

<span data-ttu-id="8030b-130">第五个和第六个命令使用 **TransactedString** 对象的 **ToString** 方法将 **TransactedString** 的值显示为字符串。</span><span class="sxs-lookup"><span data-stu-id="8030b-130">The fifth and sixth commands use the **ToString** method of the **TransactedString** object to display the value of the **TransactedString** as a string.</span></span>
<span data-ttu-id="8030b-131">同样，其中一条命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="8030b-131">Again, one command is part of the transaction.</span></span>
<span data-ttu-id="8030b-132">另一条则不是如此。</span><span class="sxs-lookup"><span data-stu-id="8030b-132">The other transaction is not.</span></span>

<span data-ttu-id="8030b-133">第五个命令使用 **ToString** 方法显示 $TransactedString 变量的当前值。</span><span class="sxs-lookup"><span data-stu-id="8030b-133">The fifth command uses the **ToString** method to display the current value of the $TransactedString variable.</span></span>
<span data-ttu-id="8030b-134">因为它未包含在事务中，所以它仅显示字符串的当前状态。</span><span class="sxs-lookup"><span data-stu-id="8030b-134">Because it is not part of the transaction, it displays only the current state of the string.</span></span>

<span data-ttu-id="8030b-135">第六条命令使用 **Use-Transaction** 在事务中运行同一命令。</span><span class="sxs-lookup"><span data-stu-id="8030b-135">The sixth command uses **Use-Transaction** to run the same command in the transaction.</span></span>
<span data-ttu-id="8030b-136">由于该命令包含在事务中，因此它会显示事务中字符串的当前值，这与预览事务更改非常类似。</span><span class="sxs-lookup"><span data-stu-id="8030b-136">Because the command is part of the transaction, it displays the current value of the string in the transaction, much like a preview of the transaction changes.</span></span>

<span data-ttu-id="8030b-137">第七条命令使用 Complete-Transaction cmdlet 提交事务。</span><span class="sxs-lookup"><span data-stu-id="8030b-137">The seventh command uses the Complete-Transaction cmdlet to commit the transaction.</span></span>

<span data-ttu-id="8030b-138">最后一条命令使用 **ToString** 方法将变量的结果值显示为字符串。</span><span class="sxs-lookup"><span data-stu-id="8030b-138">The final command uses the **ToString** method to display the resulting value of the variable as a string.</span></span>

### <span data-ttu-id="8030b-139">示例 2：回滚事务</span><span class="sxs-lookup"><span data-stu-id="8030b-139">Example 2: Roll back a transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

<span data-ttu-id="8030b-140">此示例显示回滚包含 **使用事务** 命令的事务的效果。</span><span class="sxs-lookup"><span data-stu-id="8030b-140">This example shows the effect of rolling back a transaction that includes **Use-Transaction** commands.</span></span>
<span data-ttu-id="8030b-141">与事务中的所有命令一样，当事务回滚后，事务型更改将被丢弃，而数据保持不变。</span><span class="sxs-lookup"><span data-stu-id="8030b-141">Like all commands in a transaction, when the transaction is rolled back, the transacted changes are discarded and the data is unchanged.</span></span>

<span data-ttu-id="8030b-142">第一条命令使用 **Start-Transaction** 启动事务。</span><span class="sxs-lookup"><span data-stu-id="8030b-142">The first command uses **Start-Transaction** to start a transaction.</span></span>

<span data-ttu-id="8030b-143">第二条命令使用 **New-Object** 创建 **TransactedString** 对象。</span><span class="sxs-lookup"><span data-stu-id="8030b-143">The second command uses **New-Object** to create a **TransactedString** object.</span></span>
<span data-ttu-id="8030b-144">它将该对象存储在 $TransactedString 变量中。</span><span class="sxs-lookup"><span data-stu-id="8030b-144">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="8030b-145">第三个命令（不是事务的一部分）使用 **Append** 方法将 "Hello" 添加到 $TransactedString 的值。</span><span class="sxs-lookup"><span data-stu-id="8030b-145">The third command, which is not part of the transaction, uses the **Append** method to add "Hello" to the value of $TransactedString.</span></span>

<span data-ttu-id="8030b-146">第四条命令使用 **Use-Transaction** 运行在事务中使用 **Append** 方法的另一个命令。</span><span class="sxs-lookup"><span data-stu-id="8030b-146">The fourth command uses **Use-Transaction** to run another command that uses the **Append** method in the transaction.</span></span>
<span data-ttu-id="8030b-147">该命令使用 **Append** 方法将 "，World" 添加到 $TransactedString 的值。</span><span class="sxs-lookup"><span data-stu-id="8030b-147">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>

<span data-ttu-id="8030b-148">第五条命令使用 Undo-Transaction cmdlet 回滚事务。</span><span class="sxs-lookup"><span data-stu-id="8030b-148">The fifth command uses the Undo-Transaction cmdlet to roll back the transaction.</span></span>
<span data-ttu-id="8030b-149">因此，在事务中执行的所有命令都将被恢复。</span><span class="sxs-lookup"><span data-stu-id="8030b-149">As a result, all commands performed in the transaction are reversed.</span></span>

<span data-ttu-id="8030b-150">最后一条命令使用 **ToString** 方法将 $TransactedString 的结果值显示为字符串。</span><span class="sxs-lookup"><span data-stu-id="8030b-150">The final command uses the **ToString** method to display the resulting value of $TransactedString as a string.</span></span>
<span data-ttu-id="8030b-151">结果显示，只有在事务外部所做的更改才被应用于对象。</span><span class="sxs-lookup"><span data-stu-id="8030b-151">The results show that only the changes that were made outside the transaction were applied to the object.</span></span>

## <span data-ttu-id="8030b-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8030b-152">PARAMETERS</span></span>

### <span data-ttu-id="8030b-153">-TransactedScript</span><span class="sxs-lookup"><span data-stu-id="8030b-153">-TransactedScript</span></span>
<span data-ttu-id="8030b-154">指定在事务中运行的脚本块。</span><span class="sxs-lookup"><span data-stu-id="8030b-154">Specifies the script block that is run in the transaction.</span></span>
<span data-ttu-id="8030b-155">可输入用大括号 ( { } ) 括起的任何有效脚本块。</span><span class="sxs-lookup"><span data-stu-id="8030b-155">Enter any valid script block enclosed in braces ( { } ).</span></span>
<span data-ttu-id="8030b-156">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="8030b-156">This parameter is required.</span></span>

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

### <span data-ttu-id="8030b-157">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="8030b-157">-UseTransaction</span></span>
<span data-ttu-id="8030b-158">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="8030b-158">Includes the command in the active transaction.</span></span>
<span data-ttu-id="8030b-159">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="8030b-159">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="8030b-160">有关详细信息，请参阅 about_transactions。</span><span class="sxs-lookup"><span data-stu-id="8030b-160">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="8030b-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8030b-161">CommonParameters</span></span>
<span data-ttu-id="8030b-162">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8030b-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8030b-163">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8030b-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8030b-164">输入</span><span class="sxs-lookup"><span data-stu-id="8030b-164">INPUTS</span></span>

### <span data-ttu-id="8030b-165">无</span><span class="sxs-lookup"><span data-stu-id="8030b-165">None</span></span>
<span data-ttu-id="8030b-166">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8030b-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8030b-167">输出</span><span class="sxs-lookup"><span data-stu-id="8030b-167">OUTPUTS</span></span>

### <span data-ttu-id="8030b-168">PSObject</span><span class="sxs-lookup"><span data-stu-id="8030b-168">PSObject</span></span>
<span data-ttu-id="8030b-169">此 cmdlet 返回事务结果。</span><span class="sxs-lookup"><span data-stu-id="8030b-169">This cmdlet returns the result of the transaction.</span></span>

## <span data-ttu-id="8030b-170">注释</span><span class="sxs-lookup"><span data-stu-id="8030b-170">NOTES</span></span>

* <span data-ttu-id="8030b-171">*UseTransaction* 参数将命令包含在活动事务中。</span><span class="sxs-lookup"><span data-stu-id="8030b-171">The *UseTransaction* parameter includes the command in the active transaction.</span></span> <span data-ttu-id="8030b-172">由于 **使用事务** cmdlet 始终用在事务中，因此需要使用此参数才能使任何 **使用-transaction** 命令生效。</span><span class="sxs-lookup"><span data-stu-id="8030b-172">Because the **Use-Transaction** cmdlet is always used in transactions, this parameter is required to make any **Use-Transaction** command effective.</span></span>

*

## <span data-ttu-id="8030b-173">相关链接</span><span class="sxs-lookup"><span data-stu-id="8030b-173">RELATED LINKS</span></span>

[<span data-ttu-id="8030b-174">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="8030b-174">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="8030b-175">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="8030b-175">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="8030b-176">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="8030b-176">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="8030b-177">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="8030b-177">Undo-Transaction</span></span>](Undo-Transaction.md)
