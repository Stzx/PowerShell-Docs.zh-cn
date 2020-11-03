---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/disable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-LocalUser
ms.openlocfilehash: a62242251da00688d3299c60e4cdae7aae6f581a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197411"
---
# <span data-ttu-id="00593-103">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="00593-103">Disable-LocalUser</span></span>

## <span data-ttu-id="00593-104">摘要</span><span class="sxs-lookup"><span data-stu-id="00593-104">SYNOPSIS</span></span>
<span data-ttu-id="00593-105">禁用本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="00593-105">Disables a local user account.</span></span>

## <span data-ttu-id="00593-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="00593-106">SYNTAX</span></span>

### <span data-ttu-id="00593-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="00593-107">InputObject</span></span>

```
Disable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="00593-108">默认</span><span class="sxs-lookup"><span data-stu-id="00593-108">Default</span></span>

```
Disable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="00593-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="00593-109">SecurityIdentifier</span></span>

```
Disable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="00593-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="00593-110">DESCRIPTION</span></span>
<span data-ttu-id="00593-111">**LocalUser** cmdlet 禁用本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="00593-111">The **Disable-LocalUser** cmdlet disables local user accounts.</span></span>
<span data-ttu-id="00593-112">禁用用户帐户后，用户将无法登录。</span><span class="sxs-lookup"><span data-stu-id="00593-112">When a user account is disabled, the user cannot log on.</span></span>
<span data-ttu-id="00593-113">用户帐户启用后，用户可以登录。</span><span class="sxs-lookup"><span data-stu-id="00593-113">When a user account is enabled, the user can log on.</span></span>

> [!NOTE]
> <span data-ttu-id="00593-114">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="00593-114">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="00593-115">示例</span><span class="sxs-lookup"><span data-stu-id="00593-115">EXAMPLES</span></span>

### <span data-ttu-id="00593-116">示例1：通过指定名称来禁用帐户</span><span class="sxs-lookup"><span data-stu-id="00593-116">Example 1: Disable an account by specifying a name</span></span>

```
PS C:\> Disable-LocalUser -Name "Admin02"
```

<span data-ttu-id="00593-117">此命令禁用名为 Admin02 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="00593-117">This command disables the user account named Admin02.</span></span>

### <span data-ttu-id="00593-118">示例2：使用管道禁用帐户</span><span class="sxs-lookup"><span data-stu-id="00593-118">Example 2: Disable an account by using the pipeline</span></span>

```
PS C:\> Get-LocalUser Guest | Disable-LocalUser
```

<span data-ttu-id="00593-119">此命令使用 **LocalUser** 获取内置来宾帐户，然后使用管道运算符将其传递给当前 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00593-119">This command gets the built-in Guest account by using **Get-LocalUser** , and then passes it to the current cmdlet by using the pipeline operator.</span></span>
<span data-ttu-id="00593-120">该 cmdlet 将禁用该帐户。</span><span class="sxs-lookup"><span data-stu-id="00593-120">That cmdlet disables that account.</span></span>

## <span data-ttu-id="00593-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="00593-121">PARAMETERS</span></span>

### <span data-ttu-id="00593-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="00593-122">-InputObject</span></span>
<span data-ttu-id="00593-123">指定此 cmdlet 禁用的用户帐户的数组。</span><span class="sxs-lookup"><span data-stu-id="00593-123">Specifies an array of user accounts that this cmdlet disables.</span></span>
<span data-ttu-id="00593-124">若要获取用户帐户，请使用 Get-LocalUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00593-124">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="00593-125">-Name</span><span class="sxs-lookup"><span data-stu-id="00593-125">-Name</span></span>
<span data-ttu-id="00593-126">指定此 cmdlet 禁用的用户帐户的名称数组。</span><span class="sxs-lookup"><span data-stu-id="00593-126">Specifies an array of names of the user accounts that this cmdlet disables.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="00593-127">-SID</span><span class="sxs-lookup"><span data-stu-id="00593-127">-SID</span></span>
<span data-ttu-id="00593-128">指定此 cmdlet 禁用的用户帐户的数组。</span><span class="sxs-lookup"><span data-stu-id="00593-128">Specifies an array of user accounts that this cmdlet disables.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="00593-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="00593-129">-Confirm</span></span>
<span data-ttu-id="00593-130">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="00593-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="00593-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="00593-131">-WhatIf</span></span>
<span data-ttu-id="00593-132">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="00593-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="00593-133">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="00593-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="00593-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="00593-134">CommonParameters</span></span>
<span data-ttu-id="00593-135">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="00593-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="00593-136">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="00593-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="00593-137">输入</span><span class="sxs-lookup"><span data-stu-id="00593-137">INPUTS</span></span>

### <span data-ttu-id="00593-138">SecurityAccountsManager. LocalUser、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="00593-138">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="00593-139">可以通过管道将本地用户、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="00593-139">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="00593-140">输出</span><span class="sxs-lookup"><span data-stu-id="00593-140">OUTPUTS</span></span>

### <span data-ttu-id="00593-141">无</span><span class="sxs-lookup"><span data-stu-id="00593-141">None</span></span>
<span data-ttu-id="00593-142">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="00593-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="00593-143">注释</span><span class="sxs-lookup"><span data-stu-id="00593-143">NOTES</span></span>

* <span data-ttu-id="00593-144">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="00593-144">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="00593-145">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="00593-145">The possible sources are as follows:</span></span>

- <span data-ttu-id="00593-146">Local</span><span class="sxs-lookup"><span data-stu-id="00593-146">Local</span></span>
- <span data-ttu-id="00593-147">Active Directory</span><span class="sxs-lookup"><span data-stu-id="00593-147">Active Directory</span></span>
- <span data-ttu-id="00593-148">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="00593-148">Azure Active Directory group</span></span>
- <span data-ttu-id="00593-149">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="00593-149">Microsoft Account</span></span>

<span data-ttu-id="00593-150">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="00593-150">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="00593-151">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="00593-151">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="00593-152">相关链接</span><span class="sxs-lookup"><span data-stu-id="00593-152">RELATED LINKS</span></span>

[<span data-ttu-id="00593-153">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="00593-153">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="00593-154">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="00593-154">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="00593-155">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="00593-155">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="00593-156">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="00593-156">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="00593-157">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="00593-157">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="00593-158">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="00593-158">Set-LocalUser</span></span>](Set-LocalUser.md)
