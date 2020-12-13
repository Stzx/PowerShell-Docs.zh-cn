---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace01 (C#) 代码示例
description: Runspace01 (C#) 代码示例
ms.openlocfilehash: e6121c144e1a4c1a1d9460d01119f44ee5835821
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657152"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="51bcf-103">Runspace01 (C#) 代码示例</span><span class="sxs-lookup"><span data-stu-id="51bcf-103">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="51bcf-104">下面是 [创建运行指定命令的控制台应用程序](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)中所述的运行空间的代码示例。</span><span class="sxs-lookup"><span data-stu-id="51bcf-104">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="51bcf-105">为此，应用程序将调用运行空间，然后调用命令。</span><span class="sxs-lookup"><span data-stu-id="51bcf-105">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="51bcf-106"> (请注意，此应用程序不指定运行空间配置信息，也不会) 显式创建管道。</span><span class="sxs-lookup"><span data-stu-id="51bcf-106">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="51bcf-107">调用的命令是 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51bcf-107">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="51bcf-108">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，为此运行空间下载 c # 源文件 (runspace01.cs) 。</span><span class="sxs-lookup"><span data-stu-id="51bcf-108">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="51bcf-109">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="51bcf-109">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="51bcf-110">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="51bcf-110">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="51bcf-111">代码示例</span><span class="sxs-lookup"><span data-stu-id="51bcf-111">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="51bcf-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51bcf-112">See Also</span></span>

[<span data-ttu-id="51bcf-113">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="51bcf-113">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="51bcf-114">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="51bcf-114">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
