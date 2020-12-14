---
description: 描述在 PowerShell 中比较值的运算符。
Locale: en-US
ms.date: 12/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: dbda5371224345a2e22dd281c17ae0d7c928aad6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "97090220"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="bea1a-103">关于比较运算符</span><span class="sxs-lookup"><span data-stu-id="bea1a-103">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="bea1a-104">简短说明</span><span class="sxs-lookup"><span data-stu-id="bea1a-104">Short description</span></span>
<span data-ttu-id="bea1a-105">描述在 PowerShell 中比较值的运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-105">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="bea1a-106">长说明</span><span class="sxs-lookup"><span data-stu-id="bea1a-106">Long description</span></span>

<span data-ttu-id="bea1a-107">比较运算符使你可以指定比较值和查找与指定模式匹配的值的条件。</span><span class="sxs-lookup"><span data-stu-id="bea1a-107">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="bea1a-108">若要使用比较运算符，请指定要与这些值分隔的运算符进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-108">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="bea1a-109">PowerShell 包含以下比较运算符：</span><span class="sxs-lookup"><span data-stu-id="bea1a-109">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="bea1a-110">类型</span><span class="sxs-lookup"><span data-stu-id="bea1a-110">Type</span></span>        | <span data-ttu-id="bea1a-111">运算符</span><span class="sxs-lookup"><span data-stu-id="bea1a-111">Operators</span></span>    | <span data-ttu-id="bea1a-112">说明</span><span class="sxs-lookup"><span data-stu-id="bea1a-112">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="bea1a-113">相等</span><span class="sxs-lookup"><span data-stu-id="bea1a-113">Equality</span></span>    | <span data-ttu-id="bea1a-114">-eq</span><span class="sxs-lookup"><span data-stu-id="bea1a-114">-eq</span></span>          | <span data-ttu-id="bea1a-115">equals</span><span class="sxs-lookup"><span data-stu-id="bea1a-115">equals</span></span>                                      |
|             | <span data-ttu-id="bea1a-116">-ne</span><span class="sxs-lookup"><span data-stu-id="bea1a-116">-ne</span></span>          | <span data-ttu-id="bea1a-117">不等于</span><span class="sxs-lookup"><span data-stu-id="bea1a-117">not equals</span></span>                                  |
|             | <span data-ttu-id="bea1a-118">-gt</span><span class="sxs-lookup"><span data-stu-id="bea1a-118">-gt</span></span>          | <span data-ttu-id="bea1a-119">大于</span><span class="sxs-lookup"><span data-stu-id="bea1a-119">greater than</span></span>                                |
|             | <span data-ttu-id="bea1a-120">-ge</span><span class="sxs-lookup"><span data-stu-id="bea1a-120">-ge</span></span>          | <span data-ttu-id="bea1a-121">大于或等于</span><span class="sxs-lookup"><span data-stu-id="bea1a-121">greater than or equal</span></span>                       |
|             | <span data-ttu-id="bea1a-122">-lt</span><span class="sxs-lookup"><span data-stu-id="bea1a-122">-lt</span></span>          | <span data-ttu-id="bea1a-123">小于</span><span class="sxs-lookup"><span data-stu-id="bea1a-123">less than</span></span>                                   |
|             | <span data-ttu-id="bea1a-124">-le</span><span class="sxs-lookup"><span data-stu-id="bea1a-124">-le</span></span>          | <span data-ttu-id="bea1a-125">小于或等于</span><span class="sxs-lookup"><span data-stu-id="bea1a-125">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="bea1a-126">Matching</span><span class="sxs-lookup"><span data-stu-id="bea1a-126">Matching</span></span>    | <span data-ttu-id="bea1a-127">-like</span><span class="sxs-lookup"><span data-stu-id="bea1a-127">-like</span></span>        | <span data-ttu-id="bea1a-128">如果字符串匹配通配符，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-128">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="bea1a-129">pattern</span><span class="sxs-lookup"><span data-stu-id="bea1a-129">pattern</span></span>                                     |
|             | <span data-ttu-id="bea1a-130">-notlike</span><span class="sxs-lookup"><span data-stu-id="bea1a-130">-notlike</span></span>     | <span data-ttu-id="bea1a-131">如果字符串不匹配，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-131">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="bea1a-132">通配符模式</span><span class="sxs-lookup"><span data-stu-id="bea1a-132">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="bea1a-133">-match</span><span class="sxs-lookup"><span data-stu-id="bea1a-133">-match</span></span>       | <span data-ttu-id="bea1a-134">如果字符串与正则表达式匹配，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-134">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="bea1a-135">化$matches 包含匹配的字符串</span><span class="sxs-lookup"><span data-stu-id="bea1a-135">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="bea1a-136">-notmatch</span><span class="sxs-lookup"><span data-stu-id="bea1a-136">-notmatch</span></span>    | <span data-ttu-id="bea1a-137">如果字符串不匹配，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-137">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="bea1a-138">regex 模式;$matches 包含匹配</span><span class="sxs-lookup"><span data-stu-id="bea1a-138">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="bea1a-139">字符串</span><span class="sxs-lookup"><span data-stu-id="bea1a-139">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="bea1a-140">Containment</span><span class="sxs-lookup"><span data-stu-id="bea1a-140">Containment</span></span> | <span data-ttu-id="bea1a-141">-contains</span><span class="sxs-lookup"><span data-stu-id="bea1a-141">-contains</span></span>    | <span data-ttu-id="bea1a-142">如果引用值包含，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-142">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="bea1a-143">在集合中</span><span class="sxs-lookup"><span data-stu-id="bea1a-143">in a collection</span></span>                             |
|             | <span data-ttu-id="bea1a-144">-notcontains</span><span class="sxs-lookup"><span data-stu-id="bea1a-144">-notcontains</span></span> | <span data-ttu-id="bea1a-145">如果引用值不为，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-145">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="bea1a-146">包含在集合中</span><span class="sxs-lookup"><span data-stu-id="bea1a-146">contained in a collection</span></span>                   |
|             | <span data-ttu-id="bea1a-147">-in</span><span class="sxs-lookup"><span data-stu-id="bea1a-147">-in</span></span>          | <span data-ttu-id="bea1a-148">如果中包含的测试值为</span><span class="sxs-lookup"><span data-stu-id="bea1a-148">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="bea1a-149">collection</span><span class="sxs-lookup"><span data-stu-id="bea1a-149">collection</span></span>                                  |
|             | <span data-ttu-id="bea1a-150">-notin</span><span class="sxs-lookup"><span data-stu-id="bea1a-150">-notin</span></span>       | <span data-ttu-id="bea1a-151">如果测试值不包含，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-151">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="bea1a-152">在集合中</span><span class="sxs-lookup"><span data-stu-id="bea1a-152">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="bea1a-153">Replacement</span><span class="sxs-lookup"><span data-stu-id="bea1a-153">Replacement</span></span> | <span data-ttu-id="bea1a-154">-replace</span><span class="sxs-lookup"><span data-stu-id="bea1a-154">-replace</span></span>     | <span data-ttu-id="bea1a-155">替换字符串模式</span><span class="sxs-lookup"><span data-stu-id="bea1a-155">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="bea1a-156">类型</span><span class="sxs-lookup"><span data-stu-id="bea1a-156">Type</span></span>        | <span data-ttu-id="bea1a-157">-为</span><span class="sxs-lookup"><span data-stu-id="bea1a-157">-is</span></span>          | <span data-ttu-id="bea1a-158">如果两个对象相同，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-158">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="bea1a-159">类型</span><span class="sxs-lookup"><span data-stu-id="bea1a-159">type</span></span>                                        |
|             | <span data-ttu-id="bea1a-160">-isnot</span><span class="sxs-lookup"><span data-stu-id="bea1a-160">-isnot</span></span>       | <span data-ttu-id="bea1a-161">如果对象不相同，则返回 true</span><span class="sxs-lookup"><span data-stu-id="bea1a-161">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="bea1a-162">类型</span><span class="sxs-lookup"><span data-stu-id="bea1a-162">type</span></span>                                        |

<span data-ttu-id="bea1a-163">默认情况下，所有比较运算符都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bea1a-163">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="bea1a-164">若要使比较运算符区分大小写，请在运算符名称之前加 `c` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-164">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="bea1a-165">例如，区分大小写的版本 `-eq` 为 `-ceq` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-165">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="bea1a-166">若要使不区分大小写的显式，请在运算符前面加上 `i` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-166">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="bea1a-167">例如，的显式不区分大小写的版本 `-eq` 为 `-ieq` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-167">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="bea1a-168">当运算符的输入是标量值时，比较运算符将返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-168">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="bea1a-169">当输入是值的集合时，比较运算符返回任何匹配值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-169">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="bea1a-170">如果集合中没有匹配项，则比较运算符返回空数组。</span><span class="sxs-lookup"><span data-stu-id="bea1a-170">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="bea1a-171">例外情况包括：包含运算符、In 运算符和类型运算符，它们始终返回 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-171">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="bea1a-172">如果需要比较值， `$null` 应将该值放 `$null` 在比较的左侧。</span><span class="sxs-lookup"><span data-stu-id="bea1a-172">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="bea1a-173">当与 `$null` **对象 []** 进行比较时，结果为 **False** ，因为比较对象是一个数组。</span><span class="sxs-lookup"><span data-stu-id="bea1a-173">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="bea1a-174">将数组与进行比较时 `$null` ，比较筛选出 `$null` 存储在数组中的所有值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-174">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="bea1a-175">例如：</span><span class="sxs-lookup"><span data-stu-id="bea1a-175">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

## <a name="equality-operators"></a><span data-ttu-id="bea1a-176">相等运算符</span><span class="sxs-lookup"><span data-stu-id="bea1a-176">Equality operators</span></span>

<span data-ttu-id="bea1a-177">相等运算符 (`-eq` ， `-ne`) 在一个或多个输入值与指定模式相同时返回值或匹配项。</span><span class="sxs-lookup"><span data-stu-id="bea1a-177">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="bea1a-178">整个模式必须匹配整个值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-178">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="bea1a-179">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-179">Example:</span></span>

### <a name="-eq"></a><span data-ttu-id="bea1a-180">-eq</span><span class="sxs-lookup"><span data-stu-id="bea1a-180">-eq</span></span>

<span data-ttu-id="bea1a-181">说明：等于。</span><span class="sxs-lookup"><span data-stu-id="bea1a-181">Description: Equal to.</span></span> <span data-ttu-id="bea1a-182">包含相同的值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-182">Includes an identical value.</span></span>

<span data-ttu-id="bea1a-183">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-183">Example:</span></span>

```powershell
PS> 2 -eq 2
True

PS> 2 -eq 3
False

PS> 1,2,3 -eq 2
2
PS> "abc" -eq "abc"
True

PS> "abc" -eq "abc", "def"
False

PS> "abc", "def" -eq "abc"
abc
```

### <a name="-ne"></a><span data-ttu-id="bea1a-184">-ne</span><span class="sxs-lookup"><span data-stu-id="bea1a-184">-ne</span></span>

<span data-ttu-id="bea1a-185">说明：不等于。</span><span class="sxs-lookup"><span data-stu-id="bea1a-185">Description: Not equal to.</span></span> <span data-ttu-id="bea1a-186">包含不同的值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-186">Includes a different value.</span></span>

<span data-ttu-id="bea1a-187">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-187">Example:</span></span>

```powershell
PS> "abc" -ne "def"
True

PS> "abc" -ne "abc"
False

PS> "abc" -ne "abc", "def"
True

PS> "abc", "def" -ne "abc"
def
```

### <a name="-gt"></a><span data-ttu-id="bea1a-188">-gt</span><span class="sxs-lookup"><span data-stu-id="bea1a-188">-gt</span></span>

<span data-ttu-id="bea1a-189">说明：大于。</span><span class="sxs-lookup"><span data-stu-id="bea1a-189">Description: Greater-than.</span></span>

<span data-ttu-id="bea1a-190">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-190">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="bea1a-191">这不应与 `>` 其他许多编程语言中的大于运算符混淆。</span><span class="sxs-lookup"><span data-stu-id="bea1a-191">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="bea1a-192">在 PowerShell 中， `>` 用于重定向。</span><span class="sxs-lookup"><span data-stu-id="bea1a-192">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="bea1a-193">有关详细信息，请参阅 [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators)。</span><span class="sxs-lookup"><span data-stu-id="bea1a-193">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

### <a name="-ge"></a><span data-ttu-id="bea1a-194">-ge</span><span class="sxs-lookup"><span data-stu-id="bea1a-194">-ge</span></span>

<span data-ttu-id="bea1a-195">说明：大于或等于。</span><span class="sxs-lookup"><span data-stu-id="bea1a-195">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="bea1a-196">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-196">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

### <a name="-lt"></a><span data-ttu-id="bea1a-197">-lt</span><span class="sxs-lookup"><span data-stu-id="bea1a-197">-lt</span></span>

<span data-ttu-id="bea1a-198">说明：小于。</span><span class="sxs-lookup"><span data-stu-id="bea1a-198">Description: Less-than.</span></span>

<span data-ttu-id="bea1a-199">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-199">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

### <a name="-le"></a><span data-ttu-id="bea1a-200">-le</span><span class="sxs-lookup"><span data-stu-id="bea1a-200">-le</span></span>

<span data-ttu-id="bea1a-201">说明：小于或等于。</span><span class="sxs-lookup"><span data-stu-id="bea1a-201">Description: Less-than or equal to.</span></span>

<span data-ttu-id="bea1a-202">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-202">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

## <a name="matching-operators"></a><span data-ttu-id="bea1a-203">匹配运算符</span><span class="sxs-lookup"><span data-stu-id="bea1a-203">Matching operators</span></span>

<span data-ttu-id="bea1a-204">Like 运算符 (`-like` 和 `-notlike`) 使用通配符表达式查找匹配或与指定模式不匹配的元素。</span><span class="sxs-lookup"><span data-stu-id="bea1a-204">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="bea1a-205">语法为：</span><span class="sxs-lookup"><span data-stu-id="bea1a-205">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="bea1a-206">匹配运算符 (`-match` 和 `-notmatch`) 使用正则表达式查找匹配或与指定模式不匹配的元素。</span><span class="sxs-lookup"><span data-stu-id="bea1a-206">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="bea1a-207">`$Matches`当输入 (左侧参数) 为单个标量对象时，匹配运算符将填充自动变量。</span><span class="sxs-lookup"><span data-stu-id="bea1a-207">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="bea1a-208">当输入是标量时， `-match` 和 `-notmatch` 运算符将返回一个布尔值，并将自动变量的值设置 `$Matches` 为参数的匹配组件。</span><span class="sxs-lookup"><span data-stu-id="bea1a-208">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="bea1a-209">语法为：</span><span class="sxs-lookup"><span data-stu-id="bea1a-209">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

### <a name="-like"></a><span data-ttu-id="bea1a-210">-like</span><span class="sxs-lookup"><span data-stu-id="bea1a-210">-like</span></span>

<span data-ttu-id="bea1a-211">说明：使用通配符)  (匹配 \* 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-211">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="bea1a-212">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-212">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

### <a name="-notlike"></a><span data-ttu-id="bea1a-213">-notlike</span><span class="sxs-lookup"><span data-stu-id="bea1a-213">-notlike</span></span>

<span data-ttu-id="bea1a-214">说明：使用通配符 () 不匹配 \* 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-214">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="bea1a-215">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-215">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="bea1a-216">-match</span><span class="sxs-lookup"><span data-stu-id="bea1a-216">-match</span></span>

<span data-ttu-id="bea1a-217">说明：使用正则表达式匹配字符串。</span><span class="sxs-lookup"><span data-stu-id="bea1a-217">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="bea1a-218">当输入是标量时，它将填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="bea1a-218">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="bea1a-219">如果输入是集合，则 `-match` 和 `-notmatch` 运算符返回该集合的匹配成员，但是运算符不填充该 `$Matches` 变量。</span><span class="sxs-lookup"><span data-stu-id="bea1a-219">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="bea1a-220">例如，以下命令将字符串的集合提交给 `-match` 运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-220">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="bea1a-221">`-match`运算符返回集合中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="bea1a-221">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="bea1a-222">它不填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="bea1a-222">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="bea1a-223">与此相反，以下命令将单个字符串提交给 `-match` 运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-223">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="bea1a-224">`-match`运算符返回布尔值并填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="bea1a-224">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="bea1a-225">`$Matches`自动变量是 **哈希表**。</span><span class="sxs-lookup"><span data-stu-id="bea1a-225">The `$Matches` automatic variable is a **Hashtable**.</span></span> <span data-ttu-id="bea1a-226">如果未使用分组或捕获，则只填充一个键。</span><span class="sxs-lookup"><span data-stu-id="bea1a-226">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="bea1a-227">`0`键表示匹配的所有文本。</span><span class="sxs-lookup"><span data-stu-id="bea1a-227">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="bea1a-228">有关使用正则表达式进行分组和捕获的详细信息，请参阅 [about_Regular_Expressions](about_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="bea1a-228">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="bea1a-229">请注意， `$Matches` 哈希表只包含任何匹配模式的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="bea1a-229">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="bea1a-230">`0`该键是一个 **整数**。</span><span class="sxs-lookup"><span data-stu-id="bea1a-230">The `0` key is an **Integer**.</span></span> <span data-ttu-id="bea1a-231">您可以使用任何 **哈希表** 方法来访问存储的值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-231">You can use any **Hashtable** method to access the value stored.</span></span>
>
> ```powershell
> PS> "Good Dog" -match "Dog"
> True
>
> PS> $Matches[0]
> Dog
>
> PS> $Matches.Item(0)
> Dog
>
> PS> $Matches.0
> Dog
> ```

<span data-ttu-id="bea1a-232">`-notmatch` `$Matches` 当输入是标量时，运算符将填充自动变量，并且在检测到匹配项时，结果为 False。</span><span class="sxs-lookup"><span data-stu-id="bea1a-232">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

```powershell
PS> "Sunday" -notmatch "rain"
True

PS> $matches
PS>

PS> "Sunday" -notmatch "day"
False

PS> $matches

Name                           Value
----                           -----
0                              day
```

### <a name="-notmatch"></a><span data-ttu-id="bea1a-233">-notmatch</span><span class="sxs-lookup"><span data-stu-id="bea1a-233">-notmatch</span></span>

<span data-ttu-id="bea1a-234">说明：不匹配字符串。</span><span class="sxs-lookup"><span data-stu-id="bea1a-234">Description: Does not match a string.</span></span> <span data-ttu-id="bea1a-235">使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="bea1a-235">Uses regular expressions.</span></span> <span data-ttu-id="bea1a-236">当输入是标量时，它将填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="bea1a-236">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="bea1a-237">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-237">Example:</span></span>

```powershell
PS> "Sunday" -notmatch "sun"
False

PS> $matches
Name Value
---- -----
0    sun

PS> "Sunday", "Monday" -notmatch "sun"
Monday
```

## <a name="containment-operators"></a><span data-ttu-id="bea1a-238">包含运算符</span><span class="sxs-lookup"><span data-stu-id="bea1a-238">Containment operators</span></span>

<span data-ttu-id="bea1a-239">包含运算符 (`-contains` 和 `-notcontains`) 类似于相等运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-239">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="bea1a-240">但是，包含运算符始终返回布尔值，即使输入是集合也是如此。</span><span class="sxs-lookup"><span data-stu-id="bea1a-240">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="bea1a-241">另外，与相等运算符不同，包含运算符在检测到第一个匹配项后就会返回一个值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-241">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="bea1a-242">相等运算符计算所有输入，然后返回集合中的所有匹配项。</span><span class="sxs-lookup"><span data-stu-id="bea1a-242">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

### <a name="-contains"></a><span data-ttu-id="bea1a-243">-contains</span><span class="sxs-lookup"><span data-stu-id="bea1a-243">-contains</span></span>

<span data-ttu-id="bea1a-244">Description：包含运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-244">Description: Containment operator.</span></span> <span data-ttu-id="bea1a-245">指示引用值的集合是否包含一个测试值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-245">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="bea1a-246">始终返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-246">Always returns a Boolean value.</span></span> <span data-ttu-id="bea1a-247">仅当测试值与至少一个引用值完全匹配时才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bea1a-247">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="bea1a-248">如果测试值是集合，则 Contains 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="bea1a-248">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="bea1a-249">仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bea1a-249">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="bea1a-250">在非常大的集合中， `-contains` 运算符比等于运算符更快地返回结果。</span><span class="sxs-lookup"><span data-stu-id="bea1a-250">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="bea1a-251">语法：</span><span class="sxs-lookup"><span data-stu-id="bea1a-251">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="bea1a-252">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-252">Examples:</span></span>

```powershell
PS> "abc", "def" -contains "def"
True

PS> "Windows", "PowerShell" -contains "Shell"
False  #Not an exact match

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $DomainServers -contains $thisComputer
True

PS> "abc", "def", "ghi" -contains "abc", "def"
False

PS> $a = "abc", "def"
PS> "abc", "def", "ghi" -contains $a
False
PS> $a, "ghi" -contains $a
True
```

### <a name="-notcontains"></a><span data-ttu-id="bea1a-253">-notcontains</span><span class="sxs-lookup"><span data-stu-id="bea1a-253">-notcontains</span></span>

<span data-ttu-id="bea1a-254">Description：包含运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-254">Description: Containment operator.</span></span> <span data-ttu-id="bea1a-255">指示引用值的集合是否包含一个测试值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-255">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="bea1a-256">始终返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-256">Always returns a Boolean value.</span></span> <span data-ttu-id="bea1a-257">如果测试值不是至少一个引用值的完全匹配项，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bea1a-257">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="bea1a-258">如果测试值是集合，则 NotContains 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="bea1a-258">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="bea1a-259">语法：</span><span class="sxs-lookup"><span data-stu-id="bea1a-259">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="bea1a-260">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-260">Examples:</span></span>

```powershell
PS> "Windows", "PowerShell" -notcontains "Shell"
True  #Not an exact match

# Get cmdlet parameters, but exclude common parameters
function get-parms ($cmdlet)
{
    $Common = "Verbose", "Debug", "WarningAction", "WarningVariable",
      "ErrorAction", "ErrorVariable", "OutVariable", "OutBuffer"

    $allparms = (Get-Command $Cmdlet).parametersets |
      foreach {$_.Parameters} |
        foreach {$_.Name} | Sort-Object | Get-Unique

    $allparms | where {$Common -notcontains $_ }
}

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $myVerbs = Get-Command -Module MyModule | foreach {$_.verb}
PS> $myVerbs | where {$ApprovedVerbs -notcontains $_}
ForEach
Sort
Tee
Where
```

### <a name="-in"></a><span data-ttu-id="bea1a-261">-in</span><span class="sxs-lookup"><span data-stu-id="bea1a-261">-in</span></span>

<span data-ttu-id="bea1a-262">说明： In 运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-262">Description: In operator.</span></span> <span data-ttu-id="bea1a-263">指示测试值是否显示在引用值的集合中。</span><span class="sxs-lookup"><span data-stu-id="bea1a-263">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="bea1a-264">始终以布尔值的形式返回。</span><span class="sxs-lookup"><span data-stu-id="bea1a-264">Always return as Boolean value.</span></span> <span data-ttu-id="bea1a-265">仅当测试值与至少一个引用值完全匹配时才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bea1a-265">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="bea1a-266">如果测试值是集合，则 In 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="bea1a-266">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="bea1a-267">仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bea1a-267">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="bea1a-268">此 `-in` 操作员是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="bea1a-268">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="bea1a-269">语法：</span><span class="sxs-lookup"><span data-stu-id="bea1a-269">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="bea1a-270">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-270">Examples:</span></span>

```powershell
PS> "def" -in "abc", "def"
True

PS> "Shell" -in "Windows", "PowerShell"
False  #Not an exact match

PS> "Windows" -in "Windows", "PowerShell"
True  #An exact match

PS> "Windows", "PowerShell" -in "Windows", "PowerShell", "ServerManager"
False  #Using reference equality

PS> $a = "Windows", "PowerShell"
PS> $a -in $a, "ServerManager"
True  #Using reference equality

# Does the list of computers in $DomainServers include $ThisComputer?
PS> $thisComputer -in  $domainServers
True
```

### <a name="-notin"></a><span data-ttu-id="bea1a-271">-notin</span><span class="sxs-lookup"><span data-stu-id="bea1a-271">-notin</span></span>

<span data-ttu-id="bea1a-272">说明：指示测试值是否显示在引用值的集合中。</span><span class="sxs-lookup"><span data-stu-id="bea1a-272">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="bea1a-273">始终返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-273">Always returns a Boolean value.</span></span> <span data-ttu-id="bea1a-274">如果测试值不是至少一个引用值的完全匹配项，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bea1a-274">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="bea1a-275">如果测试值是集合，则 In 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="bea1a-275">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="bea1a-276">仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="bea1a-276">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="bea1a-277">此 `-notin` 操作员是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="bea1a-277">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="bea1a-278">语法：</span><span class="sxs-lookup"><span data-stu-id="bea1a-278">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="bea1a-279">示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-279">Examples:</span></span>

```powershell
PS> "def" -notin "abc", "def"
False

PS> "ghi" -notin "abc", "def"
True

PS> "Shell" -notin "Windows", "PowerShell"
True  #Not an exact match

PS> "Windows" -notin "Windows", "PowerShell"
False  #An exact match

# Find unapproved verbs in the functions in my module
PS> $ApprovedVerbs = Get-Verb | foreach {$_.verb}
PS> $MyVerbs = Get-Command -Module MyModule | foreach {$_.verb}

PS> $MyVerbs | where {$_ -notin $ApprovedVerbs}
ForEach
Sort
Tee
Where
```

## <a name="replacement-operator"></a><span data-ttu-id="bea1a-280">替换运算符</span><span class="sxs-lookup"><span data-stu-id="bea1a-280">Replacement Operator</span></span>

<span data-ttu-id="bea1a-281">`-replace`运算符具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="bea1a-281">The `-replace` operator has the following syntax:</span></span>

`<input> -replace <original>, <substitute>`

<span data-ttu-id="bea1a-282">`<original>`占位符是与要替换的字符匹配的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="bea1a-282">The `<original>` placeholder is a regular expression matching the characters to be replaced.</span></span> <span data-ttu-id="bea1a-283">`<substitute>`占位符是替换它们的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="bea1a-283">The `<substitute>` placeholder is a literal string that replaces them.</span></span>

<span data-ttu-id="bea1a-284">使用正则表达式将运算符替换为指定值的全部或部分值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-284">The operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="bea1a-285">对于许多管理任务（如重命名文件），都可以使用运算符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-285">You can use the operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="bea1a-286">例如，以下命令将所有文件的文件扩展名更改 `.txt` 为 `.log` ：</span><span class="sxs-lookup"><span data-stu-id="bea1a-286">For example, the following command changes the file name extensions of all `.txt` files to `.log`:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

### <a name="case-sensitive-matches"></a><span data-ttu-id="bea1a-287">区分大小写的匹配</span><span class="sxs-lookup"><span data-stu-id="bea1a-287">Case-sensitive matches</span></span>

<span data-ttu-id="bea1a-288">默认情况下， `-replace` 运算符不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bea1a-288">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="bea1a-289">若要区分大小写，请使用 `-creplace` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-289">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="bea1a-290">若要使它显式不区分大小写，请使用 `-ireplace` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-290">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="bea1a-291">请开考虑以下示例：</span><span class="sxs-lookup"><span data-stu-id="bea1a-291">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
Cook
```

```powershell
PS> "book" -ireplace "B", "C"
Cook
```

```powershell
PS> "book" -creplace "B", "C"
book
```

### <a name="substitutions-in-regular-expressions"></a><span data-ttu-id="bea1a-292">正则表达式中的替换</span><span class="sxs-lookup"><span data-stu-id="bea1a-292">Substitutions in regular expressions</span></span>

<span data-ttu-id="bea1a-293">还可以使用正则表达式，使用捕获组和替换动态替换文本。</span><span class="sxs-lookup"><span data-stu-id="bea1a-293">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="bea1a-294">可以 `<substitute>` 使用分组标识符之前的美元符号 () 字符，在字符串中引用捕获组 `$` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-294">Capture groups can be referenced in the `<substitute>` string using the dollar sign (`$`) character before the group identifier.</span></span>

<span data-ttu-id="bea1a-295">捕获组可以按 **数字** 或 **名称** 引用</span><span class="sxs-lookup"><span data-stu-id="bea1a-295">Capture groups can be referenced by **Number** or **Name**</span></span>

- <span data-ttu-id="bea1a-296">按 **编号** 捕获组按从左到右的顺序进行编号。</span><span class="sxs-lookup"><span data-stu-id="bea1a-296">By **Number** - Capturing Groups are numbered from left to right.</span></span>

  ```powershell
  PS> "John D. Smith" -replace "(\w+) (\w+)\. (\w+)", '$1.$2.$3@contoso.com'
  John.D.Smith@contoso.com
  ```

- <span data-ttu-id="bea1a-297">通过 **名称** ，也可以按名称引用捕获组。</span><span class="sxs-lookup"><span data-stu-id="bea1a-297">By **Name** - Capturing Groups can also be referenced by name.</span></span>

  ```powershell
  PS> "CONTOSO\Administrator" -replace '\w+\\(?<user>\w+)', 'FABRIKAM\${user}'
  FABRIKAM\Administrator
  ```

> [!WARNING]
> <span data-ttu-id="bea1a-298">由于 `$` 字符是在字符串扩展中使用的，因此必须使用文本字符串或对字符进行转义 `$` 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-298">Since the `$` character is used in string expansion, you will must use literal strings or escape the `$` character.</span></span>
>
> ```powershell
> PS> 'Hello World' -replace '(\w+) \w+', "`$1 Universe"
> Hello Universe
> ```
>
> <span data-ttu-id="bea1a-299">此外，由于 `$` 字符用于替换，因此必须对字符串中的任何实例进行转义。</span><span class="sxs-lookup"><span data-stu-id="bea1a-299">Additionally, since the `$` character is used in substitution, you must escape any instances in your string.</span></span>
>
> ```powershell
> PS> '5.72' -replace '(.+)', '$$$1'
> $5.72
> ```

<span data-ttu-id="bea1a-300">若要了解详细信息，请参阅[正则表达式中的](/dotnet/standard/base-types/substitutions-in-regular-expressions) [about_Regular_Expressions](about_Regular_Expressions.md)和替换</span><span class="sxs-lookup"><span data-stu-id="bea1a-300">To learn more see [about_Regular_Expressions](about_Regular_Expressions.md) and [Substitutions in Regular Expressions](/dotnet/standard/base-types/substitutions-in-regular-expressions)</span></span>

### <a name="substituting-in-a-collection"></a><span data-ttu-id="bea1a-301">在集合中替换</span><span class="sxs-lookup"><span data-stu-id="bea1a-301">Substituting in a collection</span></span>

<span data-ttu-id="bea1a-302">如果 `<input>` 到运算符为 `-replace` 集合，则 PowerShell 会将替换应用于集合中的每个值。</span><span class="sxs-lookup"><span data-stu-id="bea1a-302">When the `<input>` to the `-replace` operator is a collection, PowerShell applies the replacement to every value in the collection.</span></span> <span data-ttu-id="bea1a-303">例如：</span><span class="sxs-lookup"><span data-stu-id="bea1a-303">For example:</span></span>

```powershell
"B1","B2","B3","B4","B5" -replace "B", 'a'
a1
a2
a3
a4
a5
```

### <a name="scriptblock-substitutions"></a><span data-ttu-id="bea1a-304">ScriptBlock 替换</span><span class="sxs-lookup"><span data-stu-id="bea1a-304">ScriptBlock substitutions</span></span>

<span data-ttu-id="bea1a-305">从 PowerShell 6 开始，可以将 **ScriptBlock** 参数用于 _替代_ 文本。</span><span class="sxs-lookup"><span data-stu-id="bea1a-305">Beginning in PowerShell 6, you can use a **ScriptBlock** argument for the _Substitution_ text.</span></span> <span data-ttu-id="bea1a-306">将对 _输入_ 字符串中找到的每个匹配项执行 **ScriptBlock** 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-306">The **ScriptBlock** will execute for each match found in the _input_ string.</span></span>

<span data-ttu-id="bea1a-307">在 **ScriptBlock** 内，使用 `$_` 自动变量来引用当前的 **system.text.regularexpressions** 对象。</span><span class="sxs-lookup"><span data-stu-id="bea1a-307">Within the **ScriptBlock**, use the `$_` automatic variable to refer to the current **System.Text.RegularExpressions.Match** object.</span></span> <span data-ttu-id="bea1a-308">**Match** 对象使您可以访问要替换的当前输入文本以及其他有用信息。</span><span class="sxs-lookup"><span data-stu-id="bea1a-308">The **Match** object gives you access to the current input text being replaced, as well as other useful information.</span></span>

<span data-ttu-id="bea1a-309">此示例将三个小数的每个序列替换为等效字符。</span><span class="sxs-lookup"><span data-stu-id="bea1a-309">This example replaces each sequence of three decimals with the character equivalent.</span></span> <span data-ttu-id="bea1a-310">将为每个需要替换的三个小数组运行 **ScriptBlock** 。</span><span class="sxs-lookup"><span data-stu-id="bea1a-310">The **ScriptBlock** is run for each set of three decimals that needs to be replaced.</span></span>

```powershell
PS> "072101108108111" -replace "\d{3}", {[char][int]$_.Value}
Hello
```

## <a name="type-comparison"></a><span data-ttu-id="bea1a-311">类型比较</span><span class="sxs-lookup"><span data-stu-id="bea1a-311">Type comparison</span></span>

<span data-ttu-id="bea1a-312"> (和) 的类型比较运算符 `-is` `-isnot` 用于确定对象是否为特定类型。</span><span class="sxs-lookup"><span data-stu-id="bea1a-312">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

### <a name="-is"></a><span data-ttu-id="bea1a-313">-为</span><span class="sxs-lookup"><span data-stu-id="bea1a-313">-is</span></span>

<span data-ttu-id="bea1a-314">语法：</span><span class="sxs-lookup"><span data-stu-id="bea1a-314">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="bea1a-315">例如：</span><span class="sxs-lookup"><span data-stu-id="bea1a-315">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

### <a name="-isnot"></a><span data-ttu-id="bea1a-316">-isnot</span><span class="sxs-lookup"><span data-stu-id="bea1a-316">-isnot</span></span>

<span data-ttu-id="bea1a-317">语法：</span><span class="sxs-lookup"><span data-stu-id="bea1a-317">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="bea1a-318">例如：</span><span class="sxs-lookup"><span data-stu-id="bea1a-318">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="bea1a-319">请参阅</span><span class="sxs-lookup"><span data-stu-id="bea1a-319">See also</span></span>

- [<span data-ttu-id="bea1a-320">about_Operators</span><span class="sxs-lookup"><span data-stu-id="bea1a-320">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="bea1a-321">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="bea1a-321">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="bea1a-322">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="bea1a-322">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="bea1a-323">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="bea1a-323">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="bea1a-324">Foreach-对象</span><span class="sxs-lookup"><span data-stu-id="bea1a-324">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="bea1a-325">Where-Object</span><span class="sxs-lookup"><span data-stu-id="bea1a-325">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
