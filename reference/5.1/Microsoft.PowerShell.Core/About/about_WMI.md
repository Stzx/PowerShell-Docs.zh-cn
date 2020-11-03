---
description: " (WMI) Windows Management Instrumentation 使用 (通用信息模型来表示新式企业的系统、应用程序、网络、设备和其他可管理组件。"
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI
ms.openlocfilehash: d24b952ee167e51815d6d9920e95bbc9a6bb9608
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200232"
---
# <a name="about-wmi"></a><span data-ttu-id="7801b-104">关于 WMI</span><span class="sxs-lookup"><span data-stu-id="7801b-104">About WMI</span></span>

## <a name="short-description"></a><span data-ttu-id="7801b-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="7801b-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="7801b-106"> (WMI) Windows Management Instrumentation 使用 (通用信息模型来表示新式企业的系统、应用程序、网络、设备和其他可管理组件。</span><span class="sxs-lookup"><span data-stu-id="7801b-106">Windows Management Instrumentation (WMI) uses the Common Information Model (CIM) to represent systems, applications, networks, devices, and other manageable components of the modern enterprise.</span></span>

## <a name="long-description"></a><span data-ttu-id="7801b-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="7801b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7801b-108">Windows Management Instrumentation (WMI) 是 Microsoft 实现的 Web-Based 企业管理 (WBEM) ，这是行业标准。</span><span class="sxs-lookup"><span data-stu-id="7801b-108">Windows Management Instrumentation (WMI) is Microsoft's implementation of Web-Based Enterprise Management (WBEM), the industry standard.</span></span>

<span data-ttu-id="7801b-109">经典 WMI 使用 DCOM 与网络设备通信，以管理远程系统。</span><span class="sxs-lookup"><span data-stu-id="7801b-109">Classic WMI uses DCOM to communicate with networked devices to manage remote systems.</span></span> <span data-ttu-id="7801b-110">Windows PowerShell 3.0 引入了一个 CIM 提供程序模型，该模型使用 WinRM 删除对 DCOM 的依赖项。</span><span class="sxs-lookup"><span data-stu-id="7801b-110">Windows PowerShell 3.0 introduces a CIM provider model that uses WinRM to remove the dependency on DCOM.</span></span> <span data-ttu-id="7801b-111">此 CIM 提供程序模型还使用新的 WMI 提供程序 Api，使开发人员能够在本机代码 (C) 中编写 Windows PowerShell cmdlet \+ \+ 。</span><span class="sxs-lookup"><span data-stu-id="7801b-111">This CIM provider model also uses new WMI provider APIs that enable developers to write Windows PowerShell cmdlets in native code (C\+\+).</span></span>

<span data-ttu-id="7801b-112">不要将 WMI 提供程序与 Windows PowerShell 提供程序混淆。</span><span class="sxs-lookup"><span data-stu-id="7801b-112">Do not confuse WMI providers with Windows PowerShell providers.</span></span> <span data-ttu-id="7801b-113">许多 Windows 功能都有一个关联的 WMI 提供程序，该提供程序公开其管理功能。</span><span class="sxs-lookup"><span data-stu-id="7801b-113">Many Windows features have an associated WMI provider that exposes their management capabilities.</span></span> <span data-ttu-id="7801b-114">若要获取 WMI 提供程序，请运行 WMI 查询以获取 __Provider WMI 类的实例，例如以下查询。</span><span class="sxs-lookup"><span data-stu-id="7801b-114">To get WMI providers, run a WMI query that gets instances of the __Provider WMI class, such as the following query.</span></span>

```powershell
Get-WmiObject -Class __Provider
```

## <a name="three-components-of-wmi"></a><span data-ttu-id="7801b-115">WMI 的三个组件</span><span class="sxs-lookup"><span data-stu-id="7801b-115">THREE COMPONENTS OF WMI</span></span>

<span data-ttu-id="7801b-116">以下三个 WMI 组件与 Windows PowerShell 交互：命名空间、提供程序和类。</span><span class="sxs-lookup"><span data-stu-id="7801b-116">The following three components of WMI interact with Windows PowerShell: Namespaces, Providers, and Classes.</span></span>

<span data-ttu-id="7801b-117">WMI 命名空间将 WMI 提供程序和 WMI 类组织到相关组件组中。</span><span class="sxs-lookup"><span data-stu-id="7801b-117">WMI Namespaces organize WMI providers and WMI classes into groups of related components.</span></span> <span data-ttu-id="7801b-118">通过这种方式，它们类似于 .NET Framework 命名空间。</span><span class="sxs-lookup"><span data-stu-id="7801b-118">In this way, they are similar to .NET Framework namespaces.</span></span>
<span data-ttu-id="7801b-119">命名空间不是物理位置，但更像是逻辑数据库。</span><span class="sxs-lookup"><span data-stu-id="7801b-119">Namespaces are not physical locations, but are more like logical databases.</span></span>
<span data-ttu-id="7801b-120">所有 WMI 命名空间都是 __Namespace 系统类的实例。</span><span class="sxs-lookup"><span data-stu-id="7801b-120">All WMI namespaces are instances of the __Namespace system class.</span></span> <span data-ttu-id="7801b-121">由于 Microsoft Windows 2000) ，默认 WMI 命名空间为根 \/ CIMV2 (。</span><span class="sxs-lookup"><span data-stu-id="7801b-121">The default WMI namespace is Root\/CIMV2 (since Microsoft Windows 2000).</span></span> <span data-ttu-id="7801b-122">若要使用 Windows PowerShell 来获取当前会话中的 WMI 命名空间，请使用具有以下格式的命令。</span><span class="sxs-lookup"><span data-stu-id="7801b-122">To use Windows PowerShell to get WMI namespaces in the current session, use a command with the following format.</span></span>

```powershell
Get-WmiObject -Class __Namespace
```

<span data-ttu-id="7801b-123">若要获取其他命名空间中的 WMI 命名空间，请使用 Namespace 参数更改搜索的位置。</span><span class="sxs-lookup"><span data-stu-id="7801b-123">To get WMI namespaces in other namespaces, use the Namespace parameter to change the location of the search.</span></span> <span data-ttu-id="7801b-124">以下命令查找位于 Root/Cimv2/Applications 命名空间中的 WMI 命名空间。</span><span class="sxs-lookup"><span data-stu-id="7801b-124">The following command finds WMI namespaces that reside in the Root/Cimv2/Applications namespace.</span></span>

```powershell
Get-WmiObject -Class __Namespace -Namespace root/CIMv2/applications
```

<span data-ttu-id="7801b-125">WMI 命名空间是分层的。</span><span class="sxs-lookup"><span data-stu-id="7801b-125">WMI namespaces are hierarchical.</span></span> <span data-ttu-id="7801b-126">因此，若要获取特定系统上所有命名空间的列表，需要执行从根命名空间开始的递归查询。</span><span class="sxs-lookup"><span data-stu-id="7801b-126">Therefore, obtaining a list of all namespaces on a particular system requires performing a recursive query starting at the root namespace.</span></span>

<span data-ttu-id="7801b-127">WMI 提供程序公开有关 Windows 可管理对象的信息。</span><span class="sxs-lookup"><span data-stu-id="7801b-127">WMI Providers expose information about Windows manageable objects.</span></span> <span data-ttu-id="7801b-128">提供程序从组件中检索数据，并通过 WMI 将该数据传递到管理应用程序，如 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7801b-128">A provider retrieves data from a component, and passes that data through WMI to a management application, such as Windows PowerShell.</span></span> <span data-ttu-id="7801b-129">大多数 WMI 提供程序是动态提供程序，这意味着当通过管理应用程序请求数据时，它们会动态地获取数据。</span><span class="sxs-lookup"><span data-stu-id="7801b-129">Most WMI providers are dynamic providers, which means that they obtain the data dynamically when it is requested through the management application.</span></span>

## <a name="finding-wmi-classes"></a><span data-ttu-id="7801b-130">查找 WMI 类</span><span class="sxs-lookup"><span data-stu-id="7801b-130">FINDING WMI CLASSES</span></span>

<span data-ttu-id="7801b-131">在 Windows 8 的默认安装中，根 Cimv2 中的 WMI 类超过1100个 \/ 。</span><span class="sxs-lookup"><span data-stu-id="7801b-131">In a default installation of Windows 8, there are more than 1,100 WMI classes in Root\/Cimv2.</span></span> <span data-ttu-id="7801b-132">使用此类 WMI 类，质询将会确定要用于执行特定任务的相应 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="7801b-132">With this many WMI classes, the challenge becomes identifying the appropriate WMI class to use to perform a specific task.</span></span> <span data-ttu-id="7801b-133">Windows PowerShell 3.0 提供了两种方法来查找与特定主题相关的 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="7801b-133">Windows PowerShell 3.0 provides two ways to find WMI classes that are related to a specific topic.</span></span>

<span data-ttu-id="7801b-134">例如，若要查找 \\ 与磁盘相关的根 CIMV2 wmi 命名空间中的 WMI 类，可以使用如下所示的查询。</span><span class="sxs-lookup"><span data-stu-id="7801b-134">For example,to find WMI classes in the root\\CIMV2 WMI namespace that are related to disks, you can use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *disk*
```

<span data-ttu-id="7801b-135">若要查找与内存相关的 WMI 类，可以使用如下所示的查询。</span><span class="sxs-lookup"><span data-stu-id="7801b-135">To find WMI classes that are related to memory, you might use a query such as the one shown here.</span></span>

```powershell
Get-WmiObject -List *memory*
```

<span data-ttu-id="7801b-136">CIM cmdlet 还提供了发现 WMI 类的功能。</span><span class="sxs-lookup"><span data-stu-id="7801b-136">The CIM cmdlets also provide the ability to discover WMI classes.</span></span> <span data-ttu-id="7801b-137">为此，请使用 Get-CIMClass cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7801b-137">To do this, use the Get-CIMClass cmdlet.</span></span> <span data-ttu-id="7801b-138">此处显示的命令列出了与视频相关的 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="7801b-138">The command shown here lists WMI classes related to video.</span></span>

```powershell
Get-CimClass *video*
```

<span data-ttu-id="7801b-139">选项卡扩展适用于更改 WMI 命名空间，因此使用选项卡扩展使子 WMI 命名空间易于发现。</span><span class="sxs-lookup"><span data-stu-id="7801b-139">Tab expansion works when changing WMI namespaces, and therefore use of tab expansion makes sub-WMI namespaces easily discoverable.</span></span> <span data-ttu-id="7801b-140">在下面的示例中，Get-CimClass cmdlet 列出了与电源设置相关的 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="7801b-140">In the following example, the Get-CimClass cmdlet lists WMI classes related to power settings.</span></span>
<span data-ttu-id="7801b-141">若要找到该命名空间，请键入 `root/CIMV2/` 命名空间，然后按若干次 tab 键，直到出现 power 命名空间。</span><span class="sxs-lookup"><span data-stu-id="7801b-141">To find it, type the `root/CIMV2/` namespace and then press the Tab key several times until the power namespace appears.</span></span> <span data-ttu-id="7801b-142">命令如下：</span><span class="sxs-lookup"><span data-stu-id="7801b-142">Here is the command:</span></span>

```powershell
Get-CimClass *power* -Namespace root/cimv2/power
```
