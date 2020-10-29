---
ms.date: 10/19/2020
keywords: powershell,cmdlet,调试
title: 使用 Visual Studio Code 调试已编译的 cmdlet
description: 如何为 .NET Core 中的 PSModule 项目设置生成任务和启动配置
ms.openlocfilehash: b51a69110c64b386f5c3ccf2527d1e184ef89257
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501637"
---
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a><span data-ttu-id="5aaaf-104">使用 Visual Studio Code 调试已编译的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="5aaaf-104">Using Visual Studio Code to debug compiled cmdlets</span></span>

<span data-ttu-id="5aaaf-105">本指南介绍如何使用 Visual Studio Code (VS Code) 和 C# 扩展，以交互方式调试已编译的 PowerShell 模块的 C# 源代码。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-105">This guide shows you how to interactively debug C# source code for a compiled PowerShell module using Visual Studio Code (VS Code) and the C# extension.</span></span>

<span data-ttu-id="5aaaf-106">本指南假设你对 Visual Studio Code 调试程序有一定的了解。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-106">Some familiarity with the Visual Studio Code debugger is assumed.</span></span>

- <span data-ttu-id="5aaaf-107">有关 VS Code 调试程序的一般简介，请参阅 [Visual Studio Code 中的调试][]。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-107">For a general introduction to the VS Code debugger, see [Debugging in Visual Studio Code][].</span></span>

- <span data-ttu-id="5aaaf-108">有关调试 PowerShell 脚本文件和模块的示例，请参阅[使用 Visual Studio Code 进行远程编辑和调试][]。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-108">For examples of debugging PowerShell script files and modules, see [Using Visual Studio Code for remote editing and debugging][].</span></span>

<span data-ttu-id="5aaaf-109">本指南假设你已经阅读并遵循了[编写可移植模块][]指南中的说明。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-109">This guide assumes you have read and followed the instructions in the [Writing Portable Modules][] guide.</span></span>

## <a name="creating-a-build-task"></a><span data-ttu-id="5aaaf-110">创建生成任务</span><span class="sxs-lookup"><span data-stu-id="5aaaf-110">Creating a build task</span></span>

<span data-ttu-id="5aaaf-111">在启动调试会话之前自动生成项目。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-111">Build your project automatically before launching a debugging session.</span></span> <span data-ttu-id="5aaaf-112">重新生成可确保调试最新版本的代码。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-112">Rebuilding ensures that you debug the latest version of your code.</span></span>

<span data-ttu-id="5aaaf-113">配置生成任务：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-113">Configure a build task:</span></span>

1. <span data-ttu-id="5aaaf-114">在“命令面板”中，运行“配置默认生成任务”命令 。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-114">In the **Command Palette** , run the **Configure Default Build Task** command.</span></span>

   ![运行配置默认生成任务](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. <span data-ttu-id="5aaaf-116">在“选择要配置的任务”对话框中，选择“从模板创建 tasks.json 文件” 。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-116">In the **Select a task to configure** dialog, choose **Create tasks.json file from template** .</span></span>

1. <span data-ttu-id="5aaaf-117">在“选择任务模板”对话框中，选择“.NET Core” 。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-117">In the **Select a Task Template** dialog, choose **.NET Core** .</span></span>

<span data-ttu-id="5aaaf-118">如果尚不存在 `tasks.json` 文件，则会创建一个新的该文件。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-118">A new `tasks.json` file is created if one doesn't exist yet.</span></span>

<span data-ttu-id="5aaaf-119">测试生成任务：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-119">To test your build task:</span></span>

1. <span data-ttu-id="5aaaf-120">在“命令面板”中，运行“运行生成任务”命令 。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-120">In the **Command Palette** , run the **Run Build Task** command.</span></span>

1. <span data-ttu-id="5aaaf-121">在“选择要运行的生成任务”对话框中，选择“生成” 。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-121">In the **Select the build task to run** dialog, choose **build** .</span></span>

### <a name="information-about-dll-files-being-locked"></a><span data-ttu-id="5aaaf-122">有关被锁定的 DLL 文件的信息</span><span class="sxs-lookup"><span data-stu-id="5aaaf-122">Information about DLL files being locked</span></span>

<span data-ttu-id="5aaaf-123">默认情况下，成功的生成不会在终端窗格中显示输出。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-123">By default, a successful build doesn't show output in the terminal pane.</span></span> <span data-ttu-id="5aaaf-124">如果你看到包含文本“项目文件不存在”的输出，则应编辑 `tasks.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-124">If you see output that contains the text **Project file doesn't exist** , you should edit the `tasks.json` file.</span></span> <span data-ttu-id="5aaaf-125">包含 C# 项目的显式路径，表示为 `"${workspaceFolder}/myModule"`。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-125">Include the explicit path to the C# project expressed as `"${workspaceFolder}/myModule"`.</span></span> <span data-ttu-id="5aaaf-126">在此示例中，`myModule` 是项目文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-126">In this example, `myModule` is the name of the project folder.</span></span> <span data-ttu-id="5aaaf-127">此条目必须位于 `args` 列表的 `build` 条目后，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-127">This entry must go after the `build` entry in the `args` list as follows:</span></span>

```json
    {
        "label": "build",
        "command": "dotnet",
        "type": "shell",
        "args": [
            "build",
            "${workspaceFolder}/myModule",
            // Ask dotnet build to generate full paths for file names.
            "/property:GenerateFullPaths=true",
            // Do not generate summary otherwise it leads to duplicate errors in Problems panel
            "/consoleloggerparameters:NoSummary",
        ],
        "group": "build",
        "presentation": {
            "reveal": "silent"
        },
        "problemMatcher": "$msCompile"
    }
```

<span data-ttu-id="5aaaf-128">调试时，模块 DLL 将导入到 VS Code 终端的 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-128">When debugging, your module DLL is imported into the PowerShell session in the VS Code terminal.</span></span> <span data-ttu-id="5aaaf-129">DLL 将被锁定。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-129">The DLL becomes locked.</span></span> <span data-ttu-id="5aaaf-130">在不关闭终端会话的情况下运行生成任务时，将显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-130">The following message is displayed when you run the build task without closing the terminal session:</span></span>

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

<span data-ttu-id="5aaaf-131">必须先关闭终端会话，然后再重新生成。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-131">Terminal sessions must be closed before you rebuild.</span></span>

## <a name="setting-up-the-debugger"></a><span data-ttu-id="5aaaf-132">设置调试程序</span><span class="sxs-lookup"><span data-stu-id="5aaaf-132">Setting up the debugger</span></span>

<span data-ttu-id="5aaaf-133">若要调试 PowerShell cmdlet，需要设置自定义启动配置。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-133">To debug the PowerShell cmdlet, you need to set up a custom launch configuration.</span></span> <span data-ttu-id="5aaaf-134">此配置用于：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-134">This configuration is used to:</span></span>

- <span data-ttu-id="5aaaf-135">生成源代码</span><span class="sxs-lookup"><span data-stu-id="5aaaf-135">Build your source code</span></span>
- <span data-ttu-id="5aaaf-136">启动 PowerShell 并加载模块</span><span class="sxs-lookup"><span data-stu-id="5aaaf-136">Start PowerShell with your module loaded</span></span>
- <span data-ttu-id="5aaaf-137">在终端窗格中使 PowerShell 保持打开状态</span><span class="sxs-lookup"><span data-stu-id="5aaaf-137">Leave PowerShell open in the terminal pane</span></span>

<span data-ttu-id="5aaaf-138">在终端会话中调用 cmdlet 时，调试程序会在源代码中设置的任何断点处停止。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-138">When you invoke your cmdlet in the terminal session, the debugger stops at any breakpoints set in your source code.</span></span>

### <a name="configuring-launchjson-for-powershell-core"></a><span data-ttu-id="5aaaf-139">为 PowerShell Core 配置 launch.json</span><span class="sxs-lookup"><span data-stu-id="5aaaf-139">Configuring launch.json for PowerShell Core</span></span>

1. <span data-ttu-id="5aaaf-140">安装[适用于 Visual Studio Code 的 C#][] 扩展</span><span class="sxs-lookup"><span data-stu-id="5aaaf-140">Install the [C# for Visual Studio Code][] extension</span></span>

1. <span data-ttu-id="5aaaf-141">在“调试”窗格中添加调试配置</span><span class="sxs-lookup"><span data-stu-id="5aaaf-141">In the Debug pane, add a debug configuration</span></span>

1. <span data-ttu-id="5aaaf-142">在 `Select environment` 对话框中，选择 `.NET Core`</span><span class="sxs-lookup"><span data-stu-id="5aaaf-142">In the `Select environment` dialog, choose `.NET Core`</span></span>

1. <span data-ttu-id="5aaaf-143">`launch.json` 文件将在编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-143">The `launch.json` file is opened in the editor.</span></span> <span data-ttu-id="5aaaf-144">将光标置于 `configurations` 数组中时，会看到 `configuration` 选择器。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-144">With your cursor inside the `configurations` array, you see the `configuration` picker.</span></span> <span data-ttu-id="5aaaf-145">如果看不到此列表，请选择“添加配置”。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-145">If you don't see this list, select **Add Configuration** .</span></span>

1. <span data-ttu-id="5aaaf-146">若要创建默认的调试配置，请选择“启动 .NET Core 控制台应用”：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-146">To create a default debug configuration, select **Launch .NET Core Console App** :</span></span>

   ![启动 .NET Core 控制台应用](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. <span data-ttu-id="5aaaf-148">编辑 `name`、`program`、`args` 和 `console` 字段，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-148">Edit the `name`, `program`, `args`, and `console` fields as follows:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: pwsh",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "pwsh",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

<span data-ttu-id="5aaaf-149">`program` 字段用于启动 `pwsh`，以便可以运行正在调试的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-149">The `program` field is used to launch `pwsh` so that the cmdlet being debugged can be run.</span></span> <span data-ttu-id="5aaaf-150">`-NoExit` 参数防止 PowerShell 会话在导入模块后立即退出。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-150">The `-NoExit` argument prevents the PowerShell session from exiting as soon as the module is imported.</span></span>
<span data-ttu-id="5aaaf-151">如果已遵循[编写可移植模块][]指南，则 `Import-Module` 参数中的路径为默认生成输出路径。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-151">The path in the `Import-Module` argument is the default build output path when you've followed the [Writing Portable Modules][] guide.</span></span> <span data-ttu-id="5aaaf-152">如果创建了模块清单（`.psd1` 文件），则应使用该清单的路径。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-152">If you've created a module manifest (`.psd1` file), you should use the path to that instead.</span></span> <span data-ttu-id="5aaaf-153">`/` 路径分隔符适用于 Windows、Linux 和 macOS。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-153">The `/` path separator works on Windows, Linux, and macOS.</span></span> <span data-ttu-id="5aaaf-154">必须使用集成终端运行要调试的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-154">You must use the integrated terminal to run the PowerShell commands you want to debug.</span></span>

> [!NOTE]
> <span data-ttu-id="5aaaf-155">如果调试程序未在任何断点处停止，请在 Visual Studio Code 调试控制台中查找显示以下内容的行：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-155">If the debugger doesn't stop at any breakpoints, look in the Visual Studio Code Debug Console for a line that says:</span></span>
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> <span data-ttu-id="5aaaf-156">如果看到此情况，请将 `"justMyCode": false` 添加到启动配置中（与 `"console": "integratedTerminal"` 处于同一级别）。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-156">If you see this, add `"justMyCode": false` to your launch config (at the same level as `"console": "integratedTerminal"`.</span></span>

### <a name="configuring-launchjson-for-windows-powershell"></a><span data-ttu-id="5aaaf-157">为 Windows PowerShell 配置 launch.json</span><span class="sxs-lookup"><span data-stu-id="5aaaf-157">Configuring launch.json for Windows PowerShell</span></span>

<span data-ttu-id="5aaaf-158">此启动配置适用于在 Windows PowerShell (`powershell.exe`) 中测试 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-158">This launch configuration works for testing your cmdlets in Windows PowerShell (`powershell.exe`).</span></span>
<span data-ttu-id="5aaaf-159">使用以下更改创建第二个启动配置：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-159">Create a second launch configuration with the following changes:</span></span>

1. <span data-ttu-id="5aaaf-160">`name` 应为 `PowerShell cmdlets: powershell`</span><span class="sxs-lookup"><span data-stu-id="5aaaf-160">`name` should be `PowerShell cmdlets: powershell`</span></span>

1. <span data-ttu-id="5aaaf-161">`type` 应为 `clr`</span><span class="sxs-lookup"><span data-stu-id="5aaaf-161">`type` should be `clr`</span></span>

1. <span data-ttu-id="5aaaf-162">`program` 应为 `powershell`</span><span class="sxs-lookup"><span data-stu-id="5aaaf-162">`program` should be `powershell`</span></span>

   <span data-ttu-id="5aaaf-163">应如下所示：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-163">It should look like this:</span></span>

   ```json
    {
        "name": "PowerShell cmdlets: powershell",
        "type": "clr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "powershell",
        "args": [
            "-NoExit",
            "-NoProfile",
            "-Command",
            "Import-Module ${workspaceFolder}/myModule/bin/Debug/netstandard2.0/myModule.dll",
        ],
        "cwd": "${workspaceFolder}",
        "stopAtEntry": false,
        "console": "integratedTerminal"
    }
   ```

## <a name="launching-a-debugging-session"></a><span data-ttu-id="5aaaf-164">启动调试会话</span><span class="sxs-lookup"><span data-stu-id="5aaaf-164">Launching a debugging session</span></span>

<span data-ttu-id="5aaaf-165">现在一切准备就绪，可以开始调试。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-165">Now everything is ready to begin debugging.</span></span>

- <span data-ttu-id="5aaaf-166">在要调试的 cmdlet 的源代码中放置一个断点：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-166">Place a breakpoint in the source code for the cmdlet you want to debug:</span></span>

  ![断点显示为装订线中的一个红点](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- <span data-ttu-id="5aaaf-168">确保在“调试”视图的配置下拉菜单中选择了相关的 PowerShell cmdlet 配置 ：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-168">Ensure that the relevant **PowerShell cmdlets** configuration is selected in the configuration drop-down menu in the **Debug** view:</span></span>

  ![选择启动配置](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- <span data-ttu-id="5aaaf-170">按 F5 或单击“启动调试”按钮<kbd></kbd></span><span class="sxs-lookup"><span data-stu-id="5aaaf-170">Press <kbd>F5</kbd> or click on the **Start Debugging** button</span></span>

- <span data-ttu-id="5aaaf-171">切换到终端窗格并调用 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-171">Switch to the terminal pane and invoke your cmdlet:</span></span>

  ![调用 cmdlet](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- <span data-ttu-id="5aaaf-173">执行在断点处停止：</span><span class="sxs-lookup"><span data-stu-id="5aaaf-173">Execution stops at the breakpoint:</span></span>

  ![执行在断点处暂停](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

<span data-ttu-id="5aaaf-175">可以单步执行源代码、检查变量并检查调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-175">You can step through the source code, inspect variables, and inspect the call stack.</span></span>

<span data-ttu-id="5aaaf-176">若要结束调试，请单击调试工具栏中的“停止”，或按 Shift-F5<kbd></kbd><kbd></kbd>。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-176">To end debugging, click **Stop** in the debug toolbar or press <kbd>Shift</kbd>-<kbd>F5</kbd>.</span></span> <span data-ttu-id="5aaaf-177">用于调试的 shell 将退出并解除对已编译的 DLL 文件的锁定。</span><span class="sxs-lookup"><span data-stu-id="5aaaf-177">The shell used for debugging exits and releases the lock on the compiled DLL file.</span></span>

<!-- reference links -->
[在 Visual Studio Code 中进行调试]: https://code.visualstudio.com/docs/editor/debugging
[Debugging in Visual Studio Code]: https://code.visualstudio.com/docs/editor/debugging
[使用 Visual Studio Code 进行远程编辑和调试]: using-vscode-for-remote-editing-and-debugging.md
[Using Visual Studio Code for remote editing and debugging]: using-vscode-for-remote-editing-and-debugging.md
[编写可移植模块]: ../writing-portable-modules.md
[Writing Portable Modules]: ../writing-portable-modules.md
[用于 Visual Studio Code 的 C#]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
[C# for Visual Studio Code]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
