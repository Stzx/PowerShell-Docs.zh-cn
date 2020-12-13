---
ms.date: 09/12/2016
ms.topic: reference
title: 基于注释的帮助的语法
description: 基于注释的帮助的语法
ms.openlocfilehash: 3866f25b40fc970e8d219af6f423b7a25f5b875c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659522"
---
# <a name="syntax-of-comment-based-help"></a><span data-ttu-id="0b4fc-103">基于注释的帮助的语法</span><span class="sxs-lookup"><span data-stu-id="0b4fc-103">Syntax of Comment-Based Help</span></span>

<span data-ttu-id="0b4fc-104">本部分介绍基于注释的帮助的语法。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-104">This section describes the syntax of comment-based help.</span></span>

## <a name="syntax-diagram"></a><span data-ttu-id="0b4fc-105">语法关系图</span><span class="sxs-lookup"><span data-stu-id="0b4fc-105">Syntax Diagram</span></span>

 <span data-ttu-id="0b4fc-106">基于注释的帮助的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="0b4fc-106">The syntax for comment-based Help is as follows:</span></span>

```
# .< help keyword>
# <help content>

-or -

<#
.< help keyword>
< help content>
#>
```

## <a name="syntax-description"></a><span data-ttu-id="0b4fc-107">语法说明</span><span class="sxs-lookup"><span data-stu-id="0b4fc-107">Syntax Description</span></span>

 <span data-ttu-id="0b4fc-108">基于注释的帮助以一系列注释形式编写。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-108">Comment-based Help is written as a series of comments.</span></span> <span data-ttu-id="0b4fc-109">你可以在 `#` 每行注释之前键入注释符号 () ，也可以使用 `<#` 和 `#>` 符号来创建注释块。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-109">You can type a comment symbol (`#`) before each line of comments, or you can use the `<#` and `#>` symbols to create a comment block.</span></span> <span data-ttu-id="0b4fc-110">注释块内的所有行都解释为注释。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-110">All the lines within the comment block are interpreted as comments.</span></span>

 <span data-ttu-id="0b4fc-111">基于注释的帮助的每个部分都由关键字定义，每个关键字前面有一个点 (`.`) 。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-111">Each section of comment-based Help is defined by a keyword and each keyword is preceded by a dot (`.`).</span></span> <span data-ttu-id="0b4fc-112">关键字可以按任意顺序出现。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-112">The keywords can appear in any order.</span></span> <span data-ttu-id="0b4fc-113">关键字名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-113">The keyword names are not case-sensitive.</span></span>

 <span data-ttu-id="0b4fc-114">注释块必须包含至少一个 help 关键字。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-114">A comment block must contain at least one help keyword.</span></span> <span data-ttu-id="0b4fc-115">**例如**，某些关键字可以在同一注释块中出现多次。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-115">Some of the keywords, such as **EXAMPLE**, can appear many times in the same comment block.</span></span> <span data-ttu-id="0b4fc-116">每个关键字的帮助内容都从关键字后面的行开始，可以跨多行。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-116">The Help content for each keyword begins on the line after the keyword and can span multiple lines.</span></span>

 <span data-ttu-id="0b4fc-117">基于注释的帮助主题中的所有行都必须是连续的。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-117">All of the lines in a comment-based Help topic must be contiguous.</span></span> <span data-ttu-id="0b4fc-118">如果基于注释的帮助主题遵循的注释不是帮助主题的一部分，则最后一个非帮助注释行与基于注释的帮助的开头之间必须至少有一个空白行。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-118">If a comment-based Help topic follows a comment that is not part of the Help topic, there must be at least one blank line between the last non-Help comment line and the beginning of the comment-based Help.</span></span>

 <span data-ttu-id="0b4fc-119">例如，下面的基于注释的帮助主题包含。Description 关键字及其值，这是对函数或脚本的描述。</span><span class="sxs-lookup"><span data-stu-id="0b4fc-119">For example, the following comment-based help topic contains the .Description keyword and its value, which is a description of a function or script.</span></span>

```powershell
<#
    .Description
    The Get-Function function displays the name and syntax of all functions in the session.
#>
```
