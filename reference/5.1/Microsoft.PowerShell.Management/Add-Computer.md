---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388342"
---
# <span data-ttu-id="172c1-103">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="172c1-103">Add-Computer</span></span>

## <span data-ttu-id="172c1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="172c1-104">SYNOPSIS</span></span>
<span data-ttu-id="172c1-105">将本地计算机添加到域或工作组中。</span><span class="sxs-lookup"><span data-stu-id="172c1-105">Add the local computer to a domain or workgroup.</span></span>

## <span data-ttu-id="172c1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="172c1-106">SYNTAX</span></span>

### <span data-ttu-id="172c1-107">域 (默认值) </span><span class="sxs-lookup"><span data-stu-id="172c1-107">Domain (Default)</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="172c1-108">工作组</span><span class="sxs-lookup"><span data-stu-id="172c1-108">Workgroup</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="172c1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="172c1-109">DESCRIPTION</span></span>

<span data-ttu-id="172c1-110">`Add-Computer`Cmdlet 将本地计算机或远程计算机添加到域或工作组中，或将它们从一个域移到另一个域。</span><span class="sxs-lookup"><span data-stu-id="172c1-110">The `Add-Computer` cmdlet adds the local computer or remote computers to a domain or workgroup, or moves them from one domain to another.</span></span> <span data-ttu-id="172c1-111">它还为添加到域中的无帐户计算机创建域帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-111">It also creates a domain account if the computer is added to the domain without an account.</span></span>

<span data-ttu-id="172c1-112">可以使用此 cmdlet 的参数来指定组织单位 (OU) 和域控制器，或执行不安全的加入。</span><span class="sxs-lookup"><span data-stu-id="172c1-112">You can use the parameters of this cmdlet to specify an organizational unit (OU) and domain controller or to perform an unsecure join.</span></span>

<span data-ttu-id="172c1-113">若要获取此命令的结果，请使用 **Verbose** 和 **PassThru** 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-113">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span>

## <span data-ttu-id="172c1-114">示例</span><span class="sxs-lookup"><span data-stu-id="172c1-114">EXAMPLES</span></span>

### <span data-ttu-id="172c1-115">示例1：将本地计算机添加到域中，然后重新启动计算机</span><span class="sxs-lookup"><span data-stu-id="172c1-115">Example 1: Add a local computer to a domain then restart the computer</span></span>

```powershell
Add-Computer -DomainName Domain01 -Restart
```

<span data-ttu-id="172c1-116">此命令将本地计算机添加到 Domain01 域，然后重新启动计算机以使更改生效。</span><span class="sxs-lookup"><span data-stu-id="172c1-116">This command adds the local computer to the Domain01 domain and then restarts the computer to make the change effective.</span></span>

### <span data-ttu-id="172c1-117">示例2：将本地计算机添加到工作组</span><span class="sxs-lookup"><span data-stu-id="172c1-117">Example 2: Add a local computer to a workgroup</span></span>

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

<span data-ttu-id="172c1-118">此命令将本地计算机添加到 Workgroup-A 工作组中。</span><span class="sxs-lookup"><span data-stu-id="172c1-118">This command adds the local computer to the Workgroup-A workgroup.</span></span>

### <span data-ttu-id="172c1-119">示例3：将本地计算机添加到域</span><span class="sxs-lookup"><span data-stu-id="172c1-119">Example 3: Add a local computer to a domain</span></span>

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

<span data-ttu-id="172c1-120">此命令使用 Domain01\DC01 域控制器将本地计算机添加到 Domain01 域中。</span><span class="sxs-lookup"><span data-stu-id="172c1-120">This command adds the local computer to the Domain01 domain by using the Domain01\DC01 domain controller.</span></span>

<span data-ttu-id="172c1-121">该命令使用 **PassThru** 和 **Verbose** 参数来获取有关命令结果的详细信息。</span><span class="sxs-lookup"><span data-stu-id="172c1-121">The command uses the **PassThru** and **Verbose** parameters to get detailed information about the results of the command.</span></span>

### <span data-ttu-id="172c1-122">示例4：使用 OUPath 参数将本地计算机添加到域</span><span class="sxs-lookup"><span data-stu-id="172c1-122">Example 4: Add a local computer to a domain using the OUPath parameter</span></span>

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

<span data-ttu-id="172c1-123">此命令将本地计算机添加到 Domain02 域中。</span><span class="sxs-lookup"><span data-stu-id="172c1-123">This command adds the local computer to the Domain02 domain.</span></span>
<span data-ttu-id="172c1-124">它使用 OUPath 参数为新帐户指定组织单位。</span><span class="sxs-lookup"><span data-stu-id="172c1-124">It uses the OUPath parameter to specify the organizational unit for the new accounts.</span></span>

### <span data-ttu-id="172c1-125">示例5：使用凭据将本地计算机添加到域</span><span class="sxs-lookup"><span data-stu-id="172c1-125">Example 5: Add a local computer to a domain using credentials</span></span>

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

<span data-ttu-id="172c1-126">此命令将 Server01 计算机添加到 Domain02 域中。</span><span class="sxs-lookup"><span data-stu-id="172c1-126">This command adds the Server01 computer to the Domain02 domain.</span></span> <span data-ttu-id="172c1-127">它使用 **LocalCredential** 参数指定有权连接到 Server01 计算机的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-127">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the Server01 computer.</span></span> <span data-ttu-id="172c1-128">它使用 **Credential** 参数指定有权将计算机加入到域中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-128">It uses the **Credential** parameter to specify a user account that has permission to join computers to the domain.</span></span> <span data-ttu-id="172c1-129">它使用 **Restart** 参数在加入操作完成后重新启动计算机，并使用 **Force** 参数取消用户确认消息。</span><span class="sxs-lookup"><span data-stu-id="172c1-129">It uses the **Restart** parameter to restart the computer after the join operation completes and the **Force** parameter to suppress user confirmation messages.</span></span>

### <span data-ttu-id="172c1-130">示例6：将一组计算机移到新域</span><span class="sxs-lookup"><span data-stu-id="172c1-130">Example 6: Move a group of computers to a new domain</span></span>

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="172c1-131">此命令将 Server01 和 Server02 计算机以及本地计算机从 Domain01 移至 Domain02。</span><span class="sxs-lookup"><span data-stu-id="172c1-131">This command moves the Server01 and Server02 computers, and the local computer, from Domain01 to Domain02.</span></span>

<span data-ttu-id="172c1-132">它使用 **LocalCredential** 参数指定有权连接到这三台受影响的计算机的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-132">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the three affected computers.</span></span> <span data-ttu-id="172c1-133">它使用 **UnjoinDomainCredential** 参数指定有权将计算机退出 Domain01 域的用户帐户，并使用 **Credential** 参数指定有权将计算机加入到 Domain02 域的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-133">It uses the **UnjoinDomainCredential** parameter to specify a user account that has permission to unjoin the computers from the Domain01 domain and the **Credential** parameter to specify a user account that has permission to join the computers to the Domain02 domain.</span></span> <span data-ttu-id="172c1-134">它使用 **Restart** 参数在移动操作完成后重新启动所有三台计算机。</span><span class="sxs-lookup"><span data-stu-id="172c1-134">It uses the **Restart** parameter to restart all three computers after the move is complete.</span></span>

### <span data-ttu-id="172c1-135">示例7：将计算机移到新域并更改计算机的名称</span><span class="sxs-lookup"><span data-stu-id="172c1-135">Example 7: Move a computer to a new domain and change the name of the computer</span></span>

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="172c1-136">此命令将 Server01 计算机移至 Domain02 并将计算机名称更改为 Server044。</span><span class="sxs-lookup"><span data-stu-id="172c1-136">This command moves the Server01 computer to the Domain02 and changes the machine name to Server044.</span></span>

<span data-ttu-id="172c1-137">该命令使用当前用户的凭据连接到 Server01 计算机并将其从其当前域中退出。</span><span class="sxs-lookup"><span data-stu-id="172c1-137">The command uses the credential of the current user to connect to the Server01 computer and unjoin it from its current domain.</span></span> <span data-ttu-id="172c1-138">它使用 **Credential** 参数指定有权将计算机加入到 Domain02 域中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-138">It uses the **Credential** parameter to specify a user account that has permission to join the computer to the Domain02 domain.</span></span>

### <span data-ttu-id="172c1-139">示例8：将文件中列出的计算机添加到新域</span><span class="sxs-lookup"><span data-stu-id="172c1-139">Example 8: Add computers listed in a file to a new domain</span></span>

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

<span data-ttu-id="172c1-140">此命令将 Servers.txt 文件中列出的计算机添加到 Domain02 域。</span><span class="sxs-lookup"><span data-stu-id="172c1-140">This command adds the computers that are listed in the Servers.txt file to the Domain02 domain.</span></span> <span data-ttu-id="172c1-141">它使用 **Options** 参数来指定 **Win9xUpgrade** 选项。</span><span class="sxs-lookup"><span data-stu-id="172c1-141">It uses the **Options** parameter to specify the **Win9xUpgrade** option.</span></span> <span data-ttu-id="172c1-142">**Restart** 参数将在加入操作完成后重新启动所有新添加的计算机。</span><span class="sxs-lookup"><span data-stu-id="172c1-142">The **Restart** parameter restarts all of the newly added computers after the join operation completes.</span></span>

### <span data-ttu-id="172c1-143">示例9：使用预定义的计算机凭据将计算机添加到域</span><span class="sxs-lookup"><span data-stu-id="172c1-143">Example 9: Add a computer to a domain using predefined computer credentials</span></span>

<span data-ttu-id="172c1-144">此第一个命令应由管理员从已加入域的计算机运行 `Domain03` ：</span><span class="sxs-lookup"><span data-stu-id="172c1-144">This first command should be run by an administrator from a computer that is already joined to domain `Domain03`:</span></span>

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

<span data-ttu-id="172c1-145">此命令组合使用现有的已加入域的计算机在域中创建一个具有预定义名称和临时联接密码的新计算机帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-145">This combination of commands creates a new computer account with a predefined name and temporary join password in a domain using an existing domain-joined computer.</span></span> <span data-ttu-id="172c1-146">然后，单独使用具有预定义名称的计算机仅使用计算机名称和临时联接密码加入域。</span><span class="sxs-lookup"><span data-stu-id="172c1-146">Then separately, a computer with the predefined name joins the domain using only the computer name and the temporary join password.</span></span>
<span data-ttu-id="172c1-147">预定义的密码仅用于支持联接操作，并且在计算机完成联接后被替换为普通计算机帐户过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="172c1-147">The predefined password is only used to support the join operation and is replaced as part of normal computer account procedures after the computer completes the join.</span></span>

## <span data-ttu-id="172c1-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="172c1-148">PARAMETERS</span></span>

### <span data-ttu-id="172c1-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="172c1-149">-ComputerName</span></span>

<span data-ttu-id="172c1-150">指定要添加到域或工作组中的计算机。</span><span class="sxs-lookup"><span data-stu-id="172c1-150">Specifies the computers to add to a domain or workgroup.</span></span>
<span data-ttu-id="172c1-151">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="172c1-151">The default is the local computer.</span></span>

<span data-ttu-id="172c1-152">键入每台远程计算机的 NetBIOS 名称、Internet 协议 (IP) 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="172c1-152">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of each of the remote computers.</span></span> <span data-ttu-id="172c1-153">若要指定本地计算机，请键入计算机名、点 (`.`) 或 "localhost"。</span><span class="sxs-lookup"><span data-stu-id="172c1-153">To specify the local computer, type the computer name, a dot (`.`), or "localhost".</span></span>

<span data-ttu-id="172c1-154">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="172c1-154">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="172c1-155">**ComputerName** `Add-Computer` 即使你的计算机未配置为运行远程命令，你也可以使用 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-155">You can use the **ComputerName** parameter of `Add-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="172c1-156">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="172c1-156">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="172c1-157">-Credential</span></span>

<span data-ttu-id="172c1-158">指定有权将计算机加入新域的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-158">Specifies a user account that has permission to join the computers to a new domain.</span></span>
<span data-ttu-id="172c1-159">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="172c1-159">The default is the current user.</span></span>

<span data-ttu-id="172c1-160">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="172c1-160">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="172c1-161">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="172c1-161">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="172c1-162">若要指定有权将计算机从其当前域中删除的用户帐户，请使用 **UnjoinDomainCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-162">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span> <span data-ttu-id="172c1-163">若要指定有权连接到远程计算机的用户帐户，请使用 **LocalCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-163">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-164">-DomainName</span><span class="sxs-lookup"><span data-stu-id="172c1-164">-DomainName</span></span>

<span data-ttu-id="172c1-165">指定要向其中添加计算机的域。</span><span class="sxs-lookup"><span data-stu-id="172c1-165">Specifies the domain to which the computers are added.</span></span> <span data-ttu-id="172c1-166">在将计算机添加到域时需要使用此参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-166">This parameter is required when adding the computers to a domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-167">-Force</span><span class="sxs-lookup"><span data-stu-id="172c1-167">-Force</span></span>

<span data-ttu-id="172c1-168">取消用户确认提示。</span><span class="sxs-lookup"><span data-stu-id="172c1-168">Suppresses the user confirmation prompt.</span></span> <span data-ttu-id="172c1-169">如果没有此参数， `Add-Computer` 则要求你确认是否添加了每台计算机。</span><span class="sxs-lookup"><span data-stu-id="172c1-169">Without this parameter, `Add-Computer` requires you to confirm the addition of each computer.</span></span>

<span data-ttu-id="172c1-170">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="172c1-170">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="172c1-171">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="172c1-171">-LocalCredential</span></span>

<span data-ttu-id="172c1-172">指定有权连接到由 **ComputerName** 参数指定的计算机的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-172">Specifies a user account that has permission to connect to the computers that are specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="172c1-173">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="172c1-173">The default is the current user.</span></span>

<span data-ttu-id="172c1-174">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="172c1-174">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="172c1-175">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="172c1-175">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="172c1-176">若要指定有权将计算机添加到新域的用户帐户，请使用 **Credential** 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-176">To specify a user account that has permission to add the computers to a new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="172c1-177">若要指定有权将计算机从其当前域中删除的用户帐户，请使用 **UnjoinDomainCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-177">To specify a user account that has permission to remove the computers from their current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="172c1-178">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="172c1-178">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-179">-NewName</span><span class="sxs-lookup"><span data-stu-id="172c1-179">-NewName</span></span>

<span data-ttu-id="172c1-180">在新域中指定计算机的新名称。</span><span class="sxs-lookup"><span data-stu-id="172c1-180">Specifies a new name for the computer in the new domain.</span></span> <span data-ttu-id="172c1-181">此参数仅在一台计算机被添加或移动时有效。</span><span class="sxs-lookup"><span data-stu-id="172c1-181">This parameter is valid only when one computer is being added or moved.</span></span>

<span data-ttu-id="172c1-182">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="172c1-182">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-183">-Options</span><span class="sxs-lookup"><span data-stu-id="172c1-183">-Options</span></span>

<span data-ttu-id="172c1-184">指定用于 **添加计算机** 加入操作的高级选项。</span><span class="sxs-lookup"><span data-stu-id="172c1-184">Specifies advanced options for the **Add-Computer** join operation.</span></span> <span data-ttu-id="172c1-185">在逗号分隔的字符串中输入一个或多个值。</span><span class="sxs-lookup"><span data-stu-id="172c1-185">Enter one or more values in a comma-separated string.</span></span>

<span data-ttu-id="172c1-186">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="172c1-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="172c1-187">**帐户** ：创建域帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-187">**AccountCreate** : Creates a domain account.</span></span> <span data-ttu-id="172c1-188">将计算机添加到域时， **添加计算机** cmdlet 会自动创建一个域帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-188">The **Add-Computer** cmdlet automatically creates a domain account when it adds a computer to a domain.</span></span> <span data-ttu-id="172c1-189">提供此选项是为了提供完整性。</span><span class="sxs-lookup"><span data-stu-id="172c1-189">This option is included for completeness.</span></span>

- <span data-ttu-id="172c1-190">**Win9XUpgrade** ：指示加入操作是 Windows 操作系统升级的一部分。</span><span class="sxs-lookup"><span data-stu-id="172c1-190">**Win9XUpgrade** : Indicates that the join operation is part of a Windows operating system upgrade.</span></span>

- <span data-ttu-id="172c1-191">**UnsecuredJoin** ：执行不安全的联接。</span><span class="sxs-lookup"><span data-stu-id="172c1-191">**UnsecuredJoin** : Performs an unsecured join.</span></span> <span data-ttu-id="172c1-192">若要请求不安全的联接，请使用不 *安全* 的参数或此选项。</span><span class="sxs-lookup"><span data-stu-id="172c1-192">To request an unsecured join, use the *Unsecure* parameter or this option.</span></span> <span data-ttu-id="172c1-193">如果要传递计算机密码，则必须将此选项与选项结合使用 `PasswordPass` 。</span><span class="sxs-lookup"><span data-stu-id="172c1-193">If you want to pass a machine password, then you must use this option in combination with `PasswordPass` option.</span></span>

- <span data-ttu-id="172c1-194">**PasswordPass** ：在执行不安全的联接后，将计算机密码设置为 *Credential* (DomainCredential) 参数的值。</span><span class="sxs-lookup"><span data-stu-id="172c1-194">**PasswordPass** : Sets the machine password to the value of the *Credential* (DomainCredential) parameter after performing an unsecured join.</span></span> <span data-ttu-id="172c1-195">此选项还表示 *Credential* (DomainCredential) 参数的值为计算机密码，而不是用户密码。</span><span class="sxs-lookup"><span data-stu-id="172c1-195">This option also indicates that the value of the *Credential* (DomainCredential) parameter is a machine password, not a user password.</span></span> <span data-ttu-id="172c1-196">仅当指定了选项时，此选项才有效 `UnsecuredJoin` 。</span><span class="sxs-lookup"><span data-stu-id="172c1-196">This option is valid only when the `UnsecuredJoin` option is specified.</span></span> <span data-ttu-id="172c1-197">使用此选项时，为参数提供的凭据 `-Credential` *必须* 为 null 用户名。</span><span class="sxs-lookup"><span data-stu-id="172c1-197">When using this option, the credential provided to the `-Credential` parameter *must* have a null username.</span></span>

- <span data-ttu-id="172c1-198">**JoinWithNewName** ：将新域中的计算机名称重命名为 *NewName* 参数指定的名称。</span><span class="sxs-lookup"><span data-stu-id="172c1-198">**JoinWithNewName** : Renames the computer name in the new domain to the name specified by the *NewName* parameter.</span></span> <span data-ttu-id="172c1-199">在使用 *NewName* 参数时，此选项将自动设置。</span><span class="sxs-lookup"><span data-stu-id="172c1-199">When you use the *NewName* parameter, this option is set automatically.</span></span> <span data-ttu-id="172c1-200">此选项设计为与 Rename-Computer cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="172c1-200">This option is designed to be used with the Rename-Computer cmdlet.</span></span> <span data-ttu-id="172c1-201">如果使用 **重命名计算机** cmdlet 重命名计算机，但不重新启动计算机以使更改生效，则可以使用此参数将计算机加入到具有其新名称的域中。</span><span class="sxs-lookup"><span data-stu-id="172c1-201">If you use the **Rename-Computer** cmdlet to rename the computer, but do not restart the computer to make the change effective, you can use this parameter to join the computer to a domain with its new name.</span></span>

- <span data-ttu-id="172c1-202">**JoinReadOnly** ：使用现有计算机帐户将计算机加入到只读域控制器。</span><span class="sxs-lookup"><span data-stu-id="172c1-202">**JoinReadOnly** : Uses an existing machine account to join the computer to a read-only domain controller.</span></span> <span data-ttu-id="172c1-203">必须将计算机帐户添加到密码复制策略的允许列表中，并且必须在加入操作之前将帐户密码复制到只读域控制器。</span><span class="sxs-lookup"><span data-stu-id="172c1-203">The machine account must be added to the allowed list for password replication policy and the account password must be replicated to the read-only domain controller prior to the join operation.</span></span>

- <span data-ttu-id="172c1-204">**InstallInvoke** ：设置 **JoinDomainOrWorkgroup** 方法的 **FJoinOptions** 参数的 create (0x2) 并删除 (0x4) 标志。</span><span class="sxs-lookup"><span data-stu-id="172c1-204">**InstallInvoke** : Sets the create (0x2) and delete (0x4) flags of the **FJoinOptions** parameter of the **JoinDomainOrWorkgroup** method.</span></span> <span data-ttu-id="172c1-205">有关 **JoinDomainOrWorkgroup** 方法的详细信息，请参阅 [Win32_ComputerSystem 类的 JoinDomainOrWorkgroup 方法](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem)。</span><span class="sxs-lookup"><span data-stu-id="172c1-205">For more information about the **JoinDomainOrWorkgroup** method, see [JoinDomainOrWorkgroup method of the Win32_ComputerSystem class](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span></span>
  <span data-ttu-id="172c1-206">有关这些选项的详细信息，请参阅 [NetJoinDomain 函数](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain)。</span><span class="sxs-lookup"><span data-stu-id="172c1-206">For more information about these options, see [NetJoinDomain function](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).</span></span>

<span data-ttu-id="172c1-207">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-208">-OUPath</span><span class="sxs-lookup"><span data-stu-id="172c1-208">-OUPath</span></span>

<span data-ttu-id="172c1-209">为域帐户指定组织单位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="172c1-209">Specifies an organizational unit (OU) for the domain account.</span></span> <span data-ttu-id="172c1-210">在引号中输入 OU 的完全可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="172c1-210">Enter the full distinguished name of the OU in quotation marks.</span></span> <span data-ttu-id="172c1-211">默认值为域中计算机对象的默认 OU。</span><span class="sxs-lookup"><span data-stu-id="172c1-211">The default value is the default OU for machine objects in the domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-212">-PassThru</span><span class="sxs-lookup"><span data-stu-id="172c1-212">-PassThru</span></span>

<span data-ttu-id="172c1-213">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="172c1-213">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="172c1-214">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="172c1-214">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="172c1-215">-Restart</span><span class="sxs-lookup"><span data-stu-id="172c1-215">-Restart</span></span>

<span data-ttu-id="172c1-216">重启已添加到域或工作组中的计算机。</span><span class="sxs-lookup"><span data-stu-id="172c1-216">Restarts the computers that were added to the domain or workgroup.</span></span> <span data-ttu-id="172c1-217">若要更改生效，通常需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="172c1-217">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="172c1-218">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="172c1-218">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="172c1-219">-Server</span><span class="sxs-lookup"><span data-stu-id="172c1-219">-Server</span></span>

<span data-ttu-id="172c1-220">指定向域中添加计算机的域控制器的名称。</span><span class="sxs-lookup"><span data-stu-id="172c1-220">Specifies the name of a domain controller that adds the computer to the domain.</span></span> <span data-ttu-id="172c1-221">以 DomainName\ComputerName 格式输入该名称。</span><span class="sxs-lookup"><span data-stu-id="172c1-221">Enter the name in DomainName\ComputerName format.</span></span> <span data-ttu-id="172c1-222">默认情况下，将不指定域控制器。</span><span class="sxs-lookup"><span data-stu-id="172c1-222">By default, no domain controller is specified.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-223">-UnjoinDomainCredential</span><span class="sxs-lookup"><span data-stu-id="172c1-223">-UnjoinDomainCredential</span></span>

<span data-ttu-id="172c1-224">指定有权将计算机从其当前域中删除的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="172c1-224">Specifies a user account that has permission to remove the computers from their current domains.</span></span> <span data-ttu-id="172c1-225">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="172c1-225">The default is the current user.</span></span>

<span data-ttu-id="172c1-226">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="172c1-226">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="172c1-227">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="172c1-227">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="172c1-228">在将计算机移动到不同的域中时使用此参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-228">Use this parameter when you are moving computers to a different domain.</span></span> <span data-ttu-id="172c1-229">若要指定有权加入新域的用户帐户，请使用 **Credential** 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-229">To specify a user account that has permission to join the new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="172c1-230">若要指定有权连接到远程计算机的用户帐户，请使用 **LocalCredential** 参数。</span><span class="sxs-lookup"><span data-stu-id="172c1-230">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="172c1-231">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="172c1-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-232">-不安全</span><span class="sxs-lookup"><span data-stu-id="172c1-232">-Unsecure</span></span>

<span data-ttu-id="172c1-233">执行不安全的加入指定域的操作。</span><span class="sxs-lookup"><span data-stu-id="172c1-233">Performs an unsecure join to the specified domain.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-234">-WorkgroupName</span><span class="sxs-lookup"><span data-stu-id="172c1-234">-WorkgroupName</span></span>

<span data-ttu-id="172c1-235">指定要将计算机添加到的工作组的名称。</span><span class="sxs-lookup"><span data-stu-id="172c1-235">Specifies the name of a workgroup to which the computers are added.</span></span> <span data-ttu-id="172c1-236">默认值为“WORKGROUP”。</span><span class="sxs-lookup"><span data-stu-id="172c1-236">The default value is "WORKGROUP".</span></span>

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="172c1-237">-Confirm</span><span class="sxs-lookup"><span data-stu-id="172c1-237">-Confirm</span></span>

<span data-ttu-id="172c1-238">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="172c1-238">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="172c1-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="172c1-239">-WhatIf</span></span>

<span data-ttu-id="172c1-240">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="172c1-240">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="172c1-241">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="172c1-241">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="172c1-242">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="172c1-242">CommonParameters</span></span>

<span data-ttu-id="172c1-243">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="172c1-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="172c1-244">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="172c1-244">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="172c1-245">输入</span><span class="sxs-lookup"><span data-stu-id="172c1-245">INPUTS</span></span>

### <span data-ttu-id="172c1-246">System.String</span><span class="sxs-lookup"><span data-stu-id="172c1-246">System.String</span></span>

<span data-ttu-id="172c1-247">可以通过管道将计算机名称和新名称传递给 `Add-Computer` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="172c1-247">You can pipe computer names and new names to the `Add-Computer` Cmdlet.</span></span>

## <span data-ttu-id="172c1-248">输出</span><span class="sxs-lookup"><span data-stu-id="172c1-248">OUTPUTS</span></span>

### <span data-ttu-id="172c1-249">Microsoft.PowerShell.Commands.ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="172c1-249">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="172c1-250">当使用 **PassThru** 参数时，将 `Add-Computer` 返回 **ComputerChangeInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="172c1-250">When you use the **PassThru** parameter, `Add-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="172c1-251">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="172c1-251">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="172c1-252">注释</span><span class="sxs-lookup"><span data-stu-id="172c1-252">NOTES</span></span>

- <span data-ttu-id="172c1-253">在 Windows PowerShell 2.0 中， **服务器** 参数 `Add-Computer` 失败即使服务器存在也会失败。</span><span class="sxs-lookup"><span data-stu-id="172c1-253">In Windows PowerShell 2.0, the **Server** parameter of `Add-Computer` fails even when the server is present.</span></span> <span data-ttu-id="172c1-254">在 Windows PowerShell 3.0 中，将更改 **Server** 参数的实现方式，以便它能够稳定运行。</span><span class="sxs-lookup"><span data-stu-id="172c1-254">In Windows PowerShell 3.0, the implementation of the **Server** parameter is changed so that it works reliably.</span></span>

## <span data-ttu-id="172c1-255">相关链接</span><span class="sxs-lookup"><span data-stu-id="172c1-255">RELATED LINKS</span></span>

[<span data-ttu-id="172c1-256">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="172c1-256">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="172c1-257">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="172c1-257">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="172c1-258">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="172c1-258">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="172c1-259">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="172c1-259">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="172c1-260">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="172c1-260">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="172c1-261">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="172c1-261">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="172c1-262">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="172c1-262">Test-Connection</span></span>](Test-Connection.md)
