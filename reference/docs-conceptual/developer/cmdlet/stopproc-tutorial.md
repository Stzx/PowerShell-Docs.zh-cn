---
ms.date: 09/13/2016
ms.topic: reference
title: StopProc 教程
description: StopProc 教程
ms.openlocfilehash: 95229ee3c4905d295bd6991fe8ccf8c9840c3cdd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646417"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="cca4a-103">StopProc 教程</span><span class="sxs-lookup"><span data-stu-id="cca4a-103">StopProc Tutorial</span></span>

<span data-ttu-id="cca4a-104">本部分提供了创建 Stop-Proc cmdlet 的教程，该 cmdlet 非常类似于 Windows PowerShell 提供的 " [停止进程](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) " cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cca4a-104">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="cca4a-105">本教程提供了代码段，阐释了如何实现 cmdlet 以及代码的说明。</span><span class="sxs-lookup"><span data-stu-id="cca4a-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="cca4a-106">本教程中的主题</span><span class="sxs-lookup"><span data-stu-id="cca4a-106">Topics in this Tutorial</span></span>

<span data-ttu-id="cca4a-107">本教程中的主题旨在按顺序阅读，每个主题都按照上一主题中讨论的内容来构建。</span><span class="sxs-lookup"><span data-stu-id="cca4a-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="cca4a-108">[创建修改系统的 Cmdlet](./creating-a-cmdlet-that-modifies-the-system.md) 本部分介绍如何创建支持系统修改的 cmdlet，如停止计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="cca4a-108">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="cca4a-109">[向 Cmdlet 添加用户消息](./adding-user-messages-to-your-cmdlet.md) 本部分介绍如何将写入用户消息、调试消息、警告消息和进度信息的功能添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cca4a-109">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="cca4a-110">[向 Cmdlet 参数添加别名、通配符扩展和帮助](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) 本部分介绍如何创建支持参数别名、帮助和通配符扩展的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cca4a-110">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="cca4a-111">向[Cmdlet 添加参数集](./adding-parameter-sets-to-a-cmdlet.md)本部分介绍如何将参数集添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cca4a-111">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="cca4a-112">参数集允许 cmdlet 根据用户指定的参数进行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="cca4a-112">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="cca4a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cca4a-113">See Also</span></span>

[<span data-ttu-id="cca4a-114">创建用于修改系统的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cca4a-114">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="cca4a-115">向 Cmdlet 添加用户消息</span><span class="sxs-lookup"><span data-stu-id="cca4a-115">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="cca4a-116">向 Cmdlet 参数添加别名、通配符扩展和帮助</span><span class="sxs-lookup"><span data-stu-id="cca4a-116">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="cca4a-117">向 Cmdlet 添加参数集</span><span class="sxs-lookup"><span data-stu-id="cca4a-117">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="cca4a-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cca4a-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
