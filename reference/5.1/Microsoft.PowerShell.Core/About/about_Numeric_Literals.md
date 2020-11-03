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
# <a name="about-numeric-literals"></a>关于数字文本

有两种类型的数值：整数和实数。 两者都可以具有类型和乘数后缀。

## <a name="integer-literals"></a>整数文本

整数文本可以用十进制或十六进制表示法来编写。 十六进制文本 `0x` 以为前缀，以将它们与十进制数区分开来。

整数文本可以具有类型后缀和乘数后缀。

| Suffix |       含义       |
| ------ | ------------------- |
| l      | long 数据类型      |
| kb     | kb 乘数 |
| mb     | 兆字节乘数 |
| 内存     | 千兆字节乘数 |
| tb     | tb 乘数 |
| 容量     | pb 乘数 |

整数文本的类型由其值、类型后缀和数值乘数后缀确定。

对于无类型后缀的整数文本：

- 如果值可以通过类型表示 `[int]` ，则为其类型。
- 否则，如果该值可以由类型表示 `[long]` ，则为其类型。
- 否则，如果该值可以由类型表示 `[decimal]` ，则为其类型。
- 否则，它由类型表示 `[double]` 。

对于类型为后缀的整数文本：

- 如果类型后缀为 `u` ，并且值可由类型表示， `[int]` 则其类型为 `[int]` 。
- 如果类型后缀为 `u` ，并且值可由类型表示， `[long]` 则其类型为 `[long]` 。
- 如果其值可由指定的类型表示，则为其类型。
- 否则，该文本的格式不正确。

## <a name="real-literals"></a>真实文本

实际文本只能用十进制符号编写。 此表示法可以在小数点后包含小数值，使用指数部分包括科学记数法。

指数部分包含一个 "e"，后跟一个可选符号 (+/-) 和一个表示指数的数字。 例如，文本值 `1e2` 等于数值100。

真实文本可以具有类型后缀和乘数后缀。

| Suffix |       含义       |
| ------ | ------------------- |
| d      | decimal 数据类型   |
| kb     | kb 乘数 |
| mb     | 兆字节乘数 |
| 内存     | 千兆字节乘数 |
| tb     | tb 乘数 |
| 容量     | pb 乘数 |

有两种类型的真实文本： double 和 decimal。 它们分别由一个或两个 decimal 类型的后缀表示。 PowerShell 不支持值的文本表示形式 `[float]` 。 双实型文本具有类型 `[double]` 。 Decimal 实型文本具有类型 `[decimal]` 。
Decimal 实文字的小数部分的尾随零非常重要。

如果实际文本中指数部分的数字值 `[double]` 小于支持的最小值，则该 `[double]` 实数文本的值为0。 如果实际文本中指数部分的数字值 `[decimal]` 小于所支持的最小值，则该文本的格式不正确。 如果指数部分的数字或真实文本中的数字 `[double]` `[decimal]` 大于所支持的最大值，则该文本的格式不正确。

> [!NOTE]
> 语法允许双实型文本具有长类型的后缀。
> PowerShell 将此事例视为一个整数文本，其值由类型表示 `[long]` 。 保留此功能是为了向后兼容早期版本的 PowerShell。 但是，不鼓励程序员使用此窗体的整数文本，因为它们可以轻松地遮蔽文本的实际值。 例如， `1.2L` 值为1，值为12，值为 `1.2345e1L` `1.2345e-5L` 0，则不会立即出现这种情况。

## <a name="numeric-multipliers"></a>数值乘数

为方便起见，整数和真实文本可以包含数值乘数，这表示一组常用的一组2的幂。 数值乘数可以用大写或小写字母的任意组合来编写。

乘数后缀可与 `u` 、 `ul` 和 `l` 类型后缀结合使用。

### <a name="multiplier-examples"></a>乘数示例

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

## <a name="numeric-type-accelerators"></a>数值类型加速器

PowerShell 支持以下类型加速器：

| 加速器 |         备注         |           说明            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | 字节 (无符号)                   |
| `[sbyte]`   |                      | 字节 (有符号)                     |
| `[Int16]`   |                      | 16 位整数                   |
| `[UInt16]`  |                      | 16位整数 (无符号)         |
| `[Int32]`   |                      | 32-bit integer                   |
| `[int]`     | 别名 `[int32]`  | 32-bit integer                   |
| `[UInt32]`  |                      | 32位整数 (无符号)         |
| `[Int64]`   |                      | 64 位整数                   |
| `[long]`    | 别名 `[int64]`  | 64 位整数                   |
| `[UInt64]`  |                      | 64位整数 (无符号)         |
| `[bigint]`  |                      | 请参阅 [BigInteger 结构][bigint]  |
| `[single]`  |                      | 单精度浮点  |
| `[float]`   | 别名 `[single]` | 单精度浮点  |
| `[double]`  |                      | 双精度浮点  |
| `[decimal]` |                      | 128位浮点           |

### <a name="working-with-other-numeric-types"></a>使用其他数值类型

若要使用任何其他数值类型，必须使用类型加速器，这一点不会出现一些问题。 例如，在强制转换为任何其他类型之前，高整数值始终被分析为双精度值。

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

值首先分析为 double，在较高范围内会丢失精度。
若要避免此问题，请将值作为字符串输入，然后转换这些值：

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a>示例

下表包含几个数字文本示例，并列出它们的类型和值：

|  数字  |  类型   |    值     |
| -------: | ------- | -----------: |
|      100 | Int32   |          100 |
|     100D | 十进制 |          100 |
|     100l | Int64   |          100 |
|      1e2 | Double  |          100 |
|     1. e2 | Double  |          100 |
|    0x1e2 | Int32   |          482 |
|   0x1e2L | Int64   |          482 |
|   0x1e2D | Int32   |         7725 |
|     482D | 十进制 |          482 |
|    482gb | Int64   | 517543559168 |
| 0x1e2lgb | Int64   | 517543559168 |

### <a name="commands-that-look-like-numeric-literals"></a>类似于数字文本的命令

任何类似数字文本的命令都必须使用 call 运算符 () 来执行 `&` ，否则它将被解释为关联类型的数字。

### <a name="access-properties-and-methods-of-numeric-objects"></a>访问数字对象的属性和方法

若要访问数字文本的成员，需要将文本括在括号中。

- 文本不具有小数点
- 小数点后的文本不包含任何数字
- 文本没有后缀

例如，下面的示例将失败：

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

下面的示例工作：

```
PS> 2L.GetType().Name
Int64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

前两个示例在不将文本值括在括号中的情况下工作，因为 PowerShell 分析器可以确定数字文本的结束位置和 **GetType** 方法的启动位置。

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
