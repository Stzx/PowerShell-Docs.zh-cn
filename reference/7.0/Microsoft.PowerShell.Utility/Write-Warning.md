---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-warning?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Warning
ms.openlocfilehash: dde8e497159e3e9a7bf63010bc12566d68d8de0f
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200538"
---
# <span data-ttu-id="58672-103">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="58672-103">Write-Warning</span></span>

## <span data-ttu-id="58672-104">摘要</span><span class="sxs-lookup"><span data-stu-id="58672-104">SYNOPSIS</span></span>
<span data-ttu-id="58672-105">写入一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="58672-105">Writes a warning message.</span></span>

## <span data-ttu-id="58672-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="58672-106">SYNTAX</span></span>

```
Write-Warning [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="58672-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="58672-107">DESCRIPTION</span></span>

<span data-ttu-id="58672-108">`Write-Warning`Cmdlet 将向 PowerShell 主机写入一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="58672-108">The `Write-Warning` cmdlet writes a warning message to the PowerShell host.</span></span> <span data-ttu-id="58672-109">对警告的响应取决于用户的 `$WarningPreference` 变量值和 **WarningAction** 通用参数的使用情况。</span><span class="sxs-lookup"><span data-stu-id="58672-109">The response to the warning depends on the value of the user's `$WarningPreference` variable and the use of the **WarningAction** common parameter.</span></span>

## <span data-ttu-id="58672-110">示例</span><span class="sxs-lookup"><span data-stu-id="58672-110">EXAMPLES</span></span>

### <span data-ttu-id="58672-111">示例 1：写入警告消息</span><span class="sxs-lookup"><span data-stu-id="58672-111">Example 1: Write a warning message</span></span>

<span data-ttu-id="58672-112">此命令显示消息“WARNING: This is only a test warning”。</span><span class="sxs-lookup"><span data-stu-id="58672-112">This command displays the message "WARNING: This is only a test warning."</span></span>

```powershell
Write-Warning "This is only a test warning."
```

### <span data-ttu-id="58672-113">示例 2：将字符串传递给 Write-Warning</span><span class="sxs-lookup"><span data-stu-id="58672-113">Example 2: Pass a string to Write-Warning</span></span>

<span data-ttu-id="58672-114">此命令显示可以使用管道运算符 (`|`) 将字符串发送到 `Write-Warning` 。</span><span class="sxs-lookup"><span data-stu-id="58672-114">This command shows that you can use a pipeline operator (`|`) to send a string to `Write-Warning`.</span></span>
<span data-ttu-id="58672-115">你可以将字符串保存在变量中，如下面的命令中所示，或直接通过管道将字符串传递给 `Write-Warning` 。</span><span class="sxs-lookup"><span data-stu-id="58672-115">You can save the string in a variable, as shown in this command, or pipe the string directly to `Write-Warning`.</span></span>

```powershell
$w = "This is only a test warning."
$w | Write-Warning
```

### <span data-ttu-id="58672-116">示例 3：设置 $WarningPreference 变量并写入警告</span><span class="sxs-lookup"><span data-stu-id="58672-116">Example 3: Set the $WarningPreference variable and write a warning</span></span>

<span data-ttu-id="58672-117">此示例显示了对命令的值的影响 `$WarningPreference` `Write-Warning` 。</span><span class="sxs-lookup"><span data-stu-id="58672-117">This example shows the effect of the value of the `$WarningPreference` variable on a `Write-Warning` command.</span></span>

```powershell
PS> $WarningPreference
Continue
PS> Write-Warning "This is only a test warning."
This is only a test warning.
PS> $WarningPreference = "SilentlyContinue"
PS> Write-Warning "This is only a test warning."
PS> $WarningPreference = "Stop"
PS> Write-Warning "This is only a test warning."
WARNING: This is only a test message.
Write-Warning : Command execution stopped because the shell variable "WarningPreference" is set to Stop.
At line:1 char:14
     + Write-Warning <<<<  "This is only a test message."
```

<span data-ttu-id="58672-118">第一个命令显示变量的默认值 `$WarningPreference` ，即 `Continue` 。</span><span class="sxs-lookup"><span data-stu-id="58672-118">The first command displays the default value of the `$WarningPreference` variable, which is `Continue`.</span></span> <span data-ttu-id="58672-119">因此，当你编写一条警告时，将显示警告消息，并且继续执行。</span><span class="sxs-lookup"><span data-stu-id="58672-119">As a result, when you write a warning, the warning message is displayed and execution continues.</span></span>

<span data-ttu-id="58672-120">更改变量的值时 `$WarningPreference` ，该命令的效果将 `Write-Warning` 再次更改。</span><span class="sxs-lookup"><span data-stu-id="58672-120">When you change the value of the `$WarningPreference` variable, the effect of the `Write-Warning` command changes again.</span></span> <span data-ttu-id="58672-121">值为将 `SilentlyContinue` 禁止显示警告。</span><span class="sxs-lookup"><span data-stu-id="58672-121">A value of `SilentlyContinue` suppresses the warning.</span></span> <span data-ttu-id="58672-122">值 `Stop` 显示警告，然后停止执行命令。</span><span class="sxs-lookup"><span data-stu-id="58672-122">A value of `Stop` displays the warning and then stops execution of the command.</span></span>

<span data-ttu-id="58672-123">有关变量的详细信息 `$WarningPreference` ，请参阅 [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="58672-123">For more information about the `$WarningPreference` variable, see [about_Preference_Variables](../Microsoft.Powershell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="58672-124">示例 4：设置 WarningAction 参数并写入警告</span><span class="sxs-lookup"><span data-stu-id="58672-124">Example 4: Set the WarningAction parameter and write a warning</span></span>

<span data-ttu-id="58672-125">此示例演示 **WarningAction** 通用参数对命令的影响 `Write-Warning` 。</span><span class="sxs-lookup"><span data-stu-id="58672-125">This example shows the effect of the **WarningAction** common parameter on a `Write-Warning` command.</span></span> <span data-ttu-id="58672-126">可以将 **WarningAction** 通用参数与任何 cmdlet 一起使用，以确定 PowerShell 如何响应该命令生成的警告。</span><span class="sxs-lookup"><span data-stu-id="58672-126">You can use the **WarningAction** common parameter with any cmdlet to determine how PowerShell responds to warnings resulting from that command.</span></span> <span data-ttu-id="58672-127">**WarningAction** 通用参数会重写 `$WarningPreference` 该特定命令的的值。</span><span class="sxs-lookup"><span data-stu-id="58672-127">The **WarningAction** common parameter overrides the value of the `$WarningPreference` only for that particular command.</span></span>

```powershell
PS> Write-Warning "This is only a test warning." -WarningAction Inquire
WARNING: This is only a test warning.
Confirm
Continue with this operation?
 [Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="58672-128">此命令使用 `Write-Warning` cmdlet 显示警告。</span><span class="sxs-lookup"><span data-stu-id="58672-128">This command uses the `Write-Warning` cmdlet to display a warning.</span></span> <span data-ttu-id="58672-129">值为 Inquire 的 WarningAction  通用参数指示系统在该命令显示警告时提示用户。</span><span class="sxs-lookup"><span data-stu-id="58672-129">The **WarningAction** common parameter with a value of Inquire directs the system to prompt the user when the command displays a warning.</span></span>

<span data-ttu-id="58672-130">有关 **WarningAction** 通用参数的详细信息，请参阅 [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="58672-130">For more information about the **WarningAction** common parameter, see [about_CommonParameters](../Microsoft.Powershell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="58672-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="58672-131">PARAMETERS</span></span>

### <span data-ttu-id="58672-132">-Message</span><span class="sxs-lookup"><span data-stu-id="58672-132">-Message</span></span>
<span data-ttu-id="58672-133">指定警告消息。</span><span class="sxs-lookup"><span data-stu-id="58672-133">Specifies the warning message.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="58672-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="58672-134">CommonParameters</span></span>

<span data-ttu-id="58672-135">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="58672-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="58672-136">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="58672-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="58672-137">输入</span><span class="sxs-lookup"><span data-stu-id="58672-137">INPUTS</span></span>

### <span data-ttu-id="58672-138">System.String</span><span class="sxs-lookup"><span data-stu-id="58672-138">System.String</span></span>

<span data-ttu-id="58672-139">可以通过管道将包含警告的字符串传递给 `Write-Warning` 。</span><span class="sxs-lookup"><span data-stu-id="58672-139">You can pipe a string that contains the warning to `Write-Warning`.</span></span>

## <span data-ttu-id="58672-140">输出</span><span class="sxs-lookup"><span data-stu-id="58672-140">OUTPUTS</span></span>

### <span data-ttu-id="58672-141">无</span><span class="sxs-lookup"><span data-stu-id="58672-141">None</span></span>

<span data-ttu-id="58672-142">`Write-Warning` 仅写入到警告流。</span><span class="sxs-lookup"><span data-stu-id="58672-142">`Write-Warning` writes only to the warning stream.</span></span> <span data-ttu-id="58672-143">它不生成任何其他输出。</span><span class="sxs-lookup"><span data-stu-id="58672-143">It does not generate any other output.</span></span>

## <span data-ttu-id="58672-144">注释</span><span class="sxs-lookup"><span data-stu-id="58672-144">NOTES</span></span>

<span data-ttu-id="58672-145">变量的默认值 `$WarningPreference` 为 `Continue` ，它显示警告，然后继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="58672-145">The default value for the `$WarningPreference` variable is `Continue`, which displays the warning and then continues executing the command.</span></span> <span data-ttu-id="58672-146">若要确定首选项变量（如）的有效值 `$WarningPreference` ，请将其设置为随机字符的字符串，例如 "abc"。</span><span class="sxs-lookup"><span data-stu-id="58672-146">To determine valid values for a preference variable such as `$WarningPreference`, set it to a string of random characters, such as "abc".</span></span> <span data-ttu-id="58672-147">生成的错误消息将列出有效值。</span><span class="sxs-lookup"><span data-stu-id="58672-147">The resulting error message lists the valid values.</span></span>

## <span data-ttu-id="58672-148">相关链接</span><span class="sxs-lookup"><span data-stu-id="58672-148">RELATED LINKS</span></span>

[<span data-ttu-id="58672-149">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="58672-149">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="58672-150">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="58672-150">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="58672-151">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="58672-151">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="58672-152">写入错误</span><span class="sxs-lookup"><span data-stu-id="58672-152">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="58672-153">Write-Host</span><span class="sxs-lookup"><span data-stu-id="58672-153">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="58672-154">Write-Information</span><span class="sxs-lookup"><span data-stu-id="58672-154">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="58672-155">Write-Output</span><span class="sxs-lookup"><span data-stu-id="58672-155">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="58672-156">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="58672-156">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="58672-157">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="58672-157">Write-Verbose</span></span>](Write-Verbose.md)
