---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: b551f50b024e5fd8083d853195eb9992587ca16c
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196776"
---
# <span data-ttu-id="1c3a8-103">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="1c3a8-103">Get-PSCallStack</span></span>

## <span data-ttu-id="1c3a8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="1c3a8-104">SYNOPSIS</span></span>
<span data-ttu-id="1c3a8-105">显示当前的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-105">Displays the current call stack.</span></span>

## <span data-ttu-id="1c3a8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c3a8-106">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="1c3a8-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1c3a8-107">DESCRIPTION</span></span>

<span data-ttu-id="1c3a8-108">**Get-pscallstack** cmdlet 显示当前的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-108">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="1c3a8-109">尽管它旨在用于 PowerShell 调试器，但你可以使用此 cmdlet 在调试器外的脚本或函数中显示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-109">Although it is designed to be used with the PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="1c3a8-110">若要在调试器中运行 **get-pscallstack** 命令，请键入 `k` 或 `Get-PSCallStack` 。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-110">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="1c3a8-111">示例</span><span class="sxs-lookup"><span data-stu-id="1c3a8-111">EXAMPLES</span></span>

### <span data-ttu-id="1c3a8-112">示例1：获取函数的调用堆栈</span><span class="sxs-lookup"><span data-stu-id="1c3a8-112">Example 1: Get the call stack for a function</span></span>

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

<span data-ttu-id="1c3a8-113">此命令使用 **get-pscallstack** cmdlet 来显示别名的调用堆栈，这是一个获取 cmdlet 名称的别名的简单函数。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-113">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="1c3a8-114">第一个命令在 PowerShell 提示符下进入函数。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-114">The first command enters the function at the PowerShell prompt.</span></span>
<span data-ttu-id="1c3a8-115">第二个命令使用 Set-PSBreakpoint cmdlet 在 My-Alias 函数上设置断点。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-115">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="1c3a8-116">第三个命令使用 My-Alias 函数在 Get-Content cmdlet 的当前会话中获取所有别名。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-116">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="1c3a8-117">调试器在函数调用时中断。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-117">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="1c3a8-118">两个连续的 step-into (s) 命令开始逐行执行该函数。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-118">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="1c3a8-119">然后，使用 **get-pscallstack** 命令来检索调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-119">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="1c3a8-120">最后的命令是 Step-Out 命令 (o)，它退出调试器并继续执行该脚本直到完成。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-120">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="1c3a8-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c3a8-121">PARAMETERS</span></span>

### <span data-ttu-id="1c3a8-122">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1c3a8-122">CommonParameters</span></span>

<span data-ttu-id="1c3a8-123">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c3a8-124">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c3a8-125">输入</span><span class="sxs-lookup"><span data-stu-id="1c3a8-125">INPUTS</span></span>

### <span data-ttu-id="1c3a8-126">无</span><span class="sxs-lookup"><span data-stu-id="1c3a8-126">None</span></span>

<span data-ttu-id="1c3a8-127">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="1c3a8-128">输出</span><span class="sxs-lookup"><span data-stu-id="1c3a8-128">OUTPUTS</span></span>

### <span data-ttu-id="1c3a8-129">System.web. CallStackFrame</span><span class="sxs-lookup"><span data-stu-id="1c3a8-129">System.Management.Automation.CallStackFrame</span></span>

<span data-ttu-id="1c3a8-130">**Get-pscallstack** 返回一个对象，该对象表示调用堆栈中的项。</span><span class="sxs-lookup"><span data-stu-id="1c3a8-130">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="1c3a8-131">注释</span><span class="sxs-lookup"><span data-stu-id="1c3a8-131">NOTES</span></span>

## <span data-ttu-id="1c3a8-132">相关链接</span><span class="sxs-lookup"><span data-stu-id="1c3a8-132">RELATED LINKS</span></span>

[<span data-ttu-id="1c3a8-133">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1c3a8-133">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="1c3a8-134">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1c3a8-134">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="1c3a8-135">Format-Table</span><span class="sxs-lookup"><span data-stu-id="1c3a8-135">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="1c3a8-136">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1c3a8-136">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="1c3a8-137">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1c3a8-137">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="1c3a8-138">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="1c3a8-138">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

