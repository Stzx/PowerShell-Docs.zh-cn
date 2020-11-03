---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 29a72bac55dd4aabca52673a192b13f75b88f308
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196689"
---
# <span data-ttu-id="a3467-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="a3467-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="a3467-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a3467-104">SYNOPSIS</span></span>
<span data-ttu-id="a3467-105">关闭包含本地进程的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="a3467-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="a3467-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a3467-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="a3467-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a3467-107">DESCRIPTION</span></span>
<span data-ttu-id="a3467-108">**Enter-pshostprocess** cmdlet 会关闭一个交互式会话，其中包含通过运行 Enter-PSHostProcess cmdlet 打开的本地进程。</span><span class="sxs-lookup"><span data-stu-id="a3467-108">The **Exit-PSHostProcess** cmdlet closes an interactive session with a local process that you have opened by running the Enter-PSHostProcess cmdlet.</span></span>
<span data-ttu-id="a3467-109">完成调试或排查进程内运行的脚本时，可以从进程内运行 **enter-pshostprocess** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3467-109">You run the **Exit-PSHostProcess** cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span>

## <span data-ttu-id="a3467-110">示例</span><span class="sxs-lookup"><span data-stu-id="a3467-110">EXAMPLES</span></span>

### <span data-ttu-id="a3467-111">示例1：退出进程</span><span class="sxs-lookup"><span data-stu-id="a3467-111">Example 1: Exit a process</span></span>

```
PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

<span data-ttu-id="a3467-112">在此示例中，你一直在活动进程中，调试在进程的运行空间中运行的脚本，如 Enter-pshostprocess 中所述。</span><span class="sxs-lookup"><span data-stu-id="a3467-112">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in Enter-PSHostProcess.</span></span>
<span data-ttu-id="a3467-113">键入 **exit** 命令退出调试程序后，请运行 **enter-pshostprocess** cmdlet 以关闭与此进程的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="a3467-113">After you type the **exit** command to exit the debugger, run the **Exit-PSHostProcess** cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="a3467-114">Cmdlet 可在进程中关闭会话，并返回到 PS C： \\ \> prompt。</span><span class="sxs-lookup"><span data-stu-id="a3467-114">The cmdlet closes your session in the process, and returns you to the PS C:\\\> prompt.</span></span>

## <span data-ttu-id="a3467-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a3467-115">PARAMETERS</span></span>

### <span data-ttu-id="a3467-116">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a3467-116">CommonParameters</span></span>
<span data-ttu-id="a3467-117">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a3467-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a3467-118">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a3467-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a3467-119">输入</span><span class="sxs-lookup"><span data-stu-id="a3467-119">INPUTS</span></span>

## <span data-ttu-id="a3467-120">输出</span><span class="sxs-lookup"><span data-stu-id="a3467-120">OUTPUTS</span></span>

## <span data-ttu-id="a3467-121">注释</span><span class="sxs-lookup"><span data-stu-id="a3467-121">NOTES</span></span>

## <span data-ttu-id="a3467-122">相关链接</span><span class="sxs-lookup"><span data-stu-id="a3467-122">RELATED LINKS</span></span>

[<span data-ttu-id="a3467-123">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="a3467-123">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
