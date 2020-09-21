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
# <a name="create-xml-based-help-using-platyps"></a><span data-ttu-id="d05c4-103">使用 PlatyPS 创建基于 XML 的帮助文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-103">Create XML-based help using PlatyPS</span></span>

<span data-ttu-id="d05c4-104">创建 PowerShell 模块时，始终建议包含有关所创建的 cmdlet 的详细帮助。</span><span class="sxs-lookup"><span data-stu-id="d05c4-104">When creating a PowerShell module, it is always recommended that you include detailed help for the cmdlets you create.</span></span> <span data-ttu-id="d05c4-105">如果 cmdlet 是用已编译代码实现的，就必须使用基于 XML 的帮助。</span><span class="sxs-lookup"><span data-stu-id="d05c4-105">If your cmdlets are implemented in compiled code, you must use the XML-based help.</span></span> <span data-ttu-id="d05c4-106">这种 XML 格式称为 Microsoft 协助标记语言 (MAML)。</span><span class="sxs-lookup"><span data-stu-id="d05c4-106">This XML format is known as the Microsoft Assistance Markup Language (MAML).</span></span>

<span data-ttu-id="d05c4-107">旧版 PowerShell SDK 文档涵盖了为打包到模块中的 PowerShell cmdlet 创建帮助文件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d05c4-107">The legacy PowerShell SDK documentation covers the details of creating help for PowerShell cmdlets packaged into modules.</span></span> <span data-ttu-id="d05c4-108">但是，PowerShell 不会为创建基于 XML 的帮助文件提供任何工具。</span><span class="sxs-lookup"><span data-stu-id="d05c4-108">However, PowerShell does not provide any tools for creating the XML-based help.</span></span> <span data-ttu-id="d05c4-109">SDK 文档介绍了 MAML 帮助的结构，但你需要手动创建复杂且深度嵌套的 MAML 内容。</span><span class="sxs-lookup"><span data-stu-id="d05c4-109">The SDK documentation explains the structure of MAML help, but leaves you the task of creating the complex, and deeply nested, MAML content by hand.</span></span>

<span data-ttu-id="d05c4-110">[PlatyPS][] 模块可对此提供帮助。</span><span class="sxs-lookup"><span data-stu-id="d05c4-110">This is where the [PlatyPS][] module can help.</span></span>

## <a name="what-is-platyps"></a><span data-ttu-id="d05c4-111">什么是 PlatyPS？</span><span class="sxs-lookup"><span data-stu-id="d05c4-111">What is PlatyPS?</span></span>

<span data-ttu-id="d05c4-112">PlatyPS 是一种[开放源代码][platyps-repo]工具，最初属于黑客马拉松项目，目的是以更轻松的方式创建和维护 MAML。</span><span class="sxs-lookup"><span data-stu-id="d05c4-112">PlatyPS is an [open-source][platyps-repo] tool that started as a _hackathon_ project to make the creation and maintenance of MAML easier.</span></span> <span data-ttu-id="d05c4-113">PlatyPS 记录了参数集的语法以及模块中每个 cmdlet 的各个参数。</span><span class="sxs-lookup"><span data-stu-id="d05c4-113">PlatyPS documents the syntax of parameter sets and the individual parameters for each cmdlet in your module.</span></span> <span data-ttu-id="d05c4-114">PlatyPS 可创建包含语法信息的结构化 [Markdown][] 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-114">PlatyPS creates structured [Markdown][] files that contain the syntax information.</span></span> <span data-ttu-id="d05c4-115">它无法创建说明或提供示例。</span><span class="sxs-lookup"><span data-stu-id="d05c4-115">It can't create descriptions or provide examples.</span></span>

<span data-ttu-id="d05c4-116">PlatyPS 会创建占位符，以供填写说明和示例。</span><span class="sxs-lookup"><span data-stu-id="d05c4-116">PlatyPS creates placeholders for you to fill in descriptions and examples.</span></span> <span data-ttu-id="d05c4-117">添加所需的信息后，PlatyPS 会将 Markdown 文件编译为 MAML 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-117">After adding the required information, PlatyPS compiles the Markdown files into MAML files.</span></span> <span data-ttu-id="d05c4-118">PowerShell 的帮助系统还允许提供纯文本概念性帮助文件（关于主题）。</span><span class="sxs-lookup"><span data-stu-id="d05c4-118">PowerShell's help system also allows for plain-text conceptual help files (about topics).</span></span> <span data-ttu-id="d05c4-119">PlatyPS 有一个 cmdlet，用于为新的“关于”文件创建结构化 Markdown 模板，但是这些 `about_*.help.txt` 文件必须手动进行维护。</span><span class="sxs-lookup"><span data-stu-id="d05c4-119">PlatyPS has a cmdlet to create a structured Markdown template for a new _about_ file, but these `about_*.help.txt` files must be maintained manually.</span></span>

<span data-ttu-id="d05c4-120">可以在模块中包含 MAML 和文本帮助文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-120">You can include the MAML and Text help files with your module.</span></span> <span data-ttu-id="d05c4-121">还可以使用 PlatyPS 将帮助文件编译成可托管的 CAB 包，以提供可更新帮助。</span><span class="sxs-lookup"><span data-stu-id="d05c4-121">You can also use PlatyPS to compile the help files into a CAB package that can be hosted for updateable help.</span></span>

## <a name="get-started-using-platyps"></a><span data-ttu-id="d05c4-122">开始使用 PlatyPS</span><span class="sxs-lookup"><span data-stu-id="d05c4-122">Get started using PlatyPS</span></span>

<span data-ttu-id="d05c4-123">首先，必须从 PowerShell 库安装 PlatyPS。</span><span class="sxs-lookup"><span data-stu-id="d05c4-123">First you must install PlatyPS from the PowerShell Gallery.</span></span>

```powershell
Install-Module platyps -Force
Import-Module platyps
```

<span data-ttu-id="d05c4-124">以下流程图概述了创建或更新 PowerShell 引用内容的过程。</span><span class="sxs-lookup"><span data-stu-id="d05c4-124">The following flowchart outlines the process for creating or updating PowerShell reference content.</span></span>

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="使用 PlatyPS 创建基于 XML 的帮助文件的工作流":::

##  <a name="create-markdown-content-for-a-powershell-module"></a><span data-ttu-id="d05c4-126">为 PowerShell 模块创建 Markdown 内容</span><span class="sxs-lookup"><span data-stu-id="d05c4-126">Create Markdown content for a PowerShell module</span></span>

1. <span data-ttu-id="d05c4-127">将新模块导入会话。</span><span class="sxs-lookup"><span data-stu-id="d05c4-127">Import your new module into the session.</span></span> <span data-ttu-id="d05c4-128">对需要记录的每个模块重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d05c4-128">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="d05c4-129">运行以下命令以导入模块：</span><span class="sxs-lookup"><span data-stu-id="d05c4-129">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="d05c4-130">使用 PlatyPS 为模块页面和模块内的所有关联 cmdlet 生成 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-130">Use PlatyPS to generate Markdown files for your module page and all associated cmdlets within the module.</span></span> <span data-ttu-id="d05c4-131">对需要记录的每个模块重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d05c4-131">Repeat this step for each module you need to document.</span></span>

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

   <span data-ttu-id="d05c4-132">如果输出文件夹不存在，请使用 `New-MarkdownHelp` 创建一个。</span><span class="sxs-lookup"><span data-stu-id="d05c4-132">If the output folder does not exist, `New-MarkdownHelp` creates it.</span></span> <span data-ttu-id="d05c4-133">在本示例中，`New-MarkdownHelp` 为模块中的每个 cmdlet 创建 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-133">In this example, `New-MarkdownHelp` creates a Markdown file for each cmdlet in the module.</span></span> <span data-ttu-id="d05c4-134">同时还在名为 `<ModuleName>.md` 的文件中创建模块页面。</span><span class="sxs-lookup"><span data-stu-id="d05c4-134">It also creates the _module page_ in a file named `<ModuleName>.md`.</span></span> <span data-ttu-id="d05c4-135">此模块页面包含模块中包含的 cmdlet 的列表以及摘要说明的占位符。</span><span class="sxs-lookup"><span data-stu-id="d05c4-135">This module page contains a list of the cmdlets contained in the module and placeholders for the **Synopsis** description.</span></span> <span data-ttu-id="d05c4-136">模块页面中的元数据来自模块清单，PlatyPS 使用该数据创建 HelpInfo XML 文件（如[下面部分](#creating-an-updateable-help-package)所述）。</span><span class="sxs-lookup"><span data-stu-id="d05c4-136">The metadata in the module page comes from the module manifest and is used by PlatyPS to create the HelpInfo XML file (as explained [below](#creating-an-updateable-help-package)).</span></span>

   <span data-ttu-id="d05c4-137">`New-MarkdownAboutHelp` 创建名为 `about_topic_name.md` 的新的“关于”文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-137">`New-MarkdownAboutHelp` creates a new _about_ file named `about_topic_name.md`.</span></span>

   <span data-ttu-id="d05c4-138">有关详细信息，请参阅 [New-MarkdownHelp][] 和 [New-MarkdownAboutHelp][]。</span><span class="sxs-lookup"><span data-stu-id="d05c4-138">For more information, see [New-MarkdownHelp][] and [New-MarkdownAboutHelp][].</span></span>

### <a name="update-existing-markdown-content-when-the-module-changes"></a><span data-ttu-id="d05c4-139">模块更改时会更新现有 Markdown 内容</span><span class="sxs-lookup"><span data-stu-id="d05c4-139">Update existing Markdown content when the module changes</span></span>

<span data-ttu-id="d05c4-140">PlatyPS 还可以更新模块的现有 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-140">PlatyPS can also update existing Markdown files for a module.</span></span> <span data-ttu-id="d05c4-141">使用此步骤更新包含新 cmdlet、新参数或已更改参数的现有模块。</span><span class="sxs-lookup"><span data-stu-id="d05c4-141">Use this step to update existing modules that have new cmdlets, new parameters, or parameters that have changed.</span></span>

1. <span data-ttu-id="d05c4-142">将新模块导入会话。</span><span class="sxs-lookup"><span data-stu-id="d05c4-142">Import your new module into the session.</span></span> <span data-ttu-id="d05c4-143">对需要记录的每个模块重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d05c4-143">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="d05c4-144">运行以下命令以导入模块：</span><span class="sxs-lookup"><span data-stu-id="d05c4-144">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="d05c4-145">使用 PlatyPS 为模块登陆页面和模块内的所有关联 cmdlet 更新 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-145">Use PlatyPS to update Markdown files for your module landing page and all associated cmdlets within the module.</span></span> <span data-ttu-id="d05c4-146">对需要记录的每个模块重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d05c4-146">Repeat this step for each module you need to document.</span></span>

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

   <span data-ttu-id="d05c4-147">`Update-MarkdownHelpModule` 更新指定文件夹中的 cmdlet 和模块 Markdown 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-147">`Update-MarkdownHelpModule` updates the cmdlet and module Markdown files in the specified folder.</span></span>
   <span data-ttu-id="d05c4-148">它不会更新 `about_*.md` 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-148">It does not update the `about_*.md` files.</span></span> <span data-ttu-id="d05c4-149">模块文件 (`ModuleName.md`) 接收已添加到 cmdlet 文件中的所有新摘要文本。</span><span class="sxs-lookup"><span data-stu-id="d05c4-149">The module file (`ModuleName.md`) receives any new **Synopsis** text that has been added to the cmdlet files.</span></span> <span data-ttu-id="d05c4-150">cmdlet 文件更新包括以下更改：</span><span class="sxs-lookup"><span data-stu-id="d05c4-150">Updates to cmdlet files include the following change:</span></span>

   - <span data-ttu-id="d05c4-151">新参数集</span><span class="sxs-lookup"><span data-stu-id="d05c4-151">New parameter sets</span></span>
   - <span data-ttu-id="d05c4-152">新参数</span><span class="sxs-lookup"><span data-stu-id="d05c4-152">New parameters</span></span>
   - <span data-ttu-id="d05c4-153">更新后的参数元数据</span><span class="sxs-lookup"><span data-stu-id="d05c4-153">Updated parameter metadata</span></span>
   - <span data-ttu-id="d05c4-154">更新后的输入和输出类型信息</span><span class="sxs-lookup"><span data-stu-id="d05c4-154">Updated input and output type information</span></span>

   <span data-ttu-id="d05c4-155">有关详细信息，请参阅 [Update-MarkdownHelpModule][]。</span><span class="sxs-lookup"><span data-stu-id="d05c4-155">For more information, see [Update-MarkdownHelpModule][].</span></span>

## <a name="edit-the-new-or-updated-markdown-files"></a><span data-ttu-id="d05c4-156">编辑新的或更新后的 Markdown 文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-156">Edit the new or updated Markdown files</span></span>

<span data-ttu-id="d05c4-157">PlatyPS 记录了参数集和各个参数的语法。</span><span class="sxs-lookup"><span data-stu-id="d05c4-157">PlatyPS documents the syntax of the parameter sets and the individual parameters.</span></span> <span data-ttu-id="d05c4-158">它无法创建说明或提供示例。</span><span class="sxs-lookup"><span data-stu-id="d05c4-158">It can't create descriptions or provide examples.</span></span> <span data-ttu-id="d05c4-159">大括号中包含需要内容的特定区域。</span><span class="sxs-lookup"><span data-stu-id="d05c4-159">The specific areas where content is needed are contained in curly braces.</span></span> <span data-ttu-id="d05c4-160">例如：`{{ Fill in the Description }}`</span><span class="sxs-lookup"><span data-stu-id="d05c4-160">For example: `{{ Fill in the Description }}`</span></span>

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="显示 VS Code 中占位符的 Markdown 模板":::

<span data-ttu-id="d05c4-162">需要添加摘要、cmdlet 的说明、每个参数的说明以及至少一个示例。</span><span class="sxs-lookup"><span data-stu-id="d05c4-162">You need to add a synopsis, a description of the cmdlet, descriptions for each parameter, and at least one example.</span></span>

<span data-ttu-id="d05c4-163">有关编写 PowerShell 内容的详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="d05c4-163">For detailed information about writing PowerShell content, see the following articles:</span></span>

- [<span data-ttu-id="d05c4-164">PowerShell 风格指南</span><span class="sxs-lookup"><span data-stu-id="d05c4-164">PowerShell style guide</span></span>](/powershell/scripting/community/contributing/powershell-style-guide)
- [<span data-ttu-id="d05c4-165">编辑参考文章</span><span class="sxs-lookup"><span data-stu-id="d05c4-165">Editing reference articles</span></span>](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> <span data-ttu-id="d05c4-166">PlatyPS 具有用于 cmdlet 引用的特定架构。</span><span class="sxs-lookup"><span data-stu-id="d05c4-166">PlatyPS has a specific schema that is uses for cmdlet reference.</span></span> <span data-ttu-id="d05c4-167">该架构仅允许文档特定部分中的某些 Markdown 块。</span><span class="sxs-lookup"><span data-stu-id="d05c4-167">That schema only allows certain Markdown blocks in specific sections of the document.</span></span> <span data-ttu-id="d05c4-168">如果将内容置于错误位置，PlatyPS 构建步骤便会失败。</span><span class="sxs-lookup"><span data-stu-id="d05c4-168">If you put content in the wrong location, the PlatyPS build step fails.</span></span> <span data-ttu-id="d05c4-169">有关详细信息，请参阅 PlatyPS 存储库中的[架构][]文档。</span><span class="sxs-lookup"><span data-stu-id="d05c4-169">For more information, see the [schema][] documentation in the PlatyPS repository.</span></span> <span data-ttu-id="d05c4-170">有关格式标准的 cmdlet 引用的完整示例，请参阅 [Get-Item][]。</span><span class="sxs-lookup"><span data-stu-id="d05c4-170">For a complete example of well-formed cmdlet reference, see [Get-Item][].</span></span>

<span data-ttu-id="d05c4-171">在为每个 cmdlet 提供所需内容之后，需要确保更新模块登陆页面。</span><span class="sxs-lookup"><span data-stu-id="d05c4-171">After providing the required content for each of your cmdlets, you need to make sure that you update the module landing page.</span></span> <span data-ttu-id="d05c4-172">验证模块在 `<module-name>.md` 文件的 YAML 元数据中是否具有正确的 `Module Guid` 和 `Download Help Link` 值。</span><span class="sxs-lookup"><span data-stu-id="d05c4-172">Verify your module has the correct `Module Guid` and `Download Help Link` values in the YAML metadata of the `<module-name>.md` file.</span></span> <span data-ttu-id="d05c4-173">添加任何缺失的元数据。</span><span class="sxs-lookup"><span data-stu-id="d05c4-173">Add any missing metadata.</span></span>

<span data-ttu-id="d05c4-174">此外，你可能会注意到某些 cmdlet 可能缺少摘要（简短说明）。</span><span class="sxs-lookup"><span data-stu-id="d05c4-174">Also, you may notice that some cmdlets may be missing a **Synopsis** (_short description_).</span></span> <span data-ttu-id="d05c4-175">以下命令使用摘要说明文本更新模块登陆页面。</span><span class="sxs-lookup"><span data-stu-id="d05c4-175">The following command updates the module landing page with your **Synopsis** description text.</span></span> <span data-ttu-id="d05c4-176">打开模块登陆页面，验证说明。</span><span class="sxs-lookup"><span data-stu-id="d05c4-176">Open the module landing page to verify the descriptions.</span></span>

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

<span data-ttu-id="d05c4-177">现在，你已输入所有内容，可以创建 `Get-Help` 在 PowerShell 控制台中显示的 MAML 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-177">Now that you have entered all the content, you can create the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

## <a name="create-the-external-help-files"></a><span data-ttu-id="d05c4-178">创建外部帮助文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-178">Create the external help files</span></span>

<span data-ttu-id="d05c4-179">此步骤会创建 `Get-Help` 在 PowerShell 控制台中显示的 MAML 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-179">This step creates the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

<span data-ttu-id="d05c4-180">若要生成 MAML 文件，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d05c4-180">To build the MAML files, run the following command:</span></span>

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

<span data-ttu-id="d05c4-181">`New-ExternalHelp` 将所有 cmdlet Markdown 文件转换为一个（或多个）MAML 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-181">`New-ExternalHelp` converts all of the cmdlet Markdown files into one (or more) MAML files.</span></span> <span data-ttu-id="d05c4-182">“关于”文件会转换为具有以下名称格式的纯文本文件：`about_topic_name.help.txt`。</span><span class="sxs-lookup"><span data-stu-id="d05c4-182">About files are converted to plain-text files with the following name format: `about_topic_name.help.txt`.</span></span>
<span data-ttu-id="d05c4-183">Markdown 内容必须符合 PlatyPS 架构的要求。</span><span class="sxs-lookup"><span data-stu-id="d05c4-183">The Markdown content must meet the requirement of the PlatyPS schema.</span></span> <span data-ttu-id="d05c4-184">当内容不遵循架构时，`New-ExternalHelp` 将退出并出现错误。</span><span class="sxs-lookup"><span data-stu-id="d05c4-184">`New-ExternalHelp` will exits with errors when the content does not follow the schema.</span></span> <span data-ttu-id="d05c4-185">必须编辑文件才能解决架构冲突。</span><span class="sxs-lookup"><span data-stu-id="d05c4-185">You must edit the files to fix the schema violations.</span></span>

> [!CAUTION]
> <span data-ttu-id="d05c4-186">PlatyPS 不擅长将 `about_*.md` 文件转换为纯文本。</span><span class="sxs-lookup"><span data-stu-id="d05c4-186">PlatyPS does a poor job converting the `about_*.md` files to plain text.</span></span> <span data-ttu-id="d05c4-187">必须使用非常简单的 Markdown 才能获得可接受的结果。</span><span class="sxs-lookup"><span data-stu-id="d05c4-187">You must use very simple Markdown to get acceptable results.</span></span> <span data-ttu-id="d05c4-188">建议以纯文本 `about_topic_name.help.txt` 格式维护文件，而不是允许 PlatyPS 对其进行转换。</span><span class="sxs-lookup"><span data-stu-id="d05c4-188">You may want to maintain the files in plain-text `about_topic_name.help.txt` format, rather than allowing PlatyPS to convert them.</span></span>

<span data-ttu-id="d05c4-189">完成此步骤后，目标输出文件夹中将出现 `*-help.xml` 和 `about_*.help.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-189">Once this step is complete, you will see `*-help.xml` and `about_*.help.txt` files in the target output folder.</span></span>

<span data-ttu-id="d05c4-190">有关详细信息，请参阅 [New-ExternalHelp][]</span><span class="sxs-lookup"><span data-stu-id="d05c4-190">For more information, see [New-ExternalHelp][]</span></span>

### <a name="test-the-compiled-help-files"></a><span data-ttu-id="d05c4-191">测试编译的帮助文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-191">Test the compiled help files</span></span>

<span data-ttu-id="d05c4-192">可以使用 [Get-HelpPreview][] cmdlet 验证内容：</span><span class="sxs-lookup"><span data-stu-id="d05c4-192">You can verify the content with the [Get-HelpPreview][] cmdlet:</span></span>

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

<span data-ttu-id="d05c4-193">该 cmdlet 读取编译的 MAML 文件，并以相同格式输出要从 `Get-Help` 接收的内容。</span><span class="sxs-lookup"><span data-stu-id="d05c4-193">The cmdlet reads the compiled MAML file and outputs the content in the same format you would receive from `Get-Help`.</span></span> <span data-ttu-id="d05c4-194">这使你可以检查结果，以验证 Markdown 文件是否正确编译以及是否生成所需的结果。</span><span class="sxs-lookup"><span data-stu-id="d05c4-194">This allows you to inspect the results to verify that the Markdown files compiled correctly and produce the desired results.</span></span> <span data-ttu-id="d05c4-195">如果发现错误，请重新编辑 Markdown 文件并重新编译 MAML。</span><span class="sxs-lookup"><span data-stu-id="d05c4-195">If you find an error, re-edit the Markdown files and recompile the MAML.</span></span>

<span data-ttu-id="d05c4-196">现在可以发布帮助文件了。</span><span class="sxs-lookup"><span data-stu-id="d05c4-196">Now you are ready to publish your help files.</span></span>

## <a name="publishing-your-help"></a><span data-ttu-id="d05c4-197">发布帮助文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-197">Publishing your help</span></span>

<span data-ttu-id="d05c4-198">现在，你已将 Markdown 文件编译为 PowerShell 帮助文件，可以向用户提供这些文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-198">Now that you have compiled the Markdown files into PowerShell help files, you are ready to make the files available to users.</span></span> <span data-ttu-id="d05c4-199">在 PowerShell 控制台中有两个选项可提供帮助。</span><span class="sxs-lookup"><span data-stu-id="d05c4-199">There are two options for providing help in the PowerShell console.</span></span>

- <span data-ttu-id="d05c4-200">将帮助文件打包到模块</span><span class="sxs-lookup"><span data-stu-id="d05c4-200">Package the help files with the module</span></span>
- <span data-ttu-id="d05c4-201">创建用户使用 `Update-Help` cmdlet 安装的可更新帮助包</span><span class="sxs-lookup"><span data-stu-id="d05c4-201">Create an updateable help package that users install with the `Update-Help` cmdlet</span></span>

### <a name="packaging-help-with-the-module"></a><span data-ttu-id="d05c4-202">将帮助文件与模块一起打包</span><span class="sxs-lookup"><span data-stu-id="d05c4-202">Packaging help with the module</span></span>

<span data-ttu-id="d05c4-203">帮助文件可与模块一起打包。</span><span class="sxs-lookup"><span data-stu-id="d05c4-203">The help files can be packaged with your module.</span></span> <span data-ttu-id="d05c4-204">有关文件夹结构的详细信息，请参阅[编写针对模块的帮助][]。</span><span class="sxs-lookup"><span data-stu-id="d05c4-204">See [Writing Help for Modules][] for details of the folder structure.</span></span> <span data-ttu-id="d05c4-205">应在模块清单的 FileList 键的值中包含“帮助”文件列表。</span><span class="sxs-lookup"><span data-stu-id="d05c4-205">You should include the list of Help files in the value of the **FileList** key in the module manifest.</span></span>

### <a name="creating-an-updateable-help-package"></a><span data-ttu-id="d05c4-206">创建可更新帮助包</span><span class="sxs-lookup"><span data-stu-id="d05c4-206">Creating an updateable help package</span></span>

<span data-ttu-id="d05c4-207">用于创建可更新帮助文件的步骤大致包括：</span><span class="sxs-lookup"><span data-stu-id="d05c4-207">At a high level, the steps to create updateable help include:</span></span>

1. <span data-ttu-id="d05c4-208">查找用于托管帮助文件的 Internet 站点</span><span class="sxs-lookup"><span data-stu-id="d05c4-208">Find an internet site to host your help files</span></span>
1. <span data-ttu-id="d05c4-209">将 HelpInfoURI 键添加到模块清单</span><span class="sxs-lookup"><span data-stu-id="d05c4-209">Add a **HelpInfoURI** key to your module manifest</span></span>
1. <span data-ttu-id="d05c4-210">创建 HelpInfo XML 文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-210">Create a HelpInfo XML file</span></span>
1. <span data-ttu-id="d05c4-211">创建 CAB 文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-211">Create CAB files</span></span>
1. <span data-ttu-id="d05c4-212">上传文件</span><span class="sxs-lookup"><span data-stu-id="d05c4-212">Upload your files</span></span>

<span data-ttu-id="d05c4-213">有关详细信息，请参阅[支持可更新的帮助：分步指南][step-by-step]。</span><span class="sxs-lookup"><span data-stu-id="d05c4-213">For more information, see [Supporting Updateable Help: Step-by-step][step-by-step].</span></span>

<span data-ttu-id="d05c4-214">PlatyPS 可帮助你执行其中的一些步骤。</span><span class="sxs-lookup"><span data-stu-id="d05c4-214">PlatyPS assists you with  some of these steps.</span></span>

<span data-ttu-id="d05c4-215">HelpInfoURI 是一个 URL，指向帮助文件在 Internet 上托管的位置。</span><span class="sxs-lookup"><span data-stu-id="d05c4-215">The **HelpInfoURI** is a URL that points to location where your help files are hosted on the internet.</span></span> <span data-ttu-id="d05c4-216">此值在模块清单中进行配置。</span><span class="sxs-lookup"><span data-stu-id="d05c4-216">This value is configured in the module manifest.</span></span> <span data-ttu-id="d05c4-217">`Update-Help` 读取模块清单以获取此 URL，并下载可更新的帮助内容。</span><span class="sxs-lookup"><span data-stu-id="d05c4-217">`Update-Help` reads the module manifest to get this URL and download the updateable help content.</span></span> <span data-ttu-id="d05c4-218">此 URL 只应指向文件夹位置，而不应指向单个文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-218">This URL should only point to the folder location and not to individual files.</span></span> <span data-ttu-id="d05c4-219">`Update-Help` 根据模块清单和 HelpInfo XML 文件中的其他信息来构造要下载的文件名。</span><span class="sxs-lookup"><span data-stu-id="d05c4-219">`Update-Help` constructs the filenames to download based on other information from the module manifest and the HelpInfo XML file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d05c4-220">HelpInfoURI 必须以正斜杠字符 (`/`) 结尾。</span><span class="sxs-lookup"><span data-stu-id="d05c4-220">The **HelpInfoURI** must end with a forward-slash character (`/`).</span></span> <span data-ttu-id="d05c4-221">没有该字符，`Update-Help` 就无法构造正确的文件路径来下载内容。</span><span class="sxs-lookup"><span data-stu-id="d05c4-221">Without that character, `Update-Help` cannot construct the correct file paths to download the content.</span></span> <span data-ttu-id="d05c4-222">而且，大多数基于 HTTP 的文件服务都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d05c4-222">Also, most HTTP-based file services are case-sensitive.</span></span> <span data-ttu-id="d05c4-223">重要的是，HelpInfo XML 文件中的模块元数据应包含正确的字母大小写。</span><span class="sxs-lookup"><span data-stu-id="d05c4-223">It is important that the module metadata in the HelpInfo XML file contains the proper letter case.</span></span>

<span data-ttu-id="d05c4-224">`New-ExternalHelp` cmdlet 在输出文件夹中创建 HelpInfo XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-224">The `New-ExternalHelp` cmdlet creates the HelpInfo XML file in the output folder.</span></span> <span data-ttu-id="d05c4-225">HelpInfo XML 文件使用模块 Markdown 文件 (`ModuleName.md`).中包含的 YAML 元数据生成。</span><span class="sxs-lookup"><span data-stu-id="d05c4-225">The HelpInfo XML file is built using YAML metadata contained in the module Markdown files (`ModuleName.md`).</span></span>

<span data-ttu-id="d05c4-226">`New-ExternalHelpCab` cmdlet 可创建包含你编译的 MAML 和 `about_*.help.txt` 文件的 ZIP 和 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-226">The `New-ExternalHelpCab` cmdlet creates ZIP and CAB files containing the MAML and `about_*.help.txt` files you compiled.</span></span> <span data-ttu-id="d05c4-227">CAB 文件与所有版本的 PowerShell 都兼容。</span><span class="sxs-lookup"><span data-stu-id="d05c4-227">CAB files are compatible with all versions of PowerShell.</span></span>
<span data-ttu-id="d05c4-228">PowerShell 6 及更高版本可以使用 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="d05c4-228">PowerShell 6 and higher can use ZIP files.</span></span>

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

<span data-ttu-id="d05c4-229">创建 ZIP 和 CAB 文件后，请将 ZIP、CAB 和 HelpInfo XML 文件上传到 HTTP 文件服务器。</span><span class="sxs-lookup"><span data-stu-id="d05c4-229">After creating the ZIP and CAB files, upload the ZIP, CAB, and HelpInfo XML files to your HTTP file server.</span></span> <span data-ttu-id="d05c4-230">将文件放在 HelpInfoURI 指示的位置。</span><span class="sxs-lookup"><span data-stu-id="d05c4-230">Put the files in the location indicated by the **HelpInfoURI**.</span></span>

<span data-ttu-id="d05c4-231">有关详细信息，请参阅 [New-ExternalHelpCab][]。</span><span class="sxs-lookup"><span data-stu-id="d05c4-231">For more information, see [New-ExternalHelpCab][].</span></span>

### <a name="other-publishing-options"></a><span data-ttu-id="d05c4-232">其他发布选项</span><span class="sxs-lookup"><span data-stu-id="d05c4-232">Other publishing options</span></span>

<span data-ttu-id="d05c4-233">Markdown 是一种通用格式，可以轻松转换为其他格式以供发布。</span><span class="sxs-lookup"><span data-stu-id="d05c4-233">Markdown is a versatile format that is easy to transform to other formats for publishing.</span></span> <span data-ttu-id="d05c4-234">使用 [Pandoc][] 等工具，可以将 Markdown 帮助文件转换为许多不同的文档格式，包括纯文本、HTML、PDF 和 Office 文档格式。</span><span class="sxs-lookup"><span data-stu-id="d05c4-234">Using a tool like [Pandoc][], you can convert your Markdown help files to many different document formats, including plain text, HTML, PDF, and Office document formats.</span></span>

<span data-ttu-id="d05c4-235">此外，PowerShell 6 及更高版本中的 cmdlet [ConvertFrom-Markdown][] 和 [Show-Markdown][] 可用于将 Markdown 转换为 HTML 或在 PowerShell 控制台中创建彩色显示内容。</span><span class="sxs-lookup"><span data-stu-id="d05c4-235">Also, the cmdlets [ConvertFrom-Markdown][] and [Show-Markdown][] in PowerShell 6 and higher can be used to convert Markdown to HTML or create a colorful display in the PowerShell console.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d05c4-236">已知问题</span><span class="sxs-lookup"><span data-stu-id="d05c4-236">Known issues</span></span>

<span data-ttu-id="d05c4-237">对于创建和编译的 Markdown 文件的结构，PlatyPS 对其[模式][]非常敏感。</span><span class="sxs-lookup"><span data-stu-id="d05c4-237">PlatyPS is very sensitive to the [schema][] for the structure of the Markdown files it creates and compiles.</span></span> <span data-ttu-id="d05c4-238">很轻易就能编写违反此架构的有效 Markdown。</span><span class="sxs-lookup"><span data-stu-id="d05c4-238">It is very easy write valid Markdown that violates this schema.</span></span> <span data-ttu-id="d05c4-239">有关详细信息，请参阅 [PowerShell 风格指南][]和[编辑参考文章][]。</span><span class="sxs-lookup"><span data-stu-id="d05c4-239">For more information, consult the [PowerShell style guide][] and [Editing reference articles][].</span></span>

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[架构]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[PowerShell 风格指南]: /powershell/scripting/community/contributing/powershell-style-guide
[PowerShell style guide]: /powershell/scripting/community/contributing/powershell-style-guide
[编辑参考文章]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Editing reference articles]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[编写针对模块的帮助]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[Writing Help for Modules]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
