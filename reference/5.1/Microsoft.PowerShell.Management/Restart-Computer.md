---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 553b61c9669afab325e9feec101d701c2b9a7c83
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198996"
---
# <span data-ttu-id="ad6ff-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="ad6ff-103">Restart-Computer</span></span>

## <span data-ttu-id="ad6ff-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ad6ff-104">SYNOPSIS</span></span>
<span data-ttu-id="ad6ff-105">重新启动本地和远程计算机上的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="ad6ff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ad6ff-106">SYNTAX</span></span>

### <span data-ttu-id="ad6ff-107">DefaultSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="ad6ff-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-DcomAuthentication <AuthenticationLevel>] [-Impersonation <ImpersonationLevel>]
 [-WsmanAuthentication <String>] [-Protocol <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ad6ff-108">AsJobSet</span><span class="sxs-lookup"><span data-stu-id="ad6ff-108">AsJobSet</span></span>

```
Restart-Computer [-AsJob] [-DcomAuthentication <AuthenticationLevel>]
 [-Impersonation <ImpersonationLevel>] [[-ComputerName] <String[]>] [[-Credential] <PSCredential>]
 [-Force] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ad6ff-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ad6ff-109">DESCRIPTION</span></span>

<span data-ttu-id="ad6ff-110">`Restart-Computer`Cmdlet 将重新启动本地和远程计算机上的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-110">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="ad6ff-111">您可以使用的参数将 `Restart-Computer` 重新启动操作作为后台作业运行，指定身份验证级别和备用凭据，限制同时运行的操作，并强制立即重新启动。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-111">You can use the parameters of `Restart-Computer` to run the restart operations as a background job, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="ad6ff-112">从 Windows PowerShell 3.0 开始，可以等待重新启动完成，然后再运行下一个命令。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-112">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="ad6ff-113">指定等待超时和查询间隔，并等待特定服务在重新启动的计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-113">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="ad6ff-114">此功能使 `Restart-Computer` 在脚本和函数中使用成为现实。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-114">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

<span data-ttu-id="ad6ff-115">您可以使用 WS-Management (WSMan) 协议来重新启动计算机，在这种情况下，分布式组件对象模型 (DCOM) 调用被阻止，如企业防火墙。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-115">You can use the WS-Management (WSMan) protocol to restart the computer, in case Distributed Component Object Model (DCOM) calls are blocked, such as by an enterprise firewall.</span></span> <span data-ttu-id="ad6ff-116">有关详细信息，请参阅 [WS-Management 协议](/windows/desktop/WinRM/ws-management-protocol)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-116">For more information, see [WS-Management Protocol](/windows/desktop/WinRM/ws-management-protocol).</span></span>

<span data-ttu-id="ad6ff-117">只有在命令中使用了 **AsJob** 参数的情况下，此 cmdlet 才需要使用 Windows PowerShell 远程处理功能。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-117">This cmdlet requires Windows PowerShell remoting only when you use the **AsJob** parameter in a command.</span></span>

## <span data-ttu-id="ad6ff-118">示例</span><span class="sxs-lookup"><span data-stu-id="ad6ff-118">EXAMPLES</span></span>

### <span data-ttu-id="ad6ff-119">示例1：重新启动本地计算机</span><span class="sxs-lookup"><span data-stu-id="ad6ff-119">Example 1: Restart the local computer</span></span>

<span data-ttu-id="ad6ff-120">`Restart-Computer` 重新启动本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-120">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="ad6ff-121">示例2：重新启动多台计算机</span><span class="sxs-lookup"><span data-stu-id="ad6ff-121">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="ad6ff-122">`Restart-Computer` 可以重新启动远程和本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-122">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="ad6ff-123">**ComputerName** 参数接受计算机名称的数组。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-123">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="ad6ff-124">示例3：重新启动计算机作为后台作业</span><span class="sxs-lookup"><span data-stu-id="ad6ff-124">Example 3: Restart computers as a background job</span></span>

<span data-ttu-id="ad6ff-125">这些命令 `Restart-Computer` 在两台远程计算机上将命令作为后台作业运行，然后获取结果。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-125">These commands run a `Restart-Computer` command as a background job on two remote computers, and then get the results.</span></span>

<span data-ttu-id="ad6ff-126">由于 **AsJob** 在本地计算机上创建作业，并自动将结果返回到本地计算机，因此你可以 `Receive-Job` 将其作为本地命令运行。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-126">Because **AsJob** creates the job on the local computer and automatically returns the results to the local computer, you can run `Receive-Job` as a local command.</span></span>

```powershell
$Job = Restart-Computer -ComputerName "Server01", "Server02" -AsJob
$Job | Receive-Job
```

<span data-ttu-id="ad6ff-127">`Restart-Computer` 使用 **ComputerName** 参数指定 **Server01** 和 **Server02** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-127">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** and **Server02** .</span></span> <span data-ttu-id="ad6ff-128">**AsJob** 参数将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-128">The **AsJob** parameter runs the command as a background job.</span></span> <span data-ttu-id="ad6ff-129">作业对象存储在 `$Job` 变量中。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-129">The job object is stored in the `$Job` variable.</span></span> <span data-ttu-id="ad6ff-130">`$Job` 将管道向下发送到 `Receive-Job` 获取结果的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-130">`$Job` is sent down the pipeline to the `Receive-Job` cmdlet that gets the results.</span></span>

### <span data-ttu-id="ad6ff-131">示例4：重新启动远程计算机</span><span class="sxs-lookup"><span data-stu-id="ad6ff-131">Example 4: Restart a remote computer</span></span>

<span data-ttu-id="ad6ff-132">`Restart-Computer` 使用自定义模拟和身份验证设置重新启动远程计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-132">`Restart-Computer` restarts a remote computer with customized impersonation and authentication settings.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Impersonation Anonymous -DcomAuthentication PacketIntegrity
```

<span data-ttu-id="ad6ff-133">`Restart-Computer` 使用 **ComputerName** 参数指定 **Server01** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-133">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** .</span></span> <span data-ttu-id="ad6ff-134">**模拟** 参数指定 Anonymous 以隐藏请求者的标识。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-134">The **Impersonation** parameter specifies Anonymous to hide the requester's identity.</span></span> <span data-ttu-id="ad6ff-135">**DcomAuthentication** 参数将 PacketIntegrity 指定为连接的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-135">The **DcomAuthentication** parameter specifies PacketIntegrity as the connection's authentication level.</span></span>

### <span data-ttu-id="ad6ff-136">示例5：强制重新启动文本文件中列出的计算机</span><span class="sxs-lookup"><span data-stu-id="ad6ff-136">Example 5: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="ad6ff-137">此示例强制立即重新启动文件中列出的计算机 `Domain01.txt` 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-137">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="ad6ff-138">文本文件中的计算机名称存储在变量中。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-138">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="ad6ff-139">**Force** 参数强制立即重新启动，而 **ThrottleLimit** 参数限制并发连接数。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-139">The **Force** parameter forces an immediate restart and the **ThrottleLimit** parameter limits the number of concurrent connections.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force -ThrottleLimit 10
```

<span data-ttu-id="ad6ff-140">`Get-Content` 使用 **Path** 参数从文本文件获取计算机名称的列表， **Domain01.txt** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-140">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt** .</span></span> <span data-ttu-id="ad6ff-141">计算机名称存储在变量中 `$Names` 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-141">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="ad6ff-142">`Get-Credential` 提示输入用户名和密码，并将值存储在变量中 `$Creds` 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-142">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="ad6ff-143">`Restart-Computer` 将 **ComputerName** 和 **Credential** 参数与其变量一起使用。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-143">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="ad6ff-144">**Force** 参数将导致立即重新启动每台计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-144">The **Force** parameter causes an immediate restart of each computer.</span></span> <span data-ttu-id="ad6ff-145">**ThrottleLimit** 参数将该命令限制为10个并发连接。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-145">The **ThrottleLimit** parameter limits the command to 10 concurrent connections.</span></span>

### <span data-ttu-id="ad6ff-146">示例6：重新启动远程计算机并等待 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad6ff-146">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="ad6ff-147">`Restart-Computer` 重新启动远程计算机，然后最多等待5分钟 (300 秒) ，以便 PowerShell 在重新启动的计算机上变为可用状态，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-147">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="ad6ff-148">`Restart-Computer` 使用 **ComputerName** 参数指定 **Server01** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-148">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01** .</span></span> <span data-ttu-id="ad6ff-149">**Wait** 参数等待重新启动完成。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-149">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="ad6ff-150">的 **指定 PowerShell** 可以在远程计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-150">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="ad6ff-151">**Timeout** 参数指定5分钟等待。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-151">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="ad6ff-152">**Delay** 参数每两秒钟查询一次远程计算机，以确定它是否已重新启动。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-152">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="ad6ff-153">示例7：使用 WSMan 协议重新启动计算机</span><span class="sxs-lookup"><span data-stu-id="ad6ff-153">Example 7: Restart a computer by using the WSMan Protocol</span></span>

<span data-ttu-id="ad6ff-154">`Restart-Computer` 使用 WSMan 协议而不是默认的 DCOM 来重新启动远程计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-154">`Restart-Computer` restarts the remote computer by using the WSMan protocol instead of the default, DCOM.</span></span> <span data-ttu-id="ad6ff-155">Kerberos 身份验证确定当前用户是否有权重新启动远程计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-155">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span>

<span data-ttu-id="ad6ff-156">这些设置适用于企业，其中基于 DCOM 的重新启动失败，因为阻止了 DCOM。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-156">These settings are designed for enterprises in which DCOM-based restarts fail because DCOM is blocked.</span></span> <span data-ttu-id="ad6ff-157">例如，使用防火墙。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-157">For example, by a firewall.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Protocol WSMan -WsmanAuthentication Kerberos
```

<span data-ttu-id="ad6ff-158">`Restart-Computer` 使用 **ComputerName** 参数指定远程计算机 **Server01** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-158">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01** .</span></span>
<span data-ttu-id="ad6ff-159">**Protocol** 参数指定使用 WSMan 协议。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-159">The **Protocol** parameter specifies to use the WSMan protocol.</span></span> <span data-ttu-id="ad6ff-160">**WsmanAuthentication** 参数将身份验证方法指定为 **Kerberos** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-160">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos** .</span></span>

## <span data-ttu-id="ad6ff-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ad6ff-161">PARAMETERS</span></span>

### <span data-ttu-id="ad6ff-162">-AsJob</span><span class="sxs-lookup"><span data-stu-id="ad6ff-162">-AsJob</span></span>

<span data-ttu-id="ad6ff-163">指示 `Restart-Computer` 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-163">Indicates that `Restart-Computer` runs as a background job.</span></span>

<span data-ttu-id="ad6ff-164">若要使用此参数，必须为本地和远程计算机配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-164">To use this parameter, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="ad6ff-165">在 Windows Vista 和更高版本的 Windows 操作系统上，必须使用 "以 **管理员身份运行** " 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-165">On Windows Vista and later versions of the Windows operating system, you must open PowerShell by using the **Run as Administrator** option.</span></span> <span data-ttu-id="ad6ff-166">有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-166">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="ad6ff-167">指定 AsJob  参数时，该命令立即返回代表后台作业的对象。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-167">When you specify the **AsJob** parameter, the command immediately returns an object that represents the background job.</span></span> <span data-ttu-id="ad6ff-168">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-168">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="ad6ff-169">作业在本地计算机上创建，并且来自远程计算机的结果将自动返回本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-169">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="ad6ff-170">若要管理作业，可以使用 **Job** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-170">To manage the job, use the **Job** cmdlets.</span></span> <span data-ttu-id="ad6ff-171">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-171">To get the job results, use the `Receive-Job` cmdlet.</span></span>

<span data-ttu-id="ad6ff-172">有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-172">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-173">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="ad6ff-173">-ComputerName</span></span>

<span data-ttu-id="ad6ff-174">指定一个计算机名称或以逗号分隔的计算机名称数组。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-174">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="ad6ff-175">`Restart-Computer` 接受管道或变量中的 **ComputerName** 对象。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-175">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="ad6ff-176">键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-176">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="ad6ff-177">若要指定本地计算机，请键入计算机名、点 `.` 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-177">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="ad6ff-178">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-178">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="ad6ff-179">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-179">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="ad6ff-180">如果未指定 **ComputerName** 参数，则 `Restart-Computer` 重新启动本地计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-180">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-181">-Credential</span><span class="sxs-lookup"><span data-stu-id="ad6ff-181">-Credential</span></span>

<span data-ttu-id="ad6ff-182">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-182">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="ad6ff-183">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-183">The default is the current user.</span></span>

<span data-ttu-id="ad6ff-184">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-184">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="ad6ff-185">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-185">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="ad6ff-186">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-186">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="ad6ff-187">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-187">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-188">-DcomAuthentication</span><span class="sxs-lookup"><span data-stu-id="ad6ff-188">-DcomAuthentication</span></span>

<span data-ttu-id="ad6ff-189">指定用于 WMI 连接的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-189">Specifies the authentication level that is used for the WMI connection.</span></span> <span data-ttu-id="ad6ff-190">`Restart-Computer` 使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-190">`Restart-Computer` uses WMI.</span></span>

<span data-ttu-id="ad6ff-191">有效值是：</span><span class="sxs-lookup"><span data-stu-id="ad6ff-191">Valid values are:</span></span>

- <span data-ttu-id="ad6ff-192">**Call** ：调用级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="ad6ff-192">**Call** :            Call-level COM authentication</span></span>
- <span data-ttu-id="ad6ff-193">**Connect** ：连接级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="ad6ff-193">**Connect** :         Connect-level COM authentication</span></span>
- <span data-ttu-id="ad6ff-194">**默认** ： Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="ad6ff-194">**Default** :         Windows Authentication</span></span>
- <span data-ttu-id="ad6ff-195">**无** ：无 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="ad6ff-195">**None** :            No COM authentication</span></span>
- <span data-ttu-id="ad6ff-196">**Packet** ：数据包级 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-196">**Packet** :          Packet-level COM authentication.</span></span>
- <span data-ttu-id="ad6ff-197">**PacketIntegrity** ：数据包完整性级 COM 身份验证</span><span class="sxs-lookup"><span data-stu-id="ad6ff-197">**PacketIntegrity** : Packet Integrity-level COM authentication</span></span>
- <span data-ttu-id="ad6ff-198">**PacketPrivacy** ：数据包隐私级 COM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-198">**PacketPrivacy** :   Packet Privacy-level COM authentication.</span></span>
- <span data-ttu-id="ad6ff-199">**保持不变** ：身份验证级别与前一个命令相同。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-199">**Unchanged** :       The authentication level is the same as the previous command.</span></span>

<span data-ttu-id="ad6ff-200">有关详细信息，请参阅 [AuthenticationLevel 枚举](/dotnet/api/system.management.authenticationlevel)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-200">For more information, see [AuthenticationLevel Enumeration](/dotnet/api/system.management.authenticationlevel).</span></span>

<span data-ttu-id="ad6ff-201">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-201">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases: Authentication
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-202">-Delay</span><span class="sxs-lookup"><span data-stu-id="ad6ff-202">-Delay</span></span>

<span data-ttu-id="ad6ff-203">指定查询的频率（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-203">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="ad6ff-204">PowerShell 查询由 **For** 参数指定的服务，以确定该服务是否在计算机重新启动之后可用。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-204">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="ad6ff-205">此参数仅适用于 **Wait** **和参数** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-205">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="ad6ff-206">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="ad6ff-207">如果未指定 **Delay** 参数， `Restart-Computer` 将使用5秒钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-207">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-208">-对于</span><span class="sxs-lookup"><span data-stu-id="ad6ff-208">-For</span></span>

<span data-ttu-id="ad6ff-209">指定 PowerShell 的行为，因为它会等待指定的服务或功能在计算机重新启动后变得可用。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-209">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="ad6ff-210">此参数仅对 **Wait** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-210">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="ad6ff-211">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ad6ff-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ad6ff-212">**默认** ：等待 PowerShell 重新启动。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-212">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="ad6ff-213">**Powershell** ：可在计算机上的 powershell 远程会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-213">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="ad6ff-214">**WMI** ：接收对计算机 Win32_ComputerSystem 查询的答复。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-214">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="ad6ff-215">**WinRM** ：可以使用 ws-management 建立与计算机的远程会话。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-215">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="ad6ff-216">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-216">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: DefaultSet
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-217">-Force</span><span class="sxs-lookup"><span data-stu-id="ad6ff-217">-Force</span></span>

<span data-ttu-id="ad6ff-218">强制立即重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-218">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-219">-Impersonation</span><span class="sxs-lookup"><span data-stu-id="ad6ff-219">-Impersonation</span></span>

<span data-ttu-id="ad6ff-220">指定此 cmdlet 用来调用 WMI 的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-220">Specifies the impersonation level that this cmdlet uses to call WMI.</span></span> <span data-ttu-id="ad6ff-221">`Restart-Computer` 使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-221">`Restart-Computer` uses WMI.</span></span>
<span data-ttu-id="ad6ff-222">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ad6ff-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ad6ff-223">**默认值** ：默认模拟。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-223">**Default** : Default impersonation.</span></span> <span data-ttu-id="ad6ff-224">不管名称如何，这并不是默认值。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-224">Despite the name, this isn't the default value.</span></span>
- <span data-ttu-id="ad6ff-225">**Anonymous** ：隐藏调用方的标识。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-225">**Anonymous** : Hides the identity of the caller.</span></span>
- <span data-ttu-id="ad6ff-226">**标识** ：允许对象查询调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-226">**Identify** : Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="ad6ff-227">**模拟** ：允许对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-227">**Impersonate** : Allows objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-228">-Protocol</span><span class="sxs-lookup"><span data-stu-id="ad6ff-228">-Protocol</span></span>

<span data-ttu-id="ad6ff-229">指定重新启动计算机要使用的协议。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-229">Specifies which protocol to use to restart the computers.</span></span> <span data-ttu-id="ad6ff-230">有效值为 **WSMan** 和 **DCOM** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-230">The valid values are **WSMan** and **DCOM** .</span></span>

<span data-ttu-id="ad6ff-231">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-232">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="ad6ff-232">-ThrottleLimit</span></span>

<span data-ttu-id="ad6ff-233">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-233">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="ad6ff-234">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-234">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

<span data-ttu-id="ad6ff-235">如果未指定 **ThrottleLimit** 参数或使用值0，则 `Restart-Computer` 最多使用32并发连接。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-235">If the **ThrottleLimit** parameter isn't specified or a value of 0 is used, `Restart-Computer` uses a maximum of 32 concurrent connections.</span></span>

```yaml
Type: System.Int32
Parameter Sets: AsJobSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-236">-Timeout</span><span class="sxs-lookup"><span data-stu-id="ad6ff-236">-Timeout</span></span>

<span data-ttu-id="ad6ff-237">指定等待的持续时间，以秒为单位。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-237">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="ad6ff-238">超时到期后，将 `Restart-Computer` 返回到命令提示符，即使计算机未重启也是如此。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-238">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="ad6ff-239">**Timeout** 参数仅对 **Wait** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-239">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="ad6ff-240">**Timeout** 替代 **等待** 参数的无限等待期。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-240">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="ad6ff-241">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-241">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DefaultSet
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-242">-Wait</span><span class="sxs-lookup"><span data-stu-id="ad6ff-242">-Wait</span></span>

<span data-ttu-id="ad6ff-243">`Restart-Computer` 取消 PowerShell 提示符并阻止管道，直到计算机重新启动。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-243">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="ad6ff-244">您可以在脚本中使用此参数来重新启动计算机，然后在重新启动完成后继续处理。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-244">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="ad6ff-245">**等待** 参数会无限期地等待计算机重新启动。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-245">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="ad6ff-246">你可以使用 **超时** 调整计时，并使用和 **延迟\*\*\*\*参数，以** 等待特定服务在重新启动的计算机上变为可用。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-246">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="ad6ff-247">当你重新启动本地计算机时， **等待** 参数无效。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-247">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="ad6ff-248">如果 **ComputerName** 参数的值包含远程计算机和本地计算机的名称，则会 `Restart-Computer` 在本地计算机上生成 **等待等待** 的非终止错误，但会等待远程计算机重新启动。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-248">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="ad6ff-249">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-249">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-250">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="ad6ff-250">-WsmanAuthentication</span></span>

<span data-ttu-id="ad6ff-251">指定用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-251">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="ad6ff-252">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-252">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="ad6ff-253">此参数可接受的值为： **Basic** 、 **CredSSP** 、 **Default** 、 **Digest** 、 **Kerberos** 和 **Negotiate** 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-253">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate** .</span></span>

<span data-ttu-id="ad6ff-254">有关详细信息，请参阅 [system.management.automation.runspaces.authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-254">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="ad6ff-255">凭据安全服务提供程序 (CredSSP) 身份验证，在此身份验证中，用户凭据传递到远程计算机进行身份验证时，需要对多个资源（例如访问远程网络共享）进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-255">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="ad6ff-256">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-256">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="ad6ff-257">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-257">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: DefaultSet
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ad6ff-258">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ad6ff-258">-Confirm</span></span>

<span data-ttu-id="ad6ff-259">在运行之前提示你进行确认 `Restart-Computer` 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-259">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="ad6ff-260">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ad6ff-260">-WhatIf</span></span>

<span data-ttu-id="ad6ff-261">显示运行时将发生的情况 `Restart-Computer` 。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-261">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="ad6ff-262">`Restart-Computer`Cmdlet 不会运行。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-262">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="ad6ff-263">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ad6ff-263">CommonParameters</span></span>

<span data-ttu-id="ad6ff-264">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-264">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ad6ff-265">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-265">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ad6ff-266">输入</span><span class="sxs-lookup"><span data-stu-id="ad6ff-266">INPUTS</span></span>

### <span data-ttu-id="ad6ff-267">System.String</span><span class="sxs-lookup"><span data-stu-id="ad6ff-267">System.String</span></span>

<span data-ttu-id="ad6ff-268">`Restart-Computer` 接受管道或变量中的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-268">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

<span data-ttu-id="ad6ff-269">在 Windows PowerShell 2.0 中， **ComputerName** 参数仅按属性名称通过管道获取输入。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-269">In Windows PowerShell 2.0, the **ComputerName** parameter takes input from the pipeline only by property name.</span></span> <span data-ttu-id="ad6ff-270">在 Windows PowerShell 3.0 和更高版本中， **ComputerName** 参数按值从管道中获取输入。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-270">In Windows PowerShell 3.0, and later, the **ComputerName** parameter takes input from the pipeline by value.</span></span>

## <span data-ttu-id="ad6ff-271">输出</span><span class="sxs-lookup"><span data-stu-id="ad6ff-271">OUTPUTS</span></span>

### <span data-ttu-id="ad6ff-272">System.management.automation.remotingjob （无）</span><span class="sxs-lookup"><span data-stu-id="ad6ff-272">None, System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="ad6ff-273">如果指定 **AsJob** 参数，则 `Restart-Computer` 返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-273">If you specify the **AsJob** parameter, `Restart-Computer` returns a job object.</span></span> <span data-ttu-id="ad6ff-274">否则，不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-274">Otherwise, no output is generated.</span></span>

## <span data-ttu-id="ad6ff-275">注释</span><span class="sxs-lookup"><span data-stu-id="ad6ff-275">NOTES</span></span>

- <span data-ttu-id="ad6ff-276">`Restart-Computer` 仅在运行 Windows 的计算机上工作，并且需要 WinRM 和 WMI 关闭系统，包括本地系统。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-276">`Restart-Computer` only work on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="ad6ff-277">`Restart-Computer`使用 Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem)类的[Win32Shutdown 方法](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem)。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-277">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span>  <span data-ttu-id="ad6ff-278">此方法需要为用于重新启动计算机的用户帐户启用 **SeShutdownPrivilege** 特权。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-278">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="ad6ff-279">在 Windows PowerShell 2.0 中， **AsJob** 参数在重启或停止远程计算机时不能可靠地工作。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-279">In Windows PowerShell 2.0, the **AsJob** parameter doesn't work reliably when you are restarting or stopping remote computers.</span></span> <span data-ttu-id="ad6ff-280">在 Windows PowerShell 3.0 中，为解决此问题，该实现方式有所更改。</span><span class="sxs-lookup"><span data-stu-id="ad6ff-280">In Windows PowerShell 3.0, the implementation is changed to resolve this problem.</span></span>

## <span data-ttu-id="ad6ff-281">相关链接</span><span class="sxs-lookup"><span data-stu-id="ad6ff-281">RELATED LINKS</span></span>

[<span data-ttu-id="ad6ff-282">关于 Windows 远程管理</span><span class="sxs-lookup"><span data-stu-id="ad6ff-282">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="ad6ff-283">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="ad6ff-283">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="ad6ff-284">WS-Management 协议</span><span class="sxs-lookup"><span data-stu-id="ad6ff-284">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)
