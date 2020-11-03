---
description: 整数和实数可以具有类型和乘数后缀。
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 关于数字文本
ms.openlocfilehash: 99fa8c1a751551d028fe6df0b0cec94e07f19c59
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200670"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="c0ca9-103">关于数字文本</span><span class="sxs-lookup"><span data-stu-id="c0ca9-103">About numeric literals</span></span>

<span data-ttu-id="c0ca9-104">有两种类型的数值：整数和实数。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="c0ca9-105">两者都可以具有类型和乘数后缀。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="c0ca9-106">整数文本</span><span class="sxs-lookup"><span data-stu-id="c0ca9-106">Integer literals</span></span>

<span data-ttu-id="c0ca9-107">整数文本可以用十进制或十六进制表示法来编写。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="c0ca9-108">十六进制文本 `0x` 以为前缀，以将它们与十进制数区分开来。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="c0ca9-109">整数文本可以具有类型后缀和乘数后缀。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="c0ca9-110">Suffix</span><span class="sxs-lookup"><span data-stu-id="c0ca9-110">Suffix</span></span> |       <span data-ttu-id="c0ca9-111">含义</span><span class="sxs-lookup"><span data-stu-id="c0ca9-111">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="c0ca9-112">l</span><span class="sxs-lookup"><span data-stu-id="c0ca9-112">l</span></span>      | <span data-ttu-id="c0ca9-113">long 数据类型</span><span class="sxs-lookup"><span data-stu-id="c0ca9-113">long data type</span></span>      |
| <span data-ttu-id="c0ca9-114">kb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-114">kb</span></span>     | <span data-ttu-id="c0ca9-115">kb 乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-115">kilobyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-116">mb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-116">mb</span></span>     | <span data-ttu-id="c0ca9-117">兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-117">megabyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-118">内存</span><span class="sxs-lookup"><span data-stu-id="c0ca9-118">gb</span></span>     | <span data-ttu-id="c0ca9-119">千兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-119">gigabyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-120">tb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-120">tb</span></span>     | <span data-ttu-id="c0ca9-121">tb 乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-121">terabyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-122">容量</span><span class="sxs-lookup"><span data-stu-id="c0ca9-122">pb</span></span>     | <span data-ttu-id="c0ca9-123">pb 乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-123">petabyte multiplier</span></span> |

<span data-ttu-id="c0ca9-124">整数文本的类型由其值、类型后缀和数值乘数后缀确定。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-124">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="c0ca9-125">对于无类型后缀的整数文本：</span><span class="sxs-lookup"><span data-stu-id="c0ca9-125">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="c0ca9-126">如果值可以通过类型表示 `[int]` ，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-126">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="c0ca9-127">否则，如果该值可以由类型表示 `[long]` ，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-127">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="c0ca9-128">否则，如果该值可以由类型表示 `[decimal]` ，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-128">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="c0ca9-129">否则，它由类型表示 `[double]` 。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-129">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="c0ca9-130">对于类型为后缀的整数文本：</span><span class="sxs-lookup"><span data-stu-id="c0ca9-130">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="c0ca9-131">如果类型后缀为 `u` ，并且值可由类型表示， `[int]` 则其类型为 `[int]` 。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-131">If the type suffix is `u` and the value can be represented by type `[int]` then its type is `[int]`.</span></span>
- <span data-ttu-id="c0ca9-132">如果类型后缀为 `u` ，并且值可由类型表示， `[long]` 则其类型为 `[long]` 。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-132">If the type suffix is `u` and the value can be represented by type `[long]` then its type is `[long]`.</span></span>
- <span data-ttu-id="c0ca9-133">如果其值可由指定的类型表示，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-133">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="c0ca9-134">否则，该文本的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-134">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="c0ca9-135">真实文本</span><span class="sxs-lookup"><span data-stu-id="c0ca9-135">Real literals</span></span>

<span data-ttu-id="c0ca9-136">实际文本只能用十进制符号编写。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-136">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="c0ca9-137">此表示法可以在小数点后包含小数值，使用指数部分包括科学记数法。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-137">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="c0ca9-138">指数部分包含一个 "e"，后跟一个可选符号 (+/-) 和一个表示指数的数字。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-138">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="c0ca9-139">例如，文本值 `1e2` 等于数值100。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-139">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="c0ca9-140">真实文本可以具有类型后缀和乘数后缀。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-140">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="c0ca9-141">Suffix</span><span class="sxs-lookup"><span data-stu-id="c0ca9-141">Suffix</span></span> |       <span data-ttu-id="c0ca9-142">含义</span><span class="sxs-lookup"><span data-stu-id="c0ca9-142">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="c0ca9-143">d</span><span class="sxs-lookup"><span data-stu-id="c0ca9-143">d</span></span>      | <span data-ttu-id="c0ca9-144">decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="c0ca9-144">decimal data type</span></span>   |
| <span data-ttu-id="c0ca9-145">kb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-145">kb</span></span>     | <span data-ttu-id="c0ca9-146">kb 乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-146">kilobyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-147">mb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-147">mb</span></span>     | <span data-ttu-id="c0ca9-148">兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-148">megabyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-149">内存</span><span class="sxs-lookup"><span data-stu-id="c0ca9-149">gb</span></span>     | <span data-ttu-id="c0ca9-150">千兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-150">gigabyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-151">tb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-151">tb</span></span>     | <span data-ttu-id="c0ca9-152">tb 乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-152">terabyte multiplier</span></span> |
| <span data-ttu-id="c0ca9-153">容量</span><span class="sxs-lookup"><span data-stu-id="c0ca9-153">pb</span></span>     | <span data-ttu-id="c0ca9-154">pb 乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-154">petabyte multiplier</span></span> |

<span data-ttu-id="c0ca9-155">有两种类型的真实文本： double 和 decimal。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-155">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="c0ca9-156">它们分别由一个或两个 decimal 类型的后缀表示。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-156">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="c0ca9-157">PowerShell 不支持值的文本表示形式 `[float]` 。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-157">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="c0ca9-158">双实型文本具有类型 `[double]` 。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-158">A double real literal has type `[double]`.</span></span> <span data-ttu-id="c0ca9-159">Decimal 实型文本具有类型 `[decimal]` 。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-159">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="c0ca9-160">Decimal 实文字的小数部分的尾随零非常重要。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-160">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="c0ca9-161">如果实际文本中指数部分的数字值 `[double]` 小于支持的最小值，则该 `[double]` 实数文本的值为0。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-161">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="c0ca9-162">如果实际文本中指数部分的数字值 `[decimal]` 小于所支持的最小值，则该文本的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-162">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="c0ca9-163">如果指数部分的数字或真实文本中的数字 `[double]` `[decimal]` 大于所支持的最大值，则该文本的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-163">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="c0ca9-164">语法允许双实型文本具有长类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-164">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="c0ca9-165">PowerShell 将此事例视为一个整数文本，其值由类型表示 `[long]` 。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-165">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="c0ca9-166">保留此功能是为了向后兼容早期版本的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-166">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="c0ca9-167">但是，不鼓励程序员使用此窗体的整数文本，因为它们可以轻松地遮蔽文本的实际值。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-167">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="c0ca9-168">例如， `1.2L` 值为1，值为12，值为 `1.2345e1L` `1.2345e-5L` 0，则不会立即出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-168">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="c0ca9-169">数值乘数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-169">Numeric multipliers</span></span>

<span data-ttu-id="c0ca9-170">为方便起见，整数和真实文本可以包含数值乘数，这表示一组常用的一组2的幂。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-170">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="c0ca9-171">数值乘数可以用大写或小写字母的任意组合来编写。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-171">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="c0ca9-172">乘数后缀可与 `u` 、 `ul` 和 `l` 类型后缀结合使用。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-172">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="c0ca9-173">乘数示例</span><span class="sxs-lookup"><span data-stu-id="c0ca9-173">Multiplier examples</span></span>

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a><span data-ttu-id="c0ca9-174">数值类型加速器</span><span class="sxs-lookup"><span data-stu-id="c0ca9-174">Numeric type accelerators</span></span>

<span data-ttu-id="c0ca9-175">PowerShell 支持以下类型加速器：</span><span class="sxs-lookup"><span data-stu-id="c0ca9-175">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="c0ca9-176">加速器</span><span class="sxs-lookup"><span data-stu-id="c0ca9-176">Accelerator</span></span> |         <span data-ttu-id="c0ca9-177">备注</span><span class="sxs-lookup"><span data-stu-id="c0ca9-177">Note</span></span>         |           <span data-ttu-id="c0ca9-178">说明</span><span class="sxs-lookup"><span data-stu-id="c0ca9-178">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="c0ca9-179">字节 (无符号) </span><span class="sxs-lookup"><span data-stu-id="c0ca9-179">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="c0ca9-180">字节 (有符号) </span><span class="sxs-lookup"><span data-stu-id="c0ca9-180">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="c0ca9-181">16 位整数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-181">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="c0ca9-182">16位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="c0ca9-182">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="c0ca9-183">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="c0ca9-183">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="c0ca9-184">别名 `[int32]`</span><span class="sxs-lookup"><span data-stu-id="c0ca9-184">alias for `[int32]`</span></span>  | <span data-ttu-id="c0ca9-185">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="c0ca9-185">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="c0ca9-186">32位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="c0ca9-186">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="c0ca9-187">64 位整数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-187">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="c0ca9-188">别名 `[int64]`</span><span class="sxs-lookup"><span data-stu-id="c0ca9-188">alias for `[int64]`</span></span>  | <span data-ttu-id="c0ca9-189">64 位整数</span><span class="sxs-lookup"><span data-stu-id="c0ca9-189">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="c0ca9-190">64位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="c0ca9-190">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="c0ca9-191">请参阅 [BigInteger 结构][bigint]</span><span class="sxs-lookup"><span data-stu-id="c0ca9-191">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="c0ca9-192">单精度浮点</span><span class="sxs-lookup"><span data-stu-id="c0ca9-192">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="c0ca9-193">别名 `[single]`</span><span class="sxs-lookup"><span data-stu-id="c0ca9-193">alias for `[single]`</span></span> | <span data-ttu-id="c0ca9-194">单精度浮点</span><span class="sxs-lookup"><span data-stu-id="c0ca9-194">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="c0ca9-195">双精度浮点</span><span class="sxs-lookup"><span data-stu-id="c0ca9-195">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="c0ca9-196">128位浮点</span><span class="sxs-lookup"><span data-stu-id="c0ca9-196">128-bit floating point</span></span>           |

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="c0ca9-197">使用其他数值类型</span><span class="sxs-lookup"><span data-stu-id="c0ca9-197">Working with other numeric types</span></span>

<span data-ttu-id="c0ca9-198">若要使用任何其他数值类型，必须使用类型加速器，这一点不会出现一些问题。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-198">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="c0ca9-199">例如，在强制转换为任何其他类型之前，高整数值始终被分析为双精度值。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-199">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="c0ca9-200">值首先分析为 double，在较高范围内会丢失精度。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-200">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="c0ca9-201">若要避免此问题，请将值作为字符串输入，然后转换这些值：</span><span class="sxs-lookup"><span data-stu-id="c0ca9-201">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="c0ca9-202">示例</span><span class="sxs-lookup"><span data-stu-id="c0ca9-202">Examples</span></span>

<span data-ttu-id="c0ca9-203">下表包含几个数字文本示例，并列出它们的类型和值：</span><span class="sxs-lookup"><span data-stu-id="c0ca9-203">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="c0ca9-204">数字</span><span class="sxs-lookup"><span data-stu-id="c0ca9-204">Number</span></span>  |  <span data-ttu-id="c0ca9-205">类型</span><span class="sxs-lookup"><span data-stu-id="c0ca9-205">Type</span></span>   |    <span data-ttu-id="c0ca9-206">值</span><span class="sxs-lookup"><span data-stu-id="c0ca9-206">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="c0ca9-207">100</span><span class="sxs-lookup"><span data-stu-id="c0ca9-207">100</span></span> | <span data-ttu-id="c0ca9-208">Int32</span><span class="sxs-lookup"><span data-stu-id="c0ca9-208">Int32</span></span>   |          <span data-ttu-id="c0ca9-209">100</span><span class="sxs-lookup"><span data-stu-id="c0ca9-209">100</span></span> |
|     <span data-ttu-id="c0ca9-210">100D</span><span class="sxs-lookup"><span data-stu-id="c0ca9-210">100D</span></span> | <span data-ttu-id="c0ca9-211">十进制</span><span class="sxs-lookup"><span data-stu-id="c0ca9-211">Decimal</span></span> |          <span data-ttu-id="c0ca9-212">100</span><span class="sxs-lookup"><span data-stu-id="c0ca9-212">100</span></span> |
|     <span data-ttu-id="c0ca9-213">100l</span><span class="sxs-lookup"><span data-stu-id="c0ca9-213">100l</span></span> | <span data-ttu-id="c0ca9-214">Int64</span><span class="sxs-lookup"><span data-stu-id="c0ca9-214">Int64</span></span>   |          <span data-ttu-id="c0ca9-215">100</span><span class="sxs-lookup"><span data-stu-id="c0ca9-215">100</span></span> |
|      <span data-ttu-id="c0ca9-216">1e2</span><span class="sxs-lookup"><span data-stu-id="c0ca9-216">1e2</span></span> | <span data-ttu-id="c0ca9-217">Double</span><span class="sxs-lookup"><span data-stu-id="c0ca9-217">Double</span></span>  |          <span data-ttu-id="c0ca9-218">100</span><span class="sxs-lookup"><span data-stu-id="c0ca9-218">100</span></span> |
|     <span data-ttu-id="c0ca9-219">1. e2</span><span class="sxs-lookup"><span data-stu-id="c0ca9-219">1.e2</span></span> | <span data-ttu-id="c0ca9-220">Double</span><span class="sxs-lookup"><span data-stu-id="c0ca9-220">Double</span></span>  |          <span data-ttu-id="c0ca9-221">100</span><span class="sxs-lookup"><span data-stu-id="c0ca9-221">100</span></span> |
|    <span data-ttu-id="c0ca9-222">0x1e2</span><span class="sxs-lookup"><span data-stu-id="c0ca9-222">0x1e2</span></span> | <span data-ttu-id="c0ca9-223">Int32</span><span class="sxs-lookup"><span data-stu-id="c0ca9-223">Int32</span></span>   |          <span data-ttu-id="c0ca9-224">482</span><span class="sxs-lookup"><span data-stu-id="c0ca9-224">482</span></span> |
|   <span data-ttu-id="c0ca9-225">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="c0ca9-225">0x1e2L</span></span> | <span data-ttu-id="c0ca9-226">Int64</span><span class="sxs-lookup"><span data-stu-id="c0ca9-226">Int64</span></span>   |          <span data-ttu-id="c0ca9-227">482</span><span class="sxs-lookup"><span data-stu-id="c0ca9-227">482</span></span> |
|   <span data-ttu-id="c0ca9-228">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="c0ca9-228">0x1e2D</span></span> | <span data-ttu-id="c0ca9-229">Int32</span><span class="sxs-lookup"><span data-stu-id="c0ca9-229">Int32</span></span>   |         <span data-ttu-id="c0ca9-230">7725</span><span class="sxs-lookup"><span data-stu-id="c0ca9-230">7725</span></span> |
|     <span data-ttu-id="c0ca9-231">482D</span><span class="sxs-lookup"><span data-stu-id="c0ca9-231">482D</span></span> | <span data-ttu-id="c0ca9-232">十进制</span><span class="sxs-lookup"><span data-stu-id="c0ca9-232">Decimal</span></span> |          <span data-ttu-id="c0ca9-233">482</span><span class="sxs-lookup"><span data-stu-id="c0ca9-233">482</span></span> |
|    <span data-ttu-id="c0ca9-234">482gb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-234">482gb</span></span> | <span data-ttu-id="c0ca9-235">Int64</span><span class="sxs-lookup"><span data-stu-id="c0ca9-235">Int64</span></span>   | <span data-ttu-id="c0ca9-236">517543559168</span><span class="sxs-lookup"><span data-stu-id="c0ca9-236">517543559168</span></span> |
| <span data-ttu-id="c0ca9-237">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="c0ca9-237">0x1e2lgb</span></span> | <span data-ttu-id="c0ca9-238">Int64</span><span class="sxs-lookup"><span data-stu-id="c0ca9-238">Int64</span></span>   | <span data-ttu-id="c0ca9-239">517543559168</span><span class="sxs-lookup"><span data-stu-id="c0ca9-239">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="c0ca9-240">类似于数字文本的命令</span><span class="sxs-lookup"><span data-stu-id="c0ca9-240">Commands that look like numeric literals</span></span>

<span data-ttu-id="c0ca9-241">任何类似数字文本的命令都必须使用 call 运算符 () 来执行 `&` ，否则它将被解释为关联类型的数字。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-241">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="c0ca9-242">访问数字对象的属性和方法</span><span class="sxs-lookup"><span data-stu-id="c0ca9-242">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="c0ca9-243">若要访问数字文本的成员，需要将文本括在括号中。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-243">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="c0ca9-244">文本不具有小数点</span><span class="sxs-lookup"><span data-stu-id="c0ca9-244">The literal does not have a decimal point</span></span>
- <span data-ttu-id="c0ca9-245">小数点后的文本不包含任何数字</span><span class="sxs-lookup"><span data-stu-id="c0ca9-245">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="c0ca9-246">文本没有后缀</span><span class="sxs-lookup"><span data-stu-id="c0ca9-246">The literal does not have a suffix</span></span>

<span data-ttu-id="c0ca9-247">例如，下面的示例将失败：</span><span class="sxs-lookup"><span data-stu-id="c0ca9-247">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="c0ca9-248">下面的示例工作：</span><span class="sxs-lookup"><span data-stu-id="c0ca9-248">The following examples work:</span></span>

```
PS> 2L.GetType().Name
Int64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="c0ca9-249">前两个示例在不将文本值括在括号中的情况下工作，因为 PowerShell 分析器可以确定数字文本的结束位置和 **GetType** 方法的启动位置。</span><span class="sxs-lookup"><span data-stu-id="c0ca9-249">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
