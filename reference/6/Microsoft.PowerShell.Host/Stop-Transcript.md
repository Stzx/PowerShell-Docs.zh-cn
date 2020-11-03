---
external help file: Microsoft.PowerShell.ConsoleHost.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Host
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.host/stop-transcript?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Transcript
ms.openlocfilehash: 5f02f59e778c55b2292bb4533cf2f8aaab2dbb7d
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93194628"
---
# <span data-ttu-id="1053b-103">Stop-Transcript</span><span class="sxs-lookup"><span data-stu-id="1053b-103">Stop-Transcript</span></span>

## <span data-ttu-id="1053b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="1053b-104">SYNOPSIS</span></span>
<span data-ttu-id="1053b-105">停止脚本。</span><span class="sxs-lookup"><span data-stu-id="1053b-105">Stops a transcript.</span></span>

## <span data-ttu-id="1053b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1053b-106">SYNTAX</span></span>

```
Stop-Transcript [<CommonParameters>]
```

## <span data-ttu-id="1053b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1053b-107">DESCRIPTION</span></span>

<span data-ttu-id="1053b-108">`Stop-Transcript`Cmdlet 可停止 cmdlet 启动的脚本 `Start-Transcript` 。</span><span class="sxs-lookup"><span data-stu-id="1053b-108">The `Stop-Transcript` cmdlet stops a transcript that was started by the `Start-Transcript` cmdlet.</span></span>
<span data-ttu-id="1053b-109">或者，您可以结束会话来停止脚本。</span><span class="sxs-lookup"><span data-stu-id="1053b-109">Alternatively, you can end a session to stop a transcript.</span></span>

## <span data-ttu-id="1053b-110">示例</span><span class="sxs-lookup"><span data-stu-id="1053b-110">EXAMPLES</span></span>

### <span data-ttu-id="1053b-111">示例1：停止所有脚本</span><span class="sxs-lookup"><span data-stu-id="1053b-111">Example 1: Stop all transcripts</span></span>

```powershell
Stop-Transcript
```

<span data-ttu-id="1053b-112">此命令停止所有脚本。</span><span class="sxs-lookup"><span data-stu-id="1053b-112">This command stops all transcripts.</span></span>

## <span data-ttu-id="1053b-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1053b-113">PARAMETERS</span></span>

### <span data-ttu-id="1053b-114">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1053b-114">CommonParameters</span></span>

<span data-ttu-id="1053b-115">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="1053b-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1053b-116">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="1053b-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1053b-117">输入</span><span class="sxs-lookup"><span data-stu-id="1053b-117">INPUTS</span></span>

### <span data-ttu-id="1053b-118">无</span><span class="sxs-lookup"><span data-stu-id="1053b-118">None</span></span>

<span data-ttu-id="1053b-119">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1053b-119">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1053b-120">输出</span><span class="sxs-lookup"><span data-stu-id="1053b-120">OUTPUTS</span></span>

### <span data-ttu-id="1053b-121">System.String</span><span class="sxs-lookup"><span data-stu-id="1053b-121">System.String</span></span>

<span data-ttu-id="1053b-122">此 cmdlet 将返回一个字符串，其中包含状态消息和输出文件的路径。</span><span class="sxs-lookup"><span data-stu-id="1053b-122">This cmdlet returns a string that contains a status message and the path to the output file.</span></span>

## <span data-ttu-id="1053b-123">注释</span><span class="sxs-lookup"><span data-stu-id="1053b-123">NOTES</span></span>

* <span data-ttu-id="1053b-124">如果尚未启动脚本，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="1053b-124">If a transcript has not been started, the command fails.</span></span>

*

## <span data-ttu-id="1053b-125">相关链接</span><span class="sxs-lookup"><span data-stu-id="1053b-125">RELATED LINKS</span></span>

[<span data-ttu-id="1053b-126">Start-Transcript</span><span class="sxs-lookup"><span data-stu-id="1053b-126">Start-Transcript</span></span>](Start-Transcript.md)
