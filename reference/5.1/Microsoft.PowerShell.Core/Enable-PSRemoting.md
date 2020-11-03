---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 07/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSRemoting
ms.openlocfilehash: 0c8c386ab376afde3d15fcd29b3f653b3f738f63
ms.sourcegitcommit: 0e0f45d0d8deb8c9088a4f4a32218edde052b686
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "93198940"
---
# <span data-ttu-id="66621-103">Enable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="66621-103">Enable-PSRemoting</span></span>

## <span data-ttu-id="66621-104">摘要</span><span class="sxs-lookup"><span data-stu-id="66621-104">SYNOPSIS</span></span>
<span data-ttu-id="66621-105">将计算机配置为接收远程命令。</span><span class="sxs-lookup"><span data-stu-id="66621-105">Configures the computer to receive remote commands.</span></span>

## <span data-ttu-id="66621-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66621-106">SYNTAX</span></span>

```
Enable-PSRemoting [-Force] [-SkipNetworkProfileCheck] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="66621-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66621-107">DESCRIPTION</span></span>

<span data-ttu-id="66621-108">`Enable-PSRemoting`Cmdlet 将计算机配置为接收使用 WS-Management 技术发送的 PowerShell 远程命令。</span><span class="sxs-lookup"><span data-stu-id="66621-108">The `Enable-PSRemoting` cmdlet configures the computer to receive PowerShell remote commands that are sent by using the WS-Management technology.</span></span>

<span data-ttu-id="66621-109">默认情况下，在 Windows Server 2012 上启用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="66621-109">PowerShell remoting is enabled by default on Windows Server 2012.</span></span> <span data-ttu-id="66621-110">你可以使用 `Enable-PSRemoting` 在其他受支持的 windows 版本上启用 PowerShell 远程处理，并且在 Windows Server 2012 上重新启用远程处理（如果它已禁用）。</span><span class="sxs-lookup"><span data-stu-id="66621-110">You can use `Enable-PSRemoting` to enable PowerShell remoting on other supported versions of Windows and to re-enable remoting on Windows Server 2012 if it becomes disabled.</span></span>

<span data-ttu-id="66621-111">只需在将接收命令的每台计算机上运行一次此命令。</span><span class="sxs-lookup"><span data-stu-id="66621-111">You have to run this command only one time on each computer that will receive commands.</span></span> <span data-ttu-id="66621-112">不需要在仅发送命令的计算机上运行它。</span><span class="sxs-lookup"><span data-stu-id="66621-112">You do not have to run it on computers that only send commands.</span></span> <span data-ttu-id="66621-113">由于配置启动侦听器，因此只需在需要的位置运行侦听器。</span><span class="sxs-lookup"><span data-stu-id="66621-113">Because the configuration starts listeners, it is prudent to run it only where it is needed.</span></span>

<span data-ttu-id="66621-114">从 PowerShell 3.0 开始， `Enable-PSRemoting` 当计算机位于公用网络上时，该 cmdlet 可在客户端版本的 Windows 上启用 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="66621-114">Beginning in PowerShell 3.0, the `Enable-PSRemoting` cmdlet can enable PowerShell remoting on client versions of Windows when the computer is on a public network.</span></span> <span data-ttu-id="66621-115">有关详细信息，请参阅 **SkipNetworkProfileCheck** 参数的说明。</span><span class="sxs-lookup"><span data-stu-id="66621-115">For more information, see the description of the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="66621-116">`Enable-PSRemoting`Cmdlet 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66621-116">The `Enable-PSRemoting` cmdlet performs the following operations:</span></span>

- <span data-ttu-id="66621-117">运行 [set-wsmanquickconfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet，该 cmdlet 将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="66621-117">Runs the [Set-WSManQuickConfig](../Microsoft.WSMan.Management/Set-WSManQuickConfig.md) cmdlet, which performs the following tasks:</span></span>
  - <span data-ttu-id="66621-118">启动 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="66621-118">Starts the WinRM service.</span></span>
  - <span data-ttu-id="66621-119">将 WinRM 服务上的启动类型设置为自动。</span><span class="sxs-lookup"><span data-stu-id="66621-119">Sets the startup type on the WinRM service to Automatic.</span></span>
  - <span data-ttu-id="66621-120">创建一个可接受任何 IP 地址上的请求的侦听器。</span><span class="sxs-lookup"><span data-stu-id="66621-120">Creates a listener to accept requests on any IP address.</span></span>
  - <span data-ttu-id="66621-121">启用 WS-Management 通信的防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="66621-121">Enables a firewall exception for WS-Management communications.</span></span>
  - <span data-ttu-id="66621-122">如果尚未注册，则注册 **Microsoft powershell** 和 **microsoft powershell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="66621-122">Registers the **Microsoft.PowerShell** and **Microsoft.PowerShell.Workflow** session configurations, if it they are not already registered.</span></span>
  - <span data-ttu-id="66621-123">注册64位计算机上的 **microsoft.powershell32** 会话配置（如果尚未注册）。</span><span class="sxs-lookup"><span data-stu-id="66621-123">Registers the **Microsoft.PowerShell32** session configuration on 64-bit computers, if it is not already registered.</span></span>
  - <span data-ttu-id="66621-124">启用所有会话配置。</span><span class="sxs-lookup"><span data-stu-id="66621-124">Enables all session configurations.</span></span>
  - <span data-ttu-id="66621-125">将所有会话配置的安全描述符更改为允许远程访问。</span><span class="sxs-lookup"><span data-stu-id="66621-125">Changes the security descriptor of all session configurations to allow remote access.</span></span>
- <span data-ttu-id="66621-126">重新启动 WinRM 服务以使上述更改生效。</span><span class="sxs-lookup"><span data-stu-id="66621-126">Restarts the WinRM service to make the preceding changes effective.</span></span>

<span data-ttu-id="66621-127">若要在 Windows 平台上运行此 cmdlet，请使用 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="66621-127">To run this cmdlet on the Windows platform, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="66621-128">此功能不适用于 Linux 或 MacOS 版本的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="66621-128">This does not apply to Linux or MacOS versions of PowerShell.</span></span>

> [!CAUTION]
> <span data-ttu-id="66621-129">在同时具有 PowerShell 3.0 和 PowerShell 2.0 的系统上，不要使用 PowerShell 2.0 来运行 `Enable-PSRemoting` 和 `Disable-PSRemoting` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66621-129">On systems that have both PowerShell 3.0 and PowerShell 2.0, do not use PowerShell 2.0 to run the `Enable-PSRemoting` and `Disable-PSRemoting` cmdlets.</span></span> <span data-ttu-id="66621-130">这些命令可能看起来是成功的，但并未正确配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="66621-130">The commands might appear to succeed, but the remoting is not configured correctly.</span></span> <span data-ttu-id="66621-131">远程命令和更高版本尝试启用和禁用远程处理可能会失败。</span><span class="sxs-lookup"><span data-stu-id="66621-131">Remote commands and later attempts to enable and disable remoting, are likely to fail.</span></span>

## <span data-ttu-id="66621-132">示例</span><span class="sxs-lookup"><span data-stu-id="66621-132">EXAMPLES</span></span>

### <span data-ttu-id="66621-133">示例1：将计算机配置为接收远程命令</span><span class="sxs-lookup"><span data-stu-id="66621-133">Example 1: Configure a computer to receive remote commands</span></span>

<span data-ttu-id="66621-134">此命令将计算机配置为接收远程命令。</span><span class="sxs-lookup"><span data-stu-id="66621-134">This command configures the computer to receive remote commands.</span></span>

```powershell
Enable-PSRemoting
```

### <span data-ttu-id="66621-135">示例2：将计算机配置为在没有确认提示的情况下接收远程命令</span><span class="sxs-lookup"><span data-stu-id="66621-135">Example 2: Configure a computer to receive remote commands without a confirmation prompt</span></span>

<span data-ttu-id="66621-136">此命令将计算机配置为接收远程命令。</span><span class="sxs-lookup"><span data-stu-id="66621-136">This command configures the computer to receive remote commands.</span></span>
<span data-ttu-id="66621-137">**Force** 参数取消用户提示。</span><span class="sxs-lookup"><span data-stu-id="66621-137">The **Force** parameter suppresses the user prompts.</span></span>

```powershell
Enable-PSRemoting -Force
```

### <span data-ttu-id="66621-138">示例3：允许在客户端上进行远程访问</span><span class="sxs-lookup"><span data-stu-id="66621-138">Example 3: Allow remote access on clients</span></span>

<span data-ttu-id="66621-139">此示例演示如何允许在客户端版本的 Windows 操作系统上从公共网络进行远程访问。</span><span class="sxs-lookup"><span data-stu-id="66621-139">This example shows how to allow remote access from public networks on client versions of the Windows operating system.</span></span> <span data-ttu-id="66621-140">不同版本的 Windows 的防火墙规则名称可能不同。</span><span class="sxs-lookup"><span data-stu-id="66621-140">The name of the firewall rule can be different for different versions of Windows.</span></span>
<span data-ttu-id="66621-141">使用 `Get-NetFirewallRule` 可查看规则列表。</span><span class="sxs-lookup"><span data-stu-id="66621-141">Use `Get-NetFirewallRule` to see a list of rules.</span></span> <span data-ttu-id="66621-142">启用防火墙规则之前，请查看规则中的安全设置，以验证配置是否适合您的环境。</span><span class="sxs-lookup"><span data-stu-id="66621-142">Before enabling the firewall rule, view the security settings in the rule to verify that the configuration is appropriate for your environment.</span></span>

```powershell
Get-NetFirewallRule -Name 'WINRM*' | Select-Object Name
```

```Output
Name
----
WINRM-HTTP-In-TCP-NoScope
WINRM-HTTP-In-TCP
WINRM-HTTP-Compat-In-TCP-NoScope
WINRM-HTTP-Compat-In-TCP
```

```powershell
Enable-PSRemoting -SkipNetworkProfileCheck -Force
Set-NetFirewallRule -Name 'WINRM-HTTP-In-TCP' -RemoteAddress Any
```

<span data-ttu-id="66621-143">默认情况下， `Enable-PSRemoting` 会创建允许从专用网络和域网络进行远程访问的网络规则。</span><span class="sxs-lookup"><span data-stu-id="66621-143">By default, `Enable-PSRemoting` creates network rules that allow remote access from private and domain networks.</span></span> <span data-ttu-id="66621-144">该命令使用 **SkipNetworkProfileCheck** 参数来允许来自相同本地子网中的公用网络的远程访问。</span><span class="sxs-lookup"><span data-stu-id="66621-144">The command uses the **SkipNetworkProfileCheck** parameter to allow remote access from public networks in the same local subnet.</span></span> <span data-ttu-id="66621-145">命令指定 **Force** 参数以禁止显示确认消息。</span><span class="sxs-lookup"><span data-stu-id="66621-145">The command specifies the **Force** parameter to suppress confirmation messages.</span></span>

<span data-ttu-id="66621-146">**SkipNetworkProfileCheck** 参数不影响 Windows 操作系统的服务器版本，默认情况下，它允许从同一本地子网中的公共网络进行远程访问。</span><span class="sxs-lookup"><span data-stu-id="66621-146">The **SkipNetworkProfileCheck** parameter does not affect server versions of the Windows operating system, which allow remote access from public networks in the same local subnet by default.</span></span>

<span data-ttu-id="66621-147">`Set-NetFirewallRule` **NetSecurity** 模块中的 cmdlet 添加一个防火墙规则，该规则允许从任何远程位置从公用网络进行远程访问。</span><span class="sxs-lookup"><span data-stu-id="66621-147">The `Set-NetFirewallRule` cmdlet in the **NetSecurity** module adds a firewall rule that allows remote access from public networks from any remote location.</span></span> <span data-ttu-id="66621-148">这包括不同子网中的位置。</span><span class="sxs-lookup"><span data-stu-id="66621-148">This includes locations in different subnets.</span></span>

> [!NOTE]
> <span data-ttu-id="66621-149">防火墙规则的名称可能不同，具体取决于 Windows 的版本。</span><span class="sxs-lookup"><span data-stu-id="66621-149">The name of the firewall rule can be different depending on the version of Windows.</span></span> <span data-ttu-id="66621-150">使用 `Get-NetFirewallRule` cmdlet 列出系统上规则的名称。</span><span class="sxs-lookup"><span data-stu-id="66621-150">Use the `Get-NetFirewallRule` cmdlet to list the names of the rules on your system.</span></span>

## <span data-ttu-id="66621-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66621-151">PARAMETERS</span></span>

### <span data-ttu-id="66621-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="66621-152">-Confirm</span></span>

<span data-ttu-id="66621-153">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="66621-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="66621-154">-Force</span><span class="sxs-lookup"><span data-stu-id="66621-154">-Force</span></span>

<span data-ttu-id="66621-155">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="66621-155">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="66621-156">-SkipNetworkProfileCheck</span><span class="sxs-lookup"><span data-stu-id="66621-156">-SkipNetworkProfileCheck</span></span>

<span data-ttu-id="66621-157">指示当计算机位于公用网络上时，此 cmdlet 将在客户端版本的 Windows 操作系统上启用远程处理。</span><span class="sxs-lookup"><span data-stu-id="66621-157">Indicates that this cmdlet enables remoting on client versions of the Windows operating system when the computer is on a public network.</span></span> <span data-ttu-id="66621-158">此参数只允许为公用网络启用防火墙规则，该规则只允许远程访问同一本地子网中的计算机。</span><span class="sxs-lookup"><span data-stu-id="66621-158">This parameter enables a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="66621-159">此参数不会影响 Windows 操作系统的服务器版本，默认情况下，它具有公用网络的本地子网防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="66621-159">This parameter does not affect server versions of the Windows operating system, which, by default, have a local subnet firewall rule for public networks.</span></span> <span data-ttu-id="66621-160">如果在服务器版本上禁用了本地子网防火墙规则， `Enable-PSRemoting` 则无论此参数的值是什么，都将其重新启用。</span><span class="sxs-lookup"><span data-stu-id="66621-160">If the local subnet firewall rule is disabled on a server version, `Enable-PSRemoting` re-enables it, regardless of the value of this parameter.</span></span>

<span data-ttu-id="66621-161">若要删除本地子网限制并从公用网络上的所有位置启用远程访问，请 `Set-NetFirewallRule` 在 **NetSecurity** 模块中使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66621-161">To remove the local subnet restriction and enable remote access from all locations on public networks, use the `Set-NetFirewallRule` cmdlet in the **NetSecurity** module.</span></span>

<span data-ttu-id="66621-162">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="66621-162">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="66621-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="66621-163">-WhatIf</span></span>

<span data-ttu-id="66621-164">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="66621-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="66621-165">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="66621-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="66621-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66621-166">CommonParameters</span></span>

<span data-ttu-id="66621-167">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="66621-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66621-168">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="66621-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66621-169">输入</span><span class="sxs-lookup"><span data-stu-id="66621-169">INPUTS</span></span>

### <span data-ttu-id="66621-170">无</span><span class="sxs-lookup"><span data-stu-id="66621-170">None</span></span>

<span data-ttu-id="66621-171">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66621-171">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="66621-172">输出</span><span class="sxs-lookup"><span data-stu-id="66621-172">OUTPUTS</span></span>

### <span data-ttu-id="66621-173">System.String</span><span class="sxs-lookup"><span data-stu-id="66621-173">System.String</span></span>

<span data-ttu-id="66621-174">此 cmdlet 将返回描述其结果的字符串。</span><span class="sxs-lookup"><span data-stu-id="66621-174">This cmdlet returns strings that describe its results.</span></span>

## <span data-ttu-id="66621-175">注释</span><span class="sxs-lookup"><span data-stu-id="66621-175">NOTES</span></span>

<span data-ttu-id="66621-176">在 PowerShell 3.0 中， `Enable-PSRemoting` 为 WS-Management 通信创建以下防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="66621-176">In PowerShell 3.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="66621-177">在 Windows 操作系统的服务器版本上， `Enable-PSRemoting` 为允许远程访问的专用和域网络创建防火墙规则，并为公用网络创建防火墙规则，该规则仅允许来自同一本地子网中的计算机的远程访问。</span><span class="sxs-lookup"><span data-stu-id="66621-177">On server versions of the Windows operating system, `Enable-PSRemoting` creates firewall rules for private and domain networks that allow remote access, and creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="66621-178">在 Windows 操作系统的客户端版本中， `Enable-PSRemoting` PowerShell 3.0 为允许无限制远程访问的私有和域网络创建防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="66621-178">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 3.0 creates firewall rules for private and domain networks that allow unrestricted remote access.</span></span> <span data-ttu-id="66621-179">若要为公用网络创建防火墙规则，以允许来自相同本地子网的远程访问，请使用 **SkipNetworkProfileCheck** 参数。</span><span class="sxs-lookup"><span data-stu-id="66621-179">To create a firewall rule for public networks that allows remote access from the same local subnet, use the **SkipNetworkProfileCheck** parameter.</span></span>

<span data-ttu-id="66621-180">在 Windows 操作系统的客户端或服务器版本上，若要为公用网络创建防火墙规则，以便删除本地子网限制并允许远程访问，请使用 `Set-NetFirewallRule` NetSecurity 模块中的 cmdlet 来运行以下命令： `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span><span class="sxs-lookup"><span data-stu-id="66621-180">On client or server versions of the Windows operating system, to create a firewall rule for public networks that removes the local subnet restriction and allows remote access , use the `Set-NetFirewallRule` cmdlet in the NetSecurity module to run the following command: `Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any`</span></span>

<span data-ttu-id="66621-181">在 PowerShell 2.0 中， `Enable-PSRemoting` 为 WS-Management 通信创建以下防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="66621-181">In PowerShell 2.0, `Enable-PSRemoting` creates the following firewall exceptions for WS-Management communications.</span></span>

<span data-ttu-id="66621-182">在 Windows 操作系统的服务器版本上，它会为允许远程访问的所有网络创建防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="66621-182">On server versions of the Windows operating system, it creates firewall rules for all networks that allow remote access.</span></span>

<span data-ttu-id="66621-183">在 Windows 操作系统的客户端版本上， `Enable-PSRemoting` PowerShell 2.0 仅为域和专用网络位置创建防火墙例外。</span><span class="sxs-lookup"><span data-stu-id="66621-183">On client versions of the Windows operating system, `Enable-PSRemoting` in PowerShell 2.0 creates a firewall exception only for domain and private network locations.</span></span> <span data-ttu-id="66621-184">为了尽量降低安全风险，不 `Enable-PSRemoting` 会在客户端版本的 Windows 上为公用网络创建防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="66621-184">To minimize security risks, `Enable-PSRemoting` does not create a firewall rule for public networks on client versions of Windows.</span></span> <span data-ttu-id="66621-185">当当前网络位置为 "公共" 时，将 `Enable-PSRemoting` 返回以下消息： "无法检查防火墙的状态"。</span><span class="sxs-lookup"><span data-stu-id="66621-185">When the current network location is public, `Enable-PSRemoting` returns the following message: Unable to check the status of the firewall.</span></span>

<span data-ttu-id="66621-186">从 PowerShell 3.0 开始， `Enable-PSRemoting` 通过将所有会话配置的 " **已启用** " 属性的值设置为来启用所有会话配置 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="66621-186">Starting in PowerShell 3.0, `Enable-PSRemoting` enables all session configurations by setting the value of the **Enabled** property of all session configurations to `$True`.</span></span>

<span data-ttu-id="66621-187">在 PowerShell 2.0 中， `Enable-PSRemoting` 从会话配置的安全描述符中删除 **Deny_All** 设置。</span><span class="sxs-lookup"><span data-stu-id="66621-187">In PowerShell 2.0, `Enable-PSRemoting` removes the **Deny_All** setting from the security descriptor of session configurations.</span></span> <span data-ttu-id="66621-188">在 PowerShell 3.0 中， `Enable-PSRemoting` 删除 **Deny_All** 和 **Network_Deny_All** 设置。</span><span class="sxs-lookup"><span data-stu-id="66621-188">In PowerShell 3.0, `Enable-PSRemoting` removes the **Deny_All** and **Network_Deny_All** settings.</span></span> <span data-ttu-id="66621-189">这可以远程访问保留供本地使用的会话配置。</span><span class="sxs-lookup"><span data-stu-id="66621-189">This provides remote access to session configurations that were reserved for local use.</span></span>

## <span data-ttu-id="66621-190">相关链接</span><span class="sxs-lookup"><span data-stu-id="66621-190">RELATED LINKS</span></span>

[<span data-ttu-id="66621-191">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="66621-191">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="66621-192">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="66621-192">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="66621-193">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="66621-193">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="66621-194">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="66621-194">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="66621-195">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="66621-195">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="66621-196">Disable-PSRemoting</span><span class="sxs-lookup"><span data-stu-id="66621-196">Disable-PSRemoting</span></span>](Disable-PSRemoting.md)

[<span data-ttu-id="66621-197">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="66621-197">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="66621-198">about_Remote</span><span class="sxs-lookup"><span data-stu-id="66621-198">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="66621-199">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="66621-199">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)
