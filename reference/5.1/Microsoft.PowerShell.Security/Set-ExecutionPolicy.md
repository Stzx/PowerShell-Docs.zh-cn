---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: 313ff4f2d3fc89263cdf4d0ede860ef8e538a2ea
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197981"
---
# <span data-ttu-id="5a86b-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="5a86b-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="5a86b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="5a86b-104">SYNOPSIS</span></span>
<span data-ttu-id="5a86b-105">设置 Windows 计算机的 PowerShell 执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="5a86b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5a86b-106">SYNTAX</span></span>

### <span data-ttu-id="5a86b-107">全部</span><span class="sxs-lookup"><span data-stu-id="5a86b-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="5a86b-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="5a86b-108">DESCRIPTION</span></span>

<span data-ttu-id="5a86b-109">`Set-ExecutionPolicy`Cmdlet 更改 Windows 计算机的 PowerShell 执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="5a86b-110">有关详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5a86b-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="5a86b-111">执行策略是 PowerShell 安全策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="5a86b-111">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="5a86b-112">执行策略确定你是否可以加载配置文件（如 PowerShell 配置文件）或运行脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-112">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="5a86b-113">并且，在运行脚本之前是否必须对其进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="5a86b-113">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="5a86b-114">此 `Set-ExecutionPolicy` cmdlet 的默认作用域为 **LocalMachine** ，这会影响使用该计算机的每个人。</span><span class="sxs-lookup"><span data-stu-id="5a86b-114">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="5a86b-115">若要更改 **LocalMachine** 的执行策略，请以 **管理员身份运行** 启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a86b-115">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator** .</span></span>

<span data-ttu-id="5a86b-116">若要按优先级顺序显示每个作用域的执行策略，请使用 `Get-ExecutionPolicy -List` 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-116">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="5a86b-117">若要查看 PowerShell 会话的有效执行策略，请使用 `Get-ExecutionPolicy` 不带参数的。</span><span class="sxs-lookup"><span data-stu-id="5a86b-117">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="5a86b-118">示例</span><span class="sxs-lookup"><span data-stu-id="5a86b-118">EXAMPLES</span></span>

### <span data-ttu-id="5a86b-119">示例1：设置执行策略</span><span class="sxs-lookup"><span data-stu-id="5a86b-119">Example 1: Set an execution policy</span></span>

<span data-ttu-id="5a86b-120">此示例演示如何设置本地计算机的执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-120">This example shows how to set the execution policy for the local computer.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="5a86b-121">`Set-ExecutionPolicy`Cmdlet 使用 **set-executionpolicy** 参数指定 **RemoteSigned** 策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-121">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="5a86b-122">**Scope** 参数指定默认作用域值 " **LocalMachine** "。</span><span class="sxs-lookup"><span data-stu-id="5a86b-122">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="5a86b-123">若要查看执行策略设置，请将 `Get-ExecutionPolicy` cmdlet 与 **List** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="5a86b-123">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="5a86b-124">示例2：设置与组策略冲突的执行策略</span><span class="sxs-lookup"><span data-stu-id="5a86b-124">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="5a86b-125">此命令尝试将 **LocalMachine** 作用域的执行策略设置为 " **受限** "。</span><span class="sxs-lookup"><span data-stu-id="5a86b-125">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted** .</span></span>
<span data-ttu-id="5a86b-126">**LocalMachine** 的限制更强，但并不是有效的策略，因为它与组策略冲突。</span><span class="sxs-lookup"><span data-stu-id="5a86b-126">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="5a86b-127">**受限制** 的策略会写入到 **HKEY_LOCAL_MACHINE** 的注册表配置单元。</span><span class="sxs-lookup"><span data-stu-id="5a86b-127">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

<span data-ttu-id="5a86b-128">`Set-ExecutionPolicy`Cmdlet 使用 **set-executionpolicy** 参数指定 **受限制** 的策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-128">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="5a86b-129">**Scope** 参数指定默认作用域值 " **LocalMachine** "。</span><span class="sxs-lookup"><span data-stu-id="5a86b-129">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span>
<span data-ttu-id="5a86b-130">`Get-ChildItem`Cmdlet 将 **Path** 参数与 **HKLM** 提供程序一起使用，以指定注册表位置。</span><span class="sxs-lookup"><span data-stu-id="5a86b-130">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="5a86b-131">示例3：将远程计算机上的执行策略应用于本地计算机</span><span class="sxs-lookup"><span data-stu-id="5a86b-131">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="5a86b-132">此命令获取远程计算机上的执行策略对象并在本地计算机上设置策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-132">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="5a86b-133">`Get-ExecutionPolicy` 沿管道向下发送 **Microsoft.PowerShell.ExecutionPolicy** 对象。</span><span class="sxs-lookup"><span data-stu-id="5a86b-133">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="5a86b-134">`Set-ExecutionPolicy` 接受管道输入，而不需要 **set-executionpolicy** 参数。</span><span class="sxs-lookup"><span data-stu-id="5a86b-134">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="5a86b-135">`Invoke-Command`Cmdlet 在本地计算机上执行，并将 **ScriptBlock** 发送到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="5a86b-135">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="5a86b-136">**ComputerName** 参数指定远程计算机 **Server01** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-136">The **ComputerName** parameter specifies the remote computer, **Server01** .</span></span> <span data-ttu-id="5a86b-137">**ScriptBlock** 参数 `Get-ExecutionPolicy` 在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="5a86b-137">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="5a86b-138">将 `Get-ExecutionPolicy` 对象向下发送到 `Set-ExecutionPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-138">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="5a86b-139">`Set-ExecutionPolicy` 将执行策略应用于本地计算机的默认作用域 " **LocalMachine** "。</span><span class="sxs-lookup"><span data-stu-id="5a86b-139">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine** .</span></span>

### <span data-ttu-id="5a86b-140">示例4：设置执行策略的作用域</span><span class="sxs-lookup"><span data-stu-id="5a86b-140">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="5a86b-141">此示例演示如何为指定的作用域 " **CurrentUser** " 设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-141">This example shows how to set an execution policy for a specified scope, **CurrentUser** .</span></span> <span data-ttu-id="5a86b-142">**CurrentUser** 范围仅影响设置此作用域的用户。</span><span class="sxs-lookup"><span data-stu-id="5a86b-142">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="5a86b-143">`Set-ExecutionPolicy` 使用 **set-executionpolicy** 参数指定 **AllSigned** 策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-143">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="5a86b-144">**Scope** 参数指定 **CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-144">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="5a86b-145">若要查看执行策略设置，请将 `Get-ExecutionPolicy` cmdlet 与 **List** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="5a86b-145">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="5a86b-146">用户的有效执行策略将变为 " **AllSigned** "。</span><span class="sxs-lookup"><span data-stu-id="5a86b-146">The effective execution policy for the user becomes **AllSigned** .</span></span>

### <span data-ttu-id="5a86b-147">示例5：删除当前用户的执行策略</span><span class="sxs-lookup"><span data-stu-id="5a86b-147">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="5a86b-148">此示例演示如何使用 **未定义** 执行策略删除指定作用域的执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-148">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

<span data-ttu-id="5a86b-149">`Set-ExecutionPolicy` 使用 **set-executionpolicy** 参数指定 **未定义** 的策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-149">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="5a86b-150">**Scope** 参数指定 **CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-150">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="5a86b-151">若要查看执行策略设置，请将 `Get-ExecutionPolicy` cmdlet 与 **List** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="5a86b-151">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="5a86b-152">示例6：设置当前 PowerShell 会话的执行策略</span><span class="sxs-lookup"><span data-stu-id="5a86b-152">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="5a86b-153">**进程** 范围仅影响当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="5a86b-153">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="5a86b-154">执行策略保存在环境变量中 `$env:PSExecutionPolicyPreference` ，并在会话关闭时删除。</span><span class="sxs-lookup"><span data-stu-id="5a86b-154">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="5a86b-155">`Set-ExecutionPolicy`使用 **set-executionpolicy** 参数来指定 **AllSigned** 策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-155">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="5a86b-156">**Scope** 参数指定值 **进程** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-156">The **Scope** parameter specifies the value **Process** .</span></span> <span data-ttu-id="5a86b-157">若要查看执行策略设置，请将 `Get-ExecutionPolicy` cmdlet 与 **List** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="5a86b-157">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="5a86b-158">示例7：取消阻止脚本，以便在不更改执行策略的情况下运行该脚本</span><span class="sxs-lookup"><span data-stu-id="5a86b-158">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="5a86b-159">此示例演示 **RemoteSigned** 执行策略如何阻止你运行未签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-159">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="5a86b-160">最佳做法是读取脚本的代码，并在使用 cmdlet **之前** 验证它是否安全 `Unblock-File` 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-160">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="5a86b-161">`Unblock-File`Cmdlet 取消阻止脚本，以便它们可以运行，但不会更改执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-161">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

<span data-ttu-id="5a86b-162">`Set-ExecutionPolicy`使用 **set-executionpolicy** 参数来指定 **RemoteSigned** 策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-162">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="5a86b-163">策略设置为默认作用域 " **LocalMachine** "。</span><span class="sxs-lookup"><span data-stu-id="5a86b-163">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="5a86b-164">`Get-ExecutionPolicy`Cmdlet 显示 **RemoteSigned** 是当前 PowerShell 会话的有效执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-164">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="5a86b-165">从当前目录执行 **Start-ActivityTracker.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-165">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="5a86b-166">由于脚本未进行数字签名，因此脚本被 **RemoteSigned** 阻止。</span><span class="sxs-lookup"><span data-stu-id="5a86b-166">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="5a86b-167">在此示例中，脚本的代码已评审并验证为可安全运行。</span><span class="sxs-lookup"><span data-stu-id="5a86b-167">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="5a86b-168">`Unblock-File`Cmdlet 使用 **Path** 参数取消阻止脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-168">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="5a86b-169">若要验证是否 `Unblock-File` 未更改执行策略， `Get-ExecutionPolicy` 则会显示有效的执行策略 **RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-169">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="5a86b-170">将从当前目录执行 **Start-ActivityTracker.ps1** 的脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-170">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="5a86b-171">脚本开始运行，因为它已被 cmdlet 取消阻止 `Unblock-File` 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-171">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="5a86b-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5a86b-172">PARAMETERS</span></span>

### <span data-ttu-id="5a86b-173">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="5a86b-173">-ExecutionPolicy</span></span>

<span data-ttu-id="5a86b-174">指定执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-174">Specifies the execution policy.</span></span> <span data-ttu-id="5a86b-175">如果没有组策略，并且每个作用域的执行策略设置为 " **未定义** "，则 " **受限制** " 将成为所有用户的有效策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-175">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="5a86b-176">可接受的执行策略值如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a86b-176">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="5a86b-177">**AllSigned** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-177">**AllSigned** .</span></span> <span data-ttu-id="5a86b-178">要求所有脚本和配置文件都由受信任的发布者签名，包括在本地计算机上编写的脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-178">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="5a86b-179">**绕过** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-179">**Bypass** .</span></span> <span data-ttu-id="5a86b-180">不阻止任何操作，并且没有任何警告或提示。</span><span class="sxs-lookup"><span data-stu-id="5a86b-180">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="5a86b-181">**Default** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-181">**Default** .</span></span> <span data-ttu-id="5a86b-182">设置默认的执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-182">Sets the default execution policy.</span></span> <span data-ttu-id="5a86b-183">**适用于 windows** 客户端或 windows 服务器的 **RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-183">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="5a86b-184">**RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-184">**RemoteSigned** .</span></span> <span data-ttu-id="5a86b-185">要求从 Internet 下载的所有脚本和配置文件都由受信任的发布者进行签名。</span><span class="sxs-lookup"><span data-stu-id="5a86b-185">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="5a86b-186">Windows server 计算机的默认执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-186">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="5a86b-187">**限制** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-187">**Restricted** .</span></span> <span data-ttu-id="5a86b-188">不加载配置文件或运行脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-188">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="5a86b-189">默认的执行策略 Windows 客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="5a86b-189">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="5a86b-190">**未定义** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-190">**Undefined** .</span></span> <span data-ttu-id="5a86b-191">未为该作用域设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-191">No execution policy is set for the scope.</span></span> <span data-ttu-id="5a86b-192">从非组策略设置的作用域中删除已分配的执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-192">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="5a86b-193">如果所有作用域中的执行策略均未 **定义** ，则会 **限制** 有效的执行策略。</span><span class="sxs-lookup"><span data-stu-id="5a86b-193">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** .</span></span>
- <span data-ttu-id="5a86b-194">**无限制** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-194">**Unrestricted** .</span></span> <span data-ttu-id="5a86b-195">加载所有配置文件并运行所有脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-195">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="5a86b-196">如果运行从 Internet 下载的未签名脚本，则系统将提示你需要权限才能运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="5a86b-196">If you run an unsigned script that was downloaded from the Internet, you are prompted for permission before it runs.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5a86b-197">-Force</span><span class="sxs-lookup"><span data-stu-id="5a86b-197">-Force</span></span>

<span data-ttu-id="5a86b-198">抑制所有确认提示。</span><span class="sxs-lookup"><span data-stu-id="5a86b-198">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="5a86b-199">请谨慎使用此参数，以避免意外结果。</span><span class="sxs-lookup"><span data-stu-id="5a86b-199">Use caution with this parameter to avoid unexpected results.</span></span>

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

### <span data-ttu-id="5a86b-200">-Scope</span><span class="sxs-lookup"><span data-stu-id="5a86b-200">-Scope</span></span>

<span data-ttu-id="5a86b-201">指定受执行策略影响的作用域。</span><span class="sxs-lookup"><span data-stu-id="5a86b-201">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="5a86b-202">默认作用域为 **LocalMachine** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-202">The default scope is **LocalMachine** .</span></span>

<span data-ttu-id="5a86b-203">有效的执行策略由优先级顺序确定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a86b-203">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="5a86b-204">**MachinePolicy** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-204">**MachinePolicy** .</span></span> <span data-ttu-id="5a86b-205">为计算机的所有用户组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5a86b-205">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="5a86b-206">**UserPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-206">**UserPolicy** .</span></span> <span data-ttu-id="5a86b-207">为计算机的当前用户组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5a86b-207">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="5a86b-208">**进程** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-208">**Process** .</span></span> <span data-ttu-id="5a86b-209">仅影响当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="5a86b-209">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="5a86b-210">**CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-210">**CurrentUser** .</span></span> <span data-ttu-id="5a86b-211">仅影响当前用户。</span><span class="sxs-lookup"><span data-stu-id="5a86b-211">Affects only the current user.</span></span>
- <span data-ttu-id="5a86b-212">**LocalMachine** 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-212">**LocalMachine** .</span></span> <span data-ttu-id="5a86b-213">影响计算机的所有用户的默认作用域。</span><span class="sxs-lookup"><span data-stu-id="5a86b-213">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="5a86b-214">**进程** 范围仅影响当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="5a86b-214">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="5a86b-215">执行策略保存在环境变量中 `$env:PSExecutionPolicyPreference` ，而不是保存在注册表中。</span><span class="sxs-lookup"><span data-stu-id="5a86b-215">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="5a86b-216">关闭 PowerShell 会话后，会删除变量和值。</span><span class="sxs-lookup"><span data-stu-id="5a86b-216">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="5a86b-217">**CurrentUser** 作用域的执行策略将写入到 **HKEY_LOCAL_USER** 的注册表配置单元中。</span><span class="sxs-lookup"><span data-stu-id="5a86b-217">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER** .</span></span>

<span data-ttu-id="5a86b-218">**LocalMachine** 作用域的执行策略将写入到 **HKEY_LOCAL_MACHINE** 的注册表配置单元中。</span><span class="sxs-lookup"><span data-stu-id="5a86b-218">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="5a86b-219">-Confirm</span><span class="sxs-lookup"><span data-stu-id="5a86b-219">-Confirm</span></span>

<span data-ttu-id="5a86b-220">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="5a86b-220">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="5a86b-221">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="5a86b-221">-WhatIf</span></span>

<span data-ttu-id="5a86b-222">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="5a86b-222">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="5a86b-223">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="5a86b-223">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="5a86b-224">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5a86b-224">CommonParameters</span></span>

<span data-ttu-id="5a86b-225">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="5a86b-225">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5a86b-226">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="5a86b-226">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5a86b-227">输入</span><span class="sxs-lookup"><span data-stu-id="5a86b-227">INPUTS</span></span>

### <span data-ttu-id="5a86b-228">Microsoft.PowerShell.ExecutionPolicy、System.String</span><span class="sxs-lookup"><span data-stu-id="5a86b-228">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="5a86b-229">可以通过管道将执行策略对象或包含执行策略名称的字符串传递给 `Set-ExecutionPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="5a86b-229">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="5a86b-230">输出</span><span class="sxs-lookup"><span data-stu-id="5a86b-230">OUTPUTS</span></span>

### <span data-ttu-id="5a86b-231">无</span><span class="sxs-lookup"><span data-stu-id="5a86b-231">None</span></span>

<span data-ttu-id="5a86b-232">`Set-ExecutionPolicy` 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="5a86b-232">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="5a86b-233">注释</span><span class="sxs-lookup"><span data-stu-id="5a86b-233">NOTES</span></span>

<span data-ttu-id="5a86b-234">`Set-ExecutionPolicy` 不会更改 **MachinePolicy** 和 **UserPolicy** 作用域，因为它们由组策略设置。</span><span class="sxs-lookup"><span data-stu-id="5a86b-234">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="5a86b-235">`Set-ExecutionPolicy` 不会重写组策略，即使用户首选项比策略更严格。</span><span class="sxs-lookup"><span data-stu-id="5a86b-235">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="5a86b-236">如果为计算机或用户启用了组策略 **打开脚本执行** ，则将保存用户首选项，但这不是有效的。</span><span class="sxs-lookup"><span data-stu-id="5a86b-236">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="5a86b-237">PowerShell 会显示一条消息，说明冲突。</span><span class="sxs-lookup"><span data-stu-id="5a86b-237">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="5a86b-238">相关链接</span><span class="sxs-lookup"><span data-stu-id="5a86b-238">RELATED LINKS</span></span>

[<span data-ttu-id="5a86b-239">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="5a86b-239">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="5a86b-240">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="5a86b-240">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="5a86b-241">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5a86b-241">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="5a86b-242">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="5a86b-242">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="5a86b-243">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="5a86b-243">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="5a86b-244">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="5a86b-244">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="5a86b-245">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="5a86b-245">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="5a86b-246">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="5a86b-246">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="5a86b-247">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="5a86b-247">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)
