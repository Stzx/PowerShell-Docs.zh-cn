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
# <span data-ttu-id="27f78-103">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="27f78-103">Get-Transaction</span></span>

## <span data-ttu-id="27f78-104">摘要</span><span class="sxs-lookup"><span data-stu-id="27f78-104">SYNOPSIS</span></span>
<span data-ttu-id="27f78-105">获取当前（活动）事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-105">Gets the current (active) transaction.</span></span>

## <span data-ttu-id="27f78-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27f78-106">SYNTAX</span></span>

```
Get-Transaction [<CommonParameters>]
```

## <span data-ttu-id="27f78-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27f78-107">DESCRIPTION</span></span>
<span data-ttu-id="27f78-108">**获取事务** cmdlet 获取表示会话中的当前事务的对象。</span><span class="sxs-lookup"><span data-stu-id="27f78-108">The **Get-Transaction** cmdlet gets an object that represents the current transaction in the session.</span></span>

<span data-ttu-id="27f78-109">此 cmdlet 从不返回多个对象，原因是同一时间只有一个事务处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="27f78-109">This cmdlet never returns more than one object, because only one transaction is active at a time.</span></span>
<span data-ttu-id="27f78-110">如果通过使用启动事务) 的独立参数来启动一个或多个独立的事务 (，则最近启动的事务处于活动状态，这是 **获取事务** 的事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-110">If you start one or more independent transactions (by using the Independent parameter of Start-Transaction), the most recently started transaction is active, and that is the transaction that **Get-Transaction** returns.</span></span>

<span data-ttu-id="27f78-111">当所有活动事务都已回滚或提交时，此 cmdlet 将显示会话中最近处于活动状态的事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-111">When all active transactions have either been rolled back or committed, this cmdlet shows the transaction that was most recently active in the session.</span></span>

<span data-ttu-id="27f78-112">此 cmdlet 是在 Windows PowerShell 中支持事务功能的一组 cmdlet 之一。</span><span class="sxs-lookup"><span data-stu-id="27f78-112">This cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="27f78-113">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="27f78-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="27f78-114">示例</span><span class="sxs-lookup"><span data-stu-id="27f78-114">EXAMPLES</span></span>

### <span data-ttu-id="27f78-115">示例1：获取当前事务</span><span class="sxs-lookup"><span data-stu-id="27f78-115">Example 1: Get the current transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="27f78-116">此命令使用 Get-Transaction cmdlet 来获取当前事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-116">This command uses the Get-Transaction cmdlet to get the current transaction.</span></span>

### <span data-ttu-id="27f78-117">示例2：显示 transaction 对象的属性和方法</span><span class="sxs-lookup"><span data-stu-id="27f78-117">Example 2: Show the properties and methods of the transaction object</span></span>

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

<span data-ttu-id="27f78-118">此命令使用 Get-Member cmdlet 来显示事务对象的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="27f78-118">This command uses the Get-Member cmdlet to show the properties and methods of the transaction object.</span></span>

### <span data-ttu-id="27f78-119">示例3：显示已回滚事务的属性值</span><span class="sxs-lookup"><span data-stu-id="27f78-119">Example 3: Show the property values of a rolled back transaction</span></span>

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

<span data-ttu-id="27f78-120">此命令显示已回滚事务的事务对象属性值。</span><span class="sxs-lookup"><span data-stu-id="27f78-120">This command shows the property values of a transaction object for a transaction that has been rolled back.</span></span>

### <span data-ttu-id="27f78-121">示例4：显示已提交事务的属性值</span><span class="sxs-lookup"><span data-stu-id="27f78-121">Example 4: Show the property values of a committed transaction</span></span>

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

<span data-ttu-id="27f78-122">此命令显示已提交事务的事务对象属性值。</span><span class="sxs-lookup"><span data-stu-id="27f78-122">This command shows the property values of a transaction object for a transaction that has been committed.</span></span>

### <span data-ttu-id="27f78-123">示例5：启动事务，而另一个事务正在进行</span><span class="sxs-lookup"><span data-stu-id="27f78-123">Example 5: Start a transaction while another is in progress</span></span>

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

<span data-ttu-id="27f78-124">此示例演示当一个事务正在运行时，启动另一个事务对事务对象的影响。</span><span class="sxs-lookup"><span data-stu-id="27f78-124">This example shows the effect on the transaction object of starting a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="27f78-125">通常，当运行事务的脚本包括函数或调用包含其他完整事务的脚本时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="27f78-125">Typically, this happens when a script that runs a transaction includes a function or calls a script that contains another complete transaction.</span></span>

<span data-ttu-id="27f78-126">除非第二个 **启动事务** 命令包含 *独立* 的参数，否则 **Start transaction** 不会创建新的事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-126">Unless the second **Start-Transaction** command includes the *Independent* parameter, **Start-Transaction** does not create a new transaction.</span></span>
<span data-ttu-id="27f78-127">它会将第二个订阅者添加到原始事务中。</span><span class="sxs-lookup"><span data-stu-id="27f78-127">Instead, it adds a second subscriber to the original transaction.</span></span>

<span data-ttu-id="27f78-128">第一个 **启动事务** 命令启动事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-128">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="27f78-129">带有 *UseTransaction* 参数的 New-Item 命令是事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="27f78-129">A New-Item command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="27f78-130">第二个 **开始事务** 命令将订阅服务器添加到事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-130">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="27f78-131">下一条 New-Item 命令也是该事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="27f78-131">The next New-Item command is also part of the transaction.</span></span>

<span data-ttu-id="27f78-132">第一个 **Get transaction** 命令显示多订阅服务器事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-132">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="27f78-133">请注意，订阅者计数为 2。</span><span class="sxs-lookup"><span data-stu-id="27f78-133">Notice that the subscriber count is 2.</span></span>

<span data-ttu-id="27f78-134">第一条 Complete-Transaction 命令不会提交事务，但它会将订阅者计数减少到 1。</span><span class="sxs-lookup"><span data-stu-id="27f78-134">The first Complete-Transaction command does not commit the transaction, but it reduces the subscriber count to 1.</span></span>

<span data-ttu-id="27f78-135">第二个 **完整事务** 命令提交事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-135">The second **Complete-Transaction** command commits the transaction.</span></span>

### <span data-ttu-id="27f78-136">示例6：启动独立事务，而另一个事务正在进行</span><span class="sxs-lookup"><span data-stu-id="27f78-136">Example 6: Start an independent transaction while another is in progress</span></span>

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

<span data-ttu-id="27f78-137">此示例演示当一个事务正在运行时，启动另一个独立事务对事务对象的影响。</span><span class="sxs-lookup"><span data-stu-id="27f78-137">This example shows the effect on the transaction object of starting an independent transaction while another transaction is in progress.</span></span>

<span data-ttu-id="27f78-138">第一个 **启动事务** 命令启动事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-138">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="27f78-139">带有 *UseTransaction* 参数的 **新项** 命令是事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="27f78-139">A **New-Item** command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="27f78-140">第二个 **开始事务** 命令将订阅服务器添加到事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-140">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="27f78-141">下一个 **新项** 命令也是该事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="27f78-141">The next **New-Item** command is also part of the transaction.</span></span>

<span data-ttu-id="27f78-142">第一个 **Get transaction** 命令显示多订阅服务器事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-142">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="27f78-143">请注意，订阅者计数为 2。</span><span class="sxs-lookup"><span data-stu-id="27f78-143">Note that the subscriber count is 2.</span></span>

<span data-ttu-id="27f78-144">**Complete Transaction** 命令将订阅服务器计数减少到1，但它不提交事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-144">The **Complete-Transaction** command reduces the subscriber count to 1, but it does not commit the transaction.</span></span>

<span data-ttu-id="27f78-145">第二个 **完整事务** 命令提交事务。</span><span class="sxs-lookup"><span data-stu-id="27f78-145">The second **Complete-Transaction** command commits the transaction.</span></span>

## <span data-ttu-id="27f78-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27f78-146">PARAMETERS</span></span>

### <span data-ttu-id="27f78-147">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27f78-147">CommonParameters</span></span>
<span data-ttu-id="27f78-148">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="27f78-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27f78-149">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="27f78-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27f78-150">输入</span><span class="sxs-lookup"><span data-stu-id="27f78-150">INPUTS</span></span>

### <span data-ttu-id="27f78-151">无</span><span class="sxs-lookup"><span data-stu-id="27f78-151">None</span></span>
<span data-ttu-id="27f78-152">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27f78-152">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="27f78-153">输出</span><span class="sxs-lookup"><span data-stu-id="27f78-153">OUTPUTS</span></span>

### <span data-ttu-id="27f78-154">System.Management.Automation.PSTransaction</span><span class="sxs-lookup"><span data-stu-id="27f78-154">System.Management.Automation.PSTransaction</span></span>
<span data-ttu-id="27f78-155">此 cmdlet 将返回一个表示当前事务的对象。</span><span class="sxs-lookup"><span data-stu-id="27f78-155">This cmdlet returns an object that represents the current transaction.</span></span>

## <span data-ttu-id="27f78-156">注释</span><span class="sxs-lookup"><span data-stu-id="27f78-156">NOTES</span></span>

## <span data-ttu-id="27f78-157">相关链接</span><span class="sxs-lookup"><span data-stu-id="27f78-157">RELATED LINKS</span></span>

[<span data-ttu-id="27f78-158">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="27f78-158">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="27f78-159">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="27f78-159">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="27f78-160">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="27f78-160">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="27f78-161">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="27f78-161">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="27f78-162">New-Item</span><span class="sxs-lookup"><span data-stu-id="27f78-162">New-Item</span></span>](New-Item.md)
