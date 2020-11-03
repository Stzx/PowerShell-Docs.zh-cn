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
# <span data-ttu-id="eaad6-103">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="eaad6-103">Undo-Transaction</span></span>

## <span data-ttu-id="eaad6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="eaad6-104">SYNOPSIS</span></span>
<span data-ttu-id="eaad6-105">回滚活动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-105">Rolls back the active transaction.</span></span>

## <span data-ttu-id="eaad6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="eaad6-106">SYNTAX</span></span>

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="eaad6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="eaad6-107">DESCRIPTION</span></span>
<span data-ttu-id="eaad6-108">**Undo-Transaction** cmdlet 回滚活动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-108">The **Undo-Transaction** cmdlet rolls back the active transaction.</span></span>
<span data-ttu-id="eaad6-109">回滚事务时，事务中的命令所做的更改将被丢弃，数据将还原到其原始格式。</span><span class="sxs-lookup"><span data-stu-id="eaad6-109">When you roll back a transaction, the changes that were made by the commands in the transaction are discarded and the data is restored to its original form.</span></span>

<span data-ttu-id="eaad6-110">如果事务包含多个订阅服务器，则 **Undo transaction** 命令将回滚所有订阅服务器的整个事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-110">If the transaction includes multiple subscribers, an **Undo-Transaction** command rolls back the whole transaction for all subscribers.</span></span>

<span data-ttu-id="eaad6-111">默认情况下，如果事务中的任何命令发生错误，事务都会自动回滚。</span><span class="sxs-lookup"><span data-stu-id="eaad6-111">By default, transactions are rolled back automatically if any command in the transaction generates an error.</span></span>
<span data-ttu-id="eaad6-112">但是，可以使用不同的回滚首选项启动事务，并且你可以使用此 cmdlet 随时回滚活动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-112">However, transactions can be started by using a different rollback preference and you can use this cmdlet to roll back the active transaction at any time.</span></span>

<span data-ttu-id="eaad6-113">**Undo Transaction** cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="eaad6-113">The **Undo-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="eaad6-114">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="eaad6-114">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="eaad6-115">示例</span><span class="sxs-lookup"><span data-stu-id="eaad6-115">EXAMPLES</span></span>

### <span data-ttu-id="eaad6-116">示例1：回滚当前事务</span><span class="sxs-lookup"><span data-stu-id="eaad6-116">Example 1: Roll back the current transaction</span></span>

```
PS C:\> Undo-Transaction
```

<span data-ttu-id="eaad6-117">此命令回滚当前的活动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-117">This command rolls back the current, active, transaction.</span></span>

### <span data-ttu-id="eaad6-118">示例2：启动和回滚事务</span><span class="sxs-lookup"><span data-stu-id="eaad6-118">Example 2: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

<span data-ttu-id="eaad6-119">此示例将启动一个事务，然后将其回滚。</span><span class="sxs-lookup"><span data-stu-id="eaad6-119">This example starts a transaction and then rolls it back.</span></span>
<span data-ttu-id="eaad6-120">因此未对注册表进行更改。</span><span class="sxs-lookup"><span data-stu-id="eaad6-120">As a result, no changes are made to the registry.</span></span>

### <span data-ttu-id="eaad6-121">示例3：回滚所有订阅服务器的事务</span><span class="sxs-lookup"><span data-stu-id="eaad6-121">Example 3: Roll back a transaction for all subscribers</span></span>

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

<span data-ttu-id="eaad6-122">此示例演示当任何订阅者回滚事务时，将回滚所有订阅服务器的整个事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-122">This example demonstrates that when any subscriber rolls back a transaction, the whole transaction is rolled back for all subscribers.</span></span>

<span data-ttu-id="eaad6-123">第一条命令将位置更改为 HKCU:\Software 注册表项。</span><span class="sxs-lookup"><span data-stu-id="eaad6-123">The first command changes the location to the HKCU:\Software registry key.</span></span>

<span data-ttu-id="eaad6-124">第二条命令启动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-124">The second command starts a transaction.</span></span>

<span data-ttu-id="eaad6-125">第三条命令使用 New-Item cmdlet 创建新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="eaad6-125">The third command uses the New-Item cmdlet to create a new registry key.</span></span>
<span data-ttu-id="eaad6-126">该命令使用 *UseTransaction* 参数将更改包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="eaad6-126">The command uses the *UseTransaction* parameter to include the change in the transaction.</span></span>

<span data-ttu-id="eaad6-127">第四条命令使用 Get-Transaction cmdlet 获取活动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-127">The fourth command uses the Get-Transaction cmdlet to get the active transaction.</span></span>
<span data-ttu-id="eaad6-128">你会看到状态为 Active，订阅者计数为 1。</span><span class="sxs-lookup"><span data-stu-id="eaad6-128">Notice that the status is Active and the subscriber count is 1.</span></span>

<span data-ttu-id="eaad6-129">第五条命令同样使用 Start-Transaction 命令。</span><span class="sxs-lookup"><span data-stu-id="eaad6-129">The fifth command uses the Start-Transaction command again.</span></span>
<span data-ttu-id="eaad6-130">通常，当一个事务正在运行时，如果主事务使用的脚本包含其自己的完整事务，则会启动另一个事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-130">Typically, starting a transaction while another transaction is in progress occurs when a script that is used by the main transaction includes its own complete transaction.</span></span>
<span data-ttu-id="eaad6-131">此示例以交互方式执行，以便你可以分阶段检查。</span><span class="sxs-lookup"><span data-stu-id="eaad6-131">This example is performed interactively so that you can examine it in stages.</span></span>
<span data-ttu-id="eaad6-132">当你在另一个事务正在进行时运行 **Start Transaction** 命令时，这些命令会将现有事务作为新的订阅者加入，并递增订阅者计数。</span><span class="sxs-lookup"><span data-stu-id="eaad6-132">When you run a **Start-Transaction** command while another transaction is in progress, the commands join the existing transaction as a new subscriber and the subscriber count is incremented.</span></span>

<span data-ttu-id="eaad6-133">第六个命令使用 **获取事务** cmdlet 获取活动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-133">The sixth command uses the **Get-Transaction** cmdlet to get the active transaction.</span></span>
<span data-ttu-id="eaad6-134">你会看到此时订阅者计数为 2。</span><span class="sxs-lookup"><span data-stu-id="eaad6-134">Notice that the subscriber count is now 2.</span></span>

<span data-ttu-id="eaad6-135">第七个命令使用 **Undo-transaction** 回滚事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-135">The seventh command uses **Undo-Transaction** to roll back the transaction.</span></span>
<span data-ttu-id="eaad6-136">此命令不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="eaad6-136">This command does not return any objects.</span></span>

<span data-ttu-id="eaad6-137">最后一个命令是获取活动的（在本例中为最近活动的事务）的 **Get Transaction** 命令。</span><span class="sxs-lookup"><span data-stu-id="eaad6-137">The final command is a **Get-Transaction** command that gets the active, or in this case, the most recently active, transaction.</span></span>
<span data-ttu-id="eaad6-138">结果显示事务已回滚并且订阅者计数为 0，这表明已为所有订阅者回滚事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-138">The results show that the transaction is rolled back, and that the subscriber count is 0, showing that the transaction was rolled back for all subscribers.</span></span>

## <span data-ttu-id="eaad6-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="eaad6-139">PARAMETERS</span></span>

### <span data-ttu-id="eaad6-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="eaad6-140">-Confirm</span></span>
<span data-ttu-id="eaad6-141">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="eaad6-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="eaad6-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="eaad6-142">-WhatIf</span></span>
<span data-ttu-id="eaad6-143">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="eaad6-143">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="eaad6-144">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="eaad6-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="eaad6-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="eaad6-145">CommonParameters</span></span>
<span data-ttu-id="eaad6-146">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="eaad6-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="eaad6-147">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="eaad6-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="eaad6-148">输入</span><span class="sxs-lookup"><span data-stu-id="eaad6-148">INPUTS</span></span>

### <span data-ttu-id="eaad6-149">无</span><span class="sxs-lookup"><span data-stu-id="eaad6-149">None</span></span>
<span data-ttu-id="eaad6-150">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="eaad6-150">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="eaad6-151">输出</span><span class="sxs-lookup"><span data-stu-id="eaad6-151">OUTPUTS</span></span>

### <span data-ttu-id="eaad6-152">无</span><span class="sxs-lookup"><span data-stu-id="eaad6-152">None</span></span>
<span data-ttu-id="eaad6-153">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="eaad6-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="eaad6-154">注释</span><span class="sxs-lookup"><span data-stu-id="eaad6-154">NOTES</span></span>

* <span data-ttu-id="eaad6-155">不能回滚已提交的事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-155">You cannot roll back a transaction that has been committed.</span></span>

  <span data-ttu-id="eaad6-156">不能回滚活动事务之外的任何事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-156">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="eaad6-157">若要回滚其他独立事务，则必须先提交或回滚活动事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-157">To roll back a different, independent transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="eaad6-158">回滚事务将会终止该事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-158">Rolling back the transaction ends the transaction.</span></span>
<span data-ttu-id="eaad6-159">若要再次使用事务，则必须启动新事务。</span><span class="sxs-lookup"><span data-stu-id="eaad6-159">To use a transaction again, you must start a new transaction.</span></span>

## <span data-ttu-id="eaad6-160">相关链接</span><span class="sxs-lookup"><span data-stu-id="eaad6-160">RELATED LINKS</span></span>

[<span data-ttu-id="eaad6-161">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="eaad6-161">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="eaad6-162">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="eaad6-162">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="eaad6-163">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="eaad6-163">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="eaad6-164">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="eaad6-164">Use-Transaction</span></span>](Use-Transaction.md)
