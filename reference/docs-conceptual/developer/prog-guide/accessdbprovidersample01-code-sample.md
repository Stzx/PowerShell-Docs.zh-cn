---
title: AccessDbProviderSample01 代码示例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35540d2a-c18f-4179-b869-1a3dc5a8c1bd
caps.latest.revision: 6
ms.openlocfilehash: 429339a86b44bfa53302329fe1e21f6f91c52b42
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360546"
---
# <a name="accessdbprovidersample01-code-sample"></a><span data-ttu-id="b9bf9-102">AccessDbProviderSample01 代码示例</span><span class="sxs-lookup"><span data-stu-id="b9bf9-102">AccessDbProviderSample01 Code Sample</span></span>

<span data-ttu-id="b9bf9-103">下面的代码演示了在[创建基本 Windows Powershell 提供程序](./creating-a-basic-windows-powershell-provider.md)中所述的 Windows powershell 提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="b9bf9-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Basic Windows PowerShell Provider](./creating-a-basic-windows-powershell-provider.md).</span></span> <span data-ttu-id="b9bf9-104">此实现提供了启动和停止提供程序的方法，但它并不提供访问数据存储或获取或设置数据存储中数据的方法，但它提供了所有提供程序所需的基本功能。</span><span class="sxs-lookup"><span data-stu-id="b9bf9-104">This implementation provides methods for starting and stopping the provider, and although it does not provide a means to access a data store or to get or set the data in the data store, it does provide the basic functionality that is required by all providers.</span></span>

> [!NOTE]
> <span data-ttu-id="b9bf9-105">你可以使用适用C#于 windows Vista 的 Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件下载此访问接口的源文件（AccessDBSampleProvider01.cs）。</span><span class="sxs-lookup"><span data-stu-id="b9bf9-105">You can download the C# source file (AccessDBSampleProvider01.cs) for this provider by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="b9bf9-106">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="b9bf9-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/developer/installing-the-windows-powershell-sdk).</span></span>
>
> <span data-ttu-id="b9bf9-107">下载的源文件在 **\<PowerShell 示例 >** 目录中提供。</span><span class="sxs-lookup"><span data-stu-id="b9bf9-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>
>
> <span data-ttu-id="b9bf9-108">有关其他 Windows PowerShell 提供程序实现的详细信息，请参阅[设计 Windows Powershell 提供程序](./designing-your-windows-powershell-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bf9-108">For more information about other Windows PowerShell provider implementations, see [Designing Your Windows PowerShell Provider](./designing-your-windows-powershell-provider.md).</span></span>

## <a name="code-sample"></a><span data-ttu-id="b9bf9-109">代码示例</span><span class="sxs-lookup"><span data-stu-id="b9bf9-109">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample01.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs#L11-L30 "AccessDBProviderSample01.cs")]

## <a name="see-also"></a><span data-ttu-id="b9bf9-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9bf9-110">See Also</span></span>

[<span data-ttu-id="b9bf9-111">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="b9bf9-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="b9bf9-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="b9bf9-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)