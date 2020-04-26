---
title: 编辑参考文章
description: 本文说明编辑 PowerShell 文档中的 cmdlet 参考和“关于”主题的特定要求。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: e135f6cc81ba7537a535a08421e1ca9b2b2af573
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624765"
---
# <a name="editing-reference-articles"></a><span data-ttu-id="45838-103">编辑参考文章</span><span class="sxs-lookup"><span data-stu-id="45838-103">Editing reference articles</span></span>

<span data-ttu-id="45838-104">Cmdlet 参考文章具有特定结构。</span><span class="sxs-lookup"><span data-stu-id="45838-104">Cmdlet reference articles have a specific structure.</span></span> <span data-ttu-id="45838-105">此结构是由 [PlatyPS][] 定义的。</span><span class="sxs-lookup"><span data-stu-id="45838-105">This structure is defined by [PlatyPS][].</span></span>
<span data-ttu-id="45838-106">PlatyPS 在 Markdown 中为 PowerShell 模块生成 cmdlet 帮助。</span><span class="sxs-lookup"><span data-stu-id="45838-106">PlatyPS generates the cmdlet help for PowerShell modules in Markdown.</span></span> <span data-ttu-id="45838-107">编辑 Markdown 文件后，使用 PlatyPS 创建 `Get-Help` cmdlet 使用的 MAML 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="45838-107">After editing the Markdown files, PlatyPS is used create the MAML help files used by the `Get-Help` cmdlet.</span></span>

<span data-ttu-id="45838-108">PlatyPS 拥有针对 cmdlet 参考的硬编码架构，该架构已写入代码。</span><span class="sxs-lookup"><span data-stu-id="45838-108">PlatyPS has a hard-coded schema for cmdlet reference that is written into the code.</span></span> <span data-ttu-id="45838-109">[platyPS.schema.md][] 文档尝试描述此结构。</span><span class="sxs-lookup"><span data-stu-id="45838-109">The [platyPS.schema.md][] document attempts to describe this structure.</span></span> <span data-ttu-id="45838-110">架构冲突会导致生成错误，必须先修复这些错误，我们才能接受你参与撰写。</span><span class="sxs-lookup"><span data-stu-id="45838-110">Schema violations cause build errors that must be fixed before we can accept your contribution.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="45838-111">一般性指导</span><span class="sxs-lookup"><span data-stu-id="45838-111">General guidelines</span></span>

- <span data-ttu-id="45838-112">不要删除任何标头结构。</span><span class="sxs-lookup"><span data-stu-id="45838-112">Do not remove any of the header structures.</span></span> <span data-ttu-id="45838-113">PlatyPS 需要一组特定的标头。</span><span class="sxs-lookup"><span data-stu-id="45838-113">PlatyPS expects a specific set of headers.</span></span>
- <span data-ttu-id="45838-114">“输入类型”和“输出类型”标头必须包含一种类型。  </span><span class="sxs-lookup"><span data-stu-id="45838-114">The **Input type** and **Output type** headers must have a type.</span></span> <span data-ttu-id="45838-115">若 cmdlet 不接受输入或不返回值，则使用值 `None`。</span><span class="sxs-lookup"><span data-stu-id="45838-115">If the cmdlet does not take input or return a value then use the value `None`.</span></span>
- <span data-ttu-id="45838-116">仅[示例](#structuring-examples)部分允许隔离代码块。</span><span class="sxs-lookup"><span data-stu-id="45838-116">Fenced code blocks are only allowed in the [Examples](#structuring-examples) section.</span></span>
- <span data-ttu-id="45838-117">内联代码跨度可用于任何段落。</span><span class="sxs-lookup"><span data-stu-id="45838-117">Inline code spans can be used in any paragraph.</span></span>

## <a name="formatting-about_-files"></a><span data-ttu-id="45838-118">设置 About_ 文件的格式</span><span class="sxs-lookup"><span data-stu-id="45838-118">Formatting About_ files</span></span>

<span data-ttu-id="45838-119">`About_*` 文件是使用 Markdown 编写的，但以纯文本文件的形式提供。</span><span class="sxs-lookup"><span data-stu-id="45838-119">`About_*` files are written in Markdown but are shipped as plain text files.</span></span> <span data-ttu-id="45838-120">我们使用 [Pandoc][] 将 Markdown 转换为纯文本。</span><span class="sxs-lookup"><span data-stu-id="45838-120">We use [Pandoc][] to convert the Markdown to plain text.</span></span> <span data-ttu-id="45838-121">设置 `About_*` 文件的格式，以使其在 PowerShell 的所有版本上均可与发布工具良好兼容。</span><span class="sxs-lookup"><span data-stu-id="45838-121">`About_*` files are formatted for the best compatibility across all versions of PowerShell and with the publishing tools.</span></span>

<span data-ttu-id="45838-122">格式设置基本准则：</span><span class="sxs-lookup"><span data-stu-id="45838-122">Basic formatting guidelines:</span></span>

- <span data-ttu-id="45838-123">将行限制为 80 个字符。</span><span class="sxs-lookup"><span data-stu-id="45838-123">Limit lines to 80 characters.</span></span> <span data-ttu-id="45838-124">Pandoc 会缩进一些 Markdown 块，因此必须调整这些块。</span><span class="sxs-lookup"><span data-stu-id="45838-124">Pandoc indents some Markdown blocks so those block must be adjusted.</span></span>
  - <span data-ttu-id="45838-125">将代码块限制为 76 个字符</span><span class="sxs-lookup"><span data-stu-id="45838-125">Code blocks are limited to 76 characters</span></span>
  - <span data-ttu-id="45838-126">将表限制为 76 个字符</span><span class="sxs-lookup"><span data-stu-id="45838-126">Tables are limited 76 characters</span></span>
  - <span data-ttu-id="45838-127">将块引用（和通知）限制为 78 个字符</span><span class="sxs-lookup"><span data-stu-id="45838-127">Blockquotes (and Alerts) are limited 78 characters</span></span>

- <span data-ttu-id="45838-128">使用 Pandoc 的特殊元字符 `\`、`$` 和 `<`</span><span class="sxs-lookup"><span data-stu-id="45838-128">Using Pandoc's special meta-characters `\`,`$`, and `<`</span></span>
  - <span data-ttu-id="45838-129">在标题中，必须使用前导 `\` 字符对这些字符进行转义，或者使用反引号 (`` ` ``) 括在代码范围中</span><span class="sxs-lookup"><span data-stu-id="45838-129">Within a header - these characters must be escaped using a leading `\` character or enclosed in code spans using backticks (`` ` ``)</span></span>
  - <span data-ttu-id="45838-130">在段落中，应将这些字符置于代码跨度内。</span><span class="sxs-lookup"><span data-stu-id="45838-130">Within a paragraph, these characters should be put into code spans.</span></span> <span data-ttu-id="45838-131">例如：</span><span class="sxs-lookup"><span data-stu-id="45838-131">For example:</span></span>

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- <span data-ttu-id="45838-132">表需要在 76 个字符内</span><span class="sxs-lookup"><span data-stu-id="45838-132">Tables need to fit within 76 characters</span></span>
  - <span data-ttu-id="45838-133">手动包装多个行中单元格的内容</span><span class="sxs-lookup"><span data-stu-id="45838-133">Manually wrap contents of cells across multiple lines</span></span>
  - <span data-ttu-id="45838-134">在每行上使用开始和结束 `|` 字符</span><span class="sxs-lookup"><span data-stu-id="45838-134">Use opening and closing `|` characters on each line</span></span>
  - <span data-ttu-id="45838-135">下面的示例展示了如何正确构造一个表，该表包含在单元内的多个行上换行的信息。</span><span class="sxs-lookup"><span data-stu-id="45838-135">The following example illustrates how to properly construct a table that contains information that wraps on multiple lines within a cell.</span></span>

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > <span data-ttu-id="45838-136">76 列的限制仅适用于 `About_*` 主题。</span><span class="sxs-lookup"><span data-stu-id="45838-136">The 76-column limitation applies only to `About_*` topics.</span></span> <span data-ttu-id="45838-137">可以在概念性文章或 cmdlet 参考文章中使用宽列。</span><span class="sxs-lookup"><span data-stu-id="45838-137">You can use wide columns in conceptual or cmdlet reference articles.</span></span>

## <a name="structuring-examples"></a><span data-ttu-id="45838-138">结构示例</span><span class="sxs-lookup"><span data-stu-id="45838-138">Structuring examples</span></span>

<span data-ttu-id="45838-139">在 PlatyPS 架构中，EXAMPLES 标头是 H2 标头，每个示例是 H3 标头。 </span><span class="sxs-lookup"><span data-stu-id="45838-139">In the PlatyPS schema, the **EXAMPLES** header is an H2 header and each example is an H3 header.</span></span>

<span data-ttu-id="45838-140">在示例中，此架构不允许通过段落来分隔代码块。</span><span class="sxs-lookup"><span data-stu-id="45838-140">Within an example, the schema does not allow code blocks to be separated by paragraphs.</span></span> <span data-ttu-id="45838-141">支持的架构为：</span><span class="sxs-lookup"><span data-stu-id="45838-141">The supported schema is:</span></span>

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

<span data-ttu-id="45838-142">为每个示例编号，并添加简短标题。</span><span class="sxs-lookup"><span data-stu-id="45838-142">Number each example and add a brief title.</span></span>

<span data-ttu-id="45838-143">例如：</span><span class="sxs-lookup"><span data-stu-id="45838-143">For example:</span></span>

### <a name="example-1-get-cmdlets-functions-and-aliases"></a><span data-ttu-id="45838-144">示例 1：获取 cmdlet、函数和别名</span><span class="sxs-lookup"><span data-stu-id="45838-144">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="45838-145">此命令将获取安装在计算机上的 PowerShell cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="45838-145">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a><span data-ttu-id="45838-146">示例 2：获取当前会话中的命令</span><span class="sxs-lookup"><span data-stu-id="45838-146">Example 2: Get commands in the current session</span></span>

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a><span data-ttu-id="45838-147">后续步骤</span><span class="sxs-lookup"><span data-stu-id="45838-147">Next steps</span></span>

[<span data-ttu-id="45838-148">编辑清单</span><span class="sxs-lookup"><span data-stu-id="45838-148">Editorial checklist</span></span>](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
