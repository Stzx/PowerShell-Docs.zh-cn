---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/13/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerrestorepoint?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerRestorePoint
ms.openlocfilehash: 73819aafee9ed1911354daf9af23eedff0a3e14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198300"
---
# <span data-ttu-id="3ad4c-103">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="3ad4c-103">Get-ComputerRestorePoint</span></span>

## <span data-ttu-id="3ad4c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3ad4c-104">SYNOPSIS</span></span>
<span data-ttu-id="3ad4c-105">获取本地计算机上的还原点。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-105">Gets the restore points on the local computer.</span></span>

## <span data-ttu-id="3ad4c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ad4c-106">SYNTAX</span></span>

### <span data-ttu-id="3ad4c-107">ID（默认值）</span><span class="sxs-lookup"><span data-stu-id="3ad4c-107">ID (Default)</span></span>

```
Get-ComputerRestorePoint [[-RestorePoint] <Int32[]>] [<CommonParameters>]
```

### <span data-ttu-id="3ad4c-108">LastStatus</span><span class="sxs-lookup"><span data-stu-id="3ad4c-108">LastStatus</span></span>

```
Get-ComputerRestorePoint -LastStatus [<CommonParameters>]
```

## <span data-ttu-id="3ad4c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ad4c-109">DESCRIPTION</span></span>

<span data-ttu-id="3ad4c-110">`Get-ComputerRestorePoint`Cmdlet 将获取本地计算机的系统还原点。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-110">The `Get-ComputerRestorePoint` cmdlet gets the local computer's system restore points.</span></span> <span data-ttu-id="3ad4c-111">而且，它还可以显示最近一次尝试还原计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-111">And, it can display the status of the most recent attempt to restore the computer.</span></span>

<span data-ttu-id="3ad4c-112">你可以使用中的信息 `Get-ComputerRestorePoint` 来选择还原点。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-112">You can use the information from `Get-ComputerRestorePoint` to select a restore point.</span></span> <span data-ttu-id="3ad4c-113">例如，使用序列号来标识 cmdlet 的还原点 `Restore-Computer` 。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-113">For example, use a sequence number to identify a restore point for the `Restore-Computer` cmdlet.</span></span>

<span data-ttu-id="3ad4c-114">`Get-ComputerRestorePoint`仅在客户端操作系统（例如 windows 10、windows 7、Windows Vista 和 WINDOWS XP）上支持系统还原点和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-114">System restore points and the `Get-ComputerRestorePoint` cmdlet are supported only on client operating systems such as Windows 10, Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="3ad4c-115">示例</span><span class="sxs-lookup"><span data-stu-id="3ad4c-115">EXAMPLES</span></span>

### <span data-ttu-id="3ad4c-116">示例1：获取所有系统还原点</span><span class="sxs-lookup"><span data-stu-id="3ad4c-116">Example 1: Get all system restore points</span></span>

<span data-ttu-id="3ad4c-117">在此示例中， `Get-ComputerRestorePoint` 获取本地计算机的所有系统还原点。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-117">In this example, `Get-ComputerRestorePoint` gets all the local computer's system restore points.</span></span>

```powershell
Get-ComputerRestorePoint
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
8/7/2019  12:56:45     Installed PowerShell 6-x64     6                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

### <span data-ttu-id="3ad4c-118">示例2：获取特定序列号</span><span class="sxs-lookup"><span data-stu-id="3ad4c-118">Example 2: Get specific sequence numbers</span></span>

<span data-ttu-id="3ad4c-119">此示例获取特定序列号的系统还原点。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-119">This example gets system restore points for specific sequence numbers.</span></span>

```powershell
Get-ComputerRestorePoint -RestorePoint 4, 5
```

```Output
CreationTime           Description                    SequenceNumber    EventType         RestorePointType
------------           -----------                    --------------    ---------         ----------------
7/30/2019 09:17:24     Windows Update                 4                 BEGIN_SYSTEM_C... 17
8/5/2019  08:15:37     Installed PowerShell 7-prev... 5                 BEGIN_SYSTEM_C... APPLICATION_INSTALL
```

<span data-ttu-id="3ad4c-120">`Get-ComputerRestorePoint` 使用 **RestorePoint** 参数来指定序列号的逗号分隔数组。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-120">`Get-ComputerRestorePoint` uses the **RestorePoint** parameter to specify a comma-separated array of sequence numbers.</span></span>

### <span data-ttu-id="3ad4c-121">示例3：显示系统还原的状态</span><span class="sxs-lookup"><span data-stu-id="3ad4c-121">Example 3: Display the status of a system restore</span></span>

<span data-ttu-id="3ad4c-122">此示例显示本地计算机上最近的系统还原的状态。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-122">This example displays the status of the most recent system restore on the local computer.</span></span>

```powershell
Get-ComputerRestorePoint -LastStatus
```

```Output
The last attempt to restore the computer failed.
```

<span data-ttu-id="3ad4c-123">`Get-ComputerRestorePoint` 使用 **LastStatus** 参数显示最近的系统还原的结果。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-123">`Get-ComputerRestorePoint` uses the **LastStatus** parameter to display the result of the most recent system restore.</span></span>

### <span data-ttu-id="3ad4c-124">示例4：使用表达式转换 CreationTime</span><span class="sxs-lookup"><span data-stu-id="3ad4c-124">Example 4: Use an expression to convert the CreationTime</span></span>

<span data-ttu-id="3ad4c-125">`Get-ComputerRestorePoint` 将 **CreationTime** 作为 (WMI) 日期和时间字符串的 Windows Management Instrumentation 输出。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-125">`Get-ComputerRestorePoint` outputs the **CreationTime** as a Windows Management Instrumentation (WMI) date and time string.</span></span>

<span data-ttu-id="3ad4c-126">在此示例中，变量存储了一个表达式，该表达式将 **CreationTime** 字符串转换为 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-126">In this example, a variable stores an expression that converts the **CreationTime** string to a **DateTime** object.</span></span> <span data-ttu-id="3ad4c-127">若要在转换前查看 **CreationTime** 字符串，请使用命令（如） `((Get-ComputerRestorePoint).CreationTime)` 。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-127">To view **CreationTime** strings before they're converted, use a command such as `((Get-ComputerRestorePoint).CreationTime)`.</span></span> <span data-ttu-id="3ad4c-128">有关 WMI 日期和时间字符串的详细信息，请参阅 [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime)。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-128">For more information about the WMI date and time string, see [CIM_DATETIME](/windows/win32/wmisdk/cim-datetime).</span></span>

```powershell
$date = @{Label="Date"; Expression={$_.ConvertToDateTime($_.CreationTime)}}
Get-ComputerRestorePoint | Select-Object -Property SequenceNumber, $date, Description
```

```Output
SequenceNumber   Date                 Description
--------------   ----                 -----------
             4   7/30/2019 09:17:24   Windows Update
             5   8/5/2019  08:15:37   Installed PowerShell 7-preview-x64
             6   8/7/2019  12:56:45   Installed PowerShell 6-x64
```

<span data-ttu-id="3ad4c-129">`$date`变量使用 **ConvertToDateTime** 方法的表达式存储哈希表。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-129">The `$date` variable stores a hash table with the expression that uses the **ConvertToDateTime** method.</span></span> <span data-ttu-id="3ad4c-130">表达式将 **CreationTime** 属性的值从 WMI 字符串转换为 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-130">The expression converts the **CreationTime** property's value from a WMI string to a **DateTime** object.</span></span>

<span data-ttu-id="3ad4c-131">`Get-ComputerRestorePoint` 沿管道向下发送系统还原点对象。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-131">`Get-ComputerRestorePoint` sends the system restore point objects down the pipeline.</span></span> <span data-ttu-id="3ad4c-132">`Select-Object` 使用 **Property** 参数来指定要显示的属性。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-132">`Select-Object` uses the **Property** parameter to specify the properties to display.</span></span> <span data-ttu-id="3ad4c-133">对于管道中的每个对象，中的表达式 `$date` 转换 **CreationTime** 并在 **Date** 属性中输出结果。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-133">For each object in the pipeline, the expression in `$date` converts the **CreationTime** and outputs the result in the **Date** property.</span></span>

### <span data-ttu-id="3ad4c-134">示例5：使用属性获取序列号</span><span class="sxs-lookup"><span data-stu-id="3ad4c-134">Example 5: Use a property to get a sequence number</span></span>

<span data-ttu-id="3ad4c-135">此示例通过使用 **SequenceNumber** 属性和数组索引来获取序列号。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-135">This example gets a sequence number by using the **SequenceNumber** property and an array index.</span></span> <span data-ttu-id="3ad4c-136">输出只包含序列号。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-136">The output only contains the sequence number.</span></span>

```powershell
((Get-ComputerRestorePoint).SequenceNumber)[-1]
```

```Output
6
```

<span data-ttu-id="3ad4c-137">`Get-ComputerRestorePoint` 使用带有数组索引的 **SequenceNumber** 属性。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-137">`Get-ComputerRestorePoint` uses the **SequenceNumber** property with an array index.</span></span> <span data-ttu-id="3ad4c-138">的数组索引 `-1` 获取数组中的最新序列号。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-138">The array index of `-1` gets the most recent sequence number in the array.</span></span>

## <span data-ttu-id="3ad4c-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ad4c-139">PARAMETERS</span></span>

### <span data-ttu-id="3ad4c-140">-LastStatus</span><span class="sxs-lookup"><span data-stu-id="3ad4c-140">-LastStatus</span></span>

<span data-ttu-id="3ad4c-141">指示 `Get-ComputerRestorePoint` 获取最近的系统还原操作的状态。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-141">Indicates that `Get-ComputerRestorePoint` gets the status of the most recent system restore operation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LastStatus
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ad4c-142">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="3ad4c-142">-RestorePoint</span></span>

<span data-ttu-id="3ad4c-143">指定系统还原点的序列号。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-143">Specifies the sequence numbers of the system restore points.</span></span> <span data-ttu-id="3ad4c-144">您可以指定单个序列号或逗号分隔的序列号数组。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-144">You can specify either a single sequence number or a comma-separated array of sequence numbers.</span></span>

<span data-ttu-id="3ad4c-145">如果未指定 **RestorePoint** 参数，则 `Get-ComputerRestorePoint` 返回所有本地计算机的系统还原点。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-145">If the **RestorePoint** parameter isn't specified, `Get-ComputerRestorePoint` returns all the local computer's system restore points.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ID
Aliases:

Required: False
Position: 0
Default value: All restore points
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ad4c-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3ad4c-146">CommonParameters</span></span>

<span data-ttu-id="3ad4c-147">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ad4c-148">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ad4c-149">输入</span><span class="sxs-lookup"><span data-stu-id="3ad4c-149">INPUTS</span></span>

### <span data-ttu-id="3ad4c-150">无</span><span class="sxs-lookup"><span data-stu-id="3ad4c-150">None</span></span>

<span data-ttu-id="3ad4c-151">不能将对象向下发送到 `Get-ComputerRestorePoint` 。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-151">You can't send objects down the pipeline to `Get-ComputerRestorePoint`.</span></span>

## <span data-ttu-id="3ad4c-152">输出</span><span class="sxs-lookup"><span data-stu-id="3ad4c-152">OUTPUTS</span></span>

### <span data-ttu-id="3ad4c-153">System.management.managementobject # root\default\SystemRestore 或 String</span><span class="sxs-lookup"><span data-stu-id="3ad4c-153">System.Management.ManagementObject#root\default\SystemRestore or String</span></span>

<span data-ttu-id="3ad4c-154">`Get-ComputerRestorePoint` 返回一个 **SystemRestore** 对象，该对象是 WINDOWS MANAGEMENT INSTRUMENTATION (WMI) **SystemRestore** 类的实例。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-154">`Get-ComputerRestorePoint` returns a **SystemRestore** object, which is an instance of the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

<span data-ttu-id="3ad4c-155">当你使用 **LastStatus** 参数时，将 `Get-ComputerRestorePoint` 返回一个字符串。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-155">When you use the **LastStatus** parameter, `Get-ComputerRestorePoint` returns a string.</span></span>

## <span data-ttu-id="3ad4c-156">注释</span><span class="sxs-lookup"><span data-stu-id="3ad4c-156">NOTES</span></span>

<span data-ttu-id="3ad4c-157">若要 `Get-ComputerRestorePoint` 在 Windows Vista 和更高版本的 windows 上运行命令，请使用 "以 **管理员身份运行** " 选项打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-157">To run a `Get-ComputerRestorePoint` command on Windows Vista and later versions of Windows, open PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="3ad4c-158">`Get-ComputerRestorePoint` 使用 WMI **SystemRestore** 类。</span><span class="sxs-lookup"><span data-stu-id="3ad4c-158">`Get-ComputerRestorePoint` uses the WMI **SystemRestore** class.</span></span>

## <span data-ttu-id="3ad4c-159">相关链接</span><span class="sxs-lookup"><span data-stu-id="3ad4c-159">RELATED LINKS</span></span>

[<span data-ttu-id="3ad4c-160">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="3ad4c-160">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="3ad4c-161">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="3ad4c-161">about_Arrays</span></span>](../Microsoft.PowerShell.Core/About/about_Arrays.md)

[<span data-ttu-id="3ad4c-162">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="3ad4c-162">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="3ad4c-163">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="3ad4c-163">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="3ad4c-164">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="3ad4c-164">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="3ad4c-165">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3ad4c-165">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="3ad4c-166">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="3ad4c-166">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="3ad4c-167">SystemRestore</span><span class="sxs-lookup"><span data-stu-id="3ad4c-167">SystemRestore</span></span>](/windows/win32/sr/systemrestore)
