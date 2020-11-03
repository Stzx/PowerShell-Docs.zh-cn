---
description: 提供有关 Windows Management Instrumentation (WMI) 和 Windows PowerShell 的背景信息。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200228"
---
# <a name="about-wmi-cmdlets"></a><span data-ttu-id="7833e-104">关于 WMI Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7833e-104">About WMI Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="7833e-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="7833e-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="7833e-106">提供有关 Windows Management Instrumentation (WMI) 和 Windows PowerShell 的背景信息。</span><span class="sxs-lookup"><span data-stu-id="7833e-106">Provides background information about Windows Management Instrumentation (WMI) and Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="7833e-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="7833e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7833e-108">本主题提供有关 WMI 技术、适用于 Windows PowerShell 的 WMI cmdlet、基于 WMI 的远程处理、WMI 加速器和 WMI 疑难解答的信息。</span><span class="sxs-lookup"><span data-stu-id="7833e-108">This topic provides information about WMI technology, the WMI cmdlets for Windows PowerShell, WMI-based remoting, WMI accelerators, and WMI troubleshooting.</span></span> <span data-ttu-id="7833e-109">本主题还提供了有关 WMI 的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="7833e-109">This topic also provides links to more information about WMI.</span></span>

### <a name="about-wmi"></a><span data-ttu-id="7833e-110">关于 WMI</span><span class="sxs-lookup"><span data-stu-id="7833e-110">ABOUT WMI</span></span>

<span data-ttu-id="7833e-111">Windows Management Instrumentation (WMI) 是 Microsoft 对基于 Web 的企业管理 (WBEM) 的实现，WBEM 是一项业界倡议，用于为访问企业环境中的管理信息开发一项标准技术。</span><span class="sxs-lookup"><span data-stu-id="7833e-111">Windows Management Instrumentation (WMI) is the Microsoft implementation of Web-Based Enterprise Management (WBEM), which is an industry initiative to develop a standard technology for accessing management information in an enterprise environment.</span></span> <span data-ttu-id="7833e-112">WMI 使用通用信息模型 (CIM) 行业标准来表示系统、应用程序、网络、设备和其他托管组件。</span><span class="sxs-lookup"><span data-stu-id="7833e-112">WMI uses the Common Information Model (CIM) industry standard to represent systems, applications, networks, devices, and other managed components.</span></span> <span data-ttu-id="7833e-113">CIM 由分布式管理任务组 (DMTF) 进行开发和维护。</span><span class="sxs-lookup"><span data-stu-id="7833e-113">CIM is developed and maintained by the Distributed Management Task Force (DMTF).</span></span> <span data-ttu-id="7833e-114">您可以使用 WMI 来管理本地和远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7833e-114">You can use WMI to manage both local and remote computers.</span></span> <span data-ttu-id="7833e-115">例如，可以使用 WMI 来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7833e-115">For example, you can use WMI to do the following:</span></span>

- <span data-ttu-id="7833e-116">启动远程计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="7833e-116">Start a process on a remote computer.</span></span>
- <span data-ttu-id="7833e-117">远程重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="7833e-117">Restart a computer remotely.</span></span>
- <span data-ttu-id="7833e-118">获取本地或远程计算机上安装的应用程序的列表。</span><span class="sxs-lookup"><span data-stu-id="7833e-118">Get a list of the applications that are installed on a local or remote computer.</span></span>
- <span data-ttu-id="7833e-119">查询本地或远程计算机上的 Windows 事件日志。</span><span class="sxs-lookup"><span data-stu-id="7833e-119">Query the Windows event logs on a local or remote computer.</span></span>

### <a name="the-wmi-cmdlets-for-windows-powershell"></a><span data-ttu-id="7833e-120">适用于 WINDOWS POWERSHELL 的 WMI CMDLET</span><span class="sxs-lookup"><span data-stu-id="7833e-120">THE WMI CMDLETS FOR WINDOWS POWERSHELL</span></span>

<span data-ttu-id="7833e-121">Windows PowerShell 在默认情况下，通过 Windows PowerShell 中提供的一组 cmdlet 来实现 WMI 功能。</span><span class="sxs-lookup"><span data-stu-id="7833e-121">Windows PowerShell implements WMI functionality through a set of cmdlets that are available in Windows PowerShell by default.</span></span> <span data-ttu-id="7833e-122">你可以使用这些 cmdlet 来完成管理本地和远程计算机所需的端到端任务。</span><span class="sxs-lookup"><span data-stu-id="7833e-122">You can use these cmdlets to complete the end-to-end tasks necessary to manage local and remote computers.</span></span>

<span data-ttu-id="7833e-123">包含以下 WMI cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7833e-123">The following WMI cmdlets are included.</span></span>

|<span data-ttu-id="7833e-124">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7833e-124">Cmdlet</span></span>           |<span data-ttu-id="7833e-125">说明</span><span class="sxs-lookup"><span data-stu-id="7833e-125">Description</span></span>                                   |
|-----------------|----------------------------------------------|
|<span data-ttu-id="7833e-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="7833e-126">Get-WmiObject</span></span>    |<span data-ttu-id="7833e-127">获取 WMI 类或信息的实例</span><span class="sxs-lookup"><span data-stu-id="7833e-127">Gets instances of WMI classes or information</span></span>  |
|                 |<span data-ttu-id="7833e-128">关于可用的类。</span><span class="sxs-lookup"><span data-stu-id="7833e-128">about the available classes.</span></span>                  |
|<span data-ttu-id="7833e-129">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="7833e-129">Invoke-WmiMethod</span></span> |<span data-ttu-id="7833e-130">调用 WMI 方法。</span><span class="sxs-lookup"><span data-stu-id="7833e-130">Calls WMI methods.</span></span>                            |
|<span data-ttu-id="7833e-131">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="7833e-131">Register-WmiEvent</span></span>|<span data-ttu-id="7833e-132">订阅 WMI 事件。</span><span class="sxs-lookup"><span data-stu-id="7833e-132">Subscribes to a WMI event.</span></span>                    |
|<span data-ttu-id="7833e-133">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="7833e-133">Remove-WmiObject</span></span> |<span data-ttu-id="7833e-134">删除 WMI 类和实例。</span><span class="sxs-lookup"><span data-stu-id="7833e-134">Deletes WMI classes and instances.</span></span>            |
|<span data-ttu-id="7833e-135">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="7833e-135">Set-WmiInstance</span></span>  |<span data-ttu-id="7833e-136">创建或修改 WMI 类的实例。</span><span class="sxs-lookup"><span data-stu-id="7833e-136">Creates or modifies instances of WMI classes.</span></span> |

### <a name="sample-commands"></a><span data-ttu-id="7833e-137">示例命令</span><span class="sxs-lookup"><span data-stu-id="7833e-137">SAMPLE COMMANDS</span></span>
<span data-ttu-id="7833e-138">以下命令显示本地计算机的 BIOS 信息。</span><span class="sxs-lookup"><span data-stu-id="7833e-138">The following command displays the BIOS information for the local computer.</span></span>

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

<span data-ttu-id="7833e-139">以下命令显示有关三台远程计算机的 WinRM 服务的信息。</span><span class="sxs-lookup"><span data-stu-id="7833e-139">The following command displays information about the WinRM service for three remote computers.</span></span>

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

<span data-ttu-id="7833e-140">下面更复杂的命令退出程序的所有实例。</span><span class="sxs-lookup"><span data-stu-id="7833e-140">The following more complex command exits all instances of a program.</span></span>

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a><span data-ttu-id="7833e-141">基于 WMI 的远程处理</span><span class="sxs-lookup"><span data-stu-id="7833e-141">WMI-BASED REMOTING</span></span>

<span data-ttu-id="7833e-142">尽管通过 WMI 管理本地系统的功能非常有用，但它还是使 WMI 成为一项功能强大的管理工具的远程处理功能。</span><span class="sxs-lookup"><span data-stu-id="7833e-142">While the ability to manage a local system through WMI is useful, it is the remoting capabilities that make WMI a powerful administrative tool.</span></span> <span data-ttu-id="7833e-143">WMI 使用 Microsoft 的分布式组件对象模型 (DCOM) 连接和管理系统。</span><span class="sxs-lookup"><span data-stu-id="7833e-143">WMI uses Microsoft's Distributed Component Object Model (DCOM) to connect to and manage systems.</span></span> <span data-ttu-id="7833e-144">你可能需要将一些系统配置为允许 DCOM 连接。</span><span class="sxs-lookup"><span data-stu-id="7833e-144">You might have to configure some systems to allow DCOM connections.</span></span>
<span data-ttu-id="7833e-145">防火墙设置和锁定 DCOM 权限会阻止 WMI 远程管理系统的能力。</span><span class="sxs-lookup"><span data-stu-id="7833e-145">Firewall settings and locked-down DCOM permissions can block WMI's ability to remotely manage systems.</span></span>

### <a name="wmi-type-accelerators"></a><span data-ttu-id="7833e-146">WMI 类型加速器</span><span class="sxs-lookup"><span data-stu-id="7833e-146">WMI TYPE ACCELERATORS</span></span>

<span data-ttu-id="7833e-147">Windows PowerShell 包括 WMI 类型加速器。</span><span class="sxs-lookup"><span data-stu-id="7833e-147">Windows PowerShell includes WMI type accelerators.</span></span> <span data-ttu-id="7833e-148">这些 WMI 类型加速器 (快捷方式) 允许比非类型加速器方法更好地访问 WMI 对象。</span><span class="sxs-lookup"><span data-stu-id="7833e-148">These WMI type accelerators (shortcuts) allow more direct access to a WMI objects than a non-type accelerator approach would allow.</span></span>

<span data-ttu-id="7833e-149">WMI 支持以下类型加速器：</span><span class="sxs-lookup"><span data-stu-id="7833e-149">The following type accelerators are supported with WMI:</span></span>

<span data-ttu-id="7833e-150">[WMISEARCHER]-搜索 WMI 对象的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7833e-150">[WMISEARCHER] - A shortcut for searching for WMI objects.</span></span>

<span data-ttu-id="7833e-151">[WMICLASS]-访问类的静态属性和方法的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7833e-151">[WMICLASS] - A shortcut for accessing the static properties and methods of a class.</span></span>

<span data-ttu-id="7833e-152">[WMI]-获取类的单个实例的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7833e-152">[WMI] - A shortcut for getting a single instance of a class.</span></span>

<span data-ttu-id="7833e-153">[WMISEARCHER] 是 ManagementObjectSearcher 的类型加速器。</span><span class="sxs-lookup"><span data-stu-id="7833e-153">[WMISEARCHER] is a type accelerator for a ManagementObjectSearcher.</span></span> <span data-ttu-id="7833e-154">它可以使用字符串构造函数创建一个搜索程序，然后在上执行 GET ( # A1。</span><span class="sxs-lookup"><span data-stu-id="7833e-154">It can take a string constructor to create a searcher that you can then do a GET() on.</span></span>

<span data-ttu-id="7833e-155">例如：</span><span class="sxs-lookup"><span data-stu-id="7833e-155">For example:</span></span>

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

<span data-ttu-id="7833e-156">[WMICLASS] 是 ManagementClass 的类型加速器。</span><span class="sxs-lookup"><span data-stu-id="7833e-156">[WMICLASS] is a type accelerator for ManagementClass.</span></span> <span data-ttu-id="7833e-157">这包含一个字符串构造函数，该构造函数采用 WMI 类的本地或绝对 WMI 路径，并返回绑定到该类的对象。</span><span class="sxs-lookup"><span data-stu-id="7833e-157">This has a string constructor that takes a local or absolute WMI path to a WMI class and returns an object that is bound to that class.</span></span>

<span data-ttu-id="7833e-158">例如：</span><span class="sxs-lookup"><span data-stu-id="7833e-158">For example:</span></span>

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

<span data-ttu-id="7833e-159">[WMI] 是 System.management.managementobject 的类型加速器。</span><span class="sxs-lookup"><span data-stu-id="7833e-159">[WMI] is a type accelerator for ManagementObject.</span></span> <span data-ttu-id="7833e-160">这包含一个字符串构造函数，该构造函数采用到 WMI 实例的本地或绝对 WMI 路径，并返回绑定到该实例的对象。</span><span class="sxs-lookup"><span data-stu-id="7833e-160">This has a string constructor that takes a local or absolute WMI path to a WMI instance and returns an object that is bound to that instance.</span></span>

<span data-ttu-id="7833e-161">例如：</span><span class="sxs-lookup"><span data-stu-id="7833e-161">For example:</span></span>

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a><span data-ttu-id="7833e-162">WMI 故障排除</span><span class="sxs-lookup"><span data-stu-id="7833e-162">WMI TROUBLESHOOTING</span></span>

<span data-ttu-id="7833e-163">以下问题是尝试连接到远程计算机时可能出现的最常见问题。</span><span class="sxs-lookup"><span data-stu-id="7833e-163">The following problems are the most common problems that might occur when you try to connect to a remote computer.</span></span>

<span data-ttu-id="7833e-164">问题1：远程计算机未联机。</span><span class="sxs-lookup"><span data-stu-id="7833e-164">Problem 1: The remote computer is not online.</span></span>

<span data-ttu-id="7833e-165">如果计算机处于脱机状态，你将无法使用 WMI 连接到该计算机。</span><span class="sxs-lookup"><span data-stu-id="7833e-165">If a computer is offline, you will not be able to connect to it by using WMI.</span></span>
<span data-ttu-id="7833e-166">可能会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="7833e-166">You may receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

<span data-ttu-id="7833e-167">如果收到此错误消息，请验证计算机是否处于联机状态。</span><span class="sxs-lookup"><span data-stu-id="7833e-167">If you receive this error message, verify that the computer is online.</span></span> <span data-ttu-id="7833e-168">尝试 ping 远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7833e-168">Try to ping the remote computer.</span></span>

<span data-ttu-id="7833e-169">问题2：你没有远程计算机上的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="7833e-169">Problem 2: You do not have local administrator rights on the remote computer.</span></span>

<span data-ttu-id="7833e-170">若要远程使用 WMI，你必须拥有远程计算机上的本地管理员权限。</span><span class="sxs-lookup"><span data-stu-id="7833e-170">To use WMI remotely, you must have local administrator rights on the remote computer.</span></span> <span data-ttu-id="7833e-171">否则，将拒绝对该计算机的访问。</span><span class="sxs-lookup"><span data-stu-id="7833e-171">If you do not, access to that computer will be denied.</span></span>

<span data-ttu-id="7833e-172">验证命名空间安全性：</span><span class="sxs-lookup"><span data-stu-id="7833e-172">To verify namespace security:</span></span>

1. <span data-ttu-id="7833e-173">单击 "开始"，右键单击我的电脑，然后单击 "管理"。</span><span class="sxs-lookup"><span data-stu-id="7833e-173">Click Start, right-click My Computer, and then click Manage.</span></span>
2. <span data-ttu-id="7833e-174">在 "计算机管理" 中，展开 "服务和应用程序"，右键单击 "WMI 控制"，然后单击 "属性"。</span><span class="sxs-lookup"><span data-stu-id="7833e-174">In Computer Management, expand Services and Applications, right-click WMI Control, and then click Properties.</span></span>
3. <span data-ttu-id="7833e-175">在 "WMI 控制属性" 对话框中，单击 "安全" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7833e-175">In the WMI Control Properties dialog box, click  the Security tab.</span></span>

<span data-ttu-id="7833e-176">问题3：防火墙阻止了对远程计算机的访问。</span><span class="sxs-lookup"><span data-stu-id="7833e-176">Problem 3: A firewall is blocking access to the remote computer.</span></span>

<span data-ttu-id="7833e-177">WMI 使用 DCOM (分布式 COM) 和 RPC (远程过程调用) 协议来遍历网络。</span><span class="sxs-lookup"><span data-stu-id="7833e-177">WMI uses the DCOM (Distributed COM) and RPC (Remote Procedure Call) protocols to traverse the network.</span></span> <span data-ttu-id="7833e-178">默认情况下，很多防火墙会阻止 DCOM 和 RPC 通信。</span><span class="sxs-lookup"><span data-stu-id="7833e-178">By default, many firewalls block DCOM and RPC traffic.</span></span> <span data-ttu-id="7833e-179">如果防火墙阻止了这些协议，则连接将失败。</span><span class="sxs-lookup"><span data-stu-id="7833e-179">If your firewall is blocking these protocols, your connection will fail.</span></span> <span data-ttu-id="7833e-180">例如，Microsoft Windows XP Service Pack 2 中的 Windows 防火墙配置为自动阻止所有未经请求的网络通信，包括 DCOM 和 WMI。</span><span class="sxs-lookup"><span data-stu-id="7833e-180">For example, Windows Firewall in Microsoft Windows XP Service Pack 2 is configured to automatically block all unsolicited network traffic, including DCOM and WMI.</span></span> <span data-ttu-id="7833e-181">在默认配置中，Windows 防火墙拒绝传入的 WMI 请求，并收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="7833e-181">In its default configuration, Windows Firewall rejects an incoming WMI request, and you receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a><span data-ttu-id="7833e-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7833e-182">SEE ALSO</span></span>

[<span data-ttu-id="7833e-183">关于 WMI</span><span class="sxs-lookup"><span data-stu-id="7833e-183">About WMI</span></span>](/windows/win32/wmisdk/about-wmi)

[<span data-ttu-id="7833e-184">WMI 故障排除</span><span class="sxs-lookup"><span data-stu-id="7833e-184">WMI Troubleshooting</span></span>](/windows/win32/wmisdk/wmi-troubleshooting)

[<span data-ttu-id="7833e-185">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="7833e-185">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="7833e-186">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="7833e-186">Invoke-WmiMethod</span></span>](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[<span data-ttu-id="7833e-187">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="7833e-187">Register-WmiEvent</span></span>](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[<span data-ttu-id="7833e-188">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="7833e-188">Remove-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[<span data-ttu-id="7833e-189">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="7833e-189">Set-WmiInstance</span></span>](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
