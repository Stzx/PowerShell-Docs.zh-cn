---
description: 说明如何创建自定义 PowerShell 在控制台提示符下读取输入的方式。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 3c5f629471ce2a4315e3e90f2baec86dfda1506b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200667"
---
# <a name="about_psconsolehostreadline"></a><span data-ttu-id="a84af-104">about_PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="a84af-104">about_PSConsoleHostReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="a84af-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="a84af-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="a84af-106">说明如何创建自定义 PowerShell 在控制台提示符下读取输入的方式。</span><span class="sxs-lookup"><span data-stu-id="a84af-106">Explains how to create a customize how PowerShell reads input at the console prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="a84af-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="a84af-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="a84af-108">从 Windows PowerShell V3 开始，你可以编写一个名为 PSConsoleHostReadLine 的函数，用于重写处理控制台输入的默认方式。</span><span class="sxs-lookup"><span data-stu-id="a84af-108">Starting in Windows PowerShell V3, you can write a function named PSConsoleHostReadLine that overrides the default way that console input is processed.</span></span>

### <a name="examples"></a><span data-ttu-id="a84af-109">示例</span><span class="sxs-lookup"><span data-stu-id="a84af-109">EXAMPLES</span></span>

<span data-ttu-id="a84af-110">下面的示例启动记事本并从用户创建的文本文件获取输入：</span><span class="sxs-lookup"><span data-stu-id="a84af-110">The following example launches Notepad and gets input from a text File that the user creates:</span></span>

```powershell
function PSConsoleHostReadLine
{
  $inputFile = Join-Path $env:TEMP PSConsoleHostReadLine
  Set-Content $inputFile "PS > "

  # Notepad opens. Enter your command in it, save the file, and then exit.
  notepad $inputFile | Out-Null
  $userInput = Get-Content $inputFile
  $resultingCommand = $userInput.Replace("PS >", "")
  $resultingCommand
}
```

### <a name="remarks"></a><span data-ttu-id="a84af-111">REMARKS</span><span class="sxs-lookup"><span data-stu-id="a84af-111">REMARKS</span></span>

<span data-ttu-id="a84af-112">默认情况下，PowerShell 在所谓的 "加工模式" 下从控制台读取输入，在这种模式下，Windows 控制台子系统处理所有 keypresses、F7 菜单和其他输入。</span><span class="sxs-lookup"><span data-stu-id="a84af-112">By default, PowerShell reads input from the console in what is known as "Cooked Mode" -- in which the Windows console subsystem handles all the keypresses, F7 menus, and other input.</span></span> <span data-ttu-id="a84af-113">按 Enter 或 Tab 键时，Windows PowerShell 将获取已键入到该点的文本。</span><span class="sxs-lookup"><span data-stu-id="a84af-113">When you press Enter or Tab, Windows PowerShell gets the text that you have typed up to that point.</span></span> <span data-ttu-id="a84af-114">在按 Enter 或 Tab 之前，无法知道您按下了 Ctrl + R、Ctrl + A、Ctrl + E 或其他任何键。在 Windows PowerShell 版本3中，PSConsoleHostReadLine 函数解决了此问题。</span><span class="sxs-lookup"><span data-stu-id="a84af-114">There is no way for it to know that you pressed Ctrl-R, Ctrl-A, Ctrl-E, or any other keys before pressing Enter or Tab. In Windows PowerShell version 3, the PSConsoleHostReadLine function solves this issue.</span></span> <span data-ttu-id="a84af-115">在 Windows PowerShell 控制台主机中定义名为 PSConsoleHostReadline 的函数时，Windows PowerShell 将调用该函数，而不是 "加工模式" 输入机制。</span><span class="sxs-lookup"><span data-stu-id="a84af-115">When you define a function named PSConsoleHostReadline in the Windows PowerShell console host, Windows PowerShell calls that function instead of the "Cooked Mode" input mechanism.</span></span>

### <a name="see-also"></a><span data-ttu-id="a84af-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a84af-116">SEE ALSO</span></span>

[<span data-ttu-id="a84af-117">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="a84af-117">about_Prompts</span></span>](about_Prompts.md)
