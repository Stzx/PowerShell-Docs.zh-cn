---
title: PowerShell-Docs 风格指南
description: 本文介绍用于撰写 PowerShell 文档的风格规则。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: b60ad9a4965e75cc5f68309604f1893e5757f351
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83690850"
---
# <a name="powershell-docs-style-guide"></a><span data-ttu-id="908d4-103">PowerShell-Docs 风格指南</span><span class="sxs-lookup"><span data-stu-id="908d4-103">PowerShell-Docs style guide</span></span>

<span data-ttu-id="908d4-104">本文介绍特定于 PowerShell-Docs 内容的风格指南。</span><span class="sxs-lookup"><span data-stu-id="908d4-104">This article provides style guidance specific to the PowerShell-Docs content.</span></span> <span data-ttu-id="908d4-105">本文是根据[概述](overview.md#get-started-writing-docs)中所述的信息撰写的。</span><span class="sxs-lookup"><span data-stu-id="908d4-105">This builds on the information outlined in the [Overview](overview.md#get-started-writing-docs).</span></span>

## <a name="product-terminology"></a><span data-ttu-id="908d4-106">产品术语</span><span class="sxs-lookup"><span data-stu-id="908d4-106">Product Terminology</span></span>

<span data-ttu-id="908d4-107">PowerShell 有多个变体。</span><span class="sxs-lookup"><span data-stu-id="908d4-107">There are several variants of PowerShell.</span></span>

- <span data-ttu-id="908d4-108">**PowerShell** - 这是默认名称。</span><span class="sxs-lookup"><span data-stu-id="908d4-108">**PowerShell** - This is the default.</span></span> <span data-ttu-id="908d4-109">我们认为 PowerShell 7 及其以后的版本将是真正的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="908d4-109">We consider PowerShell 7 and beyond to be the one, true PowerShell going forward.</span></span>
- <span data-ttu-id="908d4-110">**PowerShell Core** - 基于 .NET Core 生成的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="908d4-110">**PowerShell Core** - PowerShell built on .NET Core.</span></span> <span data-ttu-id="908d4-111">只有在有必要与 Windows PowerShell 进行区分的情况下，才会使用术语“Core”  。</span><span class="sxs-lookup"><span data-stu-id="908d4-111">Usage of the term **Core** should be limited to cases where it is necessary to differentiate it from Windows PowerShell.</span></span>
- <span data-ttu-id="908d4-112">**Windows PowerShell** - 基于 .NET Framework 生成的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="908d4-112">**Windows PowerShell** - PowerShell built on .NET Framework.</span></span> <span data-ttu-id="908d4-113">Windows PowerShell 仅对 Windows 提供，并且需要完整的 Framework。</span><span class="sxs-lookup"><span data-stu-id="908d4-113">Windows PowerShell ships only on Windows and requires the complete Framework.</span></span>

  <span data-ttu-id="908d4-114">通常，可以将文档中对“Windows PowerShell”的引用更改为“PowerShell”。</span><span class="sxs-lookup"><span data-stu-id="908d4-114">In general, references to "Windows PowerShell" in documentation can be changed to "PowerShell".</span></span>
  <span data-ttu-id="908d4-115">在介绍“Windows PowerShell”特定的活动时，应使用“Windows PowerShell”。</span><span class="sxs-lookup"><span data-stu-id="908d4-115">"Windows PowerShell" should be used when "Windows PowerShell"-specific behavior is being discussed.</span></span>

<span data-ttu-id="908d4-116">相关产品</span><span class="sxs-lookup"><span data-stu-id="908d4-116">Related products</span></span>

- <span data-ttu-id="908d4-117">Visual Studio Code (VS Code)  - 这是 Microsoft 的免费开源编辑器。</span><span class="sxs-lookup"><span data-stu-id="908d4-117">**Visual Studio Code (VS Code)** - This is Microsoft's free, open source editor.</span></span> <span data-ttu-id="908d4-118">首次提及时，应使用完整名称。</span><span class="sxs-lookup"><span data-stu-id="908d4-118">At first mention, the full name should be used.</span></span> <span data-ttu-id="908d4-119">之后，可以使用 VS Code  。</span><span class="sxs-lookup"><span data-stu-id="908d4-119">After that you may use **VS Code**.</span></span> <span data-ttu-id="908d4-120">不要使用“VSCode”。</span><span class="sxs-lookup"><span data-stu-id="908d4-120">Do not use "VSCode".</span></span>
- <span data-ttu-id="908d4-121">适用于 Visual Studio Code 的 PowerShell 扩展  - 此扩展会将 VS Code 转换为适用于 PowerShell 的首选 IDE。</span><span class="sxs-lookup"><span data-stu-id="908d4-121">**PowerShell Extension for Visual Studio Code** - The extension turns VS Code into the preferred IDE for PowerShell.</span></span> <span data-ttu-id="908d4-122">首次提及时，应使用完整名称。</span><span class="sxs-lookup"><span data-stu-id="908d4-122">At first mention, the full name should be used.</span></span> <span data-ttu-id="908d4-123">之后，可以使用 PowerShell 扩展  。</span><span class="sxs-lookup"><span data-stu-id="908d4-123">After that you may use **PowerShell extension**.</span></span>
- <span data-ttu-id="908d4-124">Azure PowerShell  - 这是用于管理 Azure 服务的 PowerShell 模块的集合。</span><span class="sxs-lookup"><span data-stu-id="908d4-124">**Azure PowerShell** - This is the collection of PowerShell modules used to manage Azure services.</span></span>
- <span data-ttu-id="908d4-125">Azure Stack PowerShell  - 这是用于管理 Microsoft 混合云解决方案的 PowerShell 模块的集合。</span><span class="sxs-lookup"><span data-stu-id="908d4-125">**Azure Stack PowerShell** - This is the collection of PowerShell modules used to manage Microsoft's hybrid cloud solution.</span></span>

## <a name="markdown-specifics"></a><span data-ttu-id="908d4-126">Markdown 详情</span><span class="sxs-lookup"><span data-stu-id="908d4-126">Markdown specifics</span></span>

<span data-ttu-id="908d4-127">用于生成文档的 Microsoft 开放发布系统 (OPS) 使用 [markdig][] 处理 Markdown 文档。</span><span class="sxs-lookup"><span data-stu-id="908d4-127">The Microsoft Open Publishing System (OPS) that builds our documentation uses [markdig][] to process the Markdown documents.</span></span> <span data-ttu-id="908d4-128">Markdig 根据最新 [CommonMark][] 规范的规则分析文档。</span><span class="sxs-lookup"><span data-stu-id="908d4-128">Markdig parses the documents based on the rules of the latest [CommonMark][] specification.</span></span>

<span data-ttu-id="908d4-129">新的 CommonMark 规范比某些 Markdown 元素的构造要严格得多。</span><span class="sxs-lookup"><span data-stu-id="908d4-129">The new CommonMark spec is much stricter about the construction of some Markdown elements.</span></span> <span data-ttu-id="908d4-130">请密切关注本文档中提供的详细信息。</span><span class="sxs-lookup"><span data-stu-id="908d4-130">Pay close attention to the details provided in this document.</span></span>

### <a name="blank-lines-spaces-and-tabs"></a><span data-ttu-id="908d4-131">空白行、空格和制表符</span><span class="sxs-lookup"><span data-stu-id="908d4-131">Blank lines, spaces, and tabs</span></span>

<span data-ttu-id="908d4-132">在 Markdown 中，空白行还表示块的末尾。</span><span class="sxs-lookup"><span data-stu-id="908d4-132">Blank lines also signal the end of a block in Markdown.</span></span> <span data-ttu-id="908d4-133">在不同类型的 Markdown 块之间（例如，在段落和列表或标题之间）应该有一个空白行。</span><span class="sxs-lookup"><span data-stu-id="908d4-133">There should be a single blank between Markdown blocks of different types (for example, between a paragraph and a list or header).</span></span>

<span data-ttu-id="908d4-134">删除重复的空白行。</span><span class="sxs-lookup"><span data-stu-id="908d4-134">Remove duplicate blank lines.</span></span> <span data-ttu-id="908d4-135">多个空白行在 HTML 中呈现为单个空白行，因此多个空白行不起作用。</span><span class="sxs-lookup"><span data-stu-id="908d4-135">Multiple blank lines render as a single blank line in HTML so there is no purpose for multiple blank lines.</span></span> <span data-ttu-id="908d4-136">如果代码块中有多个空行，则会中断代码块。</span><span class="sxs-lookup"><span data-stu-id="908d4-136">Multiple blank lines within a code block break the code block.</span></span>

<span data-ttu-id="908d4-137">删除行尾的多余空格。</span><span class="sxs-lookup"><span data-stu-id="908d4-137">Remove extra spaces at the end of lines.</span></span>

> [!NOTE]
> <span data-ttu-id="908d4-138">间距在 Markdown 中非常重要。</span><span class="sxs-lookup"><span data-stu-id="908d4-138">Spacing is significant in Markdown.</span></span> <span data-ttu-id="908d4-139">始终使用空格而不是硬制表符。</span><span class="sxs-lookup"><span data-stu-id="908d4-139">Always uses spaces instead of hard tabs.</span></span> <span data-ttu-id="908d4-140">尾随空格可更改 Markdown 的呈现方式。</span><span class="sxs-lookup"><span data-stu-id="908d4-140">Trailing spaces can change how Markdown renders.</span></span>

### <a name="titles-and-headings"></a><span data-ttu-id="908d4-141">标题</span><span class="sxs-lookup"><span data-stu-id="908d4-141">Titles and headings</span></span>

<span data-ttu-id="908d4-142">只使用 [ATX 标题][atx]（# 样式，不用 `=` 或 `-` 样式标题）。</span><span class="sxs-lookup"><span data-stu-id="908d4-142">Only use [ATX headings][atx] (# style, as opposed to `=` or `-` style headers).</span></span>

- <span data-ttu-id="908d4-143">使用句首大写形式 - 只对专有名词和标题的首个字母使用大写形式</span><span class="sxs-lookup"><span data-stu-id="908d4-143">Use sentence case - only proper nouns and the first letter of a title or header should be capitalized</span></span>
- <span data-ttu-id="908d4-144">`#` 与标题的首个字母之间必须有一个空格</span><span class="sxs-lookup"><span data-stu-id="908d4-144">There must be a single space between the `#` and the first letter of the heading</span></span>
- <span data-ttu-id="908d4-145">标题前后应该都留有一个空白行</span><span class="sxs-lookup"><span data-stu-id="908d4-145">Headings should be surrounded by a single blank line</span></span>
- <span data-ttu-id="908d4-146">每个文档只有 1 个 H1</span><span class="sxs-lookup"><span data-stu-id="908d4-146">Only one H1 per document</span></span>
- <span data-ttu-id="908d4-147">标题级别应按 1 递增。</span><span class="sxs-lookup"><span data-stu-id="908d4-147">Header levels should increment by one.</span></span> <span data-ttu-id="908d4-148">不要跨级</span><span class="sxs-lookup"><span data-stu-id="908d4-148">Do not skip levels</span></span>
- <span data-ttu-id="908d4-149">不要在标题中使用粗体或其他标记</span><span class="sxs-lookup"><span data-stu-id="908d4-149">Do not use bold or other markup in headers</span></span>

### <a name="limit-line-length-to-100-characters"></a><span data-ttu-id="908d4-150">将行长度限制为 100 个字符</span><span class="sxs-lookup"><span data-stu-id="908d4-150">Limit line length to 100 characters</span></span>

<span data-ttu-id="908d4-151">这适用于概念性文章和 cmdlet 参考。</span><span class="sxs-lookup"><span data-stu-id="908d4-151">This applies to conceptual articles and cmdlet reference.</span></span> <span data-ttu-id="908d4-152">限制行长度可以改进 git diff 和历史记录的可读性。</span><span class="sxs-lookup"><span data-stu-id="908d4-152">Limiting the line length improves the readability of git diffs and history.</span></span> <span data-ttu-id="908d4-153">同时也便于其他作者参与撰写文档。</span><span class="sxs-lookup"><span data-stu-id="908d4-153">It also makes it easier for other writers to make contributions.</span></span>

<span data-ttu-id="908d4-154">在 Visual Studio Code 中使用 [Reflow Markdown][reflow] 扩展可以轻松地重排段落以适应指定的行长度。</span><span class="sxs-lookup"><span data-stu-id="908d4-154">Use the [Reflow Markdown][reflow] extension in Visual Studio Code to easily reflow paragraphs to fit the prescribed line length.</span></span>

<span data-ttu-id="908d4-155">About_topics 限制为 80 个字符。</span><span class="sxs-lookup"><span data-stu-id="908d4-155">About_topics are limited to 80 characters.</span></span> <span data-ttu-id="908d4-156">有关更具体的信息，请参阅[编辑参考文章](./editing-cmdlet-ref.md#formatting-about_-files)。</span><span class="sxs-lookup"><span data-stu-id="908d4-156">For more specific information, see [Editing reference articles](./editing-cmdlet-ref.md#formatting-about_-files).</span></span>

### <a name="lists"></a><span data-ttu-id="908d4-157">列表</span><span class="sxs-lookup"><span data-stu-id="908d4-157">Lists</span></span>

<span data-ttu-id="908d4-158">如果列表包含多个句子或段落，请考虑使用子级标题代替列表。</span><span class="sxs-lookup"><span data-stu-id="908d4-158">If your list contains multiple sentences or paragraphs, consider using a sub-level header rather than a list.</span></span>

<span data-ttu-id="908d4-159">列表前后应该都留有一个空白行。</span><span class="sxs-lookup"><span data-stu-id="908d4-159">List should be surrounded by a single blank line.</span></span>

#### <a name="unordered-lists"></a><span data-ttu-id="908d4-160">未排序列表</span><span class="sxs-lookup"><span data-stu-id="908d4-160">Unordered lists</span></span>

<span data-ttu-id="908d4-161">除非列表项包含多个句子，否则不要以句点结尾。</span><span class="sxs-lookup"><span data-stu-id="908d4-161">Do not end list items with a period unless they contain multiple sentences.</span></span> <span data-ttu-id="908d4-162">对于列表项项目符号，使用连字符 (`-`)。</span><span class="sxs-lookup"><span data-stu-id="908d4-162">Use the hyphen character (`-`) for list item bullets.</span></span> <span data-ttu-id="908d4-163">这样可以避免与使用星号 [`*`] 的粗体或斜体标记混淆。</span><span class="sxs-lookup"><span data-stu-id="908d4-163">This avoids confusion with bold or italic markup that uses the asterisk [`*`].</span></span> <span data-ttu-id="908d4-164">若要在项目符号项下添加段落或其他元素，请插入一个换行符，并使缩进与项目符号后的第一个字符对齐。</span><span class="sxs-lookup"><span data-stu-id="908d4-164">To include a paragraph or other elements under a bullet item, insert a line break and align indentation with the first character after the bullet.</span></span>

<span data-ttu-id="908d4-165">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-165">For example:</span></span>

```markdown
This is a list that contain sub-elements under a bullet item.

- First bullet item

  Sentence explaining the first bullet.

  - Sub-bullet item

    Sentence explaining the sub-bullet.

- Second bullet item
- Third bullet item
```

<span data-ttu-id="908d4-166">这是一个列表，其中包含项目符号项下的子元素。</span><span class="sxs-lookup"><span data-stu-id="908d4-166">This is a list that contains sub-elements under a bullet item.</span></span>

- <span data-ttu-id="908d4-167">第一个项目符号项</span><span class="sxs-lookup"><span data-stu-id="908d4-167">First bullet item</span></span>

  <span data-ttu-id="908d4-168">说明第一个项目符号的句子。</span><span class="sxs-lookup"><span data-stu-id="908d4-168">Sentence explaining the first bullet.</span></span>

  - <span data-ttu-id="908d4-169">子项目符号项</span><span class="sxs-lookup"><span data-stu-id="908d4-169">Sub-bullet item</span></span>

    <span data-ttu-id="908d4-170">说明子项目符号的句子。</span><span class="sxs-lookup"><span data-stu-id="908d4-170">Sentence explaining the sub-bullet.</span></span>

- <span data-ttu-id="908d4-171">第二个项目符号项</span><span class="sxs-lookup"><span data-stu-id="908d4-171">Second bullet item</span></span>
- <span data-ttu-id="908d4-172">第三个项目符号项</span><span class="sxs-lookup"><span data-stu-id="908d4-172">Third bullet item</span></span>

#### <a name="ordered-lists"></a><span data-ttu-id="908d4-173">已排序列表</span><span class="sxs-lookup"><span data-stu-id="908d4-173">Ordered lists</span></span>

<span data-ttu-id="908d4-174">若要在带编号的项下添加段落或其他元素，请使缩进与项编号后的第一个字符对齐。</span><span class="sxs-lookup"><span data-stu-id="908d4-174">To include a paragraph or other elements under a numbered item, align indentation with the first character after the item number.</span></span> <span data-ttu-id="908d4-175">编号列表中的所有项均应使用数字 `1.`，而不是递增每个项的编号数字值。</span><span class="sxs-lookup"><span data-stu-id="908d4-175">All items in a numbered listed should use the number `1.` rather than incrementing each item.</span></span> <span data-ttu-id="908d4-176">Markdown 呈现会自动递增该值。</span><span class="sxs-lookup"><span data-stu-id="908d4-176">Markdown rendering increments the value automatically.</span></span> <span data-ttu-id="908d4-177">这使重新排序项目变得更加容易，并使下级内容的缩进标准化。</span><span class="sxs-lookup"><span data-stu-id="908d4-177">This makes reordering items easier and standardizes the indentation of subordinate content.</span></span>

<span data-ttu-id="908d4-178">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-178">For example:</span></span>

```markdown
1. For the first element, insert a single space after the 1. Long sentences should be
   wrapped to the next line and must line up with the first character after the numbered
   list marker.

   To include a second element (like this one), insert a line break after the first
   and align indentations. The indentation of the second element must line up with
   the first character after the numbered list marker. For single digit items, like
   this one, you indent to column 4. For double digits items, for example item number
   10, you indent to column 5.

1. The next numbered item starts here.
```

<span data-ttu-id="908d4-179">最终呈现的 Markdown 如下：</span><span class="sxs-lookup"><span data-stu-id="908d4-179">The resulting Markdown is rendered as follows:</span></span>

1. <span data-ttu-id="908d4-180">对于第一个元素，在 1 之后插入一个空格。</span><span class="sxs-lookup"><span data-stu-id="908d4-180">For the first element, insert a single space after the 1.</span></span> <span data-ttu-id="908d4-181">长句应换行到下一行，并且必须与编号列表标记后的第一个字符对齐。</span><span class="sxs-lookup"><span data-stu-id="908d4-181">Long sentences should be wrapped to the next line and must line up with the first character after the numbered list marker.</span></span>

   <span data-ttu-id="908d4-182">若要包括第二个元素（如本例所示），请在第一个元素后插入一个换行符，并对齐缩进。</span><span class="sxs-lookup"><span data-stu-id="908d4-182">To include a second element (like this one), insert a line break after the first and align indentations.</span></span> <span data-ttu-id="908d4-183">第二个元素的缩进必须与编号列表标记后的第一个字符对齐。</span><span class="sxs-lookup"><span data-stu-id="908d4-183">The indentation of the second element must line up with the first character after the numbered list marker.</span></span> <span data-ttu-id="908d4-184">对于这样的一位数的项，缩进到第 4 列。</span><span class="sxs-lookup"><span data-stu-id="908d4-184">For single digit items, like this one, you indent to column 4.</span></span> <span data-ttu-id="908d4-185">对于两位数的项（例如项编号 10），缩进到第 5 列。</span><span class="sxs-lookup"><span data-stu-id="908d4-185">For double digits items, for example item number 10, you indent to column 5.</span></span>

1. <span data-ttu-id="908d4-186">下一个带编号的项从此处开始。</span><span class="sxs-lookup"><span data-stu-id="908d4-186">The next numbered item starts here.</span></span>

### <a name="images"></a><span data-ttu-id="908d4-187">映像</span><span class="sxs-lookup"><span data-stu-id="908d4-187">Images</span></span>

<span data-ttu-id="908d4-188">用于添加图像的语法如下：</span><span class="sxs-lookup"><span data-stu-id="908d4-188">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![Introduction](./media/overview/Introduction.png)
```

<span data-ttu-id="908d4-189">其中 `alt text` 是图像的简要说明，`<folder path>` 是图像的相对路径。</span><span class="sxs-lookup"><span data-stu-id="908d4-189">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="908d4-190">必须为视觉障碍人士的屏幕阅读器使用替代文本。</span><span class="sxs-lookup"><span data-stu-id="908d4-190">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="908d4-191">如果存在无法呈现图像的站点 bug，则此方法也非常有用。</span><span class="sxs-lookup"><span data-stu-id="908d4-191">It is also useful in case there is a site bug where the image cannot be rendered.</span></span>

<span data-ttu-id="908d4-192">图像应存储在包含文章的文件夹内的 `media/<article-name>` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="908d4-192">Images should be stored in a `media/<article-name>` folder within the folder containing the article.</span></span>
<span data-ttu-id="908d4-193">不应在文章之间共享图像。</span><span class="sxs-lookup"><span data-stu-id="908d4-193">Images should not be shared between articles.</span></span> <span data-ttu-id="908d4-194">在 `media` 文件夹下创建一个与你的文章的文件名匹配的文件夹。</span><span class="sxs-lookup"><span data-stu-id="908d4-194">Create a folder that matches the filename of your article under the `media` folder.</span></span> <span data-ttu-id="908d4-195">将该文章的图像复制到新文件夹。</span><span class="sxs-lookup"><span data-stu-id="908d4-195">Copy the images for that article to that new folder.</span></span> <span data-ttu-id="908d4-196">如果有多篇文章使用了同一个图像，则每个图像文件夹都必须包含该图像文件的副本。</span><span class="sxs-lookup"><span data-stu-id="908d4-196">If an image is used by multiple articles, each image folder must have a copy of that image file.</span></span> <span data-ttu-id="908d4-197">这种做法可以防止一篇文章中的图像更改影响另一篇文章。</span><span class="sxs-lookup"><span data-stu-id="908d4-197">This practice prevents a change to an image in one article affecting another article.</span></span>

<span data-ttu-id="908d4-198">支持以下图像文件类型：`*.png`、`*.gif`、`*.jpeg`、`*.jpg`、`*.svg`</span><span class="sxs-lookup"><span data-stu-id="908d4-198">The following image file types are supported: `*.png`, `*.gif`, `*.jpeg`, `*.jpg`, `*.svg`</span></span>

### <a name="markdown-extensions-supported-by-open-publishing"></a><span data-ttu-id="908d4-199">开放发布系统支持的 Markdown 扩展</span><span class="sxs-lookup"><span data-stu-id="908d4-199">Markdown extensions supported by Open Publishing</span></span>

<span data-ttu-id="908d4-200">[Microsoft Docs 创作包](/contribute/how-to-write-docs-auth-pack)中包含支持发布系统独有功能的工具。</span><span class="sxs-lookup"><span data-stu-id="908d4-200">The [Microsoft Docs Authoring Pack](/contribute/how-to-write-docs-auth-pack) contains tools that support features unique to our publishing system.</span></span> <span data-ttu-id="908d4-201">“通知”是一种 Markdown 扩展，用于创建在 docs.microsoft.com 上呈现的块引用，这些内容带有可突出显示内容重要性的颜色和图标。</span><span class="sxs-lookup"><span data-stu-id="908d4-201">Alerts are a Markdown extension to create blockquotes that render on docs.microsoft.com with colors and icons that highlight the significance of the content.</span></span> <span data-ttu-id="908d4-202">支持以下通知类型：</span><span class="sxs-lookup"><span data-stu-id="908d4-202">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="908d4-203">这些通知在 docs.microsoft.com 上看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="908d4-203">These alerts look like this on docs.microsoft.com:</span></span>

<span data-ttu-id="908d4-204">“注意”块</span><span class="sxs-lookup"><span data-stu-id="908d4-204">Note block</span></span>

> [!NOTE]
> <span data-ttu-id="908d4-205">即使略读，用户也应注意的信息。</span><span class="sxs-lookup"><span data-stu-id="908d4-205">Information the user should notice even if skimming.</span></span>

<span data-ttu-id="908d4-206">“提示”块</span><span class="sxs-lookup"><span data-stu-id="908d4-206">Tip block</span></span>

> [!TIP]
> <span data-ttu-id="908d4-207">为用户带来更大成就感的可选信息。</span><span class="sxs-lookup"><span data-stu-id="908d4-207">Optional information to help a user be more successful.</span></span>

<span data-ttu-id="908d4-208">“重要说明”块</span><span class="sxs-lookup"><span data-stu-id="908d4-208">Important block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="908d4-209">用户成功所需的基本信息。</span><span class="sxs-lookup"><span data-stu-id="908d4-209">Essential information required for user success.</span></span>

<span data-ttu-id="908d4-210">“小心”块</span><span class="sxs-lookup"><span data-stu-id="908d4-210">Caution block</span></span>

> [!CAUTION]
> <span data-ttu-id="908d4-211">操作的潜在不良后果。</span><span class="sxs-lookup"><span data-stu-id="908d4-211">Negative potential consequences of an action.</span></span>

<span data-ttu-id="908d4-212">“警告”块</span><span class="sxs-lookup"><span data-stu-id="908d4-212">Warning block</span></span>

> [!WARNING]
> <span data-ttu-id="908d4-213">操作的某些危险后果。</span><span class="sxs-lookup"><span data-stu-id="908d4-213">Dangerous certain consequences of an action.</span></span>

### <a name="hyperlinks"></a><span data-ttu-id="908d4-214">超链接</span><span class="sxs-lookup"><span data-stu-id="908d4-214">Hyperlinks</span></span>

- <span data-ttu-id="908d4-215">超链接必须使用 Markdown 语法 `[friendlyname](url-or-path)`</span><span class="sxs-lookup"><span data-stu-id="908d4-215">Hyperlinks must use Markdown syntax `[friendlyname](url-or-path)`</span></span>
- <span data-ttu-id="908d4-216">链接应尽可能使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="908d4-216">Links should be HTTPS when possible.</span></span>
- <span data-ttu-id="908d4-217">链接必须具有友好名称，通常是链接主题的标题</span><span class="sxs-lookup"><span data-stu-id="908d4-217">Links must have a friendly name, usually the title of the linked topic</span></span>
- <span data-ttu-id="908d4-218">底部“相关链接”部分中的所有项都应具有超链接</span><span class="sxs-lookup"><span data-stu-id="908d4-218">All items in the "related links" section at the bottom should be hyperlinked</span></span>
- <span data-ttu-id="908d4-219">不要在超链接的括号内使用反引号、粗体或其他标记。</span><span class="sxs-lookup"><span data-stu-id="908d4-219">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>
- <span data-ttu-id="908d4-220">涉及特定 URI 时，可以使用裸 URL。</span><span class="sxs-lookup"><span data-stu-id="908d4-220">Bare URLs may be used when you are talking about a specific URI.</span></span> <span data-ttu-id="908d4-221">必须用反引号引住此 URI。</span><span class="sxs-lookup"><span data-stu-id="908d4-221">The URI must be enclosed in backticks.</span></span> <span data-ttu-id="908d4-222">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-222">For example:</span></span>

  ```markdown
  By default, if you do not specify this parameter, the DMTF standard resource URI
  `http://schemas.dmtf.org/wbem/wscim/1/cim-schema/2/` is used and the class name is appended to it.
  ```

#### <a name="linking-to-other-content"></a><span data-ttu-id="908d4-223">链接到其他内容</span><span class="sxs-lookup"><span data-stu-id="908d4-223">Linking to other content</span></span>

<span data-ttu-id="908d4-224">发布系统支持两种类型的超链接：</span><span class="sxs-lookup"><span data-stu-id="908d4-224">There are two types of hyperlinks supported by the publishing system:</span></span>

<span data-ttu-id="908d4-225">URL 链接可以是相对于 docs.microsoft.com 根的 URL 路径  。</span><span class="sxs-lookup"><span data-stu-id="908d4-225">A **URL link** can be a URL path that is relative to the root of docs.microsoft.com.</span></span> <span data-ttu-id="908d4-226">也可以是包含完整 URL 语法的绝对 URL。</span><span class="sxs-lookup"><span data-stu-id="908d4-226">Or an absolute URL that include the full URL syntax.</span></span> <span data-ttu-id="908d4-227">例如： `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span><span class="sxs-lookup"><span data-stu-id="908d4-227">For example: `https:/github.com/MicrosoftDocs/PowerShell-Docs`</span></span>

- <span data-ttu-id="908d4-228">链接到 PowerShell-Docs 之外的内容时，或在 PowerShell-docs 内的 cmdlet 参考与概念性文章之间链接时，请使用 URL 链接。创建相对链接的最简单方法是从浏览器复制 URL，然后从粘贴到 Markdown 的值中删除 `https://docs.microsoft.com/en-us`。</span><span class="sxs-lookup"><span data-stu-id="908d4-228">Use URL links when linking to content outside of PowerShell-Docs or between cmdlet reference and conceptual articles within PowerShell-docs. The simplest way to create a relative link is to copy the URL from your browser then remove `https://docs.microsoft.com/en-us` from the value you paste into markdown.</span></span>
- <span data-ttu-id="908d4-229">不要在 Microsoft 属性的 URL 中包含区域设置（例如，</span><span class="sxs-lookup"><span data-stu-id="908d4-229">Do not include locales in URLs on Microsoft properties (eg.</span></span> <span data-ttu-id="908d4-230">从 URL 中删除 `/en-us`）。</span><span class="sxs-lookup"><span data-stu-id="908d4-230">remove `/en-us` from URL).</span></span>
- <span data-ttu-id="908d4-231">除非需要链接到这样的特定版本，否则请从 URL 中删除任何不必要的查询参数。</span><span class="sxs-lookup"><span data-stu-id="908d4-231">Remove any unnecessary query parameters from the URL unless you need to link to a specific version of an article.</span></span> <span data-ttu-id="908d4-232">示例：</span><span class="sxs-lookup"><span data-stu-id="908d4-232">Examples:</span></span>
  - <span data-ttu-id="908d4-233">`?view=powershell-5.1` - 用于链接到特定版本的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="908d4-233">`?view=powershell-5.1` - this is used to link to a specific version of PowerShell</span></span>
  - <span data-ttu-id="908d4-234">`?redirectedfrom=MSDN` - 当你从旧文章重定向到新位置时，会将它添加到 URL 中</span><span class="sxs-lookup"><span data-stu-id="908d4-234">`?redirectedfrom=MSDN` - this is added to the URL when you get redirected from an old article to its new location</span></span>
- <span data-ttu-id="908d4-235">指向外部网站的所有 URL 都应使用 HTTPS（除非对目标站点无效）。</span><span class="sxs-lookup"><span data-stu-id="908d4-235">All URLs to external websites should use HTTPS unless that is not valid for the target site.</span></span>

<span data-ttu-id="908d4-236">从一个参考文章链接到另一个参考文章，或从一个概念性文章链接到另一个概念性文章时，使用文件链接  。</span><span class="sxs-lookup"><span data-stu-id="908d4-236">A **file link** is used to link from one reference article to another, or from one conceptual article to another.</span></span> <span data-ttu-id="908d4-237">如果需要链接到特定版本的 PowerShell 的参考文章，必须使用 URL 链接。</span><span class="sxs-lookup"><span data-stu-id="908d4-237">If you need to link to a reference article for a specific version of PowerShell, then you must use a URL link.</span></span>

- <span data-ttu-id="908d4-238">文件链接包含相对文件路径（例如：`../folder/file.md`）</span><span class="sxs-lookup"><span data-stu-id="908d4-238">File links contain a relative file path (for example: `../folder/file.md`)</span></span>
- <span data-ttu-id="908d4-239">所有文件路径都使用正斜杠 (`/`) 字符</span><span class="sxs-lookup"><span data-stu-id="908d4-239">All file paths use forward-slash (`/`) characters</span></span>

<span data-ttu-id="908d4-240">URL 和文件链接都允许深层链接。</span><span class="sxs-lookup"><span data-stu-id="908d4-240">Deep linking is allowed on both URL and file links.</span></span> <span data-ttu-id="908d4-241">将定位点添加到目标路径的末尾。</span><span class="sxs-lookup"><span data-stu-id="908d4-241">Add the anchor to the end of the target path.</span></span>
<span data-ttu-id="908d4-242">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-242">For example:</span></span>

- `[about_Splatting](about_Splatting.md#splatting-with-arrays)`
- `[custom key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)`

<span data-ttu-id="908d4-243">有关详细信息，请参阅[在文档中使用链接](https://docs.microsoft.com/contribute/how-to-write-links)。</span><span class="sxs-lookup"><span data-stu-id="908d4-243">For more information, see [Use links in documentation](https://docs.microsoft.com/contribute/how-to-write-links).</span></span>

## <a name="formatting-command-syntax-elements"></a><span data-ttu-id="908d4-244">设置命令语法元素格式</span><span class="sxs-lookup"><span data-stu-id="908d4-244">Formatting command syntax elements</span></span>

- <span data-ttu-id="908d4-245">始终对 cmdlet 和参数使用全名。</span><span class="sxs-lookup"><span data-stu-id="908d4-245">Always use the full name for cmdlets and parameters.</span></span> <span data-ttu-id="908d4-246">避免使用别名，除非专门演示别名。</span><span class="sxs-lookup"><span data-stu-id="908d4-246">Avoid using aliases unless you are specifically demonstrating the alias.</span></span>

- <span data-ttu-id="908d4-247">属性、参数、对象、类型名称、类名、类方法应为粗体形式  。</span><span class="sxs-lookup"><span data-stu-id="908d4-247">Property, parameter, object, type names, class names, class methods should be **bold**.</span></span>
  - <span data-ttu-id="908d4-248">应使用反引号 (`` ` ``) 将属性和参数值引起来。</span><span class="sxs-lookup"><span data-stu-id="908d4-248">Property and parameter values should be wrapped in backticks (`` ` ``).</span></span>
  - <span data-ttu-id="908d4-249">使用方括号样式指代类型时，请使用反引号。</span><span class="sxs-lookup"><span data-stu-id="908d4-249">When referring to types using the bracketed style, use backticks.</span></span> <span data-ttu-id="908d4-250">例如： `[System.Io.FileInfo]`</span><span class="sxs-lookup"><span data-stu-id="908d4-250">For example: `[System.Io.FileInfo]`</span></span>

- <span data-ttu-id="908d4-251">应使用反引号 (`` ` ``) 字符将语言关键字、cmdlet 名称、函数、变量、本机 EXE、文件路径和内联语法示例引起来。</span><span class="sxs-lookup"><span data-stu-id="908d4-251">Language keywords, cmdlet names, functions, variables, native EXEs, file paths, and inline syntax examples should be wrapped in backtick (`` ` ``) characters.</span></span>

  <span data-ttu-id="908d4-252">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-252">For example:</span></span>

  ~~~markdown
  The following code uses `Get-ChildItem` to list the contents of `C:\Windows` and assigns
  the output to the `$files` variable.

  ```powershell
  $files = Get-ChildItem C:\Windows
  ```
  ~~~

  - <span data-ttu-id="908d4-253">通过名称引用参数时，名称应为粗体  。</span><span class="sxs-lookup"><span data-stu-id="908d4-253">When referring to a parameter by name, the name should be **bold**.</span></span> <span data-ttu-id="908d4-254">在说明如何使用带有连字符前缀的参数时，应使用反引号将参数引起来。</span><span class="sxs-lookup"><span data-stu-id="908d4-254">When illustrating the use of a parameter with the hyphen prefix, the parameter should be wrapped in backticks.</span></span> <span data-ttu-id="908d4-255">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-255">For example:</span></span>

    ```markdown
    The parameter's name is **Name**, but it is typed as `-Name` when used on the command
    line as a parameter.
    ```

  - <span data-ttu-id="908d4-256">显示外部命令的示例用法时，应使用反引号将示例引起来。</span><span class="sxs-lookup"><span data-stu-id="908d4-256">When showing example usage of an external command, the example should be wrapped in backticks.</span></span>
    <span data-ttu-id="908d4-257">始终在本机命令中包含文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="908d4-257">Always include the file extension in the native command.</span></span> <span data-ttu-id="908d4-258">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-258">For example:</span></span>

    ```markdown
    To start the spooler service on a remote computer named DC01, you type `sc.exe \\DC01 start spooler`.
    ```

    <span data-ttu-id="908d4-259">包括文件扩展名可确保根据 PowerShell 的命令优先级执行正确的命令。</span><span class="sxs-lookup"><span data-stu-id="908d4-259">Including the file extension ensures that the correct command is executed according PowerShell's command precedence.</span></span>

- <span data-ttu-id="908d4-260">在撰写概念性文章（而不是参考内容）时，应将 cmdlet 名称的第一个实例超链接到 cmdlet 文档。</span><span class="sxs-lookup"><span data-stu-id="908d4-260">When writing a conceptual article (as opposed to reference content), the first instance of a cmdlet name should be hyperlinked to the cmdlet documentation.</span></span> <span data-ttu-id="908d4-261">不要在超链接的括号内使用反引号、粗体或其他标记。</span><span class="sxs-lookup"><span data-stu-id="908d4-261">Do not use backticks, bold, or other markup inside the brackets of a hyperlink.</span></span>

  <span data-ttu-id="908d4-262">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-262">For example:</span></span>

  ```markdown
  This [Write-Host](/powershell/module/Microsoft.PowerShell.Utility/Write-Host) cmdlet
  uses the **Object** parameter to ...
  ```

  <span data-ttu-id="908d4-263">有关详细信息，请参阅本文中的[超链接](#hyperlinks)一节。</span><span class="sxs-lookup"><span data-stu-id="908d4-263">For more information, see [Hyperlinks](#hyperlinks) section of this article.</span></span>

## <a name="markdown-for-code-samples"></a><span data-ttu-id="908d4-264">Markdown 代码示例</span><span class="sxs-lookup"><span data-stu-id="908d4-264">Markdown for code samples</span></span>

<span data-ttu-id="908d4-265">Markdown 支持两种不同的代码样式：</span><span class="sxs-lookup"><span data-stu-id="908d4-265">Markdown supports two different code styles:</span></span>

- <span data-ttu-id="908d4-266">代码范围（内联）- 用单个反引号 (`` ` ``) 字符标记  。</span><span class="sxs-lookup"><span data-stu-id="908d4-266">**Code spans (inline)** - marked by a single backtick (`` ` ``) character.</span></span> <span data-ttu-id="908d4-267">在段落中使用，而不是作为独立的块使用。</span><span class="sxs-lookup"><span data-stu-id="908d4-267">Used within a paragraph rather than as a standalone block.</span></span>
- <span data-ttu-id="908d4-268">代码块 - 使用三个反引号 (`` ``` ``) 字符串引起来的多行代码块  。</span><span class="sxs-lookup"><span data-stu-id="908d4-268">**Code blocks** - a multi-line block surrounded by triple-backtick (`` ``` ``) strings.</span></span> <span data-ttu-id="908d4-269">代码块的反引号后面还可能跟有一个语言标签。</span><span class="sxs-lookup"><span data-stu-id="908d4-269">Code blocks may also have a language label following the backticks.</span></span> <span data-ttu-id="908d4-270">语言标签使代码块内容的语法突出显示。</span><span class="sxs-lookup"><span data-stu-id="908d4-270">The language label enables syntax highlighting for the contents of the code block.</span></span>

<span data-ttu-id="908d4-271">所有代码块都应包含在代码隔离区中。</span><span class="sxs-lookup"><span data-stu-id="908d4-271">All code blocks should be contained in a code fence.</span></span> <span data-ttu-id="908d4-272">不要对代码块使用缩进。</span><span class="sxs-lookup"><span data-stu-id="908d4-272">Never use indentation for code blocks.</span></span> <span data-ttu-id="908d4-273">Markdown 允许使用此模式，但这样可能会出现问题，应避免使用。</span><span class="sxs-lookup"><span data-stu-id="908d4-273">Markdown allows this pattern but it can be problematic and should be avoided.</span></span>

<span data-ttu-id="908d4-274">代码块是由三个反引号 (`` ``` ``) 代码隔离区包围的一个或多个代码行。</span><span class="sxs-lookup"><span data-stu-id="908d4-274">A code block is one or more lines of code surrounded by a triple-backtick (`` ``` ``) code fence.</span></span>
<span data-ttu-id="908d4-275">代码隔离区标记必须位于代码示例前后其自己的行上。</span><span class="sxs-lookup"><span data-stu-id="908d4-275">The code fence markers must be on their own line before and after the code sample.</span></span> <span data-ttu-id="908d4-276">代码块开头的标记可能具有可选的语言标签。</span><span class="sxs-lookup"><span data-stu-id="908d4-276">The marker at the start of the code block may have an optional language label.</span></span> <span data-ttu-id="908d4-277">Microsoft 的开放发布系统 (OPS) 使用语言标签来支持语法突出显示功能。</span><span class="sxs-lookup"><span data-stu-id="908d4-277">Microsoft's Open Publishing System (OPS) uses the language label to support the syntax highlighting feature.</span></span>

<span data-ttu-id="908d4-278">有关支持的语言标记的完整列表，请参阅集中式参与者指南中的[隔离代码块](/contribute/code-in-docs#fenced-code-blocks)。</span><span class="sxs-lookup"><span data-stu-id="908d4-278">For a full list of supported language tags, see [Fenced code blocks](/contribute/code-in-docs#fenced-code-blocks) in the centralized contributor guide.</span></span>

<span data-ttu-id="908d4-279">OPS 还添加了可将代码块的内容复制到剪贴板的“复制”按钮  。</span><span class="sxs-lookup"><span data-stu-id="908d4-279">OPS also adds a **Copy** button that copies the contents of the code block to the clipboard.</span></span> <span data-ttu-id="908d4-280">这样，你就可以将代码快速粘贴到脚本中，以测试代码示例。</span><span class="sxs-lookup"><span data-stu-id="908d4-280">This allows you to quickly paste the code into a script to test the code sample.</span></span> <span data-ttu-id="908d4-281">但是，并非文档中的所有示例都计划照原样运行。</span><span class="sxs-lookup"><span data-stu-id="908d4-281">However, not all examples in our documentation are intended to be run as-is.</span></span> <span data-ttu-id="908d4-282">一些代码块是 PowerShell 概念的简单说明。</span><span class="sxs-lookup"><span data-stu-id="908d4-282">Some code blocks are simple illustrations of a PowerShell concept.</span></span>

<span data-ttu-id="908d4-283">文档中使用三种类型的代码块：</span><span class="sxs-lookup"><span data-stu-id="908d4-283">There are three types code blocks used in our documentation:</span></span>

1. <span data-ttu-id="908d4-284">语法块</span><span class="sxs-lookup"><span data-stu-id="908d4-284">Syntax blocks</span></span>
1. <span data-ttu-id="908d4-285">说明性示例</span><span class="sxs-lookup"><span data-stu-id="908d4-285">Illustrative examples</span></span>
1. <span data-ttu-id="908d4-286">可执行示例</span><span class="sxs-lookup"><span data-stu-id="908d4-286">Executable examples</span></span>

### <a name="syntax-code-blocks"></a><span data-ttu-id="908d4-287">语法代码块</span><span class="sxs-lookup"><span data-stu-id="908d4-287">Syntax code blocks</span></span>

<span data-ttu-id="908d4-288">语法代码块用于说明命令的语法结构。</span><span class="sxs-lookup"><span data-stu-id="908d4-288">Syntax code blocks are used to describe the syntactic structure of a command.</span></span> <span data-ttu-id="908d4-289">不要对代码隔离区使用语言标记。</span><span class="sxs-lookup"><span data-stu-id="908d4-289">Do not use a language tag on the code fence.</span></span> <span data-ttu-id="908d4-290">此示例演示 `Get-Command` cmdlet 所有可能的参数。</span><span class="sxs-lookup"><span data-stu-id="908d4-290">This example illustrates all the possible parameters of the `Get-Command` cmdlet.</span></span>

~~~markdown
```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
  [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax]
  [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
  [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```
~~~

<span data-ttu-id="908d4-291">此示例以通用术语描述 `for` 语句：</span><span class="sxs-lookup"><span data-stu-id="908d4-291">This example describes the `for` statement in generalized terms:</span></span>

~~~markdown
```
for (<init>; <condition>; <repeat>)
{<statement list>}
```
~~~

### <a name="illustrative-examples"></a><span data-ttu-id="908d4-292">说明性示例</span><span class="sxs-lookup"><span data-stu-id="908d4-292">Illustrative examples</span></span>

<span data-ttu-id="908d4-293">说明性示例用于解释 PowerShell 概念。</span><span class="sxs-lookup"><span data-stu-id="908d4-293">Illustrative examples are used to explain a PowerShell concept.</span></span> <span data-ttu-id="908d4-294">不应将它们复制到剪贴板来执行。</span><span class="sxs-lookup"><span data-stu-id="908d4-294">They are not meant to be copied to the clipboard for execution.</span></span> <span data-ttu-id="908d4-295">这些示例最常用于易于键入且易于理解的简单示例。</span><span class="sxs-lookup"><span data-stu-id="908d4-295">These are most commonly used for simple examples that are easy to type and easy to understand.</span></span> <span data-ttu-id="908d4-296">代码块可以包括 PowerShell 提示符和示例输出。</span><span class="sxs-lookup"><span data-stu-id="908d4-296">The code block can include the PowerShell prompt and example output.</span></span>

<span data-ttu-id="908d4-297">以下简单示例展示了 PowerShell 比较运算符。</span><span class="sxs-lookup"><span data-stu-id="908d4-297">Here is a simple example illustrating the PowerShell comparison operators.</span></span> <span data-ttu-id="908d4-298">在这种情况下，我们不希望读者复制并运行此示例。</span><span class="sxs-lookup"><span data-stu-id="908d4-298">In this case, we don't intend the reader to copy and run this example.</span></span>

~~~markdown
```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS>  1,2,3 -eq 2
2

PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```
~~~

### <a name="executable-examples"></a><span data-ttu-id="908d4-299">可执行示例</span><span class="sxs-lookup"><span data-stu-id="908d4-299">Executable examples</span></span>

<span data-ttu-id="908d4-300">复杂的示例或计划用于复制和执行的示例应使用以下块样式标记：</span><span class="sxs-lookup"><span data-stu-id="908d4-300">Complex examples, or examples that are intended to be copied and executed, should use the following block-style markup:</span></span>

~~~markdown
```powershell
<Your PowerShell code goes here>
```
~~~

<span data-ttu-id="908d4-301">PowerShell 命令显示的输出应包含在 Output 代码块中，以防止语法突出显示  。</span><span class="sxs-lookup"><span data-stu-id="908d4-301">The output displayed by PowerShell commands should be enclosed in an **Output** code block to prevent syntax highlighting.</span></span> <span data-ttu-id="908d4-302">例如：</span><span class="sxs-lookup"><span data-stu-id="908d4-302">For example:</span></span>

~~~markdown
```powershell
Get-Command -Module Microsoft.PowerShell.Security
```

```Output
CommandType  Name                        Version    Source
-----------  ----                        -------    ------
Cmdlet       ConvertFrom-SecureString    3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       ConvertTo-SecureString      3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-CmsMessage              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-Credential              3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Get-PfxCertificate          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       New-FileCatalog             3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Protect-CmsMessage          3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-Acl                     3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-AuthenticodeSignature   3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Set-ExecutionPolicy         3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Test-FileCatalog            3.0.0.0    Microsoft.PowerShell.Security
Cmdlet       Unprotect-CmsMessage        3.0.0.0    Microsoft.PowerShell.Security
```
~~~

<span data-ttu-id="908d4-303">Output 代码标签不是语法突出显示系统支持的一种正式“语言”  。</span><span class="sxs-lookup"><span data-stu-id="908d4-303">The **Output** code label is not an official "language" supported by the syntax highlighting system.</span></span>
<span data-ttu-id="908d4-304">但是，此标签非常有用，因为 OPS 会将“Output”标签添加到网页上的代码框框架中。</span><span class="sxs-lookup"><span data-stu-id="908d4-304">However, this label is useful because OPS adds the "Output" label to the code box frame on the web page.</span></span> <span data-ttu-id="908d4-305">“Output”代码框不会突出显示语法。</span><span class="sxs-lookup"><span data-stu-id="908d4-305">The "Output" code box has no syntax highlighting.</span></span>

## <a name="coding-style-rules"></a><span data-ttu-id="908d4-306">编码样式规则</span><span class="sxs-lookup"><span data-stu-id="908d4-306">Coding style rules</span></span>

### <a name="avoid-line-continuation-in-code-samples"></a><span data-ttu-id="908d4-307">避免在代码示例中出现续行符</span><span class="sxs-lookup"><span data-stu-id="908d4-307">Avoid line continuation in code samples</span></span>

<span data-ttu-id="908d4-308">避免在 PowerShell 代码示例中使用续行符 (`` ` ``)。</span><span class="sxs-lookup"><span data-stu-id="908d4-308">Avoid using line continuation characters (`` ` ``) in PowerShell code examples.</span></span> <span data-ttu-id="908d4-309">如果行尾出现多余的空格，会很难看到续行符，并且可能会引发问题。</span><span class="sxs-lookup"><span data-stu-id="908d4-309">These are hard to see and can cause problems if there are extra spaces at the end of the line.</span></span>

- <span data-ttu-id="908d4-310">使用 PowerShell 展开来缩短包含大量参数的 cmdlet 的行长度。</span><span class="sxs-lookup"><span data-stu-id="908d4-310">Use PowerShell splatting to reduce line length for cmdlets that have a lot of parameters.</span></span>
- <span data-ttu-id="908d4-311">利用 PowerShell 的自然换行机会，如竖线 (`|`) 字符、左大括号、圆括号和方括号之后。</span><span class="sxs-lookup"><span data-stu-id="908d4-311">Take advantage of PowerShell's natural line break opportunities, like after pipe (`|`) characters, opening braces, parentheses, and brackets.</span></span>

### <a name="avoid-using-powershell-prompts-in-examples"></a><span data-ttu-id="908d4-312">避免在示例中使用 PowerShell 提示</span><span class="sxs-lookup"><span data-stu-id="908d4-312">Avoid using PowerShell prompts in examples</span></span>

<span data-ttu-id="908d4-313">不建议使用提示字符串，应该将其限制在旨在说明命令行用法的方案。</span><span class="sxs-lookup"><span data-stu-id="908d4-313">Use of the prompt string is discouraged and should be limited to scenarios that are meant to illustrate command line usage.</span></span> <span data-ttu-id="908d4-314">对于其中大多数示例，提示字符串应为 `PS>`。</span><span class="sxs-lookup"><span data-stu-id="908d4-314">For most of these examples, the prompt string should be `PS>`.</span></span> <span data-ttu-id="908d4-315">此提示与特定于 OS 的指示器无关。</span><span class="sxs-lookup"><span data-stu-id="908d4-315">This prompt is independent of OS-specific indicators.</span></span>

<span data-ttu-id="908d4-316">如果示例演示改变提示的命令，或显示的路径对所演示的方案非常重要时，则需要提示。</span><span class="sxs-lookup"><span data-stu-id="908d4-316">Prompts are required for examples that illustrate commands that alter the prompt or when the path displayed is significant to the scenario being illustrated.</span></span> <span data-ttu-id="908d4-317">下面的示例演示使用注册表提供程序时提示的变化。</span><span class="sxs-lookup"><span data-stu-id="908d4-317">The following example illustrates how the prompt changes when using the Registry provider.</span></span>

```powershell
PS C:\> cd HKCU:\System\
PS HKCU:\System\> dir

    Hive: HKEY_CURRENT_USER\System

Name                   Property
----                   --------
CurrentControlSet
GameConfigStore        GameDVR_Enabled                       : 1
                       GameDVR_FSEBehaviorMode               : 2
                       Win32_AutoGameModeDefaultProfile      : {2, 0, 1, 0...}
                       Win32_GameModeRelatedProcesses        : {1, 0, 1, 0...}
                       GameDVR_HonorUserFSEBehaviorMode      : 0
                       GameDVR_DXGIHonorFSEWindowsCompatible : 0
```

### <a name="do-not-use-aliases-in-examples"></a><span data-ttu-id="908d4-318">请勿在示例中使用别名</span><span class="sxs-lookup"><span data-stu-id="908d4-318">Do not use aliases in examples</span></span>

<span data-ttu-id="908d4-319">应始终使用所有 cmdlet 和参数的全名，除非专门讨论别名。</span><span class="sxs-lookup"><span data-stu-id="908d4-319">You should always use the full name of all cmdlets and parameters unless you are specifically talking about the alias.</span></span> <span data-ttu-id="908d4-320">Cmdlet 和参数名称必须采用正确的 Pascal 大小写格式。</span><span class="sxs-lookup"><span data-stu-id="908d4-320">Cmdlet and parameter names must use the proper Pascal-cased names.</span></span>

### <a name="using-parameters-in-examples"></a><span data-ttu-id="908d4-321">在示例中使用参数</span><span class="sxs-lookup"><span data-stu-id="908d4-321">Using parameters in examples</span></span>

<span data-ttu-id="908d4-322">避免使用位置参数。</span><span class="sxs-lookup"><span data-stu-id="908d4-322">Avoid using positional parameters.</span></span> <span data-ttu-id="908d4-323">通常，即使是位置参数，也应始终在示例中包含参数名称。</span><span class="sxs-lookup"><span data-stu-id="908d4-323">In general, you should always include the parameter name in an example, even if the parameter is positional.</span></span> <span data-ttu-id="908d4-324">这样可以减少在示例中产生混淆的可能性。</span><span class="sxs-lookup"><span data-stu-id="908d4-324">This reduces the chance of confusion in your examples.</span></span>

## <a name="next-steps"></a><span data-ttu-id="908d4-325">后续步骤</span><span class="sxs-lookup"><span data-stu-id="908d4-325">Next steps</span></span>

[<span data-ttu-id="908d4-326">编辑 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="908d4-326">Editing cmdlet reference</span></span>](editing-cmdlet-ref.md)

<!-- External URLs -->
[platyPS]: https://github.com/PowerShell/platyPS
[markdig]: https://github.com/lunet-io/markdig
[CommonMark]: https://spec.commonmark.org/
[atx]: https://github.github.com/gfm/#atx-headings
[pascal-case]: https://en.wikipedia.org/wiki/PascalCase
[reflow]: https://marketplace.visualstudio.com/items?itemName=marvhen.reflow-markdown
