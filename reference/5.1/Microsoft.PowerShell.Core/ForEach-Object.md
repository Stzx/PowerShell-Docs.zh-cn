---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ForEach-Object
ms.openlocfilehash: 327add884077083d37e1f58ab8f78b784a870362
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "93199400"
---
# <span data-ttu-id="98397-103">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="98397-103">ForEach-Object</span></span>

## <span data-ttu-id="98397-104">摘要</span><span class="sxs-lookup"><span data-stu-id="98397-104">Synopsis</span></span>
<span data-ttu-id="98397-105">针对输入对象集合中的每个项执行操作。</span><span class="sxs-lookup"><span data-stu-id="98397-105">Performs an operation against each item in a collection of input objects.</span></span>

## <span data-ttu-id="98397-106">语法</span><span class="sxs-lookup"><span data-stu-id="98397-106">Syntax</span></span>

### <span data-ttu-id="98397-107">ScriptBlockSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="98397-107">ScriptBlockSet (Default)</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-Begin <ScriptBlock>] [-Process] <ScriptBlock[]>
 [-End <ScriptBlock>] [-RemainingScripts <ScriptBlock[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="98397-108">PropertyAndMethodSet</span><span class="sxs-lookup"><span data-stu-id="98397-108">PropertyAndMethodSet</span></span>

```
ForEach-Object [-InputObject <PSObject>] [-MemberName] <String> [-ArgumentList <Object[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="98397-109">说明</span><span class="sxs-lookup"><span data-stu-id="98397-109">Description</span></span>

<span data-ttu-id="98397-110">`ForEach-Object`Cmdlet 对输入对象集合中的每个项执行操作。</span><span class="sxs-lookup"><span data-stu-id="98397-110">The `ForEach-Object` cmdlet performs an operation on each item in a collection of input objects.</span></span> <span data-ttu-id="98397-111">可以通过管道将输入对象传递给 cmdlet，或使用 **InputObject** 参数指定。</span><span class="sxs-lookup"><span data-stu-id="98397-111">The input objects can be piped to the cmdlet or specified by using the **InputObject** parameter.</span></span>

<span data-ttu-id="98397-112">从 Windows PowerShell 3.0 开始，可以使用两种不同的方法来构造 `ForEach-Object` 命令。</span><span class="sxs-lookup"><span data-stu-id="98397-112">Starting in Windows PowerShell 3.0, there are two different ways to construct a `ForEach-Object` command.</span></span>

- <span data-ttu-id="98397-113">**脚本块** 。</span><span class="sxs-lookup"><span data-stu-id="98397-113">**Script block** .</span></span> <span data-ttu-id="98397-114">你可以使用某个脚本块来指定操作。</span><span class="sxs-lookup"><span data-stu-id="98397-114">You can use a script block to specify the operation.</span></span> <span data-ttu-id="98397-115">在脚本块中，使用 `$_` 变量来表示当前对象。</span><span class="sxs-lookup"><span data-stu-id="98397-115">Within the script block, use the `$_` variable to represent the current object.</span></span> <span data-ttu-id="98397-116">脚本块是 **Process** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="98397-116">The script block is the value of the **Process** parameter.</span></span> <span data-ttu-id="98397-117">脚本块可以包含任何 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="98397-117">The script block can contain any PowerShell script.</span></span>

  <span data-ttu-id="98397-118">例如，以下命令将获取计算机上每个进程的 **ProcessName** 属性值。</span><span class="sxs-lookup"><span data-stu-id="98397-118">For example, the following command gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object {$_.ProcessName}`

  <span data-ttu-id="98397-119">`ForEach-Object` 支持 `begin` 、 `process` 和块， `end` 如 [about_functions](about/about_functions.md#piping-objects-to-functions)中所述。</span><span class="sxs-lookup"><span data-stu-id="98397-119">`ForEach-Object` supports the `begin`, `process`, and `end` blocks as described in [about_functions](about/about_functions.md#piping-objects-to-functions).</span></span>

  > [!NOTE]
  > <span data-ttu-id="98397-120">脚本块在调用方的作用域中运行。</span><span class="sxs-lookup"><span data-stu-id="98397-120">The script blocks run in the caller's scope.</span></span> <span data-ttu-id="98397-121">因此，这些块有权访问该范围内的变量，并且可以创建在 cmdlet 完成后在该范围内持久保留的新变量。</span><span class="sxs-lookup"><span data-stu-id="98397-121">Therefore the blocks have access to variables in that scope and can create new variables that persist in that scope after the cmdlet completes.</span></span>

- <span data-ttu-id="98397-122">**操作语句** 。</span><span class="sxs-lookup"><span data-stu-id="98397-122">**Operation statement** .</span></span> <span data-ttu-id="98397-123">你还可以编写操作语句，它更像自然语言。</span><span class="sxs-lookup"><span data-stu-id="98397-123">You can also write an operation statement, which is much more like natural language.</span></span> <span data-ttu-id="98397-124">你可以使用该操作语句来指定属性值或调用方法。</span><span class="sxs-lookup"><span data-stu-id="98397-124">You can use the operation statement to specify a property value or call a method.</span></span> <span data-ttu-id="98397-125">Windows PowerShell 3.0 中引入了操作语句。</span><span class="sxs-lookup"><span data-stu-id="98397-125">Operation statements were introduced in Windows PowerShell 3.0.</span></span>

  <span data-ttu-id="98397-126">例如，以下命令还将获取计算机上每个进程的 **ProcessName** 属性值。</span><span class="sxs-lookup"><span data-stu-id="98397-126">For example, the following command also gets the value of the **ProcessName** property of each process on the computer.</span></span>

  `Get-Process | ForEach-Object ProcessName`

## <span data-ttu-id="98397-127">示例</span><span class="sxs-lookup"><span data-stu-id="98397-127">Examples</span></span>

### <span data-ttu-id="98397-128">示例1：分割数组中的整数</span><span class="sxs-lookup"><span data-stu-id="98397-128">Example 1: Divide integers in an array</span></span>

<span data-ttu-id="98397-129">此示例使用一个包含三个整数的数组，并将每个整数除以1024。</span><span class="sxs-lookup"><span data-stu-id="98397-129">This example takes an array of three integers and divides each one of them by 1024.</span></span>

```powershell
30000, 56798, 12432 | ForEach-Object -Process {$_/1024}
```

```Output
29.296875
55.466796875
12.140625
```

### <span data-ttu-id="98397-130">示例2：获取目录中所有文件的长度</span><span class="sxs-lookup"><span data-stu-id="98397-130">Example 2: Get the length of all the files in a directory</span></span>

<span data-ttu-id="98397-131">此示例处理 PowerShell 安装目录中的文件和目录 `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="98397-131">This example processes the files and directories in the PowerShell installation directory `$PSHOME`.</span></span>

```powershell
Get-ChildItem $PSHOME |
  ForEach-Object -Process {if (!$_.PSIsContainer) {$_.Name; $_.Length / 1024; " " }}
```

<span data-ttu-id="98397-132">如果该对象不是一个目录，则脚本块将获取该文件的名称，将其 **Length** 属性的值除以1024，并添加一个空格 ( "" ) 以便将它与下一项隔开。</span><span class="sxs-lookup"><span data-stu-id="98397-132">If the object is not a directory, the script block gets the name of the file, divides the value of its **Length** property by 1024, and adds a space (" ") to separate it from the next entry.</span></span> <span data-ttu-id="98397-133">Cmdlet 使用 **PSISContainer** 属性来确定对象是否为目录。</span><span class="sxs-lookup"><span data-stu-id="98397-133">The cmdlet uses the **PSISContainer** property to determine whether an object is a directory.</span></span>

### <span data-ttu-id="98397-134">示例3：对最新系统事件进行操作</span><span class="sxs-lookup"><span data-stu-id="98397-134">Example 3: Operate on the most recent System events</span></span>

<span data-ttu-id="98397-135">此示例将系统事件日志中的最新1000事件写入文本文件。</span><span class="sxs-lookup"><span data-stu-id="98397-135">This example write the 1000 most recent events from the System event log to a text file.</span></span> <span data-ttu-id="98397-136">当前时间在处理事件之前和之后显示。</span><span class="sxs-lookup"><span data-stu-id="98397-136">The current time is displayed before and after processing the events.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$events | ForEach-Object -Begin {Get-Date} -Process {Out-File -FilePath Events.txt -Append -InputObject $_.Message} -End {Get-Date}
```

<span data-ttu-id="98397-137">`Get-EventLog` 获取系统事件日志中的最新事件1000，并将其存储在 `$Events` 变量中。</span><span class="sxs-lookup"><span data-stu-id="98397-137">`Get-EventLog` gets the 1000 most recent events from the System event log and stores them in the `$Events` variable.</span></span> <span data-ttu-id="98397-138">`$Events` 然后，将管道传递给 `ForEach-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98397-138">`$Events` is then piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="98397-139">**Begin** 参数将显示当前日期和时间。</span><span class="sxs-lookup"><span data-stu-id="98397-139">The **Begin** parameter displays the current date and time.</span></span> <span data-ttu-id="98397-140">接下来， **Process** 参数使用 `Out-File` cmdlet 创建一个名为 events.txt 的文本文件，并将每个事件的消息属性存储在该文件中。</span><span class="sxs-lookup"><span data-stu-id="98397-140">Next, the **Process** parameter uses the `Out-File` cmdlet to create a text file that is named events.txt and stores the message property of each of the events in that file.</span></span> <span data-ttu-id="98397-141">最后，在完成所有处理之后，使用 **End** 参数显示日期和时间。</span><span class="sxs-lookup"><span data-stu-id="98397-141">Last, the **End** parameter is used to display the date and time after all of the processing has completed.</span></span>

### <span data-ttu-id="98397-142">示例4：更改注册表项的值</span><span class="sxs-lookup"><span data-stu-id="98397-142">Example 4: Change the value of a Registry key</span></span>

<span data-ttu-id="98397-143">此示例将 "密钥" 下的所有子项中的 **RemotePath** 注册表项的值更改 `HKCU:\Network` 为大写文本。</span><span class="sxs-lookup"><span data-stu-id="98397-143">This example changes the value of the **RemotePath** registry entry in all of the subkeys under the `HKCU:\Network` key to uppercase text.</span></span>

```powershell
Get-ItemProperty -Path HKCU:\Network\* |
  ForEach-Object {Set-ItemProperty -Path $_.PSPath -Name RemotePath -Value $_.RemotePath.ToUpper();}
```

<span data-ttu-id="98397-144">可以使用此格式更改注册表条目值的形式或内容。</span><span class="sxs-lookup"><span data-stu-id="98397-144">You can use this format to change the form or content of a registry entry value.</span></span>

<span data-ttu-id="98397-145">**Network** 项中的每个子项都表示将在登录时重新连接的映射网络驱动器。</span><span class="sxs-lookup"><span data-stu-id="98397-145">Each subkey in the **Network** key represents a mapped network drive that will reconnect at logon.</span></span>
<span data-ttu-id="98397-146">**RemotePath** 项包含连接的驱动器的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="98397-146">The **RemotePath** entry contains the UNC path of the connected drive.</span></span> <span data-ttu-id="98397-147">例如，如果将 E：驱动器映射到，则 `\\Server\Share` 会有一个 **e** 子项， `HKCU:\Network` 并且 **e** 子项中的 **RemotePath** 注册表项的值为 `\\Server\Share` 。</span><span class="sxs-lookup"><span data-stu-id="98397-147">For example, if you map the E: drive to `\\Server\Share`, there will be an **E** subkey of `HKCU:\Network` and the value of the **RemotePath** registry entry in the **E** subkey is `\\Server\Share`.</span></span>

<span data-ttu-id="98397-148">该命令使用 `Get-ItemProperty` cmdlet 来获取 **网络** 密钥的所有子项，并使用 `Set-ItemProperty` cmdlet 来更改每个密钥中的 **RemotePath** 注册表项的值。</span><span class="sxs-lookup"><span data-stu-id="98397-148">The command uses the `Get-ItemProperty` cmdlet to get all of the subkeys of the **Network** key and the `Set-ItemProperty` cmdlet to change the value of the **RemotePath** registry entry in each key.</span></span>
<span data-ttu-id="98397-149">在 `Set-ItemProperty` 命令中，路径是注册表项的 **PSPath** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="98397-149">In the `Set-ItemProperty` command, the path is the value of the **PSPath** property of the registry key.</span></span> <span data-ttu-id="98397-150">这是表示注册表项的 Microsoft .NET Framework 对象的属性，而不是注册表项。</span><span class="sxs-lookup"><span data-stu-id="98397-150">This is a property of the Microsoft .NET Framework object that represents the registry key, not a registry entry.</span></span> <span data-ttu-id="98397-151">该命令使用 **RemotePath** 值的 **ToUpper ( # B1** 方法，这是 REG_SZ)  (字符串。</span><span class="sxs-lookup"><span data-stu-id="98397-151">The command uses the **ToUpper()** method of the **RemotePath** value, which is a string (REG_SZ).</span></span>

<span data-ttu-id="98397-152">由于 `Set-ItemProperty` 正在更改每个键的属性，因此 `ForEach-Object` 需要使用 cmdlet 来访问属性。</span><span class="sxs-lookup"><span data-stu-id="98397-152">Because `Set-ItemProperty` is changing the property of each key, the `ForEach-Object` cmdlet is required to access the property.</span></span>

### <span data-ttu-id="98397-153">示例5：使用 $Null 自动变量</span><span class="sxs-lookup"><span data-stu-id="98397-153">Example 5: Use the $Null automatic variable</span></span>

<span data-ttu-id="98397-154">此示例演示如何通过管道将 `$Null` 自动变量传递给 `ForEach-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98397-154">This example shows the effect of piping the `$Null` automatic variable to the `ForEach-Object` cmdlet.</span></span>

```powershell
1, 2, $null, 4 | ForEach-Object {"Hello"}
```

```Output
Hello
Hello
Hello
Hello
```

<span data-ttu-id="98397-155">因为 PowerShell 将 null 视为显式占位符，所以该 `ForEach-Object` cmdlet 会生成一个值 `$Null` ，就像对管道传递给它的其他对象一样。</span><span class="sxs-lookup"><span data-stu-id="98397-155">Because PowerShell treats null as an explicit placeholder, the `ForEach-Object` cmdlet generates a value for `$Null`, just as it does for other objects that you pipe to it.</span></span>

### <span data-ttu-id="98397-156">示例6：获取属性值</span><span class="sxs-lookup"><span data-stu-id="98397-156">Example 6: Get property values</span></span>

<span data-ttu-id="98397-157">此示例通过使用 cmdlet 的 **成员名称** 参数获取所有已安装的 PowerShell 模块的 **Path** 属性的值 `ForEach-Object` 。</span><span class="sxs-lookup"><span data-stu-id="98397-157">This example gets the value of the **Path** property of all installed PowerShell modules by using the **MemberName** parameter of the `ForEach-Object` cmdlet.</span></span>

```powershell
Get-Module -ListAvailable | ForEach-Object -MemberName Path
Get-Module -ListAvailable | Foreach Path
```

<span data-ttu-id="98397-158">第二个命令等效于第一个命令。</span><span class="sxs-lookup"><span data-stu-id="98397-158">The second command is equivalent to the first.</span></span> <span data-ttu-id="98397-159">它使用 `Foreach` cmdlet 的别名， `ForEach-Object` 并忽略 **成员** 名称参数的名称，此参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="98397-159">It uses the `Foreach` alias of the `ForEach-Object` cmdlet and omits the name of the **MemberName** parameter, which is optional.</span></span>

<span data-ttu-id="98397-160">`ForEach-Object`Cmdlet 对于获取属性值非常有用，因为它在不更改类型的情况下获取值，而不 **Format** 是更改 `Select-Object` 属性值类型。</span><span class="sxs-lookup"><span data-stu-id="98397-160">The `ForEach-Object` cmdlet is very useful for getting property values, because it gets the value without changing the type, unlike the **Format** cmdlets or the `Select-Object` cmdlet, which change the property value type.</span></span>

### <span data-ttu-id="98397-161">示例7：将模块名称拆分为组件名称</span><span class="sxs-lookup"><span data-stu-id="98397-161">Example 7: Split module names into component names</span></span>

<span data-ttu-id="98397-162">此示例显示了将两个以句点分隔的模块名称拆分为其组件名称的三种方法。</span><span class="sxs-lookup"><span data-stu-id="98397-162">This examples shows three ways to split two dot-separated module names into their component names.</span></span>

```powershell
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object {$_.Split(".")}
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | ForEach-Object -MemberName Split -ArgumentList "."
"Microsoft.PowerShell.Core", "Microsoft.PowerShell.Host" | Foreach Split "."
```

```Output
Microsoft
PowerShell
Core
Microsoft
PowerShell
Host
```

<span data-ttu-id="98397-163">这些命令调用字符串的 **Split** 方法。</span><span class="sxs-lookup"><span data-stu-id="98397-163">The commands call the **Split** method of strings.</span></span> <span data-ttu-id="98397-164">这三个命令使用不同的语法，但它们是等效且可互换的。</span><span class="sxs-lookup"><span data-stu-id="98397-164">The three commands use different syntax, but they are equivalent and interchangeable.</span></span>

<span data-ttu-id="98397-165">第一个命令使用传统语法，包括脚本块和当前的对象运算符 `$_` 。</span><span class="sxs-lookup"><span data-stu-id="98397-165">The first command uses the traditional syntax, which includes a script block and the current object operator `$_`.</span></span> <span data-ttu-id="98397-166">它使用句点语法来指定该方法，并使用括号将分隔符参数括起来。</span><span class="sxs-lookup"><span data-stu-id="98397-166">It uses the dot syntax to specify the method and parentheses to enclose the delimiter argument.</span></span>

<span data-ttu-id="98397-167">第二个命令使用 **MemberName** 参数来指定 **Split** 方法，并使用 **ArgumentName** 参数将句点 (".") 标识为拆分分隔符。</span><span class="sxs-lookup"><span data-stu-id="98397-167">The second command uses the **MemberName** parameter to specify the **Split** method and the **ArgumentName** parameter to identify the dot (".") as the split delimiter.</span></span>

<span data-ttu-id="98397-168">第三个命令使用 cmdlet 的 **Foreach** 别名， `ForEach-Object` 并省略 **成员** 名称和 **ArgumentList** 参数的名称，这些参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="98397-168">The third command uses the **Foreach** alias of the `ForEach-Object` cmdlet and omits the names of the **MemberName** and **ArgumentList** parameters, which are optional.</span></span>

### <span data-ttu-id="98397-169">示例8：将 ForEach-Object 用于两个脚本块</span><span class="sxs-lookup"><span data-stu-id="98397-169">Example 8: Using ForEach-Object with two script blocks</span></span>

<span data-ttu-id="98397-170">在此示例中，我们传递了两个脚本块按位置。</span><span class="sxs-lookup"><span data-stu-id="98397-170">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="98397-171">所有脚本块都绑定到 **Process** 参数。</span><span class="sxs-lookup"><span data-stu-id="98397-171">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="98397-172">但是，它们被视为已传递到 **Begin** 和 **Process** 参数。</span><span class="sxs-lookup"><span data-stu-id="98397-172">However, they are treated as if they had been passed to the **Begin** and **Process** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process' }
```

```Output
begin
process
process
```

### <span data-ttu-id="98397-173">示例9：使用包含两个以上脚本块的 ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="98397-173">Example 9: Using ForEach-Object with more than two script blocks</span></span>

<span data-ttu-id="98397-174">在此示例中，我们传递了两个脚本块按位置。</span><span class="sxs-lookup"><span data-stu-id="98397-174">In this example we pass two script blocks positionally.</span></span> <span data-ttu-id="98397-175">所有脚本块都绑定到 **Process** 参数。</span><span class="sxs-lookup"><span data-stu-id="98397-175">All the script blocks bind to the **Process** parameter.</span></span> <span data-ttu-id="98397-176">但是，它们被视为已传递到 **Begin** 、 **Process** 和 **End** 参数。</span><span class="sxs-lookup"><span data-stu-id="98397-176">However, they are treated as if they had been passed to the **Begin** , **Process** , and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object { 'begin' } { 'process A' }  { 'process B' }  { 'end' }
```

```Output
begin
process A
process B
process A
process B
end
```

> [!NOTE]
> <span data-ttu-id="98397-177">第一个脚本块始终映射到 `begin` 块，最后一个块映射到 `end` 块，中间的块全部映射到 `process` 块。</span><span class="sxs-lookup"><span data-stu-id="98397-177">The first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

### <span data-ttu-id="98397-178">示例10：运行每个管道项的多个脚本块</span><span class="sxs-lookup"><span data-stu-id="98397-178">Example 10: Run multiple script blocks for each pipeline item</span></span>

<span data-ttu-id="98397-179">如前面的示例所示，使用 **Process** 参数传递的多个脚本块将映射到 **Begin** 和 **End** 参数。</span><span class="sxs-lookup"><span data-stu-id="98397-179">As shown in the previous example, multiple script blocks passed using the **Process** parameter get mapped to the **Begin** and **End** parameters.</span></span> <span data-ttu-id="98397-180">若要避免此映射，必须为 **Begin** 和 **End** 参数提供显式值。</span><span class="sxs-lookup"><span data-stu-id="98397-180">To avoid this mapping, you must provide explicit values for the **Begin** and **End** parameters.</span></span>

```powershell
1..2 | ForEach-Object -Begin $null -Process { 'one' }, { 'two' }, { 'three' } -End $null
```

```Output
one
two
three
one
two
three
```

## <span data-ttu-id="98397-181">parameters</span><span class="sxs-lookup"><span data-stu-id="98397-181">Parameters</span></span>

### <span data-ttu-id="98397-182">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="98397-182">-ArgumentList</span></span>

<span data-ttu-id="98397-183">指定方法调用的参数数组。</span><span class="sxs-lookup"><span data-stu-id="98397-183">Specifies an array of arguments to a method call.</span></span> <span data-ttu-id="98397-184">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="98397-184">For more information about the behavior of **ArgumentList** , see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="98397-185">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="98397-185">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: PropertyAndMethodSet
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98397-186">-Begin</span><span class="sxs-lookup"><span data-stu-id="98397-186">-Begin</span></span>

<span data-ttu-id="98397-187">指定在此 cmdlet 处理任何输入对象之前运行的脚本块。</span><span class="sxs-lookup"><span data-stu-id="98397-187">Specifies a script block that runs before this cmdlet processes any input objects.</span></span> <span data-ttu-id="98397-188">此脚本块仅对整个管道运行一次。</span><span class="sxs-lookup"><span data-stu-id="98397-188">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="98397-189">有关块的详细信息 `begin` ，请参阅 [about_Functions](about/about_functions.md#piping-objects-to-functions)。</span><span class="sxs-lookup"><span data-stu-id="98397-189">For more information about the `begin` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98397-190">-End</span><span class="sxs-lookup"><span data-stu-id="98397-190">-End</span></span>

<span data-ttu-id="98397-191">指定在此 cmdlet 处理所有输入对象之后运行的脚本块。</span><span class="sxs-lookup"><span data-stu-id="98397-191">Specifies a script block that runs after this cmdlet processes all input objects.</span></span> <span data-ttu-id="98397-192">此脚本块仅对整个管道运行一次。</span><span class="sxs-lookup"><span data-stu-id="98397-192">This script block is only run once for the entire pipeline.</span></span> <span data-ttu-id="98397-193">有关块的详细信息 `end` ，请参阅 [about_Functions](about/about_functions.md#piping-objects-to-functions)。</span><span class="sxs-lookup"><span data-stu-id="98397-193">For more information about the `end` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98397-194">-InputObject</span><span class="sxs-lookup"><span data-stu-id="98397-194">-InputObject</span></span>

<span data-ttu-id="98397-195">指定输入对象。</span><span class="sxs-lookup"><span data-stu-id="98397-195">Specifies the input objects.</span></span> <span data-ttu-id="98397-196">`ForEach-Object` 在每个输入对象上运行脚本块或操作语句。</span><span class="sxs-lookup"><span data-stu-id="98397-196">`ForEach-Object` runs the script block or operation statement on each input object.</span></span> <span data-ttu-id="98397-197">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="98397-197">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

<span data-ttu-id="98397-198">当你将 **inputobject** 参数与一起使用时 `ForEach-Object` ， `ForEach-Object` **inputobject** 值将被视为单个对象，而不是管道将命令结果传递给。</span><span class="sxs-lookup"><span data-stu-id="98397-198">When you use the **InputObject** parameter with `ForEach-Object`, instead of piping command results to `ForEach-Object`, the **InputObject** value is treated as a single object.</span></span> <span data-ttu-id="98397-199">即使该值是作为命令结果的集合（如），也是如此 `-InputObject (Get-Process)` 。</span><span class="sxs-lookup"><span data-stu-id="98397-199">This is true even if the value is a collection that is the result of a command, such as `-InputObject (Get-Process)`.</span></span>
<span data-ttu-id="98397-200">由于 **InputObject** 无法从数组或对象的集合返回各个属性，因此，如果您使用在 `ForEach-Object` 已定义的属性中具有特定值的那些对象的对象集合上执行操作，则建议您 `ForEach-Object` 在管道中使用，如本主题的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="98397-200">Because **InputObject** cannot return individual properties from an array or collection of objects, we recommend that if you use `ForEach-Object` to perform operations on a collection of objects for those objects that have specific values in defined properties, you use `ForEach-Object` in the pipeline, as shown in the examples in this topic.</span></span>

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

### <span data-ttu-id="98397-201">-MemberName</span><span class="sxs-lookup"><span data-stu-id="98397-201">-MemberName</span></span>

<span data-ttu-id="98397-202">指定要获取的属性或要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="98397-202">Specifies the property to get or the method to call.</span></span>

<span data-ttu-id="98397-203">允许使用通配符，但仅在生成的字符串解析为唯一值时才有效。</span><span class="sxs-lookup"><span data-stu-id="98397-203">Wildcard characters are permitted, but work only if the resulting string resolves to a unique value.</span></span>
<span data-ttu-id="98397-204">例如，如果运行的 `Get-Process | ForEach -MemberName *Name` 是，并且存在多个具有包含字符串名称（如 **ProcessName** 和 **name** 属性）的名称的成员，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="98397-204">If, for example, you run `Get-Process | ForEach -MemberName *Name`, and more than one member exists with a name that contains the string Name, such as the **ProcessName** and **Name** properties, the command fails.</span></span>

<span data-ttu-id="98397-205">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="98397-205">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: PropertyAndMethodSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="98397-206">-Process</span><span class="sxs-lookup"><span data-stu-id="98397-206">-Process</span></span>

<span data-ttu-id="98397-207">指定对每个输入对象所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="98397-207">Specifies the operation that is performed on each input object.</span></span> <span data-ttu-id="98397-208">为管道中的每个对象运行此脚本块。</span><span class="sxs-lookup"><span data-stu-id="98397-208">This script block is run for every object in the pipeline.</span></span> <span data-ttu-id="98397-209">有关块的详细信息 `process` ，请参阅 [about_Functions](about/about_functions.md#piping-objects-to-functions)。</span><span class="sxs-lookup"><span data-stu-id="98397-209">For more information about the `process` block, see [about_Functions](about/about_functions.md#piping-objects-to-functions).</span></span>

<span data-ttu-id="98397-210">向 **Process** 参数提供多个脚本块时，第一个脚本块将始终映射到 `begin` 块。</span><span class="sxs-lookup"><span data-stu-id="98397-210">When you provide multiple script blocks to the **Process** parameter, the first script block is always mapped to the `begin` block.</span></span> <span data-ttu-id="98397-211">如果只有两个脚本块，则第二个块映射到 `process` 块。</span><span class="sxs-lookup"><span data-stu-id="98397-211">If there are only two script blocks, the second block is mapped to the `process` block.</span></span> <span data-ttu-id="98397-212">如果有三个或更多脚本块，则第一个脚本块始终映射到 `begin` 块，最后一个块映射到块 `end` ，而介于之间的块全部映射到 `process` 块。</span><span class="sxs-lookup"><span data-stu-id="98397-212">If there are three or more script blocks, first script block is always mapped to the `begin` block, the last block is mapped to the `end` block, and the blocks in between are all mapped to the `process` block.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98397-213">-RemainingScripts</span><span class="sxs-lookup"><span data-stu-id="98397-213">-RemainingScripts</span></span>

<span data-ttu-id="98397-214">指定 **进程** 参数不会使用的所有脚本块。</span><span class="sxs-lookup"><span data-stu-id="98397-214">Specifies all script blocks that are not taken by the **Process** parameter.</span></span>

<span data-ttu-id="98397-215">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="98397-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock[]
Parameter Sets: ScriptBlockSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98397-216">-Confirm</span><span class="sxs-lookup"><span data-stu-id="98397-216">-Confirm</span></span>

<span data-ttu-id="98397-217">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="98397-217">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98397-218">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="98397-218">-WhatIf</span></span>

<span data-ttu-id="98397-219">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="98397-219">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="98397-220">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="98397-220">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="98397-221">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="98397-221">CommonParameters</span></span>

<span data-ttu-id="98397-222">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="98397-222">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="98397-223">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="98397-223">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="98397-224">输入</span><span class="sxs-lookup"><span data-stu-id="98397-224">Inputs</span></span>

### <span data-ttu-id="98397-225">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="98397-225">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="98397-226">你可以通过管道将任何对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98397-226">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="98397-227">Outputs</span><span class="sxs-lookup"><span data-stu-id="98397-227">Outputs</span></span>

### <span data-ttu-id="98397-228">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="98397-228">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="98397-229">此 cmdlet 将返回由输入确定的对象。</span><span class="sxs-lookup"><span data-stu-id="98397-229">This cmdlet returns objects that are determined by the input.</span></span>

## <span data-ttu-id="98397-230">注释</span><span class="sxs-lookup"><span data-stu-id="98397-230">Notes</span></span>

- <span data-ttu-id="98397-231">此 `ForEach-Object` cmdlet 的工作方式与 **foreach** 语句非常相似，不同之处在于你不能通过管道将输入传递给 **foreach** 语句。</span><span class="sxs-lookup"><span data-stu-id="98397-231">The `ForEach-Object` cmdlet works much like the **Foreach** statement, except that you cannot pipe input to a **Foreach** statement.</span></span> <span data-ttu-id="98397-232">有关 **Foreach** 语句的详细信息，请参阅 [about_Foreach](./About/about_Foreach.md)。</span><span class="sxs-lookup"><span data-stu-id="98397-232">For more information about the **Foreach** statement, see [about_Foreach](./About/about_Foreach.md).</span></span>

- <span data-ttu-id="98397-233">从 PowerShell 4.0 开始， `Where` `ForEach` 添加了方法以与集合一起使用。</span><span class="sxs-lookup"><span data-stu-id="98397-233">Starting in PowerShell 4.0, `Where` and `ForEach` methods were added for use with collections.</span></span> <span data-ttu-id="98397-234">可在此处阅读有关这些新方法的详细信息 [about_arrays](./About/about_Arrays.md)</span><span class="sxs-lookup"><span data-stu-id="98397-234">You can read more about these new methods here [about_arrays](./About/about_Arrays.md)</span></span>

## <span data-ttu-id="98397-235">相关链接</span><span class="sxs-lookup"><span data-stu-id="98397-235">Related links</span></span>

[<span data-ttu-id="98397-236">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="98397-236">Compare-Object</span></span>](../Microsoft.PowerShell.Utility/Compare-Object.md)

[<span data-ttu-id="98397-237">Where-Object</span><span class="sxs-lookup"><span data-stu-id="98397-237">Where-Object</span></span>](Where-Object.md)

[<span data-ttu-id="98397-238">Group-Object</span><span class="sxs-lookup"><span data-stu-id="98397-238">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="98397-239">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="98397-239">Measure-Object</span></span>](../Microsoft.PowerShell.Utility/Measure-Object.md)

[<span data-ttu-id="98397-240">New-Object</span><span class="sxs-lookup"><span data-stu-id="98397-240">New-Object</span></span>](../Microsoft.PowerShell.Utility/New-Object.md)

[<span data-ttu-id="98397-241">Select-Object</span><span class="sxs-lookup"><span data-stu-id="98397-241">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="98397-242">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="98397-242">Sort-Object</span></span>](../Microsoft.PowerShell.Utility/Sort-Object.md)

[<span data-ttu-id="98397-243">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="98397-243">Tee-Object</span></span>](../Microsoft.PowerShell.Utility/Tee-Object.md)
