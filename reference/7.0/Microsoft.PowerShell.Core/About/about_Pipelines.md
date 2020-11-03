---
description: 在 PowerShell 中将命令合并到管道中
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: bf5e57389d286a2bb1cca9b3dd73ea59674461ec
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200205"
---
# <a name="about-pipelines"></a><span data-ttu-id="5a826-104">关于管道</span><span class="sxs-lookup"><span data-stu-id="5a826-104">About Pipelines</span></span>

## <a name="short-description"></a><span data-ttu-id="5a826-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="5a826-105">Short description</span></span>

<span data-ttu-id="5a826-106">在 PowerShell 中将命令合并到管道中</span><span class="sxs-lookup"><span data-stu-id="5a826-106">Combining commands into pipelines in the PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="5a826-107">长说明</span><span class="sxs-lookup"><span data-stu-id="5a826-107">Long description</span></span>

<span data-ttu-id="5a826-108">管道是一系列由管道运算符连接的命令 (`|`)  (ASCII 124) 。</span><span class="sxs-lookup"><span data-stu-id="5a826-108">A pipeline is a series of commands connected by pipeline operators (`|`) (ASCII 124).</span></span> <span data-ttu-id="5a826-109">每个管道运算符将前一个命令的结果发送到下一个命令。</span><span class="sxs-lookup"><span data-stu-id="5a826-109">Each pipeline operator sends the results of the preceding command to the next command.</span></span>

<span data-ttu-id="5a826-110">可以发送第一个命令的输出，作为第二个命令的输入进行处理。</span><span class="sxs-lookup"><span data-stu-id="5a826-110">The output of the first command can be sent for processing as input to the second command.</span></span> <span data-ttu-id="5a826-111">还可以将输出发送到另一个命令。</span><span class="sxs-lookup"><span data-stu-id="5a826-111">And that output can be sent to yet another command.</span></span> <span data-ttu-id="5a826-112">结果是一个复杂的命令链或 _管道_ ，由一系列简单的命令组成。</span><span class="sxs-lookup"><span data-stu-id="5a826-112">The result is a complex command chain or _pipeline_ that is composed of a series of simple commands.</span></span>

<span data-ttu-id="5a826-113">例如，</span><span class="sxs-lookup"><span data-stu-id="5a826-113">For example,</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="5a826-114">在此示例中，发出的对象将 `Command-1` 发送到 `Command-2` 。</span><span class="sxs-lookup"><span data-stu-id="5a826-114">In this example, the objects that `Command-1` emits are sent to `Command-2`.</span></span>
<span data-ttu-id="5a826-115">`Command-2` 处理对象并将其发送到 `Command-3` 。</span><span class="sxs-lookup"><span data-stu-id="5a826-115">`Command-2` processes the objects and sends them to `Command-3`.</span></span> <span data-ttu-id="5a826-116">`Command-3` 处理对象并将其沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="5a826-116">`Command-3` processes the objects and send them down the pipeline.</span></span> <span data-ttu-id="5a826-117">由于管道中没有更多命令，因此结果将显示在控制台上。</span><span class="sxs-lookup"><span data-stu-id="5a826-117">Because there are no more commands in the pipeline, the results are displayed at the console.</span></span>

<span data-ttu-id="5a826-118">在管道中，按从左到右的顺序处理命令。</span><span class="sxs-lookup"><span data-stu-id="5a826-118">In a pipeline, the commands are processed in order from left to right.</span></span> <span data-ttu-id="5a826-119">处理将作为单个操作进行处理，并在生成时显示输出。</span><span class="sxs-lookup"><span data-stu-id="5a826-119">The processing is handled as a single operation and output is displayed as it's generated.</span></span>

<span data-ttu-id="5a826-120">下面是一个简单的示例。</span><span class="sxs-lookup"><span data-stu-id="5a826-120">Here is a simple example.</span></span> <span data-ttu-id="5a826-121">以下命令将获取记事本进程，然后将其停止。</span><span class="sxs-lookup"><span data-stu-id="5a826-121">The following command gets the Notepad process and then stops it.</span></span>

<span data-ttu-id="5a826-122">例如，</span><span class="sxs-lookup"><span data-stu-id="5a826-122">For example,</span></span>

```powershell
Get-Process notepad | Stop-Process
```

<span data-ttu-id="5a826-123">第一个命令使用 `Get-Process` cmdlet 来获取表示记事本进程的对象。</span><span class="sxs-lookup"><span data-stu-id="5a826-123">The first command uses the `Get-Process` cmdlet to get an object representing the Notepad process.</span></span> <span data-ttu-id="5a826-124">它使用管道运算符 (`|`) 将进程对象发送到 `Stop-Process` cmdlet，后者将停止记事本进程。</span><span class="sxs-lookup"><span data-stu-id="5a826-124">It uses a pipeline operator (`|`) to send the process object to the `Stop-Process` cmdlet, which stops the Notepad process.</span></span> <span data-ttu-id="5a826-125">请注意，该 `Stop-Process` 命令没有 **Name** 或 **ID** 参数来指定进程，因为指定的进程是通过管道提交的。</span><span class="sxs-lookup"><span data-stu-id="5a826-125">Notice that the `Stop-Process` command doesn't have a **Name** or **ID** parameter to specify the process, because the specified process is submitted through the pipeline.</span></span>

<span data-ttu-id="5a826-126">此管道示例获取当前目录中的文本文件，只选择长度超过10000个字节的文件，按长度对它们进行排序，并在表中显示每个文件的名称和长度。</span><span class="sxs-lookup"><span data-stu-id="5a826-126">This pipeline example gets the text files in the current directory, selects only the files that are more than 10,000 bytes long, sorts them by length, and displays the name and length of each file in a table.</span></span>

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

<span data-ttu-id="5a826-127">此管道按指定顺序包含四个命令。</span><span class="sxs-lookup"><span data-stu-id="5a826-127">This pipeline consists of four commands in the specified order.</span></span> <span data-ttu-id="5a826-128">下图显示了每个命令的输出，因为它将传递到管道中的下一个命令。</span><span class="sxs-lookup"><span data-stu-id="5a826-128">The following illustration shows the output from each command as it's passed to the next command in the pipeline.</span></span>

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a><span data-ttu-id="5a826-129">使用管道</span><span class="sxs-lookup"><span data-stu-id="5a826-129">Using pipelines</span></span>

<span data-ttu-id="5a826-130">大多数 PowerShell cmdlet 都设计为支持管道。</span><span class="sxs-lookup"><span data-stu-id="5a826-130">Most PowerShell cmdlets are designed to support pipelines.</span></span> <span data-ttu-id="5a826-131">在大多数情况下，你可以通过 _管道_ 将 **Get** cmdlet 的结果传递给相同名词的另一个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a826-131">In most cases, you can _pipe_ the results of a **Get** cmdlet to another cmdlet of the same noun.</span></span>
<span data-ttu-id="5a826-132">例如，可以通过管道将 cmdlet 的输出传递 `Get-Service` 给 `Start-Service` 或 `Stop-Service` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a826-132">For example, you can pipe the output of the `Get-Service` cmdlet to the `Start-Service` or `Stop-Service` cmdlets.</span></span>

<span data-ttu-id="5a826-133">此示例管道在计算机上启动 WMI 服务：</span><span class="sxs-lookup"><span data-stu-id="5a826-133">This example pipeline starts the WMI service on the computer:</span></span>

```powershell
Get-Service wmi | Start-Service
```

<span data-ttu-id="5a826-134">再例如，你可以通过管道将 `Get-Item` `Get-ChildItem` PowerShell 注册表提供程序的输出传递给 `New-ItemProperty` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a826-134">For another example, you can pipe the output of `Get-Item` or `Get-ChildItem` within the PowerShell registry provider to the `New-ItemProperty` cmdlet.</span></span> <span data-ttu-id="5a826-135">此示例将值为 **8124** 的新注册表项 **NoOfEmployees** 添加到 **MyCompany** 注册表项。</span><span class="sxs-lookup"><span data-stu-id="5a826-135">This example adds a new registry entry, **NoOfEmployees** , with a value of **8124** , to the **MyCompany** registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

<span data-ttu-id="5a826-136">许多实用工具 cmdlet （如、、、 `Get-Member` `Where-Object` 和） `Sort-Object` `Group-Object` `Measure-Object` 几乎只是在管道中使用。</span><span class="sxs-lookup"><span data-stu-id="5a826-136">Many of the utility cmdlets, such as `Get-Member`, `Where-Object`, `Sort-Object`, `Group-Object`, and `Measure-Object` are used almost exclusively in pipelines.</span></span> <span data-ttu-id="5a826-137">可以通过管道将任何对象类型传递给这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a826-137">You can pipe any object type to these cmdlets.</span></span> <span data-ttu-id="5a826-138">此示例显示了如何按每个进程中打开的句柄数对计算机上的所有进程进行排序。</span><span class="sxs-lookup"><span data-stu-id="5a826-138">This example shows how to sort all the processes on the computer by the number of open handles in each process.</span></span>

```powershell
Get-Process | Sort-Object -Property handles
```

<span data-ttu-id="5a826-139">可以通过管道将对象传递给格式设置、导出和输出 cmdlet，例如 `Format-List` 、、、 `Format-Table` `Export-Clixml` `Export-CSV` 和 `Out-File` 。</span><span class="sxs-lookup"><span data-stu-id="5a826-139">You can pipe objects to the formatting, export, and output cmdlets, such as `Format-List`, `Format-Table`, `Export-Clixml`, `Export-CSV`, and `Out-File`.</span></span>

<span data-ttu-id="5a826-140">此示例演示如何使用 `Format-List` cmdlet 显示进程对象的属性列表。</span><span class="sxs-lookup"><span data-stu-id="5a826-140">This example shows how to use the `Format-List` cmdlet to display a list of properties for a process object.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="5a826-141">使用几个实践，你会发现将简单命令合并到管道可节省时间和键入内容，并使你的脚本更有效。</span><span class="sxs-lookup"><span data-stu-id="5a826-141">With a bit of practice, you'll find that combining simple commands into pipelines saves time and typing, and makes your scripting more efficient.</span></span>

## <a name="how-pipelines-work"></a><span data-ttu-id="5a826-142">管道的工作方式</span><span class="sxs-lookup"><span data-stu-id="5a826-142">How pipelines work</span></span>

<span data-ttu-id="5a826-143">本部分介绍如何将输入对象绑定到 cmdlet 参数并在管道执行期间进行处理。</span><span class="sxs-lookup"><span data-stu-id="5a826-143">This section explains how input objects are bound to cmdlet parameters and processed during pipeline execution.</span></span>

### <a name="accepts-pipeline-input"></a><span data-ttu-id="5a826-144">接受管道输入</span><span class="sxs-lookup"><span data-stu-id="5a826-144">Accepts pipeline input</span></span>

<span data-ttu-id="5a826-145">若要支持流水线，接收 cmdlet 必须具有接受管道输入的参数。</span><span class="sxs-lookup"><span data-stu-id="5a826-145">To support pipelining, the receiving cmdlet must have a parameter that accepts pipeline input.</span></span> <span data-ttu-id="5a826-146">使用 `Get-Help` 带有 **Full** 或 **Parameter** 选项的命令来确定 cmdlet 接受管道输入的参数。</span><span class="sxs-lookup"><span data-stu-id="5a826-146">Use the `Get-Help` command with the **Full** or **Parameter** options to determine which parameters of a cmdlet accept pipeline input.</span></span>

<span data-ttu-id="5a826-147">例如，若要确定 cmdlet 的哪些参数 `Start-Service` 接受管道输入，请键入：</span><span class="sxs-lookup"><span data-stu-id="5a826-147">For example, to determine which of the parameters of the `Start-Service` cmdlet accepts pipeline input, type:</span></span>

```powershell
Get-Help Start-Service -Full
```

<span data-ttu-id="5a826-148">或</span><span class="sxs-lookup"><span data-stu-id="5a826-148">or</span></span>

```powershell
Get-Help Start-Service -Parameter *
```

<span data-ttu-id="5a826-149">Cmdlet 的帮助 `Start-Service` 显示：只有 **InputObject** 和 **Name** 参数接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="5a826-149">The help for the `Start-Service` cmdlet shows that only the **InputObject** and **Name** parameters accept pipeline input.</span></span>

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

<span data-ttu-id="5a826-150">当你通过管道将对象发送到时 `Start-Service` ，PowerShell 会尝试将对象与 **InputObject** 和 **Name** 参数相关联。</span><span class="sxs-lookup"><span data-stu-id="5a826-150">When you send objects through the pipeline to `Start-Service`, PowerShell attempts to associate the objects with the **InputObject** and **Name** parameters.</span></span>

### <a name="methods-of-accepting-pipeline-input"></a><span data-ttu-id="5a826-151">接受管道输入的方法</span><span class="sxs-lookup"><span data-stu-id="5a826-151">Methods of accepting pipeline input</span></span>

<span data-ttu-id="5a826-152">Cmdlet 参数可采用以下两种不同方式之一接受管道输入：</span><span class="sxs-lookup"><span data-stu-id="5a826-152">Cmdlets parameters can accept pipeline input in one of two different ways:</span></span>

- <span data-ttu-id="5a826-153">**ByValue** ：参数接受与所需的 .net 类型匹配或可转换为该类型的值。</span><span class="sxs-lookup"><span data-stu-id="5a826-153">**ByValue** : The parameter accepts values that match the expected .NET type or that can be converted to that type.</span></span>

  <span data-ttu-id="5a826-154">例如，的 **Name** 参数 `Start-Service` 接受按值的管道输入。</span><span class="sxs-lookup"><span data-stu-id="5a826-154">For example, the **Name** parameter of `Start-Service` accepts pipeline input by value.</span></span> <span data-ttu-id="5a826-155">它可以接受可以转换为字符串的字符串对象或对象。</span><span class="sxs-lookup"><span data-stu-id="5a826-155">It can accept string objects or objects that can be converted to strings.</span></span>

- <span data-ttu-id="5a826-156">**ByPropertyName** ：仅当输入对象具有与参数名称相同的属性时，此参数才接受输入。</span><span class="sxs-lookup"><span data-stu-id="5a826-156">**ByPropertyName** : The parameter accepts input only when the input object has a property of the same name as the parameter.</span></span>

  <span data-ttu-id="5a826-157">例如，的 Name 参数 `Start-Service` 可以接受具有 **Name** 属性的对象。</span><span class="sxs-lookup"><span data-stu-id="5a826-157">For example, the Name parameter of `Start-Service` can accept objects that have a **Name** property.</span></span> <span data-ttu-id="5a826-158">若要列出某个对象的属性，请将其传递到 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="5a826-158">To list the properties of an object, pipe it to `Get-Member`.</span></span>

<span data-ttu-id="5a826-159">一些参数可以通过值或属性名称接受对象，使从管道中获取输入变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="5a826-159">Some parameters can accept objects by both value or property name, making it easier to take input from the pipeline.</span></span>

### <a name="parameter-binding"></a><span data-ttu-id="5a826-160">参数绑定</span><span class="sxs-lookup"><span data-stu-id="5a826-160">Parameter binding</span></span>

<span data-ttu-id="5a826-161">当你通过管道将对象从一个命令传递给另一个命令时，PowerShell 会尝试将管道对象与接收 cmdlet 的参数相关联。</span><span class="sxs-lookup"><span data-stu-id="5a826-161">When you pipe objects from one command to another command, PowerShell attempts to associate the piped objects with a parameter of the receiving cmdlet.</span></span>

<span data-ttu-id="5a826-162">PowerShell 的参数绑定组件根据以下条件将输入对象与 cmdlet 参数关联：</span><span class="sxs-lookup"><span data-stu-id="5a826-162">PowerShell's parameter binding component associates the input objects with cmdlet parameters according to the following criteria:</span></span>

- <span data-ttu-id="5a826-163">参数必须接受来自管道的输入。</span><span class="sxs-lookup"><span data-stu-id="5a826-163">The parameter must accept input from a pipeline.</span></span>
- <span data-ttu-id="5a826-164">参数必须接受要发送的对象的类型或可转换为预期类型的类型。</span><span class="sxs-lookup"><span data-stu-id="5a826-164">The parameter must accept the type of object being sent or a type that can be converted to the expected type.</span></span>
- <span data-ttu-id="5a826-165">命令中未使用参数。</span><span class="sxs-lookup"><span data-stu-id="5a826-165">The parameter wasn't used in the command.</span></span>

<span data-ttu-id="5a826-166">例如， `Start-Service` cmdlet 具有多个参数，但其中只有两个参数、 **名称** 和 **InputObject** 接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="5a826-166">For example, the `Start-Service` cmdlet has many parameters, but only two of them, **Name** and **InputObject** accept pipeline input.</span></span> <span data-ttu-id="5a826-167">**Name** 参数使用字符串， **InputObject** 参数使用服务对象。</span><span class="sxs-lookup"><span data-stu-id="5a826-167">The **Name** parameter takes strings and the **InputObject** parameter takes service objects.</span></span> <span data-ttu-id="5a826-168">因此，可以通过管道字符串、服务对象和具有可转换为字符串或服务对象的属性的对象。</span><span class="sxs-lookup"><span data-stu-id="5a826-168">Therefore, you can pipe strings, service objects, and objects with properties that can be converted to string or service objects.</span></span>

<span data-ttu-id="5a826-169">PowerShell 会尽可能有效地管理参数绑定。</span><span class="sxs-lookup"><span data-stu-id="5a826-169">PowerShell manages parameter binding as efficiently as possible.</span></span> <span data-ttu-id="5a826-170">不能建议或强制 PowerShell 绑定到特定参数。</span><span class="sxs-lookup"><span data-stu-id="5a826-170">You can't suggest or force the PowerShell to bind to a specific parameter.</span></span> <span data-ttu-id="5a826-171">如果 PowerShell 无法绑定管道对象，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="5a826-171">The command fails if PowerShell can't bind the piped objects.</span></span>

<span data-ttu-id="5a826-172">有关排除绑定错误的详细信息，请参阅本文后面的 [调查管道错误](#investigating-pipeline-errors) 。</span><span class="sxs-lookup"><span data-stu-id="5a826-172">For more information about troubleshooting binding errors, see [Investigating Pipeline Errors](#investigating-pipeline-errors) later in this article.</span></span>

### <a name="one-at-a-time-processing"></a><span data-ttu-id="5a826-173">一次一次性处理</span><span class="sxs-lookup"><span data-stu-id="5a826-173">One-at-a-time processing</span></span>

<span data-ttu-id="5a826-174">通过管道将对象传递给命令与使用命令的参数来提交对象非常类似。</span><span class="sxs-lookup"><span data-stu-id="5a826-174">Piping objects to a command is much like using a parameter of the command to submit the objects.</span></span> <span data-ttu-id="5a826-175">让我们看一看管道示例。</span><span class="sxs-lookup"><span data-stu-id="5a826-175">Let's look at a pipeline example.</span></span> <span data-ttu-id="5a826-176">在此示例中，我们使用管道来显示服务对象表。</span><span class="sxs-lookup"><span data-stu-id="5a826-176">In this example, we use a pipeline to display a table of service objects.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="5a826-177">在功能上，这与使用的 **InputObject** 参数 `Format-Table` 来提交对象集合类似。</span><span class="sxs-lookup"><span data-stu-id="5a826-177">Functionally, this is like using the **InputObject** parameter of `Format-Table` to submit the object collection.</span></span>

<span data-ttu-id="5a826-178">例如，我们可以将服务集合保存到使用 **InputObject** 参数传递的变量。</span><span class="sxs-lookup"><span data-stu-id="5a826-178">For example, we can save the collection of services to a variable that is passed using the **InputObject** parameter.</span></span>

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

<span data-ttu-id="5a826-179">或者，可以将该命令嵌入到 **InputObject** 参数中。</span><span class="sxs-lookup"><span data-stu-id="5a826-179">Or we can embed the command in the **InputObject** parameter.</span></span>

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

<span data-ttu-id="5a826-180">但有一个重要的差异。</span><span class="sxs-lookup"><span data-stu-id="5a826-180">However, there's an important difference.</span></span> <span data-ttu-id="5a826-181">通过管道将多个对象传递给命令时，PowerShell 会一次将对象发送到命令。</span><span class="sxs-lookup"><span data-stu-id="5a826-181">When you pipe multiple objects to a command, PowerShell sends the objects to the command one at a time.</span></span> <span data-ttu-id="5a826-182">使用命令参数时，对象将作为单个数组对象发送。</span><span class="sxs-lookup"><span data-stu-id="5a826-182">When you use a command parameter, the objects are sent as a single array object.</span></span> <span data-ttu-id="5a826-183">这种次要差别会产生重大后果。</span><span class="sxs-lookup"><span data-stu-id="5a826-183">This minor difference has significant consequences.</span></span>

<span data-ttu-id="5a826-184">执行管道时，PowerShell 会自动枚举任何实现接口的类型 `IEnumerable` ，并一次通过管道发送成员。</span><span class="sxs-lookup"><span data-stu-id="5a826-184">When executing a pipeline, PowerShell automatically enumerates any type that implements the `IEnumerable` interface and sends the members through the pipeline one at a time.</span></span> <span data-ttu-id="5a826-185">异常是 `[hashtable]` ，这需要调用 `GetEnumerator()` 方法。</span><span class="sxs-lookup"><span data-stu-id="5a826-185">The exception is `[hashtable]`, which requires a call to the `GetEnumerator()` method.</span></span>

<span data-ttu-id="5a826-186">在下面的示例中，将向 cmdlet 传递一个数组和一个哈希表， `Measure-Object` 以计算从管道接收的对象数。</span><span class="sxs-lookup"><span data-stu-id="5a826-186">In the following examples, an array and a hashtable are piped to the `Measure-Object` cmdlet to count the number of objects received from the pipeline.</span></span> <span data-ttu-id="5a826-187">该数组具有多个成员，并且哈希表具有多个键值对。</span><span class="sxs-lookup"><span data-stu-id="5a826-187">The array has multiple members, and the hashtable has multiple key-value pairs.</span></span> <span data-ttu-id="5a826-188">一次只枚举一个数组。</span><span class="sxs-lookup"><span data-stu-id="5a826-188">Only the array is enumerated one at a time.</span></span>

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="5a826-189">同样，如果你通过管道将多个进程对象传递 `Get-Process` 给 `Get-Member` cmdlet，则 PowerShell 会将每个进程对象一次发送到 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="5a826-189">Similarly, if you pipe multiple process objects from the `Get-Process` cmdlet to the `Get-Member` cmdlet, PowerShell sends each process object, one at a time, to `Get-Member`.</span></span> <span data-ttu-id="5a826-190">`Get-Member` 显示 (类型的 .NET 类) 进程对象及其属性和方法。</span><span class="sxs-lookup"><span data-stu-id="5a826-190">`Get-Member` displays the .NET class (type) of the process objects, and their properties and methods.</span></span>

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> <span data-ttu-id="5a826-191">`Get-Member` 消除重复项，因此，如果所有对象都属于同一类型，则它只显示一种对象类型。</span><span class="sxs-lookup"><span data-stu-id="5a826-191">`Get-Member` eliminates duplicates, so if the objects are all of the same type, it only displays one object type.</span></span>

<span data-ttu-id="5a826-192">但是，如果使用的 **InputObject** 参数 `Get-Member` ，则会将 `Get-Member` **system.object** 对象的数组作为单个单元接收。</span><span class="sxs-lookup"><span data-stu-id="5a826-192">However, if you use the **InputObject** parameter of `Get-Member`, then `Get-Member` receives an array of **System.Diagnostics.Process** objects as a single unit.</span></span> <span data-ttu-id="5a826-193">它显示对象数组的属性。</span><span class="sxs-lookup"><span data-stu-id="5a826-193">It displays the properties of an array of objects.</span></span> <span data-ttu-id="5a826-194"> (记下 array 符号 (在 `[]` **system.object** 类型名称后面) 。 ) </span><span class="sxs-lookup"><span data-stu-id="5a826-194">(Note the array symbol (`[]`) after the **System.Object** type name.)</span></span>

<span data-ttu-id="5a826-195">例如，</span><span class="sxs-lookup"><span data-stu-id="5a826-195">For example,</span></span>

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

<span data-ttu-id="5a826-196">此结果可能不是你所期望的结果。</span><span class="sxs-lookup"><span data-stu-id="5a826-196">This result might not be what you intended.</span></span> <span data-ttu-id="5a826-197">但在理解后，就可以使用它了。</span><span class="sxs-lookup"><span data-stu-id="5a826-197">But after you understand it, you can use it.</span></span> <span data-ttu-id="5a826-198">例如，所有数组对象都具有 **Count** 属性。</span><span class="sxs-lookup"><span data-stu-id="5a826-198">For example, all array objects have a **Count** property.</span></span> <span data-ttu-id="5a826-199">可以使用它来计算计算机上运行的进程数。</span><span class="sxs-lookup"><span data-stu-id="5a826-199">You can use that to count the number of processes running on the computer.</span></span>

<span data-ttu-id="5a826-200">例如，</span><span class="sxs-lookup"><span data-stu-id="5a826-200">For example,</span></span>

```powershell
(Get-Process).count
```

<span data-ttu-id="5a826-201">请务必记住，在管道中发送的对象每次传递一次。</span><span class="sxs-lookup"><span data-stu-id="5a826-201">It's important to remember that objects sent down the pipeline are delivered one at a time.</span></span>

## <a name="investigating-pipeline-errors"></a><span data-ttu-id="5a826-202">调查管道错误</span><span class="sxs-lookup"><span data-stu-id="5a826-202">Investigating pipeline errors</span></span>

<span data-ttu-id="5a826-203">当 PowerShell 无法将管道对象与接收 cmdlet 的参数关联时，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="5a826-203">When PowerShell can't associate the piped objects with a parameter of the receiving cmdlet, the command fails.</span></span>

<span data-ttu-id="5a826-204">在下面的示例中，我们尝试将注册表项从一个注册表项移到另一个注册表项。</span><span class="sxs-lookup"><span data-stu-id="5a826-204">In the following example, we try to move a registry entry from one registry key to another.</span></span> <span data-ttu-id="5a826-205">该 `Get-Item` cmdlet 将获取目标路径，然后将该路径传递给 `Move-ItemProperty` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a826-205">The `Get-Item` cmdlet gets the destination path, which is then piped to the `Move-ItemProperty` cmdlet.</span></span> <span data-ttu-id="5a826-206">`Move-ItemProperty`命令指定要移动的注册表项的当前路径和名称。</span><span class="sxs-lookup"><span data-stu-id="5a826-206">The `Move-ItemProperty` command specifies the current path and name of the registry entry to be moved.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

<span data-ttu-id="5a826-207">命令失败，PowerShell 将显示以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="5a826-207">The command fails and PowerShell displays the following error message:</span></span>

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

<span data-ttu-id="5a826-208">若要进行调查，请使用 `Trace-Command` cmdlet 跟踪 PowerShell 的参数绑定组件。</span><span class="sxs-lookup"><span data-stu-id="5a826-208">To investigate, use the `Trace-Command` cmdlet to trace the parameter binding component of PowerShell.</span></span> <span data-ttu-id="5a826-209">下面的示例跟踪管道的执行过程中的参数绑定。</span><span class="sxs-lookup"><span data-stu-id="5a826-209">The following example traces parameter binding while the pipeline is executing.</span></span> <span data-ttu-id="5a826-210">**PSHost** 参数将跟踪结果显示在控制台中， **FilePath** 参数会将跟踪结果发送到 `debug.txt` 文件，供以后参考。</span><span class="sxs-lookup"><span data-stu-id="5a826-210">The **PSHost** parameter displays the trace results in the console and the **FilePath** parameter send the trace results to the `debug.txt` file for later reference.</span></span>

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

<span data-ttu-id="5a826-211">跟踪的结果很长，但会显示绑定到 cmdlet 的值，然后显示 `Get-Item` 绑定到 cmdlet 的命名值 `Move-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="5a826-211">The results of the trace are lengthy, but they show the values being bound to the `Get-Item` cmdlet and then the named values being bound to the `Move-ItemProperty` cmdlet.</span></span>

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

<span data-ttu-id="5a826-212">最后，它显示尝试将路径绑定到的 **目标** 参数 `Move-ItemProperty` 失败。</span><span class="sxs-lookup"><span data-stu-id="5a826-212">Finally, it shows that the attempt to bind the path to the **Destination** parameter of `Move-ItemProperty` failed.</span></span>

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

<span data-ttu-id="5a826-213">使用 `Get-Help` cmdlet 查看 **目标** 参数的属性。</span><span class="sxs-lookup"><span data-stu-id="5a826-213">Use the `Get-Help` cmdlet to view the attributes of the **Destination** parameter.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

<span data-ttu-id="5a826-214">结果显示 **目标** 仅按属性名称获取管道输入。</span><span class="sxs-lookup"><span data-stu-id="5a826-214">The results show that **Destination** takes pipeline input only "by property name".</span></span> <span data-ttu-id="5a826-215">因此，管道对象必须具有一个名为 " **Destination** " 的属性。</span><span class="sxs-lookup"><span data-stu-id="5a826-215">Therefore, the piped object must have a property named **Destination** .</span></span>

<span data-ttu-id="5a826-216">使用 `Get-Member` 可查看来自的对象的属性 `Get-Item` 。</span><span class="sxs-lookup"><span data-stu-id="5a826-216">Use `Get-Member` to see the properties of the object coming from `Get-Item`.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

<span data-ttu-id="5a826-217">输出显示该项目是没有 **目标** 属性的 **Microsoft. Win32** 对象。</span><span class="sxs-lookup"><span data-stu-id="5a826-217">The output shows that the item is a **Microsoft.Win32.RegistryKey** object that doesn't have a **Destination** property.</span></span> <span data-ttu-id="5a826-218">这说明了命令失败的原因。</span><span class="sxs-lookup"><span data-stu-id="5a826-218">That explains why the command failed.</span></span>

<span data-ttu-id="5a826-219">**Path** 参数按名称或值接受管道输入。</span><span class="sxs-lookup"><span data-stu-id="5a826-219">The **Path** parameter accepts pipeline input by name or by value.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

<span data-ttu-id="5a826-220">若要修复此命令，必须在 cmdlet 中指定目标 `Move-ItemProperty` ，并使用 `Get-Item` 获取要移动的项的 **路径** 。</span><span class="sxs-lookup"><span data-stu-id="5a826-220">To fix the command, we must specify the destination in the `Move-ItemProperty` cmdlet and use `Get-Item` to get the **Path** of the item we want to move.</span></span>

<span data-ttu-id="5a826-221">例如，</span><span class="sxs-lookup"><span data-stu-id="5a826-221">For example,</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a><span data-ttu-id="5a826-222">内部续行符</span><span class="sxs-lookup"><span data-stu-id="5a826-222">Intrinsic line continuation</span></span>

<span data-ttu-id="5a826-223">正如前面所讨论的，管道是一系列由管道运算符连接的命令 (`|`) ，通常在一行上写入。</span><span class="sxs-lookup"><span data-stu-id="5a826-223">As already discussed, a pipeline is a series of commands connected by pipeline operators (`|`), usually written on a single line.</span></span> <span data-ttu-id="5a826-224">但是，为了提高可读性，PowerShell 允许跨多个行拆分管道。</span><span class="sxs-lookup"><span data-stu-id="5a826-224">However, for readability, PowerShell allows you to split the pipeline across multiple lines.</span></span>
<span data-ttu-id="5a826-225">当管道运算符是行上的最后一个标记时，PowerShell 分析器会将下一行连接到当前命令以继续构造管道。</span><span class="sxs-lookup"><span data-stu-id="5a826-225">When a pipe operator is the last token on the line, the PowerShell parser joins the next line to current command to continue the construction of the pipeline.</span></span>

<span data-ttu-id="5a826-226">例如，以下单行管道：</span><span class="sxs-lookup"><span data-stu-id="5a826-226">For example, the following single-line pipeline:</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="5a826-227">可以编写为：</span><span class="sxs-lookup"><span data-stu-id="5a826-227">can be written as:</span></span>

```powershell
Command-1 |
  Command-2 |
    Command-3
```

<span data-ttu-id="5a826-228">后续行中的前导空格并不重要。</span><span class="sxs-lookup"><span data-stu-id="5a826-228">The leading spaces on the subsequent lines are not significant.</span></span> <span data-ttu-id="5a826-229">缩进增强了可读性。</span><span class="sxs-lookup"><span data-stu-id="5a826-229">The indentation enhances readability.</span></span>

<span data-ttu-id="5a826-230">PowerShell 7 增加了对管道的延续的支持，并在行的开头提供管道字符。</span><span class="sxs-lookup"><span data-stu-id="5a826-230">PowerShell 7 adds support for continuation of pipelines with the pipeline character at the beginning of a line.</span></span> <span data-ttu-id="5a826-231">下面的示例演示如何使用此新功能。</span><span class="sxs-lookup"><span data-stu-id="5a826-231">The following examples show how you could use this new functionality.</span></span>

```powershell
# Wrapping with a pipe at the beginning of a line (no backtick required)
Get-Process | Where-Object CPU | Where-Object Path
    | Get-Item | Where-Object FullName -match "AppData"
    | Sort-Object FullName -Unique

# Wrapping with a pipe on a line by itself
Get-Process | Where-Object CPU | Where-Object Path
    |
    Get-Item | Where-Object FullName -match "AppData"
    |
    Sort-Object FullName -Unique
```

> [!IMPORTANT]
> <span data-ttu-id="5a826-232">在 shell 中以交互方式工作时，仅当使用<kbd>Ctrl</kbd> + <kbd>V</kbd>粘贴时，才将代码粘贴到行的开头。</span><span class="sxs-lookup"><span data-stu-id="5a826-232">When working interactively in the shell, pasting code with pipelines at the beginning of a line only when using <kbd>Ctrl</kbd>+<kbd>V</kbd> to paste.</span></span>
> <span data-ttu-id="5a826-233">右键单击 "粘贴操作"，一次插入一个行。</span><span class="sxs-lookup"><span data-stu-id="5a826-233">Right-click paste operations insert the lines one at a time.</span></span> <span data-ttu-id="5a826-234">因为行不以管道字符结尾，所以 PowerShell 会将输入视为已完成，并按输入执行该行。</span><span class="sxs-lookup"><span data-stu-id="5a826-234">Since the line does not end with a pipeline character, PowerShell considers the input to be complete and executes that line as entered.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a826-235">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a826-235">See Also</span></span>

[<span data-ttu-id="5a826-236">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="5a826-236">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="5a826-237">about_Objects</span><span class="sxs-lookup"><span data-stu-id="5a826-237">about_Objects</span></span>](about_objects.md)

[<span data-ttu-id="5a826-238">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="5a826-238">about_Parameters</span></span>](about_parameters.md)

[<span data-ttu-id="5a826-239">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="5a826-239">about_Command_Syntax</span></span>](about_command_syntax.md)

[<span data-ttu-id="5a826-240">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="5a826-240">about_ForEach</span></span>](about_foreach.md)
