---
Download Help Link: https://aka.ms/powershell71-help
Help Version: 7.1.0.0
keywords: powershell
Locale: en-US
Module Guid: 5714753b-2afd-4492-a5fd-01d9e2cff8b5
Module Name: PSReadLine
ms.date: 02/10/2020
schema: 2.0.0
title: PSReadLine
ms.openlocfilehash: a404461e2b92f269d581b18c3ebe7643aa86c3a4
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "93199528"
---
# <span data-ttu-id="16481-103">PSReadLine 模块</span><span class="sxs-lookup"><span data-stu-id="16481-103">PSReadLine Module</span></span>

## <span data-ttu-id="16481-104">说明</span><span class="sxs-lookup"><span data-stu-id="16481-104">Description</span></span>

<span data-ttu-id="16481-105">PSReadLine 模块包含可用于在 PowerShell 中自定义命令行编辑环境的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="16481-105">The PSReadLine module contains cmdlets that let you customize the command-line editing environment in PowerShell.</span></span> <span data-ttu-id="16481-106">这些文章介绍了 PSReadLine v2.0。</span><span class="sxs-lookup"><span data-stu-id="16481-106">These articles documents PSReadLine v2.0.</span></span> <span data-ttu-id="16481-107">此版本随附于 PowerShell v6 和 Windows 10 10 月2018更新 (生成 1809) 。</span><span class="sxs-lookup"><span data-stu-id="16481-107">This version ships in PowerShell v6 and the Windows 10 October 2018 Update (Build 1809).</span></span>

> [!NOTE]
> <span data-ttu-id="16481-108">从 PowerShell 7.0 开始，如果检测到屏幕阅读器程序，PowerShell 会跳过在 Windows 上自动加载 PSReadLine。</span><span class="sxs-lookup"><span data-stu-id="16481-108">Beginning with PowerShell 7.0, PowerShell skips auto-loading PSReadLine on Windows if a screen reader program is detected.</span></span> <span data-ttu-id="16481-109">目前，PSReadLine 不能与屏幕阅读器很好地配合使用。</span><span class="sxs-lookup"><span data-stu-id="16481-109">Currently, PSReadLine doesn't work well with the screen readers.</span></span> <span data-ttu-id="16481-110">Windows 上 PowerShell 7.0 的默认呈现和格式设置正常。</span><span class="sxs-lookup"><span data-stu-id="16481-110">The default rendering and formatting of PowerShell 7.0 on Windows works properly.</span></span> <span data-ttu-id="16481-111">如有必要，可以手动加载模块。</span><span class="sxs-lookup"><span data-stu-id="16481-111">You can manually load the module if necessary.</span></span>

## <span data-ttu-id="16481-112">PSReadLine Cmdlet</span><span class="sxs-lookup"><span data-stu-id="16481-112">PSReadLine Cmdlets</span></span>

### [<span data-ttu-id="16481-113">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="16481-113">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="16481-114">PSReadLine 的主入口点。</span><span class="sxs-lookup"><span data-stu-id="16481-114">The main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="16481-115">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="16481-115">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)
<span data-ttu-id="16481-116">获取 PSReadLine 模块的绑定键函数。</span><span class="sxs-lookup"><span data-stu-id="16481-116">Gets the bound key functions for the PSReadLine module.</span></span>

### [<span data-ttu-id="16481-117">PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="16481-117">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)
<span data-ttu-id="16481-118">获取可配置的选项的值。</span><span class="sxs-lookup"><span data-stu-id="16481-118">Gets values for the options that can be configured.</span></span>

### [<span data-ttu-id="16481-119">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="16481-119">PSConsoleHostReadLine</span></span>](PSConsoleHostReadLine.md)
<span data-ttu-id="16481-120">此函数是 PSReadLine 的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="16481-120">This function is the main entry point for PSReadLine.</span></span>

### [<span data-ttu-id="16481-121">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="16481-121">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)
<span data-ttu-id="16481-122">删除键绑定。</span><span class="sxs-lookup"><span data-stu-id="16481-122">Removes a key binding.</span></span>

### [<span data-ttu-id="16481-123">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="16481-123">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
<span data-ttu-id="16481-124">将键绑定到用户定义的或 PSReadLine 的密钥处理程序函数。</span><span class="sxs-lookup"><span data-stu-id="16481-124">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

### [<span data-ttu-id="16481-125">PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="16481-125">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)
<span data-ttu-id="16481-126">自定义 **PSReadLine** 中命令行编辑的行为。</span><span class="sxs-lookup"><span data-stu-id="16481-126">Customizes the behavior of command line editing in **PSReadLine** .</span></span>

