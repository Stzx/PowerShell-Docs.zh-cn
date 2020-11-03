---
description: 介绍 Windows PowerShell 工作流添加到活动中的参数。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_ActivityCommonParameters
ms.openlocfilehash: b745bf17e4ae26156042ecdc25211830177bc692
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199909"
---
# <a name="about-activitycommonparameters"></a><span data-ttu-id="5c7c2-104">关于 ActivityCommonParameters</span><span class="sxs-lookup"><span data-stu-id="5c7c2-104">About ActivityCommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="5c7c2-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="5c7c2-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="5c7c2-106">介绍 Windows PowerShell 工作流添加到活动中的参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-106">Describes the parameters that Windows PowerShell Workflow adds to activities.</span></span>

## <a name="long-description"></a><span data-ttu-id="5c7c2-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="5c7c2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="5c7c2-108">Windows PowerShell 工作流将活动通用参数添加到从 PSActivity 基类派生的活动。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-108">Windows PowerShell Workflow adds the activity common parameters to activities that are derived from the PSActivity base class.</span></span> <span data-ttu-id="5c7c2-109">此类别包括 InlineScript 活动以及作为活动实现的 Windows PowerShell cmdlet，例如 Get-Process 和 Get-winevent。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-109">This category includes the InlineScript activity and Windows PowerShell cmdlets that are implemented as activities, such as Get-Process and Get-WinEvent.</span></span>

<span data-ttu-id="5c7c2-110">活动通用参数在 Suspend-Workflow 和 Checkpoint-Workflow 活动中无效，它们不会添加到 Windows PowerShell 工作流在 InlineScript 脚本块或类似活动中自动运行的 cmdlet 或表达式中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-110">The activity common parameters are not valid on the Suspend-Workflow and Checkpoint-Workflow activities and they are not added to cmdlets or expressions that Windows PowerShell Workflow automatically runs in an InlineScript script block or similar activity.</span></span> <span data-ttu-id="5c7c2-111">活动通用参数在 InlineScript 活动上可用，但在 InlineScript 脚本块中的命令上不可用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-111">The activity common parameters are available on the InlineScript activity, but not on commands in the InlineScript script block.</span></span>

<span data-ttu-id="5c7c2-112">某些活动通用参数也是工作流通用参数或 Windows PowerShell 通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-112">Several of the activity common parameters are also workflow common parameters or Windows PowerShell common parameters.</span></span> <span data-ttu-id="5c7c2-113">其他活动通用参数对于活动是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-113">Other activity common parameters are unique to activities.</span></span>

<span data-ttu-id="5c7c2-114">有关工作流通用参数的信息，请参阅 about_WorkflowCommonParameters。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-114">For information about the workflow common parameters, see about_WorkflowCommonParameters.</span></span> <span data-ttu-id="5c7c2-115">有关 Windows PowerShell 通用参数的信息，请参阅 about_CommonParameters。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-115">For information about the Windows PowerShell common parameters, see about_CommonParameters.</span></span>

### <a name="list-of-activity-common-parameters"></a><span data-ttu-id="5c7c2-116">活动通用参数的列表</span><span class="sxs-lookup"><span data-stu-id="5c7c2-116">LIST OF ACTIVITY COMMON PARAMETERS</span></span>

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a><span data-ttu-id="5c7c2-117">参数说明</span><span class="sxs-lookup"><span data-stu-id="5c7c2-117">PARAMETER DESCRIPTIONS</span></span>

<span data-ttu-id="5c7c2-118">本部分介绍活动通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-118">This section describes the activity common parameters.</span></span>

#### <a name="appendoutput-boolean"></a><span data-ttu-id="5c7c2-119">AppendOutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-119">AppendOutput \<Boolean\></span></span>

<span data-ttu-id="5c7c2-120">值为 `$True` 将活动的输出添加到变量的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-120">A value of `$True` adds the output of the activity to the value of the variable.</span></span>
<span data-ttu-id="5c7c2-121">值 `$False` 不起作用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-121">A value of `$False` has no effect.</span></span> <span data-ttu-id="5c7c2-122">默认情况下，向变量分配值会替换变量值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-122">By default, assigning a value to a variable replaces the variable value.</span></span>

<span data-ttu-id="5c7c2-123">例如，以下命令将进程对象添加到变量中的服务对象 `$x` 。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-123">For example, the following commands add a process object to the service object in the `$x` variable.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

<span data-ttu-id="5c7c2-124">此参数适用于基于 XAML 的工作流。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-124">This parameter is designed for XAML-based workflows.</span></span> <span data-ttu-id="5c7c2-125">在脚本工作流中，还可以使用 + = 赋值运算符将输出添加到变量的值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-125">In script workflows, you can also use the += assignment operator to add output to the value of a variable, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a><span data-ttu-id="5c7c2-126">Debug.exe \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-126">Debug \<SwitchParameter\></span></span>

<span data-ttu-id="5c7c2-127">显示有关命令所执行操作的程序员级别的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-127">Displays programmer-level detail about the operation performed by the command.</span></span>
<span data-ttu-id="5c7c2-128">Debug 参数重写当前命令的 $DebugPreference 变量的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-128">The Debug parameter overrides the value of the $DebugPreference variable for the current command.</span></span> <span data-ttu-id="5c7c2-129">仅当命令生成调试消息时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-129">This parameter works only when the command generates debugging messages.</span></span> <span data-ttu-id="5c7c2-130">此参数也是 Windows PowerShell 通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-130">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="displayname-string"></a><span data-ttu-id="5c7c2-131">DisplayName \<String\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-131">DisplayName \<String\></span></span>

<span data-ttu-id="5c7c2-132">为活动指定友好名称。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-132">Specifies a friendly name for the activity.</span></span> <span data-ttu-id="5c7c2-133">在工作流运行时，"显示名称" 值显示在进度栏中，在工作流作业的 "进度" 属性值中显示。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-133">The DisplayName value appears in the progress bar while the workflow runs and in the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="5c7c2-134">如果命令中还包含 PSProgressMessage 参数，则进度栏内容将以 \<DisplayName\> ： \<PSProgressMessage\> 格式显示。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-134">When the PSProgressMessage parameter is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

#### <a name="erroraction-actionpreference"></a><span data-ttu-id="5c7c2-135">ErrorAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-135">ErrorAction \<ActionPreference\></span></span>

<span data-ttu-id="5c7c2-136">确定活动如何响应命令中的非终止错误。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-136">Determines how the activity responds to a non-terminating error from the command.</span></span> <span data-ttu-id="5c7c2-137">它不会影响终止错误。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-137">It has no effect on termination errors.</span></span> <span data-ttu-id="5c7c2-138">此参数仅在命令生成非终止错误（如 Write-Error cmdlet 中的错误）时才起作用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-138">This parameter works only when the command generates a non-terminating error, such as those from the Write-Error cmdlet.</span></span> <span data-ttu-id="5c7c2-139">ErrorAction 参数重写当前命令的 $ErrorActionPreference 变量的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-139">The ErrorAction parameter overrides the value of the $ErrorActionPreference variable for the current command.</span></span> <span data-ttu-id="5c7c2-140">此参数也是 Windows PowerShell 通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-140">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="5c7c2-141">有效值：</span><span class="sxs-lookup"><span data-stu-id="5c7c2-141">Valid values:</span></span>

- <span data-ttu-id="5c7c2-142">仍.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-142">Continue.</span></span> <span data-ttu-id="5c7c2-143">显示错误消息并继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-143">Displays the error message and continues executing the command.</span></span> <span data-ttu-id="5c7c2-144">默认值为 "Continue"。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-144">"Continue" is the default value.</span></span>

- <span data-ttu-id="5c7c2-145">忽略。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-145">Ignore.</span></span> <span data-ttu-id="5c7c2-146">禁止显示错误消息并继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-146">Suppresses the error message and continues executing the command.</span></span>
  <span data-ttu-id="5c7c2-147">与 SilentlyContinue 不同，Ignore 不会将错误消息添加到 $Error 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-147">Unlike SilentlyContinue, Ignore does not add the error message to the $Error automatic variable.</span></span> <span data-ttu-id="5c7c2-148">忽略值在 Windows PowerShell 3.0 中引入。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-148">The Ignore value is introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="5c7c2-149">时刻表.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-149">Inquire.</span></span> <span data-ttu-id="5c7c2-150">显示错误消息并提示您进行确认，然后再继续执行。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-150">Displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="5c7c2-151">此值很少使用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-151">This value is rarely used.</span></span>

- <span data-ttu-id="5c7c2-152">休眠.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-152">Suspend.</span></span> <span data-ttu-id="5c7c2-153">自动挂起工作流作业以便进一步进行调查。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-153">Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="5c7c2-154">调查后，工作流可以恢复。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-154">After investigation, the workflow can be resumed.</span></span>

- <span data-ttu-id="5c7c2-155">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-155">SilentlyContinue.</span></span> <span data-ttu-id="5c7c2-156">禁止显示错误消息并继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-156">Suppresses the error message and continues executing the command.</span></span>

- <span data-ttu-id="5c7c2-157">停止。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-157">Stop.</span></span> <span data-ttu-id="5c7c2-158">显示错误消息并停止执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-158">Displays the error message and stops executing the command.</span></span>

#### <a name="input-object"></a><span data-ttu-id="5c7c2-159">送 \<Object[]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-159">Input \<Object[]\></span></span>

<span data-ttu-id="5c7c2-160">将对象的集合提交到活动。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-160">Submits a collection of objects to an activity.</span></span> <span data-ttu-id="5c7c2-161">这是将对象一次一个地通过管道传递给活动的替代方法。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-161">This is an alternative to piping objects to the activity one at a time.</span></span>

#### <a name="mergeerrortooutput-boolean"></a><span data-ttu-id="5c7c2-162">MergeErrorToOutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-162">MergeErrorToOutput \<Boolean\></span></span>

<span data-ttu-id="5c7c2-163">值 `$True` 将错误添加到输出流中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-163">A value of `$True` adds errors to the output stream.</span></span> <span data-ttu-id="5c7c2-164">值 `$False` 无效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-164">A value of `$False` has not effect.</span></span> <span data-ttu-id="5c7c2-165">将此参数与并行和关键字一起使用， `ForEach -Parallel` 可从单个集合中的多个并行命令收集错误和输出。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-165">Use this parameter with the Parallel and `ForEach -Parallel` keywords to collect errors and output from multiple parallel commands in a single collection.</span></span>

#### <a name="psactionretrycount-int32"></a><span data-ttu-id="5c7c2-166">PSActionRetryCount \<Int32\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-166">PSActionRetryCount \<Int32\></span></span>

<span data-ttu-id="5c7c2-167">如果首次尝试失败，则反复尝试运行活动。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-167">Tries repeatedly to run the activity if the first attempt fails.</span></span> <span data-ttu-id="5c7c2-168">默认值 0 表示不重试。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-168">The default value, 0, does not retry.</span></span>

#### <a name="psactionretryintervalsec-int32"></a><span data-ttu-id="5c7c2-169">PSActionRetryIntervalSec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-169">PSActionRetryIntervalSec \<Int32\></span></span>

<span data-ttu-id="5c7c2-170">确定操作重试之间的间隔（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-170">Determines the interval between action retries in seconds.</span></span> <span data-ttu-id="5c7c2-171">默认值 0 表示立即重试操作。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-171">The default value, 0, retries the action immediately.</span></span> <span data-ttu-id="5c7c2-172">仅当命令中还使用了 PSActionRetryCount 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-172">This parameter is valid only when the PSActionRetryCount parameter is also used in the command.</span></span>

#### <a name="psactionrunningtimeoutsec-int32"></a><span data-ttu-id="5c7c2-173">PSActionRunningTimeoutSec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-173">PSActionRunningTimeoutSec \<Int32\></span></span>

<span data-ttu-id="5c7c2-174">确定活动每台目标计算机上可以运行的时间长度。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-174">Determines how long the activity can run on each target computer.</span></span> <span data-ttu-id="5c7c2-175">如果在超时过期之前没有完成该活动，则 Windows PowerShell 工作流将生成一个终止错误并停止处理受影响的目标计算机上的工作流。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-175">If the activity does not complete before the timeout expires, Windows PowerShell Workflow generates a terminating error and stops processing the workflow on the affected target computer.</span></span>

#### <a name="psallowredirection-boolean"></a><span data-ttu-id="5c7c2-176">PSAllowRedirection \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-176">PSAllowRedirection \<Boolean\></span></span>

<span data-ttu-id="5c7c2-177">值 $True 允许将连接重定向到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-177">A value of $True allows redirection of the connection to the target computers.</span></span>
<span data-ttu-id="5c7c2-178">值 $False 不起作用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-178">A value of $False has no effect.</span></span> <span data-ttu-id="5c7c2-179">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-179">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-180">使用 PSConnectionURI 参数时，远程目标将返回一个指令，以重定向到不同的 URI。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-180">When you use the PSConnectionURI parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="5c7c2-181">默认情况下，Windows PowerShell 不会重定向连接，但你可以使用值为 $True 的 PSAllowRedirection 参数，以允许将连接重定向到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-181">By default, Windows PowerShell does not redirect connections, but you can use the PSAllowRedirection parameter with a value of $True to allow redirection of the connection to the target computer.</span></span>

<span data-ttu-id="5c7c2-182">你还可以通过设置 `$PSSessionOption` 首选项变量的 MaximumConnectionRedirectionCount 属性，或创建会话的 cmdlet 的 SSessionOption 参数值的 MaximumConnectionRedirectionCount 属性来限制重定向连接的次数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-182">You can also limit the number of times that the connection is redirected by setting the MaximumConnectionRedirectionCount property of the `$PSSessionOption` preference variable, or the MaximumConnectionRedirectionCount property of the value of the SSessionOption parameter of cmdlets that create a session.</span></span> <span data-ttu-id="5c7c2-183">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-183">The default value is 5.</span></span>

#### <a name="psapplicationname-string"></a><span data-ttu-id="5c7c2-184">PSApplicationName \<String\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-184">PSApplicationName \<String\></span></span>

<span data-ttu-id="5c7c2-185">指定连接 URI 的应用程序名称段，该连接 URI 用于连接到目标计算机。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-185">Specifies the application name segment of the connection URI that is used to connect to the target computers.</span></span> <span data-ttu-id="5c7c2-186">当命令中未使用 ConnectionURI 参数时，请使用此参数指定应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-186">Use this parameter to specify the application name when you are not using the ConnectionURI parameter in the command.</span></span> <span data-ttu-id="5c7c2-187">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-187">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-188">默认值是 `$PSSessionApplicationName` 目标计算机上首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-188">The default value is the value of the `$PSSessionApplicationName` preference variable on the target computer.</span></span> <span data-ttu-id="5c7c2-189">如果未定义此首选项变量，则默认值为 WSMAN。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-189">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="5c7c2-190">该值适用于大多数使用情况。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-190">This value is appropriate for most uses.</span></span> <span data-ttu-id="5c7c2-191">有关详细信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-191">For more information, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="5c7c2-192">WinRM 服务使用应用程序名称来选择为连接请求提供服务的侦听器。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-192">The WinRM service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="5c7c2-193">此参数的值应与远程计算机上的侦听器的 URLPrefix 属性值相匹配。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-193">The value of this parameter should match the value of the URLPrefix property of a listener on the remote computer.</span></span>

#### <a name="psauthentication-authenticationmechanism"></a><span data-ttu-id="5c7c2-194">PSAuthentication \<AuthenticationMechanism\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-194">PSAuthentication \<AuthenticationMechanism\></span></span>

<span data-ttu-id="5c7c2-195">指定在连接到目标计算机时用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-195">Specifies the mechanism that is used to authenticate the user's credentials when connecting to the target computers.</span></span> <span data-ttu-id="5c7c2-196">有效值为 Default、Basic、Credssp、Digest、Kerberos、Negotiate 和 NegotiateWithImplicitCredential。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-196">Valid values are Default, Basic, Credssp, Digest, Kerberos, Negotiate, and NegotiateWithImplicitCredential.</span></span> <span data-ttu-id="5c7c2-197">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-197">The default value is Default.</span></span> <span data-ttu-id="5c7c2-198">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-198">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-199">有关此参数的值的信息，请参阅 MSDN 中 **System.Management.Automation.Runspaces.AuthenticationMechanism** 枚举的说明。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-199">For information about the values of this parameter, see the description of the **System.Management.Automation.Runspaces.AuthenticationMechanism** enumeration in MSDN.</span></span>

> [!WARNING]
> <span data-ttu-id="5c7c2-200">在凭据安全服务提供程序 (CredSSP) 身份验证中，用户凭据传递到远程计算机中以进行验证，这种验证用于要求对多个资源（例如访问远程网络共享）进行验证的命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-200">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="5c7c2-201">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="5c7c2-202">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

#### <a name="pscertificatethumbprint-string"></a><span data-ttu-id="5c7c2-203">PSCertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-203">PSCertificateThumbprint \<String\></span></span>

<span data-ttu-id="5c7c2-204">指定有权执行此操作的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-204">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="5c7c2-205">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-205">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="5c7c2-206">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-206">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-207">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-207">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="5c7c2-208">证书只能映射到本地用户帐户，而不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-208">They can only be mapped to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="5c7c2-209">若要获取证书，请使用 Windows PowerShell Cert：驱动器中的 [Get 项](xref:Microsoft.PowerShell.Management.Get-Item) 或 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-209">To get a certificate, use the [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) or [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) cmdlets in the Windows PowerShell Cert: drive.</span></span>

#### <a name="pscomputername-string"></a><span data-ttu-id="5c7c2-210">PSComputerName \<String[]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-210">PSComputerName \<String[]\></span></span>

<span data-ttu-id="5c7c2-211">指定运行活动的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-211">Specifies the target computers on which the activity run.</span></span> <span data-ttu-id="5c7c2-212">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-212">The default is the local computer.</span></span> <span data-ttu-id="5c7c2-213">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-213">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-214">在以逗号分隔的列表中键入一台或多台计算机的 NETBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-214">Type the NETBIOS name, IP address, or fully-qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="5c7c2-215">若要指定本地计算机，请键入该计算机名称、“localhost”或句点 (.)。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-215">To specify the local computer, type the computer name, "localhost", or a dot (.).</span></span>

<span data-ttu-id="5c7c2-216">若要将本地计算机包含在 PSComputerName 参数的值中，请通过 "以管理员身份运行" 选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-216">To include the local computer in the value of the PSComputerName parameter, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="5c7c2-217">如果从命令中省略此参数，或该值 $null 或空字符串，则工作流目标为本地计算机，并且不使用 Windows PowerShell 远程处理来运行该命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-217">If this parameter is omitted from the command, or it value is $null or an empty string, the workflow target is the local computer and Windows PowerShell remoting is not used to run the command.</span></span>

<span data-ttu-id="5c7c2-218">若要在 ComputerName 参数的值中使用 IP 地址，该命令必须包含 PSCredential 参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-218">To use an IP address in the value of the ComputerName parameter, the command must include the PSCredential parameter.</span></span> <span data-ttu-id="5c7c2-219">此外，必须为计算机配置 HTTPS 传输，或者必须在本地计算机上的 WinRM TrustedHosts 列表中包含远程计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-219">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="5c7c2-220">有关将计算机名称添加到 TrustedHosts 列表的说明，请参阅 [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)中的 "如何将计算机添加到受信任的主机列表中"。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-220">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

#### <a name="psconfigurationname-string"></a><span data-ttu-id="5c7c2-221">PSConfigurationName \<String\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-221">PSConfigurationName \<String\></span></span>

<span data-ttu-id="5c7c2-222">指定用于在目标计算机上创建会话的会话配置。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-222">Specifies the session configurations that are used to create sessions on the target computers.</span></span> <span data-ttu-id="5c7c2-223">在运行工作流的计算机上 (不在目标计算机上输入会话配置的名称。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-223">Enter the name of a session configuration on the target computers (not on the computer that is running the workflow.</span></span> <span data-ttu-id="5c7c2-224">默认值为 "Microsoft PowerShell"。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-224">The default is Microsoft.PowerShell.</span></span> <span data-ttu-id="5c7c2-225">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-225">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretrycount-uint"></a><span data-ttu-id="5c7c2-226">PSConnectionRetryCount \<UInt\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-226">PSConnectionRetryCount \<UInt\></span></span>

<span data-ttu-id="5c7c2-227">指定第一次连接尝试失败时连接到每台目标计算机的最大尝试次数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-227">Specifies the maximum number of attempts to connect to each target computer if the first connection attempt fails.</span></span> <span data-ttu-id="5c7c2-228">输入介于1到 4294967295 (UInt) 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-228">Enter a number between 1 and 4,294,967,295 (UInt.MaxValue).</span></span> <span data-ttu-id="5c7c2-229">默认值为零 (0) 表示不重试尝试。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-229">The default value, zero (0), represents no retry attempts.</span></span>
<span data-ttu-id="5c7c2-230">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-230">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretryintervalsec-uint"></a><span data-ttu-id="5c7c2-231">PSConnectionRetryIntervalSec \<UInt\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-231">PSConnectionRetryIntervalSec \<UInt\></span></span>

<span data-ttu-id="5c7c2-232">指定连接重试尝试之间的延迟（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-232">Specifies the delay between connection retry attempts in seconds.</span></span> <span data-ttu-id="5c7c2-233">默认值为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-233">The default value is zero (0).</span></span> <span data-ttu-id="5c7c2-234">仅当 PSConnectionRetryCount 的值为1时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-234">This parameter is valid only when the value of PSConnectionRetryCount is at least 1.</span></span> <span data-ttu-id="5c7c2-235">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-235">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionuri-systemuri"></a><span data-ttu-id="5c7c2-236">PSConnectionURI \<System.Uri\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-236">PSConnectionURI \<System.Uri\></span></span>

<span data-ttu-id="5c7c2-237">指定 (URI) 的统一资源标识符，该标识符定义目标计算机上的活动的连接终结点。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-237">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint for the activity on the target computer.</span></span> <span data-ttu-id="5c7c2-238">URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-238">The URI must be fully qualified.</span></span> <span data-ttu-id="5c7c2-239">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-239">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-240">此字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="5c7c2-240">The format of this string is as follows:</span></span>

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

<span data-ttu-id="5c7c2-241">默认值是 `http://localhost:5985/WSMAN`。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-241">The default value is `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="5c7c2-242">如果未指定 PSConnectionURI，则可以使用 PSUseSSL、PSComputerName、PSPort 和 PSApplicationName 参数来指定 PSConnectionURI 值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-242">If you do not specify a PSConnectionURI, you can use the PSUseSSL, PSComputerName, PSPort, and PSApplicationName parameters to specify the PSConnectionURI values.</span></span>

<span data-ttu-id="5c7c2-243">URI 的 Transport 段的有效值为 HTTP 和 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-243">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="5c7c2-244">如果使用 Transport 段指定连接 URI，但不指定端口，将使用以下标准端口来创建会话：80 用于 HTTP，443 用于 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-244">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="5c7c2-245">若要使用 Windows PowerShell 远程处理的默认端口，请指定 HTTP 端口 5985 或 HTTPS 端口 5986。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-245">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

#### <a name="pscredential-pscredential"></a><span data-ttu-id="5c7c2-246">PSCredential \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-246">PSCredential \<PSCredential\></span></span>

<span data-ttu-id="5c7c2-247">指定有权在目标计算机上运行活动的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-247">Specifies a user account that has permission to run the activity on the target computer.</span></span> <span data-ttu-id="5c7c2-248">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-248">The default is the current user.</span></span> <span data-ttu-id="5c7c2-249">仅当命令中包括 PSComputerName 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-249">This parameter is valid only when the PSComputerName parameter is included in the command.</span></span> <span data-ttu-id="5c7c2-250">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-250">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-251">键入用户名，如 "User01" 或 "Domain01\User01"，或输入包含 PSCredential 对象（例如 Get-Credential cmdlet 返回的一个 PSCredential 对象）的变量。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-251">Type a user name, such as "User01" or "Domain01\User01", or enter a variable that contains a PSCredential object, such as one that the Get-Credential cmdlet returns.</span></span> <span data-ttu-id="5c7c2-252">如果仅输入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-252">If you enter only a user name, you will be prompted for a password.</span></span>

#### <a name="psdebug-psdatacollectiondebugrecord"></a><span data-ttu-id="5c7c2-253">Set-psdebug \<PSDataCollection[DebugRecord]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-253">PSDebug \<PSDataCollection[DebugRecord]\></span></span>

<span data-ttu-id="5c7c2-254">将活动中的调试消息添加到指定的调试记录集合，而不是将调试消息写入控制台或工作流作业的 "调试" 属性的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-254">Adds debug messages from the activity to the specified debug record collection, instead of writing the debug messages to the console or to the value of the Debug property of the workflow job.</span></span> <span data-ttu-id="5c7c2-255">可以将来自多个活动的调试消息添加到同一个调试记录集合对象中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-255">You can add debug messages from multiple activities to the same debug record collection object.</span></span>

<span data-ttu-id="5c7c2-256">若要使用此活动通用参数，请使用 New-Object cmdlet 创建具有 DebugRecord 类型的 C o 对象，并将该对象保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-256">To use this activity common parameter, use the New-Object cmdlet to create a PSDataCollection object with a type of DebugRecord and save the object in a variable.</span></span> <span data-ttu-id="5c7c2-257">然后，将变量用作一个或多个活动的 Set-psdebug 参数的值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-257">Then, use the variable as the value of the PSDebug parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a><span data-ttu-id="5c7c2-258">PSDisableSerialization \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-258">PSDisableSerialization \<Boolean\></span></span>

<span data-ttu-id="5c7c2-259">指示活动将“实时”（未序列化）对象返回给工作流。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-259">Directs the activity to return "live" (not serialized) objects to the workflow.</span></span>
<span data-ttu-id="5c7c2-260">得到的对象具有方法以及属性，但它们无法在采用检查点时进行保存。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-260">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>

#### <a name="psdisableserializationpreference-boolean"></a><span data-ttu-id="5c7c2-261">PSDisableSerializationPreference \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-261">PSDisableSerializationPreference \<Boolean\></span></span>

<span data-ttu-id="5c7c2-262">将 PSDisableSerialization 参数的等效项应用于整个工作流，而不仅仅是活动。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-262">Applies the equivalent of the PSDisableSerialization parameter to the entire workflow, not just the activity.</span></span> <span data-ttu-id="5c7c2-263">通常不建议添加此参数，因为不序列化其对象的工作流无法恢复或保持。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-263">Adding this parameter is generally not recommended, because a workflow that doesn't serialize its objects cannot be resumed or persisted.</span></span>

<span data-ttu-id="5c7c2-264">有效值：</span><span class="sxs-lookup"><span data-stu-id="5c7c2-264">Valid values:</span></span>

- <span data-ttu-id="5c7c2-265"> (默认值) 如果省略，并且还没有向活动中添加 PSDisableSerialization 参数，则会序列化对象。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-265">(Default) If omitted, and you have also not added the PSDisableSerialization parameter to an activity, objects are serialized.</span></span>

- <span data-ttu-id="5c7c2-266">`$True`.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-266">`$True`.</span></span> <span data-ttu-id="5c7c2-267">指示工作流中的所有活动返回“实时”（未序列化）对象。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-267">Directs all activities within a workflow to return "live" (not serialized) objects.</span></span> <span data-ttu-id="5c7c2-268">得到的对象具有方法以及属性，但它们无法在采用检查点时进行保存。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-268">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>
- <span data-ttu-id="5c7c2-269">`$False`.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-269">`$False`.</span></span> <span data-ttu-id="5c7c2-270">工作流对象进行序列化。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-270">Workflow objects are serialized.</span></span>

#### <a name="pserror-psdatacollectionerrorrecord"></a><span data-ttu-id="5c7c2-271">PSError \<PSDataCollection[ErrorRecord]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-271">PSError \<PSDataCollection[ErrorRecord]\></span></span>

<span data-ttu-id="5c7c2-272">将活动中的错误消息添加到指定的错误记录集合，而不是将错误消息写入控制台或工作流作业的 Error 属性的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-272">Adds error messages from the activity to the specified error record collection, instead of writing the error messages to the console or to the value of the Error property of the workflow job.</span></span> <span data-ttu-id="5c7c2-273">可以将来自多个活动的错误消息添加到同一个错误记录集合对象中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-273">You can add error messages from multiple activities to the same error record collection object.</span></span>

<span data-ttu-id="5c7c2-274">若要使用此活动通用参数，请使用 `New-Object` cmdlet 创建类型为 ErrorRecord 的 c o 对象，并将该对象保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-274">To use this activity common parameter, use the `New-Object` cmdlet to create a PSDataCollection object with a type of ErrorRecord and save the object in a variable.</span></span> <span data-ttu-id="5c7c2-275">然后，将变量用作一个或多个活动的 PSError 参数的值，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-275">Then, use the variable as the value of the PSError parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a><span data-ttu-id="5c7c2-276">PSPersist \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-276">PSPersist \<Boolean\></span></span>

<span data-ttu-id="5c7c2-277">在活动后使用一个检查点。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-277">Takes a checkpoint after the activity.</span></span> <span data-ttu-id="5c7c2-278">除了工作流中指定的任何检查点之外，此检查点也是如此。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-278">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span> <span data-ttu-id="5c7c2-279">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-279">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-280">"检查点" 或 "持久性点" 是工作流状态和工作流运行时捕获的数据的快照，并保存到磁盘上的持久性存储中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-280">A "checkpoint" or "persistence point" is a snapshot of the workflow state and data that is captured while the workflow runs and is saved to a persistence store on disk.</span></span> <span data-ttu-id="5c7c2-281">Windows PowerShell 工作流使用保存的数据从最后一个暂留点恢复挂起或中断的工作流，而不是重新启动工作流。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-281">Windows PowerShell Workflow uses the saved data to resume a suspended or interrupted workflow from the last persistence point, rather than to restart the workflow.</span></span>

<span data-ttu-id="5c7c2-282">有效值：</span><span class="sxs-lookup"><span data-stu-id="5c7c2-282">Valid values:</span></span>

- <span data-ttu-id="5c7c2-283"> (默认值) 如果省略此参数，则不会添加任何检查点。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-283">(Default) If you omit this parameter, no checkpoints are added.</span></span> <span data-ttu-id="5c7c2-284">检查点基于工作流的设置。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-284">Checkpoints are taken based on the settings for the workflow.</span></span>

- <span data-ttu-id="5c7c2-285">`$True`.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-285">`$True`.</span></span> <span data-ttu-id="5c7c2-286">在活动完成后使用一个检查点。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-286">Takes a checkpoint after the activity completes.</span></span>
  <span data-ttu-id="5c7c2-287">除了工作流中指定的任何检查点之外，此检查点也是如此。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-287">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="5c7c2-288">`$False`.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-288">`$False`.</span></span> <span data-ttu-id="5c7c2-289">不添加任何检查点。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-289">No checkpoints are added.</span></span> <span data-ttu-id="5c7c2-290">仅在工作流中指定了检查点。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-290">Checkpoints are taken only when specified in the workflow.</span></span>

#### <a name="psport-int32"></a><span data-ttu-id="5c7c2-291">PSPort \<Int32\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-291">PSPort \<Int32\></span></span>

<span data-ttu-id="5c7c2-292">指定目标计算机上的网络端口。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-292">Specifies the network port on the target computers.</span></span> <span data-ttu-id="5c7c2-293">默认端口为 5985（HTTP 的 WinRM 端口）和 5986（HTTPS 的 WinRM 端口）。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-293">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span> <span data-ttu-id="5c7c2-294">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-294">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-295">请勿使用 PSPort 参数，除非你必须这样做。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-295">Do not use the PSPort parameter unless you must.</span></span> <span data-ttu-id="5c7c2-296">命令中设置的端口适用于运行该命令的所有计算机或会话。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-296">The port set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="5c7c2-297">备用端口设置可能会阻止在所有计算机上运行该命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-297">An alternate port setting might prevent the command from running on all computers.</span></span> <span data-ttu-id="5c7c2-298">使用备用端口之前，你必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-298">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>

#### <a name="psprogress-psdatacollectionprogressrecord"></a><span data-ttu-id="5c7c2-299">PSProgress \<PSDataCollection[ProgressRecord]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-299">PSProgress \<PSDataCollection[ProgressRecord]\></span></span>

<span data-ttu-id="5c7c2-300">将活动中的进度消息添加到指定的进度记录集合，而不是将进度消息写入控制台或工作流作业的进度属性值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-300">Adds progress messages from the activity to the specified progress record collection, instead of writing the progress messages to the console or to the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="5c7c2-301">可以将来自多个活动的进度消息添加到同一个进度记录集合对象中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-301">You can add progress messages from multiple activities to the same progress record collection object.</span></span>

#### <a name="psprogressmessage-string"></a><span data-ttu-id="5c7c2-302">PSProgressMessage \<String\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-302">PSProgressMessage \<String\></span></span>

<span data-ttu-id="5c7c2-303">指定活动的易懂描述。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-303">Specifies a friendly description of the activity.</span></span> <span data-ttu-id="5c7c2-304">工作流运行时，PSProgressMessage 值会显示在进度栏中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-304">The PSProgressMessage value appears in the progress bar while the workflow runs.</span></span> <span data-ttu-id="5c7c2-305">如果该显示名称也包含在命令中，则进度栏内容将以 \<DisplayName\> ： \<PSProgressMessage\> 格式显示。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-305">When the DisplayName is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

<span data-ttu-id="5c7c2-306">此参数对于标识 ForEach 并行脚本块中的活动特别有用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-306">This parameter is particularly useful for identifying activities in a ForEach -Parallel script block.</span></span> <span data-ttu-id="5c7c2-307">没有此消息时，所有并行分支中的活动都通过相同名称进行标识。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-307">Without this message, activities in all parallel branches are identified by the same name.</span></span>

#### <a name="psremotingbehavior-remotingbehavior"></a><span data-ttu-id="5c7c2-308">PSRemotingBehavior \<RemotingBehavior\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-308">PSRemotingBehavior \<RemotingBehavior\></span></span>

<span data-ttu-id="5c7c2-309">指定活动在目标计算机上运行时的远程处理管理方式。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-309">Specifies how remoting is managed when the activity is run on target computers.</span></span>
<span data-ttu-id="5c7c2-310">默认值为 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-310">PowerShell is the default.</span></span>

<span data-ttu-id="5c7c2-311">有效值是：</span><span class="sxs-lookup"><span data-stu-id="5c7c2-311">Valid values are:</span></span>

- <span data-ttu-id="5c7c2-312">无：活动不在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-312">None: The activity is not run on remote computers.</span></span>

- <span data-ttu-id="5c7c2-313">PowerShell：使用 Windows PowerShell 远程处理在目标计算机上运行活动。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-313">PowerShell: Windows PowerShell remoting is used to run the activity on target computers.</span></span>

- <span data-ttu-id="5c7c2-314">自定义：活动支持其自己的远程处理类型。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-314">Custom: The activity supports its own type of remoting.</span></span> <span data-ttu-id="5c7c2-315">当作为活动实现的 cmdlet 将 RemotingCapability 属性的值设置为 SupportedByCommand，并且该命令包含 ComputerName 参数时，此值有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-315">This value is valid when the cmdlet that is being implemented as an activity sets the value of the RemotingCapability attribute to SupportedByCommand and the command includes the ComputerName parameter.</span></span>

#### <a name="psrequiredmodules-string"></a><span data-ttu-id="5c7c2-316">PSRequiredModules \<String[]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-316">PSRequiredModules \<String[]\></span></span>

<span data-ttu-id="5c7c2-317">在运行命令之前导入指定模块。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-317">Imports the specified modules before running the command.</span></span> <span data-ttu-id="5c7c2-318">输入模块名。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-318">Enter the module names.</span></span> <span data-ttu-id="5c7c2-319">该模块必须安装在目标计算机上。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-319">The modules must be installed on the target computer.</span></span>

<span data-ttu-id="5c7c2-320">当首次使用模块中的任何命令时，将自动导入在 PSModulePath 环境变量中指定的路径中安装的模块。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-320">Modules that are installed in a path specified in the PSModulePath environment variable are automatically imported on first use of any command in the module.</span></span>
<span data-ttu-id="5c7c2-321">使用此参数可导入不在 PSModulePath 位置中的模块。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-321">Use this parameter to import modules that are not in a PSModulePath location.</span></span>

<span data-ttu-id="5c7c2-322">因为工作流中的每个活动都在其自己的会话中运行，所以 Import-Module 命令仅将模块导入运行它的会话中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-322">Because each activity in a workflow runs in its own session, an Import-Module command imports a module only into the session in which it runs.</span></span> <span data-ttu-id="5c7c2-323">它不将模块导入运行其他活动的会话中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-323">It does not import the module into sessions in which other activities run.</span></span>

#### <a name="pssessionoption-pssessionoption"></a><span data-ttu-id="5c7c2-324">PSSessionOption \<PSSessionOption\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-324">PSSessionOption \<PSSessionOption\></span></span>

<span data-ttu-id="5c7c2-325">为目标计算机的会话设置高级选项。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-325">Sets advanced options for the sessions to the target computers.</span></span> <span data-ttu-id="5c7c2-326">输入一个 PSSessionOption 对象，例如使用 New-PSSessionOption cmdlet 创建的对象。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-326">Enter a PSSessionOption object, such as one that you create by using the New-PSSessionOption cmdlet.</span></span> <span data-ttu-id="5c7c2-327">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-327">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-328">会话选项的默认值取决于 `$PSSessionOption` 首选项变量的值（如果已设置）。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-328">The default values for the session options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="5c7c2-329">否则，会话将使用在会话配置中指定的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-329">Otherwise, the session uses the values specified in the session configuration.</span></span>

<span data-ttu-id="5c7c2-330">有关会话选项（包括默认值）的说明，请参阅 New-PSSessionOption cmdlet [PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-330">For a description of the session options, including the default values, see the help topic for the New-PSSessionOption cmdlet [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="5c7c2-331">有关 $PSSessionOption 首选项变量的详细信息，请参阅 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-331">For more information about the $PSSessionOption preference variable, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

#### <a name="psusessl-boolean"></a><span data-ttu-id="5c7c2-332">PSUseSSL \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-332">PSUseSSL \<Boolean\></span></span>

<span data-ttu-id="5c7c2-333">值 $True 使用安全套接字层 (SSL) 协议建立与目标计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-333">A value of $True uses the Secure Sockets Layer (SSL) protocol to establish a connection to the target computer.</span></span> <span data-ttu-id="5c7c2-334">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-334">By default, SSL is not used.</span></span> <span data-ttu-id="5c7c2-335">值 $False 不起作用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-335">A value of $False has no effect.</span></span> <span data-ttu-id="5c7c2-336">此活动通用参数也是工作流通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-336">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="5c7c2-337">WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-337">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="5c7c2-338">UseSSL 是一种额外的保护措施，它通过 HTTPS 而不是 HTTP 来发送数据。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-338">UseSSL is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span> <span data-ttu-id="5c7c2-339">如果你使用此参数，但 SSL 在用于此命令的端口上不可用，则命令将失败。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-339">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

#### <a name="psverbose-psdatacollectionverboserecord"></a><span data-ttu-id="5c7c2-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span></span>

<span data-ttu-id="5c7c2-341">将来自活动的详细消息添加到指定的详细记录集合，而不是将详细消息写入控制台或工作流作业的详细属性值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-341">Adds verbose messages from the activity to the specified verbose record collection, instead of writing the verbose messages to the console or to the value of the Verbose property of the workflow job.</span></span> <span data-ttu-id="5c7c2-342">可以将来自多个活动的详细消息添加到同一个详细记录集合对象中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-342">You can add verbose messages from multiple activities to the same verbose record collection object.</span></span>

#### <a name="pswarning-psdatacollectionwarningrecord"></a><span data-ttu-id="5c7c2-343">PSWarning \<PSDataCollection[WarningRecord]\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-343">PSWarning \<PSDataCollection[WarningRecord]\></span></span>

<span data-ttu-id="5c7c2-344">将来自活动的警告消息添加到指定的警告记录集合，而不是将警告消息写入控制台或工作流作业的 Warning 属性的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-344">Adds warning messages from the activity to the specified warning record collection, instead of writing the warning messages to the console or to the value of the Warning property of the workflow job.</span></span> <span data-ttu-id="5c7c2-345">可以将来自多个活动的警告消息添加到同一个警告记录集合对象中。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-345">You can add warning messages from multiple activities to the same warning record collection object.</span></span>

#### <a name="result"></a><span data-ttu-id="5c7c2-346">结果</span><span class="sxs-lookup"><span data-stu-id="5c7c2-346">Result</span></span>

<span data-ttu-id="5c7c2-347">此参数仅在 XAML 工作流中有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-347">This parameter is valid only in XAML workflows.</span></span>

#### <a name="usedefaultinput-boolean"></a><span data-ttu-id="5c7c2-348">UseDefaultInput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-348">UseDefaultInput \<Boolean\></span></span>

<span data-ttu-id="5c7c2-349">按值接受所有工作流输入作为活动的输入。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-349">Accepts all workflow input as input to the activity by value.</span></span>

<span data-ttu-id="5c7c2-350">例如，以下示例工作流中的 Get-Process 活动使用 UseDefaultInput 活动通用参数获取传递给工作流的输入。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-350">For example, the Get-Process activity in the following sample workflow uses the UseDefaultInput activity common parameter to get input that is passed to the workflow.</span></span> <span data-ttu-id="5c7c2-351">使用输入运行工作流时，活动会使用该输入。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-351">When you run the workflow with input, that input is used by the activity.</span></span>

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a><span data-ttu-id="5c7c2-352">详细 \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-352">Verbose \<SwitchParameter\></span></span>

<span data-ttu-id="5c7c2-353">显示有关命令所执行操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-353">Displays detailed information about the operation performed by the command.</span></span>
<span data-ttu-id="5c7c2-354">此信息类似于跟踪或事务日志中的信息。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-354">This information resembles the information in a trace or in a transaction log.</span></span>
<span data-ttu-id="5c7c2-355">Verbose 参数重写当前命令的 $VerbosePreference 变量的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-355">The Verbose parameter overrides the value of the $VerbosePreference variable for the current command.</span></span> <span data-ttu-id="5c7c2-356">仅当命令生成详细消息时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-356">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="5c7c2-357">此参数也是 Windows PowerShell 通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-357">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="warningaction-actionpreference"></a><span data-ttu-id="5c7c2-358">WarningAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="5c7c2-358">WarningAction \<ActionPreference\></span></span>

<span data-ttu-id="5c7c2-359">确定活动如何响应警告。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-359">Determines how the activity responds to a warning.</span></span> <span data-ttu-id="5c7c2-360">默认值为 "Continue"。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-360">"Continue" is the default value.</span></span> <span data-ttu-id="5c7c2-361">WarningAction 参数重写当前命令的 $WarningPreference 变量的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-361">The WarningAction parameter overrides the value of the $WarningPreference variable for the current command.</span></span> <span data-ttu-id="5c7c2-362">仅当命令生成警告消息时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-362">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="5c7c2-363">此参数也是 Windows PowerShell 通用参数。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-363">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="5c7c2-364">有效值：</span><span class="sxs-lookup"><span data-stu-id="5c7c2-364">Valid Values:</span></span>

- <span data-ttu-id="5c7c2-365">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-365">SilentlyContinue.</span></span> <span data-ttu-id="5c7c2-366">禁止显示警告消息并继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-366">Suppresses the warning message and continues executing the command.</span></span>

- <span data-ttu-id="5c7c2-367">仍.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-367">Continue.</span></span> <span data-ttu-id="5c7c2-368">显示警告消息并继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-368">Displays the warning message and continues executing the command.</span></span>
  <span data-ttu-id="5c7c2-369">默认值为 "Continue"。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-369">"Continue" is the default value.</span></span>

- <span data-ttu-id="5c7c2-370">时刻表.</span><span class="sxs-lookup"><span data-stu-id="5c7c2-370">Inquire.</span></span> <span data-ttu-id="5c7c2-371">显示警告消息并提示您进行确认，然后再继续执行。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-371">Displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="5c7c2-372">此值很少使用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-372">This value is rarely used.</span></span>

- <span data-ttu-id="5c7c2-373">停止。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-373">Stop.</span></span> <span data-ttu-id="5c7c2-374">显示警告消息，并停止执行命令。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-374">Displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="5c7c2-375">当在命令中使用参数运行脚本或函数时，WarningAction 参数不会重写 $WarningAction 首选项变量的值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-375">The WarningAction parameter does not override the value of the $WarningAction preference variable when the parameter is used in a command to run a script or function.</span></span>

### <a name="examples"></a><span data-ttu-id="5c7c2-376">示例</span><span class="sxs-lookup"><span data-stu-id="5c7c2-376">EXAMPLES</span></span>

<span data-ttu-id="5c7c2-377">活动通用参数非常有用。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-377">The activity common parameters are extremely useful.</span></span> <span data-ttu-id="5c7c2-378">例如，你可以使用 PSComputerName 参数来仅对目标计算机的一个子集运行特定活动。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-378">For example, you can use the PSComputerName parameter to run particular activities on only a subset of the target computers.</span></span>

<span data-ttu-id="5c7c2-379">或者，你可以使用 PSConnectionRetryCount 和 PSConnectionRetryIntervalSec 参数来调整特定活动的重试值。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-379">Or, you might use the PSConnectionRetryCount and PSConnectionRetryIntervalSec parameters to adjust the retry values for particular activities.</span></span>

<span data-ttu-id="5c7c2-380">下面的示例演示如何使用 PSComputerName 活动通用参数仅在其特定域的计算机上运行 Get-EventLog 活动。</span><span class="sxs-lookup"><span data-stu-id="5c7c2-380">The following example shows how to use the PSComputerName activity common parameters to run a Get-EventLog activity only on computers it a particular domain.</span></span>

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a><span data-ttu-id="5c7c2-381">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c7c2-381">SEE ALSO</span></span>

<span data-ttu-id="5c7c2-382">[about_Workflows](about_workflows.md) 
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="5c7c2-382">[about_Workflows](about_workflows.md)
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span></span>
