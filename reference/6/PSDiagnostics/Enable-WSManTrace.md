---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 70ce4849e78262fc3553502d307e1df4e9ecfcf3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196710"
---
# <span data-ttu-id="3b815-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="3b815-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="3b815-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3b815-104">SYNOPSIS</span></span>
<span data-ttu-id="3b815-105">启动启用了 WSMan 提供程序的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="3b815-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="3b815-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3b815-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="3b815-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3b815-107">DESCRIPTION</span></span>
<span data-ttu-id="3b815-108">此 cmdlet 将启动启用了 WSMan 提供程序的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="3b815-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="3b815-109">启用以下事件提供程序：</span><span class="sxs-lookup"><span data-stu-id="3b815-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="3b815-110">事件转发</span><span class="sxs-lookup"><span data-stu-id="3b815-110">Event Forwarding</span></span>
- <span data-ttu-id="3b815-111">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="3b815-111">IpmiDrv</span></span>
- <span data-ttu-id="3b815-112">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="3b815-112">IPMIPrv</span></span>
- <span data-ttu-id="3b815-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="3b815-113">WinRM</span></span>
- <span data-ttu-id="3b815-114">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="3b815-114">WinrsCmd</span></span>
- <span data-ttu-id="3b815-115">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="3b815-115">WinrsExe</span></span>
- <span data-ttu-id="3b815-116">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="3b815-116">WinrsMgr</span></span>
- <span data-ttu-id="3b815-117">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="3b815-117">WSManProvHost</span></span>

<span data-ttu-id="3b815-118">会话名为 "wsmlog"。</span><span class="sxs-lookup"><span data-stu-id="3b815-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="3b815-119">此 cmdlet 使用 `Start-Trace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3b815-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="3b815-120">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3b815-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="3b815-121">示例</span><span class="sxs-lookup"><span data-stu-id="3b815-121">EXAMPLES</span></span>

### <span data-ttu-id="3b815-122">示例1：启动 WSMan 日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="3b815-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="3b815-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3b815-123">PARAMETERS</span></span>

### <span data-ttu-id="3b815-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3b815-124">CommonParameters</span></span>

<span data-ttu-id="3b815-125">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3b815-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3b815-126">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3b815-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3b815-127">输入</span><span class="sxs-lookup"><span data-stu-id="3b815-127">INPUTS</span></span>

### <span data-ttu-id="3b815-128">无</span><span class="sxs-lookup"><span data-stu-id="3b815-128">None</span></span>

## <span data-ttu-id="3b815-129">输出</span><span class="sxs-lookup"><span data-stu-id="3b815-129">OUTPUTS</span></span>

### <span data-ttu-id="3b815-130">无</span><span class="sxs-lookup"><span data-stu-id="3b815-130">None</span></span>

## <span data-ttu-id="3b815-131">注释</span><span class="sxs-lookup"><span data-stu-id="3b815-131">NOTES</span></span>

## <span data-ttu-id="3b815-132">相关链接</span><span class="sxs-lookup"><span data-stu-id="3b815-132">RELATED LINKS</span></span>

[<span data-ttu-id="3b815-133">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="3b815-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="3b815-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="3b815-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="3b815-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="3b815-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
