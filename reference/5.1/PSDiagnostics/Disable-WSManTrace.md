---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 90cb571f93243e6fbc59970e5602911e17e25ec7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197817"
---
# <span data-ttu-id="aabe7-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="aabe7-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="aabe7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="aabe7-104">SYNOPSIS</span></span>
<span data-ttu-id="aabe7-105">停止通过 Enable-WSManTrace 启动的 WSMan 日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="aabe7-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="aabe7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aabe7-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="aabe7-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aabe7-107">DESCRIPTION</span></span>
<span data-ttu-id="aabe7-108">此 cmdlet 将停止通过 Enable-WSManTrace 启动的 WSMan 日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="aabe7-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="aabe7-109">此 cmdlet 使用 `Stop-Trace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aabe7-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="aabe7-110">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aabe7-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="aabe7-111">示例</span><span class="sxs-lookup"><span data-stu-id="aabe7-111">EXAMPLES</span></span>

### <span data-ttu-id="aabe7-112">示例1：停止 WSMan 跟踪</span><span class="sxs-lookup"><span data-stu-id="aabe7-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="aabe7-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aabe7-113">PARAMETERS</span></span>

### <span data-ttu-id="aabe7-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aabe7-114">CommonParameters</span></span>

<span data-ttu-id="aabe7-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="aabe7-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aabe7-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="aabe7-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aabe7-117">输入</span><span class="sxs-lookup"><span data-stu-id="aabe7-117">INPUTS</span></span>

### <span data-ttu-id="aabe7-118">无</span><span class="sxs-lookup"><span data-stu-id="aabe7-118">None</span></span>

## <span data-ttu-id="aabe7-119">输出</span><span class="sxs-lookup"><span data-stu-id="aabe7-119">OUTPUTS</span></span>

### <span data-ttu-id="aabe7-120">System.Object</span><span class="sxs-lookup"><span data-stu-id="aabe7-120">System.Object</span></span>

## <span data-ttu-id="aabe7-121">注释</span><span class="sxs-lookup"><span data-stu-id="aabe7-121">NOTES</span></span>

## <span data-ttu-id="aabe7-122">相关链接</span><span class="sxs-lookup"><span data-stu-id="aabe7-122">RELATED LINKS</span></span>

[<span data-ttu-id="aabe7-123">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="aabe7-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="aabe7-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="aabe7-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="aabe7-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="aabe7-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
