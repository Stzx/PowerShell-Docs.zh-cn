---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Date
ms.openlocfilehash: 4ae3734d0ce41ef2faa7bcf3e07f136b9e9916a2
ms.sourcegitcommit: 077488408c820c860131382324bdd576d0edf52a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "95514953"
---
# <span data-ttu-id="a64f4-103">Get-Date</span><span class="sxs-lookup"><span data-stu-id="a64f4-103">Get-Date</span></span>

## <span data-ttu-id="a64f4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a64f4-104">SYNOPSIS</span></span>
<span data-ttu-id="a64f4-105">获取当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-105">Gets the current date and time.</span></span>

## <span data-ttu-id="a64f4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a64f4-106">SYNTAX</span></span>

### <span data-ttu-id="a64f4-107">net (默认值) </span><span class="sxs-lookup"><span data-stu-id="a64f4-107">net (Default)</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-Format <String>] [<CommonParameters>]
```

### <span data-ttu-id="a64f4-108">UFormat</span><span class="sxs-lookup"><span data-stu-id="a64f4-108">UFormat</span></span>

```
Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>] [-Day <Int32>] [-Hour <Int32>]
 [-Minute <Int32>] [-Second <Int32>] [-Millisecond <Int32>] [-DisplayHint <DisplayHintType>]
 [-UFormat <String>] [<CommonParameters>]
```

## <span data-ttu-id="a64f4-109">说明</span><span class="sxs-lookup"><span data-stu-id="a64f4-109">DESCRIPTION</span></span>

<span data-ttu-id="a64f4-110">该 `Get-Date` cmdlet 将获取表示当前日期或指定日期的 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-110">The `Get-Date` cmdlet gets a **DateTime** object that represents the current date or a date that you specify.</span></span> <span data-ttu-id="a64f4-111">`Get-Date` 可以采用多种 .NET 和 UNIX 格式设置日期和时间的格式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-111">`Get-Date` can format the date and time in several .NET and UNIX formats.</span></span> <span data-ttu-id="a64f4-112">您可以使用 `Get-Date` 生成日期或时间字符串，然后将字符串发送到其他 cmdlet 或程序。</span><span class="sxs-lookup"><span data-stu-id="a64f4-112">You can use `Get-Date` to generate a date or time character string, and then send the string to other cmdlets or programs.</span></span>

<span data-ttu-id="a64f4-113">`Get-Date` 使用计算机的区域性设置来确定输出的格式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-113">`Get-Date` uses the computer's culture settings to determine how the output is formatted.</span></span> <span data-ttu-id="a64f4-114">若要查看计算机的设置，请使用 `(Get-Culture).DateTimeFormat` 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-114">To view your computer's settings, use `(Get-Culture).DateTimeFormat`.</span></span>

## <span data-ttu-id="a64f4-115">示例</span><span class="sxs-lookup"><span data-stu-id="a64f4-115">EXAMPLES</span></span>

### <span data-ttu-id="a64f4-116">示例1：获取当前日期和时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-116">Example 1: Get the current date and time</span></span>

<span data-ttu-id="a64f4-117">在此示例中， `Get-Date` 显示当前的系统日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-117">In this example, `Get-Date` displays the current system date and time.</span></span> <span data-ttu-id="a64f4-118">输出采用长日期和长时间格式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-118">The output is in the long-date and long-time formats.</span></span>

```powershell
Get-Date
```

```Output
Tuesday, June 25, 2019 14:53:32
```

### <span data-ttu-id="a64f4-119">示例2：获取当前日期和时间的元素</span><span class="sxs-lookup"><span data-stu-id="a64f4-119">Example 2: Get elements of the current date and time</span></span>

<span data-ttu-id="a64f4-120">此示例演示如何使用 `Get-Date` 获取日期或时间元素。</span><span class="sxs-lookup"><span data-stu-id="a64f4-120">This example shows how to use `Get-Date` to get either the date or time element.</span></span> <span data-ttu-id="a64f4-121">参数使用参数 **Date**、 **Time** 或 **DateTime**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-121">The parameter uses the arguments **Date**, **Time**, or **DateTime**.</span></span>

```powershell
Get-Date -DisplayHint Date
```

```Output
Tuesday, June 25, 2019
```

<span data-ttu-id="a64f4-122">`Get-Date` 将 **DisplayHint** 参数与 **date** 参数一起使用，以仅获取日期。</span><span class="sxs-lookup"><span data-stu-id="a64f4-122">`Get-Date` uses the **DisplayHint** parameter with the **Date** argument to get only the date.</span></span>

### <span data-ttu-id="a64f4-123">示例3：使用 .NET 格式说明符获取日期和时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-123">Example 3: Get the date and time with a .NET format specifier</span></span>

<span data-ttu-id="a64f4-124">在此示例中，.NET 格式说明符用于自定义输出的格式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-124">In this example, a .NET format specifier is used to customize the output's format.</span></span> <span data-ttu-id="a64f4-125">输出是一个 **字符串** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-125">The output is a **String** object.</span></span>

```powershell
Get-Date -Format "dddd MM/dd/yyyy HH:mm K"
```

```Output
Tuesday 06/25/2019 16:17 -07:00
```

<span data-ttu-id="a64f4-126">`Get-Date` 使用 **format** 参数指定若干格式说明符。</span><span class="sxs-lookup"><span data-stu-id="a64f4-126">`Get-Date` uses the **Format** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="a64f4-127">本示例中使用的 .NET 格式说明符定义如下：</span><span class="sxs-lookup"><span data-stu-id="a64f4-127">The .NET format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="a64f4-128">说明符</span><span class="sxs-lookup"><span data-stu-id="a64f4-128">Specifier</span></span> | <span data-ttu-id="a64f4-129">定义</span><span class="sxs-lookup"><span data-stu-id="a64f4-129">Definition</span></span> |
| --- | --- |
| `dddd` | <span data-ttu-id="a64f4-130">一周中的某一天-全名</span><span class="sxs-lookup"><span data-stu-id="a64f4-130">Day of the week - full name</span></span> |
| `MM` | <span data-ttu-id="a64f4-131">月份</span><span class="sxs-lookup"><span data-stu-id="a64f4-131">Month number</span></span> |
| `dd` | <span data-ttu-id="a64f4-132">每月的第几天-2 位数</span><span class="sxs-lookup"><span data-stu-id="a64f4-132">Day of the month - 2 digits</span></span> |
| `yyyy` | <span data-ttu-id="a64f4-133">年份采用4位格式</span><span class="sxs-lookup"><span data-stu-id="a64f4-133">Year in 4-digit format</span></span> |
| `HH:mm` | <span data-ttu-id="a64f4-134">时间采用24小时格式-无秒</span><span class="sxs-lookup"><span data-stu-id="a64f4-134">Time in 24-hour format -no seconds</span></span> |
| `K` | <span data-ttu-id="a64f4-135">与通用时间坐标 (UTC 的时区偏移量) </span><span class="sxs-lookup"><span data-stu-id="a64f4-135">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="a64f4-136">有关 .NET 格式说明符的详细信息，请参阅 [自定义日期和时间格式字符串](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8)。</span><span class="sxs-lookup"><span data-stu-id="a64f4-136">For more information about .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

### <span data-ttu-id="a64f4-137">示例4：使用 UFormat 说明符获取日期和时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-137">Example 4: Get the date and time with a UFormat specifier</span></span>

<span data-ttu-id="a64f4-138">在此示例中，使用了多个 **UFormat** 格式说明符来自定义输出的格式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-138">In this example, several **UFormat** format specifiers are used to customize the output's format.</span></span>
<span data-ttu-id="a64f4-139">输出是一个 **字符串** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-139">The output is a **String** object.</span></span>

```powershell
Get-Date -UFormat "%A %m/%d/%Y %R %Z"
```

```Output
Tuesday 06/25/2019 16:19 -07
```

<span data-ttu-id="a64f4-140">`Get-Date` 使用 **UFormat** 参数来指定若干格式说明符。</span><span class="sxs-lookup"><span data-stu-id="a64f4-140">`Get-Date` uses the **UFormat** parameter to specify several format specifiers.</span></span>

<span data-ttu-id="a64f4-141">本示例中使用的 **UFormat** 格式说明符定义如下：</span><span class="sxs-lookup"><span data-stu-id="a64f4-141">The **UFormat** format specifiers used in this example are defined as follows:</span></span>

| <span data-ttu-id="a64f4-142">说明符</span><span class="sxs-lookup"><span data-stu-id="a64f4-142">Specifier</span></span> | <span data-ttu-id="a64f4-143">定义</span><span class="sxs-lookup"><span data-stu-id="a64f4-143">Definition</span></span> |
| --- | --- |
| `%A` | <span data-ttu-id="a64f4-144">一周中的某一天-全名</span><span class="sxs-lookup"><span data-stu-id="a64f4-144">Day of the week - full name</span></span> |
| `%m` | <span data-ttu-id="a64f4-145">月份</span><span class="sxs-lookup"><span data-stu-id="a64f4-145">Month number</span></span> |
| `%d` | <span data-ttu-id="a64f4-146">每月的第几天-2 位数</span><span class="sxs-lookup"><span data-stu-id="a64f4-146">Day of the month - 2 digits</span></span> |
| `%Y` | <span data-ttu-id="a64f4-147">年份采用4位格式</span><span class="sxs-lookup"><span data-stu-id="a64f4-147">Year in 4-digit format</span></span> |
| `%R` | <span data-ttu-id="a64f4-148">时间采用24小时格式-无秒</span><span class="sxs-lookup"><span data-stu-id="a64f4-148">Time in 24-hour format -no seconds</span></span> |
| `%Z` | <span data-ttu-id="a64f4-149">与通用时间坐标 (UTC 的时区偏移量) </span><span class="sxs-lookup"><span data-stu-id="a64f4-149">Time zone offset from Universal Time Coordinate (UTC)</span></span> |

<span data-ttu-id="a64f4-150">有关有效 **UFormat** 格式说明符的列表，请参见 [注释](#notes) 部分。</span><span class="sxs-lookup"><span data-stu-id="a64f4-150">For a list of valid **UFormat** format specifiers, see the [Notes](#notes) section.</span></span>

### <span data-ttu-id="a64f4-151">示例5：获取日期是一年中的某一天</span><span class="sxs-lookup"><span data-stu-id="a64f4-151">Example 5: Get a date's day of the year</span></span>

<span data-ttu-id="a64f4-152">在此示例中，使用了一个属性来获取该年份中的数字日期。</span><span class="sxs-lookup"><span data-stu-id="a64f4-152">In this example, a property is used to get the numeric day of the year.</span></span>

<span data-ttu-id="a64f4-153">公历的日期为365天，但闰年为366天。</span><span class="sxs-lookup"><span data-stu-id="a64f4-153">The Gregorian calendar has 365 days, except for leap years that have 366 days.</span></span> <span data-ttu-id="a64f4-154">例如，2020年12月31日为366。</span><span class="sxs-lookup"><span data-stu-id="a64f4-154">For example, December 31, 2020 is day 366.</span></span>

```powershell
(Get-Date -Year 2020 -Month 12 -Day 31).DayOfYear
```

```Output
366
```

<span data-ttu-id="a64f4-155">`Get-Date` 使用三个参数指定日期： **Year**、 **Month** 和 **Day**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-155">`Get-Date` uses three parameters to specify the date: **Year**, **Month**, and **Day**.</span></span> <span data-ttu-id="a64f4-156">命令用括号括起来，以便 **DayofYear** 属性计算结果。</span><span class="sxs-lookup"><span data-stu-id="a64f4-156">The command is wrapped with parentheses so that the result is evaluated by the **DayofYear** property.</span></span>

### <span data-ttu-id="a64f4-157">示例6：检查是否为夏令时调整了日期</span><span class="sxs-lookup"><span data-stu-id="a64f4-157">Example 6: Check if a date is adjusted for daylight savings time</span></span>

<span data-ttu-id="a64f4-158">此示例使用布尔方法来验证日期是否按夏令时进行调整。</span><span class="sxs-lookup"><span data-stu-id="a64f4-158">This example uses a boolean method to verify if a date is adjusted by daylight savings time.</span></span>

```powershell
$DST = Get-Date
$DST.IsDaylightSavingTime()
```

```Output
True
```

<span data-ttu-id="a64f4-159">变量 `$DST` 存储的结果 `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-159">A variable, `$DST` stores the result of `Get-Date`.</span></span> <span data-ttu-id="a64f4-160">`$DST` 使用 **IsDaylightSavingTime** 方法来测试日期是否针对夏令时进行调整。</span><span class="sxs-lookup"><span data-stu-id="a64f4-160">`$DST` uses the **IsDaylightSavingTime** method to test if the date is adjusted for daylight savings time.</span></span>

### <span data-ttu-id="a64f4-161">示例7：将当前时间转换为 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-161">Example 7: Convert the current time to UTC time</span></span>

<span data-ttu-id="a64f4-162">在此示例中，当前时间转换为 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-162">In this example, the current time is converted to UTC time.</span></span> <span data-ttu-id="a64f4-163">系统区域设置的 UTC 偏移量用于转换时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-163">The UTC offset for the system's locale is used to convert the time.</span></span> <span data-ttu-id="a64f4-164">" [注释](#notes) " 部分中的表列出了有效的 **UFormat** 格式说明符。</span><span class="sxs-lookup"><span data-stu-id="a64f4-164">A table in the [Notes](#notes) section lists the valid **UFormat** format specifiers.</span></span>

```powershell
Get-Date -UFormat "%A %B/%d/%Y %T %Z"
$Time = Get-Date
$Time.ToUniversalTime()
```

```Output
Wednesday June/26/2019 10:45:26 -07

Wednesday, June 26, 2019 17:45:26
```

<span data-ttu-id="a64f4-165">`Get-Date` 使用带有格式说明符的 **UFormat** 参数显示当前系统日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-165">`Get-Date` uses the **UFormat** parameter with format specifiers to display the current system date and time.</span></span> <span data-ttu-id="a64f4-166">格式说明符 **% Z** 表示 UTC 偏移量 **07**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-166">The format specifier **%Z** represents the UTC offset of **-07**.</span></span>

<span data-ttu-id="a64f4-167">`$Time`变量存储当前的系统日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-167">The `$Time` variable stores the current system date and time.</span></span> <span data-ttu-id="a64f4-168">`$Time` 使用 **ToUniversalTime ( # B1** 方法，根据计算机的 UTC 偏移量转换时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-168">`$Time` uses the **ToUniversalTime()** method to convert the time based on the computer's UTC offset.</span></span>

### <span data-ttu-id="a64f4-169">示例8：创建时间戳</span><span class="sxs-lookup"><span data-stu-id="a64f4-169">Example 8: Create a timestamp</span></span>

<span data-ttu-id="a64f4-170">在此示例中，格式说明符为目录名称创建时间戳 **字符串** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-170">In this example, a format specifier creates a timestamp **String** object for a directory name.</span></span> <span data-ttu-id="a64f4-171">时间戳包含日期、时间和 UTC 的偏移量。</span><span class="sxs-lookup"><span data-stu-id="a64f4-171">The timestamp includes the date, time, and UTC offset.</span></span>

```powershell
$timestamp = Get-Date -Format o | ForEach-Object { $_ -replace ":", "." }
New-Item -Path C:\Test\$timestamp -Type Directory
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         6/27/2019    07:59                2019-06-27T07.59.24.4603750-07.00
```

<span data-ttu-id="a64f4-172">`$timestamp`变量存储命令的结果 `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-172">The `$timestamp` variable stores the results of a `Get-Date` command.</span></span> <span data-ttu-id="a64f4-173">`Get-Date` 使用带有小写格式说明符的 **format** 参数 `o` 创建时间戳 **字符串** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-173">`Get-Date` uses the **Format** parameter with the format specifier of lowercase `o` to create a timestamp **String** object.</span></span> <span data-ttu-id="a64f4-174">将对象向下发送到 `ForEach-Object` 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-174">The object is sent down the pipeline to `ForEach-Object`.</span></span> <span data-ttu-id="a64f4-175">**ScriptBlock** 包含 `$_` 表示当前管道对象的变量。</span><span class="sxs-lookup"><span data-stu-id="a64f4-175">A **ScriptBlock** contains the `$_` variable that represents the current pipeline object.</span></span> <span data-ttu-id="a64f4-176">时间戳字符串由用句点替换的冒号分隔。</span><span class="sxs-lookup"><span data-stu-id="a64f4-176">The timestamp string is delimited by colons that are replaced by periods.</span></span>

<span data-ttu-id="a64f4-177">`New-Item` 使用 **Path** 参数指定新目录的位置。</span><span class="sxs-lookup"><span data-stu-id="a64f4-177">`New-Item` uses the **Path** parameter to specify the location for a new directory.</span></span> <span data-ttu-id="a64f4-178">路径包含 `$timestamp` 变量作为目录名称。</span><span class="sxs-lookup"><span data-stu-id="a64f4-178">The path includes the `$timestamp` variable as the directory name.</span></span> <span data-ttu-id="a64f4-179">**类型** 参数指定创建目录。</span><span class="sxs-lookup"><span data-stu-id="a64f4-179">The **Type** parameter specifies that a directory is created.</span></span>

## <span data-ttu-id="a64f4-180">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a64f4-180">PARAMETERS</span></span>

### <span data-ttu-id="a64f4-181">-Date</span><span class="sxs-lookup"><span data-stu-id="a64f4-181">-Date</span></span>

<span data-ttu-id="a64f4-182">指定日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-182">Specifies a date and time.</span></span> <span data-ttu-id="a64f4-183">时间是可选的，如果未指定，则返回00:00:00。</span><span class="sxs-lookup"><span data-stu-id="a64f4-183">Time is optional and if not specified, returns 00:00:00.</span></span>

<span data-ttu-id="a64f4-184">输入日期和时间，格式为标准的系统区域设置。</span><span class="sxs-lookup"><span data-stu-id="a64f4-184">Enter the date and time in a format that is standard for the system locale.</span></span>

<span data-ttu-id="a64f4-185">例如，在美国英语中：</span><span class="sxs-lookup"><span data-stu-id="a64f4-185">For example, in US English:</span></span>

<span data-ttu-id="a64f4-186">`Get-Date -Date "6/25/2019 12:30:22"` 返回 2019 12:30:22 的星期二6月25日</span><span class="sxs-lookup"><span data-stu-id="a64f4-186">`Get-Date -Date "6/25/2019 12:30:22"` returns Tuesday, June 25, 2019 12:30:22</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases: LastWriteTime

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-187">-日</span><span class="sxs-lookup"><span data-stu-id="a64f4-187">-Day</span></span>

<span data-ttu-id="a64f4-188">指定显示月份中的某一天。</span><span class="sxs-lookup"><span data-stu-id="a64f4-188">Specifies the day of the month that is displayed.</span></span> <span data-ttu-id="a64f4-189">输入一个介于 1 到 31 之间的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-189">Enter a value from 1 to 31.</span></span>

<span data-ttu-id="a64f4-190">如果指定的值大于每月的天数，则 PowerShell 会将天数添加到月份。</span><span class="sxs-lookup"><span data-stu-id="a64f4-190">If the specified value is greater than the number of days in a month, PowerShell adds the number of days to the month.</span></span> <span data-ttu-id="a64f4-191">例如， `Get-Date -Month 2 -Day 31` 显示 3 **月 3** 日，而不是 **2 月31日**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-191">For example, `Get-Date -Month 2 -Day 31` displays **March 3**, not **February 31**.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-192">-DisplayHint</span><span class="sxs-lookup"><span data-stu-id="a64f4-192">-DisplayHint</span></span>

<span data-ttu-id="a64f4-193">确定要显示日期和时间的哪些元素。</span><span class="sxs-lookup"><span data-stu-id="a64f4-193">Determines which elements of the date and time are displayed.</span></span>

<span data-ttu-id="a64f4-194">接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="a64f4-194">The accepted values are as follows:</span></span>

- <span data-ttu-id="a64f4-195">**Date**：仅显示日期</span><span class="sxs-lookup"><span data-stu-id="a64f4-195">**Date**: displays only the date</span></span>
- <span data-ttu-id="a64f4-196">**Time**：仅显示时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-196">**Time**: displays only the time</span></span>
- <span data-ttu-id="a64f4-197">**DateTime**：显示日期和时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-197">**DateTime**: displays the date and time</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.DisplayHintType
Parameter Sets: (All)
Aliases:
Accepted values: Date, Time, DateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-198">-Format</span><span class="sxs-lookup"><span data-stu-id="a64f4-198">-Format</span></span>

<span data-ttu-id="a64f4-199">采用格式说明符指示的 Microsoft .NET Framework 格式显示日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-199">Displays the date and time in the Microsoft .NET Framework format indicated by the format specifier.</span></span>
<span data-ttu-id="a64f4-200">**Format** 参数输出 **String** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-200">The **Format** parameter outputs a **String** object.</span></span>

<span data-ttu-id="a64f4-201">有关可用的 .NET 格式说明符的列表，请参阅 [自定义日期和时间格式字符串](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8)。</span><span class="sxs-lookup"><span data-stu-id="a64f4-201">For a list of available .NET format specifiers, see [Custom date and time format strings](/dotnet/standard/base-types/custom-date-and-time-format-strings?view=netframework-4.8).</span></span>

<span data-ttu-id="a64f4-202">使用 **Format** 参数时， `Get-Date` 仅获取显示日期所需的 **DateTime** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="a64f4-202">When the **Format** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="a64f4-203">因此，**DateTime** 对象的某些属性和方法可能不可用。</span><span class="sxs-lookup"><span data-stu-id="a64f4-203">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

<span data-ttu-id="a64f4-204">从 PowerShell 5.0 开始，可以使用以下附加格式作为 **Format** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-204">Starting in PowerShell 5.0, you can use the following additional formats as values for the **Format** parameter.</span></span>

- <span data-ttu-id="a64f4-205">**FileDate**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-205">**FileDate**.</span></span> <span data-ttu-id="a64f4-206">以本地时间表示的当前日期的文件或路径友好表示形式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-206">A file or path-friendly representation of the current date in local time.</span></span> <span data-ttu-id="a64f4-207">格式 `yyyyMMdd` (区分大小写，使用四位数年份、2位数月和两位数表示的日期) 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-207">The format is `yyyyMMdd` (case-sensitive, using a 4-digit year, 2-digit month, and 2-digit day).</span></span> <span data-ttu-id="a64f4-208">例如：</span><span class="sxs-lookup"><span data-stu-id="a64f4-208">For example:</span></span>
  20190627.

- <span data-ttu-id="a64f4-209">**FileDateUniversal**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-209">**FileDateUniversal**.</span></span> <span data-ttu-id="a64f4-210">在通用时间 (UTC) 的当前日期的文件或路径友好表示形式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-210">A file or path-friendly representation of the current date in universal time (UTC).</span></span> <span data-ttu-id="a64f4-211">格式 `yyyyMMddZ` (区分大小写，使用四位数的年份、2位数的月份、2位数的日期和字母 `Z` 作为 UTC 指示器) 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-211">The format is `yyyyMMddZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="a64f4-212">例如：20190627Z。</span><span class="sxs-lookup"><span data-stu-id="a64f4-212">For example: 20190627Z.</span></span>

- <span data-ttu-id="a64f4-213">**FileDateTime**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-213">**FileDateTime**.</span></span> <span data-ttu-id="a64f4-214">以24小时格式表示的当前日期和时间的文件或路径友好表示形式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-214">A file or path-friendly representation of the current date and time in local time, in 24-hour format.</span></span> <span data-ttu-id="a64f4-215">格式 `yyyyMMddTHHmmssffff` (区分大小写，使用四位数的年份、2位数的月份、2位数的日期、字母作为时间分隔符、2位数小时、2位数字 `T` 分钟、2位数秒和4位数毫秒) 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-215">The format is `yyyyMMddTHHmmssffff` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, and 4-digit millisecond).</span></span> <span data-ttu-id="a64f4-216">例如：20190627T0840107271。</span><span class="sxs-lookup"><span data-stu-id="a64f4-216">For example: 20190627T0840107271.</span></span>

- <span data-ttu-id="a64f4-217">**FileDateTimeUniversal**。</span><span class="sxs-lookup"><span data-stu-id="a64f4-217">**FileDateTimeUniversal**.</span></span> <span data-ttu-id="a64f4-218">以24小时格式 (UTC) 的当前日期和时间的文件或路径友好表示形式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-218">A file or path-friendly representation of the current date and time in universal time (UTC), in 24-hour format.</span></span> <span data-ttu-id="a64f4-219">格式 `yyyyMMddTHHmmssffffZ` (区分大小写，使用四位数的年份、2位数的月份、2位数的日期、字母 `T` 作为时间分隔符、2位数的小时、2位数字的分钟、2位秒、4位数的毫秒以及与 `Z` UTC 指示器) 的字母。</span><span class="sxs-lookup"><span data-stu-id="a64f4-219">The format is `yyyyMMddTHHmmssffffZ` (case-sensitive, using a 4-digit year, 2-digit month, 2-digit day, the letter `T` as a time separator, 2-digit hour, 2-digit minute, 2-digit second, 4-digit millisecond, and the letter `Z` as the UTC indicator).</span></span> <span data-ttu-id="a64f4-220">例如：20190627T1540500718Z。</span><span class="sxs-lookup"><span data-stu-id="a64f4-220">For example: 20190627T1540500718Z.</span></span>

```yaml
Type: System.String
Parameter Sets: net
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-221">-小时</span><span class="sxs-lookup"><span data-stu-id="a64f4-221">-Hour</span></span>

<span data-ttu-id="a64f4-222">指定要显示的小时。</span><span class="sxs-lookup"><span data-stu-id="a64f4-222">Specifies the hour that is displayed.</span></span> <span data-ttu-id="a64f4-223">输入一个介于0到23之间的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-223">Enter a value from 0 to 23.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-224">-毫秒</span><span class="sxs-lookup"><span data-stu-id="a64f4-224">-Millisecond</span></span>

<span data-ttu-id="a64f4-225">指定日期中的毫秒。</span><span class="sxs-lookup"><span data-stu-id="a64f4-225">Specifies the milliseconds in the date.</span></span> <span data-ttu-id="a64f4-226">输入一个介于0到999之间的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-226">Enter a value from 0 to 999.</span></span>

<span data-ttu-id="a64f4-227">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a64f4-227">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-228">-分钟</span><span class="sxs-lookup"><span data-stu-id="a64f4-228">-Minute</span></span>

<span data-ttu-id="a64f4-229">指定要显示的分钟。</span><span class="sxs-lookup"><span data-stu-id="a64f4-229">Specifies the minute that is displayed.</span></span> <span data-ttu-id="a64f4-230">输入一个介于0到59之间的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-230">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-231">-月</span><span class="sxs-lookup"><span data-stu-id="a64f4-231">-Month</span></span>

<span data-ttu-id="a64f4-232">指定要显示的月份。</span><span class="sxs-lookup"><span data-stu-id="a64f4-232">Specifies the month that is displayed.</span></span> <span data-ttu-id="a64f4-233">输入一个介于1和12之间的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-233">Enter a value from 1 to 12.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-234">-秒</span><span class="sxs-lookup"><span data-stu-id="a64f4-234">-Second</span></span>

<span data-ttu-id="a64f4-235">指定要显示的秒。</span><span class="sxs-lookup"><span data-stu-id="a64f4-235">Specifies the second that is displayed.</span></span> <span data-ttu-id="a64f4-236">输入一个介于0到59之间的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-236">Enter a value from 0 to 59.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-237">-UFormat</span><span class="sxs-lookup"><span data-stu-id="a64f4-237">-UFormat</span></span>

<span data-ttu-id="a64f4-238">采用 UNIX 格式显示日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a64f4-238">Displays the date and time in UNIX format.</span></span> <span data-ttu-id="a64f4-239">**UFormat** 参数输出 string 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-239">The **UFormat** parameter outputs a string object.</span></span>

<span data-ttu-id="a64f4-240">**UFormat** 说明符前面有一个百分号 (`%`) ，例如，、 `%m` `%d` 和 `%Y` 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-240">**UFormat** specifiers are preceded by a percent sign (`%`), for example, `%m`, `%d`, and `%Y`.</span></span> <span data-ttu-id="a64f4-241">" [注释](#notes) " 部分包含有效 **UFormat 说明符** 的表。</span><span class="sxs-lookup"><span data-stu-id="a64f4-241">The [Notes](#notes) section contains a table of valid **UFormat specifiers**.</span></span>

<span data-ttu-id="a64f4-242">使用 **UFormat** 参数时， `Get-Date` 仅获取显示日期所需的 **DateTime** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="a64f4-242">When the **UFormat** parameter is used, `Get-Date` only gets the **DateTime** object's properties necessary to display the date.</span></span> <span data-ttu-id="a64f4-243">因此，**DateTime** 对象的某些属性和方法可能不可用。</span><span class="sxs-lookup"><span data-stu-id="a64f4-243">As a result, some of the properties and methods of **DateTime** objects might not be available.</span></span>

```yaml
Type: System.String
Parameter Sets: UFormat
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-244">-Year</span><span class="sxs-lookup"><span data-stu-id="a64f4-244">-Year</span></span>

<span data-ttu-id="a64f4-245">指定要显示的年份。</span><span class="sxs-lookup"><span data-stu-id="a64f4-245">Specifies the year that is displayed.</span></span> <span data-ttu-id="a64f4-246">输入一个介于1到9999之间的值。</span><span class="sxs-lookup"><span data-stu-id="a64f4-246">Enter a value from 1 to 9999.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a64f4-247">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a64f4-247">CommonParameters</span></span>

<span data-ttu-id="a64f4-248">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a64f4-248">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a64f4-249">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a64f4-249">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a64f4-250">输入</span><span class="sxs-lookup"><span data-stu-id="a64f4-250">INPUTS</span></span>

### <span data-ttu-id="a64f4-251">管道输入</span><span class="sxs-lookup"><span data-stu-id="a64f4-251">Pipeline input</span></span>

<span data-ttu-id="a64f4-252">`Get-Date` 接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="a64f4-252">`Get-Date` accepts pipeline input.</span></span> <span data-ttu-id="a64f4-253">例如 `Get-ChildItem | Get-Date`。</span><span class="sxs-lookup"><span data-stu-id="a64f4-253">For example, `Get-ChildItem | Get-Date`.</span></span>

## <span data-ttu-id="a64f4-254">输出</span><span class="sxs-lookup"><span data-stu-id="a64f4-254">OUTPUTS</span></span>

### <span data-ttu-id="a64f4-255">System.object 或 System.string</span><span class="sxs-lookup"><span data-stu-id="a64f4-255">System.DateTime or System.String</span></span>

<span data-ttu-id="a64f4-256">`Get-Date` 返回 **DateTime** 对象，但使用 **Format** 和 **UFormat** 参数。</span><span class="sxs-lookup"><span data-stu-id="a64f4-256">`Get-Date` returns a **DateTime** object except when the **Format** and **UFormat** parameters are used.</span></span> <span data-ttu-id="a64f4-257">**Format** 或 **UFormat** 参数返回 **String** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-257">The **Format** or **UFormat** parameters return **String** objects.</span></span>

<span data-ttu-id="a64f4-258">如果将 **DateTime** 对象向下发送到 `Add-Content` 需要字符串输入的 cmdlet （如），则 PowerShell 会将对象转换为 **字符串** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-258">When a **DateTime** object is sent down the pipeline to a cmdlet such as `Add-Content` that expects string input, PowerShell converts the object to a **String** object.</span></span>

<span data-ttu-id="a64f4-259">方法 `(Get-Date).ToString()` 将 **DateTime** 对象转换为 **String** 对象。</span><span class="sxs-lookup"><span data-stu-id="a64f4-259">The method `(Get-Date).ToString()` converts a **DateTime** object a **String** object.</span></span>

<span data-ttu-id="a64f4-260">若要显示对象的属性和方法，请将对象向下发送到 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="a64f4-260">To display an object's properties and methods, send the object down the pipeline to `Get-Member`.</span></span>
<span data-ttu-id="a64f4-261">例如 `Get-Date | Get-Member`。</span><span class="sxs-lookup"><span data-stu-id="a64f4-261">For example, `Get-Date | Get-Member`.</span></span>

## <span data-ttu-id="a64f4-262">注释</span><span class="sxs-lookup"><span data-stu-id="a64f4-262">NOTES</span></span>

<span data-ttu-id="a64f4-263">**DateTime** 对象采用系统区域设置的长日期和长时间格式。</span><span class="sxs-lookup"><span data-stu-id="a64f4-263">**DateTime** objects are in long-date and long-time formats for the system locale.</span></span>

<span data-ttu-id="a64f4-264">下表显示了有效的 **UFormat 说明符** ：</span><span class="sxs-lookup"><span data-stu-id="a64f4-264">The valid **UFormat specifiers** are displayed in the following table:</span></span>

| <span data-ttu-id="a64f4-265">格式说明符</span><span class="sxs-lookup"><span data-stu-id="a64f4-265">Format specifier</span></span> |                                 <span data-ttu-id="a64f4-266">含义</span><span class="sxs-lookup"><span data-stu-id="a64f4-266">Meaning</span></span>                     |         <span data-ttu-id="a64f4-267">示例</span><span class="sxs-lookup"><span data-stu-id="a64f4-267">Example</span></span>          |
| ---- | ----------------------------------------------------------------------- | ------------------------ |
| `%A` | <span data-ttu-id="a64f4-268">一周中的某一天-全名</span><span class="sxs-lookup"><span data-stu-id="a64f4-268">Day of the week - full name</span></span>                                             | <span data-ttu-id="a64f4-269">星期一</span><span class="sxs-lookup"><span data-stu-id="a64f4-269">Monday</span></span>                   |
| `%a` | <span data-ttu-id="a64f4-270">星期几-缩写名称</span><span class="sxs-lookup"><span data-stu-id="a64f4-270">Day of the week - abbreviated name</span></span>                                      | <span data-ttu-id="a64f4-271">Mon</span><span class="sxs-lookup"><span data-stu-id="a64f4-271">Mon</span></span>                      |
| `%B` | <span data-ttu-id="a64f4-272">月份名称-完整</span><span class="sxs-lookup"><span data-stu-id="a64f4-272">Month name - full</span></span>                                                       | <span data-ttu-id="a64f4-273">1 月</span><span class="sxs-lookup"><span data-stu-id="a64f4-273">January</span></span>                  |
| `%b` | <span data-ttu-id="a64f4-274">月份名称-缩写</span><span class="sxs-lookup"><span data-stu-id="a64f4-274">Month name - abbreviated</span></span>                                                | <span data-ttu-id="a64f4-275">一月</span><span class="sxs-lookup"><span data-stu-id="a64f4-275">Jan</span></span>                      |
| `%C` | <span data-ttu-id="a64f4-276">纪元</span><span class="sxs-lookup"><span data-stu-id="a64f4-276">Century</span></span>                                                                 | <span data-ttu-id="a64f4-277">20 2019</span><span class="sxs-lookup"><span data-stu-id="a64f4-277">20 for 2019</span></span>              |
| `%c` | <span data-ttu-id="a64f4-278">日期和时间-缩写</span><span class="sxs-lookup"><span data-stu-id="a64f4-278">Date and time - abbreviated</span></span>                                             | <span data-ttu-id="a64f4-279">Thu 27 08:44:18 2019 年6月</span><span class="sxs-lookup"><span data-stu-id="a64f4-279">Thu Jun 27 08:44:18 2019</span></span> |
| `%D` | <span data-ttu-id="a64f4-280">日期采用 mm/dd/yy 格式</span><span class="sxs-lookup"><span data-stu-id="a64f4-280">Date in mm/dd/yy format</span></span>                                                 | <span data-ttu-id="a64f4-281">06/27/19</span><span class="sxs-lookup"><span data-stu-id="a64f4-281">06/27/19</span></span>                 |
| `%d` | <span data-ttu-id="a64f4-282">每月的第几天-2 位数</span><span class="sxs-lookup"><span data-stu-id="a64f4-282">Day of the month - 2 digits</span></span>                                             | <span data-ttu-id="a64f4-283">05</span><span class="sxs-lookup"><span data-stu-id="a64f4-283">05</span></span>                       |
| `%e` | <span data-ttu-id="a64f4-284">月份中的第几天，如果只有单个数字，则以空格开头</span><span class="sxs-lookup"><span data-stu-id="a64f4-284">Day of the month - preceded by a space if only a single digit</span></span>           | <span data-ttu-id="a64f4-285">\<space\>5</span><span class="sxs-lookup"><span data-stu-id="a64f4-285">\<space\>5</span></span>               |
| `%F` | <span data-ttu-id="a64f4-286">采用 YYYY-MM-DD 格式的日期，等于% Y-% m-% d (ISO 8601 日期格式) </span><span class="sxs-lookup"><span data-stu-id="a64f4-286">Date in YYYY-mm-dd format, equal to %Y-%m-%d (the ISO 8601 date format)</span></span> | <span data-ttu-id="a64f4-287">2019-06-27</span><span class="sxs-lookup"><span data-stu-id="a64f4-287">2019-06-27</span></span>               |
| `%G` | <span data-ttu-id="a64f4-288">与 "Y" 相同</span><span class="sxs-lookup"><span data-stu-id="a64f4-288">Same as 'Y'</span></span>                                                             |                          |
| `%g` | <span data-ttu-id="a64f4-289">与 "y" 相同</span><span class="sxs-lookup"><span data-stu-id="a64f4-289">Same as 'y'</span></span>                                                             |                          |
| `%H` | <span data-ttu-id="a64f4-290">24小时制格式的小时</span><span class="sxs-lookup"><span data-stu-id="a64f4-290">Hour in 24-hour format</span></span>                                                  | <span data-ttu-id="a64f4-291">17</span><span class="sxs-lookup"><span data-stu-id="a64f4-291">17</span></span>                       |
| `%h` | <span data-ttu-id="a64f4-292">与 "b" 相同</span><span class="sxs-lookup"><span data-stu-id="a64f4-292">Same as 'b'</span></span>                                                             |                          |
| `%I` | <span data-ttu-id="a64f4-293">12小时制格式</span><span class="sxs-lookup"><span data-stu-id="a64f4-293">Hour in 12-hour format</span></span>                                                  | <span data-ttu-id="a64f4-294">05</span><span class="sxs-lookup"><span data-stu-id="a64f4-294">05</span></span>                       |
| `%j` | <span data-ttu-id="a64f4-295">一年中的第几天</span><span class="sxs-lookup"><span data-stu-id="a64f4-295">Day of the year</span></span>                                                         | <span data-ttu-id="a64f4-296">1-366</span><span class="sxs-lookup"><span data-stu-id="a64f4-296">1-366</span></span>                    |
| `%k` | <span data-ttu-id="a64f4-297">与 "H" 相同</span><span class="sxs-lookup"><span data-stu-id="a64f4-297">Same as 'H'</span></span>                                                             |                          |
| `%l` | <span data-ttu-id="a64f4-298">与 (大写的 "I" 相同) </span><span class="sxs-lookup"><span data-stu-id="a64f4-298">Same as 'I' (Upper-case I)</span></span>                                              | <span data-ttu-id="a64f4-299">05</span><span class="sxs-lookup"><span data-stu-id="a64f4-299">05</span></span>                       |
| `%M` | <span data-ttu-id="a64f4-300">分钟数</span><span class="sxs-lookup"><span data-stu-id="a64f4-300">Minutes</span></span>                                                                 | <span data-ttu-id="a64f4-301">35</span><span class="sxs-lookup"><span data-stu-id="a64f4-301">35</span></span>                       |
| `%m` | <span data-ttu-id="a64f4-302">月份</span><span class="sxs-lookup"><span data-stu-id="a64f4-302">Month number</span></span>                                                            | <span data-ttu-id="a64f4-303">06</span><span class="sxs-lookup"><span data-stu-id="a64f4-303">06</span></span>                       |
| `%n` | <span data-ttu-id="a64f4-304">换行符</span><span class="sxs-lookup"><span data-stu-id="a64f4-304">newline character</span></span>                                                       |                          |
| `%p` | <span data-ttu-id="a64f4-305">AM 或 PM</span><span class="sxs-lookup"><span data-stu-id="a64f4-305">AM or PM</span></span>                                                                |                          |
| `%R` | <span data-ttu-id="a64f4-306">时间采用24小时格式-无秒</span><span class="sxs-lookup"><span data-stu-id="a64f4-306">Time in 24-hour format -no seconds</span></span>                                      | <span data-ttu-id="a64f4-307">17:45</span><span class="sxs-lookup"><span data-stu-id="a64f4-307">17:45</span></span>                    |
| `%r` | <span data-ttu-id="a64f4-308">采用12小时格式的时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-308">Time in 12-hour format</span></span>                                                  | <span data-ttu-id="a64f4-309">上午09:15:36</span><span class="sxs-lookup"><span data-stu-id="a64f4-309">09:15:36 AM</span></span>              |
| `%S` | <span data-ttu-id="a64f4-310">秒</span><span class="sxs-lookup"><span data-stu-id="a64f4-310">Seconds</span></span>                                                                 | <span data-ttu-id="a64f4-311">05</span><span class="sxs-lookup"><span data-stu-id="a64f4-311">05</span></span>                       |
| `%s` | <span data-ttu-id="a64f4-312">自 00:00:00 1970 年1月1日起经过的秒数</span><span class="sxs-lookup"><span data-stu-id="a64f4-312">Seconds elapsed since January 1, 1970 00:00:00</span></span>                          | <span data-ttu-id="a64f4-313">1150451174</span><span class="sxs-lookup"><span data-stu-id="a64f4-313">1150451174</span></span>               |
| `%t` | <span data-ttu-id="a64f4-314">水平制表符</span><span class="sxs-lookup"><span data-stu-id="a64f4-314">Horizontal tab character</span></span>                                                |                          |
| `%T` | <span data-ttu-id="a64f4-315">24 小时格式的时间</span><span class="sxs-lookup"><span data-stu-id="a64f4-315">Time in 24-hour format</span></span>                                                  | <span data-ttu-id="a64f4-316">17:45:52</span><span class="sxs-lookup"><span data-stu-id="a64f4-316">17:45:52</span></span>                 |
| `%U` | <span data-ttu-id="a64f4-317">与 "W" 相同</span><span class="sxs-lookup"><span data-stu-id="a64f4-317">Same as 'W'</span></span>                                                             |                          |
| `%u` | <span data-ttu-id="a64f4-318">周日期-数字</span><span class="sxs-lookup"><span data-stu-id="a64f4-318">Day of the week - number</span></span>                                                | <span data-ttu-id="a64f4-319">星期日 = 0</span><span class="sxs-lookup"><span data-stu-id="a64f4-319">Sunday = 0</span></span>               |
| `%V` | <span data-ttu-id="a64f4-320">一年中的某一周</span><span class="sxs-lookup"><span data-stu-id="a64f4-320">Week of the year</span></span>                                                        | <span data-ttu-id="a64f4-321">01-53</span><span class="sxs-lookup"><span data-stu-id="a64f4-321">01-53</span></span>                    |
| `%w` | <span data-ttu-id="a64f4-322">与 "u" 相同</span><span class="sxs-lookup"><span data-stu-id="a64f4-322">Same as 'u'</span></span>                                                             |                          |
| `%W` | <span data-ttu-id="a64f4-323">一年中的某一周</span><span class="sxs-lookup"><span data-stu-id="a64f4-323">Week of the year</span></span>                                                        | <span data-ttu-id="a64f4-324">00-52</span><span class="sxs-lookup"><span data-stu-id="a64f4-324">00-52</span></span>                    |
| `%X` | <span data-ttu-id="a64f4-325">与 "t" 相同</span><span class="sxs-lookup"><span data-stu-id="a64f4-325">Same as 'T'</span></span>                                                             |                          |
| `%x` | <span data-ttu-id="a64f4-326">区域设置的标准格式日期</span><span class="sxs-lookup"><span data-stu-id="a64f4-326">Date in standard format for locale</span></span>                                      | <span data-ttu-id="a64f4-327">美国英语06/27/19</span><span class="sxs-lookup"><span data-stu-id="a64f4-327">06/27/19 for English-US</span></span>  |
| `%Y` | <span data-ttu-id="a64f4-328">年份采用4位格式</span><span class="sxs-lookup"><span data-stu-id="a64f4-328">Year in 4-digit format</span></span>                                                  | <span data-ttu-id="a64f4-329">2019</span><span class="sxs-lookup"><span data-stu-id="a64f4-329">2019</span></span>                     |
| `%y` | <span data-ttu-id="a64f4-330">年份（2位数字格式）</span><span class="sxs-lookup"><span data-stu-id="a64f4-330">Year in 2-digit format</span></span>                                                  | <span data-ttu-id="a64f4-331">19</span><span class="sxs-lookup"><span data-stu-id="a64f4-331">19</span></span>                       |
| `%Z` | <span data-ttu-id="a64f4-332">与通用时间坐标 (UTC 的时区偏移量) </span><span class="sxs-lookup"><span data-stu-id="a64f4-332">Time zone offset from Universal Time Coordinate (UTC)</span></span>                   | <span data-ttu-id="a64f4-333">-07</span><span class="sxs-lookup"><span data-stu-id="a64f4-333">-07</span></span>                      |

## <span data-ttu-id="a64f4-334">相关链接</span><span class="sxs-lookup"><span data-stu-id="a64f4-334">RELATED LINKS</span></span>

[<span data-ttu-id="a64f4-335">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="a64f4-335">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="a64f4-336">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="a64f4-336">Get-Culture</span></span>](Get-Culture.md)

[<span data-ttu-id="a64f4-337">Get-Member</span><span class="sxs-lookup"><span data-stu-id="a64f4-337">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="a64f4-338">New-Item</span><span class="sxs-lookup"><span data-stu-id="a64f4-338">New-Item</span></span>](../Microsoft.PowerShell.Management/New-Item.md)

[<span data-ttu-id="a64f4-339">New-TimeSpan</span><span class="sxs-lookup"><span data-stu-id="a64f4-339">New-TimeSpan</span></span>](New-TimeSpan.md)

[<span data-ttu-id="a64f4-340">Set-Date</span><span class="sxs-lookup"><span data-stu-id="a64f4-340">Set-Date</span></span>](Set-Date.md)
