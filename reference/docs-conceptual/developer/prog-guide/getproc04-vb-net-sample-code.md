---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc04 (VB.NET) 示例代码
description: GetProc04 (VB.NET) 示例代码
ms.openlocfilehash: c46a374ab9d77f343b5ac6f45be1711eaec6dd75
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659224"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="5e26f-103">GetProc04 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="5e26f-103">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="5e26f-104">下面的代码演示了 `Get-Process` 用于报告非终止错误的 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="5e26f-104">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="5e26f-105">此实现将调用 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) 方法来报告非终止错误。</span><span class="sxs-lookup"><span data-stu-id="5e26f-105">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="5e26f-106">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件，为此 Get-Proc cmdlet 下载 c # 源文件 (getprov04.cs) 。</span><span class="sxs-lookup"><span data-stu-id="5e26f-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="5e26f-107">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="5e26f-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="5e26f-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="5e26f-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5e26f-109">代码示例</span><span class="sxs-lookup"><span data-stu-id="5e26f-109">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="5e26f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e26f-110">See Also</span></span>

[<span data-ttu-id="5e26f-111">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="5e26f-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="5e26f-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="5e26f-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
