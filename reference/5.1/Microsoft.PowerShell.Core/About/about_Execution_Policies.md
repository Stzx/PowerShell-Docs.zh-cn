---
description: 介绍 PowerShell 执行策略并说明如何管理它们。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Execution_Policies
ms.openlocfilehash: 3332adb76c76fa644d23060abe2af43bd45a15a6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200308"
---
# <a name="about-execution-policies"></a><span data-ttu-id="96640-104">关于执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-104">About Execution Policies</span></span>

## <a name="short-description"></a><span data-ttu-id="96640-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="96640-105">Short Description</span></span>

<span data-ttu-id="96640-106">介绍 PowerShell 执行策略并说明如何管理它们。</span><span class="sxs-lookup"><span data-stu-id="96640-106">Describes the PowerShell execution policies and explains how to manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="96640-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="96640-107">Long Description</span></span>

<span data-ttu-id="96640-108">PowerShell 执行策略是一项安全功能，用于控制 PowerShell 加载配置文件和运行脚本的条件。</span><span class="sxs-lookup"><span data-stu-id="96640-108">PowerShell's execution policy is a safety feature that controls the conditions under which PowerShell loads configuration files and runs scripts.</span></span> <span data-ttu-id="96640-109">此功能有助于防止恶意脚本的执行。</span><span class="sxs-lookup"><span data-stu-id="96640-109">This feature helps prevent the execution of malicious scripts.</span></span>

<span data-ttu-id="96640-110">在 Windows 计算机上，可以为本地计算机、当前用户或特定会话设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-110">On a Windows computer you can set an execution policy for the local computer, for the current user, or for a particular session.</span></span> <span data-ttu-id="96640-111">你还可以使用组策略设置为计算机和用户设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-111">You can also use a Group Policy setting to set execution policies for computers and users.</span></span>

<span data-ttu-id="96640-112">本地计算机和当前用户的执行策略存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="96640-112">Execution policies for the local computer and current user are stored in the registry.</span></span> <span data-ttu-id="96640-113">不需要在 PowerShell 配置文件中设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-113">You don't need to set execution policies in your PowerShell profile.</span></span>
<span data-ttu-id="96640-114">特定会话的执行策略仅存储在内存中，并在会话关闭时丢失。</span><span class="sxs-lookup"><span data-stu-id="96640-114">The execution policy for a particular session is stored only in memory and is lost when the session is closed.</span></span>

<span data-ttu-id="96640-115">执行策略不是限制用户操作的安全系统。</span><span class="sxs-lookup"><span data-stu-id="96640-115">The execution policy isn't a security system that restricts user actions.</span></span> <span data-ttu-id="96640-116">例如，当用户无法运行脚本时，可以通过在命令行中键入脚本内容来轻松地绕过策略。</span><span class="sxs-lookup"><span data-stu-id="96640-116">For example, users can easily bypass a policy by typing the script contents at the command line when they cannot run a script.</span></span> <span data-ttu-id="96640-117">相反，执行策略可帮助用户设置基本规则并防止无意中违反它们。</span><span class="sxs-lookup"><span data-stu-id="96640-117">Instead, the execution policy helps users to set basic rules and prevents them from violating them unintentionally.</span></span>

## <a name="powershell-execution-policies"></a><span data-ttu-id="96640-118">PowerShell 执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-118">PowerShell execution policies</span></span>

<span data-ttu-id="96640-119">PowerShell 执行策略如下所示：</span><span class="sxs-lookup"><span data-stu-id="96640-119">The PowerShell execution policies are as follows:</span></span>

### <a name="allsigned"></a><span data-ttu-id="96640-120">AllSigned</span><span class="sxs-lookup"><span data-stu-id="96640-120">AllSigned</span></span>

- <span data-ttu-id="96640-121">脚本可以运行。</span><span class="sxs-lookup"><span data-stu-id="96640-121">Scripts can run.</span></span>
- <span data-ttu-id="96640-122">要求所有脚本和配置文件都由受信任的发布者签名，包括在本地计算机上编写的脚本。</span><span class="sxs-lookup"><span data-stu-id="96640-122">Requires that all scripts and configuration files be signed by a trusted publisher, including scripts that you write on the local computer.</span></span>
- <span data-ttu-id="96640-123">在从尚未归类为受信任或不受信任的发布者运行脚本之前，将提示您。</span><span class="sxs-lookup"><span data-stu-id="96640-123">Prompts you before running scripts from publishers that you haven't yet classified as trusted or untrusted.</span></span>
- <span data-ttu-id="96640-124">运行已签名但恶意脚本的风险。</span><span class="sxs-lookup"><span data-stu-id="96640-124">Risks running signed, but malicious, scripts.</span></span>

### <a name="bypass"></a><span data-ttu-id="96640-125">免验证</span><span class="sxs-lookup"><span data-stu-id="96640-125">Bypass</span></span>

- <span data-ttu-id="96640-126">不阻止任何操作，并且没有任何警告或提示。</span><span class="sxs-lookup"><span data-stu-id="96640-126">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="96640-127">此执行策略适用于以下配置：将 PowerShell 脚本内置于更大的应用程序或配置，其中 PowerShell 是具有其自己的安全模型的程序的基础。</span><span class="sxs-lookup"><span data-stu-id="96640-127">This execution policy is designed for configurations in which a PowerShell script is built in to a larger application or for configurations in which PowerShell is the foundation for a program that has its own security model.</span></span>

### <a name="default"></a><span data-ttu-id="96640-128">默认</span><span class="sxs-lookup"><span data-stu-id="96640-128">Default</span></span>

- <span data-ttu-id="96640-129">设置默认的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-129">Sets the default execution policy.</span></span>
- <span data-ttu-id="96640-130">Windows 客户端 **限制** 。</span><span class="sxs-lookup"><span data-stu-id="96640-130">**Restricted** for Windows clients.</span></span>
- <span data-ttu-id="96640-131">适用于 Windows server 的 **RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="96640-131">**RemoteSigned** for Windows servers.</span></span>

### <a name="remotesigned"></a><span data-ttu-id="96640-132">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="96640-132">RemoteSigned</span></span>

- <span data-ttu-id="96640-133">Windows server 计算机的默认执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-133">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="96640-134">脚本可以运行。</span><span class="sxs-lookup"><span data-stu-id="96640-134">Scripts can run.</span></span>
- <span data-ttu-id="96640-135">要求来自受信任的发布者的脚本和配置文件的数字签名，这些脚本和配置文件是从 internet 下载的，其中包括电子邮件和即时消息程序。</span><span class="sxs-lookup"><span data-stu-id="96640-135">Requires a digital signature from a trusted publisher on scripts and configuration files that are downloaded from the internet which includes email and instant messaging programs.</span></span>
- <span data-ttu-id="96640-136">不需要在本地计算机上编写的脚本上的数字签名，也不需要从 internet 下载。</span><span class="sxs-lookup"><span data-stu-id="96640-136">Doesn't require digital signatures on scripts that are written on the local computer and not downloaded from the internet.</span></span>
- <span data-ttu-id="96640-137">如果未对脚本进行阻止，则运行从 internet 下载的脚本，而不是未签名的脚本，例如通过使用 `Unblock-File` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96640-137">Runs scripts that are downloaded from the internet and not signed, if the scripts are unblocked, such as by using the `Unblock-File` cmdlet.</span></span>
- <span data-ttu-id="96640-138">从 internet 以外的源运行未签名脚本的风险，以及可能是恶意的签名脚本。</span><span class="sxs-lookup"><span data-stu-id="96640-138">Risks running unsigned scripts from sources other than the internet and signed scripts that could be malicious.</span></span>

### <a name="restricted"></a><span data-ttu-id="96640-139">受限制</span><span class="sxs-lookup"><span data-stu-id="96640-139">Restricted</span></span>

- <span data-ttu-id="96640-140">Windows 客户端计算机的默认执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-140">The default execution policy for Windows client computers.</span></span>
- <span data-ttu-id="96640-141">允许单独的命令，但不允许脚本。</span><span class="sxs-lookup"><span data-stu-id="96640-141">Permits individual commands, but does not allow scripts.</span></span>
- <span data-ttu-id="96640-142">阻止运行所有脚本文件，包括格式设置和配置文件 (`.ps1xml`) 、模块脚本文件 (`.psm1`) 和 PowerShell 配置文件 (`.ps1`) 。</span><span class="sxs-lookup"><span data-stu-id="96640-142">Prevents running of all script files, including formatting and configuration files (`.ps1xml`), module script files (`.psm1`), and PowerShell profiles (`.ps1`).</span></span>

### <a name="undefined"></a><span data-ttu-id="96640-143">Undefined</span><span class="sxs-lookup"><span data-stu-id="96640-143">Undefined</span></span>

- <span data-ttu-id="96640-144">当前作用域中没有设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-144">There is no execution policy set in the current scope.</span></span>
- <span data-ttu-id="96640-145">如果所有作用域中的执行策略均未 **定义** ，则对 windows 客户端和 Windows Server **RemoteSigned** 的有效执行策略将 **受到限制** 。</span><span class="sxs-lookup"><span data-stu-id="96640-145">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** for Windows clients and **RemoteSigned** for Windows Server.</span></span>

### <a name="unrestricted"></a><span data-ttu-id="96640-146">非受限</span><span class="sxs-lookup"><span data-stu-id="96640-146">Unrestricted</span></span>

- <span data-ttu-id="96640-147">未签名的脚本可以运行。</span><span class="sxs-lookup"><span data-stu-id="96640-147">Unsigned scripts can run.</span></span> <span data-ttu-id="96640-148">存在运行恶意脚本的风险。</span><span class="sxs-lookup"><span data-stu-id="96640-148">There is a risk of running malicious scripts.</span></span>
- <span data-ttu-id="96640-149">在运行不在本地 intranet 区域中的脚本和配置文件之前警告用户。</span><span class="sxs-lookup"><span data-stu-id="96640-149">Warns the user before running scripts and configuration files that are not from the local intranet zone.</span></span>

> [!NOTE]
> <span data-ttu-id="96640-150">在不区分通用命名约定 (UNC) 路径与 internet 路径的系统上，可能无法使用 **RemoteSigned** 执行策略来运行 unc 路径标识的脚本。</span><span class="sxs-lookup"><span data-stu-id="96640-150">On systems that do not distinguish Universal Naming Convention (UNC) paths from internet paths, scripts that are identified by a UNC path might not be permitted to run with the **RemoteSigned** execution policy.</span></span>

## <a name="execution-policy-scope"></a><span data-ttu-id="96640-151">执行策略作用域</span><span class="sxs-lookup"><span data-stu-id="96640-151">Execution policy scope</span></span>

<span data-ttu-id="96640-152">可以设置仅在特定作用域内有效的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-152">You can set an execution policy that is effective only in a particular scope.</span></span>

<span data-ttu-id="96640-153">**作用域** 的有效值为 **MachinePolicy** 、 **UserPolicy** 、 **Process** 、 **CurrentUser** 和 **LocalMachine** 。</span><span class="sxs-lookup"><span data-stu-id="96640-153">The valid values for **Scope** are **MachinePolicy** , **UserPolicy** , **Process** , **CurrentUser** , and **LocalMachine** .</span></span> <span data-ttu-id="96640-154">设置执行策略时， **LocalMachine** 为默认值。</span><span class="sxs-lookup"><span data-stu-id="96640-154">**LocalMachine** is the default when setting an execution policy.</span></span>

<span data-ttu-id="96640-155">**作用域** 值按优先级顺序列出。</span><span class="sxs-lookup"><span data-stu-id="96640-155">The **Scope** values are listed in precedence order.</span></span> <span data-ttu-id="96640-156">优先级相同的策略在当前会话中有效，即使在优先级较低的情况下设置了限制性更强的策略也是如此。</span><span class="sxs-lookup"><span data-stu-id="96640-156">The policy that takes precedence is effective in the current session, even if a more restrictive policy was set at a lower level of precedence.</span></span>

<span data-ttu-id="96640-157">有关详细信息，请参阅 [set-executionpolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)。</span><span class="sxs-lookup"><span data-stu-id="96640-157">For more information, see [Set-ExecutionPolicy](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy).</span></span>

### <a name="machinepolicy"></a><span data-ttu-id="96640-158">MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="96640-158">MachinePolicy</span></span>

<span data-ttu-id="96640-159">为计算机的所有用户组策略设置。</span><span class="sxs-lookup"><span data-stu-id="96640-159">Set by a Group Policy for all users of the computer.</span></span>

### <a name="userpolicy"></a><span data-ttu-id="96640-160">UserPolicy</span><span class="sxs-lookup"><span data-stu-id="96640-160">UserPolicy</span></span>

<span data-ttu-id="96640-161">为计算机的当前用户组策略设置。</span><span class="sxs-lookup"><span data-stu-id="96640-161">Set by a Group Policy for the current user of the computer.</span></span>

### <a name="process"></a><span data-ttu-id="96640-162">过程</span><span class="sxs-lookup"><span data-stu-id="96640-162">Process</span></span>

<span data-ttu-id="96640-163">**进程** 范围仅影响当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="96640-163">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="96640-164">执行策略保存在环境变量中 `$env:PSExecutionPolicyPreference` ，而不是保存在注册表中。</span><span class="sxs-lookup"><span data-stu-id="96640-164">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="96640-165">关闭 PowerShell 会话后，会删除变量和值。</span><span class="sxs-lookup"><span data-stu-id="96640-165">When the PowerShell session is closed, the variable and value are deleted.</span></span>

### <a name="currentuser"></a><span data-ttu-id="96640-166">CurrentUser</span><span class="sxs-lookup"><span data-stu-id="96640-166">CurrentUser</span></span>

<span data-ttu-id="96640-167">执行策略仅影响当前用户。</span><span class="sxs-lookup"><span data-stu-id="96640-167">The execution policy affects only the current user.</span></span> <span data-ttu-id="96640-168">它存储在 **HKEY_CURRENT_USER** 注册表子项中。</span><span class="sxs-lookup"><span data-stu-id="96640-168">It's stored in the **HKEY_CURRENT_USER** registry subkey.</span></span>

### <a name="localmachine"></a><span data-ttu-id="96640-169">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="96640-169">LocalMachine</span></span>

<span data-ttu-id="96640-170">执行策略会影响当前计算机上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="96640-170">The execution policy affects all users on the current computer.</span></span> <span data-ttu-id="96640-171">它存储在 **HKEY_LOCAL_MACHINE** 注册表子项中。</span><span class="sxs-lookup"><span data-stu-id="96640-171">It's stored in the **HKEY_LOCAL_MACHINE** registry subkey.</span></span>

## <a name="managing-the-execution-policy-with-powershell"></a><span data-ttu-id="96640-172">通过 PowerShell 管理执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-172">Managing the execution policy with PowerShell</span></span>

<span data-ttu-id="96640-173">若要获取当前 PowerShell 会话的有效执行策略，请使用 `Get-ExecutionPolicy` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96640-173">To get the effective execution policy for the current PowerShell session, use the `Get-ExecutionPolicy` cmdlet.</span></span>

<span data-ttu-id="96640-174">以下命令将获取有效的执行策略：</span><span class="sxs-lookup"><span data-stu-id="96640-174">The following command gets the effective execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

<span data-ttu-id="96640-175">若要获取影响当前会话的所有执行策略，并按优先顺序显示它们：</span><span class="sxs-lookup"><span data-stu-id="96640-175">To get all of the execution policies that affect the current session and display them in precedence order:</span></span>

```powershell
Get-ExecutionPolicy -List
```

<span data-ttu-id="96640-176">结果与以下示例输出类似：</span><span class="sxs-lookup"><span data-stu-id="96640-176">The result looks similar to the following sample output:</span></span>

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser    RemoteSigned
 LocalMachine       AllSigned
```

<span data-ttu-id="96640-177">在这种情况下，有效的执行策略是 **RemoteSigned** ，因为当前用户的执行策略优先于为本地计算机设置的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-177">In this case, the effective execution policy is **RemoteSigned** because the execution policy for the current user takes precedence over the execution policy set for the local computer.</span></span>

<span data-ttu-id="96640-178">若要获取为特定作用域设置的执行策略，请使用的 **作用域** 参数 `Get-ExecutionPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="96640-178">To get the execution policy set for a particular scope, use the **Scope** parameter of `Get-ExecutionPolicy`.</span></span>

<span data-ttu-id="96640-179">例如，以下命令将获取 **CurrentUser** 作用域的执行策略：</span><span class="sxs-lookup"><span data-stu-id="96640-179">For example, the following command gets the execution policy for the **CurrentUser** scope:</span></span>

```powershell
Get-ExecutionPolicy -Scope CurrentUser
```

### <a name="change-the-execution-policy"></a><span data-ttu-id="96640-180">更改执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-180">Change the execution policy</span></span>

<span data-ttu-id="96640-181">若要更改 Windows 计算机上的 PowerShell 执行策略，请使用 `Set-ExecutionPolicy` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96640-181">To change the PowerShell execution policy on your Windows computer, use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="96640-182">更改立即生效。</span><span class="sxs-lookup"><span data-stu-id="96640-182">The change is effective immediately.</span></span> <span data-ttu-id="96640-183">不需要重新启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="96640-183">You don't need to restart PowerShell.</span></span>

<span data-ttu-id="96640-184">如果设置作用域 **LocalMachine** 或 **CurrentUser** 的执行策略，则更改将保存在注册表中并保持有效，直到再次更改。</span><span class="sxs-lookup"><span data-stu-id="96640-184">If you set the execution policy for the scopes **LocalMachine** or the **CurrentUser** , the change is saved in the registry and remains effective until you change it again.</span></span>

<span data-ttu-id="96640-185">如果为 **进程** 范围设置了执行策略，则它不会保存在注册表中。</span><span class="sxs-lookup"><span data-stu-id="96640-185">If you set the execution policy for the **Process** scope, it's not saved in the registry.</span></span> <span data-ttu-id="96640-186">将保留执行策略，直到关闭当前进程和任何子进程。</span><span class="sxs-lookup"><span data-stu-id="96640-186">The execution policy is retained until the current process and any child processes are closed.</span></span>

> [!NOTE]
> <span data-ttu-id="96640-187">在 Windows Vista 和更高版本的 Windows 中，若要运行更改本地计算机的执行策略的命令 **，则** 可以通过 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="96640-187">In Windows Vista and later versions of Windows, to run commands that change the execution policy for the local computer, **LocalMachine** scope, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="96640-188">更改执行策略：</span><span class="sxs-lookup"><span data-stu-id="96640-188">To change your execution policy:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName>
```

<span data-ttu-id="96640-189">例如：</span><span class="sxs-lookup"><span data-stu-id="96640-189">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="96640-190">若要设置特定范围中的执行策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="96640-190">To set the execution policy in a particular scope:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy <PolicyName> -Scope <scope>
```

<span data-ttu-id="96640-191">例如：</span><span class="sxs-lookup"><span data-stu-id="96640-191">For example:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

<span data-ttu-id="96640-192">用于更改执行策略的命令可以成功，但仍不会更改有效的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-192">A command to change an execution policy can succeed but still not change the effective execution policy.</span></span>

<span data-ttu-id="96640-193">例如，为本地计算机设置执行策略的命令可能会成功，但会被当前用户的执行策略覆盖。</span><span class="sxs-lookup"><span data-stu-id="96640-193">For example, a command that sets the execution policy for the local computer can succeed but be overridden by the execution policy for the current user.</span></span>

### <a name="remove-the-execution-policy"></a><span data-ttu-id="96640-194">删除执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-194">Remove the execution policy</span></span>

<span data-ttu-id="96640-195">若要删除特定作用域的执行策略，请将执行策略设置为 **Undefined** 。</span><span class="sxs-lookup"><span data-stu-id="96640-195">To remove the execution policy for a particular scope, set the execution policy to **Undefined** .</span></span>

<span data-ttu-id="96640-196">例如，要为本地计算机的所有用户删除执行策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="96640-196">For example, to remove the execution policy for all the users of the local computer:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope LocalMachine
```

<span data-ttu-id="96640-197">删除 **作用域** 的执行策略：</span><span class="sxs-lookup"><span data-stu-id="96640-197">To remove the execution policy for a **Scope** :</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
```

<span data-ttu-id="96640-198">如果未在任何范围内设置执行策略，则会 **限制** 有效执行策略，这是 Windows 客户端的默认设置。</span><span class="sxs-lookup"><span data-stu-id="96640-198">If no execution policy is set in any scope, the effective execution policy is **Restricted** , which is the default for Windows clients.</span></span>

### <a name="set-a-different-policy-for-one-session"></a><span data-ttu-id="96640-199">为一个会话设置不同的策略</span><span class="sxs-lookup"><span data-stu-id="96640-199">Set a different policy for one session</span></span>

<span data-ttu-id="96640-200">你可以使用 **powershell.exe** 的 **set-executionpolicy** 参数为新的 PowerShell 会话设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-200">You can use the **ExecutionPolicy** parameter of **powershell.exe** to set an execution policy for a new PowerShell session.</span></span> <span data-ttu-id="96640-201">策略只影响当前会话和子会话。</span><span class="sxs-lookup"><span data-stu-id="96640-201">The policy affects only the current session and child sessions.</span></span>

<span data-ttu-id="96640-202">若要为新会话设置执行策略，请在命令行中启动 PowerShell，如 **cmd.exe** 或 powershell，然后使用 **powershell.exe** 的 **set-executionpolicy** 参数设置执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-202">To set the execution policy for a new session, start PowerShell at the command line, such as **cmd.exe** or from PowerShell, and then use the **ExecutionPolicy** parameter of **powershell.exe** to set the execution policy.</span></span>

<span data-ttu-id="96640-203">例如：</span><span class="sxs-lookup"><span data-stu-id="96640-203">For example:</span></span>

```powershell
powershell.exe -ExecutionPolicy AllSigned
```

<span data-ttu-id="96640-204">你设置的执行策略未存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="96640-204">The execution policy that you set isn't stored in the registry.</span></span> <span data-ttu-id="96640-205">相反，它存储在 `$env:PSExecutionPolicyPreference` 环境变量中。</span><span class="sxs-lookup"><span data-stu-id="96640-205">Instead, it's stored in the `$env:PSExecutionPolicyPreference` environment variable.</span></span> <span data-ttu-id="96640-206">关闭设置了策略的会话时，将删除该变量。</span><span class="sxs-lookup"><span data-stu-id="96640-206">The variable is deleted when you close the session in which the policy is set.</span></span> <span data-ttu-id="96640-207">不能通过编辑变量值来更改策略。</span><span class="sxs-lookup"><span data-stu-id="96640-207">You cannot change the policy by editing the variable value.</span></span>

<span data-ttu-id="96640-208">在会话期间，为会话设置的执行策略优先于在注册表中为本地计算机或当前用户设置的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-208">During the session, the execution policy that is set for the session takes precedence over an execution policy that is set in the registry for the local computer or current user.</span></span> <span data-ttu-id="96640-209">但是，它不会优先于通过使用组策略设置的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-209">However, it doesn't take precedence over the execution policy set by using a Group Policy.</span></span>

## <a name="use-group-policy-to-manage-execution-policy"></a><span data-ttu-id="96640-210">使用组策略来管理执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-210">Use Group Policy to Manage Execution Policy</span></span>

<span data-ttu-id="96640-211">您可以使用 " **打开脚本执行** 组策略" 设置来管理企业中的计算机的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-211">You can use the **Turn on Script Execution** Group Policy setting to manage the execution policy of computers in your enterprise.</span></span> <span data-ttu-id="96640-212">组策略设置将替代在所有作用域中在 PowerShell 中设置的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-212">The Group Policy setting overrides the execution policies set in PowerShell in all scopes.</span></span>

<span data-ttu-id="96640-213">" **打开脚本执行** " 策略设置如下所示：</span><span class="sxs-lookup"><span data-stu-id="96640-213">The **Turn on Script Execution** policy settings are as follows:</span></span>

- <span data-ttu-id="96640-214">如果禁用 " **启用脚本执行** "，脚本将不会运行。</span><span class="sxs-lookup"><span data-stu-id="96640-214">If you disable **Turn on Script Execution** , scripts do not run.</span></span> <span data-ttu-id="96640-215">这等效于 **受限制** 的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-215">This is equivalent to the **Restricted** execution policy.</span></span>
- <span data-ttu-id="96640-216">如果启用 "启用 **脚本执行** "，则可以选择执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-216">If you enable **Turn on Script Execution** , you can select an execution policy.</span></span> <span data-ttu-id="96640-217">组策略设置等效于以下执行策略设置：</span><span class="sxs-lookup"><span data-stu-id="96640-217">The Group Policy settings are equivalent to the following execution policy settings:</span></span>

  | <span data-ttu-id="96640-218">组策略</span><span class="sxs-lookup"><span data-stu-id="96640-218">Group Policy</span></span>                                  | <span data-ttu-id="96640-219">执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-219">Execution Policy</span></span> |
  | --------------------------------------------- | ---------------- |
  | <span data-ttu-id="96640-220">允许所有脚本</span><span class="sxs-lookup"><span data-stu-id="96640-220">Allow all scripts</span></span>                             | <span data-ttu-id="96640-221">非受限</span><span class="sxs-lookup"><span data-stu-id="96640-221">Unrestricted</span></span>     |
  | <span data-ttu-id="96640-222">允许本地脚本和远程签名的脚本</span><span class="sxs-lookup"><span data-stu-id="96640-222">Allow local scripts and remote signed scripts</span></span> | <span data-ttu-id="96640-223">RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="96640-223">RemoteSigned</span></span>     |
  | <span data-ttu-id="96640-224">仅允许签名脚本</span><span class="sxs-lookup"><span data-stu-id="96640-224">Allow only signed scripts</span></span>                     | <span data-ttu-id="96640-225">AllSigned</span><span class="sxs-lookup"><span data-stu-id="96640-225">AllSigned</span></span>        |

- <span data-ttu-id="96640-226">如果未配置 " **启用脚本执行** "，则它不起作用。</span><span class="sxs-lookup"><span data-stu-id="96640-226">If **Turn on Script Execution** is not configured, it has no effect.</span></span> <span data-ttu-id="96640-227">在 PowerShell 中设置的执行策略是有效的。</span><span class="sxs-lookup"><span data-stu-id="96640-227">The execution policy set in PowerShell is effective.</span></span>

<span data-ttu-id="96640-228">PowerShellExecutionPolicy 和 PowerShellExecutionPolicy 文件将 **打开脚本执行** 策略添加到组策略编辑器中的 "计算机配置" 和 "用户配置" 节点，路径如下。</span><span class="sxs-lookup"><span data-stu-id="96640-228">The PowerShellExecutionPolicy.adm and PowerShellExecutionPolicy.admx files add the **Turn on Script Execution** policy to the Computer Configuration and User Configuration nodes in Group Policy Editor in the following paths.</span></span>

<span data-ttu-id="96640-229">对于 Windows XP 和 Windows Server 2003：</span><span class="sxs-lookup"><span data-stu-id="96640-229">For Windows XP and Windows Server 2003:</span></span>

<span data-ttu-id="96640-230">管理 \Windows 组件 \Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96640-230">Administrative Templates\Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="96640-231">对于 Windows Vista 和更高版本的 Windows：</span><span class="sxs-lookup"><span data-stu-id="96640-231">For Windows Vista and later versions of Windows:</span></span>

<span data-ttu-id="96640-232">管理 Templates\Classic 管理模板 </span><span class="sxs-lookup"><span data-stu-id="96640-232">Administrative Templates\Classic Administrative Templates</span></span>\
<span data-ttu-id="96640-233">Windows \Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="96640-233">Windows Components\Windows PowerShell</span></span>

<span data-ttu-id="96640-234">"计算机配置" 节点中设置的策略优先于 "用户配置" 节点中设置的策略。</span><span class="sxs-lookup"><span data-stu-id="96640-234">Policies set in the Computer Configuration node take precedence over policies set in the User Configuration node.</span></span>

<span data-ttu-id="96640-235">有关详细信息，请参阅 [about_Group_Policy_Settings](about_Group_Policy_Settings.md)。</span><span class="sxs-lookup"><span data-stu-id="96640-235">For more information, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

### <a name="execution-policy-precedence"></a><span data-ttu-id="96640-236">执行策略优先级</span><span class="sxs-lookup"><span data-stu-id="96640-236">Execution policy precedence</span></span>

<span data-ttu-id="96640-237">在确定会话的有效执行策略时，PowerShell 将按以下优先顺序评估执行策略：</span><span class="sxs-lookup"><span data-stu-id="96640-237">When determining the effective execution policy for a session, PowerShell evaluates the execution policies in the following precedence order:</span></span>

- <span data-ttu-id="96640-238">组策略： MachinePolicy</span><span class="sxs-lookup"><span data-stu-id="96640-238">Group Policy: MachinePolicy</span></span>
- <span data-ttu-id="96640-239">组策略： UserPolicy</span><span class="sxs-lookup"><span data-stu-id="96640-239">Group Policy: UserPolicy</span></span>
- <span data-ttu-id="96640-240">执行策略：处理 (或 `powershell.exe -ExecutionPolicy`) </span><span class="sxs-lookup"><span data-stu-id="96640-240">Execution Policy: Process (or `powershell.exe -ExecutionPolicy`)</span></span>
- <span data-ttu-id="96640-241">执行策略： CurrentUser</span><span class="sxs-lookup"><span data-stu-id="96640-241">Execution Policy: CurrentUser</span></span>
- <span data-ttu-id="96640-242">执行策略： LocalMachine</span><span class="sxs-lookup"><span data-stu-id="96640-242">Execution Policy: LocalMachine</span></span>

## <a name="manage-signed-and-unsigned-scripts"></a><span data-ttu-id="96640-243">管理签名和未签名的脚本</span><span class="sxs-lookup"><span data-stu-id="96640-243">Manage signed and unsigned scripts</span></span>

<span data-ttu-id="96640-244">在 Windows 中，Internet Explorer 和 Microsoft Edge 等程序将备用数据流添加到下载的文件中。</span><span class="sxs-lookup"><span data-stu-id="96640-244">In Windows, programs like Internet Explorer and Microsoft Edge add an alternate data stream to files that are downloaded.</span></span> <span data-ttu-id="96640-245">这会将该文件标记为 "来自 Internet"。</span><span class="sxs-lookup"><span data-stu-id="96640-245">This marks the file as "coming from the Internet".</span></span> <span data-ttu-id="96640-246">如果 PowerShell 执行策略是 **RemoteSigned** ，则 powershell 不会运行从 internet 下载的未签名脚本，其中包括电子邮件和即时消息程序。</span><span class="sxs-lookup"><span data-stu-id="96640-246">If your PowerShell execution policy is **RemoteSigned** , PowerShell won't run unsigned scripts that are downloaded from the internet which includes email and instant messaging programs.</span></span>

<span data-ttu-id="96640-247">你可以对脚本进行签名，或选择运行未签名的脚本，而无需更改执行策略。</span><span class="sxs-lookup"><span data-stu-id="96640-247">You can sign the script or elect to run an unsigned script without changing the execution policy.</span></span>

<span data-ttu-id="96640-248">从 PowerShell 3.0 开始，可以使用 cmdlet 的 **Stream** 参数 `Get-Item` 来检测因从 internet 下载而被阻止的文件。</span><span class="sxs-lookup"><span data-stu-id="96640-248">Beginning in PowerShell 3.0, you can use the **Stream** parameter of the `Get-Item` cmdlet to detect files that are blocked because they were downloaded from the internet.</span></span> <span data-ttu-id="96640-249">使用 `Unblock-File` cmdlet 取消阻止脚本，以便可以在 PowerShell 中运行它们。</span><span class="sxs-lookup"><span data-stu-id="96640-249">Use the `Unblock-File` cmdlet to unblock the scripts so that you can run them in PowerShell.</span></span>

<span data-ttu-id="96640-250">有关详细信息，请参阅 [about_Signing](about_Signing.md)、 [获取项](xref:Microsoft.PowerShell.Management.Get-Item)和 [取消阻止文件](xref:Microsoft.PowerShell.Utility.Unblock-File)。</span><span class="sxs-lookup"><span data-stu-id="96640-250">For more information, see [about_Signing](about_Signing.md), [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item), and [Unblock-File](xref:Microsoft.PowerShell.Utility.Unblock-File).</span></span>

> [!NOTE]
> <span data-ttu-id="96640-251">下载文件的其他方法可能不会将文件标记为来自 Internet 区域。</span><span class="sxs-lookup"><span data-stu-id="96640-251">Other methods of downloading files may not mark the files as coming from the Internet Zone.</span></span> <span data-ttu-id="96640-252">示例包括：</span><span class="sxs-lookup"><span data-stu-id="96640-252">Some examples include:</span></span>
>
> - `curl.exe`
> - `Invoke-RestMethod`
> - `Invoke-WebRequest`

## <a name="execution-policy-on-windows-server-core-and-window-nano-server"></a><span data-ttu-id="96640-253">Windows Server Core 和 Window Nano Server 上的执行策略</span><span class="sxs-lookup"><span data-stu-id="96640-253">Execution policy on Windows Server Core and Window Nano Server</span></span>

<span data-ttu-id="96640-254">在某些情况下，当 PowerShell 5.1 在 Windows Server Core 或 Windows Nano Server 上运行时，执行策略可能会失败并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="96640-254">When PowerShell 5.1 is run on Windows Server Core or Windows Nano Server under certain conditions, execution policies can fail with the following error:</span></span>

```Output
AuthorizationManager check failed.
At line:1 char:1
+ C:\scriptpath\scriptname.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="96640-255">PowerShell 使用 Windows Desktop Shell 中的 Api (`explorer.exe`) 验证脚本文件的区域。</span><span class="sxs-lookup"><span data-stu-id="96640-255">PowerShell uses APIs in the Windows Desktop Shell (`explorer.exe`) to validate the Zone of a script file.</span></span> <span data-ttu-id="96640-256">Windows Shell 在 Windows Server Core 和 Windows Nano Server 上不可用。</span><span class="sxs-lookup"><span data-stu-id="96640-256">The Windows Shell is not available on Windows Server Core and Windows Nano Server.</span></span>

<span data-ttu-id="96640-257">如果 Windows 桌面 Shell 不可用或无响应，也可能会在任何 Windows 系统上收到此错误。</span><span class="sxs-lookup"><span data-stu-id="96640-257">You could also get this error on any Windows system if the Windows Desktop Shell is unavailable or unresponsive.</span></span> <span data-ttu-id="96640-258">例如，在登录过程中，PowerShell 登录脚本可以在 Windows 桌面准备就绪之前开始执行，从而导致失败。</span><span class="sxs-lookup"><span data-stu-id="96640-258">For example, during sign on, a PowerShell logon script could start execution before the Windows Desktop is ready, resulting in failure.</span></span>

<span data-ttu-id="96640-259">使用 **绕过** 或 **AllSigned** 的执行策略不需要区域检查来避免此问题。</span><span class="sxs-lookup"><span data-stu-id="96640-259">Using an execution policy of **ByPass** or **AllSigned** does not require a Zone check which avoids the problem.</span></span>

## <a name="see-also"></a><span data-ttu-id="96640-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96640-260">See Also</span></span>

[<span data-ttu-id="96640-261">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="96640-261">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="96640-262">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="96640-262">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="96640-263">about_Signing</span><span class="sxs-lookup"><span data-stu-id="96640-263">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="96640-264">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="96640-264">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="96640-265">Get-Item</span><span class="sxs-lookup"><span data-stu-id="96640-265">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)

[<span data-ttu-id="96640-266">PowerShell.exe 命令行帮助</span><span class="sxs-lookup"><span data-stu-id="96640-266">PowerShell.exe Command-Line Help</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="96640-267">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="96640-267">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="96640-268">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="96640-268">Unblock-File</span></span>](xref:Microsoft.PowerShell.Utility.Unblock-File)
