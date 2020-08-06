---
title: StopProc 教程 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e298c729b7ac59141638052d19b95ab77aa25cd6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786469"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="67c1d-102">StopProc 教程</span><span class="sxs-lookup"><span data-stu-id="67c1d-102">StopProc Tutorial</span></span>

<span data-ttu-id="67c1d-103">本部分提供了有关创建停止过程 cmdlet 的教程，它与 Windows PowerShell 提供的 "[停止过程](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)" cmdlet 非常类似。</span><span class="sxs-lookup"><span data-stu-id="67c1d-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="67c1d-104">本教程提供了代码段，阐释了如何实现 cmdlet 以及代码的说明。</span><span class="sxs-lookup"><span data-stu-id="67c1d-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="67c1d-105">本教程中的主题</span><span class="sxs-lookup"><span data-stu-id="67c1d-105">Topics in this Tutorial</span></span>

<span data-ttu-id="67c1d-106">本教程中的主题旨在按顺序阅读，每个主题都按照上一主题中讨论的内容来构建。</span><span class="sxs-lookup"><span data-stu-id="67c1d-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="67c1d-107">[创建修改系统的 Cmdlet](./creating-a-cmdlet-that-modifies-the-system.md)本部分介绍如何创建支持系统修改的 cmdlet，如停止计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="67c1d-107">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="67c1d-108">[向 Cmdlet 添加用户消息](./adding-user-messages-to-your-cmdlet.md)本部分介绍如何将写入用户消息、调试消息、警告消息和进度信息的功能添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="67c1d-108">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="67c1d-109">[向 Cmdlet 参数添加别名、通配符扩展和帮助](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)本部分介绍如何创建支持参数别名、帮助和通配符扩展的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="67c1d-109">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="67c1d-110">向[Cmdlet 添加参数集](./adding-parameter-sets-to-a-cmdlet.md)本部分介绍如何将参数集添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="67c1d-110">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="67c1d-111">参数集允许 cmdlet 根据用户指定的参数进行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="67c1d-111">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="67c1d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67c1d-112">See Also</span></span>

[<span data-ttu-id="67c1d-113">创建用于修改系统的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="67c1d-113">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="67c1d-114">向 Cmdlet 添加用户消息</span><span class="sxs-lookup"><span data-stu-id="67c1d-114">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="67c1d-115">向 Cmdlet 参数添加别名、通配符扩展和帮助</span><span class="sxs-lookup"><span data-stu-id="67c1d-115">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="67c1d-116">向 Cmdlet 添加参数集</span><span class="sxs-lookup"><span data-stu-id="67c1d-116">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="67c1d-117">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="67c1d-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
