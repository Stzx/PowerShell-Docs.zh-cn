---
description: 说明如何将输出从 PowerShell 重定向到文本文件。
keywords: PowerShell，cmdlet
Locale: en-US
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_redirection?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Redirection
ms.openlocfilehash: 59151c31857f12e3a78fd6d292a6a952c312c850
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200509"
---
# <a name="about-redirection"></a><span data-ttu-id="59212-104">关于重定向</span><span class="sxs-lookup"><span data-stu-id="59212-104">About Redirection</span></span>

## <a name="short-description"></a><span data-ttu-id="59212-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="59212-105">Short description</span></span>
<span data-ttu-id="59212-106">说明如何将输出从 PowerShell 重定向到文本文件。</span><span class="sxs-lookup"><span data-stu-id="59212-106">Explains how to redirect output from PowerShell to text files.</span></span>

## <a name="long-description"></a><span data-ttu-id="59212-107">长说明</span><span class="sxs-lookup"><span data-stu-id="59212-107">Long description</span></span>

<span data-ttu-id="59212-108">默认情况下，PowerShell 会将输出发送到 PowerShell 主机。</span><span class="sxs-lookup"><span data-stu-id="59212-108">By default, PowerShell sends output to the PowerShell host.</span></span> <span data-ttu-id="59212-109">通常，这是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="59212-109">Usually this is the console application.</span></span> <span data-ttu-id="59212-110">但是，您可以将输出定向到一个文本文件，您可以将错误输出重定向到常规输出流。</span><span class="sxs-lookup"><span data-stu-id="59212-110">However, you can direct the output to a text file, and you can redirect error output to the regular output stream.</span></span>

<span data-ttu-id="59212-111">您可以使用以下方法来重定向输出：</span><span class="sxs-lookup"><span data-stu-id="59212-111">You can use the following methods to redirect output:</span></span>

- <span data-ttu-id="59212-112">使用 `Out-File` cmdlet，该 cmdlet 将命令输出发送到文本文件。</span><span class="sxs-lookup"><span data-stu-id="59212-112">Use the `Out-File` cmdlet, which sends command output to a text file.</span></span>
  <span data-ttu-id="59212-113">通常， `Out-File` 需要使用 cmdlet （如 `Encoding` 、 `Force` 、 `Width` 或参数）时，请使用 cmdlet `NoClobber` 。</span><span class="sxs-lookup"><span data-stu-id="59212-113">Typically, you use the `Out-File` cmdlet when you need to use its parameters, such as the `Encoding`, `Force`, `Width`, or `NoClobber` parameters.</span></span>

- <span data-ttu-id="59212-114">使用 `Tee-Object` cmdlet，该 cmdlet 将命令输出发送到文本文件，然后将其发送到管道。</span><span class="sxs-lookup"><span data-stu-id="59212-114">Use the `Tee-Object` cmdlet, which sends command output to a text file and then sends it to the pipeline.</span></span>

- <span data-ttu-id="59212-115">使用 PowerShell 重定向运算符。</span><span class="sxs-lookup"><span data-stu-id="59212-115">Use the PowerShell redirection operators.</span></span> <span data-ttu-id="59212-116">使用带有文件目标的重定向运算符在功能上等效于 `Out-File` 无额外参数的管道。</span><span class="sxs-lookup"><span data-stu-id="59212-116">Using the redirection operator with a file target is functionally equivalent to piping to `Out-File` with no extra parameters.</span></span>

<span data-ttu-id="59212-117">有关流的详细信息，请参阅 [about_Output_Streams](about_Output_Streams.md)。</span><span class="sxs-lookup"><span data-stu-id="59212-117">For more information about streams, see [about_Output_Streams](about_Output_Streams.md).</span></span>

### <a name="redirectable-output-streams"></a><span data-ttu-id="59212-118">可重定向输出流</span><span class="sxs-lookup"><span data-stu-id="59212-118">Redirectable output streams</span></span>

<span data-ttu-id="59212-119">PowerShell 支持以下输出流的重定向。</span><span class="sxs-lookup"><span data-stu-id="59212-119">PowerShell supports redirection of the following output streams.</span></span>

| <span data-ttu-id="59212-120">流#</span><span class="sxs-lookup"><span data-stu-id="59212-120">Stream #</span></span> |      <span data-ttu-id="59212-121">说明</span><span class="sxs-lookup"><span data-stu-id="59212-121">Description</span></span>       | <span data-ttu-id="59212-122">引入</span><span class="sxs-lookup"><span data-stu-id="59212-122">Introduced in</span></span>  |    <span data-ttu-id="59212-123">写入 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="59212-123">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="59212-124">1</span><span class="sxs-lookup"><span data-stu-id="59212-124">1</span></span>        | <span data-ttu-id="59212-125">**成功** 流</span><span class="sxs-lookup"><span data-stu-id="59212-125">**Success** Stream</span></span>     | <span data-ttu-id="59212-126">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="59212-126">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="59212-127">2</span><span class="sxs-lookup"><span data-stu-id="59212-127">2</span></span>        | <span data-ttu-id="59212-128">**错误** 流</span><span class="sxs-lookup"><span data-stu-id="59212-128">**Error** Stream</span></span>       | <span data-ttu-id="59212-129">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="59212-129">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="59212-130">3</span><span class="sxs-lookup"><span data-stu-id="59212-130">3</span></span>        | <span data-ttu-id="59212-131">**警告** 流</span><span class="sxs-lookup"><span data-stu-id="59212-131">**Warning** Stream</span></span>     | <span data-ttu-id="59212-132">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="59212-132">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="59212-133">4</span><span class="sxs-lookup"><span data-stu-id="59212-133">4</span></span>        | <span data-ttu-id="59212-134">**详细** 流</span><span class="sxs-lookup"><span data-stu-id="59212-134">**Verbose** Stream</span></span>     | <span data-ttu-id="59212-135">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="59212-135">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="59212-136">5</span><span class="sxs-lookup"><span data-stu-id="59212-136">5</span></span>        | <span data-ttu-id="59212-137">**调试** 流</span><span class="sxs-lookup"><span data-stu-id="59212-137">**Debug** Stream</span></span>       | <span data-ttu-id="59212-138">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="59212-138">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="59212-139">6</span><span class="sxs-lookup"><span data-stu-id="59212-139">6</span></span>        | <span data-ttu-id="59212-140">**信息** 流</span><span class="sxs-lookup"><span data-stu-id="59212-140">**Information** Stream</span></span> | <span data-ttu-id="59212-141">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="59212-141">PowerShell 5.0</span></span> | `Write-Information` |
| *        | <span data-ttu-id="59212-142">所有流</span><span class="sxs-lookup"><span data-stu-id="59212-142">All Streams</span></span>            | <span data-ttu-id="59212-143">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="59212-143">PowerShell 3.0</span></span> |                     |

> [!NOTE]
> <span data-ttu-id="59212-144">PowerShell 中还有一个 **进度** 流，但它不支持重定向。</span><span class="sxs-lookup"><span data-stu-id="59212-144">There is also a **Progress** stream in PowerShell, but it does not support redirection.</span></span>

### <a name="powershell-redirection-operators"></a><span data-ttu-id="59212-145">PowerShell 重定向运算符</span><span class="sxs-lookup"><span data-stu-id="59212-145">PowerShell redirection operators</span></span>

<span data-ttu-id="59212-146">PowerShell 重定向运算符如下所示，其中 `n` 表示流号。</span><span class="sxs-lookup"><span data-stu-id="59212-146">The PowerShell redirection operators are as follows, where `n` represents the stream number.</span></span> <span data-ttu-id="59212-147">**Success** `1` 如果未指定流，则 ( ) 的成功流为默认值。</span><span class="sxs-lookup"><span data-stu-id="59212-147">The **Success** stream ( `1` ) is the default if no stream is specified.</span></span>

| <span data-ttu-id="59212-148">运算符</span><span class="sxs-lookup"><span data-stu-id="59212-148">Operator</span></span> |                         <span data-ttu-id="59212-149">说明</span><span class="sxs-lookup"><span data-stu-id="59212-149">Description</span></span>                         | <span data-ttu-id="59212-150">语法</span><span class="sxs-lookup"><span data-stu-id="59212-150">Syntax</span></span> |
| -------- | ----------------------------------------------------------- | ------ |
| `>`      | <span data-ttu-id="59212-151">向文件发送指定的流。</span><span class="sxs-lookup"><span data-stu-id="59212-151">Send specified stream to a file.</span></span>                            | `n>`   |
| `>>`     | <span data-ttu-id="59212-152">将指定的流 **追加** 到文件中。</span><span class="sxs-lookup"><span data-stu-id="59212-152">**Append** specified stream to a file.</span></span>                      | `n>>`  |
| `>&1`    | <span data-ttu-id="59212-153">将指定的流 _重定向_ 到 **成功** 流。</span><span class="sxs-lookup"><span data-stu-id="59212-153">_Redirects_ the specified stream to the **Success** stream.</span></span> | `n>&1` |

> [!NOTE]
> <span data-ttu-id="59212-154">与某些 Unix shell 不同，只能将其他流重定向到 **成功** 流。</span><span class="sxs-lookup"><span data-stu-id="59212-154">Unlike some Unix shells, you can only redirect other streams to the **Success** stream.</span></span>

## <a name="examples"></a><span data-ttu-id="59212-155">示例</span><span class="sxs-lookup"><span data-stu-id="59212-155">Examples</span></span>

### <a name="example-1-redirect-errors-and-output-to-a-file"></a><span data-ttu-id="59212-156">示例1：将错误和输出重定向到文件</span><span class="sxs-lookup"><span data-stu-id="59212-156">Example 1: Redirect errors and output to a file</span></span>

<span data-ttu-id="59212-157">此示例 `dir` 在一个将成功的项和一个将出错的项上运行。</span><span class="sxs-lookup"><span data-stu-id="59212-157">This example runs `dir` on one item that will succeed, and one that will error.</span></span>

```powershell
dir 'C:\', 'fakepath' 2>&1 > .\dir.log
```

<span data-ttu-id="59212-158">它使用 `2>&1` 将 **错误** 流重定向到 **成功** 流，并将 `>` 结果 **成功** 流发送到名为的文件 `dir.log`</span><span class="sxs-lookup"><span data-stu-id="59212-158">It uses `2>&1` to redirect the **Error** stream to the **Success** stream, and `>` to send the resultant **Success** stream to a file called `dir.log`</span></span>

### <a name="example-2-send-all-success-stream-data-to-a-file"></a><span data-ttu-id="59212-159">示例2：将所有成功流数据发送到文件</span><span class="sxs-lookup"><span data-stu-id="59212-159">Example 2: Send all Success stream data to a file</span></span>

<span data-ttu-id="59212-160">此示例将所有 **成功** 流数据发送到名为的文件 `script.log` 。</span><span class="sxs-lookup"><span data-stu-id="59212-160">This example sends all **Success** stream data to a file called `script.log`.</span></span>

```powershell
.\script.ps1 > script.log
```

### <a name="example-3-send-success-warning-and-error-streams-to-a-file"></a><span data-ttu-id="59212-161">示例3：将成功、警告和错误流发送到文件</span><span class="sxs-lookup"><span data-stu-id="59212-161">Example 3: Send Success, Warning, and Error streams to a file</span></span>

<span data-ttu-id="59212-162">此示例演示如何组合重定向运算符以获得所需的结果。</span><span class="sxs-lookup"><span data-stu-id="59212-162">This example shows how you can combine redirection operators to achieve a desired result.</span></span>

```powershell
&{
   Write-Warning "hello"
   Write-Error "hello"
   Write-Output "hi"
} 3>&1 2>&1 > P:\Temp\redirection.log
```

- <span data-ttu-id="59212-163">`3>&1` 将 **警告** 流重定向到 **成功** 流。</span><span class="sxs-lookup"><span data-stu-id="59212-163">`3>&1` redirects the **Warning** stream to the **Success** stream.</span></span>
- <span data-ttu-id="59212-164">`2>&1` 将 **错误** 流重定向到 **成功** 流 (后者现在同时包含所有 **警告** 流数据) </span><span class="sxs-lookup"><span data-stu-id="59212-164">`2>&1` redirects the **Error** stream to the **Success** stream (which also now includes all **Warning** stream data)</span></span>
- <span data-ttu-id="59212-165">`>` 重定向 **成功** 流， (现在包含) 到名为的文件的 **警告** 和 **错误** 流 `C:\temp\redirection.log`) </span><span class="sxs-lookup"><span data-stu-id="59212-165">`>` redirects the **Success** stream (which now contains both **Warning** and **Error** streams) to a file called `C:\temp\redirection.log`)</span></span>

### <a name="example-4-redirect-all-streams-to-a-file"></a><span data-ttu-id="59212-166">示例4：将所有流重定向到文件</span><span class="sxs-lookup"><span data-stu-id="59212-166">Example 4: Redirect all streams to a file</span></span>

<span data-ttu-id="59212-167">此示例将一个名为的脚本输出从一个名 `script.ps1` 为 `script.log`</span><span class="sxs-lookup"><span data-stu-id="59212-167">This example sends all streams output from a script called `script.ps1` to a file called `script.log`</span></span>

```powershell
.\script.ps1 *> script.log
```

### <a name="example-5-suppress-all-write-host-and-information-stream-data"></a><span data-ttu-id="59212-168">示例5：禁止显示所有 Write-Host 和信息流数据</span><span class="sxs-lookup"><span data-stu-id="59212-168">Example 5: Suppress all Write-Host and Information stream data</span></span>

<span data-ttu-id="59212-169">此示例将禁止显示所有信息流数据。</span><span class="sxs-lookup"><span data-stu-id="59212-169">This example suppresses all information stream data.</span></span> <span data-ttu-id="59212-170">若要了解有关 **信息流** cmdlet 的详细信息，请参阅 [写入主机](xref:Microsoft.PowerShell.Utility.Write-Host) 和 [写入信息](xref:Microsoft.PowerShell.Utility.Write-Information)</span><span class="sxs-lookup"><span data-stu-id="59212-170">To read more about **Information** stream cmdlets, see [Write-Host](xref:Microsoft.PowerShell.Utility.Write-Host) and [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information)</span></span>

```powershell
&{
   Write-Host "Hello"
   Write-Information "Hello" -InformationAction Continue
} 6> $null
```

### <a name="example-6-show-the-effect-of-action-preferences"></a><span data-ttu-id="59212-171">示例6：显示操作首选项的效果</span><span class="sxs-lookup"><span data-stu-id="59212-171">Example 6: Show the effect of Action Preferences</span></span>

<span data-ttu-id="59212-172">操作首选项变量和参数可以更改写入特定流的内容。</span><span class="sxs-lookup"><span data-stu-id="59212-172">Action Preference variables and parameters can change what gets written to a particular stream.</span></span> <span data-ttu-id="59212-173">此示例中的脚本显示的值如何 `$ErrorActionPreference` 影响写入 **错误** 流的内容。</span><span class="sxs-lookup"><span data-stu-id="59212-173">The script in this example shows how the value of `$ErrorActionPreference` affects what gets written to the **Error** stream.</span></span>

```powershell
$ErrorActionPreference = 'Continue'
$ErrorActionPreference > log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'SilentlyContinue'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Stop'
$ErrorActionPreference >> log.txt
Try {
    get-item /not-here 2>&1 >> log.txt
}
catch {
    "`tError caught!" >> log.txt
}
$ErrorActionPreference = 'Ignore'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Inquire'
$ErrorActionPreference >> log.txt
get-item /not-here 2>&1 >> log.txt

$ErrorActionPreference = 'Continue'
```

<span data-ttu-id="59212-174">当我们运行此脚本时 `$ErrorActionPreference` ，将在设置为时收到提示 `Inquire` 。</span><span class="sxs-lookup"><span data-stu-id="59212-174">When we run this script we get prompted when `$ErrorActionPreference` is set to `Inquire`.</span></span>

```powershell
PS C:\temp> .\test.ps1

Confirm
Cannot find path 'C:\not-here' because it does not exist.
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"): H
Get-Item: C:\temp\test.ps1:23
Line |
  23 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | The running command stopped because the user selected the Stop option.
```

<span data-ttu-id="59212-175">当我们检查日志文件时，将看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="59212-175">When we examine the log file we see the following:</span></span>

```
PS C:\temp> Get-Content .\log.txt
Continue

Get-Item: C:\temp\test.ps1:3
Line |
   3 |  get-item /not-here 2>&1 >> log.txt
     |  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
     | Cannot find path 'C:\not-here' because it does not exist.

SilentlyContinue
Stop
    Error caught!
Ignore
Inquire
```

## <a name="notes"></a><span data-ttu-id="59212-176">注释</span><span class="sxs-lookup"><span data-stu-id="59212-176">Notes</span></span>

<span data-ttu-id="59212-177">不会在不发出警告的情况下将数据追加 (`>` 和 `n>`) 覆盖指定文件的当前内容的重定向运算符。</span><span class="sxs-lookup"><span data-stu-id="59212-177">The redirection operators that do not append data (`>` and `n>`) overwrite the current contents of the specified file without warning.</span></span>

<span data-ttu-id="59212-178">但是，如果该文件是只读文件、隐藏文件或系统文件，则重定向 **会失败** 。</span><span class="sxs-lookup"><span data-stu-id="59212-178">However, if the file is a read-only, hidden, or system file, the redirection **fails** .</span></span> <span data-ttu-id="59212-179">追加重定向运算符 (`>>` 和 `n>>`) 不写入只读文件，但会将内容附加到系统文件或隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="59212-179">The append redirection operators (`>>` and `n>>`) do not write to a read-only file, but they append content to a system or hidden file.</span></span>

<span data-ttu-id="59212-180">若要强制将内容重定向到只读、隐藏或系统文件，请使用 `Out-File` cmdlet 及其 `Force` 参数。</span><span class="sxs-lookup"><span data-stu-id="59212-180">To force the redirection of content to a read-only, hidden, or system file, use the `Out-File` cmdlet with its `Force` parameter.</span></span>

<span data-ttu-id="59212-181">写入文件时，重定向运算符使用 `UTF8NoBOM` 编码。</span><span class="sxs-lookup"><span data-stu-id="59212-181">When you are writing to files, the redirection operators use `UTF8NoBOM` encoding.</span></span> <span data-ttu-id="59212-182">如果文件具有不同的编码，则输出的格式可能不正确。</span><span class="sxs-lookup"><span data-stu-id="59212-182">If the file has a different encoding, the output might not be formatted correctly.</span></span> <span data-ttu-id="59212-183">若要使用不同的编码写入文件，请使用 `Out-File` cmdlet 及其 `Encoding` 参数。</span><span class="sxs-lookup"><span data-stu-id="59212-183">To write to files with a different encoding, use the `Out-File` cmdlet with its `Encoding` parameter.</span></span>

### <a name="potential-confusion-with-comparison-operators"></a><span data-ttu-id="59212-184">比较运算符可能产生混淆</span><span class="sxs-lookup"><span data-stu-id="59212-184">Potential confusion with comparison operators</span></span>

<span data-ttu-id="59212-185">`>`运算符不会与[大于](about_Comparison_Operators.md#-gt)比较运算符混淆， (通常 `>`) 的其他编程语言中表示为。</span><span class="sxs-lookup"><span data-stu-id="59212-185">The `>` operator is not to be confused with the [Greater-than](about_Comparison_Operators.md#-gt) comparison operator (often denoted as `>` in other programming languages).</span></span>

<span data-ttu-id="59212-186">根据所比较的对象，使用的输出 `>` 可能看起来是正确的 (因为36不大于 42) 。</span><span class="sxs-lookup"><span data-stu-id="59212-186">Depending on the objects being compared, the output using `>` can appear to be correct (because 36 is not greater than 42).</span></span>

```powershell
PS> if (36 > 42) { "true" } else { "false" }
false
```

<span data-ttu-id="59212-187">但是，对本地文件系统的检查可以看到名为的文件 `42` 是用内容编写的 `36` 。</span><span class="sxs-lookup"><span data-stu-id="59212-187">However, a check of the local filesystem can see that a file called `42` was written, with the contents `36`.</span></span>

```powershell
PS> dir

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
------          1/02/20  10:10 am              3 42

PS> cat 42
36
```

<span data-ttu-id="59212-188">尝试使用反向比较 `<` (小于) 时，会产生系统错误：</span><span class="sxs-lookup"><span data-stu-id="59212-188">Attempting to use the reverse comparison `<` (less than), yields a system error:</span></span>

```powershell
PS> if (36 < 42) { "true" } else { "false" }
At line:1 char:8
+ if (36 < 42) { "true" } else { "false" }
+        ~
The '<' operator is reserved for future use.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : RedirectionNotSupported
```

<span data-ttu-id="59212-189">如果数字比较是必需的操作， `-lt` 则 `-gt` 应使用。</span><span class="sxs-lookup"><span data-stu-id="59212-189">If numeric comparison is the required operation, `-lt` and `-gt` should be used.</span></span> <span data-ttu-id="59212-190">请参阅： [ `-gt` 比较运算符](about_Comparison_Operators.md#-gt)</span><span class="sxs-lookup"><span data-stu-id="59212-190">See: [`-gt` Comparison Operator](about_Comparison_Operators.md#-gt)</span></span>

## <a name="see-also"></a><span data-ttu-id="59212-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59212-191">See also</span></span>

- [<span data-ttu-id="59212-192">Out-File</span><span class="sxs-lookup"><span data-stu-id="59212-192">Out-File</span></span>](xref:Microsoft.PowerShell.Utility.Out-File)
- [<span data-ttu-id="59212-193">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="59212-193">Tee-Object</span></span>](xref:Microsoft.PowerShell.Utility.Tee-Object)
- [<span data-ttu-id="59212-194">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="59212-194">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="59212-195">写入错误</span><span class="sxs-lookup"><span data-stu-id="59212-195">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="59212-196">Write-Host</span><span class="sxs-lookup"><span data-stu-id="59212-196">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="59212-197">Write-Information</span><span class="sxs-lookup"><span data-stu-id="59212-197">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="59212-198">Write-Output</span><span class="sxs-lookup"><span data-stu-id="59212-198">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="59212-199">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="59212-199">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="59212-200">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="59212-200">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="59212-201">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="59212-201">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="59212-202">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="59212-202">about_Output_Streams</span></span>](about_Output_Streams.md)
- [<span data-ttu-id="59212-203">about_Operators</span><span class="sxs-lookup"><span data-stu-id="59212-203">about_Operators</span></span>](about_Operators.md)
- [<span data-ttu-id="59212-204">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="59212-204">about_Command_Syntax</span></span>](about_Command_Syntax.md)
- [<span data-ttu-id="59212-205">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="59212-205">about_Path_Syntax</span></span>](about_Path_Syntax.md)
