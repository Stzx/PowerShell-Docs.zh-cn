---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: d5856ead8fa3f0f30e7509c43aeeb73013b7a801
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196752"
---
# <span data-ttu-id="710dd-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="710dd-103">Stop-Transcript</span></span>

## <span data-ttu-id="710dd-104">摘要</span><span class="sxs-lookup"><span data-stu-id="710dd-104">SYNOPSIS</span></span>
<span data-ttu-id="710dd-105">停止脚本。</span><span class="sxs-lookup"><span data-stu-id="710dd-105">Stops a transcript.</span></span>

## <span data-ttu-id="710dd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="710dd-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="710dd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="710dd-107">DESCRIPTION</span></span>

<span data-ttu-id="710dd-108">`Stop-Transcript`Cmdlet 可停止 cmdlet 启动的脚本 `Start-Transcript` 。</span><span class="sxs-lookup"><span data-stu-id="710dd-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="710dd-109">或者，您可以结束会话来停止脚本。</span><span class="sxs-lookup"><span data-stu-id="710dd-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="710dd-110">示例</span><span class="sxs-lookup"><span data-stu-id="710dd-110">EXAMPLES</span></span>

### <span data-ttu-id="710dd-111">示例1：停止所有脚本</span><span class="sxs-lookup"><span data-stu-id="710dd-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="710dd-112">此命令停止所有脚本。</span><span class="sxs-lookup"><span data-stu-id="710dd-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="710dd-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="710dd-113">PARAMETERS</span></span>

### <span data-ttu-id="710dd-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="710dd-114">CommonParameters</span></span>

<span data-ttu-id="710dd-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="710dd-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="710dd-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="710dd-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="710dd-117">输入</span><span class="sxs-lookup"><span data-stu-id="710dd-117">INPUTS</span></span>

### <span data-ttu-id="710dd-118">无</span><span class="sxs-lookup"><span data-stu-id="710dd-118">None</span></span>

<span data-ttu-id="710dd-119">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="710dd-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="710dd-120">输出</span><span class="sxs-lookup"><span data-stu-id="710dd-120">OUTPUTS</span></span>

### <span data-ttu-id="710dd-121">System.String</span><span class="sxs-lookup"><span data-stu-id="710dd-121">System.String</span></span>

<span data-ttu-id="710dd-122">此 cmdlet 将返回一个字符串，其中包含状态消息和输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="710dd-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="710dd-123">注释</span><span class="sxs-lookup"><span data-stu-id="710dd-123">NOTES</span></span>

* <span data-ttu-id="710dd-124">如果尚未启动脚本，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="710dd-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="710dd-125">相关链接</span><span class="sxs-lookup"><span data-stu-id="710dd-125">RELATED LINKS</span></span>

[<span data-ttu-id="710dd-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="710dd-126">Start-Transcript</span></span>](Start-Transcript.md)
