---
description: 描述在 PowerShell 中连接语句的运算符。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_logical_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Logical_Operators
ms.openlocfilehash: 1262ed0f5797d8dcb8cb4719cad69ac6b6a28d59
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199977"
---
# <a name="about_logical_operators"></a><span data-ttu-id="de6a4-104">about_Logical_Operators</span><span class="sxs-lookup"><span data-stu-id="de6a4-104">about_Logical_Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="de6a4-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="de6a4-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="de6a4-106">描述在 PowerShell 中连接语句的运算符。</span><span class="sxs-lookup"><span data-stu-id="de6a4-106">Describes the operators that connect statements in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="de6a4-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="de6a4-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="de6a4-108">PowerShell 逻辑运算符连接表达式和语句，允许使用单个表达式来测试多个条件。</span><span class="sxs-lookup"><span data-stu-id="de6a4-108">The PowerShell logical operators connect expressions and statements, allowing you to use a single expression to test for multiple conditions.</span></span>

<span data-ttu-id="de6a4-109">例如，下面的语句使用 and 运算符和 or 运算符连接三个条件语句。</span><span class="sxs-lookup"><span data-stu-id="de6a4-109">For example, the following statement uses the and operator and the or operator to connect three conditional statements.</span></span> <span data-ttu-id="de6a4-110">仅当 $a 的值大于 $b 的值并且 $a 或 $b 小于时，语句才为 true</span><span class="sxs-lookup"><span data-stu-id="de6a4-110">The statement is true only when the value of $a is greater than the value of $b, and either $a or $b is less than</span></span>
20.

```powershell
($a -gt $b) -and (($a -lt 20) -or ($b -lt 20))
```

<span data-ttu-id="de6a4-111">PowerShell 支持以下逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="de6a4-111">PowerShell supports the following logical operators.</span></span>

|<span data-ttu-id="de6a4-112">运算符</span><span class="sxs-lookup"><span data-stu-id="de6a4-112">Operator</span></span>|<span data-ttu-id="de6a4-113">说明</span><span class="sxs-lookup"><span data-stu-id="de6a4-113">Description</span></span>                        |<span data-ttu-id="de6a4-114">示例</span><span class="sxs-lookup"><span data-stu-id="de6a4-114">Example</span></span>                   |
|--------|-----------------------------------|--------------------------|
|`-and`  |<span data-ttu-id="de6a4-115">逻辑 AND。</span><span class="sxs-lookup"><span data-stu-id="de6a4-115">Logical AND.</span></span> <span data-ttu-id="de6a4-116">如果两者都为 TRUE</span><span class="sxs-lookup"><span data-stu-id="de6a4-116">TRUE when both</span></span>        |`(1 -eq 1) -and (1 -eq 2)`|
|        |<span data-ttu-id="de6a4-117">语句为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="de6a4-117">statements are TRUE.</span></span>               |`False`                   |
|`-or`   |<span data-ttu-id="de6a4-118">逻辑 OR。</span><span class="sxs-lookup"><span data-stu-id="de6a4-118">Logical OR.</span></span> <span data-ttu-id="de6a4-119">如果为 TRUE</span><span class="sxs-lookup"><span data-stu-id="de6a4-119">TRUE when either</span></span>       |`(1 -eq 1) -or (1 -eq 2)` |
|        |<span data-ttu-id="de6a4-120">语句为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="de6a4-120">statement is TRUE.</span></span>                 |`True`                    |
|`-xor`  |<span data-ttu-id="de6a4-121">逻辑异或。</span><span class="sxs-lookup"><span data-stu-id="de6a4-121">Logical EXCLUSIVE OR.</span></span> <span data-ttu-id="de6a4-122">如果</span><span class="sxs-lookup"><span data-stu-id="de6a4-122">TRUE when</span></span>    |`(1 -eq 1) -xor (2 -eq 2)`|
|        |<span data-ttu-id="de6a4-123">只有一个语句为 TRUE</span><span class="sxs-lookup"><span data-stu-id="de6a4-123">only one statement is TRUE</span></span>         |`False`                   |
|`-not`  |<span data-ttu-id="de6a4-124">逻辑非。</span><span class="sxs-lookup"><span data-stu-id="de6a4-124">Logical not.</span></span> <span data-ttu-id="de6a4-125">对语句求反</span><span class="sxs-lookup"><span data-stu-id="de6a4-125">Negates the statement</span></span> |`-not (1 -eq 1)`          |
|        |<span data-ttu-id="de6a4-126">如下所示。</span><span class="sxs-lookup"><span data-stu-id="de6a4-126">that follows.</span></span>                      |`False`                   |
|`!`     |<span data-ttu-id="de6a4-127">与 `-not` 相同</span><span class="sxs-lookup"><span data-stu-id="de6a4-127">Same as `-not`</span></span>                     |`!(1 -eq 1)`              |
|        |                                   |`False`                   |

 <span data-ttu-id="de6a4-128">注意：</span><span class="sxs-lookup"><span data-stu-id="de6a4-128">Note:</span></span>

<span data-ttu-id="de6a4-129">前面的示例还使用了等于比较运算符 `-eq` 。</span><span class="sxs-lookup"><span data-stu-id="de6a4-129">The previous examples also use the equal to comparison operator `-eq`.</span></span> <span data-ttu-id="de6a4-130">有关详细信息，请参阅 [about_Comparison_Operators](about_Comparison_Operators.md)。</span><span class="sxs-lookup"><span data-stu-id="de6a4-130">For more information, see [about_Comparison_Operators](about_Comparison_Operators.md).</span></span> <span data-ttu-id="de6a4-131">这些示例还使用整数的布尔值。</span><span class="sxs-lookup"><span data-stu-id="de6a4-131">The examples also use the Boolean values of integers.</span></span> <span data-ttu-id="de6a4-132">整数0的值为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="de6a4-132">The integer 0 has a value of FALSE.</span></span> <span data-ttu-id="de6a4-133">所有其他整数的值均为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="de6a4-133">All other integers have a value of TRUE.</span></span>

<span data-ttu-id="de6a4-134">逻辑运算符的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="de6a4-134">The syntax of the logical operators is as follows:</span></span>

```
<statement> {-AND | -OR | -XOR} <statement>
{! | -NOT} <statement>
```

<span data-ttu-id="de6a4-135">使用逻辑运算符的语句将返回布尔值 (TRUE 或 FALSE) 值。</span><span class="sxs-lookup"><span data-stu-id="de6a4-135">Statements that use the logical operators return Boolean (TRUE or FALSE) values.</span></span>

<span data-ttu-id="de6a4-136">PowerShell 逻辑运算符只计算确定语句的真假值所需的语句。</span><span class="sxs-lookup"><span data-stu-id="de6a4-136">The PowerShell logical operators evaluate only the statements required to determine the truth value of the statement.</span></span> <span data-ttu-id="de6a4-137">如果包含 and 运算符的语句中的左操作数为 FALSE，则不计算右操作数。</span><span class="sxs-lookup"><span data-stu-id="de6a4-137">If the left operand in a statement that contains the and operator is FALSE, the right operand is not evaluated.</span></span>
<span data-ttu-id="de6a4-138">如果包含或语句的语句中的左操作数为 TRUE，则不计算右操作数。</span><span class="sxs-lookup"><span data-stu-id="de6a4-138">If the left operand in a statement that contains the or statement is TRUE, the right operand is not evaluated.</span></span> <span data-ttu-id="de6a4-139">因此，您可以使用这些语句，与使用语句的方式相同 `If` 。</span><span class="sxs-lookup"><span data-stu-id="de6a4-139">As a result, you can use these statements in the same way that you would use the `If` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="de6a4-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de6a4-140">SEE ALSO</span></span>

[<span data-ttu-id="de6a4-141">about_Operators</span><span class="sxs-lookup"><span data-stu-id="de6a4-141">about_Operators</span></span>](about_Operators.md)

[<span data-ttu-id="de6a4-142">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="de6a4-142">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)

[<span data-ttu-id="de6a4-143">about_Comparison_operators</span><span class="sxs-lookup"><span data-stu-id="de6a4-143">about_Comparison_operators</span></span>](about_Comparison_Operators.md)

[<span data-ttu-id="de6a4-144">about_If</span><span class="sxs-lookup"><span data-stu-id="de6a4-144">about_If</span></span>](about_If.md)
