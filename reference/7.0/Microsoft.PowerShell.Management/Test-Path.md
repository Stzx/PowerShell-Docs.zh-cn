---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Path
ms.openlocfilehash: fcfb974a360c450f474ba97d65190b019860d8c4
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197075"
---
# <span data-ttu-id="36ece-103">Test-Path</span><span class="sxs-lookup"><span data-stu-id="36ece-103">Test-Path</span></span>

## <span data-ttu-id="36ece-104">摘要</span><span class="sxs-lookup"><span data-stu-id="36ece-104">SYNOPSIS</span></span>
<span data-ttu-id="36ece-105">确定路径的所有元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="36ece-105">Determines whether all elements of a path exist.</span></span>

## <span data-ttu-id="36ece-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="36ece-106">SYNTAX</span></span>

### <span data-ttu-id="36ece-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="36ece-107">Path (Default)</span></span>

```
Test-Path [-Path] <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

### <span data-ttu-id="36ece-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="36ece-108">LiteralPath</span></span>

```
Test-Path -LiteralPath <String[]> [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-PathType <TestPathType>] [-IsValid] [-Credential <PSCredential>]
 [-OlderThan <DateTime>] [-NewerThan <DateTime>] [<CommonParameters>]
```

## <span data-ttu-id="36ece-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="36ece-109">DESCRIPTION</span></span>

<span data-ttu-id="36ece-110">`Test-Path`Cmdlet 确定路径的所有元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="36ece-110">The `Test-Path` cmdlet determines whether all elements of the path exist.</span></span> <span data-ttu-id="36ece-111">`$True`如果所有元素都存在，则返回，否则返回 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-111">It returns `$True` if all elements exist and `$False` if any are missing.</span></span> <span data-ttu-id="36ece-112">它还可以指示路径语法是否有效，以及路径是指向容器还是终结或叶元素。</span><span class="sxs-lookup"><span data-stu-id="36ece-112">It can also tell whether the path syntax is valid and whether the path leads to a container or a terminal or leaf element.</span></span> <span data-ttu-id="36ece-113">如果 `Path` 为空字符串，则 `$False` 返回。</span><span class="sxs-lookup"><span data-stu-id="36ece-113">If the `Path` is whitespace an empty string, then `$False` is returned.</span></span> <span data-ttu-id="36ece-114">如果 `Path` 为 `$null` 、数组 `$null` 或空数组，则返回一个非终止错误。</span><span class="sxs-lookup"><span data-stu-id="36ece-114">If the `Path` is `$null`, array of `$null` or empty array, a non-terminating error is returned.</span></span>

## <span data-ttu-id="36ece-115">示例</span><span class="sxs-lookup"><span data-stu-id="36ece-115">EXAMPLES</span></span>

### <span data-ttu-id="36ece-116">示例1：测试路径</span><span class="sxs-lookup"><span data-stu-id="36ece-116">Example 1: Test a path</span></span>

```powershell
Test-Path -Path "C:\Documents and Settings\DavidC"
```

```Output
True
```

<span data-ttu-id="36ece-117">此命令检查路径中的所有元素是否都存在（即 C：目录、文档和设置目录）以及 DavidC 目录。</span><span class="sxs-lookup"><span data-stu-id="36ece-117">This command checks whether all elements in the path exist, that is, the C: directory, the Documents and Settings directory, and the DavidC directory.</span></span> <span data-ttu-id="36ece-118">如果缺少任何，cmdlet 将返回 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-118">If any are missing, the cmdlet returns `$False`.</span></span>
<span data-ttu-id="36ece-119">否则，它将返回 `$True`。</span><span class="sxs-lookup"><span data-stu-id="36ece-119">Otherwise, it returns `$True`.</span></span>

### <span data-ttu-id="36ece-120">示例2：测试配置文件的路径</span><span class="sxs-lookup"><span data-stu-id="36ece-120">Example 2: Test the path of a profile</span></span>

```powershell
Test-Path -Path $profile
```

```Output
False
```

```powershell
Test-Path -Path $profile -IsValid
```

```Output
True
```

<span data-ttu-id="36ece-121">这些命令测试 PowerShell 配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="36ece-121">These commands test the path of the PowerShell profile.</span></span>

<span data-ttu-id="36ece-122">第一个命令确定路径中的所有元素是否都存在。</span><span class="sxs-lookup"><span data-stu-id="36ece-122">The first command determines whether all elements in the path exist.</span></span> <span data-ttu-id="36ece-123">第二个命令确定路径的语法是否正确。</span><span class="sxs-lookup"><span data-stu-id="36ece-123">The second command determines whether the syntax of the path is correct.</span></span> <span data-ttu-id="36ece-124">在这种情况下，路径为 `$False` ，但语法正确 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-124">In this case, the path is `$False`, but the syntax is correct `$True`.</span></span> <span data-ttu-id="36ece-125">即使配置文件不存在，这些命令 `$profile` 也使用自动变量，该变量指向配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="36ece-125">These commands use `$profile`, the automatic variable that points to the location for the profile, even if the profile does not exist.</span></span>

<span data-ttu-id="36ece-126">有关自动变量的详细信息，请参阅 about_Automatic_Variables。</span><span class="sxs-lookup"><span data-stu-id="36ece-126">For more information about automatic variables, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="36ece-127">示例3：检查是否存在除指定类型之外的任何文件</span><span class="sxs-lookup"><span data-stu-id="36ece-127">Example 3: Check whether there are any files besides a specified type</span></span>

```powershell
Test-Path -Path "C:\CAD\Commercial Buildings\*" -Exclude *.dwg
```

```Output
False
```

<span data-ttu-id="36ece-128">此命令检查商业大楼目录中是否存在除 dwg 文件之外的任何文件。</span><span class="sxs-lookup"><span data-stu-id="36ece-128">This command checks whether there are any files in the Commercial Buildings directory other than .dwg files.</span></span>

<span data-ttu-id="36ece-129">该命令使用 **path** 参数来指定路径。</span><span class="sxs-lookup"><span data-stu-id="36ece-129">The command uses the **Path** parameter to specify the path.</span></span> <span data-ttu-id="36ece-130">由于路径包含空格，因此该路径用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="36ece-130">Because the path includes a space, the path is enclosed in quotation marks.</span></span> <span data-ttu-id="36ece-131">该路径末尾的星号指示 Commercial Building 目录的内容。</span><span class="sxs-lookup"><span data-stu-id="36ece-131">The asterisk at the end of the path indicates the contents of the Commercial Building directory.</span></span> <span data-ttu-id="36ece-132">使用长路径（如此类），键入路径的前几个字母，然后使用 TAB 键完成路径。</span><span class="sxs-lookup"><span data-stu-id="36ece-132">With long paths, such as this one, type the first few letters of the path, and then use the TAB key to complete the path.</span></span>

<span data-ttu-id="36ece-133">命令指定 **Exclude** 参数，以指定将在计算中省略的文件。</span><span class="sxs-lookup"><span data-stu-id="36ece-133">The command specifies the **Exclude** parameter to specify files that will be omitted from the evaluation.</span></span>

<span data-ttu-id="36ece-134">在这种情况下，由于目录只包含 dwg 文件，因此结果为 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-134">In this case, because the directory contains only .dwg files, the result is `$False`.</span></span>

### <span data-ttu-id="36ece-135">示例4：检查文件</span><span class="sxs-lookup"><span data-stu-id="36ece-135">Example 4: Check for a file</span></span>

```powershell
Test-Path -Path $profile -PathType leaf
```

```Output
True
```

<span data-ttu-id="36ece-136">此命令检查变量中存储的路径是否会 `$profile` 导致文件。</span><span class="sxs-lookup"><span data-stu-id="36ece-136">This command checks whether the path stored in the `$profile` variable leads to a file.</span></span> <span data-ttu-id="36ece-137">在这种情况下，由于 PowerShell 配置文件是一个 `.ps1` 文件，因此该 cmdlet 将返回 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-137">In this case, because the PowerShell profile is a `.ps1` file, the cmdlet returns `$True`.</span></span>

### <span data-ttu-id="36ece-138">示例5：检查注册表中的路径</span><span class="sxs-lookup"><span data-stu-id="36ece-138">Example 5: Check paths in the Registry</span></span>

<span data-ttu-id="36ece-139">这些命令 `Test-Path` 与 PowerShell 注册表提供程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="36ece-139">These commands use `Test-Path` with the PowerShell registry provider.</span></span>

<span data-ttu-id="36ece-140">第一个命令测试系统上的 **Microsoft PowerShell** 注册表项的注册表路径是否正确。</span><span class="sxs-lookup"><span data-stu-id="36ece-140">The first command tests whether the registry path of the **Microsoft.PowerShell** registry key is correct on the system.</span></span> <span data-ttu-id="36ece-141">如果 PowerShell 安装正确，则该 cmdlet 将返回 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-141">If PowerShell is installed correctly, the cmdlet returns `$True`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36ece-142">`Test-Path` 不适用于所有 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="36ece-142">`Test-Path` does not work correctly with all PowerShell providers.</span></span> <span data-ttu-id="36ece-143">例如，你可以使用 `Test-Path` 来测试注册表项的路径，但如果你使用它来测试注册表项的路径，它将始终返回 `$False` ，即使存在该注册表项。</span><span class="sxs-lookup"><span data-stu-id="36ece-143">For example, you can use `Test-Path` to test the path of a registry key, but if you use it to test the path of a registry entry, it always returns `$False`, even if the registry entry is present.</span></span>

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell"
```

```Output
True
```

```powershell
Test-Path -Path "HKLM:\Software\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell\ExecutionPolicy"
```

```Output
False
```

### <span data-ttu-id="36ece-144">示例6：测试文件是否比指定日期新</span><span class="sxs-lookup"><span data-stu-id="36ece-144">Example 6: Test if a file is newer than a specified date</span></span>

<span data-ttu-id="36ece-145">此命令使用 **NewerThan** 动态参数来确定计算机上的 "PowerShell.exe" 文件是否比 "7 月13日 2009" 新。</span><span class="sxs-lookup"><span data-stu-id="36ece-145">This command uses the **NewerThan** dynamic parameter to determine whether the "PowerShell.exe" file on the computer is newer than "July 13, 2009".</span></span>

<span data-ttu-id="36ece-146">NewerThan 参数仅在文件系统驱动器中有效。</span><span class="sxs-lookup"><span data-stu-id="36ece-146">The NewerThan parameter works only in file system drives.</span></span>

```powershell
Test-Path $pshome\PowerShell.exe -NewerThan "July 13, 2009"
```

```Output
True
```

### <span data-ttu-id="36ece-147">示例7：使用 null 作为值测试路径</span><span class="sxs-lookup"><span data-stu-id="36ece-147">Example 7: Test a path with null as the value</span></span>

<span data-ttu-id="36ece-148">为返回的错误 `null` 、数组 `null` 或空数组为非终止错误。</span><span class="sxs-lookup"><span data-stu-id="36ece-148">The error returned for `null`, array of `null` or empty array is a non-terminating error.</span></span> <span data-ttu-id="36ece-149">可以通过使用将其取消 `-ErrorAction SilentlyContinue` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-149">It can be suppress by using `-ErrorAction SilentlyContinue`.</span></span> <span data-ttu-id="36ece-150">下面的示例显示返回错误的所有情况 `NullPathNotPermitted` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-150">The following example shows all cases which return the `NullPathNotPermitted` error.</span></span>

```powershell
Test-Path $null
Test-Path $null, $null
Test-Path @()
```

```Output
Test-Path : Cannot bind argument to parameter 'Path' because it is null.
At line:1 char:11
+ Test-Path $null
+           ~~~~~
    + CategoryInfo          : InvalidData: (:) [Test-Path], ParameterBindingValidationException
    + FullyQualifiedErrorId : ParameterArgumentValidationErrorNullNotAllowed,Microsoft.PowerShell.Commands.TestPathCommand
```

### <span data-ttu-id="36ece-151">示例8：测试带有空格作为值的路径</span><span class="sxs-lookup"><span data-stu-id="36ece-151">Example 8: Test a path with whitespace as the value</span></span>

<span data-ttu-id="36ece-152">如果为参数提供了空白或空字符串 `-Path` ，则返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="36ece-152">When a whitespace or empty string is provided for the the `-Path` parameter, it returns **False** .</span></span>
<span data-ttu-id="36ece-153">下面的示例显示了空白和空字符串。</span><span class="sxs-lookup"><span data-stu-id="36ece-153">The following example show whitespace and empty string.</span></span>

```powershell
Test-Path ' '
Test-Path ''
```

```Output
False
False
```

## <span data-ttu-id="36ece-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="36ece-154">PARAMETERS</span></span>

### <span data-ttu-id="36ece-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="36ece-155">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="36ece-156">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="36ece-156">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="36ece-157">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="36ece-157">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36ece-158">-Exclude</span><span class="sxs-lookup"><span data-stu-id="36ece-158">-Exclude</span></span>

<span data-ttu-id="36ece-159">指定此 cmdlet 省略的项。</span><span class="sxs-lookup"><span data-stu-id="36ece-159">Specifies items that this cmdlet omits.</span></span> <span data-ttu-id="36ece-160">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="36ece-160">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="36ece-161">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="36ece-161">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="36ece-162">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="36ece-162">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="36ece-163">-Filter</span><span class="sxs-lookup"><span data-stu-id="36ece-163">-Filter</span></span>

<span data-ttu-id="36ece-164">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="36ece-164">Specifies a filter in the format or language of the provider.</span></span> <span data-ttu-id="36ece-165">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="36ece-165">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="36ece-166">筛选器的语法（包括通配符字符的使用），具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="36ece-166">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="36ece-167">筛选器比其他参数更有效，因为提供程序在检索对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="36ece-167">Filters are more efficient than other parameters, because the provider applies them when it retrieves the objects instead of having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="36ece-168">-Include</span><span class="sxs-lookup"><span data-stu-id="36ece-168">-Include</span></span>

<span data-ttu-id="36ece-169">指定此 cmdlet 测试的路径。</span><span class="sxs-lookup"><span data-stu-id="36ece-169">Specifies paths that this cmdlet tests.</span></span> <span data-ttu-id="36ece-170">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="36ece-170">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="36ece-171">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="36ece-171">Enter a path element or pattern, such as "\*.txt".</span></span> <span data-ttu-id="36ece-172">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="36ece-172">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="36ece-173">-IsValid</span><span class="sxs-lookup"><span data-stu-id="36ece-173">-IsValid</span></span>

<span data-ttu-id="36ece-174">指示此 cmdlet 测试路径的语法，而不考虑路径的元素是否存在。</span><span class="sxs-lookup"><span data-stu-id="36ece-174">Indicates that this cmdlet tests the syntax of the path, regardless of whether the elements of the path exist.</span></span> <span data-ttu-id="36ece-175">`$True`如果路径语法有效，则此 cmdlet 将返回 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-175">This cmdlet returns `$True` if the path syntax is valid and `$False` if it is not.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36ece-176">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="36ece-176">-LiteralPath</span></span>

<span data-ttu-id="36ece-177">指定要测试的路径。</span><span class="sxs-lookup"><span data-stu-id="36ece-177">Specifies a path to be tested.</span></span> <span data-ttu-id="36ece-178">与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="36ece-178">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="36ece-179">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="36ece-179">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="36ece-180">如果路径中包含可以由 PowerShell 解释为转义序列的字符，则必须将路径括在单引号中，以便不会解释它们。</span><span class="sxs-lookup"><span data-stu-id="36ece-180">If the path includes characters that could be interpreted by PowerShell as escape sequences, you must enclose the path in single quote so that they won't be interpreted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="36ece-181">-NewerThan</span><span class="sxs-lookup"><span data-stu-id="36ece-181">-NewerThan</span></span>

<span data-ttu-id="36ece-182">指定时间作为 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="36ece-182">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36ece-183">-OlderThan</span><span class="sxs-lookup"><span data-stu-id="36ece-183">-OlderThan</span></span>

<span data-ttu-id="36ece-184">指定时间作为 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="36ece-184">Specify a time as a **DateTime** object.</span></span>

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36ece-185">-Path</span><span class="sxs-lookup"><span data-stu-id="36ece-185">-Path</span></span>

<span data-ttu-id="36ece-186">指定要测试的路径。</span><span class="sxs-lookup"><span data-stu-id="36ece-186">Specifies a path to be tested.</span></span> <span data-ttu-id="36ece-187">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="36ece-187">Wildcard characters are permitted.</span></span> <span data-ttu-id="36ece-188">如果路径包括空格，请将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="36ece-188">If the path includes spaces, enclose it in quotation marks.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="36ece-189">-PathType</span><span class="sxs-lookup"><span data-stu-id="36ece-189">-PathType</span></span>

<span data-ttu-id="36ece-190">指定路径中最后一个元素的类型。</span><span class="sxs-lookup"><span data-stu-id="36ece-190">Specifies the type of the final element in the path.</span></span> <span data-ttu-id="36ece-191">`$True`如果元素为指定的类型，则此 cmdlet 将返回，如果不是，则返回 `$False` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-191">This cmdlet returns `$True` if the element is of the specified type and `$False` if it is not.</span></span> <span data-ttu-id="36ece-192">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="36ece-192">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="36ece-193">容器。</span><span class="sxs-lookup"><span data-stu-id="36ece-193">Container.</span></span>
  <span data-ttu-id="36ece-194">-- 包含其他元素的元素，例如目录或注册表项。</span><span class="sxs-lookup"><span data-stu-id="36ece-194">An element that contains other elements, such as a directory or registry key.</span></span>
- <span data-ttu-id="36ece-195">片.</span><span class="sxs-lookup"><span data-stu-id="36ece-195">Leaf.</span></span>
  <span data-ttu-id="36ece-196">-- 不包含其他元素的元素，例如文件。</span><span class="sxs-lookup"><span data-stu-id="36ece-196">An element that does not contain other elements, such as a file.</span></span>
- <span data-ttu-id="36ece-197">随时.</span><span class="sxs-lookup"><span data-stu-id="36ece-197">Any.</span></span>
  <span data-ttu-id="36ece-198">container 或 leaf。</span><span class="sxs-lookup"><span data-stu-id="36ece-198">Either a container or a leaf.</span></span>

<span data-ttu-id="36ece-199">指示路径中的最后一个元素是否为特定类型。</span><span class="sxs-lookup"><span data-stu-id="36ece-199">Tells whether the final element in the path is of a particular type.</span></span>

> [!CAUTION]
>
> <span data-ttu-id="36ece-200">最多 PowerShell 版本6.1.2，当 **IsValid** 和 **PathType** 开关一起指定时，该 `Test-Path` cmdlet 将忽略 **PathType** 开关，并且仅验证句法路径，而不验证路径类型。</span><span class="sxs-lookup"><span data-stu-id="36ece-200">Up to PowerShell version 6.1.2, when the **IsValid** and **PathType** switches are specified together, the `Test-Path` cmdlet ignores the **PathType** switch and only validates the syntactic path without validating the path type.</span></span>
>
> <span data-ttu-id="36ece-201">根据 [问题 #8607](https://github.com/PowerShell/PowerShell/issues/8607)，修复此行为可能是将来版本中的重大更改，其中 **IsValid** 和 **PathType** 开关属于单独的参数集，因此不能共同使用来避免这种混淆。</span><span class="sxs-lookup"><span data-stu-id="36ece-201">According to [issue #8607](https://github.com/PowerShell/PowerShell/issues/8607), fixing this behavior may be a breaking change in a future version, where the **IsValid** and **PathType** switches belong to separate parameter sets, and thus, cannot be used together avoiding this confusion.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.TestPathType
Parameter Sets: (All)
Aliases: Type
Accepted values: Any, Container, Leaf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="36ece-202">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="36ece-202">CommonParameters</span></span>

<span data-ttu-id="36ece-203">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="36ece-203">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="36ece-204">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="36ece-204">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="36ece-205">输入</span><span class="sxs-lookup"><span data-stu-id="36ece-205">INPUTS</span></span>

### <span data-ttu-id="36ece-206">System.String</span><span class="sxs-lookup"><span data-stu-id="36ece-206">System.String</span></span>

<span data-ttu-id="36ece-207">可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="36ece-207">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="36ece-208">输出</span><span class="sxs-lookup"><span data-stu-id="36ece-208">OUTPUTS</span></span>

### <span data-ttu-id="36ece-209">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="36ece-209">System.Boolean</span></span>

<span data-ttu-id="36ece-210">该 cmdlet 将返回一个 **布尔** 值。</span><span class="sxs-lookup"><span data-stu-id="36ece-210">The cmdlet returns a **Boolean** value.</span></span>

## <span data-ttu-id="36ece-211">注释</span><span class="sxs-lookup"><span data-stu-id="36ece-211">NOTES</span></span>

<span data-ttu-id="36ece-212">包含路径 cmdlet (路径 **名词的** cmdlet) **使用路径名，** 并以所有 PowerShell 提供程序可解释的简洁格式返回名称。</span><span class="sxs-lookup"><span data-stu-id="36ece-212">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="36ece-213">这些 cmdlet 用于需要在其中以特定格式显示全部或部分路径名称的程序或脚本中。</span><span class="sxs-lookup"><span data-stu-id="36ece-213">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="36ece-214">使用 **Dirname** 、 **Normpath** 、 **Realpath** 、 **Join** 或其他路径操控器。</span><span class="sxs-lookup"><span data-stu-id="36ece-214">Use them as you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="36ece-215">`Test-Path`设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="36ece-215">The `Test-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="36ece-216">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="36ece-216">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="36ece-217">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="36ece-217">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="36ece-218">相关链接</span><span class="sxs-lookup"><span data-stu-id="36ece-218">RELATED LINKS</span></span>

[<span data-ttu-id="36ece-219">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="36ece-219">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="36ece-220">Join-Path</span><span class="sxs-lookup"><span data-stu-id="36ece-220">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="36ece-221">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="36ece-221">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="36ece-222">Split-Path</span><span class="sxs-lookup"><span data-stu-id="36ece-222">Split-Path</span></span>](Split-Path.md)
