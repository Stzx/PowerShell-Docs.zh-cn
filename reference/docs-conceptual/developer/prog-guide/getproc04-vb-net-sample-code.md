---
title: GetProc04 (VB.NET) 示例代码 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 63fbbb2d6bef4634bf72d4b0f9e429de9ed9deca
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771866"
---
# <a name="getproc04-vbnet-sample-code"></a><span data-ttu-id="21a23-102">GetProc04 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="21a23-102">GetProc04 (VB.NET) Sample Code</span></span>

<span data-ttu-id="21a23-103">下面的代码演示了 `Get-Process` 用于报告非终止错误的 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="21a23-103">The following code shows the implementation of a `Get-Process` cmdlet that reports nonterminating errors.</span></span> <span data-ttu-id="21a23-104">此实现将调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法来报告非终止错误。</span><span class="sxs-lookup"><span data-stu-id="21a23-104">This implementation calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method to report nonterminating errors.</span></span>

> [!NOTE]
> <span data-ttu-id="21a23-105">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件 (getprov04.cs cmdlet 下载 c # 源文件) 。</span><span class="sxs-lookup"><span data-stu-id="21a23-105">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="21a23-106">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="21a23-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="21a23-107">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="21a23-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="21a23-108">代码示例</span><span class="sxs-lookup"><span data-stu-id="21a23-108">Code Sample</span></span>

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc04#GetProc04vball](Msh_samplesgetproc04#GetProc04vball)]  -->

## <a name="see-also"></a><span data-ttu-id="21a23-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21a23-109">See Also</span></span>

[<span data-ttu-id="21a23-110">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="21a23-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="21a23-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="21a23-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
