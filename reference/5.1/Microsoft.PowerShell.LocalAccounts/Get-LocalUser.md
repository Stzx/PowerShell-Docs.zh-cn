---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 34210145bcddc8d9420552d637a6cd6e5f8e61cc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197402"
---
# <span data-ttu-id="ae931-103">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ae931-103">Get-LocalUser</span></span>

## <span data-ttu-id="ae931-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ae931-104">SYNOPSIS</span></span>
<span data-ttu-id="ae931-105">获取本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ae931-105">Gets local user accounts.</span></span>

## <span data-ttu-id="ae931-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ae931-106">SYNTAX</span></span>

### <span data-ttu-id="ae931-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="ae931-107">Default (Default)</span></span>

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ae931-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ae931-108">SecurityIdentifier</span></span>

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="ae931-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ae931-109">DESCRIPTION</span></span>

<span data-ttu-id="ae931-110">`Get-LocalUser`Cmdlet 将获取本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ae931-110">The `Get-LocalUser` cmdlet gets local user accounts.</span></span> <span data-ttu-id="ae931-111">此 cmdlet 将获取默认的内置用户帐户、所创建的本地用户帐户，以及连接到 Microsoft 帐户的本地帐户。</span><span class="sxs-lookup"><span data-stu-id="ae931-111">This cmdlet gets default built-in user accounts, local user accounts that you created, and local accounts that you connected to Microsoft accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="ae931-112">LocalAccounts 模块在64位系统上的32位 PowerShell 中不可用。</span><span class="sxs-lookup"><span data-stu-id="ae931-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="ae931-113">示例</span><span class="sxs-lookup"><span data-stu-id="ae931-113">EXAMPLES</span></span>

### <span data-ttu-id="ae931-114">示例1：使用帐户名称获取帐户</span><span class="sxs-lookup"><span data-stu-id="ae931-114">Example 1: Get an account by using its name</span></span>

<span data-ttu-id="ae931-115">此示例将获取名为 AdminContoso02 的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ae931-115">This example gets a user account named AdminContoso02.</span></span>

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### <span data-ttu-id="ae931-116">示例2：获取连接到 Microsoft 帐户的帐户</span><span class="sxs-lookup"><span data-stu-id="ae931-116">Example 2: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="ae931-117">此示例将获取连接到 Microsoft 帐户的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ae931-117">This example gets a user account that is connected to a Microsoft account.</span></span> <span data-ttu-id="ae931-118">此示例在 Outlook.com 处为帐户的用户名使用占位符值。</span><span class="sxs-lookup"><span data-stu-id="ae931-118">This example uses a placeholder value for the username of an account at Outlook.com.</span></span>

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### <span data-ttu-id="ae931-119">示例3：获取连接到 Microsoft 帐户的帐户</span><span class="sxs-lookup"><span data-stu-id="ae931-119">Example 3: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="ae931-120">此示例获取具有指定 SID 的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ae931-120">This example gets a local user account that has the specified SID.</span></span>

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## <span data-ttu-id="ae931-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ae931-121">PARAMETERS</span></span>

### <span data-ttu-id="ae931-122">-Name</span><span class="sxs-lookup"><span data-stu-id="ae931-122">-Name</span></span>

<span data-ttu-id="ae931-123">指定此 cmdlet 获取的用户帐户的名称数组。</span><span class="sxs-lookup"><span data-stu-id="ae931-123">Specifies an array of names of user accounts that this cmdlet gets.</span></span> <span data-ttu-id="ae931-124">您可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ae931-124">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="ae931-125">-SID</span><span class="sxs-lookup"><span data-stu-id="ae931-125">-SID</span></span>

<span data-ttu-id="ae931-126">指定 (此 cmdlet 获取的用户帐户的 Sid) 安全 Id 的数组。</span><span class="sxs-lookup"><span data-stu-id="ae931-126">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet gets.</span></span>

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

### <span data-ttu-id="ae931-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ae931-127">CommonParameters</span></span>

<span data-ttu-id="ae931-128">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ae931-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ae931-129">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ae931-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ae931-130">输入</span><span class="sxs-lookup"><span data-stu-id="ae931-130">INPUTS</span></span>

### <span data-ttu-id="ae931-131">System.string、SecurityIdentifier。）</span><span class="sxs-lookup"><span data-stu-id="ae931-131">System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="ae931-132">可以通过管道将字符串或 SID 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae931-132">You can pipe a string or SID to this cmdlet.</span></span>

## <span data-ttu-id="ae931-133">输出</span><span class="sxs-lookup"><span data-stu-id="ae931-133">OUTPUTS</span></span>

### <span data-ttu-id="ae931-134">SecurityAccountsManager. LocalUser []</span><span class="sxs-lookup"><span data-stu-id="ae931-134">System.Management.Automation.SecurityAccountsManager.LocalUser[]</span></span>

<span data-ttu-id="ae931-135">此 cmdlet 将返回本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ae931-135">This cmdlet returns local user accounts.</span></span>

## <span data-ttu-id="ae931-136">注释</span><span class="sxs-lookup"><span data-stu-id="ae931-136">NOTES</span></span>

<span data-ttu-id="ae931-137">**LocalUser** 、 **LocalGroup** 和 **LocalPrincipal** 对象上的 **PrincipalSource** 属性描述了对象的源。</span><span class="sxs-lookup"><span data-stu-id="ae931-137">The **PrincipalSource** property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects describes the source of the object.</span></span> <span data-ttu-id="ae931-138">可能的源如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae931-138">The possible sources are as follows:</span></span>

- <span data-ttu-id="ae931-139">Local</span><span class="sxs-lookup"><span data-stu-id="ae931-139">Local</span></span>
- <span data-ttu-id="ae931-140">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ae931-140">Active Directory</span></span>
- <span data-ttu-id="ae931-141">Azure Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="ae931-141">Azure Active Directory group</span></span>
- <span data-ttu-id="ae931-142">Microsoft 帐户</span><span class="sxs-lookup"><span data-stu-id="ae931-142">Microsoft Account</span></span>

<span data-ttu-id="ae931-143">只有 Windows 10、Windows Server 2016 和更高版本的 Windows 操作系统才支持 **PrincipalSource** 。</span><span class="sxs-lookup"><span data-stu-id="ae931-143">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="ae931-144">对于早期版本，属性为空白。</span><span class="sxs-lookup"><span data-stu-id="ae931-144">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="ae931-145">相关链接</span><span class="sxs-lookup"><span data-stu-id="ae931-145">RELATED LINKS</span></span>

[<span data-ttu-id="ae931-146">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ae931-146">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="ae931-147">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ae931-147">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="ae931-148">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ae931-148">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="ae931-149">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ae931-149">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="ae931-150">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ae931-150">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="ae931-151">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ae931-151">Set-LocalUser</span></span>](Set-LocalUser.md)
