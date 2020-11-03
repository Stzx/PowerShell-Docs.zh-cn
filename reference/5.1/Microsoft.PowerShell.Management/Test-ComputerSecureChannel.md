---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198016"
---
# <span data-ttu-id="a5beb-103">Test-ComputerSecureChannel</span><span class="sxs-lookup"><span data-stu-id="a5beb-103">Test-ComputerSecureChannel</span></span>

## <span data-ttu-id="a5beb-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a5beb-104">SYNOPSIS</span></span>
<span data-ttu-id="a5beb-105">测试并修复本地计算机与其域之间的安全通道。</span><span class="sxs-lookup"><span data-stu-id="a5beb-105">Tests and repairs the secure channel between the local computer and its domain.</span></span>

## <span data-ttu-id="a5beb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5beb-106">SYNTAX</span></span>

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a5beb-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a5beb-107">DESCRIPTION</span></span>
<span data-ttu-id="a5beb-108">**Test-ComputerSecureChannel** cmdlet 通过检查本地计算机与其域之间的通道信任关系的状态，来验证通道是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="a5beb-108">The **Test-ComputerSecureChannel** cmdlet verifies that the channel between the local computer and its domain is working correctly by checking the status of its trust relationships.</span></span>
<span data-ttu-id="a5beb-109">如果连接失败，可以使用 *Repair* 参数尝试还原。</span><span class="sxs-lookup"><span data-stu-id="a5beb-109">If a connection fails, you can use the *Repair* parameter to try to restore it.</span></span>

<span data-ttu-id="a5beb-110">如果通道正常工作，则 **Test-ComputerSecureChannel** 将返回 $True；否则，返回 $False。</span><span class="sxs-lookup"><span data-stu-id="a5beb-110">**Test-ComputerSecureChannel** returns $True if the channel is working correctly and $False if it is not.</span></span>
<span data-ttu-id="a5beb-111">此结果使你可以在函数和脚本的条件语句中使用该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5beb-111">This result lets you use the cmdlet in conditional statements in functions and scripts.</span></span>
<span data-ttu-id="a5beb-112">若要获取更详细的测试结果，请使用 *Verbose* 参数。</span><span class="sxs-lookup"><span data-stu-id="a5beb-112">To get more detailed test results, use the *Verbose* parameter.</span></span>

<span data-ttu-id="a5beb-113">此 cmdlet 的工作原理与 NetDom.exe 非常类似。</span><span class="sxs-lookup"><span data-stu-id="a5beb-113">This cmdlet works much like NetDom.exe.</span></span>
<span data-ttu-id="a5beb-114">NetDom 和 **test-computersecurechannel** 都使用 **NetLogon** 服务来执行操作。</span><span class="sxs-lookup"><span data-stu-id="a5beb-114">Both NetDom and **Test-ComputerSecureChannel** use the **NetLogon** service to perform the actions.</span></span>

## <span data-ttu-id="a5beb-115">示例</span><span class="sxs-lookup"><span data-stu-id="a5beb-115">EXAMPLES</span></span>

### <span data-ttu-id="a5beb-116">示例 1：测试本地计算机与其域之间的通道</span><span class="sxs-lookup"><span data-stu-id="a5beb-116">Example 1: Test a channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel
True
```

<span data-ttu-id="a5beb-117">此命令测试本地计算机与它所加入的域之间的通道。</span><span class="sxs-lookup"><span data-stu-id="a5beb-117">This command tests the channel between the local computer and the domain to which it is joined.</span></span>

### <span data-ttu-id="a5beb-118">示例 2：测试本地计算机和域控制器之间的通道</span><span class="sxs-lookup"><span data-stu-id="a5beb-118">Example 2: Test a channel between the local computer and a domain controller</span></span>

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

<span data-ttu-id="a5beb-119">此命令指定要进行测试的首选域控制器。</span><span class="sxs-lookup"><span data-stu-id="a5beb-119">This command specifies a preferred domain controller for the test.</span></span>

### <span data-ttu-id="a5beb-120">示例 3：重置本地计算机与其域之间的通道</span><span class="sxs-lookup"><span data-stu-id="a5beb-120">Example 3: Reset the channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

<span data-ttu-id="a5beb-121">此命令重置本地计算机与其域之间的通道。</span><span class="sxs-lookup"><span data-stu-id="a5beb-121">This command resets the channel between the local computer and its domain.</span></span>

### <span data-ttu-id="a5beb-122">示例 4：显示有关测试的详细信息</span><span class="sxs-lookup"><span data-stu-id="a5beb-122">Example 4: Display detailed information about the test</span></span>

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

<span data-ttu-id="a5beb-123">此命令使用 *Verbose* 通用参数来请求有关操作的详细消息。</span><span class="sxs-lookup"><span data-stu-id="a5beb-123">This command uses the *Verbose* common parameter to request detailed messages about the operation.</span></span>
<span data-ttu-id="a5beb-124">有关 Verbose  的详细信息，请参阅 about_CommonParameters。</span><span class="sxs-lookup"><span data-stu-id="a5beb-124">For more information about *Verbose* , see about_CommonParameters.</span></span>

### <span data-ttu-id="a5beb-125">示例 5：运行脚本前测试连接</span><span class="sxs-lookup"><span data-stu-id="a5beb-125">Example 5: Test a connection before you run a script</span></span>

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

<span data-ttu-id="a5beb-126">此示例演示如何使用 **Test-ComputerSecureChannel** 在运行需要连接的脚本之前测试连接。</span><span class="sxs-lookup"><span data-stu-id="a5beb-126">This example shows how to use **Test-ComputerSecureChannel** to test a connection before you run a script that requires the connection.</span></span>

<span data-ttu-id="a5beb-127">第一个命令使用 Set-Alias cmdlet 为该 cmdlet 名称创建一个别名。</span><span class="sxs-lookup"><span data-stu-id="a5beb-127">The first command uses the Set-Alias cmdlet to create an alias for the cmdlet name.</span></span>
<span data-ttu-id="a5beb-128">这可节省空间并避免键入错误。</span><span class="sxs-lookup"><span data-stu-id="a5beb-128">This saves space and prevents typing errors.</span></span>

<span data-ttu-id="a5beb-129">**If** 语句将在运行脚本前检查 **Test-ComputerSecureChannel** 返回的值。</span><span class="sxs-lookup"><span data-stu-id="a5beb-129">The **If** statement checks the value that **Test-ComputerSecureChannel** returns before it runs a script.</span></span>

## <span data-ttu-id="a5beb-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5beb-130">PARAMETERS</span></span>

### <span data-ttu-id="a5beb-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="a5beb-131">-Credential</span></span>
<span data-ttu-id="a5beb-132">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a5beb-132">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="a5beb-133">键入用户名，如 User01 或 Domain01\User01；或输入一个 **PSCredential** 对象，如 Get-Credential cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="a5beb-133">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one that the Get-Credential cmdlet returns.</span></span>
<span data-ttu-id="a5beb-134">默认情况下，该 cmdlet 使用当前用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="a5beb-134">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="a5beb-135">Credential  参数设计用于使用 Repair  参数来修复计算机与域之间的通道的命令。</span><span class="sxs-lookup"><span data-stu-id="a5beb-135">The *Credential* parameter is designed for use in commands that use the *Repair* parameter to repair the channel between the computer and the domain.</span></span>

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

### <span data-ttu-id="a5beb-136">-Repair</span><span class="sxs-lookup"><span data-stu-id="a5beb-136">-Repair</span></span>
<span data-ttu-id="a5beb-137">指示此 cmdlet 删除由 NetLogon 服务建立的通道，然后再重建该通道。</span><span class="sxs-lookup"><span data-stu-id="a5beb-137">Indicates that this cmdlet removes and then rebuilds the channel established by the NetLogon service.</span></span>
<span data-ttu-id="a5beb-138">使用此参数可尝试恢复未通过测试的连接。</span><span class="sxs-lookup"><span data-stu-id="a5beb-138">Use this parameter to try to restore a connection that has failed the test.</span></span>

<span data-ttu-id="a5beb-139">若要使用此参数，则当前用户必须是本地计算机上管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="a5beb-139">To use this parameter, the current user must be a member of the Administrators group on the local computer.</span></span>

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

### <span data-ttu-id="a5beb-140">-Server</span><span class="sxs-lookup"><span data-stu-id="a5beb-140">-Server</span></span>
<span data-ttu-id="a5beb-141">指定要运行该命令的域控制器。</span><span class="sxs-lookup"><span data-stu-id="a5beb-141">Specifies the domain controller to run the command.</span></span>
<span data-ttu-id="a5beb-142">如果未指定此参数，则此 cmdlet 将选择默认域控制器来执行操作。</span><span class="sxs-lookup"><span data-stu-id="a5beb-142">If this parameter is not specified, this cmdlet selects a default domain controller for the operation.</span></span>

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

### <span data-ttu-id="a5beb-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a5beb-143">-Confirm</span></span>
<span data-ttu-id="a5beb-144">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="a5beb-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a5beb-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a5beb-145">-WhatIf</span></span>
<span data-ttu-id="a5beb-146">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="a5beb-146">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a5beb-147">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="a5beb-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a5beb-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a5beb-148">CommonParameters</span></span>
<span data-ttu-id="a5beb-149">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a5beb-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5beb-150">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a5beb-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5beb-151">输入</span><span class="sxs-lookup"><span data-stu-id="a5beb-151">INPUTS</span></span>

### <span data-ttu-id="a5beb-152">无</span><span class="sxs-lookup"><span data-stu-id="a5beb-152">None</span></span>
<span data-ttu-id="a5beb-153">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a5beb-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a5beb-154">输出</span><span class="sxs-lookup"><span data-stu-id="a5beb-154">OUTPUTS</span></span>

### <span data-ttu-id="a5beb-155">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="a5beb-155">System.Boolean</span></span>
<span data-ttu-id="a5beb-156">如果连接正常工作，则该 cmdlet 将返回 $True；否则，返回 $False。</span><span class="sxs-lookup"><span data-stu-id="a5beb-156">This cmdlet returns $True if the connection is working correctly and $False if it is not.</span></span>

## <span data-ttu-id="a5beb-157">注释</span><span class="sxs-lookup"><span data-stu-id="a5beb-157">NOTES</span></span>

* <span data-ttu-id="a5beb-158">若要在 Windows Vista 以及更高版本的 Windows 操作系统上运行 **Test-ComputerSecureChannel** 命令，请使用“以管理员身份运行”选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a5beb-158">To run a **Test-ComputerSecureChannel** command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="a5beb-159">**Test-ComputerSecureChannel** 通过使用 **I_NetLogonControl2** 函数来实现，该函数可控制 Netlogon 服务的各个方面。</span><span class="sxs-lookup"><span data-stu-id="a5beb-159">**Test-ComputerSecureChannel** is implemented by using the **I_NetLogonControl2** function, which controls various aspects of the Netlogon service.</span></span>

## <span data-ttu-id="a5beb-160">相关链接</span><span class="sxs-lookup"><span data-stu-id="a5beb-160">RELATED LINKS</span></span>

[<span data-ttu-id="a5beb-161">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="a5beb-161">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="a5beb-162">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="a5beb-162">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="a5beb-163">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="a5beb-163">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="a5beb-164">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="a5beb-164">Stop-Computer</span></span>](Stop-Computer.md)
