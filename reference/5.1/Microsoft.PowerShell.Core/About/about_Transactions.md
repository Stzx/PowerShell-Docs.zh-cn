---
description: 介绍如何在 PowerShell 中管理事务处理操作。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200050"
---
# <a name="about-transactions"></a><span data-ttu-id="84959-104">关于事务</span><span class="sxs-lookup"><span data-stu-id="84959-104">About Transactions</span></span>

## <a name="short-description"></a><span data-ttu-id="84959-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="84959-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="84959-106">介绍如何在 PowerShell 中管理事务处理操作。</span><span class="sxs-lookup"><span data-stu-id="84959-106">Describes how to manage transacted operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="84959-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="84959-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="84959-108">从 PowerShell 2.0 开始，PowerShell 支持事务。</span><span class="sxs-lookup"><span data-stu-id="84959-108">Transactions are supported in PowerShell beginning in PowerShell 2.0.</span></span> <span data-ttu-id="84959-109">利用此功能，您可以启动事务，指示哪些命令是事务的一部分，以及提交或回滚事务。</span><span class="sxs-lookup"><span data-stu-id="84959-109">This feature enables you to start a transaction, to indicate which commands are part of the transaction, and to commit or roll back a transaction.</span></span>

## <a name="about-transactions"></a><span data-ttu-id="84959-110">关于事务</span><span class="sxs-lookup"><span data-stu-id="84959-110">ABOUT TRANSACTIONS</span></span>

<span data-ttu-id="84959-111">在 PowerShell 中，事务是作为一个逻辑单元进行管理的一个或多个命令的集合。</span><span class="sxs-lookup"><span data-stu-id="84959-111">In PowerShell, a transaction is a set of one or more commands that are managed as a logical unit.</span></span> <span data-ttu-id="84959-112">事务可以 ( "已提交" ) 完成，这将更改受事务影响的数据。</span><span class="sxs-lookup"><span data-stu-id="84959-112">A transaction can be completed ("committed"), which changes data affected by the transaction.</span></span> <span data-ttu-id="84959-113">或者，事务可以完全撤消 ( "回滚" ) 以便事务不更改受影响的数据。</span><span class="sxs-lookup"><span data-stu-id="84959-113">Or, a transaction can be completely undone ("rolled back") so that the affected data is not changed by the transaction.</span></span>

<span data-ttu-id="84959-114">由于事务中的命令作为一个单元进行管理，因此要么提交所有命令，要么回滚所有命令。</span><span class="sxs-lookup"><span data-stu-id="84959-114">Because the commands in a transaction are managed as a unit, either all commands are committed, or all commands are rolled back.</span></span>

<span data-ttu-id="84959-115">事务广泛用于数据处理，最值得注意的是数据库操作和财务交易。</span><span class="sxs-lookup"><span data-stu-id="84959-115">Transactions are widely used in data processing, most notably in database operations and for financial transactions.</span></span> <span data-ttu-id="84959-116">当一组命令的最坏情况下，事务不会失败，但某些命令在其他情况下会成功，而其他命令则会失败，使系统处于损坏、误报或 uninterpretable 状态，难于修复。</span><span class="sxs-lookup"><span data-stu-id="84959-116">Transactions are most often used when the worst-case scenario for a set of commands is not that they all fail, but that some commands succeed while others fail, leaving the system in a damaged, false, or uninterpretable state that is difficult to repair.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="84959-117">事务 CMDLET</span><span class="sxs-lookup"><span data-stu-id="84959-117">TRANSACTION CMDLETS</span></span>

<span data-ttu-id="84959-118">PowerShell 包含用于管理事务的多个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84959-118">PowerShell includes several cmdlets designed for managing transactions.</span></span>

- <span data-ttu-id="84959-119">Start-Transaction：启动新的事务。</span><span class="sxs-lookup"><span data-stu-id="84959-119">Start-Transaction: Starts a new transaction.</span></span>
- <span data-ttu-id="84959-120">使用事务：向事务中添加命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="84959-120">Use-Transaction: Adds a command or expression to the transaction.</span></span> <span data-ttu-id="84959-121">此命令必须使用启用事务的对象。</span><span class="sxs-lookup"><span data-stu-id="84959-121">The command must use transaction-enabled objects.</span></span>
- <span data-ttu-id="84959-122">Undo-Transaction：回滚事务，使事务不更改数据。</span><span class="sxs-lookup"><span data-stu-id="84959-122">Undo-Transaction: Rolls back the transaction so that no data is changed by the transaction.</span></span>
- <span data-ttu-id="84959-123">Complete-Transaction：提交事务。</span><span class="sxs-lookup"><span data-stu-id="84959-123">Complete-Transaction: Commits the transaction.</span></span> <span data-ttu-id="84959-124">更改受事务影响的数据。</span><span class="sxs-lookup"><span data-stu-id="84959-124">The data affected by the transaction is changed.</span></span>
- <span data-ttu-id="84959-125">获取事务：获取有关活动事务的信息。</span><span class="sxs-lookup"><span data-stu-id="84959-125">Get-Transaction: Gets information about the active transaction.</span></span>

<span data-ttu-id="84959-126">要获取事务 cmdlet 列表，请键入：</span><span class="sxs-lookup"><span data-stu-id="84959-126">For a list of transaction cmdlets, type:</span></span>

```powershell
get-command *transaction
```

<span data-ttu-id="84959-127">有关 cmdlet 的详细信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="84959-127">For detailed information about the cmdlets, type:</span></span>

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a><span data-ttu-id="84959-128">启用事务的元素</span><span class="sxs-lookup"><span data-stu-id="84959-128">TRANSACTION-ENABLED ELEMENTS</span></span>

<span data-ttu-id="84959-129">若要参与事务，cmdlet 和提供程序都必须支持事务。</span><span class="sxs-lookup"><span data-stu-id="84959-129">To participate in a transaction, both the cmdlet and the provider must support transactions.</span></span> <span data-ttu-id="84959-130">此功能内置于受事务影响的对象。</span><span class="sxs-lookup"><span data-stu-id="84959-130">This feature is built in to the objects that are affected by the transaction.</span></span>

<span data-ttu-id="84959-131">PowerShell 注册表提供程序在 Windows Vista 中支持事务。</span><span class="sxs-lookup"><span data-stu-id="84959-131">The PowerShell Registry provider supports transactions in Windows Vista.</span></span> <span data-ttu-id="84959-132">TransactedString 对象 (TransactedString) 可与运行 PowerShell 的任何操作系统配合使用。</span><span class="sxs-lookup"><span data-stu-id="84959-132">The TransactedString object (Microsoft.PowerShell.Commands.Management.TransactedString) works with any operating system that runs PowerShell.</span></span>

<span data-ttu-id="84959-133">其他 PowerShell 提供程序可以支持事务。</span><span class="sxs-lookup"><span data-stu-id="84959-133">Other PowerShell providers can support transactions.</span></span> <span data-ttu-id="84959-134">若要在会话中查找支持事务的 PowerShell 提供程序，请使用以下命令在提供程序的功能属性中查找 "事务" 值：</span><span class="sxs-lookup"><span data-stu-id="84959-134">To find the PowerShell providers in your session that support transactions, use the following command to find the "Transactions" value in the Capabilities property of providers:</span></span>

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

<span data-ttu-id="84959-135">有关提供程序的详细信息，请参阅提供程序的帮助。</span><span class="sxs-lookup"><span data-stu-id="84959-135">For more information about a provider, see the Help for the provider.</span></span> <span data-ttu-id="84959-136">若要获取提供程序帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="84959-136">To get provider Help, type:</span></span>

```
get-help <provider-name>
```

<span data-ttu-id="84959-137">例如，若要获取有关 Registry 提供程序的帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="84959-137">For example, to get Help for the Registry provider, type:</span></span>

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a><span data-ttu-id="84959-138">USETRANSACTION 参数</span><span class="sxs-lookup"><span data-stu-id="84959-138">THE USETRANSACTION PARAMETER</span></span>

<span data-ttu-id="84959-139">可支持事务的 cmdlet 具有 UseTransaction 参数。</span><span class="sxs-lookup"><span data-stu-id="84959-139">Cmdlets that can support transactions have a UseTransaction parameter.</span></span> <span data-ttu-id="84959-140">此参数将命令包含在活动事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-140">This parameter includes the command in the active transaction.</span></span> <span data-ttu-id="84959-141">您可以使用完整参数名或其别名 "usetx"。</span><span class="sxs-lookup"><span data-stu-id="84959-141">You can use the full parameter name or its alias, "usetx".</span></span>

<span data-ttu-id="84959-142">参数只能在会话包含活动事务时使用。</span><span class="sxs-lookup"><span data-stu-id="84959-142">The parameter can be used only when the session contains an active transaction.</span></span> <span data-ttu-id="84959-143">如果在没有活动事务时输入带有 UseTransaction 参数的命令，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="84959-143">If you enter a command with the UseTransaction parameter when there is no active transaction, the command fails.</span></span>

<span data-ttu-id="84959-144">若要查找具有 UseTransaction 参数的 cmdlet，请键入：</span><span class="sxs-lookup"><span data-stu-id="84959-144">To find cmdlets with the UseTransaction parameter, type:</span></span>

```powershell
get-help * -parameter UseTransaction
```

<span data-ttu-id="84959-145">在 PowerShell core 中，所有旨在使用 PowerShell 提供程序的 cmdlet 都支持事务。</span><span class="sxs-lookup"><span data-stu-id="84959-145">In PowerShell core, all of the cmdlets designed to work with PowerShell providers support transactions.</span></span> <span data-ttu-id="84959-146">因此，你可以使用提供程序 cmdlet 来管理事务。</span><span class="sxs-lookup"><span data-stu-id="84959-146">As a result, you can use the provider cmdlets to manage transactions.</span></span>

<span data-ttu-id="84959-147">有关 PowerShell 提供程序的详细信息，请参阅 [about_Providers](about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="84959-147">For more information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

## <a name="the-transaction-object"></a><span data-ttu-id="84959-148">TRANSACTION 对象</span><span class="sxs-lookup"><span data-stu-id="84959-148">THE TRANSACTION OBJECT</span></span>

<span data-ttu-id="84959-149">事务在 PowerShell 中通过事务对象的 System.object 表示。</span><span class="sxs-lookup"><span data-stu-id="84959-149">Transactions are represented in PowerShell by a transaction object, System.Management.Automation.Transaction.</span></span>

<span data-ttu-id="84959-150">该对象包含以下属性：</span><span class="sxs-lookup"><span data-stu-id="84959-150">The object has the following properties:</span></span>

- <span data-ttu-id="84959-151">RollbackPreference：包含当前事务的回滚首选项集。</span><span class="sxs-lookup"><span data-stu-id="84959-151">RollbackPreference: Contains the rollback preference set for the current transaction.</span></span> <span data-ttu-id="84959-152">您可以在使用 Start-Transaction 启动事务时设置 rollback 首选项。</span><span class="sxs-lookup"><span data-stu-id="84959-152">You can set the rollback preference when you use Start-Transaction to start the transaction.</span></span>

  <span data-ttu-id="84959-153">Rollback 首选项确定了自动回滚事务的条件。</span><span class="sxs-lookup"><span data-stu-id="84959-153">The rollback preference determines the conditions under which the transaction is rolled back automatically.</span></span> <span data-ttu-id="84959-154">有效值为 Error、TerminatingError 和 Never。</span><span class="sxs-lookup"><span data-stu-id="84959-154">Valid values are Error, TerminatingError, and Never.</span></span> <span data-ttu-id="84959-155">默认值为 "错误"。</span><span class="sxs-lookup"><span data-stu-id="84959-155">The default value is Error.</span></span>

- <span data-ttu-id="84959-156">Status：包含事务的当前状态。</span><span class="sxs-lookup"><span data-stu-id="84959-156">Status: Contains the current status of the transaction.</span></span> <span data-ttu-id="84959-157">有效值为 "活动"、"已提交" 和 "RolledBack"。</span><span class="sxs-lookup"><span data-stu-id="84959-157">Valid values are Active, Committed, and RolledBack.</span></span>

- <span data-ttu-id="84959-158">SubscriberCount：包含事务的订阅服务器的数目。</span><span class="sxs-lookup"><span data-stu-id="84959-158">SubscriberCount: Contains the number of subscribers to the transaction.</span></span> <span data-ttu-id="84959-159">当你在另一个事务正在进行时启动事务时，将向事务中添加一个订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="84959-159">A subscriber is added to a transaction when you start a transaction while another transaction is in progress.</span></span> <span data-ttu-id="84959-160">订阅服务器提交事务时，订阅服务器计数将减少。</span><span class="sxs-lookup"><span data-stu-id="84959-160">The subscriber count is decremented when a subscriber commits the transaction.</span></span>

## <a name="active-transactions"></a><span data-ttu-id="84959-161">活动事务</span><span class="sxs-lookup"><span data-stu-id="84959-161">ACTIVE TRANSACTIONS</span></span>

<span data-ttu-id="84959-162">在 PowerShell 中，一次只能有一个事务处于活动状态，并且只能管理活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-162">In PowerShell, only one transaction is active at a time, and you can manage only the active transaction.</span></span> <span data-ttu-id="84959-163">同一会话中可能正在进行多个事务，但只有最新启动的事务处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="84959-163">Multiple transactions can be in progress in the same session at the same time, but only the most-recently started transaction is active.</span></span>

<span data-ttu-id="84959-164">因此，在使用事务 cmdlet 时，不能指定特定的事务。</span><span class="sxs-lookup"><span data-stu-id="84959-164">As a result, you cannot specify a particular transaction when using the transaction cmdlets.</span></span> <span data-ttu-id="84959-165">命令始终应用于活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-165">Commands always apply to the active transaction.</span></span>

<span data-ttu-id="84959-166">在 Get-Transaction cmdlet 的行为中，这是最明显的。</span><span class="sxs-lookup"><span data-stu-id="84959-166">This is most evident in the behavior of the Get-Transaction cmdlet.</span></span> <span data-ttu-id="84959-167">输入 Get-Transaction 命令时，Get-Transaction 始终只获取一个 transaction 对象。</span><span class="sxs-lookup"><span data-stu-id="84959-167">When you enter a Get-Transaction command, Get-Transaction always gets only one transaction object.</span></span> <span data-ttu-id="84959-168">此对象是表示活动事务的对象。</span><span class="sxs-lookup"><span data-stu-id="84959-168">This object is the object that represents the active transaction.</span></span>

<span data-ttu-id="84959-169">若要管理不同的事务，必须先通过提交或回滚活动事务来完成该事务。</span><span class="sxs-lookup"><span data-stu-id="84959-169">To manage a different transaction, you must first finish the active transaction, either by committing it or rolling it back.</span></span> <span data-ttu-id="84959-170">执行此操作时，前一个事务会自动变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="84959-170">When you do this, the previous transaction becomes active automatically.</span></span> <span data-ttu-id="84959-171">事务会按照它们的启动顺序处于活动状态，因此，最新启动的事务始终处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="84959-171">Transactions become active in the reverse of order of which they are started, so that the most recently started transaction is always active.</span></span>

## <a name="subscribers-and-independent-transactions"></a><span data-ttu-id="84959-172">订阅服务器和独立事务</span><span class="sxs-lookup"><span data-stu-id="84959-172">SUBSCRIBERS AND INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="84959-173">如果在另一个事务正在进行时启动事务，则默认情况下，PowerShell 不会启动新的事务。</span><span class="sxs-lookup"><span data-stu-id="84959-173">If you start a transaction while another transaction is in progress, by default, PowerShell does not start a new transaction.</span></span> <span data-ttu-id="84959-174">相反，它会将 "订阅服务器" 添加到当前事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-174">Instead, it adds a "subscriber" to the current transaction.</span></span>

<span data-ttu-id="84959-175">当某个事务有多个订阅服务器时，在任何时候都有单个 Undo-Transaction 命令将回滚所有订阅服务器的整个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-175">When a transaction has multiple subscribers, a single Undo-Transaction command at any point rolls back the entire transaction for all subscribers.</span></span> <span data-ttu-id="84959-176">但是，若要提交事务，你必须为每个订阅服务器输入 Complete-Transaction 命令。</span><span class="sxs-lookup"><span data-stu-id="84959-176">However, to commit the transaction, you must enter a Complete-Transaction command for every subscriber.</span></span>

<span data-ttu-id="84959-177">若要查找事务的订阅服务器数，请检查 transaction 对象的 SubscriberCount 属性。</span><span class="sxs-lookup"><span data-stu-id="84959-177">To find the number of subscribers to a transaction, check the SubscriberCount property of the transaction object.</span></span> <span data-ttu-id="84959-178">例如，以下命令使用 Get-Transaction cmdlet 获取活动事务的 SubscriberCount 属性的值：</span><span class="sxs-lookup"><span data-stu-id="84959-178">For example, the following command uses the Get-Transaction cmdlet to get the value of the SubscriberCount property of the active transaction:</span></span>

```powershell
(Get-Transaction).SubscriberCount
```

<span data-ttu-id="84959-179">添加订阅服务器是默认行为，因为当另一个事务正在进行时，大多数已启动的事务与原始事务相关。</span><span class="sxs-lookup"><span data-stu-id="84959-179">Adding a subscriber is the default behavior because most transactions that are started while another transaction is in progress are related to the original transaction.</span></span> <span data-ttu-id="84959-180">在典型模型中，包含事务的脚本将调用包含其自己的事务的帮助器脚本。</span><span class="sxs-lookup"><span data-stu-id="84959-180">In the typical model, a script that contains a transaction calls a helper script that contains its own transaction.</span></span> <span data-ttu-id="84959-181">由于事务是相关的，因此应将它们回滚或作为一个单元提交。</span><span class="sxs-lookup"><span data-stu-id="84959-181">Because the transactions are related, they should be rolled back or committed as a unit.</span></span>

<span data-ttu-id="84959-182">但是，可以使用 Start-Transaction cmdlet 的独立参数启动与当前事务无关的事务。</span><span class="sxs-lookup"><span data-stu-id="84959-182">However, you can start a transaction that is independent of the current transaction by using the Independent parameter of the Start-Transaction cmdlet.</span></span>

<span data-ttu-id="84959-183">启动独立事务时，Start-Transaction 会创建一个新的 transaction 对象，而新事务将成为活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-183">When you start an independent transaction, Start-Transaction creates a new transaction object, and the new transaction becomes the active transaction.</span></span>
<span data-ttu-id="84959-184">独立事务可以提交或回滚，而不会影响原始事务。</span><span class="sxs-lookup"><span data-stu-id="84959-184">The independent transaction can be committed or rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="84959-185">当独立事务 (提交或回滚) 时，原来的事务将再次成为活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-185">When the independent transaction is finished (committed or rolled back), the original transaction becomes the active transaction again.</span></span>

## <a name="changing-data"></a><span data-ttu-id="84959-186">更改数据</span><span class="sxs-lookup"><span data-stu-id="84959-186">CHANGING DATA</span></span>

<span data-ttu-id="84959-187">当使用事务更改数据时，在提交事务之前，不会更改事务影响的数据。</span><span class="sxs-lookup"><span data-stu-id="84959-187">When you use transactions to change data, the data that is affected by the transaction is not changed until you commit the transaction.</span></span> <span data-ttu-id="84959-188">但是，不属于事务的命令可以更改相同的数据。</span><span class="sxs-lookup"><span data-stu-id="84959-188">However, the same data can be changed by commands that are not part of the transaction.</span></span>

<span data-ttu-id="84959-189">使用事务来管理共享数据时，请记住这一点。</span><span class="sxs-lookup"><span data-stu-id="84959-189">Keep this in mind when you are using transactions to manage shared data.</span></span>
<span data-ttu-id="84959-190">通常，数据库具有在处理数据时锁定数据的机制，阻止其他用户以及其他命令、脚本和函数更改。</span><span class="sxs-lookup"><span data-stu-id="84959-190">Typically, databases have mechanisms that lock the data while you are working on it, preventing other users, and other commands, scripts, and functions, from changing it.</span></span>

<span data-ttu-id="84959-191">但是，该锁是数据库的一项功能。</span><span class="sxs-lookup"><span data-stu-id="84959-191">However, the lock is a feature of the database.</span></span> <span data-ttu-id="84959-192">它与事务无关。</span><span class="sxs-lookup"><span data-stu-id="84959-192">It is not related to transactions.</span></span> <span data-ttu-id="84959-193">如果正在启用事务的文件系统或其他数据存储中工作，则可以在事务进行过程中更改数据。</span><span class="sxs-lookup"><span data-stu-id="84959-193">If you are working in a transaction-enabled file system or other data store, the data can be changed while the transaction is in progress.</span></span>

## <a name="examples"></a><span data-ttu-id="84959-194">示例</span><span class="sxs-lookup"><span data-stu-id="84959-194">EXAMPLES</span></span>

<span data-ttu-id="84959-195">本部分中的示例使用 PowerShell 注册表提供程序，并假定你熟悉它。</span><span class="sxs-lookup"><span data-stu-id="84959-195">The examples in this section use the PowerShell Registry provider and assume that you are familiar with it.</span></span> <span data-ttu-id="84959-196">有关注册表提供程序的信息，请键入 "get-help Registry"。</span><span class="sxs-lookup"><span data-stu-id="84959-196">For information about the Registry provider, type "get-help registry".</span></span>

### <a name="example-1-committing-a-transaction"></a><span data-ttu-id="84959-197">示例1：提交事务</span><span class="sxs-lookup"><span data-stu-id="84959-197">EXAMPLE 1: COMMITTING A TRANSACTION</span></span>

<span data-ttu-id="84959-198">若要创建事务，请使用 Start-Transaction cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84959-198">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="84959-199">以下命令使用默认设置启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-199">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-200">若要在事务中包含命令，请使用 cmdlet 的 UseTransaction 参数。</span><span class="sxs-lookup"><span data-stu-id="84959-200">To include commands in the transaction, use the UseTransaction parameter of the cmdlet.</span></span> <span data-ttu-id="84959-201">默认情况下，不会将命令包含在事务中，</span><span class="sxs-lookup"><span data-stu-id="84959-201">By default, commands are not included in the transaction,</span></span>

<span data-ttu-id="84959-202">例如，以下命令（用于设置 HKCU：驱动器的软件密钥中的当前位置）不包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-202">For example, the following command, which sets the current location in the Software key of the HKCU: drive, is not included in the transaction.</span></span>

```powershell
cd hkcu:\Software
```

<span data-ttu-id="84959-203">以下用于创建 MyCompany 密钥的命令使用 New-Item cmdlet 的 UseTransaction 参数将该命令包含在活动事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-203">The following command, which creates the MyCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="84959-204">命令返回一个表示新键的对象，但由于该命令是事务的一部分，因此注册表尚未更改。</span><span class="sxs-lookup"><span data-stu-id="84959-204">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

<span data-ttu-id="84959-205">若要提交事务，请使用 Complete-Transaction cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84959-205">To commit the transaction, use the Complete-Transaction cmdlet.</span></span> <span data-ttu-id="84959-206">由于它始终影响活动事务，因此不能指定事务。</span><span class="sxs-lookup"><span data-stu-id="84959-206">Because it always affects the active transaction, you cannot specify the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="84959-207">因此，会将 MyCompany 项添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="84959-207">As a result, the MyCompany key is added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a><span data-ttu-id="84959-208">示例2：回滚事务</span><span class="sxs-lookup"><span data-stu-id="84959-208">EXAMPLE 2: ROLLING BACK A TRANSACTION</span></span>

<span data-ttu-id="84959-209">若要创建事务，请使用 Start-Transaction cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84959-209">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="84959-210">以下命令使用默认设置启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-210">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-211">以下用于创建 MyOtherCompany 密钥的命令使用 New-Item cmdlet 的 UseTransaction 参数将该命令包含在活动事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-211">The following command, which creates the MyOtherCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -UseTransaction
```

<span data-ttu-id="84959-212">命令返回一个表示新键的对象，但由于该命令是事务的一部分，因此注册表尚未更改。</span><span class="sxs-lookup"><span data-stu-id="84959-212">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

<span data-ttu-id="84959-213">若要回滚事务，请使用 Undo-Transaction cmdlet。</span><span class="sxs-lookup"><span data-stu-id="84959-213">To roll back the transaction, use the Undo-Transaction cmdlet.</span></span> <span data-ttu-id="84959-214">由于它始终影响活动事务，因此您不能指定事务。</span><span class="sxs-lookup"><span data-stu-id="84959-214">Because it always affects the active transaction, you do not specify the transaction.</span></span>

```powershell
Undo-transaction
```

<span data-ttu-id="84959-215">结果是不会将 MyOtherCompany 键添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="84959-215">The result is that the MyOtherCompany key is not added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a><span data-ttu-id="84959-216">示例3：预览事务</span><span class="sxs-lookup"><span data-stu-id="84959-216">EXAMPLE 3: PREVIEWING A TRANSACTION</span></span>

<span data-ttu-id="84959-217">通常，在事务中使用的命令将更改数据。</span><span class="sxs-lookup"><span data-stu-id="84959-217">Typically, the commands used in a transaction change data.</span></span> <span data-ttu-id="84959-218">但是，获取数据的命令也会在事务中使用，因为它们会在事务中获取数据。</span><span class="sxs-lookup"><span data-stu-id="84959-218">However, the commands that get data are useful in a transaction, too, because they get data inside of the transaction.</span></span> <span data-ttu-id="84959-219">这会提供提交事务的更改的预览。</span><span class="sxs-lookup"><span data-stu-id="84959-219">This provides a preview of the changes that committing the transaction would cause.</span></span>

<span data-ttu-id="84959-220">下面的示例演示如何使用 Get-ChildItem 命令 (别名为 "dir" ) 预览事务中的更改。</span><span class="sxs-lookup"><span data-stu-id="84959-220">The following example shows how to use the Get-ChildItem command (the alias is "dir") to preview the changes in a transaction.</span></span>

<span data-ttu-id="84959-221">下面的命令启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-221">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-222">以下命令使用 New-ItemProperty cmdlet 将 MyKey 注册表条目添加到 MyCompany 项。</span><span class="sxs-lookup"><span data-stu-id="84959-222">The following command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="84959-223">该命令使用 UseTransaction 参数将命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-223">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

<span data-ttu-id="84959-224">该命令将返回一个表示新注册表项的对象，但不会更改注册表项。</span><span class="sxs-lookup"><span data-stu-id="84959-224">The command returns an object representing the new registry entry, but the registry entry is not changed.</span></span>

```
MyKey
-----
123
```

<span data-ttu-id="84959-225">若要获取注册表中的当前项，请使用 Get-ChildItem 命令 ( "dir" ) ，而不使用 UseTransaction 参数。</span><span class="sxs-lookup"><span data-stu-id="84959-225">To get the items that are currently in the registry, use a Get-ChildItem command ("dir") without the UseTransaction parameter.</span></span> <span data-ttu-id="84959-226">以下命令将获取以 "M" 开头的项。</span><span class="sxs-lookup"><span data-stu-id="84959-226">The following command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="84959-227">结果显示尚未将任何条目添加到 MyCompany 项。</span><span class="sxs-lookup"><span data-stu-id="84959-227">The result shows that no entries have yet been added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

<span data-ttu-id="84959-228">若要预览提交事务的效果，请使用 UseTransaction 参数输入 Get-ChildItem ( "dir" ) 命令。</span><span class="sxs-lookup"><span data-stu-id="84959-228">To preview the effect of committing the transaction, enter a Get-ChildItem ("dir") command with the UseTransaction parameter.</span></span> <span data-ttu-id="84959-229">此命令从事务内查看数据。</span><span class="sxs-lookup"><span data-stu-id="84959-229">This command has a view of the data from within the transaction.</span></span>

```powershell
dir m* -useTransaction
```

<span data-ttu-id="84959-230">结果显示，如果提交事务，MyKey 条目将添加到 MyCompany 键。</span><span class="sxs-lookup"><span data-stu-id="84959-230">The result shows that, if the transaction is committed, the MyKey entry will be added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a><span data-ttu-id="84959-231">示例4：合并事务和非事务处理命令</span><span class="sxs-lookup"><span data-stu-id="84959-231">EXAMPLE 4: COMBINING TRANSACTED AND NON-TRANSACTED COMMANDS</span></span>

<span data-ttu-id="84959-232">可以在事务中输入非事务性命令。</span><span class="sxs-lookup"><span data-stu-id="84959-232">You can enter non-transacted commands during a transaction.</span></span> <span data-ttu-id="84959-233">非事务性命令会立即影响数据，但不会影响事务。</span><span class="sxs-lookup"><span data-stu-id="84959-233">The non-transacted commands affect the data immediately, but they do not affect the transaction.</span></span>
<span data-ttu-id="84959-234">以下命令在 HKCU： \ Software 注册表项中启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-234">The following command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-235">接下来的三个命令使用 New-Item cmdlet 向注册表中添加项。</span><span class="sxs-lookup"><span data-stu-id="84959-235">The next three commands use the New-Item cmdlet to add keys to the registry.</span></span>
<span data-ttu-id="84959-236">第一条和第三条命令使用 UseTransaction 参数将命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-236">The first and third commands use the UseTransaction parameter to include the commands in the transaction.</span></span> <span data-ttu-id="84959-237">第二个命令省略了该参数。</span><span class="sxs-lookup"><span data-stu-id="84959-237">The second command omits the parameter.</span></span> <span data-ttu-id="84959-238">由于第二个命令未包含在事务中，因此它会立即生效。</span><span class="sxs-lookup"><span data-stu-id="84959-238">Because the second command is not included in the transaction, it is effective immediately.</span></span>

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

<span data-ttu-id="84959-239">若要查看注册表的当前状态，请使用不带 UseTransaction 参数的 Get-ChildItem ( "dir" ) 命令。</span><span class="sxs-lookup"><span data-stu-id="84959-239">To view the current state of the registry, use a Get-ChildItem ("dir") command without the UseTransaction parameter.</span></span> <span data-ttu-id="84959-240">此命令获取以 "M" 开头的项。</span><span class="sxs-lookup"><span data-stu-id="84959-240">This command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="84959-241">结果显示，MyCompany2 项已添加到注册表中，但不会添加 MyCompany1 和 MyCompany3 键，这是事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="84959-241">The result shows that the MyCompany2 key is added to the registry, but the MyCompany1 and MyCompany3 keys, which are part of the transaction, are not added.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

<span data-ttu-id="84959-242">以下命令将提交事务。</span><span class="sxs-lookup"><span data-stu-id="84959-242">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="84959-243">现在，作为事务一部分添加的密钥显示在注册表中。</span><span class="sxs-lookup"><span data-stu-id="84959-243">Now, the keys that were added as part of the transaction appear in the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a><span data-ttu-id="84959-244">示例5：使用自动回滚</span><span class="sxs-lookup"><span data-stu-id="84959-244">EXAMPLE 5: USING AUTOMATIC ROLLBACK</span></span>

<span data-ttu-id="84959-245">当事务中的命令生成任意类型的错误时，将自动回滚该事务。</span><span class="sxs-lookup"><span data-stu-id="84959-245">When a command in a transaction generates an error of any kind, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="84959-246">此默认行为是针对运行事务的脚本而设计的。</span><span class="sxs-lookup"><span data-stu-id="84959-246">This default behavior is designed for scripts that run transactions.</span></span> <span data-ttu-id="84959-247">脚本通常经过良好的测试并包含错误处理逻辑，因此错误不是预期的，应终止事务。</span><span class="sxs-lookup"><span data-stu-id="84959-247">Scripts are typically well tested and include error-handling logic, so errors are not expected and should terminate the transaction.</span></span>

<span data-ttu-id="84959-248">第一个命令在 HKCU： \ Software 注册表项中启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-248">The first command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-249">以下命令使用 New-Item cmdlet 将 MyCompany 项添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="84959-249">The following command uses the New-Item cmdlet to add the MyCompany key to the registry.</span></span> <span data-ttu-id="84959-250">该命令使用 UseTransaction 参数 (别名为 "usetx" ) ，以将命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-250">The command uses the UseTransaction parameter (the alias is "usetx") to include the command in the transaction.</span></span>

```powershell
New-Item MyCompany -UseTX
```

<span data-ttu-id="84959-251">由于注册表中已经存在 MyCompany 项，因此该命令将失败，并且将回滚该事务。</span><span class="sxs-lookup"><span data-stu-id="84959-251">Because the MyCompany key already exists in the registry, the command fails, and the transaction is rolled back.</span></span>

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="84959-252">Get-Transaction 命令确认事务已回滚并且 SubscriberCount 为0。</span><span class="sxs-lookup"><span data-stu-id="84959-252">A Get-Transaction command confirms that the transaction has been rolled back and that the SubscriberCount is 0.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a><span data-ttu-id="84959-253">示例6：更改 ROLLBACK 首选项</span><span class="sxs-lookup"><span data-stu-id="84959-253">EXAMPLE 6: CHANGING THE ROLLBACK PREFERENCE</span></span>

<span data-ttu-id="84959-254">如果希望事务更容错，可以使用 Start-Transaction 的 RollbackPreference 参数来更改首选项。</span><span class="sxs-lookup"><span data-stu-id="84959-254">If you want the transaction to be more error tolerant, you can use the RollbackPreference parameter of Start-Transaction to change the preference.</span></span>

<span data-ttu-id="84959-255">下面的命令启动一个事务，该事务的 rollback 首选项为 "Never"。</span><span class="sxs-lookup"><span data-stu-id="84959-255">The following command starts a transaction with a rollback preference of "Never".</span></span>

```powershell
start-transaction -rollbackpreference Never
```

<span data-ttu-id="84959-256">在这种情况下，当命令失败时，不会自动回滚事务。</span><span class="sxs-lookup"><span data-stu-id="84959-256">In this case, when the command fails, the transaction is not automatically rolled back.</span></span>

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="84959-257">由于事务仍处于活动状态，因此你可以在事务中重新提交此命令。</span><span class="sxs-lookup"><span data-stu-id="84959-257">Because the transaction is still active, you can resubmit the command as part of the transaction.</span></span>

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a><span data-ttu-id="84959-258">示例7：使用使用事务 CMDLET</span><span class="sxs-lookup"><span data-stu-id="84959-258">EXAMPLE 7: USING THE USE-TRANSACTION CMDLET</span></span>

<span data-ttu-id="84959-259">Use-Transaction cmdlet 可让你针对启用事务的 Microsoft .NET 框架对象执行直接脚本编写。</span><span class="sxs-lookup"><span data-stu-id="84959-259">The Use-Transaction cmdlet enables you to do direct scripting against transaction-enabled Microsoft .NET Framework objects.</span></span> <span data-ttu-id="84959-260">Use-Transaction 采用一个脚本块，该脚本块只能包含使用启用事务的 .NET Framework 对象（如 TransactedString 类的实例）的命令和表达式。</span><span class="sxs-lookup"><span data-stu-id="84959-260">Use-Transaction takes a script block that can only contain commands and expressions that use transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="84959-261">下面的命令启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-261">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-262">下面的 New-Object 命令创建 TransactedString 类的一个实例，并将其保存在 $t 变量中。</span><span class="sxs-lookup"><span data-stu-id="84959-262">The following New-Object command creates an instance of the TransactedString class and saves it in the $t variable.</span></span>

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

<span data-ttu-id="84959-263">下面的命令使用 TransactedString 对象的 Append 方法将文本添加到字符串。</span><span class="sxs-lookup"><span data-stu-id="84959-263">The following command uses the Append method of the TransactedString object to add text to the string.</span></span> <span data-ttu-id="84959-264">由于该命令不是事务的一部分，因此更改将立即生效。</span><span class="sxs-lookup"><span data-stu-id="84959-264">Because the command is not part of the transaction, the change is effective immediately.</span></span>

```powershell
$t.append("Windows")
```

<span data-ttu-id="84959-265">以下命令使用相同的 Append 方法来添加文本，但会将文本添加为事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="84959-265">The following command uses the same Append method to add text, but it adds the text as part of the transaction.</span></span> <span data-ttu-id="84959-266">命令括在大括号内，并将其设置为使用事务的 ScriptBlock 参数的值。</span><span class="sxs-lookup"><span data-stu-id="84959-266">The command is enclosed in braces, and it is set as the value of the ScriptBlock parameter of Use-Transaction.</span></span> <span data-ttu-id="84959-267">需要 UseTransaction 参数 (UseTx) 。</span><span class="sxs-lookup"><span data-stu-id="84959-267">The UseTransaction parameter (UseTx) is required.</span></span>

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

<span data-ttu-id="84959-268">若要查看 $t 中的事务处理字符串的当前内容，请使用 TransactedString 对象的 ToString 方法。</span><span class="sxs-lookup"><span data-stu-id="84959-268">To see the current content of the transacted string in $t, use the ToString method of the TransactedString object.</span></span>

```powershell
$t.tostring()
```

<span data-ttu-id="84959-269">输出显示只有非事务性更改才有效。</span><span class="sxs-lookup"><span data-stu-id="84959-269">The output shows that only the non-transacted changes are effective.</span></span>

```output
Windows
```

<span data-ttu-id="84959-270">若要查看事务内 $t 中的事务处理字符串的当前内容，请在 Use-Transaction 命令中嵌入表达式。</span><span class="sxs-lookup"><span data-stu-id="84959-270">To see the current content of the transacted string in $t from within the transaction, embed the expression in a Use-Transaction command.</span></span>

```powershell
use-transaction {$s.tostring()} -usetx
```

<span data-ttu-id="84959-271">输出显示事务视图。</span><span class="sxs-lookup"><span data-stu-id="84959-271">The output shows the transaction view.</span></span>

```output
PowerShell
```

<span data-ttu-id="84959-272">以下命令将提交事务。</span><span class="sxs-lookup"><span data-stu-id="84959-272">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="84959-273">若要查看最终字符串：</span><span class="sxs-lookup"><span data-stu-id="84959-273">To see the final string:</span></span>

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a><span data-ttu-id="84959-274">示例8：管理多订户事务</span><span class="sxs-lookup"><span data-stu-id="84959-274">EXAMPLE 8: MANAGING MULTI-SUBSCRIBER TRANSACTIONS</span></span>

<span data-ttu-id="84959-275">当在另一个事务正在进行时启动事务时，默认情况下，PowerShell 不会创建第二个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-275">When you start a transaction while another transaction is in progress, PowerShell does not create a second transaction by default.</span></span> <span data-ttu-id="84959-276">相反，它会将订阅者添加到当前事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-276">Instead, it adds a subscriber to the current transaction.</span></span>

<span data-ttu-id="84959-277">此示例演示如何查看和管理多订户事务。</span><span class="sxs-lookup"><span data-stu-id="84959-277">This example shows how to view and manage a multi-subscriber transaction.</span></span>

<span data-ttu-id="84959-278">首先，在 HKCU： \ Software 密钥中启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-278">Begin by starting a transaction in the HKCU:\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-279">以下命令使用 Get-Transaction 命令获取活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-279">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="84959-280">结果显示表示活动事务的对象。</span><span class="sxs-lookup"><span data-stu-id="84959-280">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="84959-281">以下命令将 MyCompany 键添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="84959-281">The following command adds the MyCompany key to the registry.</span></span> <span data-ttu-id="84959-282">该命令使用 UseTransaction 参数将命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-282">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="84959-283">以下命令使用 Start-Transaction 命令启动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-283">The following command uses the Start-Transaction command to start a transaction.</span></span> <span data-ttu-id="84959-284">尽管此命令在命令提示符下键入，但当你运行包含事务的脚本时，可能会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="84959-284">Although this command is typed at the command prompt, this scenario is more likely to happen when you run a script that contains a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-285">Get-Transaction 的命令显示，事务对象上的订阅服务器计数是递增的。</span><span class="sxs-lookup"><span data-stu-id="84959-285">A Get-Transaction command shows that the subscriber count on the transaction object is incremented.</span></span> <span data-ttu-id="84959-286">值现在为2。</span><span class="sxs-lookup"><span data-stu-id="84959-286">The value is now 2.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="84959-287">下一个命令使用 New-ItemProperty cmdlet 将 MyKey 注册表条目添加到 MyCompany 项。</span><span class="sxs-lookup"><span data-stu-id="84959-287">The next command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="84959-288">它使用 UseTransaction 参数将命令包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-288">It uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

<span data-ttu-id="84959-289">注册表中不存在 MyCompany 项，但此命令成功，因为这两个命令是同一事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="84959-289">The MyCompany key does not exist in the registry, but this command succeeds because the two commands are part of the same transaction.</span></span>

<span data-ttu-id="84959-290">以下命令将提交事务。</span><span class="sxs-lookup"><span data-stu-id="84959-290">The following command commits the transaction.</span></span> <span data-ttu-id="84959-291">如果回滚事务，则会为所有订阅服务器回滚该事务。</span><span class="sxs-lookup"><span data-stu-id="84959-291">If it rolled back the transaction, the transaction would be rolled back for all the subscribers.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="84959-292">Get-Transaction 命令显示事务对象上的订阅服务器计数为1，但状态的值仍处于活动状态， (未提交的) 。</span><span class="sxs-lookup"><span data-stu-id="84959-292">A Get-Transaction command shows that the subscriber count on the transaction object is 1, but the value of Status is still Active (not Committed).</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="84959-293">若要完成事务提交，请输入第二个完整事务命令。</span><span class="sxs-lookup"><span data-stu-id="84959-293">To finish committing the transaction, enter a second Complete- Transaction command.</span></span> <span data-ttu-id="84959-294">若要提交多订户事务，你必须为每个 Start-Transaction 命令输入一个 Complete-Transaction 命令。</span><span class="sxs-lookup"><span data-stu-id="84959-294">To commit a multi-subscriber transaction, you must enter one Complete-Transaction command for each Start-Transaction command.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="84959-295">另一个 Get-Transaction 命令显示事务已提交。</span><span class="sxs-lookup"><span data-stu-id="84959-295">Another Get-Transaction command shows that the transaction has been committed.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a><span data-ttu-id="84959-296">示例9：管理独立事务</span><span class="sxs-lookup"><span data-stu-id="84959-296">EXAMPLE 9: MANAGING INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="84959-297">当在另一个事务正在进行时启动事务时，可以使用 Start-Transaction 的独立参数，使新事务独立于原始事务。</span><span class="sxs-lookup"><span data-stu-id="84959-297">When you start a transaction while another transaction is in progress, you can use the Independent parameter of Start-Transaction to make the new transaction independent of the original transaction.</span></span>

<span data-ttu-id="84959-298">执行此操作时，Start-Transaction 会创建一个新的 transaction 对象，并使新事务成为活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-298">When you do, Start-Transaction creates a new transaction object and makes the new transaction the active transaction.</span></span>

<span data-ttu-id="84959-299">首先，在 HKCU： Software 密钥中启动一个事务 \\ 。</span><span class="sxs-lookup"><span data-stu-id="84959-299">Begin by starting a transaction in the HKCU:\\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="84959-300">以下命令使用 Get-Transaction 命令获取活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-300">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="84959-301">结果显示表示活动事务的对象。</span><span class="sxs-lookup"><span data-stu-id="84959-301">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="84959-302">以下命令将 MyCompany 注册表项作为事务的一部分添加。</span><span class="sxs-lookup"><span data-stu-id="84959-302">The following command adds the MyCompany registry key as part of the transaction.</span></span> <span data-ttu-id="84959-303">它使用 UseTransaction 参数 (UseTx) 将命令包含在活动事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-303">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -use
```

<span data-ttu-id="84959-304">以下命令将启动新事务。</span><span class="sxs-lookup"><span data-stu-id="84959-304">The following command starts a new transaction.</span></span> <span data-ttu-id="84959-305">该命令使用独立参数指示此事务不是活动事务的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="84959-305">The command uses the Independent parameter to indicate that this transaction is not a subscriber to the active transaction.</span></span>

```powershell
start-transaction -independent
```

<span data-ttu-id="84959-306">创建独立事务时，最近创建的新 () 事务将成为活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-306">When you create an independent transaction, the new (most-recently created) transaction becomes the active transaction.</span></span> <span data-ttu-id="84959-307">您可以使用 Get-Transaction 命令获取活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-307">You can use a Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="84959-308">请注意，事务的 SubscriberCount 为1，表示没有其他订阅服务器，并且该事务是新的。</span><span class="sxs-lookup"><span data-stu-id="84959-308">Note that the SubscriberCount of the transaction is 1, indicating that there are no other subscribers and that the transaction is new.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="84959-309">必须先提交或回滚) 新事务，然后才能管理原始事务 (。</span><span class="sxs-lookup"><span data-stu-id="84959-309">The new transaction must be finished (either committed or rolled back) before you can manage the original transaction.</span></span>

<span data-ttu-id="84959-310">以下命令将 MyOtherCompany 键添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="84959-310">The following command adds the MyOtherCompany key to the registry.</span></span> <span data-ttu-id="84959-311">它使用 UseTransaction 参数 (UseTx) 将命令包含在活动事务中。</span><span class="sxs-lookup"><span data-stu-id="84959-311">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -usetx
```

<span data-ttu-id="84959-312">现在，回滚事务。</span><span class="sxs-lookup"><span data-stu-id="84959-312">Now, roll back the transaction.</span></span> <span data-ttu-id="84959-313">如果有两个订阅服务器的单个事务，回滚事务会回滚所有订阅服务器的整个事务。</span><span class="sxs-lookup"><span data-stu-id="84959-313">If there were a single transaction with two subscribers, rolling back the transaction would roll back the entire transaction for all the subscribers.</span></span>

<span data-ttu-id="84959-314">但是，因为这些事务是独立的，所以回滚最新的事务会取消注册表更改，并使原始事务成为活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-314">However, because these transactions are independent, rolling back the newest transaction cancels the registry changes and makes the original transaction the active transaction.</span></span>

```powershell
undo-transaction
```

<span data-ttu-id="84959-315">Get-Transaction 命令确认原始事务在会话中是否仍处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="84959-315">A Get-Transaction command confirms that the original transaction is still active in the session.</span></span>

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="84959-316">以下命令将提交活动事务。</span><span class="sxs-lookup"><span data-stu-id="84959-316">The following command commits the active transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="84959-317">Get-ChildItem 命令显示注册表已更改。</span><span class="sxs-lookup"><span data-stu-id="84959-317">A Get-ChildItem command shows that the registry has been changed.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a><span data-ttu-id="84959-318">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84959-318">SEE ALSO</span></span>

[<span data-ttu-id="84959-319">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="84959-319">Start-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Start-Transaction)

[<span data-ttu-id="84959-320">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="84959-320">Get-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Get-Transaction)

[<span data-ttu-id="84959-321">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="84959-321">Complete-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[<span data-ttu-id="84959-322">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="84959-322">Undo-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[<span data-ttu-id="84959-323">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="84959-323">Use-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Use-Transaction)

[<span data-ttu-id="84959-324">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="84959-324">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[<span data-ttu-id="84959-325">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="84959-325">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[<span data-ttu-id="84959-326">about_Providers</span><span class="sxs-lookup"><span data-stu-id="84959-326">about_Providers</span></span>](about_Providers.md)
