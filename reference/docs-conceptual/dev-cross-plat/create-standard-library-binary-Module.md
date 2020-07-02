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
# <a name="how-to-create-a-standard-library-binary-module"></a>如何创建标准库二进制模块

最近，我有了一个想要将模块实现为二进制模块的想法。 我还没有使用 [PowerShell 标准库][]创建过模块，这看起来是个不错的机会。 我利用[创建跨平台二进制模块][]指南成功创建了这一模块，没有任何障碍。
在这里，我们将执行同一过程，我将在此过程中添加一些额外的说明。

> [!NOTE]
> 本文的[原始版本][]发布在 [@KevinMarquette][] 撰写的博客上。 PowerShell 团队感谢 Kevin 与我们分享这篇文章。 请前往 [PowerShellExplained.com][] 访问他的博客。

## <a name="what-is-the-powershell-standard-library"></a>什么是 PowerShell 标准库？

使用 PowerShell 标准库，我们可以创建同时适用于 PowerShell Core 和 Windows PowerShell 5.1（或者 3.0）的跨平台模块。

## <a name="planning-our-module"></a>规划模块

此模块的计划是为 C# 代码创建一个 `src` 文件夹，并像对脚本模块那样构造其余内容。 这包括使用生成脚本将所有内容编译到 `output` 文件夹中。 该文件夹结构如下所示：

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

## <a name="getting-started"></a>入门

我通常会使用 Plaster 模板，但当前的模板尚不支持任何二进制模块。 小事一桩， 这次我会手动创建一个。

首先，我需要创建文件夹和 git 存储库。 我将 `$module` 用作模块名的占位符。 这会让你更轻松地重用这些示例（需要时）。

```powershell
$module = 'MyModule'
New-Item -Path $module -Type Directory
Set-Location $module
git init
```

然后创建根级别文件夹。

```powershell
New-Item -Path 'src' -Type Directory
New-Item -Path 'Output' -Type Directory
New-Item -Path 'Tests' -Type Directory
New-Item -Path $module -Type Directory
```

### <a name="binary-module-setup"></a>二进制模块设置

本文主要侧重于二进制模块，因此，我们将从这里开始。 本部分的示例来自[创建跨平台二进制模块][]指南。 如果你需要更多详细信息或遇到任何问题，请查阅该指南。

我们要做的第一件事是，检查安装的 [dotnet core SDK][] 版本。 我使用的是 2.1.4，但你应该用 2.0.0 或更高版本才能继续操作。

```powershell
PS> dotnet --version
2.1.4
```

我正在为这一部分做出 `src` 文件夹。

```powershell
Set-Location 'src'
```

使用 dotnet 命令创建一个新类库。

```powershell
dotnet new classlib --name $module
```

这会在子文件夹中创建库项目，但我不希望有额外的嵌套级别。 我要将这些文件上移一级。

```powershell
Move-Item -Path .\$module\* -Destination .\
Remove-Item $module -Recurse
```

为项目设置 .NET core SDK 版本。 我安装了 2.1 SDK，因此，我将指定 2.1.0。
如果你使用的是 2.0 SDK，请指定 2.0.0。

```powershell
dotnet new globaljson --sdk-version 2.1.0
```

将 PowerShell 标准库 [NuGet 包][]添加到项目中。 请确保你使用的是适用于你所需的兼容性级别的最新版本。 我将默认使用最新版本，但我并不认为此模块充分利用了版本高于 PowerShell 3.0 的任何功能。

```powershell
dotnet add package PowerShellStandard.Library --version 7.0.0-preview.1
```

我们应该有一个 src 文件夹，类似如下所示：

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

现在，我们已准备好将自己的代码添加到项目中。

### <a name="building-a-binary-cmdlet"></a>构建二进制 cmdlet

我们需要更新 `src\Class1.cs` 以包含这一开头的 cmdlet：

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

重命名文件，使其与类名匹配。

```powershell
Rename-Item .\Class1.cs .\ResolveMyCmdletCommand.cs
```

接下来，我们可以构建自己的模块。

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

我们可以对新 dll 调用 `Import-Module` 以加载新的 cmdlet。

```powershell
PS> Import-Module .\bin\Debug\netstandard2.0\$module.dll
PS> Get-Command -Module $module

CommandType Name                    Version Source
----------- ----                    ------- ------
Cmdlet      Resolve-MyCmdlet        1.0.0.0 MyModule
```

如果在你的系统上导入失败，请尝试将 .NET 更新到 4.7.1 或更新版本。 [创建跨平台二进制模块][]指南详细地介绍了较旧版本的 .NET 的 .NET 支持和兼容性。

### <a name="module-manifest"></a>模块清单

很酷的是，我们可以导入 dll 并获得一个有效的模块。 我想继续使用它并创建一个模块清单。 如果稍后要发布到 PSGallery，我们需要该清单。

在项目的根目录中，可以运行以下命令来创建所需的模块清单。

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

此外，我还要为将来的 PowerShell 函数创建一个空的根模块。

```powershell
Set-Content -Value '' -Path ".\$module\$module.psm1"
```

这样，我就可以将普通的 PowerShell 函数和二进制 Cmdlet 混合到同一个项目中。

### <a name="building-the-full-module"></a>生成完整的模块

我将所有内容编译到一个输出文件夹中。 我们需要创建一个生成脚本来实现这一点。 我通常会将它添加到 `Invoke-Build` 脚本，但在本例中可以简单一点。 将它添加到项目根目录中的 `build.ps1`。

```powershell
$module = 'MyModule'
Push-Location $PSScriptRoot

dotnet build $PSScriptRoot\src -o $PSScriptRoot\output\$module\bin
Copy-Item "$PSScriptRoot\$module\*" "$PSScriptRoot\output\$module" -Recurse -Force

Import-Module "$PSScriptRoot\Output\$module\$module.psd1"
Invoke-Pester "$PSScriptRoot\Tests"
```

这些命令会生成 DLL，并把它放到 `output\$module\bin` 文件夹中。 然后，将其他模块文件复制到该位置。

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

此时，可以导入我们的模块和 psd1 文件。

```powershell
Import-Module ".\Output\$module\$module.psd1"
```

在这里，我们可以将 `.\Output\$module` 文件夹放到 `$env:PSModulePath` 目录，它会在我们需要时自动加载命令。

### <a name="update-dotnet-new-psmodule"></a>更新：dotnet new PSModule

我了解到 `dotnet` 工具有一个 `PSModule` 模板。

我上面所述的所有步骤仍有效，但这个模板去掉了很多步骤。它还是一个非常新的模板，仍需要打磨。 希望从这里开始它能够更出色。

以下就是使用安装和使用 PSModule 模板的方式。

```powershell
dotnet new -i Microsoft.PowerShell.Standard.Module.Template
dotnet new psmodule
dotnet build
Import-Module "bin\Debug\netstandard2.0\$module.dll"
Get-Module $module
```

这种最低可行模板负责添加 .NET SDK、PowerShell 标准库，并在项目中创建一个示例类。 你可以立即生成并运行它。

## <a name="important-details"></a>重要详细信息

在结束本文之前，这里有一些其他的细节值得一提。

### <a name="unloading-dlls"></a>卸载 DLL

加载二进制模块后，就不能真正将其卸载。 DLL 文件会被锁定，直到你将其卸载。 在开发时，这可能会令人厌烦，因为每次进行更改并想要生成时，文件通常会被锁定。 解决此问题的唯一可靠方法是关闭加载 DLL 的 PowerShell 会话。

### <a name="vs-code-reload-window-action"></a>VS Code 重新加载窗口操作

我在 [VS Code][] 中完成了大部分 PowerShell 开发工作。 使用二进制模块（或包含类的模块）时，我习惯于每次生成时都重新加载 VS Code。
按 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> 会弹出命令窗口，`Reload Window` 始终在列表顶部。

### <a name="nested-powershell-sessions"></a>嵌套的 PowerShell 会话

另一个选项是拥有良好的 Pester 测试覆盖率。 然后，可以调整 build.ps1 脚本以启动新的 PowerShell 会话，执行内部版本，运行测试，最后关闭会话。

### <a name="updating-installed-modules"></a>更新已安装模块

尝试更新本地已安装的模块时，这种锁定可能会令人厌烦。 如果有任何会话加载了它，则必须找到并关闭它。 从 PSGallery 进行安装时，这不是什么大问题，因为模块版本控制在其他文件夹中放了一个新的。

可以设置本地 PSGallery，并作为生成操作的一部分进行发布。 然后从该 PSGallery 进行本地安装。 这听起来好像是个大工程，实际上像启动 docker 容器一样简单。 我在[为 PSRepository 使用 NuGet 服务器][]一文中介绍了一种方法。

## <a name="why-binary-modules"></a>为什么选择二进制模块？

我直接跳到了如何生成一个二进制模块，但没有提到为什么要这样做。 事实上，你正在编写 C# 并放弃了轻松访问 PowerShell Cmdlet 和函数的权利。 这就是我没有更快转向二进制模块的主要原因。

但是，如果你要创建不依赖于许多其他 PowerShell 命令的模块，则性能优势可能会很显著。 通过使用 C#，你可以减少 PowerShell 增加的开销。 PowerShell 针对管理员而不是计算机进行了优化，这会增加一些开销。

在工作中，我们有一个关键流程要通过 JSON 和哈希表完成大量工作。 我们已经尽可能优化 PowerShell，但此流程仍要运行 12 分钟之久。 模块中已包含很多 C# 样式 PowerShell。 这使得转换为二进制模块变得简单明了。 通过转换可以将该流程从 12 分钟以上缩短到 4 分钟以内。

### <a name="hybrid-modules"></a>混合模块

可以将二进制 Cmdlet 与 PowerShell 高级函数混合使用。 这正是我在本指南中所做的。 对于你所了解的关于脚本模块的所有内容，都能以同样的方式应用。
我今天创建了空 `psm1` 文件，稍后你可以考虑其他 PowerShell 函数。

我们创建的几乎所有已编译 cmdlet 一开始都是 PowerShell 函数。 所有二进制模块实际上都是混合模块。

### <a name="build-scripts"></a>生成脚本

这里我保持了生成脚本的简单性。 我通常使用大型 `Invoke-Build` 脚本作为 CI/CD 管道的一部分。 它确实更神奇，如运行 Pester 测试、运行 PSScriptAnalyzer、管理版本控制以及发布到 PSGallery。 开始对模块使用生成脚本后，我可以找到许多要添加到其中的内容。

## <a name="final-thoughts"></a>结束语

二进制模块易于创建。 我没有提及创建 Cmdlet 的 C# 语法，但 [Windows PowerShell SDK][] 中提供了大量相关文档。 作为深入了解 C# 的跳板，这绝对是值得尝试了解的内容。

<!-- link references -->
[原始版本]: https://powershellexplained.com/2018-08-04-Powershell-Standard-Library-Binary-Module/
[powershellexplained.com]: https://powershellexplained.com/
[@KevinMarquette]: https://twitter.com/KevinMarquette
[PowerShell 标准库]: https://github.com/PowerShell/PowerShellStandard
[创建跨平台二进制模块]: https://github.com/PowerShell/PowerShell/blob/master/docs/cmdlet-example/command-line-simple-example.md
[dotnet core SDK]: https://www.microsoft.com/net/download/core
[为 PSRepository 使用 NuGet 服务器]: https://powershellexplained.com/2018-03-03-Powershell-Using-a-NuGet-server-for-a-PSRepository/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell-reference
[VS Code]: https://code.visualstudio.com
[nuget 包]: https://www.nuget.org/packages/PowerShellStandard.Library/
