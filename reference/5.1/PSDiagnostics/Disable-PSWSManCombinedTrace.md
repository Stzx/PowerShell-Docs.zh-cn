---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: 4a98941de072b9b57b89a25bc180c0ee391d8b63
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197820"
---
# <span data-ttu-id="634c4-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="634c4-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="634c4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="634c4-104">SYNOPSIS</span></span>
<span data-ttu-id="634c4-105">停止通过 Enable-PSWSManCombinedTrace 启动的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="634c4-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="634c4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="634c4-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="634c4-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="634c4-107">DESCRIPTION</span></span>

<span data-ttu-id="634c4-108">此 cmdlet 将停止启动的日志记录会话 `Enable-PSWSManCombinedTrace` 。</span><span class="sxs-lookup"><span data-stu-id="634c4-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="634c4-109">此 cmdlet 使用 `Stop-Trace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="634c4-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="634c4-110">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="634c4-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="634c4-111">示例</span><span class="sxs-lookup"><span data-stu-id="634c4-111">EXAMPLES</span></span>

### <span data-ttu-id="634c4-112">示例1：禁用合并的日志记录会话</span><span class="sxs-lookup"><span data-stu-id="634c4-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="634c4-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="634c4-113">PARAMETERS</span></span>

### <span data-ttu-id="634c4-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="634c4-114">CommonParameters</span></span>

<span data-ttu-id="634c4-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="634c4-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="634c4-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="634c4-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="634c4-117">输入</span><span class="sxs-lookup"><span data-stu-id="634c4-117">INPUTS</span></span>

### <span data-ttu-id="634c4-118">无</span><span class="sxs-lookup"><span data-stu-id="634c4-118">None</span></span>

## <span data-ttu-id="634c4-119">输出</span><span class="sxs-lookup"><span data-stu-id="634c4-119">OUTPUTS</span></span>

### <span data-ttu-id="634c4-120">System.Object</span><span class="sxs-lookup"><span data-stu-id="634c4-120">System.Object</span></span>

## <span data-ttu-id="634c4-121">注释</span><span class="sxs-lookup"><span data-stu-id="634c4-121">NOTES</span></span>

## <span data-ttu-id="634c4-122">相关链接</span><span class="sxs-lookup"><span data-stu-id="634c4-122">RELATED LINKS</span></span>

[<span data-ttu-id="634c4-123">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="634c4-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="634c4-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="634c4-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="634c4-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="634c4-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
