---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalUser
ms.openlocfilehash: fc5740e52e08ad2146981799a4e1659cd420b321
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198338"
---
# <span data-ttu-id="c95e3-103">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c95e3-103">Rename-LocalUser</span></span>

## <span data-ttu-id="c95e3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c95e3-104">SYNOPSIS</span></span>
<span data-ttu-id="c95e3-105">重命名本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c95e3-105">Renames a local user account.</span></span>

## <span data-ttu-id="c95e3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c95e3-106">SYNTAX</span></span>

### <span data-ttu-id="c95e3-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="c95e3-107">InputObject</span></span>

```
Rename-LocalUser [-InputObject] <LocalUser> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c95e3-108">默认</span><span class="sxs-lookup"><span data-stu-id="c95e3-108">Default</span></span>

```
Rename-LocalUser [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c95e3-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="c95e3-109">SecurityIdentifier</span></span>

```
Rename-LocalUser [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c95e3-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c95e3-110">DESCRIPTION</span></span>
<span data-ttu-id="c95e3-111">**LocalUser** cmdlet 重命名本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c95e3-111">The **Rename-LocalUser** cmdlet renames a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="c95e3-112">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="c95e3-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="c95e3-113">示例</span><span class="sxs-lookup"><span data-stu-id="c95e3-113">EXAMPLES</span></span>

### <span data-ttu-id="c95e3-114">示例1：重命名用户帐户</span><span class="sxs-lookup"><span data-stu-id="c95e3-114">Example 1: Rename a user account</span></span>

```
PS C:\> Rename-LocalUser -Name "Admin02" -NewName "AdminContoso02"
```

<span data-ttu-id="c95e3-115">此命令重命名名为 Admin02 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c95e3-115">This command renames the user account named Admin02.</span></span>

## <span data-ttu-id="c95e3-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c95e3-116">PARAMETERS</span></span>

### <span data-ttu-id="c95e3-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c95e3-117">-InputObject</span></span>
<span data-ttu-id="c95e3-118">指定此 cmdlet 重命名的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c95e3-118">Specifies the user account that this cmdlet renames.</span></span>
<span data-ttu-id="c95e3-119">若要获取用户帐户，请使用 Get-LocalUser cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c95e3-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="c95e3-120">-Name</span><span class="sxs-lookup"><span data-stu-id="c95e3-120">-Name</span></span>
<span data-ttu-id="c95e3-121">指定此 cmdlet 重命名的用户帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="c95e3-121">Specifies the name of the user account that this cmdlet renames.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c95e3-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="c95e3-122">-NewName</span></span>
<span data-ttu-id="c95e3-123">指定用户帐户的新名称。</span><span class="sxs-lookup"><span data-stu-id="c95e3-123">Specifies a new name for the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c95e3-124">-SID</span><span class="sxs-lookup"><span data-stu-id="c95e3-124">-SID</span></span>
<span data-ttu-id="c95e3-125">指定此 cmdlet 重命名的用户帐户 (SID) 的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="c95e3-125">Specifies the security ID (SID) of a user accounts that this cmdlet renames.</span></span>

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

### <span data-ttu-id="c95e3-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c95e3-126">-Confirm</span></span>
<span data-ttu-id="c95e3-127">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="c95e3-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c95e3-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c95e3-128">-WhatIf</span></span>
<span data-ttu-id="c95e3-129">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="c95e3-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c95e3-130">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="c95e3-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c95e3-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c95e3-131">CommonParameters</span></span>
<span data-ttu-id="c95e3-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c95e3-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c95e3-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c95e3-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c95e3-134">输入</span><span class="sxs-lookup"><span data-stu-id="c95e3-134">INPUTS</span></span>

### <span data-ttu-id="c95e3-135">SecurityAccountsManager. LocalUser、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="c95e3-135">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="c95e3-136">可以通过管道将本地用户、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c95e3-136">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="c95e3-137">输出</span><span class="sxs-lookup"><span data-stu-id="c95e3-137">OUTPUTS</span></span>

### <span data-ttu-id="c95e3-138">无</span><span class="sxs-lookup"><span data-stu-id="c95e3-138">None</span></span>
<span data-ttu-id="c95e3-139">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="c95e3-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c95e3-140">注释</span><span class="sxs-lookup"><span data-stu-id="c95e3-140">NOTES</span></span>

* <span data-ttu-id="c95e3-141">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="c95e3-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="c95e3-142">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="c95e3-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="c95e3-143">Local</span><span class="sxs-lookup"><span data-stu-id="c95e3-143">Local</span></span>
- <span data-ttu-id="c95e3-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c95e3-144">Active Directory</span></span>
- <span data-ttu-id="c95e3-145">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="c95e3-145">Azure Active Directory group</span></span>
- <span data-ttu-id="c95e3-146">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="c95e3-146">Microsoft Account</span></span>

<span data-ttu-id="c95e3-147">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="c95e3-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="c95e3-148">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="c95e3-148">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="c95e3-149">相关链接</span><span class="sxs-lookup"><span data-stu-id="c95e3-149">RELATED LINKS</span></span>

[<span data-ttu-id="c95e3-150">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c95e3-150">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="c95e3-151">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c95e3-151">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="c95e3-152">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c95e3-152">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="c95e3-153">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c95e3-153">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="c95e3-154">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c95e3-154">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="c95e3-155">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="c95e3-155">Set-LocalUser</span></span>](Set-LocalUser.md)
