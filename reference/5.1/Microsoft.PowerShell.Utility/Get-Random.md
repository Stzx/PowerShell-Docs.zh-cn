---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-random?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Random
ms.openlocfilehash: 6aa7d6db9e8c2fb8a3001c8ddb9593a7ceafe2ab
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197919"
---
# <span data-ttu-id="0aa7a-103">Get-Random</span><span class="sxs-lookup"><span data-stu-id="0aa7a-103">Get-Random</span></span>

## <span data-ttu-id="0aa7a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0aa7a-104">SYNOPSIS</span></span>
<span data-ttu-id="0aa7a-105">获取一个随机数，或从集合中随机选择对象。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-105">Gets a random number, or selects objects randomly from a collection.</span></span>

## <span data-ttu-id="0aa7a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0aa7a-106">SYNTAX</span></span>

### <span data-ttu-id="0aa7a-107">RandomNumberParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="0aa7a-107">RandomNumberParameterSet (Default)</span></span>

```
Get-Random [-SetSeed <Int32>] [[-Maximum] <Object>] [-Minimum <Object>] [<CommonParameters>]
```

### <span data-ttu-id="0aa7a-108">RandomListItemParameterSet</span><span class="sxs-lookup"><span data-stu-id="0aa7a-108">RandomListItemParameterSet</span></span>

```
Get-Random [-SetSeed <Int32>] [-InputObject] <Object[]> [-Count <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="0aa7a-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0aa7a-109">DESCRIPTION</span></span>

<span data-ttu-id="0aa7a-110">`Get-Random`Cmdlet 将获取随机选择的数字。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-110">The `Get-Random` cmdlet gets a randomly selected number.</span></span> <span data-ttu-id="0aa7a-111">如果将对象的集合提交到 `Get-Random` ，则它将从集合中获取一个或多个随机选择的对象。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-111">If you submit a collection of objects to `Get-Random`, it gets one or more randomly selected objects from the collection.</span></span>

<span data-ttu-id="0aa7a-112">如果不使用参数或输入，则 `Get-Random` 命令将返回 0 (零) 和 () 之间随机选择的 **Int32.MaxValue** 32 位无符号 `0x7FFFFFFF` 整数 `2,147,483,647` 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-112">Without parameters or input, a `Get-Random` command returns a randomly selected 32-bit unsigned integer between 0 (zero) and **Int32.MaxValue** (`0x7FFFFFFF`, `2,147,483,647`).</span></span>

<span data-ttu-id="0aa7a-113">您可以使用的参数 `Get-Random` 指定种子数、最小值和最大值，以及从已提交的集合中返回的对象数。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-113">You can use the parameters of `Get-Random` to specify a seed number, minimum and maximum values, and the number of objects returned from a submitted collection.</span></span>

## <span data-ttu-id="0aa7a-114">示例</span><span class="sxs-lookup"><span data-stu-id="0aa7a-114">EXAMPLES</span></span>

### <span data-ttu-id="0aa7a-115">示例1：获取随机整数</span><span class="sxs-lookup"><span data-stu-id="0aa7a-115">Example 1: Get a random integer</span></span>

<span data-ttu-id="0aa7a-116">此命令将获取一个介于 0 (零) 之间的随机 **整数。**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-116">This command gets a random integer between 0 (zero) and **Int32.MaxValue** .</span></span>

```powershell
Get-Random
```

```Output
3951433
```

### <span data-ttu-id="0aa7a-117">示例2：获取0到99之间的随机整数</span><span class="sxs-lookup"><span data-stu-id="0aa7a-117">Example 2: Get a random integer between 0 and 99</span></span>

```powershell
Get-Random -Maximum 100
```

```Output
47
```

### <span data-ttu-id="0aa7a-118">示例3：获取-100 和99之间的随机整数</span><span class="sxs-lookup"><span data-stu-id="0aa7a-118">Example 3: Get a random integer between -100 and 99</span></span>

```powershell
Get-Random -Minimum -100 -Maximum 100
```

```Output
56
```

### <span data-ttu-id="0aa7a-119">示例4：获取随机浮点数</span><span class="sxs-lookup"><span data-stu-id="0aa7a-119">Example 4: Get a random floating-point number</span></span>

<span data-ttu-id="0aa7a-120">此命令将获取一个大于或等于 10.7 且小于 20.92 的随机浮点数。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-120">This command gets a random floating-point number greater than or equal to 10.7 and less than 20.92.</span></span>

```powershell
Get-Random -Minimum 10.7 -Maximum 20.93
```

```Output
18.08467273887
```

### <span data-ttu-id="0aa7a-121">示例5：从数组获取随机整数</span><span class="sxs-lookup"><span data-stu-id="0aa7a-121">Example 5: Get a random integer from an array</span></span>

<span data-ttu-id="0aa7a-122">此命令将从指定的数组中获取一个随机选择的数字。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-122">This command gets a randomly selected number from the specified array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random
```

```Output
8
```

### <span data-ttu-id="0aa7a-123">示例6：从数组获取几个随机整数</span><span class="sxs-lookup"><span data-stu-id="0aa7a-123">Example 6: Get several random integers from an array</span></span>

<span data-ttu-id="0aa7a-124">此命令以随机顺序从数组中获取三个随机选择的数字。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-124">This command gets three randomly selected numbers in random order from an array.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count 3
```

```Output
3
1
13
```

### <span data-ttu-id="0aa7a-125">示例7：随机化整个集合</span><span class="sxs-lookup"><span data-stu-id="0aa7a-125">Example 7: Randomize an entire collection</span></span>

<span data-ttu-id="0aa7a-126">此命令将按随机顺序返回整个集合。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-126">This command returns the entire collection in random order.</span></span>

<span data-ttu-id="0aa7a-127">**Count** 参数的值是 **整数的一个静态属性** 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-127">The value of the **Count** parameter is the **MaxValue** static property of integers.</span></span>

<span data-ttu-id="0aa7a-128">若要按随机顺序返回整个集合，请输入任一大于或等于该集合中的对象数的数字。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-128">To return an entire collection in random order, enter any number that is greater than or equal to the number of objects in the collection.</span></span>

```powershell
1, 2, 3, 5, 8, 13 | Get-Random -Count ([int]::MaxValue)
```

```Output
2
3
5
1
8
13
```

### <span data-ttu-id="0aa7a-129">示例8：获取随机非数值</span><span class="sxs-lookup"><span data-stu-id="0aa7a-129">Example 8: Get a random non-numeric value</span></span>

<span data-ttu-id="0aa7a-130">此命令将从非数值集合中返回一个随机值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-130">This command returns a random value from a non-numeric collection.</span></span>

```powershell
"red", "yellow", "blue" | Get-Random
```

```Output
yellow
```

### <span data-ttu-id="0aa7a-131">示例9：使用 SetSeed 参数</span><span class="sxs-lookup"><span data-stu-id="0aa7a-131">Example 9: Use the SetSeed parameter</span></span>

<span data-ttu-id="0aa7a-132">此示例显示了使用 **SetSeed** 参数的效果。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-132">This example shows the effect of using the **SetSeed** parameter.</span></span>

<span data-ttu-id="0aa7a-133">因为 **SetSeed** 会产生非随机行为，所以它通常仅用于重现结果，例如调试或分析脚本时。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-133">Because **SetSeed** produces non-random behavior, it's typically used only to reproduce results, such as when debugging or analyzing a script.</span></span>

```powershell
# Commands with the default seed are pseudorandom
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

```powershell
# Commands with the same seed are not random
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100 -SetSeed 23
```

```Output
74
74
74
```

```powershell
# SetSeed results in a repeatable series
Get-Random -Maximum 100 -SetSeed 23
Get-Random -Maximum 100
Get-Random -Maximum 100
Get-Random -Maximum 100
```

```Output
74
56
84
46
```

### <span data-ttu-id="0aa7a-134">示例10：获取随机文件</span><span class="sxs-lookup"><span data-stu-id="0aa7a-134">Example 10: Get random files</span></span>

<span data-ttu-id="0aa7a-135">这些命令将从本地计算机驱动器获取随机选择的50文件示例 `C:` 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-135">These commands get a randomly selected sample of 50 files from the `C:` drive of the local computer.</span></span>

```powershell
$Files = Get-ChildItem -Path C:\* -Recurse
$Sample = $Files | Get-Random -Count 50
```

### <span data-ttu-id="0aa7a-136">示例11：滚动公平骰子</span><span class="sxs-lookup"><span data-stu-id="0aa7a-136">Example 11: Roll fair dice</span></span>

<span data-ttu-id="0aa7a-137">此示例将一个公平片1200次，并对结果进行计数。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-137">This example rolls a fair die 1200 times and counts the outcomes.</span></span> <span data-ttu-id="0aa7a-138">第一个命令 `For-EachObject` `Get-Random` 从数字 (1-6) 中的数字中重复对的调用。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-138">The first command, `For-EachObject` repeats the call to `Get-Random` from the piped in numbers (1-6).</span></span> <span data-ttu-id="0aa7a-139">结果按其值进行分组 `Group-Object` ，并将设置为带有的表格式 `Select-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-139">The results are grouped by their value with `Group-Object` and formatted as a table with `Select-Object`.</span></span>

```powershell
1..1200 | ForEach-Object {
    1..6 | Get-Random
} | Group-Object | Select-Object Name,Count
```

```Output
Name Count
---- -----
1      206
2      199
3      196
4      226
5      185
6      188
```

## <span data-ttu-id="0aa7a-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0aa7a-140">PARAMETERS</span></span>

### <span data-ttu-id="0aa7a-141">-Count</span><span class="sxs-lookup"><span data-stu-id="0aa7a-141">-Count</span></span>

<span data-ttu-id="0aa7a-142">指定要返回的随机对象或数字的数目。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-142">Specifies the number of random objects or numbers to return.</span></span> <span data-ttu-id="0aa7a-143">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-143">The default is 1.</span></span>

<span data-ttu-id="0aa7a-144">当与一起使用时 `InputObject` ，如果 **Count** 的值超过集合中的对象数， `Get-Random` 则将按随机顺序返回所有对象。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-144">When used with `InputObject`, if the value of **Count** exceeds the number of objects in the collection, `Get-Random` returns all of the objects in random order.</span></span>

```yaml
Type: System.Int32
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aa7a-145">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0aa7a-145">-InputObject</span></span>

<span data-ttu-id="0aa7a-146">指定对象的集合。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-146">Specifies a collection of objects.</span></span> <span data-ttu-id="0aa7a-147">`Get-Random` 以随机顺序从集合中随机选择的对象到 **Count** 指定的数字。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-147">`Get-Random` gets randomly selected objects in random order from the collection up to the number specified by **Count** .</span></span> <span data-ttu-id="0aa7a-148">输入对象、一个包含这些对象的变量，或可获取这些对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-148">Enter the objects, a variable that contains the objects, or a command or expression that gets the objects.</span></span> <span data-ttu-id="0aa7a-149">还可以通过管道将对象集合传递给 `Get-Random` 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-149">You can also pipe a collection of objects to `Get-Random`.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: RandomListItemParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0aa7a-150">-Maximum</span><span class="sxs-lookup"><span data-stu-id="0aa7a-150">-Maximum</span></span>

<span data-ttu-id="0aa7a-151">指定随机数的最大值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-151">Specifies a maximum value for the random number.</span></span> <span data-ttu-id="0aa7a-152">`Get-Random` 返回小于 (不等于) 的最大值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-152">`Get-Random` returns a value that is less than the maximum (not equal).</span></span> <span data-ttu-id="0aa7a-153">输入一个整数和一个双精度浮点数，或一个可以转换为整数或双精度的对象，如数值字符串 ( "100" ) 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-153">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span>

<span data-ttu-id="0aa7a-154">**Maximum** 值必须大于（不等于） **Minimum** 值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-154">The value of **Maximum** must be greater than (not equal to) the value of **Minimum** .</span></span> <span data-ttu-id="0aa7a-155">如果 **最大** 值或 **最小** 值为浮点数，则 `Get-Random` 返回随机选择的浮点数。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-155">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

<span data-ttu-id="0aa7a-156">在64位计算机上，如果 **最小** 值为32位整数，则 **最大** 值的默认 **值为 int32.maxvalue。**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-156">On a 64-bit computer, if the value of **Minimum** is a 32-bit integer, the default value of **Maximum** is **Int32.MaxValue** .</span></span>

<span data-ttu-id="0aa7a-157">如果 " **最小** 值" 为 double (浮点数) ，则 **最大** 值的默认值为 2 **。**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-157">If the value of **Minimum** is a double (a floating-point number), the default value of **Maximum** is **Double.MaxValue** .</span></span> <span data-ttu-id="0aa7a-158">否则，默认 **值为 int32.maxvalue。**</span><span class="sxs-lookup"><span data-stu-id="0aa7a-158">Otherwise, the default value is **Int32.MaxValue** .</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aa7a-159">-Minimum</span><span class="sxs-lookup"><span data-stu-id="0aa7a-159">-Minimum</span></span>

<span data-ttu-id="0aa7a-160">指定随机数的最小值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-160">Specifies a minimum value for the random number.</span></span> <span data-ttu-id="0aa7a-161">输入一个整数和一个双精度浮点数，或一个可以转换为整数或双精度的对象，如数值字符串 ( "100" ) 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-161">Enter an integer, a double-precision floating-point number, or an object that can be converted to an integer or double, such as a numeric string ("100").</span></span> <span data-ttu-id="0aa7a-162">默认值为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-162">The default value is 0 (zero).</span></span>

<span data-ttu-id="0aa7a-163">**Minimum** 值必须小于（不等于） **Maximum** 值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-163">The value of **Minimum** must be less than (not equal to) the value of **Maximum** .</span></span> <span data-ttu-id="0aa7a-164">如果 **最大** 值或 **最小** 值为浮点数，则 `Get-Random` 返回随机选择的浮点数。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-164">If the value of **Maximum** or **Minimum** is a floating-point number, `Get-Random` returns a randomly selected floating-point number.</span></span>

```yaml
Type: System.Object
Parameter Sets: RandomNumberParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aa7a-165">-SetSeed</span><span class="sxs-lookup"><span data-stu-id="0aa7a-165">-SetSeed</span></span>

<span data-ttu-id="0aa7a-166">为随机数生成程序指定种子值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-166">Specifies a seed value for the random number generator.</span></span> <span data-ttu-id="0aa7a-167">此种子值用于当前命令和当前会话中的所有后续 `Get-Random` 命令，直到再次使用 **SetSeed** 或关闭会话。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-167">This seed value is used for the current command and for all subsequent `Get-Random` commands in the current session until you use **SetSeed** again or close the session.</span></span> <span data-ttu-id="0aa7a-168">不能将种子重置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-168">You can't reset the seed to its default value.</span></span>

<span data-ttu-id="0aa7a-169">**SetSeed** 参数不是必需的。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-169">The **SetSeed** parameter is not required.</span></span> <span data-ttu-id="0aa7a-170">默认情况下， `Get-Random` 使用 [RandomNumberGenerator ( # B1 ](/dotnet/api/system.security.cryptography.randomnumbergenerator) 方法来生成种子值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-170">By default, `Get-Random` uses the [RandomNumberGenerator()](/dotnet/api/system.security.cryptography.randomnumbergenerator) method to generate a seed value.</span></span> <span data-ttu-id="0aa7a-171">因为 **SetSeed** 会导致非随机行为，所以通常仅在尝试重现行为时（例如在调试或分析包含命令的脚本时）使用 `Get-Random` 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-171">Because **SetSeed** results in non-random behavior, it's typically used only when trying to reproduce behavior, such as when debugging or analyzing a script that includes `Get-Random` commands.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0aa7a-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0aa7a-172">CommonParameters</span></span>

<span data-ttu-id="0aa7a-173">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0aa7a-174">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0aa7a-175">输入</span><span class="sxs-lookup"><span data-stu-id="0aa7a-175">INPUTS</span></span>

### <span data-ttu-id="0aa7a-176">System.Object</span><span class="sxs-lookup"><span data-stu-id="0aa7a-176">System.Object</span></span>

<span data-ttu-id="0aa7a-177">可以通过管道发送一个或多个对象。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-177">You can pipe one or more objects.</span></span> <span data-ttu-id="0aa7a-178">`Get-Random` 从管道对象中随机选择值。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-178">`Get-Random` selects values randomly from the piped objects.</span></span>

## <span data-ttu-id="0aa7a-179">输出</span><span class="sxs-lookup"><span data-stu-id="0aa7a-179">OUTPUTS</span></span>

### <span data-ttu-id="0aa7a-180">System.Int32, System.Int64, System.Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-180">System.Int32, System.Int64, System.Double</span></span>

<span data-ttu-id="0aa7a-181">`Get-Random` 返回一个整数或浮点数，或从已提交的集合中随机选择的对象。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-181">`Get-Random` returns an integer or floating-point number, or an object selected randomly from a submitted collection.</span></span>

## <span data-ttu-id="0aa7a-182">注释</span><span class="sxs-lookup"><span data-stu-id="0aa7a-182">NOTES</span></span>

<span data-ttu-id="0aa7a-183">`Get-Random` 在会话启动时，根据系统时间时钟设置每个会话的默认种子。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-183">`Get-Random` sets a default seed for each session based on the system time clock when the session starts.</span></span>

<span data-ttu-id="0aa7a-184">`Get-Random` 并不总是返回与输入值相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-184">`Get-Random` does not alway return the same data type as the input value.</span></span> <span data-ttu-id="0aa7a-185">下表显示了每个数值输入类型的输出类型。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-185">The following table shows the output type for each of the numeric input types.</span></span>

| <span data-ttu-id="0aa7a-186">输入类型</span><span class="sxs-lookup"><span data-stu-id="0aa7a-186">Input Type</span></span> | <span data-ttu-id="0aa7a-187">输出类型</span><span class="sxs-lookup"><span data-stu-id="0aa7a-187">Output Type</span></span> |
| :--------: | :---------: |
|   <span data-ttu-id="0aa7a-188">SByte</span><span class="sxs-lookup"><span data-stu-id="0aa7a-188">SByte</span></span>    |   <span data-ttu-id="0aa7a-189">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-189">Double</span></span>    |
|    <span data-ttu-id="0aa7a-190">Byte</span><span class="sxs-lookup"><span data-stu-id="0aa7a-190">Byte</span></span>    |   <span data-ttu-id="0aa7a-191">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-191">Double</span></span>    |
|   <span data-ttu-id="0aa7a-192">Int16</span><span class="sxs-lookup"><span data-stu-id="0aa7a-192">Int16</span></span>    |   <span data-ttu-id="0aa7a-193">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-193">Double</span></span>    |
|   <span data-ttu-id="0aa7a-194">UInt16</span><span class="sxs-lookup"><span data-stu-id="0aa7a-194">UInt16</span></span>   |   <span data-ttu-id="0aa7a-195">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-195">Double</span></span>    |
|   <span data-ttu-id="0aa7a-196">Int32</span><span class="sxs-lookup"><span data-stu-id="0aa7a-196">Int32</span></span>    |    <span data-ttu-id="0aa7a-197">Int32</span><span class="sxs-lookup"><span data-stu-id="0aa7a-197">Int32</span></span>    |
|   <span data-ttu-id="0aa7a-198">UInt32</span><span class="sxs-lookup"><span data-stu-id="0aa7a-198">UInt32</span></span>   |   <span data-ttu-id="0aa7a-199">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-199">Double</span></span>    |
|   <span data-ttu-id="0aa7a-200">Int64</span><span class="sxs-lookup"><span data-stu-id="0aa7a-200">Int64</span></span>    |    <span data-ttu-id="0aa7a-201">Int64</span><span class="sxs-lookup"><span data-stu-id="0aa7a-201">Int64</span></span>    |
|   <span data-ttu-id="0aa7a-202">UInt64</span><span class="sxs-lookup"><span data-stu-id="0aa7a-202">UInt64</span></span>   |   <span data-ttu-id="0aa7a-203">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-203">Double</span></span>    |
|   <span data-ttu-id="0aa7a-204">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-204">Double</span></span>   |   <span data-ttu-id="0aa7a-205">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-205">Double</span></span>    |
|   <span data-ttu-id="0aa7a-206">Single</span><span class="sxs-lookup"><span data-stu-id="0aa7a-206">Single</span></span>   |   <span data-ttu-id="0aa7a-207">Double</span><span class="sxs-lookup"><span data-stu-id="0aa7a-207">Double</span></span>    |

<span data-ttu-id="0aa7a-208">从 Windows PowerShell 3.0 开始， `Get-Random` 支持64位整数。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-208">Beginning in Windows PowerShell 3.0, `Get-Random` supports 64-bit integers.</span></span> <span data-ttu-id="0aa7a-209">在 Windows PowerShell 2.0 中，所有值都强制转换为 **system.object** 。</span><span class="sxs-lookup"><span data-stu-id="0aa7a-209">In Windows PowerShell 2.0, all values are cast to **System.Int32** .</span></span>

## <span data-ttu-id="0aa7a-210">相关链接</span><span class="sxs-lookup"><span data-stu-id="0aa7a-210">RELATED LINKS</span></span>
