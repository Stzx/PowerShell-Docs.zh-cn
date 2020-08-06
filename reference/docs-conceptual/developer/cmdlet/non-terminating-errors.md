---
title: 非终止错误 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d74c248e6ef54151400b8060d76524e89d87352c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786554"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="dc484-102">非终止错误</span><span class="sxs-lookup"><span data-stu-id="dc484-102">Non-Terminating Errors</span></span>

<span data-ttu-id="dc484-103">本主题讨论用于报告非终止错误的方法。</span><span class="sxs-lookup"><span data-stu-id="dc484-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="dc484-104">还介绍了如何从 cmdlet 内调用方法。</span><span class="sxs-lookup"><span data-stu-id="dc484-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="dc484-105">当发生非终止错误时，此 cmdlet 应通过调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法报告此错误。</span><span class="sxs-lookup"><span data-stu-id="dc484-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="dc484-106">当 cmdlet 报告非终止错误时，该 cmdlet 可以继续对该输入对象和其他传入管道对象执行操作。</span><span class="sxs-lookup"><span data-stu-id="dc484-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="dc484-107">如果该 cmdlet 调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法，则该 cmdlet 可以编写一个错误记录，用于描述导致非终止错误的情况。</span><span class="sxs-lookup"><span data-stu-id="dc484-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="dc484-108">有关错误记录的详细信息，请参阅[Windows PowerShell 错误记录](./windows-powershell-error-records.md)。</span><span class="sxs-lookup"><span data-stu-id="dc484-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="dc484-109">Cmdlet 可以根据需要从其输入处理方法中调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 。</span><span class="sxs-lookup"><span data-stu-id="dc484-109">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="dc484-110">但是，cmdlet 只能从名为 BeginProcessing、ProcessRecord[或](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)输入处理方法的线程调用[System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)（可能为一个类型为[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)的方法）的类型的调用程序中的方法的调用程序。</span><span class="sxs-lookup"><span data-stu-id="dc484-110">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="dc484-111">不要从另一个线程调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) ，则为。</span><span class="sxs-lookup"><span data-stu-id="dc484-111">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="dc484-112">而是将错误传递回主线程。</span><span class="sxs-lookup"><span data-stu-id="dc484-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc484-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc484-113">See Also</span></span>

[<span data-ttu-id="dc484-114">"WriteError"。</span><span class="sxs-lookup"><span data-stu-id="dc484-114">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="dc484-115">"BeginProcessing"。</span><span class="sxs-lookup"><span data-stu-id="dc484-115">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="dc484-116">"ProcessRecord"。</span><span class="sxs-lookup"><span data-stu-id="dc484-116">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="dc484-117">System.web. EndProcessing. EndProcessing</span><span class="sxs-lookup"><span data-stu-id="dc484-117">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="dc484-118">Windows PowerShell 错误记录</span><span class="sxs-lookup"><span data-stu-id="dc484-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="dc484-119">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc484-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
