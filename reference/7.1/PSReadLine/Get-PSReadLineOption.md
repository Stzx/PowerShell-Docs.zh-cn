---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlineoption?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineOption
ms.openlocfilehash: 78fa1c50d629484a013f7bd91bc3758e3efb141e
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200687"
---
# <span data-ttu-id="2efdd-103">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="2efdd-103">Get-PSReadLineOption</span></span>

## <span data-ttu-id="2efdd-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2efdd-104">SYNOPSIS</span></span>
<span data-ttu-id="2efdd-105">获取可配置的选项的值。</span><span class="sxs-lookup"><span data-stu-id="2efdd-105">Gets values for the options that can be configured.</span></span>

## <span data-ttu-id="2efdd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2efdd-106">SYNTAX</span></span>

```
Get-PSReadLineOption [<CommonParameters>]
```

## <span data-ttu-id="2efdd-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2efdd-107">DESCRIPTION</span></span>

<span data-ttu-id="2efdd-108">`Get-PSReadLineOption`Cmdlet 可返回可使用 cmdlet 配置的设置的当前状态 `Set-PSReadLineOption` 。</span><span class="sxs-lookup"><span data-stu-id="2efdd-108">The `Get-PSReadLineOption` cmdlet returns the current state of the settings that can be configured by using the `Set-PSReadLineOption` cmdlet.</span></span> <span data-ttu-id="2efdd-109">您可以使用返回的对象更改 **PSReadLine** 选项。</span><span class="sxs-lookup"><span data-stu-id="2efdd-109">You can use the returned object to change **PSReadLine** options.</span></span> <span data-ttu-id="2efdd-110">这为设置多种标记的语法着色选项提供了略微简单的方法。</span><span class="sxs-lookup"><span data-stu-id="2efdd-110">This provides a slightly simpler way to set syntax coloring options for multiple kinds of tokens.</span></span>

## <span data-ttu-id="2efdd-111">示例</span><span class="sxs-lookup"><span data-stu-id="2efdd-111">EXAMPLES</span></span>

### <span data-ttu-id="2efdd-112">示例1：获取选项及其值</span><span class="sxs-lookup"><span data-stu-id="2efdd-112">Example 1: Get options and their values</span></span>

```powershell
Get-PSReadLineOption
```

```Output
EditMode                               : Windows
AddToHistoryHandler                    : System.Func`2[System.String,System.Object]
HistoryNoDuplicates                    : True
HistorySavePath                        : C:\Users\username\AppData\Roaming\Microsoft\Windows\
                                         PowerShell\PSReadLine\ConsoleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
HistorySearchCaseSensitive             : False
HistorySearchCursorMovesToEnd          : False
MaximumHistoryCount                    : 4096
ContinuationPrompt                     : >>
ExtraPromptLineCount                   : 0
PromptText                             : {> }
BellStyle                              : Audible
DingDuration                           : 50
DingTone                               : 1221
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
CommandValidationHandler               :
CompletionQueryItems                   : 100
MaximumKillRingCount                   : 10
ShowToolTips                           : True
ViModeIndicator                        : None
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"---
AnsiEscapeTimeout                      : 100
CommandColor                           : "`e[93m"
CommentColor                           : "`e[32m"
ContinuationPromptColor                : "`e[97m"
DefaultTokenColor                      : "`e[97m"
EmphasisColor                          : "`e[96m"
ErrorColor                             : "`e[91m"
KeywordColor                           : "`e[92m"
MemberColor                            : "`e[97m"
NumberColor                            : "`e[97m"
OperatorColor                          : "`e[90m"
ParameterColor                         : "`e[90m"
SelectionColor                         : "`e[30;107m"
StringColor                            : "`e[36m"
TypeColor                              : "`e[37m"
VariableColor                          : "`e[92m"
```

<span data-ttu-id="2efdd-113">此命令返回可用 PSReadLine 选项及其当前值的列表。</span><span class="sxs-lookup"><span data-stu-id="2efdd-113">This command returns the list of available PSReadLine options and their current values.</span></span>

## <span data-ttu-id="2efdd-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2efdd-114">PARAMETERS</span></span>

### <span data-ttu-id="2efdd-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2efdd-115">CommonParameters</span></span>

<span data-ttu-id="2efdd-116">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2efdd-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2efdd-117">有关详细信息，请参阅 [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2efdd-117">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2efdd-118">输入</span><span class="sxs-lookup"><span data-stu-id="2efdd-118">INPUTS</span></span>

### <span data-ttu-id="2efdd-119">无</span><span class="sxs-lookup"><span data-stu-id="2efdd-119">None</span></span>

<span data-ttu-id="2efdd-120">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2efdd-120">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="2efdd-121">输出</span><span class="sxs-lookup"><span data-stu-id="2efdd-121">OUTPUTS</span></span>

### <span data-ttu-id="2efdd-122">PSConsoleReadLineOptions</span><span class="sxs-lookup"><span data-stu-id="2efdd-122">Microsoft.PowerShell.PSConsoleReadLineOptions</span></span>

<span data-ttu-id="2efdd-123">当前选项的实例。</span><span class="sxs-lookup"><span data-stu-id="2efdd-123">An instance of the current options.</span></span> <span data-ttu-id="2efdd-124">更改此对象的属性值将直接更新 PSReadLine 中的设置，而无需调用 `Set-PSReadLineOption` 。</span><span class="sxs-lookup"><span data-stu-id="2efdd-124">Changing the property values of this object updates the settings in PSReadLine directly without invoking `Set-PSReadLineOption`.</span></span>

## <span data-ttu-id="2efdd-125">注释</span><span class="sxs-lookup"><span data-stu-id="2efdd-125">NOTES</span></span>

## <span data-ttu-id="2efdd-126">相关链接</span><span class="sxs-lookup"><span data-stu-id="2efdd-126">RELATED LINKS</span></span>

[<span data-ttu-id="2efdd-127">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="2efdd-127">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="2efdd-128">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="2efdd-128">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="2efdd-129">PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="2efdd-129">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="2efdd-130">PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="2efdd-130">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)