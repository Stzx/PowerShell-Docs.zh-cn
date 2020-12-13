---
ms.date: 01/18/2019
ms.topic: reference
title: Cmdlet 输出的类型
description: Cmdlet 输出的类型
ms.openlocfilehash: 591b7699e951db9016e48d5ef623265e23791e11
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660493"
---
# <a name="types-of-cmdlet-output"></a><span data-ttu-id="1b2e6-103">Cmdlet 输出的类型</span><span class="sxs-lookup"><span data-stu-id="1b2e6-103">Types of cmdlet output</span></span>

<span data-ttu-id="1b2e6-104">PowerShell 提供多种方法，这些方法可由 cmdlet 调用以生成输出。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-104">PowerShell provides several methods that can be called by cmdlets to generate output.</span></span> <span data-ttu-id="1b2e6-105">这些方法使用特定操作将其输出写入特定数据流，如成功数据流或错误数据流。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-105">These methods use a specific operation to write their output to a specific data stream, such as the success data stream or the error data stream.</span></span> <span data-ttu-id="1b2e6-106">本文介绍输出类型以及用于生成它们的方法。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-106">This article describes the types of output and the methods used to generate them.</span></span>

## <a name="types-of-output"></a><span data-ttu-id="1b2e6-107">输出类型</span><span class="sxs-lookup"><span data-stu-id="1b2e6-107">Types of output</span></span>

### <a name="success-output"></a><span data-ttu-id="1b2e6-108">成功输出</span><span class="sxs-lookup"><span data-stu-id="1b2e6-108">Success output</span></span>

<span data-ttu-id="1b2e6-109">Cmdlet 可以通过返回可由管道中的下一个命令处理的对象来报告成功。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-109">Cmdlets can report success by returning an object that can be processed by the next command in the pipeline.</span></span> <span data-ttu-id="1b2e6-110">Cmdlet 成功执行了其操作后，该 cmdlet 将调用 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) 方法。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-110">After the cmdlet has successfully performed its action, the cmdlet calls the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span> <span data-ttu-id="1b2e6-111">我们建议你调用此方法，而不是调用[PSHostUserInterface](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine)方法或[方法的方法](/dotnet/api/System.Console.WriteLine)。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-111">We recommend that you call this method instead of the [System.Console.WriteLine](/dotnet/api/System.Console.WriteLine) or [System.Management.Automation.Host.PSHostUserInterface.WriteLine](/dotnet/api/System.Management.Automation.Host.PSHostUserInterface.WriteLine) methods.</span></span>

<span data-ttu-id="1b2e6-112">你可以为不返回对象的 cmdlet 提供 **PassThru** 交换机参数。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-112">You can provide a **PassThru** switch parameter for cmdlets that do not typically return objects.</span></span>
<span data-ttu-id="1b2e6-113">当在命令行中指定 **PassThru** 交换机参数时，系统将要求 cmdlet 返回对象。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-113">When the **PassThru** switch parameter is specified at the command line, the cmdlet is asked to return an object.</span></span> <span data-ttu-id="1b2e6-114">有关具有 **PassThru** 参数的 cmdlet 的示例，请参阅 [添加-历史记录](/powershell/module/Microsoft.PowerShell.Core/Add-History)。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-114">For an example of a cmdlet that has a **PassThru** parameter, see [Add-History](/powershell/module/Microsoft.PowerShell.Core/Add-History).</span></span>

### <a name="error-output"></a><span data-ttu-id="1b2e6-115">错误输出</span><span class="sxs-lookup"><span data-stu-id="1b2e6-115">Error output</span></span>

<span data-ttu-id="1b2e6-116">Cmdlet 可以报告错误。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-116">Cmdlets can report errors.</span></span> <span data-ttu-id="1b2e6-117">当发生终止错误时，cmdlet 会引发异常。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-117">When a terminating error occurs, the cmdlet throws an exception.</span></span> <span data-ttu-id="1b2e6-118">当发生非终止错误时，该 cmdlet 将调用 [CmdletProvider. WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) 方法，将错误记录发送到错误数据流。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-118">When a non-terminating error occurs, the cmdlet calls the [System.Management.Automation.Provider.CmdletProvider.WriteError](/dotnet/api/System.Management.Automation.Provider.CmdletProvider.WriteError) method to send an error record to the error data stream.</span></span> <span data-ttu-id="1b2e6-119">有关错误报告的详细信息，请参阅 [错误报告概念](./error-reporting-concepts.md)。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-119">For more information about error reporting, see [Error Reporting Concepts](./error-reporting-concepts.md).</span></span>

### <a name="verbose-output"></a><span data-ttu-id="1b2e6-120">详细输出</span><span class="sxs-lookup"><span data-stu-id="1b2e6-120">Verbose output</span></span>

<span data-ttu-id="1b2e6-121">Cmdlet 可以通过调用 [WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) 方法正确地处理记录，为你提供有用的信息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-121">Cmdlets can provide useful information to you while the cmdlet is correctly processing records by calling the [System.Management.Automation.Cmdlet.WriteVerbose](/dotnet/api/System.Management.Automation.Cmdlet.WriteVerbose) method.</span></span> <span data-ttu-id="1b2e6-122">方法会生成详细消息，指示操作的执行方式。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-122">The method generates verbose messages that indicate how the action is proceeding.</span></span>

<span data-ttu-id="1b2e6-123">默认情况下，不显示详细消息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-123">By default, verbose messages are not displayed.</span></span> <span data-ttu-id="1b2e6-124">可以在运行 cmdlet 时指定 **详细** 参数，以显示这些消息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-124">You can specify the **Verbose** parameter when the cmdlet is run to display these messages.</span></span> <span data-ttu-id="1b2e6-125">**详细** 是适用于所有 cmdlet 的通用参数。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-125">**Verbose** is a common parameter that is available to all cmdlets.</span></span>

### <a name="progress-output"></a><span data-ttu-id="1b2e6-126">进度输出</span><span class="sxs-lookup"><span data-stu-id="1b2e6-126">Progress output</span></span>

<span data-ttu-id="1b2e6-127">当 cmdlet 执行需要很长时间才能完成的任务（例如，递归复制目录）时，cmdlet 可为你提供进度信息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-127">Cmdlets can provide progress information to you when the cmdlet is performing tasks that take a long time to complete, such as copying a directory recursively.</span></span> <span data-ttu-id="1b2e6-128">若要显示进度信息，cmdlet 将调用 [WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) 方法。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-128">To display progress information the cmdlet calls the [System.Management.Automation.Cmdlet.WriteProgress](/dotnet/api/System.Management.Automation.Cmdlet.WriteProgress) method.</span></span>

### <a name="debug-output"></a><span data-ttu-id="1b2e6-129">调试输出</span><span class="sxs-lookup"><span data-stu-id="1b2e6-129">Debug output</span></span>

<span data-ttu-id="1b2e6-130">Cmdlet 可以提供调试消息，这些消息对 cmdlet 代码进行疑难解答时非常有用。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-130">Cmdlets can provide debug messages that are helpful when troubleshooting the cmdlet code.</span></span> <span data-ttu-id="1b2e6-131">若要显示调试信息，该 cmdlet 将调用 [WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) 方法。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-131">To display debug information the cmdlet calls the [System.Management.Automation.Cmdlet.WriteDebug](/dotnet/api/System.Management.Automation.Cmdlet.WriteDebug) method.</span></span>

<span data-ttu-id="1b2e6-132">默认情况下，不显示调试消息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-132">By default, debug messages are not displayed.</span></span> <span data-ttu-id="1b2e6-133">可以在运行 cmdlet 时指定 **Debug** 参数以显示这些消息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-133">You can specify the **Debug** parameter when the cmdlet is run to display these messages.</span></span> <span data-ttu-id="1b2e6-134">**Debug** 是适用于所有 cmdlet 的通用参数。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-134">**Debug** is a common parameter that is available to all cmdlets.</span></span>

### <a name="warning-output"></a><span data-ttu-id="1b2e6-135">警告输出</span><span class="sxs-lookup"><span data-stu-id="1b2e6-135">Warning output</span></span>

<span data-ttu-id="1b2e6-136">Cmdlet 可以通过调用 [WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) 方法来显示警告消息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-136">Cmdlets can display warning messages by calling the [System.Management.Automation.Cmdlet.WriteWarning](/dotnet/api/System.Management.Automation.Cmdlet.WriteWarning) method.</span></span>

<span data-ttu-id="1b2e6-137">默认情况下，会显示警告消息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-137">By default, warning messages are displayed.</span></span> <span data-ttu-id="1b2e6-138">但是，您可以使用 `$WarningPreference` 变量或在调用 cmdlet 时使用 **Verbose** 和 **Debug** 参数来配置警告消息。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-138">However, you can configure warning messages by using the `$WarningPreference` variable or by using the **Verbose** and **Debug** parameters when the cmdlet is called.</span></span>

## <a name="displaying-output"></a><span data-ttu-id="1b2e6-139">显示输出</span><span class="sxs-lookup"><span data-stu-id="1b2e6-139">Displaying output</span></span>

<span data-ttu-id="1b2e6-140">对于所有写方法调用，内容显示由特定的运行时变量确定。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-140">For all write-method calls, the content display is determined by specific runtime variables.</span></span> <span data-ttu-id="1b2e6-141">[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)方法是异常的例外情况。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-141">The exception is the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span> <span data-ttu-id="1b2e6-142">通过使用这些变量，你可以在代码中的正确位置进行适当的写入调用，而无需担心是否应显示输出。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-142">By using these variables, you can make the appropriate write call at the correct place in your code and not worry about when or if the output should be displayed.</span></span>

## <a name="accessing-the-output-functionality-of-a-host-application"></a><span data-ttu-id="1b2e6-143">访问主机应用程序的输出功能</span><span class="sxs-lookup"><span data-stu-id="1b2e6-143">Accessing the output functionality of a host application</span></span>

<span data-ttu-id="1b2e6-144">你还可以设计 cmdlet，以通过 PowerShell 运行时直接访问主机应用程序的输出功能。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-144">You can also design a cmdlet to directly access the output functionality of a host application through the PowerShell runtime.</span></span> <span data-ttu-id="1b2e6-145">使用 PowerShell 提供的宿主 Api，而不是使用 [system. 控制台](/dotnet/api/System.Console) 或 [System.web。窗体](/dotnet/api/System.Windows.Forms) 可确保你的 cmdlet 可与各种主机一起使用。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-145">Using the host APIs provided by PowerShell instead of [System.Console](/dotnet/api/System.Console) or [System.Windows.Forms](/dotnet/api/System.Windows.Forms) ensures that your cmdlet will work with a variety of hosts.</span></span> <span data-ttu-id="1b2e6-146">例如： **powershell.exe** 控制台主机、 **powershell_ise.exe** 图形主机、PowerShell 远程处理主机和第三方主机。</span><span class="sxs-lookup"><span data-stu-id="1b2e6-146">For example: the **powershell.exe** console host, the **powershell_ise.exe** graphical host, the PowerShell remoting host, and third-party hosts.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b2e6-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b2e6-147">See also</span></span>

[<span data-ttu-id="1b2e6-148">错误报告概念</span><span class="sxs-lookup"><span data-stu-id="1b2e6-148">Error Reporting Concepts</span></span>](./error-reporting-concepts.md)

[<span data-ttu-id="1b2e6-149">Cmdlet 概述</span><span class="sxs-lookup"><span data-stu-id="1b2e6-149">Cmdlet Overview</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="1b2e6-150">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1b2e6-150">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
