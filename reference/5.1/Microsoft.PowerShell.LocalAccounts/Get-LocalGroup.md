---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197406"
---
# <span data-ttu-id="02e4c-103">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="02e4c-103">Get-LocalGroup</span></span>

## <span data-ttu-id="02e4c-104">摘要</span><span class="sxs-lookup"><span data-stu-id="02e4c-104">SYNOPSIS</span></span>
<span data-ttu-id="02e4c-105">获取本地安全组。</span><span class="sxs-lookup"><span data-stu-id="02e4c-105">Gets the local security groups.</span></span>

## <span data-ttu-id="02e4c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="02e4c-106">SYNTAX</span></span>

### <span data-ttu-id="02e4c-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="02e4c-107">Default (Default)</span></span>

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="02e4c-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="02e4c-108">SecurityIdentifier</span></span>

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="02e4c-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="02e4c-109">DESCRIPTION</span></span>
<span data-ttu-id="02e4c-110">**LocalGroup** cmdlet 将获取安全帐户管理器中的本地安全组。</span><span class="sxs-lookup"><span data-stu-id="02e4c-110">The **Get-LocalGroup** cmdlet gets local security groups in Security Account Manager.</span></span>
<span data-ttu-id="02e4c-111">此 cmdlet 将获取创建的默认内置组和本地安全组。</span><span class="sxs-lookup"><span data-stu-id="02e4c-111">This cmdlet gets default built-in groups and local security groups that you create.</span></span>

> [!NOTE]
> <span data-ttu-id="02e4c-112">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="02e4c-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="02e4c-113">示例</span><span class="sxs-lookup"><span data-stu-id="02e4c-113">EXAMPLES</span></span>

### <span data-ttu-id="02e4c-114">示例1：获取 Administrators 组</span><span class="sxs-lookup"><span data-stu-id="02e4c-114">Example 1: Get the Administrators group</span></span>

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

<span data-ttu-id="02e4c-115">此命令获取本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="02e4c-115">This command gets the local Administrators group.</span></span>
<span data-ttu-id="02e4c-116">该命令显示控制台中组的属性。</span><span class="sxs-lookup"><span data-stu-id="02e4c-116">The command displays properties of the group in the console.</span></span>

## <span data-ttu-id="02e4c-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="02e4c-117">PARAMETERS</span></span>

### <span data-ttu-id="02e4c-118">-Name</span><span class="sxs-lookup"><span data-stu-id="02e4c-118">-Name</span></span>
<span data-ttu-id="02e4c-119">指定此 cmdlet 获取的安全组的名称数组。</span><span class="sxs-lookup"><span data-stu-id="02e4c-119">Specifies an array of names of security groups that this cmdlet gets.</span></span>
<span data-ttu-id="02e4c-120">您可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="02e4c-120">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="02e4c-121">-SID</span><span class="sxs-lookup"><span data-stu-id="02e4c-121">-SID</span></span>
<span data-ttu-id="02e4c-122">指定 (此 cmdlet 获取的安全组的 Sid) 安全 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="02e4c-122">Specifies an array of security IDs (SIDs) of security groups that this cmdlet gets.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="02e4c-123">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="02e4c-123">CommonParameters</span></span>
<span data-ttu-id="02e4c-124">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="02e4c-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="02e4c-125">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="02e4c-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="02e4c-126">输入</span><span class="sxs-lookup"><span data-stu-id="02e4c-126">INPUTS</span></span>

### <span data-ttu-id="02e4c-127">System.string、SecurityIdentifier。）</span><span class="sxs-lookup"><span data-stu-id="02e4c-127">System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="02e4c-128">可以通过管道将字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="02e4c-128">You can pipe a string or a SID to this cmdlet.</span></span>

## <span data-ttu-id="02e4c-129">输出</span><span class="sxs-lookup"><span data-stu-id="02e4c-129">OUTPUTS</span></span>

### <span data-ttu-id="02e4c-130">SecurityAccountsManager. LocalGroup。</span><span class="sxs-lookup"><span data-stu-id="02e4c-130">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="02e4c-131">此 cmdlet 将返回本地组。</span><span class="sxs-lookup"><span data-stu-id="02e4c-131">This cmdlet returns a local group.</span></span>

## <span data-ttu-id="02e4c-132">注释</span><span class="sxs-lookup"><span data-stu-id="02e4c-132">NOTES</span></span>

* <span data-ttu-id="02e4c-133">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="02e4c-133">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="02e4c-134">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="02e4c-134">The possible sources are as follows:</span></span>

- <span data-ttu-id="02e4c-135">Local</span><span class="sxs-lookup"><span data-stu-id="02e4c-135">Local</span></span>
- <span data-ttu-id="02e4c-136">Active Directory</span><span class="sxs-lookup"><span data-stu-id="02e4c-136">Active Directory</span></span>
- <span data-ttu-id="02e4c-137">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="02e4c-137">Azure Active Directory group</span></span>
- <span data-ttu-id="02e4c-138">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="02e4c-138">Microsoft Account</span></span>

<span data-ttu-id="02e4c-139">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="02e4c-139">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="02e4c-140">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="02e4c-140">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="02e4c-141">相关链接</span><span class="sxs-lookup"><span data-stu-id="02e4c-141">RELATED LINKS</span></span>

[<span data-ttu-id="02e4c-142">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="02e4c-142">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="02e4c-143">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="02e4c-143">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="02e4c-144">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="02e4c-144">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="02e4c-145">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="02e4c-145">Set-LocalGroup</span></span>](Set-LocalGroup.md)
