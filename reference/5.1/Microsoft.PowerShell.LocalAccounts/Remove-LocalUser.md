---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalUser
ms.openlocfilehash: de1054971dab19f8cfae654208488ca9ce5e17e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198339"
---
# <span data-ttu-id="66595-103">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66595-103">Remove-LocalUser</span></span>

## <span data-ttu-id="66595-104">摘要</span><span class="sxs-lookup"><span data-stu-id="66595-104">SYNOPSIS</span></span>
<span data-ttu-id="66595-105">删除本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="66595-105">Deletes local user accounts.</span></span>

## <span data-ttu-id="66595-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="66595-106">SYNTAX</span></span>

### <span data-ttu-id="66595-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="66595-107">InputObject</span></span>

```
Remove-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="66595-108">默认</span><span class="sxs-lookup"><span data-stu-id="66595-108">Default</span></span>

```
Remove-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="66595-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="66595-109">SecurityIdentifier</span></span>

```
Remove-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="66595-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="66595-110">DESCRIPTION</span></span>
<span data-ttu-id="66595-111">**LocalUser** cmdlet 删除本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="66595-111">The **Remove-LocalUser** cmdlet deletes local user accounts.</span></span>

## <span data-ttu-id="66595-112">示例</span><span class="sxs-lookup"><span data-stu-id="66595-112">EXAMPLES</span></span>

### <span data-ttu-id="66595-113">示例1：删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="66595-113">Example 1: Delete a user account</span></span>

```
PS C:\> Remove-LocalUser -Name "AdminContoso02"
```

<span data-ttu-id="66595-114">此命令删除名为 AdminContoso02 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="66595-114">This command deletes the user account named AdminContoso02.</span></span>

> [!NOTE]
> <span data-ttu-id="66595-115">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="66595-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="66595-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="66595-116">PARAMETERS</span></span>

### <span data-ttu-id="66595-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="66595-117">-InputObject</span></span>
<span data-ttu-id="66595-118">指定此 cmdlet 删除的用户帐户的数组。</span><span class="sxs-lookup"><span data-stu-id="66595-118">Specifies an array of user accounts that this cmdlet deletes.</span></span>
<span data-ttu-id="66595-119">若要获取用户帐户，请使用 Get-LocalUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66595-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="66595-120">-Name</span><span class="sxs-lookup"><span data-stu-id="66595-120">-Name</span></span>
<span data-ttu-id="66595-121">指定此 cmdlet 删除的用户帐户的名称数组。</span><span class="sxs-lookup"><span data-stu-id="66595-121">Specifies an array of names of the user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="66595-122">-SID</span><span class="sxs-lookup"><span data-stu-id="66595-122">-SID</span></span>
<span data-ttu-id="66595-123">指定此 cmdlet 删除的用户帐户的 Sid)  (安全 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="66595-123">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="66595-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="66595-124">-Confirm</span></span>
<span data-ttu-id="66595-125">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="66595-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="66595-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="66595-126">-WhatIf</span></span>
<span data-ttu-id="66595-127">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="66595-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="66595-128">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="66595-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="66595-129">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="66595-129">CommonParameters</span></span>
<span data-ttu-id="66595-130">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="66595-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="66595-131">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="66595-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="66595-132">输入</span><span class="sxs-lookup"><span data-stu-id="66595-132">INPUTS</span></span>

### <span data-ttu-id="66595-133">SecurityAccountsManager. LocalUser、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="66595-133">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="66595-134">可以通过管道将本地用户、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66595-134">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="66595-135">输出</span><span class="sxs-lookup"><span data-stu-id="66595-135">OUTPUTS</span></span>

### <span data-ttu-id="66595-136">无</span><span class="sxs-lookup"><span data-stu-id="66595-136">None</span></span>
<span data-ttu-id="66595-137">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="66595-137">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="66595-138">注释</span><span class="sxs-lookup"><span data-stu-id="66595-138">NOTES</span></span>

* <span data-ttu-id="66595-139">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="66595-139">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="66595-140">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="66595-140">The possible sources are as follows:</span></span>

- <span data-ttu-id="66595-141">Local</span><span class="sxs-lookup"><span data-stu-id="66595-141">Local</span></span>
- <span data-ttu-id="66595-142">Active Directory</span><span class="sxs-lookup"><span data-stu-id="66595-142">Active Directory</span></span>
- <span data-ttu-id="66595-143">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="66595-143">Azure Active Directory group</span></span>
- <span data-ttu-id="66595-144">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="66595-144">Microsoft Account</span></span>

<span data-ttu-id="66595-145">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="66595-145">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="66595-146">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="66595-146">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="66595-147">相关链接</span><span class="sxs-lookup"><span data-stu-id="66595-147">RELATED LINKS</span></span>

[<span data-ttu-id="66595-148">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66595-148">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="66595-149">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66595-149">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="66595-150">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66595-150">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="66595-151">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66595-151">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="66595-152">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66595-152">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="66595-153">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="66595-153">Set-LocalUser</span></span>](Set-LocalUser.md)
