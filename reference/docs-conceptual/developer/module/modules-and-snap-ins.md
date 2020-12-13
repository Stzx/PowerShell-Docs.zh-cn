---
ms.date: 09/13/2016
ms.topic: reference
title: 模块和管理单元
description: 模块和管理单元
ms.openlocfilehash: de4ff1de9a29b78d7783fe7ed0265f5516db1fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658689"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="9f883-103">模块和管理单元</span><span class="sxs-lookup"><span data-stu-id="9f883-103">Modules and Snap-ins</span></span>

<span data-ttu-id="9f883-104">Cmdlet 可以使用 Windows PowerShell 2.0) 或管理单元引入 (模块添加到会话中。将 cmdlet 添加到会话后，它可以通过主机应用程序以编程方式运行，或在命令行中以编程方式运行。</span><span class="sxs-lookup"><span data-stu-id="9f883-104">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="9f883-105">出于以下原因，建议使用模块作为向会话添加 cmdlet 的传递方法：</span><span class="sxs-lookup"><span data-stu-id="9f883-105">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="9f883-106">模块允许通过加载定义 cmdlet 的程序集来添加 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9f883-106">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="9f883-107">无需实现管理单元类。</span><span class="sxs-lookup"><span data-stu-id="9f883-107">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="9f883-108">模块允许添加其他资源，例如变量、函数、脚本、类型和格式设置文件等。</span><span class="sxs-lookup"><span data-stu-id="9f883-108">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="9f883-109">管理单元只能用于向会话添加 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="9f883-109">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f883-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f883-110">See Also</span></span>

[<span data-ttu-id="9f883-111">编写 Windows PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="9f883-111">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="9f883-112">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9f883-112">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
