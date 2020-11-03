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
# <span data-ttu-id="de5d3-103">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="de5d3-103">Start-Transaction</span></span>

## <span data-ttu-id="de5d3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="de5d3-104">SYNOPSIS</span></span>
<span data-ttu-id="de5d3-105">启动事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-105">Starts a transaction.</span></span>

## <span data-ttu-id="de5d3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de5d3-106">SYNTAX</span></span>

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="de5d3-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de5d3-107">DESCRIPTION</span></span>
<span data-ttu-id="de5d3-108">**启动事务** cmdlet 启动事务，事务是作为一个单元进行管理的一系列命令。</span><span class="sxs-lookup"><span data-stu-id="de5d3-108">The **Start-Transaction** cmdlet starts a transaction, which is a series of commands that are managed as a unit.</span></span>
<span data-ttu-id="de5d3-109">可以完成或提交事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-109">A transaction can be completed, or committed.</span></span>
<span data-ttu-id="de5d3-110">另外，还可以完全撤消或回滚，以使事务更改的所有数据还原为其原始状态。</span><span class="sxs-lookup"><span data-stu-id="de5d3-110">Alternatively, it can be completely undone, or rolled back, so that any data changed by the transaction is restored to its original state.</span></span>
<span data-ttu-id="de5d3-111">由于事务中的命令作为一个单元进行管理，因此所有命令不是全部提交就是全部回滚。</span><span class="sxs-lookup"><span data-stu-id="de5d3-111">Because the commands in a transaction are managed as a unit, either all commands are committed or all commands are rolled back.</span></span>

<span data-ttu-id="de5d3-112">默认情况下，如果事务中的任何命令生成错误，将自动回滚事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-112">By default, if any command in the transaction generates an error, transactions are rolled back automatically.</span></span>
<span data-ttu-id="de5d3-113">可以使用 *RollbackPreference* 参数更改此行为。</span><span class="sxs-lookup"><span data-stu-id="de5d3-113">You can use the *RollbackPreference* parameter to change this behavior.</span></span>

<span data-ttu-id="de5d3-114">事务中使用的 cmdlet 必须设计为支持事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-114">The cmdlets used in a transaction must be designed to support transactions.</span></span>
<span data-ttu-id="de5d3-115">支持事务的 cmdlet 具有 *UseTransaction* 参数。</span><span class="sxs-lookup"><span data-stu-id="de5d3-115">Cmdlets that support transactions have a *UseTransaction* parameter.</span></span>
<span data-ttu-id="de5d3-116">若要通过提供程序执行事务，则该提供程序必须支持事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-116">To perform transactions in a provider, the provider must support transactions.</span></span>
<span data-ttu-id="de5d3-117">Windows Vista 和更高版本的 windows 操作系统中的 Windows PowerShell 注册表提供程序支持事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-117">The Windows PowerShell Registry provider in Windows Vista and later versions of the Windows operating system supports transactions.</span></span>
<span data-ttu-id="de5d3-118">你还可以使用 **TransactedString** 类在支持 windows PowerShell 的任意版本的 windows 系统上的事务中包含表达式。</span><span class="sxs-lookup"><span data-stu-id="de5d3-118">You can also use the **Microsoft.PowerShell.Commands.Management.TransactedString** class to include expressions in transactions on any version of the Windows system that supports Windows PowerShell.</span></span>
<span data-ttu-id="de5d3-119">其他 Windows PowerShell 提供程序也可以支持事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-119">Other Windows PowerShell providers can also support transactions.</span></span>

<span data-ttu-id="de5d3-120">一次只能有一个事务处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="de5d3-120">Only one transaction can be active at a time.</span></span>
<span data-ttu-id="de5d3-121">如果在事务正在进行的过程中启动一个新的独立事务，则新事务将成为活动事务，并且必须在对原始事务进行任何更改之前提交或回滚新事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-121">If you start a new, independent transaction while a transaction is in progress, the new transaction becomes the active transaction, and you must commit or roll back the new transaction before you make any changes to the original transaction.</span></span>

<span data-ttu-id="de5d3-122">**启动-Transaction** cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="de5d3-122">**Start-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="de5d3-123">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="de5d3-123">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="de5d3-124">示例</span><span class="sxs-lookup"><span data-stu-id="de5d3-124">EXAMPLES</span></span>

### <span data-ttu-id="de5d3-125">示例1：启动和回滚事务</span><span class="sxs-lookup"><span data-stu-id="de5d3-125">Example 1: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

<span data-ttu-id="de5d3-126">这些命令先启动事务，然后回滚事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-126">These commands start and then roll back a transaction.</span></span>
<span data-ttu-id="de5d3-127">由于回滚了事务，因此未对注册表进行更改。</span><span class="sxs-lookup"><span data-stu-id="de5d3-127">Because the transaction is rolled back, no changes are made to the registry.</span></span>

### <span data-ttu-id="de5d3-128">示例2：启动并完成事务</span><span class="sxs-lookup"><span data-stu-id="de5d3-128">Example 2: Start and complete a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="de5d3-129">这些命令先启动事务，然后完成事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-129">These commands start and then complete a transaction.</span></span>
<span data-ttu-id="de5d3-130">在使用 **完整事务** 命令之前，不会对注册表进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="de5d3-130">No changes are made to the registry until the **Complete-Transaction** command is used.</span></span>

### <span data-ttu-id="de5d3-131">示例3：使用不同的回滚首选项</span><span class="sxs-lookup"><span data-stu-id="de5d3-131">Example 3: Use different rollback preferences</span></span>

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

<span data-ttu-id="de5d3-132">此示例演示了更改 *RollbackPreference* 参数值的效果。</span><span class="sxs-lookup"><span data-stu-id="de5d3-132">This example demonstrates the effect of changing the *RollbackPreference* parameter value.</span></span>

<span data-ttu-id="de5d3-133">在第一组命令中， **Start-Transaction** 不使用 *RollbackPreference* 。</span><span class="sxs-lookup"><span data-stu-id="de5d3-133">In the first set of commands, **Start-Transaction** does not use *RollbackPreference* .</span></span>
<span data-ttu-id="de5d3-134">因此，会使用 (错误) 默认值。</span><span class="sxs-lookup"><span data-stu-id="de5d3-134">As a result, the default value (Error) is used.</span></span>
<span data-ttu-id="de5d3-135">当事务命令中发生错误（即，指定的路径不存在）时，将自动回滚该事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-135">When an error occurs in a transaction command, that is, the specified path does not exist, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="de5d3-136">在第二组命令中， **Start-Transaction** 使用值为 "Never" 的 *RollbackPreference* 。</span><span class="sxs-lookup"><span data-stu-id="de5d3-136">In the second set of commands, **Start-Transaction** uses *RollbackPreference* with a value of Never.</span></span>
<span data-ttu-id="de5d3-137">因此当事务命令发生错误时，事务仍处于活动状态并且可以成功完成。</span><span class="sxs-lookup"><span data-stu-id="de5d3-137">As a result, when an error occurs in a transaction command, the transaction is still active and can be completed successfully.</span></span>

<span data-ttu-id="de5d3-138">由于大多数事务都必须在没有错误的情况下执行，因此 *RollbackPreference* 的默认值通常是首选值。</span><span class="sxs-lookup"><span data-stu-id="de5d3-138">Because most transactions must be performed without error, the default value of *RollbackPreference* is typically preferred.</span></span>

### <span data-ttu-id="de5d3-139">示例4：在事务正在进行时使用此 cmdlet</span><span class="sxs-lookup"><span data-stu-id="de5d3-139">Example 4: Use this cmdlet while a transaction is in progress</span></span>

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

<span data-ttu-id="de5d3-140">此示例显示了在事务正在进行时使用 **启动事务** 的效果。</span><span class="sxs-lookup"><span data-stu-id="de5d3-140">This example shows the effect of using **Start-Transaction** while a transaction is in progress.</span></span>
<span data-ttu-id="de5d3-141">这与加入正在执行的事务的效果非常类似。</span><span class="sxs-lookup"><span data-stu-id="de5d3-141">The effect is much like joining the transaction in progress.</span></span>

<span data-ttu-id="de5d3-142">尽管这是一个简化的命令，但当事务涉及到运行包含完整事务的脚本时，通常会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="de5d3-142">Although this is a simplified command, this scenario frequently occurs when the transaction involves running a script that includes a complete transaction.</span></span>

<span data-ttu-id="de5d3-143">第一个 **启动事务** 命令启动事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-143">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="de5d3-144">第一个 **新项** 命令是事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="de5d3-144">The first **New-Item** command is part of the transaction.</span></span>

<span data-ttu-id="de5d3-145">第二个 **启动事务** 命令向事务中添加新的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="de5d3-145">The second **Start-Transaction** command adds a new subscriber to the transaction.</span></span>
<span data-ttu-id="de5d3-146">现在， **获取事务** 命令返回的事务的订户计数为2。</span><span class="sxs-lookup"><span data-stu-id="de5d3-146">The **Get-Transaction** command now returns a transaction with a subscriber count of 2.</span></span>
<span data-ttu-id="de5d3-147">第二个 **新项** 命令是同一事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="de5d3-147">The second **New-Item** command is part of the same transaction.</span></span>

<span data-ttu-id="de5d3-148">在整个事务完成之前，不会对注册表进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="de5d3-148">No changes are made to the registry until the whole transaction is completed.</span></span>
<span data-ttu-id="de5d3-149">若要完成事务，必须输入两个 **完整事务** 的命令，每个订阅服务器一个。</span><span class="sxs-lookup"><span data-stu-id="de5d3-149">To complete the transaction, you must enter two **Complete-Transaction** commands, one for each subscriber.</span></span>
<span data-ttu-id="de5d3-150">如果要回滚事务，则所有事务都将回滚到这两个订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="de5d3-150">If you were to roll back the transaction at any point, all the transaction would be rolled back for both subscribers.</span></span>

### <span data-ttu-id="de5d3-151">示例5：启动一个独立的事务，而另一个事务正在进行</span><span class="sxs-lookup"><span data-stu-id="de5d3-151">Example 5: Start an independent transaction while one is in progress</span></span>

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

<span data-ttu-id="de5d3-152">此示例显示了在另一个事务正在进行时使用 **启动事务** 的 *独立* 参数启动事务的效果。</span><span class="sxs-lookup"><span data-stu-id="de5d3-152">This example shows the effect of using the *Independent* parameter of **Start-Transaction** to start a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="de5d3-153">在本例中，将回滚新事务，而不影响原来的事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-153">In this case, the new transaction is rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="de5d3-154">虽然事务在逻辑上是独立的，但由于一次只能有一个事务处于活动状态，因此你必须回滚或提交最新事务，然后才能继续处理原来的事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-154">Although the transactions are logically independent, because only one transaction can be active at a time, you must roll back or commit the newest transaction before resuming work on the original transaction.</span></span>

<span data-ttu-id="de5d3-155">第一组命令启动一个事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-155">The first set of commands starts a transaction.</span></span>
<span data-ttu-id="de5d3-156">**新项** 命令是第一个事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="de5d3-156">The **New-Item** command is part of the first transaction.</span></span>

<span data-ttu-id="de5d3-157">在第二组命令中， **Start Transaction** 命令使用 *独立* 参数。</span><span class="sxs-lookup"><span data-stu-id="de5d3-157">In the second set of commands, the **Start-Transaction** command uses the *Independent* parameter.</span></span>
<span data-ttu-id="de5d3-158">下面的 **Get Transaction** 命令显示活动事务的事务对象，这是最新的事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-158">The **Get-Transaction** command that follows shows the transaction object for the active transaction, which is the newest one.</span></span>
<span data-ttu-id="de5d3-159">订阅者计数等于1，表明事务不相关。</span><span class="sxs-lookup"><span data-stu-id="de5d3-159">The subscriber count is equal to 1, that shows that the transactions are unrelated.</span></span>

<span data-ttu-id="de5d3-160">当使用 **Undo transaction** 命令回滚活动事务时，原来的事务将再次变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="de5d3-160">When the active transaction is rolled back by using an **Undo-Transaction** command, the original transaction becomes active again.</span></span>

<span data-ttu-id="de5d3-161">**Set-itemproperty** 命令（它是原始事务的一部分）完成时不会出错，并且可以通过使用 **Complete transaction** 命令完成原始事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-161">The **New-ItemProperty** command, which is part of the original transaction, finishes without error, and the original transaction can be completed by using the **Complete-Transaction** command.</span></span>
<span data-ttu-id="de5d3-162">因此注册表会发生更改。</span><span class="sxs-lookup"><span data-stu-id="de5d3-162">As a result, the registry is changed.</span></span>

### <span data-ttu-id="de5d3-163">示例6：运行不属于事务的命令</span><span class="sxs-lookup"><span data-stu-id="de5d3-163">Example 6: Run commands that are not part of a transaction</span></span>

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

<span data-ttu-id="de5d3-164">此示例演示了在事务正在执行时提交的命令可以包含在事务中，也可以不包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="de5d3-164">This example demonstrates that commands that are submitted while a transaction is in progress can be included in the transaction or not included.</span></span>
<span data-ttu-id="de5d3-165">只有使用 *UseTransaction* 参数的命令才包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="de5d3-165">Only commands that use the *UseTransaction* parameter are part of the transaction.</span></span>

<span data-ttu-id="de5d3-166">第一个和第三个 **新项** 命令使用 *UseTransaction* 参数。</span><span class="sxs-lookup"><span data-stu-id="de5d3-166">The first and third **New-Item** commands use the *UseTransaction* parameter.</span></span>
<span data-ttu-id="de5d3-167">这两个命令都包含在事务中。</span><span class="sxs-lookup"><span data-stu-id="de5d3-167">These commands are part of the transaction.</span></span>
<span data-ttu-id="de5d3-168">因为第二个 **新项** 命令不使用 *UseTransaction* 参数，所以它不是事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="de5d3-168">Because the second **New-Item** command does not use the *UseTransaction* parameter, it is not part of the transaction.</span></span>

<span data-ttu-id="de5d3-169">第一个 dir 命令显示了效果。</span><span class="sxs-lookup"><span data-stu-id="de5d3-169">The first dir command shows the effect.</span></span>
<span data-ttu-id="de5d3-170">第二个 **新项** 命令将立即完成，但在提交事务之前，第一个和第三个 **新的** 命令将不会生效。</span><span class="sxs-lookup"><span data-stu-id="de5d3-170">The second **New-Item** command is completed immediately, but the first and third **New-Item** commands are not effective until the transaction is committed.</span></span>

<span data-ttu-id="de5d3-171">**Complete transaction** 命令提交事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-171">The **Complete-Transaction** command commits the transaction.</span></span>
<span data-ttu-id="de5d3-172">因此，第二个 dir 命令显示已将所有新项添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="de5d3-172">As a result, the second dir command shows that all of the new items are added to the registry.</span></span>

### <span data-ttu-id="de5d3-173">示例7：回滚在指定时间内未完成的事务</span><span class="sxs-lookup"><span data-stu-id="de5d3-173">Example 7: Roll back a transaction that does not finish in a specified time</span></span>

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

<span data-ttu-id="de5d3-174">此命令使用 **Start transaction** 的 *Timeout* 参数启动必须在两分钟内完成的事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-174">This command uses the *Timeout* parameter of **Start-Transaction** to start a transaction that must be completed within two minutes.</span></span>
<span data-ttu-id="de5d3-175">如果在超时过期后事务未完成，则会自动回滚。</span><span class="sxs-lookup"><span data-stu-id="de5d3-175">If the transaction is not finished when the time-out expires, it is rolled back automatically.</span></span>

<span data-ttu-id="de5d3-176">当超时到期时，你不会收到通知，但事务对象的 **Status** 属性将设置为 RolledBack，并且使用 *UseTransaction* 参数的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="de5d3-176">When the time-out expires, you are not notified, but the **Status** property of the transaction object is set to RolledBack and commands that use the *UseTransaction* parameter fail.</span></span>

## <span data-ttu-id="de5d3-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de5d3-177">PARAMETERS</span></span>

### <span data-ttu-id="de5d3-178">-Independent</span><span class="sxs-lookup"><span data-stu-id="de5d3-178">-Independent</span></span>
<span data-ttu-id="de5d3-179">指示此 cmdlet 启动独立于正在进行的事务的事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-179">Indicates that this cmdlet starts a transaction that is independent of any transactions in progress.</span></span>
<span data-ttu-id="de5d3-180">默认情况下，如果在另一个事务正在进行时使用 **启动事务** ，则会向正在进行的事务中添加新的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="de5d3-180">By default, if you use **Start-Transaction** while another transaction is in progress, a new subscriber is added to the transaction in progress.</span></span>
<span data-ttu-id="de5d3-181">仅当会话中已经在执行某项事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="de5d3-181">This parameter has an effect only when a transaction is already in progress in the session.</span></span>

<span data-ttu-id="de5d3-182">默认情况下，如果在事务正在进行时使用 **Start transaction** ，将重用现有事务对象，并且订阅者计数将递增。</span><span class="sxs-lookup"><span data-stu-id="de5d3-182">By default, if you use **Start-Transaction** while a transaction is in progress, the existing transaction object is reused and the subscriber count is incremented.</span></span>
<span data-ttu-id="de5d3-183">这与加入原来事务的效果非常类似。</span><span class="sxs-lookup"><span data-stu-id="de5d3-183">The effect is much like joining the original transaction.</span></span>
<span data-ttu-id="de5d3-184">Undo-Transaction 命令将回滚整个事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-184">An Undo-Transaction command rolls back the whole the transaction.</span></span>
<span data-ttu-id="de5d3-185">若要完成事务，则必须为每个订阅者输入一个 Complete-Transaction 命令。</span><span class="sxs-lookup"><span data-stu-id="de5d3-185">To complete the transaction, you must enter a Complete-Transaction command for each subscriber.</span></span>
<span data-ttu-id="de5d3-186">因为同时执行的多数事务都是相关的，所以默认设置可满足大多数用途的要求。</span><span class="sxs-lookup"><span data-stu-id="de5d3-186">Because most transactions that are in progress at the same time are related, the default is sufficient for most uses.</span></span>

<span data-ttu-id="de5d3-187">如果指定 *独立* 参数，则此 cmdlet 会创建一个新事务，该事务可在不影响原始事务的情况下完成或撤消。</span><span class="sxs-lookup"><span data-stu-id="de5d3-187">If you specify the *Independent* parameter, this cmdlet creates a new transaction that can be completed or undone without affecting the original transaction.</span></span>
<span data-ttu-id="de5d3-188">但是，由于一次只能有一个事务处于活动状态，因此必须完成或回滚新事务，然后才能继续处理原来的事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-188">However, because only one transaction can be active at a time, you must complete or roll back the new transaction before resuming work on the original transaction.</span></span>

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

### <span data-ttu-id="de5d3-189">-RollbackPreference</span><span class="sxs-lookup"><span data-stu-id="de5d3-189">-RollbackPreference</span></span>
<span data-ttu-id="de5d3-190">指定自动回滚事务的条件。</span><span class="sxs-lookup"><span data-stu-id="de5d3-190">Specifies the conditions under which a transaction is automatically rolled back.</span></span>
<span data-ttu-id="de5d3-191">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="de5d3-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="de5d3-192">错误。</span><span class="sxs-lookup"><span data-stu-id="de5d3-192">Error.</span></span>
<span data-ttu-id="de5d3-193">当发生终止错误或非终止错误时，自动回滚事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-193">The transaction is rolled back automatically if a terminating or non-terminating error occurs.</span></span>
- <span data-ttu-id="de5d3-194">TerminatingError.</span><span class="sxs-lookup"><span data-stu-id="de5d3-194">TerminatingError.</span></span>
<span data-ttu-id="de5d3-195">当发生终止错误时，自动回滚事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-195">The transaction is rolled back automatically if a terminating error occurs.</span></span>
- <span data-ttu-id="de5d3-196">从不。</span><span class="sxs-lookup"><span data-stu-id="de5d3-196">Never.</span></span>
<span data-ttu-id="de5d3-197">从不自动回滚事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-197">The transaction is never rolled back automatically.</span></span>

<span data-ttu-id="de5d3-198">默认值为 "错误"。</span><span class="sxs-lookup"><span data-stu-id="de5d3-198">The default value is Error.</span></span>

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

### <span data-ttu-id="de5d3-199">-Timeout</span><span class="sxs-lookup"><span data-stu-id="de5d3-199">-Timeout</span></span>
<span data-ttu-id="de5d3-200">指定事务处于活动状态的最长时间，以分钟为单位。</span><span class="sxs-lookup"><span data-stu-id="de5d3-200">Specifies the maximum time, in minutes, that the transaction is active.</span></span>
<span data-ttu-id="de5d3-201">当该超时到期时，将自动回滚事务。</span><span class="sxs-lookup"><span data-stu-id="de5d3-201">When the time-out expires, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="de5d3-202">默认情况下，在命令行启动的事务没有超时值。</span><span class="sxs-lookup"><span data-stu-id="de5d3-202">By default, there is no time-out for transactions that are started at the command line.</span></span>
<span data-ttu-id="de5d3-203">如果事务由脚本启动，则默认超时值为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="de5d3-203">When transactions are started by a script, the default time-out is 30 minutes.</span></span>

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

### <span data-ttu-id="de5d3-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="de5d3-204">-Confirm</span></span>
<span data-ttu-id="de5d3-205">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="de5d3-205">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="de5d3-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="de5d3-206">-WhatIf</span></span>
<span data-ttu-id="de5d3-207">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="de5d3-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="de5d3-208">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="de5d3-208">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="de5d3-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="de5d3-209">CommonParameters</span></span>
<span data-ttu-id="de5d3-210">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="de5d3-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de5d3-211">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="de5d3-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de5d3-212">输入</span><span class="sxs-lookup"><span data-stu-id="de5d3-212">INPUTS</span></span>

### <span data-ttu-id="de5d3-213">无</span><span class="sxs-lookup"><span data-stu-id="de5d3-213">None</span></span>
<span data-ttu-id="de5d3-214">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de5d3-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="de5d3-215">输出</span><span class="sxs-lookup"><span data-stu-id="de5d3-215">OUTPUTS</span></span>

### <span data-ttu-id="de5d3-216">无</span><span class="sxs-lookup"><span data-stu-id="de5d3-216">None</span></span>
<span data-ttu-id="de5d3-217">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="de5d3-217">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="de5d3-218">注释</span><span class="sxs-lookup"><span data-stu-id="de5d3-218">NOTES</span></span>

## <span data-ttu-id="de5d3-219">相关链接</span><span class="sxs-lookup"><span data-stu-id="de5d3-219">RELATED LINKS</span></span>

[<span data-ttu-id="de5d3-220">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="de5d3-220">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="de5d3-221">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="de5d3-221">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="de5d3-222">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="de5d3-222">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="de5d3-223">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="de5d3-223">Use-Transaction</span></span>](Use-Transaction.md)
