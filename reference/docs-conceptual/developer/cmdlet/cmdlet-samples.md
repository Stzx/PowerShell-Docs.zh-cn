---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 示例
description: Cmdlet 示例
ms.openlocfilehash: 6ee149f611e5af5c45a62363e19e66bf200c0c0a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668246"
---
# <a name="cmdlet-samples"></a><span data-ttu-id="bf775-103">Cmdlet 示例</span><span class="sxs-lookup"><span data-stu-id="bf775-103">Cmdlet Samples</span></span>

<span data-ttu-id="bf775-104">本部分介绍了 Windows PowerShell 2.0 SDK 中提供的示例代码。</span><span class="sxs-lookup"><span data-stu-id="bf775-104">This section describes sample code that is provided in the Windows PowerShell 2.0 SDK.</span></span> <span data-ttu-id="bf775-105">可以从本部分中的各个主题复制代码，也可以打开随 SDK 一起安装的源文件。</span><span class="sxs-lookup"><span data-stu-id="bf775-105">You can copy code from the topics in this section, or open the source files installed with the SDK.</span></span> <span data-ttu-id="bf775-106">[Windows PowerShell 2.0 软件开发工具包 (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) 提供了每个示例的自述文件、源文件和 Visual Studio 项目文件。</span><span class="sxs-lookup"><span data-stu-id="bf775-106">The [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) provides ReadMe files, source files, and Visual Studio project files for each sample.</span></span> <span data-ttu-id="bf775-107">安装 SDK 后，可以在 `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` 文件夹下找到示例。</span><span class="sxs-lookup"><span data-stu-id="bf775-107">With the SDK installed, you can find the samples under the `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` folder.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bf775-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="bf775-108">In This Section</span></span>

<span data-ttu-id="bf775-109">[GetProcessSample01 示例](./getprocesssample01-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="bf775-109">[GetProcessSample01 Sample](./getprocesssample01-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span>

<span data-ttu-id="bf775-110">[GetProcessSample02 示例](./getprocesssample02-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="bf775-110">[GetProcessSample02 Sample](./getprocesssample02-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="bf775-111">它提供了 Name 参数，可用于指定要检索的进程。</span><span class="sxs-lookup"><span data-stu-id="bf775-111">It provides a Name parameter that can be used to specify the processes to be retrieved.</span></span>

<span data-ttu-id="bf775-112">[GetProcessSample03 示例](./getprocesssample03-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="bf775-112">[GetProcessSample03 Sample](./getprocesssample03-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="bf775-113">它提供了 Name 参数，此参数可以接受管道中的对象，也可以接受属性名与参数名称相同的对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="bf775-113">It provides a Name parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span>

<span data-ttu-id="bf775-114">[GetProcessSample04 示例](./getprocesssample04-sample.md)：此示例展示了如何编写 cmdlet 来检索本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="bf775-114">[GetProcessSample04 Sample](./getprocesssample04-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="bf775-115">如果在检索进程时发生错误，则生成一个不可终止的错误。</span><span class="sxs-lookup"><span data-stu-id="bf775-115">It generates a nonterminating error if an error occurs while retrieving a process.</span></span>

<span data-ttu-id="bf775-116">[GetProcessSample05 示例](./getprocesssample05-sample.md)：此示例展示了 Get-Proc cmdlet 的完整版本。</span><span class="sxs-lookup"><span data-stu-id="bf775-116">[GetProcessSample05 Sample](./getprocesssample05-sample.md) This sample shows a complete version of the Get-Proc cmdlet.</span></span>

<span data-ttu-id="bf775-117">[StopProcessSample01 示例](./stopprocesssample01-sample.md)：此示例展示了如何编写 cmdlet，以在尝试停止进程之前请求获取用户的反馈，以及如何实现 `PassThru` 参数来指明用户希望此 cmdlet 返回对象。</span><span class="sxs-lookup"><span data-stu-id="bf775-117">[StopProcessSample01 Sample](./stopprocesssample01-sample.md) This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object.</span></span>

<span data-ttu-id="bf775-118">[StopProcessSample02 示例](./stopprocesssample02-sample.md)：此示例展示了如何编写 cmdlet，以在本地计算机上停止进程时写入调试、详细和警告消息。</span><span class="sxs-lookup"><span data-stu-id="bf775-118">[StopProcessSample02 Sample](./stopprocesssample02-sample.md) This sample shows how to write a cmdlet that writes debug, verbose, and warning messages while stopping processes on the local computer.</span></span>

<span data-ttu-id="bf775-119">[StopProcessSample03 示例](./stopprocesssample03-sample.md)：此示例展示了如何编写其参数有别名且支持通配符的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bf775-119">[StopProcessSample03 Sample](./stopprocesssample03-sample.md) This sample shows how to write a cmdlet whose parameters have aliases and that support wildcard characters.</span></span>

<span data-ttu-id="bf775-120">[StopProcessSample04 示例](./stopprocesssample04-sample.md)：此示例展示了如何编写 cmdlet，以声明参数集、指定默认参数集并能接受输入对象。</span><span class="sxs-lookup"><span data-stu-id="bf775-120">[StopProcessSample04 Sample](./stopprocesssample04-sample.md) This sample shows how to write a cmdlet that declares parameter sets, specifies the default parameter set, and can accept an input object.</span></span>

<span data-ttu-id="bf775-121">[Events01 示例](./events01-sample.md)：此示例展示了如何创建 cmdlet，以便用户能够注册由 [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher) 引发的事件。</span><span class="sxs-lookup"><span data-stu-id="bf775-121">[Events01 Sample](./events01-sample.md) This sample shows how to create a cmdlet that allows the user to register for events raised by [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="bf775-122">例如，使用此 cmdlet，用户可以注册在特定目录下创建文件时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="bf775-122">With this cmdlet users can, for example, register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="bf775-123">此示例派生自 [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基类。</span><span class="sxs-lookup"><span data-stu-id="bf775-123">This sample derives from the [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf775-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf775-124">See Also</span></span>

[<span data-ttu-id="bf775-125">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bf775-125">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
