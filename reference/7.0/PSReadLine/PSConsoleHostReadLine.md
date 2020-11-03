---
external help file: PSReadLine-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: 47d97fd50294a0dda1064bad123dc17931f8a470
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200697"
---
# <span data-ttu-id="723c4-103">PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="723c4-103">PSConsoleHostReadLine</span></span>

## <span data-ttu-id="723c4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="723c4-104">SYNOPSIS</span></span>
<span data-ttu-id="723c4-105">此函数是 PSReadLine 的主要入口点。</span><span class="sxs-lookup"><span data-stu-id="723c4-105">This function is the main entry point for PSReadLine.</span></span>

## <span data-ttu-id="723c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="723c4-106">SYNTAX</span></span>

```
PSConsoleHostReadLine
```

## <span data-ttu-id="723c4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="723c4-107">DESCRIPTION</span></span>

<span data-ttu-id="723c4-108">`PSConsoleHostReadLine` 是 PSReadLine 模块的主入口点。</span><span class="sxs-lookup"><span data-stu-id="723c4-108">`PSConsoleHostReadLine` is the main entry point for the PSReadLine module.</span></span> <span data-ttu-id="723c4-109">PowerShell 控制台主机会自动加载 PSReadLine 模块并调用此函数。</span><span class="sxs-lookup"><span data-stu-id="723c4-109">The PowerShell console host automatically loads the PSReadLine module and calls this function.</span></span> <span data-ttu-id="723c4-110">在正常操作情况下，不应从命令行使用此函数。</span><span class="sxs-lookup"><span data-stu-id="723c4-110">Under normal operating conditions, this function is not intended to be used from the command line.</span></span>

<span data-ttu-id="723c4-111">扩展点 `PSConsoleHostReadLine` 对于控制台主机是特殊的。</span><span class="sxs-lookup"><span data-stu-id="723c4-111">The extension point `PSConsoleHostReadLine` is special to the console host.</span></span> <span data-ttu-id="723c4-112">主机将调用具有此名称的任何别名、函数或脚本。</span><span class="sxs-lookup"><span data-stu-id="723c4-112">The host calls any alias, function, or script with this name.</span></span> <span data-ttu-id="723c4-113">PSReadLine 定义此函数，使其从控制台主机调用。</span><span class="sxs-lookup"><span data-stu-id="723c4-113">PSReadLine defines this function so that it is called from the console host.</span></span>

## <span data-ttu-id="723c4-114">示例</span><span class="sxs-lookup"><span data-stu-id="723c4-114">EXAMPLES</span></span>

### <span data-ttu-id="723c4-115">示例 1</span><span class="sxs-lookup"><span data-stu-id="723c4-115">Example 1</span></span>

<span data-ttu-id="723c4-116">不应从命令行使用此函数。</span><span class="sxs-lookup"><span data-stu-id="723c4-116">This function is not intended to be used from the command line.</span></span>

## <span data-ttu-id="723c4-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="723c4-117">PARAMETERS</span></span>

## <span data-ttu-id="723c4-118">输入</span><span class="sxs-lookup"><span data-stu-id="723c4-118">INPUTS</span></span>

### <span data-ttu-id="723c4-119">无</span><span class="sxs-lookup"><span data-stu-id="723c4-119">None</span></span>

## <span data-ttu-id="723c4-120">输出</span><span class="sxs-lookup"><span data-stu-id="723c4-120">OUTPUTS</span></span>

### <span data-ttu-id="723c4-121">无</span><span class="sxs-lookup"><span data-stu-id="723c4-121">None</span></span>

## <span data-ttu-id="723c4-122">注释</span><span class="sxs-lookup"><span data-stu-id="723c4-122">NOTES</span></span>

## <span data-ttu-id="723c4-123">相关链接</span><span class="sxs-lookup"><span data-stu-id="723c4-123">RELATED LINKS</span></span>

[<span data-ttu-id="723c4-124">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="723c4-124">about_PSReadLine</span></span>](./About/about_PSReadLine.md)
