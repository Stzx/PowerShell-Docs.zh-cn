---
description: 介绍 `Prompt` 函数并演示如何创建自定义 `Prompt` 函数。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/15/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_prompts?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Prompts
ms.openlocfilehash: c21c51a58beeb454e785e57989d3b4a75d575d0e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200441"
---
# <a name="about-prompts"></a><span data-ttu-id="824fb-104">关于提示符</span><span class="sxs-lookup"><span data-stu-id="824fb-104">About Prompts</span></span>

## <a name="short-description"></a><span data-ttu-id="824fb-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="824fb-105">Short description</span></span>
<span data-ttu-id="824fb-106">介绍 `Prompt` 函数并演示如何创建自定义 `Prompt` 函数。</span><span class="sxs-lookup"><span data-stu-id="824fb-106">Describes the `Prompt` function and demonstrates how to create a custom `Prompt` function.</span></span>

## <a name="long-description"></a><span data-ttu-id="824fb-107">长说明</span><span class="sxs-lookup"><span data-stu-id="824fb-107">Long description</span></span>

<span data-ttu-id="824fb-108">PowerShell 命令提示符指示 PowerShell 已准备好运行命令：</span><span class="sxs-lookup"><span data-stu-id="824fb-108">The PowerShell command prompt indicates that PowerShell is ready to run a command:</span></span>

```
PS C:\>
```

<span data-ttu-id="824fb-109">PowerShell 提示符由内置 `Prompt` 函数决定。</span><span class="sxs-lookup"><span data-stu-id="824fb-109">The PowerShell prompt is determined by the built-in `Prompt` function.</span></span> <span data-ttu-id="824fb-110">你可以通过创建自己的 `Prompt` 函数并将其保存到 PowerShell 配置文件中来自定义该提示。</span><span class="sxs-lookup"><span data-stu-id="824fb-110">You can customize the prompt by creating your own `Prompt` function and saving it in your PowerShell profile.</span></span>

## <a name="about-the-prompt-function"></a><span data-ttu-id="824fb-111">关于 Prompt 函数</span><span class="sxs-lookup"><span data-stu-id="824fb-111">About the Prompt function</span></span>

<span data-ttu-id="824fb-112">`Prompt`函数确定 PowerShell 提示符的外观。</span><span class="sxs-lookup"><span data-stu-id="824fb-112">The `Prompt` function determines the appearance of the PowerShell prompt.</span></span>
<span data-ttu-id="824fb-113">PowerShell 附带了一个内置 `Prompt` 函数，但你可以通过定义自己的函数来替代它 `Prompt` 。</span><span class="sxs-lookup"><span data-stu-id="824fb-113">PowerShell comes with a built-in `Prompt` function, but you can override it by defining your own `Prompt` function.</span></span>

<span data-ttu-id="824fb-114">`Prompt`函数具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="824fb-114">The `Prompt` function has the following syntax:</span></span>

```powershell
function Prompt { <function-body> }
```

<span data-ttu-id="824fb-115">`Prompt`函数必须返回对象。</span><span class="sxs-lookup"><span data-stu-id="824fb-115">The `Prompt` function must return an object.</span></span> <span data-ttu-id="824fb-116">作为最佳做法，返回一个字符串或格式化为字符串的对象。</span><span class="sxs-lookup"><span data-stu-id="824fb-116">As a best practice, return a string or an object that is formatted as a string.</span></span> <span data-ttu-id="824fb-117">建议最大长度是 80 个字符。</span><span class="sxs-lookup"><span data-stu-id="824fb-117">The maximum recommended length is 80 characters.</span></span>

<span data-ttu-id="824fb-118">例如，以下 `Prompt` 函数返回一个 "Hello，World" 字符串，后跟一个右尖括号 (`>`) 。</span><span class="sxs-lookup"><span data-stu-id="824fb-118">For example, the following `Prompt` function returns a "Hello, World" string followed by a  right angle bracket (`>`).</span></span>

```powershell
PS C:\> function prompt {"Hello, World > "}
Hello, World >
```

### <a name="getting-the-prompt-function"></a><span data-ttu-id="824fb-119">获取 Prompt 函数</span><span class="sxs-lookup"><span data-stu-id="824fb-119">Getting the Prompt function</span></span>

<span data-ttu-id="824fb-120">若要获取 `Prompt` 函数，请使用 `Get-Command` cmdlet 或 `Get-Item` 在函数驱动器中使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="824fb-120">To get the `Prompt` function, use the `Get-Command` cmdlet or use the `Get-Item` cmdlet in the Function drive.</span></span>

<span data-ttu-id="824fb-121">例如：</span><span class="sxs-lookup"><span data-stu-id="824fb-121">For example:</span></span>

```powershell
PS C:\> Get-Command Prompt

CommandType     Name      ModuleName
-----------     ----      ----------
Function        prompt
```

<span data-ttu-id="824fb-122">若要获取设置提示值的脚本，请使用点方法获取函数的 **ScriptBlock** 属性 `Prompt` 。</span><span class="sxs-lookup"><span data-stu-id="824fb-122">To get the script that sets the value of the prompt, use the dot method to get the **ScriptBlock** property of the `Prompt` function.</span></span>

<span data-ttu-id="824fb-123">例如：</span><span class="sxs-lookup"><span data-stu-id="824fb-123">For example:</span></span>

```powershell
(Get-Command Prompt).ScriptBlock
```

```Output
"PS $($executionContext.SessionState.Path.CurrentLocation)$('>' * ($nestedPromptLevel + 1)) "
# .Link
# https://go.microsoft.com/fwlink/?LinkID=225750
# .ExternalHelp System.Management.Automation.dll-help.xml
```

<span data-ttu-id="824fb-124">与所有函数一样，该 `Prompt` 函数存储在 `Function:` 驱动器中。</span><span class="sxs-lookup"><span data-stu-id="824fb-124">Like all functions, the `Prompt` function is stored in the `Function:` drive.</span></span>
<span data-ttu-id="824fb-125">若要显示用于创建当前函数的脚本 `Prompt` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="824fb-125">To display the script that creates the current `Prompt` function, type:</span></span>

```powershell
(Get-Item function:prompt).ScriptBlock
```

### <a name="the-default-prompt"></a><span data-ttu-id="824fb-126">默认提示</span><span class="sxs-lookup"><span data-stu-id="824fb-126">The default prompt</span></span>

<span data-ttu-id="824fb-127">仅当 `Prompt` 函数生成错误或不返回对象时，才会显示默认提示。</span><span class="sxs-lookup"><span data-stu-id="824fb-127">The default prompt appears only when the `Prompt` function generates an error or does not return an object.</span></span>

<span data-ttu-id="824fb-128">默认 PowerShell 提示符为：</span><span class="sxs-lookup"><span data-stu-id="824fb-128">The default PowerShell prompt is:</span></span>

```
PS>
```

<span data-ttu-id="824fb-129">例如，下面的命令将函数设置 `Prompt` 为 `$null` ，这是无效的。</span><span class="sxs-lookup"><span data-stu-id="824fb-129">For example, the following command sets the `Prompt` function to `$null`, which is invalid.</span></span> <span data-ttu-id="824fb-130">因此会显示默认提示符。</span><span class="sxs-lookup"><span data-stu-id="824fb-130">As a result, the default prompt appears.</span></span>

```powershell
PS C:\> function prompt {$null}
PS>
```

<span data-ttu-id="824fb-131">因为 PowerShell 附带了内置提示，所以通常不会看到默认提示。</span><span class="sxs-lookup"><span data-stu-id="824fb-131">Because PowerShell comes with a built-in prompt, you usually do not see the default prompt.</span></span>

### <a name="built-in-prompt"></a><span data-ttu-id="824fb-132">内置提示</span><span class="sxs-lookup"><span data-stu-id="824fb-132">Built-in prompt</span></span>

<span data-ttu-id="824fb-133">PowerShell 包含内置 `Prompt` 函数。</span><span class="sxs-lookup"><span data-stu-id="824fb-133">PowerShell includes a built-in `Prompt` function.</span></span>

```powershell
function prompt {
    $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
      else { '' }) + 'PS ' + $(Get-Location) +
        $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="824fb-134">函数使用 `Test-Path` cmdlet 来确定是否 `$PSDebugContext` 填充了自动变量。</span><span class="sxs-lookup"><span data-stu-id="824fb-134">The function uses the `Test-Path` cmdlet to determine whether the `$PSDebugContext` automatic variable is populated.</span></span> <span data-ttu-id="824fb-135">如果 `$PSDebugContext` 填充了，则处于调试模式，并 `[DBG]:` 添加到提示符下，如下所示：</span><span class="sxs-lookup"><span data-stu-id="824fb-135">If `$PSDebugContext` is populated, you are in debugging mode, and `[DBG]:` is added to the prompt, as follows:</span></span>

```Output
[DBG]: PS C:\ps-test>
```

<span data-ttu-id="824fb-136">如果 `$PSDebugContext` 未填充，则函数将添加 `PS` 到提示符。</span><span class="sxs-lookup"><span data-stu-id="824fb-136">If `$PSDebugContext` is not populated, the function adds `PS` to the prompt.</span></span>
<span data-ttu-id="824fb-137">函数使用 `Get-Location` cmdlet 来获取当前的文件系统目录位置。</span><span class="sxs-lookup"><span data-stu-id="824fb-137">And, the function uses the `Get-Location` cmdlet to get the current file system directory location.</span></span> <span data-ttu-id="824fb-138">然后，将 () 中添加一个右尖括号 `>` 。</span><span class="sxs-lookup"><span data-stu-id="824fb-138">Then, it adds a right angle bracket (`>`).</span></span>

<span data-ttu-id="824fb-139">例如：</span><span class="sxs-lookup"><span data-stu-id="824fb-139">For example:</span></span>

```Output
PS C:\ps-test>
```

<span data-ttu-id="824fb-140">如果在嵌套提示符下，函数会向提示符添加两个尖括号 (`>>`) 。</span><span class="sxs-lookup"><span data-stu-id="824fb-140">If you are in a nested prompt, the function adds two angle brackets (`>>`) to the prompt.</span></span> <span data-ttu-id="824fb-141">如果自动变量的值大于1，则 (在嵌套提示符下 `$NestedPromptLevel` 。 ) </span><span class="sxs-lookup"><span data-stu-id="824fb-141">(You are in a nested prompt if the value of the `$NestedPromptLevel` automatic variable is greater than 1.)</span></span>

<span data-ttu-id="824fb-142">例如，在嵌套提示符中进行调试时，提示符类似于以下提示符：</span><span class="sxs-lookup"><span data-stu-id="824fb-142">For example, when you are debugging in a nested prompt, the prompt resembles the following prompt:</span></span>

```Output
[DBG] PS C:\ps-test>>>
```

### <a name="changes-to-the-prompt"></a><span data-ttu-id="824fb-143">对提示的更改</span><span class="sxs-lookup"><span data-stu-id="824fb-143">Changes to the prompt</span></span>

<span data-ttu-id="824fb-144">该 `Enter-PSSession` cmdlet 将远程计算机的名称前面预置到当前 `Prompt` 函数。</span><span class="sxs-lookup"><span data-stu-id="824fb-144">The `Enter-PSSession` cmdlet prepends the name of the remote computer to the current `Prompt` function.</span></span> <span data-ttu-id="824fb-145">使用 `Enter-PSSession` cmdlet 启动与远程计算机的会话时，命令提示符将更改为包含远程计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="824fb-145">When you use the `Enter-PSSession` cmdlet to start a session with a remote computer, the command prompt changes to include the name of the remote computer.</span></span> <span data-ttu-id="824fb-146">例如：</span><span class="sxs-lookup"><span data-stu-id="824fb-146">For example:</span></span>

```Output
PS Hello, World> Enter-PSSession Server01
[Server01]: PS Hello, World>
```

<span data-ttu-id="824fb-147">其他 PowerShell 主机应用程序和备用 shell 可能有其自己的自定义命令提示符。</span><span class="sxs-lookup"><span data-stu-id="824fb-147">Other PowerShell host applications and alternate shells might have their own custom command prompts.</span></span>

<span data-ttu-id="824fb-148">有关 `$PSDebugContext` 和自动变量的详细信息 `$NestedPromptLevel` ，请参阅 [about_Automatic_Variables](about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="824fb-148">For more information about the `$PSDebugContext` and `$NestedPromptLevel` automatic variables, see [about_Automatic_Variables](about_Automatic_Variables.md).</span></span>

### <a name="how-to-customize-the-prompt"></a><span data-ttu-id="824fb-149">如何自定义提示符</span><span class="sxs-lookup"><span data-stu-id="824fb-149">How to customize the prompt</span></span>

<span data-ttu-id="824fb-150">若要自定义提示，请编写新 `Prompt` 函数。</span><span class="sxs-lookup"><span data-stu-id="824fb-150">To customize the prompt, write a new `Prompt` function.</span></span> <span data-ttu-id="824fb-151">该函数不受保护，因此可以覆盖它。</span><span class="sxs-lookup"><span data-stu-id="824fb-151">The function is not protected, so you can overwrite it.</span></span>

<span data-ttu-id="824fb-152">若要编写 `Prompt` 函数，请键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="824fb-152">To write a `Prompt` function, type the following:</span></span>

```powershell
function prompt { }
```

<span data-ttu-id="824fb-153">随后在大括号之间，输入创建提示符的命令或字符串。</span><span class="sxs-lookup"><span data-stu-id="824fb-153">Then, between the braces, enter the commands or the string that creates your prompt.</span></span>

<span data-ttu-id="824fb-154">例如，下面的提示符包含计算机名称：</span><span class="sxs-lookup"><span data-stu-id="824fb-154">For example, the following prompt includes your computer name:</span></span>

```powershell
function prompt {"PS [$env:COMPUTERNAME]> "}
```

<span data-ttu-id="824fb-155">在 Server01 计算机上，提示符类似于以下提示符：</span><span class="sxs-lookup"><span data-stu-id="824fb-155">On the Server01 computer, the prompt resembles the following prompt:</span></span>

```Output
PS [Server01] >
```

<span data-ttu-id="824fb-156">以下 `Prompt` 函数包含当前日期和时间：</span><span class="sxs-lookup"><span data-stu-id="824fb-156">The following `Prompt` function includes the current date and time:</span></span>

```powershell
function prompt {"$(Get-Date)> "}
```

<span data-ttu-id="824fb-157">提示符类似于以下提示符：</span><span class="sxs-lookup"><span data-stu-id="824fb-157">The prompt resembles the following prompt:</span></span>

```Output
03/15/2012 17:49:47>
```

<span data-ttu-id="824fb-158">还可以更改默认 `Prompt` 函数：</span><span class="sxs-lookup"><span data-stu-id="824fb-158">You can also change the default `Prompt` function:</span></span>

<span data-ttu-id="824fb-159">例如， `Prompt` `[ADMIN]:` 使用 " **以管理员身份运行** " 选项打开 PowerShell 时，以下已修改的函数会将添加到内置 powershell 提示符：</span><span class="sxs-lookup"><span data-stu-id="824fb-159">For example, the following modified `Prompt` function adds `[ADMIN]:` to the built-in PowerShell prompt when PowerShell is opened by using the **Run as administrator** option:</span></span>

```powershell
function prompt {
  $identity = [Security.Principal.WindowsIdentity]::GetCurrent()
  $principal = [Security.Principal.WindowsPrincipal] $identity
  $adminRole = [Security.Principal.WindowsBuiltInRole]::Administrator

  $(if (Test-Path variable:/PSDebugContext) { '[DBG]: ' }
    elseif($principal.IsInRole($adminRole)) { "[ADMIN]: " }
    else { '' }
  ) + 'PS ' + $(Get-Location) +
    $(if ($NestedPromptLevel -ge 1) { '>>' }) + '> '
}
```

<span data-ttu-id="824fb-160">使用 "以 **管理员身份运行** " 选项启动 PowerShell 时，将出现类似于下面的提示：</span><span class="sxs-lookup"><span data-stu-id="824fb-160">When you start PowerShell by using the **Run as administrator** option, a prompt that resembles the following prompt appears:</span></span>

```Output
[ADMIN]: PS C:\ps-test>
```

<span data-ttu-id="824fb-161">以下 `Prompt` 函数显示下一个命令的历史记录 ID。</span><span class="sxs-lookup"><span data-stu-id="824fb-161">The following `Prompt` function displays the history ID of the next command.</span></span> <span data-ttu-id="824fb-162">若要查看命令历史记录，请使用 `Get-History` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="824fb-162">To view the command history, use the `Get-History` cmdlet.</span></span>

```powershell
function prompt {
   # The at sign creates an array in case only one history item exists.
   $history = @(Get-History)
   if($history.Count -gt 0)
   {
      $lastItem = $history[$history.Count - 1]
      $lastId = $lastItem.Id
   }

   $nextCommand = $lastId + 1
   $currentDirectory = Get-Location
   "PS: $nextCommand $currentDirectory >"
}
```

<span data-ttu-id="824fb-163">以下提示使用 `Write-Host` 和 `Get-Random` cmdlet 来创建随机更改颜色的提示。</span><span class="sxs-lookup"><span data-stu-id="824fb-163">The following prompt uses the `Write-Host` and `Get-Random` cmdlets to create a prompt that changes color randomly.</span></span> <span data-ttu-id="824fb-164">由于 `Write-Host` 写入当前宿主应用程序但未返回对象，因此此函数包含一个 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="824fb-164">Because `Write-Host` writes to the current host application but does not return an object, this function includes a `Return` statement.</span></span> <span data-ttu-id="824fb-165">如果不使用它，PowerShell 将使用默认提示 `PS>` 。</span><span class="sxs-lookup"><span data-stu-id="824fb-165">Without it, PowerShell uses the default prompt, `PS>`.</span></span>

```powershell
function prompt {
    $color = Get-Random -Min 1 -Max 16
    Write-Host ("PS " + $(Get-Location) +">") -NoNewLine `
     -ForegroundColor $Color
    return " "
}
```

### <a name="saving-the-prompt-function"></a><span data-ttu-id="824fb-166">保存 Prompt 函数</span><span class="sxs-lookup"><span data-stu-id="824fb-166">Saving the Prompt function</span></span>

<span data-ttu-id="824fb-167">与任何函数一样，该 `Prompt` 函数仅存在于当前会话中。</span><span class="sxs-lookup"><span data-stu-id="824fb-167">Like any function, the `Prompt` function exists only in the current session.</span></span> <span data-ttu-id="824fb-168">若要为 `Prompt` 将来的会话保存该函数，请将其添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="824fb-168">To save the `Prompt` function for future sessions, add it to your PowerShell profiles.</span></span> <span data-ttu-id="824fb-169">有关配置文件的详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="824fb-169">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="824fb-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="824fb-170">See also</span></span>

[<span data-ttu-id="824fb-171">Get-Location</span><span class="sxs-lookup"><span data-stu-id="824fb-171">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)

[<span data-ttu-id="824fb-172">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="824fb-172">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="824fb-173">Get-History</span><span class="sxs-lookup"><span data-stu-id="824fb-173">Get-History</span></span>](xref:Microsoft.PowerShell.Core.Get-History)

[<span data-ttu-id="824fb-174">Get-Random</span><span class="sxs-lookup"><span data-stu-id="824fb-174">Get-Random</span></span>](xref:Microsoft.PowerShell.Utility.Get-Random)

[<span data-ttu-id="824fb-175">Write-Host</span><span class="sxs-lookup"><span data-stu-id="824fb-175">Write-Host</span></span>](xref:Microsoft.PowerShell.Utility.Write-Host)

[<span data-ttu-id="824fb-176">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="824fb-176">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="824fb-177">about_Functions</span><span class="sxs-lookup"><span data-stu-id="824fb-177">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="824fb-178">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="824fb-178">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="824fb-179">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="824fb-179">about_Debuggers</span></span>](about_Debuggers.md)

[<span data-ttu-id="824fb-180">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="824fb-180">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

