---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/unregister-pssessionconfiguration?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSSessionConfiguration
ms.openlocfilehash: f9cc2f83ec0fca1c957c670e13ac7b455c322adb
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345335"
---
# <span data-ttu-id="47db6-103">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-103">Unregister-PSSessionConfiguration</span></span>

## <span data-ttu-id="47db6-104">摘要</span><span class="sxs-lookup"><span data-stu-id="47db6-104">SYNOPSIS</span></span>
<span data-ttu-id="47db6-105">从计算机中删除已注册的会话配置。</span><span class="sxs-lookup"><span data-stu-id="47db6-105">Deletes registered session configurations from the computer.</span></span>

## <span data-ttu-id="47db6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47db6-106">SYNTAX</span></span>

```
Unregister-PSSessionConfiguration [-Name] <String> [-Force] [-NoServiceRestart] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="47db6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="47db6-107">DESCRIPTION</span></span>

<span data-ttu-id="47db6-108">`Unregister-PSSessionConfiguration`Cmdlet 将从计算机中删除已注册的会话配置。</span><span class="sxs-lookup"><span data-stu-id="47db6-108">The `Unregister-PSSessionConfiguration` cmdlet deletes registered session configurations from the computer.</span></span> <span data-ttu-id="47db6-109">此 cmdlet 旨在供系统管理员管理用户的自定义会话配置。</span><span class="sxs-lookup"><span data-stu-id="47db6-109">This cmdlet is designed for system administrators to manage customized session configurations for users.</span></span>

<span data-ttu-id="47db6-110">若要使更改生效，请 `Unregister-PSSessionConfiguration` 重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="47db6-110">To make the change effective, `Unregister-PSSessionConfiguration` restarts the **WinRM** service.</span></span> <span data-ttu-id="47db6-111">若要防止重启，请指定 NoServiceRestart 参数。</span><span class="sxs-lookup"><span data-stu-id="47db6-111">To prevent the restart, specify the **NoServiceRestart** parameter.</span></span>

<span data-ttu-id="47db6-112">如果意外删除 **了默认的** **microsoft.powershell32** 会话配置，请使用 `Enable-PSRemoting` cmdlet 来还原它们。</span><span class="sxs-lookup"><span data-stu-id="47db6-112">If you accidentally delete the default **Microsoft.PowerShell** or **Microsoft.PowerShell32** session configurations, use the `Enable-PSRemoting` cmdlet to restore them.</span></span> <span data-ttu-id="47db6-113">有关详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="47db6-113">For more information, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="47db6-114">示例</span><span class="sxs-lookup"><span data-stu-id="47db6-114">EXAMPLES</span></span>

### <span data-ttu-id="47db6-115">示例 1：删除会话配置</span><span class="sxs-lookup"><span data-stu-id="47db6-115">Example 1: Delete a session configuration</span></span>

<span data-ttu-id="47db6-116">此示例将从计算机中删除 **MaintenanceShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="47db6-116">This example deletes the **MaintenanceShell** session configuration from the computer.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name "MaintenanceShell"
```

### <span data-ttu-id="47db6-117">示例 2：删除会话配置并重启 WinRM 服务</span><span class="sxs-lookup"><span data-stu-id="47db6-117">Example 2: Delete a session configuration and restart the WinRM service</span></span>

<span data-ttu-id="47db6-118">在此示例中，我们将删除 **MaintenanceShell** 配置并重新启动 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="47db6-118">In this example, we delete the **MaintenanceShell** configuration and restart the WinRM service.</span></span> <span data-ttu-id="47db6-119">**Force** 参数取消所有用户消息，以便在不提示的情况下重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="47db6-119">The **Force** parameter suppresses all user messages to restart the **WinRM** service without prompting.</span></span>

```powershell
Unregister-PSSessionConfiguration -Name MaintenanceShell -Force
```

### <span data-ttu-id="47db6-120">示例 3：删除所有会话配置</span><span class="sxs-lookup"><span data-stu-id="47db6-120">Example 3: Delete all session configurations</span></span>

<span data-ttu-id="47db6-121">此示例显示了删除计算机上的所有会话配置的两种方法。</span><span class="sxs-lookup"><span data-stu-id="47db6-121">This examples show two ways to delete all the session configurations on the computer.</span></span> <span data-ttu-id="47db6-122">这两个命令具有相同的效果，并且可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="47db6-122">Both commands have the same effect and can be used interchangeably.</span></span>

```
Unregister-PSSessionConfiguration -Name *
Get-PSSessionConfiguration -Name * | Unregister-PSSessionConfiguration
```

### <span data-ttu-id="47db6-123">示例 4：注销（不重启）</span><span class="sxs-lookup"><span data-stu-id="47db6-123">Example 4: Unregister without a restart</span></span>

<span data-ttu-id="47db6-124">此示例显示了使用 **NoServiceRestart** 参数防止服务重新启动，从而中断计算机上的任何会话的影响。</span><span class="sxs-lookup"><span data-stu-id="47db6-124">This example shows the effect of using the **NoServiceRestart** parameter to prevent a service restart that would disrupt any sessions on the computer.</span></span>

```
PS> Unregister-PSSessionConfiguration -Name "MaintenanceShell" -NoServiceRestart
PS> Get-PSSessionConfiguration -Name "MaintenanceShell"

Get-PSSessionConfiguration -Name MaintenanceShell : No Session Configuration matches criteria "MaintenanceShell".
+ CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
+ FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

PS> New-PSSession -ConfigurationName "MaintenanceShell"

Id Name      ComputerName    State    Configuration         Availability
-- ----      ------------    -----    -------------         ------------
1 Session1  localhost       Opened   MaintenanceShell      Available

PS> Restart-Service winrm
PS> New-PSSession -ConfigurationName MaintenanceShell

[localhost] Connecting to remote server failed with the following error message :
 The WS-Management service cannot process the request.
 The resource URI (http://schemas.microsoft.com/powershell/MaintenanceShell) was not found in the WS-Management catalog.
 The catalog contains the metadata that describes resources, or logical endpoints.
 For more information, see the about_Remote_Troubleshooting Help topic.
 + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
 + FullyQualifiedErrorId : PSSessionOpenFailed
```

<span data-ttu-id="47db6-125">`Unregister-PSSessionConfiguration`删除 **MaintenanceShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="47db6-125">The `Unregister-PSSessionConfiguration` deletes the **MaintenanceShell** session configuration.</span></span>
<span data-ttu-id="47db6-126">但是，因为该命令使用 NoServiceRestart 参数，所以不会重启 **WinRM** 服务，而且更改尚未完全起效。</span><span class="sxs-lookup"><span data-stu-id="47db6-126">However, because the command uses the **NoServiceRestart** parameter, the **WinRM** service is not restarted and the change is not yet completely effective.</span></span>

<span data-ttu-id="47db6-127">接下来， `Get-PSSessionConfiguration` 尝试获取 **MaintenanceShell** 会话。</span><span class="sxs-lookup"><span data-stu-id="47db6-127">Next, the `Get-PSSessionConfiguration` tries to get the **MaintenanceShell** session.</span></span> <span data-ttu-id="47db6-128">由于已从 WS-Management 资源表中删除该会话，因此 `Get-PSSessionConfiguration` 无法将其返回。</span><span class="sxs-lookup"><span data-stu-id="47db6-128">Because the session has been removed from the WS-Management resource table, `Get-PSSessionConfiguration` cannot return it.</span></span>

<span data-ttu-id="47db6-129">`New-PSSession`Cmdlet 使用 **MaintenanceShell** 配置创建会话。</span><span class="sxs-lookup"><span data-stu-id="47db6-129">The `New-PSSession` cmdlet creates a session using the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="47db6-130">该命令执行成功。</span><span class="sxs-lookup"><span data-stu-id="47db6-130">The command succeeds.</span></span> <span data-ttu-id="47db6-131">接下来，重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="47db6-131">Next, we restart the **WinRM** service.</span></span>

<span data-ttu-id="47db6-132">最后，该 `New-PSSession` cmdlet 会尝试创建使用 **MaintenanceShell** 配置的会话。</span><span class="sxs-lookup"><span data-stu-id="47db6-132">Finally, the `New-PSSession` cmdlet tries to create a session that uses the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="47db6-133">这次会话失败，因为在重新启动 WinRM 服务时已删除 **MaintenanceShell** 配置。</span><span class="sxs-lookup"><span data-stu-id="47db6-133">This time, the session fails because the **MaintenanceShell** configuration was deleted when the WinRM service restarted.</span></span>

## <span data-ttu-id="47db6-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47db6-134">PARAMETERS</span></span>

### <span data-ttu-id="47db6-135">-Force</span><span class="sxs-lookup"><span data-stu-id="47db6-135">-Force</span></span>

<span data-ttu-id="47db6-136">指示 cmdlet 不提示进行确认，并且将在无提示的情况下重启 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="47db6-136">Indicates that the cmdlet does not prompt you for confirmation, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="47db6-137">重新启动服务可使配置更改生效。</span><span class="sxs-lookup"><span data-stu-id="47db6-137">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="47db6-138">若要阻止重新启动并取消重新启动提示，请使用 **NoServiceRestart** 参数。</span><span class="sxs-lookup"><span data-stu-id="47db6-138">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47db6-139">-Name</span><span class="sxs-lookup"><span data-stu-id="47db6-139">-Name</span></span>

<span data-ttu-id="47db6-140">指定要删除的会话配置的名称。</span><span class="sxs-lookup"><span data-stu-id="47db6-140">Specifies the names of the session configurations to delete.</span></span> <span data-ttu-id="47db6-141">输入一个会话配置名称或配置名称模式。</span><span class="sxs-lookup"><span data-stu-id="47db6-141">Enter one session configuration name or a configuration name pattern.</span></span> <span data-ttu-id="47db6-142">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="47db6-142">Wildcard characters are permitted.</span></span> <span data-ttu-id="47db6-143">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="47db6-143">This parameter is required.</span></span>

<span data-ttu-id="47db6-144">还可以通过管道将会话配置传递给 `Unregister-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="47db6-144">You can also pipe a session configurations to `Unregister-PSSessionConfiguration`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="47db6-145">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="47db6-145">-NoServiceRestart</span></span>

<span data-ttu-id="47db6-146">指示此 cmdlet 不重启 **WinRM** 服务，并且禁止提示重启该服务。</span><span class="sxs-lookup"><span data-stu-id="47db6-146">Indicates that this cmdlet does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="47db6-147">默认情况下，当你运行 `Unregister-PSSessionConfiguration` 命令时，系统将提示你重新启动 **WinRM** 服务以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="47db6-147">By default, when you run an `Unregister-PSSessionConfiguration` command, you are prompted to restart the **WinRM** service to make the change effective.</span></span> <span data-ttu-id="47db6-148">在重新启动 **WinRM** 服务之前，用户仍然可以使用未注册的会话配置，即使 `Get-PSSessionConfiguration` 找不到它。</span><span class="sxs-lookup"><span data-stu-id="47db6-148">Until the **WinRM** service is restarted, users can still use the unregistered session configuration, even though `Get-PSSessionConfiguration` does not find it.</span></span>

<span data-ttu-id="47db6-149">若要在无提示的情况下重启 **WinRM** 服务，请指定 Force 参数。</span><span class="sxs-lookup"><span data-stu-id="47db6-149">To restart the **WinRM** service without prompting, specify the **Force** parameter.</span></span> <span data-ttu-id="47db6-150">若要手动重新启动 **WinRM** 服务，请使用 `Restart-Service` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="47db6-150">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47db6-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="47db6-151">-Confirm</span></span>

<span data-ttu-id="47db6-152">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="47db6-152">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47db6-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="47db6-153">-WhatIf</span></span>

<span data-ttu-id="47db6-154">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="47db6-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="47db6-155">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="47db6-155">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="47db6-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="47db6-156">CommonParameters</span></span>

<span data-ttu-id="47db6-157">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="47db6-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47db6-158">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="47db6-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="47db6-159">输入</span><span class="sxs-lookup"><span data-stu-id="47db6-159">INPUTS</span></span>

### <span data-ttu-id="47db6-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-160">Microsoft.PowerShell.Commands.PSSessionConfigurationCommands#PSSessionConfiguration</span></span>

<span data-ttu-id="47db6-161">你可以通过管道将会话配置对象传递 `Get-PSSessionConfiguration` 给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="47db6-161">You can pipe a session configuration object from `Get-PSSessionConfiguration` to this cmdlet.</span></span>

## <span data-ttu-id="47db6-162">输出</span><span class="sxs-lookup"><span data-stu-id="47db6-162">OUTPUTS</span></span>

### <span data-ttu-id="47db6-163">None</span><span class="sxs-lookup"><span data-stu-id="47db6-163">None</span></span>

<span data-ttu-id="47db6-164">此 cmdlet 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="47db6-164">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="47db6-165">注释</span><span class="sxs-lookup"><span data-stu-id="47db6-165">NOTES</span></span>

<span data-ttu-id="47db6-166">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="47db6-166">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="47db6-167">若要运行此 cmdlet，必须使用 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="47db6-167">To run this cmdlet you must start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="47db6-168">相关链接</span><span class="sxs-lookup"><span data-stu-id="47db6-168">RELATED LINKS</span></span>

[<span data-ttu-id="47db6-169">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-169">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="47db6-170">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-170">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="47db6-171">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-171">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="47db6-172">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="47db6-172">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="47db6-173">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="47db6-173">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="47db6-174">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-174">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="47db6-175">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-175">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="47db6-176">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="47db6-176">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="47db6-177">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db6-177">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="47db6-178">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="47db6-178">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="47db6-179">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="47db6-179">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="47db6-180">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="47db6-180">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
