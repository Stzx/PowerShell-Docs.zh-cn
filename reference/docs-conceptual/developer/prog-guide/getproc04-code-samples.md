---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc04 代码示例
description: GetProc04 代码示例
ms.openlocfilehash: db94eda2b3aa5fc88a3054df66f54628e1482f56
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659248"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="04be7-103">GetProc04 代码示例</span><span class="sxs-lookup"><span data-stu-id="04be7-103">GetProc04 Code Samples</span></span>

<span data-ttu-id="04be7-104">下面是 GetProc04 cmdlet 的代码示例。</span><span class="sxs-lookup"><span data-stu-id="04be7-104">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="04be7-105">这是 `Get-Process` [将非终止错误报告添加到 cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)中所述的 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="04be7-105">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="04be7-106">`Get-Process`当检索进程信息时引发无效操作异常时，此 cmdlet 将调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法。</span><span class="sxs-lookup"><span data-stu-id="04be7-106">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="04be7-107">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件，为此 Get-Proc cmdlet 下载 c # 源文件 (getprov04.cs) 。</span><span class="sxs-lookup"><span data-stu-id="04be7-107">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="04be7-108">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="04be7-108">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="04be7-109">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="04be7-109">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="04be7-110">有关完整的示例代码，请参阅以下主题。</span><span class="sxs-lookup"><span data-stu-id="04be7-110">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="04be7-111">语言</span><span class="sxs-lookup"><span data-stu-id="04be7-111">Language</span></span>|<span data-ttu-id="04be7-112">主题</span><span class="sxs-lookup"><span data-stu-id="04be7-112">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="04be7-113">C#</span><span class="sxs-lookup"><span data-stu-id="04be7-113">C#</span></span>|[<span data-ttu-id="04be7-114">GetProc04 (C#) 示例代码</span><span class="sxs-lookup"><span data-stu-id="04be7-114">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="04be7-115">VB.NET</span><span class="sxs-lookup"><span data-stu-id="04be7-115">VB.NET</span></span>|[<span data-ttu-id="04be7-116">GetProc04 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="04be7-116">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="04be7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04be7-117">See Also</span></span>

[<span data-ttu-id="04be7-118">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="04be7-118">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="04be7-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="04be7-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
