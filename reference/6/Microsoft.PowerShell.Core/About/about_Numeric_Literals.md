---
description: 整数和实数可以具有类型和乘数后缀。
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 关于数字文本
ms.openlocfilehash: 62f00ae9f3643724808146134fd03b6f01c29bce
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200602"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="fe1e9-103">关于数字文本</span><span class="sxs-lookup"><span data-stu-id="fe1e9-103">About numeric literals</span></span>

<span data-ttu-id="fe1e9-104">有两种类型的数值：整数和实数。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="fe1e9-105">两者都可以具有类型和乘数后缀。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="fe1e9-106">整数文本</span><span class="sxs-lookup"><span data-stu-id="fe1e9-106">Integer literals</span></span>

<span data-ttu-id="fe1e9-107">整数文本可以用十进制或十六进制表示法来编写。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="fe1e9-108">十六进制文本 `0x` 以为前缀，以将它们与十进制数区分开来。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="fe1e9-109">整数文本可以具有类型后缀和乘数后缀。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="fe1e9-110">Suffix</span><span class="sxs-lookup"><span data-stu-id="fe1e9-110">Suffix</span></span> |            <span data-ttu-id="fe1e9-111">含义</span><span class="sxs-lookup"><span data-stu-id="fe1e9-111">Meaning</span></span>             |          <span data-ttu-id="fe1e9-112">备注</span><span class="sxs-lookup"><span data-stu-id="fe1e9-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="fe1e9-113">y</span><span class="sxs-lookup"><span data-stu-id="fe1e9-113">y</span></span>      | <span data-ttu-id="fe1e9-114">带符号字节数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-114">signed byte data type</span></span>          | <span data-ttu-id="fe1e9-115">在 PowerShell 6.2 中添加</span><span class="sxs-lookup"><span data-stu-id="fe1e9-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="fe1e9-116">uy</span><span class="sxs-lookup"><span data-stu-id="fe1e9-116">uy</span></span>     | <span data-ttu-id="fe1e9-117">无符号 byte 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-117">unsigned byte data type</span></span>        | <span data-ttu-id="fe1e9-118">在 PowerShell 6.2 中添加</span><span class="sxs-lookup"><span data-stu-id="fe1e9-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="fe1e9-119">s</span><span class="sxs-lookup"><span data-stu-id="fe1e9-119">s</span></span>      | <span data-ttu-id="fe1e9-120">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-120">short data type</span></span>                | <span data-ttu-id="fe1e9-121">在 PowerShell 6.2 中添加</span><span class="sxs-lookup"><span data-stu-id="fe1e9-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="fe1e9-122">us</span><span class="sxs-lookup"><span data-stu-id="fe1e9-122">us</span></span>     | <span data-ttu-id="fe1e9-123">无符号 short 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-123">unsigned short data type</span></span>       | <span data-ttu-id="fe1e9-124">在 PowerShell 6.2 中添加</span><span class="sxs-lookup"><span data-stu-id="fe1e9-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="fe1e9-125">l</span><span class="sxs-lookup"><span data-stu-id="fe1e9-125">l</span></span>      | <span data-ttu-id="fe1e9-126">long 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-126">long data type</span></span>                 |                         |
| <span data-ttu-id="fe1e9-127">u</span><span class="sxs-lookup"><span data-stu-id="fe1e9-127">u</span></span>      | <span data-ttu-id="fe1e9-128">无符号 int 或 long 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-128">unsigned int or long data type</span></span> | <span data-ttu-id="fe1e9-129">在 PowerShell 6.2 中添加</span><span class="sxs-lookup"><span data-stu-id="fe1e9-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="fe1e9-130">ul</span><span class="sxs-lookup"><span data-stu-id="fe1e9-130">ul</span></span>     | <span data-ttu-id="fe1e9-131">无符号 long 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-131">unsigned long data type</span></span>        | <span data-ttu-id="fe1e9-132">在 PowerShell 6.2 中添加</span><span class="sxs-lookup"><span data-stu-id="fe1e9-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="fe1e9-133">kb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-133">kb</span></span>     | <span data-ttu-id="fe1e9-134">kb 乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-134">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="fe1e9-135">mb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-135">mb</span></span>     | <span data-ttu-id="fe1e9-136">兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-136">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="fe1e9-137">内存</span><span class="sxs-lookup"><span data-stu-id="fe1e9-137">gb</span></span>     | <span data-ttu-id="fe1e9-138">千兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-138">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="fe1e9-139">tb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-139">tb</span></span>     | <span data-ttu-id="fe1e9-140">tb 乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-140">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="fe1e9-141">容量</span><span class="sxs-lookup"><span data-stu-id="fe1e9-141">pb</span></span>     | <span data-ttu-id="fe1e9-142">pb 乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-142">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="fe1e9-143">整数文本的类型由其值、类型后缀和数值乘数后缀确定。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-143">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="fe1e9-144">对于无类型后缀的整数文本：</span><span class="sxs-lookup"><span data-stu-id="fe1e9-144">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="fe1e9-145">如果值可以通过类型表示 `[int]` ，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-145">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="fe1e9-146">否则，如果该值可以由类型表示 `[long]` ，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-146">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="fe1e9-147">否则，如果该值可以由类型表示 `[decimal]` ，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-147">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="fe1e9-148">否则，它由类型表示 `[double]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-148">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="fe1e9-149">对于类型为后缀的整数文本：</span><span class="sxs-lookup"><span data-stu-id="fe1e9-149">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="fe1e9-150">如果类型后缀为 `u` ，并且值可由类型表示， `[uint]` 则其类型为 `[uint]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-150">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="fe1e9-151">如果类型后缀为 `u` ，并且值可由类型表示， `[ulong]` 则其类型为 `[ulong]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-151">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="fe1e9-152">如果其值可由指定的类型表示，则为其类型。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-152">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="fe1e9-153">否则，该文本的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-153">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="fe1e9-154">真实文本</span><span class="sxs-lookup"><span data-stu-id="fe1e9-154">Real literals</span></span>

<span data-ttu-id="fe1e9-155">实际文本只能用十进制符号编写。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-155">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="fe1e9-156">此表示法可以在小数点后包含小数值，使用指数部分包括科学记数法。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-156">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="fe1e9-157">指数部分包含一个 "e"，后跟一个可选符号 (+/-) 和一个表示指数的数字。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-157">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="fe1e9-158">例如，文本值 `1e2` 等于数值100。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-158">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="fe1e9-159">真实文本可以具有类型后缀和乘数后缀。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-159">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="fe1e9-160">Suffix</span><span class="sxs-lookup"><span data-stu-id="fe1e9-160">Suffix</span></span> |       <span data-ttu-id="fe1e9-161">含义</span><span class="sxs-lookup"><span data-stu-id="fe1e9-161">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="fe1e9-162">d</span><span class="sxs-lookup"><span data-stu-id="fe1e9-162">d</span></span>      | <span data-ttu-id="fe1e9-163">decimal 数据类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-163">decimal data type</span></span>   |
| <span data-ttu-id="fe1e9-164">kb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-164">kb</span></span>     | <span data-ttu-id="fe1e9-165">kb 乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-165">kilobyte multiplier</span></span> |
| <span data-ttu-id="fe1e9-166">mb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-166">mb</span></span>     | <span data-ttu-id="fe1e9-167">兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-167">megabyte multiplier</span></span> |
| <span data-ttu-id="fe1e9-168">内存</span><span class="sxs-lookup"><span data-stu-id="fe1e9-168">gb</span></span>     | <span data-ttu-id="fe1e9-169">千兆字节乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-169">gigabyte multiplier</span></span> |
| <span data-ttu-id="fe1e9-170">tb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-170">tb</span></span>     | <span data-ttu-id="fe1e9-171">tb 乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-171">terabyte multiplier</span></span> |
| <span data-ttu-id="fe1e9-172">容量</span><span class="sxs-lookup"><span data-stu-id="fe1e9-172">pb</span></span>     | <span data-ttu-id="fe1e9-173">pb 乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-173">petabyte multiplier</span></span> |

<span data-ttu-id="fe1e9-174">有两种类型的真实文本： double 和 decimal。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-174">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="fe1e9-175">它们分别由一个或两个 decimal 类型的后缀表示。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-175">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="fe1e9-176">PowerShell 不支持值的文本表示形式 `[float]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-176">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="fe1e9-177">双实型文本具有类型 `[double]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-177">A double real literal has type `[double]`.</span></span> <span data-ttu-id="fe1e9-178">Decimal 实型文本具有类型 `[decimal]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-178">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="fe1e9-179">Decimal 实文字的小数部分的尾随零非常重要。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-179">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="fe1e9-180">如果实际文本中指数部分的数字值 `[double]` 小于支持的最小值，则该 `[double]` 实数文本的值为0。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-180">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="fe1e9-181">如果实际文本中指数部分的数字值 `[decimal]` 小于所支持的最小值，则该文本的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-181">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="fe1e9-182">如果指数部分的数字或真实文本中的数字 `[double]` `[decimal]` 大于所支持的最大值，则该文本的格式不正确。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-182">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="fe1e9-183">语法允许双实型文本具有长类型的后缀。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-183">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="fe1e9-184">PowerShell 将此事例视为一个整数文本，其值由类型表示 `[long]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-184">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="fe1e9-185">保留此功能是为了向后兼容早期版本的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-185">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="fe1e9-186">但是，不鼓励程序员使用此窗体的整数文本，因为它们可以轻松地遮蔽文本的实际值。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-186">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="fe1e9-187">例如， `1.2L` 值为1，值为12，值为 `1.2345e1L` `1.2345e-5L` 0，则不会立即出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-187">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="fe1e9-188">数值乘数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-188">Numeric multipliers</span></span>

<span data-ttu-id="fe1e9-189">为方便起见，整数和真实文本可以包含数值乘数，这表示一组常用的一组2的幂。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-189">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="fe1e9-190">数值乘数可以用大写或小写字母的任意组合来编写。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-190">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="fe1e9-191">乘数后缀可与 `u` 、 `ul` 和 `l` 类型后缀结合使用。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-191">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="fe1e9-192">乘数示例</span><span class="sxs-lookup"><span data-stu-id="fe1e9-192">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="fe1e9-193">数值类型加速器</span><span class="sxs-lookup"><span data-stu-id="fe1e9-193">Numeric type accelerators</span></span>

<span data-ttu-id="fe1e9-194">PowerShell 支持以下类型加速器：</span><span class="sxs-lookup"><span data-stu-id="fe1e9-194">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="fe1e9-195">加速器</span><span class="sxs-lookup"><span data-stu-id="fe1e9-195">Accelerator</span></span> |         <span data-ttu-id="fe1e9-196">备注</span><span class="sxs-lookup"><span data-stu-id="fe1e9-196">Note</span></span>         |           <span data-ttu-id="fe1e9-197">说明</span><span class="sxs-lookup"><span data-stu-id="fe1e9-197">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="fe1e9-198">字节 (无符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-198">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="fe1e9-199">字节 (有符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-199">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="fe1e9-200">16 位整数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-200">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="fe1e9-201">别名 `[int16]`</span><span class="sxs-lookup"><span data-stu-id="fe1e9-201">alias for `[int16]`</span></span>  | <span data-ttu-id="fe1e9-202">16 位整数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-202">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="fe1e9-203">16位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-203">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="fe1e9-204">别名 `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="fe1e9-204">alias for `[uint16]`</span></span> | <span data-ttu-id="fe1e9-205">16位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-205">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="fe1e9-206">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="fe1e9-206">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="fe1e9-207">别名 `[int32]`</span><span class="sxs-lookup"><span data-stu-id="fe1e9-207">alias for `[int32]`</span></span>  | <span data-ttu-id="fe1e9-208">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="fe1e9-208">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="fe1e9-209">32位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-209">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="fe1e9-210">别名 `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="fe1e9-210">alias for `[uint32]`</span></span> | <span data-ttu-id="fe1e9-211">32位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-211">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="fe1e9-212">64 位整数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-212">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="fe1e9-213">别名 `[int64]`</span><span class="sxs-lookup"><span data-stu-id="fe1e9-213">alias for `[int64]`</span></span>  | <span data-ttu-id="fe1e9-214">64 位整数</span><span class="sxs-lookup"><span data-stu-id="fe1e9-214">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="fe1e9-215">64位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-215">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="fe1e9-216">别名 `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="fe1e9-216">alias for `[uint64]`</span></span> | <span data-ttu-id="fe1e9-217">64位整数 (无符号) </span><span class="sxs-lookup"><span data-stu-id="fe1e9-217">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="fe1e9-218">请参阅 [BigInteger 结构][bigint]</span><span class="sxs-lookup"><span data-stu-id="fe1e9-218">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="fe1e9-219">单精度浮点</span><span class="sxs-lookup"><span data-stu-id="fe1e9-219">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="fe1e9-220">别名 `[single]`</span><span class="sxs-lookup"><span data-stu-id="fe1e9-220">alias for `[single]`</span></span> | <span data-ttu-id="fe1e9-221">单精度浮点</span><span class="sxs-lookup"><span data-stu-id="fe1e9-221">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="fe1e9-222">双精度浮点</span><span class="sxs-lookup"><span data-stu-id="fe1e9-222">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="fe1e9-223">128位浮点</span><span class="sxs-lookup"><span data-stu-id="fe1e9-223">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="fe1e9-224">PowerShell 6.2 中添加了以下类型加速器： `[short]` 、 `[ushort]` 、 `[uint]` 和 `[ulong]` 。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-224">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="fe1e9-225">使用其他数值类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-225">Working with other numeric types</span></span>

<span data-ttu-id="fe1e9-226">若要使用任何其他数值类型，必须使用类型加速器，这一点不会出现一些问题。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-226">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="fe1e9-227">例如，在强制转换为任何其他类型之前，高整数值始终被分析为双精度值。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-227">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="fe1e9-228">值首先分析为 double，在较高范围内会丢失精度。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-228">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="fe1e9-229">若要避免此问题，请将值作为字符串输入，然后转换这些值：</span><span class="sxs-lookup"><span data-stu-id="fe1e9-229">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="fe1e9-230">示例</span><span class="sxs-lookup"><span data-stu-id="fe1e9-230">Examples</span></span>

<span data-ttu-id="fe1e9-231">下表包含几个数字文本示例，并列出它们的类型和值：</span><span class="sxs-lookup"><span data-stu-id="fe1e9-231">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="fe1e9-232">数字</span><span class="sxs-lookup"><span data-stu-id="fe1e9-232">Number</span></span>  |  <span data-ttu-id="fe1e9-233">类型</span><span class="sxs-lookup"><span data-stu-id="fe1e9-233">Type</span></span>   |    <span data-ttu-id="fe1e9-234">值</span><span class="sxs-lookup"><span data-stu-id="fe1e9-234">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="fe1e9-235">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-235">100</span></span> | <span data-ttu-id="fe1e9-236">Int32</span><span class="sxs-lookup"><span data-stu-id="fe1e9-236">Int32</span></span>   |          <span data-ttu-id="fe1e9-237">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-237">100</span></span> |
|     <span data-ttu-id="fe1e9-238">100D</span><span class="sxs-lookup"><span data-stu-id="fe1e9-238">100D</span></span> | <span data-ttu-id="fe1e9-239">十进制</span><span class="sxs-lookup"><span data-stu-id="fe1e9-239">Decimal</span></span> |          <span data-ttu-id="fe1e9-240">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-240">100</span></span> |
|     <span data-ttu-id="fe1e9-241">100l</span><span class="sxs-lookup"><span data-stu-id="fe1e9-241">100l</span></span> | <span data-ttu-id="fe1e9-242">Int64</span><span class="sxs-lookup"><span data-stu-id="fe1e9-242">Int64</span></span>   |          <span data-ttu-id="fe1e9-243">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-243">100</span></span> |
|    <span data-ttu-id="fe1e9-244">100uL</span><span class="sxs-lookup"><span data-stu-id="fe1e9-244">100uL</span></span> | <span data-ttu-id="fe1e9-245">UInt64</span><span class="sxs-lookup"><span data-stu-id="fe1e9-245">UInt64</span></span>  |          <span data-ttu-id="fe1e9-246">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-246">100</span></span> |
|    <span data-ttu-id="fe1e9-247">100us</span><span class="sxs-lookup"><span data-stu-id="fe1e9-247">100us</span></span> | <span data-ttu-id="fe1e9-248">UInt16</span><span class="sxs-lookup"><span data-stu-id="fe1e9-248">UInt16</span></span>  |          <span data-ttu-id="fe1e9-249">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-249">100</span></span> |
|    <span data-ttu-id="fe1e9-250">100uy</span><span class="sxs-lookup"><span data-stu-id="fe1e9-250">100uy</span></span> | <span data-ttu-id="fe1e9-251">Byte</span><span class="sxs-lookup"><span data-stu-id="fe1e9-251">Byte</span></span>    |          <span data-ttu-id="fe1e9-252">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-252">100</span></span> |
|     <span data-ttu-id="fe1e9-253">100y</span><span class="sxs-lookup"><span data-stu-id="fe1e9-253">100y</span></span> | <span data-ttu-id="fe1e9-254">SByte</span><span class="sxs-lookup"><span data-stu-id="fe1e9-254">SByte</span></span>   |          <span data-ttu-id="fe1e9-255">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-255">100</span></span> |
|      <span data-ttu-id="fe1e9-256">1e2</span><span class="sxs-lookup"><span data-stu-id="fe1e9-256">1e2</span></span> | <span data-ttu-id="fe1e9-257">Double</span><span class="sxs-lookup"><span data-stu-id="fe1e9-257">Double</span></span>  |          <span data-ttu-id="fe1e9-258">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-258">100</span></span> |
|     <span data-ttu-id="fe1e9-259">1. e2</span><span class="sxs-lookup"><span data-stu-id="fe1e9-259">1.e2</span></span> | <span data-ttu-id="fe1e9-260">Double</span><span class="sxs-lookup"><span data-stu-id="fe1e9-260">Double</span></span>  |          <span data-ttu-id="fe1e9-261">100</span><span class="sxs-lookup"><span data-stu-id="fe1e9-261">100</span></span> |
|    <span data-ttu-id="fe1e9-262">0x1e2</span><span class="sxs-lookup"><span data-stu-id="fe1e9-262">0x1e2</span></span> | <span data-ttu-id="fe1e9-263">Int32</span><span class="sxs-lookup"><span data-stu-id="fe1e9-263">Int32</span></span>   |          <span data-ttu-id="fe1e9-264">482</span><span class="sxs-lookup"><span data-stu-id="fe1e9-264">482</span></span> |
|   <span data-ttu-id="fe1e9-265">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="fe1e9-265">0x1e2L</span></span> | <span data-ttu-id="fe1e9-266">Int64</span><span class="sxs-lookup"><span data-stu-id="fe1e9-266">Int64</span></span>   |          <span data-ttu-id="fe1e9-267">482</span><span class="sxs-lookup"><span data-stu-id="fe1e9-267">482</span></span> |
|   <span data-ttu-id="fe1e9-268">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="fe1e9-268">0x1e2D</span></span> | <span data-ttu-id="fe1e9-269">Int32</span><span class="sxs-lookup"><span data-stu-id="fe1e9-269">Int32</span></span>   |         <span data-ttu-id="fe1e9-270">7725</span><span class="sxs-lookup"><span data-stu-id="fe1e9-270">7725</span></span> |
|     <span data-ttu-id="fe1e9-271">482D</span><span class="sxs-lookup"><span data-stu-id="fe1e9-271">482D</span></span> | <span data-ttu-id="fe1e9-272">十进制</span><span class="sxs-lookup"><span data-stu-id="fe1e9-272">Decimal</span></span> |          <span data-ttu-id="fe1e9-273">482</span><span class="sxs-lookup"><span data-stu-id="fe1e9-273">482</span></span> |
|    <span data-ttu-id="fe1e9-274">482gb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-274">482gb</span></span> | <span data-ttu-id="fe1e9-275">Int64</span><span class="sxs-lookup"><span data-stu-id="fe1e9-275">Int64</span></span>   | <span data-ttu-id="fe1e9-276">517543559168</span><span class="sxs-lookup"><span data-stu-id="fe1e9-276">517543559168</span></span> |
| <span data-ttu-id="fe1e9-277">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="fe1e9-277">0x1e2lgb</span></span> | <span data-ttu-id="fe1e9-278">Int64</span><span class="sxs-lookup"><span data-stu-id="fe1e9-278">Int64</span></span>   | <span data-ttu-id="fe1e9-279">517543559168</span><span class="sxs-lookup"><span data-stu-id="fe1e9-279">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="fe1e9-280">类似于数字文本的命令</span><span class="sxs-lookup"><span data-stu-id="fe1e9-280">Commands that look like numeric literals</span></span>

<span data-ttu-id="fe1e9-281">任何类似数字文本的命令都必须使用 call 运算符 () 来执行 `&` ，否则它将被解释为关联类型的数字。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-281">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="fe1e9-282">访问数字对象的属性和方法</span><span class="sxs-lookup"><span data-stu-id="fe1e9-282">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="fe1e9-283">若要访问数字文本的成员，需要将文本括在括号中。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-283">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="fe1e9-284">文本不具有小数点</span><span class="sxs-lookup"><span data-stu-id="fe1e9-284">The literal does not have a decimal point</span></span>
- <span data-ttu-id="fe1e9-285">小数点后的文本不包含任何数字</span><span class="sxs-lookup"><span data-stu-id="fe1e9-285">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="fe1e9-286">文本没有后缀</span><span class="sxs-lookup"><span data-stu-id="fe1e9-286">The literal does not have a suffix</span></span>

<span data-ttu-id="fe1e9-287">例如，下面的示例将失败：</span><span class="sxs-lookup"><span data-stu-id="fe1e9-287">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="fe1e9-288">下面的示例工作：</span><span class="sxs-lookup"><span data-stu-id="fe1e9-288">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="fe1e9-289">前两个示例在不将文本值括在括号中的情况下工作，因为 PowerShell 分析器可以确定数字文本的结束位置和 **GetType** 方法的启动位置。</span><span class="sxs-lookup"><span data-stu-id="fe1e9-289">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger?view=netcore-2.2
