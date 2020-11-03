---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/sort-object?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Sort-Object
ms.openlocfilehash: 1d27641f94d82b85bab694b392c0f09bb3265517
ms.sourcegitcommit: 9a6b6714ded4edb5119f1b82a253608018ea6b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "93199239"
---
# <span data-ttu-id="0738e-103">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-103">Sort-Object</span></span>

## <span data-ttu-id="0738e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0738e-104">SYNOPSIS</span></span>
<span data-ttu-id="0738e-105">按照属性值对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-105">Sorts objects by property values.</span></span>

## <span data-ttu-id="0738e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0738e-106">SYNTAX</span></span>

### <span data-ttu-id="0738e-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="0738e-107">Default (Default)</span></span>

```
Sort-Object [[-Property] <Object[]>] [-Descending] [-Unique] [-InputObject <psobject>]
 [-Culture <string>] [-CaseSensitive] [<CommonParameters>]
```

## <span data-ttu-id="0738e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0738e-108">DESCRIPTION</span></span>

<span data-ttu-id="0738e-109">该 `Sort-Object` cmdlet 根据对象属性值按升序或降序对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-109">The `Sort-Object` cmdlet sorts objects in ascending or descending order based on object property values.</span></span> <span data-ttu-id="0738e-110">如果命令中未包含 sort 属性，则 PowerShell 将使用第一个输入对象的默认排序属性。</span><span class="sxs-lookup"><span data-stu-id="0738e-110">If sort properties are not included in a command, PowerShell uses default sort properties of the first input object.</span></span> <span data-ttu-id="0738e-111">如果输入对象的类型没有默认的排序属性，则 PowerShell 会尝试比较对象本身。</span><span class="sxs-lookup"><span data-stu-id="0738e-111">If the type of the input object has no default sort properties, PowerShell attempts to compare the objects themselves.</span></span> <span data-ttu-id="0738e-112">有关详细信息，请参阅 " [备注](#notes) " 部分。</span><span class="sxs-lookup"><span data-stu-id="0738e-112">For more information, see the [Notes](#notes) section.</span></span>

<span data-ttu-id="0738e-113">可以按单个属性或多个属性对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-113">You can sort objects by a single property or multiple properties.</span></span> <span data-ttu-id="0738e-114">多个属性使用哈希表按升序、降序或排序顺序的组合进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-114">Multiple properties use hash tables to sort in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="0738e-115">属性被排序为区分大小写或不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0738e-115">Properties are sorted as case-sensitive or case-insensitive.</span></span> <span data-ttu-id="0738e-116">使用 **Unique** 参数从输出中消除重复项。</span><span class="sxs-lookup"><span data-stu-id="0738e-116">Use the **Unique** parameter to eliminate duplicates from the output.</span></span>

## <span data-ttu-id="0738e-117">示例</span><span class="sxs-lookup"><span data-stu-id="0738e-117">EXAMPLES</span></span>

### <span data-ttu-id="0738e-118">示例 1：按名称对当前目录进行排序</span><span class="sxs-lookup"><span data-stu-id="0738e-118">Example 1: Sort the current directory by name</span></span>

<span data-ttu-id="0738e-119">此命令对目录中的文件和子目录进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-119">This command sorts the files and subdirectories in a directory.</span></span>

```
PS> Get-ChildItem -Path C:\Test | Sort-Object

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
d-----        2/25/2019     18:25                Files
d-----        2/25/2019     18:24                Logs
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
```

<span data-ttu-id="0738e-120">`Get-ChildItem`Cmdlet 从 **Path** 参数 **C:\Test** 指定的目录中获取文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="0738e-120">The `Get-ChildItem` cmdlet gets the files and subdirectories from the directory specified by the **Path** parameter, **C:\Test** .</span></span> <span data-ttu-id="0738e-121">对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-121">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="0738e-122">`Sort-Object` 未指定属性，因此输出按默认排序属性 " **名称** " 排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-122">`Sort-Object` does not specify a property so the output is sorted by the default sort property, **Name** .</span></span>

### <span data-ttu-id="0738e-123">示例 2：按文件长度对当前目录进行排序</span><span class="sxs-lookup"><span data-stu-id="0738e-123">Example 2: Sort the current directory by file length</span></span>

<span data-ttu-id="0738e-124">此命令以升序显示当前目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0738e-124">This command displays the files in the current directory by length in ascending order.</span></span>

```
PS> Get-ChildItem -Path C:\Test -File | Sort-Object -Property Length

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     13:26             20 Bfile.txt
-a----        2/12/2019     16:24             23 Zsystemlog.log
-a----        2/13/2019     08:55             26 anotherfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-a----        2/12/2019     15:40         118014 Command.txt
```

<span data-ttu-id="0738e-125">`Get-ChildItem`Cmdlet 将从 **Path** 参数所指定的目录中获取文件。</span><span class="sxs-lookup"><span data-stu-id="0738e-125">The `Get-ChildItem` cmdlet gets the files from the directory specified by the **Path** parameter.</span></span>
<span data-ttu-id="0738e-126">**File** 参数指定 `Get-ChildItem` 仅获取文件对象。</span><span class="sxs-lookup"><span data-stu-id="0738e-126">The **File** parameter specifies that `Get-ChildItem` only gets file objects.</span></span> <span data-ttu-id="0738e-127">对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-127">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-128">`Sort-Object` 使用 **length** 参数以升序对文件进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-128">`Sort-Object` uses the **Length** parameter to sort the files by length in ascending order.</span></span>

### <span data-ttu-id="0738e-129">示例3：按内存使用情况对进程排序</span><span class="sxs-lookup"><span data-stu-id="0738e-129">Example 3: Sort processes by memory usage</span></span>

<span data-ttu-id="0738e-130">此示例根据 (WS) 大小的工作集显示具有最高内存使用率的进程。</span><span class="sxs-lookup"><span data-stu-id="0738e-130">This example displays processes with the highest memory usage based on their working set (WS) size.</span></span>

```
PS> Get-Process | Sort-Object -Property WS | Select-Object -Last 5

 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    136   193.92     217.11     889.16   87492   8 OUTLOOK
    112   347.73     297.02      95.19  106908   8 Teams
    206   266.54     323.71      37.17   60620   8 MicrosoftEdgeCP
     35   552.19     549.94     131.66    6552   8 Code
      0     1.43     595.12       0.00    2780   0 Memory Compression
```

<span data-ttu-id="0738e-131">`Get-Process`Cmdlet 将获取计算机上正在运行的进程的列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-131">The `Get-Process` cmdlet gets the list of processes running on the computer.</span></span> <span data-ttu-id="0738e-132">进程对象将通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-132">The process objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-133">`Sort-Object` 使用 **属性** 参数按 **WS** 对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-133">`Sort-Object` uses the **Property** parameter to sort the objects by **WS** .</span></span> <span data-ttu-id="0738e-134">对象通过管道向下发送到 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-134">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="0738e-135">`Select-Object` 使用 **最后一个** 参数来指定最后五个对象，这些对象是具有最高 **WS** 使用量的对象。</span><span class="sxs-lookup"><span data-stu-id="0738e-135">`Select-Object` uses the **Last** parameter to specify the last five objects, which are the objects with the highest **WS** usage.</span></span>

### <span data-ttu-id="0738e-136">示例4：按 Id 对 HistoryInfo 对象进行排序</span><span class="sxs-lookup"><span data-stu-id="0738e-136">Example 4: Sort HistoryInfo objects by Id</span></span>

<span data-ttu-id="0738e-137">此命令使用 **Id** 属性对 PowerShell 会话的 **HistoryInfo** 对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-137">This command sorts the PowerShell session's **HistoryInfo** objects using the **Id** property.</span></span> <span data-ttu-id="0738e-138">每个 PowerShell 会话都有自己的命令历史记录。</span><span class="sxs-lookup"><span data-stu-id="0738e-138">Each PowerShell session has its own command history.</span></span>

```
PS> Get-History | Sort-Object -Property Id -Descending

  Id CommandLine
  -- -----------
  10 Get-Command Sort-Object -Syntax
   9 $PSVersionTable
   8 Get-Command Sort-Object -Syntax
   7 Get-Command Sort-Object -ShowCommandInfo
   6 Get-ChildItem -Path C:\Test | Sort-Object -Property Length
   5 Get-Help Clear-History -online
   4 Get-Help Clear-History -full
   3 Get-ChildItem | Get-Member
   2 Get-Command Sort-Object -Syntax
   1 Set-Location C:\Test\
```

<span data-ttu-id="0738e-139">`Get-History`Cmdlet 从当前 PowerShell 会话中获取历史记录对象。</span><span class="sxs-lookup"><span data-stu-id="0738e-139">The `Get-History` cmdlet gets the history objects from the current PowerShell session.</span></span> <span data-ttu-id="0738e-140">对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-140">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-141">`Sort-Object` 使用 **属性** 参数按 **Id** 对对象进行排序。 **降序** 参数按从最新到最旧的命令历史记录进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-141">`Sort-Object` uses the **Property** parameter to sort the objects by **Id** . The **Descending** parameter sorts the command history from newest to oldest.</span></span>

### <span data-ttu-id="0738e-142">示例5：使用哈希表按升序和降序对属性进行排序</span><span class="sxs-lookup"><span data-stu-id="0738e-142">Example 5: Use a hash table to sort properties in ascending and descending order</span></span>

<span data-ttu-id="0738e-143">此命令使用两个属性对对象、 **状态** 和 **DisplayName** 进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-143">This command uses two properties to sort the objects, **Status** and **DisplayName** .</span></span> <span data-ttu-id="0738e-144">**状态** 按降序排序， **DisplayName** 按升序排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-144">**Status** is sorted in descending order and **DisplayName** is sorted in ascending order.</span></span>

<span data-ttu-id="0738e-145">哈希表用于指定 **属性** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="0738e-145">A hash table is used to specify the **Property** parameter's value.</span></span> <span data-ttu-id="0738e-146">哈希表使用表达式来指定属性名称和排序顺序。</span><span class="sxs-lookup"><span data-stu-id="0738e-146">The hash table uses an expression to specify the property names and sort orders.</span></span> <span data-ttu-id="0738e-147">有关哈希表的详细信息，请参阅 [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)。</span><span class="sxs-lookup"><span data-stu-id="0738e-147">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="0738e-148">哈希表中使用的 **Status** 属性是一个枚举属性。</span><span class="sxs-lookup"><span data-stu-id="0738e-148">The **Status** property used in the hash table is an enumerated property.</span></span>
<span data-ttu-id="0738e-149">有关详细信息，请参阅 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)。</span><span class="sxs-lookup"><span data-stu-id="0738e-149">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

```
PS C:\> Get-Service | Sort-Object -Property @{Expression = "Status"; Descending = $True}, @{Expression = "DisplayName"; Descending = $False}

Status   Name               DisplayName
------   ----               -----------
Running  Appinfo            Application Information
Running  BthAvctpSvc        AVCTP service
Running  BrokerInfrastru... Background Tasks Infrastructure Ser...
Running  BDESVC             BitLocker Drive Encryption Service
Running  CoreMessagingRe... CoreMessaging
Running  VaultSvc           Credential Manager
Running  DsSvc              Data Sharing Service
Running  Dhcp               DHCP Client
...
Stopped  ALG                Application Layer Gateway Service
Stopped  AppMgmt            Application Management
Stopped  BITS               Background Intelligent Transfer Ser...
Stopped  wbengine           Block Level Backup Engine Service
Stopped  BluetoothUserSe... Bluetooth User Support Service_14fb...
Stopped  COMSysApp          COM+ System Application
Stopped  smstsmgr           ConfigMgr Task Sequence Agent
Stopped  DeviceInstall      Device Install Service
Stopped  MSDTC              Distributed Transaction Coordinator
```

<span data-ttu-id="0738e-150">`Get-Service`Cmdlet 将获取计算机上的服务列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-150">The `Get-Service` cmdlet gets the list of services on the computer.</span></span> <span data-ttu-id="0738e-151">服务对象将通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-151">The service objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-152">`Sort-Object` 将 **property** 参数与哈希表一起使用，以指定属性名称和排序顺序。</span><span class="sxs-lookup"><span data-stu-id="0738e-152">`Sort-Object` uses the **Property** parameter with a hash table to specify the property names and sort orders.</span></span> <span data-ttu-id="0738e-153">**属性** 参数按两个 **属性进行排序，按** 降序 **排列，按** 升序排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-153">The **Property** parameter is sorted by two properties, **Status** in descending order and **DisplayName** in ascending order.</span></span>

<span data-ttu-id="0738e-154">**状态** 为枚举属性。</span><span class="sxs-lookup"><span data-stu-id="0738e-154">**Status** is an enumerated property.</span></span> <span data-ttu-id="0738e-155">已 **停止** 的值为 **1** ，并且 **运行** 的值为 **4** 。</span><span class="sxs-lookup"><span data-stu-id="0738e-155">**Stopped** has a value of **1** and **Running** has a value of **4** .</span></span> <span data-ttu-id="0738e-156">**降序** 参数设置为， `$True` 以便在 **停止** 进程之前显示 **正在运行** 的进程。</span><span class="sxs-lookup"><span data-stu-id="0738e-156">The **Descending** parameter is set to `$True` so that **Running** processes are displayed before **Stopped** processes.</span></span> <span data-ttu-id="0738e-157">**DisplayName** 将 **降序** 参数设置为 `$False` ，以按字母顺序对显示名称进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-157">**DisplayName** sets the **Descending** parameter to `$False` to sort the display names in alphabetical order.</span></span>

### <span data-ttu-id="0738e-158">示例 6：按时间跨度对文本文件进行排序</span><span class="sxs-lookup"><span data-stu-id="0738e-158">Example 6: Sort text files by time span</span></span>

<span data-ttu-id="0738e-159">此命令按 **CreationTime** 和 **LastWriteTime** 之间的时间跨度以降序对文本文件进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-159">This command sorts text files in descending order by the time span between **CreationTime** and **LastWriteTime** .</span></span>

```
PS> Get-ChildItem -Path C:\Test\*.txt | Sort-Object -Property @{Expression = {$_.CreationTime - $_.LastWriteTime}; Descending = $False} | Format-Table CreationTime, LastWriteTime, FullName

CreationTime          LastWriteTime        FullName
------------          -------------        --------
11/21/2018 12:39:01   2/26/2019 08:59:36   C:\Test\test2.txt
12/4/2018 08:29:41    2/26/2019 08:57:05   C:\Test\powershell_list.txt
2/20/2019 08:15:59    2/26/2019 12:09:43   C:\Test\CreateTestFile.txt
2/20/2019 08:15:59    2/26/2019 12:07:41   C:\Test\Command.txt
2/20/2019 08:15:59    2/26/2019 08:57:52   C:\Test\ReadOnlyFile.txt
11/29/2018 15:16:50   12/4/2018 16:16:24   C:\Test\LogData.txt
2/25/2019 18:25:11    2/26/2019 12:08:47   C:\Test\Zsystemlog.txt
2/25/2019 18:25:11    2/26/2019 08:55:33   C:\Test\Bfile.txt
2/26/2019 08:46:59    2/26/2019 12:12:19   C:\Test\LogFile3.txt

```

<span data-ttu-id="0738e-160">`Get-ChildItem`Cmdlet 使用 **Path** 参数来指定目录 **C:\Test** 以及所有 `*.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="0738e-160">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** and all of the `*.txt` files.</span></span> <span data-ttu-id="0738e-161">对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-161">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="0738e-162">`Sort-Object` 将 **Property** 参数与哈希表一起使用，以确定每个文件在 **CreationTime** 与 **LastWriteTime** 之间的时间跨度。</span><span class="sxs-lookup"><span data-stu-id="0738e-162">`Sort-Object` uses the **Property** parameter with a hash table to determine each files time span between **CreationTime** and **LastWriteTime** .</span></span> <span data-ttu-id="0738e-163">**降序** 参数将设置为 `$False` ，以便按最长到最短时间跨度的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-163">The **Descending** parameter is set to `$False` to sort in the order of longest to shortest time span.</span></span>

### <span data-ttu-id="0738e-164">示例 7：对文本文件中的名称进行排序</span><span class="sxs-lookup"><span data-stu-id="0738e-164">Example 7: Sort names in a text file</span></span>

<span data-ttu-id="0738e-165">此示例演示如何对文本文件中的列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-165">This example shows how to sort a list from a text file.</span></span> <span data-ttu-id="0738e-166">原始文件显示为未排序的列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-166">The original file is displayed as an unsorted list.</span></span> <span data-ttu-id="0738e-167">`Sort-Object` 对内容进行排序，然后用删除重复项的 **唯一** 参数对内容进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-167">`Sort-Object` sorts the contents and then sorts the contents with the **Unique** parameter that removes duplicates.</span></span>

```
PS> Get-Content -Path C:\Test\ServerNames.txt
localhost
server01
server25
LOCALHOST
Server19
server3
localhost

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object
localhost
LOCALHOST
localhost
server01
Server19
server25
server3

PS> Get-Content -Path C:\Test\ServerNames.txt | Sort-Object -Unique
localhost
server01
Server19
server25
server3
```

<span data-ttu-id="0738e-168">`Get-Content`Cmdlet 使用 **Path** 参数来指定目录和文件名。</span><span class="sxs-lookup"><span data-stu-id="0738e-168">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="0738e-169">文件 **ServerNames.txt** 包含计算机名称的未排序列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-169">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span>

<span data-ttu-id="0738e-170">`Get-Content`Cmdlet 使用 **Path** 参数来指定目录和文件名。</span><span class="sxs-lookup"><span data-stu-id="0738e-170">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="0738e-171">文件 **ServerNames.txt** 包含计算机名称的未排序列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-171">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="0738e-172">对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-172">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-173">`Sort-Object` 按默认顺序升序排序列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-173">`Sort-Object` sorts the list in the default order, ascending.</span></span>

<span data-ttu-id="0738e-174">`Get-Content`Cmdlet 使用 **Path** 参数来指定目录和文件名。</span><span class="sxs-lookup"><span data-stu-id="0738e-174">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="0738e-175">文件 **ServerNames.txt** 包含计算机名称的未排序列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-175">The file **ServerNames.txt** contains an unsorted list of computer names.</span></span> <span data-ttu-id="0738e-176">对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-176">The objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-177">`Sort-Object` 使用 **Unique** 参数删除重复的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="0738e-177">`Sort-Object` uses the **Unique** parameter to remove duplicate computer names.</span></span> <span data-ttu-id="0738e-178">列表按默认顺序升序排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-178">The list is sorted in the default order, ascending.</span></span>

### <span data-ttu-id="0738e-179">示例8：将字符串作为整数排序</span><span class="sxs-lookup"><span data-stu-id="0738e-179">Example 8: Sort a string as an integer</span></span>

<span data-ttu-id="0738e-180">此示例演示如何对包含字符串对象的文本文件进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-180">This example shows how to sort a text file that contains string objects as integers.</span></span> <span data-ttu-id="0738e-181">可以将每个命令向下发送到管道， `Get-Member` 并验证对象是否为字符串而不是整数。</span><span class="sxs-lookup"><span data-stu-id="0738e-181">You can send each command down the pipeline to `Get-Member` and verify that the objects are strings instead of integers.</span></span> <span data-ttu-id="0738e-182">对于这些示例， `ProductId.txt` 文件包含未排序的产品编号列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-182">For these examples, the `ProductId.txt` file contains an unsorted list of product numbers.</span></span>

<span data-ttu-id="0738e-183">在第一个示例中， `Get-Content` 获取该 cmdlet 的文件和管道的内容 `Sort-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0738e-183">In the first example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-184">`Sort-Object` 按升序对字符串对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-184">`Sort-Object` sorts the string objects in ascending order.</span></span>

```
PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object
0
1
12345
1500
2
2800
3500
4100
500
6200
77
88
99999

PS> Get-Content -Path C:\Test\ProductId.txt | Sort-Object {[int]$_}
0
1
2
77
88
500
1500
2800
3500
4100
6200
12345
99999
```

<span data-ttu-id="0738e-185">在第二个示例中， `Get-Content` 获取该 cmdlet 的文件和管道的内容 `Sort-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0738e-185">In the second example, `Get-Content` gets the contents of the file and pipes lines to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-186">`Sort-Object` 使用脚本块将字符串转换为整数。</span><span class="sxs-lookup"><span data-stu-id="0738e-186">`Sort-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="0738e-187">在示例代码中， `[int]` 将字符串转换为整数，并 `$_` 表示每个字符串在管道中出现。</span><span class="sxs-lookup"><span data-stu-id="0738e-187">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="0738e-188">整数对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-188">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span>
<span data-ttu-id="0738e-189">`Sort-Object` 按数值顺序对整数对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-189">`Sort-Object` sorts the integer objects in numeric order.</span></span>

<span data-ttu-id="0738e-190">`Get-Content`Cmdlet 使用 **Path** 参数来指定目录和文件名。</span><span class="sxs-lookup"><span data-stu-id="0738e-190">The `Get-Content` cmdlet uses the **Path** parameter to specify the directory and file name.</span></span> <span data-ttu-id="0738e-191">文件 **ProductId.txt** 包含未排序的产品编号列表。</span><span class="sxs-lookup"><span data-stu-id="0738e-191">The file **ProductId.txt** contains an unsorted list of product numbers.</span></span> <span data-ttu-id="0738e-192">字符串对象通过管道向下发送到 `ForEach-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-192">The string objects are sent down the pipeline to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="0738e-193">`ForEach-Object` 使用脚本块将字符串转换为整数。</span><span class="sxs-lookup"><span data-stu-id="0738e-193">`ForEach-Object` uses a script block to convert the strings to integers.</span></span> <span data-ttu-id="0738e-194">在示例代码中， `[int]` 将字符串转换为整数，并 `$_` 表示每个字符串在管道中出现。</span><span class="sxs-lookup"><span data-stu-id="0738e-194">In the sample code, `[int]` converts the string to an integer and `$_` represents each string as it comes down the pipeline.</span></span> <span data-ttu-id="0738e-195">整数对象通过管道向下发送到 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0738e-195">The integer objects are sent down the pipeline to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="0738e-196">`Sort-Object` 按数值顺序对整数对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-196">`Sort-Object` sorts the integer objects in numeric order.</span></span>
## <span data-ttu-id="0738e-197">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0738e-197">PARAMETERS</span></span>

### <span data-ttu-id="0738e-198">-CaseSensitive</span><span class="sxs-lookup"><span data-stu-id="0738e-198">-CaseSensitive</span></span>

<span data-ttu-id="0738e-199">指示排序区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0738e-199">Indicates that the sort is case-sensitive.</span></span> <span data-ttu-id="0738e-200">默认情况下，排序不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0738e-200">By default, sorts are not case-sensitive.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Case-insensitive
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0738e-201">-Culture</span><span class="sxs-lookup"><span data-stu-id="0738e-201">-Culture</span></span>

<span data-ttu-id="0738e-202">指定用于排序的区域性配置。</span><span class="sxs-lookup"><span data-stu-id="0738e-202">Specifies the cultural configuration to use for sorts.</span></span> <span data-ttu-id="0738e-203">用于 `Get-Culture` 显示系统的区域性配置。</span><span class="sxs-lookup"><span data-stu-id="0738e-203">Use `Get-Culture` to display the system's culture configuration.</span></span>

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

### <span data-ttu-id="0738e-204">-Descending</span><span class="sxs-lookup"><span data-stu-id="0738e-204">-Descending</span></span>

<span data-ttu-id="0738e-205">指示按 `Sort-Object` 降序对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-205">Indicates that `Sort-Object` sorts the objects in descending order.</span></span> <span data-ttu-id="0738e-206">默认值为升序。</span><span class="sxs-lookup"><span data-stu-id="0738e-206">The default is ascending order.</span></span>

<span data-ttu-id="0738e-207">若要使用不同的排序顺序对多个属性进行排序，请使用哈希表。</span><span class="sxs-lookup"><span data-stu-id="0738e-207">To sort multiple properties with different sort orders, use a hash table.</span></span> <span data-ttu-id="0738e-208">例如，使用哈希表，可以按升序对一个属性进行排序，而按降序对另一个属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-208">For example, with a hash table you can sort one property in ascending order and another property in descending order.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Ascending
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0738e-209">-InputObject</span><span class="sxs-lookup"><span data-stu-id="0738e-209">-InputObject</span></span>

<span data-ttu-id="0738e-210">若要对对象进行排序，请将其向下发送到 `Sort-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0738e-210">To sort objects, send them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="0738e-211">如果使用 **InputObject** 参数提交项的集合，则将 `Sort-Object` 接收一个表示该集合的对象。</span><span class="sxs-lookup"><span data-stu-id="0738e-211">If you use the **InputObject** parameter to submit a collection of items, `Sort-Object` receives one object that represents the collection.</span></span> <span data-ttu-id="0738e-212">由于无法对一个对象进行排序，因此 `Sort-Object` 返回未更改的整个集合。</span><span class="sxs-lookup"><span data-stu-id="0738e-212">Because one object cannot be sorted, `Sort-Object` returns the entire collection unchanged.</span></span>

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

### <span data-ttu-id="0738e-213">-Property</span><span class="sxs-lookup"><span data-stu-id="0738e-213">-Property</span></span>

<span data-ttu-id="0738e-214">指定用于对 `Sort-Object` 对象进行排序的属性名称。</span><span class="sxs-lookup"><span data-stu-id="0738e-214">Specifies the property names that `Sort-Object` uses to sort the objects.</span></span> <span data-ttu-id="0738e-215">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0738e-215">Wildcards are permitted.</span></span>
<span data-ttu-id="0738e-216">根据属性值对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-216">Objects are sorted based on the property values.</span></span> <span data-ttu-id="0738e-217">如果未指定属性，则会 `Sort-Object` 根据对象类型或对象本身的默认属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-217">If you do not specify a property, `Sort-Object` sorts based on default properties for the object type or the objects themselves.</span></span>

<span data-ttu-id="0738e-218">多个属性可以按升序、降序或排序顺序的组合进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-218">Multiple properties can be sorted in ascending order, descending order, or a combination of sort orders.</span></span> <span data-ttu-id="0738e-219">如果指定多个属性，则按第一个属性对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-219">When you specify multiple properties, the objects are sorted by the first property.</span></span> <span data-ttu-id="0738e-220">如果有多个对象的第一个属性的值相同，则按第二个属性对这些对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-220">If multiple objects have the same value for the first property, those objects are sorted by the second property.</span></span> <span data-ttu-id="0738e-221">此过程将一直继续，直到不存在其他指的定属性或没有对象组。</span><span class="sxs-lookup"><span data-stu-id="0738e-221">This process continues until there are no more specified properties or no groups of objects.</span></span>

<span data-ttu-id="0738e-222">**属性** 参数的值可以是计算属性。</span><span class="sxs-lookup"><span data-stu-id="0738e-222">The **Property** parameter's value can be a calculated property.</span></span> <span data-ttu-id="0738e-223">若要创建计算属性，请使用哈希表。</span><span class="sxs-lookup"><span data-stu-id="0738e-223">To create a calculated property, use a hash table.</span></span>

<span data-ttu-id="0738e-224">哈希表的有效键如下所示：</span><span class="sxs-lookup"><span data-stu-id="0738e-224">Valid keys for a hash table are as follows:</span></span>

- <span data-ttu-id="0738e-225">`expression` - `<string>` 或 `<script block>`</span><span class="sxs-lookup"><span data-stu-id="0738e-225">`expression` - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="0738e-226">`ascending` 或 `descending` - `<boolean>`</span><span class="sxs-lookup"><span data-stu-id="0738e-226">`ascending` or `descending` - `<boolean>`</span></span>

<span data-ttu-id="0738e-227">有关详细信息，请参阅 [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="0738e-227">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: Default properties
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="0738e-228">-Unique</span><span class="sxs-lookup"><span data-stu-id="0738e-228">-Unique</span></span>

<span data-ttu-id="0738e-229">指示 `Sort-Object` 消除重复项并仅返回集合中的唯一成员。</span><span class="sxs-lookup"><span data-stu-id="0738e-229">Indicates that `Sort-Object` eliminates duplicates and returns only the unique members of the collection.</span></span> <span data-ttu-id="0738e-230">唯一值的第一个实例包括在已排序的输出中。</span><span class="sxs-lookup"><span data-stu-id="0738e-230">The first instance of a unique value is included in the sorted output.</span></span>

<span data-ttu-id="0738e-231">**Unique** 不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0738e-231">**Unique** is case-insensitive.</span></span> <span data-ttu-id="0738e-232">只有字符大小写不同的字符串被视为相同。</span><span class="sxs-lookup"><span data-stu-id="0738e-232">Strings that only differ by character case are considered the same.</span></span>
<span data-ttu-id="0738e-233">例如，字符和字符。</span><span class="sxs-lookup"><span data-stu-id="0738e-233">For example, character and CHARACTER.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: All
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0738e-234">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0738e-234">CommonParameters</span></span>

<span data-ttu-id="0738e-235">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0738e-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0738e-236">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0738e-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0738e-237">输入</span><span class="sxs-lookup"><span data-stu-id="0738e-237">INPUTS</span></span>

### <span data-ttu-id="0738e-238">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0738e-238">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0738e-239">可以通过管道将要排序的对象传递给 `Sort-Object` 。</span><span class="sxs-lookup"><span data-stu-id="0738e-239">You can pipe the objects to be sorted to `Sort-Object`.</span></span>

## <span data-ttu-id="0738e-240">输出</span><span class="sxs-lookup"><span data-stu-id="0738e-240">OUTPUTS</span></span>

### <span data-ttu-id="0738e-241">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="0738e-241">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="0738e-242">`Sort-Object` 返回已排序的对象。</span><span class="sxs-lookup"><span data-stu-id="0738e-242">`Sort-Object` returns the sorted objects.</span></span>

## <span data-ttu-id="0738e-243">注释</span><span class="sxs-lookup"><span data-stu-id="0738e-243">NOTES</span></span>

<span data-ttu-id="0738e-244">该 `Sort-Object` cmdlet 根据命令中指定的属性或对象类型的默认排序属性来对对象进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-244">The `Sort-Object` cmdlet sorts objects based on properties specified in the command or the default sort properties for the object type.</span></span> <span data-ttu-id="0738e-245">使用 `PropertySet` 文件中指定的来定义默认的排序属性 `DefaultKeyPropertySet` `types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="0738e-245">Default sort properties are defined using the `PropertySet` named `DefaultKeyPropertySet` in a `types.ps1xml` file.</span></span> <span data-ttu-id="0738e-246">有关详细信息，请参阅 [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml)。</span><span class="sxs-lookup"><span data-stu-id="0738e-246">For more information, see [about_Types.ps1xml](/powershell/module/Microsoft.PowerShell.Core/About/about_Types.ps1xml).</span></span>

<span data-ttu-id="0738e-247">如果对象不具有指定的属性之一，则会将该对象的属性值解释 `Sort-Object` 为 **Null** ，并将其放置在排序顺序的末尾。</span><span class="sxs-lookup"><span data-stu-id="0738e-247">If an object does not have one of the specified properties, the property value for that object is interpreted by `Sort-Object` as **Null** and placed at the end of the sort order.</span></span>

<span data-ttu-id="0738e-248">如果没有可用的排序属性，则 PowerShell 会尝试比较对象本身。</span><span class="sxs-lookup"><span data-stu-id="0738e-248">When no sort properties are available, PowerShell attempts to compare the objects themselves.</span></span>
<span data-ttu-id="0738e-249">`Sort-Object` 对每个属性使用 **Compare** 方法。</span><span class="sxs-lookup"><span data-stu-id="0738e-249">`Sort-Object` uses the **Compare** method for each property.</span></span> <span data-ttu-id="0738e-250">如果某个属性未实现 **IComparable** ，则该 cmdlet 会将属性值转换为字符串，并将 **Compare** 方法用于 **system.string** 。</span><span class="sxs-lookup"><span data-stu-id="0738e-250">If a property does not implement **IComparable** , the cmdlet converts the property value to a string and uses the **Compare** method for **System.String** .</span></span> <span data-ttu-id="0738e-251">有关详细信息，请参阅 [CompareTo (Object) 方法](/dotnet/api/system.management.automation.psobject.compareto)。</span><span class="sxs-lookup"><span data-stu-id="0738e-251">For more information, see [PSObject.CompareTo(Object) Method](/dotnet/api/system.management.automation.psobject.compareto).</span></span>

<span data-ttu-id="0738e-252">如果对枚举属性（如 **状态** ）进行排序，则 `Sort-Object` 按枚举值排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-252">If you sort on an enumerated property such as **Status** , `Sort-Object` sorts by the enumeration values.</span></span> <span data-ttu-id="0738e-253">对于 Windows 服务，"已 **停止** " 的值为 **1** ，并且 **运行** 的值为 **4** 。</span><span class="sxs-lookup"><span data-stu-id="0738e-253">For Windows services, **Stopped** has a value of **1** and **Running** has a value of **4** .</span></span>
<span data-ttu-id="0738e-254">由于枚举值的原因， **停止** 在 **运行** 前进行排序。</span><span class="sxs-lookup"><span data-stu-id="0738e-254">**Stopped** is sorted before **Running** because of the enumerated values.</span></span> <span data-ttu-id="0738e-255">有关详细信息，请参阅 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)。</span><span class="sxs-lookup"><span data-stu-id="0738e-255">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="0738e-256">相关链接</span><span class="sxs-lookup"><span data-stu-id="0738e-256">RELATED LINKS</span></span>

[<span data-ttu-id="0738e-257">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="0738e-257">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="0738e-258">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="0738e-258">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="0738e-259">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="0738e-259">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="0738e-260">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-260">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="0738e-261">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-261">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="0738e-262">Group-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-262">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="0738e-263">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-263">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="0738e-264">New-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-264">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="0738e-265">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-265">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="0738e-266">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="0738e-266">Tee-Object</span></span>](Tee-Object.md)
