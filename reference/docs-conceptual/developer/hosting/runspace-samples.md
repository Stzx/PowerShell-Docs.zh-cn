---
title: 运行空间示例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c92a6d3d-8d34-4a76-bdc3-dea923d9858e
caps.latest.revision: 17
ms.openlocfilehash: e24d40746da91f60aaf2af655ddcadc88ab6a4db
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360996"
---
# <a name="runspace-samples"></a><span data-ttu-id="f8203-102">运行空间示例</span><span class="sxs-lookup"><span data-stu-id="f8203-102">Runspace Samples</span></span>

<span data-ttu-id="f8203-103">本部分包含的示例代码演示如何使用不同类型的运行空间以同步和异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="f8203-103">This section includes sample code that shows how to use different types of runspaces to run commands synchronously and asynchronously.</span></span> <span data-ttu-id="f8203-104">你可以使用 Microsoft Visual Studio 来创建控制台应用程序，然后将此部分中的主题中的代码复制到主机应用程序中。</span><span class="sxs-lookup"><span data-stu-id="f8203-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f8203-105">本部分内容</span><span class="sxs-lookup"><span data-stu-id="f8203-105">In This Section</span></span>

> [!NOTE]
> <span data-ttu-id="f8203-106">有关创建自定义宿主接口的主机应用程序的示例，请参阅[自定义主机示例](./custom-host-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="f8203-106">For samples of host applications that create custom host interfaces, see [Custom Host Samples](./custom-host-samples.md).</span></span>

 <span data-ttu-id="f8203-107">[Runspace01 示例](./runspace01-sample.md)此示例演示如何使用[system.exception 类同步](/dotnet/api/system.management.automation.powershell)运行[获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)cmdlet，并在控制台窗口中显示其输出。</span><span class="sxs-lookup"><span data-stu-id="f8203-107">[Runspace01 Sample](./runspace01-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously and display its output in a console window.</span></span>

 <span data-ttu-id="f8203-108">[Runspace02 示例](./runspace02-sample.md)此示例演示如何使用[system.exception 类来](/dotnet/api/system.management.automation.powershell)同步运行[获取进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process)和[排序对象](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object)的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8203-108">[Runspace02 Sample](./runspace02-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span> <span data-ttu-id="f8203-109">这些命令的结果使用 " [system.web](/dotnet/api/System.Windows.Forms.DataGridView) " 控件显示。</span><span class="sxs-lookup"><span data-stu-id="f8203-109">The results of these commands is displayed by using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

 <span data-ttu-id="f8203-110">[Runspace03 示例](./runspace03-sample.md)此示例演示如何使用[system.web](/dotnet/api/system.management.automation.powershell)类来同步运行脚本，以及如何处理非终止错误的操作。</span><span class="sxs-lookup"><span data-stu-id="f8203-110">[Runspace03 Sample](./runspace03-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span> <span data-ttu-id="f8203-111">该脚本可接收一系列进程名称，然后检索这些进程。</span><span class="sxs-lookup"><span data-stu-id="f8203-111">The script receives a list of process names and then retrieves those processes.</span></span> <span data-ttu-id="f8203-112">脚本的结果（包括运行脚本时生成的非终止错误）显示在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="f8203-112">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

 <span data-ttu-id="f8203-113">[Runspace04 示例](./runspace04-sample.md)此示例演示如何使用[system.web](/dotnet/api/system.management.automation.powershell)类来运行命令，以及如何捕获运行命令时引发的终止错误。</span><span class="sxs-lookup"><span data-stu-id="f8203-113">[Runspace04 Sample](./runspace04-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="f8203-114">运行了两个命令，最后一个命令传递给了一个无效的参数。</span><span class="sxs-lookup"><span data-stu-id="f8203-114">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="f8203-115">因此，将不返回任何对象，并引发终止错误。</span><span class="sxs-lookup"><span data-stu-id="f8203-115">As a result no objects are returned and a terminating error is thrown.</span></span>

 <span data-ttu-id="f8203-116">[Runspace05 示例](./runspace05-sample.md)此示例演示如何将管理单元添加到[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象，以便打开运行空间时，管理单元的 cmdlet 可用于该管理单元。</span><span class="sxs-lookup"><span data-stu-id="f8203-116">[Runspace05 Sample](./runspace05-sample.md) This sample shows how to add a snap-in to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span> <span data-ttu-id="f8203-117">该管理单元提供了一个通过使用[GetProcessSample01 示例](../cmdlet/getprocesssample01-sample.md)同步运行的获取处理器 cmdlet （由该示例定义[）。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="f8203-117">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](../cmdlet/getprocesssample01-sample.md)) that is run synchronously using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="f8203-118">[Runspace06 示例](./runspace06-sample.md)此示例演示如何将模块添加到[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象中，以便在打开运行空间时加载该模块。</span><span class="sxs-lookup"><span data-stu-id="f8203-118">[Runspace06 Sample](./runspace06-sample.md) This sample shows how to add a module to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the module is loaded when the runspace is opened.</span></span> <span data-ttu-id="f8203-119">该模块提供了一个使用[GetProcessSample02](../cmdlet/getprocesssample02-sample.md)的 cmdlet，该 cmdlet 使用一个[系统管理](/dotnet/api/system.management.automation.powershell)对象进行同步运行。</span><span class="sxs-lookup"><span data-stu-id="f8203-119">The module provides a Get-Proc cmdlet (defined by the [GetProcessSample02 Sample](../cmdlet/getprocesssample02-sample.md)) that is run synchronously using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="f8203-120">[Runspace07 示例](./runspace07-sample.md)此示例演示如何创建一个运行空间，然后使用该运行空间通过[使用一个以](/dotnet/api/system.management.automation.powershell)同步方式运行两个 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8203-120">[Runspace07 Sample](./runspace07-sample.md) This sample shows how to create a runspace, and then use that runspace to run two cmdlets synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="f8203-121">[Runspace08 示例](./runspace08-sample.md)此示例演示如何将命令和参数添加到[system.web](/dotnet/api/system.management.automation.powershell)对象的管道，以及如何以同步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="f8203-121">[Runspace08 Sample](./runspace08-sample.md) This sample shows how to add commands and arguments to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

 <span data-ttu-id="f8203-122">[Runspace09 示例](./runspace09-sample.md)此示例演示如何将脚本添加到[system.web](/dotnet/api/system.management.automation.powershell)对象的管道，以及如何以异步方式运行脚本。</span><span class="sxs-lookup"><span data-stu-id="f8203-122">[Runspace09 Sample](./runspace09-sample.md) This sample shows how to add a script to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the script asynchronously.</span></span> <span data-ttu-id="f8203-123">使用事件处理脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="f8203-123">Events are used to handle the output of the script.</span></span>

 <span data-ttu-id="f8203-124">[Runspace10 示例](./runspace10-sample.md)此示例演示如何创建默认初始会话状态，如何将 cmdlet 添加到[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)，如何创建使用初始会话状态的运行空间，以及如何使用来运行该命令的示例。" [System.object](/dotnet/api/system.management.automation.powershell) " 对象。</span><span class="sxs-lookup"><span data-stu-id="f8203-124">[Runspace10 Sample](./runspace10-sample.md) This sample shows how to create a default initial session state, how to add a cmdlet to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), how to create a runspace that uses the initial session state, and how to run the command by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="f8203-125">[Runspace11 示例](./runspace11-sample.md)这说明了如何使用[Proxycommand](/dotnet/api/System.Management.Automation.ProxyCommand)类来创建一个代理命令，该命令将调用现有的 cmdlet，但会限制可用参数的集合。</span><span class="sxs-lookup"><span data-stu-id="f8203-125">[Runspace11 Sample](./runspace11-sample.md) This shows how to use the [System.Management.Automation.Proxycommand](/dotnet/api/System.Management.Automation.ProxyCommand) class to create a proxy command that calls an existing cmdlet, but restricts the set of available parameters.</span></span> <span data-ttu-id="f8203-126">然后，代理命令被添加到用来创建受限运行空间的初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="f8203-126">The proxy command is then added to an initial session state that is used to create a constrained runspace.</span></span> <span data-ttu-id="f8203-127">这意味着用户只能通过该代理命令使用该 cmdlet 的功能。</span><span class="sxs-lookup"><span data-stu-id="f8203-127">This means that the user can access the functionality of the cmdlet only through the proxy command.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8203-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8203-128">See Also</span></span>