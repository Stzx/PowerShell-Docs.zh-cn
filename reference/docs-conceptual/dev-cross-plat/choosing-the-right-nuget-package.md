---
title: 为 .NET 项目选择正确的 PowerShell NuGet 包
description: PowerShell 团队不仅会维护随每种 PowerShell 版本一起发布的可执行包，还会维护 NuGet 上提供的多个包。 这些包允许将 PowerShell 视为 .NET 中的 API 平台。
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 39369ed872faa76ad2c41d813da5e0a98cf1c078
ms.sourcegitcommit: d0461273abb6db099c5e784ef00f57fd551be4a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "85795255"
---
# <a name="choosing-the-right-powershell-nuget-package-for-your-net-project"></a><span data-ttu-id="7d5f9-104">为 .NET 项目选择正确的 PowerShell NuGet 包</span><span class="sxs-lookup"><span data-stu-id="7d5f9-104">Choosing the right PowerShell NuGet package for your .NET project</span></span>

<span data-ttu-id="7d5f9-105">PowerShell 团队不仅会维护随每种 PowerShell 版本一起发布的 `pwsh` 可执行包，还会维护 [NuGet][] 上提供的多个包。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-105">Alongside the `pwsh` executable packages published with each PowerShell release, the PowerShell team also maintains several packages available on [NuGet][].</span></span> <span data-ttu-id="7d5f9-106">这些包允许将 PowerShell 视为 .NET 中的 API 平台。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-106">These packages allow targeting PowerShell as an API platform in .NET.</span></span>

<span data-ttu-id="7d5f9-107">作为提供 API 并希望加载实现自己的（二进制模块）的 .NET 库的 .NET 应用程序，必须以 NuGet 包的形式提供 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-107">As a .NET application that provides APIs and expects to load .NET libraries implementing its own (binary modules), it's essential that PowerShell be available in the form of a NuGet package.</span></span>

<span data-ttu-id="7d5f9-108">目前，有多个 NuGet 包提供 PowerShell API 外围应用的某种表示形式。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-108">Currently there are several NuGet packages that provide some representation of the PowerShell API surface area.</span></span> <span data-ttu-id="7d5f9-109">特定项目使用哪种包并不总是明确。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-109">Which package to use with a particular project hasn't always been made clear.</span></span> <span data-ttu-id="7d5f9-110">本文介绍了一些面向 PowerShell 的 .NET 项目的常见方案，以及如何为面向 PowerShell 的 .NET 项目选择合适的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-110">This article sheds some light on a few common scenarios for PowerShell-targeting .NET projects and how to choose the right NuGet package to target for your PowerShell-oriented .NET project.</span></span>

## <a name="hosting-vs-referencing"></a><span data-ttu-id="7d5f9-111">托管与引用</span><span class="sxs-lookup"><span data-stu-id="7d5f9-111">Hosting vs referencing</span></span>

<span data-ttu-id="7d5f9-112">一些 .NET 项目设法编写要加载到预先存在的 PowerShell 运行时（例如 `pwsh`、`powershell.exe` 和 PowerShell 集成控制台或 ISE）中的代码，而其他 .NET 项目则希望在自己的应用程序中运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-112">Some .NET projects seek to write code to be loaded into a pre-existing PowerShell runtime (such as `pwsh`, `powershell.exe`, the PowerShell Integrated Console or the ISE), while others want to run PowerShell in their own applications.</span></span>

- <span data-ttu-id="7d5f9-113">引用适用于打算将项目（通常是模块）加载到 PowerShell 中的情况。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-113">**Referencing** is for when a project, usually a module, is intended to be loaded into PowerShell.</span></span>
  <span data-ttu-id="7d5f9-114">必须针对 PowerShell 提供的 API 编译引用编译才能与之交互，但 PowerShell 实现是由将其加载到其中的 PowerShell 进程提供的。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-114">It must be compiled against the APIs that PowerShell provides in order to interact with it, but the PowerShell implementation is supplied by the PowerShell process loading it in.</span></span> <span data-ttu-id="7d5f9-115">若要进行引用，项目可以使用引[用程序集][]或实际运行时程序集作为编译目标，但必须确保项目不会在其构建中发布任何这些程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-115">For referencing, a project can use [reference assemblies][] or the actual runtime assemblies as a compilation target, but must ensure that it does not publish any of these with its build.</span></span>
- <span data-ttu-id="7d5f9-116">托管是指项目需要自己的 PowerShell 实现，通常是因为项目需要运行 PowerShell 的独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-116">**Hosting** is when a project needs its own implementation of PowerShell, usually because it is a standalone application that needs to run PowerShell.</span></span> <span data-ttu-id="7d5f9-117">在这种情况下，不能使用纯引用程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-117">In this case, pure reference assemblies cannot be used.</span></span> <span data-ttu-id="7d5f9-118">而是必须依赖具体的 PowerShell 实现。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-118">Instead, a concrete PowerShell implementation must be depended upon.</span></span> <span data-ttu-id="7d5f9-119">由于必须使用具体的 PowerShell 实现，因此必须选择特定版本的 PowerShell 进行托管；单个主机应用程序不能有多个目标 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-119">Because a concrete PowerShell implementation must be used, a specific version of PowerShell must be chosen for hosting; a single host application cannot multi-target PowerShell versions.</span></span>

### <a name="publishing-projects-that-target-powershell-as-a-reference"></a><span data-ttu-id="7d5f9-120">发布以 PowerShell 作为引用的项目</span><span class="sxs-lookup"><span data-stu-id="7d5f9-120">Publishing projects that target PowerShell as a reference</span></span>

> [!NOTE]
> <span data-ttu-id="7d5f9-121">我们在本文中使用术语“发布”来指代运行 `dotnet publish`，该运行会将 .NET 库放入包含其所有依赖项的目录中，以准备好部署到特定的运行时。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-121">We use the term **publish** in this article to refer to running `dotnet publish`, which places a .NET library into a directory with all of its dependencies, ready for deployment to a particular runtime.</span></span>

<span data-ttu-id="7d5f9-122">为了防止发布仅用作编译引用目标的项目依赖项，建议设置 [PrivateAssets 属性][]：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-122">In order to prevent publishing project dependencies that are just being used as compilation reference targets, it is recommended to set the [PrivateAssets attribute][]:</span></span>

```xml
<PackageReference Include="PowerShellStandard.Library" Version="5.1.0.0" PrivateAssets="all" />
```

<span data-ttu-id="7d5f9-123">如果忘记执行此操作，并将引用程序集用作目标，则可能会出现与使用引用程序集的默认实现（而不是实际实现）相关的问题。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-123">If you forget to do this and use a reference assembly as your target, you may see issues related to using the reference assembly's default implementation instead of the actual implementation.</span></span> <span data-ttu-id="7d5f9-124">这可能采用 `NullReferenceException` 的形式，因为引用程序集通常只需返回 `null` 即可模拟实现 API。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-124">This may take the form of a `NullReferenceException`, since reference assemblies often mock the implementation API by simply returning `null`.</span></span>

## <a name="key-kinds-of-powershell-targeting-net-projects"></a><span data-ttu-id="7d5f9-125">面向 PowerShell 的 .NET 项目的主要类型</span><span class="sxs-lookup"><span data-stu-id="7d5f9-125">Key kinds of PowerShell-targeting .NET projects</span></span>

<span data-ttu-id="7d5f9-126">尽管任何 .NET 库或应用程序都可以嵌入 PowerShell，但某些常见场景下会使用 PowerShell API：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-126">While any .NET library or application can embed PowerShell, there are some common scenarios that use PowerShell APIs:</span></span>

- <span data-ttu-id="7d5f9-127">**实现 PowerShell 二进制模块**</span><span class="sxs-lookup"><span data-stu-id="7d5f9-127">**Implementing a PowerShell binary module**</span></span>

  <span data-ttu-id="7d5f9-128">PowerShell 二进制模块是由 PowerShell 加载的 .NET 库，必须实现 PowerShell API（例如 [PSCmdlet][] 或 [CmdletProvider][] 类型）才能分别公开 cmdlet 或提供程序。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-128">PowerShell binary modules are .NET libraries loaded by PowerShell that must implement PowerShell APIs like the [PSCmdlet][] or [CmdletProvider][] types in order to expose cmdlets or providers respectively.</span></span> <span data-ttu-id="7d5f9-129">由于已加载这些模块，因此模块会设法根据对 PowerShell 的引用进行编译，而不在其生成过程中发布。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-129">Because they are loaded in, modules seek to compile against references to PowerShell without publishing it in their build.</span></span> <span data-ttu-id="7d5f9-130">通常，模块也希望支持多种 PowerShell 版本和平台，最好能够最大限度地减少磁盘空间的开销、复杂性或重复实现。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-130">It's also common for modules to want to support multiple PowerShell versions and platforms, ideally with a minimum of overhead of disk space, complexity, or repeated implementation.</span></span> <span data-ttu-id="7d5f9-131">有关模块的详细信息，请参阅 [about_Modules][]。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-131">See [about_Modules][] for more information about modules.</span></span>

- <span data-ttu-id="7d5f9-132">**实现 PowerShell 主机**</span><span class="sxs-lookup"><span data-stu-id="7d5f9-132">**Implementing a PowerShell Host**</span></span>

  <span data-ttu-id="7d5f9-133">PowerShell 主机为 PowerShell 运行时提供交互层。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-133">A PowerShell Host provides an interaction layer for the PowerShell runtime.</span></span> <span data-ttu-id="7d5f9-134">该交互层是托管的一种特定形式，其中 [PSHost][] 作为 PowerShell 的新用户界面实现。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-134">It is a specific form of _hosting_, where a [PSHost][] is implemented as a new user interface to PowerShell.</span></span> <span data-ttu-id="7d5f9-135">例如，PowerShell ConsoleHost 为 PowerShell 可执行文件提供终端用户界面，而 PowerShell 编辑器服务主机和 ISE 主机均为 PowerShell 提供集成了编辑器的部分图形用户界面。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-135">For example, the PowerShell ConsoleHost provides a terminal user interface for PowerShell executables, while the PowerShell Editor Services Host and the ISE Host both provide an editor-integrated partially graphical user interface around PowerShell.</span></span> <span data-ttu-id="7d5f9-136">虽然可以将主机加载到现有 PowerShell 进程中，但更为常见的是，主机实现充当重新分发 PowerShell 引擎的独立 PowerShell 实现。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-136">While it's possible to load a host onto an existing PowerShell process, it's much more common for a host implementation to act as a standalone PowerShell implementation that redistributes the PowerShell engine.</span></span>

- <span data-ttu-id="7d5f9-137">**从其他 .NET 应用程序调用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7d5f9-137">**Calling into PowerShell from another .NET application**</span></span>

  <span data-ttu-id="7d5f9-138">与任何应用程序一样，PowerShell 可以作为运行工作负载的子进程来进行调用。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-138">As with any application, PowerShell can be called as a subprocess to run workloads.</span></span> <span data-ttu-id="7d5f9-139">但 PowerShell 作为一种 .NET 应用程序，也可以在进程内调用它来获取完整的 .NET 对象，以供在调用应用程序的过程中使用。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-139">However, as a .NET application, it's also possible to invoke PowerShell in-process to get back full .NET objects for use within the calling application.</span></span> <span data-ttu-id="7d5f9-140">这是一种更为常见的托管形式，其中应用程序拥有自己的 PowerShell 实现，供内部使用。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-140">This is a more general form of _hosting_, where the application holds its own PowerShell implementation for internal use.</span></span> <span data-ttu-id="7d5f9-141">此类示例可以是运行 PowerShell 以管理计算机状态的服务或守护程序，也可以是按请求运行 PowerShell 以执行某些操作（例如管理云部署）的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-141">Examples of this might be a service or daemon running PowerShell to manage machine state or a web application that runs PowerShell on request to do something like manage cloud deployments.</span></span>

- <span data-ttu-id="7d5f9-142">**从 .NET 对 PowerShell 模块进行单元测试**</span><span class="sxs-lookup"><span data-stu-id="7d5f9-142">**Unit testing PowerShell modules from .NET**</span></span>

  <span data-ttu-id="7d5f9-143">虽然应主要通过 PowerShell 测试专用于向 PowerShell 公开功能的模块和其他库（建议使用 [Pester][]），但有时需要从 .NET 为 PowerShell 模块编写的 API 进行单元测试。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-143">While modules and other libraries designed to expose functionality to PowerShell should be primarily tested from PowerShell (we recommend [Pester][]), sometimes it's necessary to unit test APIs written for a PowerShell module from .NET.</span></span> <span data-ttu-id="7d5f9-144">这种情况涉及到尝试以多种 PowerShell 版本为目标的模块代码，而测试应在特定的具体实现上运行该代码。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-144">This situation involves the module code trying to target a number of PowerShell versions, while testing should run it on specific, concrete implementations.</span></span>

## <a name="powershell-nuget-packages-at-a-glance"></a><span data-ttu-id="7d5f9-145">PowerShell NuGet 包概述</span><span class="sxs-lookup"><span data-stu-id="7d5f9-145">PowerShell NuGet packages at a glance</span></span>

<span data-ttu-id="7d5f9-146">在本文中，我们将介绍以下可公开 PowerShell API 的 NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-146">In this article, we'll cover the following NuGet packages that expose PowerShell APIs:</span></span>

- <span data-ttu-id="7d5f9-147">[PowerShellStandard.Library][] 是引用程序集，可用于构建一个可由多个 PowerShell 运行时加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-147">[PowerShellStandard.Library][], a reference assembly that enables building a single assembly that can be loaded by multiple PowerShell runtimes.</span></span>
- <span data-ttu-id="7d5f9-148">[Microsoft.PowerShell.SDK][] 用于面向整个 PowerShell SDK 并对其进行重新托管</span><span class="sxs-lookup"><span data-stu-id="7d5f9-148">[Microsoft.PowerShell.SDK][], the way to target and rehost the whole PowerShell SDK</span></span>
- <span data-ttu-id="7d5f9-149">[System.Management.Automation][] 包是核心 PowerShell 运行时和引擎实现，适用于最少的托管实现以及特定于版本的目标设定场景。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-149">The [System.Management.Automation][] package, the core PowerShell runtime and engine implementation, that can be useful in minimal hosted implementations and for version-specific targeting scenarios.</span></span>
- <span data-ttu-id="7d5f9-150">Windows PowerShell 引用程序集用于面向 Windows PowerShell（PowerShell 版本 5.1 及更低版本）并对其进行有效托管。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-150">The **Windows PowerShell reference assemblies**, the way to target and effectively rehost Windows PowerShell (PowerShell versions 5.1 and below).</span></span>

> [!NOTE]
> <span data-ttu-id="7d5f9-151">[PowerShell NuGet][] 包根本不是 .NET 库包，但会提供 PowerShell dotnet 全局工具实现。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-151">The [PowerShell NuGet][] package is not a .NET library package at all, but instead provides the PowerShell dotnet global tool implementation.</span></span> <span data-ttu-id="7d5f9-152">任何项目都不应使用此包，因为它仅提供可执行文件。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-152">This should not be used by any projects, since it only provides an executable.</span></span>

## <a name="powershellstandardlibrary"></a><span data-ttu-id="7d5f9-153">PowerShellStandard.Library</span><span class="sxs-lookup"><span data-stu-id="7d5f9-153">PowerShellStandard.Library</span></span>

<span data-ttu-id="7d5f9-154">PowerShell Standard 库是引用程序集，可捕获 PowerShell 版本 7、6 和 5.1 的 API 的交集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-154">The PowerShell Standard library is a reference assembly that captures the intersection of the APIs of PowerShell versions 7, 6 and 5.1.</span></span> <span data-ttu-id="7d5f9-155">该库提供了经过编译时检查的 API 图面，可以根据其编译 .NET 代码，从而使 .NET 项目可以面向 PowerShell 版本 7、6 和 5.1，而不必冒险调用不存在的 API。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-155">This provides a compile-time-checked API surface to compile .NET code against, allowing .NET projects to target PowerShell versions 7, 6 and 5.1 without risking calling an API that won't be there.</span></span>

<span data-ttu-id="7d5f9-156">PowerShell Standard 用于编写 PowerShell 模块或其他代码（只有将代码加载到 PowerShell 进程后才能运行）。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-156">PowerShell Standard is intended for writing PowerShell modules, or other code only intended to be run after loading it into a PowerShell process.</span></span> <span data-ttu-id="7d5f9-157">由于 PowerShell Standard 是引用程序集，它本身不包含任何实现，因此不为独立应用程序提供任何功能。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-157">Because it is a reference assembly, PowerShell Standard contains no implementation itself, so provides no functionality for standalone applications.</span></span>

### <a name="using-powershell-standard-with-different-net-runtimes"></a><span data-ttu-id="7d5f9-158">将 PowerShell Standard 用于不同的 .NET 运行时</span><span class="sxs-lookup"><span data-stu-id="7d5f9-158">Using PowerShell Standard with different .NET runtimes</span></span>

<span data-ttu-id="7d5f9-159">PowerShell Standard 面向 [.NET Standard 2.0][] 目标运行时，后者是外观运行时，旨在提供 .NET Framework 和 .NET Core 共享的公共外围应用。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-159">PowerShell Standard targets the [.NET Standard 2.0][] target runtime, which is a façade runtime designed to provide a common surface area shared by .NET Framework and .NET Core.</span></span> <span data-ttu-id="7d5f9-160">这样就可以将单个运行时作为目标，以生成可用于多种 PowerShell 版本的单个程序集，但具有以下后果：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-160">This allows targeting a single runtime to produce a single assembly that will work with multiple PowerShell versions, but has the following consequences:</span></span>

- <span data-ttu-id="7d5f9-161">加载模块或库的 PowerShell 必须至少运行 .NET 4.6.1；.NET 4.6 和 .NET 4.5.2 不支持 .NET Standard。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-161">The PowerShell loading the module or library must be running a minimum of .NET 4.6.1; .NET 4.6 and .NET 4.5.2 do not support .NET Standard.</span></span> <span data-ttu-id="7d5f9-162">请注意，Windows PowerShell 版本越新并不意味着 .NET Framework 版本越新。Windows PowerShell 5.1 可在 .NET 4.5.2 上运行。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-162">Note that a newer Windows PowerShell version does not mean a newer .NET Framework version; Windows PowerShell 5.1 may run on .NET 4.5.2.</span></span>
- <span data-ttu-id="7d5f9-163">为使用运行 .NET Framework 4.7.1 或更低版本的 PowerShell，.NET 4.6.1 [NETStandard.Library][] 实现需要在旧版 .NET Framework 中提供 netstandard.dll 和其他填充码程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-163">In order to work with a PowerShell running .NET Framework 4.7.1 or below, the .NET 4.6.1 [NETStandard.Library][] implementation is required to provide the netstandard.dll and other shim assemblies in older .NET Framework versions.</span></span>

<span data-ttu-id="7d5f9-164">PowerShell 6 及更高版本提供自己的填充码程序集，用于从 .NET Framework 4.6.1（及更高版本）到 .NET Core 的类型转发。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-164">PowerShell 6+ provides its own shim assemblies for type forwarding from .NET Framework 4.6.1 (and above) to .NET Core.</span></span> <span data-ttu-id="7d5f9-165">这意味着，只要模块仅使用 .NET Core 中存在的 API，PowerShell 6 及更高版本就可以在为 .NET Framework 4.6.1（`net461` 运行时目标）构建模块时加载并运行该模块。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-165">This means that as long as a module uses only APIs that exist in .NET Core, PowerShell 6+ can load and run it when it has been built for .NET Framework 4.6.1 (the `net461` runtime target).</span></span>

<span data-ttu-id="7d5f9-166">这意味着使用 PowerShell Standard 面向具有单个发布的 DLL 的多种 PowerShell 版本的二进制模块有两个选项：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-166">This means that binary modules using PowerShell Standard to target multiple PowerShell versions with a single published DLL have two options:</span></span>

1. <span data-ttu-id="7d5f9-167">发布为 `net461` 目标运行时构建的程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-167">Publishing an assembly built for the `net461` target runtime.</span></span> <span data-ttu-id="7d5f9-168">这涉及：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-168">This involves:</span></span>
   - <span data-ttu-id="7d5f9-169">为 `net461` 运行时发布项目</span><span class="sxs-lookup"><span data-stu-id="7d5f9-169">Publishing the project for the `net461` runtime</span></span>
   - <span data-ttu-id="7d5f9-170">还要针对 `netstandard2.0` 运行时进行编译（不使用其生成输出），确保所使用的所有 API 也都存在于 .NET Core 中。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-170">Also compiling against the `netstandard2.0` runtime (without using its build output) to ensure that all APIs used are also present in .NET Core.</span></span>

1. <span data-ttu-id="7d5f9-171">发布为 `netstandard2.0` 目标运行时构建的程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-171">Publishing an assembly build for the `netstandard2.0` target runtime.</span></span> <span data-ttu-id="7d5f9-172">这需要：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-172">This requires:</span></span>
   - <span data-ttu-id="7d5f9-173">为 `netstandard2.0` 运行时发布项目</span><span class="sxs-lookup"><span data-stu-id="7d5f9-173">Publishing the project for the `netstandard2.0` runtime</span></span>
   - <span data-ttu-id="7d5f9-174">获取 NETStandard.Library 的 `net461` 依赖项并将其复制到项目程序集的发布位置，以便在 .NET Framework 中对程序集进行正确类型转发。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-174">Taking the `net461` dependencies of NETStandard.Library and copying them into the project assembly's publish location so that the assembly is type-forwarded corrected in .NET Framework.</span></span>

<span data-ttu-id="7d5f9-175">若要构建面向旧版 .NET Framework 的 PowerShell 模块或库，可能面向多个 .NET 运行时更好。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-175">To build PowerShell modules or libraries targeting older .NET Framework versions, it may be preferable to target multiple .NET runtimes.</span></span> <span data-ttu-id="7d5f9-176">这将为每个目标运行时发布一个程序集，并且需要在模块加载时加载合适的程序集（例如，以较小的 psm1 作为根模块）。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-176">This will publish an assembly for each target runtime, and the correct assembly will need to be loaded at module load time (for example with a small psm1 as the root module).</span></span>

### <a name="testing-powershell-standard-projects-in-net"></a><span data-ttu-id="7d5f9-177">在 .NET 中测试 PowerShell Standard 项目</span><span class="sxs-lookup"><span data-stu-id="7d5f9-177">Testing PowerShell Standard projects in .NET</span></span>

<span data-ttu-id="7d5f9-178">在 .NET 测试运行程序（例如 xUnit）中测试模块时，请记住，编译时检查提供的帮助不大。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-178">When it comes to testing your module in .NET test runners like xUnit, remember that compile-time checks can only go so far.</span></span> <span data-ttu-id="7d5f9-179">必须针对相关的 PowerShell 平台测试模块。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-179">You must test your module against the relevant PowerShell platforms.</span></span>

<span data-ttu-id="7d5f9-180">若要测试针对 .NET 中的 PowerShell Standard 构建的 API，你应该向 .NET Core 添加 `Microsoft.Powershell.SDK` 作为（其版本设置为与所需 PowerShell 版本相匹配）测试依赖项，并对 .NET Framework 添加相应的 Windows PowerShell 引用程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-180">To test APIs built against PowerShell Standard in .NET, you should add `Microsoft.Powershell.SDK` as a testing dependency with .NET Core (with the version set to match the desired PowerShell version), and the appropriate Windows PowerShell reference assemblies with .NET Framework.</span></span>

<span data-ttu-id="7d5f9-181">若要详细了解 PowerShell Standard 以及如何将其用于编写可在多种 PowerShell 版本中使用的二进制模块，请参阅[这篇博客文章][]。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-181">For more information on PowerShell Standard and using it to write a binary module that works in multiple PowerShell versions, see [this blog post][].</span></span> <span data-ttu-id="7d5f9-182">另请参阅 GitHub 上的 [PowerShell Standard 存储库][]。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-182">Also see the [PowerShell Standard repository][] on GitHub.</span></span>

## <a name="microsoftpowershellsdk"></a><span data-ttu-id="7d5f9-183">Microsoft.PowerShell.SDK</span><span class="sxs-lookup"><span data-stu-id="7d5f9-183">Microsoft.PowerShell.SDK</span></span>

<span data-ttu-id="7d5f9-184">`Microsoft.PowerShell.SDK` 是一个元包，可将 PowerShell SDK 的所有组件组合到单个 NuGet 包中。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-184">`Microsoft.PowerShell.SDK` is a meta-package that pulls together all of the components of the PowerShell SDK into a single NuGet package.</span></span> <span data-ttu-id="7d5f9-185">独立 .NET 应用程序可以使用 Microsoft.PowerShell.SDK 运行任意 PowerShell 功能，而无需依赖任何外部 PowerShell 安装或库。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-185">A self-contained .NET application can use Microsoft.PowerShell.SDK to run arbitrary PowerShell functionality without depending on any external PowerShell installations or libraries.</span></span>

> [!NOTE]
> <span data-ttu-id="7d5f9-186">PowerShell SDK 仅仅是指构成 PowerShell 的所有组件包，而这些包可用于通过 PowerShell 进行 .NET 开发。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-186">The PowerShell SDK just refers to all the component packages that make up PowerShell, and which can be used for .NET development with PowerShell.</span></span>

<span data-ttu-id="7d5f9-187">给定的 `Microsoft.Powershell.SDK` 版本包含同一版本的 PowerShell 应用程序的具体实现；7.0 版包含 PowerShell 7.0 的实现，并且使用该实现运行命令或脚本的方式主要取决于在 PowerShell 7.0 中运行这些命令或脚本的方式。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-187">A given `Microsoft.Powershell.SDK` version contains the concrete implementation of the same version of the PowerShell application; version 7.0 contains the implementation of PowerShell 7.0 and running commands or scripts with it will largely behave like running them in PowerShell 7.0.</span></span>

<span data-ttu-id="7d5f9-188">从 SDK 运行 PowerShell 命令与从 `pwsh` 运行这些命令大体相同，但不完全相同。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-188">Running PowerShell commands from the SDK is mostly, but not totally, the same as running them from `pwsh`.</span></span> <span data-ttu-id="7d5f9-189">例如，[Start-Job][] 当前取决于可用的 `pwsh` 可执行文件，因此默认情况下不能与 `Microsoft.Powershell.SDK` 一起使用。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-189">For example, [Start-Job][] currently depends on the `pwsh` executable being available, and so will not work with `Microsoft.Powershell.SDK` by default.</span></span>

<span data-ttu-id="7d5f9-190">通过将 .NET 应用程序中的 `Microsoft.Powershell.SDK` 作为目标，你可以与 PowerShell 的所有实现程序集（例如 `System.Management.Automation`、`Microsoft.PowerShell.Management` 和其他模块程序集）集成。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-190">Targeting `Microsoft.Powershell.SDK` from a .NET application allows you to integrate with all of PowerShell's implementation assemblies, such as `System.Management.Automation`, `Microsoft.PowerShell.Management`, and other module assemblies.</span></span>

<span data-ttu-id="7d5f9-191">发布面向 `Microsoft.Powershell.SDK` 的应用程序将包括所有这些程序集，以及 PowerShell 所需的所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-191">Publishing an application targeting `Microsoft.Powershell.SDK` will include all these assemblies, and any dependencies PowerShell requires.</span></span> <span data-ttu-id="7d5f9-192">其中还将包括 PowerShell 在其构建过程中所需的其他资产，例如 `Microsoft.PowerShell.*` 模块的模块清单和 [Add-Type][] 所需的 `ref` 目录。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-192">It will also include other assets that PowerShell required in its build, such as the module manifests for `Microsoft.PowerShell.*` modules and the `ref` directory required by [Add-Type][].</span></span>

<span data-ttu-id="7d5f9-193">鉴于 `Microsoft.Powershell.SDK` 的完整性，它最适用于：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-193">Given the completeness of `Microsoft.Powershell.SDK`, it's best suited for:</span></span>

- <span data-ttu-id="7d5f9-194">PowerShell 主机的实现。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-194">Implementation of PowerShell hosts.</span></span>
- <span data-ttu-id="7d5f9-195">对面向 PowerShell 引用程序集的库进行 xUnit 测试。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-195">xUnit testing of libraries targeting PowerShell reference assemblies.</span></span>
- <span data-ttu-id="7d5f9-196">从 .NET 应用程序在进程内调用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-196">Invoking PowerShell in-process from a .NET application.</span></span>

<span data-ttu-id="7d5f9-197">打算将 .NET 项目用作模块或由 PowerShell 加载时，`Microsoft.PowerShell.SDK` 也可以用作引用目标，但这取决于只有特定版本的 PowerShell 中才存在的 API。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-197">`Microsoft.PowerShell.SDK` may also be used as a reference target when a .NET project is intended to be used as a module or otherwise loaded by PowerShell, but depends on APIs only present in a particular version of PowerShell.</span></span> <span data-ttu-id="7d5f9-198">请注意，针对特定版本的 `Microsoft.PowerShell.SDK` 发布的程序集只能在该版本的 PowerShell 中安全地加载和使用。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-198">Note that an assembly published against a specific version of `Microsoft.PowerShell.SDK` will only be safe to load and use in that version of PowerShell.</span></span> <span data-ttu-id="7d5f9-199">若要面向具有特定 API 的多种 PowerShell 版本，则需要多个构建，每个构建都面向其自己的 `Microsoft.Powershell.SDK` 版本。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-199">To target multiple PowerShell versions with specific APIs, multiple builds are required, each targeting their own version of `Microsoft.Powershell.SDK`.</span></span>

> [!NOTE]
> <span data-ttu-id="7d5f9-200">PowerShell SDK 仅适用于 PowerShell 版本 6 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-200">The PowerShell SDK is only available for PowerShell versions 6 and up.</span></span> <span data-ttu-id="7d5f9-201">若要提供 Windows PowerShell 的等效功能，请使用下面介绍的 Windows PowerShell 引用程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-201">To provide equivalent functionality with Windows PowerShell, use the Windows PowerShell reference assemblies described below.</span></span>

## <a name="systemmanagementautomation"></a><span data-ttu-id="7d5f9-202">System.Management.Automation</span><span class="sxs-lookup"><span data-stu-id="7d5f9-202">System.Management.Automation</span></span>

<span data-ttu-id="7d5f9-203">`System.Management.Automation` 包是 PowerShell SDK 的核心。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-203">The `System.Management.Automation` package is the heart of the PowerShell SDK.</span></span> <span data-ttu-id="7d5f9-204">该包主要位于 NuGet 上，作为供 `Microsoft.Powershell.SDK` 引入的资产。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-204">It exists on NuGet, primarily, as an asset for `Microsoft.Powershell.SDK` to pull in.</span></span> <span data-ttu-id="7d5f9-205">不过，该包也可以直接用作包，用于较小的托管方案和面向版本的模块。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-205">However, it can also be used directly as a package for smaller hosting scenarios and version-targeting modules.</span></span>

<span data-ttu-id="7d5f9-206">具体而言，对于以下情况，`System.Management.Automation` 包可能是 PowerShell 功能的首选提供程序：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-206">Specifically, the `System.Management.Automation` package may be a preferable provider of PowerShell functionality when:</span></span>

- <span data-ttu-id="7d5f9-207">你只希望使用 PowerShell 语言功能（在 `System.Management.Automation.Language` 名称空间中），如 PowerShell 分析程序、AST 和 AST 访问者 API（例如，对 PowerShell 进行静态分析）。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-207">You're only looking to use PowerShell language functionality (in the `System.Management.Automation.Language` namespace) like the PowerShell parser, AST, and AST visitor APIs (for example for static analysis of PowerShell).</span></span>
- <span data-ttu-id="7d5f9-208">你只希望从 `Microsoft.PowerShell.Core` 模块执行特定命令且可在使用 [CreateDefault2][] 工厂方法创建的会话状态下执行这些命令。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-208">You only wish to execute specific commands from the `Microsoft.PowerShell.Core` module and can execute them in a session state created with the [CreateDefault2][] factory method.</span></span>

<span data-ttu-id="7d5f9-209">此外，对于以下情况，`System.Management.Automation` 是有用的引用程序集：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-209">Additionally, `System.Management.Automation` is a useful reference assembly when:</span></span>

- <span data-ttu-id="7d5f9-210">你希望面向只有特定 PowerShell 版本中才存在的 API</span><span class="sxs-lookup"><span data-stu-id="7d5f9-210">You wish to target APIs that are only present within a specific PowerShell version</span></span>
- <span data-ttu-id="7d5f9-211">你不会依赖于 `System.Management.Automation` 程序集之外发生的类型（例如，由 `Microsoft.PowerShell.*` 模块中的 cmdlet 导出的类型）。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-211">You won't be depending on types occurring outside the `System.Management.Automation` assembly (for example, types exported by cmdlets in `Microsoft.PowerShell.*` modules).</span></span>

## <a name="windows-powershell-reference-assemblies"></a><span data-ttu-id="7d5f9-212">Windows PowerShell 引用程序集</span><span class="sxs-lookup"><span data-stu-id="7d5f9-212">Windows PowerShell reference assemblies</span></span>

<span data-ttu-id="7d5f9-213">对于 PowerShell 版本 5.1 及更低版本 (Windows PowerShell)，没有 SDK 可提供 PowerShell 的实现，因为 Windows PowerShell 的实现是 Windows 的一部分。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-213">For PowerShell versions 5.1 and older (Windows PowerShell), there is no SDK to provide an implementation of PowerShell, since Windows PowerShell's implementation is a part of Windows.</span></span>

<span data-ttu-id="7d5f9-214">相反，Windows PowerShell 引用程序集既提供引用目标，又提供一种重新托管 Windows PowerShell 的方式，其行为与 PowerShell SDK 版本 6 及更高版本相同。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-214">Instead, the Windows PowerShell reference assemblies provide both reference targets and a way to rehost Windows PowerShell, acting the same as the PowerShell SDK does for versions 6 and up.</span></span>

<span data-ttu-id="7d5f9-215">Windows PowerShell 引用程序集针对每个版本的 Windows PowerShell 具有不同的包，而不是按版本区分：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-215">Rather than being differentiated by version, Windows PowerShell reference assemblies have a different package for each version of Windows PowerShell:</span></span>

- [<span data-ttu-id="7d5f9-216">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="7d5f9-216">PowerShell 5.1</span></span>](https://www.nuget.org/packages/Microsoft.PowerShell.5.ReferenceAssemblies/)
- [<span data-ttu-id="7d5f9-217">PowerShell 4</span><span class="sxs-lookup"><span data-stu-id="7d5f9-217">PowerShell 4</span></span>](https://www.nuget.org/packages/Microsoft.PowerShell.4.ReferenceAssemblies/)
- [<span data-ttu-id="7d5f9-218">PowerShell 3</span><span class="sxs-lookup"><span data-stu-id="7d5f9-218">PowerShell 3</span></span>](https://www.nuget.org/packages/Microsoft.PowerShell.3.ReferenceAssemblies/)

<span data-ttu-id="7d5f9-219">有关如何使用 Windows PowerShell 引用程序集的信息，请参阅 [Windows PowerShell SDK][]。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-219">Information on how to use the Windows PowerShell reference assemblies can be found in the [Windows PowerShell SDK][].</span></span>

## <a name="real-world-examples-using-these-nuget-packages"></a><span data-ttu-id="7d5f9-220">使用这些 NuGet 包的实际示例</span><span class="sxs-lookup"><span data-stu-id="7d5f9-220">Real-world examples using these NuGet packages</span></span>

<span data-ttu-id="7d5f9-221">根据其需求，不同的 PowerShell 工具项目以不同的 PowerShell NuGet 包为目标。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-221">Different PowerShell tooling projects target different PowerShell NuGet packages depending on their needs.</span></span> <span data-ttu-id="7d5f9-222">下面列出了一些值得注意的示例。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-222">Listed here are some notable examples.</span></span>

### <a name="psreadline"></a><span data-ttu-id="7d5f9-223">PSReadLine</span><span class="sxs-lookup"><span data-stu-id="7d5f9-223">PSReadLine</span></span>

<span data-ttu-id="7d5f9-224">[PSReadLine][] 是提供大部分 PowerShell 丰富控制台经验的 PowerShell 模块，将 PowerShell Standard（而不是特定的 PowerShell 版本）作为依赖项目标，并面向 [csproj][] 中的 `net461` .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-224">[PSReadLine][], the PowerShell module that provides much of PowerShell's rich console experience, targets PowerShell Standard as a dependency rather than a specific PowerShell version, and targets the `net461` .NET runtime in its [csproj][].</span></span>

<span data-ttu-id="7d5f9-225">PowerShell 6 及更高版本提供自己的填充码程序集，这些程序集允许以 `net461` 运行时为目标的 DLL 在加载后“正常工作”（通过将绑定到 .NET Framework 的 `mscorlib.dll` 重定向到相关的 .NET Core 程序集）。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-225">PowerShell 6+ supplies its own shim assemblies that allow a DLL targeting the `net461` runtime to "just work" when loaded in (by redirecting binding to .NET Framework's `mscorlib.dll` to the relevant .NET Core assembly).</span></span>

<span data-ttu-id="7d5f9-226">由于 PowerShell Standard 确保 PowerShell 5.1 和 PowerShell 6 及更高版本中都存在唯一使用过的 API，这大大简化了 PSReadLine 的模块布局和交付，同时还允许该模块仅随单个组件一起提供。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-226">This simplifies PSReadLine's module layout and delivery significantly, since PowerShell Standard ensures the only APIs used will be present in both PowerShell 5.1 and PowerShell 6+, while also allowing the module to ship with only a single assembly.</span></span>

<span data-ttu-id="7d5f9-227">不过，.NET 4.6.1 目标确实表示不支持在 .NET 4.5.2 和 .NET 4.6 上运行的 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-227">The .NET 4.6.1 target does mean that Windows PowerShell running on .NET 4.5.2 and .NET 4.6 is not supported though.</span></span>

### <a name="powershell-editor-services"></a><span data-ttu-id="7d5f9-228">PowerShell 编辑器服务</span><span class="sxs-lookup"><span data-stu-id="7d5f9-228">PowerShell Editor Services</span></span>

<span data-ttu-id="7d5f9-229">[PowerShell 编辑器服务][] (PSES) 是用于 [Visual Studio Code][] 的 [PowerShell 扩展][]的后端，这实际上是 PowerShell 模块的一种形式，该模块由 PowerShell 可执行文件加载，然后接管该过程以在其内部重新托管 PowerShell，同时还提供语言服务协议和调试适配器功能。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-229">[PowerShell Editor Services][] (PSES) is the backend for the [PowerShell extension][] for [Visual Studio Code][], and is actually a form of PowerShell module that gets loaded by a PowerShell executable and then takes over that process to rehost PowerShell within itself while also providing Language Service Protocol and Debug Adapter features.</span></span>

<span data-ttu-id="7d5f9-230">PSES 为 `netcoreapp2.1` 和 `net461` 提供具体的实现目标，以分别面向 PowerShell 6 及更高版本（因为 PowerShell 7 的 `netcoreapp3.1` 运行时后向兼容）和 Windows PowerShell 5.1，但其大部分逻辑包含在面向 `netstandard2.0` 和 PowerShell Standard 的第二个程序集中。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-230">PSES provides concrete implementation targets for `netcoreapp2.1` to target PowerShell 6+ (since PowerShell 7's `netcoreapp3.1` runtime is backwards compatible) and `net461` to target Windows PowerShell 5.1, but contains most of its logic in a second assembly that targets `netstandard2.0` and PowerShell Standard.</span></span> <span data-ttu-id="7d5f9-231">这使 PSES 可以引入 .NET Core 和 .NET Framework 平台所需的依赖项，同时还可简化统一抽象背后的大多数代码库。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-231">This allows it to pull in dependencies required for .NET Core and .NET Framework platforms, while still simplifying most of the codebase behind a uniform abstraction.</span></span>

<span data-ttu-id="7d5f9-232">由于 PSES 针对 PowerShell Standard 而构建，因此需要 PowerShell 的运行时实现才能正确进行测试。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-232">Because it is built against PowerShell Standard, PSES requires a runtime implementation of PowerShell in order to be tested correctly.</span></span> <span data-ttu-id="7d5f9-233">为此，[PSES 的 xUnit][] 测试引入了 `Microsoft.PowerShell.SDK` 和 `Microsoft.PowerShell.5.ReferenceAssemblies`，以便在测试环境中提供 PowerShell 实现。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-233">To do this, [PSES's xUnit][] tests pull in `Microsoft.PowerShell.SDK` and `Microsoft.PowerShell.5.ReferenceAssemblies` in order to provide a PowerShell implementation in the test environment.</span></span>

<span data-ttu-id="7d5f9-234">与 PSReadLine 一样，PSES 不支持 .NET 4.6 及更低版本，但它会先在运行时[执行检查][]，然后调用任何可能在较低的 .NET Framework 运行时导致故障的 API。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-234">As with PSReadLine, PSES cannot support .NET 4.6 and below, but it [performs a check][] at runtime before calling any of the APIs that could cause a crash on the lower .NET Framework runtimes.</span></span>

### <a name="psscriptanalyzer"></a><span data-ttu-id="7d5f9-235">PSScriptAnalyzer</span><span class="sxs-lookup"><span data-stu-id="7d5f9-235">PSScriptAnalyzer</span></span>

<span data-ttu-id="7d5f9-236">[PSScriptAnalyzer][]（用于 PowerShell 的 Linter）必须面向仅在某些版本的 PowerShell 中引入的语法元素。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-236">[PSScriptAnalyzer][], the linter for PowerShell, must target syntactic elements only introduced in certain versions of PowerShell.</span></span> <span data-ttu-id="7d5f9-237">由于对这些语法元素的识别是通过实现 [AstVisitor2][] 来完成的，因此无法使用 PowerShellStandard 并为较新的 PowerShell 语法实现 AST 访问者方法。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-237">Because recognition of these syntactic elements is accomplished by implementing an [AstVisitor2][], it's not possible to use PowerShellStandard and also implement AST visitor methods for newer PowerShell syntaxes.</span></span>

<span data-ttu-id="7d5f9-238">不过，PSScriptAnalyzer 会[将每种 PowerShell 版本][]作为生成配置目标，并为每种版本生成一个单独的 DLL。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-238">Instead, PSScriptAnalyzer [targets each PowerShell version][] as a build configuration, and produces a separate DLL for each of them.</span></span> <span data-ttu-id="7d5f9-239">这增加了构建大小和复杂性，但可实现以下几点：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-239">This increases build size and complexity, but allows:</span></span>

- <span data-ttu-id="7d5f9-240">特定于版本的 API 目标设定</span><span class="sxs-lookup"><span data-stu-id="7d5f9-240">Version-specific API targeting</span></span>
- <span data-ttu-id="7d5f9-241">在实现特定于版本的功能时实际上不花费运行时成本</span><span class="sxs-lookup"><span data-stu-id="7d5f9-241">Version-specific functionality to be implemented with essentially no runtime cost</span></span>
- <span data-ttu-id="7d5f9-242">一直往回追溯到版本 .NET Framework 4.5.2，都提供对 Windows PowerShell 的全面支持</span><span class="sxs-lookup"><span data-stu-id="7d5f9-242">Total support for Windows PowerShell all the way down to .NET Framework 4.5.2</span></span>

## <a name="summary"></a><span data-ttu-id="7d5f9-243">摘要</span><span class="sxs-lookup"><span data-stu-id="7d5f9-243">Summary</span></span>

<span data-ttu-id="7d5f9-244">在本文中，我们列出并讨论了实现使用 PowerShell 的 .NET 项目时可作为目标的 NuGet 包，以及使用某个包而不使用其他包的原因。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-244">In this article, we've listed and discussed the NuGet packages available to target when implementing a .NET project that uses PowerShell, and the reasons you might have for using one over another.</span></span>

<span data-ttu-id="7d5f9-245">如果你跳过了摘要，一些普遍建议是：</span><span class="sxs-lookup"><span data-stu-id="7d5f9-245">If you've skipped to the summary, some broad recommendations are:</span></span>

- <span data-ttu-id="7d5f9-246">如果 PowerShell 模块仅需要不同 PowerShell 版本共用的 API，则应该针对 PowerShell Standard 进行编译。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-246">PowerShell **modules** should compile against PowerShell Standard if they only require APIs common to different PowerShell versions.</span></span>
- <span data-ttu-id="7d5f9-247">需要在内部运行 PowerShell 的 PowerShell 主机和应用程序应面向 PowerShell 6 及更高版本的 PowerShell SDK 或适用于 Windows PowerShell 的相关 Windows PowerShell 引用程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-247">PowerShell **hosts and applications** that need to run PowerShell internally should target the PowerShell SDK for PowerShell 6+ or the relevant Windows PowerShell reference assemblies for Windows PowerShell.</span></span>
- <span data-ttu-id="7d5f9-248">需要版本特定的 API 的 PowerShell 模块应面向 PowerShell SDK 或所需 PowerShell 版本的 Windows PowerShell 引用程序集，并将其用作引用程序集（即不发布 PowerShell 依赖项）。</span><span class="sxs-lookup"><span data-stu-id="7d5f9-248">PowerShell modules that need **version-specific APIs** should target the PowerShell SDK or Windows PowerShell reference assemblies for the required PowerShell versions, using them as reference assemblies (that is, not publishing the PowerShell dependencies).</span></span>

<!--link references -->

[.NET Standard 2.0]: /dotnet/standard/net-standard
[about_Modules]: /powershell/module/microsoft.powershell.core/about/about_modules
[Add-Type]: /powershell/module/microsoft.powershell.utility/add-type
[AstVisitor2]: /dotnet/api/system.management.automation.language.astvisitor2
[CmdletProvider]: /dotnet/api/system.management.automation.provider.cmdletprovider
[CreateDefault2]: /dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2
[csproj]: https://github.com/PowerShell/PSReadLine/blob/master/PSReadLine/PSReadLine.csproj
[Microsoft.PowerShell.SDK]: https://www.nuget.org/packages/Microsoft.PowerShell.SDK/
[NETStandard.Library]: https://www.nuget.org/packages/NETStandard.Library/
[NuGet]: https://www.nuget.org/
[执行检查]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/src/PowerShellEditorServices.Hosting/EditorServicesLoader.cs#L231-L251
[performs a check]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/src/PowerShellEditorServices.Hosting/EditorServicesLoader.cs#L231-L251
[Pester]: https://github.com/Pester/Pester
[PowerShell 编辑器服务]: https://github.com/PowerShell/PowerShellEditorServices/
[PowerShell Editor Services]: https://github.com/PowerShell/PowerShellEditorServices/
[PowerShell 扩展]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[PowerShell extension]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[PowerShell NuGet]: https://www.nuget.org/packages/PowerShell/
[PowerShell Standard 存储库]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard repository]: https://github.com/PowerShell/PowerShellStandard
[PowerShellStandard.Library]: https://www.nuget.org/packages/PowerShellStandard.Library/
[PSCmdlet]: /dotnet/api/system.management.automation.pscmdlet
[PSES 的 xUnit]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/test/PowerShellEditorServices.Test/PowerShellEditorServices.Test.csproj#L15-L20
[PSES's xUnit]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/test/PowerShellEditorServices.Test/PowerShellEditorServices.Test.csproj#L15-L20
[PSHost]: /dotnet/api/system.management.automation.host.pshost
[PrivateAssets 属性]: /dotnet/core/tools/csproj#packagereference
[PrivateAssets attribute]: /dotnet/core/tools/csproj#packagereference
[PSReadLine]: https://github.com/PowerShell/PSReadLine
[PSScriptAnalyzer]: https://github.com/powershell/psscriptanalyzer
[引用程序集]: https://github.com/dotnet/standard/blob/master/docs/history/evolution-of-design-time-assemblies.md#definitions
[reference assemblies]: https://github.com/dotnet/standard/blob/master/docs/history/evolution-of-design-time-assemblies.md#definitions
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[System.Management.Automation]: https://www.nuget.org/packages/System.Management.Automation/
[将每种 PowerShell 版本作为目标]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/Engine/Engine.csproj
[targets each PowerShell version]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/Engine/Engine.csproj
[这篇博客文章]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[this blog post]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[Visual Studio Code]: https://code.visualstudio.com/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell
