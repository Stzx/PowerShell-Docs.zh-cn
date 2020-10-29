---
ms.date: 05/22/2020
keywords: powershell,cmdlet
title: 什么是 PowerShell？
description: 本文介绍 PowerShell 脚本编写环境及其功能。
ms.openlocfilehash: 91fc580af9a3adf43a24c40b4aaf3f1843882705
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500770"
---
# <a name="what-is-powershell"></a><span data-ttu-id="c1fe7-104">什么是 PowerShell？</span><span class="sxs-lookup"><span data-stu-id="c1fe7-104">What is PowerShell?</span></span>

<span data-ttu-id="c1fe7-105">PowerShell 是一种跨平台的任务自动化和配置管理框架，由命令行管理程序和脚本语言组成。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-105">PowerShell is a cross-platform task automation and configuration management framework, consisting of a command-line shell and scripting language.</span></span> <span data-ttu-id="c1fe7-106">与大多数接受并返回文本的 shell 不同，PowerShell 构建在 .NET 公共语言运行时 (CLR) 的基础之上，接受并返回 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-106">Unlike most shells, which accept and return text, PowerShell is built on top of the .NET Common Language Runtime (CLR), and accepts and returns .NET objects.</span></span> <span data-ttu-id="c1fe7-107">这一根本上的改变引入了全新的自动化工具和方法。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-107">This fundamental change brings entirely new tools and methods for automation.</span></span>

<!-- removing images until we can get replacements
:::row:::
   :::column span="":::
      Windows
      [![PowerShell on Windows](media/overview/windows-desktop-660.gif)](media/overview/windows-desktop.gif#lightbox)
      [Install on Windows](install/installing-powershell-core-on-windows.md)
   :::column-end:::
   :::column span="":::
      Linux
      [![PowerShell on Linux](media/overview/linux-desktop-660.gif)](media/overview/linux-desktop.gif#lightbox)
      [Install on Linux](install/installing-powershell-core-on-linux.md)
   :::column-end:::
   :::column span="":::
      macOS
      [![PowerShell on macOS](media/overview/macos-desktop-660.gif)](media/overview/macos-desktop.gif#lightbox)
      [Install on macOS](install/installing-powershell-core-on-macos.md)
   :::column-end:::
:::row-end:::
-->

## <a name="output-is-object-based"></a><span data-ttu-id="c1fe7-108">输出是基于对象的</span><span class="sxs-lookup"><span data-stu-id="c1fe7-108">Output is object-based</span></span>

<span data-ttu-id="c1fe7-109">不同于传统的命令行接口，PowerShell cmdlet 旨在处理对象。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-109">Unlike traditional command-line interfaces, PowerShell cmdlets are designed to deal with objects.</span></span>
<span data-ttu-id="c1fe7-110">对象是结构化信息，不仅仅是屏幕上出现的字符串。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-110">An object is structured information that is more than just the string of characters appearing on the screen.</span></span> <span data-ttu-id="c1fe7-111">命令输出会始终包含你在需要时可使用的额外信息。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-111">Command output always carries extra information that you can use if you need it.</span></span>

<span data-ttu-id="c1fe7-112">如果以前使用过文本处理工具来处理数据，那么在 PowerShell 中使用时，会发现它们的行为有所不同。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-112">If you've used text-processing tools to process data in the past, you'll find that they behave differently when used in PowerShell.</span></span> <span data-ttu-id="c1fe7-113">在大多数情况下，不需要文本或文本处理工具来提取特定信息。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-113">In most cases, you don't need text-processing tools to extract specific information.</span></span> <span data-ttu-id="c1fe7-114">可以使用标准 PowerShell 对象语法直接访问数据的各部分。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-114">You directly access portions of the data using standard PowerShell object syntax.</span></span>

## <a name="the-command-family-is-extensible"></a><span data-ttu-id="c1fe7-115">命令系列是可扩展的</span><span class="sxs-lookup"><span data-stu-id="c1fe7-115">The command family is extensible</span></span>

<span data-ttu-id="c1fe7-116">接口（如 `cmd.exe`）不提供可直接扩展内置命令集的方法。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-116">Interfaces such as `cmd.exe` don't provide a way for you to directly extend the built-in command set.</span></span> <span data-ttu-id="c1fe7-117">可创建在 `cmd.exe` 中运行的外部命令行工具。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-117">You can create external command-line tools that run in `cmd.exe`.</span></span> <span data-ttu-id="c1fe7-118">但这些外部工具不包含服务，例如帮助集成。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-118">But these external tools don't have services, such as Help integration.</span></span> <span data-ttu-id="c1fe7-119">`cmd.exe` 不会自动知道这些外部工具是有效命令。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-119">`cmd.exe` doesn't automatically know that these external tools are valid commands.</span></span>

<span data-ttu-id="c1fe7-120">PowerShell 中的命令被称为 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-120">The commands in PowerShell are known as _cmdlets_ .</span></span> <span data-ttu-id="c1fe7-121">可单独使用每个 cmdlet，但只有结合使用它们来执行复杂的任务时，才能发挥它们的作用。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-121">You can use each cmdlet separately, but their power is realized when you combine them to perform complex tasks.</span></span> <span data-ttu-id="c1fe7-122">与许多 Shell 类似，可通过 PowerShell 访问计算机上的文件系统。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-122">Like many shells, PowerShell gives you access to the file system on the computer.</span></span> <span data-ttu-id="c1fe7-123">通过 PowerShell 提供程序，可像访问文件系统一样轻松访问其他数据存储（例如注册表和证书存储）。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-123">PowerShell _providers_ enable you to access other data stores, such as the registry and the certificate stores, as easily as you access the file system.</span></span>

<span data-ttu-id="c1fe7-124">可使用编译的代码或脚本自行创建 cmdlet 和函数模块。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-124">You can create your own cmdlet and function modules using compiled code or scripts.</span></span> <span data-ttu-id="c1fe7-125">模块可以向 shell 添加 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-125">Modules can add cmdlets and providers to the shell.</span></span> <span data-ttu-id="c1fe7-126">PowerShell 还支持类似于 UNIX shell 脚本和 `cmd.exe` 批处理文件的脚本。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-126">PowerShell also supports scripts that are analogous to UNIX shell scripts and `cmd.exe` batch files.</span></span>

## <a name="support-for-command-aliases"></a><span data-ttu-id="c1fe7-127">支持命令别名</span><span class="sxs-lookup"><span data-stu-id="c1fe7-127">Support for command aliases</span></span>

<span data-ttu-id="c1fe7-128">PowerShell 支持别名以通过备用名称引用命令。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-128">PowerShell supports aliases to refer to commands by alternate names.</span></span> <span data-ttu-id="c1fe7-129">别名允许具有其他 Shell 经验的用户使用其已知的常见命令名称在 PowerShell 中执行类似操作。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-129">Aliasing allows users with experience in other shells to use common command names that they already know for similar operations in PowerShell.</span></span>

<span data-ttu-id="c1fe7-130">别名将新名称与其他命令关联。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-130">Aliasing associates a new name with another command.</span></span> <span data-ttu-id="c1fe7-131">例如，PowerShell 具有名为 `Clear-Host` 的内部函数，该函数清空输出窗口。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-131">For example, PowerShell has an internal function named `Clear-Host` that clears the output window.</span></span> <span data-ttu-id="c1fe7-132">可以在命令提示符下键入 `cls` 或 `clear` 别名。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-132">You can type either the `cls` or `clear` alias at a command prompt.</span></span> <span data-ttu-id="c1fe7-133">PowerShell 解释这些别名并运行 `Clear-Host` 函数。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-133">PowerShell interprets these aliases and runs the `Clear-Host` function.</span></span>

<span data-ttu-id="c1fe7-134">此功能可帮助用户了解 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-134">This feature helps users to learn PowerShell.</span></span> <span data-ttu-id="c1fe7-135">首先，大多数 `cmd.exe` 和 Unix 用户都要使用大量命令，用户通过名称已经了解这些命令。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-135">First, most `cmd.exe` and Unix users have a large repertoire of commands that users already know by name.</span></span> <span data-ttu-id="c1fe7-136">PowerShell 等效项可能不会产生相同的结果。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-136">The PowerShell equivalents may not produce identical results.</span></span> <span data-ttu-id="c1fe7-137">但是，结果非常接近，用户可以在不知道 PowerShell 命令名称的情况下完成工作。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-137">However, the results are close enough that users can do work without knowing the PowerShell command name.</span></span> <span data-ttu-id="c1fe7-138">在学习新的命令 shell 时，“肌肉记忆”是另一个令人沮丧的主要原因。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-138">"Muscle memory" is another major source of frustration when learning a new command shell.</span></span> <span data-ttu-id="c1fe7-139">如果你已使用 `cmd.exe` 多年，则可能会条件反射地键入 `cls` 命令来清除屏幕。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-139">If you have used `cmd.exe` for years, you might reflexively type the `cls` command to clear the screen.</span></span> <span data-ttu-id="c1fe7-140">如果没有 `Clear-Host` 的别名，则会收到一条错误消息，并且不知道如何操作才能清除输出。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-140">Without the alias for `Clear-Host`, you receive an error message and won't know what to do to clear the output.</span></span>

## <a name="powershell-handles-console-input-and-display"></a><span data-ttu-id="c1fe7-141">PowerShell 处理控制台输入和显示</span><span class="sxs-lookup"><span data-stu-id="c1fe7-141">PowerShell handles console input and display</span></span>

<span data-ttu-id="c1fe7-142">当你键入命令时，PowerShell 会始终直接处理命令行输入。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-142">When you type a command, PowerShell always processes the command-line input directly.</span></span> <span data-ttu-id="c1fe7-143">PowerShell 还会对你在屏幕上看到的输出进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-143">PowerShell also formats the output that you see on the screen.</span></span> <span data-ttu-id="c1fe7-144">这种差异非常重要，因为它减少了每个 cmdlet 必须完成的工作量。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-144">This difference is significant because it reduces the work required of each cmdlet.</span></span> <span data-ttu-id="c1fe7-145">它确保你始终可以使用任何 cmdlet 以相同的方式执行操作。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-145">It ensures that you can always do things the same way with any cmdlet.</span></span> <span data-ttu-id="c1fe7-146">Cmdlet 开发人员无需编写代码来分析命令行参数或格式化输出。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-146">Cmdlet developers don't need to write code to parse the command-line arguments or format the output.</span></span>

<span data-ttu-id="c1fe7-147">传统的命令行工具有自己的用于请求和显示帮助的方案。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-147">Traditional command-line tools have their own schemes for requesting and displaying Help.</span></span> <span data-ttu-id="c1fe7-148">某些命令行工具使用 `/?` 来触发帮助显示；而其他一些使用 `-?`、`/H`，甚至 `//`。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-148">Some command-line tools use `/?` to trigger the Help display; others use `-?`, `/H`, or even `//`.</span></span> <span data-ttu-id="c1fe7-149">有些工具会在 GUI 窗口而不是在控制台显示区域显示帮助。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-149">Some will display Help in a GUI window, rather than in the console display.</span></span> <span data-ttu-id="c1fe7-150">如果你使用的参数有误，该工具可能会忽略你键入的内容并自动开始执行任务。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-150">If you use the wrong parameter, the tool might ignore what you typed and begin executing a task automatically.</span></span>
<span data-ttu-id="c1fe7-151">由于 PowerShell 会自动分析和处理命令行，因此 `-?` 参数始终表示“向我显示此命令的帮助”。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-151">Since PowerShell automatically parses and processes the command line, the `-?` parameter always means "show me Help for this command".</span></span>

> [!NOTE]
> <span data-ttu-id="c1fe7-152">如果在 PowerShell 中运行图形应用程序，将随即打开该应用程序的窗口。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-152">If you run a graphic application in PowerShell, the window for the application opens.</span></span>
> <span data-ttu-id="c1fe7-153">PowerShell 仅会在处理你提供的命令行输入或返回到控制台窗口中的应用程序输出时才会进行干预。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-153">PowerShell intervenes only when processing the command-line input you supply or the application output returned to the console window.</span></span> <span data-ttu-id="c1fe7-154">它不会内在地影响应用程序的工作方式。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-154">It does not affect how the application works internally.</span></span>

## <a name="powershell-has-a-pipeline"></a><span data-ttu-id="c1fe7-155">PowerShell 有一个管道</span><span class="sxs-lookup"><span data-stu-id="c1fe7-155">PowerShell has a pipeline</span></span>

<span data-ttu-id="c1fe7-156">管道可能是命令行界面中使用的最有价值的概念。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-156">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="c1fe7-157">如果使用得当，管道可减少使用复杂命令的工作量，并让你更轻松地查看工作流程。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-157">When used properly, pipelines reduce the effort of using complex commands and make it easier to see the flow of work.</span></span> <span data-ttu-id="c1fe7-158">管道中的每个命令将其输出逐项传递给下一个命令。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-158">Each command in a pipeline passes its output, item by item, to the next command.</span></span> <span data-ttu-id="c1fe7-159">命令不必一次处理多个项目。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-159">Commands don't have to handle more than one item at a time.</span></span> <span data-ttu-id="c1fe7-160">这样就减少了资源消耗，并能立即获取输出。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-160">The result is reduced resource consumption and the ability to get output immediately.</span></span>

<span data-ttu-id="c1fe7-161">用于管道的符号类似于其他 shell 中使用的符号。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-161">The notation used for pipelines is similar to the notation used in other shells.</span></span> <span data-ttu-id="c1fe7-162">初看起来 PowerShell 中管道的不同之处可能并不明显。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-162">At first glance, it may not be apparent how pipelines are different in PowerShell.</span></span> <span data-ttu-id="c1fe7-163">尽管你会在屏幕上看到文本，但 PowerShell 通过管道在命令之间传递对象，而不是文本。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-163">Although you see text on the screen, PowerShell pipes objects, not text, between commands.</span></span>

<span data-ttu-id="c1fe7-164">例如，如果使用 `Out-Host` cmdlet 来强制逐页显示来自于另一个命令的输出，那么这一输出看起来就像分页显示在屏幕上的普通文本：</span><span class="sxs-lookup"><span data-stu-id="c1fe7-164">For example, if you use the `Out-Host` cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```powershell
Get-ChildItem | Out-Host -Paging
```

```Output
    Directory: /mnt/c/Git/PS-Docs/PowerShell-Docs/reference/7.0/Microsoft.PowerShell.Core

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d----          05/22/2020    08:30                About
-----          05/20/2020    14:36           9044 Add-History.md
-----          05/20/2020    14:36          12227 Clear-History.md
-----          05/20/2020    14:36           3566 Clear-Host.md
-----          05/20/2020    14:36          29087 Connect-PSSession.md
-----          05/20/2020    14:36           5705 Debug-Job.md
-----          05/20/2020    14:36           3515 Disable-ExperimentalFeature.md
-----          05/20/2020    14:36          25531 Disable-PSRemoting.md
-----          05/20/2020    14:36           7852 Disable-PSSessionConfiguration.md
-----          05/20/2020    14:36          25355 Disconnect-PSSession.md
-----          05/20/2020    14:36           3491 Enable-ExperimentalFeature.md
-----          05/20/2020    14:36          13310 Enable-PSRemoting.md
-----          05/20/2020    14:36           8401 Enable-PSSessionConfiguration.md
-----          05/20/2020    14:36           9531 Enter-PSHostProcess.md
...
<SPACE> next page; <CR> next line; Q quit
```

<span data-ttu-id="c1fe7-165">分页还会降低 CPU 利用率，因为准备好显示完整页面时，会转为处理 `Out-Host` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-165">Paging also reduces CPU utilization because processing transfers to the `Out-Host` cmdlet when it has a complete page ready to display.</span></span> <span data-ttu-id="c1fe7-166">管道中位于前面的 cmdlet 暂停执行，直到输出的下一页可用。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-166">The cmdlets that precede it in the pipeline pause execution until the next page of output is available.</span></span>

### <a name="objects-in-the-pipeline"></a><span data-ttu-id="c1fe7-167">管道中的对象</span><span class="sxs-lookup"><span data-stu-id="c1fe7-167">Objects in the pipeline</span></span>

<span data-ttu-id="c1fe7-168">在 PowerShell 中运行 cmdlet 时，可以看到文本输出，因为必须在控制台窗口中以文本形式表示对象。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-168">When you run a cmdlet in PowerShell, you see text output because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="c1fe7-169">文本输出可能不会显示输出的对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-169">The text output may not display all of the properties of the object being output.</span></span>

<span data-ttu-id="c1fe7-170">例如，请考虑 `Get-Location` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-170">For example, consider the `Get-Location` cmdlet.</span></span> <span data-ttu-id="c1fe7-171">文本输出是信息摘要，而非 `Get-Location` 返回的对象的完整表示形式。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-171">The text output is a summary of information, not a complete representation of the object returned by `Get-Location`.</span></span> <span data-ttu-id="c1fe7-172">输出中的标题通过格式化屏幕显示数据的过程添加。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-172">The heading in the output is added by the process that formats the data for onscreen display.</span></span>

```powershell
Get-Location
```

```Output
Path
----
C:\
```

<span data-ttu-id="c1fe7-173">通过管道将输出传递到 `Get-Member` cmdlet 后，可获得有关 `Get-Location` 返回的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-173">Piping the output to the `Get-Member` cmdlet displays information about the object returned by `Get-Location`.</span></span>

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

<span data-ttu-id="c1fe7-174">`Get-Location` 返回 PathInfo 对象，其中包含当前路径和其他信息。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-174">`Get-Location` returns a **PathInfo** object that contains the current path and other information.</span></span>

## <a name="built-in-help-system"></a><span data-ttu-id="c1fe7-175">内置帮助系统</span><span class="sxs-lookup"><span data-stu-id="c1fe7-175">Built-in help system</span></span>

<span data-ttu-id="c1fe7-176">与 `man` 页面类似，PowerShell 包含了详细的帮助文章，其中解释了 PowerShell 概念和命令语法。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-176">Similar to Unix `man` pages, PowerShell includes detailed help articles that explain PowerShell concepts and command syntax.</span></span> <span data-ttu-id="c1fe7-177">使用 [Get-Help][] cmdlet 在命令提示符下显示这些文章，或在 PowerShell 文档中在线查看这些文章的最近更新版本。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-177">Use the [Get-Help][] cmdlet to display these articles at the command prompt or view the most recently updated versions of these articles in the PowerShell documentation online.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1fe7-178">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c1fe7-178">Next steps</span></span>

<span data-ttu-id="c1fe7-179">要详细了解 PowerShell，请查看此网站的“学习 PowerShell”部分。</span><span class="sxs-lookup"><span data-stu-id="c1fe7-179">To learn more about PowerShell, see the **Learning PowerShell** section of this site.</span></span>

<!-- link references -->

[Get-Help]: /powershell/module/microsoft.powershell.core/Get-Help
