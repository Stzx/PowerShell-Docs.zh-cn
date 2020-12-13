---
ms.date: 09/13/2016
ms.topic: reference
title: RunSpace03 (C#) 代码示例
description: RunSpace03 (C#) 代码示例
ms.openlocfilehash: cdb08811de13f8bbf5cd91fcbef552c78594b788
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653844"
---
# <a name="runspace03-c-code-sample"></a><span data-ttu-id="cc2b5-103">RunSpace03 (C#) 代码示例</span><span class="sxs-lookup"><span data-stu-id="cc2b5-103">RunSpace03 (C#) Code Sample</span></span>

<span data-ttu-id="cc2b5-104">下面是 "创建运行指定脚本的控制台应用程序" 中所述的控制台应用程序的 c # 源代码。</span><span class="sxs-lookup"><span data-stu-id="cc2b5-104">Here is the C# source code for the console application described in "Creating a Console Application That Runs a Specified Script".</span></span> <span data-ttu-id="cc2b5-105">此示例使用 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) 类来执行一个脚本，该脚本通过使用传递到脚本的进程名称列表来检索进程信息。</span><span class="sxs-lookup"><span data-stu-id="cc2b5-105">This sample uses the [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke) class to execute a script that retrieves process information by using the list of process names passed into the script.</span></span> <span data-ttu-id="cc2b5-106">它演示如何将输入对象传递给脚本，以及如何检索错误对象以及输出对象。</span><span class="sxs-lookup"><span data-stu-id="cc2b5-106">It shows how to pass input objects to a script and how to retrieve error objects as well as the output objects.</span></span>

> [!NOTE]
> <span data-ttu-id="cc2b5-107">您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，下载此示例的 c # 源文件 (runspace03.cs) 。</span><span class="sxs-lookup"><span data-stu-id="cc2b5-107">You can download the C# source file (runspace03.cs) for this sample using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="cc2b5-108">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="cc2b5-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="cc2b5-109">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="cc2b5-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="cc2b5-110">代码示例</span><span class="sxs-lookup"><span data-stu-id="cc2b5-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs" range="11-88":::

## <a name="see-also"></a><span data-ttu-id="cc2b5-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc2b5-111">See Also</span></span>

[<span data-ttu-id="cc2b5-112">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="cc2b5-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="cc2b5-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cc2b5-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
