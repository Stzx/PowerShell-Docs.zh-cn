---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/group-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Group-Object
ms.openlocfilehash: f430dd1f9d9f820dda88ba5ad40023650204604d
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "93199279"
---
# <span data-ttu-id="76ab8-103">Group-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-103">Group-Object</span></span>

## <span data-ttu-id="76ab8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="76ab8-104">SYNOPSIS</span></span>
<span data-ttu-id="76ab8-105">包含相同指定属性的值的组对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-105">Groups objects that contain the same value for specified properties.</span></span>

## <span data-ttu-id="76ab8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="76ab8-106">SYNTAX</span></span>

### <span data-ttu-id="76ab8-107">散</span><span class="sxs-lookup"><span data-stu-id="76ab8-107">HashTable</span></span>

```
Group-Object [-NoElement] [-AsHashTable] [-AsString] [-InputObject <PSObject>]
 [[-Property] <Object[]>] [-Culture <String>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="76ab8-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="76ab8-108">DESCRIPTION</span></span>

<span data-ttu-id="76ab8-109">该 `Group-Object` cmdlet 根据指定属性的值在组中显示对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-109">The `Group-Object` cmdlet displays objects in groups based on the value of a specified property.</span></span>
<span data-ttu-id="76ab8-110">`Group-Object` 返回一个表，其中每个属性值对应一行，列显示具有该值的项的数目。</span><span class="sxs-lookup"><span data-stu-id="76ab8-110">`Group-Object` returns a table with one row for each property value and a column that displays the number of items with that value.</span></span>

<span data-ttu-id="76ab8-111">如果指定多个属性，则 `Group-Object` 先按第一个属性的值对它们进行分组，然后在每个属性组内按下一个属性的值进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-111">If you specify more than one property, `Group-Object` first groups them by the values of the first property, and then, within each property group, it groups by the value of the next property.</span></span>

## <span data-ttu-id="76ab8-112">示例</span><span class="sxs-lookup"><span data-stu-id="76ab8-112">EXAMPLES</span></span>

### <span data-ttu-id="76ab8-113">示例1：按扩展名对文件进行分组</span><span class="sxs-lookup"><span data-stu-id="76ab8-113">Example 1: Group files by extension</span></span>

<span data-ttu-id="76ab8-114">此示例以递归方式获取下的文件 `$PSHOME` ，并按文件扩展名对其进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-114">This example recursively gets the files under `$PSHOME` and groups them by file name extension.</span></span> <span data-ttu-id="76ab8-115">输出将发送到 `Sort-Object` cmdlet，该 cmdlet 会按给定扩展的计数文件进行排序。</span><span class="sxs-lookup"><span data-stu-id="76ab8-115">The output is sent to the `Sort-Object` cmdlet, which sorts them by the count files found for the given extension.</span></span> <span data-ttu-id="76ab8-116">空 **名称** 表示目录。</span><span class="sxs-lookup"><span data-stu-id="76ab8-116">The empty **Name** represents directories.</span></span>

<span data-ttu-id="76ab8-117">此示例使用 **NoElement** 参数来省略该组的成员。</span><span class="sxs-lookup"><span data-stu-id="76ab8-117">This example uses the **NoElement** parameter to omit the members of the group.</span></span>

```powershell
$files = Get-ChildItem -Path $PSHOME -Recurse
$files | Group-Object -Property extension -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count Name
----- ----
  365 .xml
  231 .cdxml
  197
  169 .ps1xml
  142 .txt
  114 .psd1
   63 .psm1
   49 .xsd
   36 .dll
   15 .mfl
   15 .mof
...
```

### <span data-ttu-id="76ab8-118">示例2：按几率和能够对整数分组</span><span class="sxs-lookup"><span data-stu-id="76ab8-118">Example 2: Group integers by odds and evens</span></span>

<span data-ttu-id="76ab8-119">此示例演示如何将脚本块用作 **Property** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="76ab8-119">This example shows how to use script blocks as the value of the **Property** parameter.</span></span> <span data-ttu-id="76ab8-120">此命令显示1到20之间的整数，并按可能性甚至进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-120">This command displays the integers from 1 to 20, grouped by odds and even.</span></span>

```powershell
1..20 | Group-Object -Property {$_ % 2}
```

```Output
Count Name                      Group
----- ----                      -----
   10 0                         {2, 4, 6, 8...}
   10 1                         {1, 3, 5, 7...}
```

### <span data-ttu-id="76ab8-121">示例3：按 EntryType 对事件日志事件进行分组</span><span class="sxs-lookup"><span data-stu-id="76ab8-121">Example 3: Group event log events by EntryType</span></span>

<span data-ttu-id="76ab8-122">此示例在系统事件日志中显示1000的最新条目，按 **EntryType** 分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-122">This example displays the 1,000 most recent entries in the System event log, grouped by **EntryType** .</span></span>

<span data-ttu-id="76ab8-123">在输出中， **Count** 列表示每个组中的条目数。</span><span class="sxs-lookup"><span data-stu-id="76ab8-123">In the output, the **Count** column represents the number of entries in each group.</span></span> <span data-ttu-id="76ab8-124">**Name** 列表示定义组 **的类型名称值。**</span><span class="sxs-lookup"><span data-stu-id="76ab8-124">The **Name** column represents the **EventType** values that define a group.</span></span> <span data-ttu-id="76ab8-125">**组** 列表示每个组中的对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-125">The **Group** column represents the objects in each group.</span></span>

```powershell
Get-WinEvent -LogName System -MaxEvents 1000 | Group-Object -Property LevelDisplayName
```

```Output
Count Name          Group
----- ----          -----
  153 Error         {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  722 Information   {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
  125 Warning       {System.Diagnostics.Eventing.Reader.EventLogRecord, System.Diagnostics...}
```

### <span data-ttu-id="76ab8-126">示例4：按优先级类对进程分组</span><span class="sxs-lookup"><span data-stu-id="76ab8-126">Example 4: Group processes by priority class</span></span>

<span data-ttu-id="76ab8-127">此示例演示了 **NoElement** 参数的效果。</span><span class="sxs-lookup"><span data-stu-id="76ab8-127">This example demonstrates the effect of the **NoElement** parameter.</span></span> <span data-ttu-id="76ab8-128">这些命令按优先级对计算机上的进程进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-128">These commands group the processes on the computer by priority class.</span></span>

<span data-ttu-id="76ab8-129">第一个命令使用 `Get-Process` cmdlet 来获取计算机上的进程，并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-129">The first command uses the `Get-Process` cmdlet to get the processes on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="76ab8-130">`Group-Object`按进程的 **PriorityClass** 属性的值对对象进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-130">`Group-Object`groups the objects by the value of the **PriorityClass** property of the process.</span></span>

<span data-ttu-id="76ab8-131">第二个示例使用 **NoElement** 参数从输出中删除组的成员。</span><span class="sxs-lookup"><span data-stu-id="76ab8-131">The second example uses the **NoElement** parameter to eliminate the members of the group from the output.</span></span> <span data-ttu-id="76ab8-132">结果为仅具有 **Count** 和 **Name** 属性值的表。</span><span class="sxs-lookup"><span data-stu-id="76ab8-132">The result is a table with only the **Count** and **Name** property value.</span></span>

<span data-ttu-id="76ab8-133">结果显示在下面的示例输出中。</span><span class="sxs-lookup"><span data-stu-id="76ab8-133">The results are shown in the following sample output.</span></span>

```powershell
Get-Process | Group-Object -Property PriorityClass
```

```Output
Count Name         Group
----- ----         -----
   55 Normal       {System.Diagnostics.Process (AdtAgent), System.Diagnosti...
    1              {System.Diagnostics.Process (Idle)}
    3 High         {System.Diagnostics.Process (Newproc), System.Diagnostic...
    2 BelowNormal  {System.Diagnostics.Process (winperf),
```

```powershell
Get-Process | Group-Object -Property PriorityClass -NoElement
```

```Output
Count Name
----- ----
   55 Normal
    1
    3 High
    2 BelowNormal
```

### <span data-ttu-id="76ab8-134">示例5：按名称对进程分组</span><span class="sxs-lookup"><span data-stu-id="76ab8-134">Example 5: Group processes by name</span></span>

<span data-ttu-id="76ab8-135">下面的示例使用 `Group-Object` 对本地计算机上运行的多个进程实例进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-135">The following example uses `Group-Object` to group multiple instances of processes running on the local computer.</span></span> <span data-ttu-id="76ab8-136">`Where-Object` 显示具有多个实例的进程。</span><span class="sxs-lookup"><span data-stu-id="76ab8-136">`Where-Object` displays processes with more than one instance.</span></span>

```powershell
Get-Process | Group-Object -Property Name -NoElement | Where-Object {$_.Count -gt 1}
```

```Output
Count Name
----- ----
2     csrss
5     svchost
2     winlogon
2     wmiprvse
```

### <span data-ttu-id="76ab8-137">示例6：将对象分组到哈希表中</span><span class="sxs-lookup"><span data-stu-id="76ab8-137">Example 6: Group objects in a hash table</span></span>

<span data-ttu-id="76ab8-138">此示例使用 **AsHashTable** 和 **AsString** 参数以键-值对集合的形式返回哈希表中的组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-138">This example uses the **AsHashTable** and **AsString** parameters to return the groups in a hash table, as a collection of key-value pairs.</span></span>

<span data-ttu-id="76ab8-139">在生成的哈希表中，每个属性值都是一个键，组元素是值。</span><span class="sxs-lookup"><span data-stu-id="76ab8-139">In the resulting hash table, each property value is a key, and the group elements are the values.</span></span>
<span data-ttu-id="76ab8-140">因为每个键都是哈希表对象的一个属性，所以你可以使用点表示法来显示这些值。</span><span class="sxs-lookup"><span data-stu-id="76ab8-140">Because each key is a property of the hash table object, you can use dot notation to display the values.</span></span>

<span data-ttu-id="76ab8-141">第一个命令获取 `Get` `Set` 会话中的和 cmdlet、按谓词对其进行分组、以哈希表的形式返回组，并将哈希表保存在 `$A` 变量中。</span><span class="sxs-lookup"><span data-stu-id="76ab8-141">The first command gets the `Get` and `Set` cmdlets in the session, groups them by verb, returns the groups as a hash table, and saves the hash table in the `$A` variable.</span></span>

<span data-ttu-id="76ab8-142">第二个命令显示中的哈希表 `$A` 。</span><span class="sxs-lookup"><span data-stu-id="76ab8-142">The second command displays the hash table in `$A`.</span></span> <span data-ttu-id="76ab8-143">有两个键-值对，一个用于 `Get` cmdlet，一个用于 `Set` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76ab8-143">There are two key-value pairs, one for the `Get` cmdlets and one for the `Set` cmdlets.</span></span>

<span data-ttu-id="76ab8-144">第三个命令使用点表示法， `$A.Get` 在中显示 " **获取** 密钥" 的值 `$A` 。</span><span class="sxs-lookup"><span data-stu-id="76ab8-144">The third command uses dot notation, `$A.Get` to display the values of the **Get** key in `$A`.</span></span> <span data-ttu-id="76ab8-145">这些值是 **CmdletInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-145">The values are **CmdletInfo** object.</span></span> <span data-ttu-id="76ab8-146">**AsString** 参数不会将组中的对象转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="76ab8-146">The **AsString** parameter doesn't convert the objects in the groups to strings.</span></span>

```powershell
$A = Get-Command Get-*, Set-* -CommandType cmdlet | Group-Object -Property Verb -AsHashTable -AsString
$A
```

```Output
Name     Value
----     -----
Get      {Get-Acl, Get-Alias, Get-AppLockerFileInformation, Get-AppLockerPolicy...}
Set      {Set-Acl, Set-Alias, Set-AppBackgroundTaskResourcePolicy, Set-AppLockerPolicy...}
```

```powershell
$A.Get
```

```Output
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Cmdlet          Get-Acl                            6.1.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-Alias                          6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Get-AuthenticodeSignature          6.1.0.0    Microsoft.PowerShell.Security
Cmdlet          Get-ChildItem                      6.1.0.0    Microsoft.PowerShell.Management
...
```

## <span data-ttu-id="76ab8-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="76ab8-147">PARAMETERS</span></span>

### <span data-ttu-id="76ab8-148">-AsHashTable</span><span class="sxs-lookup"><span data-stu-id="76ab8-148">-AsHashTable</span></span>

<span data-ttu-id="76ab8-149">指示此 cmdlet 将组作为哈希表返回。</span><span class="sxs-lookup"><span data-stu-id="76ab8-149">Indicates that this cmdlet returns the group as a hash table.</span></span> <span data-ttu-id="76ab8-150">哈希表的键是作为对象分组依据的属性值。</span><span class="sxs-lookup"><span data-stu-id="76ab8-150">The keys of the hash table are the property values by which the objects are grouped.</span></span> <span data-ttu-id="76ab8-151">哈希表的值是具有该属性值的对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-151">The values of the hash table are the objects that have that property value.</span></span>

<span data-ttu-id="76ab8-152">**AsHashTable** 参数本身返回每个哈希表，其中每个键都是一个分组对象的实例。</span><span class="sxs-lookup"><span data-stu-id="76ab8-152">By itself, the **AsHashTable** parameter returns each hash table in which each key is an instance of the grouped object.</span></span> <span data-ttu-id="76ab8-153">与 **AsString** 参数一起使用时，哈希表中的键是字符串。</span><span class="sxs-lookup"><span data-stu-id="76ab8-153">When used with the **AsString** parameter, the keys in the hash table are strings.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: AHT

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76ab8-154">-AsString</span><span class="sxs-lookup"><span data-stu-id="76ab8-154">-AsString</span></span>

<span data-ttu-id="76ab8-155">指示此 cmdlet 将哈希表键转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="76ab8-155">Indicates that this cmdlet converts the hash table keys to strings.</span></span> <span data-ttu-id="76ab8-156">默认情况下，哈希表键是分组对象的实例。</span><span class="sxs-lookup"><span data-stu-id="76ab8-156">By default, the hash table keys are instances of the grouped object.</span></span> <span data-ttu-id="76ab8-157">此参数仅在与 **AsHashTable** 参数一起使用时才有效。</span><span class="sxs-lookup"><span data-stu-id="76ab8-157">This parameter is valid only when used with the **AsHashTable** parameter.</span></span>

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

### <span data-ttu-id="76ab8-158">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="76ab8-158">-CaseSensitive</span></span>

<span data-ttu-id="76ab8-159">指示此 cmdlet 使分组区分大小写。</span><span class="sxs-lookup"><span data-stu-id="76ab8-159">Indicates that this cmdlet makes the grouping case-sensitive.</span></span> <span data-ttu-id="76ab8-160">在没有此参数的情况下，组中对象的属性值可能有不同的大小写。</span><span class="sxs-lookup"><span data-stu-id="76ab8-160">Without this parameter, the property values of objects in a group might have different cases.</span></span>

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

### <span data-ttu-id="76ab8-161">-Culture</span><span class="sxs-lookup"><span data-stu-id="76ab8-161">-Culture</span></span>

<span data-ttu-id="76ab8-162">指定要在比较字符串时使用的区域性。</span><span class="sxs-lookup"><span data-stu-id="76ab8-162">Specifies the culture to use when comparing strings.</span></span>

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

### <span data-ttu-id="76ab8-163">-InputObject</span><span class="sxs-lookup"><span data-stu-id="76ab8-163">-InputObject</span></span>

<span data-ttu-id="76ab8-164">指定要分组的对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-164">Specifies the objects to group.</span></span> <span data-ttu-id="76ab8-165">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="76ab8-165">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="76ab8-166">使用 **InputObject** 参数将对象集合提交到时 `Group-Object` ，会 `Group-Object` 收到一个表示集合的对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-166">When you use the **InputObject** parameter to submit a collection of objects to `Group-Object`, `Group-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="76ab8-167">因此，它将创建一个组并将该对象用作其成员。</span><span class="sxs-lookup"><span data-stu-id="76ab8-167">As a result, it creates a single group with that object as its member.</span></span>

<span data-ttu-id="76ab8-168">若要对集合中的对象进行分组，请通过管道将对象传递给 `Group-Object` 。</span><span class="sxs-lookup"><span data-stu-id="76ab8-168">To group the objects in a collection, pipe the objects to `Group-Object`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="76ab8-169">-NoElement</span><span class="sxs-lookup"><span data-stu-id="76ab8-169">-NoElement</span></span>

<span data-ttu-id="76ab8-170">指示此 cmdlet 省略结果中组的成员。</span><span class="sxs-lookup"><span data-stu-id="76ab8-170">Indicates that this cmdlet omits the members of a group from the results.</span></span>

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

### <span data-ttu-id="76ab8-171">-Property</span><span class="sxs-lookup"><span data-stu-id="76ab8-171">-Property</span></span>

<span data-ttu-id="76ab8-172">指定用于分组的属性。</span><span class="sxs-lookup"><span data-stu-id="76ab8-172">Specifies the properties for grouping.</span></span> <span data-ttu-id="76ab8-173">根据指定属性的值将对象排列成组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-173">The objects are arranged into groups based on the value of the specified property.</span></span>

<span data-ttu-id="76ab8-174">**Property** 参数的值可以是新的计算属性。</span><span class="sxs-lookup"><span data-stu-id="76ab8-174">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="76ab8-175">计算属性可以是脚本块，也可以是哈希表。</span><span class="sxs-lookup"><span data-stu-id="76ab8-175">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="76ab8-176">有效的键-值对为：</span><span class="sxs-lookup"><span data-stu-id="76ab8-176">Valid key-value pairs are:</span></span>

- <span data-ttu-id="76ab8-177">Expression `<string>` 或 `<script block>`</span><span class="sxs-lookup"><span data-stu-id="76ab8-177">Expression - `<string>` or `<script block>`</span></span>

<span data-ttu-id="76ab8-178">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="76ab8-178">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="76ab8-179">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="76ab8-179">CommonParameters</span></span>

<span data-ttu-id="76ab8-180">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="76ab8-180">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="76ab8-181">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="76ab8-181">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="76ab8-182">输入</span><span class="sxs-lookup"><span data-stu-id="76ab8-182">INPUTS</span></span>

### <span data-ttu-id="76ab8-183">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="76ab8-183">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="76ab8-184">可以通过管道将任何对象传递给 `Group-Object` 。</span><span class="sxs-lookup"><span data-stu-id="76ab8-184">You can pipe any object to `Group-Object`.</span></span>

## <span data-ttu-id="76ab8-185">输出</span><span class="sxs-lookup"><span data-stu-id="76ab8-185">OUTPUTS</span></span>

### <span data-ttu-id="76ab8-186">Microsoft.PowerShell.Commands.GroupInfo 或 System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="76ab8-186">Microsoft.PowerShell.Commands.GroupInfo or System.Collections.Hashtable</span></span>

<span data-ttu-id="76ab8-187">当你使用 **AsHashTable** 参数时，将 `Group-Object` 返回一个 **哈希表** 对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-187">When you use the **AsHashTable** parameter, `Group-Object` returns a **Hashtable** object.</span></span>
<span data-ttu-id="76ab8-188">否则，它将返回 **GroupInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="76ab8-188">Otherwise, it returns a **GroupInfo** object.</span></span>

## <span data-ttu-id="76ab8-189">注释</span><span class="sxs-lookup"><span data-stu-id="76ab8-189">NOTES</span></span>

<span data-ttu-id="76ab8-190">您可以使用格式设置 cmdlet （例如和）的 **GroupBy** 参数 `Format-Table` `Format-List` 对对象进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-190">You can use the **GroupBy** parameter of the formatting cmdlets, such as `Format-Table` and `Format-List`, to group objects.</span></span> <span data-ttu-id="76ab8-191">与 `Group-Object` （这会创建一个表，其中每个属性值对应一行）不同， **GroupBy** 参数为每个属性值创建一个表，每个属性值对应于具有属性值的每个项。</span><span class="sxs-lookup"><span data-stu-id="76ab8-191">Unlike `Group-Object`, which creates a single table with a row for each property value, the **GroupBy** parameters create a table for each property value with a row for each item that has the property value.</span></span>

<span data-ttu-id="76ab8-192">`Group-Object` 不要求分组的对象具有相同的 Microsoft .NET 核心类型。</span><span class="sxs-lookup"><span data-stu-id="76ab8-192">`Group-Object` doesn't require that the objects being grouped are of the same Microsoft .NET Core type.</span></span> <span data-ttu-id="76ab8-193">分组不同 .NET Core 类型的对象时， `Group-Object` 将使用以下规则：</span><span class="sxs-lookup"><span data-stu-id="76ab8-193">When grouping objects of different .NET Core types, `Group-Object` uses the following rules:</span></span>

- <span data-ttu-id="76ab8-194">相同的属性名和类型。</span><span class="sxs-lookup"><span data-stu-id="76ab8-194">Same Property Names and Types.</span></span>

  <span data-ttu-id="76ab8-195">如果对象具有具有指定名称的属性，并且属性值具有相同的 .NET Core 类型，则将使用与同一类型的对象相同的规则对属性值进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-195">If the objects have a property with the specified name, and the property values have the same .NET Core type, the property values are grouped by using the same rules that would be used for objects of the same type.</span></span>

- <span data-ttu-id="76ab8-196">相同的属性名称和不同类型。</span><span class="sxs-lookup"><span data-stu-id="76ab8-196">Same Property Names, Different Types.</span></span>

  <span data-ttu-id="76ab8-197">如果对象具有具有指定名称的属性，但属性值在不同的对象中具有不同的 .NET Core 类型，则使用该属性的 `Group-Object` 第一个匹配项的 .Net 核心类型作为该属性组的 .Net core 类型。</span><span class="sxs-lookup"><span data-stu-id="76ab8-197">If the objects have a property with the specified name, but the property values have a different .NET Core type in different objects, `Group-Object` uses the .NET Core type of the first occurrence of the property as the .NET Core type for that property group.</span></span> <span data-ttu-id="76ab8-198">当对象具有不同类型的属性时，会将属性值转换为该组的类型。</span><span class="sxs-lookup"><span data-stu-id="76ab8-198">When an object has a property with a different type, the property value is converted to the type for that group.</span></span> <span data-ttu-id="76ab8-199">如果类型转换失败，则不会将该对象包含在组中。</span><span class="sxs-lookup"><span data-stu-id="76ab8-199">If the type conversion fails, the object isn't included in the group.</span></span>

- <span data-ttu-id="76ab8-200">缺少属性。</span><span class="sxs-lookup"><span data-stu-id="76ab8-200">Missing Properties.</span></span>

  <span data-ttu-id="76ab8-201">不能对没有指定属性的对象进行分组。</span><span class="sxs-lookup"><span data-stu-id="76ab8-201">Objects that don't have a specified property can't be grouped.</span></span> <span data-ttu-id="76ab8-202">未分组的对象会出现在名为的组中的最终 **GroupInfo** 对象输出中 `AutomationNull.Value` 。</span><span class="sxs-lookup"><span data-stu-id="76ab8-202">Objects that aren't grouped appear in the final **GroupInfo** object output in a group named `AutomationNull.Value`.</span></span>

## <span data-ttu-id="76ab8-203">相关链接</span><span class="sxs-lookup"><span data-stu-id="76ab8-203">RELATED LINKS</span></span>

[<span data-ttu-id="76ab8-204">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="76ab8-204">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="76ab8-205">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="76ab8-205">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="76ab8-206">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-206">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="76ab8-207">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-207">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="76ab8-208">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-208">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="76ab8-209">New-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-209">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="76ab8-210">Select-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-210">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="76ab8-211">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-211">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="76ab8-212">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-212">Tee-Object</span></span>](Tee-Object.md)

[<span data-ttu-id="76ab8-213">Where-Object</span><span class="sxs-lookup"><span data-stu-id="76ab8-213">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
