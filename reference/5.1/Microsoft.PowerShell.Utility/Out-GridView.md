---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 473571aa73d9b9331545b80cb5949e7a83c26eff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197876"
---
# <span data-ttu-id="89996-103">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="89996-103">Out-GridView</span></span>

## <span data-ttu-id="89996-104">摘要</span><span class="sxs-lookup"><span data-stu-id="89996-104">SYNOPSIS</span></span>
<span data-ttu-id="89996-105">将输出发送到单独窗口中的交互式表中。</span><span class="sxs-lookup"><span data-stu-id="89996-105">Sends output to an interactive table in a separate window.</span></span>

## <span data-ttu-id="89996-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89996-106">SYNTAX</span></span>

### <span data-ttu-id="89996-107">PassThru (默认值) </span><span class="sxs-lookup"><span data-stu-id="89996-107">PassThru (Default)</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="89996-108">Wait</span><span class="sxs-lookup"><span data-stu-id="89996-108">Wait</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### <span data-ttu-id="89996-109">OutputMode</span><span class="sxs-lookup"><span data-stu-id="89996-109">OutputMode</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## <span data-ttu-id="89996-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89996-110">DESCRIPTION</span></span>

<span data-ttu-id="89996-111">`Out-GridView`Cmdlet 将命令的输出发送到网格视图窗口，其中的输出显示在交互式表中。</span><span class="sxs-lookup"><span data-stu-id="89996-111">The `Out-GridView` cmdlet sends the output from a command to a grid view window where the output is displayed in an interactive table.</span></span>

<span data-ttu-id="89996-112">由于此 cmdlet 需要用户界面，因此它在 Windows Server Core 或 Windows Nano Server 上不起作用。</span><span class="sxs-lookup"><span data-stu-id="89996-112">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span>

<span data-ttu-id="89996-113">你可以使用该表的以下功能检查你的数据：</span><span class="sxs-lookup"><span data-stu-id="89996-113">You can use the following features of the table to examine your data:</span></span>

- <span data-ttu-id="89996-114">隐藏、显示和重新排列列</span><span class="sxs-lookup"><span data-stu-id="89996-114">Hide, Show, and Reorder Columns</span></span>
- <span data-ttu-id="89996-115">对行进行排序</span><span class="sxs-lookup"><span data-stu-id="89996-115">Sort rows</span></span>
- <span data-ttu-id="89996-116">快速筛选器</span><span class="sxs-lookup"><span data-stu-id="89996-116">Quick Filter</span></span>
- <span data-ttu-id="89996-117">添加条件筛选器</span><span class="sxs-lookup"><span data-stu-id="89996-117">Add Criteria Filter</span></span>
- <span data-ttu-id="89996-118">复制和粘贴</span><span class="sxs-lookup"><span data-stu-id="89996-118">Copy and paste</span></span>

<span data-ttu-id="89996-119">有关完整说明，请参阅本文的 " [备注](#notes) " 部分。</span><span class="sxs-lookup"><span data-stu-id="89996-119">For full instructions, see the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="89996-120">示例</span><span class="sxs-lookup"><span data-stu-id="89996-120">EXAMPLES</span></span>

### <span data-ttu-id="89996-121">示例1：将进程输出到网格视图</span><span class="sxs-lookup"><span data-stu-id="89996-121">Example 1: Output processes to a grid view</span></span>

<span data-ttu-id="89996-122">此示例将获取在本地计算机上运行的进程，并将其发送到网格视图窗口。</span><span class="sxs-lookup"><span data-stu-id="89996-122">This example gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
Get-Process | Out-GridView
```

### <span data-ttu-id="89996-123">示例2：使用变量将进程输出到网格视图</span><span class="sxs-lookup"><span data-stu-id="89996-123">Example 2: Use a variable to output processes to a grid view</span></span>

<span data-ttu-id="89996-124">此示例还将获取在本地计算机上运行的进程，并将其发送到网格视图窗口。</span><span class="sxs-lookup"><span data-stu-id="89996-124">This example also gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
$P = Get-Process
$P | Out-GridView
```

<span data-ttu-id="89996-125">Cmdlet 的输出 `Get-Process` 保存在 `$P` 变量中。</span><span class="sxs-lookup"><span data-stu-id="89996-125">The output of the `Get-Process` cmdlet is saved in the `$P` variable.</span></span> <span data-ttu-id="89996-126">然后， `$P` 将传递给 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-126">Then, `$P` is piped to `Out-GridView`.</span></span>

### <span data-ttu-id="89996-127">示例3：在网格视图中显示所选属性</span><span class="sxs-lookup"><span data-stu-id="89996-127">Example 3: Display a selected properties in a grid view</span></span>

<span data-ttu-id="89996-128">此示例在网格视图中显示正在运行的进程的选定属性。</span><span class="sxs-lookup"><span data-stu-id="89996-128">This example displays selected properties of the running processes in a grid view.</span></span>

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

<span data-ttu-id="89996-129">的输出 `Get-Process` 将输送到， `Select-Object` 以选择 **名称** 、工作 **WorkingSet** 集和 **PeakWorkingSet** 属性。</span><span class="sxs-lookup"><span data-stu-id="89996-129">The output of `Get-Process` is piped to `Select-Object` to select the **Name** , **WorkingSet** , and **PeakWorkingSet** properties.</span></span> <span data-ttu-id="89996-130">另一个管道运算符将筛选的对象发送到 `Sort-Object` cmdlet，以按工作集属性的值降序对 **WorkingSet** 它们进行排序。</span><span class="sxs-lookup"><span data-stu-id="89996-130">Another pipeline operator sends the filtered objects to the `Sort-Object` cmdlet to sort them in descending order by the value of the **WorkingSet** property.</span></span>
<span data-ttu-id="89996-131">然后，将排序结果传递给 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-131">Then, the sorted results are piped to `Out-GridView`.</span></span> <span data-ttu-id="89996-132">你现在可以使用网格视图的功能搜索、排序和筛选数据。</span><span class="sxs-lookup"><span data-stu-id="89996-132">You can now use the features of the grid view to search, sort, and filter the data.</span></span>

### <span data-ttu-id="89996-133">示例4：将输出保存到变量，然后输出网格视图</span><span class="sxs-lookup"><span data-stu-id="89996-133">Example 4: Save output to a variable, and then output a grid view</span></span>

<span data-ttu-id="89996-134">此示例将 cmdlet 输出保存在一个变量中，然后将其发送到 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-134">This example saves cmdlet output in a variable then sends it to `Out-GridView`.</span></span>

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

<span data-ttu-id="89996-135">`Get-ChildItem` 使用自动变量获取 PowerShell 安装目录及其子目录中的所有文件 `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="89996-135">`Get-ChildItem` gets all the files in the PowerShell installation directory and its subdirectories using the the `$PSHOME` automatic variable.</span></span> <span data-ttu-id="89996-136">命令中的括号可建立操作的顺序。</span><span class="sxs-lookup"><span data-stu-id="89996-136">The parentheses in the command establish the order of operations.</span></span> <span data-ttu-id="89996-137">因此，该命令的输出 `Get-ChildItem` 保存在变量中， `$A` 然后再将其发送到 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-137">As a result, the output from the `Get-ChildItem` command is saved in the `$A` variable before it is sent to `Out-GridView`.</span></span>

### <span data-ttu-id="89996-138">示例5：将指定计算机的输出过程输出到网格视图</span><span class="sxs-lookup"><span data-stu-id="89996-138">Example 5: Output processes for a specified computer to a grid view</span></span>

<span data-ttu-id="89996-139">此示例在网格视图窗口中显示在 Server01 计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="89996-139">This example displays the processes that are running on the Server01 computer in a grid view window.</span></span>

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

<span data-ttu-id="89996-140">示例使用 `ogv` ，它是 cmdlet 的别名 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-140">The examle uses `ogv`, which is the alias for the `Out-GridView` cmdlet.</span></span> <span data-ttu-id="89996-141">**Title** 参数指定窗口标题。</span><span class="sxs-lookup"><span data-stu-id="89996-141">The **Title** parameter specifies the window title.</span></span>

### <span data-ttu-id="89996-142">示例6：将数据从远程计算机输出到网格视图</span><span class="sxs-lookup"><span data-stu-id="89996-142">Example 6: Output data from remote computers to a grid view</span></span>

<span data-ttu-id="89996-143">此示例演示如何将从远程计算机收集的数据发送到 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-143">This example shows how to send data collected from remote computers to `Out-GridView`.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

<span data-ttu-id="89996-144">`Invoke-Command``Get-Culture`在三台远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="89996-144">`Invoke-Command` runs `Get-Culture` on three remote computers.</span></span> <span data-ttu-id="89996-145">生成的数据将通过管道传输到 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-145">The resulting data is piped to `Out-GridView`.</span></span> <span data-ttu-id="89996-146">请注意，在远程计算机上运行的脚本块不包含 `Out-GridView` 命令。</span><span class="sxs-lookup"><span data-stu-id="89996-146">Notice that the script block that runs on the remote computer does not include the `Out-GridView` command.</span></span> <span data-ttu-id="89996-147">如果包括该命令，则当它尝试在每台远程计算机上打开网格视图窗口时，该命令将会失败。</span><span class="sxs-lookup"><span data-stu-id="89996-147">If it did, the command would fail when it tried to open a grid view window on each of the remote computers.</span></span>

### <span data-ttu-id="89996-148">示例7：通过传递多个项 `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="89996-148">Example 7: Pass multiple items through `Out-GridView`</span></span>

<span data-ttu-id="89996-149">此示例可让你从窗口中选择多个进程 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-149">This example lets you select multiple processes from the `Out-GridView` window.</span></span> <span data-ttu-id="89996-150">你选择的进程将传递到 `Export-Csv` 命令并写入到 `ProcessLog.csv` 文件中。</span><span class="sxs-lookup"><span data-stu-id="89996-150">The processes that you select are passed to the `Export-Csv` command and written to the `ProcessLog.csv` file.</span></span>

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

<span data-ttu-id="89996-151">**通过的 PassThru** 参数 `Out-GridView` ，可将多个项沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="89996-151">The **PassThru** parameter of `Out-GridView` lets you send multiple items down the pipeline.</span></span> <span data-ttu-id="89996-152">**PassThru** 参数等效于使用 **OutputMode** 参数的 **Multiple** 值。</span><span class="sxs-lookup"><span data-stu-id="89996-152">The **PassThru** parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

### <span data-ttu-id="89996-153">示例8：创建 Windows 快捷方式 `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="89996-153">Example 8: Create a Windows shortcut to `Out-GridView`</span></span>

<span data-ttu-id="89996-154">此示例演示如何使用的 **Wait** 参数 `Out-GridView` 创建窗口的窗口快捷方式 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-154">This example shows how to use the **Wait** parameter of `Out-GridView` to create a Windows shortcut to the `Out-GridView` window.</span></span>

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

<span data-ttu-id="89996-155">可在 Windows 快捷方式中使用此命令行。</span><span class="sxs-lookup"><span data-stu-id="89996-155">This command line can be used in a Windows shortcut.</span></span> <span data-ttu-id="89996-156">如果没有 **Wait** 参数，PowerShell 将在窗口打开后立即退出 `Out-GridView` ，这会 `Out-GridView` 立即关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="89996-156">Without the **Wait** parameter, PowerShell would exit as soon as the `Out-GridView` window opened, which would close the `Out-GridView` window almost immediately.</span></span>

## <span data-ttu-id="89996-157">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89996-157">PARAMETERS</span></span>

### <span data-ttu-id="89996-158">-InputObject</span><span class="sxs-lookup"><span data-stu-id="89996-158">-InputObject</span></span>

<span data-ttu-id="89996-159">指定 cmdlet 接受作为输入的对象 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-159">Specifies object that the cmdlet accepts as input for `Out-GridView`.</span></span>

<span data-ttu-id="89996-160">使用 **InputObject** 参数将对象集合发送到时 `Out-GridView` ， `Out-GridView` 会将该集合视为一个集合对象，并显示一个表示该集合的行。</span><span class="sxs-lookup"><span data-stu-id="89996-160">When you use the **InputObject** parameter to send a collection of objects to `Out-GridView`, `Out-GridView` treats the collection as one collection object, and it displays one row that represents the collection.</span></span> <span data-ttu-id="89996-161">若要显示集合中的每个对象，请使用管道运算符 (|要将对象发送到 `Out-GridView` 的) 。</span><span class="sxs-lookup"><span data-stu-id="89996-161">To display the each object in the collection, use a pipeline operator (|) to send objects to `Out-GridView`.</span></span>

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

### <span data-ttu-id="89996-162">-OutputMode</span><span class="sxs-lookup"><span data-stu-id="89996-162">-OutputMode</span></span>

<span data-ttu-id="89996-163">指定交互式窗口将管道向下发送到其他命令的输入的项。</span><span class="sxs-lookup"><span data-stu-id="89996-163">Specifies the items that the interactive window sends down the pipeline as input to other commands.</span></span>
<span data-ttu-id="89996-164">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="89996-164">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="89996-165">若要将交互式窗口中的项通过管道向下发送，请单击以选择项，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="89996-165">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span>

<span data-ttu-id="89996-166">此参数的值确定你可以通过管道向下发送多少项。</span><span class="sxs-lookup"><span data-stu-id="89996-166">The values of this parameter determine how many items you can send down the pipeline.</span></span>

- <span data-ttu-id="89996-167">无。</span><span class="sxs-lookup"><span data-stu-id="89996-167">None.</span></span>  <span data-ttu-id="89996-168">无项。</span><span class="sxs-lookup"><span data-stu-id="89996-168">No items.</span></span> <span data-ttu-id="89996-169">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="89996-169">This is the default value.</span></span>
- <span data-ttu-id="89996-170">单一。</span><span class="sxs-lookup"><span data-stu-id="89996-170">Single.</span></span> <span data-ttu-id="89996-171">零个项或一个项。</span><span class="sxs-lookup"><span data-stu-id="89996-171">Zero items or one item.</span></span> <span data-ttu-id="89996-172">当下一个命令只能获取一个输入对象时，使用此值。</span><span class="sxs-lookup"><span data-stu-id="89996-172">Use this value when the next command can take only one input object.</span></span>
- <span data-ttu-id="89996-173">多个.</span><span class="sxs-lookup"><span data-stu-id="89996-173">Multiple.</span></span> <span data-ttu-id="89996-174">零个、一个或多个项。</span><span class="sxs-lookup"><span data-stu-id="89996-174">Zero, one, or many items.</span></span> <span data-ttu-id="89996-175">当下一个命令可以获取多个输入对象时，使用此值。</span><span class="sxs-lookup"><span data-stu-id="89996-175">Use this value when the next command can take multiple input objects.</span></span> <span data-ttu-id="89996-176">此值等效于 **Passthru** 参数。</span><span class="sxs-lookup"><span data-stu-id="89996-176">This value is equivalent to the **Passthru** parameter.</span></span>

<span data-ttu-id="89996-177">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="89996-177">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputModeOption
Parameter Sets: OutputMode
Aliases:
Accepted values: None, Single, Multiple

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89996-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="89996-178">-PassThru</span></span>

<span data-ttu-id="89996-179">指示该 cmdlet 将交互窗口中的项作为输入通过管道向下发送到其他命令。</span><span class="sxs-lookup"><span data-stu-id="89996-179">Indicates that the cmdlet sends items from the interactive window down the pipeline as input to other commands.</span></span> <span data-ttu-id="89996-180">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="89996-180">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="89996-181">此参数等效于使用 **OutputMode** 参数的 **Multiple** 值。</span><span class="sxs-lookup"><span data-stu-id="89996-181">This parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

<span data-ttu-id="89996-182">若要将交互式窗口中的项通过管道向下发送，请单击以选择项，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="89996-182">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span> <span data-ttu-id="89996-183">支持 Shift 单击和 Ctrl 单击。</span><span class="sxs-lookup"><span data-stu-id="89996-183">Shift-click and Ctrl-click are supported.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PassThru
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89996-184">-Title</span><span class="sxs-lookup"><span data-stu-id="89996-184">-Title</span></span>

<span data-ttu-id="89996-185">指定在窗口的标题栏中显示的文本 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-185">Specifies the text that appears in the title bar of the `Out-GridView` window.</span></span> <span data-ttu-id="89996-186">默认情况下，标题栏将显示调用的命令 `Out-GridView` 。</span><span class="sxs-lookup"><span data-stu-id="89996-186">By default, the title bar displays the command that invokes `Out-GridView`.</span></span>

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

### <span data-ttu-id="89996-187">-Wait</span><span class="sxs-lookup"><span data-stu-id="89996-187">-Wait</span></span>

<span data-ttu-id="89996-188">指示此 cmdlet 禁止显示命令提示符，并阻止 Windows PowerShell 关闭，直到 `Out-GridView` 窗口关闭。</span><span class="sxs-lookup"><span data-stu-id="89996-188">Indicates that the cmdlet suppresses the command prompt and prevents Windows PowerShell from closing until the `Out-GridView` window is closed.</span></span> <span data-ttu-id="89996-189">默认情况下，当窗口打开时，命令提示符 `Out-GridView` 会返回。</span><span class="sxs-lookup"><span data-stu-id="89996-189">By default, the command prompt returns when the `Out-GridView` window opens.</span></span>

<span data-ttu-id="89996-190">此功能可让你 `Out-GridView` 在 Windows 快捷方式中使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="89996-190">This feature lets you use the `Out-GridView` cmdlets in Windows shortcuts.</span></span> <span data-ttu-id="89996-191">如果 `Out-GridView` 在没有 **Wait** 参数的快捷方式中使用，则该 `Out-GridView` 窗口仅在 PowerShell 关闭之前出现一段时间。</span><span class="sxs-lookup"><span data-stu-id="89996-191">When `Out-GridView` is used in a shortcut without the **Wait** parameter, the `Out-GridView` window appears only momentarily before PowerShell closes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Wait
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89996-192">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="89996-192">CommonParameters</span></span>

<span data-ttu-id="89996-193">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="89996-193">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89996-194">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="89996-194">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89996-195">输入</span><span class="sxs-lookup"><span data-stu-id="89996-195">INPUTS</span></span>

### <span data-ttu-id="89996-196">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="89996-196">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="89996-197">可以向此 cmdlet 发送任何对象。</span><span class="sxs-lookup"><span data-stu-id="89996-197">You can send any object to this cmdlet.</span></span>

## <span data-ttu-id="89996-198">输出</span><span class="sxs-lookup"><span data-stu-id="89996-198">OUTPUTS</span></span>

### <span data-ttu-id="89996-199">无</span><span class="sxs-lookup"><span data-stu-id="89996-199">None</span></span>

<span data-ttu-id="89996-200">通常，不 `Out-GridView` 返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="89996-200">Normally, `Out-GridView` does not return any objects.</span></span> <span data-ttu-id="89996-201">当使用 **PassThru** 参数时，表示所选行的对象将返回到管道中。</span><span class="sxs-lookup"><span data-stu-id="89996-201">When using the **PassThru** parameter, the objects representing the selected rows are returned to the pipeline.</span></span>

## <span data-ttu-id="89996-202">注释</span><span class="sxs-lookup"><span data-stu-id="89996-202">NOTES</span></span>

<span data-ttu-id="89996-203">你不能使用远程命令在另一台计算机上打开网格视图窗口。</span><span class="sxs-lookup"><span data-stu-id="89996-203">You cannot use a remote command to open a grid view window on another computer.</span></span>

<span data-ttu-id="89996-204">你发送到的命令输出 `Out-GridView` 不能使用 `Format` cmdlet （如或 cmdlet）进行格式设置 `Format-Table` `Format-Wide` 。</span><span class="sxs-lookup"><span data-stu-id="89996-204">The command output that you send to `Out-GridView` cannot be formatted using the `Format` cmdlets, such as `Format-Table` or `Format-Wide` cmdlets.</span></span> <span data-ttu-id="89996-205">若要选择属性，请使用 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="89996-205">To select properties, use the `Select-Object` cmdlet.</span></span>

<span data-ttu-id="89996-206">在网格视图窗口中，可能无法对来自远程命令的反序列化输出正确进行格式设置。</span><span class="sxs-lookup"><span data-stu-id="89996-206">Deserialized output from remote commands might not be formatted correctly in the grid view window.</span></span>

<span data-ttu-id="89996-207">**键盘快捷方式**`Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="89996-207">**Keyboard Shortcuts for** `Out-GridView`</span></span>

|              <span data-ttu-id="89996-208">使用此键：</span><span class="sxs-lookup"><span data-stu-id="89996-208">Use this key:</span></span>              |                                   <span data-ttu-id="89996-209">若要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="89996-209">To perform this action:</span></span>                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <span data-ttu-id="89996-210"><kbd>选项卡</kbd></span><span class="sxs-lookup"><span data-stu-id="89996-210"><kbd>Tab</kbd></span></span>                          | <span data-ttu-id="89996-211">将光标从 " **筛选器** " 框移到表的 " **添加条件** " 菜单，然后返回。</span><span class="sxs-lookup"><span data-stu-id="89996-211">Moves the cursor from the **Filter** box to the **Add criteria** menu to the table and back.</span></span> |
| <span data-ttu-id="89996-212"><kbd>向上键</kbd></span><span class="sxs-lookup"><span data-stu-id="89996-212"><kbd>UpArrow</kbd></span></span>                      | <span data-ttu-id="89996-213">向上移动一行。</span><span class="sxs-lookup"><span data-stu-id="89996-213">Move up one row.</span></span> <span data-ttu-id="89996-214">从数据的第一行移到列标题。</span><span class="sxs-lookup"><span data-stu-id="89996-214">Moves to column headers from first row of data.</span></span>                             |
| <span data-ttu-id="89996-215"><kbd>向下键</kbd></span><span class="sxs-lookup"><span data-stu-id="89996-215"><kbd>DownArrow</kbd></span></span>                    | <span data-ttu-id="89996-216">向下移动一行。</span><span class="sxs-lookup"><span data-stu-id="89996-216">Move down one row.</span></span>                                                                           |
| <span data-ttu-id="89996-217"><kbd>向左键</kbd></span><span class="sxs-lookup"><span data-stu-id="89996-217"><kbd>LeftArrow</kbd></span></span>                    | <span data-ttu-id="89996-218">在列标题行中，向左移动一列。</span><span class="sxs-lookup"><span data-stu-id="89996-218">In column header row, move left one column.</span></span>                                                  |
| <span data-ttu-id="89996-219"><kbd>右箭头</kbd></span><span class="sxs-lookup"><span data-stu-id="89996-219"><kbd>RightArrow</kbd></span></span>                   | <span data-ttu-id="89996-220">在列标题行中，右移一列。</span><span class="sxs-lookup"><span data-stu-id="89996-220">In column header row, move right one column.</span></span>                                                 |
| <span data-ttu-id="89996-221"><kbd>ContextMenuKey</kbd></span><span class="sxs-lookup"><span data-stu-id="89996-221"><kbd>ContextMenuKey</kbd></span></span>               | <span data-ttu-id="89996-222">在 "列标题行" 中，显示 "选择列" 选项。</span><span class="sxs-lookup"><span data-stu-id="89996-222">In column header row, displays the Select Columns option.</span></span>                                    |
| <span data-ttu-id="89996-223"><kbd>Enter</kbd> 或 <kbd>空格键</kbd></span><span class="sxs-lookup"><span data-stu-id="89996-223"><kbd>Enter</kbd> or <kbd>Spacebar</kbd></span></span> | <span data-ttu-id="89996-224">在列标题行中，对列数据进行排序 (切换 a-z，Z-A) 。</span><span class="sxs-lookup"><span data-stu-id="89996-224">In column header row, sort column data (toggle A-Z, Z-A).</span></span>                                    |

<span data-ttu-id="89996-225">**如何使用网格视图窗口功能**</span><span class="sxs-lookup"><span data-stu-id="89996-225">**How to Use the Grid View Window Features**</span></span>

<span data-ttu-id="89996-226">**若要隐藏或显示列：**</span><span class="sxs-lookup"><span data-stu-id="89996-226">**To hide or show a column:**</span></span>

1. <span data-ttu-id="89996-227">右键单击任何列标题，然后单击 " **选择列** "。</span><span class="sxs-lookup"><span data-stu-id="89996-227">Right-click any column header and click **Select Columns** .</span></span>
2. <span data-ttu-id="89996-228">在 " **选择列** " 对话框中，使用箭头键将所选列之间的列移动到 "可用的列" 框中。</span><span class="sxs-lookup"><span data-stu-id="89996-228">In the **Select Columns** dialog box, use the arrow keys to move the columns between the Selected columns to the Available columns boxes.</span></span> <span data-ttu-id="89996-229">网格视图窗口中仅显示 " **选择列** " 框中的列。</span><span class="sxs-lookup"><span data-stu-id="89996-229">Only columns in the **Select Columns** box appear in the grid view window.</span></span>

<span data-ttu-id="89996-230">**若要重新排序列：**</span><span class="sxs-lookup"><span data-stu-id="89996-230">**To reorder columns:**</span></span>

<span data-ttu-id="89996-231">您可以将列拖放到所需的位置。</span><span class="sxs-lookup"><span data-stu-id="89996-231">You can drag and drop columns into the desired location.</span></span> <span data-ttu-id="89996-232">或使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="89996-232">Or use the following steps:</span></span>

1. <span data-ttu-id="89996-233">右键单击任何列标题，然后单击 " **选择列** "。</span><span class="sxs-lookup"><span data-stu-id="89996-233">Right-click any column header and click **Select Columns** .</span></span>
2. <span data-ttu-id="89996-234">在 " **选择列** " 对话框中，使用 " **上移** **" 和 "下移"** 按钮对列进行重新排序。</span><span class="sxs-lookup"><span data-stu-id="89996-234">In the **Select Columns** dialog box, use the **Move up** and **Move down** buttons to reorder the columns.</span></span> <span data-ttu-id="89996-235">列表顶部的列显示在网格视图窗口中列表底部的列的左边。</span><span class="sxs-lookup"><span data-stu-id="89996-235">Columns at the top of the list appear to the left of columns at the bottom of the list in the grid view window.</span></span>

<span data-ttu-id="89996-236">**如何对表数据排序**</span><span class="sxs-lookup"><span data-stu-id="89996-236">**How to Sort Table Data**</span></span>

- <span data-ttu-id="89996-237">若要对数据排序，请单击列标题。</span><span class="sxs-lookup"><span data-stu-id="89996-237">To sort the data, click a column header.</span></span>
- <span data-ttu-id="89996-238">若要更改排序顺序，请再次单击列标题。</span><span class="sxs-lookup"><span data-stu-id="89996-238">To change the sort order, click the column header again.</span></span> <span data-ttu-id="89996-239">每次你单击同一标题时，排序顺序会在升序和降序之间切换。</span><span class="sxs-lookup"><span data-stu-id="89996-239">Each time you click the same header, the sort order toggles between ascending to descending order.</span></span> <span data-ttu-id="89996-240">当前顺序由列标题中的三角形指示。</span><span class="sxs-lookup"><span data-stu-id="89996-240">The current order is indicated by a triangle in the column header.</span></span>

<span data-ttu-id="89996-241">**如何选择表数据**</span><span class="sxs-lookup"><span data-stu-id="89996-241">**How to Select Table Data**</span></span>

- <span data-ttu-id="89996-242">若要选择某一行，请选择该行或使用向上或向下箭头导航到该行。</span><span class="sxs-lookup"><span data-stu-id="89996-242">To select a row, select the row or use the up or down arrow to navigate to the row.</span></span>
- <span data-ttu-id="89996-243">若要选择除标题行) 之外的所有行 (，请按<kbd>CTRL</kbd> + <kbd>A</kbd>。</span><span class="sxs-lookup"><span data-stu-id="89996-243">To select all rows (except for the header row), press <kbd>CTRL</kbd>+<kbd>A</kbd>.</span></span>
- <span data-ttu-id="89996-244">若要选择连续的行，请在单击行或使用箭头键的同时按住 <kbd>SHIFT</kbd> 键。</span><span class="sxs-lookup"><span data-stu-id="89996-244">To select consecutive rows, press and hold the <kbd>SHIFT</kbd> key while clicking the rows or using the arrow keys.</span></span>
- <span data-ttu-id="89996-245">若要选择不连续的行，请按 <kbd>CTRL</kbd> 键，然后单击将行添加到选定内容。</span><span class="sxs-lookup"><span data-stu-id="89996-245">To select nonconsecutive rows, press the <kbd>CTRL</kbd> key and click to add a row to the selection.</span></span>
- <span data-ttu-id="89996-246">你不能选择列，也不能选择整个列标题行。</span><span class="sxs-lookup"><span data-stu-id="89996-246">You cannot select columns, and you cannot select the entire column header row.</span></span>

<span data-ttu-id="89996-247">**如何复制行**</span><span class="sxs-lookup"><span data-stu-id="89996-247">**How to Copy Rows**</span></span>

- <span data-ttu-id="89996-248">若要从表中复制一个或多个行，请选择行，然后按 CTRL + C。</span><span class="sxs-lookup"><span data-stu-id="89996-248">To copy one or more rows from the table, select the rows and then press CTRL+C.</span></span>

  <span data-ttu-id="89996-249">可以将数据粘贴到任何文本或电子表格程序。</span><span class="sxs-lookup"><span data-stu-id="89996-249">You can paste the data into any text or spreadsheet program.</span></span> <span data-ttu-id="89996-250">你无法复制列或部分行，也无法复制列标题行。</span><span class="sxs-lookup"><span data-stu-id="89996-250">You cannot copy columns or parts of rows and you cannot copy the column header row.</span></span>

<span data-ttu-id="89996-251">**如何在表中搜索 (快速筛选)**</span><span class="sxs-lookup"><span data-stu-id="89996-251">**How to Search in the Table (Quick Filter)**</span></span>

<span data-ttu-id="89996-252">使用 "筛选器" 框搜索表中的数据。</span><span class="sxs-lookup"><span data-stu-id="89996-252">Use the Filter box to search for data in the table.</span></span> <span data-ttu-id="89996-253">当你在框中进行键入时，表中仅显示包含所键入的文本的项。</span><span class="sxs-lookup"><span data-stu-id="89996-253">When you type in the box, only items that include the typed text appear in the table.</span></span>

- <span data-ttu-id="89996-254">搜索文本。</span><span class="sxs-lookup"><span data-stu-id="89996-254">Search for text.</span></span> <span data-ttu-id="89996-255">若要在表中搜索文本，请在 "筛选器" 框中键入要查找的文本。</span><span class="sxs-lookup"><span data-stu-id="89996-255">To search for text in the table, in the Filter box, type the text to find.</span></span>
- <span data-ttu-id="89996-256">搜索多个字词。</span><span class="sxs-lookup"><span data-stu-id="89996-256">Search for multiple words.</span></span> <span data-ttu-id="89996-257">若要在表中搜索多个字词，请键入由空格分隔的字词。</span><span class="sxs-lookup"><span data-stu-id="89996-257">To search for multiple words in the table, type the words separated by spaces.</span></span> <span data-ttu-id="89996-258">`Out-GridView` 显示包含 (逻辑 AND) 的所有单词的行。</span><span class="sxs-lookup"><span data-stu-id="89996-258">`Out-GridView` displays rows that include all the words (logical AND).</span></span>
- <span data-ttu-id="89996-259">搜索文字短语。</span><span class="sxs-lookup"><span data-stu-id="89996-259">Search for literal phrases.</span></span> <span data-ttu-id="89996-260">若要搜索包含空格或特殊字符的短语，请将该短语用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="89996-260">To search for phrases that include spaces or special characters, enclose the phrase in quotation marks.</span></span> <span data-ttu-id="89996-261">`Out-GridView` 显示包含短语完全匹配项的行。</span><span class="sxs-lookup"><span data-stu-id="89996-261">`Out-GridView` displays rows that include an exact match for the phrase.</span></span>
- <span data-ttu-id="89996-262">在列中搜索。</span><span class="sxs-lookup"><span data-stu-id="89996-262">Search in columns.</span></span> <span data-ttu-id="89996-263">若要在一个或多个列中搜索文本，请使用以下格式：</span><span class="sxs-lookup"><span data-stu-id="89996-263">To search for text in one or more columns, use the following format:</span></span>

  `<column>:<text> [<column>:<text>] ...`

  <span data-ttu-id="89996-264">例如，若要在 **DisplayName** 列中查找 "Net"，请在 " **筛选器** " 框中键入：</span><span class="sxs-lookup"><span data-stu-id="89996-264">For example, to find "Net" in the **DisplayName** column, in the **Filter** box, type:</span></span>

  `displayname:net`

  <span data-ttu-id="89996-265">若要在 **DisplayName** 和 **Name** 列中查找 "Net" 行，请在 " **筛选器** " 框中键入：</span><span class="sxs-lookup"><span data-stu-id="89996-265">To find rows with "Net" in the **DisplayName** and **Name** columns, in the **Filter** box, type:</span></span>

  `displayname:net name:net`

- <span data-ttu-id="89996-266">关闭搜索。</span><span class="sxs-lookup"><span data-stu-id="89996-266">Turn off search.</span></span> <span data-ttu-id="89996-267">若要再次显示整个表，请单击 " **筛选器** " 框右上角的红色 X 按钮或从 " **筛选器** " 框中删除文本。</span><span class="sxs-lookup"><span data-stu-id="89996-267">To display the entire table again, click the red X button in the top right corner of the **Filter** box or delete the text from the **Filter** box.</span></span>

<span data-ttu-id="89996-268">**使用条件来筛选表**</span><span class="sxs-lookup"><span data-stu-id="89996-268">**Use Criteria to Filter the Table**</span></span>

<span data-ttu-id="89996-269">您可以使用规则或条件来确定哪些项显示在表中。</span><span class="sxs-lookup"><span data-stu-id="89996-269">You can use rules or criteria to determine which items are displayed in the table.</span></span> <span data-ttu-id="89996-270">仅当项满足你建立的所有条件时，才会显示这些项。</span><span class="sxs-lookup"><span data-stu-id="89996-270">Items appear only when they satisfy all the criteria that you establish.</span></span> <span data-ttu-id="89996-271">可用条件由网格视图窗口中显示的对象的属性和这些属性的 .NET Framework 类型来确定。</span><span class="sxs-lookup"><span data-stu-id="89996-271">The available criteria are determined by the properties of the objects displayed in the grid view window and the .NET Framework types of those properties.</span></span>

<span data-ttu-id="89996-272">每个条件具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="89996-272">Each criterion has the following format:</span></span>

`<column> <operator> <value>`

<span data-ttu-id="89996-273">不同属性的条件由 **和** 连接。</span><span class="sxs-lookup"><span data-stu-id="89996-273">Criteria for different properties are connected by **AND** .</span></span> <span data-ttu-id="89996-274">相同属性的条件由 **或** 连接。</span><span class="sxs-lookup"><span data-stu-id="89996-274">Criteria for the same property are connected by **OR** .</span></span> <span data-ttu-id="89996-275">你不能更改逻辑连接符。</span><span class="sxs-lookup"><span data-stu-id="89996-275">You cannot change the logical connectors.</span></span>

<span data-ttu-id="89996-276">条件仅影响显示。</span><span class="sxs-lookup"><span data-stu-id="89996-276">The criteria only affects the display.</span></span> <span data-ttu-id="89996-277">它不会从表中删除项。</span><span class="sxs-lookup"><span data-stu-id="89996-277">It does not delete items from the table.</span></span>

<span data-ttu-id="89996-278">**如何添加条件**</span><span class="sxs-lookup"><span data-stu-id="89996-278">**How to Add Criteria**</span></span>

1. <span data-ttu-id="89996-279">若要显示 " **添加条件** " 菜单按钮，请在窗口右上角单击 "展开" 箭头。</span><span class="sxs-lookup"><span data-stu-id="89996-279">To display the **Add criteria** menu button, in the upper right corner of the window, click the Expand arrow.</span></span>
2. <span data-ttu-id="89996-280">单击 " **添加条件** " 菜单按钮。</span><span class="sxs-lookup"><span data-stu-id="89996-280">Click the **Add Criteria** menu button.</span></span>
3. <span data-ttu-id="89996-281">单击以选择列（属性）。</span><span class="sxs-lookup"><span data-stu-id="89996-281">Click to select columns (properties).</span></span> <span data-ttu-id="89996-282">你可以选择一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="89996-282">You can select one or many properties.</span></span>
4. <span data-ttu-id="89996-283">选择完属性后，单击 " **添加** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="89996-283">When you are finished selecting properties, click the **Add** button.</span></span>
5. <span data-ttu-id="89996-284">若要取消添加，请单击 " **取消** "。</span><span class="sxs-lookup"><span data-stu-id="89996-284">To cancel the additions, click **Cancel** .</span></span>
6. <span data-ttu-id="89996-285">若要添加更多条件，请再次单击 " **添加条件** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="89996-285">To add more criteria, click the **Add Criteria** button again.</span></span>

<span data-ttu-id="89996-286">**如何编辑条件**</span><span class="sxs-lookup"><span data-stu-id="89996-286">**How to Edit a Criterion**</span></span>

- <span data-ttu-id="89996-287">若要更改运算符，请单击蓝色运算符值，然后从下拉列表中选择其他运算符。</span><span class="sxs-lookup"><span data-stu-id="89996-287">To change an operator, click the blue operator value, and then select a different operator from the drop-down list.</span></span>
- <span data-ttu-id="89996-288">若要输入或更改值，请在 "值" 框中键入值。</span><span class="sxs-lookup"><span data-stu-id="89996-288">To enter or change a value, type a value in the value box.</span></span> <span data-ttu-id="89996-289">如果输入的值无效，将显示一个圆形的 X 图标。</span><span class="sxs-lookup"><span data-stu-id="89996-289">If you enter a value that is not valid, a circular X icon appears.</span></span> <span data-ttu-id="89996-290">若要删除它，请更改该值。</span><span class="sxs-lookup"><span data-stu-id="89996-290">To remove it, change the value.</span></span>
- <span data-ttu-id="89996-291">若要创建 **或** 语句，请添加具有相同属性的条件。</span><span class="sxs-lookup"><span data-stu-id="89996-291">To create an **OR** statement, add a criteria with the same property.</span></span>

<span data-ttu-id="89996-292">**如何删除条件**</span><span class="sxs-lookup"><span data-stu-id="89996-292">**How to Delete Criteria**</span></span>

- <span data-ttu-id="89996-293">若要删除所选的条件，请单击每个条件旁边的红色 X。</span><span class="sxs-lookup"><span data-stu-id="89996-293">To delete selected criteria, click the red X beside each criterion.</span></span>
- <span data-ttu-id="89996-294">若要删除所有条件，请单击 " **全部清除** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="89996-294">To delete all criteria, click the **Clear All** button.</span></span>

## <span data-ttu-id="89996-295">相关链接</span><span class="sxs-lookup"><span data-stu-id="89996-295">RELATED LINKS</span></span>

[<span data-ttu-id="89996-296">Out-File</span><span class="sxs-lookup"><span data-stu-id="89996-296">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="89996-297">Out-printer</span><span class="sxs-lookup"><span data-stu-id="89996-297">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="89996-298">Out-String</span><span class="sxs-lookup"><span data-stu-id="89996-298">Out-String</span></span>](Out-String.md)