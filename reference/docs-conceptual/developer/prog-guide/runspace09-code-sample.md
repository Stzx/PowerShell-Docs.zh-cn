---
title: RunSpace09 代码示例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 136e451f-767b-42e0-bd6f-6486693abd5e
caps.latest.revision: 6
ms.openlocfilehash: d7fa39485eea833483682c91c96417a76e5d770f
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977533"
---
# <a name="runspace09-code-sample"></a><span data-ttu-id="c6b79-102">RunSpace09 代码示例</span><span class="sxs-lookup"><span data-stu-id="c6b79-102">RunSpace09 Code Sample</span></span>

<span data-ttu-id="c6b79-103">下面是[创建一个以异步方式调用管道的控制台应用程序](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47)中所述的 Runspace09 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="c6b79-103">Here is the source code for the Runspace09 sample described in [Creating a Console Application That Invokes a Pipeline Asynchronously](https://msdn.microsoft.com/198c1c94-2a06-457e-93ce-c0d910618e47).</span></span>
<span data-ttu-id="c6b79-104">此示例应用程序创建并打开运行空间，创建并异步调用管道，然后使用管道事件异步处理脚本。</span><span class="sxs-lookup"><span data-stu-id="c6b79-104">This sample application creates and opens a runspace, creates and asynchronously invokes a pipeline, and then uses pipeline events to process the script asynchronously.</span></span> <span data-ttu-id="c6b79-105">此应用程序运行的脚本将以0.5 秒为间隔创建整数1到10（500毫秒）。</span><span class="sxs-lookup"><span data-stu-id="c6b79-105">The script that is run by this application creates the integers 1 through 10 in 0.5-second intervals (500 ms).</span></span>

## <a name="code-sample"></a><span data-ttu-id="c6b79-106">代码示例</span><span class="sxs-lookup"><span data-stu-id="c6b79-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace09/Runspace09.cs" range="11-113":::

## <a name="see-also"></a><span data-ttu-id="c6b79-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6b79-107">See Also</span></span>

[<span data-ttu-id="c6b79-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="c6b79-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
