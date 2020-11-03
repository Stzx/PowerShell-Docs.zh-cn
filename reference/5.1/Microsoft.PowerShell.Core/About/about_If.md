---
description: 描述可用于根据一个或多个条件测试的结果运行语句列表的语言命令。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_if?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_If
ms.openlocfilehash: 8b1be96167dab47e7e15e3e5b89c46126f117541
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200292"
---
# <a name="about-if"></a><span data-ttu-id="faf24-104">关于 If</span><span class="sxs-lookup"><span data-stu-id="faf24-104">About If</span></span>

## <a name="short-description"></a><span data-ttu-id="faf24-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="faf24-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="faf24-106">描述可用于根据一个或多个条件测试的结果运行语句列表的语言命令。</span><span class="sxs-lookup"><span data-stu-id="faf24-106">Describes a language command you can use to run statement lists based on the results of one or more conditional tests.</span></span>

## <a name="long-description"></a><span data-ttu-id="faf24-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="faf24-107">LONG DESCRIPTION</span></span>
<span data-ttu-id="faf24-108">`If`如果指定的条件测试的计算结果为 true，则可以使用语句来运行代码块。</span><span class="sxs-lookup"><span data-stu-id="faf24-108">You can use the `If` statement to run code blocks if a specified conditional test evaluates to true.</span></span> <span data-ttu-id="faf24-109">如果所有之前的测试的计算结果都为 false，则还可以指定要运行的一个或多个附加条件测试。</span><span class="sxs-lookup"><span data-stu-id="faf24-109">You can also specify one or more additional conditional tests to run if all the prior tests evaluate to false.</span></span> <span data-ttu-id="faf24-110">最后，你可以指定一个其他代码块，如果没有其他任何之前的条件测试计算为 true，则会运行该代码块。</span><span class="sxs-lookup"><span data-stu-id="faf24-110">Finally, you can specify an additional code block that is run if no other prior conditional test evaluates to true.</span></span>

### <a name="syntax"></a><span data-ttu-id="faf24-111">语法</span><span class="sxs-lookup"><span data-stu-id="faf24-111">Syntax</span></span>

<span data-ttu-id="faf24-112">下面的示例显示了 `If` 语句语法：</span><span class="sxs-lookup"><span data-stu-id="faf24-112">The following example shows the `If` statement syntax:</span></span>

```powershell
if (<test1>)
    {<statement list 1>}
[elseif (<test2>)
    {<statement list 2>}]
[else
    {<statement list 3>}]
```

<span data-ttu-id="faf24-113">运行 `If` 语句时，PowerShell 会将 `<test1>` 条件表达式计算为 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="faf24-113">When you run an `If` statement, PowerShell evaluates the `<test1>` conditional expression as true or false.</span></span> <span data-ttu-id="faf24-114">如果 `<test1>` 为 true，则 `<statement list 1>` 运行，并且 PowerShell 将退出 `If` 语句。</span><span class="sxs-lookup"><span data-stu-id="faf24-114">If `<test1>` is true, `<statement list 1>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="faf24-115">如果 `<test1>` 为 false，则 PowerShell 将计算由条件语句指定的条件 `<test2>` 。</span><span class="sxs-lookup"><span data-stu-id="faf24-115">If `<test1>` is false, PowerShell evaluates the condition specified by the `<test2>` conditional statement.</span></span>

<span data-ttu-id="faf24-116">如果 `<test2>` 为 true，则 `<statement list 2>` 运行，并且 PowerShell 将退出 `If` 语句。</span><span class="sxs-lookup"><span data-stu-id="faf24-116">If `<test2>` is true, `<statement list 2>` runs, and PowerShell exits the `If` statement.</span></span> <span data-ttu-id="faf24-117">如果 `<test1>` 和 `<test2>` 的计算结果都为 false，则 `<statement list 3`> 代码块运行，并且 PowerShell 将退出 If 语句。</span><span class="sxs-lookup"><span data-stu-id="faf24-117">If both `<test1>` and `<test2>` evaluate to false, the `<statement list 3`> code block runs, and PowerShell exits the If statement.</span></span>

<span data-ttu-id="faf24-118">可以使用多个 Elseif 语句来链接一系列条件测试。</span><span class="sxs-lookup"><span data-stu-id="faf24-118">You can use multiple Elseif statements to chain a series of conditional tests.</span></span> <span data-ttu-id="faf24-119">因此，仅当前面的所有测试都为 false 时，才会运行每个测试。</span><span class="sxs-lookup"><span data-stu-id="faf24-119">So, that each test is run only if all the previous tests are false.</span></span>
<span data-ttu-id="faf24-120">如果需要创建 `If` 包含多个 Elseif 语句的语句，请考虑改为使用 Switch 语句。</span><span class="sxs-lookup"><span data-stu-id="faf24-120">If you need to create an `If` statement that contains many Elseif statements, consider using a Switch statement instead.</span></span>

<span data-ttu-id="faf24-121">示例:</span><span class="sxs-lookup"><span data-stu-id="faf24-121">Examples:</span></span>

<span data-ttu-id="faf24-122">最简单的 `If` 语句包含一个命令，不包含任何 Elseif 语句或任何 Else 语句。</span><span class="sxs-lookup"><span data-stu-id="faf24-122">The simplest `If` statement contains a single command and does not contain any Elseif statements or any Else statements.</span></span> <span data-ttu-id="faf24-123">下面的示例显示了语句的最简单形式 `If` ：</span><span class="sxs-lookup"><span data-stu-id="faf24-123">The following example shows the simplest form of the `If` statement:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
```

<span data-ttu-id="faf24-124">在此示例中，如果 $a 变量大于2，则条件的计算结果为 true，并且语句列表将运行。</span><span class="sxs-lookup"><span data-stu-id="faf24-124">In this example, if the $a variable is greater than 2, the condition evaluates to true, and the statement list runs.</span></span> <span data-ttu-id="faf24-125">但是，如果 $a 小于或等于2或者不是现有的变量，则该语句不 `If` 显示消息。</span><span class="sxs-lookup"><span data-stu-id="faf24-125">However, if $a is less than or equal to 2 or is not an existing variable, the `If` statement does not display a message.</span></span>

<span data-ttu-id="faf24-126">通过添加 Else 语句，当 $a 小于或等于2时，将显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="faf24-126">By adding an Else statement, a message is displayed when $a is less than or equal to 2.</span></span> <span data-ttu-id="faf24-127">如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="faf24-127">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
else {
    Write-Host ("The value $a is less than or equal to 2," +
        " is not created or is not initialized.")
}
```

<span data-ttu-id="faf24-128">若要进一步优化此示例，可以使用 Elseif 语句在 $a 的值等于2时显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="faf24-128">To further refine this example, you can use the Elseif statement to display a message when the value of $a is equal to 2.</span></span> <span data-ttu-id="faf24-129">如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="faf24-129">As the next example shows:</span></span>

```powershell
if ($a -gt 2) {
    Write-Host "The value $a is greater than 2."
}
elseif ($a -eq 2) {
    Write-Host "The value $a is equal to 2."
}
else {
    Write-Host ("The value $a is less than 2 or" +
        " was not created or initialized.")
}
```

## <a name="see-also"></a><span data-ttu-id="faf24-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faf24-130">SEE ALSO</span></span>

[<span data-ttu-id="faf24-131">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="faf24-131">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="faf24-132">about_Switch</span><span class="sxs-lookup"><span data-stu-id="faf24-132">about_Switch</span></span>](about_Switch.md)