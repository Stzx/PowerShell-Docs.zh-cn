---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/invoke-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-Command
ms.openlocfilehash: 652ff321ea1c6507915be9748715604166207200
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198989"
---
# <span data-ttu-id="fd6a2-103">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="fd6a2-103">Invoke-Command</span></span>

## <span data-ttu-id="fd6a2-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fd6a2-104">SYNOPSIS</span></span>
<span data-ttu-id="fd6a2-105">在本地和远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-105">Runs commands on local and remote computers.</span></span>

## <span data-ttu-id="fd6a2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd6a2-106">SYNTAX</span></span>

### <span data-ttu-id="fd6a2-107">进程内 (默认) </span><span class="sxs-lookup"><span data-stu-id="fd6a2-107">InProcess (Default)</span></span>

```
Invoke-Command [-ScriptBlock] <ScriptBlock> [-NoNewScope] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-108">会话</span><span class="sxs-lookup"><span data-stu-id="fd6a2-108">Session</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-109">FilePathRunspace</span><span class="sxs-lookup"><span data-stu-id="fd6a2-109">FilePathRunspace</span></span>

```
Invoke-Command [[-Session] <PSSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-110">FilePathComputerName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-110">FilePathComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-FilePath] <String> [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-111">计算机名</span><span class="sxs-lookup"><span data-stu-id="fd6a2-111">ComputerName</span></span>

```
Invoke-Command [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-Port <Int32>] [-UseSSL]
 [-ConfigurationName <String>] [-ApplicationName <String>] [-ThrottleLimit <Int32>] [-AsJob]
 [-InDisconnectedSession] [-SessionName <String[]>] [-HideComputerName] [-JobName <String>]
 [-ScriptBlock] <ScriptBlock> [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-112">Uri</span><span class="sxs-lookup"><span data-stu-id="fd6a2-112">Uri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-AllowRedirection]
 [-SessionOption <PSSessionOption>] [-Authentication <AuthenticationMechanism>]
 [-EnableNetworkAccess] [-InputObject <PSObject>] [-ArgumentList <Object[]>]
 [-CertificateThumbprint <String>] [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-113">FilePathUri</span><span class="sxs-lookup"><span data-stu-id="fd6a2-113">FilePathUri</span></span>

```
Invoke-Command [-Credential <PSCredential>] [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [[-ConnectionUri] <Uri[]>] [-AsJob] [-InDisconnectedSession] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-AllowRedirection] [-SessionOption <PSSessionOption>]
 [-Authentication <AuthenticationMechanism>] [-EnableNetworkAccess] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-114">VMId</span><span class="sxs-lookup"><span data-stu-id="fd6a2-114">VMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-115">VMName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-115">VMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-ScriptBlock] <ScriptBlock> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-116">FilePathVMId</span><span class="sxs-lookup"><span data-stu-id="fd6a2-116">FilePathVMId</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] [-VMId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-117">FilePathVMName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-117">FilePathVMName</span></span>

```
Invoke-Command -Credential <PSCredential> [-ConfigurationName <String>] [-ThrottleLimit <Int32>]
 [-AsJob] [-HideComputerName] [-FilePath] <String> [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -VMName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-118">ContainerId</span><span class="sxs-lookup"><span data-stu-id="fd6a2-118">ContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-ScriptBlock] <ScriptBlock> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

### <span data-ttu-id="fd6a2-119">FilePathContainerId</span><span class="sxs-lookup"><span data-stu-id="fd6a2-119">FilePathContainerId</span></span>

```
Invoke-Command [-ConfigurationName <String>] [-ThrottleLimit <Int32>] [-AsJob] [-HideComputerName]
 [-JobName <String>] [-FilePath] <String> [-RunAsAdministrator] [-InputObject <PSObject>]
 [-ArgumentList <Object[]>] -ContainerId <String[]> [<CommonParameters>]
```

## <span data-ttu-id="fd6a2-120">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd6a2-120">DESCRIPTION</span></span>

<span data-ttu-id="fd6a2-121">`Invoke-Command`Cmdlet 在本地或远程计算机上运行命令，并返回命令中的所有输出，包括错误。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-121">The `Invoke-Command` cmdlet runs commands on a local or remote computer and returns all output from the commands, including errors.</span></span> <span data-ttu-id="fd6a2-122">使用单个 `Invoke-Command` 命令，可以在多台计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-122">Using a single `Invoke-Command` command, you can run commands on multiple computers.</span></span>

<span data-ttu-id="fd6a2-123">若要在远程计算机上运行单个命令，请使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-123">To run a single command on a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="fd6a2-124">若要运行一系列共享数据的相关命令，请使用 `New-PSSession` cmdlet 在远程计算机上创建 **一个与** (持久连接) ，然后使用的 **Session** 参数 `Invoke-Command` 在 **PSSession** 中运行该命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-124">To run a series of related commands that share data, use the `New-PSSession` cmdlet to create a **PSSession** (a persistent connection) on the remote computer, and then use the **Session** parameter of `Invoke-Command` to run the command in the **PSSession** .</span></span> <span data-ttu-id="fd6a2-125">若要在断开连接的会话中运行命令，请使用 **InDisconnectedSession** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-125">To run a command in a disconnected session, use the **InDisconnectedSession** parameter.</span></span> <span data-ttu-id="fd6a2-126">若要在后台作业中运行命令，请使用 **AsJob** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-126">To run a command in a background job, use the **AsJob** parameter.</span></span>

<span data-ttu-id="fd6a2-127">你还可以使用 `Invoke-Command` 本地计算机上的脚本块作为命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-127">You can also use `Invoke-Command` on a local computer to a script block as a command.</span></span> <span data-ttu-id="fd6a2-128">PowerShell 会立即在当前作用域的子范围内运行脚本块。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-128">PowerShell runs the script block immediately in a child scope of the current scope.</span></span>

<span data-ttu-id="fd6a2-129">在使用 `Invoke-Command` 在远程计算机上运行命令之前，请阅读 [about_Remote](./About/about_Remote.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-129">Before using `Invoke-Command` to run commands on a remote computer, read [about_Remote](./About/about_Remote.md).</span></span>

<span data-ttu-id="fd6a2-130">一些代码示例使用展开来减小行长度。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-130">Some code samples use splatting to reduce the line length.</span></span> <span data-ttu-id="fd6a2-131">有关详细信息，请参阅 [about_Splatting](./About/about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-131">For more information, see [about_Splatting](./About/about_Splatting.md).</span></span>

## <span data-ttu-id="fd6a2-132">示例</span><span class="sxs-lookup"><span data-stu-id="fd6a2-132">EXAMPLES</span></span>

### <span data-ttu-id="fd6a2-133">示例1：在服务器上运行脚本</span><span class="sxs-lookup"><span data-stu-id="fd6a2-133">Example 1: Run a script on a server</span></span>

<span data-ttu-id="fd6a2-134">此示例在 `Test.ps1` Server01 计算机上运行脚本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-134">This example runs the `Test.ps1` script on the Server01 computer.</span></span>

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

<span data-ttu-id="fd6a2-135">**FilePath** 参数指定位于本地计算机上的脚本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-135">The **FilePath** parameter specifies a script that is located on the local computer.</span></span> <span data-ttu-id="fd6a2-136">该脚本在远程计算机上运行，并将结果返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-136">The script runs on the remote computer and the results are returned to the local computer.</span></span>

### <span data-ttu-id="fd6a2-137">示例2：在远程服务器上运行命令</span><span class="sxs-lookup"><span data-stu-id="fd6a2-137">Example 2: Run a command on a remote server</span></span>

<span data-ttu-id="fd6a2-138">此示例在 `Get-Culture` Server01 远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-138">This example runs a `Get-Culture` command on the Server01 remote computer.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\User01 -ScriptBlock { Get-Culture }
```

<span data-ttu-id="fd6a2-139">**ComputerName** 参数指定远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-139">The **ComputerName** parameter specifies the name of the remote computer.</span></span> <span data-ttu-id="fd6a2-140">**Credential** 参数用于在 Domain01\User01 （有权运行命令的用户）的安全上下文中运行该命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-140">The **Credential** parameter is used to run the command in the security context of Domain01\User01, a user who has permission to run commands.</span></span> <span data-ttu-id="fd6a2-141">**ScriptBlock** 参数指定要在远程计算机上运行的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-141">The **ScriptBlock** parameter specifies the command to be run on the remote computer.</span></span>

<span data-ttu-id="fd6a2-142">在响应中，PowerShell 请求 User01 帐户的密码和身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-142">In response, PowerShell requests the password and an authentication method for the User01 account.</span></span>
<span data-ttu-id="fd6a2-143">然后，它将在 Server01 计算机上运行该命令并返回结果。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-143">It then runs the command on the Server01 computer and returns the result.</span></span>

### <span data-ttu-id="fd6a2-144">示例3：在永久连接中运行命令</span><span class="sxs-lookup"><span data-stu-id="fd6a2-144">Example 3: Run a command in a persistent connection</span></span>

<span data-ttu-id="fd6a2-145">此示例在 `Get-Culture` 名为 Server02 的远程计算机上使用持久性连接在会话中运行相同的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-145">This example runs the same `Get-Culture` command in a session, using a persistent connection, on the remote computer named Server02.</span></span>

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
Invoke-Command -Session $s -ScriptBlock {Get-Culture}
```

<span data-ttu-id="fd6a2-146">`New-PSSession`Cmdlet 在 Server02 远程计算机上创建一个会话，并将其保存在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-146">The `New-PSSession` cmdlet creates a session on the Server02 remote computer and saves it in the `$s` variable.</span></span> <span data-ttu-id="fd6a2-147">通常，仅当在远程计算机上运行一系列命令时，才会创建一个会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-147">Typically, you create a session only when you run a series of commands on the remote computer.</span></span>

<span data-ttu-id="fd6a2-148">`Invoke-Command`Cmdlet `Get-Culture` 在 Server02 上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-148">The `Invoke-Command` cmdlet runs the `Get-Culture` command on Server02.</span></span> <span data-ttu-id="fd6a2-149">**Session** 参数指定保存在变量中的会话 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-149">The **Session** parameter specifies the session saved in the `$s` variable.</span></span>

<span data-ttu-id="fd6a2-150">作为响应，PowerShell 将在 Server02 计算机上的会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-150">In response, PowerShell runs the command in the session on the Server02 computer.</span></span>

### <span data-ttu-id="fd6a2-151">示例4：使用会话运行共享数据的一系列命令</span><span class="sxs-lookup"><span data-stu-id="fd6a2-151">Example 4: Use a session to run a series of commands that share data</span></span>

<span data-ttu-id="fd6a2-152">此示例比较了使用 **ComputerName** 和的 **会话** 参数的影响 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-152">This example compares the effects of using **ComputerName** and **Session** parameters of `Invoke-Command`.</span></span> <span data-ttu-id="fd6a2-153">它显示了如何使用一个会话来运行共享相同数据的一系列命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-153">It shows how to use a session to run a series of commands that share the same data.</span></span>

```powershell
Invoke-Command -ComputerName Server02 -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -ComputerName Server02 -ScriptBlock {$p.VirtualMemorySize}
$s = New-PSSession -ComputerName Server02
Invoke-Command -Session $s -ScriptBlock {$p = Get-Process PowerShell}
Invoke-Command -Session $s -ScriptBlock {$p.VirtualMemorySize}
```

```Output
17930240
```

<span data-ttu-id="fd6a2-154">前两个命令使用的 **ComputerName** 参数在 `Invoke-Command` Server02 远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-154">The first two commands use the **ComputerName** parameter of `Invoke-Command` to run commands on the Server02 remote computer.</span></span> <span data-ttu-id="fd6a2-155">第一个命令使用 `Get-Process` cmdlet 来获取远程计算机上的 PowerShell 进程，并将其保存在变量中 `$p` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-155">The first command uses the `Get-Process` cmdlet to get the PowerShell process on the remote computer and to save it in the `$p` variable.</span></span> <span data-ttu-id="fd6a2-156">第二个命令将获取 PowerShell 进程的 **VirtualMemorySize** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-156">The second command gets the value of the **VirtualMemorySize** property of the PowerShell process.</span></span>

<span data-ttu-id="fd6a2-157">使用 **ComputerName** 参数时，PowerShell 会创建一个新会话来运行该命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-157">When you use the **ComputerName** parameter, PowerShell creates a new session to run the command.</span></span>
<span data-ttu-id="fd6a2-158">命令完成后，会话将关闭。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-158">The session is closed when the command completes.</span></span> <span data-ttu-id="fd6a2-159">`$p`变量是在一个连接中创建的，但它在为第二个命令创建的连接中不存在。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-159">The `$p` variable was created in one connection, but it doesn't exist in the connection created for the second command.</span></span>

<span data-ttu-id="fd6a2-160">此问题的解决方法是：在远程计算机上创建一个持久会话，然后在同一会话中运行这两个命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-160">The problem is solved by creating a persistent session on the remote computer, then running both of the commands in the same session.</span></span>

<span data-ttu-id="fd6a2-161">该 `New-PSSession` cmdlet 会在计算机 Server02 上创建一个持久会话，并将会话保存在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-161">The `New-PSSession` cmdlet creates a persistent session on the computer Server02 and saves the session in the `$s` variable.</span></span> <span data-ttu-id="fd6a2-162">`Invoke-Command`接下来的行使用 **Session** 参数在同一会话中运行这两个命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-162">The `Invoke-Command` lines that follow use the **Session** parameter to run both of the commands in the same session.</span></span> <span data-ttu-id="fd6a2-163">由于两个命令在同一会话中运行，因此 `$p` 值保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-163">Since both commands run in the same session, the `$p` value remains active.</span></span>

### <span data-ttu-id="fd6a2-164">示例5：输入存储在局部变量中的命令</span><span class="sxs-lookup"><span data-stu-id="fd6a2-164">Example 5: Enter a command stored in a local variable</span></span>

<span data-ttu-id="fd6a2-165">此示例演示如何创建一个命令，该命令以脚本块的形式存储在本地变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-165">This example shows how to create a command that is stored as a script block in a local variable.</span></span>
<span data-ttu-id="fd6a2-166">当脚本块保存在本地变量中时，可以将该变量指定为 **ScriptBlock** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-166">When the script block is saved in a local variable, you can specify the variable as the value of the **ScriptBlock** parameter.</span></span>

```powershell
$command = { Get-EventLog -LogName "Windows PowerShell" |
  Where-Object {$_.Message -like "*certificate*"} }
Invoke-Command -ComputerName S1, S2 -ScriptBlock $command
```

<span data-ttu-id="fd6a2-167">`$command`变量存储 `Get-EventLog` 设置为脚本块格式的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-167">The `$command` variable stores the `Get-EventLog` command that's formatted as a script block.</span></span> <span data-ttu-id="fd6a2-168">`Invoke-Command`运行在 `$command` S1 和 S2 远程计算机上存储的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-168">The `Invoke-Command` runs the command stored in `$command` on the S1 and S2 remote computers.</span></span>

### <span data-ttu-id="fd6a2-169">示例6：在多台计算机上运行单个命令</span><span class="sxs-lookup"><span data-stu-id="fd6a2-169">Example 6: Run a single command on several computers</span></span>

<span data-ttu-id="fd6a2-170">此示例演示如何使用 `Invoke-Command` 在多台计算机上运行单个命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-170">This example demonstrates how to use `Invoke-Command` to run a single command on multiple computers.</span></span>

```powershell
$parameters = @{
  ComputerName = "Server01", "Server02", "TST-0143", "localhost"
  ConfigurationName = 'MySession.PowerShell'
  ScriptBlock = { Get-EventLog "Windows PowerShell" }
}
Invoke-Command @parameters
```

<span data-ttu-id="fd6a2-171">**ComputerName** 参数指定以逗号分隔的计算机名称列表。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-171">The **ComputerName** parameter specifies a comma-separated list of computer names.</span></span> <span data-ttu-id="fd6a2-172">计算机列表包括表示本地计算机的 "localhost" 值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-172">The list of computers includes the localhost value, which represents the local computer.</span></span> <span data-ttu-id="fd6a2-173">**ConfigurationName** 参数指定备用会话配置。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-173">The **ConfigurationName** parameter specifies an alternate session configuration.</span></span> <span data-ttu-id="fd6a2-174">**ScriptBlock** 参数将运行 `Get-EventLog` ，以获取每台计算机的 Windows PowerShell 事件日志。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-174">The **ScriptBlock** parameter runs `Get-EventLog` to get the Windows PowerShell event logs from each computer.</span></span>

### <span data-ttu-id="fd6a2-175">示例7：获取多台计算机上的主机程序版本</span><span class="sxs-lookup"><span data-stu-id="fd6a2-175">Example 7: Get the version of the host program on multiple computers</span></span>

<span data-ttu-id="fd6a2-176">此示例获取在200远程计算机上运行的 PowerShell 主机程序的版本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-176">This example gets the version of the PowerShell host program running on 200 remote computers.</span></span>

```powershell
$version = Invoke-Command -ComputerName (Get-Content Machines.txt) -ScriptBlock {(Get-Host).Version}
```

<span data-ttu-id="fd6a2-177">由于只运行一个命令，因此不需要创建与每台计算机的持久连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-177">Because only one command is run, you don't have to create persistent connections to each of the computers.</span></span> <span data-ttu-id="fd6a2-178">而是由此命令使用 **ComputerName** 参数来指示计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-178">Instead, the command uses the **ComputerName** parameter to indicate the computers.</span></span> <span data-ttu-id="fd6a2-179">若要指定计算机，它将使用 `Get-Content` cmdlet 来获取 Machine.txt 文件（计算机名称的文件）的内容。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-179">To specify the computers, it uses the `Get-Content` cmdlet to get the contents of the Machine.txt file, a file of computer names.</span></span>

<span data-ttu-id="fd6a2-180">`Invoke-Command`Cmdlet `Get-Host` 在远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-180">The `Invoke-Command` cmdlet runs a `Get-Host` command on the remote computers.</span></span> <span data-ttu-id="fd6a2-181">它使用点表示法来获取 PowerShell 主机的 **版本** 属性。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-181">It uses dot notation to get the **Version** property of the PowerShell host.</span></span>

<span data-ttu-id="fd6a2-182">这些命令一次运行一个。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-182">These commands run one at a time.</span></span> <span data-ttu-id="fd6a2-183">命令完成后，所有计算机的命令输出都将保存在 `$version` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-183">When the commands complete, the output of the commands from all of the computers is saved in the `$version` variable.</span></span> <span data-ttu-id="fd6a2-184">输出包括数据来源计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-184">The output includes the name of the computer from which the data originated.</span></span>

### <span data-ttu-id="fd6a2-185">示例8：在多台远程计算机上运行后台作业</span><span class="sxs-lookup"><span data-stu-id="fd6a2-185">Example 8: Run a background job on several remote computers</span></span>

<span data-ttu-id="fd6a2-186">此示例在两台远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-186">This example runs a command on two remote computers.</span></span> <span data-ttu-id="fd6a2-187">该 `Invoke-Command` 命令使用 **AsJob** 参数，以便该命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-187">The `Invoke-Command` command uses the **AsJob** parameter so that the command runs as a background job.</span></span> <span data-ttu-id="fd6a2-188">这些命令在远程计算机上运行，但该作业存在于本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-188">The commands run on the remote computers, but the job exists on the local computer.</span></span> <span data-ttu-id="fd6a2-189">结果传输到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-189">The results are transmitted to the local computer.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
Invoke-Command -Session $s -ScriptBlock {Get-EventLog system} -AsJob
```

```Output
Id   Name    State      HasMoreData   Location           Command
---  ----    -----      -----         -----------        ---------------
1    Job1    Running    True          Server01,Server02  Get-EventLog system
```

```powershell
$j = Get-Job
$j | Format-List -Property *
```

```Output
HasMoreData   : True
StatusMessage :
Location      : Server01,Server02
Command       : Get-EventLog system
JobStateInfo  : Running
Finished      : System.Threading.ManualResetEvent
InstanceId    : e124bb59-8cb2-498b-a0d2-2e07d4e030ca
Id            : 1
Name          : Job1
ChildJobs     : {Job2, Job3}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :
```

```powershell
$results = $j | Receive-Job
```

<span data-ttu-id="fd6a2-190">`New-PSSession`Cmdlet 将在 Server01 和 Server02 远程计算机上创建会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-190">The `New-PSSession` cmdlet creates sessions on the Server01 and Server02 remote computers.</span></span> <span data-ttu-id="fd6a2-191">`Invoke-Command`Cmdlet 在每个会话中运行一个后台作业。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-191">The `Invoke-Command` cmdlet runs a background job in each of the sessions.</span></span> <span data-ttu-id="fd6a2-192">该命令使用 **AsJob** 参数将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-192">The command uses the **AsJob** parameter to run the command as a background job.</span></span> <span data-ttu-id="fd6a2-193">此命令将返回一个包含两个子作业对象的作业对象，每个子作业对象分别对应于在两台远程计算机上运行的每个作业。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-193">This command returns a job object that contains two child job objects, one for each of the jobs run on the two remote computers.</span></span>

<span data-ttu-id="fd6a2-194">该 `Get-Job` 命令将作业对象保存在 `$j` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-194">The `Get-Job` command saves the job object in the `$j` variable.</span></span> <span data-ttu-id="fd6a2-195">然后，将 `$j` 变量传递给 `Format-List` cmdlet，以在列表中显示作业对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-195">The `$j` variable is then piped to the `Format-List` cmdlet to display all properties of the job object in a list.</span></span> <span data-ttu-id="fd6a2-196">最后一个命令将获取作业的结果。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-196">The last command gets the results of the jobs.</span></span> <span data-ttu-id="fd6a2-197">它通过管道将作业对象传递 `$j` 给 `Receive-Job` cmdlet，并将结果存储在 `$results` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-197">It pipes the job object in `$j` to the `Receive-Job` cmdlet and stores the results in the `$results` variable.</span></span>

### <span data-ttu-id="fd6a2-198">示例9：在远程计算机上运行的命令中包括局部变量</span><span class="sxs-lookup"><span data-stu-id="fd6a2-198">Example 9: Include local variables in a command run on a remote computer</span></span>

<span data-ttu-id="fd6a2-199">本示例显示了如何将局部变量的值包括在运行于远程计算机上的命令中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-199">This example shows how to include the values of local variables in a command run on a remote computer.</span></span> <span data-ttu-id="fd6a2-200">该命令使用 `Using` 作用域修饰符来标识远程命令中的局部变量。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-200">The command uses the `Using` scope modifier to identify a local variable in a remote command.</span></span> <span data-ttu-id="fd6a2-201">默认情况下，假定所有变量均已在远程会话中定义。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-201">By default, all variables are assumed to be defined in the remote session.</span></span> <span data-ttu-id="fd6a2-202">`Using`PowerShell 3.0 中引入了作用域修饰符。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-202">The `Using` scope modifier was introduced in PowerShell 3.0.</span></span> <span data-ttu-id="fd6a2-203">有关 `Using` 作用域修饰符的详细信息，请参阅 [about_Remote_Variables](./About/about_Remote_Variables.md) 和 [about_Scopes](./about/about_scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-203">For more information about the `Using` scope modifier, see [about_Remote_Variables](./About/about_Remote_Variables.md) and [about_Scopes](./about/about_scopes.md).</span></span>

```powershell
$Log = "Windows PowerShell"
Invoke-Command -ComputerName Server01 -ScriptBlock { Get-EventLog -LogName $Using:Log -Newest 10 }
```

<span data-ttu-id="fd6a2-204">`$Log`变量存储事件日志的名称 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-204">The `$Log` variable stores the name of the event log, Windows PowerShell.</span></span> <span data-ttu-id="fd6a2-205">`Invoke-Command`Cmdlet `Get-EventLog` 在 Server01 上运行，以获取事件日志中的10个最新事件。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-205">The `Invoke-Command` cmdlet runs `Get-EventLog` on Server01 to get the ten newest events from the event log.</span></span> <span data-ttu-id="fd6a2-206">**LogName** 参数的值是 `$Log` 变量，该变量的 `Using` 作用域修饰符以指示它是在本地会话中创建的，而不是在远程会话中创建的。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-206">The value of the **LogName** parameter is the `$Log` variable, which is prefixed by the `Using` scope modifier to indicate that it was created in the local session, not in the remote session.</span></span>

### <span data-ttu-id="fd6a2-207">示例10：隐藏计算机名称</span><span class="sxs-lookup"><span data-stu-id="fd6a2-207">Example 10: Hide the computer name</span></span>

<span data-ttu-id="fd6a2-208">此示例演示使用的 **HideComputerName** 参数的效果 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-208">This example shows the effect of using the **HideComputerName** parameter of `Invoke-Command`.</span></span>
<span data-ttu-id="fd6a2-209">**HideComputerName** 不会更改此 cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-209">**HideComputerName** doesn't change the object that this cmdlet returns.</span></span> <span data-ttu-id="fd6a2-210">它仅更改显示。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-210">It changes only the display.</span></span> <span data-ttu-id="fd6a2-211">你仍可以使用 **Format** cmdlet 显示任何受影响的对象的 **PsComputerName** 属性。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-211">You can still use the **Format** cmdlets to display the **PsComputerName** property of any of the affected objects.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell}
```

```Output
PSComputerName    Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
--------------    -------  ------    -----      ----- -----   ------     --   -----------
S1                575      15        45100      40988   200     4.68     1392 PowerShell
S2                777      14        35100      30988   150     3.68     67   PowerShell
```

```powershell
Invoke-Command -ComputerName S1, S2 -ScriptBlock {Get-Process PowerShell} -HideComputerName
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id   ProcessName
-------  ------    -----      ----- -----   ------     --   -----------
575      15        45100      40988   200     4.68     1392 PowerShell
777      14        35100      30988   150     3.68     67   PowerShell
```

<span data-ttu-id="fd6a2-212">前两个命令用于为 `Invoke-Command` `Get-Process` PowerShell 进程运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-212">The first two commands use `Invoke-Command` to run a `Get-Process` command for the PowerShell process.</span></span> <span data-ttu-id="fd6a2-213">第一个命令的输出包括 **PsComputerName** 属性，此属性包含运行该命令的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-213">The output of the first command includes the **PsComputerName** property, which contains the name of the computer on which the command ran.</span></span> <span data-ttu-id="fd6a2-214">使用 **HideComputerName** 的第二个命令的输出不包括 **PsComputerName** 列。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-214">The output of the second command, which uses **HideComputerName** , doesn't include the **PsComputerName** column.</span></span>

### <span data-ttu-id="fd6a2-215">示例11：在脚本块中使用 Param 关键字</span><span class="sxs-lookup"><span data-stu-id="fd6a2-215">Example 11: Use the Param keyword in a script block</span></span>

<span data-ttu-id="fd6a2-216">`Param`关键字和 **ArgumentList** 参数用于将变量值传递到脚本块中的命名参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-216">The `Param` keyword and the **ArgumentList** parameter are used to pass variable values to named parameters in a script block.</span></span> <span data-ttu-id="fd6a2-217">此示例显示以字母开头 `a` 并具有扩展名的文件名 `.pdf` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-217">This example displays filenames that begin with the letter `a` and have the `.pdf` extension.</span></span>

<span data-ttu-id="fd6a2-218">有关关键字的详细信息 `Param` ，请参阅 [about_Language_Keywords](./about/about_language_keywords.md#param)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-218">For more information about the `Param` keyword, see [about_Language_Keywords](./about/about_language_keywords.md#param).</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Param ($param1,$param2) Get-ChildItem -Name $param1 -Include $param2 }
    ArgumentList = "a*", "*.pdf"
}
Invoke-Command @parameters
```

```Output
aa.pdf
ab.pdf
ac.pdf
az.pdf
```

<span data-ttu-id="fd6a2-219">`Invoke-Command` 使用定义两个变量的 **ScriptBlock** 参数 `$param1` 和 `$param2` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-219">`Invoke-Command` uses the **ScriptBlock** parameter that defines two variables, `$param1` and `$param2`.</span></span> <span data-ttu-id="fd6a2-220">`Get-ChildItem` 使用命名参数、 **名称** 和 **包含** 变量名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-220">`Get-ChildItem` uses the named parameters, **Name** and **Include** with the variable names.</span></span> <span data-ttu-id="fd6a2-221">**ArgumentList** 将值传递给这些变量。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-221">The **ArgumentList** passes the values to the variables.</span></span>

### <span data-ttu-id="fd6a2-222">示例12：使用脚本块中的 $args 自动变量</span><span class="sxs-lookup"><span data-stu-id="fd6a2-222">Example 12: Use the $args automatic variable in a script block</span></span>

<span data-ttu-id="fd6a2-223">`$args`自动变量和 **ArgumentList** 参数用于将数组值传递到脚本块中的参数位置。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-223">The `$args` automatic variable and the **ArgumentList** parameter are used to pass array values to parameter positions in a script block.</span></span> <span data-ttu-id="fd6a2-224">此示例显示服务器的目录内容 `.txt` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-224">This example displays a server's directory contents of `.txt` files.</span></span> <span data-ttu-id="fd6a2-225">`Get-ChildItem` **Path** 参数的位置为0， **筛选器** 参数为 position</span><span class="sxs-lookup"><span data-stu-id="fd6a2-225">The `Get-ChildItem` **Path** parameter is position 0 and the **Filter** parameter is position</span></span>
1.

<span data-ttu-id="fd6a2-226">有关变量的详细信息 `$args` ，请参阅 [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span><span class="sxs-lookup"><span data-stu-id="fd6a2-226">For more information about the `$args` variable, see [about_Automatic_Variables](./about/about_automatic_variables.md#args)</span></span>

```powershell
$parameters = @{
    ComputerName = "Server01"
    ScriptBlock = { Get-ChildItem $args[0] $args[1] }
    ArgumentList = "C:\Test", "*.txt*"
}
Invoke-Command @parameters
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           6/12/2019    15:15            128 alog.txt
-a---           7/27/2019    15:16            256 blog.txt
-a---           9/28/2019    17:10             64 zlog.txt
```

<span data-ttu-id="fd6a2-227">`Invoke-Command` 使用 **ScriptBlock** 参数并 `Get-ChildItem` 指定 `$args[0]` 和 `$args[1]` 数组值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-227">`Invoke-Command` uses a **ScriptBlock** parameter and `Get-ChildItem` specifies the `$args[0]` and `$args[1]` array values.</span></span> <span data-ttu-id="fd6a2-228">**ArgumentList** 将 `$args` 数组值传递给 `Get-ChildItem` **Path** 和 **Filter** 的参数位置。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-228">The **ArgumentList** passes the `$args` array values to the `Get-ChildItem` parameter positions for **Path** and **Filter** .</span></span>

### <span data-ttu-id="fd6a2-229">示例13：在文本文件中列出的所有计算机上运行脚本</span><span class="sxs-lookup"><span data-stu-id="fd6a2-229">Example 13: Run a script on all the computers listed in a text file</span></span>

<span data-ttu-id="fd6a2-230">此示例使用 `Invoke-Command` cmdlet `Sample.ps1` 在文件中列出的所有计算机上运行该脚本 `Servers.txt` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-230">This example uses the `Invoke-Command` cmdlet to run the `Sample.ps1` script on all the computers listed in the `Servers.txt` file.</span></span> <span data-ttu-id="fd6a2-231">该命令使用 **FilePath** 参数来指定脚本文件。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-231">The command uses the **FilePath** parameter to specify the script file.</span></span> <span data-ttu-id="fd6a2-232">利用此命令，你可以在远程计算机上运行脚本，即使远程计算机无法访问脚本文件也是如此。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-232">This command lets you run the script on the remote computers, even if the script file isn't accessible to the remote computers.</span></span>

```powershell
Invoke-Command -ComputerName (Get-Content Servers.txt) -FilePath C:\Scripts\Sample.ps1 -ArgumentList Process, Service
```

<span data-ttu-id="fd6a2-233">提交该命令时，该文件的内容 `Sample.ps1` 将复制到脚本块中，并且脚本块将在每台远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-233">When you submit the command, the content of the `Sample.ps1` file is copied into a script block and the script block is run on each of the remote computers.</span></span> <span data-ttu-id="fd6a2-234">此步骤等效于使用 **ScriptBlock** 参数来提交脚本的内容。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-234">This procedure is equivalent to using the **ScriptBlock** parameter to submit the contents of the script.</span></span>

### <span data-ttu-id="fd6a2-235">示例14：使用 URI 在远程计算机上运行命令</span><span class="sxs-lookup"><span data-stu-id="fd6a2-235">Example 14: Run a command on a remote computer using a URI</span></span>

<span data-ttu-id="fd6a2-236">此示例演示如何在由 (URI) 的统一资源标识符标识的远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-236">This example shows how to run a command on a remote computer that's identified by a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="fd6a2-237">此特定示例 `Set-Mailbox` 在远程 Exchange 服务器上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-237">This particular example runs a `Set-Mailbox` command on a remote Exchange server.</span></span>

```powershell
$LiveCred = Get-Credential
$parameters = @{
  ConfigurationName = 'Microsoft.Exchange'
  ConnectionUri = 'https://ps.exchangelabs.com/PowerShell'
  Credential = $LiveCred
  Authentication = 'Basic'
  ScriptBlock = {Set-Mailbox Dan -DisplayName "Dan Park"}
}
Invoke-Command @parameters
```

<span data-ttu-id="fd6a2-238">第一行使用 cmdlet 将 `Get-Credential` Windows LIVE ID 凭据存储在 `$LiveCred` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-238">The first line uses the `Get-Credential` cmdlet to store Windows Live ID credentials in the `$LiveCred` variable.</span></span> <span data-ttu-id="fd6a2-239">PowerShell 会提示用户输入 Windows Live ID 凭据。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-239">PowerShell prompts the user to enter Windows Live ID credentials.</span></span>

<span data-ttu-id="fd6a2-240">`$parameters`变量是包含要传递到 cmdlet 的参数的哈希表 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-240">The `$parameters` variable is a hash table containing the parameters to be passed to the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="fd6a2-241">`Invoke-Command`Cmdlet `Set-Mailbox` 使用 **Microsoft. Exchange** 会话配置运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-241">The `Invoke-Command` cmdlet runs a `Set-Mailbox` command using the **Microsoft.Exchange** session configuration.</span></span> <span data-ttu-id="fd6a2-242">**ConnectionURI** 参数指定 Exchange 服务器终结点的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-242">The **ConnectionURI** parameter specifies the URL of the Exchange server endpoint.</span></span> <span data-ttu-id="fd6a2-243">**Credential** 参数指定变量中存储的凭据 `$LiveCred` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-243">The **Credential** parameter specifies the credentials stored in the `$LiveCred` variable.</span></span> <span data-ttu-id="fd6a2-244">**AuthenticationMechanism** 参数指定基本身份验证的使用。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-244">The **AuthenticationMechanism** parameter specifies the use of basic authentication.</span></span> <span data-ttu-id="fd6a2-245">**ScriptBlock** 参数指定包含该命令的脚本块。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-245">The **ScriptBlock** parameter specifies a script block that contains the command.</span></span>

### <span data-ttu-id="fd6a2-246">示例15：使用 session 选项</span><span class="sxs-lookup"><span data-stu-id="fd6a2-246">Example 15: Use a session option</span></span>

<span data-ttu-id="fd6a2-247">此示例演示如何创建和使用 **SessionOption** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-247">This example shows how to create and use a **SessionOption** parameter.</span></span>

```powershell
$so = New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck
Invoke-Command -ComputerName server01 -UseSSL -ScriptBlock { Get-HotFix } -SessionOption $so -Credential server01\user01
```

<span data-ttu-id="fd6a2-248">`New-PSSessionOption`Cmdlet 创建一个会话选项对象，该对象会导致远程端在评估传入 HTTPS 连接时不会验证证书颁发机构、规范名称和吊销列表。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-248">The `New-PSSessionOption` cmdlet creates a session option object that causes the remote end not to verify the Certificate Authority, Canonical Name, and Revocation Lists while evaluating the incoming HTTPS connection.</span></span> <span data-ttu-id="fd6a2-249">**SessionOption** 对象保存在 `$so` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-249">The **SessionOption** object is saved in the `$so` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="fd6a2-250">禁用这些检查有助于进行故障排除，但明显并不安全。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-250">Disabling these checks is convenient for troubleshooting, but obviously not secure.</span></span>

<span data-ttu-id="fd6a2-251">`Invoke-Command`Cmdlet 用于远程运行 `Get-HotFix` 命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-251">The `Invoke-Command` cmdlet runs a `Get-HotFix` command remotely.</span></span> <span data-ttu-id="fd6a2-252">为 **SessionOption** 参数提供 `$so` 变量。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-252">The **SessionOption** parameter is given the `$so` variable.</span></span>

### <span data-ttu-id="fd6a2-253">示例16：在远程命令中管理 URI 重定向</span><span class="sxs-lookup"><span data-stu-id="fd6a2-253">Example 16: Manage URI redirection in a remote command</span></span>

<span data-ttu-id="fd6a2-254">此示例演示如何在远程命令中使用 **AllowRedirection** 和 **SESSIONOPTION** 参数管理 URI 重定向。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-254">This example shows how to use the **AllowRedirection** and **SessionOption** parameters to manage URI redirection in a remote command.</span></span>

```powershell
$max = New-PSSessionOption -MaximumRedirection 1
$parameters = @{
  ConnectionUri = "https://ps.exchangelabs.com/PowerShell"
  ScriptBlock = { Get-Mailbox dan }
  AllowRedirection = $true
  SessionOption = $max
}
Invoke-Command @parameters
```

<span data-ttu-id="fd6a2-255">`New-PSSessionOption`Cmdlet 将创建一个保存在变量中的 **PSSessionOption** 对象 `$max` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-255">The `New-PSSessionOption` cmdlet creates a **PSSessionOption** object that is saved in the `$max` variable.</span></span> <span data-ttu-id="fd6a2-256">该命令使用 **MaximumRedirection** 参数将 **PSSessionOption** 对象的 **MaximumConnectionRedirectionCount** 属性设置为 1。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-256">The command uses the **MaximumRedirection** parameter to set the **MaximumConnectionRedirectionCount** property of the **PSSessionOption** object to 1.</span></span>

<span data-ttu-id="fd6a2-257">`Invoke-Command`Cmdlet `Get-Mailbox` 在远程 Microsoft Exchange 服务器上运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-257">The `Invoke-Command` cmdlet runs a `Get-Mailbox` command on a remote Microsoft Exchange Server.</span></span> <span data-ttu-id="fd6a2-258">**AllowRedirection** 参数提供了用于将连接重定向到备用终结点的显式权限。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-258">The **AllowRedirection** parameter provides explicit permission to redirect the connection to an alternate endpoint.</span></span> <span data-ttu-id="fd6a2-259">**SessionOption** 参数使用变量中存储的会话对象 `$max` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-259">The **SessionOption** parameter uses the session object stored in the `$max` variable.</span></span>

<span data-ttu-id="fd6a2-260">因此，如果 **ConnectionURI** 指定的远程计算机返回重定向消息，则 PowerShell 将重定向连接，但如果新目标返回另一个重定向消息，则将超出重定向计数值1，并 `Invoke-Command` 返回一个非终止错误。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-260">As a result, if the remote computer specified by **ConnectionURI** returns a redirection message, PowerShell redirects the connection, but if the new destination returns another redirection message, the redirection count value of 1 is exceeded, and `Invoke-Command` returns a non-terminating error.</span></span>

### <span data-ttu-id="fd6a2-261">示例17：访问远程会话中的网络共享</span><span class="sxs-lookup"><span data-stu-id="fd6a2-261">Example 17: Access a network share in a remote session</span></span>

<span data-ttu-id="fd6a2-262">此示例演示如何从远程会话访问网络共享。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-262">This example shows how to access a network share from a remote session.</span></span> <span data-ttu-id="fd6a2-263">三台计算机用于演示示例。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-263">Three computers are used to demonstrate the example.</span></span> <span data-ttu-id="fd6a2-264">Server01 是本地计算机，Server02 是远程计算机，Net03 包含网络共享。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-264">Server01 is the local computer, Server02 is the remote computer, and Net03 contains the network share.</span></span> <span data-ttu-id="fd6a2-265">Server01 连接到 Server02，然后 Server02 执行第二个跃点以访问网络共享。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-265">Server01 connects to Server02, and then Server02 does a second hop to Net03 to access the network share.</span></span> <span data-ttu-id="fd6a2-266">有关 PowerShell 远程处理如何支持计算机之间的跃点的详细信息，请参阅 [在 PowerShell 远程处理中创建第二个跃点](/powershell/scripting/learn/remoting/ps-remoting-second-hop)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-266">For more information about how PowerShell Remoting supports hops between computers, see [Making the second hop in PowerShell Remoting](/powershell/scripting/learn/remoting/ps-remoting-second-hop).</span></span>

<span data-ttu-id="fd6a2-267">在本地计算机上的客户端设置中以及远程计算机上的服务设置中启用了所需的凭据安全支持提供程序 (CredSSP) 委托。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-267">The required Credential Security Support Provider (CredSSP) delegation is enabled in the client settings on the local computer, and in the service settings on the remote computer.</span></span> <span data-ttu-id="fd6a2-268">若要运行此示例中的命令，您必须是本地计算机和远程计算机上的 **Administrators** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-268">To run the commands in this example, you must be a member of the **Administrators** group on the local computer and the remote computer.</span></span>

```powershell
Enable-WSManCredSSP -Role Client -DelegateComputer Server02
$s = New-PSSession Server02
Invoke-Command -Session $s -ScriptBlock {Enable-WSManCredSSP -Role Server -Force}
$parameters = @{
  Session = $s
  ScriptBlock = { Get-Item \\Net03\Scripts\LogFiles.ps1 }
  Authentication = "CredSSP"
  Credential = "Domain01\Admin01"
}
Invoke-Command @parameters
```

<span data-ttu-id="fd6a2-269">`Enable-WSManCredSSP`Cmdlet 可启用从 Server01 本地计算机到 Server02 远程计算机的 CredSSP 委托。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-269">The `Enable-WSManCredSSP` cmdlet enables CredSSP delegation from the Server01 local computer to the Server02 remote computer.</span></span> <span data-ttu-id="fd6a2-270">**Role** 参数指定 **客户端** 以在本地计算机上配置 CredSSP 客户端设置。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-270">The **Role** parameter specifies **Client** to configure the CredSSP client setting on the local computer.</span></span>

<span data-ttu-id="fd6a2-271">`New-PSSession` 创建 Server02 的 **PSSession** 对象并将该对象存储在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-271">`New-PSSession` creates a **PSSession** object for Server02 and stores the object in the `$s` variable.</span></span>

<span data-ttu-id="fd6a2-272">`Invoke-Command`Cmdlet 使用该 `$s` 变量连接到远程计算机 Server02。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-272">The `Invoke-Command` cmdlet uses the `$s` variable to connect to the remote computer, Server02.</span></span> <span data-ttu-id="fd6a2-273">**ScriptBlock** 参数 `Enable-WSManCredSSP` 在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-273">The **ScriptBlock** parameter runs `Enable-WSManCredSSP` on the remote computer.</span></span> <span data-ttu-id="fd6a2-274">**Role** 参数指定 **服务器** 以在远程计算机上配置 CredSSP 服务器设置。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-274">The **Role** parameter specifies **Server** to configure the CredSSP server setting on the remote computer.</span></span>

<span data-ttu-id="fd6a2-275">`$parameters`变量包含用于连接到网络共享的参数值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-275">The `$parameters` variable contains the parameter values to connect to the network share.</span></span> <span data-ttu-id="fd6a2-276">`Invoke-Command`Cmdlet `Get-Item` 在中的会话中运行命令 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-276">The `Invoke-Command` cmdlet runs a `Get-Item` command in the session in `$s`.</span></span> <span data-ttu-id="fd6a2-277">此命令从网络共享获取脚本 `\\Net03\Scripts` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-277">This command gets a script from the `\\Net03\Scripts` network share.</span></span> <span data-ttu-id="fd6a2-278">该命令使用值为 **CredSSP** 的 **Authentication** 参数，并使用值为 **Domain01\Admin01** 的 **Credential** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-278">The command uses the **Authentication** parameter with a value of **CredSSP** and the **Credential** parameter with a value of **Domain01\Admin01** .</span></span>

### <span data-ttu-id="fd6a2-279">示例18：在多台远程计算机上启动脚本</span><span class="sxs-lookup"><span data-stu-id="fd6a2-279">Example 18: Start scripts on many remote computers</span></span>

<span data-ttu-id="fd6a2-280">此示例在一百多台计算机上运行脚本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-280">This example runs a script on more than a hundred computers.</span></span> <span data-ttu-id="fd6a2-281">若要最大程度地降低对本地计算机的影响，它会连接到每台计算机、启动脚本，然后从每台计算机断开连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-281">To minimize the impact on the local computer, it connects to each computer, starts the script, and then disconnects from each computer.</span></span>
<span data-ttu-id="fd6a2-282">脚本将继续在断开连接的会话中运行。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-282">The script continues to run in the disconnected sessions.</span></span>

```powershell
$parameters = @{
  ComputerName = (Get-Content -Path C:\Test\Servers.txt)
  InDisconnectedSession = $true
  FilePath = "\\Scripts\Public\ConfigInventory.ps1"
  SessionOption = @{OutputBufferingMode="Drop";IdleTimeout=43200000}
}
Invoke-Command @parameters
```

<span data-ttu-id="fd6a2-283">命令使用 `Invoke-Command` 来运行脚本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-283">The command uses `Invoke-Command` to run the script.</span></span> <span data-ttu-id="fd6a2-284">**ComputerName** 参数的值是一个 `Get-Content` 命令，该命令从文本文件获取远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-284">The value of the **ComputerName** parameter is a `Get-Content` command that gets the names of the remote computers from a text file.</span></span> <span data-ttu-id="fd6a2-285">**InDisconnectedSession** 参数将在启动该命令后立即断开与会话的连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-285">The **InDisconnectedSession** parameter disconnects the sessions as soon as it starts the command.</span></span> <span data-ttu-id="fd6a2-286">**FilePath** 参数的值是 `Invoke-Command` 在每台计算机上运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-286">The value of the **FilePath** parameter is the script that `Invoke-Command` runs on each computer.</span></span>

<span data-ttu-id="fd6a2-287">**SessionOption** 的值是一个哈希表。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-287">The value of **SessionOption** is a hash table.</span></span> <span data-ttu-id="fd6a2-288">**OutputBufferingMode** 值设置为 **Drop** ，并且 **IdleTimeout** 值设置为 **43200000** 毫秒 (12 小时) 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-288">The **OutputBufferingMode** value is set to **Drop** and the **IdleTimeout** value is set to **43200000** milliseconds (12 hours).</span></span>

<span data-ttu-id="fd6a2-289">若要获取在断开连接的会话中运行的命令和脚本的结果，请使用 `Receive-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-289">To get the results of commands and scripts that run in disconnected sessions, use the `Receive-PSSession` cmdlet.</span></span>

## <span data-ttu-id="fd6a2-290">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd6a2-290">PARAMETERS</span></span>

### <span data-ttu-id="fd6a2-291">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="fd6a2-291">-AllowRedirection</span></span>

<span data-ttu-id="fd6a2-292">允许将此连接重定向到备用统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-292">Allows redirection of this connection to an alternate Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="fd6a2-293">使用 **ConnectionURI** 参数时，远程目标将返回一个指令，以重定向到不同的 URI。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-293">When you use the **ConnectionURI** parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="fd6a2-294">默认情况下，PowerShell 不会重定向连接，但你可以使用此参数允许它重定向连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-294">By default, PowerShell doesn't redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="fd6a2-295">你也可以通过更改 **MaximumConnectionRedirectionCount** 会话选项值，限制重定向连接的次数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-295">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span> <span data-ttu-id="fd6a2-296">使用 cmdlet 的 **MaximumRedirection** 参数 `New-PSSessionOption` 或设置首选项变量的 **MaximumConnectionRedirectionCount** 属性 `$PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-296">Use the **MaximumRedirection** parameter of the `New-PSSessionOption` cmdlet or set the **MaximumConnectionRedirectionCount** property of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="fd6a2-297">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-297">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-298">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-298">-ApplicationName</span></span>

<span data-ttu-id="fd6a2-299">指定连接 URI 的应用程序名称段。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-299">Specifies the application name segment of the connection URI.</span></span> <span data-ttu-id="fd6a2-300">当你未在命令中使用 **ConnectionURI** 参数时，请使用此参数指定应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-300">Use this parameter to specify the application name when you aren't using the **ConnectionURI** parameter in the command.</span></span>

<span data-ttu-id="fd6a2-301">默认值为 `$PSSessionApplicationName` 本地计算机上首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-301">The default value is the value of the `$PSSessionApplicationName` preference variable on the local computer.</span></span> <span data-ttu-id="fd6a2-302">如果未定义此首选项变量，则默认值为 WSMAN。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-302">If this preference variable isn't defined, the default value is WSMAN.</span></span> <span data-ttu-id="fd6a2-303">该值适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-303">This value is appropriate for most uses.</span></span> <span data-ttu-id="fd6a2-304">有关详细信息，请参阅 [about_Preference_Variables](./About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-304">For more information, see [about_Preference_Variables](./About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="fd6a2-305">WinRM 服务使用应用程序名称来选择为连接请求提供服务的侦听器。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-305">The WinRM service uses the application name to select a listener to service the connection request.</span></span>
<span data-ttu-id="fd6a2-306">此参数的值应与远程计算机上的侦听器的 **URLPrefix** 属性值匹配。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-306">The value of this parameter should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: $PSSessionApplicationName if set on the local computer, otherwise WSMAN
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-307">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="fd6a2-307">-ArgumentList</span></span>

<span data-ttu-id="fd6a2-308">提供命令中的局部变量的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-308">Supplies the values of local variables in the command.</span></span> <span data-ttu-id="fd6a2-309">在远程计算机上运行命令之前，该命令中的变量将替换为这些值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-309">The variables in the command are replaced by these values before the command is run on the remote computer.</span></span> <span data-ttu-id="fd6a2-310">以逗号分隔的列表形式输入值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-310">Enter the values in a comma-separated list.</span></span> <span data-ttu-id="fd6a2-311">值按其列出顺序与变量关联。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-311">Values are associated with variables in the order that they're listed.</span></span> <span data-ttu-id="fd6a2-312">**ArgumentList** 的别名为 Args。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-312">The alias for **ArgumentList** is Args.</span></span>

<span data-ttu-id="fd6a2-313">**ArgumentList** 参数中的值可以是实际值（例如1024），也可以是对局部变量（如）的引用 `$max` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-313">The values in the **ArgumentList** parameter can be actual values, such as 1024, or they can be references to local variables, such as `$max`.</span></span>

<span data-ttu-id="fd6a2-314">若要在命令中使用局部变量，请使用以下命令格式：</span><span class="sxs-lookup"><span data-stu-id="fd6a2-314">To use local variables in a command, use the following command format:</span></span>

<span data-ttu-id="fd6a2-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` - 或 - `<local-variable>`</span><span class="sxs-lookup"><span data-stu-id="fd6a2-315">`{param($<name1>[, $<name2>]...) <command-with-local-variables>} -ArgumentList <value>` -or- `<local-variable>`</span></span>

<span data-ttu-id="fd6a2-316">**Param** 关键字列出命令中使用的局部变量。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-316">The **param** keyword lists the local variables that are used in the command.</span></span> <span data-ttu-id="fd6a2-317">**ArgumentList** 按它们列出的顺序提供变量的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-317">**ArgumentList** supplies the values of the variables, in the order that they're listed.</span></span> <span data-ttu-id="fd6a2-318">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-318">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-319">-AsJob</span><span class="sxs-lookup"><span data-stu-id="fd6a2-319">-AsJob</span></span>

<span data-ttu-id="fd6a2-320">指示此 cmdlet 在远程计算机上将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-320">Indicates that this cmdlet runs the command as a background job on a remote computer.</span></span> <span data-ttu-id="fd6a2-321">使用此参数可运行需要很长时间才能完成的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-321">Use this parameter to run commands that take an extensive time to finish.</span></span>

<span data-ttu-id="fd6a2-322">使用 **AsJob** 参数时，该命令将返回一个表示作业的对象，然后显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-322">When you use the **AsJob** parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span> <span data-ttu-id="fd6a2-323">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-323">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="fd6a2-324">若要管理作业，请使用 `*-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-324">To manage the job, use the `*-Job` cmdlets.</span></span> <span data-ttu-id="fd6a2-325">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-325">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="fd6a2-326">**AsJob** 参数类似于使用 `Invoke-Command` cmdlet 来 `Start-Job` 远程运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-326">The **AsJob** parameter resembles using the `Invoke-Command` cmdlet to run a `Start-Job` cmdlet remotely.</span></span> <span data-ttu-id="fd6a2-327">但是，对于 **AsJob** ，作业是在本地计算机上创建的，即使作业运行在远程计算机上也是如此。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-327">However, with **AsJob** , the job is created on the local computer, even though the job runs on a remote computer.</span></span> <span data-ttu-id="fd6a2-328">远程作业的结果将自动返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-328">The results of the remote job are automatically returned to the local computer.</span></span>

<span data-ttu-id="fd6a2-329">有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](About/about_Jobs.md) 和 [about_Remote_Jobs](About/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-329">For more information about PowerShell background jobs, see [about_Jobs](About/about_Jobs.md) and [about_Remote_Jobs](About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-330">-Authentication</span><span class="sxs-lookup"><span data-stu-id="fd6a2-330">-Authentication</span></span>

<span data-ttu-id="fd6a2-331">指定用于对用户凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-331">Specifies the mechanism that's used to authenticate the user's credentials.</span></span> <span data-ttu-id="fd6a2-332">CredSSP 身份验证仅在 Windows Vista、Windows Server 2008 和更高版本的 Windows 操作系统中可用。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-332">CredSSP authentication is available only in Windows Vista, Windows Server 2008, and later versions of the Windows operating system.</span></span>

<span data-ttu-id="fd6a2-333">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="fd6a2-333">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="fd6a2-334">默认</span><span class="sxs-lookup"><span data-stu-id="fd6a2-334">Default</span></span>
- <span data-ttu-id="fd6a2-335">基本</span><span class="sxs-lookup"><span data-stu-id="fd6a2-335">Basic</span></span>
- <span data-ttu-id="fd6a2-336">Credssp</span><span class="sxs-lookup"><span data-stu-id="fd6a2-336">Credssp</span></span>
- <span data-ttu-id="fd6a2-337">摘要</span><span class="sxs-lookup"><span data-stu-id="fd6a2-337">Digest</span></span>
- <span data-ttu-id="fd6a2-338">Kerberos</span><span class="sxs-lookup"><span data-stu-id="fd6a2-338">Kerberos</span></span>
- <span data-ttu-id="fd6a2-339">Negotiate</span><span class="sxs-lookup"><span data-stu-id="fd6a2-339">Negotiate</span></span>
- <span data-ttu-id="fd6a2-340">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="fd6a2-340">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="fd6a2-341">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-341">The default value is Default.</span></span>

<span data-ttu-id="fd6a2-342">有关此参数的值的详细信息，请参阅 [System.management.automation.runspaces.authenticationmechanism 枚举](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-342">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="fd6a2-343">在凭据安全支持提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-343">Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="fd6a2-344">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-344">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="fd6a2-345">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-345">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span> <span data-ttu-id="fd6a2-346">有关详细信息，请参阅 [凭据安全支持提供程序](/windows/win32/secauthn/credential-security-support-provider)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-346">For more information, see [Credential Security Support Provider](/windows/win32/secauthn/credential-security-support-provider).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-347">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="fd6a2-347">-CertificateThumbprint</span></span>

<span data-ttu-id="fd6a2-348">指定有权连接到断开连接的会话的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-348">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="fd6a2-349">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-349">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="fd6a2-350">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-350">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="fd6a2-351">它们只能映射到本地用户帐户，而不能与域帐户一起使用。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-351">They can be mapped only to local user accounts and they don't work with domain accounts.</span></span>

<span data-ttu-id="fd6a2-352">若要获取证书指纹，请 `Get-Item` `Get-ChildItem` 在 PowerShell Cert：驱动器中使用或命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-352">To get a certificate thumbprint, use a `Get-Item` or `Get-ChildItem` command in the PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, Uri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-353">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-353">-ComputerName</span></span>

<span data-ttu-id="fd6a2-354">指定运行该命令的计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-354">Specifies the computers on which the command runs.</span></span> <span data-ttu-id="fd6a2-355">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-355">The default is the local computer.</span></span>

<span data-ttu-id="fd6a2-356">使用 **ComputerName** 参数时，PowerShell 会创建一个临时连接，此连接仅用于运行指定的命令，然后关闭。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-356">When you use the **ComputerName** parameter, PowerShell creates a temporary connection that's used only to run the specified command and is then closed.</span></span> <span data-ttu-id="fd6a2-357">如果需要持续性连接，请使用 **Session** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-357">If you need a persistent connection, use the **Session** parameter.</span></span>

<span data-ttu-id="fd6a2-358">在一个逗号分隔列表中键入一台或多台计算机的 NETBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-358">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="fd6a2-359">若要指定本地计算机，请键入计算机名、localhost 或 () 的点 `.` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-359">To specify the local computer, type the computer name, localhost, or a dot (`.`).</span></span>

<span data-ttu-id="fd6a2-360">若要在 **ComputerName** 的值中使用 IP 地址，该命令必须包括 **Credential** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-360">To use an IP address in the value of **ComputerName** , the command must include the **Credential** parameter.</span></span> <span data-ttu-id="fd6a2-361">必须为计算机配置 HTTPS 传输，或者必须在本地计算机的 WinRM **TrustedHosts** 列表中包含远程计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-361">The computer must be configured for the HTTPS transport or the IP address of the remote computer must be included in the local computer's WinRM **TrustedHosts** list.</span></span> <span data-ttu-id="fd6a2-362">有关将计算机名称添加到 **TrustedHosts** 列表的说明，请参阅 [如何将计算机添加到受信任的主机列表](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-362">For instructions to add a computer name to the **TrustedHosts** list, see [How to Add a Computer to the Trusted Host List](./about/about_remote_troubleshooting.md#how-to-add-a-computer-to-the-trusted-hosts-list).</span></span>

<span data-ttu-id="fd6a2-363">在 Windows Vista 和更高版本的 Windows 操作系统上，若要将本地计算机包含在 **ComputerName** 的值中，则必须使用 "以 **管理员身份运行** " 选项运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-363">On Windows Vista and later versions of the Windows operating system, to include the local computer in the value of **ComputerName** , you must run PowerShell using the **Run as administrator** option.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases: Cn

Required: False
Position: 0
Default value: Local computer
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-364">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-364">-ConfigurationName</span></span>

<span data-ttu-id="fd6a2-365">指定用于新的 **PSSession** 的会话配置。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-365">Specifies the session configuration that is used for the new **PSSession** .</span></span>

<span data-ttu-id="fd6a2-366">输入会话配置的配置名称或完全限定的资源 URI。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-366">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span> <span data-ttu-id="fd6a2-367">如果只指定配置名称，则会预置以下架构 URI： `http://schemas.microsoft.com/PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-367">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/PowerShell`.</span></span>

<span data-ttu-id="fd6a2-368">会话的会话配置位于远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-368">The session configuration for a session is located on the remote computer.</span></span> <span data-ttu-id="fd6a2-369">如果远程计算机上不存在指定的会话配置，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-369">If the specified session configuration doesn't exist on the remote computer, the command fails.</span></span>

<span data-ttu-id="fd6a2-370">默认值为 `$PSSessionConfigurationName` 本地计算机上首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-370">The default value is the value of the `$PSSessionConfigurationName` preference variable on the local computer.</span></span> <span data-ttu-id="fd6a2-371">如果未设置此首选项变量，则默认值为 " **Microsoft PowerShell** "。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-371">If this preference variable isn't set, the default is **Microsoft.PowerShell** .</span></span> <span data-ttu-id="fd6a2-372">有关详细信息，请参阅 [about_Preference_Variables](about/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-372">For more information, see [about_Preference_Variables](about/about_Preference_Variables.md).</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: $PSSessionConfigurationName if set on the local computer, otherwise Microsoft.PowerShell
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-373">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="fd6a2-373">-ConnectionUri</span></span>

<span data-ttu-id="fd6a2-374">指定定义会话的连接终结点的统一资源标识符 (URI)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-374">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint of the session.</span></span>
<span data-ttu-id="fd6a2-375">URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-375">The URI must be fully qualified.</span></span>

<span data-ttu-id="fd6a2-376">此字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="fd6a2-376">The format of this string is as follows:</span></span>

`<Transport>://<ComputerName>:<Port>/<ApplicationName>`

<span data-ttu-id="fd6a2-377">默认值如下：</span><span class="sxs-lookup"><span data-stu-id="fd6a2-377">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="fd6a2-378">如果未指定连接 URI，则可以使用 **UseSSL** 和 **Port** 参数指定连接 uri 值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-378">If you don't specify a connection URI, you can use the **UseSSL** and **Port** parameters to specify the connection URI values.</span></span>

<span data-ttu-id="fd6a2-379">URI 的 **Transport** 段的有效值为 HTTP 和 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-379">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="fd6a2-380">如果使用传输段指定连接 URI，但未指定端口，则将使用标准端口：80用于 HTTP，443用于 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-380">If you specify a connection URI with a Transport segment, but don't specify a port, the session is created with the standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="fd6a2-381">若要使用 PowerShell 远程处理的默认端口，请为 HTTP 指定端口5985，为 HTTPS 指定5986。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-381">To use the default ports for PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="fd6a2-382">如果目标计算机将连接重定向到不同的 URI，则 PowerShell 会阻止重定向，除非你在命令中使用 **AllowRedirection** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-382">If the destination computer redirects the connection to a different URI, PowerShell prevents the redirection unless you use the **AllowRedirection** parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: Uri, FilePathUri
Aliases: URI, CU

Required: False
Position: 0
Default value: http://localhost:5985/WSMAN
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-383">-ContainerId</span><span class="sxs-lookup"><span data-stu-id="fd6a2-383">-ContainerId</span></span>

<span data-ttu-id="fd6a2-384">指定容器 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-384">Specifies an array of container IDs.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-385">-Credential</span><span class="sxs-lookup"><span data-stu-id="fd6a2-385">-Credential</span></span>

<span data-ttu-id="fd6a2-386">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-386">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="fd6a2-387">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-387">The default is the current user.</span></span>

<span data-ttu-id="fd6a2-388">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-388">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="fd6a2-389">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-389">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="fd6a2-390">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-390">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="fd6a2-391">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-391">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, FilePathComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName
Aliases:

Required: True (VMId, VMName, FilePathVMId, FilePathVMName), False (ComputerName, FilePathComputerName, Uri, FilePathUri)
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-392">-EnableNetworkAccess</span><span class="sxs-lookup"><span data-stu-id="fd6a2-392">-EnableNetworkAccess</span></span>

<span data-ttu-id="fd6a2-393">指示此 cmdlet 将交互式安全令牌添加到环回会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-393">Indicates that this cmdlet adds an interactive security token to loopback sessions.</span></span> <span data-ttu-id="fd6a2-394">通过交互式令牌，你可以在环回会话中运行用于获取其他计算机中的数据的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-394">The interactive token lets you run commands in the loopback session that get data from other computers.</span></span> <span data-ttu-id="fd6a2-395">例如，你可以在该会话中运行用于将 XML 文件从远程计算机复制到本地计算机的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-395">For example, you can run a command in the session that copies XML files from a remote computer to the local computer.</span></span>

<span data-ttu-id="fd6a2-396">环回会话是在同一计算机上开始并终止的 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-396">A loopback session is a **PSSession** that originates and ends on the same computer.</span></span> <span data-ttu-id="fd6a2-397">若要创建环回会话，请省略 **ComputerName** 参数，或将其值设置为点 (`.`) 、localhost 或本地计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-397">To create a loopback session, omit the **ComputerName** parameter or set its value to dot (`.`), localhost, or the name of the local computer.</span></span>

<span data-ttu-id="fd6a2-398">默认情况下，使用网络令牌创建环回会话，该令牌可能不提供足够的权限来对远程计算机进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-398">By default, loopback sessions are created using a network token, which might not provide sufficient permission to authenticate to remote computers.</span></span>

<span data-ttu-id="fd6a2-399">**EnableNetworkAccess** 参数仅在环回会话中有效。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-399">The **EnableNetworkAccess** parameter is effective only in loopback sessions.</span></span> <span data-ttu-id="fd6a2-400">如果在远程计算机上创建会话时使用 **EnableNetworkAccess** ，则该命令将成功，但会忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-400">If you use **EnableNetworkAccess** when you create a session on a remote computer, the command succeeds, but the parameter is ignored.</span></span>

<span data-ttu-id="fd6a2-401">你可以使用 **Authentication** 参数的 **CredSSP** 值（它将会话凭据委派给其他计算机）允许在环回会话中进行远程访问。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-401">You can allow remote access in a loopback session using the **CredSSP** value of the **Authentication** parameter, which delegates the session credentials to other computers.</span></span>

<span data-ttu-id="fd6a2-402">若要防止计算机受到恶意访问，具有交互式令牌（使用 **EnableNetworkAccess** 创建的令牌）的断开连接环回会话只能从创建会话的计算机重新连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-402">To protect the computer from malicious access, disconnected loopback sessions that have interactive tokens, which are those created using **EnableNetworkAccess** , can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="fd6a2-403">断开连接的使用 CredSSP 身份验证的会话可通过其他计算机重新连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-403">Disconnected sessions that use CredSSP authentication can be reconnected from other computers.</span></span> <span data-ttu-id="fd6a2-404">有关详细信息，请参阅 `Disconnect-PSSession`。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-404">For more information, see `Disconnect-PSSession`.</span></span>

<span data-ttu-id="fd6a2-405">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-405">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-406">-FilePath</span><span class="sxs-lookup"><span data-stu-id="fd6a2-406">-FilePath</span></span>

<span data-ttu-id="fd6a2-407">指定此 cmdlet 在一台或多台远程计算机上运行的本地脚本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-407">Specifies a local script that this cmdlet runs on one or more remote computers.</span></span> <span data-ttu-id="fd6a2-408">输入脚本的路径和文件名，或通过管道将脚本路径传递给 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-408">Enter the path and filename of the script, or pipe a script path to `Invoke-Command`.</span></span> <span data-ttu-id="fd6a2-409">脚本必须位于本地计算机或本地计算机可以访问的目录中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-409">The script must exist on the local computer or in a directory that the local computer can access.</span></span> <span data-ttu-id="fd6a2-410">使用 **ArgumentList** 指定脚本中参数的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-410">Use **ArgumentList** to specify the values of parameters in the script.</span></span>

<span data-ttu-id="fd6a2-411">当你使用此参数时，PowerShell 会将指定脚本文件的内容转换为脚本块，将脚本块传输到远程计算机，然后在远程计算机上运行它。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-411">When you use this parameter, PowerShell converts the contents of the specified script file to a script block, transmits the script block to the remote computer, and runs it on the remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePathRunspace, FilePathComputerName, FilePathUri, FilePathVMId, FilePathVMName, FilePathContainerId
Aliases: PSPath

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-412">-HideComputerName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-412">-HideComputerName</span></span>

<span data-ttu-id="fd6a2-413">指示此 cmdlet 省略输出显示中每个对象的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-413">Indicates that this cmdlet omits the computer name of each object from the output display.</span></span> <span data-ttu-id="fd6a2-414">默认情况下，生成该对象的计算机名称会出现在显示内容中。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-414">By default, the name of the computer that generated the object appears in the display.</span></span>

<span data-ttu-id="fd6a2-415">此参数仅影响输出显示。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-415">This parameter affects only the output display.</span></span> <span data-ttu-id="fd6a2-416">它不会更改对象。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-416">It doesn't change the object.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases: HCN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-417">-InDisconnectedSession</span><span class="sxs-lookup"><span data-stu-id="fd6a2-417">-InDisconnectedSession</span></span>

<span data-ttu-id="fd6a2-418">指示此 cmdlet 在断开连接的会话中运行命令或脚本。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-418">Indicates that this cmdlet runs a command or script in a disconnected session.</span></span>

<span data-ttu-id="fd6a2-419">使用 **InDisconnectedSession** 参数时，将 `Invoke-Command` 在每台远程计算机上创建一个持久会话，启动由 **ScriptBlock** 或 **FilePath** 参数指定的命令，然后断开与该会话的连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-419">When you use the **InDisconnectedSession** parameter, `Invoke-Command` creates a persistent session on each remote computer, starts the command specified by the **ScriptBlock** or **FilePath** parameter, and then disconnects from the session.</span></span> <span data-ttu-id="fd6a2-420">这些命令将继续在断开连接的会话中运行。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-420">The commands continue to run in the disconnected sessions.</span></span> <span data-ttu-id="fd6a2-421">**InDisconnectedSession** 使你能够在不保持与远程会话的连接的情况下运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-421">**InDisconnectedSession** enables you to run commands without maintaining a connection to the remote sessions.</span></span> <span data-ttu-id="fd6a2-422">而且，因为在返回任何结果之前会话已断开连接， **InDisconnectedSession** 确保所有命令结果都返回到重新连接的会话，而不是在会话之间拆分。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-422">And, because the session is disconnected before any results are returned, **InDisconnectedSession** makes sure that all command results are returned to the reconnected session, instead of being split between sessions.</span></span>

<span data-ttu-id="fd6a2-423">不能将 **InDisconnectedSession** 与 **Session** 参数或 **AsJob** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-423">You can't use **InDisconnectedSession** with the **Session** parameter or the **AsJob** parameter.</span></span>

<span data-ttu-id="fd6a2-424">使用 **InDisconnectedSession** 的命令返回表示已断开连接的会话的 **PSSession** 对象。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-424">Commands that use **InDisconnectedSession** return a **PSSession** object that represents the disconnected session.</span></span> <span data-ttu-id="fd6a2-425">它们不会返回命令输出。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-425">They don't return the command output.</span></span> <span data-ttu-id="fd6a2-426">若要连接到断开连接的会话，请使用 `Connect-PSSession` 或 `Receive-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-426">To connect to the disconnected session, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span> <span data-ttu-id="fd6a2-427">若要获取在会话中运行的命令的结果，请使用 `Receive-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-427">To get the results of commands that ran in the session, use the `Receive-PSSession` cmdlet.</span></span> <span data-ttu-id="fd6a2-428">若要运行在断开连接的会话中生成输出的命令，请将 **OutputBufferingMode** session 选项的值设置为 **Drop** 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-428">To run commands that generate output in a disconnected session, set the value of the **OutputBufferingMode** session option to **Drop** .</span></span> <span data-ttu-id="fd6a2-429">如果打算连接到断开连接的会话，请在会话中设置空闲超时，以便在删除会话之前可以提供足够的时间进行连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-429">If you intend to connect to the disconnected session, set the idle time-out in the session so that it provides sufficient time for you to connect before deleting the session.</span></span>

<span data-ttu-id="fd6a2-430">可以在 **SessionOption** 参数或 `$PSSessionOption` 首选项变量中设置输出缓冲模式和空闲超时。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-430">You can set the output buffering mode and idle time-out in the **SessionOption** parameter or in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="fd6a2-431">有关会话选项的详细信息，请参阅 `New-PSSessionOption` 和 [about_Preference_Variables](./about/about_preference_variables.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-431">For more information about session options, see `New-PSSessionOption` and [about_Preference_Variables](./about/about_preference_variables.md).</span></span>

<span data-ttu-id="fd6a2-432">有关断开连接会话的功能的详细信息，请参阅 [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-432">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](about/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="fd6a2-433">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-433">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases: Disconnected

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-434">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fd6a2-434">-InputObject</span></span>

<span data-ttu-id="fd6a2-435">指定命令的输入。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-435">Specifies input to the command.</span></span> <span data-ttu-id="fd6a2-436">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-436">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="fd6a2-437">使用 **InputObject** 参数时，请使用 `$Input` **ScriptBlock** 参数的值中的自动变量来表示输入对象。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-437">When using the **InputObject** parameter, use the `$Input` automatic variable in the value of the **ScriptBlock** parameter to represent the input objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-438">-JobName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-438">-JobName</span></span>

<span data-ttu-id="fd6a2-439">为后台作业指定友好名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-439">Specifies a friendly name for the background job.</span></span> <span data-ttu-id="fd6a2-440">默认情况下，作业名为 `Job<n>` ，其中 `<n>` 是一个序号。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-440">By default, jobs are named `Job<n>`, where `<n>` is an ordinal number.</span></span>

<span data-ttu-id="fd6a2-441">如果你在命令中使用 **JobName** 参数，则该命令将作为作业运行，并 `Invoke-Command` 返回一个作业对象，即使未在命令中包含 **AsJob** 也是如此。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-441">If you use the **JobName** parameter in a command, the command is run as a job, and `Invoke-Command` returns a job object, even if you don't include **AsJob** in the command.</span></span>

<span data-ttu-id="fd6a2-442">有关 PowerShell 后台作业的详细信息，请参阅 [about_Jobs](./About/about_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-442">For more information about PowerShell background jobs, see [about_Jobs](./About/about_Jobs.md).</span></span>

```yaml
Type: System.String
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: Job<n>
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-443">-NoNewScope</span><span class="sxs-lookup"><span data-stu-id="fd6a2-443">-NoNewScope</span></span>

<span data-ttu-id="fd6a2-444">指示此 cmdlet 在当前作用域中运行指定的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-444">Indicates that this cmdlet runs the specified command in the current scope.</span></span> <span data-ttu-id="fd6a2-445">默认情况下， `Invoke-Command` 在其自己的作用域中运行命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-445">By default, `Invoke-Command` runs commands in their own scope.</span></span>

<span data-ttu-id="fd6a2-446">此参数仅在当前会话中运行的命令（即同时省略 **ComputerName** 和 **Session** 参数的命令）中有效。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-446">This parameter is valid only in commands that are run in the current session, that is, commands that omit both the **ComputerName** and **Session** parameters.</span></span>

<span data-ttu-id="fd6a2-447">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-447">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: InProcess
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-448">-Port</span><span class="sxs-lookup"><span data-stu-id="fd6a2-448">-Port</span></span>

<span data-ttu-id="fd6a2-449">指定远程计算机上用于此命令的网络端口。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-449">Specifies the network port on the remote computer that is used for this command.</span></span> <span data-ttu-id="fd6a2-450">若要连接到一台远程计算机，则必须在该连接所用的端口上侦听远程计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-450">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span> <span data-ttu-id="fd6a2-451">对于 HTTP) ，默认端口为 5985 (WinRM 端口5986， (HTTPS 的 WinRM 端口) 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-451">The default ports are 5985 (WinRM port for HTTP) and 5986 (WinRM port for HTTPS).</span></span>

<span data-ttu-id="fd6a2-452">使用备用端口之前，请在远程计算机上配置 WinRM 侦听器，以便侦听该端口。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-452">Before using an alternate port, configure the WinRM listener on the remote computer to listen at that port.</span></span> <span data-ttu-id="fd6a2-453">若要配置侦听器，请在 PowerShell 提示符下键入以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="fd6a2-453">To configure the listener, type the following two commands at the PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="fd6a2-454">不要使用 **Port** 参数，除非必须这样做。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-454">Don't use the **Port** parameter unless you must.</span></span> <span data-ttu-id="fd6a2-455">在命令中设置的端口适用于运行该命令的所有计算机或会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-455">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="fd6a2-456">备用端口设置可能会阻止在所有计算机上运行该命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-456">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-457">-RunAsAdministrator</span><span class="sxs-lookup"><span data-stu-id="fd6a2-457">-RunAsAdministrator</span></span>

<span data-ttu-id="fd6a2-458">指示此 cmdlet 以管理员身份调用命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-458">Indicates that this cmdlet invokes a command as an Administrator.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-459">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="fd6a2-459">-ScriptBlock</span></span>

<span data-ttu-id="fd6a2-460">指定要运行的命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-460">Specifies the commands to run.</span></span> <span data-ttu-id="fd6a2-461">将命令括在大括号中 `{ }` ，以创建脚本块。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-461">Enclose the commands in curly braces `{ }` to create a script block.</span></span>
<span data-ttu-id="fd6a2-462">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-462">This parameter is required.</span></span>

<span data-ttu-id="fd6a2-463">默认情况下，将在远程计算机上评估命令中的所有变量。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-463">By default, any variables in the command are evaluated on the remote computer.</span></span> <span data-ttu-id="fd6a2-464">若要在命令中包括局部变量，请使用 **ArgumentList** 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-464">To include local variables in the command, use **ArgumentList** .</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: InProcess, Session, ComputerName, Uri, VMId, VMName, ContainerId
Aliases: Command

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-465">-Session</span><span class="sxs-lookup"><span data-stu-id="fd6a2-465">-Session</span></span>

<span data-ttu-id="fd6a2-466">指定此 cmdlet 在其中运行命令的会话的数组。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-466">Specifies an array of sessions in which this cmdlet runs the command.</span></span> <span data-ttu-id="fd6a2-467">输入包含 **pssession** 对象的变量或创建或获取 **pssession** 对象的命令，例如 `New-PSSession` 或 `Get-PSSession` 命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-467">Enter a variable that contains **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a `New-PSSession` or `Get-PSSession` command.</span></span>

<span data-ttu-id="fd6a2-468">创建 **PSSession** 时，PowerShell 会建立与远程计算机的持久连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-468">When you create a **PSSession** , PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="fd6a2-469">使用 **PSSession** 运行共享数据的一系列相关命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-469">Use a **PSSession** to run a series of related commands that share data.</span></span> <span data-ttu-id="fd6a2-470">若要运行单个命令或一系列不相关的命令，请使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-470">To run a single command or a series of unrelated commands, use the **ComputerName** parameter.</span></span> <span data-ttu-id="fd6a2-471">有关详细信息，请参阅 [about_PSSessions](./About/about_PSSessions.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-471">For more information, see [about_PSSessions](./About/about_PSSessions.md).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session, FilePathRunspace
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-472">-SessionName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-472">-SessionName</span></span>

<span data-ttu-id="fd6a2-473">为断开连接的会话指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-473">Specifies a friendly name for a disconnected session.</span></span> <span data-ttu-id="fd6a2-474">可以在后续命令中使用此名称来引用会话，例如 `Get-PSSession` 命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-474">You can use the name to refer to the session in subsequent commands, such as a `Get-PSSession` command.</span></span> <span data-ttu-id="fd6a2-475">此参数只有在与 **InDisconnectedSession** 参数一起使用时才有效。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-475">This parameter is valid only with the **InDisconnectedSession** parameter.</span></span>

<span data-ttu-id="fd6a2-476">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-476">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-477">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="fd6a2-477">-SessionOption</span></span>

<span data-ttu-id="fd6a2-478">为该会话指定高级选项。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-478">Specifies advanced options for the session.</span></span> <span data-ttu-id="fd6a2-479">输入 **SessionOption** 对象（例如使用 cmdlet 创建的对象） `New-PSSessionOption` ，或输入一个哈希表，其中的键是会话选项名称，而值是会话选项的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-479">Enter a **SessionOption** object, such as one that you create using the `New-PSSessionOption` cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="fd6a2-480">选项的默认值取决于 `$PSSessionOption` 首选项变量的值（如果已设置）。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-480">The default values for the options are determined by the value of the `$PSSessionOption` preference variable, if it's set.</span></span> <span data-ttu-id="fd6a2-481">否则，通过在会话配置中设置的选项创建默认值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-481">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="fd6a2-482">会话选项值优先于在 `$PSSessionOption` 首选项变量和会话配置中设置的会话的默认值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-482">The session option values take precedence over default values for sessions set in the `$PSSessionOption` preference variable and in the session configuration.</span></span> <span data-ttu-id="fd6a2-483">但是，它们不优先于在会话配置中设置的最大值、配额或限制。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-483">However, they don't take precedence over maximum values, quotas, or limits set in the session configuration.</span></span>

<span data-ttu-id="fd6a2-484">有关包括默认值的会话选项的说明，请参阅 `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-484">For a description of the session options that includes the default values, see `New-PSSessionOption`.</span></span> <span data-ttu-id="fd6a2-485">有关 `$PSSessionOption` 首选项变量的信息，请参阅 [about_Preference_Variables](About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-485">For information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="fd6a2-486">有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-486">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: FilePathComputerName, ComputerName, Uri, FilePathUri
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-487">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="fd6a2-487">-ThrottleLimit</span></span>

<span data-ttu-id="fd6a2-488">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-488">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="fd6a2-489">如果省略此参数或输入 0 值，则使用默认值 32。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-489">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="fd6a2-490">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-490">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: Session, FilePathRunspace, FilePathComputerName, ComputerName, Uri, FilePathUri, VMId, VMName, FilePathVMId, FilePathVMName, ContainerId, FilePathContainerId
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-491">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="fd6a2-491">-UseSSL</span></span>

<span data-ttu-id="fd6a2-492">指示此 cmdlet 使用安全套接字层 (SSL) 协议来建立与远程计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-492">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to establish a connection to the remote computer.</span></span> <span data-ttu-id="fd6a2-493">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-493">By default, SSL isn't used.</span></span>

<span data-ttu-id="fd6a2-494">WS-Management 加密通过网络传输的所有 PowerShell 内容。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-494">WS-Management encrypts all PowerShell content transmitted over the network.</span></span> <span data-ttu-id="fd6a2-495">**UseSSL** 参数是一种额外的保护措施，它通过 HTTPS 而不是 HTTP 来发送数据。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-495">The **UseSSL** parameter is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span>

<span data-ttu-id="fd6a2-496">如果使用此参数，但 SSL 在用于此命令的端口上不可用，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-496">If you use this parameter, but SSL isn't available on the port that's used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FilePathComputerName, ComputerName
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-497">-VMId</span><span class="sxs-lookup"><span data-stu-id="fd6a2-497">-VMId</span></span>

<span data-ttu-id="fd6a2-498">指定虚拟机的 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-498">Specifies an array of IDs of virtual machines.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: VMId, FilePathVMId
Aliases: VMGuid

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-499">-VMName</span><span class="sxs-lookup"><span data-stu-id="fd6a2-499">-VMName</span></span>

<span data-ttu-id="fd6a2-500">指定一个虚拟机的名称数组。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-500">Specifies an array of names of virtual machines.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName, FilePathVMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6a2-501">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd6a2-501">CommonParameters</span></span>

<span data-ttu-id="fd6a2-502">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-502">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd6a2-503">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-503">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd6a2-504">输入</span><span class="sxs-lookup"><span data-stu-id="fd6a2-504">INPUTS</span></span>

### <span data-ttu-id="fd6a2-505">System.object。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-505">System.Management.Automation.ScriptBlock</span></span>

<span data-ttu-id="fd6a2-506">可以通过管道将脚本块中的命令传递给 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-506">You can pipe a command in a script block to `Invoke-Command`.</span></span> <span data-ttu-id="fd6a2-507">使用 `$Input` 自动变量来表示命令中的输入对象。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-507">Use the `$Input` automatic variable to represent the input objects in the command.</span></span>

## <span data-ttu-id="fd6a2-508">输出</span><span class="sxs-lookup"><span data-stu-id="fd6a2-508">OUTPUTS</span></span>

### <span data-ttu-id="fd6a2-509">PSRemotingJob、、或调用的命令的输出中的命令的输出。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-509">System.Management.Automation.PSRemotingJob, System.Management.Automation.Runspaces.PSSession, or the output of the invoked command</span></span>

<span data-ttu-id="fd6a2-510">如果使用 **AsJob** 参数，则此 cmdlet 将返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-510">This cmdlet returns a job object, if you use the **AsJob** parameter.</span></span> <span data-ttu-id="fd6a2-511">如果指定 **InDisconnectedSession** 参数，则 `Invoke-Command` 将返回 **PSSession** 对象。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-511">If you specify the **InDisconnectedSession** parameter, `Invoke-Command` returns a **PSSession** object.</span></span> <span data-ttu-id="fd6a2-512">否则，它将返回调用的命令的输出，这是 **ScriptBlock** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-512">Otherwise, it returns the output of the invoked command, which is the value of the **ScriptBlock** parameter.</span></span>

## <span data-ttu-id="fd6a2-513">注释</span><span class="sxs-lookup"><span data-stu-id="fd6a2-513">NOTES</span></span>

<span data-ttu-id="fd6a2-514">在 Windows Vista 和更高版本的 Windows 操作系统上，若要使用的 **ComputerName** 参数 `Invoke-Command` 在本地计算机上运行命令，则必须使用 "以 **管理员身份运行** " 选项运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-514">On Windows Vista, and later versions of the Windows operating system, to use the **ComputerName** parameter of `Invoke-Command` to run a command on the local computer, you must run PowerShell using the **Run as administrator** option.</span></span>

<span data-ttu-id="fd6a2-515">在多台计算机上运行命令时，PowerShell 会按照它们在列表中的显示顺序连接到这些计算机。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-515">When you run commands on multiple computers, PowerShell connects to the computers in the order in which they appear in the list.</span></span> <span data-ttu-id="fd6a2-516">但是，命令输出会按从远程计算机接收的顺序显示，这可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-516">However, the command output is displayed in the order that it's received from the remote computers, which might be different.</span></span>

<span data-ttu-id="fd6a2-517">命令结果中将包含由运行的命令产生的错误 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-517">Errors that result from the command that `Invoke-Command` runs are included in the command results.</span></span>
<span data-ttu-id="fd6a2-518">在本地命令中可能是终止错误的错误在远程命令中将视作非终止错误。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-518">Errors that would be terminating errors in a local command are treated as non-terminating errors in a remote command.</span></span> <span data-ttu-id="fd6a2-519">此策略可确保一台计算机上的终止错误不会在运行它的所有计算机上关闭该命令。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-519">This strategy makes sure that terminating errors on one computer don't close the command on all computers on which it's run.</span></span> <span data-ttu-id="fd6a2-520">即使在一台计算机上运行远程命令，也使用这种做法。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-520">This practice is used even when a remote command is run on a single computer.</span></span>

<span data-ttu-id="fd6a2-521">如果远程计算机不在本地计算机信任的域中，则计算机可能无法对用户的凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-521">If the remote computer isn't in a domain that the local computer trusts, the computer might not be able to authenticate the user's credentials.</span></span> <span data-ttu-id="fd6a2-522">若要将远程计算机添加到 WS-MANAGEMENT 中的受信任主机列表中，请在提供程序中使用以下命令 `WSMAN` ，其中， `<Remote-Computer-Name>` 是远程计算机的名称：</span><span class="sxs-lookup"><span data-stu-id="fd6a2-522">To add the remote computer to the list of trusted hosts in WS-Management, use the following command in the `WSMAN` provider, where `<Remote-Computer-Name>` is the name of the remote computer:</span></span>

`Set-Item -Path WSMan:\Localhost\Client\TrustedHosts -Value \<Remote-Computer-Name\>`

<span data-ttu-id="fd6a2-523">当你使用 **InDisconnectedSession** 参数断开 **PSSession** 的连接时，会话状态将 **断开连接** ，并且可用性为 **None** 。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-523">When you disconnect a **PSSession** using the **InDisconnectedSession** parameter, the session state is **Disconnected** and the availability is **None** .</span></span> <span data-ttu-id="fd6a2-524">**State** 属性的值是相对于当前会话的。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-524">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="fd6a2-525">如果值为 "已 **断开连接** "，则意味着 **PSSession** 未连接到当前会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-525">A value of **Disconnected** means that the **PSSession** isn't connected to the current session.</span></span> <span data-ttu-id="fd6a2-526">但是，它并不意味着 **PSSession** 会与所有会话断开连接。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-526">However, it doesn't mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="fd6a2-527">它可能连接到另一个会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-527">It might be connected to a different session.</span></span> <span data-ttu-id="fd6a2-528">若要确定是否可以连接或重新连接到该会话，请使用 **Availability** 属性。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-528">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

<span data-ttu-id="fd6a2-529">**Availability** 的 **None** 值指示可连接到 PSSession。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-529">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="fd6a2-530">值为 " **忙碌** " 表示无法连接到 **PSSession** ，因为它已连接到另一个会话。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-530">A value of **Busy** indicates that you can't connect to the **PSSession** because it's connected to another session.</span></span> <span data-ttu-id="fd6a2-531">有关会话 **状态** 属性的值的详细信息，请参阅 [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-531">For more information about the values of the **State** property of sessions, see [RunspaceState](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span> <span data-ttu-id="fd6a2-532">有关会话的 **可用性** 属性值的详细信息，请参阅 [runspacestate](/dotnet/api/system.management.automation.runspaces.runspaceavailability)。</span><span class="sxs-lookup"><span data-stu-id="fd6a2-532">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="fd6a2-533">相关链接</span><span class="sxs-lookup"><span data-stu-id="fd6a2-533">RELATED LINKS</span></span>

[<span data-ttu-id="fd6a2-534">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="fd6a2-534">about_PSSessions</span></span>](./About/about_PSSessions.md)

[<span data-ttu-id="fd6a2-535">about_Remote</span><span class="sxs-lookup"><span data-stu-id="fd6a2-535">about_Remote</span></span>](./About/about_Remote.md)

[<span data-ttu-id="fd6a2-536">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="fd6a2-536">about_Remote_Disconnected_Sessions</span></span>](./About/about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="fd6a2-537">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="fd6a2-537">about_Remote_Troubleshooting</span></span>](./About/about_remote_troubleshooting.md)

[<span data-ttu-id="fd6a2-538">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="fd6a2-538">about_Remote_Variables</span></span>](./About/about_Remote_Variables.md)

[<span data-ttu-id="fd6a2-539">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="fd6a2-539">about_Scopes</span></span>](./About/about_scopes.md)

[<span data-ttu-id="fd6a2-540">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="fd6a2-540">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="fd6a2-541">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="fd6a2-541">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="fd6a2-542">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="fd6a2-542">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="fd6a2-543">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="fd6a2-543">Invoke-Item</span></span>](../Microsoft.PowerShell.Management/Invoke-Item.md)

[<span data-ttu-id="fd6a2-544">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="fd6a2-544">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="fd6a2-545">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="fd6a2-545">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="fd6a2-546">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="fd6a2-546">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
