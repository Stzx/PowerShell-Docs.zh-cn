---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc01 (VB.NET) 示例代码
description: GetProc01 (VB.NET) 示例代码
ms.openlocfilehash: c042b926615e4c88004d50841f25795ceec9aa2d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654469"
---
# <a name="getproc01-vbnet-sample-code"></a><span data-ttu-id="017cf-103">GetProc01 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="017cf-103">GetProc01 (VB.NET) Sample Code</span></span>

<span data-ttu-id="017cf-104">下面的代码演示 GetProc01 示例 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="017cf-104">The following code shows the implementation of the GetProc01 sample cmdlet.</span></span> <span data-ttu-id="017cf-105">请注意，通过将进程检索的实际工作保留给 [Getprocesses \*](/dotnet/api/System.Diagnostics.Process.GetProcesses) 方法，可简化 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="017cf-105">Notice that the cmdlet is simplified by leaving the actual work of process retrieval to the [System.Diagnostics.Process.Getprocesses\*](/dotnet/api/System.Diagnostics.Process.GetProcesses) method.</span></span>

> [!NOTE]
> <span data-ttu-id="017cf-106">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件，为此 Get-Proc cmdlet 下载 c # 源文件 (getproc01.cs) 。</span><span class="sxs-lookup"><span data-stu-id="017cf-106">You can download the C# source file (getproc01.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="017cf-107">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="017cf-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="017cf-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="017cf-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="017cf-109">代码示例</span><span class="sxs-lookup"><span data-stu-id="017cf-109">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [msh_samplesgetproc01#getproc01vball](msh_samplesgetproc01#getproc01vball)]  -->

## <a name="see-also"></a><span data-ttu-id="017cf-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="017cf-110">See Also</span></span>

[<span data-ttu-id="017cf-111">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="017cf-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="017cf-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="017cf-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
