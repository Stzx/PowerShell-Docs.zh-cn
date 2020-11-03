---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197403"
---
# <span data-ttu-id="2ec34-103">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="2ec34-103">Get-LocalGroupMember</span></span>

## <span data-ttu-id="2ec34-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2ec34-104">SYNOPSIS</span></span>
<span data-ttu-id="2ec34-105">获取本地组中的成员。</span><span class="sxs-lookup"><span data-stu-id="2ec34-105">Gets members from a local group.</span></span>

## <span data-ttu-id="2ec34-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2ec34-106">SYNTAX</span></span>

### <span data-ttu-id="2ec34-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="2ec34-107">Default (Default)</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### <span data-ttu-id="2ec34-108">组</span><span class="sxs-lookup"><span data-stu-id="2ec34-108">Group</span></span>

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### <span data-ttu-id="2ec34-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="2ec34-109">SecurityIdentifier</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## <span data-ttu-id="2ec34-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2ec34-110">DESCRIPTION</span></span>
<span data-ttu-id="2ec34-111">**LocalGroupMember** cmdlet 将获取本地组中的成员。</span><span class="sxs-lookup"><span data-stu-id="2ec34-111">The **Get-LocalGroupMember** cmdlet gets members from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="2ec34-112">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="2ec34-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="2ec34-113">示例</span><span class="sxs-lookup"><span data-stu-id="2ec34-113">EXAMPLES</span></span>

### <span data-ttu-id="2ec34-114">示例1：获取 Administrators 组的所有成员</span><span class="sxs-lookup"><span data-stu-id="2ec34-114">Example 1: Get all members of the Administrators group</span></span>

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

<span data-ttu-id="2ec34-115">此命令将获取本地 Administrators 组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="2ec34-115">This command gets all the members of the local Administrators group.</span></span>

## <span data-ttu-id="2ec34-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2ec34-116">PARAMETERS</span></span>

### <span data-ttu-id="2ec34-117">-Group</span><span class="sxs-lookup"><span data-stu-id="2ec34-117">-Group</span></span>
<span data-ttu-id="2ec34-118">指定此 cmdlet 从中获取成员的安全组。</span><span class="sxs-lookup"><span data-stu-id="2ec34-118">Specifies the security group from which this cmdlet gets members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2ec34-119">-成员</span><span class="sxs-lookup"><span data-stu-id="2ec34-119">-Member</span></span>
<span data-ttu-id="2ec34-120">指定此 cmdlet 从安全组获取的用户或组。</span><span class="sxs-lookup"><span data-stu-id="2ec34-120">Specifies a user or group that this cmdlet gets from a security group.</span></span>
<span data-ttu-id="2ec34-121">可以按名称或安全 ID 指定用户或组 (SID) 。</span><span class="sxs-lookup"><span data-stu-id="2ec34-121">You can specify users or groups by name or security ID (SID).</span></span>
<span data-ttu-id="2ec34-122">在 S-R-I-S-s 中指定 SID 字符串。</span><span class="sxs-lookup"><span data-stu-id="2ec34-122">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="2ec34-123">.</span><span class="sxs-lookup"><span data-stu-id="2ec34-123">.</span></span> <span data-ttu-id="2ec34-124">.</span><span class="sxs-lookup"><span data-stu-id="2ec34-124">.</span></span>
<span data-ttu-id="2ec34-125">格式表示）。</span><span class="sxs-lookup"><span data-stu-id="2ec34-125">format.</span></span>
<span data-ttu-id="2ec34-126">您可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="2ec34-126">You can use wildcard characters.</span></span>
<span data-ttu-id="2ec34-127">如果未指定此参数，则该 cmdlet 将获取组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="2ec34-127">If you do not specify this parameter, the cmdlet gets all members of the group.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2ec34-128">-Name</span><span class="sxs-lookup"><span data-stu-id="2ec34-128">-Name</span></span>
<span data-ttu-id="2ec34-129">指定此 cmdlet 从中获取成员的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="2ec34-129">Specifies the name of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="2ec34-130">-SID</span><span class="sxs-lookup"><span data-stu-id="2ec34-130">-SID</span></span>
<span data-ttu-id="2ec34-131">指定此 cmdlet 从中获取成员的安全组的安全 ID。</span><span class="sxs-lookup"><span data-stu-id="2ec34-131">Specifies the security ID of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="2ec34-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2ec34-132">CommonParameters</span></span>
<span data-ttu-id="2ec34-133">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2ec34-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2ec34-134">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2ec34-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2ec34-135">输入</span><span class="sxs-lookup"><span data-stu-id="2ec34-135">INPUTS</span></span>

### <span data-ttu-id="2ec34-136">SecurityAccountsManager. LocalGroup、SecurityIdentifier 和的数据库的安全层。</span><span class="sxs-lookup"><span data-stu-id="2ec34-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="2ec34-137">可以通过管道将本地组、字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2ec34-137">You can pipe a local group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="2ec34-138">输出</span><span class="sxs-lookup"><span data-stu-id="2ec34-138">OUTPUTS</span></span>

### <span data-ttu-id="2ec34-139">SecurityAccountsManager. LocalPrincipal</span><span class="sxs-lookup"><span data-stu-id="2ec34-139">Microsoft.SecurityAccountsManager.LocalPrincipal</span></span>
<span data-ttu-id="2ec34-140">此 cmdlet 返回本地主体。</span><span class="sxs-lookup"><span data-stu-id="2ec34-140">This cmdlet returns local principals.</span></span>

## <span data-ttu-id="2ec34-141">注释</span><span class="sxs-lookup"><span data-stu-id="2ec34-141">NOTES</span></span>

* <span data-ttu-id="2ec34-142">**PrincipalSource** 属性是 **LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象的属性，用于描述对象的源。</span><span class="sxs-lookup"><span data-stu-id="2ec34-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="2ec34-143">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ec34-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="2ec34-144">Local</span><span class="sxs-lookup"><span data-stu-id="2ec34-144">Local</span></span>
- <span data-ttu-id="2ec34-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="2ec34-145">Active Directory</span></span>
- <span data-ttu-id="2ec34-146">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="2ec34-146">Azure Active Directory group</span></span>
- <span data-ttu-id="2ec34-147">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="2ec34-147">Microsoft Account</span></span>

<span data-ttu-id="2ec34-148">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="2ec34-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="2ec34-149">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="2ec34-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="2ec34-150">相关链接</span><span class="sxs-lookup"><span data-stu-id="2ec34-150">RELATED LINKS</span></span>

[<span data-ttu-id="2ec34-151">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="2ec34-151">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="2ec34-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="2ec34-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="2ec34-153">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="2ec34-153">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
