---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: 0999c59ab2e27b066dc6afa0b21cce029a9419e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197355"
---
# <span data-ttu-id="a1588-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a1588-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="a1588-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a1588-104">SYNOPSIS</span></span>
<span data-ttu-id="a1588-105">启用启用了 WSMan 和 PowerShell 提供程序的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="a1588-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="a1588-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a1588-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="a1588-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a1588-107">DESCRIPTION</span></span>

<span data-ttu-id="a1588-108">此 cmdlet 将启动启用以下 PowerShell 提供程序的日志记录会话：</span><span class="sxs-lookup"><span data-stu-id="a1588-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="a1588-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1588-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="a1588-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="a1588-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="a1588-111">会话名为 "PSTrace"。</span><span class="sxs-lookup"><span data-stu-id="a1588-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="a1588-112">此 cmdlet 使用 `Start-Trace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a1588-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="a1588-113">必须从提升的 PowerShell 会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a1588-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="a1588-114">示例</span><span class="sxs-lookup"><span data-stu-id="a1588-114">EXAMPLES</span></span>

### <span data-ttu-id="a1588-115">示例1：启动合并的日志记录会话</span><span class="sxs-lookup"><span data-stu-id="a1588-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="a1588-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a1588-116">PARAMETERS</span></span>

### <span data-ttu-id="a1588-117">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="a1588-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="a1588-118">默认情况下，事件写入 "$pshome \Traces\PSTrace.etl"。</span><span class="sxs-lookup"><span data-stu-id="a1588-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="a1588-119">使用此参数时，该 cmdlet 将创建一个唯一的文件名： "$pshome \Traces\ PSTrace_ {guid} .etl"</span><span class="sxs-lookup"><span data-stu-id="a1588-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="a1588-120">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a1588-120">CommonParameters</span></span>

<span data-ttu-id="a1588-121">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a1588-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a1588-122">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a1588-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a1588-123">输入</span><span class="sxs-lookup"><span data-stu-id="a1588-123">INPUTS</span></span>

### <span data-ttu-id="a1588-124">无</span><span class="sxs-lookup"><span data-stu-id="a1588-124">None</span></span>

## <span data-ttu-id="a1588-125">输出</span><span class="sxs-lookup"><span data-stu-id="a1588-125">OUTPUTS</span></span>

### <span data-ttu-id="a1588-126">无</span><span class="sxs-lookup"><span data-stu-id="a1588-126">None</span></span>

## <span data-ttu-id="a1588-127">注释</span><span class="sxs-lookup"><span data-stu-id="a1588-127">NOTES</span></span>

## <span data-ttu-id="a1588-128">相关链接</span><span class="sxs-lookup"><span data-stu-id="a1588-128">RELATED LINKS</span></span>

[<span data-ttu-id="a1588-129">事件跟踪</span><span class="sxs-lookup"><span data-stu-id="a1588-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="a1588-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="a1588-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="a1588-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="a1588-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

