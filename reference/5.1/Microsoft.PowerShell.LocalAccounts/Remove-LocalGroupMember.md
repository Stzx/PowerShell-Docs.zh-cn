---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroupMember
ms.openlocfilehash: 6e6264a65c343657c2f2f87384d76cc3f1554d3d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198100"
---
# <span data-ttu-id="e244a-103">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e244a-103">Remove-LocalGroupMember</span></span>

## <span data-ttu-id="e244a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e244a-104">SYNOPSIS</span></span>
<span data-ttu-id="e244a-105">从本地组中删除成员。</span><span class="sxs-lookup"><span data-stu-id="e244a-105">Removes members from a local group.</span></span>

## <span data-ttu-id="e244a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e244a-106">SYNTAX</span></span>

### <span data-ttu-id="e244a-107">组</span><span class="sxs-lookup"><span data-stu-id="e244a-107">Group</span></span>

```
Remove-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="e244a-108">默认</span><span class="sxs-lookup"><span data-stu-id="e244a-108">Default</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e244a-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="e244a-109">SecurityIdentifier</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="e244a-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e244a-110">DESCRIPTION</span></span>
<span data-ttu-id="e244a-111">**LocalGroupMember** cmdlet 将从本地组中删除用户或组。</span><span class="sxs-lookup"><span data-stu-id="e244a-111">The **Remove-LocalGroupMember** cmdlet removes users or groups from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="e244a-112">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="e244a-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="e244a-113">示例</span><span class="sxs-lookup"><span data-stu-id="e244a-113">EXAMPLES</span></span>

### <span data-ttu-id="e244a-114">示例1：从 Administrators 组中删除成员</span><span class="sxs-lookup"><span data-stu-id="e244a-114">Example 1: Remove members from the Administrators group</span></span>

```
PS C:\> Remove-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

<span data-ttu-id="e244a-115">此命令从本地管理员组中删除多个成员。</span><span class="sxs-lookup"><span data-stu-id="e244a-115">This command removes several members from the local Administrators group.</span></span>
<span data-ttu-id="e244a-116">此 cmdlet 删除的成员包括本地用户帐户、Microsoft 帐户、Azure Active Directory 帐户和域组。</span><span class="sxs-lookup"><span data-stu-id="e244a-116">The members that this cmdlet removes include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span>
<span data-ttu-id="e244a-117">此示例在 Outlook.com 处为帐户的用户名使用占位符值。</span><span class="sxs-lookup"><span data-stu-id="e244a-117">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

## <span data-ttu-id="e244a-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e244a-118">PARAMETERS</span></span>

### <span data-ttu-id="e244a-119">-Group</span><span class="sxs-lookup"><span data-stu-id="e244a-119">-Group</span></span>
<span data-ttu-id="e244a-120">指定此 cmdlet 从中删除成员的安全组。</span><span class="sxs-lookup"><span data-stu-id="e244a-120">Specifies the security group from which this cmdlet removes members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e244a-121">-成员</span><span class="sxs-lookup"><span data-stu-id="e244a-121">-Member</span></span>
<span data-ttu-id="e244a-122">指定此 cmdlet 从安全组中删除的用户或组的数组。</span><span class="sxs-lookup"><span data-stu-id="e244a-122">Specifies an array of users or groups that this cmdlet removes from a security group.</span></span>
<span data-ttu-id="e244a-123">可以按名称、安全 ID (SID) 或 **LocalPrincipal** 对象指定用户或组。</span><span class="sxs-lookup"><span data-stu-id="e244a-123">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>
<span data-ttu-id="e244a-124">在 S-R-I-S-s 中指定 SID 字符串。</span><span class="sxs-lookup"><span data-stu-id="e244a-124">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="e244a-125">.</span><span class="sxs-lookup"><span data-stu-id="e244a-125">.</span></span> <span data-ttu-id="e244a-126">.</span><span class="sxs-lookup"><span data-stu-id="e244a-126">.</span></span>
<span data-ttu-id="e244a-127">格式表示）。</span><span class="sxs-lookup"><span data-stu-id="e244a-127">format.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e244a-128">-Name</span><span class="sxs-lookup"><span data-stu-id="e244a-128">-Name</span></span>
<span data-ttu-id="e244a-129">指定此 cmdlet 从中删除成员的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="e244a-129">Specifies the name of the security group from which this cmdlet removes members.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e244a-130">-SID</span><span class="sxs-lookup"><span data-stu-id="e244a-130">-SID</span></span>
<span data-ttu-id="e244a-131">指定此 cmdlet 从中删除成员的安全组的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="e244a-131">Specifies the security ID of the security group from which this cmdlet removes members.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e244a-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e244a-132">-Confirm</span></span>
<span data-ttu-id="e244a-133">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e244a-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e244a-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e244a-134">-WhatIf</span></span>
<span data-ttu-id="e244a-135">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e244a-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e244a-136">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e244a-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e244a-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e244a-137">CommonParameters</span></span>
<span data-ttu-id="e244a-138">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e244a-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e244a-139">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e244a-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e244a-140">输入</span><span class="sxs-lookup"><span data-stu-id="e244a-140">INPUTS</span></span>

### <span data-ttu-id="e244a-141">SecurityAccountsManager. LocalPrincipal、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="e244a-141">System.Management.Automation.SecurityAccountsManager.LocalPrincipal, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="e244a-142">可以通过管道将本地主体、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e244a-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="e244a-143">输出</span><span class="sxs-lookup"><span data-stu-id="e244a-143">OUTPUTS</span></span>

### <span data-ttu-id="e244a-144">无</span><span class="sxs-lookup"><span data-stu-id="e244a-144">None</span></span>
<span data-ttu-id="e244a-145">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="e244a-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e244a-146">注释</span><span class="sxs-lookup"><span data-stu-id="e244a-146">NOTES</span></span>

* <span data-ttu-id="e244a-147">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="e244a-147">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="e244a-148">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="e244a-148">The possible sources are as follows:</span></span>

- <span data-ttu-id="e244a-149">Local</span><span class="sxs-lookup"><span data-stu-id="e244a-149">Local</span></span>
- <span data-ttu-id="e244a-150">Active Directory</span><span class="sxs-lookup"><span data-stu-id="e244a-150">Active Directory</span></span>
- <span data-ttu-id="e244a-151">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="e244a-151">Azure Active Directory group</span></span>
- <span data-ttu-id="e244a-152">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="e244a-152">Microsoft Account</span></span>

<span data-ttu-id="e244a-153">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="e244a-153">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="e244a-154">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="e244a-154">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="e244a-155">相关链接</span><span class="sxs-lookup"><span data-stu-id="e244a-155">RELATED LINKS</span></span>

[<span data-ttu-id="e244a-156">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e244a-156">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="e244a-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="e244a-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="e244a-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="e244a-158">New-LocalGroup</span></span>](New-LocalGroup.md)
