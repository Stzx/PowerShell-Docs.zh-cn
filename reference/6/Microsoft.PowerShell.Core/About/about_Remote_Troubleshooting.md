---
description: 介绍如何对 PowerShell 中的远程操作进行故障排除。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: b78f3004e316b6d4de1082b914970d3c8b56f955
ms.sourcegitcommit: c1e4739f5d52282fb05a8cff92b0f5d10e2edac1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "93200755"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="7225c-104">关于远程疑难解答</span><span class="sxs-lookup"><span data-stu-id="7225c-104">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="7225c-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="7225c-105">Short description</span></span>
<span data-ttu-id="7225c-106">介绍如何对 PowerShell 中的远程操作进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="7225c-106">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="7225c-107">长说明</span><span class="sxs-lookup"><span data-stu-id="7225c-107">Long description</span></span>

<span data-ttu-id="7225c-108">本部分介绍在使用基于 WS-Management 技术的 PowerShell 的远程处理功能时可能会遇到的一些问题，并建议解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="7225c-108">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="7225c-109">使用 PowerShell 远程处理之前，请参阅 [about_Remote](about_remote.md) 和 [about_Remote_Requirements](about_Remote_Requirements.md) 了解有关配置和基本使用的指南。</span><span class="sxs-lookup"><span data-stu-id="7225c-109">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="7225c-110">此外，每个远程处理 cmdlet 的帮助主题（特别是参数说明）都包含有用的信息，旨在帮助你避免问题。</span><span class="sxs-lookup"><span data-stu-id="7225c-110">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="7225c-111">若要查看或更改 WSMan：驱动器中本地计算机的设置（包括对会话配置、受信任的主机、端口或侦听器的更改），请以 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7225c-111">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="7225c-112">权限和身份验证问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="7225c-112">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="7225c-113">本部分讨论与用户和计算机权限以及远程处理要求相关的远程处理问题。</span><span class="sxs-lookup"><span data-stu-id="7225c-113">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="7225c-114">如何以管理员身份运行</span><span class="sxs-lookup"><span data-stu-id="7225c-114">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="7225c-115">若要在本地计算机上启动远程会话，或查看或更改 WSMan：驱动器中本地计算机的设置（包括对会话配置、受信任的主机、端口或侦听器的更改），请使用 "以 **管理员身份运行** " 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7225c-115">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="7225c-116">若要通过 "以 **管理员身份运行** " 选项启动 Windows PowerShell，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7225c-116">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="7225c-117">右键单击 Windows PowerShell (或 Windows PowerShell ISE) "图标，然后单击" 以 **管理员身份运行** "。</span><span class="sxs-lookup"><span data-stu-id="7225c-117">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator** .</span></span>

  <span data-ttu-id="7225c-118">在 Windows 7 和 Windows Server 2008 R2 中，用 "以 **管理员身份运行** " 选项启动 windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7225c-118">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="7225c-119">在 Windows 任务栏中，右键单击 Windows PowerShell 图标，然后单击 "以 **管理员身份运行** "。</span><span class="sxs-lookup"><span data-stu-id="7225c-119">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator** .</span></span>

  <span data-ttu-id="7225c-120">在 Windows Server 2008 R2 中，默认情况下，Windows PowerShell 图标固定到任务栏。</span><span class="sxs-lookup"><span data-stu-id="7225c-120">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="7225c-121">如何启用远程处理</span><span class="sxs-lookup"><span data-stu-id="7225c-121">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="7225c-122">要使计算机能够发送远程命令，无需进行任何配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-122">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="7225c-123">但是，若要接收远程命令，必须在计算机上启用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="7225c-123">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="7225c-124">启用包括：启动 WinRM 服务，将 WinRM 服务的启动类型设置为 "自动"，为 HTTP 和 HTTPS 连接创建侦听器，并创建默认的会话配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-124">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="7225c-125">默认情况下，在 Windows Server 2012 和更新版本的 Windows Server 上启用 windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="7225c-125">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="7225c-126">在所有其他系统上，运行 `Enable-PSRemoting` cmdlet 以启用远程处理。</span><span class="sxs-lookup"><span data-stu-id="7225c-126">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="7225c-127">`Enable-PSRemoting`如果远程处理被禁用，还可以运行 cmdlet，在 Windows server 2012 和更高版本的 windows server 上重新启用远程处理。</span><span class="sxs-lookup"><span data-stu-id="7225c-127">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="7225c-128">若要将计算机配置为接收远程命令，请使用 `Enable-PSRemoting` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7225c-128">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="7225c-129">以下命令启用所有必需的远程设置，启用会话配置，并重新启动 WinRM 服务以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="7225c-129">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="7225c-130">若要禁止显示所有用户提示，请键入：</span><span class="sxs-lookup"><span data-stu-id="7225c-130">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="7225c-131">有关详细信息，请参阅 [enable-psremoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting)。</span><span class="sxs-lookup"><span data-stu-id="7225c-131">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="7225c-132">如何在企业中启用远程处理</span><span class="sxs-lookup"><span data-stu-id="7225c-132">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="7225c-133">若要使单台计算机能够接收远程 PowerShell 命令并接受连接，请使用 `Enable-PSRemoting` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7225c-133">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="7225c-134">若要为企业中的多台计算机启用远程处理，可以使用以下扩展选项。</span><span class="sxs-lookup"><span data-stu-id="7225c-134">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="7225c-135">若要为远程处理配置侦听器，请启用 " **允许自动配置侦听器** " 组策略。</span><span class="sxs-lookup"><span data-stu-id="7225c-135">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="7225c-136">若要在多台计算机上将 Windows 远程管理 (WinRM) 的启动类型设置为 "自动"，请使用 `Set-Service` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7225c-136">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="7225c-137">若要启用防火墙例外，请使用 **Windows 防火墙：允许本地端口例外** 组策略。</span><span class="sxs-lookup"><span data-stu-id="7225c-137">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="7225c-138">如何使用组策略启用侦听器</span><span class="sxs-lookup"><span data-stu-id="7225c-138">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="7225c-139">若要为域中的所有计算机配置侦听器，请在以下组策略路径中启用 " **允许自动配置侦听器** 策略"：</span><span class="sxs-lookup"><span data-stu-id="7225c-139">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="7225c-140">启用策略并指定 IPv4 和 IPv6 筛选器。</span><span class="sxs-lookup"><span data-stu-id="7225c-140">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="7225c-141">`*`允许使用通配符 () 。</span><span class="sxs-lookup"><span data-stu-id="7225c-141">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="7225c-142">如何在公用网络上启用远程处理</span><span class="sxs-lookup"><span data-stu-id="7225c-142">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="7225c-143">`Enable-PSRemoting`当本地网络是公共的，并且命令中未使用 **SkipNetworkProfileCheck** 参数时，该 cmdlet 将返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7225c-143">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="7225c-144">在 Windows 的服务器版本上， `Enable-PSRemoting` 在所有网络位置类型上成功。</span><span class="sxs-lookup"><span data-stu-id="7225c-144">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="7225c-145">它创建防火墙规则，以允许远程访问专用和域 ( "Home" 和 "Work" ) 网络。</span><span class="sxs-lookup"><span data-stu-id="7225c-145">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="7225c-146">对于公用网络，它会创建允许来自同一本地子网的远程访问的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="7225c-146">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="7225c-147">在 Windows 的客户端版本上，会 `Enable-PSRemoting` 在专用网络和域网络上成功。</span><span class="sxs-lookup"><span data-stu-id="7225c-147">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="7225c-148">默认情况下，它在公用网络上失败，但如果使用 **SkipNetworkProfileCheck** 参数，则会 `Enable-PSRemoting` 成功并创建允许来自同一本地子网的流量的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="7225c-148">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="7225c-149">若要删除公用网络上的本地子网限制并允许从任何位置进行远程访问，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7225c-149">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="7225c-150">`Set-NetFirewallRule`Cmdlet 由 NetSecurity 模块导出。</span><span class="sxs-lookup"><span data-stu-id="7225c-150">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="7225c-151">在运行 windows server 版本的计算机上，Windows PowerShell 2.0 `Enable-PSRemoting` 创建允许在专用、域和公用网络上进行远程访问的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="7225c-151">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="7225c-152">在运行 Windows 客户端版本的计算机上， `Enable-PSRemoting` 创建仅允许在专用网络和域网络上进行远程访问的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="7225c-152">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="7225c-153">如何使用组策略启用防火墙例外</span><span class="sxs-lookup"><span data-stu-id="7225c-153">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="7225c-154">若要为域中的所有计算机启用防火墙例外，请在以下组策略路径中启用 " **Windows 防火墙：允许本地端口例外** " 策略：</span><span class="sxs-lookup"><span data-stu-id="7225c-154">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="7225c-155">此策略允许计算机上 Administrators 组的成员使用 **控制面板** 中的 " **Windows 防火墙** " 为 Windows 远程管理服务创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="7225c-155">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="7225c-156">如果策略配置不正确，可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="7225c-156">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="7225c-157">策略中的配置错误导致 **ListeningOn** 属性值为空。</span><span class="sxs-lookup"><span data-stu-id="7225c-157">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="7225c-158">使用以下命令检查值。</span><span class="sxs-lookup"><span data-stu-id="7225c-158">Use the following command to check the value.</span></span>

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="7225c-159">如何设置 WinRM 服务的启动类型</span><span class="sxs-lookup"><span data-stu-id="7225c-159">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="7225c-160">PowerShell 远程处理依赖于 (WinRM) 服务的 Windows 远程管理。</span><span class="sxs-lookup"><span data-stu-id="7225c-160">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="7225c-161">必须运行该服务才能支持远程命令。</span><span class="sxs-lookup"><span data-stu-id="7225c-161">The service must be running to support remote commands.</span></span>

<span data-ttu-id="7225c-162">在服务器版本的 Windows 上，Windows 远程管理 (WinRM) 服务的启动类型为 "自动"。</span><span class="sxs-lookup"><span data-stu-id="7225c-162">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="7225c-163">但是，在客户端版本的 Windows 上，WinRM 服务在默认情况下处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="7225c-163">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="7225c-164">若要设置远程计算机上的服务的启动类型，请使用 `Set-Service` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7225c-164">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="7225c-165">若要在多台计算机上运行该命令，可以创建一个文本文件或计算机名称的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="7225c-165">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="7225c-166">例如，以下命令从文件中获取计算机名称的列表 `Servers.txt` ，然后将所有计算机上 WinRM 服务的启动类型设置为 " **自动** "。</span><span class="sxs-lookup"><span data-stu-id="7225c-166">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic** .</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="7225c-167">若要查看结果，请将 `Get-WMIObject` cmdlet 与 **Win32_Service** 对象结合使用。</span><span class="sxs-lookup"><span data-stu-id="7225c-167">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="7225c-168">有关详细信息，请参阅 " [设置服务](xref:Microsoft.PowerShell.Management.Set-Service)"。</span><span class="sxs-lookup"><span data-stu-id="7225c-168">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="7225c-169">如何重新创建默认会话配置</span><span class="sxs-lookup"><span data-stu-id="7225c-169">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="7225c-170">若要连接到本地计算机并远程运行命令，本地计算机必须包含用于远程命令的会话配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-170">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="7225c-171">使用时 `Enable-PSRemoting` ，它会在本地计算机上创建默认的会话配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-171">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="7225c-172">远程用户在远程命令不包含 **ConfigurationName** 参数时使用这些会话配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-172">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="7225c-173">如果未注册或删除计算机上的默认配置，请使用 `Enable-PSRemoting` cmdlet 重新创建它们。</span><span class="sxs-lookup"><span data-stu-id="7225c-173">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="7225c-174">可以重复使用此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7225c-174">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="7225c-175">如果已配置功能，则不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="7225c-175">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="7225c-176">如果更改了默认会话配置，并且想要还原原始的默认会话配置，请使用 `Unregister-PSSessionConfiguration` cmdlet 删除已更改的会话配置，然后使用 `Enable-PSRemoting` cmdlet 还原它们。</span><span class="sxs-lookup"><span data-stu-id="7225c-176">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="7225c-177">`Enable-PSRemoting` 不会更改现有会话配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-177">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="7225c-178">当 `Enable-PSRemoting` 恢复默认会话配置时，它不会为配置创建显式安全描述符。</span><span class="sxs-lookup"><span data-stu-id="7225c-178">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="7225c-179">相反，配置会继承 RootSDDL 的安全描述符，默认情况下，这是安全的。</span><span class="sxs-lookup"><span data-stu-id="7225c-179">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="7225c-180">若要查看 RootSDDL 安全描述符，请键入：</span><span class="sxs-lookup"><span data-stu-id="7225c-180">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="7225c-181">若要更改 RootSDDL，请使用 `Set-Item` WSMan：驱动器中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7225c-181">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="7225c-182">若要更改会话配置的安全描述符，请将 `Set-PSSessionConfiguration` cmdlet 与 **SecurityDescriptorSDDL** 或 **ShowSecurityDescriptorUI** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="7225c-182">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="7225c-183">有关 WSMan：驱动器的详细信息，请参阅 WSMan 提供程序的帮助主题 ( "Get-help WSMan" ) 。</span><span class="sxs-lookup"><span data-stu-id="7225c-183">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="7225c-184">如何提供管理员凭据</span><span class="sxs-lookup"><span data-stu-id="7225c-184">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="7225c-185">若要在远程计算机上创建 PSSession 或运行命令，则默认情况下，当前用户必须是远程计算机上 Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="7225c-185">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="7225c-186">即使当前用户登录到作为 Administrators 组成员的帐户，也需要使用凭据。</span><span class="sxs-lookup"><span data-stu-id="7225c-186">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="7225c-187">如果当前用户是远程计算机上的 Administrators 组的成员，或者可以提供 Administrators 组的成员的凭据，请使用的 **Credential** 参数 `New-PSSession` 或用于 `Enter-PSSession` `Invoke-Command` 远程连接的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7225c-187">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="7225c-188">例如，以下命令提供管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="7225c-188">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="7225c-189">有关 **Credential** 参数的详细信息，请参阅 [新的 pssession](xref:Microsoft.PowerShell.Core.New-PSSession)、 [Enter-pssession](xref:Microsoft.PowerShell.Core.Enter-PSSession) 或 [Invoke 命令](xref:Microsoft.PowerShell.Core.Invoke-Command)。</span><span class="sxs-lookup"><span data-stu-id="7225c-189">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="7225c-190">如何为非管理用户启用远程处理</span><span class="sxs-lookup"><span data-stu-id="7225c-190">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="7225c-191">若要在远程计算机上建立 PSSession 或运行命令，用户必须有权使用远程计算机上的会话配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-191">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="7225c-192">默认情况下，只有计算机上 Administrators 组的成员才有权使用默认的会话配置。</span><span class="sxs-lookup"><span data-stu-id="7225c-192">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="7225c-193">因此，只有 Administrators 组的成员才能远程连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="7225c-193">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="7225c-194">若要允许其他用户连接到本地计算机，请向用户授予对本地计算机上默认会话配置的执行权限。</span><span class="sxs-lookup"><span data-stu-id="7225c-194">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="7225c-195">下面的命令将打开一个属性表，您可以在本地计算机上更改默认的 Microsoft PowerShell 会话配置的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="7225c-195">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="7225c-196">有关详细信息，请参阅 [about_Session_Configurations](about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="7225c-196">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="7225c-197">如何为其他域中的管理员启用远程处理</span><span class="sxs-lookup"><span data-stu-id="7225c-197">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="7225c-198">当另一个域中的用户是本地计算机上 Administrators 组的成员时，该用户将无法使用管理员权限远程连接到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7225c-198">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="7225c-199">默认情况下，来自其他域的远程连接仅使用标准用户特权令牌运行。</span><span class="sxs-lookup"><span data-stu-id="7225c-199">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="7225c-200">但是，你可以使用 **LocalAccountTokenFilterPolicy** 注册表项来更改默认行为，并允许作为 Administrators 组成员的远程用户使用管理员权限运行。</span><span class="sxs-lookup"><span data-stu-id="7225c-200">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="7225c-201">**LocalAccountTokenFilterPolicy** 条目禁用用户帐户控制 (UAC) 所有受影响计算机的所有用户的远程限制。</span><span class="sxs-lookup"><span data-stu-id="7225c-201">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="7225c-202">在更改策略之前，请仔细考虑此设置的含义。</span><span class="sxs-lookup"><span data-stu-id="7225c-202">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="7225c-203">若要更改策略，请使用以下命令将 **LocalAccountTokenFilterPolicy** 注册表项的值设置为1。</span><span class="sxs-lookup"><span data-stu-id="7225c-203">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="7225c-204">如何在远程命令中使用 ip 地址</span><span class="sxs-lookup"><span data-stu-id="7225c-204">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="7225c-205">的 **ComputerName** 参数 `New-PSSession` 、 `Enter-PSSession` 和 `Invoke-Command` cmdlet 接受 IP 地址作为有效的值。</span><span class="sxs-lookup"><span data-stu-id="7225c-205">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="7225c-206">但是，由于 Kerberos 身份验证不支持 IP 地址，因此，当你指定 IP 地址时，默认情况下将使用 NTLM 身份验证。</span><span class="sxs-lookup"><span data-stu-id="7225c-206">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="7225c-207">使用 NTLM 身份验证时，需要以下过程进行远程处理。</span><span class="sxs-lookup"><span data-stu-id="7225c-207">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="7225c-208">为 HTTPS 传输配置计算机，或将远程计算机的 IP 地址添加到本地计算机上的 TrustedHosts 列表中。</span><span class="sxs-lookup"><span data-stu-id="7225c-208">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="7225c-209">将 **Credential** 参数用于所有远程命令。</span><span class="sxs-lookup"><span data-stu-id="7225c-209">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="7225c-210">即使正在提交当前用户的凭据，也是必需的。</span><span class="sxs-lookup"><span data-stu-id="7225c-210">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="7225c-211">如何从基于工作组的计算机进行远程连接</span><span class="sxs-lookup"><span data-stu-id="7225c-211">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="7225c-212">如果本地计算机不在域中，则需要以下过程进行远程处理。</span><span class="sxs-lookup"><span data-stu-id="7225c-212">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="7225c-213">为 HTTPS 传输配置计算机，或将远程计算机的名称添加到本地计算机上的 TrustedHosts 列表中。</span><span class="sxs-lookup"><span data-stu-id="7225c-213">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="7225c-214">验证在基于工作组的计算机上是否设置了密码。</span><span class="sxs-lookup"><span data-stu-id="7225c-214">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="7225c-215">如果未设置密码或密码值为空，则无法运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="7225c-215">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="7225c-216">若要设置用户帐户的密码，请使用控制面板中的 "用户帐户"。</span><span class="sxs-lookup"><span data-stu-id="7225c-216">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="7225c-217">将 **Credential** 参数用于所有远程命令。</span><span class="sxs-lookup"><span data-stu-id="7225c-217">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="7225c-218">即使正在提交当前用户的凭据，也是必需的。</span><span class="sxs-lookup"><span data-stu-id="7225c-218">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="7225c-219">如何将计算机添加到受信任的主机列表</span><span class="sxs-lookup"><span data-stu-id="7225c-219">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="7225c-220">TrustedHosts 项可以包含以逗号分隔的计算机名称、IP 地址和完全限定的域名的列表。</span><span class="sxs-lookup"><span data-stu-id="7225c-220">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="7225c-221">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="7225c-221">Wildcards are permitted.</span></span>

<span data-ttu-id="7225c-222">若要查看或更改受信任的主机列表，请使用 WSMan：驱动器。</span><span class="sxs-lookup"><span data-stu-id="7225c-222">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="7225c-223">TrustedHost 项在 `WSMan:\localhost\Client` 节点中。</span><span class="sxs-lookup"><span data-stu-id="7225c-223">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="7225c-224">只有计算机上 Administrators 组的成员才有权更改计算机上的受信任主机列表。</span><span class="sxs-lookup"><span data-stu-id="7225c-224">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="7225c-225">警告：为 TrustedHosts 项设置的值会影响计算机的所有用户。</span><span class="sxs-lookup"><span data-stu-id="7225c-225">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="7225c-226">若要查看受信任的主机列表，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="7225c-226">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="7225c-227">你还可以使用 `Set-Location` cmdlet (alias = cd) 来浏览 WSMan：驱动器到位置。</span><span class="sxs-lookup"><span data-stu-id="7225c-227">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="7225c-228">例如：</span><span class="sxs-lookup"><span data-stu-id="7225c-228">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="7225c-229">若要将所有计算机添加到受信任的主机列表中，请使用以下命令，该命令将值 \* (ComputerName 中的所有) </span><span class="sxs-lookup"><span data-stu-id="7225c-229">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="7225c-230">你还可以使用通配符 (`*`) 将特定域中的所有计算机添加到受信任的主机列表。</span><span class="sxs-lookup"><span data-stu-id="7225c-230">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="7225c-231">例如，以下命令将 Fabrikam 域中的所有计算机添加到受信任的主机列表。</span><span class="sxs-lookup"><span data-stu-id="7225c-231">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="7225c-232">若要将特定计算机的名称添加到受信任的主机列表中，请使用以下命令格式：</span><span class="sxs-lookup"><span data-stu-id="7225c-232">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="7225c-233">其中每个值都 `<ComputerName>` 必须采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="7225c-233">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="7225c-234">例如：</span><span class="sxs-lookup"><span data-stu-id="7225c-234">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="7225c-235">若要将计算机名称添加到现有的受信任主机列表中，请先将当前值保存在变量中，然后将值设置为包含当前值和新值的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="7225c-235">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="7225c-236">例如，要将 Server01 计算机添加到现有的受信任主机列表，请使用以下命令</span><span class="sxs-lookup"><span data-stu-id="7225c-236">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="7225c-237">若要将特定计算机的 IP 地址添加到受信任的主机列表，请使用以下命令格式：</span><span class="sxs-lookup"><span data-stu-id="7225c-237">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="7225c-238">例如：</span><span class="sxs-lookup"><span data-stu-id="7225c-238">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="7225c-239">若要将计算机添加到远程计算机的 TrustedHosts 列表，请使用 `Connect-WSMan` cmdlet 将远程计算机的节点添加到本地计算机上的 WSMan：驱动器。</span><span class="sxs-lookup"><span data-stu-id="7225c-239">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="7225c-240">然后，使用 `Set-Item` 命令添加计算机。</span><span class="sxs-lookup"><span data-stu-id="7225c-240">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="7225c-241">有关 cmdlet 的详细信息 `Connect-WSMan` ，请参阅 [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan)。</span><span class="sxs-lookup"><span data-stu-id="7225c-241">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="7225c-242">计算机配置问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="7225c-242">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="7225c-243">本部分讨论与计算机、域或企业的特定配置相关的远程处理问题。</span><span class="sxs-lookup"><span data-stu-id="7225c-243">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="7225c-244">如何在备用端口上配置远程处理</span><span class="sxs-lookup"><span data-stu-id="7225c-244">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="7225c-245">默认情况下，PowerShell 远程处理将端口80用于 HTTP 传输。</span><span class="sxs-lookup"><span data-stu-id="7225c-245">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="7225c-246">只要用户未在远程命令中指定 **ConnectionURI** 或 **port** 参数，就会使用默认端口。</span><span class="sxs-lookup"><span data-stu-id="7225c-246">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="7225c-247">若要更改 PowerShell 使用的默认端口，请使用 `Set-Item` WSMan：驱动器中的 cmdlet 来更改侦听器叶节点中的端口值。</span><span class="sxs-lookup"><span data-stu-id="7225c-247">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="7225c-248">例如，以下命令将默认端口更改为8080。</span><span class="sxs-lookup"><span data-stu-id="7225c-248">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="7225c-249">如何配置与代理服务器的远程处理</span><span class="sxs-lookup"><span data-stu-id="7225c-249">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="7225c-250">由于 PowerShell 远程处理使用 HTTP 协议，因此它受 HTTP 代理设置的影响。</span><span class="sxs-lookup"><span data-stu-id="7225c-250">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="7225c-251">在具有代理服务器的企业中，用户无法直接访问 PowerShell 远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7225c-251">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="7225c-252">若要解决此问题，请使用远程命令中的代理设置选项。</span><span class="sxs-lookup"><span data-stu-id="7225c-252">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="7225c-253">提供了下列设置：</span><span class="sxs-lookup"><span data-stu-id="7225c-253">The following settings are available:</span></span>

- <span data-ttu-id="7225c-254">对 system.management.automation.remoting.proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="7225c-254">ProxyAccessType</span></span>
- <span data-ttu-id="7225c-255">ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="7225c-255">ProxyAuthentication</span></span>
- <span data-ttu-id="7225c-256">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="7225c-256">ProxyCredential</span></span>

<span data-ttu-id="7225c-257">若要为特定命令设置这些选项，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="7225c-257">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="7225c-258">使用 cmdlet 的 **对 system.management.automation.remoting.proxyaccesstype** 、 **ProxyAuthentication** 和 **ProxyCredential** 参数 `New-PSSessionOption` 创建具有企业代理设置的会话选项对象。</span><span class="sxs-lookup"><span data-stu-id="7225c-258">Use the **ProxyAccessType** , **ProxyAuthentication** , and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="7225c-259">Save 选项对象是一个变量。</span><span class="sxs-lookup"><span data-stu-id="7225c-259">Save the option object is a variable.</span></span>

1. <span data-ttu-id="7225c-260">使用包含选项对象的变量作为 **SessionOption** `New-PSSession` 、 `Enter-PSSession` 或命令的 SessionOption 参数的值 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-260">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="7225c-261">例如，以下命令使用代理会话选项创建会话选项对象，然后使用该对象创建远程会话。</span><span class="sxs-lookup"><span data-stu-id="7225c-261">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="7225c-262">有关 cmdlet 的详细信息 `New-PSSessionOption` ，请参阅 [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)。</span><span class="sxs-lookup"><span data-stu-id="7225c-262">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="7225c-263">若要为当前会话中的所有远程命令设置这些选项，请使用 `New-PSSessionOption` 在首选项变量的值中创建的选项对象 `$PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-263">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="7225c-264">有关详细信息，请参阅 [about_Preference_Variables](about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="7225c-264">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="7225c-265">若要在本地计算机上为所有远程命令设置这些选项，请将 `$PSSessionOption` 首选项变量添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="7225c-265">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="7225c-266">有关 PowerShell 配置文件的详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="7225c-266">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="7225c-267">如何检测64位计算机上的32位会话</span><span class="sxs-lookup"><span data-stu-id="7225c-267">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="7225c-268">如果远程计算机运行的是64位版本的 Windows，并且远程命令使用32位会话配置（如 Microsoft.powershell32），则 Windows 远程管理 (WinRM) 加载 WOW64 进程，Windows 会将对目录的所有引用自动重定向 `$env:Windir\System32` 到 `$env:Windir\SysWOW64` 目录。</span><span class="sxs-lookup"><span data-stu-id="7225c-268">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="7225c-269">因此，如果你尝试使用 System32 目录中的工具，但在 SysWow64 目录中没有相应的工具（如 `Defrag.exe` ），则在目录中找不到这些工具。</span><span class="sxs-lookup"><span data-stu-id="7225c-269">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="7225c-270">若要查找正在会话中使用的处理器体系结构，请使用 **PROCESSOR_ARCHITECTURE** 环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="7225c-270">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="7225c-271">以下命令将查找变量中会话的处理器体系结构 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-271">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="7225c-272">有关会话配置的详细信息，请参阅 [about_Session_Configurations](about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="7225c-272">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="7225c-273">策略和首选项问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="7225c-273">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="7225c-274">本部分讨论在本地和远程计算机上设置的策略和首选项相关的远程处理问题。</span><span class="sxs-lookup"><span data-stu-id="7225c-274">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="7225c-275">如何更改 Import-PSSession 和 Import-Module 的执行策略</span><span class="sxs-lookup"><span data-stu-id="7225c-275">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="7225c-276">`Import-PSSession`和 `Export-PSSession` cmdlet 将创建包含未签名的脚本文件和格式化文件的模块。</span><span class="sxs-lookup"><span data-stu-id="7225c-276">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="7225c-277">若要导入通过使用或创建的模块， `Import-PSSession` `Import-Module` 当前会话中的执行策略不能是受限的，也不能 AllSigned。</span><span class="sxs-lookup"><span data-stu-id="7225c-277">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="7225c-278">有关 PowerShell 执行策略的信息，请参阅 [about_Execution_Policies](about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7225c-278">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="7225c-279">若要在不更改注册表中设置的本地计算机的执行策略的情况下导入模块，请使用的 **作用域** 参数 `Set-ExecutionPolicy` 为单个进程设置限制性较低的执行策略。</span><span class="sxs-lookup"><span data-stu-id="7225c-279">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="7225c-280">例如，以下命令使用 `RemoteSigned` 执行策略启动进程。</span><span class="sxs-lookup"><span data-stu-id="7225c-280">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="7225c-281">执行策略更改只会影响当前进程，并且不会更改 PowerShell **set-executionpolicy** 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="7225c-281">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="7225c-282">你还可以使用的 **set-executionpolicy** 参数 `PowerShell.exe` 来启动具有限制性较低的执行策略的单个会话。</span><span class="sxs-lookup"><span data-stu-id="7225c-282">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="7225c-283">有关执行策略的详细信息，请参阅 [about_Execution_Policies](about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7225c-283">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="7225c-284">要了解详情，请键入 `PowerShell.exe -?`。</span><span class="sxs-lookup"><span data-stu-id="7225c-284">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="7225c-285">如何设置和更改配额</span><span class="sxs-lookup"><span data-stu-id="7225c-285">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="7225c-286">您可以使用配额来保护本地计算机和远程计算机的资源使用过度，这两者都是意外的和恶意的。</span><span class="sxs-lookup"><span data-stu-id="7225c-286">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="7225c-287">基本配置中提供以下配额。</span><span class="sxs-lookup"><span data-stu-id="7225c-287">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="7225c-288">WSMan 提供程序 (WSMan： ) 提供多个配额设置，如节点中的 **MaxEnvelopeSizeKB** 和 **MaxProviderRequests** 设置 `WSMan:<ComputerName>` 以及节点中的 **MaxConcurrentOperations** 、 **MaxConcurrentOperationsPerUser** 和 **MaxConnections** 设置 `WSMan:<ComputerName>\Service` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-288">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations** , **MaxConcurrentOperationsPerUser** , and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="7225c-289">可以通过使用 cmdlet 的 **MaximumReceivedDataSizePerCommand** 和 **MaximumReceivedObjectSize** 参数 `New-PSSessionOption` 和 `$PSSessionOption` 首选项变量来保护本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7225c-289">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="7225c-290">可以通过添加对会话配置的限制来保护远程计算机，例如通过使用 cmdlet 的 **MaximumReceivedDataSizePerCommandMB** 和 **MaximumReceivedObjectSizeMB** 参数 `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-290">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="7225c-291">当配额与命令冲突时，PowerShell 会生成错误。</span><span class="sxs-lookup"><span data-stu-id="7225c-291">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="7225c-292">若要解决此错误，请更改远程命令以符合配额要求。</span><span class="sxs-lookup"><span data-stu-id="7225c-292">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="7225c-293">或者，确定配额的来源，然后增加配额以允许命令完成。</span><span class="sxs-lookup"><span data-stu-id="7225c-293">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="7225c-294">例如，以下命令将远程计算机上的 Microsoft PowerShell 会话配置中的对象大小配额增加 10 MB (默认值) 为 11 MB。</span><span class="sxs-lookup"><span data-stu-id="7225c-294">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="7225c-295">有关 cmdlet 的详细信息 `New-PSSessionOption` ，请参阅 `New-PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-295">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="7225c-296">有关 WS-Management 配额的详细信息，请参阅 [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7225c-296">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="7225c-297">如何解决超时错误</span><span class="sxs-lookup"><span data-stu-id="7225c-297">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="7225c-298">您可以使用超时来保护本地计算机和远程计算机的资源使用过度，这两者都是意外的和恶意的。</span><span class="sxs-lookup"><span data-stu-id="7225c-298">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="7225c-299">如果在本地计算机和远程计算机上设置了超时，则 PowerShell 将使用最短超时设置。</span><span class="sxs-lookup"><span data-stu-id="7225c-299">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="7225c-300">基本配置中提供以下超时。</span><span class="sxs-lookup"><span data-stu-id="7225c-300">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="7225c-301">WSMan 提供程序 (WSMan： ) 提供多个客户端和服务端超时设置，如节点中的 **MaxTimeoutms** 设置 `WSMan:<ComputerName>` 以及节点中的 **EnumerationTimeoutms** 和 **MaxPacketRetrievalTimeSeconds** 设置 `WSMan:<ComputerName>\Service` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-301">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="7225c-302">可以通过使用 cmdlet 的 **CancelTimeout** 、 **IdleTimeout** 、 **OpenTimeout** 和 **OperationTimeout** 参数 `New-PSSessionOption` 以及首选项变量来保护本地计算机 `$PSSessionOption` 。</span><span class="sxs-lookup"><span data-stu-id="7225c-302">You can protect the local computer by using the **CancelTimeout** , **IdleTimeout** , **OpenTimeout** , and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="7225c-303">还可以通过在会话的会话配置中以编程方式设置超时值来保护远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7225c-303">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="7225c-304">当超时值不允许操作完成时，PowerShell 将终止操作并生成错误。</span><span class="sxs-lookup"><span data-stu-id="7225c-304">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="7225c-305">若要解决此错误，请将命令更改为在超时间隔内完成，或确定超时限制的源，并增加超时间隔以允许命令完成。</span><span class="sxs-lookup"><span data-stu-id="7225c-305">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="7225c-306">例如，以下命令使用 `New-PSSessionOption` cmdlet 来创建 **OperationTimeout** 值为4分钟)  (的会话选项对象，并使用 session 选项对象来创建远程会话。</span><span class="sxs-lookup"><span data-stu-id="7225c-306">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="7225c-307">有关 WS-Management 超时的详细信息，请参阅 WSMan 提供程序的帮助主题 (类型 `Get-Help WSMan`) 。</span><span class="sxs-lookup"><span data-stu-id="7225c-307">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="7225c-308">有关 cmdlet 的详细信息 `New-PSSessionOption` ，请参阅 [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)。</span><span class="sxs-lookup"><span data-stu-id="7225c-308">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="7225c-309">无响应行为疑难解答</span><span class="sxs-lookup"><span data-stu-id="7225c-309">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="7225c-310">本部分讨论的远程处理问题会阻止命令完成，并防止或延迟 PowerShell 提示符的返回。</span><span class="sxs-lookup"><span data-stu-id="7225c-310">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="7225c-311">如何中断命令</span><span class="sxs-lookup"><span data-stu-id="7225c-311">How to interrupt a command</span></span>

<span data-ttu-id="7225c-312">某些本机 Windows 程序（例如具有用户界面的程序、提示输入的控制台应用程序以及使用 Win32 控制台 API 的控制台应用程序）在 PowerShell 远程主机中无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="7225c-312">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="7225c-313">使用这些程序时，可能会出现意外的行为，例如无输出、部分输出或未完成的远程命令。</span><span class="sxs-lookup"><span data-stu-id="7225c-313">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="7225c-314">若要结束无响应的程序，请键入<kbd>CTRL</kbd> + <kbd>C</kbd>。</span><span class="sxs-lookup"><span data-stu-id="7225c-314">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="7225c-315">若要查看可能已报告的任何错误，请键入 `$error` 本地主机和远程会话。</span><span class="sxs-lookup"><span data-stu-id="7225c-315">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="7225c-316">如何从操作失败中恢复</span><span class="sxs-lookup"><span data-stu-id="7225c-316">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="7225c-317">如果操作在完成之前终止，则会返回此错误。</span><span class="sxs-lookup"><span data-stu-id="7225c-317">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="7225c-318">通常，当 WinRM 服务在其他 WinRM 操作正在进行时停止或重新启动时，会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="7225c-318">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="7225c-319">若要解决此问题，请确认 WinRM 服务正在运行，然后重试该命令。</span><span class="sxs-lookup"><span data-stu-id="7225c-319">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="7225c-320">通过 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7225c-320">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="7225c-321">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7225c-321">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="7225c-322">重新运行生成错误的命令。</span><span class="sxs-lookup"><span data-stu-id="7225c-322">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="7225c-323">Linux 和 macOS 限制</span><span class="sxs-lookup"><span data-stu-id="7225c-323">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="7225c-324">身份验证</span><span class="sxs-lookup"><span data-stu-id="7225c-324">Authentication</span></span>

<span data-ttu-id="7225c-325">在 macOS 上只使用基本身份验证，尝试使用其他身份验证方案可能会导致进程崩溃。</span><span class="sxs-lookup"><span data-stu-id="7225c-325">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="7225c-326">请参阅 [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) 说明。</span><span class="sxs-lookup"><span data-stu-id="7225c-326">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="7225c-327">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7225c-327">SEE ALSO</span></span>

[<span data-ttu-id="7225c-328">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="7225c-328">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="7225c-329">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="7225c-329">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="7225c-330">Import-Module</span><span class="sxs-lookup"><span data-stu-id="7225c-330">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="7225c-331">about_Remote</span><span class="sxs-lookup"><span data-stu-id="7225c-331">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="7225c-332">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="7225c-332">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="7225c-333">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="7225c-333">about_Remote_Variables</span></span>](about_Remote_Variables.md)
