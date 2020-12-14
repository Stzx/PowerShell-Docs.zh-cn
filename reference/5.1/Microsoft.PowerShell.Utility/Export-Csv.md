---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/export-csv?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Csv
ms.openlocfilehash: 17c3ef3046ba8f0cca9a85cf41aaf683212a58e9
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913335"
---
# <span data-ttu-id="0f3c0-102">Export-Csv</span><span class="sxs-lookup"><span data-stu-id="0f3c0-102">Export-Csv</span></span>

## <span data-ttu-id="0f3c0-103">摘要</span><span class="sxs-lookup"><span data-stu-id="0f3c0-103">SYNOPSIS</span></span>
<span data-ttu-id="0f3c0-104">将对象转换为一系列逗号分隔值 (CSV) 字符串，并将字符串保存到文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-104">Converts objects into a series of comma-separated value (CSV) strings and saves the strings to a file.</span></span>

## <span data-ttu-id="0f3c0-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f3c0-105">SYNTAX</span></span>

### <span data-ttu-id="0f3c0-106">Delimiter（默认值）</span><span class="sxs-lookup"><span data-stu-id="0f3c0-106">Delimiter (Default)</span></span>

```
Export-Csv [[-Path] <string>] [[-Delimiter] <char>] -InputObject <psobject> [-LiteralPath <string>]
 [-Force] [-NoClobber] [-Encoding <string>] [-Append] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="0f3c0-107">UseCulture</span><span class="sxs-lookup"><span data-stu-id="0f3c0-107">UseCulture</span></span>

```
Export-Csv [[-Path] <string>] -InputObject <psobject> [-LiteralPath <string>] [-Force] [-NoClobber]
 [-Encoding <string>] [-Append] [-UseCulture] [-NoTypeInformation] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="0f3c0-108">说明</span><span class="sxs-lookup"><span data-stu-id="0f3c0-108">DESCRIPTION</span></span>

<span data-ttu-id="0f3c0-109">`Export-CSV`Cmdlet 可创建你提交的对象的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-109">The `Export-CSV` cmdlet creates a CSV file of the objects that you submit.</span></span> <span data-ttu-id="0f3c0-110">每个对象都是一个行，其中包含以逗号分隔的对象属性值列表。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-110">Each object is a row that includes a comma-separated list of the object's property values.</span></span> <span data-ttu-id="0f3c0-111">可以使用 `Export-CSV` cmdlet 创建电子表格并与接受 CSV 文件作为输入的程序共享数据。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-111">You can use the `Export-CSV` cmdlet to create spreadsheets and share data with programs that accept CSV files as input.</span></span>

<span data-ttu-id="0f3c0-112">在将对象发送到 cmdlet 之前，请不要设置它们的格式 `Export-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-112">Do not format objects before sending them to the `Export-CSV` cmdlet.</span></span> <span data-ttu-id="0f3c0-113">如果 `Export-CSV` 接收格式化对象，则 CSV 文件包含格式属性而不是对象属性。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-113">If `Export-CSV` receives formatted objects the CSV file contains the format properties rather than the object properties.</span></span> <span data-ttu-id="0f3c0-114">若要仅导出对象的选定属性，请使用 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-114">To export only selected properties of an object, use the `Select-Object` cmdlet.</span></span>

## <span data-ttu-id="0f3c0-115">示例</span><span class="sxs-lookup"><span data-stu-id="0f3c0-115">EXAMPLES</span></span>

### <span data-ttu-id="0f3c0-116">示例1：将进程属性导出到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="0f3c0-116">Example 1: Export process properties to a CSV file</span></span>

<span data-ttu-id="0f3c0-117">此示例选择具有特定属性的 **进程** 对象，将对象导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-117">This example selects **Process** objects with specific properties, exports the objects to a CSV file.</span></span>

```powershell
Get-Process -Name WmiPrvSE | Select-Object -Property BasePriority,Id,SessionId,WorkingSet |
  Export-Csv -Path .\WmiData.csv -NoTypeInformation
Import-Csv -Path .\WmiData.csv
```

```Output
BasePriority Id    SessionId WorkingSet
------------ --    --------- ----------
8            976   0         20267008
8            2292  0         36786176
8            3816  0         30351360
8            8604  0         15011840
8            10008 0         8830976
8            11764 0         14237696
8            54632 0         9502720
```

<span data-ttu-id="0f3c0-118">`Get-Process`Cmdlet 将获取 **进程** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-118">The `Get-Process` cmdlet gets the **Process** objects.</span></span> <span data-ttu-id="0f3c0-119">**Name** 参数将输出筛选为仅包含 WmiPrvSE 进程对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-119">The **Name** parameter filters the output to include only the WmiPrvSE process objects.</span></span> <span data-ttu-id="0f3c0-120">进程对象将通过管道向下发送到 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-120">The process objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="0f3c0-121">`Select-Object` 使用 **Property** 参数选择进程对象属性的子集。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-121">`Select-Object` uses the **Property** parameter to select a subset of process object properties.</span></span> <span data-ttu-id="0f3c0-122">进程对象将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-122">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-123">`Export-Csv` 将进程对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-123">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="0f3c0-124">**Path** 参数指定将 WmiData.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-124">The **Path** parameter specifies that the WmiData.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-125">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-125">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0f3c0-126">`Import-Csv`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-126">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0f3c0-127">示例2：将进程导出到逗号分隔的文件</span><span class="sxs-lookup"><span data-stu-id="0f3c0-127">Example 2: Export processes to a comma-delimited file</span></span>

<span data-ttu-id="0f3c0-128">此示例获取 **进程** 对象并将对象导出到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-128">This example gets **Process** objects and exports the objects to a CSV file.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="0f3c0-129">`Get-Process`Cmdlet 将获取 **进程** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-129">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0f3c0-130">进程对象将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-130">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-131">`Export-Csv` 将进程对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-131">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="0f3c0-132">**Path** 参数指定将 Processes.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-132">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-133">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-133">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0f3c0-134">`Get-Content`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-134">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0f3c0-135">示例3：将进程导出为分号分隔的文件</span><span class="sxs-lookup"><span data-stu-id="0f3c0-135">Example 3: Export processes to a semicolon delimited file</span></span>

<span data-ttu-id="0f3c0-136">此示例获取 **进程** 对象并将对象导出到带有分号分隔符的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-136">This example gets **Process** objects and exports the objects to a file with a semicolon delimiter.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv -Delimiter ';' -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="0f3c0-137">`Get-Process`Cmdlet 将获取 **进程** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-137">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0f3c0-138">进程对象将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-138">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-139">`Export-Csv` 将进程对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-139">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="0f3c0-140">**Path** 参数指定将 Processes.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-140">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-141">**分隔符** 参数指定用分号分隔字符串值。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-141">The **Delimiter** parameter specifies a semicolon to separate the string values.</span></span> <span data-ttu-id="0f3c0-142">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-142">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0f3c0-143">`Get-Content`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-143">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0f3c0-144">示例4：使用当前区域性的列表分隔符导出进程</span><span class="sxs-lookup"><span data-stu-id="0f3c0-144">Example 4: Export processes using the current culture's list separator</span></span>

<span data-ttu-id="0f3c0-145">此示例获取 **进程** 对象并将对象导出到文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-145">This example gets **Process** objects and exports the objects to a file.</span></span> <span data-ttu-id="0f3c0-146">分隔符为当前区域性的列表分隔符。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-146">The delimiter is the current culture's list separator.</span></span>

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-Process | Export-Csv -Path .\Processes.csv -UseCulture -NoTypeInformation
Get-Content -Path .\Processes.csv
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","511","2203597099008","35364864","21979136","30048", ...
```

<span data-ttu-id="0f3c0-147">该 `Get-Culture` cmdlet 使用嵌套属性 **TextInfo** 和 **ListSeparator** ，并显示当前区域性的默认列表分隔符。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-147">The `Get-Culture` cmdlet uses the nested properties **TextInfo** and **ListSeparator** and displays the current culture's default list separator.</span></span> <span data-ttu-id="0f3c0-148">`Get-Process`Cmdlet 将获取 **进程** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-148">The `Get-Process` cmdlet gets **Process** objects.</span></span>
<span data-ttu-id="0f3c0-149">进程对象将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-149">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-150">`Export-Csv` 将进程对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-150">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="0f3c0-151">**Path** 参数指定将 Processes.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-151">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-152">**UseCulture** 参数使用当前区域性的默认列表分隔符作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-152">The **UseCulture** parameter uses the current culture's default list separator as the delimiter.</span></span> <span data-ttu-id="0f3c0-153">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-153">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0f3c0-154">`Get-Content`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-154">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0f3c0-155">示例5：导出具有类型信息的进程</span><span class="sxs-lookup"><span data-stu-id="0f3c0-155">Example 5: Export processes with type information</span></span>

<span data-ttu-id="0f3c0-156">此示例说明如何将 **#TYPE** 标头信息包含在 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-156">This example explains how to include the **#TYPE** header information in a CSV file.</span></span> <span data-ttu-id="0f3c0-157">**#TYPE** 标头在 PowerShell 6.0 之前的版本中是默认标头。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-157">The **#TYPE** header is the default in versions prior to PowerShell 6.0.</span></span>

```powershell
Get-Process | Export-Csv -Path .\Processes.csv
Get-Content -Path .\Processes.csv
```

```Output
#TYPE System.Diagnostics.Process
"Name","SI","Handles","VM","WS","PM","NPM","Path","Company","CPU","FileVersion", ...
"ApplicationFrameHost","4","507","2203595001856","35139584","20934656","29504", ...
```

<span data-ttu-id="0f3c0-158">`Get-Process`Cmdlet 将获取 **进程** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-158">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0f3c0-159">进程对象将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-159">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-160">`Export-Csv` 将进程对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-160">`Export-Csv` converts the process objects to a series of CSV strings.</span></span>
<span data-ttu-id="0f3c0-161">**Path** 参数指定将 Processes.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-161">The **Path** parameter specifies that the Processes.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-162">`Get-Content`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-162">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0f3c0-163">示例6：将对象导出并追加到 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="0f3c0-163">Example 6: Export and append objects to a CSV file</span></span>

<span data-ttu-id="0f3c0-164">此示例说明如何将对象导出到 CSV 文件，并使用 **Append** 参数将对象添加到现有文件中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-164">This example describes how to export objects to a CSV file and use the **Append** parameter to add objects to an existing file.</span></span>

```powershell
$AppService = (Get-Service -DisplayName *Application* | Select-Object -Property DisplayName, Status)
$AppService | Export-Csv -Path .\Services.Csv -NoTypeInformation
Get-Content -Path .\Services.Csv
$WinService = (Get-Service -DisplayName *Windows* | Select-Object -Property DisplayName, Status)
$WinService | Export-Csv -Path ./Services.csv -NoTypeInformation -Append
Get-Content -Path .\Services.Csv
```

```Output
"DisplayName","Status"
"Application Layer Gateway Service","Stopped"
"Application Identity","Running"
"Windows Audio Endpoint Builder","Running"
"Windows Audio","Running"
"Windows Event Log","Running"
```

<span data-ttu-id="0f3c0-165">`Get-Service`Cmdlet 将获取服务对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-165">The `Get-Service` cmdlet gets service objects.</span></span> <span data-ttu-id="0f3c0-166">**DisplayName** 参数返回包含 Word 应用程序的服务。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-166">The **DisplayName** parameter returns services that contain the word Application.</span></span> <span data-ttu-id="0f3c0-167">服务对象将通过管道向下发送到 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-167">The service objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="0f3c0-168">`Select-Object` 使用 **Property** 参数来指定 **DisplayName** 和 **Status** 属性。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-168">`Select-Object` uses the **Property** parameter to specify the **DisplayName** and **Status** properties.</span></span> <span data-ttu-id="0f3c0-169">`$AppService`变量存储对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-169">The `$AppService` variable stores the objects.</span></span>

<span data-ttu-id="0f3c0-170">`$AppService`对象通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-170">The `$AppService` objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-171">`Export-Csv` 将服务对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-171">`Export-Csv` converts the service objects to a series of CSV strings.</span></span> <span data-ttu-id="0f3c0-172">**Path** 参数指定将 Services.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-172">The **Path** parameter specifies that the Services.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-173">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-173">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0f3c0-174">`Get-Content`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-174">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

<span data-ttu-id="0f3c0-175">`Get-Service`和 `Select-Object` cmdlet 对于包含 word Windows 的服务重复。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-175">The `Get-Service` and `Select-Object` cmdlets are repeated for services that contain the word Windows.</span></span> <span data-ttu-id="0f3c0-176">`$WinService`变量存储服务对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-176">The `$WinService` variable stores the service objects.</span></span> <span data-ttu-id="0f3c0-177">`Export-Csv`Cmdlet 使用 **Append** 参数指定将 `$WinService` 对象添加到现有 Services.csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-177">The `Export-Csv` cmdlet uses the **Append** parameter to specify that the `$WinService` objects are added to the existing Services.csv file.</span></span> <span data-ttu-id="0f3c0-178">此 `Get-Content` cmdlet 将重复显示已更新的文件，其中包含追加的数据。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-178">The `Get-Content` cmdlet is repeated to display the updated file that includes the appended data.</span></span>

### <span data-ttu-id="0f3c0-179">示例7：管道内的格式 cmdlet 产生意外的结果</span><span class="sxs-lookup"><span data-stu-id="0f3c0-179">Example 7: Format cmdlet within a pipeline creates unexpected results</span></span>

<span data-ttu-id="0f3c0-180">此示例说明为什么不在管道内使用格式 cmdlet 很重要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-180">This example shows why it is important not to use a format cmdlet within a pipeline.</span></span> <span data-ttu-id="0f3c0-181">收到意外的输出时，会对管道语法进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-181">When unexpected output is received, troubleshoot the pipeline syntax.</span></span>

```powershell
Get-Date | Select-Object -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\DateTime.csv -NoTypeInformation
Get-Content -Path .\DateTime.csv
```

```Output
"DateTime","Day","DayOfWeek","DayOfYear"
"Wednesday, January 2, 2019 14:59:34","2","Wednesday","2"
```

```powershell
Get-Date | Format-Table -Property DateTime, Day, DayOfWeek, DayOfYear |
 Export-Csv -Path .\FTDateTime.csv -NoTypeInformation
Get-Content -Path .\FTDateTime.csv
```

```Output
"ClassId2e4f51ef21dd47e99d3c952918aff9cd","pageHeaderEntry","pageFooterEntry","autosizeInfo", ...
"033ecb2bc07a4d43b5ef94ed5a35d280",,,,"Microsoft.PowerShell.Commands.Internal.Format. ...
"9e210fe47d09416682b841769c78b8a3",,,,,
"27c87ef9bbda4f709f6b4002fa4af63c",,,,,
"4ec4f0187cb04f4cb6973460dfe252df",,,,,
"cf522b78d86c486691226b40aa69e95c",,,,,
```

<span data-ttu-id="0f3c0-182">`Get-Date`Cmdlet 将获取 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-182">The `Get-Date` cmdlet gets the **DateTime** object.</span></span> <span data-ttu-id="0f3c0-183">对象通过管道向下发送到 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-183">The object is sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="0f3c0-184">`Select-Object` 使用 **Property** 参数来选择对象属性的子集。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-184">`Select-Object` uses the **Property** parameter to select a subset of object properties.</span></span> <span data-ttu-id="0f3c0-185">对象通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-185">The object is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-186">`Export-Csv` 将对象转换为 CSV 格式。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-186">`Export-Csv` converts the object to a CSV format.</span></span> <span data-ttu-id="0f3c0-187">**Path** 参数指定将 DateTime.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-187">The **Path** parameter specifies that the DateTime.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-188">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-188">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0f3c0-189">`Get-Content`Cmdlet 使用 **Path** 参数显示位于当前目录中的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-189">The `Get-Content` cmdlet uses the **Path** parameter to display the CSV file located in the current directory.</span></span>

<span data-ttu-id="0f3c0-190">当在 `Format-Table` 管道中使用 cmdlet 来选择属性时，会收到意外结果。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-190">When the `Format-Table` cmdlet is used within the pipeline to select properties unexpected results are received.</span></span> <span data-ttu-id="0f3c0-191">`Format-Table` 将表格式对象向下发送到 `Export-Csv` cmdlet，而不是 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-191">`Format-Table` sends table format objects down the pipeline to the `Export-Csv` cmdlet rather than the **DateTime** object.</span></span> <span data-ttu-id="0f3c0-192">`Export-Csv` 将表格式对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-192">`Export-Csv` converts the table format objects to a series of CSV strings.</span></span> <span data-ttu-id="0f3c0-193">`Get-Content`Cmdlet 显示包含表格式对象的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-193">The `Get-Content` cmdlet displays the CSV file which contains the table format objects.</span></span>

### <span data-ttu-id="0f3c0-194">示例8：使用 Force 参数覆盖只读文件</span><span class="sxs-lookup"><span data-stu-id="0f3c0-194">Example 8: Using the Force parameter to overwrite read-only files</span></span>

<span data-ttu-id="0f3c0-195">此示例创建一个空的只读文件，并使用 **Force** 参数更新该文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-195">This example creates an empty, read-only file and uses the **Force** parameter to update the file.</span></span>

```powershell
New-Item -Path .\ReadOnly.csv -ItemType File
Set-ItemProperty -Path .\ReadOnly.csv -Name IsReadOnly -Value $true
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
```

```Output
Export-Csv : Access to the path 'C:\ReadOnly.csv' is denied.
At line:1 char:15
+ Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation
+               ~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (:) [Export-Csv], UnauthorizedAccessException
+ FullyQualifiedErrorId : FileOpenFailure,Microsoft.PowerShell.Commands.ExportCsvCommand
```

```powershell
Get-Process | Export-Csv -Path .\ReadOnly.csv -NoTypeInformation -Force
Get-Content -Path .\ReadOnly.csv
```

```Output
"Name";"SI";"Handles";"VM";"WS";"PM";"NPM";"Path";"Parent";"Company";"CPU";"FileVersion"; ...
"ApplicationFrameHost";"4";"509";"2203595321344";"34807808";"21770240";"29504"; ...
```

<span data-ttu-id="0f3c0-196">`New-Item`Cmdlet 使用 **Path** 和 **ItemType** 参数创建当前目录中的 ReadOnly.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-196">The `New-Item` cmdlet uses the **Path** and **ItemType** parameters to create the ReadOnly.csv file in the current directory.</span></span> <span data-ttu-id="0f3c0-197">`Set-ItemProperty`Cmdlet 使用 **Name** 和 **Value** 参数将文件的 **IsReadOnly** 属性更改为 true。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-197">The `Set-ItemProperty` cmdlet uses the **Name** and **Value** parameters to change the file's **IsReadOnly** property to true.</span></span> <span data-ttu-id="0f3c0-198">`Get-Process`Cmdlet 将获取 **进程** 对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-198">The `Get-Process` cmdlet gets **Process** objects.</span></span> <span data-ttu-id="0f3c0-199">进程对象将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-199">The process objects are sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-200">`Export-Csv` 将进程对象转换为一系列 CSV 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-200">`Export-Csv` converts the process objects to a series of CSV strings.</span></span> <span data-ttu-id="0f3c0-201">**Path** 参数指定将 ReadOnly.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-201">The **Path** parameter specifies that the ReadOnly.csv file is saved in the current directory.</span></span> <span data-ttu-id="0f3c0-202">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-202">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span> <span data-ttu-id="0f3c0-203">输出显示该文件未写入，因为访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-203">The output shows that the file is not written because access is denied.</span></span>

<span data-ttu-id="0f3c0-204">将 **force** 参数添加到 `Export-Csv` cmdlet，以强制将导出写入文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-204">The **Force** parameter is added to the `Export-Csv` cmdlet to force the export to write to the file.</span></span> <span data-ttu-id="0f3c0-205">`Get-Content`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-205">The `Get-Content` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

### <span data-ttu-id="0f3c0-206">示例9：将 Force 参数与 Append 一起使用</span><span class="sxs-lookup"><span data-stu-id="0f3c0-206">Example 9: Using the Force parameter with Append</span></span>

<span data-ttu-id="0f3c0-207">此示例演示如何使用 **Force** 和 **Append** 参数。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-207">This example shows how to use the **Force** and **Append** parameters.</span></span> <span data-ttu-id="0f3c0-208">如果组合这些参数，则不匹配的对象属性可以写入 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-208">When these parameters are combined, mismatched object properties can be written to a CSV file.</span></span>

```powershell
$Content = [PSCustomObject]@{Name = 'PowerShell Core'; Version = '6.0'}
$Content | Export-Csv -Path .\ParmFile.csv -NoTypeInformation
$AdditionalContent = [PSCustomObject]@{Name = 'Windows PowerShell'; Edition = 'Desktop'}
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
```

```Output
Export-Csv : Cannot append CSV content to the following file: ParmFile.csv.
The appended object does not have a property that corresponds to the following column:
Version. To continue with mismatched properties, add the -Force parameter, and then retry
 the command.
At line:1 char:22
+ $AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (Version:String) [Export-Csv], InvalidOperationException
+ FullyQualifiedErrorId : CannotAppendCsvWithMismatchedPropertyNames,Microsoft.PowerShell. ...
```

```powershell
$AdditionalContent | Export-Csv -Path .\ParmFile.csv -NoTypeInformation -Append -Force
Import-Csv -Path .\ParmFile.csv
```

```Output
Name               Version
----               -------
PowerShell Core    6.0
Windows PowerShell
```

<span data-ttu-id="0f3c0-209">表达式使用 **Name** 和 **Version** 属性创建 **PSCustomObject** 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-209">An expression creates the **PSCustomObject** with **Name** and **Version** properties.</span></span> <span data-ttu-id="0f3c0-210">值存储在 `$Content` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-210">The values are stored in the `$Content` variable.</span></span> <span data-ttu-id="0f3c0-211">该 `$Content` 变量将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-211">The `$Content` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-212">`Export-Csv` 使用 **Path** 参数，并将 ParmFile.csv 文件保存到当前目录中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-212">`Export-Csv` uses the **Path** parameter and saves the ParmFile.csv file in the current directory.</span></span> <span data-ttu-id="0f3c0-213">**NoTypeInformation** 参数从 CSV 输出中删除 **#TYPE** 信息标头，而在 PowerShell 6 中则不需要。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-213">The **NoTypeInformation** parameter removes the **#TYPE** information header from the CSV output and is not required in PowerShell 6.</span></span>

<span data-ttu-id="0f3c0-214">另一个表达式将创建 **PSCustomObject** ，其 **名称** 和 **版本** 属性为。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-214">Another expression creates a **PSCustomObject** with the **Name** and **Edition** properties.</span></span> <span data-ttu-id="0f3c0-215">值存储在 `$AdditionalContent` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-215">The values are stored in the `$AdditionalContent` variable.</span></span> <span data-ttu-id="0f3c0-216">该 `$AdditionalContent` 变量将通过管道向下发送到 `Export-Csv` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-216">The `$AdditionalContent` variable is sent down the pipeline to the `Export-Csv` cmdlet.</span></span> <span data-ttu-id="0f3c0-217">**Append** 参数用于向文件添加数据。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-217">The **Append** parameter is used to add the data to the file.</span></span> <span data-ttu-id="0f3c0-218">追加 **失败，因为\*\*\*\*版本** 和版本之间存在属性名称不匹配的情况。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-218">The append fails because there is a property name mismatch between **Version** and **Edition**.</span></span>

<span data-ttu-id="0f3c0-219">`Export-Csv`Cmdlet **force** 参数用于强制导出写入文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-219">The `Export-Csv` cmdlet **Force** parameter is used to force the export to write to the file.</span></span> <span data-ttu-id="0f3c0-220">将丢弃 **Edition** 属性。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-220">The **Edition** property is discarded.</span></span> <span data-ttu-id="0f3c0-221">`Import-Csv`Cmdlet 使用 **Path** 参数显示位于当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-221">The `Import-Csv` cmdlet uses the **Path** parameter to display the file located in the current directory.</span></span>

## <span data-ttu-id="0f3c0-222">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f3c0-222">PARAMETERS</span></span>

### <span data-ttu-id="0f3c0-223">-Append</span><span class="sxs-lookup"><span data-stu-id="0f3c0-223">-Append</span></span>

<span data-ttu-id="0f3c0-224">使用此参数可 `Export-CSV` 将 CSV 输出添加到指定文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-224">Use this parameter so that `Export-CSV` adds CSV output to the end of the specified file.</span></span> <span data-ttu-id="0f3c0-225">如果没有此参数， `Export-CSV` 则替换文件内容而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-225">Without this parameter, `Export-CSV` replaces the file contents without warning.</span></span>

<span data-ttu-id="0f3c0-226">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-226">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0f3c0-227">-Delimiter</span><span class="sxs-lookup"><span data-stu-id="0f3c0-227">-Delimiter</span></span>

<span data-ttu-id="0f3c0-228">指定分隔符以分隔属性值。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-228">Specifies a delimiter to separate the property values.</span></span> <span data-ttu-id="0f3c0-229">默认值为逗号 (`,`) 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-229">The default is a comma (`,`).</span></span> <span data-ttu-id="0f3c0-230">输入一个字符，例如冒号 (`:`) 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-230">Enter a character, such as a colon (`:`).</span></span> <span data-ttu-id="0f3c0-231">若要指定分号 (`;`) ，请将其括在引号中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-231">To specify a semicolon (`;`), enclose it in quotation marks.</span></span>

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-232">-Encoding</span><span class="sxs-lookup"><span data-stu-id="0f3c0-232">-Encoding</span></span>

<span data-ttu-id="0f3c0-233">指定目标文件的编码类型。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-233">Specifies the type of encoding for the target file.</span></span> <span data-ttu-id="0f3c0-234">默认值为 `ASCII`。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-234">The default value is `ASCII`.</span></span>

<span data-ttu-id="0f3c0-235">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f3c0-235">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="0f3c0-236">`ASCII` 使用 ASCII (7 位) 字符集。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-236">`ASCII` Uses ASCII (7-bit) character set.</span></span>
- <span data-ttu-id="0f3c0-237">`BigEndianUnicode` 使用带有大 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-237">`BigEndianUnicode` Uses UTF-16 with the big-endian byte order.</span></span>
- <span data-ttu-id="0f3c0-238">`Default` 使用与系统的活动代码页相对应的编码 (通常为 ANSI) 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-238">`Default` Uses the encoding that corresponds to the system's active code page (usually ANSI).</span></span>
- <span data-ttu-id="0f3c0-239">`OEM` 使用与系统的当前 OEM 代码页相对应的编码。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-239">`OEM` Uses the encoding that corresponds to the system's current OEM code page.</span></span>
- <span data-ttu-id="0f3c0-240">`Unicode` 使用带有小 endian 字节顺序的 UTF-16。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-240">`Unicode` Uses UTF-16 with the little-endian byte order.</span></span>
- <span data-ttu-id="0f3c0-241">`UTF7` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-241">`UTF7` Uses UTF-7.</span></span>
- <span data-ttu-id="0f3c0-242">`UTF8` 使用 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-242">`UTF8` Uses UTF-8.</span></span>
- <span data-ttu-id="0f3c0-243">`UTF32` 使用带有小 endian 字节顺序的 32 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-243">`UTF32` Uses UTF-32 with the little-endian byte order.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: ASCII, BigEndianUnicode, Default, OEM, Unicode, UTF7, UTF8, UTF32

Required: False
Position: Named
Default value: ASCII
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-244">-Force</span><span class="sxs-lookup"><span data-stu-id="0f3c0-244">-Force</span></span>

<span data-ttu-id="0f3c0-245">此参数允许 `Export-Csv` 覆盖具有 **只读** 属性的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-245">This parameter allows `Export-Csv` to overwrite files with the **Read Only** attribute.</span></span>

<span data-ttu-id="0f3c0-246">合并 **Force** 和 **Append** 参数时，可以将包含不匹配的属性的对象写入 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-246">When **Force** and **Append** parameters are combined, objects that contain mismatched properties can be written to a CSV file.</span></span> <span data-ttu-id="0f3c0-247">只有与匹配的属性才会写入文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-247">Only the properties that match are written to the file.</span></span> <span data-ttu-id="0f3c0-248">放弃不匹配的属性。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-248">The mismatched properties are discarded.</span></span>

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

### <span data-ttu-id="0f3c0-249">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0f3c0-249">-InputObject</span></span>

<span data-ttu-id="0f3c0-250">指定要导出为 CSV 字符串的对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-250">Specifies the objects to export as CSV strings.</span></span> <span data-ttu-id="0f3c0-251">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-251">Enter a variable that contains the objects or type a command or expression that gets the objects.</span></span> <span data-ttu-id="0f3c0-252">还可以通过管道将对象传递给 `Export-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-252">You can also pipe objects to `Export-CSV`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-253">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0f3c0-253">-LiteralPath</span></span>

<span data-ttu-id="0f3c0-254">指定指向 CSV 输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-254">Specifies the path to the CSV output file.</span></span> <span data-ttu-id="0f3c0-255">与 **Path** 不同，**LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-255">Unlike **Path**, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="0f3c0-256">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-256">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0f3c0-257">如果路径包含转义符，请使用单引号。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-257">If the path includes escape characters, use single quotation marks.</span></span> <span data-ttu-id="0f3c0-258">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-258">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-259">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="0f3c0-259">-NoClobber</span></span>

<span data-ttu-id="0f3c0-260">使用此参数，以便不 `Export-CSV` 会覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-260">Use this parameter so that `Export-CSV` does not overwrite an existing file.</span></span> <span data-ttu-id="0f3c0-261">默认情况下，如果文件存在于指定的路径中，则 `Export-CSV` 将覆盖该文件而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-261">By default, if the file exists in the specified path, `Export-CSV` overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-262">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="0f3c0-262">-NoTypeInformation</span></span>

<span data-ttu-id="0f3c0-263">从输出中删除 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-263">Removes the **#TYPE** information header from the output.</span></span> <span data-ttu-id="0f3c0-264">此参数已成为 PowerShell 6.0 中的默认参数，包含它是为了向后兼容。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-264">This parameter became the default in PowerShell 6.0 and is included for backwards compatibility.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-265">-Path</span><span class="sxs-lookup"><span data-stu-id="0f3c0-265">-Path</span></span>

<span data-ttu-id="0f3c0-266">一个必需的参数，用于指定要保存 CSV 输出文件的位置。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-266">A required parameter that specifies the location to save the CSV output file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-267">-UseCulture</span><span class="sxs-lookup"><span data-stu-id="0f3c0-267">-UseCulture</span></span>

<span data-ttu-id="0f3c0-268">将当前区域性的列表分隔符用作项分隔符。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-268">Uses the list separator for the current culture as the item delimiter.</span></span> <span data-ttu-id="0f3c0-269">若要查找区域性的列表分隔符，请使用以下命令： `(Get-Culture).TextInfo.ListSeparator` 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-269">To find the list separator for a culture, use the following command: `(Get-Culture).TextInfo.ListSeparator`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0f3c0-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0f3c0-270">-Confirm</span></span>

<span data-ttu-id="0f3c0-271">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0f3c0-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0f3c0-272">-WhatIf</span></span>

<span data-ttu-id="0f3c0-273">阻止对 cmdlet 进行处理或更改。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-273">Prevents the cmdlet from being processed or making changes.</span></span> <span data-ttu-id="0f3c0-274">此输出显示了在运行 cmdlet 后将发生的情况。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-274">The output shows what would happen if the cmdlet were run.</span></span>

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

### <span data-ttu-id="0f3c0-275">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f3c0-275">CommonParameters</span></span>

<span data-ttu-id="0f3c0-276">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-276">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f3c0-277">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-277">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f3c0-278">输入</span><span class="sxs-lookup"><span data-stu-id="0f3c0-278">INPUTS</span></span>

### <span data-ttu-id="0f3c0-279">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0f3c0-279">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0f3c0-280">可以通过管道将具有扩展类型系统 (ETS) 适配器的任何对象传递给 `Export-CSV` 。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-280">You can pipe any object with an Extended Type System (ETS) adapter to `Export-CSV`.</span></span>

## <span data-ttu-id="0f3c0-281">输出</span><span class="sxs-lookup"><span data-stu-id="0f3c0-281">OUTPUTS</span></span>

### <span data-ttu-id="0f3c0-282">System.String</span><span class="sxs-lookup"><span data-stu-id="0f3c0-282">System.String</span></span>

<span data-ttu-id="0f3c0-283">CSV 列表将发送到 Path 参数中指定的文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-283">The CSV list is sent to the file designated in the Path parameter.</span></span>

## <span data-ttu-id="0f3c0-284">注释</span><span class="sxs-lookup"><span data-stu-id="0f3c0-284">NOTES</span></span>

<span data-ttu-id="0f3c0-285">`Export-CSV`Cmdlet 将提交的对象转换为一系列 CSV 字符串，并将它们保存在指定的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-285">The `Export-CSV` cmdlet converts the objects that you submit into a series of CSV strings and saves them in the specified text file.</span></span> <span data-ttu-id="0f3c0-286">你可以使用将 `Export-CSV` 对象保存在 csv 文件中，然后使用 `Import-Csv` CMDLET 从 csv 文件创建对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-286">You can use `Export-CSV` to save objects in a CSV file and then use the `Import-Csv` cmdlet to create objects from the CSV file.</span></span>

<span data-ttu-id="0f3c0-287">在 CSV 文件中，通过以逗号分隔的对象属性值列表来表示每个对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-287">In the CSV file, each object is represented by a comma-separated list of the property values of the object.</span></span> <span data-ttu-id="0f3c0-288">使用 **ToString ( # B1** 方法将属性值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-288">The property values are converted to strings using the **ToString()** method.</span></span> <span data-ttu-id="0f3c0-289">字符串由属性值名称表示。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-289">The strings are represented by the property value name.</span></span> <span data-ttu-id="0f3c0-290">"Export-CSV 不导出对象的方法。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-290">\`Export-CSV does not export the methods of the object.</span></span>

<span data-ttu-id="0f3c0-291">CSV 字符串的输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f3c0-291">The CSV strings are output as follows:</span></span>

- <span data-ttu-id="0f3c0-292">默认情况下，第一个字符串包含后跟对象类型的完全限定名称的 **#TYPE** 信息标头。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-292">By default the first string contains the **#TYPE** information header followed by the object type's fully qualified name.</span></span> <span data-ttu-id="0f3c0-293">例如， **#TYPE**"。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-293">For example, **#TYPE System.Diagnostics.Process**.</span></span>
- <span data-ttu-id="0f3c0-294">如果使用 **NoTypeInformation** ，则第一个字符串包括列标题。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-294">If **NoTypeInformation** is used the first string includes the column headers.</span></span> <span data-ttu-id="0f3c0-295">标头以逗号分隔的列表的形式包含第一个对象的属性名称。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-295">The headers contain the first object's property names as a comma-separated list.</span></span>
- <span data-ttu-id="0f3c0-296">其余字符串包含每个对象的属性值的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-296">The remaining strings contain comma-separated lists of each object's property values.</span></span>

<span data-ttu-id="0f3c0-297">当你将多个对象提交到时 `Export-CSV` ，将 `Export-CSV` 根据你提交的第一个对象的属性来组织文件。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-297">When you submit multiple objects to `Export-CSV`, `Export-CSV` organizes the file based on the properties of the first object that you submit.</span></span> <span data-ttu-id="0f3c0-298">如果剩余的对象没有指定的属性之一，则该对象的属性值为 null，由两个连续的逗号表示。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-298">If the remaining objects do not have one of the specified properties, the property value of that object is null, as represented by two consecutive commas.</span></span> <span data-ttu-id="0f3c0-299">如果剩余的对象有其他属性，这些属性值将不包括在文件中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-299">If the remaining objects have additional properties, those property values are not included in the file.</span></span>

<span data-ttu-id="0f3c0-300">可以使用 `Import-Csv` cmdlet 从文件中的 CSV 字符串重新创建对象。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-300">You can use the `Import-Csv` cmdlet to recreate objects from the CSV strings in the files.</span></span> <span data-ttu-id="0f3c0-301">生成的对象是原始对象的 CSV 版本，这些版本由属性值的字符串表示形式组成，且不包括方法。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-301">The resulting objects are CSV versions of the original objects that consist of string representations of the property values and no methods.</span></span>

<span data-ttu-id="0f3c0-302">`ConvertTo-Csv`和 `ConvertFrom-Csv` cmdlet 将对象转换为 csv 字符串，并将对象转换为 csv 字符串。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-302">The `ConvertTo-Csv` and `ConvertFrom-Csv` cmdlets convert objects to CSV strings and from CSV strings.</span></span> <span data-ttu-id="0f3c0-303">`Export-CSV` 与相同 `ConvertTo-CSV` ，只不过它将 CSV 字符串保存在文件中。</span><span class="sxs-lookup"><span data-stu-id="0f3c0-303">`Export-CSV` is the same as `ConvertTo-CSV`, except that it saves the CSV strings in a file.</span></span>

## <span data-ttu-id="0f3c0-304">相关链接</span><span class="sxs-lookup"><span data-stu-id="0f3c0-304">RELATED LINKS</span></span>

[<span data-ttu-id="0f3c0-305">ConvertFrom-Csv</span><span class="sxs-lookup"><span data-stu-id="0f3c0-305">ConvertFrom-Csv</span></span>](ConvertFrom-Csv.md)

[<span data-ttu-id="0f3c0-306">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="0f3c0-306">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="0f3c0-307">Format-Table</span><span class="sxs-lookup"><span data-stu-id="0f3c0-307">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="0f3c0-308">Import-Csv</span><span class="sxs-lookup"><span data-stu-id="0f3c0-308">Import-Csv</span></span>](Import-Csv.md)

[<span data-ttu-id="0f3c0-309">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0f3c0-309">Select-Object</span></span>](Select-Object.md)
