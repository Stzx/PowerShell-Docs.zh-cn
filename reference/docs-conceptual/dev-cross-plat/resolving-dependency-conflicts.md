---
title: 解决 PowerShell 模块程序集依赖项冲突
description: 在采用 C# 编写二进制 PowerShell 模块时，自然会通过其他包或库的依赖项来提供功能。
ms.date: 06/25/2020
ms.custom: rjmholt
ms.openlocfilehash: 536bcfd1ced536faccde0d6c5bc483cdaf31ce68
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87775187"
---
# <a name="resolving-powershell-module-assembly-dependency-conflicts"></a>解决 PowerShell 模块程序集依赖项冲突

在采用 C# 编写二进制 PowerShell 模块时，自然会通过其他包或库的依赖项来提供功能。 需要依赖其他库以重用代码。 PowerShell 始终将程序集加载到相同的上下文中。 如果模块的依赖项与已加载的 DLL 冲突，则会出现问题，并且可能会阻止在同一 PowerShell 会话中使用其他两个不相关的模块。

如果你遇到过这种问题，就一定见过如下错误消息：

![程序集加载冲突错误消息](./media/resolving-dependency-conflicts/moduleconflict.png)

本文介绍 PowerShell 中发生依赖项冲突的一些方式以及缓解依赖项冲突问题的方法。 即使你不是模块创建者，这里也有一些技巧可以帮助应对所使用的模块中发生的依赖项冲突。

## <a name="why-do-dependency-conflicts-occur"></a>为什么会发生依赖项冲突？

在 .NET 中，当将同一程序集的两个版本加载到同一程序集加载上下文中时，将发生依赖项冲突。 这一术语在不同 .NET 平台上的含义略有不同，[稍后](#powershell-and-net)将进行介绍。 此冲突是一个常见的问题，使用版本控制依赖项的任何软件都会出现这种冲突。 由于没有简单的解决方案，并且许多依赖项解决方案框架都尝试以不同的方式解决此问题，因此这种情况通常称为“依赖项地狱”。

一个项目几乎不会有意或直接依赖于同一依赖项的两个版本，这一事实使冲突问题更加复杂。 相反，如果项目具有两个或多个依赖项，则每个依赖项都需要同一依赖项的不同版本。

例如，假设 .NET 应用程序 `DuckBuilder` 引入了两个依赖项来执行其部分功能，如下所示：

![DuckBuilder 的两个依赖项依赖于 Newtonsoft.json 的不同版本](./media/resolving-dependency-conflicts/dep-conflict.jpg)

由于 `Contoso.ZipTools` 和 `Fabrikam.FileHelpers` 都依赖于 `Newtonsoft.Json` 的不同版本，因此可能存在依赖项冲突，具体取决于每个依赖项的加载方式。

### <a name="conflicting-with-powershells-dependencies"></a>与 PowerShell 的依赖项冲突

在 PowerShell 中，由于 PowerShell 模块和 PowerShell 自己的依赖项加载到同一共享上下文中，因此依赖项冲突问题会被放大。 这意味着 PowerShell 引擎和所有已加载的 PowerShell 模块不能有产生冲突的依赖项。 一个典型示例是 `Newtonsoft.Json`：

![相较于 PowerShell，FictionalTools 模块所依赖的 Newtonsoft.json 版本较新](./media/resolving-dependency-conflicts/engine-conflict.jpg)

在此示例中，模块 `FictionalTools` 依赖于 `Newtonsoft.Json` 版本 `12.0.3`，此版本的 `Newtonsoft.Json` 比示例 PowerShell 中随附的 `11.0.2` 更新。

> [!NOTE]
> 这是一个示例，PowerShell 7 当前随附有 `Newtonsoft.Json 12.0.3`。

因为该模块依赖于程序集的较新版本，所以它不会接受 PowerShell 已加载的版本。 但是，由于 PowerShell 已加载了该程序集的一个版本，因此该模块无法使用常规加载机制来加载其自己的版本。

### <a name="conflicting-with-another-modules-dependencies"></a>与另一个模块的依赖项冲突

PowerShell 中的另一种常见情况是，加载依赖于某程序集的一个版本的模块，然后再加载依赖于该程序集的不同版本的另一个模块。

此行为通常如下所示：

![两个 PowerShell 模块需要 Microsoft.Extensions.Logging 依赖项的不同版本](./media/resolving-dependency-conflicts/mod-conflict.jpg)

在此例中，`FictionalTools` 模块需要比 `FilesystemManager` 模块更新的 `Microsoft.Extensions.Logging` 版本。

假设这些模块通过将依赖项程序集与根模块程序集放在同一目录中来加载其依赖项。 这使 .NET 可以按名称隐式加载它们。 如果运行的是 PowerShell 7（在 .NET Core 3.1 之上），则可以加载并运行 `FictionalTools`，然后加载并运行 `FilesystemManager`，而不会出现问题。 但是，在新会话中，如果我们加载并运行 `FilesystemManager`，然后加载 `FictionalTools`，则会从 `FictionalTools` 命令中得到 `FileLoadException`，因为它需要比已加载的 `Microsoft.Extensions.Logging` 版本更新的版本。
`FictionalTools` 无法加载所需的版本，因为已加载了同名的程序集。

## <a name="powershell-and-net"></a>PowerShell 和 .NET

PowerShell 在 .NET 平台上运行。 NET 最终负责解析和加载程序集依赖项，因此我们必须在此处了解 .NET 的操作方式，以了解依赖项冲突。

我们还必须正视这样一个事实：不同版本的 PowerShell 在不同的 .NET 实现上运行。 通常，PowerShell 5.1 和更低版本在 .NET Framework 上运行，而 PowerShell 6 和更高版本则在 .NET Core 上运行。 .NET 的这两种实现以不同的方式加载和处理程序集。
这意味着依赖项冲突的解决方式可能会因基础 .NET 平台而异。

### <a name="assembly-load-contexts"></a>程序集加载上下文

在 .NET 中，程序集加载上下文 (ALC) 是指将程序集加载到其中的运行时命名空间。 程序集的名称必须是唯一的。 此概念允许在每个 ALC 中按名称唯一地解析程序集。

### <a name="assembly-reference-loading-in-net"></a>.NET 中的程序集引用加载

程序集加载的语义取决于 .NET 实现（.NET Core 与 .NET Framework）以及用于加载特定程序集的 .NET API。 此处不进行详细介绍，[延伸阅读](#further-reading)部分中的链接非常详细地介绍了每个 .NET 实现中 .NET 程序集加载的工作方式。

在本文中，我们将介绍以下机制：

- 隐式程序集加载（有效地 `Assembly.Load(AssemblyName)`），如果 .NET 隐式尝试从 .NET 代码中的静态程序集引用按名称加载程序集的话。
- `Assembly.LoadFrom()`，它是一个面向插件的加载 API，可添加处理程序来解析加载的 DLL 的依赖项。 此方法可能不会按所需方式解析依赖项。
- `Assembly.LoadFile()`，它是一个基本的加载 API，旨在仅加载请求的程序集，不处理任何依赖项。

### <a name="differences-in-net-framework-vs-net-core"></a>.NET Framework 与 .NET Core 之间的差异

这些 API 在 .NET Core 和 .NET Framework 之间的工作方式已发生了细微的变化，因此有必要通读随附的[链接](#further-reading)内容。 重要的是，.NET Framework 和 .NET Core 之间的程序集加载上下文和其他程序集解析机制已更改。

具体而言，.NET Framework 具有以下功能：

- 全局程序集缓存，适用于计算机范围内的程序集解析
- 应用程序域，其工作方式类似于用于程序集隔离的进程内沙盒，但也提供了一个要与之争用的序列化层
- 受限的程序集加载上下文模型（[此处](/dotnet/framework/deployment/best-practices-for-assembly-loading)进行了详细说明），具有一组固定的程序集加载上下文，每个上下文都有其各自的行为：
  - 默认加载上下文，默认情况下在其中加载程序集
  - 加载位置上下文，用于在运行时手动加载程序集
  - 仅反射上下文，用于安全地加载程序集，以在不运行它们的情况下读取其元数据
  - 特殊的 void，用于存储通过 `Assembly.LoadFile(string path)` 和 `Assembly.Load(byte[] asmBytes)` 加载的程序集

.NET Core（和 .NET 5+）已将此复杂内容替换为更简单的模型：

- 无全局程序集缓存。 应用程序会引入其所有依赖项。 这将删除应用程序中依赖项解析的外部因素，使依赖项解析更具可重现性。
  对于模块，插件主机 PowerShell 使这种情况略微复杂一些。 它在 `$PSHOME` 中的依赖项与所有模块共享。
- 只有一个应用程序域，且无法创建新的应用程序域。 .NET Core 中保留的应用程序域概念纯粹是指 .NET 进程的全局状态。
- 新的可扩展程序集加载上下文模型。 可以通过将程序集解析放入新的 ALC 中来设置其命名空间。 .NET Core 进程从一个默认的 ALC 开始，所有程序集均加载到其中。 （那些通过 `Assembly.LoadFile(string)` 和 `Assembly.Load(byte[])` 加载的程序集除外）但是，该进程可以创建和定义自己的 ALC 及其自己的加载逻辑。 加载程序集时，加载到其中的第一个 ALC 负责解析其依赖项。 这样就有机会实现功能强大的 .NET 插件加载机制。

在这两种实现中，程序集都是延迟加载的。 这意味着它们是在首次运行需要其类型的方法时加载的。

例如，下面是同一代码的两个版本，它们在不同的时间加载依赖项。

第一个始终在调用 `Program.GetRange()` 时加载其依赖项，因为方法中在词法上存在依赖项引用：

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

第二个仅在 `limit` 参数大于或等于 20 时才加载其依赖项，这是因为需要通过某方法进行内部间接寻址：

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

这是一种很好的做法，因为它可以最大程度地减少内存和文件系统 I/O，并更有效地使用资源。 不幸的是，这样做存在一个副作用，即在到达尝试加载程序集的代码路径之前，我们无法知道程序集无法加载。

它还可以针对程序集加载冲突创建计时条件。 如果同一程序的两个部分尝试加载同一程序集的不同版本，则加载的版本取决于首先运行的代码路径。

对于 PowerShell，这意味着以下因素可能会影响程序集加载冲突：

- 首先加载哪个模块？
- 使用依赖项库的代码路径是否运行？
- PowerShell 是在启动时加载冲突的依赖项，还是仅在某些代码路径下加载？

## <a name="quick-fixes-and-their-limitations"></a>快速解决方案及其限制

在某些情况下，可以对模块进行少量调整，通过最少的工作量来解决问题。 但这些解决方案往往有一些注意事项。 虽然它们可能适用于你的模块，但并非适用于所有模块。

### <a name="change-your-dependency-version"></a>更改依赖项版本

避免依赖项冲突的最简单方法是就依赖项达成一致。 在以下情况下可实现这一操作：

- 冲突与模块的直接依赖项有关，并且你可以控制版本。
- 冲突与间接依赖项有关，但你可以将直接依赖项配置为使用可操作的间接依赖项版本。
- 你知道存在冲突的版本，可以依赖于它，并且不进行更改。

`Newtonsoft.Json` 包是最后一种情况的一个很好的示例。 这是 PowerShell 6 及更高版本的依赖项，不在 Windows PowerShell 中使用。 这意味着，解决版本控制冲突的一种简单方法是，将希望作为目标的 PowerShell 版本中最低版本的 `Newtonsoft.Json` 作为目标。

例如，PowerShell 6.2.6 和 PowerShell 7.0.2 当前都使用 `Newtonsoft.Json` 版本 12.0.3。 因此，若要创建面向 Windows PowerShell、PowerShell 6 和 PowerShell 7 的模块，需要将 `Newtonsoft.Json 12.0.3` 作为依赖项并将其添加到构建的模块中。 在 PowerShell 6 或 7 中加载该模块后，PowerShell 自己的 `Newtonsoft.Json` 程序集已加载。 此外，它至少是模块所需的版本，因此解析成功。 在 Windows PowerShell 中，PowerShell 中尚不存在该程序集。 因此，它改为从模块文件夹中加载。

通常，如果以具体的 PowerShell 包（例如 `Microsoft.PowerShell.Sdk` 或 `System.Management.Automation`）作为目标，NuGet 应能够解析所需的正确依赖项版本。 由于必须在以多个框架还是以 `PowerShellStandard.Library` 作为目标之间进行选择，因此同时以 Windows PowerShell 和 PowerShell 6+ 作为目标会变得更加困难。

固定为某个通用依赖项版本不起作用的情况包括：

- 冲突与间接依赖项有关，并且所有依赖项都不能配置为使用通用版本。
- 其他依赖项版本可能会经常更改，因此使用通用版本只是短期解决方案。

### <a name="add-an-assemblyresolve-event-handler-to-create-a-dynamic-binding-redirect"></a>添加 AssemblyResolve 事件处理程序以创建动态绑定重定向

有时无法更改自己的依赖项版本，或者这样做非常困难。 另一种选项是通过注册 `AssemblyResolve` 事件的事件处理程序来设置动态绑定重定向。

与静态绑定重定向一样，关键是要强制某依赖项的所有使用者使用相同的实际程序集。 截获加载依赖项的调用，并始终将其重定向到所需的版本。

如下所示：

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

在技术上，可以在 PowerShell 中注册脚本块来处理 `AssemblyResolve` 事件，但是：

- 在任何线程上都可能触发 `AssemblyResolve` 事件，而 PowerShell 无法对此进行处理。
- 即使在正确的线程上处理事件，PowerShell 的范围概念也意味着必须谨慎编写事件处理程序脚本块，以避免依赖于其外部定义的变量。

在某些情况下，无法重定向到通用版本：

- 当依赖项在版本之间进行了中断性变更，或依赖项代码依赖于某个功能否则在重定向到的版本中不可用时。
- 依赖项冲突之前未加载模块时。 如果在加载依赖项后注册 `AssemblyResolve` 事件处理程序，则永远不会触发该处理程序。 如果尝试防止依赖项与另一个模块冲突，则这可能是一个问题，因为可能会先加载另一个模块。

### <a name="use-the-dependency-out-of-process"></a>使用进程外的依赖项

此解决方案更适用于模块用户，而不是模块创建者。 当遇到由于现有依赖项冲突而无法工作的模块时，可使用此解决方案。

由于将同一程序集的两个版本加载到同一 .NET 进程中，因此发生依赖项冲突。 一个简单的解决方案是将它们加载到不同的进程中，前提是你仍然可以同时使用这两者的功能。

在 PowerShell 中，有几种方法可以实现此目的：

- 调用 PowerShell 作为子进程

  在当前进程之外运行 PowerShell 命令的一种简单方法是，直接通过命令调用启动新的 PowerShell 进程：

  ```powershell
  pwsh -c 'Invoke-ConflictingCommand'
  ```

  此处的主要限制在于，与其他选项相比，重构结果可能会更棘手或更容易出错。

- PowerShell 作业系统

  通过将命令发送到新的 PowerShell 进程并返回结果，PowerShell 作业系统也可以在进程之外运行命令：

  ```powershell
  $result = Start-Job { Invoke-ConflictingCommand } | Receive-Job -Wait
  ```

  在这种情况下，只需要确保正确传递所有变量和状态即可。

  即使运行少量命令，作业系统也可能会有点繁琐。

- PowerShell 远程处理

  如果 PowerShell 远程处理可用，则这可能是在进程之外运行命令的有用方法。 通过远程处理，可以在新进程中创建新的 PSSession，通过 PowerShell 远程处理调用其命令，然后将结果与包含冲突依赖项的其他模块一起在本地使用。

  示例可能如下所示：

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

- 对 Windows PowerShell 的隐式远程处理

  PowerShell 7 中的另一个选项是在 `Import-Module` 上使用 `-UseWindowsPowerShell` 标志。 这将通过本地远程处理会话将模块导入 Windows PowerShell：

  ```powershell
  Import-Module -Name ConflictingModule -UseWindowsPowerShell
  ```

  请注意，模块可能无法与 Windows PowerShell 一起使用，或与 Windows PowerShell 的工作方式不同。

#### <a name="when-out-of-process-invocation-should-not-be-used"></a>不应使用进程外调用的情况

作为模块创建者，进程外命令调用很难嵌入到模块中，并可能出现导致问题的极端情况。 具体而言，在模块需要在其中工作的所有环境中，远程处理和作业可能并非都可用。 但是，将实现移出进程并允许 PowerShell 模块成为更精简的客户端，此一般原则可能仍然适用。

在某些情况下，模块用户无法进行进程外调用：

- 当 PowerShell 远程处理因缺少使用权限或未启用而无法使用时。
- 当需要将来自输出的特定 .NET 类型作为方法或其他命令的输入时。
  在 PowerShell 远程处理上运行的命令将发出反序列化对象，而不是强类型 .NET 对象。 这意味着方法调用和强类型 API 不能与通过远程处理导入的命令的输出一起使用。

## <a name="more-robust-solutions"></a>更可靠的解决方案

上述解决方案均有不起作用的情况和模块。 但它们有一个共同的优点，那就是正确实现相对简单。 以下解决方案更可靠，但需要付出更多的努力才能正确实现，并且如果不谨慎编写，可能会引入一些细微的 bug。

### <a name="loading-through-net-core-assembly-load-contexts"></a>通过 .NET Core 程序集加载上下文进行加载

.NET Core 1.0 中引入了[程序集加载上下文](/dotnet/api/system.runtime.loader.assemblyloadcontext) (ALC) 作为可实现的 API，专门用于解决将同一程序集的多个版本加载到同一运行时的需求。

在 .NET Core 和 .NET 5 中，它们为加载程序集版本冲突问题提供了最可靠的解决方案。 但是，自定义 ALC 在 .NET Framework 中不可用。 这意味着此解决方案仅适用于 PowerShell 6 及更高版本。

当前，在 PowerShell 中使用 ALC 进行依赖项隔离的最佳示例是 PowerShell 编辑器服务，这是适用于 Visual Studio Code 的 PowerShell 扩展的语言服务器。 [ALC](https://github.com/PowerShell/PowerShellEditorServices/blob/master/src/PowerShellEditorServices.Hosting/Internal/PsesLoadContext.cs) 用于防止 PowerShell 编辑器服务自已的依赖项与 PowerShell 模块中的依赖项冲突。

从概念上讲，使用 ALC 实现模块依赖项隔离很困难，但我们将通过一个最简单的示例来完成。 假设我们有一个仅适用于 PowerShell 7 的简单模块。
源代码组织如下：

```
+ AlcModule.psd1
+ src/
    + TestAlcModuleCommand.cs
    + AlcModule.csproj
```

cmdlet 实现如下所示：

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

高度简化的清单如下所示：

```powershell
@{
    Author = 'Me'
    ModuleVersion = '0.0.1'
    RootModule = 'AlcModule.dll'
    CmdletsToExport = @('Test-AlcModule')
    PowerShellVersion = '7.0'
}
```

`csproj` 如下所示：

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

生成此模块时，生成的输出的布局如下：

```
AlcModule/
  + AlcModule.psd1
  + AlcModule.dll
  + Shared.Dependency.dll
```

在此示例中，我们的问题在于 `Shared.Dependency.dll` 程序集，这是我们假设的冲突依赖项。 我们需要将此依赖项放在 ALC 后面，以便我们可以使用特定于模块的版本。

我们需要重新设计模块，以便：

- 模块依赖项仅加载到自定义 ALC 中，而不加载到 PowerShell 的 ALC 中，因此不会发生冲突。 此外，随着我们向项目中添加的依赖项增多，我们不想要不断添加更多代码来保持加载正常运行。 相反，我们想要可重用的通用依赖项解析逻辑。
- 在 PowerShell 中加载模块仍可正常运行。 PowerShell 模块系统所需的 cmdlet 和其他类型是在 PowerShell 自己的 ALC 中定义的。

若要协调这两个要求，必须将模块分成两个程序集：

- 一个 cmdlet 程序集 `AlcModule.Cmdlets.dll`，其中包含 PowerShell 的模块系统正确加载模块所需的所有类型的定义。 即 `Cmdlet` 基类和实现 `IModuleAssemblyInitializer` 的类的任何实现，用于设置 `AssemblyLoadContext.Default.Resolving` 的事件处理程序，以通过自定义 ALC 正确加载 `AlcModule.Engine.dll`。 由于 PowerShell 7 故意隐藏了在其他 ALC 中加载的程序集中定义的类型，因此任何要公开给 PowerShell 的类型也必须在此处进行定义。 最后，需要在此程序集中定义自定义 ALC。 除此之外，此程序集中包含的代码应尽可能少。
- 一个引擎程序集 `AlcModule.Engine.dll`，用于处理模块的实际实现。
  来自此程序集的类型可在 PowerShell ALC 中获取，但最初将通过自定义 ALC 进行加载。 它的依赖项仅加载到自定义 ALC 中。 实际上，这成为了两个 ALC 之间的桥梁。

利用这种桥梁概念，新程序集情况如下所示：

![表示 AlcModule.Engine.dll 桥接两个 ALC 的图](./media/resolving-dependency-conflicts/alc-diagram.jpg)

若要确保默认 ALC 的依赖项探测逻辑不会解析要加载到自定义 ALC 中的依赖项，我们需要在不同的目录中分隔此模块的这两个部分。 新模块布局的结构如下：

```
AlcModule/
  AlcModule.Cmdlets.dll
  AlcModule.psd1
  Dependencies/
  | + AlcModule.Engine.dll
  | + Shared.Dependency.dll
```

为了查看实现的更改方式，我们将从 `AlcModule.Engine.dll` 的实现开始：

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

这是用于依赖项 `Shared.Dependency.dll` 的简单容器，但应将其视为针对其他程序集中的 cmdlet 为 PowerShell 封装的功能的 .NET API。

`AlcModule.Cmdlets.dll` 中的 cmdlet 如下所示：

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

此时，如果我们要加载 AlcModule 并运行 `Test-AlcModule`，则当默认 ALC 尝试加载 `Alc.Engine.dll` 以运行 `EndProcessing()` 时，我们将收到 `FileNotFoundException`。 这样很好，因为这意味着默认 ALC 找不到我们要隐藏的依赖项。

现在，我们需要向 `AlcModule.Cmdlets.dll` 添加代码，以告知它如何解析 `AlcModule.Engine.dll`。 首先，我们必须定义自定义 ALC，它将解析模块的 `Dependencies` 目录中的程序集：

```csharp
namespace AlcModule.Cmdlets
{
    internal class AlcModuleAssemblyLoadContext : AssemblyLoadContext
    {
        private readonly string _dependencyDirPath;

        public AlcModuleAssemblyLoadContext(string dependencyDirPath)
        {
            _depdendencyDirPath = dependencyDirPath;
        }

        protected override Assembly Load(AssemblyName assemblyName)
        {
            // We do the simple logic here of
            // looking for an assembly of the given name
            // in the configured dependency directory
            string assemblyPath = Path.Combine(
                s_dependencyDirPath,
                $"{assemblyName.Name}.dll");

            // The ALC must use inherited methods to load assemblies
            // Assembly.Load*() won't work here
            return LoadFromAssemblyPath(assemblyPath);
        }
    }
}
```

然后，我们需要将自定义 ALC 挂接到默认 ALC 的 `Resolving` 事件，该事件是应用程序域上 `AssemblyResolve` 事件的 ALC 版本。 调用 `EndProcessing()` 时，将触发此事件以查找 `AlcModule.Engine.dll`。

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

通过新实现，查看在加载模块并运行 `Test-AlcModule` 时发生的调用序列：

![使用自定义 ALC 加载依赖项的调用序列图](./media/resolving-dependency-conflicts/alc-sequence.png)

兴趣点包括：

- 模块加载并设置 `Resolving` 事件时，将首先运行 `IModuleAssemblyInitializer`。
- 在运行 `Test-AlcModule` 并调用其 `EndProcessing()` 方法之前，不会加载依赖项。
- 调用 `EndProcessing()` 时，默认 ALC 无法找到 `AlcModule.Engine.dll` 并触发 `Resolving` 事件。
- 事件处理程序会将自定义 ALC 挂接到默认 ALC 并仅加载 `AlcModule.Engine.dll`。
- 在 `AlcModule.Engine.dll` 内调用 `AlcEngine.Use()` 时，自定义 ALC 将再次启动以解析 `Shared.Dependency.dll`。 具体而言，它始终加载 `Shared.Dependency.dll`，因为它永远不会与默认 ALC 中的任何内容冲突，而只会在 `Dependencies` 目录中进行查找。

汇编实现，新源代码布局如下所示：

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

AlcModule.Cmdlets.csproj 如下所示：

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

AlcModule.Engine.csproj 如下所示：

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

因此，生成模块时，我们的策略是：

- 生成 `AlcModule.Engine`
- 生成 `AlcModule.Cmdlets`
- 将 `AlcModule.Engine` 中的所有内容复制到 `Dependencies` 目录，并记住所复制的内容
- 将 `AlcModule.Cmdlets` 中所有不在 `AlcModule.Engine` 中的内容复制到基础模块目录中

由于此处的模块布局对于依赖项分隔至关重要，因此可从源根目录使用以下生成脚本：

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

最后，我们提供了一种通用方法来使用程序集加载上下文隔离模块的依赖项，随着时间的推移、依赖项不断增加，该方法仍然可靠。

有关更详细的示例，请转到此 [GitHub 存储库](https://github.com/rjmholt/ModuleDependencyIsolationExample)。 此示例演示如何迁移模块以使用 ALC，同时使该模块在 .NET Framework 中正常运行。 它还演示了如何使用 .NET Standard 和 PowerShell Standard 来简化核心实现。

### <a name="assembly-resolve-handler-for-side-by-side-loading-with-assemblyloadfile"></a>用于通过 `Assembly.LoadFile()` 并行加载的程序集解析处理程序

另一种实现并行程序集加载的方法是将 `AssemblyResolve` 事件挂接到 `Assembly.LoadFile()`，这种方法可能更加简单。 使用 `Assembly.LoadFile()` 的优势在于，它是最简单的实现解决方案，并同时适用于 .NET Core 和 .NET Framework。

为了说明这一点，我们来看一个简单的实现示例，该示例结合了动态绑定重定向示例和上面的程序集加载上下文示例的理念。

我们将此模块称为 LoadFileModule，它有一个简单的命令 `Test-LoadFile [-Path] <path>`。 此模块采用 `CsvHelper` 程序集（版本 15.0.5）的依赖项。

与 ALC 模块一样，必须首先将模块拆分为两个部分。

第一个部分执行实际的实现 `LoadFileModule.Engine`：

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

第二个部分是 PowerShell 直接加载的 `LoadFileModule.Cmdlets`。 使用与 ALC 模块类似的策略，将依赖项隔离在不同的目录中。 但这次，使用 resolve 事件而不只是 `LoadFileModule.Engine.dll` 来加载所有程序集。

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

最后，此模块的布局也类似于 ALC 模块：

```
LoadFileModule/
  + LoadFileModule.Cmdlets.dll
  + LoadFileModule.psd1
  + Dependencies/
  |  + LoadFileModule.Engine.dll
  |  + CsvHelper.dll
```

借助此结构，LoadFileModule 现在支持与使用 CsvHelper 的依赖项的其他模块一起加载 。

因为处理程序适用于整个应用程序域中的所有 `AssemblyResolve` 事件，所以我们需要在此处进行一些具体的设计选择：

- 为缩减事件可能会干扰其他加载的时段，我们仅在加载 `LoadFileModule.Engine.dll` 后才开始处理常规依赖项加载。
- 将 `LoadFileModule.Engine.dll` 推送到 Dependencies 目录中，以便通过 `LoadFile()` 调用而不是 PowerShell 进行加载。 这意味着，即使在 PowerShell 中加载了另一个 `CsvHelper.dll`（例如），它自己的依赖项加载也始终会引发 `AssemblyResolve` 事件。
  这使我们有机会找到正确的依赖项。
- 由于必须只解析模块的特定依赖项，因此我们不得不在处理程序中编码依赖项名称和版本的字典。 在特定情况下，可以使用 `ResolveEventArgs.RequestingAssembly` 属性来确定模块是否正在请求 `CsvHelper`。 但这并不适用于依赖项的依赖项；例如，如果 `CsvHelper` 本身引发了 `AssemblyResolve` 事件。 若要实现此目的，还有其他更困难的方法，例如，将请求的程序集与 `Dependencies` 目录中的程序集的元数据进行比较。 但在此示例中，我们更明确地进行了此检查，以突出问题并简化示例。

这是 `LoadFile()` 策略与 ALC 策略之间的主要区别：`AssemblyResolve` 事件必须为应用程序域中的所有加载提供服务，这使得依赖项解析更难与其他模块混杂在一起。 但是，由于 .NET Framework 中缺少 ALC，因此可以理解为何存在此选项。

### <a name="custom-application-domains"></a>自定义应用程序域

程序集隔离的最后也是最极端的选项是使用自定义应用程序域。
应用程序域（采用复数形式）仅适用于 .NET Framework。 它们用于在 .NET 应用程序的各个部分之间提供进程内隔离。 一种用途是在同一进程中将程序集加载彼此隔离。

但是，应用程序域是序列化边界。 一个应用程序域中的对象不能供其他应用程序域中的对象直接引用和使用。 通过实现 `MarshalByRefObject` 可解决此问题。 但如果不控制类型（常见于依赖项），就不可能在此处强制实现。 唯一的解决方案是进行大型体系结构更改。 序列化边界也会对性能产生严重影响。

由于应用程序域具有这一严重限制，实现起来很复杂，并且仅适用于 .NET Framework，因此本文将不提供其使用方式的示例。 虽然值得一提的是，它们是一种可能的解决方案，但不建议使用。

如果有兴趣尝试使用自定义应用程序域，以下链接可能会有所帮助：

- [有关应用程序域的概念性文档](/dotnet/framework/app-domains/application-domains)
- [使用应用程序域的示例](/dotnet/framework/app-domains/use)

## <a name="solutions-for-dependency-conflicts-that-dont-work-for-powershell"></a>不适用于 PowerShell 的依赖项冲突解决方案

最后，我们将介绍在研究 .NET 中的 .NET 依赖项冲突时提出的一些看好的可能解决方案，但通常不适用于 PowerShell。

这些解决方案有共同的主题，即针对在其中控制应用程序的环境（可能整个计算机），更改部署配置。 这些解决方案面向的是 Web 服务器和部署到服务器环境的其他应用程序之类的场景，其中环境旨在托管应用程序，并可由进行部署的用户自由配置。 它们往往也面向 .NET Framework，这意味着它们不适用于 PowerShell 6 或更高版本。

如果你知道模块仅在完全受你控制的 Windows PowerShell 5.1 环境中使用，则可以选择其中一些内容。 但是，模块通常不应像这样修改全局计算机状态。 这种操作可能会中断配置，导致 `powershell.exe`、其他模块或其他从属应用程序出现问题，从而导致模块意外失败。

### <a name="static-binding-redirect-with-appconfig-to-force-using-the-same-dependency-version"></a>使用 app.config 进行静态绑定重定向以强制使用相同的依赖项版本

.NET Framework 应用程序可以利用 `app.config` 文件以声明方式配置应用程序的某些行为。 可以编写一个 `app.config` 条目来配置程序集绑定，以将程序集加载重定向到特定版本。

对于 PowerShell，此操作存在以下两个问题：

- .NET Core 不支持 `app.config`，所以此解决方案仅适用于 `powershell.exe`。
- `powershell.exe` 是位于 `System32` 目录中的共享应用程序。 在许多系统上，模块可能无法修改其内容。 即使可以，修改 `app.config` 也可能会中断现有配置或影响加载其他模块。

### <a name="setting-codebase-with-appconfig"></a>通过 app.config 设置 `codebase`

出于相同的原因，尝试在 `app.config` 中配置 `codebase` 设置在 PowerShell 模块中不起作用。

### <a name="installing-dependencies-to-the-global-assembly-cache-gac"></a>在全局程序集缓存 (GAC) 中安装依赖项

若要解决 .NET Framework 中依赖项版本冲突，另一种方法是将依赖项安装到 GAC 中，以便可以从 GAC 并行加载不同的版本。

同样，对于 PowerShell 模块，这里的主要问题是：

- GAC 仅适用于 .NET Framework，因此对 PowerShell 6 及更高版本没有帮助。
- 将程序集安装到 GAC 中是对全局计算机状态的修改，并可能在其他应用程序或其他模块中产生副作用。 即使模块具有所需的访问权限，也可能难以正确操作。 错误的操作可能会在其他 .NET 应用程序中引起计算机范围的严重问题。

## <a name="further-reading"></a>其他阅读材料

有关 .NET 程序集版本依赖项冲突，还有很多内容可供阅读。 从以下内容开始阅读就很不错：

- [.NET：.NET 中的程序集](/dotnet/standard/assembly/)
- [.NET Core：托管程序集加载算法](/dotnet/core/dependency-loading/loading-managed)
- [.NET Core：了解 System.Runtime.Loader.AssemblyLoadContext](/dotnet/core/dependency-loading/understanding-assemblyloadcontext)
- [.NET Core：有关程序集并行加载解决方案的讨论](https://github.com/dotnet/runtime/issues/13471)
- [.NET Framework：重定向程序集版本](/dotnet/framework/configure-apps/redirect-assembly-versions)
- [.NET Framework：适用于程序集加载的最佳做法](/dotnet/framework/deployment/best-practices-for-assembly-loading)
- [.NET Framework：运行时如何定位程序集](/dotnet/framework/deployment/how-the-runtime-locates-assemblies)
- [.NET Framework：解析程序集加载](/dotnet/standard/assembly/resolve-loads)
- [StackOverflow：程序集绑定重定向的方法和原因](https://stackoverflow.com/questions/43365736/assembly-binding-redirect-how-and-why)
- [PowerShell：有关实现 AssemblyLoadContexts 的讨论](https://github.com/PowerShell/PowerShell/issues/11571)
- [PowerShell：`Assembly.LoadFile()` 不会加载到默认 AssemblyLoadContext 中](https://github.com/PowerShell/PowerShell/issues/12052)
- [Rick Strahl：何时加载 .NET 程序集依赖项？](https://weblog.west-wind.com/posts/2012/Nov/03/Back-to-Basics-When-does-a-NET-Assembly-Dependency-get-loaded)
- [Jon Skeet：.NET 中的版本控制摘要](https://codeblog.jonskeet.uk/2019/06/30/versioning-limitations-in-net/)
- [Nate McMaster：深入了解 .NET Core 基元](https://natemcmaster.com/blog/2017/12/21/netcore-primitives/)
