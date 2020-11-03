---
description: 描述在 PowerShell 中比较值的运算符。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Comparison_Operators
ms.openlocfilehash: d6096de14d0bb8c7ba86c0585806b86cf3bb921a
ms.sourcegitcommit: c9e56ec489522c706b8d6b8733f3f015d6d7e893
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200565"
---
# <a name="about-comparison-operators"></a><span data-ttu-id="dbb5c-104">关于比较运算符</span><span class="sxs-lookup"><span data-stu-id="dbb5c-104">About Comparison Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="dbb5c-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="dbb5c-105">Short description</span></span>
<span data-ttu-id="dbb5c-106">描述在 PowerShell 中比较值的运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-106">Describes the operators that compare values in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="dbb5c-107">长说明</span><span class="sxs-lookup"><span data-stu-id="dbb5c-107">Long description</span></span>

<span data-ttu-id="dbb5c-108">比较运算符使你可以指定比较值和查找与指定模式匹配的值的条件。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-108">Comparison operators let you specify conditions for comparing values and finding values that match specified patterns.</span></span> <span data-ttu-id="dbb5c-109">若要使用比较运算符，请指定要与这些值分隔的运算符进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-109">To use a comparison operator, specify the values that you want to compare together with an operator that separates these values.</span></span>

<span data-ttu-id="dbb5c-110">PowerShell 包含以下比较运算符：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-110">PowerShell includes the following comparison operators:</span></span>

| <span data-ttu-id="dbb5c-111">类型</span><span class="sxs-lookup"><span data-stu-id="dbb5c-111">Type</span></span>        | <span data-ttu-id="dbb5c-112">运算符</span><span class="sxs-lookup"><span data-stu-id="dbb5c-112">Operators</span></span>    | <span data-ttu-id="dbb5c-113">说明</span><span class="sxs-lookup"><span data-stu-id="dbb5c-113">Description</span></span>                                 |
| ----------- | ------------ | --------------------------------------------|
| <span data-ttu-id="dbb5c-114">等式</span><span class="sxs-lookup"><span data-stu-id="dbb5c-114">Equality</span></span>    | <span data-ttu-id="dbb5c-115">-eq</span><span class="sxs-lookup"><span data-stu-id="dbb5c-115">-eq</span></span>          | <span data-ttu-id="dbb5c-116">equals</span><span class="sxs-lookup"><span data-stu-id="dbb5c-116">equals</span></span>                                      |
|             | <span data-ttu-id="dbb5c-117">-ne</span><span class="sxs-lookup"><span data-stu-id="dbb5c-117">-ne</span></span>          | <span data-ttu-id="dbb5c-118">不等于</span><span class="sxs-lookup"><span data-stu-id="dbb5c-118">not equals</span></span>                                  |
|             | <span data-ttu-id="dbb5c-119">-gt</span><span class="sxs-lookup"><span data-stu-id="dbb5c-119">-gt</span></span>          | <span data-ttu-id="dbb5c-120">大于</span><span class="sxs-lookup"><span data-stu-id="dbb5c-120">greater than</span></span>                                |
|             | <span data-ttu-id="dbb5c-121">-ge</span><span class="sxs-lookup"><span data-stu-id="dbb5c-121">-ge</span></span>          | <span data-ttu-id="dbb5c-122">大于或等于</span><span class="sxs-lookup"><span data-stu-id="dbb5c-122">greater than or equal</span></span>                       |
|             | <span data-ttu-id="dbb5c-123">-lt</span><span class="sxs-lookup"><span data-stu-id="dbb5c-123">-lt</span></span>          | <span data-ttu-id="dbb5c-124">小于</span><span class="sxs-lookup"><span data-stu-id="dbb5c-124">less than</span></span>                                   |
|             | <span data-ttu-id="dbb5c-125">-le</span><span class="sxs-lookup"><span data-stu-id="dbb5c-125">-le</span></span>          | <span data-ttu-id="dbb5c-126">小于或等于</span><span class="sxs-lookup"><span data-stu-id="dbb5c-126">less than or equal</span></span>                          |
|             |              |                                             |
| <span data-ttu-id="dbb5c-127">Matching</span><span class="sxs-lookup"><span data-stu-id="dbb5c-127">Matching</span></span>    | <span data-ttu-id="dbb5c-128">-like</span><span class="sxs-lookup"><span data-stu-id="dbb5c-128">-like</span></span>        | <span data-ttu-id="dbb5c-129">如果字符串匹配通配符，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-129">Returns true when string matches wildcard</span></span>   |
|             |              | <span data-ttu-id="dbb5c-130">pattern</span><span class="sxs-lookup"><span data-stu-id="dbb5c-130">pattern</span></span>                                     |
|             | <span data-ttu-id="dbb5c-131">-notlike</span><span class="sxs-lookup"><span data-stu-id="dbb5c-131">-notlike</span></span>     | <span data-ttu-id="dbb5c-132">如果字符串不匹配，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-132">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="dbb5c-133">通配符模式</span><span class="sxs-lookup"><span data-stu-id="dbb5c-133">wildcard pattern</span></span>                            |
|             | <span data-ttu-id="dbb5c-134">-match</span><span class="sxs-lookup"><span data-stu-id="dbb5c-134">-match</span></span>       | <span data-ttu-id="dbb5c-135">如果字符串与正则表达式匹配，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-135">Returns true when string matches regex</span></span>      |
|             |              | <span data-ttu-id="dbb5c-136">化$matches 包含匹配的字符串</span><span class="sxs-lookup"><span data-stu-id="dbb5c-136">pattern; $matches contains matching strings</span></span> |
|             | <span data-ttu-id="dbb5c-137">-notmatch</span><span class="sxs-lookup"><span data-stu-id="dbb5c-137">-notmatch</span></span>    | <span data-ttu-id="dbb5c-138">如果字符串不匹配，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-138">Returns true when string does not match</span></span>     |
|             |              | <span data-ttu-id="dbb5c-139">regex 模式;$matches 包含匹配</span><span class="sxs-lookup"><span data-stu-id="dbb5c-139">regex pattern; $matches contains matching</span></span>   |
|             |              | <span data-ttu-id="dbb5c-140">字符串</span><span class="sxs-lookup"><span data-stu-id="dbb5c-140">strings</span></span>                                     |
|             |              |                                             |
| <span data-ttu-id="dbb5c-141">Containment</span><span class="sxs-lookup"><span data-stu-id="dbb5c-141">Containment</span></span> | <span data-ttu-id="dbb5c-142">-contains</span><span class="sxs-lookup"><span data-stu-id="dbb5c-142">-contains</span></span>    | <span data-ttu-id="dbb5c-143">如果引用值包含，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-143">Returns true when reference value contained</span></span> |
|             |              | <span data-ttu-id="dbb5c-144">在集合中</span><span class="sxs-lookup"><span data-stu-id="dbb5c-144">in a collection</span></span>                             |
|             | <span data-ttu-id="dbb5c-145">-notcontains</span><span class="sxs-lookup"><span data-stu-id="dbb5c-145">-notcontains</span></span> | <span data-ttu-id="dbb5c-146">如果引用值不为，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-146">Returns true when reference value not</span></span>       |
|             |              | <span data-ttu-id="dbb5c-147">包含在集合中</span><span class="sxs-lookup"><span data-stu-id="dbb5c-147">contained in a collection</span></span>                   |
|             | <span data-ttu-id="dbb5c-148">-in</span><span class="sxs-lookup"><span data-stu-id="dbb5c-148">-in</span></span>          | <span data-ttu-id="dbb5c-149">如果中包含的测试值为</span><span class="sxs-lookup"><span data-stu-id="dbb5c-149">Returns true when test value contained in a</span></span> |
|             |              | <span data-ttu-id="dbb5c-150">collection</span><span class="sxs-lookup"><span data-stu-id="dbb5c-150">collection</span></span>                                  |
|             | <span data-ttu-id="dbb5c-151">-notin</span><span class="sxs-lookup"><span data-stu-id="dbb5c-151">-notin</span></span>       | <span data-ttu-id="dbb5c-152">如果测试值不包含，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-152">Returns true when test value not contained</span></span>  |
|             |              | <span data-ttu-id="dbb5c-153">在集合中</span><span class="sxs-lookup"><span data-stu-id="dbb5c-153">in a collection</span></span>                             |
|             |              |                                             |
| <span data-ttu-id="dbb5c-154">Replacement</span><span class="sxs-lookup"><span data-stu-id="dbb5c-154">Replacement</span></span> | <span data-ttu-id="dbb5c-155">-replace</span><span class="sxs-lookup"><span data-stu-id="dbb5c-155">-replace</span></span>     | <span data-ttu-id="dbb5c-156">替换字符串模式</span><span class="sxs-lookup"><span data-stu-id="dbb5c-156">Replaces a string pattern</span></span>                   |
|             |              |                                             |
| <span data-ttu-id="dbb5c-157">类型</span><span class="sxs-lookup"><span data-stu-id="dbb5c-157">Type</span></span>        | <span data-ttu-id="dbb5c-158">-为</span><span class="sxs-lookup"><span data-stu-id="dbb5c-158">-is</span></span>          | <span data-ttu-id="dbb5c-159">如果两个对象相同，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-159">Returns true if both object are the same</span></span>    |
|             |              | <span data-ttu-id="dbb5c-160">类型</span><span class="sxs-lookup"><span data-stu-id="dbb5c-160">type</span></span>                                        |
|             | <span data-ttu-id="dbb5c-161">-isnot</span><span class="sxs-lookup"><span data-stu-id="dbb5c-161">-isnot</span></span>       | <span data-ttu-id="dbb5c-162">如果对象不相同，则返回 true</span><span class="sxs-lookup"><span data-stu-id="dbb5c-162">Returns true if the objects are not the same</span></span>|
|             |              | <span data-ttu-id="dbb5c-163">类型</span><span class="sxs-lookup"><span data-stu-id="dbb5c-163">type</span></span>                                        |

<span data-ttu-id="dbb5c-164">默认情况下，所有比较运算符都不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-164">By default, all comparison operators are case-insensitive.</span></span> <span data-ttu-id="dbb5c-165">若要使比较运算符区分大小写，请在运算符名称之前加 `c` 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-165">To make a comparison operator case-sensitive, precede the operator name with a `c`.</span></span> <span data-ttu-id="dbb5c-166">例如，区分大小写的版本 `-eq` 为 `-ceq` 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-166">For example, the case-sensitive version of `-eq` is `-ceq`.</span></span> <span data-ttu-id="dbb5c-167">若要使不区分大小写的显式，请在运算符前面加上 `i` 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-167">To make the case-insensitivity explicit, precede the operator with an `i`.</span></span> <span data-ttu-id="dbb5c-168">例如，的显式不区分大小写的版本 `-eq` 为 `-ieq` 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-168">For example, the explicitly case-insensitive version of `-eq` is `-ieq`.</span></span>

<span data-ttu-id="dbb5c-169">当运算符的输入是标量值时，比较运算符将返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-169">When the input to an operator is a scalar value, comparison operators return a Boolean value.</span></span> <span data-ttu-id="dbb5c-170">当输入是值的集合时，比较运算符返回任何匹配值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-170">When the input is a collection of values, the comparison operators return any matching values.</span></span> <span data-ttu-id="dbb5c-171">如果集合中没有匹配项，则比较运算符返回空数组。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-171">If there are no matches in a collection, comparison operators return an empty array.</span></span>

```powershell
PS> (1, 2 -eq 3).GetType().FullName
System.Object[]
```

<span data-ttu-id="dbb5c-172">例外情况包括：包含运算符、In 运算符和类型运算符，它们始终返回 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-172">The exceptions are the containment operators, the In operators, and the type operators, which always return a **Boolean** value.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb5c-173">如果需要比较值， `$null` 应将该值放 `$null` 在比较的左侧。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-173">If you need to compare a value to `$null` you should put `$null` on the left-hand side of the comparison.</span></span> <span data-ttu-id="dbb5c-174">当与 `$null` **对象 []** 进行比较时，结果为 **False** ，因为比较对象是一个数组。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-174">When you compare `$null` to an **Object[]** the result is **False** because the comparison object is an array.</span></span> <span data-ttu-id="dbb5c-175">将数组与进行比较时 `$null` ，比较筛选出 `$null` 存储在数组中的所有值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-175">When you compare an array to `$null`, the comparison filters out any `$null` values stored in the array.</span></span> <span data-ttu-id="dbb5c-176">例如：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-176">For example:</span></span>
>
> ```powershell
> PS> $null -ne $null, "hello"
> True
> PS> $null, "hello" -ne $null
> hello
> ```

### <a name="equality-operators"></a><span data-ttu-id="dbb5c-177">相等运算符</span><span class="sxs-lookup"><span data-stu-id="dbb5c-177">Equality Operators</span></span>

<span data-ttu-id="dbb5c-178">相等运算符 (`-eq` ， `-ne`) 在一个或多个输入值与指定模式相同时返回值或匹配项。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-178">The equality operators (`-eq`, `-ne`) return a value of TRUE or the matches when one or more of the input values is identical to the specified pattern.</span></span> <span data-ttu-id="dbb5c-179">整个模式必须匹配整个值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-179">The entire pattern must match an entire value.</span></span>

<span data-ttu-id="dbb5c-180">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-180">Example:</span></span>

#### <a name="-eq"></a><span data-ttu-id="dbb5c-181">-eq</span><span class="sxs-lookup"><span data-stu-id="dbb5c-181">-eq</span></span>

<span data-ttu-id="dbb5c-182">说明：等于。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-182">Description: Equal to.</span></span> <span data-ttu-id="dbb5c-183">包含相同的值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-183">Includes an identical value.</span></span>

<span data-ttu-id="dbb5c-184">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-184">Example:</span></span>

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

#### <a name="-ne"></a><span data-ttu-id="dbb5c-185">-ne</span><span class="sxs-lookup"><span data-stu-id="dbb5c-185">-ne</span></span>

<span data-ttu-id="dbb5c-186">说明：不等于。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-186">Description: Not equal to.</span></span> <span data-ttu-id="dbb5c-187">包含不同的值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-187">Includes a different value.</span></span>

<span data-ttu-id="dbb5c-188">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-188">Example:</span></span>

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

#### <a name="-gt"></a><span data-ttu-id="dbb5c-189">-gt</span><span class="sxs-lookup"><span data-stu-id="dbb5c-189">-gt</span></span>

<span data-ttu-id="dbb5c-190">说明：大于。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-190">Description: Greater-than.</span></span>

<span data-ttu-id="dbb5c-191">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-191">Example:</span></span>

```powershell
PS> 8 -gt 6
True

PS> 7, 8, 9 -gt 8
9
```

> [!NOTE]
> <span data-ttu-id="dbb5c-192">这不应与 `>` 其他许多编程语言中的大于运算符混淆。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-192">This should not to be confused with `>`, the greater-than operator in many other programming languages.</span></span> <span data-ttu-id="dbb5c-193">在 PowerShell 中， `>` 用于重定向。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-193">In PowerShell, `>` is used for redirection.</span></span> <span data-ttu-id="dbb5c-194">有关详细信息，请参阅 [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators)。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-194">For more information, see [About_redirection](about_Redirection.md#potential-confusion-with-comparison-operators).</span></span>

#### <a name="-ge"></a><span data-ttu-id="dbb5c-195">-ge</span><span class="sxs-lookup"><span data-stu-id="dbb5c-195">-ge</span></span>

<span data-ttu-id="dbb5c-196">说明：大于或等于。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-196">Description: Greater-than or equal to.</span></span>

<span data-ttu-id="dbb5c-197">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-197">Example:</span></span>

```powershell
PS> 8 -ge 8
True

PS> 7, 8, 9 -ge 8
8
9
```

#### <a name="-lt"></a><span data-ttu-id="dbb5c-198">-lt</span><span class="sxs-lookup"><span data-stu-id="dbb5c-198">-lt</span></span>

<span data-ttu-id="dbb5c-199">说明：小于。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-199">Description: Less-than.</span></span>

<span data-ttu-id="dbb5c-200">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-200">Example:</span></span>

```powershell

PS> 8 -lt 6
False

PS> 7, 8, 9 -lt 8
7
```

#### <a name="-le"></a><span data-ttu-id="dbb5c-201">-le</span><span class="sxs-lookup"><span data-stu-id="dbb5c-201">-le</span></span>

<span data-ttu-id="dbb5c-202">说明：小于或等于。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-202">Description: Less-than or equal to.</span></span>

<span data-ttu-id="dbb5c-203">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-203">Example:</span></span>

```powershell
PS> 6 -le 8
True

PS> 7, 8, 9 -le 8
7
8
```

### <a name="matching-operators"></a><span data-ttu-id="dbb5c-204">匹配运算符</span><span class="sxs-lookup"><span data-stu-id="dbb5c-204">Matching Operators</span></span>

<span data-ttu-id="dbb5c-205">Like 运算符 (`-like` 和 `-notlike`) 使用通配符表达式查找匹配或与指定模式不匹配的元素。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-205">The like operators (`-like` and `-notlike`) find elements that match or do not match a specified pattern using wildcard expressions.</span></span>

<span data-ttu-id="dbb5c-206">语法为：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-206">The syntax is:</span></span>

```powershell
<string[]> -like <wildcard-expression>
<string[]> -notlike <wildcard-expression>
```

<span data-ttu-id="dbb5c-207">匹配运算符 (`-match` 和 `-notmatch`) 使用正则表达式查找匹配或与指定模式不匹配的元素。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-207">The match operators (`-match` and `-notmatch`) find elements that match or do not match a specified pattern using regular expressions.</span></span>

<span data-ttu-id="dbb5c-208">`$Matches`当输入 (左侧参数) 为单个标量对象时，匹配运算符将填充自动变量。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-208">The match operators populate the `$Matches` automatic variable when the input (the left-side argument) to the operator is a single scalar object.</span></span> <span data-ttu-id="dbb5c-209">当输入是标量时， `-match` 和 `-notmatch` 运算符将返回一个布尔值，并将自动变量的值设置 `$Matches` 为参数的匹配组件。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-209">When the input is scalar, the `-match` and `-notmatch` operators return a Boolean value and set the value of the `$Matches` automatic variable to the matched components of the argument.</span></span>

<span data-ttu-id="dbb5c-210">语法为：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-210">The syntax is:</span></span>

```powershell
<string[]> -match <regular-expression>
<string[]> -notmatch <regular-expression>
```

#### <a name="-like"></a><span data-ttu-id="dbb5c-211">-like</span><span class="sxs-lookup"><span data-stu-id="dbb5c-211">-like</span></span>

<span data-ttu-id="dbb5c-212">说明：使用通配符)  (匹配 \* 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-212">Description: Match using the wildcard character (\*).</span></span>

<span data-ttu-id="dbb5c-213">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-213">Example:</span></span>

```powershell
PS> "PowerShell" -like "*shell"
True

PS> "PowerShell", "Server" -like "*shell"
PowerShell
```

#### <a name="-notlike"></a><span data-ttu-id="dbb5c-214">-notlike</span><span class="sxs-lookup"><span data-stu-id="dbb5c-214">-notlike</span></span>

<span data-ttu-id="dbb5c-215">说明：使用通配符 () 不匹配 \* 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-215">Description: Does not match using the wildcard character (\*).</span></span>

<span data-ttu-id="dbb5c-216">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-216">Example:</span></span>

```powershell
PS> "PowerShell" -notlike "*shell"
False

PS> "PowerShell", "Server" -notlike "*shell"
Server
```

### <a name="-match"></a><span data-ttu-id="dbb5c-217">-match</span><span class="sxs-lookup"><span data-stu-id="dbb5c-217">-match</span></span>

<span data-ttu-id="dbb5c-218">说明：使用正则表达式匹配字符串。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-218">Description: Matches a string using regular expressions.</span></span> <span data-ttu-id="dbb5c-219">当输入是标量时，它将填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-219">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="dbb5c-220">如果输入是集合，则 `-match` 和 `-notmatch` 运算符返回该集合的匹配成员，但是运算符不填充该 `$Matches` 变量。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-220">If the input is a collection, the `-match` and `-notmatch` operators return the matching members of that collection, but the operator does not populate the `$Matches` variable.</span></span>

<span data-ttu-id="dbb5c-221">例如，以下命令将字符串的集合提交给 `-match` 运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-221">For example, the following command submits a collection of strings to the `-match` operator.</span></span> <span data-ttu-id="dbb5c-222">`-match`运算符返回集合中的匹配项。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-222">The `-match` operator returns the items in the collection that match.</span></span> <span data-ttu-id="dbb5c-223">它不填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-223">It does not populate the `$Matches` automatic variable.</span></span>

```powershell
PS> "Sunday", "Monday", "Tuesday" -match "sun"
Sunday

PS> $Matches
PS>
```

<span data-ttu-id="dbb5c-224">与此相反，以下命令将单个字符串提交给 `-match` 运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-224">In contrast, the following command submits a single string to the `-match` operator.</span></span> <span data-ttu-id="dbb5c-225">`-match`运算符返回布尔值并填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-225">The `-match` operator returns a Boolean value and populates the `$Matches` automatic variable.</span></span> <span data-ttu-id="dbb5c-226">`$Matches`自动变量是 **哈希表** 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-226">The `$Matches` automatic variable is a **Hashtable** .</span></span> <span data-ttu-id="dbb5c-227">如果未使用分组或捕获，则只填充一个键。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-227">If no grouping or capturing is used, only one key is populated.</span></span>
<span data-ttu-id="dbb5c-228">`0`键表示匹配的所有文本。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-228">The `0` key represents all text that was matched.</span></span> <span data-ttu-id="dbb5c-229">有关使用正则表达式进行分组和捕获的详细信息，请参阅 [about_Regular_Expressions](about_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-229">For more information about grouping and capturing using regular expressions, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

```powershell
PS> "Sunday" -match "sun"
True

PS> $Matches

Name                           Value
----                           -----
0                              Sun
```

<span data-ttu-id="dbb5c-230">请注意， `$Matches` 哈希表只包含任何匹配模式的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-230">It is important to note that the `$Matches` hashtable will only contain the first occurrence of any matching pattern.</span></span>

```powershell
PS> "Banana" -match "na"
True

PS> $Matches

Name                           Value
----                           -----
0                              na
```

> [!IMPORTANT]
> <span data-ttu-id="dbb5c-231">`0`该键是一个 **整数** 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-231">The `0` key is an **Integer** .</span></span> <span data-ttu-id="dbb5c-232">您可以使用任何 **哈希表** 方法来访问存储的值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-232">You can use any **Hashtable** method to access the value stored.</span></span>
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

<span data-ttu-id="dbb5c-233">`-notmatch` `$Matches` 当输入是标量时，运算符将填充自动变量，并且在检测到匹配项时，结果为 False。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-233">The `-notmatch` operator populates the `$Matches` automatic variable when the input is scalar and the result is False, that it, when it detects a match.</span></span>

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

#### <a name="-notmatch"></a><span data-ttu-id="dbb5c-234">-notmatch</span><span class="sxs-lookup"><span data-stu-id="dbb5c-234">-notmatch</span></span>

<span data-ttu-id="dbb5c-235">说明：不匹配字符串。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-235">Description: Does not match a string.</span></span> <span data-ttu-id="dbb5c-236">使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-236">Uses regular expressions.</span></span> <span data-ttu-id="dbb5c-237">当输入是标量时，它将填充 `$Matches` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-237">When the input is scalar, it populates the `$Matches` automatic variable.</span></span>

<span data-ttu-id="dbb5c-238">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-238">Example:</span></span>

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

### <a name="containment-operators"></a><span data-ttu-id="dbb5c-239">包含运算符</span><span class="sxs-lookup"><span data-stu-id="dbb5c-239">Containment Operators</span></span>

<span data-ttu-id="dbb5c-240">包含运算符 (`-contains` 和 `-notcontains`) 类似于相等运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-240">The containment operators (`-contains` and `-notcontains`) are similar to the equality operators.</span></span> <span data-ttu-id="dbb5c-241">但是，包含运算符始终返回布尔值，即使输入是集合也是如此。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-241">However, the containment operators always return a Boolean value, even when the input is a collection.</span></span>

<span data-ttu-id="dbb5c-242">另外，与相等运算符不同，包含运算符在检测到第一个匹配项后就会返回一个值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-242">Also, unlike the equality operators, the containment operators return a value as soon as they detect the first match.</span></span> <span data-ttu-id="dbb5c-243">相等运算符计算所有输入，然后返回集合中的所有匹配项。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-243">The equality operators evaluate all input and then return all the matches in the collection.</span></span>

#### <a name="-contains"></a><span data-ttu-id="dbb5c-244">-contains</span><span class="sxs-lookup"><span data-stu-id="dbb5c-244">-contains</span></span>

<span data-ttu-id="dbb5c-245">Description：包含运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-245">Description: Containment operator.</span></span> <span data-ttu-id="dbb5c-246">指示引用值的集合是否包含一个测试值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-246">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="dbb5c-247">始终返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-247">Always returns a Boolean value.</span></span> <span data-ttu-id="dbb5c-248">仅当测试值与至少一个引用值完全匹配时才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-248">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="dbb5c-249">如果测试值是集合，则 Contains 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-249">When the test value is a collection, the Contains operator uses reference equality.</span></span> <span data-ttu-id="dbb5c-250">仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-250">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="dbb5c-251">在非常大的集合中， `-contains` 运算符比等于运算符更快地返回结果。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-251">In a very large collection, the `-contains` operator returns results quicker than the equal to operator.</span></span>

<span data-ttu-id="dbb5c-252">语法：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-252">Syntax:</span></span>

`<Reference-values> -contains <Test-value>`

<span data-ttu-id="dbb5c-253">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-253">Examples:</span></span>

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

#### <a name="-notcontains"></a><span data-ttu-id="dbb5c-254">-notcontains</span><span class="sxs-lookup"><span data-stu-id="dbb5c-254">-notcontains</span></span>

<span data-ttu-id="dbb5c-255">Description：包含运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-255">Description: Containment operator.</span></span> <span data-ttu-id="dbb5c-256">指示引用值的集合是否包含一个测试值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-256">Tells whether a collection of reference values includes a single test value.</span></span> <span data-ttu-id="dbb5c-257">始终返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-257">Always returns a Boolean value.</span></span> <span data-ttu-id="dbb5c-258">如果测试值不是至少一个引用值的完全匹配项，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-258">Returns TRUE when the test value is not an exact matches for at least one of the reference values.</span></span>

<span data-ttu-id="dbb5c-259">如果测试值是集合，则 NotContains 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-259">When the test value is a collection, the NotContains operator uses reference equality.</span></span>

<span data-ttu-id="dbb5c-260">语法：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-260">Syntax:</span></span>

`<Reference-values> -notcontains <Test-value>`

<span data-ttu-id="dbb5c-261">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-261">Examples:</span></span>

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

#### <a name="-in"></a><span data-ttu-id="dbb5c-262">-in</span><span class="sxs-lookup"><span data-stu-id="dbb5c-262">-in</span></span>

<span data-ttu-id="dbb5c-263">说明： In 运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-263">Description: In operator.</span></span> <span data-ttu-id="dbb5c-264">指示测试值是否显示在引用值的集合中。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-264">Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="dbb5c-265">始终以布尔值的形式返回。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-265">Always return as Boolean value.</span></span> <span data-ttu-id="dbb5c-266">仅当测试值与至少一个引用值完全匹配时才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-266">Returns TRUE only when the test value exactly matches at least one of the reference values.</span></span>

<span data-ttu-id="dbb5c-267">如果测试值是集合，则 In 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-267">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="dbb5c-268">仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-268">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="dbb5c-269">此 `-in` 操作员是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-269">The `-in` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="dbb5c-270">语法：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-270">Syntax:</span></span>

`<Test-value> -in <Reference-values>`

<span data-ttu-id="dbb5c-271">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-271">Examples:</span></span>

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

#### <a name="-notin"></a><span data-ttu-id="dbb5c-272">-notin</span><span class="sxs-lookup"><span data-stu-id="dbb5c-272">-notin</span></span>

<span data-ttu-id="dbb5c-273">说明：指示测试值是否显示在引用值的集合中。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-273">Description: Tells whether a test value appears in a collection of reference values.</span></span> <span data-ttu-id="dbb5c-274">始终返回一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-274">Always returns a Boolean value.</span></span> <span data-ttu-id="dbb5c-275">如果测试值不是至少一个引用值的完全匹配项，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-275">Returns TRUE when the test value is not an exact match for at least one of the reference values.</span></span>

<span data-ttu-id="dbb5c-276">如果测试值是集合，则 In 运算符使用引用相等性。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-276">When the test value is a collection, the In operator uses reference equality.</span></span>
<span data-ttu-id="dbb5c-277">仅当其中一个引用值为测试值对象的同一实例时，它才返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-277">It returns TRUE only when one of the reference values is the same instance of the test value object.</span></span>

<span data-ttu-id="dbb5c-278">此 `-notin` 操作员是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-278">The `-notin` operator was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="dbb5c-279">语法：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-279">Syntax:</span></span>

`<Test-value> -notin <Reference-values>`

<span data-ttu-id="dbb5c-280">示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-280">Examples:</span></span>

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

### <a name="replacement-operator"></a><span data-ttu-id="dbb5c-281">替换运算符</span><span class="sxs-lookup"><span data-stu-id="dbb5c-281">Replacement Operator</span></span>

<span data-ttu-id="dbb5c-282">`-replace`使用正则表达式将运算符替换为指定值的全部或部分值。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-282">The `-replace` operator replaces all or part of a value with the specified value using regular expressions.</span></span> <span data-ttu-id="dbb5c-283">`-replace`对于许多管理任务（如重命名文件），都可以使用运算符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-283">You can use the `-replace` operator for many administrative tasks, such as renaming files.</span></span> <span data-ttu-id="dbb5c-284">例如，以下命令将所有 .txt 文件的文件扩展名更改为 .log：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-284">For example, the following command changes the file name extensions of all .txt files to .log:</span></span>

```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.name -replace '\.txt$','.log' }
```

<span data-ttu-id="dbb5c-285">运算符的语法如下所示 `-replace` ，其中 `<original>` 占位符表示要替换的字符， `<substitute>` 占位符表示将替换它们的字符：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-285">The syntax of the `-replace` operator is as follows, where the `<original>` placeholder represents the characters to be replaced, and the `<substitute>` placeholder represents the characters that will replace them:</span></span>

`<input> <operator> <original>, <substitute>`

<span data-ttu-id="dbb5c-286">默认情况下， `-replace` 运算符不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-286">By default, the `-replace` operator is case-insensitive.</span></span> <span data-ttu-id="dbb5c-287">若要区分大小写，请使用 `-creplace` 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-287">To make it case sensitive, use `-creplace`.</span></span> <span data-ttu-id="dbb5c-288">若要使它显式不区分大小写，请使用 `-ireplace` 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-288">To make it explicitly case-insensitive, use `-ireplace`.</span></span>

<span data-ttu-id="dbb5c-289">请考虑以下示例：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-289">Consider the following examples:</span></span>

```powershell
PS> "book" -replace "B", "C"
```

```Output
Cook
```

```powershell
"book" -ireplace "B", "C"
```

```Output
Cook
```

```powershell
"book" -creplace "B", "C"
```

```Output
book
```

<span data-ttu-id="dbb5c-290">还可以使用正则表达式，使用捕获组和替换动态替换文本。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-290">It is also possible to use regular expressions to dynamically replace text using capturing groups, and substitutions.</span></span> <span data-ttu-id="dbb5c-291">有关详细信息，请参阅 [about_Regular_Expressions](about_Regular_Expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-291">For more information, see [about_Regular_Expressions](about_Regular_Expressions.md).</span></span>

### <a name="scriptblock-substitutions"></a><span data-ttu-id="dbb5c-292">ScriptBlock 替换</span><span class="sxs-lookup"><span data-stu-id="dbb5c-292">ScriptBlock substitutions</span></span>

<span data-ttu-id="dbb5c-293">从 PowerShell 6 开始，可以将 **ScriptBlock** 参数用于 *替代* 文本。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-293">Beginning in PowerShell 6, you can use a **ScriptBlock** argument for the *Substitution* text.</span></span> <span data-ttu-id="dbb5c-294">将对 *输入* 字符串中找到的每个匹配项执行 **ScriptBlock** 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-294">The **ScriptBlock** will execute for each match found in the *input* string.</span></span>

<span data-ttu-id="dbb5c-295">在 **ScriptBlock** 内，使用 `$_` 自动变量来引用当前的 **system.text.regularexpressions** 对象。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-295">Within the **ScriptBlock** , use the `$_` automatic variable to refer to the current **System.Text.RegularExpressions.Match** object.</span></span> <span data-ttu-id="dbb5c-296">**Match** 对象使您可以访问要替换的当前输入文本以及其他有用信息。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-296">The **Match** object gives you access to the current input text being replaced, as well as other useful information.</span></span>

<span data-ttu-id="dbb5c-297">此示例将三个小数的每个序列替换为等效字符。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-297">This example replaces each sequence of three decimals with the character equivalent.</span></span> <span data-ttu-id="dbb5c-298">将为每个需要替换的三个小数组运行 **ScriptBlock** 。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-298">The **ScriptBlock** is run for each set of three decimals that needs to be replaced.</span></span>

```powershell
PS> "072101108108111" -replace "\d{3}", {[char][int]$_.Value}
Hello
```

### <a name="type-comparison"></a><span data-ttu-id="dbb5c-299">类型比较</span><span class="sxs-lookup"><span data-stu-id="dbb5c-299">Type comparison</span></span>

<span data-ttu-id="dbb5c-300"> (和) 的类型比较运算符 `-is` `-isnot` 用于确定对象是否为特定类型。</span><span class="sxs-lookup"><span data-stu-id="dbb5c-300">The type comparison operators (`-is` and `-isnot`) are used to determine if an object is a specific type.</span></span>

#### <a name="-is"></a><span data-ttu-id="dbb5c-301">-为</span><span class="sxs-lookup"><span data-stu-id="dbb5c-301">-is</span></span>

<span data-ttu-id="dbb5c-302">语法：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-302">Syntax:</span></span>

`<object> -is <type reference>`

<span data-ttu-id="dbb5c-303">例如：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-303">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -is [int]
True
PS> $a -is $b.GetType()
False
```

#### <a name="-isnot"></a><span data-ttu-id="dbb5c-304">-isnot</span><span class="sxs-lookup"><span data-stu-id="dbb5c-304">-isnot</span></span>

<span data-ttu-id="dbb5c-305">语法：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-305">Syntax:</span></span>

`<object> -isnot <type reference>`

<span data-ttu-id="dbb5c-306">例如：</span><span class="sxs-lookup"><span data-stu-id="dbb5c-306">Example:</span></span>

```powershell
PS> $a = 1
PS> $b = "1"
PS> $a -isnot $b.GetType()
True
PS> $b -isnot [int]
True
```

## <a name="see-also"></a><span data-ttu-id="dbb5c-307">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbb5c-307">SEE ALSO</span></span>

- [<span data-ttu-id="dbb5c-308">about_Operators</span><span class="sxs-lookup"><span data-stu-id="dbb5c-308">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="dbb5c-309">about_Regular_Expressions</span><span class="sxs-lookup"><span data-stu-id="dbb5c-309">about_Regular_Expressions</span></span>](about_Regular_Expressions.md)
- [<span data-ttu-id="dbb5c-310">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="dbb5c-310">about_Wildcards</span></span>](about_Wildcards.md)
- [<span data-ttu-id="dbb5c-311">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="dbb5c-311">Compare-Object</span></span>](xref:Microsoft.PowerShell.Utility.Compare-Object)
- [<span data-ttu-id="dbb5c-312">Foreach-对象</span><span class="sxs-lookup"><span data-stu-id="dbb5c-312">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
- [<span data-ttu-id="dbb5c-313">Where-Object</span><span class="sxs-lookup"><span data-stu-id="dbb5c-313">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
