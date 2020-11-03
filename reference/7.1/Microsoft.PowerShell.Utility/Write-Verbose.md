---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: fab0d14d8f22227b37d0dabd2287a5cdff13cce7
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200554"
---
# <span data-ttu-id="17c5e-103">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="17c5e-103">Write-Verbose</span></span>

## <span data-ttu-id="17c5e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="17c5e-104">SYNOPSIS</span></span>
<span data-ttu-id="17c5e-105">将文本写入详细消息流。</span><span class="sxs-lookup"><span data-stu-id="17c5e-105">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="17c5e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="17c5e-106">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="17c5e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="17c5e-107">DESCRIPTION</span></span>

<span data-ttu-id="17c5e-108">`Write-Verbose`Cmdlet 将文本写入 PowerShell 中的详细消息流。</span><span class="sxs-lookup"><span data-stu-id="17c5e-108">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="17c5e-109">通常，详细消息流用于传递有关命令处理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-109">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="17c5e-110">默认情况下，不显示详细消息流，但你可以通过更改变量的值 `$VerbosePreference` 或在任何命令中使用 **verbose** 通用参数来显示它。</span><span class="sxs-lookup"><span data-stu-id="17c5e-110">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="17c5e-111">示例</span><span class="sxs-lookup"><span data-stu-id="17c5e-111">EXAMPLES</span></span>

### <span data-ttu-id="17c5e-112">示例1：编写状态消息</span><span class="sxs-lookup"><span data-stu-id="17c5e-112">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="17c5e-113">这些命令使用 `Write-Verbose` cmdlet 来显示状态消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-113">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="17c5e-114">默认情况下，不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-114">By default, the message is not displayed.</span></span>

<span data-ttu-id="17c5e-115">第二个命令使用 **verbose** 通用参数，该参数显示任何详细消息，而不考虑变量的值 `$VerbosePreference` 。</span><span class="sxs-lookup"><span data-stu-id="17c5e-115">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="17c5e-116">示例2：设置 $VerbosePreference 并写入状态消息</span><span class="sxs-lookup"><span data-stu-id="17c5e-116">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="17c5e-117">这些命令使用 `Write-Verbose` cmdlet 来显示状态消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-117">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="17c5e-118">默认情况下，不显示此消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-118">By default, the message is not displayed.</span></span>

<span data-ttu-id="17c5e-119">第一个命令将 "Continue" 的值分配给 `$VerbosePreference` 首选项变量。</span><span class="sxs-lookup"><span data-stu-id="17c5e-119">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="17c5e-120">默认值 `SilentlyContinue` 禁止详细消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-120">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="17c5e-121">第二个命令写入详细消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-121">The second command writes a verbose message.</span></span>

## <span data-ttu-id="17c5e-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="17c5e-122">PARAMETERS</span></span>

### <span data-ttu-id="17c5e-123">-Message</span><span class="sxs-lookup"><span data-stu-id="17c5e-123">-Message</span></span>

<span data-ttu-id="17c5e-124">指定要显示的消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-124">Specifies the message to display.</span></span> <span data-ttu-id="17c5e-125">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="17c5e-125">This parameter is required.</span></span> <span data-ttu-id="17c5e-126">还可以通过管道将消息字符串传递给 `Write-Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="17c5e-126">You can also pipe a message string to `Write-Verbose`.</span></span>

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

### <span data-ttu-id="17c5e-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="17c5e-127">CommonParameters</span></span>

<span data-ttu-id="17c5e-128">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="17c5e-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="17c5e-129">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="17c5e-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="17c5e-130">输入</span><span class="sxs-lookup"><span data-stu-id="17c5e-130">INPUTS</span></span>

### <span data-ttu-id="17c5e-131">System.String</span><span class="sxs-lookup"><span data-stu-id="17c5e-131">System.String</span></span>

<span data-ttu-id="17c5e-132">可以通过管道将包含消息的字符串传递给 `Write-Verbose` 。</span><span class="sxs-lookup"><span data-stu-id="17c5e-132">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="17c5e-133">输出</span><span class="sxs-lookup"><span data-stu-id="17c5e-133">OUTPUTS</span></span>

### <span data-ttu-id="17c5e-134">无</span><span class="sxs-lookup"><span data-stu-id="17c5e-134">None</span></span>

<span data-ttu-id="17c5e-135">`Write-Verbose` 仅写入详细消息流。</span><span class="sxs-lookup"><span data-stu-id="17c5e-135">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="17c5e-136">注释</span><span class="sxs-lookup"><span data-stu-id="17c5e-136">NOTES</span></span>

- <span data-ttu-id="17c5e-137">仅在该命令使用 **Verbose** 通用参数时才返回详细消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-137">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="17c5e-138">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="17c5e-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="17c5e-139">在 Windows PowerShell 后台作业和远程命令中， `$VerbosePreference` 作业会话和远程会话中的变量确定默认情况下是否显示详细消息。</span><span class="sxs-lookup"><span data-stu-id="17c5e-139">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="17c5e-140">有关变量的详细信息 `$VerbosePreference` ，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="17c5e-140">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="17c5e-141">相关链接</span><span class="sxs-lookup"><span data-stu-id="17c5e-141">RELATED LINKS</span></span>

[<span data-ttu-id="17c5e-142">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="17c5e-142">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="17c5e-143">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="17c5e-143">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="17c5e-144">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="17c5e-144">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="17c5e-145">写入错误</span><span class="sxs-lookup"><span data-stu-id="17c5e-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="17c5e-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="17c5e-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="17c5e-147">Write-Information</span><span class="sxs-lookup"><span data-stu-id="17c5e-147">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="17c5e-148">Write-Output</span><span class="sxs-lookup"><span data-stu-id="17c5e-148">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="17c5e-149">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="17c5e-149">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="17c5e-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="17c5e-150">Write-Warning</span></span>](Write-Warning.md)