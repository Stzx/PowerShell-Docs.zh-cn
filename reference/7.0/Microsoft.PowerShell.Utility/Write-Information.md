---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: 9fe1e66cbd8ae55e0a26d9702998564dcd7f9450
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "93200535"
---
# <span data-ttu-id="a516b-103">Write-Information</span><span class="sxs-lookup"><span data-stu-id="a516b-103">Write-Information</span></span>

## <span data-ttu-id="a516b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a516b-104">SYNOPSIS</span></span>

<span data-ttu-id="a516b-105">指定 PowerShell 如何处理命令的信息流数据。</span><span class="sxs-lookup"><span data-stu-id="a516b-105">Specifies how PowerShell handles information stream data for a command.</span></span>

## <span data-ttu-id="a516b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a516b-106">SYNTAX</span></span>

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a516b-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a516b-107">DESCRIPTION</span></span>

<span data-ttu-id="a516b-108">`Write-Information`Cmdlet 指定 PowerShell 如何处理命令的信息流数据。</span><span class="sxs-lookup"><span data-stu-id="a516b-108">The `Write-Information` cmdlet specifies how PowerShell handles information stream data for a command.</span></span>

<span data-ttu-id="a516b-109">Windows PowerShell 5.0 引入了一个新的结构化信息流。</span><span class="sxs-lookup"><span data-stu-id="a516b-109">Windows PowerShell 5.0 introduces a new, structured information stream.</span></span> <span data-ttu-id="a516b-110">您可以使用此流在脚本和其调用方或主机应用程序之间传输结构化数据。</span><span class="sxs-lookup"><span data-stu-id="a516b-110">You can use this stream to transmit structured data between a script and its callers or the host application.</span></span>
<span data-ttu-id="a516b-111">`Write-Information` 允许你将信息性消息添加到流，并指定 PowerShell 如何处理命令的信息流数据。</span><span class="sxs-lookup"><span data-stu-id="a516b-111">`Write-Information` lets you add an informational message to the stream, and specify how PowerShell handles information stream data for a command.</span></span> <span data-ttu-id="a516b-112">信息流也适用于 `PowerShell.Streams` 、作业和计划任务。</span><span class="sxs-lookup"><span data-stu-id="a516b-112">Information streams also work for `PowerShell.Streams`, jobs, and scheduled tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="a516b-113">信息流不遵循标准约定，其消息的前缀为 "[Stream Name]："。</span><span class="sxs-lookup"><span data-stu-id="a516b-113">The information stream does not follow the standard convention of prefixing its messages with "[Stream Name]:".</span></span> <span data-ttu-id="a516b-114">这适用于简洁和直观的 cleanliness。</span><span class="sxs-lookup"><span data-stu-id="a516b-114">This was intended for brevity and visual cleanliness.</span></span>

<span data-ttu-id="a516b-115">`$InformationPreference`首选项变量值确定所提供的消息是否在 `Write-Information` 脚本操作中的预期点显示。</span><span class="sxs-lookup"><span data-stu-id="a516b-115">The `$InformationPreference` preference variable value determines whether the message you provide to `Write-Information` is displayed at the expected point in a script's operation.</span></span> <span data-ttu-id="a516b-116">由于此变量的默认值为 `SilentlyContinue` ，因此默认情况下不显示信息性消息。</span><span class="sxs-lookup"><span data-stu-id="a516b-116">Because the default value of this variable is `SilentlyContinue`, by default, informational messages are not shown.</span></span> <span data-ttu-id="a516b-117">如果你不想更改的值 `$InformationPreference` ，则可以通过将 `InformationAction` common 参数添加到你的命令来重写其值。</span><span class="sxs-lookup"><span data-stu-id="a516b-117">If you don't want to change the value of `$InformationPreference`, you can override its value by adding the `InformationAction` common parameter to your command.</span></span> <span data-ttu-id="a516b-118">有关详细信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) 和 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="a516b-118">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) and [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a516b-119">从 Windows PowerShell 5.0 开始， `Write-Host` 是的包装器， `Write-Information` 它允许你使用 `Write-Host` 向信息流发出输出。</span><span class="sxs-lookup"><span data-stu-id="a516b-119">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="a516b-120">这样就可以 **捕获** 或 **抑制** 使用编写的数据， `Write-Host` 同时保留向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="a516b-120">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span> <span data-ttu-id="a516b-121">有关详细信息，请参阅 [写入主机](Write-Host.md)</span><span class="sxs-lookup"><span data-stu-id="a516b-121">For more information see [Write-Host](Write-Host.md)</span></span>

<span data-ttu-id="a516b-122">`Write-Information` 在 PowerShell 1.x 中也是受支持的工作流活动。</span><span class="sxs-lookup"><span data-stu-id="a516b-122">`Write-Information` is also a supported workflow activity in PowerShell 5.x.</span></span>

## <span data-ttu-id="a516b-123">示例</span><span class="sxs-lookup"><span data-stu-id="a516b-123">EXAMPLES</span></span>

### <span data-ttu-id="a516b-124">示例 1：为 Get- results 写入信息</span><span class="sxs-lookup"><span data-stu-id="a516b-124">Example 1: Write information for Get- results</span></span>

<span data-ttu-id="a516b-125">在此示例中，将显示一条信息性消息 "获取功能！"，并在运行该 `Get-WindowsFeature` 命令以查找名称值以 "p" 开头的所有功能。</span><span class="sxs-lookup"><span data-stu-id="a516b-125">In this example, you show an informational message, "Got your features!", after running the `Get-WindowsFeature` command to find all features that have a Name value that starts with 'p'.</span></span>
<span data-ttu-id="a516b-126">由于 `$InformationPreference` 变量仍设置为其默认值，因此 `SilentlyContinue` ，您将添加 `InformationAction` 参数以重写 `$InformationPreference` 该值，并显示消息。</span><span class="sxs-lookup"><span data-stu-id="a516b-126">Because the `$InformationPreference` variable is still set to its default, `SilentlyContinue`, you add the `InformationAction` parameter to override the `$InformationPreference` value, and show the message.</span></span> <span data-ttu-id="a516b-127">`InformationAction`该值将继续，这意味着会显示你的消息，但脚本或命令会继续（如果尚未完成）。</span><span class="sxs-lookup"><span data-stu-id="a516b-127">The `InformationAction` value is Continue, which means that your message is shown, but the script or command continues, if it is not yet finished.</span></span>

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### <span data-ttu-id="a516b-128">示例 2：写入信息并进行标记</span><span class="sxs-lookup"><span data-stu-id="a516b-128">Example 2: Write information and tag it</span></span>

<span data-ttu-id="a516b-129">在此示例中，你将使用 `Write-Information` 来让用户知道他们在运行完当前命令后需要运行另一个命令。</span><span class="sxs-lookup"><span data-stu-id="a516b-129">In this example, you use `Write-Information` to let users know they'll need to run another command after they're done running the current command.</span></span> <span data-ttu-id="a516b-130">该示例将标记 Instructions 添加到信息性消息。</span><span class="sxs-lookup"><span data-stu-id="a516b-130">The example adds the tag Instructions to the informational message.</span></span> <span data-ttu-id="a516b-131">运行此命令之后，如果在信息流中搜索使用 Instructions 标记的消息，则此处指定的消息会处于结果中。</span><span class="sxs-lookup"><span data-stu-id="a516b-131">After running this command, if you search the information stream for messages tagged Instructions, the message specified here would be among the results.</span></span>

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### <span data-ttu-id="a516b-132">示例 3：将信息写入文件</span><span class="sxs-lookup"><span data-stu-id="a516b-132">Example 3: Write information to a file</span></span>

<span data-ttu-id="a516b-133">在此示例中，使用代码将函数中的信息流重定向到。 `Info.txt` `6>`</span><span class="sxs-lookup"><span data-stu-id="a516b-133">In this example, you redirect the information stream in the function to a `Info.txt` using the code `6>`.</span></span> <span data-ttu-id="a516b-134">打开该文件时 `Info.txt` ，你会看到文本 "你想要"。</span><span class="sxs-lookup"><span data-stu-id="a516b-134">When you open the `Info.txt` file, you see the text, "Here you go."</span></span>

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

### <span data-ttu-id="a516b-135">示例4：传递对象以写入信息</span><span class="sxs-lookup"><span data-stu-id="a516b-135">Example 4: Pass object to write information</span></span>

<span data-ttu-id="a516b-136">在此示例中，你可以使用 `Write-Information` 从 `Get-Process` 已通过多个管道的对象输出写入前10个最高的 CPU 使用率进程。</span><span class="sxs-lookup"><span data-stu-id="a516b-136">In this example, you can use `Write-Information` to write the top 10 highest CPU utilization processes from the `Get-Process` object output that has passes through multiple pipelines.</span></span>

```powershell
Get-Process | Sort-Object CPU -Descending |
    Select-Object Id, ProcessName, CPU -First 10 |
        Write-Information -InformationAction Continue
```

```Output
@{Id=12692; ProcessName=chrome; CPU=39431.296875}
@{Id=21292; ProcessName=OUTLOOK; CPU=23991.875}
@{Id=10548; ProcessName=CefSharp.BrowserSubprocess; CPU=20546.203125}
@{Id=312848; ProcessName=Taskmgr; CPU=13173.1875}
@{Id=10848; ProcessName=SnapClient; CPU=7014.265625}
@{Id=9760; ProcessName=Receiver; CPU=6792.359375}
@{Id=12040; ProcessName=Teams; CPU=5605.578125}
@{Id=498388; ProcessName=chrome; CPU=3062.453125}
@{Id=6900; ProcessName=chrome; CPU=2546.9375}
@{Id=9044; ProcessName=explorer; CPU=2358.765625}
```

## <span data-ttu-id="a516b-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a516b-137">PARAMETERS</span></span>

### <span data-ttu-id="a516b-138">-MessageData</span><span class="sxs-lookup"><span data-stu-id="a516b-138">-MessageData</span></span>

<span data-ttu-id="a516b-139">指定要在用户运行脚本或命令时向他们显示的信息性消息。</span><span class="sxs-lookup"><span data-stu-id="a516b-139">Specifies an informational message that you want to display to users as they run a script or command.</span></span> <span data-ttu-id="a516b-140">为获得最佳结果，请将信息性消息用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="a516b-140">For best results, enclose the informational message in quotation marks.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a516b-141">-Tags</span><span class="sxs-lookup"><span data-stu-id="a516b-141">-Tags</span></span>

<span data-ttu-id="a516b-142">指定一个简单的字符串，该字符串可用于对已添加到信息流的消息进行排序和筛选 `Write-Information` 。</span><span class="sxs-lookup"><span data-stu-id="a516b-142">Specifies a simple string that you can use to sort and filter messages that you have added to the information stream with `Write-Information`.</span></span> <span data-ttu-id="a516b-143">此参数的工作方式类似于中的 **标记** 参数 `New-ModuleManifest` 。</span><span class="sxs-lookup"><span data-stu-id="a516b-143">This parameter works similarly to the **Tags** parameter in `New-ModuleManifest`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a516b-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a516b-144">CommonParameters</span></span>

<span data-ttu-id="a516b-145">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a516b-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a516b-146">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a516b-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a516b-147">输入</span><span class="sxs-lookup"><span data-stu-id="a516b-147">INPUTS</span></span>

### <span data-ttu-id="a516b-148">System.Object</span><span class="sxs-lookup"><span data-stu-id="a516b-148">System.Object</span></span>

<span data-ttu-id="a516b-149">`Write-Information` 接受要传递到信息流的管道对象。</span><span class="sxs-lookup"><span data-stu-id="a516b-149">`Write-Information` accepts piped objects to pass to the information stream.</span></span>

## <span data-ttu-id="a516b-150">输出</span><span class="sxs-lookup"><span data-stu-id="a516b-150">OUTPUTS</span></span>

### <span data-ttu-id="a516b-151">System.Management.Automation.InformationRecord</span><span class="sxs-lookup"><span data-stu-id="a516b-151">System.Management.Automation.InformationRecord</span></span>

## <span data-ttu-id="a516b-152">注释</span><span class="sxs-lookup"><span data-stu-id="a516b-152">NOTES</span></span>

## <span data-ttu-id="a516b-153">相关链接</span><span class="sxs-lookup"><span data-stu-id="a516b-153">RELATED LINKS</span></span>

[<span data-ttu-id="a516b-154">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="a516b-154">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="a516b-155">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="a516b-155">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="a516b-156">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a516b-156">about_CommonParameters</span></span>](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[<span data-ttu-id="a516b-157">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="a516b-157">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="a516b-158">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="a516b-158">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="a516b-159">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="a516b-159">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="a516b-160">Write-Host</span><span class="sxs-lookup"><span data-stu-id="a516b-160">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="a516b-161">Write-Information</span><span class="sxs-lookup"><span data-stu-id="a516b-161">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="a516b-162">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="a516b-162">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="a516b-163">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="a516b-163">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="a516b-164">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="a516b-164">Write-Warning</span></span>](Write-Warning.md)

[<span data-ttu-id="a516b-165">Write-Output</span><span class="sxs-lookup"><span data-stu-id="a516b-165">Write-Output</span></span>](Write-Output.md)
