---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace08 代码示例
description: RunSpace08 代码示例
ms.openlocfilehash: f8d08e5b6bbd98d0901abe5b05c8b9ee682b8e04
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654224"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="550f6-103">RunSpace08 代码示例</span><span class="sxs-lookup"><span data-stu-id="550f6-103">RunSpace08 Code Sample</span></span>

<span data-ttu-id="550f6-104">下面是 [创建将参数添加到命令的控制台应用程序](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)中所述的 Runspace08 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="550f6-104">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="550f6-105">此示例应用程序创建一个运行空间，创建一个管道，将两个命令添加到管道，将两个参数添加到第二个命令，然后执行管道。</span><span class="sxs-lookup"><span data-stu-id="550f6-105">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="550f6-106">添加到管道中的命令是 `Get-Process` 和 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="550f6-106">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="550f6-107">代码示例</span><span class="sxs-lookup"><span data-stu-id="550f6-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="550f6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="550f6-108">See Also</span></span>

[<span data-ttu-id="550f6-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="550f6-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
