---
description: 描述使用 Microsoft .NET 类型的运算符。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 10/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_type_operators?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Type_Operators
ms.openlocfilehash: 6ea2ef2f61636d67a8bacf69ff577f477712a165
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200508"
---
# <a name="about-type-operators"></a><span data-ttu-id="1bc6e-104">关于类型运算符</span><span class="sxs-lookup"><span data-stu-id="1bc6e-104">About Type Operators</span></span>

## <a name="short-description"></a><span data-ttu-id="1bc6e-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="1bc6e-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="1bc6e-106">描述使用 Microsoft .NET 类型的运算符。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-106">Describes the operators that work with Microsoft .NET types.</span></span>

## <a name="long-description"></a><span data-ttu-id="1bc6e-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="1bc6e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="1bc6e-108">布尔类型运算符 (`-is` 和 `-isNot`) 指示对象是否为指定 .net 类型的实例。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-108">The Boolean type operators (`-is` and `-isNot`) tell whether an object is an instance of a specified .NET type.</span></span> <span data-ttu-id="1bc6e-109">`-is`如果类型匹配并且值为 FALSE，则运算符返回 **TRUE** ; 否则返回 **FALSE** 。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-109">The `-is` operator returns a value of **TRUE** if the type matches and a value of **FALSE** otherwise.</span></span> <span data-ttu-id="1bc6e-110">`-isNot`如果类型匹配并且值为 **TRUE** ，则运算符将返回值 **FALSE** 。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-110">The `-isNot` operator returns a value of **FALSE** if the type matches and a value of **TRUE** otherwise.</span></span>

<span data-ttu-id="1bc6e-111">`-as`运算符尝试将输入对象转换为指定的 .net 类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-111">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="1bc6e-112">如果成功，则返回转换后的对象。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-112">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="1bc6e-113">如果失败，则返回 `$null`。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-113">If it fails, it returns `$null`.</span></span> <span data-ttu-id="1bc6e-114">它不会返回错误。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-114">It does not return an error.</span></span>

<span data-ttu-id="1bc6e-115">下表列出了 PowerShell 中的类型运算符。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-115">The following table lists the type operators in PowerShell.</span></span>

|<span data-ttu-id="1bc6e-116">运算符</span><span class="sxs-lookup"><span data-stu-id="1bc6e-116">Operator</span></span>|<span data-ttu-id="1bc6e-117">说明</span><span class="sxs-lookup"><span data-stu-id="1bc6e-117">Description</span></span>                |<span data-ttu-id="1bc6e-118">示例</span><span class="sxs-lookup"><span data-stu-id="1bc6e-118">Example</span></span>                          |
|--------|---------------------------|---------------------------------|
|`-is`   |<span data-ttu-id="1bc6e-119">当输入</span><span class="sxs-lookup"><span data-stu-id="1bc6e-119">Returns TRUE when the input</span></span>|`(get-date) -is [DateTime]`      |
|        |<span data-ttu-id="1bc6e-120">是的一个实例。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-120">is an instance of the</span></span>      |`True`                           |
|        |<span data-ttu-id="1bc6e-121">指定的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-121">specified .NET type.</span></span>       |                                 |
|`-isNot`|<span data-ttu-id="1bc6e-122">当输入</span><span class="sxs-lookup"><span data-stu-id="1bc6e-122">Returns TRUE when the input</span></span>|`(get-date) -isNot [DateTime]`   |
|        |<span data-ttu-id="1bc6e-123">不是的实例</span><span class="sxs-lookup"><span data-stu-id="1bc6e-123">not an instance of the</span></span>     |`False`                          |
|        |<span data-ttu-id="1bc6e-124">specified.NET 类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-124">specified.NET type.</span></span>        |                                 |
|`-as`   |<span data-ttu-id="1bc6e-125">将输入转换为</span><span class="sxs-lookup"><span data-stu-id="1bc6e-125">Converts the input to the</span></span>  |`"5/7/07" -as [DateTime]`        |
|        |<span data-ttu-id="1bc6e-126">指定的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-126">specified .NET type.</span></span>       |`Monday, May 7, 2007 12:00:00 AM`|

<span data-ttu-id="1bc6e-127">类型运算符的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="1bc6e-127">The syntax of the type operators is as follows:</span></span>

```powershell
<input> <operator> [.NET type]
```

<span data-ttu-id="1bc6e-128">你还可以使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="1bc6e-128">You can also use the following syntax:</span></span>

```powershell
<input> <operator> ".NET type"
```

<span data-ttu-id="1bc6e-129">.NET 类型可以在括号中编写为类型名称，也可以作为字符串写入，如 `[DateTime]` 或 `"DateTime"` 。 **System.DateTime**</span><span class="sxs-lookup"><span data-stu-id="1bc6e-129">The .NET type can be written as a type name in brackets or a string, such as `[DateTime]` or `"DateTime"` for **System.DateTime** .</span></span> <span data-ttu-id="1bc6e-130">如果类型不在 system 命名空间的根中，则指定该对象类型的完整名称。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-130">If the type is not at the root of the system namespace, specify the full name of the object type.</span></span> <span data-ttu-id="1bc6e-131">您可以省略 "System."。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-131">You can omit "System.".</span></span> <span data-ttu-id="1bc6e-132">例如，若 **要指定 system.exception，请输入** `[System.Diagnostics.Process]` 、 `[Diagnostics.Process]` 或 `"Diagnostics.Process"` 。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-132">For example, to specify **System.Diagnostics.Process** , enter `[System.Diagnostics.Process]`, `[Diagnostics.Process]`, or `"Diagnostics.Process"`.</span></span>

<span data-ttu-id="1bc6e-133">类型运算符始终作为一个整体对输入对象进行操作。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-133">The type operators always operate on the input object as a whole.</span></span> <span data-ttu-id="1bc6e-134">也就是说，如果输入对象是集合，则它是所测试的 _集合_ 类型，而不是集合的 _元素_ 的类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-134">That is, if the input object is a collection, it is the _collection_ type that is tested, not the types of the collection's _elements_ .</span></span>

### <a name="-isisnot-operators"></a><span data-ttu-id="1bc6e-135">-is/isNot 运算符</span><span class="sxs-lookup"><span data-stu-id="1bc6e-135">-is/isNot operators</span></span>

<span data-ttu-id="1bc6e-136">**布尔** 类型运算符 (`-is` 和 `-isNot`) 总是返回一个 **布尔** 值，即使输入是对象的集合。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-136">The **Boolean** type operators (`-is` and `-isNot`) always return a **Boolean** value, even if the input is a collection of objects.</span></span>

<span data-ttu-id="1bc6e-137">如果 `<input>` 是与 .Net 类型相同或 _派生_ 自 .net 类型的类型，则 `-is` 运算符返回 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-137">If `<input>` is a type that is the same as or is _derived_ from the .NET Type, the `-is` operator returns `$True`.</span></span>

<span data-ttu-id="1bc6e-138">例如， **DirectoryInfo** 类型派生自 **FileSystemInfo** 类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-138">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="1bc6e-139">因此，这两个示例都返回 **True** 。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-139">Therefore, both of these examples return **True** .</span></span>

```powershell
PS> (Get-Item /) -is [System.IO.DirectoryInfo]
True
PS> (Get-Item /) -is [System.IO.FileSystemInfo]
True
```

<span data-ttu-id="1bc6e-140">`-is`如果在 `<input>` 比较中实现了接口，则运算符还可以匹配接口。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-140">The `-is` operator can also match interfaces if the `<input>` implements the interface in the comparison.</span></span> <span data-ttu-id="1bc6e-141">在此示例中，输入是一个数组。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-141">In this example, the input is an array.</span></span> <span data-ttu-id="1bc6e-142">数组实现了 **system.object** 接口。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-142">Arrays implement the **System.Collections.IList** interface.</span></span>

```powershell
PS> 1, 2 -is [System.Collections.IList]
True
```

### <a name="-as-operator"></a><span data-ttu-id="1bc6e-143">-as 运算符</span><span class="sxs-lookup"><span data-stu-id="1bc6e-143">-as operator</span></span>

<span data-ttu-id="1bc6e-144">`-as`运算符尝试将输入对象转换为指定的 .net 类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-144">The `-as` operator tries to convert the input object to the specified .NET type.</span></span> <span data-ttu-id="1bc6e-145">如果成功，则返回转换后的对象。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-145">If it succeeds, it returns the converted object.</span></span> <span data-ttu-id="1bc6e-146">如果失败，它将返回 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-146">It if fails, it returns `$null`.</span></span> <span data-ttu-id="1bc6e-147">它不会返回错误。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-147">It does not return an error.</span></span>

<span data-ttu-id="1bc6e-148">如果 `<input>` 是 _派生_ 自 .net 类型的类型，则 `-as` _通过_ 返回的输入对象保持不变。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-148">If the `<input>` is a type that is _derived_ from the .NET Type `-as` _passes through_ returns input object unchanged.</span></span> <span data-ttu-id="1bc6e-149">例如， **DirectoryInfo** 类型派生自 **FileSystemInfo** 类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-149">For example, the **DirectoryInfo** type is derived from the **FileSystemInfo** type.</span></span> <span data-ttu-id="1bc6e-150">因此，在以下示例中，对象类型保持不变：</span><span class="sxs-lookup"><span data-stu-id="1bc6e-150">Therefore, the object type is unchanged in the following example:</span></span>

```powershell
PS> $fsroot = (Get-Item /) -as [System.IO.FileSystemInfo]
PS> $fsroot.GetType().FullName
System.IO.DirectoryInfo
```

#### <a name="converting-the-datetime-type-is-culture-sensitive"></a><span data-ttu-id="1bc6e-151">转换 DateTime 类型区分区域性</span><span class="sxs-lookup"><span data-stu-id="1bc6e-151">Converting the DateTime type is culture-sensitive</span></span>

<span data-ttu-id="1bc6e-152">与类型强制转换不同， `[DateTime]` 使用运算符转换为类型 `-as` 仅适用于根据当前区域性的规则进行格式设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-152">Unlike type casting, converting to `[DateTime]` type using the `-as` operator only works with strings that are formatted according to the rules of the current culture.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr-FR'
PS> '13/5/20' -as [datetime]

mercredi 13 mai 2020 00:00:00

PS> '05/13/20' -as [datetime]
PS> [datetime]'05/13/20'

mercredi 13 mai 2020 00:00:00

PS> [datetime]'13/05/20'
InvalidArgument: Cannot convert value "13/05/20" to type "System.DateTime".
Error: "String '13/05/20' was not recognized as a valid DateTime."
```

<span data-ttu-id="1bc6e-153">若要查找对象的 .NET 类型，请使用 `Get-Member` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-153">To find the .NET type of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="1bc6e-154">或者，将所有对象的 **GetType** 方法与此方法的 **FullName** 属性一起使用。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-154">Or, use the **GetType** method of all the objects together with the **FullName** property of this method.</span></span> <span data-ttu-id="1bc6e-155">例如，下面的语句获取命令的返回值的类型 `Get-Culture` ：</span><span class="sxs-lookup"><span data-stu-id="1bc6e-155">For example, the following statement gets the type of the return value of a `Get-Culture` command:</span></span>

```powershell
PS> (Get-Culture).GetType().FullName
System.Globalization.CultureInfo
```

## <a name="examples"></a><span data-ttu-id="1bc6e-156">示例</span><span class="sxs-lookup"><span data-stu-id="1bc6e-156">EXAMPLES</span></span>

<span data-ttu-id="1bc6e-157">下面的示例演示类型运算符的一些用法：</span><span class="sxs-lookup"><span data-stu-id="1bc6e-157">The following examples show some uses of the Type operators:</span></span>

```powershell
PS> 32 -is [Float]
False

PS> 32 -is "int"
True

PS> (get-date) -is [DateTime]
True

PS> "12/31/2007" -is [DateTime]
False

PS> "12/31/2007" -is [String]
True

PS> (get-process PowerShell)[0] -is [System.Diagnostics.Process]
True

PS> (get-command get-member) -is [System.Management.Automation.CmdletInfo]
True
```

<span data-ttu-id="1bc6e-158">下面的示例演示当输入为对象的集合时，匹配类型为集合的 .NET 类型，而不是集合中各个对象的类型。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-158">The following example shows that when the input is a collection of objects, the matching type is the .NET type of the collection, not the type of the individual objects in the collection.</span></span>

<span data-ttu-id="1bc6e-159">在此示例中，尽管 `Get-Culture` 和 `Get-UICulture` cmdlet 都返回 **system.object** 对象，但这些对象的集合是一个 system.object 数组。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-159">In this example, although both the `Get-Culture` and `Get-UICulture` cmdlets return **System.Globalization.CultureInfo** objects, a collection of these objects is a System.Object array.</span></span>

```powershell
PS> (get-culture) -is [System.Globalization.CultureInfo]
True

PS> (get-uiculture) -is [System.Globalization.CultureInfo]
True

PS> (get-culture), (get-uiculture) -is [System.Globalization.CultureInfo]
False

PS> (get-culture), (get-uiculture) -is [Array]
True

PS> (get-culture), (get-uiculture) | foreach {
  $_ -is [System.Globalization.CultureInfo])
}
True
True

PS> (get-culture), (get-uiculture) -is [Object]
True
```

<span data-ttu-id="1bc6e-160">下面的示例演示如何使用 `-as` 运算符。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-160">The following examples show how to use the `-as` operator.</span></span>

```powershell
PS> "12/31/07" -is [DateTime]
False

PS> "12/31/07" -as [DateTime]
Monday, December 31, 2007 12:00:00 AM

PS> $date = "12/31/07" -as [DateTime]

C:\PS>$a -is [DateTime]
True

PS> 1031 -as [System.Globalization.CultureInfo]

LCID      Name      DisplayName
----      ----      -----------
1031      de-DE     German (Germany)
```

<span data-ttu-id="1bc6e-161">下面的示例演示当 `-as` 运算符不能将输入对象转换为 .net 类型时，它将返回 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="1bc6e-161">The following example shows that when the `-as` operator cannot convert the input object to the .NET type, it returns `$null`.</span></span>

```powershell
PS> 1031 -as [System.Diagnostics.Process]
PS>
```

## <a name="see-also"></a><span data-ttu-id="1bc6e-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bc6e-162">SEE ALSO</span></span>

[<span data-ttu-id="1bc6e-163">about_Operators</span><span class="sxs-lookup"><span data-stu-id="1bc6e-163">about_Operators</span></span>](about_Operators.md)
