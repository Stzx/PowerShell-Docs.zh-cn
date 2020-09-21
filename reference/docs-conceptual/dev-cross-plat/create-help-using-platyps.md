---
title: 使用 PlatyPS 创建基于 XML 的帮助文件
description: 使用 PlatyPS 创建基于 XML 的帮助文件是一种快速高效的方法。
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972568"
---
# <a name="create-xml-based-help-using-platyps"></a>使用 PlatyPS 创建基于 XML 的帮助文件

创建 PowerShell 模块时，始终建议包含有关所创建的 cmdlet 的详细帮助。 如果 cmdlet 是用已编译代码实现的，就必须使用基于 XML 的帮助。 这种 XML 格式称为 Microsoft 协助标记语言 (MAML)。

旧版 PowerShell SDK 文档涵盖了为打包到模块中的 PowerShell cmdlet 创建帮助文件的详细信息。 但是，PowerShell 不会为创建基于 XML 的帮助文件提供任何工具。 SDK 文档介绍了 MAML 帮助的结构，但你需要手动创建复杂且深度嵌套的 MAML 内容。

[PlatyPS][] 模块可对此提供帮助。

## <a name="what-is-platyps"></a>什么是 PlatyPS？

PlatyPS 是一种[开放源代码][platyps-repo]工具，最初属于黑客马拉松项目，目的是以更轻松的方式创建和维护 MAML。 PlatyPS 记录了参数集的语法以及模块中每个 cmdlet 的各个参数。 PlatyPS 可创建包含语法信息的结构化 [Markdown][] 文件。 它无法创建说明或提供示例。

PlatyPS 会创建占位符，以供填写说明和示例。 添加所需的信息后，PlatyPS 会将 Markdown 文件编译为 MAML 文件。 PowerShell 的帮助系统还允许提供纯文本概念性帮助文件（关于主题）。 PlatyPS 有一个 cmdlet，用于为新的“关于”文件创建结构化 Markdown 模板，但是这些 `about_*.help.txt` 文件必须手动进行维护。

可以在模块中包含 MAML 和文本帮助文件。 还可以使用 PlatyPS 将帮助文件编译成可托管的 CAB 包，以提供可更新帮助。

## <a name="get-started-using-platyps"></a>开始使用 PlatyPS

首先，必须从 PowerShell 库安装 PlatyPS。

```powershell
Install-Module platyps -Force
Import-Module platyps
```

以下流程图概述了创建或更新 PowerShell 引用内容的过程。

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="使用 PlatyPS 创建基于 XML 的帮助文件的工作流":::

##  <a name="create-markdown-content-for-a-powershell-module"></a>为 PowerShell 模块创建 Markdown 内容

1. 将新模块导入会话。 对需要记录的每个模块重复此步骤。

   运行以下命令以导入模块：

   ```powershell
   Import-Module <your module name>
   ```

1. 使用 PlatyPS 为模块页面和模块内的所有关联 cmdlet 生成 Markdown 文件。 对需要记录的每个模块重复此步骤。

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   如果输出文件夹不存在，请使用 `New-MarkdownHelp` 创建一个。 在本示例中，`New-MarkdownHelp` 为模块中的每个 cmdlet 创建 Markdown 文件。 同时还在名为 `<ModuleName>.md` 的文件中创建模块页面。 此模块页面包含模块中包含的 cmdlet 的列表以及摘要说明的占位符。 模块页面中的元数据来自模块清单，PlatyPS 使用该数据创建 HelpInfo XML 文件（如[下面部分](#creating-an-updateable-help-package)所述）。

   `New-MarkdownAboutHelp` 创建名为 `about_topic_name.md` 的新的“关于”文件。

   有关详细信息，请参阅 [New-MarkdownHelp][] 和 [New-MarkdownAboutHelp][]。

### <a name="update-existing-markdown-content-when-the-module-changes"></a>模块更改时会更新现有 Markdown 内容

PlatyPS 还可以更新模块的现有 Markdown 文件。 使用此步骤更新包含新 cmdlet、新参数或已更改参数的现有模块。

1. 将新模块导入会话。 对需要记录的每个模块重复此步骤。

   运行以下命令以导入模块：

   ```powershell
   Import-Module <your module name>
   ```

1. 使用 PlatyPS 为模块登陆页面和模块内的所有关联 cmdlet 更新 Markdown 文件。 对需要记录的每个模块重复此步骤。

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   `Update-MarkdownHelpModule` 更新指定文件夹中的 cmdlet 和模块 Markdown 文件。
   它不会更新 `about_*.md` 文件。 模块文件 (`ModuleName.md`) 接收已添加到 cmdlet 文件中的所有新摘要文本。 cmdlet 文件更新包括以下更改：

   - 新参数集
   - 新参数
   - 更新后的参数元数据
   - 更新后的输入和输出类型信息

   有关详细信息，请参阅 [Update-MarkdownHelpModule][]。

## <a name="edit-the-new-or-updated-markdown-files"></a>编辑新的或更新后的 Markdown 文件

PlatyPS 记录了参数集和各个参数的语法。 它无法创建说明或提供示例。 大括号中包含需要内容的特定区域。 例如：`{{ Fill in the Description }}`

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="显示 VS Code 中占位符的 Markdown 模板":::

需要添加摘要、cmdlet 的说明、每个参数的说明以及至少一个示例。

有关编写 PowerShell 内容的详细信息，请参阅以下文章：

- [PowerShell 风格指南](/powershell/scripting/community/contributing/powershell-style-guide)
- [编辑参考文章](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> PlatyPS 具有用于 cmdlet 引用的特定架构。 该架构仅允许文档特定部分中的某些 Markdown 块。 如果将内容置于错误位置，PlatyPS 构建步骤便会失败。 有关详细信息，请参阅 PlatyPS 存储库中的[架构][]文档。 有关格式标准的 cmdlet 引用的完整示例，请参阅 [Get-Item][]。

在为每个 cmdlet 提供所需内容之后，需要确保更新模块登陆页面。 验证模块在 `<module-name>.md` 文件的 YAML 元数据中是否具有正确的 `Module Guid` 和 `Download Help Link` 值。 添加任何缺失的元数据。

此外，你可能会注意到某些 cmdlet 可能缺少摘要（简短说明）。 以下命令使用摘要说明文本更新模块登陆页面。 打开模块登陆页面，验证说明。

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

现在，你已输入所有内容，可以创建 `Get-Help` 在 PowerShell 控制台中显示的 MAML 帮助文件。

## <a name="create-the-external-help-files"></a>创建外部帮助文件

此步骤会创建 `Get-Help` 在 PowerShell 控制台中显示的 MAML 帮助文件。

若要生成 MAML 文件，请运行以下命令：

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

`New-ExternalHelp` 将所有 cmdlet Markdown 文件转换为一个（或多个）MAML 文件。 “关于”文件会转换为具有以下名称格式的纯文本文件：`about_topic_name.help.txt`。
Markdown 内容必须符合 PlatyPS 架构的要求。 当内容不遵循架构时，`New-ExternalHelp` 将退出并出现错误。 必须编辑文件才能解决架构冲突。

> [!CAUTION]
> PlatyPS 不擅长将 `about_*.md` 文件转换为纯文本。 必须使用非常简单的 Markdown 才能获得可接受的结果。 建议以纯文本 `about_topic_name.help.txt` 格式维护文件，而不是允许 PlatyPS 对其进行转换。

完成此步骤后，目标输出文件夹中将出现 `*-help.xml` 和 `about_*.help.txt` 文件。

有关详细信息，请参阅 [New-ExternalHelp][]

### <a name="test-the-compiled-help-files"></a>测试编译的帮助文件

可以使用 [Get-HelpPreview][] cmdlet 验证内容：

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

该 cmdlet 读取编译的 MAML 文件，并以相同格式输出要从 `Get-Help` 接收的内容。 这使你可以检查结果，以验证 Markdown 文件是否正确编译以及是否生成所需的结果。 如果发现错误，请重新编辑 Markdown 文件并重新编译 MAML。

现在可以发布帮助文件了。

## <a name="publishing-your-help"></a>发布帮助文件

现在，你已将 Markdown 文件编译为 PowerShell 帮助文件，可以向用户提供这些文件。 在 PowerShell 控制台中有两个选项可提供帮助。

- 将帮助文件打包到模块
- 创建用户使用 `Update-Help` cmdlet 安装的可更新帮助包

### <a name="packaging-help-with-the-module"></a>将帮助文件与模块一起打包

帮助文件可与模块一起打包。 有关文件夹结构的详细信息，请参阅[编写针对模块的帮助][]。 应在模块清单的 FileList 键的值中包含“帮助”文件列表。

### <a name="creating-an-updateable-help-package"></a>创建可更新帮助包

用于创建可更新帮助文件的步骤大致包括：

1. 查找用于托管帮助文件的 Internet 站点
1. 将 HelpInfoURI 键添加到模块清单
1. 创建 HelpInfo XML 文件
1. 创建 CAB 文件
1. 上传文件

有关详细信息，请参阅[支持可更新的帮助：分步指南][step-by-step]。

PlatyPS 可帮助你执行其中的一些步骤。

HelpInfoURI 是一个 URL，指向帮助文件在 Internet 上托管的位置。 此值在模块清单中进行配置。 `Update-Help` 读取模块清单以获取此 URL，并下载可更新的帮助内容。 此 URL 只应指向文件夹位置，而不应指向单个文件。 `Update-Help` 根据模块清单和 HelpInfo XML 文件中的其他信息来构造要下载的文件名。

> [!IMPORTANT]
> HelpInfoURI 必须以正斜杠字符 (`/`) 结尾。 没有该字符，`Update-Help` 就无法构造正确的文件路径来下载内容。 而且，大多数基于 HTTP 的文件服务都区分大小写。 重要的是，HelpInfo XML 文件中的模块元数据应包含正确的字母大小写。

`New-ExternalHelp` cmdlet 在输出文件夹中创建 HelpInfo XML 文件。 HelpInfo XML 文件使用模块 Markdown 文件 (`ModuleName.md`).中包含的 YAML 元数据生成。

`New-ExternalHelpCab` cmdlet 可创建包含你编译的 MAML 和 `about_*.help.txt` 文件的 ZIP 和 CAB 文件。 CAB 文件与所有版本的 PowerShell 都兼容。
PowerShell 6 及更高版本可以使用 ZIP 文件。

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

创建 ZIP 和 CAB 文件后，请将 ZIP、CAB 和 HelpInfo XML 文件上传到 HTTP 文件服务器。 将文件放在 HelpInfoURI 指示的位置。

有关详细信息，请参阅 [New-ExternalHelpCab][]。

### <a name="other-publishing-options"></a>其他发布选项

Markdown 是一种通用格式，可以轻松转换为其他格式以供发布。 使用 [Pandoc][] 等工具，可以将 Markdown 帮助文件转换为许多不同的文档格式，包括纯文本、HTML、PDF 和 Office 文档格式。

此外，PowerShell 6 及更高版本中的 cmdlet [ConvertFrom-Markdown][] 和 [Show-Markdown][] 可用于将 Markdown 转换为 HTML 或在 PowerShell 控制台中创建彩色显示内容。

## <a name="known-issues"></a>已知问题

对于创建和编译的 Markdown 文件的结构，PlatyPS 对其[模式][]非常敏感。 很轻易就能编写违反此架构的有效 Markdown。 有关详细信息，请参阅 [PowerShell 风格指南][]和[编辑参考文章][]。

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[架构]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[PowerShell 风格指南]: /powershell/scripting/community/contributing/powershell-style-guide
[编辑参考文章]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[编写针对模块的帮助]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
