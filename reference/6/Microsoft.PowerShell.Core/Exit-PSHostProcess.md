---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 1734758d34e89020f579fffa217cef58eb222736
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94344042"
---
# <span data-ttu-id="dd8a0-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="dd8a0-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="dd8a0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="dd8a0-104">SYNOPSIS</span></span>
<span data-ttu-id="dd8a0-105">关闭包含本地进程的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="dd8a0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dd8a0-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="dd8a0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="dd8a0-107">DESCRIPTION</span></span>

<span data-ttu-id="dd8a0-108">`Exit-PSHostProcess`Cmdlet 可通过运行 cmdlet 来关闭与已打开的本地进程的交互式会话 `Enter-PSHostProcess` 。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-108">The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet.</span></span> <span data-ttu-id="dd8a0-109">`Exit-PSHostProcess`完成调试或排查进程内运行的脚本时，可以从进程中运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-109">You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span> <span data-ttu-id="dd8a0-110">从 PowerShell 6.2 开始，非 Windows 平台上支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-110">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="dd8a0-111">示例</span><span class="sxs-lookup"><span data-stu-id="dd8a0-111">EXAMPLES</span></span>

### <span data-ttu-id="dd8a0-112">示例1：退出进程</span><span class="sxs-lookup"><span data-stu-id="dd8a0-112">Example 1: Exit a process</span></span>

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

<span data-ttu-id="dd8a0-113">在此示例中，你一直在活动进程中，调试在进程的运行空间中运行的脚本，如中所述 `Enter-PSHostProcess` 。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-113">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in `Enter-PSHostProcess`.</span></span> <span data-ttu-id="dd8a0-114">键入 `exit` 命令退出调试程序后，运行 `Exit-PSHostProcess` cmdlet 以关闭与此进程的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-114">After you type the `exit` command to exit the debugger, run the `Exit-PSHostProcess` cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="dd8a0-115">Cmdlet 可在进程中关闭会话，并返回到 `PS C:\>` 提示符。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-115">The cmdlet closes your session in the process, and returns you to the `PS C:\>` prompt.</span></span>

## <span data-ttu-id="dd8a0-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dd8a0-116">PARAMETERS</span></span>

### <span data-ttu-id="dd8a0-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="dd8a0-117">CommonParameters</span></span>

<span data-ttu-id="dd8a0-118">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dd8a0-119">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="dd8a0-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="dd8a0-120">输入</span><span class="sxs-lookup"><span data-stu-id="dd8a0-120">INPUTS</span></span>

## <span data-ttu-id="dd8a0-121">输出</span><span class="sxs-lookup"><span data-stu-id="dd8a0-121">OUTPUTS</span></span>

## <span data-ttu-id="dd8a0-122">注释</span><span class="sxs-lookup"><span data-stu-id="dd8a0-122">NOTES</span></span>

## <span data-ttu-id="dd8a0-123">相关链接</span><span class="sxs-lookup"><span data-stu-id="dd8a0-123">RELATED LINKS</span></span>

[<span data-ttu-id="dd8a0-124">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="dd8a0-124">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
