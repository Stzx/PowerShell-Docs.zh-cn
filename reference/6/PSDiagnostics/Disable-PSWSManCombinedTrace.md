---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: dc817a2f8629744ce4bdcf428530713e76c3d044
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196713"
---
# <span data-ttu-id="a4d91-103">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a4d91-103">Disable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="a4d91-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a4d91-104">SYNOPSIS</span></span>
<span data-ttu-id="a4d91-105">停止通过 Enable-PSWSManCombinedTrace 启动的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="a4d91-105">Stop the logging session started by Enable-PSWSManCombinedTrace.</span></span>

## <span data-ttu-id="a4d91-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a4d91-106">SYNTAX</span></span>

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## <span data-ttu-id="a4d91-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a4d91-107">DESCRIPTION</span></span>

<span data-ttu-id="a4d91-108">此 cmdlet 将停止启动的日志记录会话 `Enable-PSWSManCombinedTrace` 。</span><span class="sxs-lookup"><span data-stu-id="a4d91-108">This cmdlet stops the logging session started by `Enable-PSWSManCombinedTrace`.</span></span>

<span data-ttu-id="a4d91-109">此 cmdlet 使用 `Stop-Trace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4d91-109">This cmdlet uses the `Stop-Trace` cmdlet.</span></span>

<span data-ttu-id="a4d91-110">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4d91-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a4d91-111">示例</span><span class="sxs-lookup"><span data-stu-id="a4d91-111">EXAMPLES</span></span>

### <span data-ttu-id="a4d91-112">示例1：禁用合并的日志记录会话</span><span class="sxs-lookup"><span data-stu-id="a4d91-112">Example 1: Disable the combined logging session</span></span>

```powershell
Disable-PSWSManCombinedTrace
```

## <span data-ttu-id="a4d91-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a4d91-113">PARAMETERS</span></span>

### <span data-ttu-id="a4d91-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a4d91-114">CommonParameters</span></span>

<span data-ttu-id="a4d91-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a4d91-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a4d91-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a4d91-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a4d91-117">输入</span><span class="sxs-lookup"><span data-stu-id="a4d91-117">INPUTS</span></span>

### <span data-ttu-id="a4d91-118">无</span><span class="sxs-lookup"><span data-stu-id="a4d91-118">None</span></span>

## <span data-ttu-id="a4d91-119">输出</span><span class="sxs-lookup"><span data-stu-id="a4d91-119">OUTPUTS</span></span>

### <span data-ttu-id="a4d91-120">无</span><span class="sxs-lookup"><span data-stu-id="a4d91-120">None</span></span>

## <span data-ttu-id="a4d91-121">注释</span><span class="sxs-lookup"><span data-stu-id="a4d91-121">NOTES</span></span>

## <span data-ttu-id="a4d91-122">相关链接</span><span class="sxs-lookup"><span data-stu-id="a4d91-122">RELATED LINKS</span></span>

[<span data-ttu-id="a4d91-123">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="a4d91-123">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="a4d91-124">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="a4d91-124">Stop-Trace</span></span>](stop-trace.md)

[<span data-ttu-id="a4d91-125">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a4d91-125">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)
