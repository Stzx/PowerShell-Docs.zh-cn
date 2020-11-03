---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalGroup
ms.openlocfilehash: 566d33bdeb52323cca41fa9757d36334b40f1654
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198336"
---
# <span data-ttu-id="f84af-103">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f84af-103">Rename-LocalGroup</span></span>

## <span data-ttu-id="f84af-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f84af-104">SYNOPSIS</span></span>
<span data-ttu-id="f84af-105">重命名本地安全组。</span><span class="sxs-lookup"><span data-stu-id="f84af-105">Renames a local security group.</span></span>

## <span data-ttu-id="f84af-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f84af-106">SYNTAX</span></span>

### <span data-ttu-id="f84af-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="f84af-107">InputObject</span></span>

```
Rename-LocalGroup [-InputObject] <LocalGroup> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f84af-108">默认</span><span class="sxs-lookup"><span data-stu-id="f84af-108">Default</span></span>

```
Rename-LocalGroup [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f84af-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="f84af-109">SecurityIdentifier</span></span>

```
Rename-LocalGroup [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f84af-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f84af-110">DESCRIPTION</span></span>
<span data-ttu-id="f84af-111">**LocalGroup** cmdlet 重命名本地安全组。</span><span class="sxs-lookup"><span data-stu-id="f84af-111">The **Rename-LocalGroup** cmdlet renames a local security group.</span></span>

> [!NOTE]
> <span data-ttu-id="f84af-112">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="f84af-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="f84af-113">示例</span><span class="sxs-lookup"><span data-stu-id="f84af-113">EXAMPLES</span></span>

### <span data-ttu-id="f84af-114">示例1：更改组的名称</span><span class="sxs-lookup"><span data-stu-id="f84af-114">Example 1: Change the name of a group</span></span>

```
PS C:\> Rename-LocalGroup -Name "SecurityGroup" -NewName "SecurityGroup04"
```

<span data-ttu-id="f84af-115">此命令重命名名为 SecurityGroup 的安全组。</span><span class="sxs-lookup"><span data-stu-id="f84af-115">This command renames a security group named SecurityGroup.</span></span>

## <span data-ttu-id="f84af-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f84af-116">PARAMETERS</span></span>

### <span data-ttu-id="f84af-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f84af-117">-InputObject</span></span>
<span data-ttu-id="f84af-118">指定此 cmdlet 重命名的安全组。</span><span class="sxs-lookup"><span data-stu-id="f84af-118">Specifies the security group that this cmdlet renames.</span></span>
<span data-ttu-id="f84af-119">若要获取安全组，请使用 Get-LocalGroup cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f84af-119">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f84af-120">-Name</span><span class="sxs-lookup"><span data-stu-id="f84af-120">-Name</span></span>
<span data-ttu-id="f84af-121">指定此 cmdlet 重命名的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="f84af-121">Specifies the name of the security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="f84af-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="f84af-122">-NewName</span></span>
<span data-ttu-id="f84af-123">指定安全组的新名称。</span><span class="sxs-lookup"><span data-stu-id="f84af-123">Specifies a new name for the security group.</span></span>

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

### <span data-ttu-id="f84af-124">-SID</span><span class="sxs-lookup"><span data-stu-id="f84af-124">-SID</span></span>
<span data-ttu-id="f84af-125">指定此 cmdlet 重命名的安全组 (SID) 的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="f84af-125">Specifies the security ID (SID) of a security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="f84af-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f84af-126">-Confirm</span></span>
<span data-ttu-id="f84af-127">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="f84af-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f84af-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f84af-128">-WhatIf</span></span>
<span data-ttu-id="f84af-129">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="f84af-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f84af-130">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="f84af-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f84af-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f84af-131">CommonParameters</span></span>
<span data-ttu-id="f84af-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="f84af-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f84af-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="f84af-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f84af-134">输入</span><span class="sxs-lookup"><span data-stu-id="f84af-134">INPUTS</span></span>

### <span data-ttu-id="f84af-135">SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="f84af-135">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="f84af-136">可以通过管道将安全组、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f84af-136">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="f84af-137">输出</span><span class="sxs-lookup"><span data-stu-id="f84af-137">OUTPUTS</span></span>

### <span data-ttu-id="f84af-138">无</span><span class="sxs-lookup"><span data-stu-id="f84af-138">None</span></span>
<span data-ttu-id="f84af-139">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="f84af-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f84af-140">注释</span><span class="sxs-lookup"><span data-stu-id="f84af-140">NOTES</span></span>

* <span data-ttu-id="f84af-141">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="f84af-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="f84af-142">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="f84af-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="f84af-143">Local</span><span class="sxs-lookup"><span data-stu-id="f84af-143">Local</span></span>
- <span data-ttu-id="f84af-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="f84af-144">Active Directory</span></span>
- <span data-ttu-id="f84af-145">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="f84af-145">Azure Active Directory group</span></span>
- <span data-ttu-id="f84af-146">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="f84af-146">Microsoft Account</span></span>

<span data-ttu-id="f84af-147">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="f84af-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="f84af-148">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="f84af-148">For earlier  versions, the property is blank.</span></span>

## <span data-ttu-id="f84af-149">相关链接</span><span class="sxs-lookup"><span data-stu-id="f84af-149">RELATED LINKS</span></span>

[<span data-ttu-id="f84af-150">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f84af-150">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="f84af-151">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f84af-151">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="f84af-152">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f84af-152">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="f84af-153">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f84af-153">Set-LocalGroup</span></span>](Set-LocalGroup.md)
