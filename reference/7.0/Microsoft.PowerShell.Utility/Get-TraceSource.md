---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: 024fa690ff9ddd4eae2d7fd6203e83f56fef6cd7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197117"
---
# <span data-ttu-id="0135f-103">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="0135f-103">Get-TraceSource</span></span>

## <span data-ttu-id="0135f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0135f-104">SYNOPSIS</span></span>
<span data-ttu-id="0135f-105">获取用于跟踪的 PowerShell 组件。</span><span class="sxs-lookup"><span data-stu-id="0135f-105">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="0135f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0135f-106">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="0135f-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0135f-107">DESCRIPTION</span></span>

<span data-ttu-id="0135f-108">**TraceSource** cmdlet 获取当前正在使用的 PowerShell 组件的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="0135f-108">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="0135f-109">你可以使用数据来确定你可以跟踪哪些 PowerShell 组件。</span><span class="sxs-lookup"><span data-stu-id="0135f-109">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="0135f-110">在跟踪过程中，该组件将生成有关其内部处理过程中每个步骤的详细消息。</span><span class="sxs-lookup"><span data-stu-id="0135f-110">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="0135f-111">开发人员使用跟踪数据来监视数据流、程序执行情况和错误。</span><span class="sxs-lookup"><span data-stu-id="0135f-111">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="0135f-112">跟踪 cmdlet 专为 PowerShell 开发人员而设计，但可供所有用户使用。</span><span class="sxs-lookup"><span data-stu-id="0135f-112">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="0135f-113">示例</span><span class="sxs-lookup"><span data-stu-id="0135f-113">EXAMPLES</span></span>

### <span data-ttu-id="0135f-114">示例1：按名称获取跟踪源</span><span class="sxs-lookup"><span data-stu-id="0135f-114">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="0135f-115">此命令将获取名称中包含提供程序的所有跟踪源。</span><span class="sxs-lookup"><span data-stu-id="0135f-115">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="0135f-116">示例2：获取所有跟踪源</span><span class="sxs-lookup"><span data-stu-id="0135f-116">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="0135f-117">此命令将获取可以跟踪的所有 PowerShell 组件。</span><span class="sxs-lookup"><span data-stu-id="0135f-117">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="0135f-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0135f-118">PARAMETERS</span></span>

### <span data-ttu-id="0135f-119">-Name</span><span class="sxs-lookup"><span data-stu-id="0135f-119">-Name</span></span>

<span data-ttu-id="0135f-120">指定要获取的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="0135f-120">Specifies the trace sources to get.</span></span>
<span data-ttu-id="0135f-121">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0135f-121">Wildcards are permitted.</span></span>
<span data-ttu-id="0135f-122">参数名称 *名称* 是可选的。</span><span class="sxs-lookup"><span data-stu-id="0135f-122">The parameter name *Name* is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0135f-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0135f-123">CommonParameters</span></span>

<span data-ttu-id="0135f-124">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0135f-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0135f-125">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0135f-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0135f-126">输入</span><span class="sxs-lookup"><span data-stu-id="0135f-126">INPUTS</span></span>

### <span data-ttu-id="0135f-127">System.String</span><span class="sxs-lookup"><span data-stu-id="0135f-127">System.String</span></span>

<span data-ttu-id="0135f-128">可以通过管道将包含跟踪源名称的字符串传递给 **TraceSource** 。</span><span class="sxs-lookup"><span data-stu-id="0135f-128">You can pipe a string that contains the name of a trace source to **Get-TraceSource** .</span></span>

## <span data-ttu-id="0135f-129">输出</span><span class="sxs-lookup"><span data-stu-id="0135f-129">OUTPUTS</span></span>

### <span data-ttu-id="0135f-130">System.web. System.management.automation.pstracesource</span><span class="sxs-lookup"><span data-stu-id="0135f-130">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="0135f-131">**TraceSource** 返回表示跟踪源的对象。</span><span class="sxs-lookup"><span data-stu-id="0135f-131">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="0135f-132">注释</span><span class="sxs-lookup"><span data-stu-id="0135f-132">NOTES</span></span>

## <span data-ttu-id="0135f-133">相关链接</span><span class="sxs-lookup"><span data-stu-id="0135f-133">RELATED LINKS</span></span>

[<span data-ttu-id="0135f-134">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="0135f-134">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="0135f-135">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="0135f-135">Trace-Command</span></span>](Trace-Command.md)
