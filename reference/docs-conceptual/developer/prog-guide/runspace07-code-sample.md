---
title: RunSpace07 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 615bb237d26bf3a314ea7fb21e983ba2b000d105
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784701"
---
# <a name="runspace07-code-sample"></a><span data-ttu-id="f9e50-102">RunSpace07 代码示例</span><span class="sxs-lookup"><span data-stu-id="f9e50-102">RunSpace07 Code Sample</span></span>

<span data-ttu-id="f9e50-103">下面是[创建将命令添加到管道的控制台应用程序](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)中所述的 Runspace07 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="f9e50-103">Here is the source code for the Runspace07 sample described in [Creating a Console Application That Adds Commands to a Pipeline](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e).</span></span>
<span data-ttu-id="f9e50-104">此示例应用程序创建运行空间，创建管道，将两个命令添加到管道，然后执行管道。</span><span class="sxs-lookup"><span data-stu-id="f9e50-104">This sample application creates a runspace, creates a pipeline, adds two commands to the pipeline, and then executes the pipeline.</span></span> <span data-ttu-id="f9e50-105">添加到管道的命令是 `Get-Process` 和 `Measure-Object` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f9e50-105">The commands added to the pipeline are the `Get-Process` and `Measure-Object` cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="f9e50-106">您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件 (runspace07.cs) 下载 c # 源文件。</span><span class="sxs-lookup"><span data-stu-id="f9e50-106">You can download the C# source file (runspace07.cs) using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="f9e50-107">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="f9e50-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="f9e50-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="f9e50-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="f9e50-109">代码示例</span><span class="sxs-lookup"><span data-stu-id="f9e50-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs" range="11-108":::

## <a name="see-also"></a><span data-ttu-id="f9e50-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9e50-110">See Also</span></span>

[<span data-ttu-id="f9e50-111">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="f9e50-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="f9e50-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f9e50-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
