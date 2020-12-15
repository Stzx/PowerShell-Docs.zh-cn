---
ms.date: 12/01/2020
title: PowerShell 库
description: PowerShell 库是 PowerShell 模块、脚本和 DSC 资源的中心存储库。
ms.openlocfilehash: f1ce6a8e2d5d72ac14cf3e4854626ef612d27891
ms.sourcegitcommit: 62282bb9c36fea3b4290b9263c1cd8e9ac216e29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "96470309"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="608d9-103">PowerShell 库</span><span class="sxs-lookup"><span data-stu-id="608d9-103">The PowerShell Gallery</span></span>

<span data-ttu-id="608d9-104">PowerShell 库是 PowerShell 内容的中心存储库。</span><span class="sxs-lookup"><span data-stu-id="608d9-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="608d9-105">在 PowerShell 库中，可找到包含 PowerShell 命令和 Desired State Configuration (DSC) 资源的实用 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="608d9-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="608d9-106">还可找到 PowerShell 脚本，其中一些脚本可能包含 PowerShell 工作流、概述任务组和提供这些任务的序列。</span><span class="sxs-lookup"><span data-stu-id="608d9-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="608d9-107">其中一些包由 Microsoft 编写，另一些包由 PowerShell 社区编写。</span><span class="sxs-lookup"><span data-stu-id="608d9-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="608d9-108">PowerShellGet 概述</span><span class="sxs-lookup"><span data-stu-id="608d9-108">PowerShellGet Overview</span></span>

<span data-ttu-id="608d9-109">PowerShellGet 模块包含用于发现、安装、更新和发布包含来自 [PowerShell 库](https://www.PowerShellGallery.com)和其他专用存储库的模块、DSC 资源、角色功能和脚本等项目的 PowerShell 包的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="608d9-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="608d9-110">库入门</span><span class="sxs-lookup"><span data-stu-id="608d9-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="608d9-111">从库安装包需要 PowerShellGet 模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="608d9-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span> <span data-ttu-id="608d9-112">请参阅[安装 PowerShellGet](installing-psget.md)，获取完整说明。</span><span class="sxs-lookup"><span data-stu-id="608d9-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="608d9-113">有关如何在库中使用 PowerShellGet 命令的详细信息，请参阅[入门](getting-started.md)页面。</span><span class="sxs-lookup"><span data-stu-id="608d9-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="608d9-114">你也可运行 *Update-Help -Module PowerShellGet* 安装这些命令的本地帮助。</span><span class="sxs-lookup"><span data-stu-id="608d9-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="608d9-115">支持的操作系统</span><span class="sxs-lookup"><span data-stu-id="608d9-115">Supported Operating Systems</span></span>

<span data-ttu-id="608d9-116">**PowerShellGet** 模块需要 **PowerShell 3.0 或更高版本**。</span><span class="sxs-lookup"><span data-stu-id="608d9-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="608d9-117">PowerShellGet 需要 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="608d9-117">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="608d9-118">有关详细信息，请参阅[安装面向开发人员的 .NET Framework](/dotnet/framework/install/guide-for-developers)。</span><span class="sxs-lookup"><span data-stu-id="608d9-118">For more information, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>

<span data-ttu-id="608d9-119">由于 PowerShell Core 是跨平台的，这意味着它可以在 Windows、Linux 和 MacOS 上工作，这也使得 PowerShellGet 在这些系统上均可用。</span><span class="sxs-lookup"><span data-stu-id="608d9-119">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="608d9-120">有关 PowerShell Core 支持的完整系统列表，请参阅[安装 PowerShell](/powershell/scripting/install/installing-powershell)。</span><span class="sxs-lookup"><span data-stu-id="608d9-120">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/install/installing-powershell).</span></span>

<span data-ttu-id="608d9-121">许多托管在库中的模块都支持不同的操作系统并具有附加要求。</span><span class="sxs-lookup"><span data-stu-id="608d9-121">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span>
<span data-ttu-id="608d9-122">有关详细信息，请参阅模块文档。</span><span class="sxs-lookup"><span data-stu-id="608d9-122">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="608d9-123">遇到问题？</span><span class="sxs-lookup"><span data-stu-id="608d9-123">Got a question?</span></span> <span data-ttu-id="608d9-124">想提供反馈？</span><span class="sxs-lookup"><span data-stu-id="608d9-124">Have feedback?</span></span>

<span data-ttu-id="608d9-125">可在[入门](getting-started.md)页面找到有关 PowerShell 库和 PowerShellGet 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="608d9-125">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span>

<span data-ttu-id="608d9-126">若要查看 PowerShell 库服务的当前状态，请参阅 GitHub 上的 [PowerShell 库状态](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md)页面。</span><span class="sxs-lookup"><span data-stu-id="608d9-126">To see the current status of the PowerShell Gallery services, see the [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) page on GitHub.</span></span>

<span data-ttu-id="608d9-127">请在 [GitHub 存储库](https://github.com/PowerShell/PowerShellGallery/issues)中提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="608d9-127">Please provide feedback and report issues the [GitHub repository](https://github.com/PowerShell/PowerShellGallery/issues).</span></span>
