---
description: Windows PowerShell 会创建一个名为 "Windows PowerShell" 的 Windows 事件日志来记录 Windows PowerShell 事件。 可以事件查看器中查看此日志，也可以使用获取事件的 cmdlet （如 cmdlet）来查看此日志 `Get-EventLog` 。 默认情况下，Windows PowerShell 引擎和提供程序事件记录在事件日志中，但你可以使用事件日志首选项变量来自定义事件日志。 例如，你可以添加有关 Windows PowerShell 命令的事件。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200307"
---
# <a name="about-eventlogs"></a><span data-ttu-id="9c4d2-107">关于事件日志</span><span class="sxs-lookup"><span data-stu-id="9c4d2-107">About Eventlogs</span></span>

## <a name="short-description"></a><span data-ttu-id="9c4d2-108">简短说明</span><span class="sxs-lookup"><span data-stu-id="9c4d2-108">Short Description</span></span>

<span data-ttu-id="9c4d2-109">Windows PowerShell 会创建一个名为 "Windows PowerShell" 的 Windows 事件日志来记录 Windows PowerShell 事件。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-109">Windows PowerShell creates a Windows event log that is named "Windows PowerShell" to record Windows PowerShell events.</span></span> <span data-ttu-id="9c4d2-110">可以事件查看器中查看此日志，也可以使用获取事件的 cmdlet （如 cmdlet）来查看此日志 `Get-EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-110">You can view this log in Event Viewer or by using cmdlets that get events, such as the `Get-EventLog` cmdlet.</span></span> <span data-ttu-id="9c4d2-111">默认情况下，Windows PowerShell 引擎和提供程序事件记录在事件日志中，但你可以使用事件日志首选项变量来自定义事件日志。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-111">By default, Windows PowerShell engine and provider events are recorded in the event log, but you can use the event log preference variables to customize the event log.</span></span> <span data-ttu-id="9c4d2-112">例如，你可以添加有关 Windows PowerShell 命令的事件。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-112">For example, you can add events about Windows PowerShell commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="9c4d2-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="9c4d2-113">Long Description</span></span>

<span data-ttu-id="9c4d2-114">Windows PowerShell 事件日志记录 Windows PowerShell 操作的详细信息，例如启动和停止程序引擎，以及启动和停止 Windows PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-114">The Windows PowerShell event log records details of Windows PowerShell operations, such as starting and stopping the program engine and starting and stopping the Windows PowerShell providers.</span></span> <span data-ttu-id="9c4d2-115">你还可以记录有关 Windows PowerShell 命令的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-115">You can also log details about Windows PowerShell commands.</span></span>

<span data-ttu-id="9c4d2-116">Windows PowerShell 事件日志位于 "应用程序和服务日志" 组中。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-116">The Windows PowerShell event log is in the Application and Services Logs group.</span></span> <span data-ttu-id="9c4d2-117">Windows PowerShell 日志是典型的事件日志，不使用 Windows 事件技术。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-117">The Windows PowerShell log is a classic event log that does not use the Windows Eventing technology.</span></span> <span data-ttu-id="9c4d2-118">若要查看日志，请使用为经典事件日志设计的 cmdlet，例如 `Get-EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-118">To view the log, use the cmdlets designed for classic event logs, such as `Get-EventLog`.</span></span>

## <a name="viewing-the-windows-powershell-event-log"></a><span data-ttu-id="9c4d2-119">查看 Windows PowerShell 事件日志</span><span class="sxs-lookup"><span data-stu-id="9c4d2-119">Viewing the Windows PowerShell Event Log</span></span>

<span data-ttu-id="9c4d2-120">可以事件查看器中或使用和 cmdlet 来查看 Windows PowerShell 事件日志 `Get-EventLog` `Get-WmiObject` 。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-120">You can view the Windows PowerShell event log in Event Viewer or by using the `Get-EventLog` and `Get-WmiObject` cmdlets.</span></span> <span data-ttu-id="9c4d2-121">若要查看 Windows PowerShell 日志的内容，请键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-121">To view the contents of the Windows PowerShell log, type:</span></span>

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

<span data-ttu-id="9c4d2-122">若要检查事件及其属性，请使用 cmdlet `Sort-Object` 、cmdlet 以及 `Group-Object` 包含 `Format` cmdlet)  (谓词的 cmdlet `Format` 。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-122">To examine the events and their properties, use the `Sort-Object` cmdlet, the `Group-Object` cmdlet, and the cmdlets that contain the `Format` verb (the `Format` cmdlets).</span></span>

<span data-ttu-id="9c4d2-123">例如，若要查看日志中按事件 ID 分组的事件，请键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-123">For example, to view the events in the log grouped by the event ID, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

<span data-ttu-id="9c4d2-124">或者键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-124">Or, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

<span data-ttu-id="9c4d2-125">若要查看所有经典事件日志，请键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-125">To view all the classic event logs, type:</span></span>

```powershell
Get-EventLog -List
```

<span data-ttu-id="9c4d2-126">你还可以使用 `Get-WmiObject` cmdlet 来使用与事件相关的 Windows Management Instrumentation (WMI) 类来检查事件日志。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-126">You can also use the `Get-WmiObject` cmdlet to use the event-related Windows Management Instrumentation (WMI) classes to examine the event log.</span></span> <span data-ttu-id="9c4d2-127">例如，若要查看事件日志文件的所有属性，请键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-127">For example, to view all the properties of the event log file, type:</span></span>

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

<span data-ttu-id="9c4d2-128">若要查找与 Win32 事件相关的 WMI 类，请键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-128">To find the Win32 event-related WMI classes, type:</span></span>

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

<span data-ttu-id="9c4d2-129">有关详细信息，请键入 "Get-help Get-help" 和 "Get-help Get-wmiobject"。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-129">For more information, type "Get-Help Get-EventLog" and "Get-Help Get-WmiObject".</span></span>

## <a name="selecting-events-for-the-windows-powershell-event-log"></a><span data-ttu-id="9c4d2-130">为 Windows PowerShell 事件日志选择事件</span><span class="sxs-lookup"><span data-stu-id="9c4d2-130">Selecting Events for the Windows PowerShell Event Log</span></span>

<span data-ttu-id="9c4d2-131">您可以使用事件日志首选项变量来确定哪些事件记录在 Windows PowerShell 事件日志中。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-131">You can use the event log preference variables to determine which events are recorded in the Windows PowerShell event log.</span></span>

<span data-ttu-id="9c4d2-132">有六个事件日志首选项变量;这三个日志记录组件中的每个组件都有两个变量：引擎 (Windows PowerShell 程序) 、提供程序和命令。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-132">There are six event log preference variables; two variables for each of the three logging components: the engine (the Windows PowerShell program), the providers, and the commands.</span></span> <span data-ttu-id="9c4d2-133">LifeCycleEvent 变量记录正常的启动和停止事件。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-133">The LifeCycleEvent variables log normal starting and stopping events.</span></span> <span data-ttu-id="9c4d2-134">运行状况变量记录错误事件。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-134">The Health variables log error events.</span></span>

<span data-ttu-id="9c4d2-135">下表列出了事件日志首选项变量。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-135">The following table lists the event log preference variables.</span></span>

|<span data-ttu-id="9c4d2-136">变量</span><span class="sxs-lookup"><span data-stu-id="9c4d2-136">Variable</span></span>                  |<span data-ttu-id="9c4d2-137">说明</span><span class="sxs-lookup"><span data-stu-id="9c4d2-137">Description</span></span>                                    |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="9c4d2-138">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-138">$LogEngineLifeCycleEvent</span></span>  |<span data-ttu-id="9c4d2-139">记录 PowerShell 的启动和停止</span><span class="sxs-lookup"><span data-stu-id="9c4d2-139">Logs the start and stop of PowerShell</span></span>          |
|<span data-ttu-id="9c4d2-140">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-140">$LogEngineHealthEvent</span></span>     |<span data-ttu-id="9c4d2-141">记录 PowerShell 程序错误</span><span class="sxs-lookup"><span data-stu-id="9c4d2-141">Logs PowerShell program errors</span></span>                 |
|<span data-ttu-id="9c4d2-142">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-142">$LogProviderLifeCycleEvent</span></span>|<span data-ttu-id="9c4d2-143">记录 PowerShell 提供程序的启动和停止</span><span class="sxs-lookup"><span data-stu-id="9c4d2-143">Logs the start and stop of PowerShell providers</span></span>|
|<span data-ttu-id="9c4d2-144">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-144">$LogProviderHealthEvent</span></span>   |<span data-ttu-id="9c4d2-145">记录 PowerShell 提供程序错误</span><span class="sxs-lookup"><span data-stu-id="9c4d2-145">Logs PowerShell provider errors</span></span>                |
|<span data-ttu-id="9c4d2-146">$LogCommandLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-146">$LogCommandLifeCycleEvent</span></span> |<span data-ttu-id="9c4d2-147">记录命令的启动和完成</span><span class="sxs-lookup"><span data-stu-id="9c4d2-147">Logs the starting and completion of commands</span></span>   |
|<span data-ttu-id="9c4d2-148">$LogCommandHealthEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-148">$LogCommandHealthEvent</span></span>    |<span data-ttu-id="9c4d2-149">记录命令错误</span><span class="sxs-lookup"><span data-stu-id="9c4d2-149">Logs command errors</span></span>                            |

<span data-ttu-id="9c4d2-150"> (有关 Windows PowerShell 提供程序的信息，请参阅 [about_Providers](about_Providers.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="9c4d2-150">(For information about Windows PowerShell providers, see [about_Providers](about_Providers.md).)</span></span>

<span data-ttu-id="9c4d2-151">默认情况下，只启用以下事件类型：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-151">By default, only the following event types are enabled:</span></span>

* <span data-ttu-id="9c4d2-152">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-152">$LogEngineLifeCycleEvent</span></span>
* <span data-ttu-id="9c4d2-153">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-153">$LogEngineHealthEvent</span></span>
* <span data-ttu-id="9c4d2-154">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-154">$LogProviderLifeCycleEvent</span></span>
* <span data-ttu-id="9c4d2-155">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="9c4d2-155">$LogProviderHealthEvent</span></span>

<span data-ttu-id="9c4d2-156">若要启用某个事件类型，请将该事件类型的首选项变量设置为 $true。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-156">To enable an event type, set the preference variable for that event type to $true.</span></span> <span data-ttu-id="9c4d2-157">例如，若要启用命令生命周期事件，请键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-157">For example, to enable command life-cycle events, type:</span></span>

```powershell
$LogCommandLifeCycleEvent
```

<span data-ttu-id="9c4d2-158">或者键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-158">Or, type:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="9c4d2-159">若要禁用事件类型，请将该事件类型的首选项变量设置为 $false。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-159">To disable an event type, set the preference variable for that event type to $false.</span></span> <span data-ttu-id="9c4d2-160">例如，若要禁用命令生命周期事件，请键入：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-160">For example, to disable command life-cycle events, type:</span></span>

```powershell
$LogProviderLifeCycleEvent = $false
```

<span data-ttu-id="9c4d2-161">您可以禁用任何事件，但表明 Windows PowerShell 引擎和核心提供程序已启动的事件除外。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-161">You can disable any event, except for the events that indicate that the Windows PowerShell engine and the core providers are started.</span></span> <span data-ttu-id="9c4d2-162">这些事件是在运行 Windows PowerShell 配置文件之前、主机程序准备接受命令之前生成的。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-162">These events are generated before the Windows PowerShell profiles are run and before the host program is ready to accept commands.</span></span>

<span data-ttu-id="9c4d2-163">变量设置仅适用于当前的 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-163">The variable settings apply only for the current Windows PowerShell session.</span></span>
<span data-ttu-id="9c4d2-164">若要将其应用到所有 Windows PowerShell 会话，请将其添加到 Windows PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-164">To apply them to all Windows PowerShell sessions, add them to your Windows PowerShell profile.</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="9c4d2-165">记录模块事件</span><span class="sxs-lookup"><span data-stu-id="9c4d2-165">Logging Module Events</span></span>

<span data-ttu-id="9c4d2-166">从 Windows PowerShell 3.0 开始，可以通过将模块和管理单元的 LogPipelineExecutionDetails 属性设置为 TRUE，在 Windows PowerShell 模块和管理单元中记录 cmdlet 和函数的执行事件。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-166">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets and functions in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="9c4d2-167">在 Windows PowerShell 2.0 中，此功能仅适用于管理单元。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-167">In Windows PowerShell 2.0, this feature is available only for snap-ins.</span></span>

<span data-ttu-id="9c4d2-168">当 LogPipelineExecutionDetails 属性值为 TRUE 时 (`$true`) ，Windows powershell 会将会话中的 cmdlet 和函数执行事件写入事件查看器的 Windows powershell 日志中。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-168">When the LogPipelineExecutionDetails property value is TRUE (`$true`), Windows PowerShell writes cmdlet and function execution events in the session to the Windows PowerShell log in Event Viewer.</span></span> <span data-ttu-id="9c4d2-169">此设置仅在当前会话中有效。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-169">The setting is effective only in the current session.</span></span>

<span data-ttu-id="9c4d2-170">若要对某个模块中的 cmdlet 和函数的执行事件进行日志记录，请使用以下命令序列。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-170">To enable logging of execution events of cmdlets and functions in a module, use the following command sequence.</span></span>

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

<span data-ttu-id="9c4d2-171">若要在管理单元中启用 cmdlet 的执行事件日志记录，请使用以下命令序列。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-171">To enable logging of execution events of cmdlets in a snap-in, use the following command sequence.</span></span>

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

<span data-ttu-id="9c4d2-172">若要禁用日志记录，请使用相同的命令序列将属性值设置为 FALSE (`$false`) 。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-172">To disable logging, use the same command sequence to set the property value to FALSE (`$false`).</span></span>

<span data-ttu-id="9c4d2-173">你还可以使用 "打开模块日志记录" 组策略设置来启用和禁用模块和管理单元日志记录。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-173">You can also use the "Turn on Module Logging" Group Policy setting to enable and disable module and snap-in logging.</span></span> <span data-ttu-id="9c4d2-174">策略值包括模块和管理单元名称的列表。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-174">The policy value includes a list of module and snap-in names.</span></span> <span data-ttu-id="9c4d2-175">支持通配符。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-175">Wildcards are supported.</span></span>

<span data-ttu-id="9c4d2-176">为模块设置 "打开模块日志记录" 时，模块的 LogPipelineExecutionDetails 属性的值在所有会话中都为 TRUE，并且无法更改。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-176">When "Turn on Module Logging" is set for a module, the value of the LogPipelineExecutionDetails property of the module is TRUE in all sessions and it cannot be changed.</span></span>

<span data-ttu-id="9c4d2-177">"打开模块日志记录" 组策略设置位于以下组策略路径中：</span><span class="sxs-lookup"><span data-stu-id="9c4d2-177">The Turn On Module Logging group policy setting is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

<span data-ttu-id="9c4d2-178">用户配置策略优先于计算机配置策略，并且两个策略优先于模块和管理单元的 LogPipelineExecutionDetails 属性的值。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-178">The User Configuration policy takes precedence over the Computer Configuration policy, and both policies take preference over the value of the LogPipelineExecutionDetails property of modules and snap-ins.</span></span>

<span data-ttu-id="9c4d2-179">有关此组策略设置的详细信息，请参阅 [about_Group_Policy_Settings](about_Group_Policy_Settings.md)。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-179">For more information about this Group Policy setting, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="security-and-auditing"></a><span data-ttu-id="9c4d2-180">安全和审核</span><span class="sxs-lookup"><span data-stu-id="9c4d2-180">Security and Auditing</span></span>

<span data-ttu-id="9c4d2-181">Windows PowerShell 事件日志旨在指示活动，并提供操作详细信息以进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-181">The Windows PowerShell event log is designed to indicate activity and to provide operational details for troubleshooting.</span></span>

<span data-ttu-id="9c4d2-182">但是，与大多数基于 Windows 的应用程序事件日志类似，Windows PowerShell 事件日志并未设计为安全。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-182">However, like most Windows-based application event logs, the Windows PowerShell event log is not designed to be secure.</span></span> <span data-ttu-id="9c4d2-183">它不应用于审核安全或记录机密信息或专有信息。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-183">It should not be used to audit security or to record confidential or proprietary information.</span></span>

<span data-ttu-id="9c4d2-184">事件日志旨在供用户阅读和理解。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-184">Event logs are designed to be read and understood by users.</span></span> <span data-ttu-id="9c4d2-185">用户可以读取和写入日志。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-185">Users can read from and write to the log.</span></span> <span data-ttu-id="9c4d2-186">恶意用户可能会读取本地或远程计算机上的事件日志，记录虚假数据，然后阻止日志记录其活动。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-186">A malicious user could read an event log on a local or remote computer, record false data, and then prevent the logging of their activities.</span></span>

## <a name="notes"></a><span data-ttu-id="9c4d2-187">注释</span><span class="sxs-lookup"><span data-stu-id="9c4d2-187">Notes</span></span>

<span data-ttu-id="9c4d2-188">模块作者的作者可以向其模块中添加日志记录功能。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-188">Authors of module authors can add logging features to their modules.</span></span> <span data-ttu-id="9c4d2-189">有关详细信息，请参阅 [编写 Windows PowerShell 模块](/powershell/scripting/developer/module/writing-a-windows-powershell-module)。</span><span class="sxs-lookup"><span data-stu-id="9c4d2-189">For more information, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c4d2-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c4d2-190">See Also</span></span>

[<span data-ttu-id="9c4d2-191">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="9c4d2-191">Get-EventLog</span></span>](xref:Microsoft.PowerShell.Management.Get-EventLog)

[<span data-ttu-id="9c4d2-192">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9c4d2-192">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="9c4d2-193">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="9c4d2-193">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="9c4d2-194">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="9c4d2-194">about_Preference_Variables</span></span>](about_Preference_Variables.md)
