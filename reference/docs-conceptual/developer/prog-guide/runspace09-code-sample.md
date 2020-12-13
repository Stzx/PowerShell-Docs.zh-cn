---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace09 代码示例
description: RunSpace09 代码示例
ms.openlocfilehash: 52ebfa5dcfd6c12d2ded78a41a6090caa5087149
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654197"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="3d28a-103">RunSpace09 代码示例</span><span class="sxs-lookup"><span data-stu-id="3d28a-103">RunSpace09 Code Sample</span></span>

<span data-ttu-id="3d28a-104">下面是 [创建一个以异步方式调用管道的控制台应用程序](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)中所述的 Runspace09 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="3d28a-104">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="3d28a-105">此示例应用程序创建并打开运行空间，创建并异步调用管道，然后使用管道事件异步处理脚本。</span><span class="sxs-lookup"><span data-stu-id="3d28a-105">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="3d28a-106">此应用程序运行的脚本将以0.5 秒为间隔创建整数1到10， (500 ms) 。</span><span class="sxs-lookup"><span data-stu-id="3d28a-106">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="3d28a-107">代码示例</span><span class="sxs-lookup"><span data-stu-id="3d28a-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="3d28a-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d28a-108">See Also</span></span>

[<span data-ttu-id="3d28a-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3d28a-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
