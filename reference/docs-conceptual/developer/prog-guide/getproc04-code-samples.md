---
title: GetProc04 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b90b7e96c1454e57df93863b526758f25d9be690
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771951"
---
# <a name="getproc04-code-samples"></a><span data-ttu-id="935f9-102">GetProc04 代码示例</span><span class="sxs-lookup"><span data-stu-id="935f9-102">GetProc04 Code Samples</span></span>

<span data-ttu-id="935f9-103">下面是 GetProc04 cmdlet 的代码示例。</span><span class="sxs-lookup"><span data-stu-id="935f9-103">Here are the code samples for the GetProc04 sample cmdlet.</span></span> <span data-ttu-id="935f9-104">这是 `Get-Process` [将非终止错误报告添加到 cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)中所述的 cmdlet 示例。</span><span class="sxs-lookup"><span data-stu-id="935f9-104">This is the `Get-Process` cmdlet sample described in [Adding Nonterminating Error Reporting to Your Cmdlet](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md).</span></span> <span data-ttu-id="935f9-105">`Get-Process`当检索进程信息时引发无效操作异常时，此 cmdlet 将调用[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)方法。</span><span class="sxs-lookup"><span data-stu-id="935f9-105">This `Get-Process` cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method whenever an invalid operation exception is thrown while retrieving process information.</span></span>

> [!NOTE]
> <span data-ttu-id="935f9-106">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件 (getprov04.cs cmdlet 下载 c # 源文件) 。</span><span class="sxs-lookup"><span data-stu-id="935f9-106">You can download the C# source file (getprov04.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="935f9-107">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="935f9-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="935f9-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="935f9-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

<span data-ttu-id="935f9-109">有关完整的示例代码，请参阅以下主题。</span><span class="sxs-lookup"><span data-stu-id="935f9-109">For complete sample code, see the following topics.</span></span>

|<span data-ttu-id="935f9-110">语言</span><span class="sxs-lookup"><span data-stu-id="935f9-110">Language</span></span>|<span data-ttu-id="935f9-111">主题</span><span class="sxs-lookup"><span data-stu-id="935f9-111">Topic</span></span>|
|--------------|-----------|
|<span data-ttu-id="935f9-112">C#</span><span class="sxs-lookup"><span data-stu-id="935f9-112">C#</span></span>|[<span data-ttu-id="935f9-113">GetProc04 (C#) 示例代码</span><span class="sxs-lookup"><span data-stu-id="935f9-113">GetProc04 (C#) Sample Code</span></span>](./getproc04-csharp-sample-code.md)|
|<span data-ttu-id="935f9-114">VB.NET</span><span class="sxs-lookup"><span data-stu-id="935f9-114">VB.NET</span></span>|[<span data-ttu-id="935f9-115">GetProc04 (VB.NET) 示例代码</span><span class="sxs-lookup"><span data-stu-id="935f9-115">GetProc04 (VB.NET) Sample Code</span></span>](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a><span data-ttu-id="935f9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="935f9-116">See Also</span></span>

[<span data-ttu-id="935f9-117">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="935f9-117">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="935f9-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="935f9-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
