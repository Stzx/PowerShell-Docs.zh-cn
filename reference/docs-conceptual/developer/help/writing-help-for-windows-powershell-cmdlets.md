---
ms.date: 09/13/2016
ms.topic: reference
title: 编写针对 PowerShell Cmdlet 的帮助
description: 编写针对 PowerShell Cmdlet 的帮助
ms.openlocfilehash: b1deaa5998dbc54add93764db785d57afcc0a779
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658100"
---
# <a name="writing-help-for-powershell-cmdlets"></a><span data-ttu-id="16d6e-103">编写针对 PowerShell Cmdlet 的帮助</span><span class="sxs-lookup"><span data-stu-id="16d6e-103">Writing Help for PowerShell Cmdlets</span></span>

<span data-ttu-id="16d6e-104">PowerShell cmdlet 非常有用，但除非帮助主题清楚地说明了 cmdlet 的作用以及使用方式，否则 cmdlet 可能不会被使用，甚至更糟糕的是，它可能会使用户不快。</span><span class="sxs-lookup"><span data-stu-id="16d6e-104">PowerShell cmdlets can be useful, but unless your Help topics clearly explain what the cmdlet does and how to use it, the cmdlet may not get used or, even worse, it might frustrate users.</span></span> <span data-ttu-id="16d6e-105">基于 XML 的 cmdlet 帮助文件格式增强了一致性，但有很大的帮助需要进一步的帮助。</span><span class="sxs-lookup"><span data-stu-id="16d6e-105">The XML-based cmdlet Help file format enhances consistency, but great help requires much more.</span></span>

<span data-ttu-id="16d6e-106">如果你从未编写过 cmdlet 帮助，请查看以下准则。</span><span class="sxs-lookup"><span data-stu-id="16d6e-106">If you have never written cmdlet Help, review the following guidelines.</span></span> <span data-ttu-id="16d6e-107">以下部分介绍了创作 cmdlet 帮助主题所需的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="16d6e-107">The XML schema required to author the cmdlet Help topic is described in the following section.</span></span> <span data-ttu-id="16d6e-108">首先 [创建 Cmdlet 帮助文件](./how-to-create-the-cmdlet-help-file.md)。</span><span class="sxs-lookup"><span data-stu-id="16d6e-108">Start with [Creating the Cmdlet Help File](./how-to-create-the-cmdlet-help-file.md).</span></span> <span data-ttu-id="16d6e-109">该主题包括顶级 XML 节点的说明。</span><span class="sxs-lookup"><span data-stu-id="16d6e-109">That topic includes a description of the top-level XML nodes.</span></span>

## <a name="writing-guidelines-for-cmdlet-help"></a><span data-ttu-id="16d6e-110">编写 Cmdlet 帮助指南</span><span class="sxs-lookup"><span data-stu-id="16d6e-110">Writing Guidelines for Cmdlet Help</span></span>

### <a name="write-well"></a><span data-ttu-id="16d6e-111">编写良好</span><span class="sxs-lookup"><span data-stu-id="16d6e-111">Write well</span></span>

<span data-ttu-id="16d6e-112">任何内容都不会替代编写良好的主题。</span><span class="sxs-lookup"><span data-stu-id="16d6e-112">Nothing replaces a well-written topic.</span></span> <span data-ttu-id="16d6e-113">如果您不是专业作者，请找到编写器或编辑器来帮助您。</span><span class="sxs-lookup"><span data-stu-id="16d6e-113">If you are not a professional writer, find a writer or editor to help you.</span></span> <span data-ttu-id="16d6e-114">另一种方法是将帮助文本复制到 Microsoft Word 中，并使用语法和拼写检查来改善您的工作。</span><span class="sxs-lookup"><span data-stu-id="16d6e-114">Another alternative is to copy your Help text into Microsoft Word and use the grammar and spelling checks to improve your work.</span></span>

### <a name="write-simply"></a><span data-ttu-id="16d6e-115">简单编写</span><span class="sxs-lookup"><span data-stu-id="16d6e-115">Write simply</span></span>

<span data-ttu-id="16d6e-116">使用简单的单词和短语。</span><span class="sxs-lookup"><span data-stu-id="16d6e-116">Use simple words and phrases.</span></span> <span data-ttu-id="16d6e-117">避免行业术语。</span><span class="sxs-lookup"><span data-stu-id="16d6e-117">Avoid jargon.</span></span> <span data-ttu-id="16d6e-118">请注意，许多读者只配有外文字典和帮助主题。</span><span class="sxs-lookup"><span data-stu-id="16d6e-118">Consider that many readers are equipped only with a foreign-language dictionary and your Help topic.</span></span>

### <a name="write-consistently"></a><span data-ttu-id="16d6e-119">一致性写入</span><span class="sxs-lookup"><span data-stu-id="16d6e-119">Write consistently</span></span>

<span data-ttu-id="16d6e-120">相关 cmdlet 的帮助应类似 (例如，x-blade 和集-x) 。</span><span class="sxs-lookup"><span data-stu-id="16d6e-120">Help for related cmdlets should be similar (for example, get-x and set-x).</span></span> <span data-ttu-id="16d6e-121">为标准参数（如 **Force** 和 **InputObject**）使用标准说明。</span><span class="sxs-lookup"><span data-stu-id="16d6e-121">Use the standard descriptions for standard parameters, like **Force** and **InputObject**.</span></span> <span data-ttu-id="16d6e-122"> (将其从核心 cmdlet 的帮助中复制。 ) 使用标准术语。</span><span class="sxs-lookup"><span data-stu-id="16d6e-122">(Copy them from Help for the core cmdlets.) Use standard terms.</span></span> <span data-ttu-id="16d6e-123">例如，使用 "参数" 而不是 "参数"，并使用 "cmdlet" 而不是 "命令" 或 "命令-let"。</span><span class="sxs-lookup"><span data-stu-id="16d6e-123">For example, use "parameter", not "argument", and use "cmdlet" not "command" or "command-let."</span></span>

### <a name="start-the-synopsis-with-a-verb"></a><span data-ttu-id="16d6e-124">使用谓词启动摘要</span><span class="sxs-lookup"><span data-stu-id="16d6e-124">Start the synopsis with a verb</span></span>

<span data-ttu-id="16d6e-125">"摘要" 字段向用户通知 cmdlet 的功能，而不是它的作用或工作方式。</span><span class="sxs-lookup"><span data-stu-id="16d6e-125">The synopsis field informs the user what the cmdlet does, not what it is or how it works.</span></span> <span data-ttu-id="16d6e-126">谓词创建一个基于任务的语句，该语句通知用户此 cmdlet 是否满足其要求。</span><span class="sxs-lookup"><span data-stu-id="16d6e-126">Verbs create a task-based statement that informs users if this cmdlet meets their requirements.</span></span> <span data-ttu-id="16d6e-127">使用简单的谓词，例如 "get"、"create" 和 "change"。</span><span class="sxs-lookup"><span data-stu-id="16d6e-127">Use simple verbs like "get", "create", and "change."</span></span> <span data-ttu-id="16d6e-128">避免出现 "set"，这可能是个含糊的词，如 "修改"。</span><span class="sxs-lookup"><span data-stu-id="16d6e-128">Avoid "set", which can be vague and fancy words like "modify".</span></span>

### <a name="focus-on-objects"></a><span data-ttu-id="16d6e-129">专注于对象</span><span class="sxs-lookup"><span data-stu-id="16d6e-129">Focus on objects</span></span>

<span data-ttu-id="16d6e-130">大多数 "get" cmdlet 显示某些内容，但其主要功能是获取对象。</span><span class="sxs-lookup"><span data-stu-id="16d6e-130">Most "get" cmdlets display something, but their primary function is to get an object.</span></span> <span data-ttu-id="16d6e-131">在您的帮助中，将重点放在对象上，以便用户理解默认显示为多个，并可使用以不同方式为其检索的对象的方法和属性。</span><span class="sxs-lookup"><span data-stu-id="16d6e-131">In your Help, focus on the object, so that users understand that the default display is one of many, and that they can use the methods and properties of the object that you retrieved for them in different ways.</span></span>

### <a name="write-detailed-descriptions"></a><span data-ttu-id="16d6e-132">编写详细说明</span><span class="sxs-lookup"><span data-stu-id="16d6e-132">Write detailed descriptions</span></span>

<span data-ttu-id="16d6e-133">简要列出 cmdlet 可在详细说明中执行的所有操作。</span><span class="sxs-lookup"><span data-stu-id="16d6e-133">Briefly list everything that the cmdlet can do in the detailed description.</span></span> <span data-ttu-id="16d6e-134">如果主函数是更改一个属性，但该 cmdlet 可以更改所有属性，请在详细说明中列出此项。</span><span class="sxs-lookup"><span data-stu-id="16d6e-134">If the main function is to change one property, but the cmdlet can change all properties, list this in the detailed description.</span></span>

### <a name="use-conventional-syntax"></a><span data-ttu-id="16d6e-135">使用传统语法</span><span class="sxs-lookup"><span data-stu-id="16d6e-135">Use conventional syntax</span></span>

<span data-ttu-id="16d6e-136">使用 Windows 和 UNIX 命令行帮助中常见的标准 Backus-Naur 格式。</span><span class="sxs-lookup"><span data-stu-id="16d6e-136">Use the standard Backus-Naur format which is common for Windows and UNIX command-line Help.</span></span>

### <a name="use-microsoft-net-types-for-parameter-values"></a><span data-ttu-id="16d6e-137">使用 Microsoft .NET 类型作为参数值</span><span class="sxs-lookup"><span data-stu-id="16d6e-137">Use Microsoft .NET types for parameter values</span></span>

<span data-ttu-id="16d6e-138">语法和参数说明中 (参数值的占位符) 显示参数将接受的对象 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="16d6e-138">The placeholders for parameter values (in the syntax and parameter descriptions) show the .NET Framework types of the objects that the parameter will accept.</span></span> <span data-ttu-id="16d6e-139">PowerShell 团队开发了此约定，以帮助用户了解 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="16d6e-139">The PowerShell team developed this convention to help teach users about the .NET Framework.</span></span>

### <a name="write-complete-parameter-descriptions"></a><span data-ttu-id="16d6e-140">编写完整的参数说明</span><span class="sxs-lookup"><span data-stu-id="16d6e-140">Write complete parameter descriptions</span></span>

<span data-ttu-id="16d6e-141">参数说明必须向用户通知两个问题：参数的作用 (其效果) 以及必须为参数值键入的内容。</span><span class="sxs-lookup"><span data-stu-id="16d6e-141">Parameter descriptions must inform users of two things: what the parameter does (its effect) and what they must type for the parameter values.</span></span>

### <a name="write-practical-examples"></a><span data-ttu-id="16d6e-142">编写实际示例</span><span class="sxs-lookup"><span data-stu-id="16d6e-142">Write practical examples</span></span>

<span data-ttu-id="16d6e-143">这些示例应说明如何使用所有参数，但最重要的一点是说明如何在实际任务中使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="16d6e-143">The examples should show how to use all of the parameters, but the most important thing is to show how to use the cmdlet in real-world tasks.</span></span> <span data-ttu-id="16d6e-144">从一个简单的示例开始，编写越来越复杂的示例。</span><span class="sxs-lookup"><span data-stu-id="16d6e-144">Start with a simple example and write increasingly complex examples.</span></span> <span data-ttu-id="16d6e-145">在最后的示例中，说明如何在管道中使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="16d6e-145">In the final example, show how to use the cmdlet in a pipeline.</span></span>

### <a name="use-the-notes-field"></a><span data-ttu-id="16d6e-146">使用 "注释" 字段</span><span class="sxs-lookup"><span data-stu-id="16d6e-146">Use the Notes field</span></span>

<span data-ttu-id="16d6e-147">使用 "注释" 字段来解释用户需要了解 cmdlet 的概念。</span><span class="sxs-lookup"><span data-stu-id="16d6e-147">Use the Notes field to explain concepts that users need to understand the cmdlet.</span></span> <span data-ttu-id="16d6e-148">你还可以使用注释来帮助用户避免常见错误。</span><span class="sxs-lookup"><span data-stu-id="16d6e-148">You can also use notes to help users avoid common errors.</span></span> <span data-ttu-id="16d6e-149">避免更改 Url。</span><span class="sxs-lookup"><span data-stu-id="16d6e-149">Avoid URLs as they change.</span></span> <span data-ttu-id="16d6e-150">相反，请提供用户搜索搜索条件。</span><span class="sxs-lookup"><span data-stu-id="16d6e-150">Instead, provide users terms to search for.</span></span>

### <a name="test-your-help"></a><span data-ttu-id="16d6e-151">测试您的帮助</span><span class="sxs-lookup"><span data-stu-id="16d6e-151">Test your Help</span></span>

<span data-ttu-id="16d6e-152">测试帮助，就像测试代码一样。</span><span class="sxs-lookup"><span data-stu-id="16d6e-152">Test the Help just like you test your code.</span></span> <span data-ttu-id="16d6e-153">让朋友和同事阅读你的帮助内容并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="16d6e-153">Have friends and colleagues read your Help content and provide feedback.</span></span> <span data-ttu-id="16d6e-154">你还可以从新闻组请求反馈。</span><span class="sxs-lookup"><span data-stu-id="16d6e-154">You can also solicit feedback from newsgroups.</span></span>

## <a name="see-also"></a><span data-ttu-id="16d6e-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16d6e-155">See Also</span></span>

 [<span data-ttu-id="16d6e-156">如何创建 Cmdlet 帮助文件</span><span class="sxs-lookup"><span data-stu-id="16d6e-156">How to Create the Cmdlet Help File</span></span>](./how-to-create-the-cmdlet-help-file.md)

 [<span data-ttu-id="16d6e-157">如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要</span><span class="sxs-lookup"><span data-stu-id="16d6e-157">How to Add the Cmdlet Name and Synopsis to a Cmdlet Help Topic</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="16d6e-158">如何将详细描述添加到 Cmdlet 帮助主题</span><span class="sxs-lookup"><span data-stu-id="16d6e-158">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="16d6e-159">如何向 Cmdlet 帮助主题添加语法</span><span class="sxs-lookup"><span data-stu-id="16d6e-159">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="16d6e-160">如何将参数添加到 Cmdlet 帮助主题</span><span class="sxs-lookup"><span data-stu-id="16d6e-160">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="16d6e-161">如何将输入类型添加到 Cmdlet 帮助主题</span><span class="sxs-lookup"><span data-stu-id="16d6e-161">How to add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="16d6e-162">如何向 Cmdlet 帮助主题添加返回值</span><span class="sxs-lookup"><span data-stu-id="16d6e-162">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="16d6e-163">如何向 Cmdlet 帮助主题添加备注</span><span class="sxs-lookup"><span data-stu-id="16d6e-163">How to Add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="16d6e-164">如何向 Cmdlet 帮助主题添加示例</span><span class="sxs-lookup"><span data-stu-id="16d6e-164">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="16d6e-165">如何向 Cmdlet 帮助主题添加相关链接</span><span class="sxs-lookup"><span data-stu-id="16d6e-165">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="16d6e-166">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="16d6e-166">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
