---
title: Runspace01 （C#）代码示例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: 0978880a4294edb96fc6edb00f420cd0a9ad197b
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80977975"
---
# <a name="runspace01-c-code-sample"></a><span data-ttu-id="e7389-102">Runspace01 (C#) 代码示例</span><span class="sxs-lookup"><span data-stu-id="e7389-102">Runspace01 (C#) Code Sample</span></span>

<span data-ttu-id="e7389-103">下面是[创建运行指定命令的控制台应用程序](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)中所述的运行空间的代码示例。</span><span class="sxs-lookup"><span data-stu-id="e7389-103">Here are the code samples for the runspace described in [Creating a Console Application That Runs a Specified Command](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program).</span></span>
<span data-ttu-id="e7389-104">为此，应用程序将调用运行空间，然后调用命令。</span><span class="sxs-lookup"><span data-stu-id="e7389-104">To do this, the application invokes a runspace, and then invokes a command.</span></span> <span data-ttu-id="e7389-105">（请注意，此应用程序不会指定运行空间配置信息，也不会显式创建管道）。</span><span class="sxs-lookup"><span data-stu-id="e7389-105">(Note that this application does not specify runspace configuration information, nor does it explicitly create a pipeline).</span></span> <span data-ttu-id="e7389-106">调用的命令是 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e7389-106">The command that is invoked is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="e7389-107">你可以使用适用C#于 windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件下载此运行空间的源文件（runspace01.cs）。</span><span class="sxs-lookup"><span data-stu-id="e7389-107">You can download the C# source file (runspace01.cs) for this runspace using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span>
> <span data-ttu-id="e7389-108">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="e7389-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="e7389-109">下载的源文件在 **\<PowerShell 示例 >** 目录中提供。</span><span class="sxs-lookup"><span data-stu-id="e7389-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e7389-110">代码示例</span><span class="sxs-lookup"><span data-stu-id="e7389-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a><span data-ttu-id="e7389-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7389-111">See Also</span></span>

[<span data-ttu-id="e7389-112">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="e7389-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="e7389-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e7389-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
