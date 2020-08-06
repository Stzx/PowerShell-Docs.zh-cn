---
title: RunSpace05 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 31a73f965a6e38dceec740a2f7d4adead3e2a3f9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784735"
---
# <a name="runspace05-code-sample"></a><span data-ttu-id="3c27a-102">RunSpace05 代码示例</span><span class="sxs-lookup"><span data-stu-id="3c27a-102">RunSpace05 Code Sample</span></span>

<span data-ttu-id="3c27a-103">下面是[使用 RunspaceConfiguration 配置运行空间](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2)中所述的 Runspace05 示例的源代码。</span><span class="sxs-lookup"><span data-stu-id="3c27a-103">Here is the source code for the Runspace05 sample that is described in [Configuring a Runspace Using RunspaceConfiguration](https://msdn.microsoft.com/42681d19-2d05-4975-befd-afb1990e79b2).</span></span>
<span data-ttu-id="3c27a-104">此示例演示如何创建运行空间配置信息、创建运行空间、使用单个命令创建管道，然后执行管道。</span><span class="sxs-lookup"><span data-stu-id="3c27a-104">This sample shows how to create the runspace configuration information, create a runspace, create a pipeline with a single command, and then execute the pipeline.</span></span> <span data-ttu-id="3c27a-105">执行的命令是 `Get-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3c27a-105">The command that is executed is the `Get-Process` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3c27a-106">您可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件 (runspace05.cs) 下载 c # 源文件。</span><span class="sxs-lookup"><span data-stu-id="3c27a-106">You can download the C# source file (runspace05.cs) by using the Microsoft Windows Software Development Kit for Windows Vista and Microsoft .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="3c27a-107">有关下载说明，请参阅[如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="3c27a-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="3c27a-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="3c27a-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="3c27a-109">代码示例</span><span class="sxs-lookup"><span data-stu-id="3c27a-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs" range="11-86":::

## <a name="see-also"></a><span data-ttu-id="3c27a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c27a-110">See Also</span></span>

[<span data-ttu-id="3c27a-111">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="3c27a-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3c27a-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3c27a-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
