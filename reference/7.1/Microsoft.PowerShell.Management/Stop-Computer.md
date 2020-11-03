---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 12/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-computer?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Computer
ms.openlocfilehash: a1fa09116e7069f3fc7f3d196bffd20f491a93e2
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199116"
---
# <span data-ttu-id="7b417-103">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="7b417-103">Stop-Computer</span></span>

## <span data-ttu-id="7b417-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7b417-104">SYNOPSIS</span></span>
<span data-ttu-id="7b417-105">停止（关闭）本地和远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-105">Stops (shuts down) local and remote computers.</span></span>

## <span data-ttu-id="7b417-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7b417-106">SYNTAX</span></span>

### <span data-ttu-id="7b417-107">全部</span><span class="sxs-lookup"><span data-stu-id="7b417-107">All</span></span>

```
Stop-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential] <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="7b417-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7b417-108">DESCRIPTION</span></span>

<span data-ttu-id="7b417-109">Cmdlet 将关闭 `Stop-Computer` 本地计算机和远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-109">The `Stop-Computer` cmdlet shuts down the local computer and remote computers.</span></span>

<span data-ttu-id="7b417-110">你可以使用的参数 `Stop-Computer` 来指定身份验证级别和备用凭据，并强制立即关闭。</span><span class="sxs-lookup"><span data-stu-id="7b417-110">You can use the parameters of `Stop-Computer` to specify the authentication levels and alternate credentials, and to force an immediate shut down.</span></span>

<span data-ttu-id="7b417-111">在 PowerShell 7.1 中， `Stop-Computer` 为 Linux 和 macOS 添加了。</span><span class="sxs-lookup"><span data-stu-id="7b417-111">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="7b417-112">参数在这些平台上不起作用。</span><span class="sxs-lookup"><span data-stu-id="7b417-112">The parameters have no effect on these platforms.</span></span> <span data-ttu-id="7b417-113">该 cmdlet 只调用本机命令 `/sbin/shutdown` 。</span><span class="sxs-lookup"><span data-stu-id="7b417-113">The cmdlet is just calling the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="7b417-114">示例</span><span class="sxs-lookup"><span data-stu-id="7b417-114">EXAMPLES</span></span>

### <span data-ttu-id="7b417-115">示例 1：关闭本地计算机</span><span class="sxs-lookup"><span data-stu-id="7b417-115">Example 1: Shut down the local computer</span></span>

<span data-ttu-id="7b417-116">此示例关闭本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-116">This example shuts down the local computer.</span></span>

```powershell
Stop-Computer -ComputerName localhost
```

### <span data-ttu-id="7b417-117">示例 2：关闭两台远程计算机和本地计算机</span><span class="sxs-lookup"><span data-stu-id="7b417-117">Example 2: Shut down two remote computers and the local computer</span></span>

<span data-ttu-id="7b417-118">此示例将停止两台远程计算机和本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-118">This example stops two remote computers and the local computer.</span></span>

```powershell
Stop-Computer -ComputerName "Server01", "Server02", "localhost"
```

<span data-ttu-id="7b417-119">`Stop-Computer` 使用 **ComputerName** 参数指定两台远程计算机和本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-119">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers and the local computer.</span></span> <span data-ttu-id="7b417-120">每台计算机都已关闭。</span><span class="sxs-lookup"><span data-stu-id="7b417-120">Each computer is shut down.</span></span>

### <span data-ttu-id="7b417-121">示例 3：关闭远程计算机，作为后台作业运行</span><span class="sxs-lookup"><span data-stu-id="7b417-121">Example 3: Shut down remote computers as a background job</span></span>

<span data-ttu-id="7b417-122">在此示例中，在 `Stop-Computer` 两台远程计算机上作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="7b417-122">In this example, `Stop-Computer` runs as a background job on two remote computers.</span></span>

<span data-ttu-id="7b417-123">后台运算符将 `&` `Stop-Computer` 命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="7b417-123">The background operator `&` runs the `Stop-Computer` command as a background job.</span></span> <span data-ttu-id="7b417-124">有关详细信息，请参阅 [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-)。</span><span class="sxs-lookup"><span data-stu-id="7b417-124">For more information, see [about_Operators](../microsoft.powershell.core/about/about_operators.md#background-operator-).</span></span>

```powershell
$j = Stop-Computer -ComputerName "Server01", "Server02" &
$results = $j | Receive-Job
$results
```

<span data-ttu-id="7b417-125">`Stop-Computer` 使用 **ComputerName** 参数指定两台远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-125">`Stop-Computer` uses the **ComputerName** parameter to specify two remote computers.</span></span> <span data-ttu-id="7b417-126">`&`后台运算符将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="7b417-126">The `&` background operator runs the command as a background job.</span></span> <span data-ttu-id="7b417-127">作业对象存储在 `$j` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7b417-127">The job objects are stored in the `$j` variable.</span></span>

<span data-ttu-id="7b417-128">变量中的作业对象 `$j` 会向下发送到 `Receive-Job` ，后者将获取作业结果。</span><span class="sxs-lookup"><span data-stu-id="7b417-128">The job objects in the `$j` variable are sent down the pipeline to `Receive-Job`, which gets the job results.</span></span> <span data-ttu-id="7b417-129">这些对象存储在变量中 `$results` 。</span><span class="sxs-lookup"><span data-stu-id="7b417-129">The objects are stored in the `$results` variable.</span></span> <span data-ttu-id="7b417-130">此 `$results` 变量在 PowerShell 控制台中显示作业信息。</span><span class="sxs-lookup"><span data-stu-id="7b417-130">The `$results` variable displays the job information in the PowerShell console.</span></span>

### <span data-ttu-id="7b417-131">示例 4：关闭远程计算机</span><span class="sxs-lookup"><span data-stu-id="7b417-131">Example 4: Shut down a remote computer</span></span>

<span data-ttu-id="7b417-132">此示例使用指定的身份验证关闭远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-132">This example shuts down a remote computer using specified authentication.</span></span>

```powershell
Stop-Computer -ComputerName "Server01" -WsmanAuthentication Kerberos
```

<span data-ttu-id="7b417-133">`Stop-Computer` 使用 **ComputerName** 参数来指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-133">`Stop-Computer` uses the **ComputerName** parameter to specify the remote computer.</span></span> <span data-ttu-id="7b417-134">**WsmanAuthentication** 参数指定使用 Kerberos 建立远程连接。</span><span class="sxs-lookup"><span data-stu-id="7b417-134">The **WsmanAuthentication** parameter specifies to use Kerberos to establish a remote connection.</span></span>

### <span data-ttu-id="7b417-135">示例5：关闭域中的计算机</span><span class="sxs-lookup"><span data-stu-id="7b417-135">Example 5: Shut down computers in a domain</span></span>

<span data-ttu-id="7b417-136">在此示例中，这些命令强制立即关闭指定域中的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-136">In this example, the commands force an immediate shut down of all computers in a specified domain.</span></span>

```powershell
$s = Get-Content -Path ./Domain01.txt
$c = Get-Credential -Credential Domain01\Admin01
Stop-Computer -ComputerName $s -Force -Credential $c
```

<span data-ttu-id="7b417-137">`Get-Content` 使用 **Path** 参数获取当前目录中包含域计算机列表的文件。</span><span class="sxs-lookup"><span data-stu-id="7b417-137">`Get-Content` uses the **Path** parameter to get a file in the current directory with the list of domain computers.</span></span> <span data-ttu-id="7b417-138">这些对象存储在变量中 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="7b417-138">The objects are stored in the `$s` variable.</span></span>

<span data-ttu-id="7b417-139">`Get-Credential` 使用 **Credential** 参数指定域管理员的凭据。</span><span class="sxs-lookup"><span data-stu-id="7b417-139">`Get-Credential` uses the **Credential** parameter to specify the credentials of a domain administrator.</span></span> <span data-ttu-id="7b417-140">凭据存储在 `$c` 变量中。</span><span class="sxs-lookup"><span data-stu-id="7b417-140">The credentials are stored in the `$c` variable.</span></span>

<span data-ttu-id="7b417-141">`Stop-Computer` 关闭在变量中用 **ComputerName** 参数的计算机列表指定的计算机 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="7b417-141">`Stop-Computer` shuts down the computers specified with the **ComputerName** parameter's list of computers in the `$s` variable.</span></span> <span data-ttu-id="7b417-142">**Force** 参数强制立即关闭。</span><span class="sxs-lookup"><span data-stu-id="7b417-142">The **Force** parameter forces an immediate shutdown.</span></span> <span data-ttu-id="7b417-143">**Credential** 参数提交保存在变量中的凭据 `$c` 。</span><span class="sxs-lookup"><span data-stu-id="7b417-143">The **Credential** parameter submits the credentials saved in the `$c` variable.</span></span>

## <span data-ttu-id="7b417-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7b417-144">PARAMETERS</span></span>

### <span data-ttu-id="7b417-145">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="7b417-145">-ComputerName</span></span>

<span data-ttu-id="7b417-146">指定要停止的计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-146">Specifies the computers to stop.</span></span> <span data-ttu-id="7b417-147">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-147">The default is the local computer.</span></span>

<span data-ttu-id="7b417-148">在一个逗号分隔列表中键入一台或多台计算机的 NETBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="7b417-148">Type the NETBIOS name, IP address, or fully qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="7b417-149">若要指定本地计算机，请键入计算机名称或“localhost”。</span><span class="sxs-lookup"><span data-stu-id="7b417-149">To specify the local computer, type the computer name or localhost.</span></span>

<span data-ttu-id="7b417-150">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="7b417-150">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="7b417-151">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="7b417-151">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7b417-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7b417-152">-Confirm</span></span>

<span data-ttu-id="7b417-153">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="7b417-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7b417-154">-Credential</span><span class="sxs-lookup"><span data-stu-id="7b417-154">-Credential</span></span>

<span data-ttu-id="7b417-155">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7b417-155">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="7b417-156">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="7b417-156">The default is the current user.</span></span>

<span data-ttu-id="7b417-157">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="7b417-157">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="7b417-158">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="7b417-158">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="7b417-159">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="7b417-159">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="7b417-160">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="7b417-160">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7b417-161">-Force</span><span class="sxs-lookup"><span data-stu-id="7b417-161">-Force</span></span>

<span data-ttu-id="7b417-162">强制立即关闭计算机。</span><span class="sxs-lookup"><span data-stu-id="7b417-162">Forces an immediate shut down of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7b417-163">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="7b417-163">-WsmanAuthentication</span></span>

<span data-ttu-id="7b417-164">指定此 cmdlet 使用 WSMan 协议时用于对用户的凭据进行身份验证的机制。</span><span class="sxs-lookup"><span data-stu-id="7b417-164">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="7b417-165">默认值为 **Default** 。</span><span class="sxs-lookup"><span data-stu-id="7b417-165">The default value is **Default** .</span></span>

<span data-ttu-id="7b417-166">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="7b417-166">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="7b417-167">基本</span><span class="sxs-lookup"><span data-stu-id="7b417-167">Basic</span></span>
- <span data-ttu-id="7b417-168">CredSSP</span><span class="sxs-lookup"><span data-stu-id="7b417-168">CredSSP</span></span>
- <span data-ttu-id="7b417-169">默认</span><span class="sxs-lookup"><span data-stu-id="7b417-169">Default</span></span>
- <span data-ttu-id="7b417-170">摘要</span><span class="sxs-lookup"><span data-stu-id="7b417-170">Digest</span></span>
- <span data-ttu-id="7b417-171">Kerberos</span><span class="sxs-lookup"><span data-stu-id="7b417-171">Kerberos</span></span>
- <span data-ttu-id="7b417-172">Negotiate。</span><span class="sxs-lookup"><span data-stu-id="7b417-172">Negotiate.</span></span>

<span data-ttu-id="7b417-173">有关此参数的值的详细信息，请参阅 [system.management.automation.runspaces.authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)。</span><span class="sxs-lookup"><span data-stu-id="7b417-173">For more information about the values of this parameter, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!CAUTION]
> <span data-ttu-id="7b417-174">凭据安全服务提供程序 (CredSSP) 身份验证，在此身份验证中，用户凭据传递到远程计算机进行身份验证时，需要对多个资源（例如访问远程网络共享）进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="7b417-174">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="7b417-175">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="7b417-175">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="7b417-176">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="7b417-176">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

<span data-ttu-id="7b417-177">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7b417-177">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: Default
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7b417-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7b417-178">-WhatIf</span></span>

<span data-ttu-id="7b417-179">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="7b417-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="7b417-180">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="7b417-180">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="7b417-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7b417-181">CommonParameters</span></span>

<span data-ttu-id="7b417-182">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7b417-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7b417-183">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="7b417-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7b417-184">输入</span><span class="sxs-lookup"><span data-stu-id="7b417-184">INPUTS</span></span>

### <span data-ttu-id="7b417-185">无</span><span class="sxs-lookup"><span data-stu-id="7b417-185">None</span></span>

<span data-ttu-id="7b417-186">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b417-186">You can't pipe input to this cmdlet.</span></span>

## <span data-ttu-id="7b417-187">输出</span><span class="sxs-lookup"><span data-stu-id="7b417-187">OUTPUTS</span></span>

### <span data-ttu-id="7b417-188">无</span><span class="sxs-lookup"><span data-stu-id="7b417-188">None</span></span>

## <span data-ttu-id="7b417-189">注释</span><span class="sxs-lookup"><span data-stu-id="7b417-189">NOTES</span></span>

<span data-ttu-id="7b417-190">此 cmdlet 使用 **Win32_OperatingSystem** WMI 类的 **Win32Shutdown** 方法。</span><span class="sxs-lookup"><span data-stu-id="7b417-190">This cmdlet uses the **Win32Shutdown** method of the **Win32_OperatingSystem** WMI class.</span></span> <span data-ttu-id="7b417-191">此方法需要为用于重新启动计算机的用户帐户启用 **SeShutdownPrivilege** 特权。</span><span class="sxs-lookup"><span data-stu-id="7b417-191">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

<span data-ttu-id="7b417-192">在 PowerShell 7.1 中， `Stop-Computer` 为 Linux 和 macOS 添加了。</span><span class="sxs-lookup"><span data-stu-id="7b417-192">In PowerShell 7.1, `Stop-Computer` was added for Linux and macOS.</span></span> <span data-ttu-id="7b417-193">对于这些平台，cmdlet 将调用本机命令 `/sbin/shutdown` 。</span><span class="sxs-lookup"><span data-stu-id="7b417-193">For these platorms, the cmdlet calls the native command `/sbin/shutdown`.</span></span>

## <span data-ttu-id="7b417-194">相关链接</span><span class="sxs-lookup"><span data-stu-id="7b417-194">RELATED LINKS</span></span>

[<span data-ttu-id="7b417-195">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="7b417-195">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="7b417-196">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="7b417-196">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="7b417-197">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="7b417-197">Test-Connection</span></span>](Test-Connection.md)

