---
title: 解决 PowerShell 模块程序集依赖项冲突
description: 在采用 C# 编写二进制 PowerShell 模块时，自然会通过其他包或库的依赖项来提供功能。
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 93bb39bdd440c7f97c27aa81e68f68331569b69e
ms.sourcegitcommit: 2fc6ee49a70bda4c59135136bd5cc7782836a124
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "94810396"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a><span data-ttu-id="a796f-103">解决 PowerShell 模块程序集依赖项冲突</span><span class="sxs-lookup"><span data-stu-id="a796f-103">Resolving PowerShell module assembly dependency conflicts</span></span>

<span data-ttu-id="a796f-104">在采用 C# 编写二进制 PowerShell 模块时，自然会通过其他包或库的依赖项来提供功能。</span><span class="sxs-lookup"><span data-stu-id="a796f-104">When writing a binary PowerShell module in C#, it's natural to take dependencies on other packages or libraries to provide functionality.</span></span> <span data-ttu-id="a796f-105">需要依赖其他库以重用代码。</span><span class="sxs-lookup"><span data-stu-id="a796f-105">Taking dependencies on other libraries is desirable for code reuse.</span></span> <span data-ttu-id="a796f-106">PowerShell 始终将程序集加载到相同的上下文中。</span><span class="sxs-lookup"><span data-stu-id="a796f-106">PowerShell always loads assemblies into the same context.</span></span> <span data-ttu-id="a796f-107">如果模块的依赖项与已加载的 DLL 冲突，则会出现问题，并且可能会阻止在同一 PowerShell 会话中使用其他两个不相关的模块。</span><span class="sxs-lookup"><span data-stu-id="a796f-107">This presents issues when a module's dependencies conflict with already-loaded DLLs and may prevent using two otherwise unrelated modules in the same PowerShell session.</span></span>

<span data-ttu-id="a796f-108">如果你遇到过这种问题，就一定见过如下错误消息：</span><span class="sxs-lookup"><span data-stu-id="a796f-108">If you've had this problem, you've seen an error message like this:</span></span>

![程序集加载冲突错误消息](./media/resolving-dependency-conflicts/moduleconflict.png)

<span data-ttu-id="a796f-110">本文介绍 PowerShell 中发生依赖项冲突的一些方式以及缓解依赖项冲突问题的方法。</span><span class="sxs-lookup"><span data-stu-id="a796f-110">This article looks at some of the ways dependency conflicts occur in PowerShell and ways to mitigate dependency conflict issues.</span></span> <span data-ttu-id="a796f-111">即使你不是模块创建者，这里也有一些技巧可以帮助应对所使用的模块中发生的依赖项冲突。</span><span class="sxs-lookup"><span data-stu-id="a796f-111">Even if you're not a module author, there are some tricks in here that might help you with dependency conflicts occurring in modules that you use.</span></span>

## <a name="why-do-dependency-conflicts-occur"></a><span data-ttu-id="a796f-112">为什么会发生依赖项冲突？</span><span class="sxs-lookup"><span data-stu-id="a796f-112">Why do dependency conflicts occur?</span></span>

<span data-ttu-id="a796f-113">在 .NET 中，当将同一程序集的两个版本加载到同一程序集加载上下文中时，将发生依赖项冲突。</span><span class="sxs-lookup"><span data-stu-id="a796f-113">In .NET, dependency conflicts occur when two versions of the same assembly are loaded into the same _Assembly Load Context_.</span></span> <span data-ttu-id="a796f-114">这一术语在不同 .NET 平台上的含义略有不同，[稍后](#powershell-and-net)将进行介绍。</span><span class="sxs-lookup"><span data-stu-id="a796f-114">This term means slightly different things on different .NET platforms, which is covered [later](#powershell-and-net).</span></span> <span data-ttu-id="a796f-115">此冲突是一个常见的问题，使用版本控制依赖项的任何软件都会出现这种冲突。</span><span class="sxs-lookup"><span data-stu-id="a796f-115">This conflict is a common problem that occurs in any software where versioned dependencies are used.</span></span> <span data-ttu-id="a796f-116">由于没有简单的解决方案，并且许多依赖项解决方案框架都尝试以不同的方式解决此问题，因此这种情况通常称为“依赖项地狱”。</span><span class="sxs-lookup"><span data-stu-id="a796f-116">Because there are no simple solutions, and because many dependency-resolution frameworks try to solve the problem in different ways, this situation is often called "dependency hell".</span></span>

<span data-ttu-id="a796f-117">一个项目几乎不会有意或直接依赖于同一依赖项的两个版本，这一事实使冲突问题更加复杂。</span><span class="sxs-lookup"><span data-stu-id="a796f-117">Conflict issues are compounded by the fact that a project almost never deliberately or directly depends on two versions of the same dependency.</span></span> <span data-ttu-id="a796f-118">相反，如果项目具有两个或多个依赖项，则每个依赖项都需要同一依赖项的不同版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-118">Instead, the project has two or more dependencies that each require a different version of the same dependency.</span></span>

<span data-ttu-id="a796f-119">例如，假设 .NET 应用程序 `DuckBuilder` 引入了两个依赖项来执行其部分功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-119">For example, say your .NET application, `DuckBuilder`, brings in two dependencies, to perform parts of its functionality and looks like this:</span></span>

![DuckBuilder 的两个依赖项依赖于 Newtonsoft.json 的不同版本](./media/resolving-dependency-conflicts/dep-conflict.jpg)

<span data-ttu-id="a796f-121">由于 `Contoso.ZipTools` 和 `Fabrikam.FileHelpers` 都依赖于 `Newtonsoft.Json` 的不同版本，因此可能存在依赖项冲突，具体取决于每个依赖项的加载方式。</span><span class="sxs-lookup"><span data-stu-id="a796f-121">Because `Contoso.ZipTools` and `Fabrikam.FileHelpers` both depend on different versions of `Newtonsoft.Json`, there may be a dependency conflict depending on how each dependency is loaded.</span></span>

### <a name="conflicting-with-powershells-dependencies"></a><span data-ttu-id="a796f-122">与 PowerShell 的依赖项冲突</span><span class="sxs-lookup"><span data-stu-id="a796f-122">Conflicting with PowerShell's dependencies</span></span>

<span data-ttu-id="a796f-123">在 PowerShell 中，由于 PowerShell 模块和 PowerShell 自己的依赖项加载到同一共享上下文中，因此依赖项冲突问题会被放大。</span><span class="sxs-lookup"><span data-stu-id="a796f-123">In PowerShell, the dependency conflict issue is magnified because PowerShell modules and PowerShell's own dependencies are loaded into the same shared context.</span></span> <span data-ttu-id="a796f-124">这意味着 PowerShell 引擎和所有已加载的 PowerShell 模块不能有产生冲突的依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-124">This means the PowerShell engine and all loaded PowerShell modules must not have conflicting dependencies.</span></span> <span data-ttu-id="a796f-125">一个典型示例是 `Newtonsoft.Json`：</span><span class="sxs-lookup"><span data-stu-id="a796f-125">A classic example of this is `Newtonsoft.Json`:</span></span>

![相较于 PowerShell，FictionalTools 模块所依赖的 Newtonsoft.json 版本较新](./media/resolving-dependency-conflicts/engine-conflict.jpg)

<span data-ttu-id="a796f-127">在此示例中，模块 `FictionalTools` 依赖于 `Newtonsoft.Json` 版本 `12.0.3`，此版本的 `Newtonsoft.Json` 比示例 PowerShell 中随附的 `11.0.2` 更新。</span><span class="sxs-lookup"><span data-stu-id="a796f-127">In this example, the module `FictionalTools` depends on `Newtonsoft.Json` version `12.0.3`, which is a newer version of `Newtonsoft.Json` than `11.0.2` that ships in the example PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="a796f-128">这是一个示例，PowerShell 7 当前随附有 `Newtonsoft.Json 12.0.3`。</span><span class="sxs-lookup"><span data-stu-id="a796f-128">This is an example and PowerShell 7 currently ships with `Newtonsoft.Json 12.0.3`.</span></span>

<span data-ttu-id="a796f-129">因为该模块依赖于程序集的较新版本，所以它不会接受 PowerShell 已加载的版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-129">Because the module depends on a newer version of the assembly, it won't accept the version that PowerShell already has loaded.</span></span> <span data-ttu-id="a796f-130">但是，由于 PowerShell 已加载了该程序集的一个版本，因此该模块无法使用常规加载机制来加载其自己的版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-130">But because PowerShell has already loaded a version of the assembly, the module can't load its own version using the conventional load mechanism.</span></span>

### <a name="conflicting-with-another-modules-dependencies"></a><span data-ttu-id="a796f-131">与另一个模块的依赖项冲突</span><span class="sxs-lookup"><span data-stu-id="a796f-131">Conflicting with another module's dependencies</span></span>

<span data-ttu-id="a796f-132">PowerShell 中的另一种常见情况是，加载依赖于某程序集的一个版本的模块，然后再加载依赖于该程序集的不同版本的另一个模块。</span><span class="sxs-lookup"><span data-stu-id="a796f-132">Another common scenario in PowerShell is that a module is loaded that depends on one version of an assembly, and then another module is loaded later that depends on a different version of that assembly.</span></span>

<span data-ttu-id="a796f-133">此行为通常如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-133">This often looks like the following:</span></span>

![两个 PowerShell 模块需要 Microsoft.Extensions.Logging 依赖项的不同版本](./media/resolving-dependency-conflicts/mod-conflict.jpg)

<span data-ttu-id="a796f-135">在此例中，`FictionalTools` 模块需要比 `FilesystemManager` 模块更新的 `Microsoft.Extensions.Logging` 版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-135">In this case, the `FictionalTools` module requires a newer version of `Microsoft.Extensions.Logging` than the `FilesystemManager` module.</span></span>

<span data-ttu-id="a796f-136">假设这些模块通过将依赖项程序集与根模块程序集放在同一目录中来加载其依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-136">Imagine these modules load their dependencies by placing the dependency assemblies in the same directory as the root module assembly.</span></span> <span data-ttu-id="a796f-137">这使 .NET 可以按名称隐式加载它们。</span><span class="sxs-lookup"><span data-stu-id="a796f-137">This allows .NET to implicitly load them by name.</span></span> <span data-ttu-id="a796f-138">如果运行的是 PowerShell 7（在 .NET Core 3.1 之上），则可以加载并运行 `FictionalTools`，然后加载并运行 `FilesystemManager`，而不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="a796f-138">If we're running PowerShell 7 (on top of .NET Core 3.1), we can load and run `FictionalTools`, then load and run `FilesystemManager` without issue.</span></span> <span data-ttu-id="a796f-139">但是，在新会话中，如果我们加载并运行 `FilesystemManager`，然后加载 `FictionalTools`，则会从 `FictionalTools` 命令中得到 `FileLoadException`，因为它需要比已加载的 `Microsoft.Extensions.Logging` 版本更新的版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-139">However, in a new session, if we load and run `FilesystemManager`, then load `FictionalTools`, we get a `FileLoadException` from the `FictionalTools` command because it requires a newer version of `Microsoft.Extensions.Logging` than the one loaded.</span></span>
<span data-ttu-id="a796f-140">`FictionalTools` 无法加载所需的版本，因为已加载了同名的程序集。</span><span class="sxs-lookup"><span data-stu-id="a796f-140">`FictionalTools` can't load the version needed because an assembly of the same name has already been loaded.</span></span>

## <a name="powershell-and-net"></a><span data-ttu-id="a796f-141">PowerShell 和 .NET</span><span class="sxs-lookup"><span data-stu-id="a796f-141">PowerShell and .NET</span></span>

<span data-ttu-id="a796f-142">PowerShell 在 .NET 平台上运行。</span><span class="sxs-lookup"><span data-stu-id="a796f-142">PowerShell runs on the .NET platform.</span></span> <span data-ttu-id="a796f-143">NET 最终负责解析和加载程序集依赖项，因此我们必须在此处了解 .NET 的操作方式，以了解依赖项冲突。</span><span class="sxs-lookup"><span data-stu-id="a796f-143">NET is ultimately responsible for resolving and loading assembly dependencies, so we must understand how .NET operates here to understand dependency conflicts.</span></span>

<span data-ttu-id="a796f-144">我们还必须正视这样一个事实：不同版本的 PowerShell 在不同的 .NET 实现上运行。</span><span class="sxs-lookup"><span data-stu-id="a796f-144">We must also confront the fact that different versions of PowerShell run on different .NET implementations.</span></span> <span data-ttu-id="a796f-145">通常，PowerShell 5.1 和更低版本在 .NET Framework 上运行，而 PowerShell 6 和更高版本则在 .NET Core 上运行。</span><span class="sxs-lookup"><span data-stu-id="a796f-145">In general, PowerShell 5.1 and below run on .NET Framework, while PowerShell 6 and above run on .NET Core.</span></span> <span data-ttu-id="a796f-146">.NET 的这两种实现以不同的方式加载和处理程序集。</span><span class="sxs-lookup"><span data-stu-id="a796f-146">These two implementations of .NET load and handle assemblies differently.</span></span>
<span data-ttu-id="a796f-147">这意味着依赖项冲突的解决方式可能会因基础 .NET 平台而异。</span><span class="sxs-lookup"><span data-stu-id="a796f-147">This means that resolving dependency conflicts can vary depending on the underlying .NET platform.</span></span>

### <a name="assembly-load-contexts"></a><span data-ttu-id="a796f-148">程序集加载上下文</span><span class="sxs-lookup"><span data-stu-id="a796f-148">Assembly Load Contexts</span></span>

<span data-ttu-id="a796f-149">在 .NET 中，程序集加载上下文 (ALC) 是指将程序集加载到其中的运行时命名空间。</span><span class="sxs-lookup"><span data-stu-id="a796f-149">In .NET, an _Assembly Load Context_ (ALC) that is a runtime namespace into which assemblies are loaded.</span></span> <span data-ttu-id="a796f-150">程序集的名称必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a796f-150">The assemblies' names must be unique.</span></span> <span data-ttu-id="a796f-151">此概念允许在每个 ALC 中按名称唯一地解析程序集。</span><span class="sxs-lookup"><span data-stu-id="a796f-151">This concept allows assemblies to be uniquely resolved by name in each ALC.</span></span>

### <a name="assembly-reference-loading-in-net"></a><span data-ttu-id="a796f-152">.NET 中的程序集引用加载</span><span class="sxs-lookup"><span data-stu-id="a796f-152">Assembly reference loading in .NET</span></span>

<span data-ttu-id="a796f-153">程序集加载的语义取决于 .NET 实现（.NET Core 与 .NET Framework）以及用于加载特定程序集的 .NET API。</span><span class="sxs-lookup"><span data-stu-id="a796f-153">The semantics of assembly loading depend on both the .NET implementation (.NET Core vs .NET Framework) and the .NET API used to load a particular assembly.</span></span> <span data-ttu-id="a796f-154">此处不进行详细介绍，[延伸阅读](#further-reading)部分中的链接非常详细地介绍了每个 .NET 实现中 .NET 程序集加载的工作方式。</span><span class="sxs-lookup"><span data-stu-id="a796f-154">Rather than go into detail here, there are links in the [Further reading](#further-reading) section that go into great detail on how .NET assembly loading works in each .NET implementation.</span></span>

<span data-ttu-id="a796f-155">在本文中，我们将介绍以下机制：</span><span class="sxs-lookup"><span data-stu-id="a796f-155">In this article we'll refer to the following mechanisms:</span></span>

- <span data-ttu-id="a796f-156">隐式程序集加载（有效地 `Assembly.Load(AssemblyName)`），如果 .NET 隐式尝试从 .NET 代码中的静态程序集引用按名称加载程序集的话。</span><span class="sxs-lookup"><span data-stu-id="a796f-156">Implicit assembly loading (effectively `Assembly.Load(AssemblyName)`), when .NET implicitly tries to load an assembly by name from a static assembly reference in .NET code.</span></span>
- <span data-ttu-id="a796f-157">`Assembly.LoadFrom()`，它是一个面向插件的加载 API，可添加处理程序来解析加载的 DLL 的依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-157">`Assembly.LoadFrom()`, a plugin-oriented loading API that adds handlers to resolve dependencies of the loaded DLL.</span></span> <span data-ttu-id="a796f-158">此方法可能不会按所需方式解析依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-158">This method may not resolve dependencies the way we want.</span></span>
- <span data-ttu-id="a796f-159">`Assembly.LoadFile()`，它是一个基本的加载 API，旨在仅加载请求的程序集，不处理任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-159">`Assembly.LoadFile()`, a basic loading API intended to load only the assembly asked for and does not handle any dependencies.</span></span>

### <a name="differences-in-net-framework-vs-net-core"></a><span data-ttu-id="a796f-160">.NET Framework 与 .NET Core 之间的差异</span><span class="sxs-lookup"><span data-stu-id="a796f-160">Differences in .NET Framework vs .NET Core</span></span>

<span data-ttu-id="a796f-161">这些 API 在 .NET Core 和 .NET Framework 之间的工作方式已发生了细微的变化，因此有必要通读随附的[链接](#further-reading)内容。</span><span class="sxs-lookup"><span data-stu-id="a796f-161">The way these APIs work has changed in subtle ways between .NET Core and .NET Framework, so it's worth reading through the included [links](#further-reading).</span></span> <span data-ttu-id="a796f-162">重要的是，.NET Framework 和 .NET Core 之间的程序集加载上下文和其他程序集解析机制已更改。</span><span class="sxs-lookup"><span data-stu-id="a796f-162">Importantly, Assembly Load Contexts and other assembly resolution mechanisms have changed between .NET Framework and .NET Core.</span></span>

<span data-ttu-id="a796f-163">具体而言，.NET Framework 具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="a796f-163">In particular, .NET Framework has the following features:</span></span>

- <span data-ttu-id="a796f-164">全局程序集缓存，适用于计算机范围内的程序集解析</span><span class="sxs-lookup"><span data-stu-id="a796f-164">The Global Assembly Cache, for machine-wide assembly resolution</span></span>
- <span data-ttu-id="a796f-165">应用程序域，其工作方式类似于用于程序集隔离的进程内沙盒，但也提供了一个要与之争用的序列化层</span><span class="sxs-lookup"><span data-stu-id="a796f-165">Application Domains, which work like in-process sandboxes for assembly isolation, but also present a serialization layer to contend with</span></span>
- <span data-ttu-id="a796f-166">受限的程序集加载上下文模型（[此处](/dotnet/framework/deployment/best-practices-for-assembly-loading)进行了详细说明），具有一组固定的程序集加载上下文，每个上下文都有其各自的行为：</span><span class="sxs-lookup"><span data-stu-id="a796f-166">A limited assembly load context model, explained in depth [here](/dotnet/framework/deployment/best-practices-for-assembly-loading), that has a fixed set of assembly load contexts, each with their own behavior:</span></span>
  - <span data-ttu-id="a796f-167">默认加载上下文，默认情况下在其中加载程序集</span><span class="sxs-lookup"><span data-stu-id="a796f-167">The default load context, where assemblies are loaded by default</span></span>
  - <span data-ttu-id="a796f-168">加载位置上下文，用于在运行时手动加载程序集</span><span class="sxs-lookup"><span data-stu-id="a796f-168">The load-from context, for loading assemblies manually at runtime</span></span>
  - <span data-ttu-id="a796f-169">仅反射上下文，用于安全地加载程序集，以在不运行它们的情况下读取其元数据</span><span class="sxs-lookup"><span data-stu-id="a796f-169">The reflection-only context, for safely loading assemblies to read their metadata without running them</span></span>
  - <span data-ttu-id="a796f-170">特殊的 void，用于存储通过 `Assembly.LoadFile(string path)` 和 `Assembly.Load(byte[] asmBytes)` 加载的程序集</span><span class="sxs-lookup"><span data-stu-id="a796f-170">The mysterious void that assemblies loaded with `Assembly.LoadFile(string path)` and `Assembly.Load(byte[] asmBytes)` live in</span></span>

<span data-ttu-id="a796f-171">.NET Core（和 .NET 5+）已将此复杂内容替换为更简单的模型：</span><span class="sxs-lookup"><span data-stu-id="a796f-171">.NET Core (and .NET 5+) has replaced this complexity with a simpler model:</span></span>

- <span data-ttu-id="a796f-172">无全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="a796f-172">No Global Assembly Cache.</span></span> <span data-ttu-id="a796f-173">应用程序会引入其所有依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-173">Applications bring all their own dependencies.</span></span> <span data-ttu-id="a796f-174">这将删除应用程序中依赖项解析的外部因素，使依赖项解析更具可重现性。</span><span class="sxs-lookup"><span data-stu-id="a796f-174">This removes an external factor for dependency resolution in applications, making dependency resolution more reproducible.</span></span>
  <span data-ttu-id="a796f-175">对于模块，插件主机 PowerShell 使这种情况略微复杂一些。</span><span class="sxs-lookup"><span data-stu-id="a796f-175">PowerShell, as the plugin host, complicates this slightly for modules.</span></span> <span data-ttu-id="a796f-176">它在 `$PSHOME` 中的依赖项与所有模块共享。</span><span class="sxs-lookup"><span data-stu-id="a796f-176">Its dependencies in `$PSHOME` are shared with all modules.</span></span>
- <span data-ttu-id="a796f-177">只有一个应用程序域，且无法创建新的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a796f-177">Only one Application Domain, and no ability to create new ones.</span></span> <span data-ttu-id="a796f-178">.NET Core 中保留的应用程序域概念纯粹是指 .NET 进程的全局状态。</span><span class="sxs-lookup"><span data-stu-id="a796f-178">The Application Domain concept is maintained in .NET Core purely to be the global state of the .NET process.</span></span>
- <span data-ttu-id="a796f-179">新的可扩展程序集加载上下文模型。</span><span class="sxs-lookup"><span data-stu-id="a796f-179">A new, extensible Assembly Load Context model.</span></span> <span data-ttu-id="a796f-180">可以通过将程序集解析放入新的 ALC 中来设置其命名空间。</span><span class="sxs-lookup"><span data-stu-id="a796f-180">Assembly resolution can be namespaced by putting it in a new ALC.</span></span> <span data-ttu-id="a796f-181">.NET Core 进程从一个默认的 ALC 开始，所有程序集均加载到其中。</span><span class="sxs-lookup"><span data-stu-id="a796f-181">.NET Core processes begin with a single default ALC into which all assemblies are loaded.</span></span> <span data-ttu-id="a796f-182">（那些通过 `Assembly.LoadFile(string)` 和 `Assembly.Load(byte[])` 加载的程序集除外）但是，该进程可以创建和定义自己的 ALC 及其自己的加载逻辑。</span><span class="sxs-lookup"><span data-stu-id="a796f-182">(except for those loaded with `Assembly.LoadFile(string)` and `Assembly.Load(byte[])`) But the process can create and define its own custom ALCs with its own loading logic.</span></span> <span data-ttu-id="a796f-183">加载程序集时，加载到其中的第一个 ALC 负责解析其依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-183">When an assembly is loaded, the first ALC it is loaded into is responsible for resolving its dependencies.</span></span> <span data-ttu-id="a796f-184">这样就有机会实现功能强大的 .NET 插件加载机制。</span><span class="sxs-lookup"><span data-stu-id="a796f-184">This creates opportunities to implement powerful .NET plugin loading mechanisms.</span></span>

<span data-ttu-id="a796f-185">在这两种实现中，程序集都是延迟加载的。</span><span class="sxs-lookup"><span data-stu-id="a796f-185">In both implementations, assemblies are loaded lazily.</span></span> <span data-ttu-id="a796f-186">这意味着它们是在首次运行需要其类型的方法时加载的。</span><span class="sxs-lookup"><span data-stu-id="a796f-186">This means that they are loaded when a method requiring their type is run for the first time.</span></span>

<span data-ttu-id="a796f-187">例如，下面是同一代码的两个版本，它们在不同的时间加载依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-187">For example, here are two versions of the same code that load a dependency at different times.</span></span>

<span data-ttu-id="a796f-188">第一个始终在调用 `Program.GetRange()` 时加载其依赖项，因为方法中在词法上存在依赖项引用：</span><span class="sxs-lookup"><span data-stu-id="a796f-188">The first always loads its dependency when `Program.GetRange()` is called, because the dependency reference is lexically present within the method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetRange(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library will be loaded when GetRange is run
                // because the dependency call occurs directly within the method
                DependencyApi.Use();
            }

            list.Add(i);
        }
        return list;
    }
}
```

<span data-ttu-id="a796f-189">第二个仅在 `limit` 参数大于或等于 20 时才加载其依赖项，这是因为需要通过某方法进行内部间接寻址：</span><span class="sxs-lookup"><span data-stu-id="a796f-189">The second will load its dependency only if the `limit` parameter is 20 or more, because of the internal indirection through a method:</span></span>

```csharp
using Dependency.Library;

public static class Program
{
    public static List<int> GetNumbers(int limit)
    {
        var list = new List<int>();
        for (int i = 0; i < limit; i++)
        {
            if (i >= 20)
            {
                // Dependency.Library is only referenced within
                // the UseDependencyApi() method,
                // so will only be loaded when limit >= 20
                UseDependencyApi();
            }

            list.Add(i);
        }
        return list;
    }

    private static void UseDependencyApi()
    {
        // Once UseDependencyApi() is called, Dependency.Library is loaded
        DependencyApi.Use();
    }
}
```

<span data-ttu-id="a796f-190">这是一种很好的做法，因为它可以最大程度地减少内存和文件系统 I/O，并更有效地使用资源。</span><span class="sxs-lookup"><span data-stu-id="a796f-190">This is a good practice since it minimizes the memory and filesystem I/O and uses the resources more efficiently.</span></span> <span data-ttu-id="a796f-191">不幸的是，这样做存在一个副作用，即在到达尝试加载程序集的代码路径之前，我们无法知道程序集无法加载。</span><span class="sxs-lookup"><span data-stu-id="a796f-191">The unfortunate a side effect of this is that we won't know that the assembly fails to load until we reach the code path that tries to load the assembly.</span></span>

<span data-ttu-id="a796f-192">它还可以针对程序集加载冲突创建计时条件。</span><span class="sxs-lookup"><span data-stu-id="a796f-192">It can also create a timing condition for assembly load conflicts.</span></span> <span data-ttu-id="a796f-193">如果同一程序的两个部分尝试加载同一程序集的不同版本，则加载的版本取决于首先运行的代码路径。</span><span class="sxs-lookup"><span data-stu-id="a796f-193">If two parts of the same program try to load different versions of the same assembly, the version loaded depends on which code path is run first.</span></span>

<span data-ttu-id="a796f-194">对于 PowerShell，这意味着以下因素可能会影响程序集加载冲突：</span><span class="sxs-lookup"><span data-stu-id="a796f-194">For PowerShell, this means that the following factors can affect an assembly load conflict:</span></span>

- <span data-ttu-id="a796f-195">首先加载哪个模块？</span><span class="sxs-lookup"><span data-stu-id="a796f-195">Which module was loaded first?</span></span>
- <span data-ttu-id="a796f-196">使用依赖项库的代码路径是否运行？</span><span class="sxs-lookup"><span data-stu-id="a796f-196">Was the code path that uses the dependency library run?</span></span>
- <span data-ttu-id="a796f-197">PowerShell 是在启动时加载冲突的依赖项，还是仅在某些代码路径下加载？</span><span class="sxs-lookup"><span data-stu-id="a796f-197">Does PowerShell load a conflicting dependency at startup or only under certain code paths?</span></span>

## <a name="quick-fixes-and-their-limitations"></a><span data-ttu-id="a796f-198">快速解决方案及其限制</span><span class="sxs-lookup"><span data-stu-id="a796f-198">Quick fixes and their limitations</span></span>

<span data-ttu-id="a796f-199">在某些情况下，可以对模块进行少量调整，通过最少的工作量来解决问题。</span><span class="sxs-lookup"><span data-stu-id="a796f-199">In some cases, it's possible to make small adjustments to your module and fix things with minimal effort.</span></span> <span data-ttu-id="a796f-200">但这些解决方案往往有一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="a796f-200">But these solutions tend to come with caveats.</span></span> <span data-ttu-id="a796f-201">虽然它们可能适用于你的模块，但并非适用于所有模块。</span><span class="sxs-lookup"><span data-stu-id="a796f-201">While they may apply to your module, they won't work for every module.</span></span>

### <a name="change-your-dependency-version"></a><span data-ttu-id="a796f-202">更改依赖项版本</span><span class="sxs-lookup"><span data-stu-id="a796f-202">Change your dependency version</span></span>

<span data-ttu-id="a796f-203">避免依赖项冲突的最简单方法是就依赖项达成一致。</span><span class="sxs-lookup"><span data-stu-id="a796f-203">The simplest way to avoid dependency conflicts is to agree on a dependency.</span></span> <span data-ttu-id="a796f-204">在以下情况下可实现这一操作：</span><span class="sxs-lookup"><span data-stu-id="a796f-204">This may be possible when:</span></span>

- <span data-ttu-id="a796f-205">冲突与模块的直接依赖项有关，并且你可以控制版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-205">Your conflict is with a direct dependency of your module and you control the version.</span></span>
- <span data-ttu-id="a796f-206">冲突与间接依赖项有关，但你可以将直接依赖项配置为使用可操作的间接依赖项版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-206">Your conflict is with an indirect dependency, but you can configure your direct dependencies to use a workable indirect dependency version.</span></span>
- <span data-ttu-id="a796f-207">你知道存在冲突的版本，可以依赖于它，并且不进行更改。</span><span class="sxs-lookup"><span data-stu-id="a796f-207">You know the conflicting version and can rely on it not changing.</span></span>

<span data-ttu-id="a796f-208">`Newtonsoft.Json` 包是最后一种情况的一个很好的示例。</span><span class="sxs-lookup"><span data-stu-id="a796f-208">The `Newtonsoft.Json` package is a good example of this last scenario.</span></span> <span data-ttu-id="a796f-209">这是 PowerShell 6 及更高版本的依赖项，不在 Windows PowerShell 中使用。</span><span class="sxs-lookup"><span data-stu-id="a796f-209">This is a dependency of PowerShell 6 and above, and isn't used in Windows PowerShell.</span></span> <span data-ttu-id="a796f-210">这意味着，解决版本控制冲突的一种简单方法是，将希望作为目标的 PowerShell 版本中最低版本的 `Newtonsoft.Json` 作为目标。</span><span class="sxs-lookup"><span data-stu-id="a796f-210">Meaning a simple way to resolve versioning conflicts is to target the lowest version of `Newtonsoft.Json` across the PowerShell versions you wish to target.</span></span>

<span data-ttu-id="a796f-211">例如，PowerShell 6.2.6 和 PowerShell 7.0.2 当前都使用 `Newtonsoft.Json` 版本 12.0.3。</span><span class="sxs-lookup"><span data-stu-id="a796f-211">For example, PowerShell 6.2.6 and PowerShell 7.0.2 both currently use `Newtonsoft.Json` version 12.0.3.</span></span> <span data-ttu-id="a796f-212">因此，若要创建面向 Windows PowerShell、PowerShell 6 和 PowerShell 7 的模块，需要将 `Newtonsoft.Json 12.0.3` 作为依赖项并将其添加到构建的模块中。</span><span class="sxs-lookup"><span data-stu-id="a796f-212">So, to create a module targeting Windows PowerShell, PowerShell 6, and PowerShell 7, you would target `Newtonsoft.Json 12.0.3` as a dependency and include it in your built module.</span></span> <span data-ttu-id="a796f-213">在 PowerShell 6 或 7 中加载该模块后，PowerShell 自己的 `Newtonsoft.Json` 程序集已加载。</span><span class="sxs-lookup"><span data-stu-id="a796f-213">When the module is loaded in PowerShell 6 or 7, PowerShell's own `Newtonsoft.Json` assembly is already loaded.</span></span> <span data-ttu-id="a796f-214">此外，它至少是模块所需的版本，因此解析成功。</span><span class="sxs-lookup"><span data-stu-id="a796f-214">Also, it is at least the version required for your module, so resolution succeeds.</span></span> <span data-ttu-id="a796f-215">在 Windows PowerShell 中，PowerShell 中尚不存在该程序集。</span><span class="sxs-lookup"><span data-stu-id="a796f-215">In Windows PowerShell, the assembly isn't already present in PowerShell.</span></span> <span data-ttu-id="a796f-216">因此，它改为从模块文件夹中加载。</span><span class="sxs-lookup"><span data-stu-id="a796f-216">So, it's loaded from your module folder instead.</span></span>

<span data-ttu-id="a796f-217">通常，如果以具体的 PowerShell 包（例如 `Microsoft.PowerShell.Sdk` 或 `System.Management.Automation`）作为目标，NuGet 应能够解析所需的正确依赖项版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-217">Generally, when targeting a concrete PowerShell package, like `Microsoft.PowerShell.Sdk` or `System.Management.Automation`, NuGet should be able to resolve the right dependency versions required.</span></span> <span data-ttu-id="a796f-218">由于必须在以多个框架还是以 `PowerShellStandard.Library` 作为目标之间进行选择，因此同时以 Windows PowerShell 和 PowerShell 6+ 作为目标会变得更加困难。</span><span class="sxs-lookup"><span data-stu-id="a796f-218">Targeting both Windows PowerShell and PowerShell 6+ becomes more difficult because you must choose between targeting multiple frameworks or `PowerShellStandard.Library`.</span></span>

<span data-ttu-id="a796f-219">固定为某个通用依赖项版本不起作用的情况包括：</span><span class="sxs-lookup"><span data-stu-id="a796f-219">Circumstances where pinning to a common dependency version won't work include:</span></span>

- <span data-ttu-id="a796f-220">冲突与间接依赖项有关，并且所有依赖项都不能配置为使用通用版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-220">The conflict is with an indirect dependency, and none of your dependencies can be configured to use a common version.</span></span>
- <span data-ttu-id="a796f-221">其他依赖项版本可能会经常更改，因此使用通用版本只是短期解决方案。</span><span class="sxs-lookup"><span data-stu-id="a796f-221">The other dependency version is likely to change often, so settling on a common version is only a short-term fix.</span></span>

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a><span data-ttu-id="a796f-222">添加 AssemblyResolve 事件处理程序以创建动态绑定重定向</span><span class="sxs-lookup"><span data-stu-id="a796f-222">Add an AssemblyResolve event handler to create a dynamic binding redirect</span></span>

<span data-ttu-id="a796f-223">有时无法更改自己的依赖项版本，或者这样做非常困难。</span><span class="sxs-lookup"><span data-stu-id="a796f-223">Sometimes changing your own dependency version isn't possible or is too difficult.</span></span> <span data-ttu-id="a796f-224">另一种选项是通过注册 `AssemblyResolve` 事件的事件处理程序来设置动态绑定重定向。</span><span class="sxs-lookup"><span data-stu-id="a796f-224">Another option is to set up a dynamic binding redirect by registering an event handler for the `AssemblyResolve` event.</span></span>

<span data-ttu-id="a796f-225">与静态绑定重定向一样，关键是要强制某依赖项的所有使用者使用相同的实际程序集。</span><span class="sxs-lookup"><span data-stu-id="a796f-225">As with a static binding redirect, the point is to force all consumers of a dependency to use the same actual assembly.</span></span> <span data-ttu-id="a796f-226">截获加载依赖项的调用，并始终将其重定向到所需的版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-226">You intercept calls to load the dependency and always redirect them to the version you want.</span></span>

<span data-ttu-id="a796f-227">如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-227">This looks something like this:</span></span>

```csharp
// Register the event handler as early as you can in your code.
// A good option is to use the IModuleAssemblyInitializer interface
// that PowerShell provides to run code early on when your module is loaded.

// This class will be instantiated on module import and the OnImport() method run.
// Make sure that:
//  - the class is public
//  - the class has a public, parameterless constructor
//  - the class implements IModuleAssemblyInitializer
public class MyModuleInitializer : IModuleAssemblyInitializer
{
    public void OnImport()
    {
        AppDomain.CurrentDomain.AssemblyResolve += DependencyResolution.ResolveNewtonsoftJson;
    }
}

// Clean up the event handler when the the module is removed
// to prevent memory leaks.
//
// Like IModuleAssemblyInitializer, IModuleAssemblyCleanup allows
// you to register code to run when a module is removed (with Remove-Module).
// Make sure it is also public with a public parameterless contructor
// and implements IModuleAssemblyCleanup.
public class MyModuleCleanup : IModuleAssemblyCleanup
{
    public void OnRemove()
    {
        AppDomain.CurrentDomain.AssemblyResolve -= DependencyResolution.ResolveNewtonsoftJson;
    }
}

internal static class DependencyResolution
{
    private static readonly string s_modulePath = Path.GetDirectoryName(
        Assembly.GetExecutingAssembly().Location);

    public static Assembly ResolveNewtonsoftJson(object sender, ResolveEventArgs args)
    {
        // Parse the assembly name
        var assemblyName = new AssemblyName(args.Name);

        // We only want to handle the dependency we care about.
        // In this example it's Newtonsoft.Json.
        if (!assemblyName.Name.Equals("Newtonsoft.Json"))
        {
            return null;
        }

        // Generally the version of the dependency you want to load is the higher one,
        // since it's the most likely to be compatible with all dependent assemblies.
        // The logic here assumes our module always has the version we want to load.
        // Also note the use of Assembly.LoadFrom() here rather than Assembly.LoadFile().
        return Assembly.LoadFrom(Path.Combine(s_modulePath, "Newtonsoft.Json.dll"));
    }
}
```

<span data-ttu-id="a796f-228">在技术上，可以在 PowerShell 中注册脚本块来处理 `AssemblyResolve` 事件，但是：</span><span class="sxs-lookup"><span data-stu-id="a796f-228">You can technically register a scriptblock within PowerShell to handle an `AssemblyResolve` event, but:</span></span>

- <span data-ttu-id="a796f-229">在任何线程上都可能触发 `AssemblyResolve` 事件，而 PowerShell 无法对此进行处理。</span><span class="sxs-lookup"><span data-stu-id="a796f-229">An `AssemblyResolve` event may be triggered on any thread, something that PowerShell will be unable to handle.</span></span>
- <span data-ttu-id="a796f-230">即使在正确的线程上处理事件，PowerShell 的范围概念也意味着必须谨慎编写事件处理程序脚本块，以避免依赖于其外部定义的变量。</span><span class="sxs-lookup"><span data-stu-id="a796f-230">Even when events are handled on the right thread, PowerShell's scoping concepts mean that the event handler scriptblock must be written carefully to not depend on variables defined outside it.</span></span>

<span data-ttu-id="a796f-231">在某些情况下，无法重定向到通用版本：</span><span class="sxs-lookup"><span data-stu-id="a796f-231">There are situations where redirecting to a common version won't work:</span></span>

- <span data-ttu-id="a796f-232">当依赖项在版本之间进行了中断性变更，或依赖项代码依赖于某个功能否则在重定向到的版本中不可用时。</span><span class="sxs-lookup"><span data-stu-id="a796f-232">When the dependency has made breaking changes between versions, or when dependent code relies on a functionality otherwise not available in the version you redirect to.</span></span>
- <span data-ttu-id="a796f-233">依赖项冲突之前未加载模块时。</span><span class="sxs-lookup"><span data-stu-id="a796f-233">When your module isn't loaded before the conflicting dependency.</span></span> <span data-ttu-id="a796f-234">如果在加载依赖项后注册 `AssemblyResolve` 事件处理程序，则永远不会触发该处理程序。</span><span class="sxs-lookup"><span data-stu-id="a796f-234">If you register an `AssemblyResolve` event handler after the dependency has been loaded, it will never be fired.</span></span> <span data-ttu-id="a796f-235">如果尝试防止依赖项与另一个模块冲突，则这可能是一个问题，因为可能会先加载另一个模块。</span><span class="sxs-lookup"><span data-stu-id="a796f-235">If you're trying to prevent dependency conflicts with another module, this may be an issue, since the other module may be loaded first.</span></span>

### <a name="use-the-dependency-out-of-process"></a><span data-ttu-id="a796f-236">使用进程外的依赖项</span><span class="sxs-lookup"><span data-stu-id="a796f-236">Use the dependency out of process</span></span>

<span data-ttu-id="a796f-237">此解决方案更适用于模块用户，而不是模块创建者。</span><span class="sxs-lookup"><span data-stu-id="a796f-237">This solution is more for module users than module authors.</span></span> <span data-ttu-id="a796f-238">当遇到由于现有依赖项冲突而无法工作的模块时，可使用此解决方案。</span><span class="sxs-lookup"><span data-stu-id="a796f-238">This is a solution to use when confronted with a module that won't work due to an existing dependency conflict.</span></span>

<span data-ttu-id="a796f-239">由于将同一程序集的两个版本加载到同一 .NET 进程中，因此发生依赖项冲突。</span><span class="sxs-lookup"><span data-stu-id="a796f-239">Dependency conflicts occur because two versions of the same assembly are loaded into the same .NET process.</span></span> <span data-ttu-id="a796f-240">一个简单的解决方案是将它们加载到不同的进程中，前提是你仍然可以同时使用这两者的功能。</span><span class="sxs-lookup"><span data-stu-id="a796f-240">A simple solution is to load them into different processes, as long as you can still use the functionality from both together.</span></span>

<span data-ttu-id="a796f-241">在 PowerShell 中，有几种方法可以实现此目的：</span><span class="sxs-lookup"><span data-stu-id="a796f-241">In PowerShell, there are several ways to achieve this:</span></span>

- <span data-ttu-id="a796f-242">调用 PowerShell 作为子进程</span><span class="sxs-lookup"><span data-stu-id="a796f-242">Invoke PowerShell as a subprocess</span></span>

  <span data-ttu-id="a796f-243">在当前进程之外运行 PowerShell 命令的一种简单方法是，直接通过命令调用启动新的 PowerShell 进程：</span><span class="sxs-lookup"><span data-stu-id="a796f-243">A simple way to run a PowerShell command out of the current process is to just start a new PowerShell process directly with the command call:</span></span>

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  <span data-ttu-id="a796f-244">此处的主要限制在于，与其他选项相比，重构结果可能会更棘手或更容易出错。</span><span class="sxs-lookup"><span data-stu-id="a796f-244">The main limitation here is that restructuring the result can be trickier or more error prone than other options.</span></span>

- <span data-ttu-id="a796f-245">PowerShell 作业系统</span><span class="sxs-lookup"><span data-stu-id="a796f-245">The PowerShell job system</span></span>

  <span data-ttu-id="a796f-246">通过将命令发送到新的 PowerShell 进程并返回结果，PowerShell 作业系统也可以在进程之外运行命令：</span><span class="sxs-lookup"><span data-stu-id="a796f-246">The PowerShell job system also runs commands out of process, by sending commands to a new PowerShell process and returning the results:</span></span>

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  <span data-ttu-id="a796f-247">在这种情况下，只需要确保正确传递所有变量和状态即可。</span><span class="sxs-lookup"><span data-stu-id="a796f-247">In this case, you just need to be sure that any variables and state are passed in correctly.</span></span>

  <span data-ttu-id="a796f-248">即使运行少量命令，作业系统也可能会有点繁琐。</span><span class="sxs-lookup"><span data-stu-id="a796f-248">The job system can also be slightly cumbersome when running small commands.</span></span>

- <span data-ttu-id="a796f-249">PowerShell 远程处理</span><span class="sxs-lookup"><span data-stu-id="a796f-249">PowerShell remoting</span></span>

  <span data-ttu-id="a796f-250">如果 PowerShell 远程处理可用，则这可能是在进程之外运行命令的有用方法。</span><span class="sxs-lookup"><span data-stu-id="a796f-250">When it's available, PowerShell remoting can be a useful way to run commands out of process.</span></span> <span data-ttu-id="a796f-251">通过远程处理，可以在新进程中创建新的 PSSession，通过 PowerShell 远程处理调用其命令，然后将结果与包含冲突依赖项的其他模块一起在本地使用。</span><span class="sxs-lookup"><span data-stu-id="a796f-251">With remoting, you can create a fresh **PSSession** in a new process, call its commands over PowerShell remoting, then use the results locally with the other modules containing the conflicting dependencies.</span></span>

  <span data-ttu-id="a796f-252">示例可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-252">An example might look like this:</span></span>

  ```powershell
  # Create a local PowerShell session
  # where the module with conflicting assemblies will be loaded
  $s = New-PSSession

  # Import the module with the conflicting dependency via remoting,
  # exposing the commands locally
  Import-Module -PSSession $s -Name ConflictingModule

  # Run a command from the module with the conflicting dependencies
  Invoke-ConflictingCommand
  ```

- <span data-ttu-id="a796f-253">对 Windows PowerShell 的隐式远程处理</span><span class="sxs-lookup"><span data-stu-id="a796f-253">Implicit remoting to Windows PowerShell</span></span>

  <span data-ttu-id="a796f-254">PowerShell 7 中的另一个选项是在 `Import-Module` 上使用 `-UseWindowsPowerShell` 标志。</span><span class="sxs-lookup"><span data-stu-id="a796f-254">Another option in PowerShell 7 is to use the `-UseWindowsPowerShell` flag on `Import-Module`.</span></span> <span data-ttu-id="a796f-255">这将通过本地远程处理会话将模块导入 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="a796f-255">This will import the module through a local remoting session into Windows PowerShell:</span></span>

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  <span data-ttu-id="a796f-256">请注意，模块可能无法与 Windows PowerShell 一起使用，或与 Windows PowerShell 的工作方式不同。</span><span class="sxs-lookup"><span data-stu-id="a796f-256">Be aware that modules may not work with, or work differently with Windows PowerShell.</span></span>

#### <a name="when-out-of-process-invocation-should-not-be-used"></a><span data-ttu-id="a796f-257">不应使用进程外调用的情况</span><span class="sxs-lookup"><span data-stu-id="a796f-257">When out-of-process invocation should not be used</span></span>

<span data-ttu-id="a796f-258">作为模块创建者，进程外命令调用很难嵌入到模块中，并可能出现导致问题的极端情况。</span><span class="sxs-lookup"><span data-stu-id="a796f-258">As a module author, out-of-process command invocation is difficult to bake into a module and may have edge cases that cause issues.</span></span> <span data-ttu-id="a796f-259">具体而言，在模块需要在其中工作的所有环境中，远程处理和作业可能并非都可用。</span><span class="sxs-lookup"><span data-stu-id="a796f-259">In particular, remoting and jobs may not be available in all environments where your module needs to work.</span></span> <span data-ttu-id="a796f-260">但是，将实现移出进程并允许 PowerShell 模块成为更精简的客户端，此一般原则可能仍然适用。</span><span class="sxs-lookup"><span data-stu-id="a796f-260">However, the general principle of moving the implementation out of process and allowing the PowerShell module to be a thinner client, may still be applicable.</span></span>

<span data-ttu-id="a796f-261">在某些情况下，模块用户无法进行进程外调用：</span><span class="sxs-lookup"><span data-stu-id="a796f-261">As a module user, there are cases where out-of-process invocation won't work:</span></span>

- <span data-ttu-id="a796f-262">当 PowerShell 远程处理因缺少使用权限或未启用而无法使用时。</span><span class="sxs-lookup"><span data-stu-id="a796f-262">When PowerShell remoting is unavailable because you don't have privileges to use it or it is not enabled.</span></span>
- <span data-ttu-id="a796f-263">当需要将来自输出的特定 .NET 类型作为方法或其他命令的输入时。</span><span class="sxs-lookup"><span data-stu-id="a796f-263">When a particular .NET type is needed from output as input to a method or another command.</span></span>
  <span data-ttu-id="a796f-264">在 PowerShell 远程处理上运行的命令将发出反序列化对象，而不是强类型 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="a796f-264">Commands running over PowerShell remoting emit deserialized objects rather than strongly-typed .NET objects.</span></span> <span data-ttu-id="a796f-265">这意味着方法调用和强类型 API 不能与通过远程处理导入的命令的输出一起使用。</span><span class="sxs-lookup"><span data-stu-id="a796f-265">This means that method calls and strongly typed APIs do not work with the output of commands imported over remoting.</span></span>

## <a name="more-robust-solutions"></a><span data-ttu-id="a796f-266">更可靠的解决方案</span><span class="sxs-lookup"><span data-stu-id="a796f-266">More robust solutions</span></span>

<span data-ttu-id="a796f-267">上述解决方案均有不起作用的情况和模块。</span><span class="sxs-lookup"><span data-stu-id="a796f-267">The previous solutions all had scenarios and modules that don't work.</span></span> <span data-ttu-id="a796f-268">但它们有一个共同的优点，那就是正确实现相对简单。</span><span class="sxs-lookup"><span data-stu-id="a796f-268">However, they also have the virtue of being relatively simple to implement correctly.</span></span> <span data-ttu-id="a796f-269">以下解决方案更可靠，但需要付出更多的努力才能正确实现，并且如果不谨慎编写，可能会引入一些细微的 bug。</span><span class="sxs-lookup"><span data-stu-id="a796f-269">The following solutions are more robust, but require more effort to implement correctly and can introduce subtle bugs if not written carefully.</span></span>

### <a name="loading-through-net-core-assembly-load-contexts"></a><span data-ttu-id="a796f-270">通过 .NET Core 程序集加载上下文进行加载</span><span class="sxs-lookup"><span data-stu-id="a796f-270">Loading through .NET Core Assembly Load Contexts</span></span>

<span data-ttu-id="a796f-271">.NET Core 1.0 中引入了[程序集加载上下文](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALC) 作为可实现的 API，专门用于解决将同一程序集的多个版本加载到同一运行时的需求。</span><span class="sxs-lookup"><span data-stu-id="a796f-271">[Assembly Load Contexts](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALCs) as an implementable API were introduced in .NET Core 1.0 to specifically address the need to load multiple versions of the same assembly into the same runtime.</span></span>

<span data-ttu-id="a796f-272">在 .NET Core 和 .NET 5 中，它们为加载程序集版本冲突问题提供了最可靠的解决方案。</span><span class="sxs-lookup"><span data-stu-id="a796f-272">Within .NET Core and .NET 5, they offer the most robust solution to the problem of loading conflicting versions of an assembly.</span></span> <span data-ttu-id="a796f-273">但是，自定义 ALC 在 .NET Framework 中不可用。</span><span class="sxs-lookup"><span data-stu-id="a796f-273">However, custom ALCs are not available in .NET Framework.</span></span> <span data-ttu-id="a796f-274">这意味着此解决方案仅适用于 PowerShell 6 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-274">This means that this solution only works in PowerShell 6 and above.</span></span>

<span data-ttu-id="a796f-275">当前，在 PowerShell 中使用 ALC 进行依赖项隔离的最佳示例是 PowerShell 编辑器服务，这是适用于 Visual Studio Code 的 PowerShell 扩展的语言服务器。</span><span class="sxs-lookup"><span data-stu-id="a796f-275">Currently, the best example of using an ALC for dependency isolation in PowerShell is in PowerShell Editor Services, the language server for the PowerShell extension for Visual Studio Code.</span></span> <span data-ttu-id="a796f-276">[ALC](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) 用于防止 PowerShell 编辑器服务自已的依赖项与 PowerShell 模块中的依赖项冲突。</span><span class="sxs-lookup"><span data-stu-id="a796f-276">An [ALC is used](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) to prevent PowerShell Editor Services' own dependencies from clashing with those in PowerShell modules.</span></span>

<span data-ttu-id="a796f-277">从概念上讲，使用 ALC 实现模块依赖项隔离很困难，但我们将通过一个最简单的示例来完成。</span><span class="sxs-lookup"><span data-stu-id="a796f-277">Implementing module dependency isolation with an ALC is conceptually difficult, but we will work through a minimal example.</span></span> <span data-ttu-id="a796f-278">假设我们有一个仅适用于 PowerShell 7 的简单模块。</span><span class="sxs-lookup"><span data-stu-id="a796f-278">Imagine we have a simple module that is only intended to work in PowerShell 7.</span></span>
<span data-ttu-id="a796f-279">源代码组织如下：</span><span class="sxs-lookup"><span data-stu-id="a796f-279">The source code is organized as follows:</span></span>

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

<span data-ttu-id="a796f-280">cmdlet 实现如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-280">The cmdlet implementation looks like this:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            // Here's where our dependency gets used
            Dependency.Use();
            // Something trivial to make our cmdlet do *something*
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="a796f-281">高度简化的清单如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-281">The (heavily simplified) manifest, looks like this:</span></span>

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

<span data-ttu-id="a796f-282">`csproj` 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-282">And the `csproj` looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="a796f-283">生成此模块时，生成的输出的布局如下：</span><span class="sxs-lookup"><span data-stu-id="a796f-283">When we build this module, the generated output has the following layout:</span></span>

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

<span data-ttu-id="a796f-284">在此示例中，我们的问题在于 `Shared.Dependency.dll` 程序集，这是我们假设的冲突依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-284">In this example, our problem is in the `Shared.Dependency.dll` assembly, which is our imaginary conflicting dependency.</span></span> <span data-ttu-id="a796f-285">我们需要将此依赖项放在 ALC 后面，以便我们可以使用特定于模块的版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-285">This is the dependency that we need to put behind an ALC so that we can use the module-specific version.</span></span>

<span data-ttu-id="a796f-286">我们需要重新设计模块，以便：</span><span class="sxs-lookup"><span data-stu-id="a796f-286">We need to re-engineer the module so that:</span></span>

- <span data-ttu-id="a796f-287">模块依赖项仅加载到自定义 ALC 中，而不加载到 PowerShell 的 ALC 中，因此不会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="a796f-287">Module dependencies are only loaded into our custom ALC, and not into PowerShell's ALC, so there can be no conflict.</span></span> <span data-ttu-id="a796f-288">此外，随着我们向项目中添加的依赖项增多，我们不想要不断添加更多代码来保持加载正常运行。</span><span class="sxs-lookup"><span data-stu-id="a796f-288">Moreover, as we add more dependencies to our project, we don't want to continuously add more code to keep loading working.</span></span> <span data-ttu-id="a796f-289">相反，我们想要可重用的通用依赖项解析逻辑。</span><span class="sxs-lookup"><span data-stu-id="a796f-289">Instead, we want reusable, generic dependency resolution logic.</span></span>
- <span data-ttu-id="a796f-290">在 PowerShell 中加载模块仍可正常运行。</span><span class="sxs-lookup"><span data-stu-id="a796f-290">Loading the module still works as normal in PowerShell.</span></span> <span data-ttu-id="a796f-291">PowerShell 模块系统所需的 cmdlet 和其他类型是在 PowerShell 自己的 ALC 中定义的。</span><span class="sxs-lookup"><span data-stu-id="a796f-291">Cmdlets and other types that the PowerShell module system needs are defined within PowerShell's own ALC.</span></span>

<span data-ttu-id="a796f-292">若要协调这两个要求，必须将模块分成两个程序集：</span><span class="sxs-lookup"><span data-stu-id="a796f-292">To mediate these two requirements, we must break up our module into two assemblies:</span></span>

- <span data-ttu-id="a796f-293">一个 cmdlet 程序集 `AlcModule.Cmdlets.dll`，其中包含 PowerShell 的模块系统正确加载模块所需的所有类型的定义。</span><span class="sxs-lookup"><span data-stu-id="a796f-293">A cmdlets assembly, `AlcModule.Cmdlets.dll`, that contains definitions of all the types that PowerShell's module system needs to load our module correctly.</span></span> <span data-ttu-id="a796f-294">即 `Cmdlet` 基类和实现 `IModuleAssemblyInitializer` 的类的任何实现，用于设置 `AssemblyLoadContext.Default.Resolving` 的事件处理程序，以通过自定义 ALC 正确加载 `AlcModule.Engine.dll`。</span><span class="sxs-lookup"><span data-stu-id="a796f-294">Namely, any implementations of the `Cmdlet` base class and the class that implements `IModuleAssemblyInitializer`, which sets up the event handler for `AssemblyLoadContext.Default.Resolving` to properly load `AlcModule.Engine.dll` through our custom ALC.</span></span> <span data-ttu-id="a796f-295">由于 PowerShell 7 故意隐藏了在其他 ALC 中加载的程序集中定义的类型，因此任何要公开给 PowerShell 的类型也必须在此处进行定义。</span><span class="sxs-lookup"><span data-stu-id="a796f-295">Since PowerShell 7 deliberately hides types defined in assemblies loaded in other ALCs, any types that are meant to be publicly exposed to PowerShell must also be defined here.</span></span> <span data-ttu-id="a796f-296">最后，需要在此程序集中定义自定义 ALC。</span><span class="sxs-lookup"><span data-stu-id="a796f-296">Finally, our custom ALC definition needs to be defined in this assembly.</span></span> <span data-ttu-id="a796f-297">除此之外，此程序集中包含的代码应尽可能少。</span><span class="sxs-lookup"><span data-stu-id="a796f-297">Beyond that, as little code as possible should live in this assembly.</span></span>
- <span data-ttu-id="a796f-298">一个引擎程序集 `AlcModule.Engine.dll`，用于处理模块的实际实现。</span><span class="sxs-lookup"><span data-stu-id="a796f-298">An engine assembly, `AlcModule.Engine.dll`, that handles the actual implementation of the module.</span></span>
  <span data-ttu-id="a796f-299">来自此程序集的类型可在 PowerShell ALC 中获取，但最初将通过自定义 ALC 进行加载。</span><span class="sxs-lookup"><span data-stu-id="a796f-299">Types from this are available in the PowerShell ALC, but it will initially be loaded through our custom ALC.</span></span> <span data-ttu-id="a796f-300">它的依赖项仅加载到自定义 ALC 中。</span><span class="sxs-lookup"><span data-stu-id="a796f-300">Its dependencies are only loaded into the custom ALC.</span></span> <span data-ttu-id="a796f-301">实际上，这成为了两个 ALC 之间的桥梁。</span><span class="sxs-lookup"><span data-stu-id="a796f-301">Effectively, this becomes a _bridge_ between the two ALCs.</span></span>

<span data-ttu-id="a796f-302">利用这种桥梁概念，新程序集情况如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-302">Using this bridge concept, our new assembly situation looks like this:</span></span>

![表示 AlcModule.Engine.dll 桥接两个 ALC 的图](./media/resolving-dependency-conflicts/alc-diagram.jpg)

<span data-ttu-id="a796f-304">若要确保默认 ALC 的依赖项探测逻辑不会解析要加载到自定义 ALC 中的依赖项，我们需要在不同的目录中分隔此模块的这两个部分。</span><span class="sxs-lookup"><span data-stu-id="a796f-304">To make sure the default ALC's dependency probing logic does not resolve the dependencies to be loaded into the custom ALC, we need to separate these two parts of the module in different directories.</span></span> <span data-ttu-id="a796f-305">新模块布局的结构如下：</span><span class="sxs-lookup"><span data-stu-id="a796f-305">The new module layout has the following structure:</span></span>

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

<span data-ttu-id="a796f-306">为了查看实现的更改方式，我们将从 `AlcModule.Engine.dll` 的实现开始：</span><span class="sxs-lookup"><span data-stu-id="a796f-306">To see how the implementation changes, we'll start with the implementation of `AlcModule.Engine.dll`:</span></span>

```csharp
using Shared.Dependency;

namespace AlcModule.Engine
{
    public class AlcEngine
    {
        public static void Use()
        {
            Dependency.Use();
        }
    }
}
```

<span data-ttu-id="a796f-307">这是用于依赖项 `Shared.Dependency.dll` 的简单容器，但应将其视为针对其他程序集中的 cmdlet 为 PowerShell 封装的功能的 .NET API。</span><span class="sxs-lookup"><span data-stu-id="a796f-307">This is a simple container for the dependency, `Shared.Dependency.dll`, but you should think of it as the .NET API for your functionality that the cmdlets in the other assembly wrap for PowerShell.</span></span>

<span data-ttu-id="a796f-308">`AlcModule.Cmdlets.dll` 中的 cmdlet 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-308">The cmdlet in `AlcModule.Cmdlets.dll` looks like this:</span></span>

```csharp
// Reference our module's Engine implementation here
using AlcModule.Engine;

namespace AlcModule.Cmdlets
{
    [Cmdlet(VerbsDiagnostic.Test, "AlcModule")]
    public class TestAlcModuleCommand : Cmdlet
    {
        protected override void EndProcessing()
        {
            AlcEngine.Use();
            WriteObject("done!");
        }
    }
}
```

<span data-ttu-id="a796f-309">此时，如果我们要加载 AlcModule 并运行 `Test-AlcModule`，则当默认 ALC 尝试加载 `Alc.Engine.dll` 以运行 `EndProcessing()` 时，我们将收到 `FileNotFoundException`。</span><span class="sxs-lookup"><span data-stu-id="a796f-309">At this point, if we were to load **AlcModule** and run `Test-AlcModule`, we get a `FileNotFoundException` when the default ALC tries to load `Alc.Engine.dll` to run `EndProcessing()`.</span></span> <span data-ttu-id="a796f-310">这样很好，因为这意味着默认 ALC 找不到我们要隐藏的依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-310">This is good, since it means the default ALC can't find the dependencies we want to hide.</span></span>

<span data-ttu-id="a796f-311">现在，我们需要向 `AlcModule.Cmdlets.dll` 添加代码，以告知它如何解析 `AlcModule.Engine.dll`。</span><span class="sxs-lookup"><span data-stu-id="a796f-311">Now we need to add code to `AlcModule.Cmdlets.dll` so that it knows how to resolve `AlcModule.Engine.dll`.</span></span> <span data-ttu-id="a796f-312">首先，我们必须定义自定义 ALC，它将解析模块的 `Dependencies` 目录中的程序集：</span><span class="sxs-lookup"><span data-stu-id="a796f-312">First we must define our custom ALC that will resolve assemblies from our module's `Dependencies` directory:</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _dependencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                _dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

<span data-ttu-id="a796f-313">然后，我们需要将自定义 ALC 挂接到默认 ALC 的 `Resolving` 事件，该事件是应用程序域上 `AssemblyResolve` 事件的 ALC 版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-313">Then we need to hook up our custom ALC to the default ALC's `Resolving` event, which is the ALC version of the `AssemblyResolve` event on Application Domains.</span></span> <span data-ttu-id="a796f-314">调用 `EndProcessing()` 时，将触发此事件以查找 `AlcModule.Engine.dll`。</span><span class="sxs-lookup"><span data-stu-id="a796f-314">This event is fired to find `AlcModule.Engine.dll` when `EndProcessing()` is called.</span></span>

```csharp
namespace AlcModule.Cmdlets
{
    public class AlcModuleResolveEventHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // Get the path of the dependency directory.
        // In this case we find it relative to the AlcModule.Cmdlets.dll location
        private static readonly string s_dependencyDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        private static readonly AlcModuleAssemblyLoadContext s_dependencyAlc = new AlcModuleAssemblyLoadContext(s_dependencyDirPath);

        public void OnImport()
        {
            // Add the Resolving event handler here
            AssemblyLoadContext.Default.Resolving += ResolveAlcEngine;
        }

        public void OnRemove()
        {
          // Remove the Resolving event handler here
          AssemblyLoadContext.Default.Resolving -= ResolveAlcEngine;
        }

        private static Assembly ResolveAlcEngine(
            AssemblyLoadContext defaultAlc,
            AssemblyName assemblyToResolve)
        {
            // We only want to resolve the Alc.Engine.dll assembly here.
            // Because this will be loaded into the custom ALC,
            // all of *its* dependencies will be resolved
            // by the logic we defined for that ALC's implementation.
            //
            // Note that we are safe in our assumption that the name is enough
            // to distinguish our assembly here,
            // since it's unique to our module.
            // There should be no other AlcModule.Engine.dll on the system.
            if (!assemblyToResolve.Name.Equals("AlcModule.Engine"))
            {
                return null;
            }

            // Allow our ALC to handle the directory discovery concept
            //
            // This is where Alc.Engine.dll is loaded into our custom ALC
            // and then passed through into PowerShell's ALC,
            // becoming the bridge between both
            return s_dependencyAlc.LoadFromAssemblyName(assemblyToResolve);
        }
    }
}
```

<span data-ttu-id="a796f-315">通过新实现，查看在加载模块并运行 `Test-AlcModule` 时发生的调用序列：</span><span class="sxs-lookup"><span data-stu-id="a796f-315">With the new implementation, take a look at the sequence of calls that occurs when the module is loaded and `Test-AlcModule` is run:</span></span>

![使用自定义 ALC 加载依赖项的调用序列图](./media/resolving-dependency-conflicts/alc-sequence.png)

<span data-ttu-id="a796f-317">兴趣点包括：</span><span class="sxs-lookup"><span data-stu-id="a796f-317">Some points of interest are:</span></span>

- <span data-ttu-id="a796f-318">模块加载并设置 `Resolving` 事件时，将首先运行 `IModuleAssemblyInitializer`。</span><span class="sxs-lookup"><span data-stu-id="a796f-318">The `IModuleAssemblyInitializer` is run first when the module loads and sets the `Resolving` event.</span></span>
- <span data-ttu-id="a796f-319">在运行 `Test-AlcModule` 并调用其 `EndProcessing()` 方法之前，不会加载依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-319">We don't load the dependencies until `Test-AlcModule` is run and its `EndProcessing()` method is called.</span></span>
- <span data-ttu-id="a796f-320">调用 `EndProcessing()` 时，默认 ALC 无法找到 `AlcModule.Engine.dll` 并触发 `Resolving` 事件。</span><span class="sxs-lookup"><span data-stu-id="a796f-320">When `EndProcessing()` is called, the default ALC fails to find `AlcModule.Engine.dll` and fires the `Resolving` event.</span></span>
- <span data-ttu-id="a796f-321">事件处理程序会将自定义 ALC 挂接到默认 ALC 并仅加载 `AlcModule.Engine.dll`。</span><span class="sxs-lookup"><span data-stu-id="a796f-321">Our event handler hooks up the custom ALC to the default ALC and loads `AlcModule.Engine.dll` only.</span></span>
- <span data-ttu-id="a796f-322">在 `AlcModule.Engine.dll` 内调用 `AlcEngine.Use()` 时，自定义 ALC 将再次启动以解析 `Shared.Dependency.dll`。</span><span class="sxs-lookup"><span data-stu-id="a796f-322">When `AlcEngine.Use()` is called within `AlcModule.Engine.dll`, the custom ALC again kicks in to resolve `Shared.Dependency.dll`.</span></span> <span data-ttu-id="a796f-323">具体而言，它始终加载 `Shared.Dependency.dll`，因为它永远不会与默认 ALC 中的任何内容冲突，而只会在 `Dependencies` 目录中进行查找。</span><span class="sxs-lookup"><span data-stu-id="a796f-323">Specifically, it always loads _our_ `Shared.Dependency.dll` since it never conflicts with anything in the default ALC and only looks in our `Dependencies` directory.</span></span>

<span data-ttu-id="a796f-324">汇编实现，新源代码布局如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-324">Assembling the implementation, our new source code layout looks like this:</span></span>

```
+ AlcModule.psd1
+ src/
  + AlcModule.Cmdlets/
  | + AlcModule.Cmdlets.csproj
  | + TestAlcModuleCommand.cs
  | + AlcModuleAssemblyLoadContext.cs
  | + AlcModuleInitializer.cs
  |
  + AlcModule.Engine/
  | + AlcModule.Engine.csproj
  | + AlcEngine.cs
```

<span data-ttu-id="a796f-325">AlcModule.Cmdlets.csproj 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-325">AlcModule.Cmdlets.csproj looks like:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <ProjectReference Include="..\AlcModule.Engine\AlcModule.Engine.csproj" />
    <PackageReference Include="Microsoft.PowerShell.Sdk" Version="7.0.1" PrivateAssets="all" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="a796f-326">AlcModule.Engine.csproj 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a796f-326">AlcModule.Engine.csproj looks like this:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Shared.Dependency" Version="1.0.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="a796f-327">因此，生成模块时，我们的策略是：</span><span class="sxs-lookup"><span data-stu-id="a796f-327">So, when we build the module, our strategy is:</span></span>

- <span data-ttu-id="a796f-328">生成 `AlcModule.Engine`</span><span class="sxs-lookup"><span data-stu-id="a796f-328">Build `AlcModule.Engine`</span></span>
- <span data-ttu-id="a796f-329">生成 `AlcModule.Cmdlets`</span><span class="sxs-lookup"><span data-stu-id="a796f-329">Build `AlcModule.Cmdlets`</span></span>
- <span data-ttu-id="a796f-330">将 `AlcModule.Engine` 中的所有内容复制到 `Dependencies` 目录，并记住所复制的内容</span><span class="sxs-lookup"><span data-stu-id="a796f-330">Copy everything from `AlcModule.Engine` into the `Dependencies` directory, and remember what we copied</span></span>
- <span data-ttu-id="a796f-331">将 `AlcModule.Cmdlets` 中所有不在 `AlcModule.Engine` 中的内容复制到基础模块目录中</span><span class="sxs-lookup"><span data-stu-id="a796f-331">Copy everything from `AlcModule.Cmdlets` that wasn't in `AlcModule.Engine` into the base module directory</span></span>

<span data-ttu-id="a796f-332">由于此处的模块布局对于依赖项分隔至关重要，因此可从源根目录使用以下生成脚本：</span><span class="sxs-lookup"><span data-stu-id="a796f-332">Since the module layout here is so crucial to dependency separation, here's a build script to use from the source root:</span></span>

```powershell
param(
    # The .NET build configuration
    [ValidateSet('Debug', 'Release')]
    [string]
    $Configuration = 'Debug'
)

# Convenient reusable constants
$mod = "AlcModule"
$netcore = "netcoreapp3.1"
$copyExtensions = @('.dll', '.pdb')

# Source code locations
$src = "$PSScriptRoot/src"
$engineSrc = "$src/$mod.Engine"
$cmdletsSrc = "$src/$mod.Cmdlets"

# Generated output locations
$outDir = "$PSScriptRoot/out/$mod"
$outDeps = "$outDir/Dependencies"

# Build AlcModule.Engine
Push-Location $engineSrc
dotnet publish -c $Configuration
Pop-Location

# Build AlcModule.Cmdlets
Push-Location $cmdletsSrc
dotnet publish -c $Configuration
Pop-Location

# Ensure out directory exists and is clean
Remove-Item -Path $outDir -Recurse -ErrorAction Ignore
New-Item -Path $outDir -ItemType Directory
New-Item -Path $outDeps -ItemType Directory

# Copy manifest
Copy-Item -Path "$PSScriptRoot/$mod.psd1"

# Copy each Engine asset and remember it
$deps = [System.Collections.Generic.Hashtable[string]]::new()
Get-ChildItem -Path "$engineSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { $_.Extension -in $copyExtensions } |
    ForEach-Object { [void]$deps.Add($_.Name); Copy-Item -Path $_.FullName -Destination $outDeps }

# Now copy each Cmdlets asset, not taking any found in Engine
Get-ChildItem -Path "$cmdletsSrc/bin/$Configuration/$netcore/publish/" |
    Where-Object { -not $deps.Contains($_.Name) -and $_.Extension -in $copyExtensions } |
    ForEach-Object { Copy-Item -Path $_.FullName -Destination $outDir }
```

<span data-ttu-id="a796f-333">最后，我们提供了一种通用方法来使用程序集加载上下文隔离模块的依赖项，随着时间的推移、依赖项不断增加，该方法仍然可靠。</span><span class="sxs-lookup"><span data-stu-id="a796f-333">Finally, we have a general way to use an Assembly Load Context to isolate our module's dependencies that remains robust over time as more dependencies are added.</span></span>

<span data-ttu-id="a796f-334">有关更详细的示例，请转到此 [GitHub 存储库](https://github.com/rjmholt/ModuleDependencyIsolationExample)。</span><span class="sxs-lookup"><span data-stu-id="a796f-334">For a more detailed example, go to this [GitHub repository](https://github.com/rjmholt/ModuleDependencyIsolationExample).</span></span> <span data-ttu-id="a796f-335">此示例演示如何迁移模块以使用 ALC，同时使该模块在 .NET Framework 中正常运行。</span><span class="sxs-lookup"><span data-stu-id="a796f-335">This example demonstrates how to migrate a module to use an ALC, while keeping that module working in .NET Framework.</span></span> <span data-ttu-id="a796f-336">它还演示了如何使用 .NET Standard 和 PowerShell Standard 来简化核心实现。</span><span class="sxs-lookup"><span data-stu-id="a796f-336">It also show how to use .NET Standard and PowerShell Standard to simplify the core implementation.</span></span>

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a><span data-ttu-id="a796f-337">用于通过 `Assembly.LoadFile()` 并行加载的程序集解析处理程序</span><span class="sxs-lookup"><span data-stu-id="a796f-337">Assembly resolve handler for side-by-side loading with `Assembly.LoadFile()`</span></span>

<span data-ttu-id="a796f-338">另一种实现并行程序集加载的方法是将 `AssemblyResolve` 事件挂接到 `Assembly.LoadFile()`，这种方法可能更加简单。</span><span class="sxs-lookup"><span data-stu-id="a796f-338">Another, possibly simpler, way to achieve side-by-side assembly loading is to hook up an `AssemblyResolve` event to `Assembly.LoadFile()`.</span></span> <span data-ttu-id="a796f-339">使用 `Assembly.LoadFile()` 的优势在于，它是最简单的实现解决方案，并同时适用于 .NET Core 和 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="a796f-339">Using `Assembly.LoadFile()` has the advantage of being the simplest solution to implement and works with both .NET Core and .NET Framework.</span></span>

<span data-ttu-id="a796f-340">为了说明这一点，我们来看一个简单的实现示例，该示例结合了动态绑定重定向示例和上面的程序集加载上下文示例的理念。</span><span class="sxs-lookup"><span data-stu-id="a796f-340">To show this, let's take a look at a quick example of an implementation that combines ideas from our dynamic binding redirect example, and the Assembly Load Context example above.</span></span>

<span data-ttu-id="a796f-341">我们将此模块称为 LoadFileModule，它有一个简单的命令 `Test-LoadFile [-Path] <path>`。</span><span class="sxs-lookup"><span data-stu-id="a796f-341">We'll call this module **LoadFileModule**, which has a trivial command `Test-LoadFile [-Path] <path>`.</span></span> <span data-ttu-id="a796f-342">此模块采用 `CsvHelper` 程序集（版本 15.0.5）的依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-342">This module takes a dependency on the `CsvHelper` assembly (version 15.0.5).</span></span>

<span data-ttu-id="a796f-343">与 ALC 模块一样，必须首先将模块拆分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="a796f-343">As with the ALC module, we must first split up the module into two pieces.</span></span>

<span data-ttu-id="a796f-344">第一个部分执行实际的实现 `LoadFileModule.Engine`：</span><span class="sxs-lookup"><span data-stu-id="a796f-344">The first part does the actual implementation, `LoadFileModule.Engine`:</span></span>

```csharp
using CsvHelper;

namespace LoadFileModule.Engine
{
    public class Runner
    {
        public void Use(string path)
        {
            // Here's where we use the CsvHelper dependency
            using (var reader = new StreamReader(path))
            using (var csvReader = new CsvReader(reader, CultureInfo.InvariantCulture))
            {
                // Imagine we do something useful here...
            }
        }
    }
}
```

<span data-ttu-id="a796f-345">第二个部分是 PowerShell 直接加载的 `LoadFileModule.Cmdlets`。</span><span class="sxs-lookup"><span data-stu-id="a796f-345">The second part is what PowerShell loads directly, `LoadFileModule.Cmdlets`.</span></span> <span data-ttu-id="a796f-346">使用与 ALC 模块类似的策略，将依赖项隔离在不同的目录中。</span><span class="sxs-lookup"><span data-stu-id="a796f-346">We use a strategy similar to the ALC module, where we isolate dependencies in a separate directory.</span></span> <span data-ttu-id="a796f-347">但这次，使用 resolve 事件而不只是 `LoadFileModule.Engine.dll` 来加载所有程序集。</span><span class="sxs-lookup"><span data-stu-id="a796f-347">But this time, we load all assemblies in with a resolve event rather than just `LoadFileModule.Engine.dll`.</span></span>

```csharp
using LoadFileModule.Engine;

namespace LoadFileModule.Cmdlets
{
    // Actual cmdlet definition
    [Cmdlet(VerbsDiagnostic.Test, "LoadFile")]
    public class TestLoadFileCommand : Cmdlet
    {
        [Parameter(Mandatory = true)]
        public string Path { get; set; }

        protected override void EndProcessing()
        {
            // Here's where we use LoadFileModule.Engine
            new Runner().Use(Path);
        }
    }

    // This class controls our dependency resolution
    public class ModuleContextHandler : IModuleAssemblyInitializer, IModuleAssemblyCleanup
    {
        // We catalog our dependencies here to ensure we don't load anything else
        private static IReadOnlyDictionary<string, int> s_dependencies = new Dictionary<string, int>
        {
            { "CsvHelper", 15 },
        };

        // Set up the path to our dependency directory within the module
        private static string s_dependenciesDirPath = Path.GetFullPath(
            Path.Combine(
                Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location),
                "Dependencies"));

        // This makes sure we only try to resolve dependencies when the module is loaded
        private static bool s_engineLoaded = false;

        public void OnImport()
          {
            // Set up our event when the module is loaded
            AppDomain.CurrentDomain.AssemblyResolve += HandleResolveEvent;
        }

        public void OnRemove(PSModuleInfo psModuleInfo)
        {
            // Unset the event when the module is unloaded
            AppDomain.CurrentDomain.AssemblyResolve -= HandleResolveEvent;
        }

        private static Assembly HandleResolveEvent(object sender, ResolveEventArgs args)
        {
            var asmName = new AssemblyName(args.Name);

            // First we want to know if this is the top-level assembly
            if (asmName.Name.Equals("LoadFileModule.Engine"))
            {
                s_engineLoaded = true;
                return Assembly.LoadFile(Path.Combine(s_dependenciesDirPath, "Unrelated.Engine.dll"));
            }

            // Otherwise, if that assembly has been loaded, we must try to resolve its dependencies too
            if (s_engineLoaded
                && s_dependencies.TryGetValue(asmName.Name, out int requiredMajorVersion)
                && asmName.Version.Major == requiredMajorVersion)
            {
                string asmPath = Path.Combine(s_dependenciesDirPath, $"{asmName.Name}.dll");
                return Assembly.LoadFile(asmPath);
            }

            return null;
        }
    }
}
```

<span data-ttu-id="a796f-348">最后，此模块的布局也类似于 ALC 模块：</span><span class="sxs-lookup"><span data-stu-id="a796f-348">Finally, the layout of the module is also similar to the ALC module:</span></span>

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

<span data-ttu-id="a796f-349">借助此结构，LoadFileModule 现在支持与使用 CsvHelper 的依赖项的其他模块一起加载 。</span><span class="sxs-lookup"><span data-stu-id="a796f-349">With this structure in place, **LoadFileModule** now supports being loaded alongside other modules with a dependency on **CsvHelper**.</span></span>

<span data-ttu-id="a796f-350">因为处理程序适用于整个应用程序域中的所有 `AssemblyResolve` 事件，所以我们需要在此处进行一些具体的设计选择：</span><span class="sxs-lookup"><span data-stu-id="a796f-350">Because our handler applies to **all** `AssemblyResolve` events across the Application Domain, we need to make some specific design choices here:</span></span>

- <span data-ttu-id="a796f-351">为缩减事件可能会干扰其他加载的时段，我们仅在加载 `LoadFileModule.Engine.dll` 后才开始处理常规依赖项加载。</span><span class="sxs-lookup"><span data-stu-id="a796f-351">To narrow the window in which our event may interfere with other loading, we only start handling general dependency loading after `LoadFileModule.Engine.dll` has been loaded.</span></span>
- <span data-ttu-id="a796f-352">将 `LoadFileModule.Engine.dll` 推送到 Dependencies 目录中，以便通过 `LoadFile()` 调用而不是 PowerShell 进行加载。</span><span class="sxs-lookup"><span data-stu-id="a796f-352">We push `LoadFileModule.Engine.dll` out into the Dependencies directory, so that it's loaded by a `LoadFile()` call rather than by PowerShell.</span></span> <span data-ttu-id="a796f-353">这意味着，即使在 PowerShell 中加载了另一个 `CsvHelper.dll`（例如），它自己的依赖项加载也始终会引发 `AssemblyResolve` 事件。</span><span class="sxs-lookup"><span data-stu-id="a796f-353">This means its own dependency loads always raise an `AssemblyResolve` event, even if another `CsvHelper.dll` (for example) is loaded in PowerShell.</span></span>
  <span data-ttu-id="a796f-354">这使我们有机会找到正确的依赖项。</span><span class="sxs-lookup"><span data-stu-id="a796f-354">This gives us the opportunity to find the correct dependency.</span></span>
- <span data-ttu-id="a796f-355">由于必须只解析模块的特定依赖项，因此我们不得不在处理程序中编码依赖项名称和版本的字典。</span><span class="sxs-lookup"><span data-stu-id="a796f-355">Since we must only resolve the specific dependencies for our module, we're forced to code a dictionary of dependency names and versions into our handler.</span></span> <span data-ttu-id="a796f-356">在特定情况下，可以使用 `ResolveEventArgs.RequestingAssembly` 属性来确定模块是否正在请求 `CsvHelper`。</span><span class="sxs-lookup"><span data-stu-id="a796f-356">In our particular case, it would be possible to use the `ResolveEventArgs.RequestingAssembly` property to work out whether `CsvHelper` is being requested by our module.</span></span> <span data-ttu-id="a796f-357">但这并不适用于依赖项的依赖项；例如，如果 `CsvHelper` 本身引发了 `AssemblyResolve` 事件。</span><span class="sxs-lookup"><span data-stu-id="a796f-357">But this doesn't work for dependencies of dependencies; for example, if `CsvHelper` itself raised an `AssemblyResolve` event.</span></span> <span data-ttu-id="a796f-358">若要实现此目的，还有其他更困难的方法，例如，将请求的程序集与 `Dependencies` 目录中的程序集的元数据进行比较。</span><span class="sxs-lookup"><span data-stu-id="a796f-358">There are other, harder ways to do this, such as comparing requested assemblies to the metadata of assemblies in the `Dependencies` directory.</span></span> <span data-ttu-id="a796f-359">但在此示例中，我们更明确地进行了此检查，以突出问题并简化示例。</span><span class="sxs-lookup"><span data-stu-id="a796f-359">But, in this example, we've made this checking more explicit to both highlight the issue and simplify the example.</span></span>

<span data-ttu-id="a796f-360">这是 `LoadFile()` 策略与 ALC 策略之间的主要区别：`AssemblyResolve` 事件必须为应用程序域中的所有加载提供服务，这使得依赖项解析更难与其他模块混杂在一起。</span><span class="sxs-lookup"><span data-stu-id="a796f-360">This is the key difference between the `LoadFile()` strategy and the ALC strategy: the `AssemblyResolve` event must service all loads in the Application Domain, making it much harder to keep our dependency resolution from being tangled with other modules.</span></span> <span data-ttu-id="a796f-361">但是，由于 .NET Framework 中缺少 ALC，因此可以理解为何存在此选项。</span><span class="sxs-lookup"><span data-stu-id="a796f-361">However, the lack of ALCs in .NET Framework makes this option worth understanding.</span></span>

### <a name="custom-application-domains"></a><span data-ttu-id="a796f-362">自定义应用程序域</span><span class="sxs-lookup"><span data-stu-id="a796f-362">Custom Application Domains</span></span>

<span data-ttu-id="a796f-363">程序集隔离的最后也是最极端的选项是使用自定义应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a796f-363">The final and most extreme option for assembly isolation is to use custom Application Domains.</span></span>
<span data-ttu-id="a796f-364">应用程序域（采用复数形式）仅适用于 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="a796f-364">Application Domains (used in the plural) are only available in .NET Framework.</span></span> <span data-ttu-id="a796f-365">它们用于在 .NET 应用程序的各个部分之间提供进程内隔离。</span><span class="sxs-lookup"><span data-stu-id="a796f-365">They are used to provide in-process isolation between parts of a .NET application.</span></span> <span data-ttu-id="a796f-366">一种用途是在同一进程中将程序集加载彼此隔离。</span><span class="sxs-lookup"><span data-stu-id="a796f-366">One of the uses is to isolate assembly loads from each other within the same process.</span></span>

<span data-ttu-id="a796f-367">但是，应用程序域是序列化边界。</span><span class="sxs-lookup"><span data-stu-id="a796f-367">However, Application Domains are serialization boundaries.</span></span> <span data-ttu-id="a796f-368">一个应用程序域中的对象不能供其他应用程序域中的对象直接引用和使用。</span><span class="sxs-lookup"><span data-stu-id="a796f-368">Objects in one Application Domain can't be referenced and used directly by objects in another Application Domain.</span></span> <span data-ttu-id="a796f-369">通过实现 `MarshalByRefObject` 可解决此问题。</span><span class="sxs-lookup"><span data-stu-id="a796f-369">You can work around this by implementing `MarshalByRefObject`.</span></span> <span data-ttu-id="a796f-370">但如果不控制类型（常见于依赖项），就不可能在此处强制实现。</span><span class="sxs-lookup"><span data-stu-id="a796f-370">But when you don't control the types, as is often the case with dependencies, it's not possible to force an implementation here.</span></span> <span data-ttu-id="a796f-371">唯一的解决方案是进行大型体系结构更改。</span><span class="sxs-lookup"><span data-stu-id="a796f-371">The only solution is to make large architectural changes.</span></span> <span data-ttu-id="a796f-372">序列化边界也会对性能产生严重影响。</span><span class="sxs-lookup"><span data-stu-id="a796f-372">The serialization boundary also has serious performance implications.</span></span>

<span data-ttu-id="a796f-373">由于应用程序域具有这一严重限制，实现起来很复杂，并且仅适用于 .NET Framework，因此本文将不提供其使用方式的示例。</span><span class="sxs-lookup"><span data-stu-id="a796f-373">Because Application Domains have this serious limitation, are complicated to implement, and only work in .NET Framework, we won't give an example of how you might use them here.</span></span> <span data-ttu-id="a796f-374">虽然值得一提的是，它们是一种可能的解决方案，但不建议使用。</span><span class="sxs-lookup"><span data-stu-id="a796f-374">While they're worth mentioning as a possibility, they're not recommended.</span></span>

<span data-ttu-id="a796f-375">如果有兴趣尝试使用自定义应用程序域，以下链接可能会有所帮助：</span><span class="sxs-lookup"><span data-stu-id="a796f-375">If you're interested in trying to use a custom Application Domain, the following links might help:</span></span>

- [<span data-ttu-id="a796f-376">有关应用程序域的概念性文档</span><span class="sxs-lookup"><span data-stu-id="a796f-376">Conceptual documentation on Application Domains</span></span>](/dotnet/framework/app-domains/application-domains)
- [<span data-ttu-id="a796f-377">使用应用程序域的示例</span><span class="sxs-lookup"><span data-stu-id="a796f-377">Examples for using Application Domains</span></span>](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a><span data-ttu-id="a796f-378">不适用于 PowerShell 的依赖项冲突解决方案</span><span class="sxs-lookup"><span data-stu-id="a796f-378">Solutions for dependency conflicts that don't work for PowerShell</span></span>

<span data-ttu-id="a796f-379">最后，我们将介绍在研究 .NET 中的 .NET 依赖项冲突时提出的一些看好的可能解决方案，但通常不适用于 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a796f-379">Finally, we'll address some possibilities that come up when researching .NET dependency conflicts in .NET that can look promising, but generally won't work for PowerShell.</span></span>

<span data-ttu-id="a796f-380">这些解决方案有共同的主题，即针对在其中控制应用程序的环境（可能整个计算机），更改部署配置。</span><span class="sxs-lookup"><span data-stu-id="a796f-380">These solutions have the common theme that they are changes to deployment configurations for an environment where you control the application and possibly the entire machine.</span></span> <span data-ttu-id="a796f-381">这些解决方案面向的是 Web 服务器和部署到服务器环境的其他应用程序之类的场景，其中环境旨在托管应用程序，并可由进行部署的用户自由配置。</span><span class="sxs-lookup"><span data-stu-id="a796f-381">These solutions are oriented toward scenarios like web servers and other applications deployed to server environments, where the environment is intended to host the application and is free to be configured by the deploying user.</span></span> <span data-ttu-id="a796f-382">它们往往也面向 .NET Framework，这意味着它们不适用于 PowerShell 6 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-382">They also tend to be very much .NET Framework oriented, meaning they do not work with PowerShell 6 or above.</span></span>

<span data-ttu-id="a796f-383">如果你知道模块仅在完全受你控制的 Windows PowerShell 5.1 环境中使用，则可以选择其中一些内容。</span><span class="sxs-lookup"><span data-stu-id="a796f-383">If you know that your module is only used in Windows PowerShell 5.1 environments that you have total control over, some of these may be options.</span></span> <span data-ttu-id="a796f-384">但是，模块通常不应像这样修改全局计算机状态。</span><span class="sxs-lookup"><span data-stu-id="a796f-384">In general however, **modules should not modify global machine state like this**.</span></span> <span data-ttu-id="a796f-385">这种操作可能会中断配置，导致 `powershell.exe`、其他模块或其他从属应用程序出现问题，从而导致模块意外失败。</span><span class="sxs-lookup"><span data-stu-id="a796f-385">It can break configurations that cause problems in `powershell.exe`, other modules, or other dependent applications that cause your module to fail in unexpected ways.</span></span>

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a><span data-ttu-id="a796f-386">使用 app.config 进行静态绑定重定向以强制使用相同的依赖项版本</span><span class="sxs-lookup"><span data-stu-id="a796f-386">Static binding redirect with app.config to force using the same dependency version</span></span>

<span data-ttu-id="a796f-387">.NET Framework 应用程序可以利用 `app.config` 文件以声明方式配置应用程序的某些行为。</span><span class="sxs-lookup"><span data-stu-id="a796f-387">.NET Framework applications can take advantage of an `app.config` file to configure some of the application's behaviors declaratively.</span></span> <span data-ttu-id="a796f-388">可以编写一个 `app.config` 条目来配置程序集绑定，以将程序集加载重定向到特定版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-388">It's possible to write an `app.config` entry that configures assembly binding to redirect assembly loading to a particular version.</span></span>

<span data-ttu-id="a796f-389">对于 PowerShell，此操作存在以下两个问题：</span><span class="sxs-lookup"><span data-stu-id="a796f-389">Two issues with this for PowerShell are:</span></span>

- <span data-ttu-id="a796f-390">.NET Core 不支持 `app.config`，所以此解决方案仅适用于 `powershell.exe`。</span><span class="sxs-lookup"><span data-stu-id="a796f-390">.NET Core does not support `app.config`, so this solution only applies to `powershell.exe`.</span></span>
- <span data-ttu-id="a796f-391">`powershell.exe` 是位于 `System32` 目录中的共享应用程序。</span><span class="sxs-lookup"><span data-stu-id="a796f-391">`powershell.exe` is a shared application that lives in the `System32` directory.</span></span> <span data-ttu-id="a796f-392">在许多系统上，模块可能无法修改其内容。</span><span class="sxs-lookup"><span data-stu-id="a796f-392">It's likely that your module won't be able to modify its contents on many systems.</span></span> <span data-ttu-id="a796f-393">即使可以，修改 `app.config` 也可能会中断现有配置或影响加载其他模块。</span><span class="sxs-lookup"><span data-stu-id="a796f-393">Even if it can, modifying the `app.config` could break an existing configuration or affect the loading of other modules.</span></span>

### <a name="setting-codebase-with-appconfig"></a><span data-ttu-id="a796f-394">通过 app.config 设置 `codebase`</span><span class="sxs-lookup"><span data-stu-id="a796f-394">Setting `codebase` with app.config</span></span>

<span data-ttu-id="a796f-395">出于相同的原因，尝试在 `app.config` 中配置 `codebase` 设置在 PowerShell 模块中不起作用。</span><span class="sxs-lookup"><span data-stu-id="a796f-395">For the same reasons, trying to configure the `codebase` setting in `app.config` is not going to work in PowerShell modules.</span></span>

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a><span data-ttu-id="a796f-396">在全局程序集缓存 (GAC) 中安装依赖项</span><span class="sxs-lookup"><span data-stu-id="a796f-396">Installing dependencies to the Global Assembly Cache (GAC)</span></span>

<span data-ttu-id="a796f-397">若要解决 .NET Framework 中依赖项版本冲突，另一种方法是将依赖项安装到 GAC 中，以便可以从 GAC 并行加载不同的版本。</span><span class="sxs-lookup"><span data-stu-id="a796f-397">Another way to resolve dependency version conflicts in .NET Framework is to install dependencies to the GAC, so that different versions can be loaded side-by-side from the GAC.</span></span>

<span data-ttu-id="a796f-398">同样，对于 PowerShell 模块，这里的主要问题是：</span><span class="sxs-lookup"><span data-stu-id="a796f-398">Again, for PowerShell modules, the chief issues here are:</span></span>

- <span data-ttu-id="a796f-399">GAC 仅适用于 .NET Framework，因此对 PowerShell 6 及更高版本没有帮助。</span><span class="sxs-lookup"><span data-stu-id="a796f-399">The GAC only applies to .NET Framework, so this does not help in PowerShell 6 and above.</span></span>
- <span data-ttu-id="a796f-400">将程序集安装到 GAC 中是对全局计算机状态的修改，并可能在其他应用程序或其他模块中产生副作用。</span><span class="sxs-lookup"><span data-stu-id="a796f-400">Installing assemblies to the GAC is a modification of global machine state and may cause side-effects in other applications or to other modules.</span></span> <span data-ttu-id="a796f-401">即使模块具有所需的访问权限，也可能难以正确操作。</span><span class="sxs-lookup"><span data-stu-id="a796f-401">It may also be difficult to do correctly, even when your module has the required access privileges.</span></span> <span data-ttu-id="a796f-402">错误的操作可能会在其他 .NET 应用程序中引起计算机范围的严重问题。</span><span class="sxs-lookup"><span data-stu-id="a796f-402">Getting it wrong could cause serious, machine-wide issues in other .NET applications.</span></span>

## <a name="further-reading"></a><span data-ttu-id="a796f-403">其他阅读材料</span><span class="sxs-lookup"><span data-stu-id="a796f-403">Further reading</span></span>

<span data-ttu-id="a796f-404">有关 .NET 程序集版本依赖项冲突，还有很多内容可供阅读。</span><span class="sxs-lookup"><span data-stu-id="a796f-404">There's plenty more to read on .NET assembly version dependency conflicts.</span></span> <span data-ttu-id="a796f-405">从以下内容开始阅读就很不错：</span><span class="sxs-lookup"><span data-stu-id="a796f-405">Here are some nice jumping off points:</span></span>

- [<span data-ttu-id="a796f-406">.NET：.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="a796f-406">.NET: Assemblies in .NET</span></span>](/dotnet/standard/assembly/)
- [<span data-ttu-id="a796f-407">.NET Core：托管程序集加载算法</span><span class="sxs-lookup"><span data-stu-id="a796f-407">.NET Core: The managed assembly loading algorithm</span></span>](/dotnet/core/dependency-loading/loading-managed)
- [<span data-ttu-id="a796f-408">.NET Core：了解 System.Runtime.Loader.AssemblyLoadContext</span><span class="sxs-lookup"><span data-stu-id="a796f-408">.NET Core: Understanding System.Runtime.Loader.AssemblyLoadContext</span></span>](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [<span data-ttu-id="a796f-409">.NET Core：有关程序集并行加载解决方案的讨论</span><span class="sxs-lookup"><span data-stu-id="a796f-409">.NET Core: Discussion about side-by-side assembly loading solutions</span></span>](https://github.com/dotnet/runtime/issues/13471)
- [<span data-ttu-id="a796f-410">.NET Framework：重定向程序集版本</span><span class="sxs-lookup"><span data-stu-id="a796f-410">.NET Framework: Redirecting assembly versions</span></span>](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [<span data-ttu-id="a796f-411">.NET Framework：适用于程序集加载的最佳做法</span><span class="sxs-lookup"><span data-stu-id="a796f-411">.NET Framework: Best practices for assembly loading</span></span>](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [<span data-ttu-id="a796f-412">.NET Framework：运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="a796f-412">.NET Framework: How the runtime locates assemblies</span></span>](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [<span data-ttu-id="a796f-413">.NET Framework：解析程序集加载</span><span class="sxs-lookup"><span data-stu-id="a796f-413">.NET Framework: Resolve assembly loads</span></span>](/dotnet/standard/assembly/resolve-loads)
- [<span data-ttu-id="a796f-414">StackOverflow：程序集绑定重定向的方法和原因</span><span class="sxs-lookup"><span data-stu-id="a796f-414">StackOverflow: Assembly binding redirect, how and why?</span></span>](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [<span data-ttu-id="a796f-415">PowerShell：有关实现 AssemblyLoadContexts 的讨论</span><span class="sxs-lookup"><span data-stu-id="a796f-415">PowerShell: Discussion about implementing AssemblyLoadContexts</span></span>](https://github.com/PowerShell/PowerShell/issues/11571)
- [<span data-ttu-id="a796f-416">PowerShell：`Assembly.LoadFile()` 不会加载到默认 AssemblyLoadContext 中</span><span class="sxs-lookup"><span data-stu-id="a796f-416">PowerShell: `Assembly.LoadFile()` doesn't load into default AssemblyLoadContext</span></span>](https://github.com/PowerShell/PowerShell/issues/12052)
- [<span data-ttu-id="a796f-417">Rick Strahl：何时加载 .NET 程序集依赖项？</span><span class="sxs-lookup"><span data-stu-id="a796f-417">Rick Strahl: When does a .NET assembly dependency get loaded?</span></span>](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [<span data-ttu-id="a796f-418">Jon Skeet：.NET 中的版本控制摘要</span><span class="sxs-lookup"><span data-stu-id="a796f-418">Jon Skeet: Summary of versioning in .NET</span></span>](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [<span data-ttu-id="a796f-419">Nate McMaster：深入了解 .NET Core 基元</span><span class="sxs-lookup"><span data-stu-id="a796f-419">Nate McMaster: Deep dive into .NET Core primitives</span></span>](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
