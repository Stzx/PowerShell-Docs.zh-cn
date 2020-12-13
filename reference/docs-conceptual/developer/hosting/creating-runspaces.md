---
ms.date: 09/13/2016
ms.topic: reference
title: 创建运行空间
description: 创建运行空间
ms.openlocfilehash: c6b2c577e435ec88364b189a0c3d065f54f02525
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649348"
---
# <a name="creating-runspaces"></a><span data-ttu-id="a2fb9-103">创建运行空间</span><span class="sxs-lookup"><span data-stu-id="a2fb9-103">Creating Runspaces</span></span>

<span data-ttu-id="a2fb9-104">运行空间是主机应用程序调用的命令的操作环境。</span><span class="sxs-lookup"><span data-stu-id="a2fb9-104">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="a2fb9-105">此环境包括当前存在的命令和数据，以及当前适用的任何语言限制。</span><span class="sxs-lookup"><span data-stu-id="a2fb9-105">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="a2fb9-106">主机应用程序可以使用 Windows PowerShell 提供的默认运行空间，其中包括所有可用的核心命令，或创建仅包含可用命令子集的自定义运行空间。</span><span class="sxs-lookup"><span data-stu-id="a2fb9-106">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="a2fb9-107">若要创建自定义的运行空间，请创建一个 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象，并将其分配给运行空间。</span><span class="sxs-lookup"><span data-stu-id="a2fb9-107">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="a2fb9-108">运行空间任务</span><span class="sxs-lookup"><span data-stu-id="a2fb9-108">Runspace tasks</span></span>

1. [<span data-ttu-id="a2fb9-109">创建 InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="a2fb9-109">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="a2fb9-110">创建受限运行空间</span><span class="sxs-lookup"><span data-stu-id="a2fb9-110">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="a2fb9-111">创建多个运行空间</span><span class="sxs-lookup"><span data-stu-id="a2fb9-111">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="a2fb9-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2fb9-112">See Also</span></span>
