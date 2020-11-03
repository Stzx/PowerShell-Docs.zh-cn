---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalGroup
ms.openlocfilehash: 471c3c7bc01bf26dfe9d8eec26e4414464cae02e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198337"
---
# <span data-ttu-id="9db3c-103">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="9db3c-103">Set-LocalGroup</span></span>

## <span data-ttu-id="9db3c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9db3c-104">SYNOPSIS</span></span>
<span data-ttu-id="9db3c-105">更改本地安全组。</span><span class="sxs-lookup"><span data-stu-id="9db3c-105">Changes a local security group.</span></span>

## <span data-ttu-id="9db3c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9db3c-106">SYNTAX</span></span>

### <span data-ttu-id="9db3c-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="9db3c-107">InputObject</span></span>

```
Set-LocalGroup -Description <String> [-InputObject] <LocalGroup> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9db3c-108">默认</span><span class="sxs-lookup"><span data-stu-id="9db3c-108">Default</span></span>

```
Set-LocalGroup -Description <String> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9db3c-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="9db3c-109">SecurityIdentifier</span></span>

```
Set-LocalGroup -Description <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9db3c-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9db3c-110">DESCRIPTION</span></span>
<span data-ttu-id="9db3c-111">**LocalGroup** cmdlet 将更改本地安全组。</span><span class="sxs-lookup"><span data-stu-id="9db3c-111">The **Set-LocalGroup** cmdlet changes a local security group.</span></span>

## <span data-ttu-id="9db3c-112">示例</span><span class="sxs-lookup"><span data-stu-id="9db3c-112">EXAMPLES</span></span>

### <span data-ttu-id="9db3c-113">示例1：更改组说明</span><span class="sxs-lookup"><span data-stu-id="9db3c-113">Example 1: Change a group description</span></span>

```
PS C:\> Set-LocalGroup -Name "SecurityGroup04" -Description "This is a sample description."
```

<span data-ttu-id="9db3c-114">此命令更改本地组的说明。</span><span class="sxs-lookup"><span data-stu-id="9db3c-114">This command changes the description of a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="9db3c-115">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="9db3c-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="9db3c-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9db3c-116">PARAMETERS</span></span>

### <span data-ttu-id="9db3c-117">-Description</span><span class="sxs-lookup"><span data-stu-id="9db3c-117">-Description</span></span>
<span data-ttu-id="9db3c-118">指定组的注释。</span><span class="sxs-lookup"><span data-stu-id="9db3c-118">Specifies a comment for the group.</span></span>
<span data-ttu-id="9db3c-119">最大长度为48个字符。</span><span class="sxs-lookup"><span data-stu-id="9db3c-119">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9db3c-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9db3c-120">-InputObject</span></span>
<span data-ttu-id="9db3c-121">指定此 cmdlet 更改的安全组。</span><span class="sxs-lookup"><span data-stu-id="9db3c-121">Specifies the security group that this cmdlet changes.</span></span>
<span data-ttu-id="9db3c-122">若要获取安全组，请使用 Get-LocalGroup cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9db3c-122">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

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

### <span data-ttu-id="9db3c-123">-Name</span><span class="sxs-lookup"><span data-stu-id="9db3c-123">-Name</span></span>
<span data-ttu-id="9db3c-124">指定此 cmdlet 更改的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="9db3c-124">Specifies the name of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="9db3c-125">-SID</span><span class="sxs-lookup"><span data-stu-id="9db3c-125">-SID</span></span>
<span data-ttu-id="9db3c-126">指定此 cmdlet 更改的安全组 (SID) 的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="9db3c-126">Specifies the security ID (SID) of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="9db3c-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9db3c-127">-Confirm</span></span>
<span data-ttu-id="9db3c-128">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="9db3c-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9db3c-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9db3c-129">-WhatIf</span></span>
<span data-ttu-id="9db3c-130">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="9db3c-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9db3c-131">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="9db3c-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9db3c-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9db3c-132">CommonParameters</span></span>
<span data-ttu-id="9db3c-133">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9db3c-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9db3c-134">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9db3c-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9db3c-135">输入</span><span class="sxs-lookup"><span data-stu-id="9db3c-135">INPUTS</span></span>

### <span data-ttu-id="9db3c-136">SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="9db3c-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="9db3c-137">可以通过管道将安全组、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9db3c-137">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="9db3c-138">输出</span><span class="sxs-lookup"><span data-stu-id="9db3c-138">OUTPUTS</span></span>

### <span data-ttu-id="9db3c-139">无</span><span class="sxs-lookup"><span data-stu-id="9db3c-139">None</span></span>
<span data-ttu-id="9db3c-140">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="9db3c-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="9db3c-141">注释</span><span class="sxs-lookup"><span data-stu-id="9db3c-141">NOTES</span></span>

* <span data-ttu-id="9db3c-142">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="9db3c-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="9db3c-143">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="9db3c-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="9db3c-144">Local</span><span class="sxs-lookup"><span data-stu-id="9db3c-144">Local</span></span>
- <span data-ttu-id="9db3c-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="9db3c-145">Active Directory</span></span>
- <span data-ttu-id="9db3c-146">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="9db3c-146">Azure Active Directory group</span></span>
- <span data-ttu-id="9db3c-147">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="9db3c-147">Microsoft Account</span></span>

<span data-ttu-id="9db3c-148">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="9db3c-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="9db3c-149">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="9db3c-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="9db3c-150">相关链接</span><span class="sxs-lookup"><span data-stu-id="9db3c-150">RELATED LINKS</span></span>

[<span data-ttu-id="9db3c-151">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="9db3c-151">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="9db3c-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="9db3c-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="9db3c-153">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="9db3c-153">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="9db3c-154">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="9db3c-154">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)
