---
description: 包含有关在 PowerShell 中运行远程命令的问题和解答。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_faq?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_FAQ
ms.openlocfilehash: da70a3a563031a04aeffd1ead692d9a605f14042
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200254"
---
# <a name="about-remote-faq"></a><span data-ttu-id="972dd-104">关于远程 FAQ</span><span class="sxs-lookup"><span data-stu-id="972dd-104">About Remote FAQ</span></span>

## <a name="short-description"></a><span data-ttu-id="972dd-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="972dd-105">Short description</span></span>
<span data-ttu-id="972dd-106">包含有关在 PowerShell 中运行远程命令的问题和解答。</span><span class="sxs-lookup"><span data-stu-id="972dd-106">Contains questions and answers about running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="972dd-107">长说明</span><span class="sxs-lookup"><span data-stu-id="972dd-107">Long description</span></span>

<span data-ttu-id="972dd-108">远程工作时，可以在一台计算机上的 PowerShell 中键入命令 (称为 "本地计算机" ) ，但这些命令会在另一台计算机上运行， (称为 "远程计算机" ) 。</span><span class="sxs-lookup"><span data-stu-id="972dd-108">When you work remotely, you type commands in PowerShell on one computer (known as the "local computer"), but the commands run on another computer (known as the "remote computer").</span></span> <span data-ttu-id="972dd-109">远程工作的体验应该非常类似于直接在远程计算机上工作。</span><span class="sxs-lookup"><span data-stu-id="972dd-109">The experience of working remotely should be as much like working directly at the remote computer as possible.</span></span>

<span data-ttu-id="972dd-110">注意：若要使用 PowerShell 远程处理，必须配置远程计算机以进行远程处理。</span><span class="sxs-lookup"><span data-stu-id="972dd-110">Note: To use PowerShell remoting, the remote computer must be configured for remoting.</span></span> <span data-ttu-id="972dd-111">有关详细信息，请参阅 [about_Remote_Requirements](about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="972dd-111">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="must-both-computers-have-powershell-installed"></a><span data-ttu-id="972dd-112">这两台计算机都必须安装 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="972dd-112">Must both computers have PowerShell installed?</span></span>

<span data-ttu-id="972dd-113">是的。</span><span class="sxs-lookup"><span data-stu-id="972dd-113">Yes.</span></span> <span data-ttu-id="972dd-114">若要远程工作，本地和远程计算机必须具有 PowerShell、Microsoft .NET 框架和用于管理的 Web 服务 (WS-MANAGEMENT) 协议。</span><span class="sxs-lookup"><span data-stu-id="972dd-114">To work remotely, the local and remote computers must have PowerShell, the Microsoft .NET Framework, and the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="972dd-115">执行特定命令所需的任何文件和其他资源必须位于远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="972dd-115">Any files and other resources that are needed to execute a particular command must be on the remote computer.</span></span>

<span data-ttu-id="972dd-116">运行 Windows PowerShell 3.0 的计算机和运行 Windows PowerShell 2.0 的计算机可以远程连接到彼此，并运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-116">Computers running Windows PowerShell 3.0 and computers running Windows PowerShell 2.0 can connect to each other remotely and run remote commands.</span></span>
<span data-ttu-id="972dd-117">但是，某些功能（如从会话断开连接并重新连接到它）仅在两台计算机都运行 Windows PowerShell 3.0 时才起作用。</span><span class="sxs-lookup"><span data-stu-id="972dd-117">However, some features, such as the ability to disconnect from a session and reconnect to it, work only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="972dd-118">您必须有权连接到远程计算机、运行 PowerShell 的权限，以及访问数据存储区的权限， (如文件和文件夹) 以及远程计算机上的注册表。</span><span class="sxs-lookup"><span data-stu-id="972dd-118">You must have permission to connect to the remote computer, permission to run PowerShell, and permission to access data stores (such as files and folders), and the registry on the remote computer.</span></span>

<span data-ttu-id="972dd-119">有关详细信息，请参阅 [about_Remote_Requirements](about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="972dd-119">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

### <a name="how-does-remoting-work"></a><span data-ttu-id="972dd-120">远程处理如何工作？</span><span class="sxs-lookup"><span data-stu-id="972dd-120">How does remoting work?</span></span>

<span data-ttu-id="972dd-121">提交远程命令时，该命令将通过网络传输到远程计算机上的 PowerShell 引擎，并在远程计算机上的 PowerShell 客户端中运行。</span><span class="sxs-lookup"><span data-stu-id="972dd-121">When you submit a remote command, the command is transmitted across the network to the PowerShell engine on the remote computer, and it runs in the PowerShell client on the remote computer.</span></span> <span data-ttu-id="972dd-122">命令结果被发送回本地计算机，并出现在本地计算机上的 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="972dd-122">The command results are sent back to the local computer and appear in the PowerShell session on the local computer.</span></span>

<span data-ttu-id="972dd-123">为了传输命令和接收输出，PowerShell 使用 WS-Management 协议。</span><span class="sxs-lookup"><span data-stu-id="972dd-123">To transmit the commands and receive the output, PowerShell uses the WS-Management protocol.</span></span> <span data-ttu-id="972dd-124">有关 WS-Management 协议的信息，请参阅 Windows 文档中的 [WS-Management 协议](/windows/win32/winrm/ws-management-protocol) 。</span><span class="sxs-lookup"><span data-stu-id="972dd-124">For information about the WS-Management protocol, see [WS-Management Protocol](/windows/win32/winrm/ws-management-protocol) in the Windows documentation.</span></span>

<span data-ttu-id="972dd-125">从 Windows PowerShell 3.0 开始，远程会话存储在远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="972dd-125">Beginning in Windows PowerShell 3.0, remote sessions are stored on the remote computer.</span></span> <span data-ttu-id="972dd-126">这使你可以断开与会话的连接，并从其他会话或其他计算机重新连接，而不会中断命令或失去状态。</span><span class="sxs-lookup"><span data-stu-id="972dd-126">This enables you to disconnect from the session and reconnect from a different session or a different computer without interrupting the commands or losing state.</span></span>

### <a name="is-powershell-remoting-secure"></a><span data-ttu-id="972dd-127">PowerShell 远程处理是否安全？</span><span class="sxs-lookup"><span data-stu-id="972dd-127">Is PowerShell remoting secure?</span></span>

<span data-ttu-id="972dd-128">当你连接到远程计算机时，系统将使用本地计算机上的用户名和密码凭据，或者在命令中提供的凭据将你登录到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="972dd-128">When you connect to a remote computer, the system uses the username and password credentials on the local computer or the credentials that you supply in the command to log you in to the remote computer.</span></span> <span data-ttu-id="972dd-129">凭据和传输的其余部分进行加密。</span><span class="sxs-lookup"><span data-stu-id="972dd-129">The credentials and the rest of the transmission are encrypted.</span></span>

<span data-ttu-id="972dd-130">若要添加其他保护，你可以将远程计算机配置为使用安全套接字层 (SSL) 而不是 HTTP 来侦听 Windows 远程管理 (WinRM) 请求。</span><span class="sxs-lookup"><span data-stu-id="972dd-130">To add additional protection, you can configure the remote computer to use Secure Sockets Layer (SSL) instead of HTTP to listen for Windows Remote Management (WinRM) requests.</span></span> <span data-ttu-id="972dd-131">然后， **UseSSL** `Invoke-Command` `New-PSSession` `Enter-PSSession` 在建立连接时，用户可以使用、和 cmdlet 的 UseSSL 参数。</span><span class="sxs-lookup"><span data-stu-id="972dd-131">Then, users can use the **UseSSL** parameter of the `Invoke-Command`, `New-PSSession`, and `Enter-PSSession` cmdlets when establishing a connection.</span></span> <span data-ttu-id="972dd-132">此选项使用更安全的 HTTPS 通道，而不是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="972dd-132">This option uses the more secure HTTPS channel instead of HTTP.</span></span>

### <a name="do-all-remote-commands-require-powershell-remoting"></a><span data-ttu-id="972dd-133">所有远程命令都需要 PowerShell 远程处理吗？</span><span class="sxs-lookup"><span data-stu-id="972dd-133">Do all remote commands require PowerShell remoting?</span></span>

<span data-ttu-id="972dd-134">不是。</span><span class="sxs-lookup"><span data-stu-id="972dd-134">No.</span></span> <span data-ttu-id="972dd-135">多个 cmdlet 具有 **ComputerName** 参数，可让你从远程计算机获取对象。</span><span class="sxs-lookup"><span data-stu-id="972dd-135">Several cmdlets have a **ComputerName** parameter that lets you get objects from the remote computer.</span></span>

<span data-ttu-id="972dd-136">这些 cmdlet 不使用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="972dd-136">These cmdlets do not use PowerShell remoting.</span></span> <span data-ttu-id="972dd-137">因此，你可以在运行 PowerShell 的任何计算机上使用它们，即使计算机未配置为进行 PowerShell 远程处理，或者计算机不满足 PowerShell 远程处理的要求。</span><span class="sxs-lookup"><span data-stu-id="972dd-137">So, you can use them on any computer that is running PowerShell, even if the computer is not configured for PowerShell remoting or if the computer does not meet the requirements for PowerShell remoting.</span></span>

<span data-ttu-id="972dd-138">这些 cmdlet 包括：</span><span class="sxs-lookup"><span data-stu-id="972dd-138">These cmdlets include the following:</span></span>

- `Get-Process`
- `Get-Service`
- `Get-WinEvent`
- `Get-EventLog`
- `Test-Connection`

<span data-ttu-id="972dd-139">若要查找包含 **ComputerName** 参数的所有 cmdlet，请键入：</span><span class="sxs-lookup"><span data-stu-id="972dd-139">To find all the cmdlets with a **ComputerName** parameter, type:</span></span>

```powershell
Get-Help * -Parameter ComputerName
# or
Get-Command -ParameterName ComputerName
```

<span data-ttu-id="972dd-140">若要确定特定 cmdlet 的 **ComputerName** 参数是否需要 PowerShell 远程处理，请参阅参数说明。</span><span class="sxs-lookup"><span data-stu-id="972dd-140">To determine whether the **ComputerName** parameter of a particular cmdlet requires PowerShell remoting, see the parameter description.</span></span> <span data-ttu-id="972dd-141">若要显示参数说明，请键入：</span><span class="sxs-lookup"><span data-stu-id="972dd-141">To display the parameter description, type:</span></span>

```powershell
Get-Help <cmdlet-name> -Parameter ComputerName
```

<span data-ttu-id="972dd-142">例如：</span><span class="sxs-lookup"><span data-stu-id="972dd-142">For example:</span></span>

```powershell
Get-Help Get-Process -Parameter ComputerName
```

<span data-ttu-id="972dd-143">对于所有其他命令，请使用 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="972dd-143">For all other commands, use the `Invoke-Command` cmdlet.</span></span>

### <a name="how-do-i-run-a-command-on-a-remote-computer"></a><span data-ttu-id="972dd-144">如何实现在远程计算机上运行命令？</span><span class="sxs-lookup"><span data-stu-id="972dd-144">How do I run a command on a remote computer?</span></span>

<span data-ttu-id="972dd-145">若要在远程计算机上运行命令，请使用 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="972dd-145">To run a command on a remote computer, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="972dd-146">将命令括在大括号中 `{}` ， () 使其成为脚本块。</span><span class="sxs-lookup"><span data-stu-id="972dd-146">Enclose your command in braces (`{}`) to make it a script block.</span></span> <span data-ttu-id="972dd-147">使用的 **ScriptBlock** 参数 `Invoke-Command` 指定命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-147">Use the **ScriptBlock** parameter of `Invoke-Command` to specify the command.</span></span>

<span data-ttu-id="972dd-148">您可以使用 **ComputerName** 参数 `Invoke-Command` 来指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="972dd-148">You can use the **ComputerName** parameter of `Invoke-Command` to specify a remote computer.</span></span> <span data-ttu-id="972dd-149">或者，你可以 (会话创建到远程计算机的持续性连接) 然后使用的 **session** 参数 `Invoke-Command` 在该会话中运行该命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-149">Or, you can create a persistent connection to a remote computer (a session) and then use the **Session** parameter of `Invoke-Command` to run the command in the session.</span></span>

<span data-ttu-id="972dd-150">例如，以下命令 `Get-Process` 远程运行命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-150">For example, the following commands run a `Get-Process` command remotely.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-Process}

#  - OR -

Invoke-Command -Session $s -ScriptBlock {Get-Process}
```

<span data-ttu-id="972dd-151">若要中断远程命令，请键入<kbd>CTRL</kbd> + <kbd>C</kbd>。</span><span class="sxs-lookup"><span data-stu-id="972dd-151">To interrupt a remote command, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="972dd-152">中断请求会传递到远程计算机，并在其中终止远程命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-152">The interruption request is passed to the remote computer, where it terminates the remote command.</span></span>

<span data-ttu-id="972dd-153">有关远程命令的详细信息，请参阅 about_Remote 和支持远程处理的 cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="972dd-153">For more information about remote commands, see about_Remote and the Help topics for the cmdlets that support remoting.</span></span>

### <a name="can-i-just-telnet-into-a-remote-computer"></a><span data-ttu-id="972dd-154">我能只是 telnet 到远程计算机上吗？</span><span class="sxs-lookup"><span data-stu-id="972dd-154">Can I just telnet into a remote computer?</span></span>

<span data-ttu-id="972dd-155">你可以使用 `Enter-PSSession` cmdlet 来启动与远程计算机的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="972dd-155">You can use the `Enter-PSSession` cmdlet to start an interactive session with a remote computer.</span></span>

<span data-ttu-id="972dd-156">在 PowerShell 提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="972dd-156">At the PowerShell prompt, type:</span></span>

```powershell
Enter-PSSession <ComputerName>
```

<span data-ttu-id="972dd-157">命令提示符更改为显示你已连接到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="972dd-157">The command prompt changes to show that you are connected to the remote computer.</span></span>

```
<ComputerName>\C:>
```

<span data-ttu-id="972dd-158">现在，你键入的命令将在远程计算机上运行，就像你直接在远程计算机上键入一样。</span><span class="sxs-lookup"><span data-stu-id="972dd-158">Now, the commands that you type run on the remote computer just as though you typed them directly on the remote computer.</span></span>

<span data-ttu-id="972dd-159">若要结束交互会话，请键入：</span><span class="sxs-lookup"><span data-stu-id="972dd-159">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="972dd-160">交互式会话是使用 WS-Management 协议的持久会话。</span><span class="sxs-lookup"><span data-stu-id="972dd-160">An interactive session is a persistent session that uses the WS-Management protocol.</span></span> <span data-ttu-id="972dd-161">它与使用 Telnet 不同，但它提供了类似的体验。</span><span class="sxs-lookup"><span data-stu-id="972dd-161">It is not the same as using Telnet, but it provides a similar experience.</span></span>

<span data-ttu-id="972dd-162">有关详细信息，请参阅 `Enter-PSSession`。</span><span class="sxs-lookup"><span data-stu-id="972dd-162">For more information, see `Enter-PSSession`.</span></span>

### <a name="can-i-create-a-persistent-connection"></a><span data-ttu-id="972dd-163">能否创建持续性连接？</span><span class="sxs-lookup"><span data-stu-id="972dd-163">Can I create a persistent connection?</span></span>

<span data-ttu-id="972dd-164">是的。</span><span class="sxs-lookup"><span data-stu-id="972dd-164">Yes.</span></span> <span data-ttu-id="972dd-165">可以通过指定远程计算机的名称、NetBIOS 名称或 IP 地址来运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-165">You can run remote commands by specifying the name of the remote computer, its NetBIOS name, or its IP address.</span></span> <span data-ttu-id="972dd-166">或者，你可以通过指定连接到远程计算机 (PSSession) 的 PowerShell 会话来运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-166">Or, you can run remote commands by specifying a PowerShell session (PSSession) that is connected to the remote computer.</span></span>

<span data-ttu-id="972dd-167">当你使用或的 **ComputerName** 参数 `Invoke-Command` 时 `Enter-PSSession` ，PowerShell 将建立一个临时连接。</span><span class="sxs-lookup"><span data-stu-id="972dd-167">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection.</span></span> <span data-ttu-id="972dd-168">PowerShell 使用连接来仅运行当前命令，然后关闭连接。</span><span class="sxs-lookup"><span data-stu-id="972dd-168">PowerShell uses the connection to run only the current command, and then it closes the connection.</span></span> <span data-ttu-id="972dd-169">这是一种非常有效的方法，可用于运行单个命令或多个不相关的命令，即使在许多远程计算机上也是如此。</span><span class="sxs-lookup"><span data-stu-id="972dd-169">This is a very efficient method for running a single command or several unrelated commands, even on many remote computers.</span></span>

<span data-ttu-id="972dd-170">使用 `New-PSSession` cmdlet 创建 pssession 时，PowerShell 将为 pssession 建立持续连接。</span><span class="sxs-lookup"><span data-stu-id="972dd-170">When you use the `New-PSSession` cmdlet to create a PSSession, PowerShell establishes a persistent connection for the PSSession.</span></span> <span data-ttu-id="972dd-171">然后，可以在 PSSession 中运行多个命令，包括共享数据的命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-171">Then, you can run multiple commands in the PSSession, including commands that share data.</span></span>

<span data-ttu-id="972dd-172">通常，可以创建 PSSession 来运行一系列共享数据的相关命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-172">Typically, you create a PSSession to run a series of related commands that share data.</span></span> <span data-ttu-id="972dd-173">否则， **ComputerName** 参数创建的临时连接就足以满足大多数命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-173">Otherwise, the temporary connection created by the **ComputerName** parameter is sufficient for most commands.</span></span>

<span data-ttu-id="972dd-174">有关会话的详细信息，请参阅 about_PSSessions。</span><span class="sxs-lookup"><span data-stu-id="972dd-174">For more information about sessions, see about_PSSessions.</span></span>

### <a name="can-i-run-commands-on-more-than-one-computer-at-a-time"></a><span data-ttu-id="972dd-175">是否可以一次在多台计算机上运行命令？</span><span class="sxs-lookup"><span data-stu-id="972dd-175">Can I run commands on more than one computer at a time?</span></span>

<span data-ttu-id="972dd-176">是的。</span><span class="sxs-lookup"><span data-stu-id="972dd-176">Yes.</span></span> <span data-ttu-id="972dd-177">此 cmdlet 的 **ComputerName** 参数 `Invoke-Command` 接受多个计算机名称， **Session** 参数接受多个 pssession。</span><span class="sxs-lookup"><span data-stu-id="972dd-177">The **ComputerName** parameter of the `Invoke-Command` cmdlet accepts multiple computer names, and the **Session** parameter accepts multiple PSSessions.</span></span>

<span data-ttu-id="972dd-178">运行命令时，PowerShell 会在所有指定的 `Invoke-Command` 计算机上或在所有指定的 pssession 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-178">When you run an `Invoke-Command` command, PowerShell runs the commands on all of the specified computers or in all of the specified PSSessions.</span></span>

<span data-ttu-id="972dd-179">PowerShell 可以管理数百个并发远程连接。</span><span class="sxs-lookup"><span data-stu-id="972dd-179">PowerShell can manage hundreds of concurrent remote connections.</span></span> <span data-ttu-id="972dd-180">但是，您可以发送的远程命令的数量可能会受到您的计算机的资源和用于建立和维护多个网络连接的容量的限制。</span><span class="sxs-lookup"><span data-stu-id="972dd-180">However, the number of remote commands that you can send might be limited by the resources of your computer and its capacity to establish and maintain multiple network connections.</span></span>

<span data-ttu-id="972dd-181">有关详细信息，请参阅帮助主题中的示例 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="972dd-181">For more information, see the example in the `Invoke-Command` Help topic.</span></span>

### <a name="where-are-my-profiles"></a><span data-ttu-id="972dd-182">我的配置文件在哪里？</span><span class="sxs-lookup"><span data-stu-id="972dd-182">Where are my profiles?</span></span>

<span data-ttu-id="972dd-183">PowerShell 配置文件不会自动在远程会话中运行，因此该配置文件添加的命令不会出现在会话中。</span><span class="sxs-lookup"><span data-stu-id="972dd-183">PowerShell profiles are not run automatically in remote sessions, so the commands that the profile adds are not present in the session.</span></span> <span data-ttu-id="972dd-184">此外，在 `$profile` 远程会话中不填充自动变量。</span><span class="sxs-lookup"><span data-stu-id="972dd-184">In addition, the `$profile` automatic variable is not populated in remote sessions.</span></span>

<span data-ttu-id="972dd-185">若要在会话中运行配置文件，请使用 `Invoke-Command` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="972dd-185">To run a profile in a session, use the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="972dd-186">例如，以下命令在的会话中运行本地计算机的 CurrentUserCurrentHost 配置文件 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="972dd-186">For example, the following command runs the CurrentUserCurrentHost profile from the local computer in the session in `$s`.</span></span>

```
Invoke-Command -Session $s -FilePath $profile
```

<span data-ttu-id="972dd-187">以下命令在的会话中从远程计算机运行 CurrentUserCurrentHost 配置文件 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="972dd-187">The following command runs the CurrentUserCurrentHost profile from the remote computer in the session in `$s`.</span></span> <span data-ttu-id="972dd-188">由于 `$profile` 未填充变量，因此该命令使用配置文件的显式路径。</span><span class="sxs-lookup"><span data-stu-id="972dd-188">Because the `$profile` variable is not populated, the command uses the explicit path to the profile.</span></span>

```powershell
Invoke-Command -Session $s {
  . "$home\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1"
}
```

<span data-ttu-id="972dd-189">运行此命令后，配置文件添加到会话中的命令在中可用 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="972dd-189">After running this command, the commands that the profile adds to the session are available in `$s`.</span></span>

<span data-ttu-id="972dd-190">你还可以使用会话配置中的启动脚本在使用会话配置的每个远程会话中运行配置文件。</span><span class="sxs-lookup"><span data-stu-id="972dd-190">You can also use a startup script in a session configuration to run a profile in every remote session that uses the session configuration.</span></span>

<span data-ttu-id="972dd-191">有关 PowerShell 配置文件的详细信息，请参阅 about_Profiles。</span><span class="sxs-lookup"><span data-stu-id="972dd-191">For more information about PowerShell profiles, see about_Profiles.</span></span>
<span data-ttu-id="972dd-192">有关会话配置的详细信息，请参阅 `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="972dd-192">For more information about session configurations, see `Register-PSSessionConfiguration`.</span></span>

### <a name="how-does-throttling-work-on-remote-commands"></a><span data-ttu-id="972dd-193">限制如何处理远程命令？</span><span class="sxs-lookup"><span data-stu-id="972dd-193">How does throttling work on remote commands?</span></span>

<span data-ttu-id="972dd-194">为帮助你管理本地计算机上的资源，PowerShell 包含一个基于命令的限制功能，该功能使你能够限制为每个命令建立的并发远程连接的数量。</span><span class="sxs-lookup"><span data-stu-id="972dd-194">To help you manage the resources on your local computer, PowerShell includes a per-command throttling feature that lets you limit the number of concurrent remote connections that are established for each command.</span></span>

<span data-ttu-id="972dd-195">默认值为32并发连接，但你可以使用 cmdlet 的 **ThrottleLimit** 参数为特定命令设置自定义限制限制。</span><span class="sxs-lookup"><span data-stu-id="972dd-195">The default is 32 concurrent connections, but you can use the **ThrottleLimit** parameter of the cmdlets to set a custom throttle limit for particular commands.</span></span>

<span data-ttu-id="972dd-196">使用限制功能时，请记住，它应用于每个命令，而不是应用于整个会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="972dd-196">When you use the throttling feature, remember that it is applied to each command, not to the entire session or to the computer.</span></span> <span data-ttu-id="972dd-197">如果在多个会话或 Pssession 中并发运行命令，则并发连接数是所有会话中的并发连接数之和。</span><span class="sxs-lookup"><span data-stu-id="972dd-197">If you are running commands concurrently in several sessions or PSSessions, the number of concurrent connections is the sum of the concurrent connections in all the sessions.</span></span>

<span data-ttu-id="972dd-198">若要查找具有 **ThrottleLimit** 参数的 cmdlet，请键入：</span><span class="sxs-lookup"><span data-stu-id="972dd-198">To find cmdlets with a **ThrottleLimit** parameter, type:</span></span>

```
Get-Help * -Parameter ThrottleLimit
-or-
Get-Command -ParameterName ThrottleLimit
```

### <a name="is-the-output-of-remote-commands-different-from-local-output"></a><span data-ttu-id="972dd-199">远程命令的输出是否与本地输出不同？</span><span class="sxs-lookup"><span data-stu-id="972dd-199">Is the output of remote commands different from local output?</span></span>

<span data-ttu-id="972dd-200">当你在本地使用 PowerShell 时，将发送和接收 "live" .NET Framework 对象;"实时" 对象是与实际程序或系统组件关联的对象。</span><span class="sxs-lookup"><span data-stu-id="972dd-200">When you use PowerShell locally, you send and receive "live" .NET Framework objects; "live" objects are objects that are associated with actual programs or system components.</span></span> <span data-ttu-id="972dd-201">在调用方法或更改活动对象的属性时，所做更改会影响实际的程序或组件。</span><span class="sxs-lookup"><span data-stu-id="972dd-201">When you invoke the methods or change the properties of live objects, the changes affect the actual program or component.</span></span> <span data-ttu-id="972dd-202">当程序或组件的属性发生更改时，表示它们的对象的属性也会发生更改。</span><span class="sxs-lookup"><span data-stu-id="972dd-202">And, when the properties of a program or component change, the properties of the object that represent them also change.</span></span>

<span data-ttu-id="972dd-203">但是，由于大多数实时对象无法通过网络进行传输，因此 PowerShell 会 "序列化" 远程命令中发送的大多数对象，也就是说，它将每个对象转换为 XML [Export-clixml] 中的一系列 XML (约束语言，) 用于传输的数据元素。</span><span class="sxs-lookup"><span data-stu-id="972dd-203">However, because most live objects cannot be transmitted over the network, PowerShell "serializes" most of the objects sent in remote commands, that is, it converts each object into a series of XML (Constraint Language in XML [CLiXML]) data elements for transmission.</span></span>

<span data-ttu-id="972dd-204">当 PowerShell 接收到序列化对象时，它会将 XML 转换为反序列化的对象类型。</span><span class="sxs-lookup"><span data-stu-id="972dd-204">When PowerShell receives a serialized object, it converts the XML into a deserialized object type.</span></span> <span data-ttu-id="972dd-205">反序列化的对象是之前的程序或组件的属性的准确记录，但它不再 "实时"，也就是说，它不再与组件直接关联。</span><span class="sxs-lookup"><span data-stu-id="972dd-205">The deserialized object is an accurate record of the properties of the program or component at a previous time, but it is no longer "live", that is, it is no longer directly associated with the component.</span></span> <span data-ttu-id="972dd-206">和将删除这些方法，因为它们不再有效。</span><span class="sxs-lookup"><span data-stu-id="972dd-206">And, the methods are removed because they are no longer effective.</span></span>

<span data-ttu-id="972dd-207">通常，您可以像使用活动对象一样使用反序列化的对象，但必须知道它们的局限性。</span><span class="sxs-lookup"><span data-stu-id="972dd-207">Typically, you can use deserialized objects just as you would use live objects, but you must be aware of their limitations.</span></span> <span data-ttu-id="972dd-208">此外，该 cmdlet 返回的对象 `Invoke-Command` 还有其他属性，可帮助你确定命令源。</span><span class="sxs-lookup"><span data-stu-id="972dd-208">Also, the objects that are returned by the `Invoke-Command` cmdlet have additional properties that help you to determine the origin of the command.</span></span>

<span data-ttu-id="972dd-209">某些对象类型（如 DirectoryInfo 对象和 Guid）在收到时转换回活动对象。</span><span class="sxs-lookup"><span data-stu-id="972dd-209">Some object types, such as DirectoryInfo objects and GUIDs, are converted back into live objects when they are received.</span></span> <span data-ttu-id="972dd-210">这些对象不需要任何特殊的处理或格式。</span><span class="sxs-lookup"><span data-stu-id="972dd-210">These objects do not need any special handling or formatting.</span></span>

<span data-ttu-id="972dd-211">有关解释和格式化远程输出的信息，请参阅 [about_Remote_Output](about_Remote_Output.md)。</span><span class="sxs-lookup"><span data-stu-id="972dd-211">For information about interpreting and formatting remote output, see [about_Remote_Output](about_Remote_Output.md).</span></span>

### <a name="can-i-run-background-jobs-remotely"></a><span data-ttu-id="972dd-212">可以远程运行后台作业吗？</span><span class="sxs-lookup"><span data-stu-id="972dd-212">Can I run background jobs remotely?</span></span>

<span data-ttu-id="972dd-213">是的。</span><span class="sxs-lookup"><span data-stu-id="972dd-213">Yes.</span></span> <span data-ttu-id="972dd-214">PowerShell 后台作业是一个在不与会话交互的情况下异步运行的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-214">A PowerShell background job is a PowerShell command that runs asynchronously without interacting with the session.</span></span> <span data-ttu-id="972dd-215">启动后台作业时，命令提示符会立即返回，你可以继续在该会话中运行，即使该作业长时间运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="972dd-215">When you start a background job, the command prompt returns immediately, and you can continue to work in the session while the job runs even if it runs for an extended period of time.</span></span>

<span data-ttu-id="972dd-216">即使其他命令正在运行，也可以启动后台作业，因为后台作业始终在临时会话中以异步方式运行。</span><span class="sxs-lookup"><span data-stu-id="972dd-216">You can start a background job even while other commands are running because background jobs always run asynchronously in a temporary session.</span></span>

<span data-ttu-id="972dd-217">可以在本地或远程计算机上运行后台作业。</span><span class="sxs-lookup"><span data-stu-id="972dd-217">You can run background jobs on a local or remote computer.</span></span> <span data-ttu-id="972dd-218">默认情况下，后台作业在本地计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="972dd-218">By default, a background job runs on the local computer.</span></span> <span data-ttu-id="972dd-219">但是，可以使用 cmdlet 的 **AsJob** 参数将 `Invoke-Command` 任何远程命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="972dd-219">However, you can use the **AsJob** parameter of the `Invoke-Command` cmdlet to run any remote command as a background job.</span></span> <span data-ttu-id="972dd-220">您也可以使用 `Invoke-Command` `Start-Job` 远程运行命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-220">And, you can use `Invoke-Command` to run a `Start-Job` command remotely.</span></span>

<span data-ttu-id="972dd-221">有关 PowerShell 中的后台作业的详细信息，请参阅 [about_Jobs (about_Jobs md) ] 和 [about_Remote_Jobs (about_Remote_Jobs。</span><span class="sxs-lookup"><span data-stu-id="972dd-221">For more information about background jobs in PowerShell , see [about_Jobs(about_Jobs.md)] and [about_Remote_Jobs(about_Remote_Jobs.md)].</span></span>

### <a name="can-i-run-windows-programs-on-a-remote-computer"></a><span data-ttu-id="972dd-222">能否在远程计算机上运行 windows 程序？</span><span class="sxs-lookup"><span data-stu-id="972dd-222">Can I run windows programs on a remote computer?</span></span>

<span data-ttu-id="972dd-223">你可以使用 PowerShell 远程命令在远程计算机上运行基于 Windows 的程序。</span><span class="sxs-lookup"><span data-stu-id="972dd-223">You can use PowerShell remote commands to run Windows-based programs on remote computers.</span></span> <span data-ttu-id="972dd-224">例如，你可以 `Shutdown.exe` `Ipconfig.exe` 在远程计算机上运行或。</span><span class="sxs-lookup"><span data-stu-id="972dd-224">For example, you can run `Shutdown.exe` or `Ipconfig.exe` on a remote computer.</span></span>

<span data-ttu-id="972dd-225">但是，不能使用 PowerShell 命令打开远程计算机上任何程序的用户界面。</span><span class="sxs-lookup"><span data-stu-id="972dd-225">However, you cannot use PowerShell commands to open the user interface for any program on a remote computer.</span></span>

<span data-ttu-id="972dd-226">当你启动远程计算机上的 Windows 程序时，该命令不会完成，并且 PowerShell 命令提示符将不会返回，直到该程序完成或按下<kbd>CTRL</kbd> + <kbd>C</kbd>来中断命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-226">When you start a Windows program on a remote computer, the command is not completed, and the PowerShell command prompt does not return, until the program is finished or until you press <kbd>CTRL</kbd>+<kbd>C</kbd> to interrupt the command.</span></span> <span data-ttu-id="972dd-227">例如，如果在 `Ipconfig.exe` 远程计算机上运行该程序，则命令提示符直到完成后才会返回 `Ipconfig.exe` 。</span><span class="sxs-lookup"><span data-stu-id="972dd-227">For example, if you run the `Ipconfig.exe` program on a remote computer, the command prompt does not return until `Ipconfig.exe` is completed.</span></span>

<span data-ttu-id="972dd-228">如果使用远程命令来启动具有用户界面的程序，程序进程将启动，但不会显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="972dd-228">If you use remote commands to start a program that has a user interface, the program process starts, but the user interface does not appear.</span></span> <span data-ttu-id="972dd-229">PowerShell 命令未完成，并且在你停止程序进程或按下<kbd>CTRL</kbd>C 之后，命令提示符才会返回， + <kbd>C</kbd>这会中断命令并停止进程。</span><span class="sxs-lookup"><span data-stu-id="972dd-229">The PowerShell command is not completed, and the command prompt does not return until you stop the program process or until you press <kbd>CTRL</kbd>+<kbd>C</kbd>, which interrupts the command and stops the process.</span></span>

<span data-ttu-id="972dd-230">例如，如果使用 PowerShell 命令 `Notepad` 在远程计算机上运行，则记事本进程将在远程计算机上启动，但不会显示记事本用户界面。</span><span class="sxs-lookup"><span data-stu-id="972dd-230">For example, if you use a PowerShell command to run `Notepad` on a remote computer, the Notepad process starts on the remote computer, but the Notepad user interface does not appear.</span></span> <span data-ttu-id="972dd-231">若要中断该命令并还原命令提示符，请按<kbd>CTRL</kbd>+ + <kbd>C</kbd>。</span><span class="sxs-lookup"><span data-stu-id="972dd-231">To interrupt the command and restore the command prompt, press <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span>

### <a name="can-i-limit-the-commands-that-users-can-run-remotely-on-my-computer"></a><span data-ttu-id="972dd-232">能否限制用户可在我的计算机上远程运行的命令？</span><span class="sxs-lookup"><span data-stu-id="972dd-232">Can I limit the commands that users can run remotely on my computer?</span></span>

<span data-ttu-id="972dd-233">是的。</span><span class="sxs-lookup"><span data-stu-id="972dd-233">Yes.</span></span> <span data-ttu-id="972dd-234">每个远程会话都必须使用远程计算机上的一个会话配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-234">Every remote session must use one of the session configurations on the remote computer.</span></span> <span data-ttu-id="972dd-235">你可以管理计算机上的会话配置 (和这些会话配置的权限) 确定哪些用户可以在你的计算机上远程运行命令和可以运行的命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-235">You can manage the session configurations on your computer (and the permissions to those session configurations) to determine who can run commands remotely on your computer and which commands they can run.</span></span>

<span data-ttu-id="972dd-236">会话配置配置会话的环境。</span><span class="sxs-lookup"><span data-stu-id="972dd-236">A session configuration configures the environment for the session.</span></span> <span data-ttu-id="972dd-237">您可以通过使用实现新的配置类的程序集或使用在会话中运行的脚本来定义配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-237">You can define the configuration by using an assembly that implements a new configuration class or by using a script that runs in the session.</span></span> <span data-ttu-id="972dd-238">此配置可以确定会话中可用的命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-238">The configuration can determine the commands that are available in the session.</span></span>
<span data-ttu-id="972dd-239">而且，配置可以包括用于保护计算机的设置，例如，用于限制在单个对象或命令中会话可以远程接收的数据量的设置。</span><span class="sxs-lookup"><span data-stu-id="972dd-239">And, the configuration can include settings that protect the computer, such as settings that limit the amount of data that the session can receive remotely in a single object or command.</span></span> <span data-ttu-id="972dd-240">您还可以指定一个安全描述符，以确定使用配置所需的权限。</span><span class="sxs-lookup"><span data-stu-id="972dd-240">You can also specify a security descriptor that determines the permissions that are required to use the configuration.</span></span>

<span data-ttu-id="972dd-241">该 `Enable-PSRemoting` cmdlet 将在你的计算机上创建默认会话配置： microsoft.powershell32 (64 位操作系统仅) 的操作系统。</span><span class="sxs-lookup"><span data-stu-id="972dd-241">The `Enable-PSRemoting` cmdlet creates the default session configurations on your computer: Microsoft.PowerShell, Microsoft.PowerShell.Workflow, and Microsoft.PowerShell32 (64-bit operating systems only).</span></span> <span data-ttu-id="972dd-242">`Enable-PSRemoting` 设置配置的安全描述符，以只允许计算机上 Administrators 组的成员使用这些配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-242">`Enable-PSRemoting` sets the security descriptor for the configuration to allow only members of the Administrators group on your computer to use them.</span></span>

<span data-ttu-id="972dd-243">你可以使用会话配置 cmdlet 来编辑默认会话配置、创建新的会话配置，以及更改所有会话配置的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="972dd-243">You can use the session configuration cmdlets to edit the default session configurations, to create new session configurations, and to change the security descriptors of all the session configurations.</span></span>

<span data-ttu-id="972dd-244">从 Windows PowerShell 3.0 开始， `New-PSSessionConfigurationFile` cmdlet 可让你使用文本文件创建自定义会话配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-244">Beginning in Windows PowerShell 3.0, the `New-PSSessionConfigurationFile` cmdlet lets you create custom session configurations by using a text file.</span></span> <span data-ttu-id="972dd-245">此文件包含用于设置语言模式和指定在使用会话配置的会话中可用的 cmdlet 和模块的选项。</span><span class="sxs-lookup"><span data-stu-id="972dd-245">The file includes options for setting the language mode and for specifying the cmdlets and modules that are available in sessions that use the session configuration.</span></span>

<span data-ttu-id="972dd-246">用户使用 `Invoke-Command` 、 `New-PSSession` 或 `Enter-PSSession` cmdlet 时，可以使用 **ConfigurationName** 参数来指示用于会话的会话配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-246">When users use the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets, they can use the **ConfigurationName** parameter to indicate the session configuration that is used for the session.</span></span> <span data-ttu-id="972dd-247">而且，他们可以通过更改 `$PSSessionConfigurationName` 会话中首选项变量的值来更改其会话使用的默认配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-247">And, they can change the default configuration that their sessions use by changing the value of the `$PSSessionConfigurationName` preference variable in the session.</span></span>

<span data-ttu-id="972dd-248">有关会话配置的详细信息，请参阅会话配置 cmdlet 的帮助。</span><span class="sxs-lookup"><span data-stu-id="972dd-248">For more information about session configurations, see the Help for the session configuration cmdlets.</span></span> <span data-ttu-id="972dd-249">若要查找会话配置 cmdlet，请键入：</span><span class="sxs-lookup"><span data-stu-id="972dd-249">To find the session configuration cmdlets, type:</span></span>

```powershell
Get-Command *PSSessionConfiguration
```

### <a name="what-are-fan-in-and-fan-out-configurations"></a><span data-ttu-id="972dd-250">风扇的配置和扇出配置是什么？</span><span class="sxs-lookup"><span data-stu-id="972dd-250">What are fan in and fan out configurations?</span></span>

<span data-ttu-id="972dd-251">涉及多台计算机的最常见的 PowerShell 远程处理方案是一对多配置，在这种配置中，一台本地计算机 (管理员的计算机) 在许多远程计算机上运行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-251">The most common PowerShell remoting scenario involving multiple computers is the one-to-many configuration, in which one local computer (the administrator's computer) runs PowerShell commands on numerous remote computers.</span></span> <span data-ttu-id="972dd-252">这称为 "扇出" 方案。</span><span class="sxs-lookup"><span data-stu-id="972dd-252">This is known as the "fan-out" scenario.</span></span>

<span data-ttu-id="972dd-253">但是，在某些企业中，配置为多对一，其中许多客户端计算机连接到运行 PowerShell 的单台远程计算机，如文件服务器或展台。</span><span class="sxs-lookup"><span data-stu-id="972dd-253">However, in some enterprises, the configuration is many-to-one, where many client computers connect to a single remote computer that is running PowerShell, such as a file server or a kiosk.</span></span> <span data-ttu-id="972dd-254">这称为 "扇入" 配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-254">This is known as the "fan-in" configuration.</span></span>

<span data-ttu-id="972dd-255">PowerShell 远程处理同时支持扇出和扇入配置。</span><span class="sxs-lookup"><span data-stu-id="972dd-255">PowerShell remoting supports both fan-out and fan-in configurations.</span></span>

<span data-ttu-id="972dd-256">对于扇出配置，PowerShell 使用 Web 服务进行管理 (WS-MANAGEMENT) 协议和 WinRM 服务，后者支持 WS-MANAGEMENT 的 Microsoft 实现。</span><span class="sxs-lookup"><span data-stu-id="972dd-256">For the fan-out configuration, PowerShell uses the Web Services for Management (WS-Management) protocol and the WinRM service that supports the Microsoft implementation of WS-Management.</span></span> <span data-ttu-id="972dd-257">当本地计算机连接到远程计算机时，WS-Management 会建立一个连接，并使用用于 PowerShell 的插件启动 PowerShell 主机进程， ( 在远程计算机上 # A0) 。</span><span class="sxs-lookup"><span data-stu-id="972dd-257">When a local computer connects to a remote computer, WS-Management establishes a connection and uses a plug-in for PowerShell to start the PowerShell host process (Wsmprovhost.exe) on the remote computer.</span></span> <span data-ttu-id="972dd-258">用户可以指定备用端口、备用会话配置以及用于自定义远程连接的其他功能。</span><span class="sxs-lookup"><span data-stu-id="972dd-258">The user can specify an alternate port, an alternate session configuration, and other features to customize the remote connection.</span></span>

<span data-ttu-id="972dd-259">为了支持 "扇入" 配置，PowerShell 使用 internet 信息服务 (IIS) 承载 WS-MANAGEMENT、加载 PowerShell 插件以及启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="972dd-259">To support the "fan-in" configuration, PowerShell uses internet Information Services (IIS) to host WS-Management, to load the PowerShell plug-in, and to start PowerShell.</span></span> <span data-ttu-id="972dd-260">在这种情况下，不是在单独的进程中启动每个 PowerShell 会话，而是在同一主机进程中运行所有 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="972dd-260">In this scenario, instead of starting each PowerShell session in a separate process, all PowerShell sessions run in the same host process.</span></span>

<span data-ttu-id="972dd-261">Windows XP 或 Windows Server 2003 不支持 IIS 承载和扇入远程管理。</span><span class="sxs-lookup"><span data-stu-id="972dd-261">IIS hosting and fan-in remote management is not supported in Windows XP or in Windows Server 2003.</span></span>

<span data-ttu-id="972dd-262">在扇入配置中，用户可以指定连接 URI 和 HTTP 终结点，包括传输、计算机名称、端口和应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="972dd-262">In a fan-in configuration, the user can specify a connection URI and an HTTP endpoint, including the transport, computer name, port, and application name.</span></span>
<span data-ttu-id="972dd-263">IIS 将具有指定应用程序名称的所有请求转发到应用程序。</span><span class="sxs-lookup"><span data-stu-id="972dd-263">IIS forwards all the requests with a specified application name to the application.</span></span> <span data-ttu-id="972dd-264">默认值为 WS-MANAGEMENT，它可以承载 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="972dd-264">The default is WS-Management, which can host PowerShell.</span></span>

<span data-ttu-id="972dd-265">还可以指定身份验证机制，并禁止或允许从 HTTP 和 HTTPS 终结点重定向。</span><span class="sxs-lookup"><span data-stu-id="972dd-265">You can also specify an authentication mechanism and prohibit or allow redirection from HTTP and HTTPS endpoints.</span></span>

### <a name="can-i-test-remoting-on-a-single-computer-not-in-a-domain"></a><span data-ttu-id="972dd-266">能否在不在域中的单台计算机上测试远程处理？</span><span class="sxs-lookup"><span data-stu-id="972dd-266">Can I test remoting on a single computer not in a domain?</span></span>

<span data-ttu-id="972dd-267">是的。</span><span class="sxs-lookup"><span data-stu-id="972dd-267">Yes.</span></span> <span data-ttu-id="972dd-268">即使本地计算机不在域中，也可以使用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="972dd-268">PowerShell remoting is available even when the local computer is not in a domain.</span></span> <span data-ttu-id="972dd-269">可以使用远程处理功能连接到会话并在同一台计算机上创建会话。</span><span class="sxs-lookup"><span data-stu-id="972dd-269">You can use the remoting features to connect to sessions and to create sessions on the same computer.</span></span> <span data-ttu-id="972dd-270">功能的工作方式与连接到远程计算机时的功能相同。</span><span class="sxs-lookup"><span data-stu-id="972dd-270">The features work the same as they do when you connect to a remote computer.</span></span>

<span data-ttu-id="972dd-271">若要在工作组中的计算机上运行远程命令，请在计算机上更改以下 Windows 设置。</span><span class="sxs-lookup"><span data-stu-id="972dd-271">To run remote commands on a computer in a workgroup, change the following Windows settings on the computer.</span></span>

<span data-ttu-id="972dd-272">注意：这些设置会影响系统上的所有用户，并使系统更易受到恶意攻击。</span><span class="sxs-lookup"><span data-stu-id="972dd-272">Caution: These settings affect all users on the system and they can make the system more vulnerable to a malicious attack.</span></span> <span data-ttu-id="972dd-273">进行这些更改时请务必小心。</span><span class="sxs-lookup"><span data-stu-id="972dd-273">Use caution when making these changes.</span></span>

- <span data-ttu-id="972dd-274">Windows Vista、Windows 7、Windows 8：</span><span class="sxs-lookup"><span data-stu-id="972dd-274">Windows Vista, Windows 7, Windows 8:</span></span>

  <span data-ttu-id="972dd-275">创建以下注册表项，然后将其值设置为1： LocalAccountTokenFilterPolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span><span class="sxs-lookup"><span data-stu-id="972dd-275">Create the following registry entry, and then set its value to 1: LocalAccountTokenFilterPolicy in ` HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`</span></span>

  <span data-ttu-id="972dd-276">你可以使用以下 PowerShell 命令来添加此项：</span><span class="sxs-lookup"><span data-stu-id="972dd-276">You can use the following PowerShell command to add this entry:</span></span>

    ```powershell
    $parameters = @{
      Path='HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'
      Name='LocalAccountTokenFilterPolicy'
      propertyType='DWord'
      Value=1
    }
    New-ItemProperty @parameters
    ```

- <span data-ttu-id="972dd-277">Windows Server 2003，Windows Server 2008，Windows Server 2012，Windows Server 2012 R2：</span><span class="sxs-lookup"><span data-stu-id="972dd-277">Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2012 R2:</span></span>

  <span data-ttu-id="972dd-278">不需要进行任何更改，因为 "网络访问：本地帐户的共享和安全模型" 策略的默认设置为 "经典"。</span><span class="sxs-lookup"><span data-stu-id="972dd-278">No changes are needed because the default setting of the "Network Access: Sharing and security model for local accounts" policy is "Classic".</span></span> <span data-ttu-id="972dd-279">验证设置是否已更改。</span><span class="sxs-lookup"><span data-stu-id="972dd-279">Verify the setting in case it has changed.</span></span>

### <a name="can-i-run-remote-commands-on-a-computer-in-another-domain"></a><span data-ttu-id="972dd-280">是否可以在另一个域中的计算机上运行远程命令？</span><span class="sxs-lookup"><span data-stu-id="972dd-280">Can I run remote commands on a computer in another domain?</span></span>

<span data-ttu-id="972dd-281">是的。</span><span class="sxs-lookup"><span data-stu-id="972dd-281">Yes.</span></span> <span data-ttu-id="972dd-282">通常，命令运行时不会出错，但你可能需要使用、 **Credential** 或 Cmdlet 的 Credential `Invoke-Command` 参数 `New-PSSession` `Enter-PSSession` 提供远程计算机上 Administrators 组的成员的凭据。</span><span class="sxs-lookup"><span data-stu-id="972dd-282">Typically, the commands run without error, although you might need to use the **Credential** parameter of the `Invoke-Command`, `New-PSSession`, or `Enter-PSSession` cmdlets to provide the credentials of a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="972dd-283">即使当前用户是本地和远程计算机上的 Administrators 组的成员，也需要进行这种情况。</span><span class="sxs-lookup"><span data-stu-id="972dd-283">This is sometimes required even when the current user is a member of the Administrators group on the local and remote computers.</span></span>

<span data-ttu-id="972dd-284">但是，如果远程计算机不在本地计算机信任的域中，则远程计算机可能无法对用户的凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="972dd-284">However, if the remote computer is not in a domain that the local computer trusts, the remote computer might not be able to authenticate the user's credentials.</span></span>

<span data-ttu-id="972dd-285">若要启用身份验证，请使用以下命令将远程计算机添加到 WinRM 中本地计算机的受信任主机列表。</span><span class="sxs-lookup"><span data-stu-id="972dd-285">To enable authentication, use the following command to add the remote computer to the list of trusted hosts for the local computer in WinRM.</span></span> <span data-ttu-id="972dd-286">在 PowerShell 提示符下键入命令。</span><span class="sxs-lookup"><span data-stu-id="972dd-286">Type the command at the PowerShell prompt.</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value <Remote-computer-name>
```

<span data-ttu-id="972dd-287">例如，要将 Server01 计算机添加到本地计算机上的受信任主机列表，请在 PowerShell 提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="972dd-287">For example, to add the Server01 computer to the list of trusted hosts on the local computer, type the following command at the PowerShell prompt:</span></span>

```powershell
Set-Item WSMan:\localhost\Client\TrustedHosts -Value Server01
```


## <a name="see-also"></a><span data-ttu-id="972dd-288">另请参阅</span><span class="sxs-lookup"><span data-stu-id="972dd-288">See also</span></span>

[<span data-ttu-id="972dd-289">about_Remote</span><span class="sxs-lookup"><span data-stu-id="972dd-289">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="972dd-290">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="972dd-290">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="972dd-291">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="972dd-291">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="972dd-292">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="972dd-292">about_Remote_Jobs</span></span>](about_Remote_Jobs.md)

[<span data-ttu-id="972dd-293">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="972dd-293">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="972dd-294">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="972dd-294">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="972dd-295">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="972dd-295">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
