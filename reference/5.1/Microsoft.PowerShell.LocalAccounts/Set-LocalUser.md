---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalUser
ms.openlocfilehash: a6352611b757dae828a2efef07f9ce65abaa5e2e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198334"
---
# <span data-ttu-id="66406-103">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66406-103">Set-LocalUser</span></span>

## <span data-ttu-id="66406-104">摘要</span><span class="sxs-lookup"><span data-stu-id="66406-104">SYNOPSIS</span></span>
<span data-ttu-id="66406-105">修改本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="66406-105">Modifies a local user account.</span></span>

## <span data-ttu-id="66406-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66406-106">SYNTAX</span></span>

### <span data-ttu-id="66406-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="66406-107">Name (Default)</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Name] <String> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="66406-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="66406-108">InputObject</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-InputObject] <LocalUser> [-Password <SecureString>] [-PasswordNeverExpires <Boolean>]
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="66406-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="66406-109">SecurityIdentifier</span></span>

```
Set-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-FullName <String>]
 [-Password <SecureString>] [-PasswordNeverExpires <Boolean>] [-SID] <SecurityIdentifier>
 [-UserMayChangePassword <Boolean>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="66406-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66406-110">DESCRIPTION</span></span>
<span data-ttu-id="66406-111">**LocalUser** cmdlet 修改本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="66406-111">The **Set-LocalUser** cmdlet modifies a local user account.</span></span>
<span data-ttu-id="66406-112">此 cmdlet 可以重置本地用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="66406-112">This cmdlet can reset the password of a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="66406-113">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="66406-113">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="66406-114">示例</span><span class="sxs-lookup"><span data-stu-id="66406-114">EXAMPLES</span></span>

### <span data-ttu-id="66406-115">示例1：更改用户帐户的说明</span><span class="sxs-lookup"><span data-stu-id="66406-115">Example 1: Change a description of a user account</span></span>

```
PS C:\> Set-LocalUser -Name "Admin07" -Description "Description of this account."
```

<span data-ttu-id="66406-116">此命令更改名为 Admin07 的用户帐户的说明。</span><span class="sxs-lookup"><span data-stu-id="66406-116">This command changes the description of a user account named Admin07.</span></span>

### <span data-ttu-id="66406-117">示例2：更改帐户的密码</span><span class="sxs-lookup"><span data-stu-id="66406-117">Example 2: Change the password on an account</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> $UserAccount = Get-LocalUser -Name "User02"
PS C:\> $UserAccount | Set-LocalUser -Password $Password
```

<span data-ttu-id="66406-118">第一个命令使用 Read-Host cmdlet 提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="66406-118">The first command prompts you for a password by using the Read-Host cmdlet.</span></span>
<span data-ttu-id="66406-119">此命令将密码存储为 $Password 变量中的安全字符串。</span><span class="sxs-lookup"><span data-stu-id="66406-119">The command stores the password as a secure string in the $Password variable.</span></span>

<span data-ttu-id="66406-120">第二个命令使用 **LocalUser** 获取名为 User02 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="66406-120">The second command gets a user account named User02 by using **Get-LocalUser** .</span></span>
<span data-ttu-id="66406-121">该命令将帐户存储在 $UserAccount 的变量中。</span><span class="sxs-lookup"><span data-stu-id="66406-121">The command stores the account in the $UserAccount variable.</span></span>

<span data-ttu-id="66406-122">第三个命令在 $UserAccount 中存储的用户帐户上设置新密码。</span><span class="sxs-lookup"><span data-stu-id="66406-122">The third command sets the new password on the user account stored in $UserAccount.</span></span>

## <span data-ttu-id="66406-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66406-123">PARAMETERS</span></span>

### <span data-ttu-id="66406-124">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="66406-124">-AccountExpires</span></span>
<span data-ttu-id="66406-125">指定用户帐户的过期时间。</span><span class="sxs-lookup"><span data-stu-id="66406-125">Specifies when the user account expires.</span></span>
<span data-ttu-id="66406-126">若要获取 **DateTime** 对象，请使用 Get-Date cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66406-126">To obtain a **DateTime** object, use the Get-Date cmdlet.</span></span>

<span data-ttu-id="66406-127">如果你不希望帐户过期，请指定 *AccountNeverExpires* 参数。</span><span class="sxs-lookup"><span data-stu-id="66406-127">If you do not want the account to expire, specify the *AccountNeverExpires* parameter.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66406-128">-AccountNeverExpires</span><span class="sxs-lookup"><span data-stu-id="66406-128">-AccountNeverExpires</span></span>
<span data-ttu-id="66406-129">指示帐户未过期。</span><span class="sxs-lookup"><span data-stu-id="66406-129">Indicates that the account does not expire.</span></span>

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

### <span data-ttu-id="66406-130">-Description</span><span class="sxs-lookup"><span data-stu-id="66406-130">-Description</span></span>
<span data-ttu-id="66406-131">指定用户帐户的注释。</span><span class="sxs-lookup"><span data-stu-id="66406-131">Specifies a comment for the user account.</span></span>
<span data-ttu-id="66406-132">最大长度为48个字符。</span><span class="sxs-lookup"><span data-stu-id="66406-132">The maximum length is 48 characters.</span></span>

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

### <span data-ttu-id="66406-133">-FullName</span><span class="sxs-lookup"><span data-stu-id="66406-133">-FullName</span></span>
<span data-ttu-id="66406-134">指定用户帐户的全名。</span><span class="sxs-lookup"><span data-stu-id="66406-134">Specifies the full name for the user account.</span></span>
<span data-ttu-id="66406-135">全名不同于用户帐户的用户名。</span><span class="sxs-lookup"><span data-stu-id="66406-135">The full name differs from the user name of the user account.</span></span>

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

### <span data-ttu-id="66406-136">-InputObject</span><span class="sxs-lookup"><span data-stu-id="66406-136">-InputObject</span></span>
<span data-ttu-id="66406-137">指定此 cmdlet 更改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="66406-137">Specifies the user account that this cmdlet changes.</span></span>
<span data-ttu-id="66406-138">若要获取用户帐户，请使用 Get-LocalUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66406-138">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66406-139">-Name</span><span class="sxs-lookup"><span data-stu-id="66406-139">-Name</span></span>
<span data-ttu-id="66406-140">指定此 cmdlet 更改的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="66406-140">Specifies the name of the user account that this cmdlet changes.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66406-141">-Password</span><span class="sxs-lookup"><span data-stu-id="66406-141">-Password</span></span>
<span data-ttu-id="66406-142">指定用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="66406-142">Specifies a password for the user account.</span></span>
<span data-ttu-id="66406-143">如果用户帐户已连接到 Microsoft 帐户，请不要设置密码。</span><span class="sxs-lookup"><span data-stu-id="66406-143">If the user account is connected to a Microsoft account, do not set a password.</span></span>

<span data-ttu-id="66406-144">可以使用 `Read-Host -GetCredential` 、Get-Credential 或 ConvertTo-SecureString 为密码创建 **SecureString** 对象。</span><span class="sxs-lookup"><span data-stu-id="66406-144">You can use `Read-Host -GetCredential`, Get-Credential, or ConvertTo-SecureString to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="66406-145">如果省略 *Password* 和 *NoPassword* 参数，则 **LocalUser** 会提示用户输入用户的密码。</span><span class="sxs-lookup"><span data-stu-id="66406-145">If you omit the *Password* and *NoPassword* parameters, **Set-LocalUser** prompts you for the user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66406-146">-PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="66406-146">-PasswordNeverExpires</span></span>
<span data-ttu-id="66406-147">指示密码是否过期。</span><span class="sxs-lookup"><span data-stu-id="66406-147">Indicates whether the password expires.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66406-148">-SID</span><span class="sxs-lookup"><span data-stu-id="66406-148">-SID</span></span>
<span data-ttu-id="66406-149">指定此 cmdlet 更改的用户帐户 (SID) 的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="66406-149">Specifies the security ID (SID) of the user account that this cmdlet changes.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="66406-150">-UserMayChangePassword</span><span class="sxs-lookup"><span data-stu-id="66406-150">-UserMayChangePassword</span></span>
<span data-ttu-id="66406-151">指示用户可以更改用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="66406-151">Indicates that the user can change the password on the user account.</span></span>

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="66406-152">-Confirm</span><span class="sxs-lookup"><span data-stu-id="66406-152">-Confirm</span></span>
<span data-ttu-id="66406-153">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="66406-153">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="66406-154">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="66406-154">-WhatIf</span></span>
<span data-ttu-id="66406-155">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="66406-155">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="66406-156">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="66406-156">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="66406-157">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66406-157">CommonParameters</span></span>
<span data-ttu-id="66406-158">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="66406-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66406-159">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="66406-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66406-160">输入</span><span class="sxs-lookup"><span data-stu-id="66406-160">INPUTS</span></span>

### <span data-ttu-id="66406-161">SecurityAccountsManager. LocalUser、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="66406-161">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="66406-162">可以通过管道将本地用户、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66406-162">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="66406-163">输出</span><span class="sxs-lookup"><span data-stu-id="66406-163">OUTPUTS</span></span>

### <span data-ttu-id="66406-164">无</span><span class="sxs-lookup"><span data-stu-id="66406-164">None</span></span>
<span data-ttu-id="66406-165">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="66406-165">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="66406-166">注释</span><span class="sxs-lookup"><span data-stu-id="66406-166">NOTES</span></span>

* <span data-ttu-id="66406-167">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="66406-167">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="66406-168">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="66406-168">The possible sources are as follows:</span></span>

- <span data-ttu-id="66406-169">Local</span><span class="sxs-lookup"><span data-stu-id="66406-169">Local</span></span>
- <span data-ttu-id="66406-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="66406-170">Active Directory</span></span>
- <span data-ttu-id="66406-171">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="66406-171">Azure Active Directory group</span></span>
- <span data-ttu-id="66406-172">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="66406-172">Microsoft Account</span></span>

<span data-ttu-id="66406-173">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="66406-173">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="66406-174">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="66406-174">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="66406-175">相关链接</span><span class="sxs-lookup"><span data-stu-id="66406-175">RELATED LINKS</span></span>

[<span data-ttu-id="66406-176">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66406-176">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="66406-177">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66406-177">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="66406-178">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66406-178">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="66406-179">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66406-179">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="66406-180">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66406-180">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="66406-181">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66406-181">Rename-LocalUser</span></span>](Rename-LocalUser.md)
