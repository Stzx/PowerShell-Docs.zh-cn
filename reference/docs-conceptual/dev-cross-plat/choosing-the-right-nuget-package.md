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
# <a name="choosing-the-right-powershell-nuget-package-for-your-net-project"></a>为 .NET 项目选择正确的 PowerShell NuGet 包

PowerShell 团队不仅会维护随每种 PowerShell 版本一起发布的 `pwsh` 可执行包，还会维护 [NuGet][] 上提供的多个包。 这些包允许将 PowerShell 视为 .NET 中的 API 平台。

作为提供 API 并希望加载实现自己的（二进制模块）的 .NET 库的 .NET 应用程序，必须以 NuGet 包的形式提供 PowerShell。

目前，有多个 NuGet 包提供 PowerShell API 外围应用的某种表示形式。 特定项目使用哪种包并不总是明确。 本文介绍了一些面向 PowerShell 的 .NET 项目的常见方案，以及如何为面向 PowerShell 的 .NET 项目选择合适的 NuGet 包。

## <a name="hosting-vs-referencing"></a>托管与引用

一些 .NET 项目设法编写要加载到预先存在的 PowerShell 运行时（例如 `pwsh`、`powershell.exe` 和 PowerShell 集成控制台或 ISE）中的代码，而其他 .NET 项目则希望在自己的应用程序中运行 PowerShell。

- 引用适用于打算将项目（通常是模块）加载到 PowerShell 中的情况。
  必须针对 PowerShell 提供的 API 编译引用编译才能与之交互，但 PowerShell 实现是由将其加载到其中的 PowerShell 进程提供的。 若要进行引用，项目可以使用引[用程序集][]或实际运行时程序集作为编译目标，但必须确保项目不会在其构建中发布任何这些程序集。
- 托管是指项目需要自己的 PowerShell 实现，通常是因为项目需要运行 PowerShell 的独立应用程序。 在这种情况下，不能使用纯引用程序集。 而是必须依赖具体的 PowerShell 实现。 由于必须使用具体的 PowerShell 实现，因此必须选择特定版本的 PowerShell 进行托管；单个主机应用程序不能有多个目标 PowerShell 版本。

### <a name="publishing-projects-that-target-powershell-as-a-reference"></a>发布以 PowerShell 作为引用的项目

> [!NOTE]
> 我们在本文中使用术语“发布”来指代运行 `dotnet publish`，该运行会将 .NET 库放入包含其所有依赖项的目录中，以准备好部署到特定的运行时。

为了防止发布仅用作编译引用目标的项目依赖项，建议设置 [PrivateAssets 属性][]：

```xml
<PackageReference Include="PowerShellStandard.Library" Version="5.1.0.0" PrivateAssets="all" />
```

如果忘记执行此操作，并将引用程序集用作目标，则可能会出现与使用引用程序集的默认实现（而不是实际实现）相关的问题。 这可能采用 `NullReferenceException` 的形式，因为引用程序集通常只需返回 `null` 即可模拟实现 API。

## <a name="key-kinds-of-powershell-targeting-net-projects"></a>面向 PowerShell 的 .NET 项目的主要类型

尽管任何 .NET 库或应用程序都可以嵌入 PowerShell，但某些常见场景下会使用 PowerShell API：

- **实现 PowerShell 二进制模块**

  PowerShell 二进制模块是由 PowerShell 加载的 .NET 库，必须实现 PowerShell API（例如 [PSCmdlet][] 或 [CmdletProvider][] 类型）才能分别公开 cmdlet 或提供程序。 由于已加载这些模块，因此模块会设法根据对 PowerShell 的引用进行编译，而不在其生成过程中发布。 通常，模块也希望支持多种 PowerShell 版本和平台，最好能够最大限度地减少磁盘空间的开销、复杂性或重复实现。 有关模块的详细信息，请参阅 [about_Modules][]。

- **实现 PowerShell 主机**

  PowerShell 主机为 PowerShell 运行时提供交互层。 该交互层是托管的一种特定形式，其中 [PSHost][] 作为 PowerShell 的新用户界面实现。 例如，PowerShell ConsoleHost 为 PowerShell 可执行文件提供终端用户界面，而 PowerShell 编辑器服务主机和 ISE 主机均为 PowerShell 提供集成了编辑器的部分图形用户界面。 虽然可以将主机加载到现有 PowerShell 进程中，但更为常见的是，主机实现充当重新分发 PowerShell 引擎的独立 PowerShell 实现。

- **从其他 .NET 应用程序调用 PowerShell**

  与任何应用程序一样，PowerShell 可以作为运行工作负载的子进程来进行调用。 但 PowerShell 作为一种 .NET 应用程序，也可以在进程内调用它来获取完整的 .NET 对象，以供在调用应用程序的过程中使用。 这是一种更为常见的托管形式，其中应用程序拥有自己的 PowerShell 实现，供内部使用。 此类示例可以是运行 PowerShell 以管理计算机状态的服务或守护程序，也可以是按请求运行 PowerShell 以执行某些操作（例如管理云部署）的 Web 应用程序。

- **从 .NET 对 PowerShell 模块进行单元测试**

  虽然应主要通过 PowerShell 测试专用于向 PowerShell 公开功能的模块和其他库（建议使用 [Pester][]），但有时需要从 .NET 为 PowerShell 模块编写的 API 进行单元测试。 这种情况涉及到尝试以多种 PowerShell 版本为目标的模块代码，而测试应在特定的具体实现上运行该代码。

## <a name="powershell-nuget-packages-at-a-glance"></a>PowerShell NuGet 包概述

在本文中，我们将介绍以下可公开 PowerShell API 的 NuGet 包：

- [PowerShellStandard.Library][] 是引用程序集，可用于构建一个可由多个 PowerShell 运行时加载的程序集。
- [Microsoft.PowerShell.SDK][] 用于面向整个 PowerShell SDK 并对其进行重新托管
- [System.Management.Automation][] 包是核心 PowerShell 运行时和引擎实现，适用于最少的托管实现以及特定于版本的目标设定场景。
- Windows PowerShell 引用程序集用于面向 Windows PowerShell（PowerShell 版本 5.1 及更低版本）并对其进行有效托管。

> [!NOTE]
> [PowerShell NuGet][] 包根本不是 .NET 库包，但会提供 PowerShell dotnet 全局工具实现。 任何项目都不应使用此包，因为它仅提供可执行文件。

## <a name="powershellstandardlibrary"></a>PowerShellStandard.Library

PowerShell Standard 库是引用程序集，可捕获 PowerShell 版本 7、6 和 5.1 的 API 的交集。 该库提供了经过编译时检查的 API 图面，可以根据其编译 .NET 代码，从而使 .NET 项目可以面向 PowerShell 版本 7、6 和 5.1，而不必冒险调用不存在的 API。

PowerShell Standard 用于编写 PowerShell 模块或其他代码（只有将代码加载到 PowerShell 进程后才能运行）。 由于 PowerShell Standard 是引用程序集，它本身不包含任何实现，因此不为独立应用程序提供任何功能。

### <a name="using-powershell-standard-with-different-net-runtimes"></a>将 PowerShell Standard 用于不同的 .NET 运行时

PowerShell Standard 面向 [.NET Standard 2.0][] 目标运行时，后者是外观运行时，旨在提供 .NET Framework 和 .NET Core 共享的公共外围应用。 这样就可以将单个运行时作为目标，以生成可用于多种 PowerShell 版本的单个程序集，但具有以下后果：

- 加载模块或库的 PowerShell 必须至少运行 .NET 4.6.1；.NET 4.6 和 .NET 4.5.2 不支持 .NET Standard。 请注意，Windows PowerShell 版本越新并不意味着 .NET Framework 版本越新。Windows PowerShell 5.1 可在 .NET 4.5.2 上运行。
- 为使用运行 .NET Framework 4.7.1 或更低版本的 PowerShell，.NET 4.6.1 [NETStandard.Library][] 实现需要在旧版 .NET Framework 中提供 netstandard.dll 和其他填充码程序集。

PowerShell 6 及更高版本提供自己的填充码程序集，用于从 .NET Framework 4.6.1（及更高版本）到 .NET Core 的类型转发。 这意味着，只要模块仅使用 .NET Core 中存在的 API，PowerShell 6 及更高版本就可以在为 .NET Framework 4.6.1（`net461` 运行时目标）构建模块时加载并运行该模块。

这意味着使用 PowerShell Standard 面向具有单个发布的 DLL 的多种 PowerShell 版本的二进制模块有两个选项：

1. 发布为 `net461` 目标运行时构建的程序集。 这涉及：
   - 为 `net461` 运行时发布项目
   - 还要针对 `netstandard2.0` 运行时进行编译（不使用其生成输出），确保所使用的所有 API 也都存在于 .NET Core 中。

1. 发布为 `netstandard2.0` 目标运行时构建的程序集。 这需要：
   - 为 `netstandard2.0` 运行时发布项目
   - 获取 NETStandard.Library 的 `net461` 依赖项并将其复制到项目程序集的发布位置，以便在 .NET Framework 中对程序集进行正确类型转发。

若要构建面向旧版 .NET Framework 的 PowerShell 模块或库，可能面向多个 .NET 运行时更好。 这将为每个目标运行时发布一个程序集，并且需要在模块加载时加载合适的程序集（例如，以较小的 psm1 作为根模块）。

### <a name="testing-powershell-standard-projects-in-net"></a>在 .NET 中测试 PowerShell Standard 项目

在 .NET 测试运行程序（例如 xUnit）中测试模块时，请记住，编译时检查提供的帮助不大。 必须针对相关的 PowerShell 平台测试模块。

若要测试针对 .NET 中的 PowerShell Standard 构建的 API，你应该向 .NET Core 添加 `Microsoft.Powershell.SDK` 作为（其版本设置为与所需 PowerShell 版本相匹配）测试依赖项，并对 .NET Framework 添加相应的 Windows PowerShell 引用程序集。

若要详细了解 PowerShell Standard 以及如何将其用于编写可在多种 PowerShell 版本中使用的二进制模块，请参阅[这篇博客文章][]。 另请参阅 GitHub 上的 [PowerShell Standard 存储库][]。

## <a name="microsoftpowershellsdk"></a>Microsoft.PowerShell.SDK

`Microsoft.PowerShell.SDK` 是一个元包，可将 PowerShell SDK 的所有组件组合到单个 NuGet 包中。 独立 .NET 应用程序可以使用 Microsoft.PowerShell.SDK 运行任意 PowerShell 功能，而无需依赖任何外部 PowerShell 安装或库。

> [!NOTE]
> PowerShell SDK 仅仅是指构成 PowerShell 的所有组件包，而这些包可用于通过 PowerShell 进行 .NET 开发。

给定的 `Microsoft.Powershell.SDK` 版本包含同一版本的 PowerShell 应用程序的具体实现；7.0 版包含 PowerShell 7.0 的实现，并且使用该实现运行命令或脚本的方式主要取决于在 PowerShell 7.0 中运行这些命令或脚本的方式。

从 SDK 运行 PowerShell 命令与从 `pwsh` 运行这些命令大体相同，但不完全相同。 例如，[Start-Job][] 当前取决于可用的 `pwsh` 可执行文件，因此默认情况下不能与 `Microsoft.Powershell.SDK` 一起使用。

通过将 .NET 应用程序中的 `Microsoft.Powershell.SDK` 作为目标，你可以与 PowerShell 的所有实现程序集（例如 `System.Management.Automation`、`Microsoft.PowerShell.Management` 和其他模块程序集）集成。

发布面向 `Microsoft.Powershell.SDK` 的应用程序将包括所有这些程序集，以及 PowerShell 所需的所有依赖项。 其中还将包括 PowerShell 在其构建过程中所需的其他资产，例如 `Microsoft.PowerShell.*` 模块的模块清单和 [Add-Type][] 所需的 `ref` 目录。

鉴于 `Microsoft.Powershell.SDK` 的完整性，它最适用于：

- PowerShell 主机的实现。
- 对面向 PowerShell 引用程序集的库进行 xUnit 测试。
- 从 .NET 应用程序在进程内调用 PowerShell。

打算将 .NET 项目用作模块或由 PowerShell 加载时，`Microsoft.PowerShell.SDK` 也可以用作引用目标，但这取决于只有特定版本的 PowerShell 中才存在的 API。 请注意，针对特定版本的 `Microsoft.PowerShell.SDK` 发布的程序集只能在该版本的 PowerShell 中安全地加载和使用。 若要面向具有特定 API 的多种 PowerShell 版本，则需要多个构建，每个构建都面向其自己的 `Microsoft.Powershell.SDK` 版本。

> [!NOTE]
> PowerShell SDK 仅适用于 PowerShell 版本 6 及更高版本。 若要提供 Windows PowerShell 的等效功能，请使用下面介绍的 Windows PowerShell 引用程序集。

## <a name="systemmanagementautomation"></a>System.Management.Automation

`System.Management.Automation` 包是 PowerShell SDK 的核心。 该包主要位于 NuGet 上，作为供 `Microsoft.Powershell.SDK` 引入的资产。 不过，该包也可以直接用作包，用于较小的托管方案和面向版本的模块。

具体而言，对于以下情况，`System.Management.Automation` 包可能是 PowerShell 功能的首选提供程序：

- 你只希望使用 PowerShell 语言功能（在 `System.Management.Automation.Language` 名称空间中），如 PowerShell 分析程序、AST 和 AST 访问者 API（例如，对 PowerShell 进行静态分析）。
- 你只希望从 `Microsoft.PowerShell.Core` 模块执行特定命令且可在使用 [CreateDefault2][] 工厂方法创建的会话状态下执行这些命令。

此外，对于以下情况，`System.Management.Automation` 是有用的引用程序集：

- 你希望面向只有特定 PowerShell 版本中才存在的 API
- 你不会依赖于 `System.Management.Automation` 程序集之外发生的类型（例如，由 `Microsoft.PowerShell.*` 模块中的 cmdlet 导出的类型）。

## <a name="windows-powershell-reference-assemblies"></a>Windows PowerShell 引用程序集

对于 PowerShell 版本 5.1 及更低版本 (Windows PowerShell)，没有 SDK 可提供 PowerShell 的实现，因为 Windows PowerShell 的实现是 Windows 的一部分。

相反，Windows PowerShell 引用程序集既提供引用目标，又提供一种重新托管 Windows PowerShell 的方式，其行为与 PowerShell SDK 版本 6 及更高版本相同。

Windows PowerShell 引用程序集针对每个版本的 Windows PowerShell 具有不同的包，而不是按版本区分：

- [PowerShell 5.1](https://www.nuget.org/packages/Microsoft.PowerShell.5.ReferenceAssemblies/)
- [PowerShell 4](https://www.nuget.org/packages/Microsoft.PowerShell.4.ReferenceAssemblies/)
- [PowerShell 3](https://www.nuget.org/packages/Microsoft.PowerShell.3.ReferenceAssemblies/)

有关如何使用 Windows PowerShell 引用程序集的信息，请参阅 [Windows PowerShell SDK][]。

## <a name="real-world-examples-using-these-nuget-packages"></a>使用这些 NuGet 包的实际示例

根据其需求，不同的 PowerShell 工具项目以不同的 PowerShell NuGet 包为目标。 下面列出了一些值得注意的示例。

### <a name="psreadline"></a>PSReadLine

[PSReadLine][] 是提供大部分 PowerShell 丰富控制台经验的 PowerShell 模块，将 PowerShell Standard（而不是特定的 PowerShell 版本）作为依赖项目标，并面向 [csproj][] 中的 `net461` .NET 运行时。

PowerShell 6 及更高版本提供自己的填充码程序集，这些程序集允许以 `net461` 运行时为目标的 DLL 在加载后“正常工作”（通过将绑定到 .NET Framework 的 `mscorlib.dll` 重定向到相关的 .NET Core 程序集）。

由于 PowerShell Standard 确保 PowerShell 5.1 和 PowerShell 6 及更高版本中都存在唯一使用过的 API，这大大简化了 PSReadLine 的模块布局和交付，同时还允许该模块仅随单个组件一起提供。

不过，.NET 4.6.1 目标确实表示不支持在 .NET 4.5.2 和 .NET 4.6 上运行的 Windows PowerShell。

### <a name="powershell-editor-services"></a>PowerShell 编辑器服务

[PowerShell 编辑器服务][] (PSES) 是用于 [Visual Studio Code][] 的 [PowerShell 扩展][]的后端，这实际上是 PowerShell 模块的一种形式，该模块由 PowerShell 可执行文件加载，然后接管该过程以在其内部重新托管 PowerShell，同时还提供语言服务协议和调试适配器功能。

PSES 为 `netcoreapp2.1` 和 `net461` 提供具体的实现目标，以分别面向 PowerShell 6 及更高版本（因为 PowerShell 7 的 `netcoreapp3.1` 运行时后向兼容）和 Windows PowerShell 5.1，但其大部分逻辑包含在面向 `netstandard2.0` 和 PowerShell Standard 的第二个程序集中。 这使 PSES 可以引入 .NET Core 和 .NET Framework 平台所需的依赖项，同时还可简化统一抽象背后的大多数代码库。

由于 PSES 针对 PowerShell Standard 而构建，因此需要 PowerShell 的运行时实现才能正确进行测试。 为此，[PSES 的 xUnit][] 测试引入了 `Microsoft.PowerShell.SDK` 和 `Microsoft.PowerShell.5.ReferenceAssemblies`，以便在测试环境中提供 PowerShell 实现。

与 PSReadLine 一样，PSES 不支持 .NET 4.6 及更低版本，但它会先在运行时[执行检查][]，然后调用任何可能在较低的 .NET Framework 运行时导致故障的 API。

### <a name="psscriptanalyzer"></a>PSScriptAnalyzer

[PSScriptAnalyzer][]（用于 PowerShell 的 Linter）必须面向仅在某些版本的 PowerShell 中引入的语法元素。 由于对这些语法元素的识别是通过实现 [AstVisitor2][] 来完成的，因此无法使用 PowerShellStandard 并为较新的 PowerShell 语法实现 AST 访问者方法。

不过，PSScriptAnalyzer 会[将每种 PowerShell 版本][]作为生成配置目标，并为每种版本生成一个单独的 DLL。 这增加了构建大小和复杂性，但可实现以下几点：

- 特定于版本的 API 目标设定
- 在实现特定于版本的功能时实际上不花费运行时成本
- 一直往回追溯到版本 .NET Framework 4.5.2，都提供对 Windows PowerShell 的全面支持

## <a name="summary"></a>摘要

在本文中，我们列出并讨论了实现使用 PowerShell 的 .NET 项目时可作为目标的 NuGet 包，以及使用某个包而不使用其他包的原因。

如果你跳过了摘要，一些普遍建议是：

- 如果 PowerShell 模块仅需要不同 PowerShell 版本共用的 API，则应该针对 PowerShell Standard 进行编译。
- 需要在内部运行 PowerShell 的 PowerShell 主机和应用程序应面向 PowerShell 6 及更高版本的 PowerShell SDK 或适用于 Windows PowerShell 的相关 Windows PowerShell 引用程序集。
- 需要版本特定的 API 的 PowerShell 模块应面向 PowerShell SDK 或所需 PowerShell 版本的 Windows PowerShell 引用程序集，并将其用作引用程序集（即不发布 PowerShell 依赖项）。

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
[Pester]: https://github.com/Pester/Pester
[PowerShell 编辑器服务]: https://github.com/PowerShell/PowerShellEditorServices/
[PowerShell 扩展]: https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[PowerShell NuGet]: https://www.nuget.org/packages/PowerShell/
[PowerShell Standard 存储库]: https://github.com/PowerShell/PowerShellStandard
[PowerShellStandard.Library]: https://www.nuget.org/packages/PowerShellStandard.Library/
[PSCmdlet]: /dotnet/api/system.management.automation.pscmdlet
[PSES 的 xUnit]: https://github.com/PowerShell/PowerShellEditorServices/blob/8c500ee1752201d3c1cc2e5d90f1a2af3b1eb15d/test/PowerShellEditorServices.Test/PowerShellEditorServices.Test.csproj#L15-L20
[PSHost]: /dotnet/api/system.management.automation.host.pshost
[PrivateAssets 属性]: /dotnet/core/tools/csproj#packagereference
[PSReadLine]: https://github.com/PowerShell/PSReadLine
[PSScriptAnalyzer]: https://github.com/powershell/psscriptanalyzer
[引用程序集]: https://github.com/dotnet/standard/blob/master/docs/history/evolution-of-design-time-assemblies.md#definitions
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[System.Management.Automation]: https://www.nuget.org/packages/System.Management.Automation/
[将每种 PowerShell 版本作为目标]: https://github.com/PowerShell/PSScriptAnalyzer/blob/master/Engine/Engine.csproj
[这篇博客文章]: https://devblogs.microsoft.com/powershell/powershell-standard-library-build-single-module-that-works-across-windows-powershell-and-powershell-core/
[Visual Studio Code]: https://code.visualstudio.com/
[Windows PowerShell SDK]: /powershell/scripting/developer/windows-powershell
