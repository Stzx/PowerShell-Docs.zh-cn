---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197412"
---
# <span data-ttu-id="a05b4-103">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="a05b4-103">Add-LocalGroupMember</span></span>

## <span data-ttu-id="a05b4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a05b4-104">SYNOPSIS</span></span>
<span data-ttu-id="a05b4-105">向本地组添加成员。</span><span class="sxs-lookup"><span data-stu-id="a05b4-105">Adds members to a local group.</span></span>

## <span data-ttu-id="a05b4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a05b4-106">SYNTAX</span></span>

### <span data-ttu-id="a05b4-107">组</span><span class="sxs-lookup"><span data-stu-id="a05b4-107">Group</span></span>

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a05b4-108">默认</span><span class="sxs-lookup"><span data-stu-id="a05b4-108">Default</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a05b4-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="a05b4-109">SecurityIdentifier</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="a05b4-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a05b4-110">DESCRIPTION</span></span>

<span data-ttu-id="a05b4-111">`Add-LocalGroupMember`Cmdlet 可将用户或组添加到本地安全组。</span><span class="sxs-lookup"><span data-stu-id="a05b4-111">The `Add-LocalGroupMember` cmdlet adds users or groups to a local security group.</span></span> <span data-ttu-id="a05b4-112">分配给组的所有权利和权限都会分配给该组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="a05b4-112">All the rights and permissions that are assigned to a group are assigned to all members of that group.</span></span>

<span data-ttu-id="a05b4-113">本地计算机上 Administrators 组的成员在该计算机上具有完全控制权限。</span><span class="sxs-lookup"><span data-stu-id="a05b4-113">Members of the Administrators group on a local computer have Full Control permissions on that computer.</span></span> <span data-ttu-id="a05b4-114">限制 Administrators 组中用户数量。</span><span class="sxs-lookup"><span data-stu-id="a05b4-114">Limit the number of users in the Administrators group.</span></span>

<span data-ttu-id="a05b4-115">如果计算机已加入某个域，则可以从该域和受信任的域向本地组添加用户帐户、计算机帐户和组帐户。</span><span class="sxs-lookup"><span data-stu-id="a05b4-115">If the computer is joined to a domain, you can add user accounts, computer accounts, and group accounts from that domain and from trusted domains to a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="a05b4-116">如果计算机已加入域，并且你尝试添加的本地用户与域的某个成员具有相同的名称，则它将添加域成员。</span><span class="sxs-lookup"><span data-stu-id="a05b4-116">If the computer is joined to a domain and you try to add a local user that has the same name as a member of the domain it adds the domain member.</span></span>

## <span data-ttu-id="a05b4-117">示例</span><span class="sxs-lookup"><span data-stu-id="a05b4-117">EXAMPLES</span></span>

### <span data-ttu-id="a05b4-118">示例1：向 Administrators 组添加成员</span><span class="sxs-lookup"><span data-stu-id="a05b4-118">Example 1: Add members to the Administrators group</span></span>

<span data-ttu-id="a05b4-119">此命令将多个成员添加到本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="a05b4-119">This command adds several members to the local Administrators group.</span></span> <span data-ttu-id="a05b4-120">新成员包括本地用户帐户、Microsoft 帐户、Azure Active Directory 帐户和域组。</span><span class="sxs-lookup"><span data-stu-id="a05b4-120">The new members include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span> <span data-ttu-id="a05b4-121">此示例在 Outlook.com 处为帐户的用户名使用占位符值。</span><span class="sxs-lookup"><span data-stu-id="a05b4-121">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## <span data-ttu-id="a05b4-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a05b4-122">PARAMETERS</span></span>

### <span data-ttu-id="a05b4-123">-Group</span><span class="sxs-lookup"><span data-stu-id="a05b4-123">-Group</span></span>

<span data-ttu-id="a05b4-124">指定此 cmdlet 向其中添加成员的安全组。</span><span class="sxs-lookup"><span data-stu-id="a05b4-124">Specifies the security group to which this cmdlet adds members.</span></span>

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

### <span data-ttu-id="a05b4-125">-成员</span><span class="sxs-lookup"><span data-stu-id="a05b4-125">-Member</span></span>

<span data-ttu-id="a05b4-126">指定此 cmdlet 添加到安全组的用户或组的数组。</span><span class="sxs-lookup"><span data-stu-id="a05b4-126">Specifies an array of users or groups that this cmdlet adds to a security group.</span></span> <span data-ttu-id="a05b4-127">可以按名称、安全 ID (SID) 或 **LocalPrincipal** 对象指定用户或组。</span><span class="sxs-lookup"><span data-stu-id="a05b4-127">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>

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

### <span data-ttu-id="a05b4-128">-Name</span><span class="sxs-lookup"><span data-stu-id="a05b4-128">-Name</span></span>

<span data-ttu-id="a05b4-129">指定此 cmdlet 向其中添加成员的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="a05b4-129">Specifies the name of the security group to which this cmdlet adds members.</span></span>

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

### <span data-ttu-id="a05b4-130">-SID</span><span class="sxs-lookup"><span data-stu-id="a05b4-130">-SID</span></span>

<span data-ttu-id="a05b4-131">指定此 cmdlet 向其中添加成员的安全组的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="a05b4-131">Specifies the security ID of the security group to which this cmdlet adds members.</span></span>

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

### <span data-ttu-id="a05b4-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a05b4-132">-Confirm</span></span>

<span data-ttu-id="a05b4-133">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="a05b4-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a05b4-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a05b4-134">-WhatIf</span></span>

<span data-ttu-id="a05b4-135">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="a05b4-135">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a05b4-136">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="a05b4-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a05b4-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a05b4-137">CommonParameters</span></span>

<span data-ttu-id="a05b4-138">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a05b4-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a05b4-139">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a05b4-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a05b4-140">输入</span><span class="sxs-lookup"><span data-stu-id="a05b4-140">INPUTS</span></span>

### <span data-ttu-id="a05b4-141">SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="a05b4-141">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="a05b4-142">可以通过管道将本地主体、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a05b4-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="a05b4-143">输出</span><span class="sxs-lookup"><span data-stu-id="a05b4-143">OUTPUTS</span></span>

### <span data-ttu-id="a05b4-144">无</span><span class="sxs-lookup"><span data-stu-id="a05b4-144">None</span></span>

<span data-ttu-id="a05b4-145">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="a05b4-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a05b4-146">注释</span><span class="sxs-lookup"><span data-stu-id="a05b4-146">NOTES</span></span>

<span data-ttu-id="a05b4-147">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="a05b4-147">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

<span data-ttu-id="a05b4-148">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="a05b4-148">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="a05b4-149">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="a05b4-149">The possible sources are as follows:</span></span>

- <span data-ttu-id="a05b4-150">Local</span><span class="sxs-lookup"><span data-stu-id="a05b4-150">Local</span></span>
- <span data-ttu-id="a05b4-151">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a05b4-151">Active Directory</span></span>
- <span data-ttu-id="a05b4-152">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="a05b4-152">Azure Active Directory group</span></span>
- <span data-ttu-id="a05b4-153">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="a05b4-153">Microsoft Account</span></span>

<span data-ttu-id="a05b4-154">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="a05b4-154">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="a05b4-155">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="a05b4-155">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="a05b4-156">相关链接</span><span class="sxs-lookup"><span data-stu-id="a05b4-156">RELATED LINKS</span></span>

[<span data-ttu-id="a05b4-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="a05b4-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="a05b4-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="a05b4-158">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="a05b4-159">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="a05b4-159">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
