---
description: 概述了用于管理的 Web 服务 (WS-MANAGEMENT) 作为使用 Windows PowerShell 中 WS-Management cmdlet 的背景。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WS Management_Cmdlets
ms.openlocfilehash: 4023198edf716ee3102ed2a009b6e2c29ddab73f
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390331"
---
# <a name="about-ws-management-cmdlets"></a><span data-ttu-id="a225d-104">关于 WS-Management Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a225d-104">About WS-Management Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="a225d-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="a225d-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="a225d-106">概述了用于管理的 Web 服务 (WS-MANAGEMENT) 作为使用 Windows PowerShell 中 WS-Management cmdlet 的背景。</span><span class="sxs-lookup"><span data-stu-id="a225d-106">Provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a225d-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="a225d-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="a225d-108">本主题概述了用于管理的 Web 服务 (WS-MANAGEMENT) 作为使用 Windows PowerShell 中 WS-Management cmdlet 的背景。</span><span class="sxs-lookup"><span data-stu-id="a225d-108">This topic provides an overview of Web Services for Management (WS-Management) as background for using the WS-Management cmdlets in Windows PowerShell.</span></span> <span data-ttu-id="a225d-109">本主题还提供了有关 WS-MANAGEMENT 的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="a225d-109">This topic also provides links to more information about WS-Management.</span></span> <span data-ttu-id="a225d-110">WS-Management 的 Microsoft 实现也称为 (WinRM) Windows 远程管理。</span><span class="sxs-lookup"><span data-stu-id="a225d-110">The Microsoft implementation of WS-Management is also known as Windows Remote Management (WinRM).</span></span>

## <a name="about-ws-management"></a><span data-ttu-id="a225d-111">关于 WS-Management</span><span class="sxs-lookup"><span data-stu-id="a225d-111">About WS-Management</span></span>

<span data-ttu-id="a225d-112">Windows 远程管理是 WS-Management 协议的 Microsoft 实现，它是一种基于 SOAP 的标准、防火墙友好的协议，它允许不同供应商的硬件和操作系统互操作。</span><span class="sxs-lookup"><span data-stu-id="a225d-112">Windows Remote Management is the Microsoft implementation of the WS-Management protocol, a standard SOAP-based, firewall-friendly protocol that allows hardware and operating systems from different vendors to interoperate.</span></span> <span data-ttu-id="a225d-113">WS-Management 协议规范为系统提供了一种通用的方法来访问和交换信息技术) 基础结构 (的管理信息。</span><span class="sxs-lookup"><span data-stu-id="a225d-113">The WS-Management protocol specification provides a common way for systems to access and exchange management information across an information technology (IT) infrastructure.</span></span> <span data-ttu-id="a225d-114">WS-Management 和智能平台管理接口 (IPMI) 和事件收集器都是 Windows 硬件管理功能的组成部分。</span><span class="sxs-lookup"><span data-stu-id="a225d-114">WS-Management and Intelligent Platform Management Interface (IPMI), along with the Event Collector, are components of the Windows Hardware Management features.</span></span>

<span data-ttu-id="a225d-115">WS-Management 协议基于以下标准 Web 服务规范： HTTPS、SOAP over HTTP (WS-I profile) 、SOAP 1.2、WS-ADDRESSING、WS 传输、WS 枚举和 WS-EVENTING。</span><span class="sxs-lookup"><span data-stu-id="a225d-115">The WS-Management protocol is based on the following standard Web service specifications: HTTPS, SOAP over HTTP (WS-I profile), SOAP 1.2, WS-Addressing, WS-Transfer, WS-Enumeration, and WS-Eventing.</span></span>

## <a name="ws-management-and-wmi"></a><span data-ttu-id="a225d-116">WS-Management 和 WMI</span><span class="sxs-lookup"><span data-stu-id="a225d-116">WS-Management and WMI</span></span>

<span data-ttu-id="a225d-117">WS-Management 可用于检索由 Windows Management Instrumentation (WMI) 公开的数据。</span><span class="sxs-lookup"><span data-stu-id="a225d-117">WS-Management can be used to retrieve data exposed by Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="a225d-118">可以使用脚本或使用 WS-Management 脚本编写 API 的应用程序或 WinRM 命令行工具获取 WMI 数据。</span><span class="sxs-lookup"><span data-stu-id="a225d-118">You can obtain WMI data with scripts or applications that use the WS-Management Scripting API or through the WinRM command-line tool.</span></span> <span data-ttu-id="a225d-119">WS-Management 支持大多数常见的 WMI 类和操作（包括嵌入对象）。</span><span class="sxs-lookup"><span data-stu-id="a225d-119">WS-Management supports most of the familiar WMI classes and operations, including embedded objects.</span></span> <span data-ttu-id="a225d-120">WS-Management 可以利用 WMI 收集有关资源的数据，或在基于 Windows 的计算机上管理资源。</span><span class="sxs-lookup"><span data-stu-id="a225d-120">WS-Management can leverage WMI to collect data about resources or to manage resources on a Windows-based computers.</span></span> <span data-ttu-id="a225d-121">这意味着你可以通过现有的 WMI 类集来获取有关企业中的磁盘、网络适配器、服务或进程的数据。</span><span class="sxs-lookup"><span data-stu-id="a225d-121">That means that you can obtain data about objects such as disks, network adapters, services, or processes in your enterprise through the existing set of WMI classes.</span></span> <span data-ttu-id="a225d-122">你还可以访问标准 WMI IPMI 提供商提供的硬件数据。</span><span class="sxs-lookup"><span data-stu-id="a225d-122">You can also access the hardware data that is available from the standard WMI IPMI provider.</span></span>

## <a name="ws-management-windows-powershell-provider-wsman"></a><span data-ttu-id="a225d-123">WS-Management Windows PowerShell 提供程序 (WSMan) </span><span class="sxs-lookup"><span data-stu-id="a225d-123">WS-Management Windows PowerShell Provider (WSMan)</span></span>

<span data-ttu-id="a225d-124">WSMan 提供程序为可用 WS-Management 配置设置提供了层次结构视图。</span><span class="sxs-lookup"><span data-stu-id="a225d-124">The WSMan provider provides a hierarchical view into the available WS-Management configuration settings.</span></span> <span data-ttu-id="a225d-125">提供程序允许您浏览和设置不同的 WS-Management 配置选项。</span><span class="sxs-lookup"><span data-stu-id="a225d-125">The provider allows you to explore and set the various WS-Management configuration options.</span></span>

## <a name="ws-management-configuration"></a><span data-ttu-id="a225d-126">WS-Management 配置</span><span class="sxs-lookup"><span data-stu-id="a225d-126">WS-Management Configuration</span></span>

<span data-ttu-id="a225d-127">如果未安装和配置 WS-Management，则无法使用 Windows PowerShell 远程处理，WS-Management cmdlet 将不会运行，WS-Management 脚本不会运行，并且 WSMan 提供程序无法执行数据操作。</span><span class="sxs-lookup"><span data-stu-id="a225d-127">If WS-Management is not installed and configured, Windows PowerShell remoting is not available, the WS-Management cmdlets do not run, WS-Management scripts do not run, and the WSMan provider cannot perform data operations.</span></span> <span data-ttu-id="a225d-128">WS-Management 命令行工具、WinRM 和事件转发也依赖于 WS-Management 配置。</span><span class="sxs-lookup"><span data-stu-id="a225d-128">The WS-Management command-line tool, WinRM, and event forwarding also depend on the WS-Management configuration.</span></span>

## <a name="ws-management-cmdlets"></a><span data-ttu-id="a225d-129">WS-Management Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a225d-129">WS-Management Cmdlets</span></span>

<span data-ttu-id="a225d-130">WS-Management 功能是在 Windows PowerShell 中通过包含一组 cmdlet 和 WSMan 提供程序的模块实现的。</span><span class="sxs-lookup"><span data-stu-id="a225d-130">WS-Management functionality is implemented in Windows PowerShell through a module that contains a set of cmdlets and the WSMan provider.</span></span> <span data-ttu-id="a225d-131">你可以使用这些 cmdlet 来完成管理本地和远程计算机上 WS-Management 设置所需的端到端任务。</span><span class="sxs-lookup"><span data-stu-id="a225d-131">You can use these cmdlets to complete the end-to-end tasks necessary to manage WS-Management settings on local and remote computers.</span></span>

<span data-ttu-id="a225d-132">以下 WS-Management cmdlet 可用。</span><span class="sxs-lookup"><span data-stu-id="a225d-132">The following WS-Management cmdlets are available.</span></span>

## <a name="connection-cmdlets"></a><span data-ttu-id="a225d-133">连接 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a225d-133">Connection Cmdlets</span></span>

- <span data-ttu-id="a225d-134">Connect-WSMan：将本地计算机连接到远程计算机上的 WS-Management (WinRM) 服务。</span><span class="sxs-lookup"><span data-stu-id="a225d-134">Connect-WSMan: Connects the local computer to the WS-Management (WinRM) service on a remote computer.</span></span>

- <span data-ttu-id="a225d-135">断开连接-WSMan：将本地计算机从远程计算机上的 WS-Management (WinRM) 服务断开连接。</span><span class="sxs-lookup"><span data-stu-id="a225d-135">Disconnect-WSMan: Disconnects the local computer from the WS-Management (WinRM) service on a remote computer.</span></span>

## <a name="management-data-cmdlets"></a><span data-ttu-id="a225d-136">Management-Data Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a225d-136">Management-Data Cmdlets</span></span>

- <span data-ttu-id="a225d-137">Get-wsmaninstance：显示由资源 URI 指定的资源实例的管理信息。</span><span class="sxs-lookup"><span data-stu-id="a225d-137">Get-WSManInstance: Displays management information for a resource instance that is specified by a resource URI.</span></span>

- <span data-ttu-id="a225d-138">Invoke-wsmanaction：对由资源 URI 和选择器指定的目标对象调用操作。</span><span class="sxs-lookup"><span data-stu-id="a225d-138">Invoke-WSManAction: Invokes an action on the target object that is specified by the resource URI and by the selectors.</span></span>

- <span data-ttu-id="a225d-139">Get-wsmaninstance：创建新的管理资源实例。</span><span class="sxs-lookup"><span data-stu-id="a225d-139">New-WSManInstance: Creates a new management resource instance.</span></span>

- <span data-ttu-id="a225d-140">Get-wsmaninstance：删除管理资源实例。</span><span class="sxs-lookup"><span data-stu-id="a225d-140">Remove-WSManInstance: Deletes a management resource instance.</span></span>

- <span data-ttu-id="a225d-141">Get-wsmaninstance：修改与资源相关的管理信息。</span><span class="sxs-lookup"><span data-stu-id="a225d-141">Set-WSManInstance: Modifies the management information that is related to a resource.</span></span>

## <a name="setup-and-configuration-cmdlets"></a><span data-ttu-id="a225d-142">安装和配置 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a225d-142">Setup and Configuration Cmdlets</span></span>

- <span data-ttu-id="a225d-143">Set-wsmanquickconfig：配置本地计算机以进行远程管理。</span><span class="sxs-lookup"><span data-stu-id="a225d-143">Set-WSManQuickConfig: Configures the local computer for remote management.</span></span>
  <span data-ttu-id="a225d-144">你可以使用 Set-WSManQuickConfig cmdlet 配置 WS-Management，以允许 WS-Management (WinRM) 服务的远程连接。</span><span class="sxs-lookup"><span data-stu-id="a225d-144">You can use the Set-WSManQuickConfig cmdlet to configure WS-Management to allow remote connections to the WS-Management (WinRM) service.</span></span> <span data-ttu-id="a225d-145">Set-WSManQuickConfig cmdlet 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a225d-145">The Set-WSManQuickConfig cmdlet performs the following operations:</span></span>
  - <span data-ttu-id="a225d-146">它确定 WS-Management (WinRM) 服务是否正在运行。</span><span class="sxs-lookup"><span data-stu-id="a225d-146">It determines whether the WS-Management (WinRM) service is running.</span></span> <span data-ttu-id="a225d-147">如果 WinRM 服务未运行，则 Set-WSManQuickConfig cmdlet 将启动该服务。</span><span class="sxs-lookup"><span data-stu-id="a225d-147">If the WinRM service is not running, the Set-WSManQuickConfig cmdlet starts the service.</span></span>
  - <span data-ttu-id="a225d-148">它将 WS-Management (WinRM) 服务启动类型设置为 "自动"。</span><span class="sxs-lookup"><span data-stu-id="a225d-148">It sets the WS-Management (WinRM) service startup type to automatic.</span></span>
  - <span data-ttu-id="a225d-149">它将创建接受来自任何 IP 地址的请求的侦听器。</span><span class="sxs-lookup"><span data-stu-id="a225d-149">It creates a listener that accepts requests from any IP address.</span></span> <span data-ttu-id="a225d-150">默认传输协议为 HTTP。</span><span class="sxs-lookup"><span data-stu-id="a225d-150">The default transport protocol is HTTP.</span></span>
  - <span data-ttu-id="a225d-151">它为 WS-Management 流量启用防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="a225d-151">It enables a firewall exception for WS-Management traffic.</span></span>

  <span data-ttu-id="a225d-152">注意：若要在 Windows Vista、Windows Server 2008 和更高版本的 Windows 中运行此 cmdlet，必须用 "以管理员身份运行" 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a225d-152">Note: To run this cmdlet in Windows Vista, Windows Server 2008, and later versions of Windows, you must start Windows PowerShell with the "Run as administrator" option.</span></span>

- <span data-ttu-id="a225d-153">测试-WSMan：验证是否安装并配置了 WS-Management。</span><span class="sxs-lookup"><span data-stu-id="a225d-153">Test-WSMan: Verifies that WS-Management is installed and configured.</span></span> <span data-ttu-id="a225d-154">Test-WSMan cmdlet 测试 WS-Management (WinRM) 服务是否正在本地或远程计算机上运行和配置。</span><span class="sxs-lookup"><span data-stu-id="a225d-154">The Test-WSMan cmdlet tests whether the WS-Management (WinRM) service is running and configured on a local or remote computer.</span></span>

- <span data-ttu-id="a225d-155">Enable-wsmancredssp：禁用客户端计算机上的 CredSSP 身份验证。</span><span class="sxs-lookup"><span data-stu-id="a225d-155">Disable-WSManCredSSP: Disables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="a225d-156">Enable-wsmancredssp：在客户端计算机上启用 CredSSP 身份验证。</span><span class="sxs-lookup"><span data-stu-id="a225d-156">Enable-WSManCredSSP: Enables CredSSP authentication on a client computer.</span></span>

- <span data-ttu-id="a225d-157">Enable-wsmancredssp：获取客户端计算机的 CredSSP 相关配置。</span><span class="sxs-lookup"><span data-stu-id="a225d-157">Get-WSManCredSSP: Gets the CredSSP-related configuration for a client computer.</span></span>

## <a name="ws-management-specific-cmdlets"></a><span data-ttu-id="a225d-158">WS-MANAGEMENT 特定的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a225d-158">WS-Management-Specific Cmdlets</span></span>

- <span data-ttu-id="a225d-159">New-wsmansessionoption：创建 New-wsmansessionoption 对象，该对象用作 WS-Management cmdlet 的一个或多个参数的输入。</span><span class="sxs-lookup"><span data-stu-id="a225d-159">New-WSManSessionOption: Creates a WSManSessionOption object to use as input to one or more parameters of a WS-Management cmdlet.</span></span>

## <a name="additional-ws-management-information"></a><span data-ttu-id="a225d-160">其他 WS-Management 信息</span><span class="sxs-lookup"><span data-stu-id="a225d-160">Additional WS-Management Information</span></span>

<span data-ttu-id="a225d-161">有关 WS-MANAGEMENT 的详细信息，请参阅 Windows 文档中的以下主题。</span><span class="sxs-lookup"><span data-stu-id="a225d-161">For more information about WS-Management, see the following topics in the Windows documentation.</span></span>

[<span data-ttu-id="a225d-162">Windows 远程管理</span><span class="sxs-lookup"><span data-stu-id="a225d-162">Windows Remote Management</span></span>](/windows/win32/winrm/portal)

[<span data-ttu-id="a225d-163">关于 Windows 远程管理</span><span class="sxs-lookup"><span data-stu-id="a225d-163">About Windows Remote Management</span></span>](/windows/win32/winrm/about-windows-remote-management)

[<span data-ttu-id="a225d-164">Windows 远程管理的安装和配置</span><span class="sxs-lookup"><span data-stu-id="a225d-164">Installation and Configuration for Windows Remote Management</span></span>](/windows/win32/winrm/installation-and-configuration-for-windows-remote-management)

[<span data-ttu-id="a225d-165">Windows 远程管理体系结构</span><span class="sxs-lookup"><span data-stu-id="a225d-165">Windows Remote Management Architecture</span></span>](/windows/win32/winrm/windows-remote-management-architecture)

[<span data-ttu-id="a225d-166">WS-Management 协议</span><span class="sxs-lookup"><span data-stu-id="a225d-166">WS-Management Protocol</span></span>](/windows/win32/winrm/ws-management-protocol)

[<span data-ttu-id="a225d-167">Windows 远程管理和 WMI</span><span class="sxs-lookup"><span data-stu-id="a225d-167">Windows Remote Management and WMI</span></span>](/windows/win32/winrm/windows-remote-management-and-wmi)

[<span data-ttu-id="a225d-168">资源 URI</span><span class="sxs-lookup"><span data-stu-id="a225d-168">Resource URIs</span></span>](/windows/win32/winrm/resource-uris)

[<span data-ttu-id="a225d-169">远程硬件管理</span><span class="sxs-lookup"><span data-stu-id="a225d-169">Remote Hardware Management</span></span>](/windows/win32/winrm/remote-hardware-management)

[<span data-ttu-id="a225d-170">事件</span><span class="sxs-lookup"><span data-stu-id="a225d-170">Events</span></span>](/windows/win32/winrm/events)

## <a name="see-also"></a><span data-ttu-id="a225d-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a225d-171">SEE ALSO</span></span>

[<span data-ttu-id="a225d-172">Connect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a225d-172">Connect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Connect-WSMan)

[<span data-ttu-id="a225d-173">Disable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a225d-173">Disable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Disable-WSManCredSSP)

[<span data-ttu-id="a225d-174">Disconnect-WSMan</span><span class="sxs-lookup"><span data-stu-id="a225d-174">Disconnect-WSMan</span></span>](xref:Microsoft.WSMan.Management.Disconnect-WSMan)

[<span data-ttu-id="a225d-175">Enable-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a225d-175">Enable-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Enable-WSManCredSSP)

[<span data-ttu-id="a225d-176">Get-WSManCredSSP</span><span class="sxs-lookup"><span data-stu-id="a225d-176">Get-WSManCredSSP</span></span>](xref:Microsoft.WSMan.Management.Get-WSManCredSSP)

[<span data-ttu-id="a225d-177">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a225d-177">Get-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Get-WSManInstance)

[<span data-ttu-id="a225d-178">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="a225d-178">Invoke-WSManAction</span></span>](xref:Microsoft.WSMan.Management.Invoke-WSManAction)

[<span data-ttu-id="a225d-179">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a225d-179">New-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.New-WSManInstance)

[<span data-ttu-id="a225d-180">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a225d-180">Remove-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Remove-WSManInstance)

[<span data-ttu-id="a225d-181">Set-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="a225d-181">Set-WSManInstance</span></span>](xref:Microsoft.WSMan.Management.Set-WSManInstance)

[<span data-ttu-id="a225d-182">Set-WSManQuickConfig</span><span class="sxs-lookup"><span data-stu-id="a225d-182">Set-WSManQuickConfig</span></span>](xref:Microsoft.WSMan.Management.Set-WSManQuickConfig)

[<span data-ttu-id="a225d-183">Test-WSMan</span><span class="sxs-lookup"><span data-stu-id="a225d-183">Test-WSMan</span></span>](xref:Microsoft.WSMan.Management.Test-WSMan)
