---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalGroup
ms.openlocfilehash: de66ad724d3cfee2d296d3b431618768a9cd38da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198102"
---
# <span data-ttu-id="6735c-103">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6735c-103">New-LocalGroup</span></span>

## <span data-ttu-id="6735c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6735c-104">SYNOPSIS</span></span>
<span data-ttu-id="6735c-105">创建本地安全组。</span><span class="sxs-lookup"><span data-stu-id="6735c-105">Creates a local security group.</span></span>

## <span data-ttu-id="6735c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6735c-106">SYNTAX</span></span>

```
New-LocalGroup [-Description <String>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6735c-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6735c-107">DESCRIPTION</span></span>
<span data-ttu-id="6735c-108">**LocalGroup** Cmdlet 在安全帐户管理器中创建本地安全组。</span><span class="sxs-lookup"><span data-stu-id="6735c-108">The **New-LocalGroup** cmdlet creates a local security group in the Security Account Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="6735c-109">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="6735c-109">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="6735c-110">示例</span><span class="sxs-lookup"><span data-stu-id="6735c-110">EXAMPLES</span></span>

### <span data-ttu-id="6735c-111">示例1：创建安全组</span><span class="sxs-lookup"><span data-stu-id="6735c-111">Example 1: Create a security group</span></span>

```
PS C:\> New-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="6735c-112">此命令创建名为 SecurityGroup04 的组。</span><span class="sxs-lookup"><span data-stu-id="6735c-112">This command creates a group named SecurityGroup04.</span></span>

## <span data-ttu-id="6735c-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6735c-113">PARAMETERS</span></span>

### <span data-ttu-id="6735c-114">-Description</span><span class="sxs-lookup"><span data-stu-id="6735c-114">-Description</span></span>
<span data-ttu-id="6735c-115">指定组的注释。</span><span class="sxs-lookup"><span data-stu-id="6735c-115">Specifies a comment for the group.</span></span>
<span data-ttu-id="6735c-116">最大长度为48个字符。</span><span class="sxs-lookup"><span data-stu-id="6735c-116">The maximum length is 48 characters.</span></span>

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

### <span data-ttu-id="6735c-117">-Name</span><span class="sxs-lookup"><span data-stu-id="6735c-117">-Name</span></span>
<span data-ttu-id="6735c-118">指定组的名称。</span><span class="sxs-lookup"><span data-stu-id="6735c-118">Specifies a name for the group.</span></span>
<span data-ttu-id="6735c-119">最大长度为 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="6735c-119">The maximum length is 256 characters.</span></span>

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

### <span data-ttu-id="6735c-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6735c-120">-Confirm</span></span>
<span data-ttu-id="6735c-121">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="6735c-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6735c-122">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6735c-122">-WhatIf</span></span>
<span data-ttu-id="6735c-123">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="6735c-123">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6735c-124">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="6735c-124">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6735c-125">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6735c-125">CommonParameters</span></span>
<span data-ttu-id="6735c-126">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6735c-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6735c-127">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6735c-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6735c-128">输入</span><span class="sxs-lookup"><span data-stu-id="6735c-128">INPUTS</span></span>

### <span data-ttu-id="6735c-129">System.String</span><span class="sxs-lookup"><span data-stu-id="6735c-129">System.String</span></span>
<span data-ttu-id="6735c-130">可以通过管道将字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6735c-130">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="6735c-131">输出</span><span class="sxs-lookup"><span data-stu-id="6735c-131">OUTPUTS</span></span>

### <span data-ttu-id="6735c-132">SecurityAccountsManager. LocalGroup。</span><span class="sxs-lookup"><span data-stu-id="6735c-132">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="6735c-133">此 cmdlet 将返回安全组。</span><span class="sxs-lookup"><span data-stu-id="6735c-133">This cmdlet returns a security group.</span></span>

## <span data-ttu-id="6735c-134">注释</span><span class="sxs-lookup"><span data-stu-id="6735c-134">NOTES</span></span>

* <span data-ttu-id="6735c-135">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="6735c-135">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="6735c-136">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="6735c-136">The possible sources are as follows:</span></span>

- <span data-ttu-id="6735c-137">Local</span><span class="sxs-lookup"><span data-stu-id="6735c-137">Local</span></span>
- <span data-ttu-id="6735c-138">Active Directory</span><span class="sxs-lookup"><span data-stu-id="6735c-138">Active Directory</span></span>
- <span data-ttu-id="6735c-139">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="6735c-139">Azure Active Directory group</span></span>
- <span data-ttu-id="6735c-140">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="6735c-140">Microsoft Account</span></span>

<span data-ttu-id="6735c-141">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="6735c-141">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="6735c-142">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="6735c-142">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="6735c-143">相关链接</span><span class="sxs-lookup"><span data-stu-id="6735c-143">RELATED LINKS</span></span>

[<span data-ttu-id="6735c-144">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6735c-144">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="6735c-145">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6735c-145">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="6735c-146">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6735c-146">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="6735c-147">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6735c-147">Set-LocalGroup</span></span>](Set-LocalGroup.md)
