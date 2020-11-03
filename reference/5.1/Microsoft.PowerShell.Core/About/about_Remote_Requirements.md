---
description: 描述在 PowerShell 中运行远程命令的系统要求和配置要求。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: 63971aeaa92eb10a745f2a02e0c7cf00dbf65d8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200247"
---
# <a name="about-remote-requirements"></a><span data-ttu-id="61ecd-104">关于远程要求</span><span class="sxs-lookup"><span data-stu-id="61ecd-104">About Remote Requirements</span></span>

## <a name="short-description"></a><span data-ttu-id="61ecd-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="61ecd-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="61ecd-106">描述在 PowerShell 中运行远程命令的系统要求和配置要求。</span><span class="sxs-lookup"><span data-stu-id="61ecd-106">Describes the system requirements and configuration requirements for running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="61ecd-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="61ecd-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="61ecd-108">本主题介绍在 PowerShell 中建立远程连接和运行远程命令的系统要求、用户要求和资源要求。</span><span class="sxs-lookup"><span data-stu-id="61ecd-108">This topic describes the system requirements, user requirements, and resource requirements for establishing remote connections and running remote commands in PowerShell.</span></span> <span data-ttu-id="61ecd-109">它还提供了有关配置远程操作的说明。</span><span class="sxs-lookup"><span data-stu-id="61ecd-109">It also provides instructions for configuring remote operations.</span></span>

<span data-ttu-id="61ecd-110">注意：许多 cmdlet (包括 Get-help、Get-wmiobject 和 Get-WinEvent cmdlet，) 从远程计算机获取对象，方法是使用 Microsoft .NET Framework 方法检索这些对象。</span><span class="sxs-lookup"><span data-stu-id="61ecd-110">Note: Many cmdlets (including the Get-Service, Get-Process, Get-WMIObject, Get-EventLog, and Get-WinEvent cmdlets) get objects from remote computers by using Microsoft .NET Framework methods to retrieve the objects.</span></span> <span data-ttu-id="61ecd-111">它们不使用 PowerShell 远程处理基础结构。</span><span class="sxs-lookup"><span data-stu-id="61ecd-111">They do not use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="61ecd-112">本文档中的要求不适用于这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="61ecd-112">The requirements in this document do not apply to these cmdlets.</span></span>

<span data-ttu-id="61ecd-113">若要查找具有 ComputerName 参数但不使用 Windows PowerShell 远程处理的 cmdlet，请阅读 cmdlet 的 ComputerName 参数说明。</span><span class="sxs-lookup"><span data-stu-id="61ecd-113">To find the cmdlets that have a ComputerName parameter but do not use Windows PowerShell remoting, read the description of the ComputerName parameter of the cmdlets.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="61ecd-114">系统要求</span><span class="sxs-lookup"><span data-stu-id="61ecd-114">SYSTEM REQUIREMENTS</span></span>

<span data-ttu-id="61ecd-115">若要在 Windows PowerShell 3.0 上运行远程会话，本地计算机和远程计算机必须具有以下各项：</span><span class="sxs-lookup"><span data-stu-id="61ecd-115">To run remote sessions on Windows PowerShell 3.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="61ecd-116">Windows PowerShell 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="61ecd-116">Windows PowerShell 3.0 or later</span></span>
- <span data-ttu-id="61ecd-117">Microsoft .NET Framework 4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="61ecd-117">The Microsoft .NET Framework 4 or later</span></span>
- <span data-ttu-id="61ecd-118">Windows 远程管理3。0</span><span class="sxs-lookup"><span data-stu-id="61ecd-118">Windows Remote Management 3.0</span></span>

<span data-ttu-id="61ecd-119">若要在 Windows PowerShell 2.0 上运行远程会话，本地计算机和远程计算机必须具有以下各项：</span><span class="sxs-lookup"><span data-stu-id="61ecd-119">To run remote sessions on Windows PowerShell 2.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="61ecd-120">Windows PowerShell 2.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="61ecd-120">Windows PowerShell 2.0 or later</span></span>
- <span data-ttu-id="61ecd-121">Microsoft .NET Framework 2.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="61ecd-121">The Microsoft .NET Framework 2.0 or later</span></span>
- <span data-ttu-id="61ecd-122">Windows 远程管理2。0</span><span class="sxs-lookup"><span data-stu-id="61ecd-122">Windows Remote Management 2.0</span></span>

<span data-ttu-id="61ecd-123">可以在运行 Windows PowerShell 2.0 和 Windows PowerShell 3.0 的计算机之间创建远程会话。</span><span class="sxs-lookup"><span data-stu-id="61ecd-123">You can create remote sessions between computers running Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span> <span data-ttu-id="61ecd-124">但是，仅在 Windows PowerShell 3.0 上运行的功能（如断开连接和重新连接到会话的能力）仅在两台计算机都运行 Windows PowerShell 3.0 时才可用。</span><span class="sxs-lookup"><span data-stu-id="61ecd-124">However, features that run only on Windows PowerShell 3.0, such as the ability to disconnect and reconnect to sessions, are available only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="61ecd-125">若要查找已安装的 PowerShell 版本的版本号，请使用 $PSVersionTable 自动变量。</span><span class="sxs-lookup"><span data-stu-id="61ecd-125">To find the version number of an installed version of PowerShell, use the $PSVersionTable automatic variable.</span></span>

<span data-ttu-id="61ecd-126">Windows 8、Windows Server 2012 和更新版本的 Windows 操作系统中都包含了 Windows 远程管理 (WinRM) 3.0 和 Microsoft .NET Framework 4。</span><span class="sxs-lookup"><span data-stu-id="61ecd-126">Windows Remote Management (WinRM) 3.0 and Microsoft .NET Framework 4 are included in Windows 8, Windows Server 2012, and newer releases of the Windows operating system.</span></span> <span data-ttu-id="61ecd-127">对于较早版本的操作系统，Windows Management Framework 3.0 中包含 WinRM 3.0。</span><span class="sxs-lookup"><span data-stu-id="61ecd-127">WinRM 3.0 is included in Windows Management Framework 3.0 for older operating systems.</span></span> <span data-ttu-id="61ecd-128">如果计算机不具有所需的 WinRM 版本或 Microsoft .NET 框架，则安装将失败。</span><span class="sxs-lookup"><span data-stu-id="61ecd-128">If the computer does not have the required version of WinRM or the Microsoft .NET Framework, the installation fails.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="61ecd-129">用户权限</span><span class="sxs-lookup"><span data-stu-id="61ecd-129">USER PERMISSIONS</span></span>

<span data-ttu-id="61ecd-130">若要创建远程会话并运行远程命令，则默认情况下，当前用户必须是远程计算机上 Administrators 组的成员，或者提供管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="61ecd-130">To create remote sessions and run remote commands, by default, the current user must be a member of the Administrators group on the remote computer or provide the credentials of an administrator.</span></span> <span data-ttu-id="61ecd-131">否则，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="61ecd-131">Otherwise, the command fails.</span></span>

<span data-ttu-id="61ecd-132">在远程计算机上创建会话和运行命令所需的权限 (或本地计算机上的远程会话中) 由会话配置建立， (在该会话连接到的远程计算机上也称为 "终结点" ) 。</span><span class="sxs-lookup"><span data-stu-id="61ecd-132">The permissions required to create sessions and run commands on a remote computer (or in a remote session on the local computer) are established by the session configuration (also known as an "endpoint") on the remote computer to which the session connects.</span></span> <span data-ttu-id="61ecd-133">具体而言，会话配置上的安全描述符确定谁有权访问会话配置，哪些用户可以使用它来进行连接。</span><span class="sxs-lookup"><span data-stu-id="61ecd-133">Specifically, the security descriptor on the session configuration determines who has access to the session configuration and who can use it to connect.</span></span>

<span data-ttu-id="61ecd-134">默认会话配置、Microsoft.powershell32 和 Microsoft PowerShell 上的安全描述符允许仅访问 Administrators 组的成员的访问权限。</span><span class="sxs-lookup"><span data-stu-id="61ecd-134">The security descriptors on the default session configurations, Microsoft.PowerShell, Microsoft.PowerShell32, and Microsoft.PowerShell.Workflow, allow access only to members of the Administrators group.</span></span>

<span data-ttu-id="61ecd-135">如果当前用户没有使用会话配置的权限，则运行命令 (使用临时会话) 或在远程计算机上创建持久会话的命令将失败。</span><span class="sxs-lookup"><span data-stu-id="61ecd-135">If the current user doesn't have permission to use the session configuration, the command to run a command (which uses a temporary session) or create a persistent session on the remote computer fails.</span></span> <span data-ttu-id="61ecd-136">用户可以使用 cmdlet 的 ConfigurationName 参数来创建会话，以选择不同的会话配置（如果有）。</span><span class="sxs-lookup"><span data-stu-id="61ecd-136">The user can use the ConfigurationName parameter of cmdlets that create sessions to select a different session configuration, if one is available.</span></span>

<span data-ttu-id="61ecd-137">计算机上 Administrators 组的成员可以通过更改默认会话配置上的安全描述符，并通过使用不同的安全描述符创建新的会话配置来确定有权远程连接到计算机的人员。</span><span class="sxs-lookup"><span data-stu-id="61ecd-137">Members of the Administrators group on a computer can determine who has permission to connect to the computer remotely by changing the security descriptors on the default session configurations and by creating new session configurations with different security descriptors.</span></span>

<span data-ttu-id="61ecd-138">有关会话配置的详细信息，请参阅 [about_Session_Configurations](about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="61ecd-138">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="windows-network-locations"></a><span data-ttu-id="61ecd-139">WINDOWS 网络位置</span><span class="sxs-lookup"><span data-stu-id="61ecd-139">WINDOWS NETWORK LOCATIONS</span></span>

<span data-ttu-id="61ecd-140">从 Windows PowerShell 3.0 开始，Enable-PSRemoting cmdlet 可在专用、域和公用网络上的 Windows 客户端和服务器版本上启用远程处理。</span><span class="sxs-lookup"><span data-stu-id="61ecd-140">Beginning in Windows PowerShell 3.0, the Enable-PSRemoting cmdlet can enable remoting on client and server versions of Windows on private, domain, and public networks.</span></span>

<span data-ttu-id="61ecd-141">在具有专用网络和域网络的 Windows server 版本中，Enable-PSRemoting cmdlet 将创建允许无限制远程访问的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="61ecd-141">On server versions of Windows with private and domain networks, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span> <span data-ttu-id="61ecd-142">它还为公用网络创建防火墙规则，该规则仅允许来自同一本地子网中的计算机进行远程访问。</span><span class="sxs-lookup"><span data-stu-id="61ecd-142">It also creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="61ecd-143">默认情况下，在公用网络上的 Windows 服务器版本上会启用此本地子网防火墙规则，但 Enable-PSRemoting 会在更改或删除规则的情况下重新应用该规则。</span><span class="sxs-lookup"><span data-stu-id="61ecd-143">This local subnet firewall rule is enabled by default on server versions of Windows on public networks, but Enable-PSRemoting reapplies the rule in case it was changed or deleted.</span></span>

<span data-ttu-id="61ecd-144">对于具有专用网络和域网络的 Windows 的客户端版本，默认情况下，Enable-PSRemoting cmdlet 将创建允许无限制远程访问的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="61ecd-144">On client versions of Windows with private and domain networks, by default, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span>

<span data-ttu-id="61ecd-145">若要在具有公用网络的 Windows 的客户端版本上启用远程处理，请使用 Enable-PSRemoting cmdlet 的 SkipNetworkProfileCheck 参数。</span><span class="sxs-lookup"><span data-stu-id="61ecd-145">To enable remoting on client versions of Windows with public networks, use the SkipNetworkProfileCheck parameter of the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="61ecd-146">它创建一个防火墙规则，该规则仅允许来自同一本地子网中的计算机进行远程访问。</span><span class="sxs-lookup"><span data-stu-id="61ecd-146">It creates a firewall rule that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="61ecd-147">若要删除公用网络上的本地子网限制并允许从 Windows 客户端和服务器版本上的所有位置进行远程访问，请在 NetSecurity 模块中使用 Set-NetFirewallRule cmdlet。</span><span class="sxs-lookup"><span data-stu-id="61ecd-147">To remove the local subnet restriction on public networks and allow remote access from all locations on client and server versions of Windows, use the Set-NetFirewallRule cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="61ecd-148">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="61ecd-148">Run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="61ecd-149">在 Windows PowerShell 2.0 中，在 Windows 的服务器版本上 Enable-PSRemoting 创建允许在所有网络上进行远程访问的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="61ecd-149">In Windows PowerShell 2.0, on server versions of Windows, Enable-PSRemoting creates firewall rules that permit remote access on all networks.</span></span>

<span data-ttu-id="61ecd-150">在 Windows PowerShell 2.0 中，在 Windows 的客户端版本上，Enable-PSRemoting 仅在专用网络和域网络上创建防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="61ecd-150">In Windows PowerShell 2.0, on client versions of Windows, Enable-PSRemoting creates firewall rules only on private and domain networks.</span></span> <span data-ttu-id="61ecd-151">如果网络位置是公共的，Enable-PSRemoting 会失败。</span><span class="sxs-lookup"><span data-stu-id="61ecd-151">If the network location is public, Enable-PSRemoting fails.</span></span>

## <a name="run-as-administrator"></a><span data-ttu-id="61ecd-152">以管理员身份运行</span><span class="sxs-lookup"><span data-stu-id="61ecd-152">RUN AS ADMINISTRATOR</span></span>

<span data-ttu-id="61ecd-153">以下远程处理操作需要管理员权限：</span><span class="sxs-lookup"><span data-stu-id="61ecd-153">Administrator privileges are required for the following remoting operations:</span></span>

- <span data-ttu-id="61ecd-154">建立与本地计算机的远程连接。</span><span class="sxs-lookup"><span data-stu-id="61ecd-154">Establishing a remote connection to the local computer.</span></span> <span data-ttu-id="61ecd-155">这通常称为 "环回" 方案。</span><span class="sxs-lookup"><span data-stu-id="61ecd-155">This is commonly known as a "loopback" scenario.</span></span>

- <span data-ttu-id="61ecd-156">管理本地计算机上的会话配置。</span><span class="sxs-lookup"><span data-stu-id="61ecd-156">Managing session configurations on the local computer.</span></span>

- <span data-ttu-id="61ecd-157">查看和更改本地计算机上的 WS-Management 设置。</span><span class="sxs-lookup"><span data-stu-id="61ecd-157">Viewing and changing WS-Management settings on the local computer.</span></span> <span data-ttu-id="61ecd-158">这些是 WSMAN：驱动器的 LocalHost 节点中的设置。</span><span class="sxs-lookup"><span data-stu-id="61ecd-158">These are the settings in the LocalHost node of the WSMAN: drive.</span></span>

<span data-ttu-id="61ecd-159">若要执行这些任务，必须使用 "以管理员身份运行" 选项启动 PowerShell，即使您是本地计算机上 Administrators 组的成员也是如此。</span><span class="sxs-lookup"><span data-stu-id="61ecd-159">To perform these tasks, you must start PowerShell with the "Run as administrator" option even if you are a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="61ecd-160">在 Windows 7 和 Windows Server 2008 R2 中，通过 "以管理员身份运行" 选项启动 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="61ecd-160">In Windows 7 and in Windows Server 2008 R2, to start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="61ecd-161">依次单击 "开始"、"所有程序"、"附件"，然后单击 "Windows PowerShell" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="61ecd-161">Click Start, click All Programs, click Accessories, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="61ecd-162">右键单击 "Windows PowerShell"，然后单击 "以管理员身份运行"。</span><span class="sxs-lookup"><span data-stu-id="61ecd-162">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="61ecd-163">若要通过 "以管理员身份运行" 选项启动 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="61ecd-163">To start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="61ecd-164">依次单击 "开始"、"所有程序"，然后单击 "Windows PowerShell" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="61ecd-164">Click Start, click All Programs, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="61ecd-165">右键单击 "Windows PowerShell"，然后单击 "以管理员身份运行"。</span><span class="sxs-lookup"><span data-stu-id="61ecd-165">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="61ecd-166">Windows PowerShell 的其他 Windows 资源管理器项（包括快捷方式）中也提供了 "以管理员身份运行" 选项。</span><span class="sxs-lookup"><span data-stu-id="61ecd-166">The "Run as administrator" option is also available in other Windows Explorer entries for Windows PowerShell, including shortcuts.</span></span> <span data-ttu-id="61ecd-167">只需右键单击该项目，然后单击 "以管理员身份运行" 即可。</span><span class="sxs-lookup"><span data-stu-id="61ecd-167">Just right-click the item, and then click "Run as administrator".</span></span>

<span data-ttu-id="61ecd-168">从其他程序（如 Cmd.exe）启动 Windows PowerShell 时，请使用 "以管理员身份运行" 选项启动程序。</span><span class="sxs-lookup"><span data-stu-id="61ecd-168">When you start Windows PowerShell from another program such as Cmd.exe, use the "Run as administrator" option to start the program.</span></span>

## <a name="how-to-configure-your-computer-for-remoting"></a><span data-ttu-id="61ecd-169">如何将计算机配置为进行远程处理</span><span class="sxs-lookup"><span data-stu-id="61ecd-169">HOW TO CONFIGURE YOUR COMPUTER FOR REMOTING</span></span>

<span data-ttu-id="61ecd-170">运行所有受支持的 Windows 版本的计算机无需任何配置即可在 PowerShell 中建立远程连接和运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="61ecd-170">Computers running all supported versions of Windows can establish remote connections to and run remote commands in PowerShell without any configuration.</span></span> <span data-ttu-id="61ecd-171">但是，若要接收连接以及允许用户创建本地和远程用户管理的 PowerShell 会话 ( "Pssession" ) 并在本地计算机上运行命令，则必须在计算机上启用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="61ecd-171">However, to receive connections, and allow users to create local and remote user-managed PowerShell sessions ("PSSessions") and run commands on the local computer, you must enable PowerShell remoting on the computer.</span></span>

<span data-ttu-id="61ecd-172">默认情况下，为 PowerShell 远程处理启用 windows server 2012 和更新版本的 Windows Server。</span><span class="sxs-lookup"><span data-stu-id="61ecd-172">Windows Server 2012 and newer releases of Windows Server are enabled for PowerShell remoting by default.</span></span> <span data-ttu-id="61ecd-173">如果更改了设置，则可以通过运行 Enable-PSRemoting cmdlet 来还原默认设置。</span><span class="sxs-lookup"><span data-stu-id="61ecd-173">If the settings are changed, you can restore the default settings by running the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="61ecd-174">在所有其他受支持的 Windows 版本上，需要运行 Enable-PSRemoting cmdlet 来启用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="61ecd-174">On all other supported versions of Windows, you need to run the Enable-PSRemoting cmdlet to enable PowerShell remoting.</span></span>

<span data-ttu-id="61ecd-175">WinRM 服务支持 PowerShell 的远程处理功能，这是用于管理的 Web 服务 (WS-MANAGEMENT) 协议的 Microsoft 实现。</span><span class="sxs-lookup"><span data-stu-id="61ecd-175">The remoting features of PowerShell are supported by the WinRM service, which is the Microsoft implementation of the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="61ecd-176">启用 PowerShell 远程处理时，将更改 WS-Management 的默认配置，并添加允许用户连接到 WS-MANAGEMENT 的系统配置。</span><span class="sxs-lookup"><span data-stu-id="61ecd-176">When you enable PowerShell remoting, you change the default configuration of WS-Management and add system configuration that allow users to connect to WS-Management.</span></span>

<span data-ttu-id="61ecd-177">将 PowerShell 配置为接收远程命令：</span><span class="sxs-lookup"><span data-stu-id="61ecd-177">To configure PowerShell to receive remote commands:</span></span>

1. <span data-ttu-id="61ecd-178">以 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="61ecd-178">Start PowerShell with the "Run as administrator" option.</span></span>
2. <span data-ttu-id="61ecd-179">在命令提示符处，键入：`Enable-PSRemoting`</span><span class="sxs-lookup"><span data-stu-id="61ecd-179">At the command prompt, type: `Enable-PSRemoting`</span></span>

<span data-ttu-id="61ecd-180">若要验证远程处理是否已正确配置，请运行以下命令（如）在本地计算机上创建远程会话的测试命令。</span><span class="sxs-lookup"><span data-stu-id="61ecd-180">To verify that remoting is configured correctly, run a test command such as the following command, which creates a remote session on the local computer.</span></span>

```powershell
New-PSSession
```

<span data-ttu-id="61ecd-181">如果远程处理配置正确，则该命令将在本地计算机上创建一个会话，并返回表示该会话的对象。</span><span class="sxs-lookup"><span data-stu-id="61ecd-181">If remoting is configured correctly, the command will create a session on the local computer and return an object that represents the session.</span></span> <span data-ttu-id="61ecd-182">输出应类似于以下示例输出：</span><span class="sxs-lookup"><span data-stu-id="61ecd-182">The output should resemble the following sample output:</span></span>

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

<span data-ttu-id="61ecd-183">如果命令失败，请参阅 [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="61ecd-183">If the command fails, for assistance, see [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span></span>

## <a name="understand-policies"></a><span data-ttu-id="61ecd-184">了解策略</span><span class="sxs-lookup"><span data-stu-id="61ecd-184">UNDERSTAND POLICIES</span></span>

<span data-ttu-id="61ecd-185">远程工作时，可以使用 PowerShell 的两个实例，一个实例在本地计算机上，另一个位于远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="61ecd-185">When you work remotely, you use two instances of PowerShell, one on the local computer and one on the remote computer.</span></span> <span data-ttu-id="61ecd-186">因此，你的工作会受到本地和远程计算机上的 Windows 策略和 PowerShell 策略的影响。</span><span class="sxs-lookup"><span data-stu-id="61ecd-186">As a result, your work is affected by the Windows policies and the PowerShell policies on the local and remote computers.</span></span>

<span data-ttu-id="61ecd-187">通常，在连接之前以及建立连接时，本地计算机上的策略是有效的。</span><span class="sxs-lookup"><span data-stu-id="61ecd-187">In general, before you connect and as you are establishing the connection, the policies on the local computer are in effect.</span></span> <span data-ttu-id="61ecd-188">使用连接时，远程计算机上的策略生效。</span><span class="sxs-lookup"><span data-stu-id="61ecd-188">When you are using the connection, the policies on the remote computer are in effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="61ecd-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61ecd-189">SEE ALSO</span></span>

[<span data-ttu-id="61ecd-190">about_Remote</span><span class="sxs-lookup"><span data-stu-id="61ecd-190">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="61ecd-191">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="61ecd-191">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="61ecd-192">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="61ecd-192">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="61ecd-193">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="61ecd-193">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="61ecd-194">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="61ecd-194">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="61ecd-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="61ecd-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
