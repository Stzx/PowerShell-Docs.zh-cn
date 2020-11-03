---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-wsmantrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-WSManTrace
ms.openlocfilehash: 08c9d61f210761e2ed7a3a5014812b2bd362201b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197814"
---
# <span data-ttu-id="f215a-103">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="f215a-103">Enable-WSManTrace</span></span>

## <span data-ttu-id="f215a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f215a-104">SYNOPSIS</span></span>
<span data-ttu-id="f215a-105">启动启用了 WSMan 提供程序的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="f215a-105">Start a logging session with the WSMan providers enabled.</span></span>

## <span data-ttu-id="f215a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f215a-106">SYNTAX</span></span>

```
Enable-WSManTrace [<CommonParameters>]
```

## <span data-ttu-id="f215a-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f215a-107">DESCRIPTION</span></span>
<span data-ttu-id="f215a-108">此 cmdlet 将启动启用了 WSMan 提供程序的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="f215a-108">This cmdlet starts a logging session with the WSMan providers enabled.</span></span> <span data-ttu-id="f215a-109">启用以下事件提供程序：</span><span class="sxs-lookup"><span data-stu-id="f215a-109">The following event providers are enabled:</span></span>

- <span data-ttu-id="f215a-110">事件转发</span><span class="sxs-lookup"><span data-stu-id="f215a-110">Event Forwarding</span></span>
- <span data-ttu-id="f215a-111">IpmiDrv</span><span class="sxs-lookup"><span data-stu-id="f215a-111">IpmiDrv</span></span>
- <span data-ttu-id="f215a-112">IPMIPrv</span><span class="sxs-lookup"><span data-stu-id="f215a-112">IPMIPrv</span></span>
- <span data-ttu-id="f215a-113">WinRM</span><span class="sxs-lookup"><span data-stu-id="f215a-113">WinRM</span></span>
- <span data-ttu-id="f215a-114">WinrsCmd</span><span class="sxs-lookup"><span data-stu-id="f215a-114">WinrsCmd</span></span>
- <span data-ttu-id="f215a-115">WinrsExe</span><span class="sxs-lookup"><span data-stu-id="f215a-115">WinrsExe</span></span>
- <span data-ttu-id="f215a-116">WinrsMgr</span><span class="sxs-lookup"><span data-stu-id="f215a-116">WinrsMgr</span></span>
- <span data-ttu-id="f215a-117">WSManProvHost</span><span class="sxs-lookup"><span data-stu-id="f215a-117">WSManProvHost</span></span>

<span data-ttu-id="f215a-118">会话名为 "wsmlog"。</span><span class="sxs-lookup"><span data-stu-id="f215a-118">The session is named 'wsmlog'.</span></span>

<span data-ttu-id="f215a-119">此 cmdlet 使用 `Start-Trace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f215a-119">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="f215a-120">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f215a-120">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="f215a-121">示例</span><span class="sxs-lookup"><span data-stu-id="f215a-121">EXAMPLES</span></span>

### <span data-ttu-id="f215a-122">示例1：启动 WSMan 日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="f215a-122">Example 1: Start a WSMan logging session.</span></span>

```powershell
Enable-WSManTrace
```

## <span data-ttu-id="f215a-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f215a-123">PARAMETERS</span></span>

### <span data-ttu-id="f215a-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f215a-124">CommonParameters</span></span>

<span data-ttu-id="f215a-125">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="f215a-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f215a-126">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="f215a-126">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f215a-127">输入</span><span class="sxs-lookup"><span data-stu-id="f215a-127">INPUTS</span></span>

### <span data-ttu-id="f215a-128">无</span><span class="sxs-lookup"><span data-stu-id="f215a-128">None</span></span>

## <span data-ttu-id="f215a-129">输出</span><span class="sxs-lookup"><span data-stu-id="f215a-129">OUTPUTS</span></span>

### <span data-ttu-id="f215a-130">System.Object</span><span class="sxs-lookup"><span data-stu-id="f215a-130">System.Object</span></span>

## <span data-ttu-id="f215a-131">注释</span><span class="sxs-lookup"><span data-stu-id="f215a-131">NOTES</span></span>

## <span data-ttu-id="f215a-132">相关链接</span><span class="sxs-lookup"><span data-stu-id="f215a-132">RELATED LINKS</span></span>

[<span data-ttu-id="f215a-133">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="f215a-133">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="f215a-134">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="f215a-134">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="f215a-135">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="f215a-135">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)
