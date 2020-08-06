---
title: 错误报告概念 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- non-terminating errors [PowerShell SDK]
- errors [PowerShell SDK], described
- terminating errors [PowerShell SDK]
- errors [PowerShell SDK]
ms.openlocfilehash: ff010bbe1a87daa351ec13ed249ffc899781a8c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774501"
---
# <a name="error-reporting-concepts"></a><span data-ttu-id="1af17-102">错误报告概念</span><span class="sxs-lookup"><span data-stu-id="1af17-102">Error Reporting Concepts</span></span>

<span data-ttu-id="1af17-103">Windows PowerShell 提供了两种用于报告错误的机制：一种用于*终止错误*的机制，另一种机制用于*非终止错误*。</span><span class="sxs-lookup"><span data-stu-id="1af17-103">Windows PowerShell provides two mechanisms for reporting errors: one mechanism for *terminating errors* and another mechanism for *non-terminating errors*.</span></span> <span data-ttu-id="1af17-104">你的 cmdlet 正确报告错误，以便运行 cmdlet 的主机应用程序能够以适当的方式做出反应，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="1af17-104">It is important for your cmdlet to report errors correctly so that the host application that is running your cmdlets can react in an appropriate manner.</span></span>

<span data-ttu-id="1af17-105">当发生不是或不应允许 cmdlet 继续处理其输入对象的错误时，你的 cmdlet 应调用[Throwterminatingerror \*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)方法。</span><span class="sxs-lookup"><span data-stu-id="1af17-105">Your cmdlet should call the [System.Management.Automation.Cmdlet.Throwterminatingerror\*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) method when an error occurs that does not or should not allow the cmdlet to continue to process its input objects.</span></span> <span data-ttu-id="1af17-106">当 cmdlet 可以继续处理输入对象时，你的 cmdlet 应调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法来报告非终止错误。</span><span class="sxs-lookup"><span data-stu-id="1af17-106">Your cmdlet should call the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report non-terminating errors when the cmdlet can continue processing the input objects.</span></span> <span data-ttu-id="1af17-107">这两种方法都提供了一个错误记录，主机应用程序可以使用这些错误记录来调查错误的原因。</span><span class="sxs-lookup"><span data-stu-id="1af17-107">Both methods provide an error record that the host application can use to investigate the cause of the error.</span></span>

<span data-ttu-id="1af17-108">使用以下准则来确定错误是终止还是非终止错误。</span><span class="sxs-lookup"><span data-stu-id="1af17-108">Use the following guidelines to determine whether an error is a terminating or non-terminating error.</span></span>

- <span data-ttu-id="1af17-109">错误是终止错误，如果它阻止你的 cmdlet 继续处理当前对象，或不能成功处理任何其他输入对象，而不管它们的内容如何。</span><span class="sxs-lookup"><span data-stu-id="1af17-109">An error is a terminating error if it prevents your cmdlet from continuing to process the current object or from successfully processing any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="1af17-110">如果你不希望 cmdlet 继续处理当前对象或任何其他输入对象，而不考虑它们的内容，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="1af17-110">An error is a terminating error if you do not want your cmdlet to continue processing the current object or any further input objects, regardless of their content.</span></span>

- <span data-ttu-id="1af17-111">如果错误发生在不接受或返回对象的 cmdlet 中，或者出现在接受或仅接受一个对象的 cmdlet 中，则会出现错误。</span><span class="sxs-lookup"><span data-stu-id="1af17-111">An error is a terminating error if it occurs in a cmdlet that does not accept or return an object or if it occurs in a cmdlet that accepts or returns only one object.</span></span>

- <span data-ttu-id="1af17-112">如果你希望 cmdlet 继续处理当前对象和任何其他输入对象，则错误为非终止错误。</span><span class="sxs-lookup"><span data-stu-id="1af17-112">An error is a non-terminating error if you want your cmdlet to continue processing the current object and any further input objects.</span></span>

- <span data-ttu-id="1af17-113">如果错误是与特定输入对象或输入对象的子集相关，则该错误为非终止错误。</span><span class="sxs-lookup"><span data-stu-id="1af17-113">An error is a non-terminating error if it is related to a specific input object or subset of input objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="1af17-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1af17-114">See Also</span></span>

[<span data-ttu-id="1af17-115">Throwterminatingerror \* 的 \*</span><span class="sxs-lookup"><span data-stu-id="1af17-115">System.Management.Automation.Cmdlet.Throwterminatingerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[<span data-ttu-id="1af17-116">"WriteError"。</span><span class="sxs-lookup"><span data-stu-id="1af17-116">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="1af17-117">Windows PowerShell 错误记录</span><span class="sxs-lookup"><span data-stu-id="1af17-117">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="1af17-118">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1af17-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
