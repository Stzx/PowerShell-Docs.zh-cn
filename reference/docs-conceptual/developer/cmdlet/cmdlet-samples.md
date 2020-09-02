---
title: Cmdlet 示例 | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7a4fb91cb316bf4231df0bb4446b9a7cd54cf647
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "89235976"
---
# <a name="cmdlet-samples"></a><span data-ttu-id="2150b-102">Cmdlet 示例</span><span class="sxs-lookup"><span data-stu-id="2150b-102">Cmdlet Samples</span></span>

<span data-ttu-id="2150b-103">本部分介绍了 Windows PowerShell 2.0 SDK 中提供的示例代码。</span><span class="sxs-lookup"><span data-stu-id="2150b-103">This section describes sample code that is provided in the Windows PowerShell 2.0 SDK.</span></span> <span data-ttu-id="2150b-104">可以从本部分中的各个主题复制代码，也可以打开随 SDK 一起安装的源文件。</span><span class="sxs-lookup"><span data-stu-id="2150b-104">You can copy code from the topics in this section, or open the source files installed with the SDK.</span></span> <span data-ttu-id="2150b-105">[Windows PowerShell 2.0 软件开发工具包 (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) 提供了每个示例的自述文件、源文件和 Visual Studio 项目文件。</span><span class="sxs-lookup"><span data-stu-id="2150b-105">The [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) provides ReadMe files, source files, and Visual Studio project files for each sample.</span></span> <span data-ttu-id="2150b-106">安装 SDK 后，可以在 `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` 文件夹下找到示例。</span><span class="sxs-lookup"><span data-stu-id="2150b-106">With the SDK installed, you can find the samples under the `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` folder.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2150b-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="2150b-107">In This Section</span></span>

<span data-ttu-id="2150b-108">[GetProcessSample01 示例](./getprocesssample01-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="2150b-108">[GetProcessSample01 Sample](./getprocesssample01-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span>

<span data-ttu-id="2150b-109">[GetProcessSample02 示例](./getprocesssample02-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="2150b-109">[GetProcessSample02 Sample](./getprocesssample02-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="2150b-110">它提供了 Name 参数，可用于指定要检索的进程。</span><span class="sxs-lookup"><span data-stu-id="2150b-110">It provides a Name parameter that can be used to specify the processes to be retrieved.</span></span>

<span data-ttu-id="2150b-111">[GetProcessSample03 示例](./getprocesssample03-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="2150b-111">[GetProcessSample03 Sample](./getprocesssample03-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="2150b-112">它提供了 Name 参数，此参数可以接受管道中的对象，也可以接受属性名与参数名称相同的对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="2150b-112">It provides a Name parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span>

<span data-ttu-id="2150b-113">[GetProcessSample04 示例](./getprocesssample04-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="2150b-113">[GetProcessSample04 Sample](./getprocesssample04-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="2150b-114">如果在检索进程时发生错误，则生成一个不可终止的错误。</span><span class="sxs-lookup"><span data-stu-id="2150b-114">It generates a nonterminating error if an error occurs while retrieving a process.</span></span>

<span data-ttu-id="2150b-115">[GetProcessSample05 示例](./getprocesssample05-sample.md)：此示例展示了 Get-Proc cmdlet 的完整版本。</span><span class="sxs-lookup"><span data-stu-id="2150b-115">[GetProcessSample05 Sample](./getprocesssample05-sample.md) This sample shows a complete version of the Get-Proc cmdlet.</span></span>

<span data-ttu-id="2150b-116">[StopProcessSample01 示例](./stopprocesssample01-sample.md)：此示例展示了如何编写 cmdlet，以在尝试停止进程之前请求获取用户的反馈，以及如何实现 `PassThru` 参数来指明用户希望此 cmdlet 返回对象。</span><span class="sxs-lookup"><span data-stu-id="2150b-116">[StopProcessSample01 Sample](./stopprocesssample01-sample.md) This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object.</span></span>

<span data-ttu-id="2150b-117">[StopProcessSample02 示例](./stopprocesssample02-sample.md)：此示例展示了如何编写 cmdlet，以在本地计算机上停止进程时写入调试、详细和警告消息。</span><span class="sxs-lookup"><span data-stu-id="2150b-117">[StopProcessSample02 Sample](./stopprocesssample02-sample.md) This sample shows how to write a cmdlet that writes debug, verbose, and warning messages while stopping processes on the local computer.</span></span>

<span data-ttu-id="2150b-118">[StopProcessSample03 示例](./stopprocesssample03-sample.md)：此示例展示了如何编写其参数有别名且支持通配符的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2150b-118">[StopProcessSample03 Sample](./stopprocesssample03-sample.md) This sample shows how to write a cmdlet whose parameters have aliases and that support wildcard characters.</span></span>

<span data-ttu-id="2150b-119">[StopProcessSample04 示例](./stopprocesssample04-sample.md)：此示例展示了如何编写 cmdlet，以声明参数集、指定默认参数集并能接受输入对象。</span><span class="sxs-lookup"><span data-stu-id="2150b-119">[StopProcessSample04 Sample](./stopprocesssample04-sample.md) This sample shows how to write a cmdlet that declares parameter sets, specifies the default parameter set, and can accept an input object.</span></span>

<span data-ttu-id="2150b-120">[Events01 示例](./events01-sample.md)：此示例展示了如何创建 cmdlet，以便用户能够注册由 [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher) 引发的事件。</span><span class="sxs-lookup"><span data-stu-id="2150b-120">[Events01 Sample](./events01-sample.md) This sample shows how to create a cmdlet that allows the user to register for events raised by [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="2150b-121">例如，使用此 cmdlet，用户可以注册在特定目录下创建文件时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2150b-121">With this cmdlet users can, for example, register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="2150b-122">此示例派生自 [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基类。</span><span class="sxs-lookup"><span data-stu-id="2150b-122">This sample derives from the [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2150b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2150b-123">See Also</span></span>

[<span data-ttu-id="2150b-124">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2150b-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
