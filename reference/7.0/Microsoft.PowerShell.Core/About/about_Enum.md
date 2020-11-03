---
description: '`enum`语句用于声明枚举。 枚举是由一组称为枚举器列表的命名标签组成的不同类型。'
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_enum?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Enum
ms.openlocfilehash: 9cd4f60db2903bc4ede6b0c3ad738b3137b87191
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200401"
---
# <a name="about-enum"></a><span data-ttu-id="199ea-105">关于枚举</span><span class="sxs-lookup"><span data-stu-id="199ea-105">About Enum</span></span>

## <a name="short-description"></a><span data-ttu-id="199ea-106">简短说明</span><span class="sxs-lookup"><span data-stu-id="199ea-106">SHORT DESCRIPTION</span></span>
<span data-ttu-id="199ea-107">`enum`语句用于声明枚举。</span><span class="sxs-lookup"><span data-stu-id="199ea-107">The `enum` statement is used to declare an enumeration.</span></span> <span data-ttu-id="199ea-108">枚举是由一组称为枚举器列表的命名标签组成的不同类型。</span><span class="sxs-lookup"><span data-stu-id="199ea-108">An enumeration is a distinct type that consists of a set of named labels called the enumerator list.</span></span>

## <a name="long-description"></a><span data-ttu-id="199ea-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="199ea-109">LONG DESCRIPTION</span></span>

<span data-ttu-id="199ea-110">`enum`语句允许您创建一组强类型的标签。</span><span class="sxs-lookup"><span data-stu-id="199ea-110">The `enum` statement allows you to create a strongly typed set of labels.</span></span> <span data-ttu-id="199ea-111">可以在代码中使用该枚举，而不必分析或检查拼写错误。</span><span class="sxs-lookup"><span data-stu-id="199ea-111">That enumeration can be used in the code without having to parse or check for spelling errors.</span></span>

<span data-ttu-id="199ea-112">枚举内部表示为整数，起始值为零。</span><span class="sxs-lookup"><span data-stu-id="199ea-112">Enumerations are internally represented as integers with a starting value of zero.</span></span> <span data-ttu-id="199ea-113">向列表中的第一个标签分配值0。</span><span class="sxs-lookup"><span data-stu-id="199ea-113">The first label in the list is assigned the value zero.</span></span> <span data-ttu-id="199ea-114">剩余的标签用连续数字分配。</span><span class="sxs-lookup"><span data-stu-id="199ea-114">The remaining labels are assigned with consecutive numbers.</span></span>

<span data-ttu-id="199ea-115">在定义中，可以为标签提供任何整数值。</span><span class="sxs-lookup"><span data-stu-id="199ea-115">In the definition, labels can be given any integer value.</span></span> <span data-ttu-id="199ea-116">未分配值的标签采用下一个整数值。</span><span class="sxs-lookup"><span data-stu-id="199ea-116">Labels with no value assigned take the next integer value.</span></span>

## <a name="syntax-basic"></a><span data-ttu-id="199ea-117">Basic) 语法 (</span><span class="sxs-lookup"><span data-stu-id="199ea-117">Syntax (basic)</span></span>

```syntax
enum <enum-name> {
    <label> [= <int-value>]
    ...
}
```

## <a name="usage-example"></a><span data-ttu-id="199ea-118">用例</span><span class="sxs-lookup"><span data-stu-id="199ea-118">Usage example</span></span>

<span data-ttu-id="199ea-119">下面的示例演示可视为媒体文件的对象的枚举。</span><span class="sxs-lookup"><span data-stu-id="199ea-119">The following example shows an enumeration of objects that can be seen as media files.</span></span> <span data-ttu-id="199ea-120">定义将显式值分配给、、的基础 `music` 值 `picture` `video` 。</span><span class="sxs-lookup"><span data-stu-id="199ea-120">The definition assigns explicit values to the underlying values of `music`, `picture`, `video`.</span></span> <span data-ttu-id="199ea-121">紧跟显式赋值后的标签获取下一个整数值。</span><span class="sxs-lookup"><span data-stu-id="199ea-121">Labels immediately following an explicit assignment get the next integer value.</span></span> <span data-ttu-id="199ea-122">可以通过将相同的值分配给另一个标签来创建同义词;请参阅： `ogg` 、、、、、或的构造值 `oga` `mogg` `jpg` `jpeg` `mpg` `mpeg` 。</span><span class="sxs-lookup"><span data-stu-id="199ea-122">Synonyms can be created by assigning the same value to another label; see the constructed values for: `ogg`, `oga`, `mogg`, or `jpg`, `jpeg`, or `mpg`, `mpeg`.</span></span>

```powershell
enum MediaTypes {
    unknown
    music = 10
    mp3
    aac
    ogg = 15
    oga = 15
    mogg = 15
    picture = 20
    jpg
    jpeg = 21
    png
    video = 40
    mpg
    mpeg = 41
    avi
    m4v
}
```

<span data-ttu-id="199ea-123">`GetEnumNames()`方法返回枚举的标签列表。</span><span class="sxs-lookup"><span data-stu-id="199ea-123">The `GetEnumNames()` method returns the list of the labels for the enumeration.</span></span>

```powershell
[MediaTypes].GetEnumNames()
unknown
music
mp3
aac
ogg
oga
mogg
picture
jpg
jpeg
png
video
mpg
mpeg
avi
m4v
```

<span data-ttu-id="199ea-124">`GetEnumValues()`方法返回枚举的值列表。</span><span class="sxs-lookup"><span data-stu-id="199ea-124">The `GetEnumValues()` method returns the list of the values for the enumeration.</span></span>

```powershell
[MediaTypes].GetEnumValues()
unknown
music
mp3
aac
oga
oga
oga
picture
jpeg
jpeg
png
video
mpeg
mpeg
avi
m4v
```

<span data-ttu-id="199ea-125">**注意** ： GetEnumNames ( # A1 和 GetEnumValues ( # A3 似乎返回相同的结果。</span><span class="sxs-lookup"><span data-stu-id="199ea-125">**Note** : GetEnumNames() and GetEnumValues() seem to return the same results.</span></span>
<span data-ttu-id="199ea-126">但是，在内部，PowerShell 将值更改为标签。</span><span class="sxs-lookup"><span data-stu-id="199ea-126">However, internally, PowerShell is changing values into labels.</span></span> <span data-ttu-id="199ea-127">仔细阅读列表，你会注意到， `oga` 和在 `mogg` "获取名称" 结果下，但不在、、和的 "获取值" 类似的输出中 `jpg` `jpeg` `mpg` `mpeg` 。</span><span class="sxs-lookup"><span data-stu-id="199ea-127">Read the list carefully and you'll notice that `oga` and `mogg` are mentioned under the 'Get Names' results, but not under the 'Get Values' similar output for `jpg`, `jpeg`, and `mpg`, `mpeg`.</span></span>

```powershell
[MediaTypes].GetEnumName(15)
oga

[MediaTypes].GetEnumNames() | ForEach-Object {
  "{0,-10} {1}" -f $_,[int]([MediaTypes]::$_)
}
unknown    0
music      10
mp3        11
aac        12
ogg        15
oga        15
mogg       15
picture    20
jpg        21
jpeg       21
png        22
video      40
mpg        41
mpeg       41
avi        42
m4v        43
```

## <a name="enumerations-as-flags"></a><span data-ttu-id="199ea-128">作为标志的枚举</span><span class="sxs-lookup"><span data-stu-id="199ea-128">Enumerations as flags</span></span>

<span data-ttu-id="199ea-129">枚举可定义为位标志的集合。</span><span class="sxs-lookup"><span data-stu-id="199ea-129">Enumerations can be defined as a collection of bit flags.</span></span>
<span data-ttu-id="199ea-130">其中，在任何给定点，枚举表示一个或多个已打开的标志。</span><span class="sxs-lookup"><span data-stu-id="199ea-130">Where, at any given point the enumeration represents one or more of those flags turned on.</span></span>

<span data-ttu-id="199ea-131">为了使作为标志的枚举正常工作，每个标签都应具有两个值的幂。</span><span class="sxs-lookup"><span data-stu-id="199ea-131">For enumerations as flags to work properly, each label should have a power of two value.</span></span>

## <a name="syntax-flags"></a><span data-ttu-id="199ea-132">语法 (标志) </span><span class="sxs-lookup"><span data-stu-id="199ea-132">Syntax (flags)</span></span>

```syntax
[Flags()] enum <enum-name> {
    <label 0> [= 1]
    <label 1> [= 2]
    <label 2> [= 4]
    <label 3> [= 8]
    ...
}
```

## <a name="flags-usage-example"></a><span data-ttu-id="199ea-133">标志用法示例</span><span class="sxs-lookup"><span data-stu-id="199ea-133">Flags usage example</span></span>

<span data-ttu-id="199ea-134">在下面的示例中，将创建 *FileAttributes* 枚举。</span><span class="sxs-lookup"><span data-stu-id="199ea-134">In the following example the *FileAttributes* enumeration is created.</span></span>

```powershell
[Flags()] enum FileAttributes {
    Archive = 1
    Compressed = 2
    Device = 4
    Directory = 8
    Encrypted = 16
    Hidden = 32
}

[FileAttributes]$file1 = [FileAttributes]::Archive
[FileAttributes]$file1 +=[FileAttributes]::Compressed
[FileAttributes]$file1 +=  [FileAttributes]::Device
"file1 attributes are: $file1"

[FileAttributes]$file2 = [FileAttributes]28 ## => 16 + 8 + 4
"file2 attributes are: $file2"
```

```output
file1 attributes are: Archive, Compressed, Device
file2 attributes are: Device, Directory, Encrypted
```

<span data-ttu-id="199ea-135">若要测试特定的是否已设置，可以使用二进制比较运算符 `-band` 。</span><span class="sxs-lookup"><span data-stu-id="199ea-135">To test that a specific is set, you can use the binary comparison operator `-band`.</span></span> <span data-ttu-id="199ea-136">在此示例中，我们将测试的值为的 **设备** 和 **存档** 属性 `$file2` 。</span><span class="sxs-lookup"><span data-stu-id="199ea-136">In this example, we test for the **Device** and the **Archive** attributes in the value of `$file2`.</span></span>

```
PS > ($file2 -band [FileAttributes]::Device) -eq [FileAttributes]::Device
True

PS > ($file2 -band [FileAttributes]::Archive) -eq [FileAttributes]::Archive
False
```
