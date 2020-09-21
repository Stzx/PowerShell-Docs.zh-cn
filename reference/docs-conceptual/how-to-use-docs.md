---
ms.date: 07/29/2020
keywords: powershell,cmdlet
title: 如何使用 PowerShell 文档
ms.openlocfilehash: 1cfeb9eea564e7618062e1b8ada4948bd9e22969
ms.sourcegitcommit: 9f9eb95bc859e9e0fed48101327a602b2ced351d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87821523"
---
# <a name="how-to-use-the-powershell-documentation"></a><span data-ttu-id="2300d-103">如何使用 PowerShell 文档</span><span class="sxs-lookup"><span data-stu-id="2300d-103">How to use the PowerShell documentation</span></span>

<span data-ttu-id="2300d-104">欢迎使用 PowerShell 联机文档。</span><span class="sxs-lookup"><span data-stu-id="2300d-104">Welcome to the PowerShell online documentation.</span></span> <span data-ttu-id="2300d-105">此站点包含以下 PowerShell 版本的 cmdlet 参考：</span><span class="sxs-lookup"><span data-stu-id="2300d-105">This site contains cmdlet reference for the following versions of PowerShell:</span></span>

- <span data-ttu-id="2300d-106">PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="2300d-106">PowerShell 7</span></span>
- <span data-ttu-id="2300d-107">PowerShell 6</span><span class="sxs-lookup"><span data-stu-id="2300d-107">PowerShell 6</span></span>
- <span data-ttu-id="2300d-108">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="2300d-108">PowerShell 5.1</span></span>

## <a name="finding-articles-and-selecting-a-version"></a><span data-ttu-id="2300d-109">查找文章并选择版本</span><span class="sxs-lookup"><span data-stu-id="2300d-109">Finding articles and selecting a version</span></span>

<span data-ttu-id="2300d-110">有两种方法可以搜索 Docs 中的内容。最简单的方法是使用版本选取器下的筛选器框。</span><span class="sxs-lookup"><span data-stu-id="2300d-110">There are two ways to search for content in Docs. The simplest way is to use the filter box under the version selector.</span></span> <span data-ttu-id="2300d-111">只需输入文章标题中出现的字词即可。</span><span class="sxs-lookup"><span data-stu-id="2300d-111">Just enter a word that appears in the title of an article.</span></span> <span data-ttu-id="2300d-112">该页面显示匹配文章的列表。</span><span class="sxs-lookup"><span data-stu-id="2300d-112">The page displays a list of matching articles.</span></span> <span data-ttu-id="2300d-113">还可以从该列表中选择用于搜索整个站点的选项。</span><span class="sxs-lookup"><span data-stu-id="2300d-113">You can also select the option to search the entire site from that list.</span></span>

<span data-ttu-id="2300d-114">默认情况下，此站点显示最新版本的 PowerShell 的文档。</span><span class="sxs-lookup"><span data-stu-id="2300d-114">By default, this site displays documentation for the latest released version of PowerShell.</span></span> <span data-ttu-id="2300d-115">一些 cmdlet 在不同版本的 PowerShell 中的工作方式有所不同。</span><span class="sxs-lookup"><span data-stu-id="2300d-115">Some cmdlets work differently in various versions of PowerShell.</span></span> <span data-ttu-id="2300d-116">确保查看所使用的 PowerShell 版本的文档。</span><span class="sxs-lookup"><span data-stu-id="2300d-116">Be sure you are viewing the documentation for the version of PowerShell you are using.</span></span>

<span data-ttu-id="2300d-117">使用页面顶部的版本选取器来选择所需的 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="2300d-117">Use the version picker at the top of the page to select the version of PowerShell you want.</span></span>

![使用版本选取器](media/how-to-use-docs/version-search.gif)

<span data-ttu-id="2300d-119">可以通过查看 `$PSversionTable.PSVersion` 值来验证所使用的 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="2300d-119">You can verify the version of PowerShell you are using by inspecting the `$PSversionTable.PSVersion` value.</span></span> <span data-ttu-id="2300d-120">下面的示例演示 Windows PowerShell 5.1 的输出。</span><span class="sxs-lookup"><span data-stu-id="2300d-120">The following example shows the output for Windows PowerShell 5.1.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      19041  1
```

<span data-ttu-id="2300d-121">如果你还不熟悉 PowerShell，并需要有关理解命令语法方面的帮助，请参阅 [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax)。</span><span class="sxs-lookup"><span data-stu-id="2300d-121">If you are new to PowerShell and need help understanding the command syntax, see [about_Command_Syntax](/powershell/module/microsoft.powershell.core/about/about_command_syntax).</span></span>

## <a name="finding-articles-for-previous-versions"></a><span data-ttu-id="2300d-122">在文章中查找历史版本</span><span class="sxs-lookup"><span data-stu-id="2300d-122">Finding articles for previous versions</span></span>

<span data-ttu-id="2300d-123">旧版 PowerShell 的相关文档已存档到我们的[历史版本](https://aka.ms/PSLegacyDocs)网站中。</span><span class="sxs-lookup"><span data-stu-id="2300d-123">Documentation for older versions of PowerShell has been archived in our [Previous Versions](https://aka.ms/PSLegacyDocs) site.</span></span>

<span data-ttu-id="2300d-124">此网站包含下列主题的文档：</span><span class="sxs-lookup"><span data-stu-id="2300d-124">This site contains documentation for the following topics:</span></span>

- <span data-ttu-id="2300d-125">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="2300d-125">PowerShell 3.0</span></span>
- <span data-ttu-id="2300d-126">PowerShell 4.0</span><span class="sxs-lookup"><span data-stu-id="2300d-126">PowerShell 4.0</span></span>
- <span data-ttu-id="2300d-127">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2300d-127">PowerShell 5.0</span></span>
- <span data-ttu-id="2300d-128">PowerShell 工作流</span><span class="sxs-lookup"><span data-stu-id="2300d-128">PowerShell Workflows</span></span>
- <span data-ttu-id="2300d-129">PowerShell Web 访问</span><span class="sxs-lookup"><span data-stu-id="2300d-129">PowerShell Web Access</span></span>
