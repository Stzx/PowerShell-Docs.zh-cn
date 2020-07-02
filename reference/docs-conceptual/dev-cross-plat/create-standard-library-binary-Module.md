---
title: 如何创建标准库二进制模块
description: 使用 PowerShell 标准库，我们可以创建同时适用于 PowerShell Core 和 Windows PowerShell 5.1 的跨平台模块。
ms.date: 05/23/2020
ms.custom: contributor-KevinMarquette
ms.openlocfilehash: 51734fd9232e7c33b11c6c5a6abddbcc1f28413c
ms.sourcegitcommit: ed4a895d672334c7b02fb7ef6e950dbc2ba4a197
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "84149410"
---
# <a name="how-to-create-a-standard-library-binary-module"></a><span data-ttu-id="4023e-103">如何创建标准库二进制模块</span><span class="sxs-lookup"><span data-stu-id="4023e-103">How to create a Standard Library binary module</span></span>

<span data-ttu-id="4023e-104">最近，我有了一个想要将模块实现为二进制模块的想法。</span><span class="sxs-lookup"><span data-stu-id="4023e-104">I recently had an idea for module that I wanted to implement as a binary module.</span></span> <span data-ttu-id="4023e-105">我还没有使用 [PowerShell 标准库][]创建过模块，这看起来是个不错的机会。</span><span class="sxs-lookup"><span data-stu-id="4023e-105">I have yet to create one using the [PowerShell Standard Library][] so this felt like a good opportunity.</span></span> <span data-ttu-id="4023e-106">我利用[创建跨平台二进制模块][]指南成功创建了这一模块，没有任何障碍。</span><span class="sxs-lookup"><span data-stu-id="4023e-106">I used the [Creating a cross-platform binary module][] guide to create this module without any roadblocks.</span></span>
<span data-ttu-id="4023e-107">在这里，我们将执行同一过程，我将在此过程中添加一些额外的说明。</span><span class="sxs-lookup"><span data-stu-id="4023e-107">We're going to walk that same process and I'll add a little extra commentary along the way.</span></span>

> [!NOTE]
> <span data-ttu-id="4023e-108">本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。</span><span class="sxs-lookup"><span data-stu-id="4023e-108">The [original version][] of this article appeared on the blog written by [@KevinMarquette][].</span></span> <span data-ttu-id="4023e-109">PowerShell 团队感谢 Kevin 与我们分享这篇文章。</span><span class="sxs-lookup"><span data-stu-id="4023e-109">The PowerShell team thanks Kevin for sharing this content with us.</span></span> <span data-ttu-id="4023e-110">请前往 [PowerShellExplained.com][] 访问他的博客。</span><span class="sxs-lookup"><span data-stu-id="4023e-110">Please check out his blog at [PowerShellExplained.com][].</span></span>

## <a name="what-is-the-powershell-standard-library"></a><span data-ttu-id="4023e-111">什么是 PowerShell 标准库？</span><span class="sxs-lookup"><span data-stu-id="4023e-111">What is the PowerShell Standard Library?</span></span>

<span data-ttu-id="4023e-112">使用 PowerShell 标准库，我们可以创建同时适用于 PowerShell Core 和 Windows PowerShell 5.1（或者 3.0）的跨平台模块。</span><span class="sxs-lookup"><span data-stu-id="4023e-112">The PowerShell Standard Library allows us to create cross platform modules that work in both PowerShell Core and with Windows PowerShell 5.1 (or 3.0).</span></span>

## <a name="planning-our-module"></a><span data-ttu-id="4023e-113">规划模块</span><span class="sxs-lookup"><span data-stu-id="4023e-113">Planning our module</span></span>

<span data-ttu-id="4023e-114">此模块的计划是为 C# 代码创建一个 `src` 文件夹，并像对脚本模块那样构造其余内容。</span><span class="sxs-lookup"><span data-stu-id="4023e-114">The plan for this module is to create a `src` folder for the C# code and structure the rest like I would for a script module.</span></span> <span data-ttu-id="4023e-115">这包括使用生成脚本将所有内容编译到 `output` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4023e-115">This includes using a build script to compile everything into an `output` folder.</span></span> <span data-ttu-id="4023e-116">该文件夹结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="4023e-116">The folder structure looks like this:</span></span>

```
MyModule
├───src
├───Output
│   └───MyModule
├───MyModule
│   ├───Data
│   ├───Private
│   └───Public
└───Tests
```

## <a name="getting-started"></a><span data-ttu-id="4023e-117">入门</span><span class="sxs-lookup"><span data-stu-id="4023e-117">Getting Started</span></span>

<span data-ttu-id="4023e-118">我通常会使用 Plaster 模板，但当前的模板尚不支持任何二进制模块。</span><span class="sxs-lookup"><span data-stu-id="4023e-118">I normally use a Plaster template but my current template doesn't have any binary module support yet.</span></span> <span data-ttu-id="4023e-119">小事一桩，</span><span class="sxs-lookup"><span data-stu-id="4023e-119">Not a big deal.</span></span> <span data-ttu-id="4023e-120">我会手动创建一个。</span><span class="sxs-lookup"><span data-stu-id="4023e-120">I'll create this one by hand this time.</span></span>

<span data-ttu-id="4023e-121">首先，我需要创建文件夹和 git 存储库。</span><span class="sxs-lookup"><span data-stu-id="4023e-121">First I need to create the folder and create the git repo.</span></span> <span data-ttu-id="4023e-122">我将 `$module` 用作模块名的占位符。</span><span class="sxs-lookup"><span data-stu-id="4023e-122">I'm using `$module` as a placeholder for the module name.</span></span> <span data-ttu-id="4023e-123">这会让你更轻松地重用这些示例（需要时）。</span><span class="sxs-lookup"><span data-stu-id="4023e-123">This should make it easier for you to reuse these examples if needed.</span></span>

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

<span data-ttu-id="4023e-124">然后创建根级别文件夹。</span><span class="sxs-lookup"><span data-stu-id="4023e-124">Then create the root level folders.</span></span>

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a><span data-ttu-id="4023e-125">二进制模块设置</span><span class="sxs-lookup"><span data-stu-id="4023e-125">Binary module setup</span></span>

<span data-ttu-id="4023e-126">本文主要侧重于二进制模块，因此，我们将从这里开始。</span><span class="sxs-lookup"><span data-stu-id="4023e-126">This article os focused on the binary module so that is where we'll start.</span></span> <span data-ttu-id="4023e-127">本部分的示例来自[创建跨平台二进制模块][]指南。</span><span class="sxs-lookup"><span data-stu-id="4023e-127">This section pulls examples from the [Creating a cross-platform binary module][] guide.</span></span> <span data-ttu-id="4023e-128">如果你需要更多详细信息或遇到任何问题，请查阅该指南。</span><span class="sxs-lookup"><span data-stu-id="4023e-128">Review that guide if you need more details or have any issues.</span></span>

<span data-ttu-id="4023e-129">我们要做的第一件事是，检查安装的 [dotnet core SDK][] 版本。</span><span class="sxs-lookup"><span data-stu-id="4023e-129">First thing we want to do is check the version of the [dotnet core SDK][] that we installed.</span></span> <span data-ttu-id="4023e-130">我使用的是 2.1.4，但你应该用 2.0.0 或更高版本才能继续操作。</span><span class="sxs-lookup"><span data-stu-id="4023e-130">I'm using 2.1.4, but you should have 2.0.0 or newer before continuing.</span></span>

```powershell
PS> dotnet --version
2.1.4
```

<span data-ttu-id="4023e-131">我正在为这一部分做出 `src` 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4023e-131">I'm working out of the `src` folder for this section.</span></span>

```powershell
Set-Location 'src'
```

<span data-ttu-id="4023e-132">使用 dotnet 命令创建一个新类库。</span><span class="sxs-lookup"><span data-stu-id="4023e-132">Using the dotnet command, create a new class library.</span></span>

```powershell
dotnet new classlib --name $module
```

<span data-ttu-id="4023e-133">这会在子文件夹中创建库项目，但我不希望有额外的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="4023e-133">This created the library project in a subfolder but I don't want that extra level of nesting.</span></span> <span data-ttu-id="4023e-134">我要将这些文件上移一级。</span><span class="sxs-lookup"><span data-stu-id="4023e-134">I'm going to move those files up a level.</span></span>

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

<span data-ttu-id="4023e-135">为项目设置 .NET core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="4023e-135">Set the .NET core SDK version for the project.</span></span> <span data-ttu-id="4023e-136">我安装了 2.1 SDK，因此，我将指定 2.1.0。</span><span class="sxs-lookup"><span data-stu-id="4023e-136">I have the 2.1 SDK so I'm going to specify 2.1.0.</span></span>
<span data-ttu-id="4023e-137">如果你使用的是 2.0 SDK，请指定 2.0.0。</span><span class="sxs-lookup"><span data-stu-id="4023e-137">Use 2.0.0 if you're using the 2.0 SDK.</span></span>

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

<span data-ttu-id="4023e-138">将 PowerShell 标准库 [NuGet 包][]添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="4023e-138">Add the PowerShell Standard Library [NuGet package][] to the project.</span></span> <span data-ttu-id="4023e-139">请确保你使用的是适用于你所需的兼容性级别的最新版本。</span><span class="sxs-lookup"><span data-stu-id="4023e-139">Make sure you use the most recent version available for the level of compatibility that you need.</span></span> <span data-ttu-id="4023e-140">我将默认使用最新版本，但我并不认为此模块充分利用了版本高于 PowerShell 3.0 的任何功能。</span><span class="sxs-lookup"><span data-stu-id="4023e-140">I would default to the latest version but I don't think this module leverages any features newer than PowerShell 3.0.</span></span>

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

<span data-ttu-id="4023e-141">我们应该有一个 src 文件夹，类似如下所示：</span><span class="sxs-lookup"><span data-stu-id="4023e-141">We should have a src folder that looks like this:</span></span>

```powershell
PS> Get-ChildItem
    Directory: \MyModule\src

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        7/14/2018   9:51 PM                obj
-a----        7/14/2018   9:51 PM             86 Class1.cs
-a----        7/14/2018  10:03 PM            259 MyModule.csproj
-a----        7/14/2018  10:05 PM             45 global.json
```

<span data-ttu-id="4023e-142">现在，我们已准备好将自己的代码添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="4023e-142">Now we're ready to add our own code to the project.</span></span>

### <a name="building-a-binary-cmdlet"></a><span data-ttu-id="4023e-143">构建二进制 cmdlet</span><span class="sxs-lookup"><span data-stu-id="4023e-143">Building a binary cmdlet</span></span>

<span data-ttu-id="4023e-144">我们需要更新 `src\Class1.cs` 以包含这一开头的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4023e-144">We need to update the `src\Class1.cs` to contain this starter cmdlet:</span></span>

```csharp
using System;
using System.Management.Automation;

namespace MyModule
{
    [Cmdlet( VerbsDiagnostic.Resolve , "MyCmdlet")]
    public class ResolveMyCmdletCommand : PSCmdlet
    {
        [Parameter(Position=0)]
        public Object InputObject { get; set; }

        protected override void EndProcessing()
        {
            this.WriteObject(this.InputObject);
            base.EndProcessing();
        }
    }
}
```

<span data-ttu-id="4023e-145">重命名文件，使其与类名匹配。</span><span class="sxs-lookup"><span data-stu-id="4023e-145">Rename the file to match the class name.</span></span>

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

<span data-ttu-id="4023e-146">接下来，我们可以构建自己的模块。</span><span class="sxs-lookup"><span data-stu-id="4023e-146">Then we can build our module.</span></span>

```powershell
PS> dotnet build

Microsoft (R) Build Engine version 15.5.180.51428 for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

Restore completed in 18.19 ms for C:\workspace\MyModule\src\MyModule.csproj.
MyModule -> C:\workspace\MyModule\src\bin\Debug\netstandard2.0\MyModule.dll

Build succeeded.
    0 Warning(s)
    0 Error(s)

Time Elapsed 00:00:02.19
```

<span data-ttu-id="4023e-147">我们可以对新 dll 调用 `Import-Module` 以加载新的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4023e-147">We can call `Import-Module` on the new dll to load our new CMDlet.</span></span>

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

<span data-ttu-id="4023e-148">如果在你的系统上导入失败，请尝试将 .NET 更新到 4.7.1 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4023e-148">If the import fails on your system, try updating .NET to 4.7.1 or newer.</span></span> <span data-ttu-id="4023e-149">[创建跨平台二进制模块][]指南详细地介绍了较旧版本的 .NET 的 .NET 支持和兼容性。</span><span class="sxs-lookup"><span data-stu-id="4023e-149">The [Creating a cross-platform binary module][] guide goes into more details on .NET support and compatibility for older versions of .NET.</span></span>

### <a name="module-manifest"></a><span data-ttu-id="4023e-150">模块清单</span><span class="sxs-lookup"><span data-stu-id="4023e-150">Module manifest</span></span>

<span data-ttu-id="4023e-151">很酷的是，我们可以导入 dll 并获得一个有效的模块。</span><span class="sxs-lookup"><span data-stu-id="4023e-151">It's cool that we can import the dll and have a working module.</span></span> <span data-ttu-id="4023e-152">我想继续使用它并创建一个模块清单。</span><span class="sxs-lookup"><span data-stu-id="4023e-152">I like to keep going with it and create a module manifest.</span></span> <span data-ttu-id="4023e-153">如果稍后要发布到 PSGallery，我们需要该清单。</span><span class="sxs-lookup"><span data-stu-id="4023e-153">We need the manifest if we want to publish to the PSGallery later.</span></span>

<span data-ttu-id="4023e-154">在项目的根目录中，可以运行以下命令来创建所需的模块清单。</span><span class="sxs-lookup"><span data-stu-id="4023e-154">From the root of our project, we can run this command to create the module manifest that we need.</span></span>

```powershell
$manifestSplat = @{
    Path              = ".\$module\$module.psd1"
    Author            = 'Kevin Marquette'
    NestedModules     = @('bin\MyModule.dll')
    RootModule        = "$module.psm1"
    FunctionsToExport = @('Resolve-MyCmdlet')
}
New-ModuleManifest @manifestSplat
```

<span data-ttu-id="4023e-155">此外，我还要为将来的 PowerShell 函数创建一个空的根模块。</span><span class="sxs-lookup"><span data-stu-id="4023e-155">I'm also going to create an empty root module for future PowerShell functions.</span></span>

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

<span data-ttu-id="4023e-156">这样，我就可以将普通的 PowerShell 函数和二进制 Cmdlet 混合到同一个项目中。</span><span class="sxs-lookup"><span data-stu-id="4023e-156">This allows me to mix both normal PowerShell functions and binary Cmdlets in the same project.</span></span>

### <a name="building-the-full-module"></a><span data-ttu-id="4023e-157">生成完整的模块</span><span class="sxs-lookup"><span data-stu-id="4023e-157">Building the full module</span></span>

<span data-ttu-id="4023e-158">我将所有内容编译到一个输出文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4023e-158">I compile everything together into an output folder.</span></span> <span data-ttu-id="4023e-159">我们需要创建一个生成脚本来实现这一点。</span><span class="sxs-lookup"><span data-stu-id="4023e-159">We need to create a build script to do that.</span></span> <span data-ttu-id="4023e-160">我通常会将它添加到 `Invoke-Build` 脚本，但在本例中可以简单一点。</span><span class="sxs-lookup"><span data-stu-id="4023e-160">I would normally add this to an `Invoke-Build` script, but we can keep it simple for this example.</span></span> <span data-ttu-id="4023e-161">将它添加到项目根目录中的 `build.ps1`。</span><span class="sxs-lookup"><span data-stu-id="4023e-161">Add this to a `build.ps1` at the root of the project.</span></span>

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

<span data-ttu-id="4023e-162">这些命令会生成 DLL，并把它放到 `output\$module\bin` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4023e-162">These commands build our DLL and place it into our `output\$module\bin` folder.</span></span> <span data-ttu-id="4023e-163">然后，将其他模块文件复制到该位置。</span><span class="sxs-lookup"><span data-stu-id="4023e-163">It then copies the other module files into place.</span></span>

```
Output
└───MyModule
    │   MyModule.psd1
    │   MyModule.psm1
    │
    └───bin
            MyModule.deps.json
            MyModule.dll
            MyModule.pdb
```

<span data-ttu-id="4023e-164">此时，可以导入我们的模块和 psd1 文件。</span><span class="sxs-lookup"><span data-stu-id="4023e-164">At this point, we can import our module with the psd1 file.</span></span>

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

<span data-ttu-id="4023e-165">在这里，我们可以将 `.\Output\$module` 文件夹放到 `$env:PSModulePath` 目录，它会在我们需要时自动加载命令。</span><span class="sxs-lookup"><span data-stu-id="4023e-165">From here, we can drop the `.\Output\$module` folder into our `$env:PSModulePath` directory and it autoloads our command whenever we need it.</span></span>

### <a name="update-dotnet-new-psmodule"></a><span data-ttu-id="4023e-166">更新：dotnet new PSModule</span><span class="sxs-lookup"><span data-stu-id="4023e-166">Update: dotnet new PSModule</span></span>

<span data-ttu-id="4023e-167">我了解到 `dotnet` 工具有一个 `PSModule` 模板。</span><span class="sxs-lookup"><span data-stu-id="4023e-167">I learned that the `dotnet` tool has a `PSModule` template.</span></span>

<span data-ttu-id="4023e-168">我上面所述的所有步骤仍有效，但这个模板去掉了很多步骤。它还是一个非常新的模板，仍需要打磨。</span><span class="sxs-lookup"><span data-stu-id="4023e-168">All the steps that I outlined above are still valid, but this template cuts many pf them out. It's still a fairly new template that is still getting some polish placed on it.</span></span> <span data-ttu-id="4023e-169">希望从这里开始它能够更出色。</span><span class="sxs-lookup"><span data-stu-id="4023e-169">Expect it to keep getting better from here.</span></span>

<span data-ttu-id="4023e-170">以下就是使用安装和使用 PSModule 模板的方式。</span><span class="sxs-lookup"><span data-stu-id="4023e-170">This is how you use install and use the PSModule template.</span></span>

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

<span data-ttu-id="4023e-171">这种最低可行模板负责添加 .NET SDK、PowerShell 标准库，并在项目中创建一个示例类。</span><span class="sxs-lookup"><span data-stu-id="4023e-171">This minimally-viable template takes care of adding the .NET SDK, PowerShell Standard Library, and creates an example class in the project.</span></span> <span data-ttu-id="4023e-172">你可以立即生成并运行它。</span><span class="sxs-lookup"><span data-stu-id="4023e-172">You can build it and run it right away.</span></span>

## <a name="important-details"></a><span data-ttu-id="4023e-173">重要详细信息</span><span class="sxs-lookup"><span data-stu-id="4023e-173">Important details</span></span>

<span data-ttu-id="4023e-174">在结束本文之前，这里有一些其他的细节值得一提。</span><span class="sxs-lookup"><span data-stu-id="4023e-174">Before we end this article, here are a few other details worth mentioning.</span></span>

### <a name="unloading-dlls"></a><span data-ttu-id="4023e-175">卸载 DLL</span><span class="sxs-lookup"><span data-stu-id="4023e-175">Unloading DLLs</span></span>

<span data-ttu-id="4023e-176">加载二进制模块后，就不能真正将其卸载。</span><span class="sxs-lookup"><span data-stu-id="4023e-176">Once a binary module is loaded, you can't really unload it.</span></span> <span data-ttu-id="4023e-177">DLL 文件会被锁定，直到你将其卸载。</span><span class="sxs-lookup"><span data-stu-id="4023e-177">The DLL file is locked until you unload it.</span></span> <span data-ttu-id="4023e-178">在开发时，这可能会令人厌烦，因为每次进行更改并想要生成时，文件通常会被锁定。</span><span class="sxs-lookup"><span data-stu-id="4023e-178">This can be annoying when developing because every time you make a change and want to build it, the file is often locked.</span></span> <span data-ttu-id="4023e-179">解决此问题的唯一可靠方法是关闭加载 DLL 的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="4023e-179">The only reliable way to resolve this is to close the PowerShell session that loaded the DLL.</span></span>

### <a name="vs-code-reload-window-action"></a><span data-ttu-id="4023e-180">VS Code 重新加载窗口操作</span><span class="sxs-lookup"><span data-stu-id="4023e-180">VS Code reload window action</span></span>

<span data-ttu-id="4023e-181">我在 [VS Code][] 中完成了大部分 PowerShell 开发工作。</span><span class="sxs-lookup"><span data-stu-id="4023e-181">I do most of my PowerShell dev work in [VS Code][].</span></span> <span data-ttu-id="4023e-182">使用二进制模块（或包含类的模块）时，我习惯于每次生成时都重新加载 VS Code。</span><span class="sxs-lookup"><span data-stu-id="4023e-182">When I'm working on a binary module (or a module with classes), I've gotten into the habit of reloading VS Code every time I build.</span></span>
<span data-ttu-id="4023e-183">按 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> 会弹出命令窗口，`Reload Window` 始终在列表顶部。</span><span class="sxs-lookup"><span data-stu-id="4023e-183"><kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> pops the command window and `Reload Window` is always at the top of my list.</span></span>

### <a name="nested-powershell-sessions"></a><span data-ttu-id="4023e-184">嵌套的 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="4023e-184">Nested PowerShell sessions</span></span>

<span data-ttu-id="4023e-185">另一个选项是拥有良好的 Pester 测试覆盖率。</span><span class="sxs-lookup"><span data-stu-id="4023e-185">One other option is to have good Pester test coverage.</span></span> <span data-ttu-id="4023e-186">然后，可以调整 build.ps1 脚本以启动新的 PowerShell 会话，执行内部版本，运行测试，最后关闭会话。</span><span class="sxs-lookup"><span data-stu-id="4023e-186">Then you can adjust the build.ps1 script to start a new PowerShell session, perform the build, run the tests, and close the session.</span></span>

### <a name="updating-installed-modules"></a><span data-ttu-id="4023e-187">更新已安装模块</span><span class="sxs-lookup"><span data-stu-id="4023e-187">Updating installed modules</span></span>

<span data-ttu-id="4023e-188">尝试更新本地已安装的模块时，这种锁定可能会令人厌烦。</span><span class="sxs-lookup"><span data-stu-id="4023e-188">This locking can be annoying when trying to update your locally installed module.</span></span> <span data-ttu-id="4023e-189">如果有任何会话加载了它，则必须找到并关闭它。</span><span class="sxs-lookup"><span data-stu-id="4023e-189">If any session has it loaded, you have to go hunt it down and close it.</span></span> <span data-ttu-id="4023e-190">从 PSGallery 进行安装时，这不是什么大问题，因为模块版本控制在其他文件夹中放了一个新的。</span><span class="sxs-lookup"><span data-stu-id="4023e-190">This is less of an issue when installing from a PSGallery because module versioning places the new one in a different folder.</span></span>

<span data-ttu-id="4023e-191">可以设置本地 PSGallery，并作为生成操作的一部分进行发布。</span><span class="sxs-lookup"><span data-stu-id="4023e-191">You can set up a local PSGallery and publish to that as part of your build.</span></span> <span data-ttu-id="4023e-192">然后从该 PSGallery 进行本地安装。</span><span class="sxs-lookup"><span data-stu-id="4023e-192">Then do your local install from that PSGallery.</span></span> <span data-ttu-id="4023e-193">这听起来好像是个大工程，实际上像启动 docker 容器一样简单。</span><span class="sxs-lookup"><span data-stu-id="4023e-193">This sounds like a lot of work, but this can be as simple as starting a docker container.</span></span> <span data-ttu-id="4023e-194">我在[为 PSRepository 使用 NuGet 服务器][]一文中介绍了一种方法。</span><span class="sxs-lookup"><span data-stu-id="4023e-194">I cover a way to do that in my post on [Using a NuGet server for a PSRepository][].</span></span>

## <a name="why-binary-modules"></a><span data-ttu-id="4023e-195">为什么选择二进制模块？</span><span class="sxs-lookup"><span data-stu-id="4023e-195">Why binary modules?</span></span>

<span data-ttu-id="4023e-196">我直接跳到了如何生成一个二进制模块，但没有提到为什么要这样做。</span><span class="sxs-lookup"><span data-stu-id="4023e-196">I jumped right into how to make a binary module and didn't mention why you want to make one.</span></span> <span data-ttu-id="4023e-197">事实上，你正在编写 C# 并放弃了轻松访问 PowerShell Cmdlet 和函数的权利。</span><span class="sxs-lookup"><span data-stu-id="4023e-197">In reality, you are writing C# and give up easy access to PowerShell Cmdlets and functions.</span></span> <span data-ttu-id="4023e-198">这就是我没有更快转向二进制模块的主要原因。</span><span class="sxs-lookup"><span data-stu-id="4023e-198">That is the main reason why I have not shifted to binary modules sooner.</span></span>

<span data-ttu-id="4023e-199">但是，如果你要创建不依赖于许多其他 PowerShell 命令的模块，则性能优势可能会很显著。</span><span class="sxs-lookup"><span data-stu-id="4023e-199">But if you are creating a module that doesn't depend on a lot of other PowerShell commands, the performance benefit can be significant.</span></span> <span data-ttu-id="4023e-200">通过使用 C#，你可以减少 PowerShell 增加的开销。</span><span class="sxs-lookup"><span data-stu-id="4023e-200">By dropping into C#, you get to shed the overhead added by PowerShell.</span></span> <span data-ttu-id="4023e-201">PowerShell 针对管理员而不是计算机进行了优化，这会增加一些开销。</span><span class="sxs-lookup"><span data-stu-id="4023e-201">PowerShell was optimized for the administrator, not the computer, and that adds a little overhead.</span></span>

<span data-ttu-id="4023e-202">在工作中，我们有一个关键流程要通过 JSON 和哈希表完成大量工作。</span><span class="sxs-lookup"><span data-stu-id="4023e-202">At work, we have a critical process that does a lot of work with JSON and Hashtables.</span></span> <span data-ttu-id="4023e-203">我们已经尽可能优化 PowerShell，但此流程仍要运行 12 分钟之久。</span><span class="sxs-lookup"><span data-stu-id="4023e-203">We optimized the PowerShell as much as we could but this process was still running for 12 minutes.</span></span> <span data-ttu-id="4023e-204">模块中已包含很多 C# 样式 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4023e-204">The module already contained a lot of C# style PowerShell.</span></span> <span data-ttu-id="4023e-205">这使得转换为二进制模块变得简单明了。</span><span class="sxs-lookup"><span data-stu-id="4023e-205">This made the conversion to a binary module clean and easy to do.</span></span> <span data-ttu-id="4023e-206">通过转换可以将该流程从 12 分钟以上缩短到 4 分钟以内。</span><span class="sxs-lookup"><span data-stu-id="4023e-206">Our conversion cut that process down from over 12 minutes to under four minutes.</span></span>

### <a name="hybrid-modules"></a><span data-ttu-id="4023e-207">混合模块</span><span class="sxs-lookup"><span data-stu-id="4023e-207">Hybrid modules</span></span>

<span data-ttu-id="4023e-208">可以将二进制 Cmdlet 与 PowerShell 高级函数混合使用。</span><span class="sxs-lookup"><span data-stu-id="4023e-208">You can mix binary Cmdlets with PowerShell advanced functions.</span></span> <span data-ttu-id="4023e-209">这正是我在本指南中所做的。</span><span class="sxs-lookup"><span data-stu-id="4023e-209">That is exactly what I'm doing in this guide.</span></span> <span data-ttu-id="4023e-210">对于你所了解的关于脚本模块的所有内容，都能以同样的方式应用。</span><span class="sxs-lookup"><span data-stu-id="4023e-210">You can take everything you know about script modules and it all applies the same way.</span></span>
<span data-ttu-id="4023e-211">我今天创建了空 `psm1` 文件，稍后你可以考虑其他 PowerShell 函数。</span><span class="sxs-lookup"><span data-stu-id="4023e-211">The empty `psm1` file that I created today is there just so you can drop in other PowerShell functions later.</span></span>

<span data-ttu-id="4023e-212">我们创建的几乎所有已编译 cmdlet 一开始都是 PowerShell 函数。</span><span class="sxs-lookup"><span data-stu-id="4023e-212">Almost all of the compiled cmdlets that we created started out as a PowerShell function first.</span></span> <span data-ttu-id="4023e-213">所有二进制模块实际上都是混合模块。</span><span class="sxs-lookup"><span data-stu-id="4023e-213">All of our binary modules are really hybrid modules.</span></span>

### <a name="build-scripts"></a><span data-ttu-id="4023e-214">生成脚本</span><span class="sxs-lookup"><span data-stu-id="4023e-214">Build scripts</span></span>

<span data-ttu-id="4023e-215">这里我保持了生成脚本的简单性。</span><span class="sxs-lookup"><span data-stu-id="4023e-215">I kept the build script simple here.</span></span> <span data-ttu-id="4023e-216">我通常使用大型 `Invoke-Build` 脚本作为 CI/CD 管道的一部分。</span><span class="sxs-lookup"><span data-stu-id="4023e-216">I generally use a large `Invoke-Build` script as part of my CI/CD pipeline.</span></span> <span data-ttu-id="4023e-217">它确实更神奇，如运行 Pester 测试、运行 PSScriptAnalyzer、管理版本控制以及发布到 PSGallery。</span><span class="sxs-lookup"><span data-stu-id="4023e-217">It does more magic like running Pester tests, running PSScriptAnalyzer, managing versioning, and publishing to the PSGallery.</span></span> <span data-ttu-id="4023e-218">开始对模块使用生成脚本后，我可以找到许多要添加到其中的内容。</span><span class="sxs-lookup"><span data-stu-id="4023e-218">Once I started using a build script for my modules, I was able to find lots of things to add to it.</span></span>

## <a name="final-thoughts"></a><span data-ttu-id="4023e-219">结束语</span><span class="sxs-lookup"><span data-stu-id="4023e-219">Final thoughts</span></span>

<span data-ttu-id="4023e-220">二进制模块易于创建。</span><span class="sxs-lookup"><span data-stu-id="4023e-220">Binary modules are easy to create.</span></span> <span data-ttu-id="4023e-221">我没有提及创建 Cmdlet 的 C# 语法，但 [Windows PowerShell SDK][] 中提供了大量相关文档。</span><span class="sxs-lookup"><span data-stu-id="4023e-221">I didn't touch on the C# syntax for creating a Cmdlet, but there is plenty of documentation on it in the [Windows PowerShell SDK][].</span></span> <span data-ttu-id="4023e-222">作为深入了解 C# 的跳板，这绝对是值得尝试了解的内容。</span><span class="sxs-lookup"><span data-stu-id="4023e-222">It is definitely something worth experimenting with as a stepping stone into more serious C#.</span></span>

<!-- link references -->
[原始版本]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[original version]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[PowerShell 标准库]: https://github.com/PowerShell/PowerShellStandard
[PowerShell Standard Library]: https://github.com/PowerShell/PowerShellStandard
[创建跨平台二进制模块]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[Creating a cross-platform binary module]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[dotnet core SDK]: https://www.microsoft.com/net/download/core
[为 PSRepository 使用 NuGet 服务器]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Using a NuGet server for a PSRepository]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell-reference
[VS Code]: https://code.visualstudio.com
[nuget 包]: https://www.nuget.org/packages/PowerShellStandard.Library/
[nuget package]: https://www.nuget.org/packages/PowerShellStandard.Library/
