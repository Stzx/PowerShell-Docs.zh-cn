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
# <a name="using-visual-studio-code-to-debug-compiled-cmdlets"></a>使用 Visual Studio Code 调试已编译的 cmdlet

本指南介绍如何使用 Visual Studio Code (VS Code) 和 C# 扩展，以交互方式调试已编译的 PowerShell 模块的 C# 源代码。

本指南假设你对 Visual Studio Code 调试程序有一定的了解。

- 有关 VS Code 调试程序的一般简介，请参阅 [Visual Studio Code 中的调试][]。

- 有关调试 PowerShell 脚本文件和模块的示例，请参阅[使用 Visual Studio Code 进行远程编辑和调试][]。

本指南假设你已经阅读并遵循了[编写可移植模块][]指南中的说明。

## <a name="creating-a-build-task"></a>创建生成任务

在启动调试会话之前自动生成项目。 重新生成可确保调试最新版本的代码。

配置生成任务：

1. 在“命令面板”中，运行“配置默认生成任务”命令 。

   ![运行配置默认生成任务](media/using-vscode-for-debugging-compiled-cmdlets/configure-default-build-task.png)

1. 在“选择要配置的任务”对话框中，选择“从模板创建 tasks.json 文件” 。

1. 在“选择任务模板”对话框中，选择“.NET Core” 。

如果尚不存在 `tasks.json` 文件，则会创建一个新的该文件。

测试生成任务：

1. 在“命令面板”中，运行“运行生成任务”命令 。

1. 在“选择要运行的生成任务”对话框中，选择“生成” 。

### <a name="information-about-dll-files-being-locked"></a>有关被锁定的 DLL 文件的信息

默认情况下，成功的生成不会在终端窗格中显示输出。 如果你看到包含文本“项目文件不存在”的输出，则应编辑 `tasks.json` 文件。 包含 C# 项目的显式路径，表示为 `"${workspaceFolder}/myModule"`。 在此示例中，`myModule` 是项目文件夹的名称。 此条目必须位于 `args` 列表的 `build` 条目后，如下所示：

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

调试时，模块 DLL 将导入到 VS Code 终端的 PowerShell 会话中。 DLL 将被锁定。 在不关闭终端会话的情况下运行生成任务时，将显示以下消息：

```Output
Could not copy "obj\Debug\netstandard2.0\myModule.dll" to "bin\Debug\netstandard2.0\myModule.dll"`.
```

必须先关闭终端会话，然后再重新生成。

## <a name="setting-up-the-debugger"></a>设置调试程序

若要调试 PowerShell cmdlet，需要设置自定义启动配置。 此配置用于：

- 生成源代码
- 启动 PowerShell 并加载模块
- 在终端窗格中使 PowerShell 保持打开状态

在终端会话中调用 cmdlet 时，调试程序会在源代码中设置的任何断点处停止。

### <a name="configuring-launchjson-for-powershell-core"></a>为 PowerShell Core 配置 launch.json

1. 安装[适用于 Visual Studio Code 的 C#][] 扩展

1. 在“调试”窗格中添加调试配置

1. 在 `Select environment` 对话框中，选择 `.NET Core`

1. `launch.json` 文件将在编辑器中打开。 将光标置于 `configurations` 数组中时，会看到 `configuration` 选择器。 如果看不到此列表，请选择“添加配置”。

1. 若要创建默认的调试配置，请选择“启动 .NET Core 控制台应用”：

   ![启动 .NET Core 控制台应用](media/using-vscode-for-debugging-compiled-cmdlets/add-configuration-dialog.png)

1. 编辑 `name`、`program`、`args` 和 `console` 字段，如下所示：

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

`program` 字段用于启动 `pwsh`，以便可以运行正在调试的 cmdlet。 `-NoExit` 参数防止 PowerShell 会话在导入模块后立即退出。
如果已遵循[编写可移植模块][]指南，则 `Import-Module` 参数中的路径为默认生成输出路径。 如果创建了模块清单（`.psd1` 文件），则应使用该清单的路径。 `/` 路径分隔符适用于 Windows、Linux 和 macOS。 必须使用集成终端运行要调试的 PowerShell 命令。

> [!NOTE]
> 如果调试程序未在任何断点处停止，请在 Visual Studio Code 调试控制台中查找显示以下内容的行：
>
> ```
> Loaded '/path/to/myModule.dll'. Skipped loading symbols. Module is optimized and the debugger option 'Just My Code' is enabled.
> ```
>
> 如果看到此情况，请将 `"justMyCode": false` 添加到启动配置中（与 `"console": "integratedTerminal"` 处于同一级别）。

### <a name="configuring-launchjson-for-windows-powershell"></a>为 Windows PowerShell 配置 launch.json

此启动配置适用于在 Windows PowerShell (`powershell.exe`) 中测试 cmdlet。
使用以下更改创建第二个启动配置：

1. `name` 应为 `PowerShell cmdlets: powershell`

1. `type` 应为 `clr`

1. `program` 应为 `powershell`

   应如下所示：

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

## <a name="launching-a-debugging-session"></a>启动调试会话

现在一切准备就绪，可以开始调试。

- 在要调试的 cmdlet 的源代码中放置一个断点：

  ![断点显示为装订线中的一个红点](media/using-vscode-for-debugging-compiled-cmdlets/set-breakpoint.png)

- 确保在“调试”视图的配置下拉菜单中选择了相关的 PowerShell cmdlet 配置 ：

  ![选择启动配置](media/using-vscode-for-debugging-compiled-cmdlets/select-launch-configuration.png)

- 按 F5 或单击“启动调试”按钮<kbd></kbd>

- 切换到终端窗格并调用 cmdlet：

  ![调用 cmdlet](media/using-vscode-for-debugging-compiled-cmdlets/invoke-the-cmdlet.png)

- 执行在断点处停止：

  ![执行在断点处暂停](media/using-vscode-for-debugging-compiled-cmdlets/stopped-at-breakpoint.png)

可以单步执行源代码、检查变量并检查调用堆栈。

若要结束调试，请单击调试工具栏中的“停止”，或按 Shift-F5<kbd></kbd><kbd></kbd>。 用于调试的 shell 将退出并解除对已编译的 DLL 文件的锁定。

<!-- reference links -->
[在 Visual Studio Code 中进行调试]: https://code.visualstudio.com/docs/editor/debugging
[使用 Visual Studio Code 进行远程编辑和调试]: using-vscode-for-remote-editing-and-debugging.md
[编写可移植模块]: ../writing-portable-modules.md
[用于 Visual Studio Code 的 C#]: https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp
