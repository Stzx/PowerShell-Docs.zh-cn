---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc 教程
description: GetProc 教程
ms.openlocfilehash: 9379e791dd5361fcf5b79061bf0a601ebeb84f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652791"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="01968-103">GetProc 教程</span><span class="sxs-lookup"><span data-stu-id="01968-103">GetProc Tutorial</span></span>

<span data-ttu-id="01968-104">本部分提供的教程介绍了如何创建 Get-Proc cmdlet，该 cmdlet 非常类似于 Windows PowerShell 提供的 [进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="01968-104">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="01968-105">本教程提供了代码段，阐释了如何实现 cmdlet 以及代码的说明。</span><span class="sxs-lookup"><span data-stu-id="01968-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="01968-106">本教程中的主题</span><span class="sxs-lookup"><span data-stu-id="01968-106">Topics in this Tutorial</span></span>

<span data-ttu-id="01968-107">本教程中的主题旨在按顺序阅读，每个主题都按照上一主题中讨论的内容来构建。</span><span class="sxs-lookup"><span data-stu-id="01968-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="01968-108">[创建不带参数的 Cmdlet](./creating-a-cmdlet-without-parameters.md) 本部分介绍如何创建一个 cmdlet，用于在不使用参数的情况下从本地计算机检索信息，然后将该信息写入管道。</span><span class="sxs-lookup"><span data-stu-id="01968-108">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="01968-109">[添加处理 Command-Line 输入的参数](./adding-parameters-that-process-command-line-input.md) 本部分介绍如何将参数添加到 Get-Proc cmdlet，以便该 cmdlet 可以基于传递到 cmdlet 的显式对象处理输入。</span><span class="sxs-lookup"><span data-stu-id="01968-109">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="01968-110">此处所述的实现根据名称检索进程，然后将该信息写入管道。</span><span class="sxs-lookup"><span data-stu-id="01968-110">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="01968-111">[添加处理管道输入的参数](./adding-parameters-that-process-pipeline-input.md) 本部分介绍如何将参数添加到 Get-Proc cmdlet，以便该 cmdlet 可以处理通过管道传递给它的对象。</span><span class="sxs-lookup"><span data-stu-id="01968-111">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="01968-112">此处所述的实现 cmdlet 检索基于传递到 cmdlet 的对象的进程，然后将该信息写入管道。</span><span class="sxs-lookup"><span data-stu-id="01968-112">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="01968-113">[将非终止错误报告添加到 Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) 本部分介绍如何将非终止错误报告添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="01968-113">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="01968-114">此处所述的实现检测在处理输入时出现的非终止错误，并将错误记录写入错误流。</span><span class="sxs-lookup"><span data-stu-id="01968-114">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="01968-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01968-115">See Also</span></span>

[<span data-ttu-id="01968-116">创建不具有参数的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="01968-116">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="01968-117">添加处理 Command-Line 输入的参数</span><span class="sxs-lookup"><span data-stu-id="01968-117">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="01968-118">添加用于处理管道输入的参数</span><span class="sxs-lookup"><span data-stu-id="01968-118">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="01968-119">将非终止错误报告添加到 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="01968-119">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="01968-120">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="01968-120">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
