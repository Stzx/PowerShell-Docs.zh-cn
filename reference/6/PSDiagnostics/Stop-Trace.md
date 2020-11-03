---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/stop-trace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Trace
ms.openlocfilehash: 48027fe707660f7844c28bf5f8916b0f51e0d4d1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198158"
---
# <span data-ttu-id="54572-103">Stop-Trace</span><span class="sxs-lookup"><span data-stu-id="54572-103">Stop-Trace</span></span>

## <span data-ttu-id="54572-104">摘要</span><span class="sxs-lookup"><span data-stu-id="54572-104">SYNOPSIS</span></span>
<span data-ttu-id="54572-105">停止事件跟踪日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="54572-105">Stop an Event Trace logging session.</span></span>

## <span data-ttu-id="54572-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="54572-106">SYNTAX</span></span>

```
Stop-Trace [-SessionName] <Object> [-ETS] [<CommonParameters>]
```

## <span data-ttu-id="54572-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="54572-107">DESCRIPTION</span></span>

<span data-ttu-id="54572-108">此 cmdlet 将停止一个 Windows 事件跟踪日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="54572-108">This cmdlet stops a Windows Event Trace logging session.</span></span>

<span data-ttu-id="54572-109">以下 cmdlet 使用此 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="54572-109">This cmdlet is used by the following cmdlets:</span></span>

- `Disable-PSWSManCombinedTrace`
- `Disable-WSManTrace`

<span data-ttu-id="54572-110">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54572-110">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="54572-111">示例</span><span class="sxs-lookup"><span data-stu-id="54572-111">EXAMPLES</span></span>

### <span data-ttu-id="54572-112">示例1：停止 WSMan 跟踪日志记录会话</span><span class="sxs-lookup"><span data-stu-id="54572-112">Example 1: Stop a WSMan Trace logging session</span></span>

```powershell
Stop-Trace -SessionName 'wsmlog'
```

## <span data-ttu-id="54572-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="54572-113">PARAMETERS</span></span>

### <span data-ttu-id="54572-114">-ETS</span><span class="sxs-lookup"><span data-stu-id="54572-114">-ETS</span></span>
<span data-ttu-id="54572-115">直接将命令发送到事件跟踪会话，无需保存或计划。</span><span class="sxs-lookup"><span data-stu-id="54572-115">Send commands to Event Trace Sessions directly without saving or scheduling.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54572-116">-SessionName</span><span class="sxs-lookup"><span data-stu-id="54572-116">-SessionName</span></span>
<span data-ttu-id="54572-117">要停止的事件跟踪会话的名称。</span><span class="sxs-lookup"><span data-stu-id="54572-117">The name of the Event Trace session to be stopped.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="54572-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="54572-118">CommonParameters</span></span>
<span data-ttu-id="54572-119">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="54572-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="54572-120">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="54572-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="54572-121">输入</span><span class="sxs-lookup"><span data-stu-id="54572-121">INPUTS</span></span>

### <span data-ttu-id="54572-122">无</span><span class="sxs-lookup"><span data-stu-id="54572-122">None</span></span>

## <span data-ttu-id="54572-123">输出</span><span class="sxs-lookup"><span data-stu-id="54572-123">OUTPUTS</span></span>

### <span data-ttu-id="54572-124">无</span><span class="sxs-lookup"><span data-stu-id="54572-124">None</span></span>

## <span data-ttu-id="54572-125">注释</span><span class="sxs-lookup"><span data-stu-id="54572-125">NOTES</span></span>

## <span data-ttu-id="54572-126">相关链接</span><span class="sxs-lookup"><span data-stu-id="54572-126">RELATED LINKS</span></span>

[<span data-ttu-id="54572-127">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="54572-127">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="54572-128">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="54572-128">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="54572-129">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="54572-129">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

[<span data-ttu-id="54572-130">Disable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="54572-130">Disable-WSManTrace</span></span>](Disable-WSManTrace.md)

[<span data-ttu-id="54572-131">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="54572-131">Enable-PSWSManCombinedTrace</span></span>](Enable-PSWSManCombinedTrace.md)

[<span data-ttu-id="54572-132">Enable-WSManTrace</span><span class="sxs-lookup"><span data-stu-id="54572-132">Enable-WSManTrace</span></span>](Enable-WSManTrace.md)