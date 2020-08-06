---
title: RunSpace08 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 67172a0f8d6daf2f5b9965d1a18f7698daddbe1a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784684"
---
# <a name="runspace08-code-sample"></a><span data-ttu-id="77ade-102">RunSpace08 代码示例</span><span class="sxs-lookup"><span data-stu-id="77ade-102">RunSpace08 Code Sample</span></span>

<span data-ttu-id="77ade-103">下面是[创建将参数添加到命令的控制台应用程序](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba)中所述的 Runspace08 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="77ade-103">Here is the source code for the Runspace08 sample described in [Creating a Console Application That Adds Parameters to a Command](https://msdn.microsoft.com/848b2b46-60f1-4a86-b448-cfc7c0cccfba).</span></span>
<span data-ttu-id="77ade-104">此示例应用程序创建一个运行空间，创建一个管道，将两个命令添加到管道，将两个参数添加到第二个命令，然后执行管道。</span><span class="sxs-lookup"><span data-stu-id="77ade-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, adds two parameters to the second command, and then executes the pipeline.</span></span> <span data-ttu-id="77ade-105">添加到管道中的命令是 `Get-Process` 和 `Sort-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77ade-105">The commands that are added to the pipeline are the `Get-Process` and `Sort-Object` cmdlets.</span></span>

## <a name="code-sample"></a><span data-ttu-id="77ade-106">代码示例</span><span class="sxs-lookup"><span data-stu-id="77ade-106">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace08/Runspace08.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="77ade-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77ade-107">See Also</span></span>

[<span data-ttu-id="77ade-108">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="77ade-108">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
