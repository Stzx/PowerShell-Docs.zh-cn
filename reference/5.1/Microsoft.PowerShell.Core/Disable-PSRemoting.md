---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197456"
---
# <span data-ttu-id="48a09-103">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="48a09-103">Disable-PSRemoting</span></span>

## <span data-ttu-id="48a09-104">摘要</span><span class="sxs-lookup"><span data-stu-id="48a09-104">SYNOPSIS</span></span>
<span data-ttu-id="48a09-105">阻止 PowerShell 终结点接收远程连接。</span><span class="sxs-lookup"><span data-stu-id="48a09-105">Prevents PowerShell endpoints from receiving remote connections.</span></span>

## <span data-ttu-id="48a09-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48a09-106">SYNTAX</span></span>

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="48a09-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48a09-107">DESCRIPTION</span></span>

<span data-ttu-id="48a09-108">该 `Disable-PSRemoting` cmdlet 会阻止远程访问本地计算机上的所有 Windows PowerShell 会话终结点配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-108">The `Disable-PSRemoting` cmdlet blocks remote access to all Windows PowerShell session endpoint configurations on the local computer.</span></span> <span data-ttu-id="48a09-109">这包括 PowerShell 6 或更高版本创建的任何终结点。</span><span class="sxs-lookup"><span data-stu-id="48a09-109">This includes any endpoints created by PowerShell 6 or higher.</span></span>

<span data-ttu-id="48a09-110">若要重新启用对所有会话配置的远程访问，请使用 `Enable-PSRemoting` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48a09-110">To re-enable remote access to all session configurations, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="48a09-111">这包括 PowerShell 6 或更高版本创建的任何终结点。</span><span class="sxs-lookup"><span data-stu-id="48a09-111">This includes any endpoints created by PowerShell 6 or higher.</span></span> <span data-ttu-id="48a09-112">若要启用对选定会话配置的远程访问，请使用 cmdlet 的 **AccessMode** 参数 `Set-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="48a09-112">To enable remote access to selected session configurations, use the **AccessMode** parameter of the `Set-PSSessionConfiguration` cmdlet.</span></span>
<span data-ttu-id="48a09-113">你还可以使用 `Enable-PSSessionConfiguration` 和 `Disable-PSSessionConfiguration` cmdlet 来启用和禁用所有用户的会话配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-113">You can also use the `Enable-PSSessionConfiguration` and `Disable-PSSessionConfiguration` cmdlets to enable and disable session configurations for all users.</span></span> <span data-ttu-id="48a09-114">有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="48a09-114">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="48a09-115">即使在运行后 `Disable-PSRemoting` ，仍可在本地计算机上进行环回连接。</span><span class="sxs-lookup"><span data-stu-id="48a09-115">Even after running `Disable-PSRemoting` you can still make loopback connections on the local machine.</span></span> <span data-ttu-id="48a09-116">环回连接是源自并连接到同一台本地计算机的 PowerShell 远程会话。</span><span class="sxs-lookup"><span data-stu-id="48a09-116">A loopback connection is a PowerShell remote session that originates from and connects to the same local machine.</span></span> <span data-ttu-id="48a09-117">来自外部源的远程会话将保持阻止。</span><span class="sxs-lookup"><span data-stu-id="48a09-117">Remote sessions from external sources remain blocked.</span></span> <span data-ttu-id="48a09-118">对于环回连接，必须使用 **EnableNetworkAccess** 参数的隐式凭据。</span><span class="sxs-lookup"><span data-stu-id="48a09-118">For loopback connections you must use implicit credentials along the **EnableNetworkAccess** parameter.</span></span> <span data-ttu-id="48a09-119">有关环回连接的详细信息，请参阅 [新的 PSSession](New-PSSession.md)。</span><span class="sxs-lookup"><span data-stu-id="48a09-119">For more information about loopback connections, see [New-PSSession](New-PSSession.md).</span></span>

<span data-ttu-id="48a09-120">若要运行此 cmdlet，请通过 "以 **管理员身份运行** " 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="48a09-120">To run this cmdlet, start Windows PowerShell with the **Run as administrator** option.</span></span>

## <span data-ttu-id="48a09-121">示例</span><span class="sxs-lookup"><span data-stu-id="48a09-121">EXAMPLES</span></span>

### <span data-ttu-id="48a09-122">示例1：阻止对所有会话配置的远程访问</span><span class="sxs-lookup"><span data-stu-id="48a09-122">Example 1: Prevent remote access to all session configurations</span></span>

<span data-ttu-id="48a09-123">此示例阻止远程访问计算机上的所有 PowerShell 会话终结点配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-123">This example prevents remote access to all PowerShell session endpoint configurations on the computer.</span></span>

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="48a09-124">示例2：在没有确认提示的情况下禁止远程访问所有会话配置</span><span class="sxs-lookup"><span data-stu-id="48a09-124">Example 2: Prevent remote access to all session configurations without confirmation prompt</span></span>

<span data-ttu-id="48a09-125">此示例阻止远程访问计算机上的所有 PowerShell 会话终结点配置，而不会提示。</span><span class="sxs-lookup"><span data-stu-id="48a09-125">This example prevents remote access all PowerShell session endpoint configurations on the computer without prompting.</span></span>

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### <span data-ttu-id="48a09-126">示例3：运行此 cmdlet 的效果</span><span class="sxs-lookup"><span data-stu-id="48a09-126">Example 3: Effects of running this cmdlet</span></span>

<span data-ttu-id="48a09-127">此示例演示如何使用 `Disable-PSRemoting` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48a09-127">This example shows the effect of using the `Disable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="48a09-128">若要运行此命令序列，请用 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="48a09-128">To run this command sequence, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="48a09-129">禁用会话配置后，该 `New-PSSession` cmdlet 会尝试创建到本地计算机的远程会话 (也称为 "环回" ) 。</span><span class="sxs-lookup"><span data-stu-id="48a09-129">After disabling the sessions configurations, the `New-PSSession` cmdlet attempts to create a remote session to the local computer (also known as a "loopback").</span></span> <span data-ttu-id="48a09-130">由于在本地计算机上禁用远程访问，因此该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="48a09-130">Because remote access is disabled on the local machine, the command fails.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### <span data-ttu-id="48a09-131">示例4：运行此 cmdlet 和 Enable-PSRemoting 的效果</span><span class="sxs-lookup"><span data-stu-id="48a09-131">Example 4: Effects of running this cmdlet and Enable-PSRemoting</span></span>

<span data-ttu-id="48a09-132">此示例演示了使用和 cmdlet 对会话配置的影响 `Disable-PSRemoting` `Enable-PSRemoting` 。</span><span class="sxs-lookup"><span data-stu-id="48a09-132">This example shows the effect on the session configurations of using the `Disable-PSRemoting` and `Enable-PSRemoting` cmdlets.</span></span>

<span data-ttu-id="48a09-133">`Disable-PSRemoting` 用于禁止远程访问所有 PowerShell 会话终结点配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-133">`Disable-PSRemoting` is used to disable remote access to all PowerShell session endpoint configurations.</span></span> <span data-ttu-id="48a09-134">**Force** 参数取消了所有用户提示。</span><span class="sxs-lookup"><span data-stu-id="48a09-134">The **Force** parameter suppresses all user prompts.</span></span> <span data-ttu-id="48a09-135">`Get-PSSessionConfiguration`和 `Format-Table` cmdlet 显示计算机上的会话配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-135">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations on the computer.</span></span>

<span data-ttu-id="48a09-136">此输出显示，具有网络令牌的所有远程用户均被拒绝访问终结点配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-136">The output shows that all remote users with a network token are denied access to the endpoint configurations.</span></span> <span data-ttu-id="48a09-137">允许本地计算机上的管理员组访问终结点配置，只要它们本地连接 (也称为环回) 并使用隐式凭据。</span><span class="sxs-lookup"><span data-stu-id="48a09-137">Administrators group on the local computer are allowed access to the endpoint configurations as long as they are connecting locally (also known as loopback) and using implicit credentials.</span></span>

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="48a09-138">`Enable-PSRemoting`Cmdlet 可重新启用对计算机上所有 PowerShell 会话终结点配置的远程访问。</span><span class="sxs-lookup"><span data-stu-id="48a09-138">The `Enable-PSRemoting` cmdlet re-enables remote access to all PowerShell session endpoint configurations on the computer.</span></span> <span data-ttu-id="48a09-139">**Force** 参数取消所有用户提示，并在不提示的情况下重新启动 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="48a09-139">The **Force** parameter suppresses all user prompts and restarts the WinRM service without prompting.</span></span> <span data-ttu-id="48a09-140">新的输出显示已从所有会话配置中删除 **AccessDenied** 安全描述符。</span><span class="sxs-lookup"><span data-stu-id="48a09-140">The new output shows that the **AccessDenied** security descriptors have been removed from all session configurations.</span></span>

### <span data-ttu-id="48a09-141">示例5：具有已禁用会话终结点配置的环回连接</span><span class="sxs-lookup"><span data-stu-id="48a09-141">Example 5: Loopback connections with disabled session endpoint configurations</span></span>

<span data-ttu-id="48a09-142">此示例演示如何禁用终结点配置，并演示如何成功连接到已禁用的终结点。</span><span class="sxs-lookup"><span data-stu-id="48a09-142">This example demonstrates how endpoint configurations are disabled, and shows how to make a successful loopback connection to a disabled endpoint.</span></span> <span data-ttu-id="48a09-143">`Disable-PSRemoting` 禁用所有 PowerShell 会话终结点配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-143">`Disable-PSRemoting` disables all PowerShell session endpoint configurations.</span></span>

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

<span data-ttu-id="48a09-144">第一次使用 `New-PSSession` 尝试创建到本地计算机的远程会话。</span><span class="sxs-lookup"><span data-stu-id="48a09-144">The first use of `New-PSSession` attempts to create a remote session to the local machine.</span></span> <span data-ttu-id="48a09-145">这种类型的连接会通过网络堆栈，并且不是环回。</span><span class="sxs-lookup"><span data-stu-id="48a09-145">This type of connection goes through the network stack and is not a loopback.</span></span> <span data-ttu-id="48a09-146">因此，尝试连接到已禁用的终结点失败，并出现 " **拒绝访问** " 错误。</span><span class="sxs-lookup"><span data-stu-id="48a09-146">Consequently, the connection attempt to the disabled endpoint fails with an **Access is denied** error.</span></span>

<span data-ttu-id="48a09-147">第二次使用时， `New-PSSession` 也会尝试创建到本地计算机的远程会话。</span><span class="sxs-lookup"><span data-stu-id="48a09-147">The second use of `New-PSSession` also attempts to create a remote session to the local machine.</span></span>
<span data-ttu-id="48a09-148">在这种情况下，它会成功，因为它是绕过网络堆栈的环回连接。</span><span class="sxs-lookup"><span data-stu-id="48a09-148">In this case, it succeeds because it is a loopback connection that bypasses the network stack.</span></span>

<span data-ttu-id="48a09-149">当满足以下条件时，将创建环回连接：</span><span class="sxs-lookup"><span data-stu-id="48a09-149">A loopback connection is created when the following conditions are met:</span></span>

- <span data-ttu-id="48a09-150">要连接到的计算机名称为 "localhost"。</span><span class="sxs-lookup"><span data-stu-id="48a09-150">The computer name to connect to is 'localhost'.</span></span>
- <span data-ttu-id="48a09-151">未传入凭据。</span><span class="sxs-lookup"><span data-stu-id="48a09-151">No credentials are passed in.</span></span> <span data-ttu-id="48a09-152">当前登录的用户 (用于连接的隐式凭据) 。</span><span class="sxs-lookup"><span data-stu-id="48a09-152">Current logged in user (implicit credentials) is used for the connection.</span></span>
- <span data-ttu-id="48a09-153">使用 **EnableNetworkAccess** 开关参数。</span><span class="sxs-lookup"><span data-stu-id="48a09-153">The **EnableNetworkAccess** switch parameter is used.</span></span>

<span data-ttu-id="48a09-154">有关环回连接的详细信息，请参阅 [新的 PSSession](New-PSSession.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="48a09-154">For more information on loopback connections, see [New-PSSession](New-PSSession.md) document.</span></span>

### <span data-ttu-id="48a09-155">示例6：阻止远程访问具有自定义安全描述符的会话配置</span><span class="sxs-lookup"><span data-stu-id="48a09-155">Example 6: Prevent remote access to session configurations that have custom security descriptors</span></span>

<span data-ttu-id="48a09-156">此示例演示 `Disable-PSRemoting` cmdlet 禁用对所有会话配置的远程访问，包括具有自定义安全描述符的会话配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-156">This example demonstrates that the `Disable-PSRemoting` cmdlet disables remote access to all session configurations that include session configurations with custom security descriptors.</span></span>

<span data-ttu-id="48a09-157">`Register-PSSessionConfiguration` 创建 **测试** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-157">`Register-PSSessionConfiguration` creates the **Test** session configuration.</span></span> <span data-ttu-id="48a09-158">**FilePath** 参数指定自定义会话的会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="48a09-158">The **FilePath** parameter specifies a session configuration file that customizes the session.</span></span> <span data-ttu-id="48a09-159">**ShowSecurityDescriptorUI** 参数显示为会话配置设置权限的对话框。</span><span class="sxs-lookup"><span data-stu-id="48a09-159">The **ShowSecurityDescriptorUI** parameter displays a dialog box that sets permissions for the session configuration.</span></span> <span data-ttu-id="48a09-160">在 "权限" 对话框中，为指定的用户创建自定义的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="48a09-160">In the Permissions dialog box, we create custom full-access permissions for the indicated user.</span></span>

<span data-ttu-id="48a09-161">`Get-PSSessionConfiguration`和 `Format-Table` cmdlet 显示会话配置及其属性。</span><span class="sxs-lookup"><span data-stu-id="48a09-161">The `Get-PSSessionConfiguration` and `Format-Table` cmdlets display the session configurations and their properties.</span></span> <span data-ttu-id="48a09-162">此输出显示 **测试** 会话配置允许所指示的用户的交互式访问和特殊权限。</span><span class="sxs-lookup"><span data-stu-id="48a09-162">The output shows that the **Test** session configuration allows interactive access and special permissions for the indicated user.</span></span>

<span data-ttu-id="48a09-163">`Disable-PSRemoting` 禁用对所有会话配置的远程访问。</span><span class="sxs-lookup"><span data-stu-id="48a09-163">`Disable-PSRemoting` disables remote access to all session configurations.</span></span>

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="48a09-164">现在 `Get-PSSessionConfiguration` ，和 `Format-Table` cmdlet 显示将所有网络用户的 **AccessDenied** 安全描述符添加到所有会话配置，包括 **测试** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-164">Now the `Get-PSSessionConfiguration` and `Format-Table` cmdlets shows that an **AccessDenied** security descriptor for all network users is added to all session configurations, including the **Test** session configuration.</span></span> <span data-ttu-id="48a09-165">尽管其他安全描述符不会更改，但 "network_deny_all" 安全描述符优先。</span><span class="sxs-lookup"><span data-stu-id="48a09-165">Although the other security descriptors are not changed, the "network_deny_all" security descriptor takes precedence.</span></span> <span data-ttu-id="48a09-166">尝试使用 `New-PSSession` 连接到 **测试** 会话配置时，将对此进行说明。</span><span class="sxs-lookup"><span data-stu-id="48a09-166">This is illustrated by the attempt to use `New-PSSession` to connect to the **Test** session configuration.</span></span>

### <span data-ttu-id="48a09-167">示例7：重新启用对选定会话配置的远程访问</span><span class="sxs-lookup"><span data-stu-id="48a09-167">Example 7: Re-enable remote access to selected session configurations</span></span>

<span data-ttu-id="48a09-168">此示例演示如何重新启用仅到选定会话配置的远程访问。</span><span class="sxs-lookup"><span data-stu-id="48a09-168">This example shows how to re-enable remote access only to selected session configurations.</span></span> <span data-ttu-id="48a09-169">禁用所有会话配置后，将重新启用特定会话。</span><span class="sxs-lookup"><span data-stu-id="48a09-169">After disabling all session configurations, we re-enable a specific session.</span></span>

<span data-ttu-id="48a09-170">`Set-PSSessionConfiguration`Cmdlet 用于更改 **microsoft。ServerManager** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-170">The `Set-PSSessionConfiguration` cmdlet is used to change the **microsoft.ServerManager** session configuration.</span></span> <span data-ttu-id="48a09-171">如果 **AccessMode** 参数的值为 **remote** ，则启用对配置的远程访问。</span><span class="sxs-lookup"><span data-stu-id="48a09-171">The **AccessMode** parameter with a value of **Remote** re-enables remote access to the configuration.</span></span>

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

## <span data-ttu-id="48a09-172">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="48a09-172">PARAMETERS</span></span>

### <span data-ttu-id="48a09-173">-Confirm</span><span class="sxs-lookup"><span data-stu-id="48a09-173">-Confirm</span></span>

<span data-ttu-id="48a09-174">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="48a09-174">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="48a09-175">-Force</span><span class="sxs-lookup"><span data-stu-id="48a09-175">-Force</span></span>
<span data-ttu-id="48a09-176">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="48a09-176">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="48a09-177">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="48a09-177">-WhatIf</span></span>

<span data-ttu-id="48a09-178">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="48a09-178">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="48a09-179">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="48a09-179">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="48a09-180">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="48a09-180">CommonParameters</span></span>

<span data-ttu-id="48a09-181">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="48a09-181">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48a09-182">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="48a09-182">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48a09-183">输入</span><span class="sxs-lookup"><span data-stu-id="48a09-183">INPUTS</span></span>

### <span data-ttu-id="48a09-184">无</span><span class="sxs-lookup"><span data-stu-id="48a09-184">None</span></span>

<span data-ttu-id="48a09-185">不能通过管道将任何对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48a09-185">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="48a09-186">输出</span><span class="sxs-lookup"><span data-stu-id="48a09-186">OUTPUTS</span></span>

### <span data-ttu-id="48a09-187">无</span><span class="sxs-lookup"><span data-stu-id="48a09-187">None</span></span>

<span data-ttu-id="48a09-188">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="48a09-188">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="48a09-189">注释</span><span class="sxs-lookup"><span data-stu-id="48a09-189">NOTES</span></span>

- <span data-ttu-id="48a09-190">禁用会话配置不会撤消由或 cmdlet 进行的所有更改 `Enable-PSRemoting` `Enable-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="48a09-190">Disabling the session configurations does not undo all the changes that were made by the `Enable-PSRemoting` or `Enable-PSSessionConfiguration` cmdlets.</span></span> <span data-ttu-id="48a09-191">你可能需要手动撤消以下更改。</span><span class="sxs-lookup"><span data-stu-id="48a09-191">You might have to undo the following changes manually.</span></span>

  1. <span data-ttu-id="48a09-192">停止并禁用 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="48a09-192">Stop and disable the WinRM service.</span></span>
  2. <span data-ttu-id="48a09-193">删除接受任何 IP 地址上的请求的侦听器。</span><span class="sxs-lookup"><span data-stu-id="48a09-193">Delete the listener that accepts requests on any IP address.</span></span>
  3. <span data-ttu-id="48a09-194">禁用 WS-Management 通信的防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="48a09-194">Disable the firewall exceptions for WS-Management communications.</span></span>
  4. <span data-ttu-id="48a09-195">将 LocalAccountTokenFilterPolicy 的值还原为 0，这将限制对计算机上 Administrators 组成员的远程访问。</span><span class="sxs-lookup"><span data-stu-id="48a09-195">Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to members of the Administrators group on the computer.</span></span>

  <span data-ttu-id="48a09-196">会话配置是一组定义会话环境的设置。</span><span class="sxs-lookup"><span data-stu-id="48a09-196">A session configuration is a group of settings that define the environment for a session.</span></span> <span data-ttu-id="48a09-197">连接到计算机的每个会话都必须使用一个在该计算机上注册的会话配置。</span><span class="sxs-lookup"><span data-stu-id="48a09-197">Every session that connects to the computer must use one of the session configurations that are registered on the computer.</span></span> <span data-ttu-id="48a09-198">通过拒绝对所有会话配置的远程访问，你可以有效地阻止远程用户建立连接到计算机的会话。</span><span class="sxs-lookup"><span data-stu-id="48a09-198">By denying remote access to all session configurations, you effectively prevent remote users from establishing sessions that connect to the computer.</span></span>

  <span data-ttu-id="48a09-199">在 Windows PowerShell 2.0 中， `Disable-PSRemoting` 将 Deny_All 条目添加到所有会话配置的安全描述符中。</span><span class="sxs-lookup"><span data-stu-id="48a09-199">In Windows PowerShell 2.0, `Disable-PSRemoting` adds a Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="48a09-200">此设置可阻止所有用户创建到本地计算机的用户托管会话。</span><span class="sxs-lookup"><span data-stu-id="48a09-200">This setting prevents all users from creating user-managed sessions to the local computer.</span></span> <span data-ttu-id="48a09-201">在 Windows PowerShell 3.0 中， `Disable-PSRemoting` 将 Network_Deny_All 条目添加到所有会话配置的安全描述符中。</span><span class="sxs-lookup"><span data-stu-id="48a09-201">In Windows PowerShell 3.0, `Disable-PSRemoting` adds a Network_Deny_All entry to the security descriptors of all session configurations.</span></span> <span data-ttu-id="48a09-202">此设置可阻止其他计算机上的用户在本地计算机上创建用户管理的会话，但允许本地计算机的用户创建用户托管环回会话。</span><span class="sxs-lookup"><span data-stu-id="48a09-202">This setting prevents users on other computers from creating user-managed sessions on the local computer, but allows users of the local computer to create user-managed loopback sessions.</span></span>

  <span data-ttu-id="48a09-203">在 Windows PowerShell 2.0 中， `Disable-PSRemoting` 是的等效项 `Disable-PSSessionConfiguration -Name *` 。</span><span class="sxs-lookup"><span data-stu-id="48a09-203">In Windows PowerShell 2.0, `Disable-PSRemoting` is the equivalent of `Disable-PSSessionConfiguration -Name *`.</span></span> <span data-ttu-id="48a09-204">在 Windows PowerShell 3.0 及更高版本中， `Disable-PSRemoting` 相当于 `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span><span class="sxs-lookup"><span data-stu-id="48a09-204">In Windows PowerShell 3.0 and later releases, `Disable-PSRemoting` is the equivalent of `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`</span></span>

## <span data-ttu-id="48a09-205">相关链接</span><span class="sxs-lookup"><span data-stu-id="48a09-205">RELATED LINKS</span></span>

[<span data-ttu-id="48a09-206">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="48a09-206">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="48a09-207">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="48a09-207">Enable-PSRemoting</span></span>](Enable-PSRemoting.md)

[<span data-ttu-id="48a09-208">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="48a09-208">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="48a09-209">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="48a09-209">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="48a09-210">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="48a09-210">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="48a09-211">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="48a09-211">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="48a09-212">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="48a09-212">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="48a09-213">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="48a09-213">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
