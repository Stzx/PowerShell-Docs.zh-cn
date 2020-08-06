---
title: Windows PowerShell02 示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a82366a88addb08e186eede79e621d90d915c50f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779380"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="bb94d-102">Windows PowerShell02 示例</span><span class="sxs-lookup"><span data-stu-id="bb94d-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="bb94d-103">此示例演示如何使用运行空间池的运行空间以异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="bb94d-103">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="bb94d-104">此示例生成命令列表，然后运行这些命令，而 Windows PowerShell 引擎在需要时从池中打开运行空间。</span><span class="sxs-lookup"><span data-stu-id="bb94d-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb94d-105">要求</span><span class="sxs-lookup"><span data-stu-id="bb94d-105">Requirements</span></span>

- <span data-ttu-id="bb94d-106">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="bb94d-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="bb94d-107">演示</span><span class="sxs-lookup"><span data-stu-id="bb94d-107">Demonstrates</span></span>

<span data-ttu-id="bb94d-108">此示例对下列内容进行了说明：</span><span class="sxs-lookup"><span data-stu-id="bb94d-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="bb94d-109">创建一个 RunspacePool 对象，该对象具有允许同时打开的最小和最大运行空间。</span><span class="sxs-lookup"><span data-stu-id="bb94d-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="bb94d-110">创建命令列表。</span><span class="sxs-lookup"><span data-stu-id="bb94d-110">Creating a list of commands.</span></span>
- <span data-ttu-id="bb94d-111">以异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="bb94d-111">Running the commands asynchronously.</span></span>
- <span data-ttu-id="bb94d-112">调用[Runspacepool. Getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces)方法以查看有多少个空闲空间。</span><span class="sxs-lookup"><span data-stu-id="bb94d-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="bb94d-113">正在捕获带有[Endinvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)方法的命令输出。</span><span class="sxs-lookup"><span data-stu-id="bb94d-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="bb94d-114">示例</span><span class="sxs-lookup"><span data-stu-id="bb94d-114">Example</span></span>

<span data-ttu-id="bb94d-115">此示例演示如何打开运行空间池的运行空间，以及如何在这些运行空间中以异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="bb94d-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="bb94d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb94d-116">See Also</span></span>

[<span data-ttu-id="bb94d-117">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="bb94d-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
