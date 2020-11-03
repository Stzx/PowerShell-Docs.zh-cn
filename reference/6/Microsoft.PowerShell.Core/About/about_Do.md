---
description: 运行一个或多个语句列表，并根据时间或截止时间。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_do?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Do
ms.openlocfilehash: ac8ddca01611f4477d424426ccedf9a39af85a82
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199854"
---
# <a name="about-do"></a><span data-ttu-id="a76b7-104">关于 Do</span><span class="sxs-lookup"><span data-stu-id="a76b7-104">About Do</span></span>

## <a name="short-description"></a><span data-ttu-id="a76b7-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="a76b7-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="a76b7-106">运行一个或多个语句列表，并根据时间或截止时间。</span><span class="sxs-lookup"><span data-stu-id="a76b7-106">Runs a statement list one or more times, subject to a While or Until condition.</span></span>

## <a name="long-description"></a><span data-ttu-id="a76b7-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="a76b7-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="a76b7-108">Do 关键字适用于 While 关键字或 Until 关键字，用于运行脚本块中的语句（根据条件）。</span><span class="sxs-lookup"><span data-stu-id="a76b7-108">The Do keyword works with the While keyword or the Until keyword to run the statements in a script block, subject to a condition.</span></span> <span data-ttu-id="a76b7-109">与相关的 While 循环不同，Do 循环中的脚本块始终运行至少一次。</span><span class="sxs-lookup"><span data-stu-id="a76b7-109">Unlike the related While loop, the script block in a Do loop always runs at least once.</span></span>

<span data-ttu-id="a76b7-110">**Do** 循环是各种 While 循环。</span><span class="sxs-lookup"><span data-stu-id="a76b7-110">A **Do-While** loop is a variety of the While loop.</span></span> <span data-ttu-id="a76b7-111">在 **Do** 循环中，将在运行脚本块后计算条件。</span><span class="sxs-lookup"><span data-stu-id="a76b7-111">In a **Do-While** loop, the condition is evaluated after the script block has run.</span></span> <span data-ttu-id="a76b7-112">与 While 循环一样，只要条件的计算结果为 true，就会重复脚本块。</span><span class="sxs-lookup"><span data-stu-id="a76b7-112">As in a While loop, the script block is repeated as long as the condition evaluates to true.</span></span>

<span data-ttu-id="a76b7-113">与 **do** 循环一样， **do Until** 循环始终在计算条件之前至少运行一次。</span><span class="sxs-lookup"><span data-stu-id="a76b7-113">Like a **Do-While** loop, a **Do-Until** loop always runs at least once before the condition is evaluated.</span></span> <span data-ttu-id="a76b7-114">但是，仅当条件为 false 时，才运行脚本块。</span><span class="sxs-lookup"><span data-stu-id="a76b7-114">However, the script block runs only while the condition is false.</span></span>

<span data-ttu-id="a76b7-115">*Continue* 和 *Break* 流控制关键字可以用在 **do** 循环或 **do Until** 循环中。</span><span class="sxs-lookup"><span data-stu-id="a76b7-115">The *Continue* and *Break* flow control keywords can be used in a **Do-While** loop or in a **Do-Until** loop.</span></span>

### <a name="syntax"></a><span data-ttu-id="a76b7-116">语法</span><span class="sxs-lookup"><span data-stu-id="a76b7-116">Syntax</span></span>

<span data-ttu-id="a76b7-117">下面显示了 **Do** 语句的语法：</span><span class="sxs-lookup"><span data-stu-id="a76b7-117">The following shows the syntax of the **Do-While** statement:</span></span>

```powershell
do {<statement list>} while (<condition>)
```

<span data-ttu-id="a76b7-118">下面显示了 **Do Until** 语句的语法：</span><span class="sxs-lookup"><span data-stu-id="a76b7-118">The following shows the syntax of the **Do-Until** statement:</span></span>

```powershell
do {<statement list>} until (<condition>)
```

<span data-ttu-id="a76b7-119">语句列表包含一个或多个在每次输入或重复循环时运行的语句。</span><span class="sxs-lookup"><span data-stu-id="a76b7-119">The statement list contains one or more statements that run each time the loop is entered or repeated.</span></span>

<span data-ttu-id="a76b7-120">语句的条件部分解析为 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="a76b7-120">The condition portion of the statement resolves to true or false.</span></span>

### <a name="example"></a><span data-ttu-id="a76b7-121">示例</span><span class="sxs-lookup"><span data-stu-id="a76b7-121">Example</span></span>

<span data-ttu-id="a76b7-122">下面的 Do 语句示例计算数组中的项，直到到达值为0的项。</span><span class="sxs-lookup"><span data-stu-id="a76b7-122">The following example of a Do statement counts the items in an array until it reaches an item with a value of 0.</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } while ($x[$a] -ne 0)
C:\PS> $count
3
```

<span data-ttu-id="a76b7-123">下面的示例使用 Until 关键字。</span><span class="sxs-lookup"><span data-stu-id="a76b7-123">The following example uses the Until keyword.</span></span> <span data-ttu-id="a76b7-124">请注意， () 不等于运算符 `-ne` () 替换为等于运算符 `-eq` 。</span><span class="sxs-lookup"><span data-stu-id="a76b7-124">Notice that the not equal to operator (`-ne`) is replaced by the equal to operator (`-eq`).</span></span>

```powershell
C:\PS> $x = 1,2,78,0
C:\PS> do { $count++; $a++; } until ($x[$a] -eq 0)
C:\PS> $count
3
```

<span data-ttu-id="a76b7-125">下面的示例将写入数组的所有值，并跳过任何小于零的值。</span><span class="sxs-lookup"><span data-stu-id="a76b7-125">The following example writes all the values of an array, skipping any value that is less than zero.</span></span>

```powershell
do {
  if ($x[$a] -lt 0) { continue }
  Write-Host $x[$a]
}
while (++$a -lt 10)
```

## <a name="see-also"></a><span data-ttu-id="a76b7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a76b7-126">SEE ALSO</span></span>

[<span data-ttu-id="a76b7-127">about_While</span><span class="sxs-lookup"><span data-stu-id="a76b7-127">about_While</span></span>](about_While.md)

[<span data-ttu-id="a76b7-128">about_Operators</span><span class="sxs-lookup"><span data-stu-id="a76b7-128">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="a76b7-129">about_Assignment_Operators</span><span class="sxs-lookup"><span data-stu-id="a76b7-129">about_Assignment_Operators</span></span>](about_Assignment_Operators.md)

[<span data-ttu-id="a76b7-130">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="a76b7-130">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="a76b7-131">about_Break</span><span class="sxs-lookup"><span data-stu-id="a76b7-131">about_Break</span></span>](about_Break.md)

[<span data-ttu-id="a76b7-132">about_Continue</span><span class="sxs-lookup"><span data-stu-id="a76b7-132">about_Continue</span></span>](about_Continue.md)
