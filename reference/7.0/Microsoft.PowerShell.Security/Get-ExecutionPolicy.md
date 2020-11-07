---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: 96d840d68240d069511afa44753789f472618e19
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347238"
---
# <span data-ttu-id="fc462-103">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="fc462-103">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="fc462-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fc462-104">SYNOPSIS</span></span>
<span data-ttu-id="fc462-105">获取当前会话的执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-105">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="fc462-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fc462-106">SYNTAX</span></span>

### <span data-ttu-id="fc462-107">全部</span><span class="sxs-lookup"><span data-stu-id="fc462-107">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="fc462-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fc462-108">DESCRIPTION</span></span>

<span data-ttu-id="fc462-109">若要按优先级顺序显示每个作用域的执行策略，请使用 `Get-ExecutionPolicy -List` 。</span><span class="sxs-lookup"><span data-stu-id="fc462-109">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="fc462-110">若要查看 PowerShell 会话的有效执行策略，请使用 `Get-ExecutionPolicy` 不带参数的。</span><span class="sxs-lookup"><span data-stu-id="fc462-110">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="fc462-111">有效的执行策略由通过设置的执行策略确定 `Set-ExecutionPolicy` ，并组策略设置。</span><span class="sxs-lookup"><span data-stu-id="fc462-111">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="fc462-112">有关详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fc462-112">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="fc462-113">示例</span><span class="sxs-lookup"><span data-stu-id="fc462-113">EXAMPLES</span></span>

### <span data-ttu-id="fc462-114">示例1：获取所有执行策略</span><span class="sxs-lookup"><span data-stu-id="fc462-114">Example 1: Get all execution policies</span></span>

<span data-ttu-id="fc462-115">此命令按优先级顺序显示每个作用域的执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-115">This command displays the execution policies for each scope in the order of precedence.</span></span>

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

<span data-ttu-id="fc462-116">`Get-ExecutionPolicy`Cmdlet 使用 **List** 参数显示每个作用域的执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-116">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="fc462-117">示例2：设置执行策略</span><span class="sxs-lookup"><span data-stu-id="fc462-117">Example 2: Set an execution policy</span></span>

<span data-ttu-id="fc462-118">此示例演示如何为本地计算机设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-118">This example shows how to set an execution policy for the local computer.</span></span>

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
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="fc462-119">`Set-ExecutionPolicy`Cmdlet 使用 **set-executionpolicy** 参数指定 **RemoteSigned** 策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-119">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="fc462-120">**Scope** 参数指定默认作用域值 " **LocalMachine** "。</span><span class="sxs-lookup"><span data-stu-id="fc462-120">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="fc462-121">若要查看执行策略设置，请将 `Get-ExecutionPolicy` cmdlet 与 **List** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="fc462-121">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="fc462-122">示例3：获取有效的执行策略</span><span class="sxs-lookup"><span data-stu-id="fc462-122">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="fc462-123">此示例演示如何显示 PowerShell 会话的有效执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-123">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

<span data-ttu-id="fc462-124">`Get-ExecutionPolicy`Cmdlet 使用 **List** 参数显示每个作用域的执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-124">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="fc462-125">`Get-ExecutionPolicy`不使用参数运行 cmdlet，以显示有效的执行策略 **AllSigned** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-125">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned**.</span></span>

### <span data-ttu-id="fc462-126">示例4：取消阻止脚本，以便在不更改执行策略的情况下运行该脚本</span><span class="sxs-lookup"><span data-stu-id="fc462-126">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="fc462-127">此示例演示 **RemoteSigned** 执行策略如何阻止你运行未签名的脚本。</span><span class="sxs-lookup"><span data-stu-id="fc462-127">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="fc462-128">最佳做法是读取脚本的代码，并在使用 cmdlet **之前** 验证它是否安全 `Unblock-File` 。</span><span class="sxs-lookup"><span data-stu-id="fc462-128">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="fc462-129">`Unblock-File`Cmdlet 取消阻止脚本，以便它们可以运行，但不会更改执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-129">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="fc462-130">`Set-ExecutionPolicy`使用 **set-executionpolicy** 参数来指定 **RemoteSigned** 策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-130">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="fc462-131">策略设置为默认作用域 " **LocalMachine** "。</span><span class="sxs-lookup"><span data-stu-id="fc462-131">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="fc462-132">`Get-ExecutionPolicy`Cmdlet 显示 **RemoteSigned** 是当前 PowerShell 会话的有效执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-132">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="fc462-133">从当前目录执行 **Start-ActivityTracker.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="fc462-133">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="fc462-134">由于脚本未进行数字签名，因此脚本被 **RemoteSigned** 阻止。</span><span class="sxs-lookup"><span data-stu-id="fc462-134">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="fc462-135">在此示例中，脚本的代码已评审并验证为可安全运行。</span><span class="sxs-lookup"><span data-stu-id="fc462-135">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="fc462-136">`Unblock-File`Cmdlet 使用 **Path** 参数取消阻止脚本。</span><span class="sxs-lookup"><span data-stu-id="fc462-136">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="fc462-137">若要验证是否 `Unblock-File` 未更改执行策略， `Get-ExecutionPolicy` 则会显示有效的执行策略 **RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-137">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="fc462-138">将从当前目录执行 **Start-ActivityTracker.ps1** 的脚本。</span><span class="sxs-lookup"><span data-stu-id="fc462-138">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="fc462-139">脚本开始运行，因为它已被 cmdlet 取消阻止 `Unblock-File` 。</span><span class="sxs-lookup"><span data-stu-id="fc462-139">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="fc462-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fc462-140">PARAMETERS</span></span>

### <span data-ttu-id="fc462-141">-List</span><span class="sxs-lookup"><span data-stu-id="fc462-141">-List</span></span>

<span data-ttu-id="fc462-142">获取按优先级顺序列出的会话的所有执行策略值。</span><span class="sxs-lookup"><span data-stu-id="fc462-142">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="fc462-143">默认情况下， `Get-ExecutionPolicy` 仅获取有效的执行策略。</span><span class="sxs-lookup"><span data-stu-id="fc462-143">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="fc462-144">-Scope</span><span class="sxs-lookup"><span data-stu-id="fc462-144">-Scope</span></span>

<span data-ttu-id="fc462-145">指定受执行策略影响的作用域。</span><span class="sxs-lookup"><span data-stu-id="fc462-145">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="fc462-146">有效的执行策略由优先级顺序确定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fc462-146">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="fc462-147">**MachinePolicy** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-147">**MachinePolicy**.</span></span> <span data-ttu-id="fc462-148">为计算机的所有用户组策略设置。</span><span class="sxs-lookup"><span data-stu-id="fc462-148">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="fc462-149">**UserPolicy** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-149">**UserPolicy**.</span></span> <span data-ttu-id="fc462-150">为计算机的当前用户组策略设置。</span><span class="sxs-lookup"><span data-stu-id="fc462-150">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="fc462-151">**进程** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-151">**Process**.</span></span> <span data-ttu-id="fc462-152">仅影响当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="fc462-152">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="fc462-153">**CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-153">**CurrentUser**.</span></span> <span data-ttu-id="fc462-154">仅影响当前用户。</span><span class="sxs-lookup"><span data-stu-id="fc462-154">Affects only the current user.</span></span>
- <span data-ttu-id="fc462-155">**LocalMachine** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-155">**LocalMachine**.</span></span> <span data-ttu-id="fc462-156">影响计算机的所有用户的默认作用域。</span><span class="sxs-lookup"><span data-stu-id="fc462-156">Default scope that affects all users of the computer.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fc462-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fc462-157">CommonParameters</span></span>

<span data-ttu-id="fc462-158">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fc462-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fc462-159">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fc462-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fc462-160">输入</span><span class="sxs-lookup"><span data-stu-id="fc462-160">INPUTS</span></span>

### <span data-ttu-id="fc462-161">None</span><span class="sxs-lookup"><span data-stu-id="fc462-161">None</span></span>

<span data-ttu-id="fc462-162">`Get-ExecutionPolicy` 不接受来自管道的输入。</span><span class="sxs-lookup"><span data-stu-id="fc462-162">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="fc462-163">输出</span><span class="sxs-lookup"><span data-stu-id="fc462-163">OUTPUTS</span></span>

### <span data-ttu-id="fc462-164">Microsoft.PowerShell.ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="fc462-164">Microsoft.PowerShell.ExecutionPolicy</span></span>

<span data-ttu-id="fc462-165">Cmdlet 始终在 Linux 和 macOS 平台上返回不 **受限制** 。</span><span class="sxs-lookup"><span data-stu-id="fc462-165">The cmdlet always returns **Unrestricted** on Linux and macOS platforms.</span></span>

## <span data-ttu-id="fc462-166">注释</span><span class="sxs-lookup"><span data-stu-id="fc462-166">NOTES</span></span>

<span data-ttu-id="fc462-167">执行策略是 PowerShell 安全策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="fc462-167">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="fc462-168">执行策略确定你是否可以加载配置文件（如 PowerShell 配置文件）或运行脚本。</span><span class="sxs-lookup"><span data-stu-id="fc462-168">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="fc462-169">并且，在运行脚本之前是否必须对其进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="fc462-169">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="fc462-170">相关链接</span><span class="sxs-lookup"><span data-stu-id="fc462-170">RELATED LINKS</span></span>

[<span data-ttu-id="fc462-171">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="fc462-171">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="fc462-172">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="fc462-172">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="fc462-173">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="fc462-173">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="fc462-174">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="fc462-174">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="fc462-175">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="fc462-175">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)
