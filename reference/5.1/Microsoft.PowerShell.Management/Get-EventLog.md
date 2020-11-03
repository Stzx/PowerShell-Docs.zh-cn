---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 3/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-eventlog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-EventLog
ms.openlocfilehash: ab1a97dc3c78bbfdcc239fd573ef3b1f839e2b21
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198297"
---
# <span data-ttu-id="8efd3-103">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="8efd3-103">Get-EventLog</span></span>

## <span data-ttu-id="8efd3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8efd3-104">SYNOPSIS</span></span>
<span data-ttu-id="8efd3-105">获取在本地计算机或远程计算机上的事件日志或事件日志列表中的事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-105">Gets the events in an event log, or a list of the event logs, on the local computer or remote computers.</span></span>

## <span data-ttu-id="8efd3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8efd3-106">SYNTAX</span></span>

### <span data-ttu-id="8efd3-107">LogName（默认值）</span><span class="sxs-lookup"><span data-stu-id="8efd3-107">LogName (Default)</span></span>

```
Get-EventLog [-LogName] <String> [-ComputerName <String[]>] [-Newest <Int32>] [-After <DateTime>]
 [-Before <DateTime>] [-UserName <String[]>] [[-InstanceId] <Int64[]>] [-Index <Int32[]>]
 [-EntryType <String[]>] [-Source <String[]>] [-Message <String>] [-AsBaseObject]
 [<CommonParameters>]
```

### <span data-ttu-id="8efd3-108">列出</span><span class="sxs-lookup"><span data-stu-id="8efd3-108">List</span></span>

```
Get-EventLog [-ComputerName <String[]>] [-List] [-AsString] [<CommonParameters>]
```

## <span data-ttu-id="8efd3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8efd3-109">DESCRIPTION</span></span>

<span data-ttu-id="8efd3-110">`Get-EventLog`Cmdlet 将从本地和远程计算机获取事件和事件日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-110">The `Get-EventLog` cmdlet gets events and event logs from local and remote computers.</span></span> <span data-ttu-id="8efd3-111">默认情况下， `Get-EventLog` 从本地计算机获取日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-111">By default, `Get-EventLog` gets logs from the local computer.</span></span> <span data-ttu-id="8efd3-112">若要从远程计算机获取日志，请使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="8efd3-112">To get logs from remote computers, use the **ComputerName** parameter.</span></span>

<span data-ttu-id="8efd3-113">您可以使用 `Get-EventLog` 参数和属性值来搜索事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-113">You can use the `Get-EventLog` parameters and property values to search for events.</span></span> <span data-ttu-id="8efd3-114">Cmdlet 将获取与指定的属性值匹配的事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-114">The cmdlet gets events that match the specified property values.</span></span>

<span data-ttu-id="8efd3-115">包含名词的 PowerShell cmdlet `EventLog` 仅适用于 Windows 经典事件日志，例如应用程序、系统或安全性。</span><span class="sxs-lookup"><span data-stu-id="8efd3-115">PowerShell cmdlets that contain the `EventLog` noun work only on Windows classic event logs such as Application, System, or Security.</span></span> <span data-ttu-id="8efd3-116">若要在 Windows Vista 和更高版本的 Windows 版本中获取使用 Windows 事件日志技术的日志，请使用 `Get-WinEvent` 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-116">To get logs that use the Windows Event Log technology in Windows Vista and later Windows versions, use `Get-WinEvent`.</span></span>

> [!NOTE]
> <span data-ttu-id="8efd3-117">`Get-EventLog` 使用已弃用的 Win32 API。</span><span class="sxs-lookup"><span data-stu-id="8efd3-117">`Get-EventLog` uses a Win32 API that is deprecated.</span></span> <span data-ttu-id="8efd3-118">结果可能不准确。</span><span class="sxs-lookup"><span data-stu-id="8efd3-118">The results may not be accurate.</span></span> <span data-ttu-id="8efd3-119">请改用 `Get-WinEvent` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8efd3-119">Use the `Get-WinEvent` cmdlet instead.</span></span>

## <span data-ttu-id="8efd3-120">示例</span><span class="sxs-lookup"><span data-stu-id="8efd3-120">EXAMPLES</span></span>

### <span data-ttu-id="8efd3-121">示例1：获取本地计算机上的事件日志</span><span class="sxs-lookup"><span data-stu-id="8efd3-121">Example 1: Get event logs on the local computer</span></span>

<span data-ttu-id="8efd3-122">此示例显示了本地计算机上可用事件日志的列表。</span><span class="sxs-lookup"><span data-stu-id="8efd3-122">This example displays the list of event logs that are available on the local computer.</span></span> <span data-ttu-id="8efd3-123">Log 列中的名称与 **LogName** 参数一起使用，以指定搜索事件的日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-123">The names in the Log column are used with the **LogName** parameter to specify which log is searched for events.</span></span>

```powershell
Get-EventLog -List
```

```Output
Max(K)   Retain   OverflowAction      Entries  Log
------   ------   --------------      -------  ---
15,168        0   OverwriteAsNeeded   20,792   Application
15,168        0   OverwriteAsNeeded   12,559   System
15,360        0   OverwriteAsNeeded   11,173   Windows PowerShell
```

<span data-ttu-id="8efd3-124">`Get-EventLog`Cmdlet 使用 **List** 参数显示可用的日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-124">The `Get-EventLog` cmdlet uses the **List** parameter to display the available logs.</span></span>

### <span data-ttu-id="8efd3-125">示例2：获取本地计算机上的事件日志中的最新条目</span><span class="sxs-lookup"><span data-stu-id="8efd3-125">Example 2: Get recent entries from an event log on the local computer</span></span>

<span data-ttu-id="8efd3-126">此示例获取系统事件日志中的最新条目。</span><span class="sxs-lookup"><span data-stu-id="8efd3-126">This example gets recent entries from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -Newest 5
```

```Output
Index   Time          EntryType    Source              InstanceID   Message
-----   ----          ---------    ------              ----------   -------
13820   Jan 17 19:16  Error        DCOM                     10016   The description for Event...
13819   Jan 17 19:08  Error        DCOM                     10016   The description for Event...
13818   Jan 17 19:06  Information  Service Control...  1073748864   The start type of the Back...
13817   Jan 17 19:05  Error        DCOM                     10016   The description for Event...
13815   Jan 17 19:03  Information  Microsoft-Windows...        35   The time service is now sync...
```

<span data-ttu-id="8efd3-127">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-127">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="8efd3-128">**最新** 参数返回五个最新事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-128">The **Newest** parameter returns the five most recent events.</span></span>

### <span data-ttu-id="8efd3-129">示例3：查找事件日志中特定数量的条目的所有源</span><span class="sxs-lookup"><span data-stu-id="8efd3-129">Example 3: Find all sources for a specific number of entries in an event log</span></span>

<span data-ttu-id="8efd3-130">此示例显示了如何查找系统事件日志中最新的1000条目中包含的所有源。</span><span class="sxs-lookup"><span data-stu-id="8efd3-130">This example shows how to find all of the sources that are included in the 1000 most recent entries in the System event log.</span></span>

```powershell
$Events = Get-EventLog -LogName System -Newest 1000
$Events | Group-Object -Property Source -NoElement | Sort-Object -Property Count -Descending
```

```Output
Count   Name
-----   ----
  110   DCOM
   65   Service Control Manager
   51   Microsoft-Windows-Kern...
   14   EventLog
   14   BTHUSB
   13   Win32k
```

<span data-ttu-id="8efd3-131">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-131">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="8efd3-132">**最新** 参数选择1000个最近事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-132">The **Newest** parameter selects the 1000 most recent events.</span></span> <span data-ttu-id="8efd3-133">事件对象存储在 `$Events` 变量中。</span><span class="sxs-lookup"><span data-stu-id="8efd3-133">The event objects are stored in the `$Events` variable.</span></span> <span data-ttu-id="8efd3-134">`$Events`对象通过管道向下发送到 `Group-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8efd3-134">The `$Events` objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span>
<span data-ttu-id="8efd3-135">`Group-Object` 使用 **Property** 参数按源将对象分组，并对每个源的对象的数目进行计数。</span><span class="sxs-lookup"><span data-stu-id="8efd3-135">`Group-Object` uses the **Property** parameter to group the objects by source and counts the number of objects for each source.</span></span> <span data-ttu-id="8efd3-136">**NoElement** 参数从输出中删除组成员。</span><span class="sxs-lookup"><span data-stu-id="8efd3-136">The **NoElement** parameter removes the group members from the output.</span></span>
<span data-ttu-id="8efd3-137">`Sort-Object`Cmdlet 使用 **Property** 参数按每个源名称的计数进行排序。</span><span class="sxs-lookup"><span data-stu-id="8efd3-137">The `Sort-Object` cmdlet uses the **Property** parameter to sort by the count of each source name.</span></span>
<span data-ttu-id="8efd3-138">**降序** 参数按从最高到最低的顺序对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="8efd3-138">The **Descending** parameter sorts the list in order by count from highest to lowest.</span></span>

### <span data-ttu-id="8efd3-139">示例4：获取特定事件日志中的错误事件</span><span class="sxs-lookup"><span data-stu-id="8efd3-139">Example 4: Get error events from a specific event log</span></span>

<span data-ttu-id="8efd3-140">此示例获取系统事件日志中的错误事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-140">This example gets error events from the System event log.</span></span>

```powershell
Get-EventLog -LogName System -EntryType Error
```

```Output
Index Time          EntryType   Source  InstanceID Message
----- ----          ---------   ------  ---------- -------
13296 Jan 16 13:53  Error       DCOM    10016 The description for Event ID '10016' in Source...
13291 Jan 16 13:51  Error       DCOM    10016 The description for Event ID '10016' in Source...
13245 Jan 16 11:45  Error       DCOM    10016 The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error       DCOM    10016 The description for Event ID '10016' in Source...
```

<span data-ttu-id="8efd3-141">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-141">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="8efd3-142">**EntryType** 参数将筛选事件，以便仅显示错误事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-142">The **EntryType** parameter filters the events to show only Error events.</span></span>

### <span data-ttu-id="8efd3-143">示例5：从具有 InstanceId 和源值的事件日志获取事件</span><span class="sxs-lookup"><span data-stu-id="8efd3-143">Example 5: Get events from an event log with an InstanceId and Source value</span></span>

<span data-ttu-id="8efd3-144">此示例从系统日志获取特定 InstanceId 和源的事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-144">This example gets events from the System log for a specific InstanceId and Source.</span></span>

```powershell
Get-EventLog -LogName System -InstanceId 10016 -Source DCOM
```

```Output
Index Time          EntryType  Source  InstanceID  Message
----- ----          ---------  ------  ----------  -------
13245 Jan 16 11:45  Error      DCOM         10016  The description for Event ID '10016' in Source...
13230 Jan 16 11:07  Error      DCOM         10016  The description for Event ID '10016' in Source...
13219 Jan 16 10:00  Error      DCOM         10016  The description for Event ID '10016' in Source...
```

<span data-ttu-id="8efd3-145">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-145">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="8efd3-146">**InstanceID** 参数选择具有指定实例 ID 的事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-146">The **InstanceID** parameter selects the events with the specified Instance ID.</span></span> <span data-ttu-id="8efd3-147">**Source** 参数指定事件属性。</span><span class="sxs-lookup"><span data-stu-id="8efd3-147">The **Source** parameter specifies the event property.</span></span>

### <span data-ttu-id="8efd3-148">示例6：从多台计算机获取事件</span><span class="sxs-lookup"><span data-stu-id="8efd3-148">Example 6: Get events from multiple computers</span></span>

<span data-ttu-id="8efd3-149">此命令从三台计算机上的系统事件日志中获取事件： Server01、Server02 和 Server03。</span><span class="sxs-lookup"><span data-stu-id="8efd3-149">This command gets the events from the System event log on three computers: Server01, Server02, and Server03.</span></span>

```powershell
Get-EventLog -LogName System -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="8efd3-150">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-150">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="8efd3-151">**ComputerName** 参数使用以逗号分隔的字符串来列出要从中获取事件日志的计算机。</span><span class="sxs-lookup"><span data-stu-id="8efd3-151">The **ComputerName** parameter uses a comma-separated string to list the computers from which you want to get the event logs.</span></span>

### <span data-ttu-id="8efd3-152">示例7：获取消息中包含特定单词的所有事件</span><span class="sxs-lookup"><span data-stu-id="8efd3-152">Example 7: Get all events that include a specific word in the message</span></span>

<span data-ttu-id="8efd3-153">此命令获取系统事件日志中的所有事件，这些事件包含事件消息中的特定字词。</span><span class="sxs-lookup"><span data-stu-id="8efd3-153">This command gets all the events in the System event log that contain a specific word in the event's message.</span></span> <span data-ttu-id="8efd3-154">您指定的 **消息** 参数的值可能包含在消息的内容中，而不会显示在 PowerShell 控制台上。</span><span class="sxs-lookup"><span data-stu-id="8efd3-154">It's possible that your specified **Message** parameter's value is included in the message's content but isn't displayed on the PowerShell console.</span></span>

```powershell
Get-EventLog -LogName System -Message *description*
```

```Output
Index Time          EntryType   Source       InstanceID   Message
----- ----          ---------   ------       ----------   -------
13821 Jan 17 19:17  Error       DCOM              10016   The description for Event ID '10016'...
13820 Jan 17 19:16  Error       DCOM              10016   The description for Event ID '10016'...
13819 Jan 17 19:08  Error       DCOM              10016   The description for Event ID '10016'...
```

<span data-ttu-id="8efd3-155">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-155">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="8efd3-156">**Message** 参数指定要在每个事件的消息字段中搜索的字。</span><span class="sxs-lookup"><span data-stu-id="8efd3-156">The **Message** parameter specifies a word to search for in the message field of each event.</span></span>

### <span data-ttu-id="8efd3-157">示例8：显示事件的属性值</span><span class="sxs-lookup"><span data-stu-id="8efd3-157">Example 8: Display the property values of an event</span></span>

<span data-ttu-id="8efd3-158">此示例演示如何显示事件的所有属性和值。</span><span class="sxs-lookup"><span data-stu-id="8efd3-158">This example shows how to display all of an event's properties and values.</span></span>

```powershell
$A = Get-EventLog -LogName System -Newest 1
$A | Select-Object -Property *
```

```Output
EventID            : 10016
MachineName        : localhost
Data               : {}
Index              : 13821
Category           : (0)
CategoryNumber     : 0
EntryType          : Error
Message            : The description for Event ID '10016' in Source 'DCOM'...
Source             : DCOM
ReplacementStrings : {Local,...}
InstanceId         : 10016
TimeGenerated      : 1/17/2019 19:17:23
TimeWritten        : 1/17/2019 19:17:23
UserName           : username
Site               :
Container          :
```

<span data-ttu-id="8efd3-159">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-159">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System event log.</span></span> <span data-ttu-id="8efd3-160">**最新** 的参数选择最新的事件对象。</span><span class="sxs-lookup"><span data-stu-id="8efd3-160">The **Newest** parameter selects the most recent event object.</span></span> <span data-ttu-id="8efd3-161">对象存储在 `$A` 变量中。</span><span class="sxs-lookup"><span data-stu-id="8efd3-161">The object is stored in the `$A` variable.</span></span> <span data-ttu-id="8efd3-162">变量中的对象通过 `$A` 管道向下发送到 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8efd3-162">The object in the `$A` variable is sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="8efd3-163">`Select-Object` 使用带有星号的 **属性** 参数 (`*`) 选择该对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="8efd3-163">`Select-Object` uses the **Property** parameter with an asterisk (`*`) to select all of the object's properties.</span></span>

### <span data-ttu-id="8efd3-164">示例9：使用源和事件 ID 从事件日志中获取事件</span><span class="sxs-lookup"><span data-stu-id="8efd3-164">Example 9: Get events from an event log using a source and event ID</span></span>

<span data-ttu-id="8efd3-165">此示例获取指定源和事件 ID 的事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-165">This example gets events for a specified Source and Event ID.</span></span>

```powershell
Get-EventLog -LogName Application -Source Outlook | Where-Object {$_.EventID -eq 63} |
              Select-Object -Property Source, EventID, InstanceId, Message
```

```Output
Source   EventID   InstanceId   Message
------   -------   ----------   -------
Outlook       63   1073741887   The Exchange web service request succeeded.
Outlook       63   1073741887   Outlook detected a change notification.
Outlook       63   1073741887   The Exchange web service request succeeded.
```

<span data-ttu-id="8efd3-166">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-166">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the Application event log.</span></span> <span data-ttu-id="8efd3-167">**Source** 参数指定应用程序名称 Outlook。</span><span class="sxs-lookup"><span data-stu-id="8efd3-167">The **Source** parameter specifies the application name, Outlook.</span></span> <span data-ttu-id="8efd3-168">对象通过管道向下发送到 `Where-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8efd3-168">The objects are sent down the pipeline to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="8efd3-169">对于管道中的每个对象，该 `Where-Object` cmdlet 都使用变量将 `$_.EventID` 事件 ID 属性与指定值进行比较。</span><span class="sxs-lookup"><span data-stu-id="8efd3-169">For each object in the pipeline, the `Where-Object` cmdlet uses the variable `$_.EventID` to compare the Event ID property to the specified value.</span></span> <span data-ttu-id="8efd3-170">对象通过管道向下发送到 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8efd3-170">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span> <span data-ttu-id="8efd3-171">`Select-Object` 使用 **Property** 参数来选择要在 PowerShell 控制台中显示的属性。</span><span class="sxs-lookup"><span data-stu-id="8efd3-171">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="8efd3-172">示例10：按属性获取事件和分组</span><span class="sxs-lookup"><span data-stu-id="8efd3-172">Example 10: Get events and group by a property</span></span>

```powershell
Get-EventLog -LogName System -UserName NT* | Group-Object -Property UserName -NoElement |
              Select-Object -Property Count, Name
```

```Output
Count  Name
-----  ----
6031   NT AUTHORITY\SYSTEM
  42   NT AUTHORITY\LOCAL SERVICE
   4   NT AUTHORITY\NETWORK SERVICE
```

<span data-ttu-id="8efd3-173">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-173">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="8efd3-174">**UserName** 参数包含星号 (`*`) 通配符来指定一部分的用户名。</span><span class="sxs-lookup"><span data-stu-id="8efd3-174">The **UserName** parameter includes the asterisk (`*`) wildcard to specify a portion of the user name.</span></span> <span data-ttu-id="8efd3-175">事件对象将通过管道向下发送到 `Group-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8efd3-175">The event objects are sent down the pipeline to the `Group-Object` cmdlet.</span></span> <span data-ttu-id="8efd3-176">`Group-Object` 使用 **property** 参数来指定 **UserName** 属性用于对对象进行分组，并计算每个用户名的对象数。</span><span class="sxs-lookup"><span data-stu-id="8efd3-176">`Group-Object` uses the **Property** parameter to specify that the **UserName** property is used to group the objects and count the number of objects for each user name.</span></span> <span data-ttu-id="8efd3-177">**NoElement** 参数从输出中删除组成员。</span><span class="sxs-lookup"><span data-stu-id="8efd3-177">The **NoElement** parameter removes the group members from the output.</span></span> <span data-ttu-id="8efd3-178">对象通过管道向下发送到 `Select-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8efd3-178">The objects are sent down the pipeline to the `Select-Object` cmdlet.</span></span>
<span data-ttu-id="8efd3-179">`Select-Object` 使用 **Property** 参数来选择要在 PowerShell 控制台中显示的属性。</span><span class="sxs-lookup"><span data-stu-id="8efd3-179">`Select-Object` uses the **Property** parameter to select the properties to display in the PowerShell console.</span></span>

### <span data-ttu-id="8efd3-180">示例11：获取在特定日期和时间范围内发生的事件</span><span class="sxs-lookup"><span data-stu-id="8efd3-180">Example 11: Get events that occurred during a specific date and time range</span></span>

<span data-ttu-id="8efd3-181">此示例从系统事件日志中获取指定日期和时间范围内的错误事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-181">This example gets Error events from the System event log for a specified date and time range.</span></span> <span data-ttu-id="8efd3-182">**Before** 和 **After** 参数设置日期和时间范围，但不包括在输出中。</span><span class="sxs-lookup"><span data-stu-id="8efd3-182">The **Before** and **After** parameters set the date and time range but are excluded from the output.</span></span>

```powershell
$Begin = Get-Date -Date '1/17/2019 08:00:00'
$End = Get-Date -Date '1/17/2019 17:00:00'
Get-EventLog -LogName System -EntryType Error -After $Begin -Before $End
```

```Output
Index Time          EntryType   Source   InstanceID  Message
----- ----          ---------   ------   ----------  -------
13821 Jan 17 13:40  Error       DCOM          10016  The description for Event ID...
13820 Jan 17 13:11  Error       DCOM          10016  The description for Event ID...
...
12372 Jan 17 10:08  Error       DCOM          10016  The description for Event ID...
12371 Jan 17 09:04  Error       DCOM          10016  The description for Event ID...
```

<span data-ttu-id="8efd3-183">`Get-Date`Cmdlet 使用 **date** 参数来指定日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8efd3-183">The `Get-Date` cmdlet uses the **Date** parameter to specify a date and time.</span></span> <span data-ttu-id="8efd3-184">**DateTime** 对象存储在 `$Begin` 和 `$End` 变量中。</span><span class="sxs-lookup"><span data-stu-id="8efd3-184">The **DateTime** objects are stored in the `$Begin` and `$End` variables.</span></span> <span data-ttu-id="8efd3-185">`Get-EventLog`Cmdlet 使用 **LogName** 参数来指定系统日志。</span><span class="sxs-lookup"><span data-stu-id="8efd3-185">The `Get-EventLog` cmdlet uses the **LogName** parameter to specify the System log.</span></span> <span data-ttu-id="8efd3-186">**EntryType** 参数指定错误事件类型。</span><span class="sxs-lookup"><span data-stu-id="8efd3-186">The **EntryType** parameter specifies the Error event type.</span></span> <span data-ttu-id="8efd3-187">日期和时间范围由 **后面** 的参数和 `$Begin` 变量以及 **之前** 的参数和 `$End` 变量设置。</span><span class="sxs-lookup"><span data-stu-id="8efd3-187">The date and time range is set by the **After** parameter and `$Begin` variable and the **Before** parameter and `$End` variable.</span></span>

## <span data-ttu-id="8efd3-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8efd3-188">PARAMETERS</span></span>

### <span data-ttu-id="8efd3-189">-After</span><span class="sxs-lookup"><span data-stu-id="8efd3-189">-After</span></span>

<span data-ttu-id="8efd3-190">获取在指定的日期和时间之后发生的事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-190">Gets events that occurred after a specified date and time.</span></span> <span data-ttu-id="8efd3-191">从输出中排除参数日期和时间 **之后** 的。</span><span class="sxs-lookup"><span data-stu-id="8efd3-191">The **After** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="8efd3-192">输入 **DateTime** 对象，例如 cmdlet 返回的值 `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-192">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-193">-AsBaseObject</span><span class="sxs-lookup"><span data-stu-id="8efd3-193">-AsBaseObject</span></span>

<span data-ttu-id="8efd3-194">指示此 cmdlet 为每个事件返回一个标准 **EventLogEntry** 对象。</span><span class="sxs-lookup"><span data-stu-id="8efd3-194">Indicates that this cmdlet returns a standard **System.Diagnostics.EventLogEntry** object for each event.</span></span> <span data-ttu-id="8efd3-195">在没有此参数的情况下， `Get-EventLog` 将返回具有附加的 **不同于 eventlogname** 、 **Source** 和 **InstanceId** 属性的扩展 **PSObject** 对象。</span><span class="sxs-lookup"><span data-stu-id="8efd3-195">Without this parameter, `Get-EventLog` returns an extended **PSObject** object with additional **EventLogName** , **Source** , and **InstanceId** properties.</span></span>

<span data-ttu-id="8efd3-196">若要查看此参数的效果，请通过管道将事件传递给 `Get-Member` cmdlet，并在结果中检查 **TypeName** 值。</span><span class="sxs-lookup"><span data-stu-id="8efd3-196">To see the effect of this parameter, pipe the events to the `Get-Member` cmdlet and examine the **TypeName** value in the result.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-197">-AsString</span><span class="sxs-lookup"><span data-stu-id="8efd3-197">-AsString</span></span>

<span data-ttu-id="8efd3-198">指示此 cmdlet 以字符串而非对象的形式返回输出。</span><span class="sxs-lookup"><span data-stu-id="8efd3-198">Indicates that this cmdlet returns the output as strings, instead of objects.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-199">-Before</span><span class="sxs-lookup"><span data-stu-id="8efd3-199">-Before</span></span>

<span data-ttu-id="8efd3-200">获取在指定日期和时间之前发生的事件。</span><span class="sxs-lookup"><span data-stu-id="8efd3-200">Gets events that occurred before a specified date and time.</span></span> <span data-ttu-id="8efd3-201">从输出中排除 **之前** 的参数日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8efd3-201">The **Before** parameter date and time are excluded from the output.</span></span> <span data-ttu-id="8efd3-202">输入 **DateTime** 对象，例如 cmdlet 返回的值 `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-202">Enter a **DateTime** object, such as the value returned by the `Get-Date` cmdlet.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-203">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8efd3-203">-ComputerName</span></span>

<span data-ttu-id="8efd3-204">此参数指定远程计算机的 NetBIOS 名称、Internet 协议 (IP) 地址或完全限定的域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-204">This parameter specifies a remote computer's NetBIOS name, Internet Protocol (IP) address, or a fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="8efd3-205">如果未指定 **ComputerName** 参数，则 `Get-EventLog` 默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8efd3-205">If the **ComputerName** parameter isn't specified, `Get-EventLog` defaults to the local computer.</span></span> <span data-ttu-id="8efd3-206">参数还接受一个点 (`.`) 来指定本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8efd3-206">The parameter also accepts a dot (`.`) to specify the local computer.</span></span>

<span data-ttu-id="8efd3-207">**ComputerName** 参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="8efd3-207">The **ComputerName** parameter doesn't rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="8efd3-208">`Get-EventLog`即使你的计算机未配置为运行远程命令，你也可以使用 With **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="8efd3-208">You can use `Get-EventLog` with the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-209">-EntryType</span><span class="sxs-lookup"><span data-stu-id="8efd3-209">-EntryType</span></span>

<span data-ttu-id="8efd3-210">指定为字符串数组，此 cmdlet 获取的事件的条目类型。</span><span class="sxs-lookup"><span data-stu-id="8efd3-210">Specifies, as a string array, the entry type of the events that this cmdlet gets.</span></span>

<span data-ttu-id="8efd3-211">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="8efd3-211">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8efd3-212">错误</span><span class="sxs-lookup"><span data-stu-id="8efd3-212">Error</span></span>
- <span data-ttu-id="8efd3-213">信息</span><span class="sxs-lookup"><span data-stu-id="8efd3-213">Information</span></span>
- <span data-ttu-id="8efd3-214">FailureAudit</span><span class="sxs-lookup"><span data-stu-id="8efd3-214">FailureAudit</span></span>
- <span data-ttu-id="8efd3-215">SuccessAudit</span><span class="sxs-lookup"><span data-stu-id="8efd3-215">SuccessAudit</span></span>
- <span data-ttu-id="8efd3-216">警告</span><span class="sxs-lookup"><span data-stu-id="8efd3-216">Warning</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ET
Accepted values: Error, Information, FailureAudit, SuccessAudit, Warning

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-217">-Index</span><span class="sxs-lookup"><span data-stu-id="8efd3-217">-Index</span></span>

<span data-ttu-id="8efd3-218">指定要从事件日志中获取的索引值。</span><span class="sxs-lookup"><span data-stu-id="8efd3-218">Specifies the index values to get from the event log.</span></span> <span data-ttu-id="8efd3-219">参数接受以逗号分隔的值字符串。</span><span class="sxs-lookup"><span data-stu-id="8efd3-219">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-220">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="8efd3-220">-InstanceId</span></span>

<span data-ttu-id="8efd3-221">指定要从事件日志中获取的实例 Id。</span><span class="sxs-lookup"><span data-stu-id="8efd3-221">Specifies the Instance IDs to get from the event log.</span></span> <span data-ttu-id="8efd3-222">参数接受以逗号分隔的值字符串。</span><span class="sxs-lookup"><span data-stu-id="8efd3-222">The parameter accepts a comma-separated string of values.</span></span>

```yaml
Type: System.Int64[]
Parameter Sets: LogName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-223">-List</span><span class="sxs-lookup"><span data-stu-id="8efd3-223">-List</span></span>

<span data-ttu-id="8efd3-224">显示计算机上的事件日志列表。</span><span class="sxs-lookup"><span data-stu-id="8efd3-224">Displays the list of event logs on the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-225">-LogName</span><span class="sxs-lookup"><span data-stu-id="8efd3-225">-LogName</span></span>

<span data-ttu-id="8efd3-226">指定一个事件日志的名称。</span><span class="sxs-lookup"><span data-stu-id="8efd3-226">Specifies the name of one event log.</span></span> <span data-ttu-id="8efd3-227">查找日志名称使用 `Get-EventLog -List` 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-227">To find the log names use `Get-EventLog -List`.</span></span> <span data-ttu-id="8efd3-228">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8efd3-228">Wildcard characters are permitted.</span></span> <span data-ttu-id="8efd3-229">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="8efd3-229">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: LN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8efd3-230">-Message</span><span class="sxs-lookup"><span data-stu-id="8efd3-230">-Message</span></span>

<span data-ttu-id="8efd3-231">指定事件消息中的字符串。</span><span class="sxs-lookup"><span data-stu-id="8efd3-231">Specifies a string in the event message.</span></span> <span data-ttu-id="8efd3-232">可以使用此参数来搜索包含特定单词或短语的消息。</span><span class="sxs-lookup"><span data-stu-id="8efd3-232">You can use this parameter to search for messages that contain certain words or phrases.</span></span> <span data-ttu-id="8efd3-233">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8efd3-233">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: LogName
Aliases: MSG

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8efd3-234">-Newest</span><span class="sxs-lookup"><span data-stu-id="8efd3-234">-Newest</span></span>

<span data-ttu-id="8efd3-235">从最新事件开始，获取指定的事件数。</span><span class="sxs-lookup"><span data-stu-id="8efd3-235">Begins with the newest events and gets the specified number of events.</span></span> <span data-ttu-id="8efd3-236">例如，事件数是必需的 `-Newest 100` 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-236">The number of events is required, for example `-Newest 100`.</span></span> <span data-ttu-id="8efd3-237">指定返回的最大事件数。</span><span class="sxs-lookup"><span data-stu-id="8efd3-237">Specifies the maximum number of events that are returned.</span></span>

```yaml
Type: System.Int32
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8efd3-238">-Source</span><span class="sxs-lookup"><span data-stu-id="8efd3-238">-Source</span></span>

<span data-ttu-id="8efd3-239">指定作为字符串数组，写入到此 cmdlet 获取的日志的源。</span><span class="sxs-lookup"><span data-stu-id="8efd3-239">Specifies, as a string array, sources that were written to the log that this cmdlet gets.</span></span> <span data-ttu-id="8efd3-240">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8efd3-240">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases: ABO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8efd3-241">-UserName</span><span class="sxs-lookup"><span data-stu-id="8efd3-241">-UserName</span></span>

<span data-ttu-id="8efd3-242">指定作为字符串数组，与事件关联的用户名。</span><span class="sxs-lookup"><span data-stu-id="8efd3-242">Specifies, as a string array, user names that are associated with events.</span></span> <span data-ttu-id="8efd3-243">输入名称或名称模式，如 `User01` 、 `User*` 或 `Domain01\User*` 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-243">Enter names or name patterns, such as `User01`, `User*`, or `Domain01\User*`.</span></span> <span data-ttu-id="8efd3-244">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="8efd3-244">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LogName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="8efd3-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8efd3-245">CommonParameters</span></span>

<span data-ttu-id="8efd3-246">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8efd3-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8efd3-247">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8efd3-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8efd3-248">输入</span><span class="sxs-lookup"><span data-stu-id="8efd3-248">INPUTS</span></span>

### <span data-ttu-id="8efd3-249">无</span><span class="sxs-lookup"><span data-stu-id="8efd3-249">None</span></span>

<span data-ttu-id="8efd3-250">不能通过管道将输入传递给 `Get-EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="8efd3-250">You cannot pipe input to `Get-EventLog`.</span></span>

## <span data-ttu-id="8efd3-251">输出</span><span class="sxs-lookup"><span data-stu-id="8efd3-251">OUTPUTS</span></span>

### <span data-ttu-id="8efd3-252">System.Diagnostics.EventLogEntry.</span><span class="sxs-lookup"><span data-stu-id="8efd3-252">System.Diagnostics.EventLogEntry.</span></span> <span data-ttu-id="8efd3-253">System.Diagnostics.EventLog.</span><span class="sxs-lookup"><span data-stu-id="8efd3-253">System.Diagnostics.EventLog.</span></span> <span data-ttu-id="8efd3-254">System.String</span><span class="sxs-lookup"><span data-stu-id="8efd3-254">System.String</span></span>

<span data-ttu-id="8efd3-255">如果指定了 **LogName** 参数，则输出为 **EventLogEntry** 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="8efd3-255">If the **LogName** parameter is specified, the output is a collection of **System.Diagnostics.EventLogEntry** objects.</span></span>

<span data-ttu-id="8efd3-256">如果仅指定了 **List** 参数，则输出为 **系统** 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="8efd3-256">If only the **List** parameter is specified, the output is a collection of **System.Diagnostics.EventLog** objects.</span></span>

<span data-ttu-id="8efd3-257">如果同时指定了 **List** 和 **AsString** 参数，则输出为 **system.string** 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="8efd3-257">If both the **List** and **AsString** parameters are specified, the output is a collection of **System.String** objects.</span></span>

## <span data-ttu-id="8efd3-258">注释</span><span class="sxs-lookup"><span data-stu-id="8efd3-258">NOTES</span></span>

<span data-ttu-id="8efd3-259">`Get-EventLog` `Get-WinEvent` Windows PE) Windows 预安装环境 (不支持 cmdlet 和。</span><span class="sxs-lookup"><span data-stu-id="8efd3-259">The cmdlets `Get-EventLog` and `Get-WinEvent` are not supported in the Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="8efd3-260">相关链接</span><span class="sxs-lookup"><span data-stu-id="8efd3-260">RELATED LINKS</span></span>

[<span data-ttu-id="8efd3-261">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="8efd3-261">Clear-EventLog</span></span>](Clear-EventLog.md)

[<span data-ttu-id="8efd3-262">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="8efd3-262">Get-WinEvent</span></span>](../Microsoft.PowerShell.Diagnostics/Get-WinEvent.md)

[<span data-ttu-id="8efd3-263">Group-Object</span><span class="sxs-lookup"><span data-stu-id="8efd3-263">Group-Object</span></span>](../Microsoft.PowerShell.Utility/Group-Object.md)

[<span data-ttu-id="8efd3-264">Limit-EventLog</span><span class="sxs-lookup"><span data-stu-id="8efd3-264">Limit-EventLog</span></span>](Limit-EventLog.md)

[<span data-ttu-id="8efd3-265">New-EventLog</span><span class="sxs-lookup"><span data-stu-id="8efd3-265">New-EventLog</span></span>](New-EventLog.md)

[<span data-ttu-id="8efd3-266">Remove-EventLog</span><span class="sxs-lookup"><span data-stu-id="8efd3-266">Remove-EventLog</span></span>](Remove-EventLog.md)

[<span data-ttu-id="8efd3-267">Select-Object</span><span class="sxs-lookup"><span data-stu-id="8efd3-267">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="8efd3-268">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="8efd3-268">Show-EventLog</span></span>](Show-EventLog.md)

[<span data-ttu-id="8efd3-269">Write-EventLog</span><span class="sxs-lookup"><span data-stu-id="8efd3-269">Write-EventLog</span></span>](Write-EventLog.md)
