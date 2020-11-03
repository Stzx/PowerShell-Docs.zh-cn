---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/compare-object?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Compare-Object
ms.openlocfilehash: c72cde8e626993726ae1a52206c88e20c3a7c588
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "93200738"
---
# <span data-ttu-id="e9726-103">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-103">Compare-Object</span></span>

## <span data-ttu-id="e9726-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e9726-104">Synopsis</span></span>
<span data-ttu-id="e9726-105">将两组对象进行比较。</span><span class="sxs-lookup"><span data-stu-id="e9726-105">Compares two sets of objects.</span></span>

## <span data-ttu-id="e9726-106">语法</span><span class="sxs-lookup"><span data-stu-id="e9726-106">Syntax</span></span>

```
Compare-Object [-ReferenceObject] <PSObject[]> [-DifferenceObject] <PSObject[]>
 [-SyncWindow <Int32>] [-Property <Object[]>] [-ExcludeDifferent] [-IncludeEqual] [-PassThru]
 [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="e9726-107">说明</span><span class="sxs-lookup"><span data-stu-id="e9726-107">Description</span></span>

<span data-ttu-id="e9726-108">`Compare-Object`Cmdlet 比较两组对象。</span><span class="sxs-lookup"><span data-stu-id="e9726-108">The `Compare-Object` cmdlet compares two sets of objects.</span></span> <span data-ttu-id="e9726-109">一组对象是 **引用** ，而另一组对象则是 **不同** 的。</span><span class="sxs-lookup"><span data-stu-id="e9726-109">One set of objects is the **reference** , and the other set of objects is the **difference** .</span></span>

<span data-ttu-id="e9726-110">`Compare-Object` 检查比较整个对象的可用方法。</span><span class="sxs-lookup"><span data-stu-id="e9726-110">`Compare-Object` checks for available methods of comparing a whole object.</span></span> <span data-ttu-id="e9726-111">如果找不到合适的方法，它将调用 input 对象的 **ToString ( # B1** 方法，并比较字符串结果。</span><span class="sxs-lookup"><span data-stu-id="e9726-111">If it can't find a suitable method, it calls the **ToString()** methods of the input objects and compares the string results.</span></span> <span data-ttu-id="e9726-112">您可以提供一个或多个用于比较的属性。</span><span class="sxs-lookup"><span data-stu-id="e9726-112">You can provide one or more properties to be used for comparison.</span></span> <span data-ttu-id="e9726-113">当提供属性时，cmdlet 仅比较这些属性的值。</span><span class="sxs-lookup"><span data-stu-id="e9726-113">When properties are provided, the cmdlet compares the values of those properties only.</span></span>

<span data-ttu-id="e9726-114">比较的结果将指示属性值是只出现在 **引用** 对象中 (`<=`) 还是仅出现在 **差异** 对象 () 中 `=>` 。</span><span class="sxs-lookup"><span data-stu-id="e9726-114">The result of the comparison indicates whether a property value appeared only in the **reference** object (`<=`) or only in the **difference** object (`=>`).</span></span> <span data-ttu-id="e9726-115">如果使用了 **IncludeEqual** 参数， (`==`) 指示值在两个对象中。</span><span class="sxs-lookup"><span data-stu-id="e9726-115">If the **IncludeEqual** parameter is used, (`==`) indicates the value is in both objects.</span></span>

<span data-ttu-id="e9726-116">如果 **引用** 或 **差异** 对象为 null (`$null`) ，则 `Compare-Object` 生成终止错误。</span><span class="sxs-lookup"><span data-stu-id="e9726-116">If the **reference** or the **difference** objects are null (`$null`), `Compare-Object` generates a terminating error.</span></span>

<span data-ttu-id="e9726-117">一些示例使用展开来减少代码示例的行长度。</span><span class="sxs-lookup"><span data-stu-id="e9726-117">Some examples use splatting to reduce the line length of the code samples.</span></span> <span data-ttu-id="e9726-118">有关详细信息，请参阅 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="e9726-118">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="e9726-119">示例</span><span class="sxs-lookup"><span data-stu-id="e9726-119">Examples</span></span>

### <span data-ttu-id="e9726-120">示例 1-比较两个文本文件的内容</span><span class="sxs-lookup"><span data-stu-id="e9726-120">Example 1 - Compare the content of two text files</span></span>

<span data-ttu-id="e9726-121">此示例比较两个文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="e9726-121">This example compares the contents of two text files.</span></span> <span data-ttu-id="e9726-122">该示例使用以下两个文本文件，每个值都在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="e9726-122">The example uses the following two text files, with each value on a separate line.</span></span>

- <span data-ttu-id="e9726-123">`Testfile1.txt` 包含以下值： dog、squirrel 和鸟。</span><span class="sxs-lookup"><span data-stu-id="e9726-123">`Testfile1.txt` contains the values: dog, squirrel, and bird.</span></span>
- <span data-ttu-id="e9726-124">`Testfile2.txt` 包含值： cat、鸟和 racoon。</span><span class="sxs-lookup"><span data-stu-id="e9726-124">`Testfile2.txt` contains the values: cat, bird, and racoon.</span></span>

<span data-ttu-id="e9726-125">输出只显示文件之间的不同行。</span><span class="sxs-lookup"><span data-stu-id="e9726-125">The output displays only the lines that are different between the files.</span></span> <span data-ttu-id="e9726-126">`Testfile1.txt`**引用** 对象 (`<=`) ， `Testfile2.txt` 是 () 的 **差异** 对象 `=>` 。</span><span class="sxs-lookup"><span data-stu-id="e9726-126">`Testfile1.txt` is the **reference** object (`<=`) and `Testfile2.txt`is the **difference** object (`=>`).</span></span> <span data-ttu-id="e9726-127">不会显示带有同时出现在这两个文件中的内容的行。</span><span class="sxs-lookup"><span data-stu-id="e9726-127">Lines with content that appear in both files aren't displayed.</span></span>

```powershell
Compare-Object -ReferenceObject (Get-Content -Path C:\Test\Testfile1.txt) -DifferenceObject (Get-Content -Path C:\Test\Testfile2.txt)
```

```Output
InputObject SideIndicator
----------- -------------
cat         =>
racoon      =>
dog         <=
squirrel    <=
```

### <span data-ttu-id="e9726-128">示例 2-比较每个内容行并排除差异</span><span class="sxs-lookup"><span data-stu-id="e9726-128">Example 2 - Compare each line of content and exclude the differences</span></span>

<span data-ttu-id="e9726-129">此示例使用 **IncludeEqual** 和 **ExcludeDifferent** 参数来比较两个文本文件中的每行内容。</span><span class="sxs-lookup"><span data-stu-id="e9726-129">This example uses the **IncludeEqual** and **ExcludeDifferent** parameters to compare each line of content in two text files.</span></span>

<span data-ttu-id="e9726-130">由于该命令使用 **ExcludeDifferent** 参数，因此输出只包含两个文件中包含的行，如 **SideIndicator** () 所示 `==` 。</span><span class="sxs-lookup"><span data-stu-id="e9726-130">Because the command uses the **ExcludeDifferent** parameter, the output only contains lines contained in both files, as shown by the **SideIndicator** (`==`).</span></span>

```powershell
$objects = @{
  ReferenceObject = (Get-Content -Path C:\Test\Testfile1.txt)
  DifferenceObject = (Get-Content -Path C:\Test\Testfile2.txt)
}
Compare-Object @objects -IncludeEqual -ExcludeDifferent
```

```Output
InputObject SideIndicator
----------- -------------
bird        ==
```

<a id="ex3" />

### <span data-ttu-id="e9726-131">示例 3-显示使用 PassThru 参数时的差异</span><span class="sxs-lookup"><span data-stu-id="e9726-131">Example 3 - Show the difference when using the PassThru parameter</span></span>

<span data-ttu-id="e9726-132">通常， `Compare-Object` 返回具有以下属性的 **PSCustomObject** 类型：</span><span class="sxs-lookup"><span data-stu-id="e9726-132">Normally, `Compare-Object` returns a **PSCustomObject** type with the following properties:</span></span>

- <span data-ttu-id="e9726-133">要比较的 **InputObject**</span><span class="sxs-lookup"><span data-stu-id="e9726-133">The **InputObject** being compared</span></span>
- <span data-ttu-id="e9726-134">显示输出所属的输入对象的 **SideIndicator** 属性</span><span class="sxs-lookup"><span data-stu-id="e9726-134">The **SideIndicator** property showing which input object the output belongs to</span></span>

<span data-ttu-id="e9726-135">当使用 **PassThru** 参数时，不会更改对象的 **类型** ，但返回的对象的实例将添加一个名为 **SideIndicator** 的 **NoteProperty** 。</span><span class="sxs-lookup"><span data-stu-id="e9726-135">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator** .</span></span> <span data-ttu-id="e9726-136">**SideIndicator** 显示输出所属的输入对象。</span><span class="sxs-lookup"><span data-stu-id="e9726-136">**SideIndicator** shows which input object the output belongs to.</span></span>

<span data-ttu-id="e9726-137">下面的示例显示了不同的输出类型。</span><span class="sxs-lookup"><span data-stu-id="e9726-137">The following examples shows the different output types.</span></span>

```powershell
$a = $True
Compare-Object -IncludeEqual $a $a
(Compare-Object -IncludeEqual $a $a) | Get-Member
```

```Output
InputObject SideIndicator
----------- -------------
       True ==

   TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
InputObject   NoteProperty System.Boolean InputObject=True
SideIndicator NoteProperty string SideIndicator===
```

```powershell
Compare-Object -IncludeEqual $a $a -PassThru
(Compare-Object -IncludeEqual $a $a -PassThru) | Get-Member
```

```Output
True

   TypeName: System.Boolean
Name          MemberType   Definition
----          ----------   ----------
CompareTo     Method       int CompareTo(System.Object obj), int CompareTo(bool value), int IComparable.CompareTo(Syst
Equals        Method       bool Equals(System.Object obj), bool Equals(bool obj), bool IEquatable[bool].Equals(bool ot
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
GetTypeCode   Method       System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean     Method       bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte        Method       byte IConvertible.ToByte(System.IFormatProvider provider)
ToChar        Method       char IConvertible.ToChar(System.IFormatProvider provider)
ToDateTime    Method       datetime IConvertible.ToDateTime(System.IFormatProvider provider)
ToDecimal     Method       decimal IConvertible.ToDecimal(System.IFormatProvider provider)
ToDouble      Method       double IConvertible.ToDouble(System.IFormatProvider provider)
ToInt16       Method       short IConvertible.ToInt16(System.IFormatProvider provider)
ToInt32       Method       int IConvertible.ToInt32(System.IFormatProvider provider)
ToInt64       Method       long IConvertible.ToInt64(System.IFormatProvider provider)
ToSByte       Method       sbyte IConvertible.ToSByte(System.IFormatProvider provider)
ToSingle      Method       float IConvertible.ToSingle(System.IFormatProvider provider)
ToString      Method       string ToString(), string ToString(System.IFormatProvider provider), string IConvertible.To
ToType        Method       System.Object IConvertible.ToType(type conversionType, System.IFormatProvider provider)
ToUInt16      Method       ushort IConvertible.ToUInt16(System.IFormatProvider provider)
ToUInt32      Method       uint IConvertible.ToUInt32(System.IFormatProvider provider)
ToUInt64      Method       ulong IConvertible.ToUInt64(System.IFormatProvider provider)
TryFormat     Method       bool TryFormat(System.Span[char] destination, [ref] int charsWritten)
SideIndicator NoteProperty string SideIndicator===
```

<span data-ttu-id="e9726-138">使用 **PassThru** 时，将返回原始对象类型 ( **system.object** ) 。</span><span class="sxs-lookup"><span data-stu-id="e9726-138">When using **PassThru** , the original object type ( **System.Boolean** ) is returned.</span></span> <span data-ttu-id="e9726-139">请注意，由 **system.exception 对象的** 默认格式显示的输出如何不显示 **SideIndicator** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9726-139">Note how the output displayed by the default format for **System.Boolean** objects didn't display the **SideIndicator** property.</span></span> <span data-ttu-id="e9726-140">但是，返回的 **system.object** 对象具有添加的 **NoteProperty** 。</span><span class="sxs-lookup"><span data-stu-id="e9726-140">However, the returned **System.Boolean** object has the added **NoteProperty** .</span></span>

### <span data-ttu-id="e9726-141">示例 4-使用属性比较两个简单对象</span><span class="sxs-lookup"><span data-stu-id="e9726-141">Example 4 - Compare two simple objects using properties</span></span>

<span data-ttu-id="e9726-142">在此示例中，比较两个具有相同长度的不同字符串。</span><span class="sxs-lookup"><span data-stu-id="e9726-142">In this example, we compare two different string that have the same length.</span></span>

```powershell
Compare-Object -ReferenceObject 'abc' -DifferenceObject 'xyz' -Property Length -IncludeEqual
```

```Output
Length SideIndicator
------ -------------
     3 ==
```

### <span data-ttu-id="e9726-143">示例 5-使用属性比较复杂对象</span><span class="sxs-lookup"><span data-stu-id="e9726-143">Example 5 - Comparing complex objects using properties</span></span>

<span data-ttu-id="e9726-144">此示例显示比较复杂对象时的行为。</span><span class="sxs-lookup"><span data-stu-id="e9726-144">This example shows the behavior when comparing complex objects.</span></span> <span data-ttu-id="e9726-145">在此示例中，我们为不同的 PowerShell 实例存储两个不同的进程对象。</span><span class="sxs-lookup"><span data-stu-id="e9726-145">In this example we store two different process objects for different instances of PowerShell.</span></span> <span data-ttu-id="e9726-146">这两个变量都包含具有相同名称的进程对象。</span><span class="sxs-lookup"><span data-stu-id="e9726-146">Both variables contain process objects with the same name.</span></span> <span data-ttu-id="e9726-147">如果在不指定 **Property** 参数的情况下比较对象，则该 cmdlet 会将对象视为相等。</span><span class="sxs-lookup"><span data-stu-id="e9726-147">When the objects are compared without specifying the **Property** parameter, the cmdlet considers the objects to be equal.</span></span> <span data-ttu-id="e9726-148">请注意， **InputObject** 的值与 **ToString ( # B1** 方法的结果相同。</span><span class="sxs-lookup"><span data-stu-id="e9726-148">Notice that the value of the **InputObject** is the same as the result of the **ToString()** method.</span></span> <span data-ttu-id="e9726-149">由于 system.exception **类没有** **IComparable** 接口，因此该 cmdlet 将对象转换为字符串，然后对结果进行比较。</span><span class="sxs-lookup"><span data-stu-id="e9726-149">Since the **System.Diagnostics.Process** class does not have the **IComparable** interface, the cmdlet converts the objects to strings then compares the results.</span></span>

```powershell
PS> Get-Process pwsh

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    101   123.32     139.10      35.81   11168   1 pwsh
     89   107.55      66.97      11.44   17600   1 pwsh

PS> $a = Get-Process -Id 11168
PS> $b = Get-Process -Id 17600
PS> $a.ToString()
System.Diagnostics.Process (pwsh)
PS> $b.ToString()
System.Diagnostics.Process (pwsh)
PS> Compare-Object $a $b -IncludeEqual

InputObject                       SideIndicator
-----------                       -------------
System.Diagnostics.Process (pwsh) ==

PS> Compare-Object $a $b -Property ProcessName, Id, CPU

ProcessName    Id       CPU SideIndicator
-----------    --       --- -------------
pwsh        17600   11.4375 =>
pwsh        11168 36.203125 <=
```

<span data-ttu-id="e9726-150">指定要比较的属性时，该 cmdlet 将显示差异。</span><span class="sxs-lookup"><span data-stu-id="e9726-150">When you specify properties to be compared, the cmdlet shows the differences.</span></span>

### <span data-ttu-id="e9726-151">示例 6-比较实现 IComparable 的复杂对象</span><span class="sxs-lookup"><span data-stu-id="e9726-151">Example 6 - Comparing complex objects that implement IComparable</span></span>

<span data-ttu-id="e9726-152">如果对象实现 **IComparable** ，则该 cmdlet 会搜索比较对象的方法。如果对象属于不同类型，则 **差异** 对象将转换为 **ReferenceObject** 的类型，然后进行比较。</span><span class="sxs-lookup"><span data-stu-id="e9726-152">If the object implements **IComparable** , the cmdlet searches for ways to compare the objects.If the objects are different types, the **Difference** object is converted to the type of the **ReferenceObject** then compared.</span></span>

<span data-ttu-id="e9726-153">在此示例中，我们将字符串与 **TimeSpan** 对象进行比较。</span><span class="sxs-lookup"><span data-stu-id="e9726-153">In this example, we are comparing a string to a **TimeSpan** object.</span></span> <span data-ttu-id="e9726-154">在第一种情况下，将字符串转换为 **TimeSpan** ，使对象相等。</span><span class="sxs-lookup"><span data-stu-id="e9726-154">In the first case, the string is converted to a **TimeSpan** so the objects are equal.</span></span>

```powershell
Compare-Object ([TimeSpan]"0:0:1") "0:0:1" -IncludeEqual
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    ==
```

```powershell
Compare-Object "0:0:1" ([TimeSpan]"0:0:1")
```

```Output
InputObject SideIndicator
----------- -------------
00:00:01    =>
0:0:1       <=
```

<span data-ttu-id="e9726-155">在第二种情况下， **TimeSpan** 转换为字符串，因此对象不同。</span><span class="sxs-lookup"><span data-stu-id="e9726-155">In the second case, the **TimeSpan** is converted to a string so the object are different.</span></span>

## <span data-ttu-id="e9726-156">parameters</span><span class="sxs-lookup"><span data-stu-id="e9726-156">Parameters</span></span>

### <span data-ttu-id="e9726-157">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="e9726-157">-CaseSensitive</span></span>

<span data-ttu-id="e9726-158">指示比较应区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e9726-158">Indicates that comparisons should be case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-159">-Culture</span><span class="sxs-lookup"><span data-stu-id="e9726-159">-Culture</span></span>

<span data-ttu-id="e9726-160">指定比较中要使用的区域性。</span><span class="sxs-lookup"><span data-stu-id="e9726-160">Specifies the culture to use for comparisons.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-161">-DifferenceObject</span><span class="sxs-lookup"><span data-stu-id="e9726-161">-DifferenceObject</span></span>

<span data-ttu-id="e9726-162">指定与 **引用** 对象进行比较的对象。</span><span class="sxs-lookup"><span data-stu-id="e9726-162">Specifies the objects that are compared to the **reference** objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-163">-ExcludeDifferent</span><span class="sxs-lookup"><span data-stu-id="e9726-163">-ExcludeDifferent</span></span>

<span data-ttu-id="e9726-164">指示此 cmdlet 仅显示相等的比较对象的特征。</span><span class="sxs-lookup"><span data-stu-id="e9726-164">Indicates that this cmdlet displays only the characteristics of compared objects that are equal.</span></span> <span data-ttu-id="e9726-165">丢弃对象之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e9726-165">The differences between the objects are discarded.</span></span>

<span data-ttu-id="e9726-166">结合使用 **ExcludeDifferent** 和 **IncludeEqual** ，只显示 **引用** 对象与 **差异** 对象之间的匹配行。</span><span class="sxs-lookup"><span data-stu-id="e9726-166">Use **ExcludeDifferent** with **IncludeEqual** to display only the lines that match between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="e9726-167">如果未指定 **ExcludeDifferent** ， **则** 没有任何输出。</span><span class="sxs-lookup"><span data-stu-id="e9726-167">If **ExcludeDifferent** is specified without **IncludeEqual** , there's no output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-168">-IncludeEqual</span><span class="sxs-lookup"><span data-stu-id="e9726-168">-IncludeEqual</span></span>

<span data-ttu-id="e9726-169">**IncludeEqual** 显示 **引用** 对象与 **差异** 对象之间的匹配项。</span><span class="sxs-lookup"><span data-stu-id="e9726-169">**IncludeEqual** displays the matches between the **reference** and **difference** objects.</span></span>

<span data-ttu-id="e9726-170">默认情况下，输出还包括 **reference** 对象和 **差异** 对象之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e9726-170">By default, the output also includes the differences between the **reference** and **difference** objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-171">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e9726-171">-PassThru</span></span>

<span data-ttu-id="e9726-172">当使用 **PassThru** 参数时，将 `Compare-Object` 省略比较的对象周围的 **PSCustomObject** 包装，并返回不变的不同对象。</span><span class="sxs-lookup"><span data-stu-id="e9726-172">When you use the **PassThru** parameter, `Compare-Object` omits the **PSCustomObject** wrapper around the compared objects and returns the differing objects, unchanged.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-173">-Property</span><span class="sxs-lookup"><span data-stu-id="e9726-173">-Property</span></span>

<span data-ttu-id="e9726-174">指定要比较的 **引用** 对象和 **差异** 对象的属性数组。</span><span class="sxs-lookup"><span data-stu-id="e9726-174">Specifies an array of properties of the **reference** and **difference** objects to compare.</span></span>

<span data-ttu-id="e9726-175">**Property** 参数的值可以是新的计算属性。</span><span class="sxs-lookup"><span data-stu-id="e9726-175">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="e9726-176">计算属性可以是脚本块，也可以是哈希表。</span><span class="sxs-lookup"><span data-stu-id="e9726-176">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="e9726-177">有效的键-值对为：</span><span class="sxs-lookup"><span data-stu-id="e9726-177">Valid key-value pairs are:</span></span>

- <span data-ttu-id="e9726-178">Expression `<string>` 或 `<script block>`</span><span class="sxs-lookup"><span data-stu-id="e9726-178">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="e9726-179">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e9726-179">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-180">-ReferenceObject</span><span class="sxs-lookup"><span data-stu-id="e9726-180">-ReferenceObject</span></span>

<span data-ttu-id="e9726-181">指定用作比较引用的对象数组。</span><span class="sxs-lookup"><span data-stu-id="e9726-181">Specifies an array of objects used as a reference for comparison.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-182">-SyncWindow</span><span class="sxs-lookup"><span data-stu-id="e9726-182">-SyncWindow</span></span>

<span data-ttu-id="e9726-183">指定 `Compare-Object` 在对象集合中查找匹配项时所检查的相邻对象的数目。</span><span class="sxs-lookup"><span data-stu-id="e9726-183">Specifies the number of adjacent objects that `Compare-Object` inspects while looking for a match in a collection of objects.</span></span> <span data-ttu-id="e9726-184">`Compare-Object` 当相邻对象在集合中的同一位置找不到该对象时，检查它们。</span><span class="sxs-lookup"><span data-stu-id="e9726-184">`Compare-Object` examines adjacent objects when it doesn't find the object in the same position in a collection.</span></span> <span data-ttu-id="e9726-185">默认值为 `[Int32]::MaxValue` ，这意味着 `Compare-Object` 检查整个对象集合。</span><span class="sxs-lookup"><span data-stu-id="e9726-185">The default value is `[Int32]::MaxValue`, which means that `Compare-Object` examines the entire object collection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: [Int32]::MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e9726-186">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e9726-186">CommonParameters</span></span>

<span data-ttu-id="e9726-187">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e9726-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e9726-188">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e9726-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e9726-189">输入</span><span class="sxs-lookup"><span data-stu-id="e9726-189">Inputs</span></span>

### <span data-ttu-id="e9726-190">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="e9726-190">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="e9726-191">可以将对象向下发送到 **DifferenceObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="e9726-191">You can send an object down the pipeline to the **DifferenceObject** parameter.</span></span>

## <span data-ttu-id="e9726-192">Outputs</span><span class="sxs-lookup"><span data-stu-id="e9726-192">Outputs</span></span>

### <span data-ttu-id="e9726-193">无</span><span class="sxs-lookup"><span data-stu-id="e9726-193">None</span></span>

<span data-ttu-id="e9726-194">如果 **引用** 对象和 **差异** 对象相同，则没有输出，除非使用 **IncludeEqual** 参数。</span><span class="sxs-lookup"><span data-stu-id="e9726-194">If the **reference** object and the **difference** object are the same, there's no output, unless you use the **IncludeEqual** parameter.</span></span>

### <span data-ttu-id="e9726-195">System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="e9726-195">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="e9726-196">如果对象不同，则 `Compare-Object` 使用 SideIndicator 属性包装包装中的不同对象， `PSCustomObject` 以引用差异。 **SideIndicator**</span><span class="sxs-lookup"><span data-stu-id="e9726-196">If the objects are different, `Compare-Object` wraps the differing objects in a `PSCustomObject` wrapper with a **SideIndicator** property to reference the differences.</span></span>

<span data-ttu-id="e9726-197">当使用 **PassThru** 参数时，不会更改对象的 **类型** ，但返回的对象的实例将添加一个名为 **SideIndicator** 的 **NoteProperty** 。</span><span class="sxs-lookup"><span data-stu-id="e9726-197">When you use the **PassThru** parameter, the **Type** of the object is not changed but the instance of the object returned has an added **NoteProperty** named **SideIndicator** .</span></span> <span data-ttu-id="e9726-198">**SideIndicator** 显示输出所属的输入对象。</span><span class="sxs-lookup"><span data-stu-id="e9726-198">**SideIndicator** shows which input object the output belongs to.</span></span>

## <span data-ttu-id="e9726-199">注释</span><span class="sxs-lookup"><span data-stu-id="e9726-199">Notes</span></span>

<span data-ttu-id="e9726-200">使用 **PassThru** 参数时，控制台中显示的输出可能不包括 **SideIndicator** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9726-200">When using the **PassThru** parameter, the output displayed in the console may not include the **SideIndicator** property.</span></span> <span data-ttu-id="e9726-201">的对象类型输出的默认格式视图 `Compare-Object` 不包括 **SideIndicator** 属性。</span><span class="sxs-lookup"><span data-stu-id="e9726-201">The default format view of the for the object type output by `Compare-Object` does not include the **SideIndicator** property.</span></span> <span data-ttu-id="e9726-202">有关详细信息，请参阅本文中的 [示例 3](#ex3) 。</span><span class="sxs-lookup"><span data-stu-id="e9726-202">For more information see [Example 3](#ex3) in this article.</span></span>

## <span data-ttu-id="e9726-203">相关链接</span><span class="sxs-lookup"><span data-stu-id="e9726-203">Related links</span></span>

[<span data-ttu-id="e9726-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="e9726-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="e9726-205">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-205">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="e9726-206">Group-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-206">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="e9726-207">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-207">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="e9726-208">New-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-208">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="e9726-209">Select-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-209">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="e9726-210">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-210">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="e9726-211">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-211">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="e9726-212">Where-Object</span><span class="sxs-lookup"><span data-stu-id="e9726-212">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)

[<span data-ttu-id="e9726-213">Get-Process</span><span class="sxs-lookup"><span data-stu-id="e9726-213">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)
