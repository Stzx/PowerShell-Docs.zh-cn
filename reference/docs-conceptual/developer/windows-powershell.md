---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell SDK
description: Windows PowerShell SDK
ms.openlocfilehash: 751ccb02741db0ea63df1768dec4a19c5fa9ce92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390195"
---
# <a name="windows-powershell"></a><span data-ttu-id="43d9d-103">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43d9d-103">Windows PowerShell</span></span>

<span data-ttu-id="43d9d-104">更新日期：2013年7月8日</span><span class="sxs-lookup"><span data-stu-id="43d9d-104">Updated: July 8, 2013</span></span>

<span data-ttu-id="43d9d-105">Windows PowerShell &reg; 是一种基于任务的命令行 shell 和脚本语言，专为系统管理而设计。</span><span class="sxs-lookup"><span data-stu-id="43d9d-105">Windows PowerShell&reg; is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="43d9d-106">Windows PowerShell 在 .NET Framework 的基础上构建， &reg; 可帮助 IT 专业人员和高级用户控制和自动执行 windows 操作系统以及在 windows 上运行的应用程序的管理。</span><span class="sxs-lookup"><span data-stu-id="43d9d-106">Built on the .NET Framework, Windows PowerShell&reg; helps IT professionals and power users control and automate the administration of the Windows operating system and applications that run on Windows.</span></span>

<span data-ttu-id="43d9d-107">此处发布的文档主要针对需要有关 Windows PowerShell 提供的 Api 的参考信息的 cmdlet、提供程序和主机应用程序开发人员编写。</span><span class="sxs-lookup"><span data-stu-id="43d9d-107">The documents published here are written primarily for cmdlet, provider, and host application developers who require reference information about the APIs provided by Windows PowerShell.</span></span>
<span data-ttu-id="43d9d-108">不过，系统管理员还可能会发现这些文档所提供的信息很有用。</span><span class="sxs-lookup"><span data-stu-id="43d9d-108">However, system administrators might also find the information provided by these documents useful.</span></span>

<span data-ttu-id="43d9d-109">有关开始使用 Windows PowerShell 所需的基本信息，请参阅使用 Windows PowerShell 入门。</span><span class="sxs-lookup"><span data-stu-id="43d9d-109">For the basic information needed to start using Windows PowerShell, see Getting Started with Windows PowerShell .</span></span>

## <a name="windows-powershell-documents"></a><span data-ttu-id="43d9d-110">Windows PowerShell 文档</span><span class="sxs-lookup"><span data-stu-id="43d9d-110">Windows PowerShell Documents</span></span>

- <span data-ttu-id="43d9d-111">[安装 Windows POWERSHELL SDK](./installing-the-windows-powershell-sdk.md) 提供有关如何安装 Windows PowerShell SDK 的信息。</span><span class="sxs-lookup"><span data-stu-id="43d9d-111">[Installing the Windows PowerShell SDK](./installing-the-windows-powershell-sdk.md) Provides information about how to install the Windows PowerShell SDK.</span></span>

- <span data-ttu-id="43d9d-112">[编写 Windows PowerShell 模块](./module/writing-a-windows-powershell-module.md) 为需要打包和分发其 Windows PowerShell 解决方案的管理员、脚本开发人员和 cmdlet 开发人员提供信息。</span><span class="sxs-lookup"><span data-stu-id="43d9d-112">[Writing a Windows PowerShell Module](./module/writing-a-windows-powershell-module.md) Provides information for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell solutions.</span></span>

- <span data-ttu-id="43d9d-113">[编写 Windows PowerShell Cmdlet](./cmdlet/writing-a-windows-powershell-cmdlet.md) 提供有关设计和实现 cmdlet 的信息。</span><span class="sxs-lookup"><span data-stu-id="43d9d-113">[Writing a Windows PowerShell Cmdlet](./cmdlet/writing-a-windows-powershell-cmdlet.md) Provides information for designing and implementing cmdlets.</span></span>

- <span data-ttu-id="43d9d-114">[编写 Windows PowerShell 提供程序](./provider/writing-a-windows-powershell-provider.md) 提供有关设计和实现 Windows PowerShell 提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="43d9d-114">[Writing a Windows PowerShell Provider](./provider/writing-a-windows-powershell-provider.md) Provides information for designing and implementing Windows PowerShell providers.</span></span> <span data-ttu-id="43d9d-115">它将帮助你了解 Windows PowerShell 提供程序的工作原理，并提供可用于开始设计或编写你自己的提供程序的示例代码。</span><span class="sxs-lookup"><span data-stu-id="43d9d-115">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

- <span data-ttu-id="43d9d-116">[编写 Windows PowerShell 主机应用程序](./hosting/writing-a-windows-powershell-host-application.md) 提供可由程序管理员使用的信息，这些程序管理器正在设计宿主应用程序，并由实现它们的开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="43d9d-116">[Writing a Windows PowerShell Host Application](./hosting/writing-a-windows-powershell-host-application.md) Provides information that can be used by program managers who are designing host applications and by developers who are implementing them.</span></span> <span data-ttu-id="43d9d-117">主机应用程序可以定义运行命令的运行空间，打开本地或远程计算机上的会话，并根据应用程序的需要以同步或异步方式调用命令。</span><span class="sxs-lookup"><span data-stu-id="43d9d-117">The host application can, define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

- <span data-ttu-id="43d9d-118">[编写 PowerShell 格式化文件](./format/writing-a-powershell-formatting-file.md) 提供有关创作格式化文件的信息，这些文件控制由 (cmdlet、函数和脚本的命令返回的对象的显示格式) 。</span><span class="sxs-lookup"><span data-stu-id="43d9d-118">[Writing a PowerShell Formatting File](./format/writing-a-powershell-formatting-file.md) Provides information for the authoring of formatting files, which control the display format for the objects that are returned by commands (cmdlets, functions, and scripts).</span></span>

- <span data-ttu-id="43d9d-119">[Windows PowerShell 参考](./windows-powershell-reference.md) 提供用于编写 cmdlet、提供程序和主机应用程序以及其他支持 Api 的 Api 的参考内容。</span><span class="sxs-lookup"><span data-stu-id="43d9d-119">[Windows PowerShell Reference](./windows-powershell-reference.md) Provides reference content for the APIs used in writing cmdlets, providers, and host applications, as well as other supporting APIs.</span></span>
