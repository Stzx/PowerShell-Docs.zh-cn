---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198070"
---
# <span data-ttu-id="90cb9-103">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-103">Remove-Computer</span></span>

## <span data-ttu-id="90cb9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="90cb9-104">SYNOPSIS</span></span>
<span data-ttu-id="90cb9-105">从本机计算机的域中删除本地计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-105">Removes the local computer from its domain.</span></span>

## <span data-ttu-id="90cb9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="90cb9-106">SYNTAX</span></span>

### <span data-ttu-id="90cb9-107">Local（默认值）</span><span class="sxs-lookup"><span data-stu-id="90cb9-107">Local (Default)</span></span>

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="90cb9-108">Remote</span><span class="sxs-lookup"><span data-stu-id="90cb9-108">Remote</span></span>

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="90cb9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="90cb9-109">DESCRIPTION</span></span>

<span data-ttu-id="90cb9-110">`Remove-Computer`Cmdlet 从其当前域中删除本地计算机和远程计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-110">The `Remove-Computer` cmdlet removes the local computer and remote computers from their current domains.</span></span>

<span data-ttu-id="90cb9-111">从域中删除计算机时，也会 `Remove-Computer` 禁用该计算机的域帐户。</span><span class="sxs-lookup"><span data-stu-id="90cb9-111">When you remove a computer from a domain, `Remove-Computer` also disables the domain account of the computer.</span></span> <span data-ttu-id="90cb9-112">必须提供显式凭据才能从其域中脱离计算机，即使是当前用户的凭据也是如此。</span><span class="sxs-lookup"><span data-stu-id="90cb9-112">You must provide explicit credentials to unjoin the computer from its domain, even when they are the credentials of the current user.</span></span> <span data-ttu-id="90cb9-113">必须重新启动计算机才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="90cb9-113">You must restart the computer to make the change effective.</span></span> <span data-ttu-id="90cb9-114">此外，在从域中删除计算机时，你必须将其移出工作组。</span><span class="sxs-lookup"><span data-stu-id="90cb9-114">Also, when you remove a computer from a domain, you must move it to a workgroup.</span></span> <span data-ttu-id="90cb9-115">使用 **WorkgroupName** 参数来指定工作组。</span><span class="sxs-lookup"><span data-stu-id="90cb9-115">Use the **WorkgroupName** parameter to specify the workgroup.</span></span>

<span data-ttu-id="90cb9-116">若要将计算机从工作组移至域，从一个工作组移至另一个工作组或者从一个域移至另一个域，请使用 `Add-Computer` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90cb9-116">To move a computer from a workgroup to a domain, from one workgroup to another, or from one domain to another, use the `Add-Computer` cmdlet.</span></span>

<span data-ttu-id="90cb9-117">若要获取此命令的结果，请使用 **Verbose** 和 **PassThru** 参数。</span><span class="sxs-lookup"><span data-stu-id="90cb9-117">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span> <span data-ttu-id="90cb9-118">若要取消用户提示，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="90cb9-118">To suppress the user prompt, use the **Force** parameter.</span></span>

<span data-ttu-id="90cb9-119">`Remove-Computer` 从域中删除本地计算机和远程计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-119">`Remove-Computer` removes the local computer and remote computers from domains.</span></span> <span data-ttu-id="90cb9-120">它包含以下参数：指定替代凭据的凭据参数，以便连接到远程计算机以及从域中退出； **Restart** 参数，以便重新启动受影响的计算机；以及 **WorkgroupName** 参数，以便指定计算机要添加到的工作组的名称。</span><span class="sxs-lookup"><span data-stu-id="90cb9-120">It includes credential parameters that specify alternate credentials for connecting to remote computers, and unjoining from a domain, a **Restart** parameter for restarting the affected computers, and a **WorkgroupName** parameter for specifying the name of the workgroup to which computers are added.</span></span>

## <span data-ttu-id="90cb9-121">示例</span><span class="sxs-lookup"><span data-stu-id="90cb9-121">EXAMPLES</span></span>

### <span data-ttu-id="90cb9-122">示例1：从其域中删除本地计算机</span><span class="sxs-lookup"><span data-stu-id="90cb9-122">Example 1: Remove the local computer from its domain</span></span>

<span data-ttu-id="90cb9-123">此示例将从它所加入的域中删除本地计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-123">This example removes the local computer from the domain to which it is joined.</span></span>

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

<span data-ttu-id="90cb9-124">**UnjoinDomainCredential** 参数提供域管理员的凭据。</span><span class="sxs-lookup"><span data-stu-id="90cb9-124">The **UnjoinDomainCredential** parameter provides the credentials of a domain administrator.</span></span> <span data-ttu-id="90cb9-125">**PassThru** 和 **Verbose** 通用参数显示有关命令成功或失败的信息。</span><span class="sxs-lookup"><span data-stu-id="90cb9-125">The **PassThru** and the **Verbose** common parameters display information about the success or failure of the command.</span></span> <span data-ttu-id="90cb9-126">**Restart** 参数重新启动计算机以完成删除操作。</span><span class="sxs-lookup"><span data-stu-id="90cb9-126">The **Restart** parameter restarts the computer to complete the remove operation.</span></span>

<span data-ttu-id="90cb9-127">如果未指定工作组名称，则会将计算机从其域中删除后移到名为的工作组。</span><span class="sxs-lookup"><span data-stu-id="90cb9-127">When no workgroup name is specified, the computer is moved to the workgroup named after it is removed from its domain.</span></span>

### <span data-ttu-id="90cb9-128">示例2：将多台计算机移动到旧工作组</span><span class="sxs-lookup"><span data-stu-id="90cb9-128">Example 2: Move several computers to a legacy workgroup</span></span>

<span data-ttu-id="90cb9-129">此示例从其域中删除在文件中列出的所有计算机 `OldServers.txt` ，并将它们移到 **旧** 工作组中。</span><span class="sxs-lookup"><span data-stu-id="90cb9-129">This example removes all the computers listed in the `OldServers.txt` file from their domains and moves them into the **Legacy** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

<span data-ttu-id="90cb9-130">**LocalCredential** 参数提供有权连接到远程计算机的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="90cb9-130">The **LocalCredential** parameter provides the credentials of a user who has permission to connect to remote computers.</span></span> <span data-ttu-id="90cb9-131">**UnjoinDomainCredential** 参数提供有权从其域中删除计算机的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="90cb9-131">The **UnjoinDomainCredential** parameter provides the credentials of a user who has permission to remove the computers from their domains.</span></span> <span data-ttu-id="90cb9-132">**Force** 参数取消每台计算机的确认提示。</span><span class="sxs-lookup"><span data-stu-id="90cb9-132">The **Force** parameter suppresses the confirmation prompts for each computer.</span></span> <span data-ttu-id="90cb9-133">从其域中删除每台计算机后， **Restart** 参数将重新启动每台计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-133">The **Restart** parameter restarts each of the computers after it is removed from its domain.</span></span>

### <span data-ttu-id="90cb9-134">示例3：在不确认的情况下从工作组中删除计算机</span><span class="sxs-lookup"><span data-stu-id="90cb9-134">Example 3: Remove computers from a workgroup without confirmation</span></span>

<span data-ttu-id="90cb9-135">此示例将从其域中删除远程计算机、Server01 和本地计算机，并将其添加到 **本地** 工作组。</span><span class="sxs-lookup"><span data-stu-id="90cb9-135">This example removes the remote computer, Server01, and the local computer from their domains and adds them to the **Local** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

<span data-ttu-id="90cb9-136">**Force** 参数取消每台计算机的确认提示。</span><span class="sxs-lookup"><span data-stu-id="90cb9-136">The **Force** parameter suppresses the confirmation prompt for each computer.</span></span> <span data-ttu-id="90cb9-137">**Restart** 参数重新启动计算机以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="90cb9-137">The **Restart** parameter restarts the computers to make the change effective.</span></span>

## <span data-ttu-id="90cb9-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="90cb9-138">PARAMETERS</span></span>

### <span data-ttu-id="90cb9-139">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="90cb9-139">-ComputerName</span></span>

<span data-ttu-id="90cb9-140">指定要从其域中删除的计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-140">Specifies the computers to be removed from their domains.</span></span> <span data-ttu-id="90cb9-141">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-141">The default is the local computer.</span></span>

<span data-ttu-id="90cb9-142">键入远程计算机的 FQDN)  (的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="90cb9-142">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of the remote computers.</span></span> <span data-ttu-id="90cb9-143">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="90cb9-143">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="90cb9-144">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="90cb9-144">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="90cb9-145">**ComputerName** `Remove-Computer` 即使你的计算机未配置为运行远程命令，你也可以使用 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="90cb9-145">You can use the **ComputerName** parameter of `Remove-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="90cb9-146">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="90cb9-146">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="90cb9-147">-Force</span><span class="sxs-lookup"><span data-stu-id="90cb9-147">-Force</span></span>

<span data-ttu-id="90cb9-148">取消用户提示。</span><span class="sxs-lookup"><span data-stu-id="90cb9-148">Suppresses the user prompt.</span></span> <span data-ttu-id="90cb9-149">默认情况下， `Remove-Computer` 会提示你在删除每台计算机前进行确认。</span><span class="sxs-lookup"><span data-stu-id="90cb9-149">By default, `Remove-Computer` prompts you for confirmation before removing each computer.</span></span>

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

### <span data-ttu-id="90cb9-150">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="90cb9-150">-LocalCredential</span></span>

<span data-ttu-id="90cb9-151">指定有权连接到 **ComputerName** 参数指定的计算机的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="90cb9-151">Specifies a user account that has permission to connect to the computers that the **ComputerName** parameter specifies.</span></span> <span data-ttu-id="90cb9-152">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="90cb9-152">The default is the current user.</span></span>

<span data-ttu-id="90cb9-153">键入用户名（如 `User01` 或 `Domain01\User01` ），或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="90cb9-153">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="90cb9-154">如果键入用户名，该 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="90cb9-154">If you type a user name, the cmdlet prompts you for a password.</span></span> <span data-ttu-id="90cb9-155">若要指定有权将计算机从其当前域中删除的用户帐户，请使用 **UnjoinDomainCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="90cb9-155">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="90cb9-156">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="90cb9-156">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90cb9-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="90cb9-157">-PassThru</span></span>

<span data-ttu-id="90cb9-158">返回命令的结果。</span><span class="sxs-lookup"><span data-stu-id="90cb9-158">Returns the results of the command.</span></span> <span data-ttu-id="90cb9-159">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="90cb9-159">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="90cb9-160">-Restart</span><span class="sxs-lookup"><span data-stu-id="90cb9-160">-Restart</span></span>

<span data-ttu-id="90cb9-161">指示此 cmdlet 重启要删除的计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-161">Indicates that this cmdlet restarts the computers that are being removed.</span></span> <span data-ttu-id="90cb9-162">若要更改生效，通常需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="90cb9-162">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="90cb9-163">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="90cb9-163">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="90cb9-164">-UnjoinDomainCredential</span><span class="sxs-lookup"><span data-stu-id="90cb9-164">-UnjoinDomainCredential</span></span>

<span data-ttu-id="90cb9-165">指定有权将计算机从其当前域中删除的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="90cb9-165">Specifies a user account that has permission to remove the computers from their current domains.</span></span>
<span data-ttu-id="90cb9-166">按照此参数所提供内容，从域中删除远程计算机需要使用显式凭据，即使值为当前用户的凭据也是如此。</span><span class="sxs-lookup"><span data-stu-id="90cb9-166">Explicit credentials, as provided by this parameter, are required to remove remote computers from a domain, even when the value is the credentials of the current user.</span></span>

<span data-ttu-id="90cb9-167">键入用户名（如 User01 或 Domain01\User01），或输入 PSCredential 对象，例如生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="90cb9-167">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by `Get-Credential`.</span></span> <span data-ttu-id="90cb9-168">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="90cb9-168">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="90cb9-169">若要指定有权连接到远程计算机的用户帐户，请使用 **LocalCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="90cb9-169">To specify a user account that has permission to connect to the remote computers, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="90cb9-170">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="90cb9-170">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90cb9-171">-WorkgroupName</span><span class="sxs-lookup"><span data-stu-id="90cb9-171">-WorkgroupName</span></span>

<span data-ttu-id="90cb9-172">指定在将计算机从其域中删除后要添加到的工作组的名称。</span><span class="sxs-lookup"><span data-stu-id="90cb9-172">Specifies the name of a workgroup to which the computers are added when they are removed from their domains.</span></span> <span data-ttu-id="90cb9-173">默认值为 " **WORKGROUP** "。</span><span class="sxs-lookup"><span data-stu-id="90cb9-173">The default value is **WORKGROUP** .</span></span> <span data-ttu-id="90cb9-174">在从域中删除计算机后，必须将其添加到工作组。</span><span class="sxs-lookup"><span data-stu-id="90cb9-174">When you remove a computer from a domain, you must add it to a workgroup.</span></span>

<span data-ttu-id="90cb9-175">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="90cb9-175">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="90cb9-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="90cb9-176">-Confirm</span></span>

<span data-ttu-id="90cb9-177">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="90cb9-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="90cb9-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="90cb9-178">-WhatIf</span></span>

<span data-ttu-id="90cb9-179">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="90cb9-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="90cb9-180">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="90cb9-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="90cb9-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="90cb9-181">CommonParameters</span></span>

<span data-ttu-id="90cb9-182">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="90cb9-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="90cb9-183">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="90cb9-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="90cb9-184">输入</span><span class="sxs-lookup"><span data-stu-id="90cb9-184">INPUTS</span></span>

### <span data-ttu-id="90cb9-185">System.String</span><span class="sxs-lookup"><span data-stu-id="90cb9-185">System.String</span></span>

<span data-ttu-id="90cb9-186">可以通过管道将计算机名称传递给 thiscmdlet。</span><span class="sxs-lookup"><span data-stu-id="90cb9-186">You can pipe computer names to thiscmdlet.</span></span>

## <span data-ttu-id="90cb9-187">输出</span><span class="sxs-lookup"><span data-stu-id="90cb9-187">OUTPUTS</span></span>

### <span data-ttu-id="90cb9-188">Microsoft.PowerShell.Commands.ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="90cb9-188">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="90cb9-189">当使用 **PassThru** 参数时，将 `Remove-Computer` 返回 **ComputerChangeInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="90cb9-189">When you use the **PassThru** parameter, `Remove-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="90cb9-190">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="90cb9-190">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="90cb9-191">注释</span><span class="sxs-lookup"><span data-stu-id="90cb9-191">NOTES</span></span>

<span data-ttu-id="90cb9-192">此 cmdlet 不会从工作组删除计算机。</span><span class="sxs-lookup"><span data-stu-id="90cb9-192">This cmdlet does not remove computers from workgroups.</span></span>

## <span data-ttu-id="90cb9-193">相关链接</span><span class="sxs-lookup"><span data-stu-id="90cb9-193">RELATED LINKS</span></span>

[<span data-ttu-id="90cb9-194">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-194">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="90cb9-195">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-195">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="90cb9-196">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-196">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="90cb9-197">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-197">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="90cb9-198">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-198">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="90cb9-199">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-199">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="90cb9-200">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="90cb9-200">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="90cb9-201">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="90cb9-201">Test-Connection</span></span>](Test-Connection.md)
