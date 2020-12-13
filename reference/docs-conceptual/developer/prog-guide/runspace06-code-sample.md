---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace06 代码示例
description: RunSpace06 代码示例
ms.openlocfilehash: 627fa2be51721dd8bfdd63fabdd2e6f286d593be
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667465"
---
# <a name="runspace06-code-sample"></a><span data-ttu-id="3f500-103">RunSpace06 代码示例</span><span class="sxs-lookup"><span data-stu-id="3f500-103">RunSpace06 Code Sample</span></span>

<span data-ttu-id="3f500-104">下面是 [使用 Windows PowerShell 管理单元配置运行空间](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83)中所述的 Runspace06 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="3f500-104">Here is the source code for the Runspace06 sample described in [Configuring a Runspace Using a Windows PowerShell Snap-in](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83).</span></span>
<span data-ttu-id="3f500-105">此示例应用程序基于 Windows PowerShell 管理单元创建一个运行空间，然后使用该管理单元通过一个命令来运行管道。</span><span class="sxs-lookup"><span data-stu-id="3f500-105">This sample application creates a runspace based on a Windows PowerShell snap-in, which is then used to run a pipeline with a single command.</span></span> <span data-ttu-id="3f500-106">为此，应用程序将创建运行空间配置信息，创建运行空间，使用单个命令创建管道，然后执行管道。</span><span class="sxs-lookup"><span data-stu-id="3f500-106">To do this, the application creates the runspace configuration information, creates a runspace, creates a pipeline with a single command, and then executes the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="3f500-107">你可以使用适用于 Windows Vista 的 Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，将 c # 源文件 (runspace06.cs) 下载。</span><span class="sxs-lookup"><span data-stu-id="3f500-107">You can download the C# source file (runspace06.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3f500-108">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="3f500-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="3f500-109">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="3f500-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3f500-110">代码示例</span><span class="sxs-lookup"><span data-stu-id="3f500-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a><span data-ttu-id="3f500-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f500-111">See Also</span></span>

[<span data-ttu-id="3f500-112">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="3f500-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3f500-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3f500-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
