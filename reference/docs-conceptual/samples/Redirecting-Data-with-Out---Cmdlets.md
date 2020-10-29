---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 使用 Out Cmdlet 重定向数据
description: 本文介绍如何使用管理 PowerShell 中的输出的 cmdlet。
ms.openlocfilehash: 3a9e3b1ac06f5be4e6f3bbc52a15c4afb5b12cef
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500209"
---
# <a name="redirecting-data-with-out--cmdlets"></a><span data-ttu-id="d31c5-104">使用 Out-\* Cmdlet 重定向数据</span><span class="sxs-lookup"><span data-stu-id="d31c5-104">Redirecting Data with Out-\* Cmdlets</span></span>

<span data-ttu-id="d31c5-105">Windows PowerShell 提供多个 cmdlet，可让你直接控制数据输出。</span><span class="sxs-lookup"><span data-stu-id="d31c5-105">Windows PowerShell provides several cmdlets that let you control data output directly.</span></span> <span data-ttu-id="d31c5-106">这些 cmdlet 具有两个重要的共同特征。</span><span class="sxs-lookup"><span data-stu-id="d31c5-106">These cmdlets share two important characteristics.</span></span>

<span data-ttu-id="d31c5-107">第一，它们通常将数据转换为某种形式的文本。</span><span class="sxs-lookup"><span data-stu-id="d31c5-107">First, they generally transform data to some form of text.</span></span> <span data-ttu-id="d31c5-108">这样做的原因是它们将数据输出到需要文本输入的系统组件。</span><span class="sxs-lookup"><span data-stu-id="d31c5-108">They do this because they output the data to system components that require text input.</span></span> <span data-ttu-id="d31c5-109">这意味着它们需要将对象表示为文本。</span><span class="sxs-lookup"><span data-stu-id="d31c5-109">This means they need to represent the objects as text.</span></span> <span data-ttu-id="d31c5-110">因此，文本的格式设置为你在 Windows PowerShell 控制台窗口中看到的形式。</span><span class="sxs-lookup"><span data-stu-id="d31c5-110">Therefore, the text is formatted as you see it in the Windows PowerShell console window.</span></span>

<span data-ttu-id="d31c5-111">第二，这些 cmdlet 使用 Windows PowerShell 谓词 **Out** ，因为它们会将信息从 Windows PowerShell 发送到别处。</span><span class="sxs-lookup"><span data-stu-id="d31c5-111">Second, these cmdlets use the Windows PowerShell verb **Out** because they send information out from Windows PowerShell to somewhere else.</span></span> <span data-ttu-id="d31c5-112">**Out-Host** cmdlet 也不例外：主机窗口显示在 Windows PowerShell 之外。</span><span class="sxs-lookup"><span data-stu-id="d31c5-112">The **Out-Host** cmdlet is no exception: the host window display is outside of Windows PowerShell.</span></span> <span data-ttu-id="d31c5-113">这一点尤为重要，原因是将数据发送出 Windows PowerShell 时，实际上已删除该数据。</span><span class="sxs-lookup"><span data-stu-id="d31c5-113">This is important because when data is sent out of Windows PowerShell, it is actually removed.</span></span> <span data-ttu-id="d31c5-114">在你尝试创建用于将数据分页到主机窗口的管道，然后尝试将其格式化为列表时，可以看到此内容，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d31c5-114">You can see this if you try to create a pipeline that pages data to the host window, and then attempt to format it as a list, as shown here:</span></span>

```powershell
Get-Process | Out-Host -Paging | Format-List
```

<span data-ttu-id="d31c5-115">你可能希望命令显示列表格式的进程信息页。</span><span class="sxs-lookup"><span data-stu-id="d31c5-115">You might expect the command to display pages of process information in list format.</span></span> <span data-ttu-id="d31c5-116">但是，它将显示默认表格式列表：</span><span class="sxs-lookup"><span data-stu-id="d31c5-116">Instead, it displays the default tabular list:</span></span>

```output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    101       5     1076       3316    32     0.05   2888 alg
...
    618      18    39348      51108   143   211.20    740 explorer
    257       8     9752      16828    79     3.02   2560 explorer
...
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="d31c5-117">**Out-Host** cmdlet 直接将数据发送到控制台，因此 **Format-List** 命令绝不会收到任何要进行格式化的内容。</span><span class="sxs-lookup"><span data-stu-id="d31c5-117">The **Out-Host** cmdlet sends the data directly to the console, so the **Format-List** command never receives anything to format.</span></span>

<span data-ttu-id="d31c5-118">构建此命令的正确方法是将 **Out-Host** cmdlet 置于管道末尾，如下所示。</span><span class="sxs-lookup"><span data-stu-id="d31c5-118">The correct way to structure this command is to put the **Out-Host** cmdlet at the end of the pipeline as shown below.</span></span> <span data-ttu-id="d31c5-119">这将导致进程数据先在列表中格式化，然后再分页和显示。</span><span class="sxs-lookup"><span data-stu-id="d31c5-119">This causes the process data to be formatted in a list before being paged and displayed.</span></span>

```
PS> Get-Process | Format-List | Out-Host -Paging

Id      : 2888
Handles : 101
CPU     : 0.046875
Name    : alg
...

Id      : 740
Handles : 612
CPU     : 211.703125
Name    : explorer

Id      : 2560
Handles : 257
CPU     : 3.015625
Name    : explorer
...
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="d31c5-120">这适用于所有 **Out** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d31c5-120">This applies to all of the **Out** cmdlets.</span></span> <span data-ttu-id="d31c5-121">**Out** cmdlet 应始终出现在管道末尾。</span><span class="sxs-lookup"><span data-stu-id="d31c5-121">An **Out** cmdlet should always appear at the end of the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="d31c5-122">所有 **Out** cmdlet 都使用对控制台窗口有效的格式（包括行长度限制）将输出呈现为文本。</span><span class="sxs-lookup"><span data-stu-id="d31c5-122">All the **Out** cmdlets render output as text, using the formatting in effect for the console window, including line length limits.</span></span>

## <a name="paging-console-output-out-host"></a><span data-ttu-id="d31c5-123">分页控制台输出 (Out-Host)</span><span class="sxs-lookup"><span data-stu-id="d31c5-123">Paging Console Output (Out-Host)</span></span>

<span data-ttu-id="d31c5-124">默认情况下，Windows PowerShell 将数据发送到主机窗口，这正是 Out-Host cmdlet 的用途。</span><span class="sxs-lookup"><span data-stu-id="d31c5-124">By default, Windows PowerShell sends data to the host window, which is exactly what the Out-Host cmdlet does.</span></span> <span data-ttu-id="d31c5-125">Out-Host cmdlet 的主要用途是对数据进行分页，如前面所述。</span><span class="sxs-lookup"><span data-stu-id="d31c5-125">The primary use for the Out-Host cmdlet is paging data as we discussed earlier.</span></span> <span data-ttu-id="d31c5-126">例如，下面的命令使用 Out-Host 对 Get-Command cmdlet 的输出进行分页：</span><span class="sxs-lookup"><span data-stu-id="d31c5-126">For example, the following command uses Out-Host to page the output of the Get-Command cmdlet:</span></span>

```powershell
Get-Command | Out-Host -Paging
```

<span data-ttu-id="d31c5-127">你还可以使用 **more** 函数对数据进行分页。</span><span class="sxs-lookup"><span data-stu-id="d31c5-127">You can also use the **more** function to page data.</span></span> <span data-ttu-id="d31c5-128">在 Windows PowerShell 中， **more** 是调用 **Out-Host -Paging** 的函数。</span><span class="sxs-lookup"><span data-stu-id="d31c5-128">In Windows PowerShell, **more** is a function that calls **Out-Host -Paging** .</span></span> <span data-ttu-id="d31c5-129">下面的命令演示了如何使用 **more** 函数对 Get-Command 的输出进行分页：</span><span class="sxs-lookup"><span data-stu-id="d31c5-129">The following command demonstrates using the **more** function to page the output of Get-Command:</span></span>

```powershell
Get-Command | more
```

<span data-ttu-id="d31c5-130">如果将一个或多个文件名作为参数包括到 more 函数中，则该函数将读取指定文件并将其内容分页到主机中：</span><span class="sxs-lookup"><span data-stu-id="d31c5-130">If you include one or more filenames as arguments to the more function, the function will read the specified files and page their contents to the host:</span></span>

```
PS> more c:\boot.ini
[boot loader]
timeout=5
default=multi(0)disk(0)rdisk(0)partition(1)\WINDOWS
[operating systems]
...
```

## <a name="discarding-output-out-null"></a><span data-ttu-id="d31c5-131">放弃输出 (Out-Null)</span><span class="sxs-lookup"><span data-stu-id="d31c5-131">Discarding Output (Out-Null)</span></span>

<span data-ttu-id="d31c5-132">**Out-Null** cmdlet 旨在用于立即放弃接收的任何输入。</span><span class="sxs-lookup"><span data-stu-id="d31c5-132">The **Out-Null** cmdlet is designed to immediately discard any input it receives.</span></span> <span data-ttu-id="d31c5-133">这对放弃收到的不利于运行命令的不必要数据很有用。</span><span class="sxs-lookup"><span data-stu-id="d31c5-133">This is useful for discarding unnecessary data that you get as a side-effect of running a command.</span></span> <span data-ttu-id="d31c5-134">键入下面的命令时，该命令不会返回任何内容：</span><span class="sxs-lookup"><span data-stu-id="d31c5-134">When type the following command, you do not get anything back from the command:</span></span>

```powershell
Get-Command | Out-Null
```

<span data-ttu-id="d31c5-135">**Out-Null** cmdlet 不会放弃错误输出。</span><span class="sxs-lookup"><span data-stu-id="d31c5-135">The **Out-Null** cmdlet does not discard error output.</span></span> <span data-ttu-id="d31c5-136">例如，如果输入下面的命令，则将显示一条消息，通知你 Windows PowerShell 无法识别“Is-NotACommand”：</span><span class="sxs-lookup"><span data-stu-id="d31c5-136">For example, if you enter the following command, a message is displayed informing you that Windows PowerShell does not recognize 'Is-NotACommand':</span></span>

```
PS> Get-Command Is-NotACommand | Out-Null
Get-Command : 'Is-NotACommand' is not recognized as a cmdlet, function, operabl
e program, or script file.
At line:1 char:12
+ Get-Command  <<<< Is-NotACommand | Out-Null
```

## <a name="printing-data-out-printer"></a><span data-ttu-id="d31c5-137">打印数据 (Out-Printer)</span><span class="sxs-lookup"><span data-stu-id="d31c5-137">Printing Data (Out-Printer)</span></span>

<span data-ttu-id="d31c5-138">可以通过使用 **Out-Printer** cmdlet 打印数据。</span><span class="sxs-lookup"><span data-stu-id="d31c5-138">You can print data by using the **Out-Printer** cmdlet.</span></span> <span data-ttu-id="d31c5-139">如果未提供打印机名称，则 **Out-Printer** cmdlet 将使用默认打印机。</span><span class="sxs-lookup"><span data-stu-id="d31c5-139">The **Out-Printer** cmdlet will use your default printer if you do not provide a printer name.</span></span> <span data-ttu-id="d31c5-140">可以通过指定其显示名称使用任何基于 Windows 的打印机。</span><span class="sxs-lookup"><span data-stu-id="d31c5-140">You can use any Windows-based printer by specifying its display name.</span></span> <span data-ttu-id="d31c5-141">无需使用任何类型的打印机端口映射，甚至无需使用真正的物理打印机。</span><span class="sxs-lookup"><span data-stu-id="d31c5-141">There is no need for any kind of printer port mapping or even a real physical printer.</span></span> <span data-ttu-id="d31c5-142">例如，如果安装了 Microsoft Office 文档映像工具，则可通过键入以下内容将数据发送到映像文件：</span><span class="sxs-lookup"><span data-stu-id="d31c5-142">For example, if you have the Microsoft Office document imaging tools installed, you can send the data to an image file by typing:</span></span>

```powershell
Get-Command Get-Command | Out-Printer -Name 'Microsoft Office Document Image Writer'
```

## <a name="saving-data-out-file"></a><span data-ttu-id="d31c5-143">保存数据 (Out-File)</span><span class="sxs-lookup"><span data-stu-id="d31c5-143">Saving Data (Out-File)</span></span>

<span data-ttu-id="d31c5-144">可以使用 **Out-File** cmdlet 将输出发送到文件而不是控制台窗口。</span><span class="sxs-lookup"><span data-stu-id="d31c5-144">You can send output to a file instead of the console window by using the **Out-File** cmdlet.</span></span> <span data-ttu-id="d31c5-145">下面的命令行将进程列表发送到文件 **C:\\temp\\processlist.txt** ：</span><span class="sxs-lookup"><span data-stu-id="d31c5-145">The following command line sends a list of processes to the file **C:\\temp\\processlist.txt** :</span></span>

```powershell
Get-Process | Out-File -FilePath C:\temp\processlist.txt
```

<span data-ttu-id="d31c5-146">如果你习惯使用传统的输出重定向，则使用 **Out-File** cmdlet 可能与你的预期结果有所不同。</span><span class="sxs-lookup"><span data-stu-id="d31c5-146">The results of using the **Out-File** cmdlet may not be what you expect if you are used to traditional output redirection.</span></span> <span data-ttu-id="d31c5-147">若要了解其行为，必须知道运行 **Out-File** cmdlet 的上下文。</span><span class="sxs-lookup"><span data-stu-id="d31c5-147">To understand its behavior, you must be aware of the context in which the **Out-File** cmdlet operates.</span></span>

<span data-ttu-id="d31c5-148">默认情况下， **Out-File** cmdlet 创建 Unicode 文件。</span><span class="sxs-lookup"><span data-stu-id="d31c5-148">By default, the **Out-File** cmdlet creates a Unicode file.</span></span> <span data-ttu-id="d31c5-149">从长远来看，这是最佳默认操作，但是它意味着应创建 ASCII 文件的工具将无法使用默认的输出格式正常运作。</span><span class="sxs-lookup"><span data-stu-id="d31c5-149">This is the best default in the long run, but it means that tools that expect ASCII files will not work correctly with the default output format.</span></span> <span data-ttu-id="d31c5-150">可以使用 **Encoding** 参数将默认输出格式更改为 ASCII：</span><span class="sxs-lookup"><span data-stu-id="d31c5-150">You can change the default output format to ASCII by using the **Encoding** parameter:</span></span>

```powershell
Get-Process | Out-File -FilePath C:\temp\processlist.txt -Encoding ASCII
```

<span data-ttu-id="d31c5-151">**Out-File** 将文件内容格式化为与控制台输出类似的形式。</span><span class="sxs-lookup"><span data-stu-id="d31c5-151">**Out-file** formats file contents to look like console output.</span></span> <span data-ttu-id="d31c5-152">这会导致输出被截断，大多数情况下正如它在控制台窗口中一样。</span><span class="sxs-lookup"><span data-stu-id="d31c5-152">This causes the output to be truncated just as it is in a console window in most circumstances.</span></span> <span data-ttu-id="d31c5-153">例如，如果运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="d31c5-153">For example, if you run the following command:</span></span>

```powershell
Get-Command | Out-File -FilePath c:\temp\output.txt
```

<span data-ttu-id="d31c5-154">输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="d31c5-154">The output will look like this:</span></span>

```output
CommandType     Name                            Definition
-----------     ----                            ----------
Cmdlet          Add-Content                     Add-Content [-Path] <String[...
Cmdlet          Add-History                     Add-History [[-InputObject] ...
...
```

<span data-ttu-id="d31c5-155">若要使不会强制换行的输出与屏幕宽度匹配，可以使用 **Width** 参数来指定行宽。</span><span class="sxs-lookup"><span data-stu-id="d31c5-155">To get output that does not force line wraps to match the screen width, you can use the **Width** parameter to specify line width.</span></span> <span data-ttu-id="d31c5-156">因为 **Width** 是一个 32 位整数参数，因此其最大值可以是 2147483647。</span><span class="sxs-lookup"><span data-stu-id="d31c5-156">Because **Width** is a 32-bit integer parameter, the maximum value it can have is 2147483647.</span></span> <span data-ttu-id="d31c5-157">键入以下内容以将行宽设置为此最大值：</span><span class="sxs-lookup"><span data-stu-id="d31c5-157">Type the following to set the line width to this maximum value:</span></span>

```powershell
Get-Command | Out-File -FilePath c:\temp\output.txt -Width 2147483647
```

<span data-ttu-id="d31c5-158">想要保存原本显示在控制台中的输出时，使用 **Out-File** cmdlet 最有用。</span><span class="sxs-lookup"><span data-stu-id="d31c5-158">The **Out-File** cmdlet is most useful when you want to save output as it would have displayed on the console.</span></span> <span data-ttu-id="d31c5-159">若要更好地控制输出格式，需要更高级的工具。</span><span class="sxs-lookup"><span data-stu-id="d31c5-159">For finer control over output format, you need more advanced tools.</span></span> <span data-ttu-id="d31c5-160">我们将在下一章中查看这些内容以及有关对象操作的一些详细信息。</span><span class="sxs-lookup"><span data-stu-id="d31c5-160">We will look at those in the next chapter, along with some details about object manipulation.</span></span>
