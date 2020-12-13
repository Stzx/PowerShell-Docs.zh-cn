---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace07 代码示例
description: RunSpace07 代码示例
ms.openlocfilehash: 6e8c9f48a6e9c5a642ecf93bca8a85003b3cfbf8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647399"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="72d54-103">RunSpace07 代码示例</span><span class="sxs-lookup"><span data-stu-id="72d54-103">RunSpace07 Code Sample</span></span>

<span data-ttu-id="72d54-104">下面是 [创建将命令添加到管道的控制台应用程序](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)中所述的 Runspace07 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="72d54-104">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="72d54-105">此示例应用程序创建运行空间，创建管道，将两个命令添加到管道，然后执行管道。</span><span class="sxs-lookup"><span data-stu-id="72d54-105">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="72d54-106">添加到管道的命令是 `Get-Process` 和 `Measure-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72d54-106">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="72d54-107">您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件 (runspace07.cs) 下载 c # 源文件。</span><span class="sxs-lookup"><span data-stu-id="72d54-107">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="72d54-108">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="72d54-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="72d54-109">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="72d54-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="72d54-110">代码示例</span><span class="sxs-lookup"><span data-stu-id="72d54-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a><span data-ttu-id="72d54-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72d54-111">See Also</span></span>

[<span data-ttu-id="72d54-112">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="72d54-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="72d54-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="72d54-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
