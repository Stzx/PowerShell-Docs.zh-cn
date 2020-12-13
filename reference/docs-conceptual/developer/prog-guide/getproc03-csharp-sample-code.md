---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc03 (C#) 示例代码
description: GetProc03 (C#) 示例代码
ms.openlocfilehash: c81ba04b2b335f4ce992c6b3ed2f019cf6d7d20f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355572"
---
# <a name="getproc03-c-sample-code"></a><span data-ttu-id="5f69d-103">GetProc03 (C#) 示例代码</span><span class="sxs-lookup"><span data-stu-id="5f69d-103">GetProc03 (C#) Sample Code</span></span>

<span data-ttu-id="5f69d-104">下面的代码演示了 `Get-Process` 可以接受流水线输入的 cmdlet 的实现。</span><span class="sxs-lookup"><span data-stu-id="5f69d-104">The following code shows the implementation of a `Get-Process` cmdlet that can accept pipelined input.</span></span> <span data-ttu-id="5f69d-105">此实现定义了一个 `Name` 参数，该参数接受管道输入，并根据提供的名称从本地计算机检索进程信息，然后使用 [WriteObject (system.object) ](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 方法作为将对象发送到管道的输出机制。</span><span class="sxs-lookup"><span data-stu-id="5f69d-105">This implementation defines a `Name` parameter that accepts pipeline input, retrieves process information from the local computer based on the supplied names, and then uses the [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) method as the output mechanism for sending objects to the pipeline.</span></span>

> [!NOTE]
> <span data-ttu-id="5f69d-106">你可以使用适用于 Windows Vista 的 Microsoft Windows 软件开发工具包和 .NET Framework 3.0 运行时组件，为此 Get-Proc cmdlet 下载 c # 源文件 (getprov03.cs) 。</span><span class="sxs-lookup"><span data-stu-id="5f69d-106">You can download the C# source file (getprov03.cs) for this Get-Proc cmdlet using the Microsoft Windows Software Development Kit for Windows Vista and .NET Framework 3.0 Runtime Components.</span></span> <span data-ttu-id="5f69d-107">有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。</span><span class="sxs-lookup"><span data-stu-id="5f69d-107">For download instructions, see [How to Install Windows PowerShell and Download the Windows PowerShell SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk).</span></span>
> <span data-ttu-id="5f69d-108">下载的源文件在目录中提供 **\<PowerShell Samples>** 。</span><span class="sxs-lookup"><span data-stu-id="5f69d-108">The downloaded source files are available in the **\<PowerShell Samples>** directory.</span></span>

## <a name="code-sample"></a><span data-ttu-id="5f69d-109">代码示例</span><span class="sxs-lookup"><span data-stu-id="5f69d-109">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="11-78":::

## <a name="see-also"></a><span data-ttu-id="5f69d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f69d-110">See Also</span></span>

[<span data-ttu-id="5f69d-111">Windows PowerShell 程序员指南</span><span class="sxs-lookup"><span data-stu-id="5f69d-111">Windows PowerShell Programmer's Guide</span></span>](./windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="5f69d-112">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="5f69d-112">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
