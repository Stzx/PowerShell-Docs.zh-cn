---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell02 示例
description: Windows PowerShell02 示例
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657351"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="8b44c-103">Windows PowerShell02 示例</span><span class="sxs-lookup"><span data-stu-id="8b44c-103">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="8b44c-104">此示例演示如何使用运行空间池的运行空间以异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="8b44c-104">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="8b44c-105">此示例生成命令列表，然后运行这些命令，而 Windows PowerShell 引擎在需要时从池中打开运行空间。</span><span class="sxs-lookup"><span data-stu-id="8b44c-105">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b44c-106">要求</span><span class="sxs-lookup"><span data-stu-id="8b44c-106">Requirements</span></span>

- <span data-ttu-id="8b44c-107">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="8b44c-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="8b44c-108">演示</span><span class="sxs-lookup"><span data-stu-id="8b44c-108">Demonstrates</span></span>

<span data-ttu-id="8b44c-109">此示例对下列内容进行了说明：</span><span class="sxs-lookup"><span data-stu-id="8b44c-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="8b44c-110">创建一个 RunspacePool 对象，该对象具有允许同时打开的最小和最大运行空间。</span><span class="sxs-lookup"><span data-stu-id="8b44c-110">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="8b44c-111">创建命令列表。</span><span class="sxs-lookup"><span data-stu-id="8b44c-111">Creating a list of commands.</span></span>
- <span data-ttu-id="8b44c-112">以异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="8b44c-112">Running the commands asynchronously.</span></span>
- <span data-ttu-id="8b44c-113">调用 [Runspacepool. Getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) 方法以查看有多少个空闲空间。</span><span class="sxs-lookup"><span data-stu-id="8b44c-113">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="8b44c-114">正在捕获带有 [Endinvoke \*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) 方法的命令输出。</span><span class="sxs-lookup"><span data-stu-id="8b44c-114">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="8b44c-115">示例</span><span class="sxs-lookup"><span data-stu-id="8b44c-115">Example</span></span>

<span data-ttu-id="8b44c-116">此示例演示如何打开运行空间池的运行空间，以及如何在这些运行空间中以异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="8b44c-116">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="8b44c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b44c-117">See Also</span></span>

[<span data-ttu-id="8b44c-118">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="8b44c-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
