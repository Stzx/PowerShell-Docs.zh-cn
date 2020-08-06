---
title: RunSpace10 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 976df6c36a5f95d17a76dcd31d287a3f064eff24
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784650"
---
# <a name="runspace10-code-sample"></a><span data-ttu-id="7b1c4-102">RunSpace10 代码示例</span><span class="sxs-lookup"><span data-stu-id="7b1c4-102">RunSpace10 Code Sample</span></span>

<span data-ttu-id="7b1c4-103">下面是 Runspace10 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-103">Here is the source code for the Runspace10 sample.</span></span> <span data-ttu-id="7b1c4-104">此示例应用程序将 cmdlet 添加到[Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) ，然后使用修改后的配置信息来创建运行空间。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-104">This sample application adds a cmdlet to [System.Management.Automation.Runspaces.Runspaceconfiguration](/dotnet/api/System.Management.Automation.Runspaces.RunspaceConfiguration) and then uses the modified configuration information to create the runspace.</span></span>

> [!NOTE]
> <span data-ttu-id="7b1c4-105">你可以使用适用于 Windows Vista 的 Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，将 c # 源文件 (runspace10.cs) 下载。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-105">You can download the C# source file (runspace10.cs) by using the Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="7b1c4-106">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-106">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="7b1c4-107">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="7b1c4-107">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="7b1c4-108">代码示例</span><span class="sxs-lookup"><span data-stu-id="7b1c4-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace10/Runspace10.cs" range="11-118":::

## <a name="see-also"></a><span data-ttu-id="7b1c4-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b1c4-109">See Also</span></span>

[<span data-ttu-id="7b1c4-110">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="7b1c4-110">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="7b1c4-111">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="7b1c4-111">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
