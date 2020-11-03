---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 860a5ec4f75136bd53fa5c9621504b1613e9c511
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198062"
---
# <span data-ttu-id="3f5b9-103">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="3f5b9-103">Rename-Computer</span></span>

## <span data-ttu-id="3f5b9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3f5b9-104">SYNOPSIS</span></span>
<span data-ttu-id="3f5b9-105">重命名计算机。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-105">Renames a computer.</span></span>

## <span data-ttu-id="3f5b9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3f5b9-106">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3f5b9-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3f5b9-107">DESCRIPTION</span></span>

<span data-ttu-id="3f5b9-108">该 `Rename-Computer` cmdlet 将重命名本地计算机或远程计算机。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-108">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="3f5b9-109">在一个命令中可重命名一台计算机。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-109">It renames one computer in each command.</span></span>

<span data-ttu-id="3f5b9-110">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="3f5b9-111">示例</span><span class="sxs-lookup"><span data-stu-id="3f5b9-111">EXAMPLES</span></span>

### <span data-ttu-id="3f5b9-112">示例1：重命名本地计算机</span><span class="sxs-lookup"><span data-stu-id="3f5b9-112">Example 1: Rename the local computer</span></span>

<span data-ttu-id="3f5b9-113">此命令将本地计算机重命名为 `Server044` ，然后重新启动它以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-113">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="3f5b9-114">示例2：重命名远程计算机</span><span class="sxs-lookup"><span data-stu-id="3f5b9-114">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="3f5b9-115">此命令将计算机重命名 `Srv01` 为 `Server001` 。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-115">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="3f5b9-116">计算机不会重新启动。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-116">The computer is not restarted.</span></span>

<span data-ttu-id="3f5b9-117">**DomainCredential** 参数指定有权对域中的计算机进行重命名的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-117">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="3f5b9-118">**Force** 参数取消显示确认提示。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-118">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="3f5b9-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3f5b9-119">PARAMETERS</span></span>

### <span data-ttu-id="3f5b9-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3f5b9-120">-ComputerName</span></span>

<span data-ttu-id="3f5b9-121">重命名指定的远程计算机。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-121">Renames the specified remote computer.</span></span>
<span data-ttu-id="3f5b9-122">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-122">The default is the local computer.</span></span>

<span data-ttu-id="3f5b9-123">键入远程计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-123">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="3f5b9-124">若要指定本地计算机，请键入计算机名、点 (`.`) 或 `localhost` 。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-124">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="3f5b9-125">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-125">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="3f5b9-126">**ComputerName** `Rename-Computer` 即使你的计算机未配置为运行远程命令，你也可以使用 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-126">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3f5b9-127">-DomainCredential</span><span class="sxs-lookup"><span data-stu-id="3f5b9-127">-DomainCredential</span></span>

<span data-ttu-id="3f5b9-128">指定有权连接到域的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-128">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="3f5b9-129">需要显式凭据才可重命名加入到域的计算机。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-129">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="3f5b9-130">键入用户名（如 `User01` 或 `Domain01\User01` ），或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-130">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="3f5b9-131">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="3f5b9-132">若要指定有权连接到由 **ComputerName** 参数指定的计算机的用户帐户，请使用 **LocalCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-132">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f5b9-133">-Force</span><span class="sxs-lookup"><span data-stu-id="3f5b9-133">-Force</span></span>

<span data-ttu-id="3f5b9-134">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="3f5b9-135">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="3f5b9-135">-LocalCredential</span></span>

<span data-ttu-id="3f5b9-136">指定有权连接到由 **ComputerName** 参数指定的计算机的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-136">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="3f5b9-137">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-137">The default is the current user.</span></span>

<span data-ttu-id="3f5b9-138">键入用户名（如 `User01` 或 `Domain01\User01` ），或输入 PSCredential 对象，例如由 cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-138">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="3f5b9-139">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="3f5b9-140">若要指定有权连接到域的用户帐户，请使用 **DomainCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-140">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f5b9-141">-NewName</span><span class="sxs-lookup"><span data-stu-id="3f5b9-141">-NewName</span></span>

<span data-ttu-id="3f5b9-142">为计算机指定一个新名称。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-142">Specifies a new name for the computer.</span></span>
<span data-ttu-id="3f5b9-143">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-143">This parameter is required.</span></span>

<span data-ttu-id="3f5b9-144">标准名称可能包含 (`a-z`) 、 (`A-Z`) 、数字 (`0-9`)  (和连字符) 的字母，但不 () `-` 空格或句点 `.` 。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-144">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="3f5b9-145">名称不能完全由数字组成，且长度不得超过63个字符</span><span class="sxs-lookup"><span data-stu-id="3f5b9-145">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3f5b9-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3f5b9-146">-PassThru</span></span>

<span data-ttu-id="3f5b9-147">返回命令的结果。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-147">Returns the results of the command.</span></span>
<span data-ttu-id="3f5b9-148">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-148">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3f5b9-149">-Protocol</span><span class="sxs-lookup"><span data-stu-id="3f5b9-149">-Protocol</span></span>

<span data-ttu-id="3f5b9-150">指定用于重命名计算机的协议。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-150">Specifies which protocol to use to rename the computer.</span></span>
<span data-ttu-id="3f5b9-151">此参数的可接受的值是：WSMan 和 DCOM。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-151">The acceptable values for this parameter are: WSMan and DCOM.</span></span>
<span data-ttu-id="3f5b9-152">默认值为 DCOM。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-152">The default value is DCOM.</span></span>

<span data-ttu-id="3f5b9-153">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-153">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f5b9-154">-Restart</span><span class="sxs-lookup"><span data-stu-id="3f5b9-154">-Restart</span></span>

<span data-ttu-id="3f5b9-155">指示此 cmdlet 重启已重命名的计算机。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-155">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="3f5b9-156">若要更改生效，通常需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-156">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="3f5b9-157">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="3f5b9-157">-WsmanAuthentication</span></span>

<span data-ttu-id="3f5b9-158">指定此 cmdlet 使用 WSMan 协议时用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-158">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="3f5b9-159">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="3f5b9-159">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3f5b9-160">**基本**</span><span class="sxs-lookup"><span data-stu-id="3f5b9-160">**Basic**</span></span>
- <span data-ttu-id="3f5b9-161">CredSSP</span><span class="sxs-lookup"><span data-stu-id="3f5b9-161">**CredSSP**</span></span>
- <span data-ttu-id="3f5b9-162">**默认**</span><span class="sxs-lookup"><span data-stu-id="3f5b9-162">**Default**</span></span>
- <span data-ttu-id="3f5b9-163">摘要式</span><span class="sxs-lookup"><span data-stu-id="3f5b9-163">**Digest**</span></span>
- <span data-ttu-id="3f5b9-164">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="3f5b9-164">**Kerberos**</span></span>
- <span data-ttu-id="3f5b9-165">**沟通**</span><span class="sxs-lookup"><span data-stu-id="3f5b9-165">**Negotiate**</span></span>

<span data-ttu-id="3f5b9-166">默认值为 **Default** 。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-166">The default value is **Default** .</span></span>

<span data-ttu-id="3f5b9-167">有关此参数的值的详细信息，请参阅 [System.management.automation.runspaces.authenticationmechanism 枚举](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-167">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="3f5b9-168">凭据安全服务提供程序 (CredSSP) 身份验证，在此身份验证中，用户凭据传递到远程计算机进行身份验证时，需要对多个资源（例如访问远程网络共享）进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-168">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="3f5b9-169">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-169">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="3f5b9-170">如果远程计算机被泄露，则传递到该计算机的凭据可用于控制网络会话 >。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-170">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="3f5b9-171">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-171">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3f5b9-172">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3f5b9-172">-Confirm</span></span>

<span data-ttu-id="3f5b9-173">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-173">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3f5b9-174">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3f5b9-174">-WhatIf</span></span>

<span data-ttu-id="3f5b9-175">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-175">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3f5b9-176">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-176">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3f5b9-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3f5b9-177">CommonParameters</span></span>

<span data-ttu-id="3f5b9-178">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3f5b9-179">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-179">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="3f5b9-180">输入</span><span class="sxs-lookup"><span data-stu-id="3f5b9-180">INPUTS</span></span>

### <span data-ttu-id="3f5b9-181">无</span><span class="sxs-lookup"><span data-stu-id="3f5b9-181">None</span></span>

<span data-ttu-id="3f5b9-182">此 cmdlet 不具有按值获取输入的参数。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-182">This cmdlet does not have parameters that take input by value.</span></span>
<span data-ttu-id="3f5b9-183">但是，你可以通过管道将对象的 **ComputerName** 和 **NewName** 属性的值传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-183">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="3f5b9-184">输出</span><span class="sxs-lookup"><span data-stu-id="3f5b9-184">OUTPUTS</span></span>

### <span data-ttu-id="3f5b9-185">Microsoft.PowerShell.Commands.ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="3f5b9-185">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="3f5b9-186">如果指定 **PassThru** 参数，则此 cmdlet 将返回 **ComputerChangeInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-186">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="3f5b9-187">否则，将不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="3f5b9-187">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="3f5b9-188">注释</span><span class="sxs-lookup"><span data-stu-id="3f5b9-188">NOTES</span></span>

## <span data-ttu-id="3f5b9-189">相关链接</span><span class="sxs-lookup"><span data-stu-id="3f5b9-189">RELATED LINKS</span></span>

[<span data-ttu-id="3f5b9-190">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="3f5b9-190">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="3f5b9-191">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="3f5b9-191">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="3f5b9-192">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="3f5b9-192">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="3f5b9-193">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3f5b9-193">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="3f5b9-194">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="3f5b9-194">Stop-Computer</span></span>](Stop-Computer.md)
