---
ms.date: 09/13/2016
ms.topic: reference
title: 非终止错误
description: 非终止错误
ms.openlocfilehash: d23642103e005c6d3a6168b317b11f40001b6bbe
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655740"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="3cd24-103">非终止错误</span><span class="sxs-lookup"><span data-stu-id="3cd24-103">Non-Terminating Errors</span></span>

<span data-ttu-id="3cd24-104">本主题讨论用于报告非终止错误的方法。</span><span class="sxs-lookup"><span data-stu-id="3cd24-104">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="3cd24-105">还介绍了如何从 cmdlet 内调用方法。</span><span class="sxs-lookup"><span data-stu-id="3cd24-105">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="3cd24-106">当发生非终止错误时，此 cmdlet 应通过调用 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 方法报告此错误。</span><span class="sxs-lookup"><span data-stu-id="3cd24-106">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="3cd24-107">当 cmdlet 报告非终止错误时，该 cmdlet 可以继续对该输入对象和其他传入管道对象执行操作。</span><span class="sxs-lookup"><span data-stu-id="3cd24-107">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="3cd24-108">如果该 cmdlet 调用 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 方法，则该 cmdlet 可以编写一个错误记录，用于描述导致非终止错误的情况。</span><span class="sxs-lookup"><span data-stu-id="3cd24-108">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="3cd24-109">有关错误记录的详细信息，请参阅 [Windows PowerShell 错误记录](./windows-powershell-error-records.md)。</span><span class="sxs-lookup"><span data-stu-id="3cd24-109">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="3cd24-110">Cmdlet 可以根据需要从其输入处理方法中调用 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 。</span><span class="sxs-lookup"><span data-stu-id="3cd24-110">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="3cd24-111">但是，cmdlet 只能从名为 BeginProcessing、ProcessRecord[或](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)输入处理方法的线程调用[](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)（可能为一个类型为[](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)的方法）的类型的调用程序中的方法的调用程序。</span><span class="sxs-lookup"><span data-stu-id="3cd24-111">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="3cd24-112">不要从另一个线程调用 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) ，则为。</span><span class="sxs-lookup"><span data-stu-id="3cd24-112">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="3cd24-113">而是将错误传递回主线程。</span><span class="sxs-lookup"><span data-stu-id="3cd24-113">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cd24-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cd24-114">See Also</span></span>

[<span data-ttu-id="3cd24-115">"WriteError"。</span><span class="sxs-lookup"><span data-stu-id="3cd24-115">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="3cd24-116">"BeginProcessing"。</span><span class="sxs-lookup"><span data-stu-id="3cd24-116">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="3cd24-117">"ProcessRecord"。</span><span class="sxs-lookup"><span data-stu-id="3cd24-117">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="3cd24-118">System.web. EndProcessing. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="3cd24-118">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="3cd24-119">Windows PowerShell 错误记录</span><span class="sxs-lookup"><span data-stu-id="3cd24-119">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="3cd24-120">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3cd24-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
