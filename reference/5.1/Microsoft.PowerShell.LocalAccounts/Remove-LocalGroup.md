---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198099"
---
# <span data-ttu-id="25231-103">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="25231-103">Remove-LocalGroup</span></span>

## <span data-ttu-id="25231-104">摘要</span><span class="sxs-lookup"><span data-stu-id="25231-104">SYNOPSIS</span></span>
<span data-ttu-id="25231-105">删除本地安全组。</span><span class="sxs-lookup"><span data-stu-id="25231-105">Deletes local security groups.</span></span>

## <span data-ttu-id="25231-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="25231-106">SYNTAX</span></span>

### <span data-ttu-id="25231-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="25231-107">InputObject</span></span>

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="25231-108">默认</span><span class="sxs-lookup"><span data-stu-id="25231-108">Default</span></span>

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="25231-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="25231-109">SecurityIdentifier</span></span>

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="25231-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="25231-110">DESCRIPTION</span></span>
<span data-ttu-id="25231-111">**LocalGroup** cmdlet 将删除本地安全组。</span><span class="sxs-lookup"><span data-stu-id="25231-111">The **Remove-LocalGroup** cmdlet deletes local security groups.</span></span>
<span data-ttu-id="25231-112">此 cmdlet 仅删除本地组。</span><span class="sxs-lookup"><span data-stu-id="25231-112">This cmdlet deletes only a local group.</span></span>
<span data-ttu-id="25231-113">它不会删除属于该组的用户帐户、计算机帐户或组帐户。</span><span class="sxs-lookup"><span data-stu-id="25231-113">It does not delete the user accounts, computer accounts, or group accounts that belong to that group.</span></span>
<span data-ttu-id="25231-114">不能恢复已删除的组。</span><span class="sxs-lookup"><span data-stu-id="25231-114">You cannot recover a deleted group.</span></span>

<span data-ttu-id="25231-115">如果删除某个组，然后再创建一个具有相同组名的组，则必须为新组设置新的权限。</span><span class="sxs-lookup"><span data-stu-id="25231-115">If you delete a group and then create another group that has the same group name, you must set new permissions for the new group.</span></span>
<span data-ttu-id="25231-116">新组不会继承分配给组的权限。</span><span class="sxs-lookup"><span data-stu-id="25231-116">The new group does not inherit the permissions that were assigned to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="25231-117">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="25231-117">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="25231-118">示例</span><span class="sxs-lookup"><span data-stu-id="25231-118">EXAMPLES</span></span>

### <span data-ttu-id="25231-119">示例1：删除安全组</span><span class="sxs-lookup"><span data-stu-id="25231-119">Example 1: Delete a security group</span></span>

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="25231-120">此命令删除名为 SecurityGroup04 的组。</span><span class="sxs-lookup"><span data-stu-id="25231-120">This command deletes the group named SecurityGroup04.</span></span>

## <span data-ttu-id="25231-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="25231-121">PARAMETERS</span></span>

### <span data-ttu-id="25231-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="25231-122">-InputObject</span></span>
<span data-ttu-id="25231-123">指定此 cmdlet 删除的安全组的数组。</span><span class="sxs-lookup"><span data-stu-id="25231-123">Specifies an array of security groups that this cmdlet deletes.</span></span>
<span data-ttu-id="25231-124">若要获取组，请使用 Get-LocalGroup cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25231-124">To obtain groups, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="25231-125">-Name</span><span class="sxs-lookup"><span data-stu-id="25231-125">-Name</span></span>
<span data-ttu-id="25231-126">指定此 cmdlet 删除的安全组的名称数组。</span><span class="sxs-lookup"><span data-stu-id="25231-126">Specifies an array of names of the security groups that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="25231-127">-SID</span><span class="sxs-lookup"><span data-stu-id="25231-127">-SID</span></span>
<span data-ttu-id="25231-128">指定此 cmdlet 删除 (安全组的 Sid) 的安全 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="25231-128">Specifies an array of security IDs (SIDs) of security groups that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="25231-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="25231-129">-Confirm</span></span>
<span data-ttu-id="25231-130">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="25231-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="25231-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="25231-131">-WhatIf</span></span>
<span data-ttu-id="25231-132">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="25231-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="25231-133">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="25231-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="25231-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="25231-134">CommonParameters</span></span>
<span data-ttu-id="25231-135">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="25231-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="25231-136">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="25231-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="25231-137">输入</span><span class="sxs-lookup"><span data-stu-id="25231-137">INPUTS</span></span>

### <span data-ttu-id="25231-138">SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="25231-138">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="25231-139">可以通过管道将安全组、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="25231-139">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="25231-140">输出</span><span class="sxs-lookup"><span data-stu-id="25231-140">OUTPUTS</span></span>

### <span data-ttu-id="25231-141">无</span><span class="sxs-lookup"><span data-stu-id="25231-141">None</span></span>
<span data-ttu-id="25231-142">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="25231-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="25231-143">注释</span><span class="sxs-lookup"><span data-stu-id="25231-143">NOTES</span></span>

* <span data-ttu-id="25231-144">此 cmdlet 不能删除以下默认组：</span><span class="sxs-lookup"><span data-stu-id="25231-144">This cmdlet cannot delete the following default groups:</span></span>

- <span data-ttu-id="25231-145">管理员</span><span class="sxs-lookup"><span data-stu-id="25231-145">Administrators</span></span>
- <span data-ttu-id="25231-146">备份操作员</span><span class="sxs-lookup"><span data-stu-id="25231-146">Backup Operators</span></span>
- <span data-ttu-id="25231-147">Cryptographic Operators</span><span class="sxs-lookup"><span data-stu-id="25231-147">Cryptographic Operators</span></span>
- <span data-ttu-id="25231-148">Distributed COM Users</span><span class="sxs-lookup"><span data-stu-id="25231-148">Distributed COM Users</span></span>
- <span data-ttu-id="25231-149">事件日志读者</span><span class="sxs-lookup"><span data-stu-id="25231-149">Event Log Readers</span></span>
- <span data-ttu-id="25231-150">来宾</span><span class="sxs-lookup"><span data-stu-id="25231-150">Guests</span></span>
- <span data-ttu-id="25231-151">Hyper-V 管理员</span><span class="sxs-lookup"><span data-stu-id="25231-151">Hyper-V Administrators</span></span>
- <span data-ttu-id="25231-152">IIS_IUSRS</span><span class="sxs-lookup"><span data-stu-id="25231-152">IIS_IUSRS</span></span>
- <span data-ttu-id="25231-153">Network Configuration Operators</span><span class="sxs-lookup"><span data-stu-id="25231-153">Network Configuration Operators</span></span>
- <span data-ttu-id="25231-154">性能日志用户</span><span class="sxs-lookup"><span data-stu-id="25231-154">Performance Log Users</span></span>
- <span data-ttu-id="25231-155">性能监视器用户</span><span class="sxs-lookup"><span data-stu-id="25231-155">Performance Monitor Users</span></span>
- <span data-ttu-id="25231-156">Power Users</span><span class="sxs-lookup"><span data-stu-id="25231-156">Power Users</span></span>
- <span data-ttu-id="25231-157">Remote Desktop Users</span><span class="sxs-lookup"><span data-stu-id="25231-157">Remote Desktop Users</span></span>
- <span data-ttu-id="25231-158">远程管理用户</span><span class="sxs-lookup"><span data-stu-id="25231-158">Remote Management Users</span></span>
- <span data-ttu-id="25231-159">复制程序</span><span class="sxs-lookup"><span data-stu-id="25231-159">Replicator</span></span>
- <span data-ttu-id="25231-160">用户</span><span class="sxs-lookup"><span data-stu-id="25231-160">Users</span></span>
- <span data-ttu-id="25231-161">WinRMRemoteWMIUsers__</span><span class="sxs-lookup"><span data-stu-id="25231-161">WinRMRemoteWMIUsers__</span></span>

* <span data-ttu-id="25231-162">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="25231-162">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="25231-163">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="25231-163">The possible sources are as follows:</span></span>

- <span data-ttu-id="25231-164">Local</span><span class="sxs-lookup"><span data-stu-id="25231-164">Local</span></span>
- <span data-ttu-id="25231-165">Active Directory</span><span class="sxs-lookup"><span data-stu-id="25231-165">Active Directory</span></span>
- <span data-ttu-id="25231-166">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="25231-166">Azure Active Directory group</span></span>
- <span data-ttu-id="25231-167">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="25231-167">Microsoft Account</span></span>

<span data-ttu-id="25231-168">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="25231-168">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="25231-169">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="25231-169">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="25231-170">相关链接</span><span class="sxs-lookup"><span data-stu-id="25231-170">RELATED LINKS</span></span>

[<span data-ttu-id="25231-171">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="25231-171">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="25231-172">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="25231-172">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="25231-173">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="25231-173">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="25231-174">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="25231-174">Set-LocalGroup</span></span>](Set-LocalGroup.md)
