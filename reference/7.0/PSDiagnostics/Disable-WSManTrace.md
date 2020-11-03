---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-wsmantrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-WSManTrace
ms.openlocfilehash: 5e91477cd840e895c25207bd5355686e0c24d473
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196786"
---
# <span data-ttu-id="9b667-103">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="9b667-103">Disable-WSManTrace</span></span>

## <span data-ttu-id="9b667-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9b667-104">SYNOPSIS</span></span>
<span data-ttu-id="9b667-105">停止通过 Enable-WSManTrace 启动的 WSMan 日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="9b667-105">Stop the WSMan logging session started by Enable-WSManTrace.</span></span>

## <span data-ttu-id="9b667-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9b667-106">SYNTAX</span></span>

```
Disable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="9b667-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9b667-107">DESCRIPTION</span></span>
<span data-ttu-id="9b667-108">此 cmdlet 将停止通过 Enable-WSManTrace 启动的 WSMan 日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="9b667-108">This cmdlet stops the WSMan logging session started by Enable-WSManTrace.</span></span>

<span data-ttu-id="9b667-109">此 cmdlet 使用 `Stop-Trace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b667-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="9b667-110">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b667-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="9b667-111">示例</span><span class="sxs-lookup"><span data-stu-id="9b667-111">EXAMPLES</span></span>

### <span data-ttu-id="9b667-112">示例1：停止 WSMan 跟踪</span><span class="sxs-lookup"><span data-stu-id="9b667-112">Example 1: Stop a WSMan trace</span></span>

```powershell
Disable-WSManTrace
```

## <span data-ttu-id="9b667-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9b667-113">PARAMETERS</span></span>

### <span data-ttu-id="9b667-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9b667-114">CommonParameters</span></span>

<span data-ttu-id="9b667-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9b667-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9b667-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9b667-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9b667-117">输入</span><span class="sxs-lookup"><span data-stu-id="9b667-117">INPUTS</span></span>

### <span data-ttu-id="9b667-118">无</span><span class="sxs-lookup"><span data-stu-id="9b667-118">None</span></span>

## <span data-ttu-id="9b667-119">输出</span><span class="sxs-lookup"><span data-stu-id="9b667-119">OUTPUTS</span></span>

### <span data-ttu-id="9b667-120">无</span><span class="sxs-lookup"><span data-stu-id="9b667-120">None</span></span>

## <span data-ttu-id="9b667-121">注释</span><span class="sxs-lookup"><span data-stu-id="9b667-121">NOTES</span></span>

## <span data-ttu-id="9b667-122">相关链接</span><span class="sxs-lookup"><span data-stu-id="9b667-122">RELATED LINKS</span></span>

[<span data-ttu-id="9b667-123">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="9b667-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="9b667-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="9b667-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="9b667-125">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="9b667-125">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)
