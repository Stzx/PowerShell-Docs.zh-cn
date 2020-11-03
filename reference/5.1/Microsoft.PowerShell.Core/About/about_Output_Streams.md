---
description: 说明 PowerShell 中输出流的可用性和用途。
keywords: PowerShell，cmdlet
Locale: en-US
ms.date: 10/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_output_streams?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Output_Streams
ms.openlocfilehash: 2f63c468f6b0d82559fca354a8ce5c1343eb2084
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200511"
---
# <a name="about-output-streams"></a><span data-ttu-id="f8f9a-104">关于输出流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-104">About output streams</span></span>

## <a name="short-description"></a><span data-ttu-id="f8f9a-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="f8f9a-105">Short description</span></span>
<span data-ttu-id="f8f9a-106">说明 PowerShell 中输出流的可用性和用途。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-106">Explains the availability and purpose of output streams in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="f8f9a-107">长说明</span><span class="sxs-lookup"><span data-stu-id="f8f9a-107">Long description</span></span>

<span data-ttu-id="f8f9a-108">PowerShell 提供多个输出流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-108">PowerShell provides multiple output streams.</span></span> <span data-ttu-id="f8f9a-109">流为不同类型的消息提供通道。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-109">The streams provide channels for different types of messages.</span></span> <span data-ttu-id="f8f9a-110">你可以使用关联的 cmdlet 或重定向写入这些流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-110">You can write to these streams using the associated cmdlet or redirection.</span></span> <span data-ttu-id="f8f9a-111">有关详细信息，请参阅 [about_Redirection](about_Redirection.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-111">For more information, see [about_Redirection](about_Redirection.md).</span></span>

<span data-ttu-id="f8f9a-112">PowerShell 支持以下输出流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-112">PowerShell supports the following output streams.</span></span>

| <span data-ttu-id="f8f9a-113">流#</span><span class="sxs-lookup"><span data-stu-id="f8f9a-113">Stream #</span></span> |      <span data-ttu-id="f8f9a-114">说明</span><span class="sxs-lookup"><span data-stu-id="f8f9a-114">Description</span></span>       | <span data-ttu-id="f8f9a-115">引入</span><span class="sxs-lookup"><span data-stu-id="f8f9a-115">Introduced in</span></span>  |    <span data-ttu-id="f8f9a-116">写入 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f8f9a-116">Write Cmdlet</span></span>     |
| -------- | ---------------------- | -------------- | ------------------- |
| <span data-ttu-id="f8f9a-117">1</span><span class="sxs-lookup"><span data-stu-id="f8f9a-117">1</span></span>        | <span data-ttu-id="f8f9a-118">**成功** 流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-118">**Success** stream</span></span>     | <span data-ttu-id="f8f9a-119">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="f8f9a-119">PowerShell 2.0</span></span> | `Write-Output`      |
| <span data-ttu-id="f8f9a-120">2</span><span class="sxs-lookup"><span data-stu-id="f8f9a-120">2</span></span>        | <span data-ttu-id="f8f9a-121">**错误** 流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-121">**Error** stream</span></span>       | <span data-ttu-id="f8f9a-122">PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="f8f9a-122">PowerShell 2.0</span></span> | `Write-Error`       |
| <span data-ttu-id="f8f9a-123">3</span><span class="sxs-lookup"><span data-stu-id="f8f9a-123">3</span></span>        | <span data-ttu-id="f8f9a-124">**警告** 流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-124">**Warning** stream</span></span>     | <span data-ttu-id="f8f9a-125">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="f8f9a-125">PowerShell 3.0</span></span> | `Write-Warning`     |
| <span data-ttu-id="f8f9a-126">4</span><span class="sxs-lookup"><span data-stu-id="f8f9a-126">4</span></span>        | <span data-ttu-id="f8f9a-127">**详细** 流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-127">**Verbose** stream</span></span>     | <span data-ttu-id="f8f9a-128">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="f8f9a-128">PowerShell 3.0</span></span> | `Write-Verbose`     |
| <span data-ttu-id="f8f9a-129">5</span><span class="sxs-lookup"><span data-stu-id="f8f9a-129">5</span></span>        | <span data-ttu-id="f8f9a-130">**调试** 流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-130">**Debug** stream</span></span>       | <span data-ttu-id="f8f9a-131">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="f8f9a-131">PowerShell 3.0</span></span> | `Write-Debug`       |
| <span data-ttu-id="f8f9a-132">6</span><span class="sxs-lookup"><span data-stu-id="f8f9a-132">6</span></span>        | <span data-ttu-id="f8f9a-133">**信息流**</span><span class="sxs-lookup"><span data-stu-id="f8f9a-133">**Information** stream</span></span> | <span data-ttu-id="f8f9a-134">PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f8f9a-134">PowerShell 5.0</span></span> | `Write-Information` |
| <span data-ttu-id="f8f9a-135">不适用</span><span class="sxs-lookup"><span data-stu-id="f8f9a-135">n/a</span></span>      | <span data-ttu-id="f8f9a-136">**进度** 流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-136">**Progress** stream</span></span>    | <span data-ttu-id="f8f9a-137">PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="f8f9a-137">PowerShell 3.0</span></span> | `Write-Progress`    |

> [!NOTE]
> <span data-ttu-id="f8f9a-138">**进度** 流不支持重定向。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-138">The **Progress** stream does not support redirection.</span></span>

## <a name="success-stream"></a><span data-ttu-id="f8f9a-139">成功流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-139">Success stream</span></span>

<span data-ttu-id="f8f9a-140">**成功** 流是正常、成功结果的默认流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-140">The **Success** stream is the default stream for normal, successful results.</span></span>
<span data-ttu-id="f8f9a-141">使用 `Write-Output` cmdlet 将对象显式写入此流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-141">Use the `Write-Output` cmdlet to explicitly write objects to this stream.</span></span> <span data-ttu-id="f8f9a-142">此流用于通过 PowerShell 管道传递对象。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-142">This stream is used for passing objects through the PowerShell pipeline.</span></span> <span data-ttu-id="f8f9a-143">**成功** 流连接到本机应用程序的 **stdout** 流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-143">The **Success** stream is connected to the **stdout** stream for native applications.</span></span>

## <a name="error-stream"></a><span data-ttu-id="f8f9a-144">错误流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-144">Error stream</span></span>

<span data-ttu-id="f8f9a-145">**错误** 流是错误结果的默认流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-145">The **Error** stream is the default stream for error results.</span></span> <span data-ttu-id="f8f9a-146">使用 `Write-Error` cmdlet 显式写入此流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-146">Use the `Write-Error` cmdlet to explicitly write to this stream.</span></span> <span data-ttu-id="f8f9a-147">**错误** 流连接到本机应用程序的 **stderr** 流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-147">The **Error** stream is connected to the **stderr** stream for native applications.</span></span> <span data-ttu-id="f8f9a-148">在大多数情况下，这些错误可能会终止执行管道。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-148">Under most conditions, these errors can terminate the execution pipeline.</span></span> <span data-ttu-id="f8f9a-149">写入到此流的错误也会添加到 `$Error` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-149">Errors written to this stream are also added the the `$Error` automatic variable.</span></span> <span data-ttu-id="f8f9a-150">有关详细信息，请参阅 [about_Automatic_Variables](about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-150">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

## <a name="warning-stream"></a><span data-ttu-id="f8f9a-151">警告流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-151">Warning stream</span></span>

<span data-ttu-id="f8f9a-152">**警告** 流适用于不符合写入 **错误** 流的错误的错误条件。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-152">The **Warning** stream is intended for error conditions that are less severe than errors written to the **Error** stream.</span></span> <span data-ttu-id="f8f9a-153">正常情况下，这些警告不会终止执行。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-153">Under normal conditions, these warnings do not terminate execution.</span></span> <span data-ttu-id="f8f9a-154">警告不会写入 `$Error` 自动变量。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-154">Warnings are not written to the `$Error` automatic variable.</span></span> <span data-ttu-id="f8f9a-155">使用 `Write-Warning` cmdlet 显式写入此流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-155">Use the `Write-Warning` cmdlet to explicitly write to this stream.</span></span>

## <a name="verbose-stream"></a><span data-ttu-id="f8f9a-156">详细流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-156">Verbose stream</span></span>

<span data-ttu-id="f8f9a-157">**详细** 流用于帮助用户在交互运行或从脚本中运行命令时排除其故障的消息。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-157">The **Verbose** stream is intended for messages that help users troubleshoot commands as they are run interactively or from a script.</span></span> <span data-ttu-id="f8f9a-158">使用 `Write-Verbose` cmdlet 将消息显式写入此流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-158">Use the `Write-Verbose` cmdlet to explicitly write messages to this stream.</span></span> <span data-ttu-id="f8f9a-159">许多 cmdlet 提供详细的输出，有助于了解 cmdlet 的内部工作原理。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-159">Many cmdlets provide verbose output that is useful for understanding the internal workings of the cmdlet.</span></span> <span data-ttu-id="f8f9a-160">仅当使用 common 参数时，才会输出详细消息 `-Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-160">The verbose messages are output only when you use the `-Verbose` common parameter.</span></span> <span data-ttu-id="f8f9a-161">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-161">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

## <a name="debug-stream"></a><span data-ttu-id="f8f9a-162">调试流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-162">Debug stream</span></span>

<span data-ttu-id="f8f9a-163">**调试** 流用于帮助脚本理解其代码失败的原因的消息。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-163">The **Debug** stream is used for messages that help scripters understand why their code is failing.</span></span> <span data-ttu-id="f8f9a-164">使用 `Write-Debug` cmdlet 显式写入此流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-164">Use the `Write-Debug` cmdlet to explicitly write to this stream.</span></span> <span data-ttu-id="f8f9a-165">仅当使用 common 参数时，才会输出调试消息 `-Debug` 。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-165">The debug messages are output only when you use the `-Debug` common parameter.</span></span> <span data-ttu-id="f8f9a-166">有关详细信息，请参阅 [about_CommonParameters](about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-166">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="f8f9a-167">调试消息适用于比最终用户更多的脚本和 cmdlet 开发人员。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-167">Debug messages are intended for script and cmdlet developers more than end users.</span></span> <span data-ttu-id="f8f9a-168">这些调试消息可能包含深层故障排除所需的内部详细信息。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-168">These debug messages can contain internal details necessary for deep troubleshooting.</span></span>

## <a name="information-stream"></a><span data-ttu-id="f8f9a-169">信息流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-169">Information stream</span></span>

<span data-ttu-id="f8f9a-170">**信息流** 旨在提供帮助用户了解脚本正在执行的操作的消息。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-170">The **Information** stream is intended to provide message that help a user understand what a script is doing.</span></span> <span data-ttu-id="f8f9a-171">开发人员也可以使用它作为通过 PowerShell 传递信息的附加流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-171">It can also be used by developers as an additional stream used to pass information through PowerShell.</span></span> <span data-ttu-id="f8f9a-172">开发人员可以标记流数据，并对该流进行特定的处理。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-172">The developer can tag stream data and have specific handling for that stream.</span></span> <span data-ttu-id="f8f9a-173">使用 `Write-Information` cmdlet 显式写入此流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-173">Use the `Write-Information` cmdlet to explicitly write to this stream.</span></span>

## <a name="progress-stream"></a><span data-ttu-id="f8f9a-174">进度流</span><span class="sxs-lookup"><span data-stu-id="f8f9a-174">Progress stream</span></span>

<span data-ttu-id="f8f9a-175">**进度** 流用于传达更长时间运行命令和脚本的进度的消息。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-175">The **Progress** stream is used for messages that communicate progress in longer running commands and scripts.</span></span> <span data-ttu-id="f8f9a-176">使用 `Write-Progress` cmdlet 将消息显式写入此流。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-176">Use the `Write-Progress` cmdlet to explicitly write messages to this stream.</span></span> <span data-ttu-id="f8f9a-177">**进度** 流不支持重定向。</span><span class="sxs-lookup"><span data-stu-id="f8f9a-177">The **Progress** stream does not support redirection.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8f9a-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8f9a-178">See also</span></span>

- [<span data-ttu-id="f8f9a-179">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="f8f9a-179">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)
- [<span data-ttu-id="f8f9a-180">写入错误</span><span class="sxs-lookup"><span data-stu-id="f8f9a-180">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)
- [<span data-ttu-id="f8f9a-181">Write-Host</span><span class="sxs-lookup"><span data-stu-id="f8f9a-181">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)
- [<span data-ttu-id="f8f9a-182">Write-Information</span><span class="sxs-lookup"><span data-stu-id="f8f9a-182">Write-Information</span></span>](xref:Microsoft.PowerShell.Utility.Write-Information)
- [<span data-ttu-id="f8f9a-183">Write-Output</span><span class="sxs-lookup"><span data-stu-id="f8f9a-183">Write-Output</span></span>](xref:Microsoft.PowerShell.Utility.Write-Output)
- [<span data-ttu-id="f8f9a-184">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="f8f9a-184">Write-Progress</span></span>](xref:Microsoft.PowerShell.Utility.Write-Progress)
- [<span data-ttu-id="f8f9a-185">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="f8f9a-185">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
- [<span data-ttu-id="f8f9a-186">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="f8f9a-186">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)
- [<span data-ttu-id="f8f9a-187">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f8f9a-187">about_CommonParameters</span></span>](about_CommonParameters.md)
- [<span data-ttu-id="f8f9a-188">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="f8f9a-188">about_Redirection</span></span>](about_Redirection.md)
