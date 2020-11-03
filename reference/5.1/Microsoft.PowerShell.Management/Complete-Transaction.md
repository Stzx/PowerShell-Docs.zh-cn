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
# <span data-ttu-id="20194-103">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="20194-103">Complete-Transaction</span></span>

## <span data-ttu-id="20194-104">摘要</span><span class="sxs-lookup"><span data-stu-id="20194-104">SYNOPSIS</span></span>
<span data-ttu-id="20194-105">提交活动事务。</span><span class="sxs-lookup"><span data-stu-id="20194-105">Commits the active transaction.</span></span>

## <span data-ttu-id="20194-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20194-106">SYNTAX</span></span>

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="20194-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20194-107">DESCRIPTION</span></span>
<span data-ttu-id="20194-108">**完整事务** cmdlet 将提交活动事务。</span><span class="sxs-lookup"><span data-stu-id="20194-108">The **Complete-Transaction** cmdlet commits an active transaction.</span></span>
<span data-ttu-id="20194-109">在提交事务时，该事务中的命令将完成，并且受这些命令影响的数据将发生更改。</span><span class="sxs-lookup"><span data-stu-id="20194-109">When you commit a transaction, the commands in the transaction are finalized and the data affected by the commands is changed.</span></span>

<span data-ttu-id="20194-110">如果事务包含多个订阅服务器，若要提交事务，则必须为每个 Start-Transaction 命令输入一个 **完整的 transaction** 命令。</span><span class="sxs-lookup"><span data-stu-id="20194-110">If the transaction includes multiple subscribers, to commit the transaction, you must enter one **Complete-Transaction** command for every Start-Transaction command.</span></span>

<span data-ttu-id="20194-111">**完整事务** cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="20194-111">The **Complete-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="20194-112">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="20194-112">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="20194-113">示例</span><span class="sxs-lookup"><span data-stu-id="20194-113">EXAMPLES</span></span>

### <span data-ttu-id="20194-114">示例1：提交事务</span><span class="sxs-lookup"><span data-stu-id="20194-114">Example 1: Commit a transaction</span></span>

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

<span data-ttu-id="20194-115">此示例显示了使用 **完整事务** cmdlet 提交事务时将发生的情况。</span><span class="sxs-lookup"><span data-stu-id="20194-115">This example shows what happens when you use the **Complete-Transaction** cmdlet to commit a transaction.</span></span>

<span data-ttu-id="20194-116">**Start transaction** 命令启动事务。</span><span class="sxs-lookup"><span data-stu-id="20194-116">The **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="20194-117">New-Item 命令使用 *UseTransaction* 参数将命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="20194-117">The New-Item command uses the *UseTransaction* parameter to include the command in the transaction.</span></span>

<span data-ttu-id="20194-118">第一个目录 (Get-childitem) 命令显示尚未将新项添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="20194-118">The first dir (Get-ChildItem) command shows that the new item has not yet been added to the registry.</span></span>

<span data-ttu-id="20194-119">**Complete transaction** 命令提交事务，这会使注册表更改生效。</span><span class="sxs-lookup"><span data-stu-id="20194-119">The **Complete-Transaction** command commits the transaction, which makes the registry change effective.</span></span>
<span data-ttu-id="20194-120">因此，第二个 dir 命令显示注册表已更改。</span><span class="sxs-lookup"><span data-stu-id="20194-120">As a result, the second dir command shows that the registry is changed.</span></span>

### <span data-ttu-id="20194-121">示例2：提交具有多个订阅服务器的事务</span><span class="sxs-lookup"><span data-stu-id="20194-121">Example 2: Commit a transaction that has more than one subscriber</span></span>

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

<span data-ttu-id="20194-122">此示例演示如何使用 **完整事务** 来提交具有多个订阅服务器的事务。</span><span class="sxs-lookup"><span data-stu-id="20194-122">This example shows how to use **Complete-Transaction** to commit a transaction that has more than one subscriber.</span></span>

<span data-ttu-id="20194-123">若要提交多订户事务，你必须为每个 **开始事务** 命令输入一个 **完整的事务** 命令。</span><span class="sxs-lookup"><span data-stu-id="20194-123">To commit a multi-subscriber transaction, you must enter one **Complete-Transaction** command for every **Start-Transaction** command.</span></span>
<span data-ttu-id="20194-124">仅当提交最后一个 **完整事务** 命令时，才会更改数据。</span><span class="sxs-lookup"><span data-stu-id="20194-124">The data is changed only when the final **Complete-Transaction** command is submitted.</span></span>

<span data-ttu-id="20194-125">出于演示目的，此示例演示了一系列在命令行中输入的命令。</span><span class="sxs-lookup"><span data-stu-id="20194-125">For demonstration purposes, this example shows a series of commands entered at the command line.</span></span>
<span data-ttu-id="20194-126">实际上，事务很可能在脚本中运行，其中二级事务由主脚本调用的函数或助手脚本运行。</span><span class="sxs-lookup"><span data-stu-id="20194-126">In practice, transactions are likely to be run in scripts, with the secondary transaction being run by a function or helper script that is called by the main script.</span></span>

<span data-ttu-id="20194-127">在此示例中， **启动事务** 命令启动事务。</span><span class="sxs-lookup"><span data-stu-id="20194-127">In this example, a **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="20194-128">带有 *UseTransaction* 参数的 **新项** 命令会将 MyCompany 项添加到软件密钥中。</span><span class="sxs-lookup"><span data-stu-id="20194-128">A **New-Item** command with the *UseTransaction* parameter adds the MyCompany key to the Software key.</span></span>
<span data-ttu-id="20194-129">尽管 **新项** cmdlet 返回密钥对象，但注册表中的数据尚未更改。</span><span class="sxs-lookup"><span data-stu-id="20194-129">Although the **New-Item** cmdlet returns a key object, the data in the registry is not yet changed.</span></span>

<span data-ttu-id="20194-130">第二个 **启动事务** 命令向现有事务中添加另一个订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="20194-130">A second **Start-Transaction** command adds a second subscriber to the existing transaction.</span></span>
<span data-ttu-id="20194-131">**获取事务** cmdlet 可确认订阅者计数为2。</span><span class="sxs-lookup"><span data-stu-id="20194-131">The **Get-Transaction** cmdlet confirms that the subscriber count is 2.</span></span>
<span data-ttu-id="20194-132">带有 *UseTransaction* 参数的 New-ItemProperty 命令将一个注册表项添加到新的 MyCompany 项。</span><span class="sxs-lookup"><span data-stu-id="20194-132">A New-ItemProperty command with the *UseTransaction* parameter adds a registry entry to the new MyCompany key.</span></span>
<span data-ttu-id="20194-133">该命令再次返回一个值，但注册表未发生更改。</span><span class="sxs-lookup"><span data-stu-id="20194-133">Again, the command returns a value, but the registry is not changed.</span></span>

<span data-ttu-id="20194-134">第一个 **完整事务** 命令将订阅服务器计数减少1。</span><span class="sxs-lookup"><span data-stu-id="20194-134">The first **Complete-Transaction** command reduces the subscriber count by 1.</span></span>
<span data-ttu-id="20194-135">此方法由 **获取事务** 命令确认。</span><span class="sxs-lookup"><span data-stu-id="20194-135">This is confirmed by a **Get-Transaction** command.</span></span>
<span data-ttu-id="20194-136">不过，出现不会更改任何数据，因为 dir m \* ( **get-childitem** ) 命令。</span><span class="sxs-lookup"><span data-stu-id="20194-136">However, no data is changed, as evidenced by a dir m\* ( **Get-ChildItem** ) command.</span></span>

<span data-ttu-id="20194-137">第二个 **完整事务** 命令将提交整个事务并更改注册表中的数据。</span><span class="sxs-lookup"><span data-stu-id="20194-137">The second **Complete-Transaction** command commits the entire transaction and changes the data in the registry.</span></span>
<span data-ttu-id="20194-138">这通过第二个 dir m \* 命令来确认，该命令显示了所做的更改。</span><span class="sxs-lookup"><span data-stu-id="20194-138">This is confirmed by a second dir m\* command, which shows the changes.</span></span>

### <span data-ttu-id="20194-139">示例3：执行不更改任何数据的事务</span><span class="sxs-lookup"><span data-stu-id="20194-139">Example 3: Perform a transaction that does not change any data</span></span>

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

<span data-ttu-id="20194-140">此示例演示在事务中使用 Get-\* 命令以及不会更改数据的其他命令的值。</span><span class="sxs-lookup"><span data-stu-id="20194-140">This example shows the value of using Get-\* commands, and other commands that do not change data, in a transaction.</span></span>
<span data-ttu-id="20194-141">在事务中使用 Get-\* 命令时，它将获取属于该事务的对象。</span><span class="sxs-lookup"><span data-stu-id="20194-141">When a Get-\* command is used in a transaction, it gets the objects that are part of the transaction.</span></span>
<span data-ttu-id="20194-142">这样，在提交更改之前，可以预览事务中的更改。</span><span class="sxs-lookup"><span data-stu-id="20194-142">This allows you to preview the changes in the transaction before the changes are committed.</span></span>

<span data-ttu-id="20194-143">在此示例中，将启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="20194-143">In this example, a transaction is started.</span></span>
<span data-ttu-id="20194-144">带有 *UseTransaction* 参数的 New-Item 命令将新项作为事务的一部分添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="20194-144">A New-Item command with the *UseTransaction* parameter adds a new key to the registry as part of the transaction.</span></span>

<span data-ttu-id="20194-145">由于在运行 **Complete Transaction** 命令之前不会将新的注册表项添加到注册表中，因此一个简单的目录 ( **get-childitem** ) 命令显示不带新密钥的注册表。</span><span class="sxs-lookup"><span data-stu-id="20194-145">Because the new registry key is not added to the registry until the **Complete-Transaction** command is run, a simple dir ( **Get-ChildItem** ) command shows the registry without the new key.</span></span>

<span data-ttu-id="20194-146">但是，将 *UseTransaction* 参数添加到 dir 命令后，该命令将成为事务的一部分，并且即使尚未将这些项添加到数据中，它也会获取事务中的项。</span><span class="sxs-lookup"><span data-stu-id="20194-146">However, when you add the *UseTransaction* parameter to the dir command, the command becomes part of the transaction, and it gets the items in the transaction even if they are not yet added to the data.</span></span>

## <span data-ttu-id="20194-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20194-147">PARAMETERS</span></span>

### <span data-ttu-id="20194-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="20194-148">-Confirm</span></span>
<span data-ttu-id="20194-149">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="20194-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="20194-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="20194-150">-WhatIf</span></span>
<span data-ttu-id="20194-151">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="20194-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="20194-152">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="20194-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="20194-153">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20194-153">CommonParameters</span></span>
<span data-ttu-id="20194-154">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="20194-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20194-155">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="20194-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20194-156">输入</span><span class="sxs-lookup"><span data-stu-id="20194-156">INPUTS</span></span>

### <span data-ttu-id="20194-157">无</span><span class="sxs-lookup"><span data-stu-id="20194-157">None</span></span>
<span data-ttu-id="20194-158">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20194-158">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="20194-159">输出</span><span class="sxs-lookup"><span data-stu-id="20194-159">OUTPUTS</span></span>

### <span data-ttu-id="20194-160">无</span><span class="sxs-lookup"><span data-stu-id="20194-160">None</span></span>
<span data-ttu-id="20194-161">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="20194-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="20194-162">注释</span><span class="sxs-lookup"><span data-stu-id="20194-162">NOTES</span></span>

* <span data-ttu-id="20194-163">无法回滚已提交的事务，或提交已回滚的事务。</span><span class="sxs-lookup"><span data-stu-id="20194-163">You cannot roll back a transaction that has been committed, or commit a transaction that has been rolled back.</span></span>

  <span data-ttu-id="20194-164">不能回滚活动事务之外的任何事务。</span><span class="sxs-lookup"><span data-stu-id="20194-164">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="20194-165">若要回滚其他事务，必须首先提交或回滚活动事务。</span><span class="sxs-lookup"><span data-stu-id="20194-165">To roll back a different transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="20194-166">默认情况下，如果无法提交事务的任何部分（例如，当事务中的某个命令产生错误时），则将回滚整个事务。</span><span class="sxs-lookup"><span data-stu-id="20194-166">By default, if any part of a transaction cannot be committed, such as when a command in the transaction results in an error, the entire transaction is rolled back.</span></span>

*

## <span data-ttu-id="20194-167">相关链接</span><span class="sxs-lookup"><span data-stu-id="20194-167">RELATED LINKS</span></span>

[<span data-ttu-id="20194-168">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="20194-168">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="20194-169">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="20194-169">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="20194-170">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="20194-170">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="20194-171">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="20194-171">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="20194-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="20194-172">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="20194-173">New-Item</span><span class="sxs-lookup"><span data-stu-id="20194-173">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="20194-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="20194-174">New-ItemProperty</span></span>](New-ItemProperty.md)
