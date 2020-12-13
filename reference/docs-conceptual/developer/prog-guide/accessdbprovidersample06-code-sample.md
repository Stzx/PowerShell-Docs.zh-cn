---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample06 代码示例
description: AccessDbProviderSample06 代码示例
ms.openlocfilehash: 401aca7fab86cfbf3fa8d671eab17412dd162a88
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647491"
---
# <a name="accessdbprovidersample06-code-sample"></a><span data-ttu-id="f89c2-103">AccessDbProviderSample06 代码示例</span><span class="sxs-lookup"><span data-stu-id="f89c2-103">AccessDbProviderSample06 Code Sample</span></span>

<span data-ttu-id="f89c2-104">下面的代码演示了在 [创建 Windows Powershell 内容提供程序](./creating-a-windows-powershell-content-provider.md)中介绍的 windows powershell 内容提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="f89c2-104">The following code shows the implementation of the Windows PowerShell content provider described in [Creating a Windows PowerShell Content Provider](./creating-a-windows-powershell-content-provider.md).</span></span>
<span data-ttu-id="f89c2-105">此提供程序使用户能够操作数据存储区中的项的内容。</span><span class="sxs-lookup"><span data-stu-id="f89c2-105">This provider enables the user to manipulate the contents of the items in a data store.</span></span>

> [!NOTE]
> <span data-ttu-id="f89c2-106">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，为此提供程序 (AccessDBSampleProvider06.cs) 下载 c # 源文件。</span><span class="sxs-lookup"><span data-stu-id="f89c2-106">You can download the C# source file (AccessDBSampleProvider06.cs) for this provider by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="f89c2-107">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="f89c2-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="f89c2-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="f89c2-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span> <span data-ttu-id="f89c2-109">有关其他 Windows PowerShell 提供程序实现的详细信息，请参阅 [设计 Windows Powershell 提供程序](./designing-your-windows-powershell-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="f89c2-109">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="f89c2-110">代码示例</span><span class="sxs-lookup"><span data-stu-id="f89c2-110">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample06/AccessDBProviderSample06.cs" range="11-2399":::

## <a name="see-also"></a><span data-ttu-id="f89c2-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f89c2-111">See Also</span></span>

[<span data-ttu-id="f89c2-112">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="f89c2-112">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="f89c2-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f89c2-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
