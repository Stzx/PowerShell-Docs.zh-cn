---
description: 描述变量如何存储可在 PowerShell 中使用的值。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Variables
ms.openlocfilehash: 59a611cf49635f0391d3f3cc18bcf6d06a688638
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200234"
---
# <a name="about-variables"></a><span data-ttu-id="cedfe-104">关于变量</span><span class="sxs-lookup"><span data-stu-id="cedfe-104">About Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="cedfe-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="cedfe-105">Short description</span></span>

<span data-ttu-id="cedfe-106">描述变量如何存储可在 PowerShell 中使用的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-106">Describes how variables store values that can be used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="cedfe-107">长说明</span><span class="sxs-lookup"><span data-stu-id="cedfe-107">Long description</span></span>

<span data-ttu-id="cedfe-108">可以在 PowerShell 变量中存储所有类型的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-108">You can store all types of values in PowerShell variables.</span></span> <span data-ttu-id="cedfe-109">例如，存储命令的结果，并存储命令和表达式中使用的元素，例如名称、路径、设置和值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-109">For example, store the results of commands, and store elements that are used in commands and expressions, such as names, paths, settings, and values.</span></span>

<span data-ttu-id="cedfe-110">变量是存储值的内存单位。</span><span class="sxs-lookup"><span data-stu-id="cedfe-110">A variable is a unit of memory in which values are stored.</span></span> <span data-ttu-id="cedfe-111">在 PowerShell 中，变量由以美元符号开头的文本字符串表示 (`$`) ，如 `$a` 、 `$process` 或 `$my_var` 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-111">In PowerShell, variables are represented by text strings that begin with a dollar sign (`$`), such as `$a`, `$process`, or `$my_var`.</span></span>

<span data-ttu-id="cedfe-112">变量名称不区分大小写，并且可以包含空格和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="cedfe-112">Variable names aren't case-sensitive, and can include spaces and special characters.</span></span> <span data-ttu-id="cedfe-113">但是，包含特殊字符和空格的变量名称难以使用，应避免使用。</span><span class="sxs-lookup"><span data-stu-id="cedfe-113">But, variable names that include special characters and spaces are difficult to use and should be avoided.</span></span> <span data-ttu-id="cedfe-114">有关详细信息，请参阅 [包含特殊字符的变量名称](#variable-names-that-include-special-characters)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-114">For more information, see [Variable names that include special characters](#variable-names-that-include-special-characters).</span></span>

<span data-ttu-id="cedfe-115">在 PowerShell 中有几种不同类型的变量。</span><span class="sxs-lookup"><span data-stu-id="cedfe-115">There are several different types of variables in PowerShell.</span></span>

- <span data-ttu-id="cedfe-116">用户创建的变量：用户创建的变量由用户创建和维护。</span><span class="sxs-lookup"><span data-stu-id="cedfe-116">User-created variables: User-created variables are created and maintained by the user.</span></span> <span data-ttu-id="cedfe-117">默认情况下，在 powershell 命令行中创建的变量仅在 PowerShell 窗口处于打开状态时才存在。</span><span class="sxs-lookup"><span data-stu-id="cedfe-117">By default, the variables that you create at the PowerShell command line exist only while the PowerShell window is open.</span></span> <span data-ttu-id="cedfe-118">当 PowerShell 窗口关闭时，这些变量将被删除。</span><span class="sxs-lookup"><span data-stu-id="cedfe-118">When the PowerShell windows is closed, the variables are deleted.</span></span> <span data-ttu-id="cedfe-119">若要保存某个变量，请将其添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="cedfe-119">To save a variable, add it to your PowerShell profile.</span></span> <span data-ttu-id="cedfe-120">你还可以在具有全局、脚本或本地范围的脚本中创建变量。</span><span class="sxs-lookup"><span data-stu-id="cedfe-120">You can also create variables in scripts with global, script, or local scope.</span></span>

- <span data-ttu-id="cedfe-121">自动变量：自动变量存储 PowerShell 的状态。</span><span class="sxs-lookup"><span data-stu-id="cedfe-121">Automatic variables: Automatic variables store the state of PowerShell.</span></span> <span data-ttu-id="cedfe-122">这些变量由 PowerShell 创建，PowerShell 会根据需要更改它们的值以保持其准确性。</span><span class="sxs-lookup"><span data-stu-id="cedfe-122">These variables are created by PowerShell, and PowerShell changes their values as required to maintain their accuracy.</span></span> <span data-ttu-id="cedfe-123">用户不能更改这些变量的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-123">Users can't change the value of these variables.</span></span> <span data-ttu-id="cedfe-124">例如， `$PSHOME` 变量存储 PowerShell 安装目录的路径。</span><span class="sxs-lookup"><span data-stu-id="cedfe-124">For example, the `$PSHOME` variable stores the path to the PowerShell installation directory.</span></span>

  <span data-ttu-id="cedfe-125">有关自动变量的详细信息、列表和说明，请参阅 [about_Automatic_Variables](about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-125">For more information, a list, and a description of the automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

- <span data-ttu-id="cedfe-126">首选项变量：首选项为 PowerShell 存储用户首选项。</span><span class="sxs-lookup"><span data-stu-id="cedfe-126">Preference variables: Preference variables store user preferences for PowerShell.</span></span> <span data-ttu-id="cedfe-127">这些变量由 PowerShell 创建，并使用默认值进行填充。</span><span class="sxs-lookup"><span data-stu-id="cedfe-127">These variables are created by PowerShell and are populated with default values.</span></span> <span data-ttu-id="cedfe-128">用户可以更改这些变量的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-128">Users can change the values of these variables.</span></span> <span data-ttu-id="cedfe-129">例如， `$MaximumHistoryCount` 变量确定会话历史记录中的最大项数。</span><span class="sxs-lookup"><span data-stu-id="cedfe-129">For example, the `$MaximumHistoryCount` variable determines the maximum number of entries in the session history.</span></span>

  <span data-ttu-id="cedfe-130">有关首选项变量的详细信息、列表和说明，请参阅 [about_Preference_Variables](about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-130">For more information, a list, and a description of the preference variables, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="working-with-variables"></a><span data-ttu-id="cedfe-131">使用变量</span><span class="sxs-lookup"><span data-stu-id="cedfe-131">Working with variables</span></span>

<span data-ttu-id="cedfe-132">若要创建新变量，请使用赋值语句为变量赋值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-132">To create a new variable, use an assignment statement to assign a value to the variable.</span></span> <span data-ttu-id="cedfe-133">不需要在使用变量之前先对其进行声明。</span><span class="sxs-lookup"><span data-stu-id="cedfe-133">You don't have to declare the variable before using it.</span></span> <span data-ttu-id="cedfe-134">所有变量的默认值为 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-134">The default value of all variables is `$null`.</span></span>

<span data-ttu-id="cedfe-135">若要获取 PowerShell 会话中所有变量的列表，请键入 `Get-Variable` 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-135">To get a list of all the variables in your PowerShell session, type `Get-Variable`.</span></span> <span data-ttu-id="cedfe-136">将显示变量名称，其中不含前面的货币 (`$` 用于引用变量的) 符号。</span><span class="sxs-lookup"><span data-stu-id="cedfe-136">The variable names are displayed without the preceding dollar (`$`) sign that is used to reference variables.</span></span>

<span data-ttu-id="cedfe-137">例如：</span><span class="sxs-lookup"><span data-stu-id="cedfe-137">For example:</span></span>

```powershell
$MyVariable = 1, 2, 3

$Path = "C:\Windows\System32"
```

<span data-ttu-id="cedfe-138">变量用于存储命令的结果。</span><span class="sxs-lookup"><span data-stu-id="cedfe-138">Variables are useful for storing the results of commands.</span></span>

<span data-ttu-id="cedfe-139">例如：</span><span class="sxs-lookup"><span data-stu-id="cedfe-139">For example:</span></span>

```powershell
$Processes = Get-Process

$Today = (Get-Date).DateTime
```

<span data-ttu-id="cedfe-140">若要显示变量的值，请键入变量名称，其前面带有美元符号 (`$`) 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-140">To display the value of a variable, type the variable name, preceded by a dollar sign (`$`).</span></span>

<span data-ttu-id="cedfe-141">例如：</span><span class="sxs-lookup"><span data-stu-id="cedfe-141">For example:</span></span>

```powershell
$MyVariable
```

```Output
1
2
3
```

```powershell
$Today
```

```Output
Tuesday, September 3, 2019 09:46:46
```

<span data-ttu-id="cedfe-142">若要更改变量的值，请将新值分配给该变量。</span><span class="sxs-lookup"><span data-stu-id="cedfe-142">To change the value of a variable, assign a new value to the variable.</span></span>

<span data-ttu-id="cedfe-143">下面的示例显示变量的值 `$MyVariable` ，更改变量的值，然后显示新值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-143">The following examples display the value of the `$MyVariable` variable, changes the value of the variable, and then displays the new value.</span></span>

```powershell
$MyVariable = 1, 2, 3
$MyVariable
```

```Output
1
2
3
```

```powershell
$MyVariable = "The green cat."
$MyVariable
```

```Output
The green cat.
```

<span data-ttu-id="cedfe-144">若要删除变量的值，请使用 `Clear-Variable` cmdlet 或将值更改为 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-144">To delete the value of a variable, use the `Clear-Variable` cmdlet or change the value to `$null`.</span></span>

```powershell
Clear-Variable -Name MyVariable
```

```powershell
$MyVariable = $null
```

<span data-ttu-id="cedfe-145">若要删除变量，请使用 " [删除变量](xref:Microsoft.PowerShell.Utility.Remove-Variable) " 或 " [删除项](xref:Microsoft.PowerShell.Management.Remove-Item)"。</span><span class="sxs-lookup"><span data-stu-id="cedfe-145">To delete the variable, use [Remove-Variable](xref:Microsoft.PowerShell.Utility.Remove-Variable) or [Remove-Item](xref:Microsoft.PowerShell.Management.Remove-Item).</span></span>

```powershell
Remove-Variable -Name MyVariable
```

```powershell
Remove-Item -Path Variable:\MyVariable
```

## <a name="types-of-variables"></a><span data-ttu-id="cedfe-146">变量类型</span><span class="sxs-lookup"><span data-stu-id="cedfe-146">Types of variables</span></span>

<span data-ttu-id="cedfe-147">可以在变量中存储任何类型的对象，包括整数、字符串、数组和哈希表。</span><span class="sxs-lookup"><span data-stu-id="cedfe-147">You can store any type of object in a variable, including integers, strings, arrays, and hash tables.</span></span> <span data-ttu-id="cedfe-148">和表示进程、服务、事件日志和计算机的对象。</span><span class="sxs-lookup"><span data-stu-id="cedfe-148">And, objects that represent processes, services, event logs, and computers.</span></span>

<span data-ttu-id="cedfe-149">PowerShell 变量是松散类型化的，这意味着它们并不限于特定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="cedfe-149">PowerShell variables are loosely typed, which means that they aren't limited to a particular type of object.</span></span> <span data-ttu-id="cedfe-150">单个变量甚至可以同时包含不同类型的对象的集合或数组。</span><span class="sxs-lookup"><span data-stu-id="cedfe-150">A single variable can even contain a collection, or array, of different types of objects at the same time.</span></span>

<span data-ttu-id="cedfe-151">变量的数据类型由变量值的 .NET 类型决定。</span><span class="sxs-lookup"><span data-stu-id="cedfe-151">The data type of a variable is determined by the .NET types of the values of the variable.</span></span> <span data-ttu-id="cedfe-152">若要查看变量的对象类型，请使用 [Get Member](xref:Microsoft.PowerShell.Utility.Get-Member)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-152">To view a variable's object type, use [Get-Member](xref:Microsoft.PowerShell.Utility.Get-Member).</span></span>

<span data-ttu-id="cedfe-153">例如：</span><span class="sxs-lookup"><span data-stu-id="cedfe-153">For example:</span></span>

```powershell
$a = 12                         # System.Int32
$a = "Word"                     # System.String
$a = 12, "Word"                 # array of System.Int32, System.String
$a = Get-ChildItem C:\Windows   # FileInfo and DirectoryInfo types
```

<span data-ttu-id="cedfe-154">您可以使用类型属性和强制转换表示法来确保变量只能包含特定的对象类型或可转换为该类型的对象。</span><span class="sxs-lookup"><span data-stu-id="cedfe-154">You can use a type attribute and cast notation to ensure that a variable can contain only specific object types or objects that can be converted to that type.</span></span> <span data-ttu-id="cedfe-155">如果尝试分配另一个类型的值，则 PowerShell 会尝试将值转换为其类型。</span><span class="sxs-lookup"><span data-stu-id="cedfe-155">If you try to assign a value of another type, PowerShell tries to convert the value to its type.</span></span> <span data-ttu-id="cedfe-156">如果无法转换类型，赋值语句将失败。</span><span class="sxs-lookup"><span data-stu-id="cedfe-156">If the type can't be converted, the assignment statement fails.</span></span>

<span data-ttu-id="cedfe-157">若要使用强制转换表示法，请在赋值语句左侧)  (的变量名称之前输入类型名称（括在括号中）。</span><span class="sxs-lookup"><span data-stu-id="cedfe-157">To use cast notation, enter a type name, enclosed in brackets, before the variable name (on the left side of the assignment statement).</span></span> <span data-ttu-id="cedfe-158">下面的示例创建一个 `$number` 变量，该变量只能包含整数、只能包含字符串的变量 `$words` ，以及只能 `$dates` 包含 **DateTime** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cedfe-158">The following example creates a `$number` variable that can contain only integers, a `$words` variable that can contain only strings, and a `$dates` variable that can contain only **DateTime** objects.</span></span>

```powershell
[int]$number = 8
$number = "12345"  # The string is converted to an integer.
$number = "Hello"
```

```Output
Cannot convert value "Hello" to type "System.Int32". Error: "Input string was
 not in a correct format."
At line:1 char:1
+ $number = "Hello"
+ ~~~~~~~~~~~~~~~~~
+ CategoryInfo          : MetadataError: (:) [],
    ArgumentTransformationMetadataException
+ FullyQualifiedErrorId : RuntimeException
```

```powershell
[string]$words = "Hello"
$words = 2       # The integer is converted to a string.
$words += 10     # The plus (+) sign concatenates the strings.
$words
```

```Output
210
```

```powershell
[datetime] $dates = "09/12/91"  # The string is converted to a DateTime object.
$dates
```

```Output
Thursday, September 12, 1991 00:00:00
```

```powershell
$dates = 10    # The integer is converted to a DateTime object.
$dates
```

```Output
Monday, January 1, 0001 00:00:00
```

## <a name="using-variables-in-commands-and-expressions"></a><span data-ttu-id="cedfe-159">在命令和表达式中使用变量</span><span class="sxs-lookup"><span data-stu-id="cedfe-159">Using variables in commands and expressions</span></span>

<span data-ttu-id="cedfe-160">若要在命令或表达式中使用变量，请键入变量名称，前面加上美元 (`$`) 符号。</span><span class="sxs-lookup"><span data-stu-id="cedfe-160">To use a variable in a command or expression, type the variable name, preceded by the dollar (`$`) sign.</span></span>

<span data-ttu-id="cedfe-161">如果变量名和美元符号没有用引号引起来，或者它们括在双引号 (`"`) 标记中，则在命令或表达式中使用该变量的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-161">If the variable name and dollar sign aren't enclosed in quotation marks, or if they're enclosed in double quotation (`"`) marks, the value of the variable is used in the command or expression.</span></span>

<span data-ttu-id="cedfe-162">如果变量名和美元符号用单引号引起 (`'`) 标记，则在表达式中使用变量名。</span><span class="sxs-lookup"><span data-stu-id="cedfe-162">If the variable name and dollar sign are enclosed in single quotation (`'`) marks, the variable name is used in the expression.</span></span>

<span data-ttu-id="cedfe-163">有关在 PowerShell 中使用引号的详细信息，请参阅 [about_Quoting_Rules](about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-163">For more information about using quotation marks in PowerShell, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="cedfe-164">此示例获取变量的值 `$PROFILE` ，它是 powershell 控制台中 powershell 用户配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="cedfe-164">This example gets the value of the `$PROFILE` variable, which is the path to the PowerShell user profile file in the PowerShell console.</span></span>

```powershell
$PROFILE
```

```Output
C:\Users\User01\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
```

<span data-ttu-id="cedfe-165">在此示例中，显示了两个命令，可在 **notepad.exe** 中打开 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="cedfe-165">In this example, two commands are shown that can open the PowerShell profile in **notepad.exe** .</span></span> <span data-ttu-id="cedfe-166">带有双引号 () 标记的示例 `"` 使用变量的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-166">The example with double-quote (`"`) marks uses the variable's value.</span></span>

```powershell
notepad $PROFILE

notepad "$PROFILE"
```

<span data-ttu-id="cedfe-167">下面的示例使用单引号 (将 `'` 变量视为文本的) 标记。</span><span class="sxs-lookup"><span data-stu-id="cedfe-167">The following examples use single-quote (`'`) marks that treat the variable as literal text.</span></span>

```powershell
'$PROFILE'
```

```Output
$PROFILE
```

```powershell
'Use the $PROFILE variable.'
```

```Output
Use the $PROFILE variable.
```

## <a name="variable-names-that-include-special-characters"></a><span data-ttu-id="cedfe-168">包含特殊字符的变量名称</span><span class="sxs-lookup"><span data-stu-id="cedfe-168">Variable names that include special characters</span></span>

<span data-ttu-id="cedfe-169">变量名称以美元 (`$`) 符号开头，可以包含字母数字字符和特殊字符。</span><span class="sxs-lookup"><span data-stu-id="cedfe-169">Variable names begin with a dollar (`$`) sign and can include alphanumeric characters and special characters.</span></span> <span data-ttu-id="cedfe-170">变量名称长度仅受可用内存的限制。</span><span class="sxs-lookup"><span data-stu-id="cedfe-170">The variable name length is limited only by available memory.</span></span>

<span data-ttu-id="cedfe-171">最佳做法是，变量名称只能包含字母数字字符和下划线 (`_`) 字符。</span><span class="sxs-lookup"><span data-stu-id="cedfe-171">The best practice is that variable names include only alphanumeric characters and the underscore (`_`) character.</span></span> <span data-ttu-id="cedfe-172">包含空格和其他特殊字符的变量名称难以使用，应避免使用。</span><span class="sxs-lookup"><span data-stu-id="cedfe-172">Variable names that include spaces and other special characters, are difficult to use and should be avoided.</span></span>

<span data-ttu-id="cedfe-173">字母数字变量名可以包含以下字符：</span><span class="sxs-lookup"><span data-stu-id="cedfe-173">Alphanumeric variable names can contain these characters:</span></span>

- <span data-ttu-id="cedfe-174">这些类别中的 Unicode 字符： **Lu** 、 **Ll** 、 **Lt** 、 **Lm** 、 **Lo** 或 **Nd** 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-174">Unicode characters from these categories: **Lu** , **Ll** , **Lt** , **Lm** , **Lo** , or **Nd** .</span></span>
- <span data-ttu-id="cedfe-175">下划线 (`_`) 字符。</span><span class="sxs-lookup"><span data-stu-id="cedfe-175">Underscore (`_`) character.</span></span>
- <span data-ttu-id="cedfe-176">问号 (`?`) 字符。</span><span class="sxs-lookup"><span data-stu-id="cedfe-176">Question mark (`?`) character.</span></span>

<span data-ttu-id="cedfe-177">下面的列表包含 Unicode 类别说明。</span><span class="sxs-lookup"><span data-stu-id="cedfe-177">The following list contains the Unicode category descriptions.</span></span> <span data-ttu-id="cedfe-178">有关详细信息，请参阅 [system.globalization.unicodecategory](/dotnet/api/system.globalization.unicodecategory)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-178">For more information, see [UnicodeCategory](/dotnet/api/system.globalization.unicodecategory).</span></span>

- <span data-ttu-id="cedfe-179">**Lu** -UppercaseLetter</span><span class="sxs-lookup"><span data-stu-id="cedfe-179">**Lu** - UppercaseLetter</span></span>
- <span data-ttu-id="cedfe-180">**Ll** -LowercaseLetter</span><span class="sxs-lookup"><span data-stu-id="cedfe-180">**Ll** - LowercaseLetter</span></span>
- <span data-ttu-id="cedfe-181">**Lt** -TitlecaseLetter</span><span class="sxs-lookup"><span data-stu-id="cedfe-181">**Lt** - TitlecaseLetter</span></span>
- <span data-ttu-id="cedfe-182">**Lm** -ModifierLetter</span><span class="sxs-lookup"><span data-stu-id="cedfe-182">**Lm** - ModifierLetter</span></span>
- <span data-ttu-id="cedfe-183">**Lo** -OtherLetter</span><span class="sxs-lookup"><span data-stu-id="cedfe-183">**Lo** - OtherLetter</span></span>
- <span data-ttu-id="cedfe-184">**Nd** -DecimalDigitNumber</span><span class="sxs-lookup"><span data-stu-id="cedfe-184">**Nd** - DecimalDigitNumber</span></span>

<span data-ttu-id="cedfe-185">若要创建或显示包含空格或特殊字符的变量名称，请使用大括号将该变量名称括 (`{}`) 字符。</span><span class="sxs-lookup"><span data-stu-id="cedfe-185">To create or display a variable name that includes spaces or special characters, enclose the variable name with the curly braces (`{}`) characters.</span></span>
<span data-ttu-id="cedfe-186">大括号直接 PowerShell 将变量名称的字符解释为文本。</span><span class="sxs-lookup"><span data-stu-id="cedfe-186">The curly braces direct PowerShell to interpret the variable name's characters as literals.</span></span>

<span data-ttu-id="cedfe-187">特殊字符变量名称可以包含以下字符：</span><span class="sxs-lookup"><span data-stu-id="cedfe-187">Special character variable names can contain these characters:</span></span>

- <span data-ttu-id="cedfe-188">任何 Unicode 字符，但以下情况除外：</span><span class="sxs-lookup"><span data-stu-id="cedfe-188">Any Unicode character, with the following exceptions:</span></span>
  - <span data-ttu-id="cedfe-189">右大括号 (`}`) 字符 (U + 007D) 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-189">The closing curly brace (`}`) character (U+007D).</span></span>
  - <span data-ttu-id="cedfe-190">反撇号 (`` ` ``) 字符 (U + 0060) 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-190">The backtick (`` ` ``) character (U+0060).</span></span> <span data-ttu-id="cedfe-191">反撇号用于对 Unicode 字符进行转义，以使它们被视为文本。</span><span class="sxs-lookup"><span data-stu-id="cedfe-191">The backtick is used to escape Unicode characters so they're treated as literals.</span></span>

<span data-ttu-id="cedfe-192">PowerShell 包含 `$$` `$?` `$^` `$_` 包含字母数字字符和特殊字符的保留变量，如、、和。</span><span class="sxs-lookup"><span data-stu-id="cedfe-192">PowerShell has reserved variables such as `$$`, `$?`, `$^`, and `$_` that contain alphanumeric and special characters.</span></span> <span data-ttu-id="cedfe-193">有关详细信息，请参阅 [about_Automatic_Variables](about_automatic_variables.md)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-193">For more information, see [about_Automatic_Variables](about_automatic_variables.md).</span></span>

<span data-ttu-id="cedfe-194">例如，以下命令将创建名为的变量 `save-items` 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-194">For example, the following command creates the variable named `save-items`.</span></span> <span data-ttu-id="cedfe-195">需要大括号 (`{}`) ，因为变量名称包含连字符 (`-`) 特殊字符。</span><span class="sxs-lookup"><span data-stu-id="cedfe-195">The curly braces (`{}`) are needed because variable name includes a hyphen (`-`) special character.</span></span>

```powershell
${save-items} = "a", "b", "c"
${save-items}
```

```Output
a
b
c
```

<span data-ttu-id="cedfe-196">以下命令将获取由环境变量表示的目录中的子项目 `ProgramFiles(x86)` 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-196">The following command gets the child items in the directory that is represented by the `ProgramFiles(x86)` environment variable.</span></span>

```powershell
Get-ChildItem ${env:ProgramFiles(x86)}
```

<span data-ttu-id="cedfe-197">若要引用包含大括号的变量名，请将变量名称括在大括号中，并使用反撇号字符来转义大括号。</span><span class="sxs-lookup"><span data-stu-id="cedfe-197">To reference a variable name that includes braces, enclose the variable name in braces, and use the backtick character to escape the braces.</span></span> <span data-ttu-id="cedfe-198">例如，若要创建名为 type 的变量 `this{value}is` ：</span><span class="sxs-lookup"><span data-stu-id="cedfe-198">For example, to create a variable named `this{value}is` type:</span></span>

```powershell
${this`{value`}is} = "This variable name uses braces and backticks."
${this`{value`}is}
```

```Output
This variable name uses braces and backticks.
```

## <a name="variables-and-scope"></a><span data-ttu-id="cedfe-199">变量和范围</span><span class="sxs-lookup"><span data-stu-id="cedfe-199">Variables and scope</span></span>

<span data-ttu-id="cedfe-200">默认情况下，变量仅在创建它们的范围内可用。</span><span class="sxs-lookup"><span data-stu-id="cedfe-200">By default, variables are only available in the scope in which they're created.</span></span>

<span data-ttu-id="cedfe-201">例如，在函数中创建的变量仅在函数内可用。</span><span class="sxs-lookup"><span data-stu-id="cedfe-201">For example, a variable that you create in a function is available only within the function.</span></span> <span data-ttu-id="cedfe-202">在脚本中创建的变量仅在脚本内可用。</span><span class="sxs-lookup"><span data-stu-id="cedfe-202">A variable that you create in a script is available only within the script.</span></span> <span data-ttu-id="cedfe-203">如果脚本为点，则将变量添加到当前作用域。</span><span class="sxs-lookup"><span data-stu-id="cedfe-203">If you dot-source the script, the variable is added to the current scope.</span></span> <span data-ttu-id="cedfe-204">有关详细信息，请参阅 [about_Scopes](about_Scopes.md)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-204">For more information, see [about_Scopes](about_Scopes.md).</span></span>

<span data-ttu-id="cedfe-205">您可以使用作用域修饰符来更改变量的默认作用域。</span><span class="sxs-lookup"><span data-stu-id="cedfe-205">You can use a scope modifier to change the default scope of the variable.</span></span> <span data-ttu-id="cedfe-206">下面的表达式创建一个名为的变量 `Computers` 。</span><span class="sxs-lookup"><span data-stu-id="cedfe-206">The following expression creates a variable named `Computers`.</span></span> <span data-ttu-id="cedfe-207">尽管变量是在脚本或函数中创建的，但它也具有全局作用域。</span><span class="sxs-lookup"><span data-stu-id="cedfe-207">The variable has a global scope, even when it's created in a script or function.</span></span>

```powershell
$Global:Computers = "Server01"
```

<span data-ttu-id="cedfe-208">对于任何执行进程外的脚本或命令，都需要 `Using` 范围修饰符来嵌入调用会话范围内的变量值，以便使会话代码不能访问它们。</span><span class="sxs-lookup"><span data-stu-id="cedfe-208">For any script or command that executes out of session, you need the `Using` scope modifier to embed variable values from the calling session scope, so that out of session code can access them.</span></span>

<span data-ttu-id="cedfe-209">有关详细信息，请参阅 [about_Remote_Variables](about_Remote_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-209">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="saving-variables"></a><span data-ttu-id="cedfe-210">保存变量</span><span class="sxs-lookup"><span data-stu-id="cedfe-210">Saving variables</span></span>

<span data-ttu-id="cedfe-211">你创建的变量仅在创建它们的会话中可用。</span><span class="sxs-lookup"><span data-stu-id="cedfe-211">Variables that you create are available only in the session in which you create them.</span></span> <span data-ttu-id="cedfe-212">关闭会话时，它们会丢失。</span><span class="sxs-lookup"><span data-stu-id="cedfe-212">They're lost when you close your session.</span></span>

<span data-ttu-id="cedfe-213">若要在启动的每个 PowerShell 会话中创建变量，请将变量添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="cedfe-213">To create the variable in every PowerShell session that you start, add the variable to your PowerShell profile.</span></span>

<span data-ttu-id="cedfe-214">例如，若要 `$VerbosePreference` 在每个 powershell 会话中更改变量的值，请将以下命令添加到 powershell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="cedfe-214">For example, to change the value of the `$VerbosePreference` variable in every PowerShell session, add the following command to your PowerShell profile.</span></span>

```powershell
$VerbosePreference = "Continue"
```

<span data-ttu-id="cedfe-215">可以通过 `$PROFILE` 在文本编辑器中打开文件（如 **notepad.exe** ），将此命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="cedfe-215">You can add this command to your PowerShell profile by opening the `$PROFILE` file in a text editor, such as **notepad.exe** .</span></span> <span data-ttu-id="cedfe-216">有关 PowerShell 配置文件的详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="cedfe-216">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="the-variable-drive"></a><span data-ttu-id="cedfe-217">变量：驱动器</span><span class="sxs-lookup"><span data-stu-id="cedfe-217">The Variable: drive</span></span>

<span data-ttu-id="cedfe-218">PowerShell 变量提供程序创建的 `Variable:` 驱动器的外观和行为类似于文件系统驱动器，但它包含会话中的变量及其值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-218">The PowerShell Variable provider creates a `Variable:` drive that looks and acts like a file system drive, but it contains the variables in your session and their values.</span></span>

<span data-ttu-id="cedfe-219">若要切换到 `Variable:` 驱动器，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="cedfe-219">To change to the `Variable:` drive, use the following command:</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="cedfe-220">若要列出驱动器中的项和变量 `Variable:` ，请使用 `Get-Item` 或 `Get-ChildItem` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cedfe-220">To list the items and variables in the `Variable:` drive, use the `Get-Item` or `Get-ChildItem` cmdlets.</span></span>

```powershell
Get-ChildItem Variable:
```

<span data-ttu-id="cedfe-221">若要获取特定变量的值，请使用文件系统表示法指定驱动器名称和变量名称。</span><span class="sxs-lookup"><span data-stu-id="cedfe-221">To get the value of a particular variable, use file system notation to specify the name of the drive and the name of the variable.</span></span> <span data-ttu-id="cedfe-222">例如，若要获取 `$PSCulture` 自动变量，请使用以下命令。</span><span class="sxs-lookup"><span data-stu-id="cedfe-222">For example, to get the `$PSCulture` automatic variable, use the following command.</span></span>

```powershell
Get-Item Variable:\PSCulture
```

```Output
Name                           Value
----                           -----
PSCulture                      en-US
```

<span data-ttu-id="cedfe-223">若要显示有关 `Variable:` 驱动器和 PowerShell Variable 提供程序的详细信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="cedfe-223">To display more information about the `Variable:` drive and the PowerShell Variable provider, type:</span></span>

```powershell
Get-Help Variable
```

## <a name="variable-syntax-with-provider-paths"></a><span data-ttu-id="cedfe-224">具有提供程序路径的变量语法</span><span class="sxs-lookup"><span data-stu-id="cedfe-224">Variable syntax with provider paths</span></span>

<span data-ttu-id="cedfe-225">你可以为提供程序路径加上前缀 (`$`) 符号，并访问实现 [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) 接口的任何提供程序的内容。</span><span class="sxs-lookup"><span data-stu-id="cedfe-225">You can prefix a provider path with the dollar (`$`) sign, and access the content of any provider that implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>

<span data-ttu-id="cedfe-226">以下内置 PowerShell 提供程序支持此表示法：</span><span class="sxs-lookup"><span data-stu-id="cedfe-226">The following built-in PowerShell providers support this notation:</span></span>

- [<span data-ttu-id="cedfe-227">about_Environment_Provider</span><span class="sxs-lookup"><span data-stu-id="cedfe-227">about_Environment_Provider</span></span>](about_Environment_Provider.md)
- [<span data-ttu-id="cedfe-228">about_Variable_Provider</span><span class="sxs-lookup"><span data-stu-id="cedfe-228">about_Variable_Provider</span></span>](about_Variable_Provider.md)
- [<span data-ttu-id="cedfe-229">about_Function_Provider</span><span class="sxs-lookup"><span data-stu-id="cedfe-229">about_Function_Provider</span></span>](about_Function_Provider.md)
- [<span data-ttu-id="cedfe-230">about_Alias_Provider</span><span class="sxs-lookup"><span data-stu-id="cedfe-230">about_Alias_Provider</span></span>](about_Alias_Provider.md)

## <a name="the-variable-cmdlets"></a><span data-ttu-id="cedfe-231">变量 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cedfe-231">The variable cmdlets</span></span>

<span data-ttu-id="cedfe-232">PowerShell 包括一组旨在管理变量的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cedfe-232">PowerShell includes a set of cmdlets that are designed to manage variables.</span></span>

<span data-ttu-id="cedfe-233">若要列出这些 cmdlet，请键入：</span><span class="sxs-lookup"><span data-stu-id="cedfe-233">To list the cmdlets, type:</span></span>

```powershell
Get-Command -Noun Variable
```

<span data-ttu-id="cedfe-234">若要获取特定 cmdlet 的帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="cedfe-234">To get help for a specific cmdlet, type:</span></span>

```powershell
Get-Help <cmdlet-name>
```

| <span data-ttu-id="cedfe-235">Cmdlet 名称</span><span class="sxs-lookup"><span data-stu-id="cedfe-235">Cmdlet Name</span></span>       | <span data-ttu-id="cedfe-236">说明</span><span class="sxs-lookup"><span data-stu-id="cedfe-236">Description</span></span>                                |
| ---------------   | ------------------------------------------ |
| `Clear-Variable`  | <span data-ttu-id="cedfe-237">删除变量的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-237">Deletes the value of a variable.</span></span>           |
| `Get-Variable`    | <span data-ttu-id="cedfe-238">获取当前控制台中的变量。</span><span class="sxs-lookup"><span data-stu-id="cedfe-238">Gets the variables in the current console.</span></span> |
| `New-Variable`    | <span data-ttu-id="cedfe-239">创建新变量。</span><span class="sxs-lookup"><span data-stu-id="cedfe-239">Creates a new variable.</span></span>                    |
| `Remove-Variable` | <span data-ttu-id="cedfe-240">删除变量及其值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-240">Deletes a variable and its value.</span></span>          |
| `Set-Variable`    | <span data-ttu-id="cedfe-241">更改变量的值。</span><span class="sxs-lookup"><span data-stu-id="cedfe-241">Changes the value of a variable.</span></span>           |

## <a name="see-also"></a><span data-ttu-id="cedfe-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cedfe-242">See also</span></span>

[<span data-ttu-id="cedfe-243">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="cedfe-243">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="cedfe-244">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="cedfe-244">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="cedfe-245">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="cedfe-245">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="cedfe-246">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="cedfe-246">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="cedfe-247">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="cedfe-247">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="cedfe-248">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="cedfe-248">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="cedfe-249">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="cedfe-249">about_Remote_Variables</span></span>](about_Remote_Variables.md)
