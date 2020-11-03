---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalUser
ms.openlocfilehash: d83f3ad12481df0849ff2fe3f61d553a9ffdcdde
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198098"
---
# <span data-ttu-id="7694d-103">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7694d-103">New-LocalUser</span></span>

## <span data-ttu-id="7694d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7694d-104">SYNOPSIS</span></span>

<span data-ttu-id="7694d-105">创建本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7694d-105">Creates a local user account.</span></span>

## <span data-ttu-id="7694d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7694d-106">SYNTAX</span></span>

### <span data-ttu-id="7694d-107">密码 (默认值) </span><span class="sxs-lookup"><span data-stu-id="7694d-107">Password (Default)</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> -Password <SecureString> [-PasswordNeverExpires]
 [-UserMayNotChangePassword] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="7694d-108">NoPassword</span><span class="sxs-lookup"><span data-stu-id="7694d-108">NoPassword</span></span>

```
New-LocalUser [-AccountExpires <DateTime>] [-AccountNeverExpires] [-Description <String>] [-Disabled]
 [-FullName <String>] [-Name] <String> [-NoPassword] [-UserMayNotChangePassword] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="7694d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7694d-109">DESCRIPTION</span></span>

<span data-ttu-id="7694d-110">`New-LocalUser`Cmdlet 将创建一个本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7694d-110">The `New-LocalUser` cmdlet creates a local user account.</span></span> <span data-ttu-id="7694d-111">此 cmdlet 将创建一个连接到 Microsoft 帐户的本地用户帐户或本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7694d-111">This cmdlet creates a local user account or a local user account that is connected to a Microsoft account.</span></span>

> [!NOTE]
> <span data-ttu-id="7694d-112">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="7694d-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="7694d-113">示例</span><span class="sxs-lookup"><span data-stu-id="7694d-113">EXAMPLES</span></span>

### <span data-ttu-id="7694d-114">示例1：创建用户帐户</span><span class="sxs-lookup"><span data-stu-id="7694d-114">Example 1: Create a user account</span></span>

```
PS C:\> New-LocalUser -Name "User02" -Description "Description of this account." -NoPassword
Name    Enabled  Description
----    -------  -----------
User02  True     Description of this account.
```

<span data-ttu-id="7694d-115">此命令将创建一个本地用户帐户，并且不指定 **AccountExpires** 或 **Password** 参数。</span><span class="sxs-lookup"><span data-stu-id="7694d-115">This command creates a local user account and does not specify the **AccountExpires** or **Password** parameters.</span></span> <span data-ttu-id="7694d-116">因此，该帐户不会过期或默认具有密码。</span><span class="sxs-lookup"><span data-stu-id="7694d-116">Therefore, the account doesn't expire or have a password by default.</span></span>

### <span data-ttu-id="7694d-117">示例2：创建具有密码的用户帐户</span><span class="sxs-lookup"><span data-stu-id="7694d-117">Example 2: Create a user account that has a password</span></span>

```
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> New-LocalUser "User03" -Password $Password -FullName "Third User" -Description "Description of this account."
Name    Enabled  Description
----    -------  -----------
User03  True     Description of this account.
```

<span data-ttu-id="7694d-118">第一个命令使用 cmdlet 提示你输入密码 `Read-Host` 。</span><span class="sxs-lookup"><span data-stu-id="7694d-118">The first command prompts you for a password by using the `Read-Host` cmdlet.</span></span> <span data-ttu-id="7694d-119">该命令将密码作为安全字符串存储在变量中 `$Password` 。</span><span class="sxs-lookup"><span data-stu-id="7694d-119">The command stores the password as a secure string in the `$Password` variable.</span></span>

<span data-ttu-id="7694d-120">第二个命令使用存储在中的密码创建一个本地用户帐户 `$Password` 。</span><span class="sxs-lookup"><span data-stu-id="7694d-120">The second command creates a local user account by using the password stored in `$Password`.</span></span> <span data-ttu-id="7694d-121">命令指定用户帐户的用户名、全名和说明。</span><span class="sxs-lookup"><span data-stu-id="7694d-121">The command specifies a user name, full name, and description for the user account.</span></span>

## <span data-ttu-id="7694d-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7694d-122">PARAMETERS</span></span>

### <span data-ttu-id="7694d-123">-AccountExpires</span><span class="sxs-lookup"><span data-stu-id="7694d-123">-AccountExpires</span></span>

<span data-ttu-id="7694d-124">指定用户帐户的过期时间。</span><span class="sxs-lookup"><span data-stu-id="7694d-124">Specifies when the user account expires.</span></span> <span data-ttu-id="7694d-125">若要获取 **DateTime** 对象，请使用 `Get-Date` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7694d-125">To obtain a **DateTime** object, use the `Get-Date` cmdlet.</span></span>
<span data-ttu-id="7694d-126">如果未指定此参数，则帐户不会过期。</span><span class="sxs-lookup"><span data-stu-id="7694d-126">If you do not specify this parameter, the account does not expire.</span></span>

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-127">-AccountNeverExpires</span><span class="sxs-lookup"><span data-stu-id="7694d-127">-AccountNeverExpires</span></span>

<span data-ttu-id="7694d-128">指示帐户未过期。</span><span class="sxs-lookup"><span data-stu-id="7694d-128">Indicates that the account does not expire.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-129">-Description</span><span class="sxs-lookup"><span data-stu-id="7694d-129">-Description</span></span>

<span data-ttu-id="7694d-130">指定用户帐户的注释。</span><span class="sxs-lookup"><span data-stu-id="7694d-130">Specifies a comment for the user account.</span></span>
<span data-ttu-id="7694d-131">最大长度为48个字符。</span><span class="sxs-lookup"><span data-stu-id="7694d-131">The maximum length is 48 characters.</span></span>

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

### <span data-ttu-id="7694d-132">-已禁用</span><span class="sxs-lookup"><span data-stu-id="7694d-132">-Disabled</span></span>

<span data-ttu-id="7694d-133">指示此 cmdlet 将用户帐户创建为已禁用。</span><span class="sxs-lookup"><span data-stu-id="7694d-133">Indicates that this cmdlet creates the user account as disabled.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-134">-FullName</span><span class="sxs-lookup"><span data-stu-id="7694d-134">-FullName</span></span>

<span data-ttu-id="7694d-135">指定用户帐户的全名。</span><span class="sxs-lookup"><span data-stu-id="7694d-135">Specifies the full name for the user account.</span></span> <span data-ttu-id="7694d-136">全名不同于用户帐户的用户名。</span><span class="sxs-lookup"><span data-stu-id="7694d-136">The full name differs from the user name of the user account.</span></span>

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

### <span data-ttu-id="7694d-137">-Name</span><span class="sxs-lookup"><span data-stu-id="7694d-137">-Name</span></span>

<span data-ttu-id="7694d-138">指定用户帐户的用户名。</span><span class="sxs-lookup"><span data-stu-id="7694d-138">Specifies the user name for the user account.</span></span>

<span data-ttu-id="7694d-139">如果为本地系统创建了本地用户帐户，则用户名最多可以包含20个大写字符或小写字符。</span><span class="sxs-lookup"><span data-stu-id="7694d-139">If you create a local user account for the local system, the user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="7694d-140">用户名不能包含以下字符：</span><span class="sxs-lookup"><span data-stu-id="7694d-140">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="7694d-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="7694d-141">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

<span data-ttu-id="7694d-142">用户名不能仅由句点 `.` 或空格组成。</span><span class="sxs-lookup"><span data-stu-id="7694d-142">A user name cannot consist only of periods `.` or spaces.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-143">-NoPassword</span><span class="sxs-lookup"><span data-stu-id="7694d-143">-NoPassword</span></span>

<span data-ttu-id="7694d-144">指示该用户帐户没有密码。</span><span class="sxs-lookup"><span data-stu-id="7694d-144">Indicates that the user account does not have a password.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoPassword
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-145">-Password</span><span class="sxs-lookup"><span data-stu-id="7694d-145">-Password</span></span>

<span data-ttu-id="7694d-146">指定用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="7694d-146">Specifies a password for the user account.</span></span> <span data-ttu-id="7694d-147">可以使用 `Read-Host -GetCredential` 、 `Get-Credential` 或 `ConvertTo-SecureString` 来创建密码的 **SecureString** 对象。</span><span class="sxs-lookup"><span data-stu-id="7694d-147">You can use `Read-Host -GetCredential`, `Get-Credential`, or `ConvertTo-SecureString` to create a **SecureString** object for the password.</span></span>

<span data-ttu-id="7694d-148">如果省略 **Password** 和 **NoPassword** 参数，则 `New-LocalUser` 会提示输入新用户的密码。</span><span class="sxs-lookup"><span data-stu-id="7694d-148">If you omit the **Password** and **NoPassword** parameters, `New-LocalUser` prompts you for the new user's password.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: Password
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-149">-PasswordNeverExpires</span><span class="sxs-lookup"><span data-stu-id="7694d-149">-PasswordNeverExpires</span></span>

<span data-ttu-id="7694d-150">指示密码是否过期。</span><span class="sxs-lookup"><span data-stu-id="7694d-150">Indicates whether the password expires.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Password
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-151">-UserMayNotChangePassword</span><span class="sxs-lookup"><span data-stu-id="7694d-151">-UserMayNotChangePassword</span></span>

<span data-ttu-id="7694d-152">指示用户无法更改用户帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="7694d-152">Indicates that the user cannot change the password on the user account.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="7694d-153">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7694d-153">-Confirm</span></span>

<span data-ttu-id="7694d-154">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="7694d-154">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7694d-155">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7694d-155">-WhatIf</span></span>

<span data-ttu-id="7694d-156">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="7694d-156">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7694d-157">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="7694d-157">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7694d-158">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7694d-158">CommonParameters</span></span>

<span data-ttu-id="7694d-159">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="7694d-159">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="7694d-160">有关详细信息，请参阅 [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="7694d-160">For more information, see [about_CommonParameters](/reference/6/Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7694d-161">输入</span><span class="sxs-lookup"><span data-stu-id="7694d-161">INPUTS</span></span>

### <span data-ttu-id="7694d-162">System.string、system.web、SecureString、system. Security</span><span class="sxs-lookup"><span data-stu-id="7694d-162">System.String, System.DateTime, System.Boolean, System.Security.SecureString</span></span>

<span data-ttu-id="7694d-163">可以通过管道将字符串、 **日期时间** 对象、布尔值或安全字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7694d-163">You can pipe a string, a **DateTime** object, a boolean value, or a secure string to this cmdlet.</span></span>

## <span data-ttu-id="7694d-164">输出</span><span class="sxs-lookup"><span data-stu-id="7694d-164">OUTPUTS</span></span>

### <span data-ttu-id="7694d-165">SecurityAccountsManager. LocalUser。</span><span class="sxs-lookup"><span data-stu-id="7694d-165">System.Management.Automation.SecurityAccountsManager.LocalUser</span></span>

<span data-ttu-id="7694d-166">此 cmdlet 将返回 **LocalUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="7694d-166">This cmdlet returns a **LocalUser** object.</span></span>
<span data-ttu-id="7694d-167">此对象提供有关用户帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="7694d-167">This object provides information about the user account.</span></span>

## <span data-ttu-id="7694d-168">注释</span><span class="sxs-lookup"><span data-stu-id="7694d-168">NOTES</span></span>

- <span data-ttu-id="7694d-169">用户名不能与计算机上的任何其他用户名或组名相同。</span><span class="sxs-lookup"><span data-stu-id="7694d-169">A user name cannot be identical to any other user name or group name on the computer.</span></span> <span data-ttu-id="7694d-170">用户名不能仅由句点 `.` 或空格组成。</span><span class="sxs-lookup"><span data-stu-id="7694d-170">A user name cannot consist only of periods `.` or spaces.</span></span> <span data-ttu-id="7694d-171">用户名最多可以包含20个大写字符或小写字符。</span><span class="sxs-lookup"><span data-stu-id="7694d-171">A user name can contain up to 20 uppercase characters or lowercase characters.</span></span> <span data-ttu-id="7694d-172">用户名不能包含以下字符：</span><span class="sxs-lookup"><span data-stu-id="7694d-172">A user name cannot contain the following characters:</span></span>

<span data-ttu-id="7694d-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span><span class="sxs-lookup"><span data-stu-id="7694d-173">`"`, `/`, `\`, `[`, `]`, `:`, `;`, `|`, `=`, `,`, `+`, `*`, `?`, `<`, `>`, `@`</span></span>

- <span data-ttu-id="7694d-174">密码最多可包含127个字符。</span><span class="sxs-lookup"><span data-stu-id="7694d-174">A password can contain up to 127 characters.</span></span>
- <span data-ttu-id="7694d-175">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="7694d-175">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="7694d-176">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="7694d-176">The possible sources are as follows:</span></span>

  - <span data-ttu-id="7694d-177">Local</span><span class="sxs-lookup"><span data-stu-id="7694d-177">Local</span></span>
  - <span data-ttu-id="7694d-178">Active Directory</span><span class="sxs-lookup"><span data-stu-id="7694d-178">Active Directory</span></span>
  - <span data-ttu-id="7694d-179">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="7694d-179">Azure Active Directory group</span></span>
  - <span data-ttu-id="7694d-180">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="7694d-180">Microsoft Account</span></span>

> [!NOTE]
> <span data-ttu-id="7694d-181">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="7694d-181">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="7694d-182">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="7694d-182">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="7694d-183">相关链接</span><span class="sxs-lookup"><span data-stu-id="7694d-183">RELATED LINKS</span></span>

[<span data-ttu-id="7694d-184">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7694d-184">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="7694d-185">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7694d-185">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="7694d-186">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7694d-186">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="7694d-187">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7694d-187">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="7694d-188">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7694d-188">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="7694d-189">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="7694d-189">Set-LocalUser</span></span>](Set-LocalUser.md)
