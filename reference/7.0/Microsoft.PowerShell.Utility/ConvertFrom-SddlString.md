---
external help file: Microsoft.PowerShell.Utility-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-sddlstring?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-SddlString
ms.openlocfilehash: 9c864ec46af9584f36eef3f3ba879cf314e0ca1c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94347306"
---
# <span data-ttu-id="ac82d-103">ConvertFrom-SddlString</span><span class="sxs-lookup"><span data-stu-id="ac82d-103">ConvertFrom-SddlString</span></span>

## <span data-ttu-id="ac82d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ac82d-104">SYNOPSIS</span></span>
<span data-ttu-id="ac82d-105">将 SDDL 字符串转换为自定义对象。</span><span class="sxs-lookup"><span data-stu-id="ac82d-105">Converts a SDDL string to a custom object.</span></span>

## <span data-ttu-id="ac82d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ac82d-106">SYNTAX</span></span>

### <span data-ttu-id="ac82d-107">全部</span><span class="sxs-lookup"><span data-stu-id="ac82d-107">All</span></span>

```
ConvertFrom-SddlString [-Sddl] <String> [-Type <AccessRightTypeNames>] [<CommonParameters>]
```

## <span data-ttu-id="ac82d-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ac82d-108">DESCRIPTION</span></span>

<span data-ttu-id="ac82d-109">`ConvertFrom-SddlString`Cmdlet 可将安全描述符定义语言字符串转换为具有以下属性的自定义 **PSCustomObject** 对象： Owner、Group、descriptor.discretionaryacl、SystemAcl 和 RawDescriptor。</span><span class="sxs-lookup"><span data-stu-id="ac82d-109">The `ConvertFrom-SddlString` cmdlet converts a Security Descriptor Definition Language string to a custom **PSCustomObject** object with the following properties: Owner, Group, DiscretionaryAcl, SystemAcl and RawDescriptor.</span></span>

<span data-ttu-id="ac82d-110">所有者、组、Descriptor.discretionaryacl 和 SystemAcl 属性包含 SDDL 字符串中指定的访问权限的可读文本表示形式。</span><span class="sxs-lookup"><span data-stu-id="ac82d-110">Owner, Group, DiscretionaryAcl and SystemAcl properties contain a readable text representation of the access rights specified in a SDDL string.</span></span>

<span data-ttu-id="ac82d-111">此 cmdlet 是在 PowerShell 5.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ac82d-111">This cmdlet was introduced in PowerShell 5.0.</span></span>

## <span data-ttu-id="ac82d-112">示例</span><span class="sxs-lookup"><span data-stu-id="ac82d-112">EXAMPLES</span></span>

### <span data-ttu-id="ac82d-113">示例1：将文件系统访问权限 SDDL 转换为 PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="ac82d-113">Example 1: Convert file system access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl -Path C:\Windows
ConvertFrom-SddlString -Sddl $acl.Sddl
```

<span data-ttu-id="ac82d-114">第一个命令使用 `Get-Acl` cmdlet 来获取 C：\Windows 文件夹的安全描述符，并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="ac82d-114">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the C:\Windows folder and saves it in the variable.</span></span>

<span data-ttu-id="ac82d-115">第二个命令使用 `ConvertFrom-SddlString` cmdlet 来获取 sddl 字符串的文本表示形式，该对象包含在表示安全描述符的对象的 "sddl" 属性中。</span><span class="sxs-lookup"><span data-stu-id="ac82d-115">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

### <span data-ttu-id="ac82d-116">示例2：将注册表访问权限 SDDL 转换为 PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="ac82d-116">Example 2: Convert registry access rights SDDL to a PSCustomObject</span></span>

```powershell
$acl = Get-Acl HKLM:\SOFTWARE\Microsoft\
ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights
```

<span data-ttu-id="ac82d-117">第一个命令使用 `Get-Acl` cmdlet 来获取 HKLM： \ SOFTWARE\Microsoft\ 密钥的安全描述符，并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="ac82d-117">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="ac82d-118">第二个命令使用 `ConvertFrom-SddlString` cmdlet 来获取 sddl 字符串的文本表示形式，该对象包含在表示安全描述符的对象的 "sddl" 属性中。</span><span class="sxs-lookup"><span data-stu-id="ac82d-118">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="ac82d-119">它使用 `-Type` 参数来指定 SDDL 字符串表示注册表安全描述符。</span><span class="sxs-lookup"><span data-stu-id="ac82d-119">It uses the `-Type` parameter to specify that SDDL string represents a registry security descriptor.</span></span>

### <span data-ttu-id="ac82d-120">示例3：使用带有和不带参数的 ConvertFrom-SddlString 将注册表访问权限 SDDL 转换为 PSCustomObject `-Type`</span><span class="sxs-lookup"><span data-stu-id="ac82d-120">Example 3: Convert registry access rights SDDL to a PSCustomObject by using ConvertFrom-SddlString with and without the `-Type` parameter</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Microsoft\

ConvertFrom-SddlString -Sddl $acl.Sddl | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateDirectories, Delete, ExecuteKey, FullControl, GenericExecute, GenericWrite, ListDirectory, ReadExtendedAttributes, ReadPermissions, TakeOwnership, Traverse, WriteData, WriteExtendedAttributes, WriteKey)

ConvertFrom-SddlString -Sddl $acl.Sddl -Type RegistryRights | Foreach-Object {$_.DiscretionaryAcl[0]}

BUILTIN\Administrators: AccessAllowed (ChangePermissions, CreateLink, CreateSubKey, Delete, EnumerateSubKeys, ExecuteKey, FullControl, GenericExecute, GenericWrite, Notify, QueryValues, ReadPermissions, SetValue, TakeOwnership, WriteKey)
```

<span data-ttu-id="ac82d-121">第一个命令使用 `Get-Acl` cmdlet 来获取 HKLM： \ SOFTWARE\Microsoft\ 密钥的安全描述符，并将其保存在变量中。</span><span class="sxs-lookup"><span data-stu-id="ac82d-121">The first command uses the `Get-Acl` cmdlet to get the security descriptor for the HKLM:\SOFTWARE\Microsoft\ key and saves it in the variable.</span></span>

<span data-ttu-id="ac82d-122">第二个命令使用 `ConvertFrom-SddlString` cmdlet 来获取 sddl 字符串的文本表示形式，该对象包含在表示安全描述符的对象的 "sddl" 属性中。</span><span class="sxs-lookup"><span data-stu-id="ac82d-122">The second command uses the `ConvertFrom-SddlString` cmdlet to get the text representation of the SDDL string, contained in the Sddl property of the object representing the security descriptor.</span></span>

<span data-ttu-id="ac82d-123">它不使用 `-Type` 参数，因此显示的访问权限用于文件系统。</span><span class="sxs-lookup"><span data-stu-id="ac82d-123">It doesn't use the `-Type` parameter, so the access rights shown are for file system.</span></span>

<span data-ttu-id="ac82d-124">第三个命令将 `ConvertFrom-SddlString` cmdlet 与参数一起使用 `-Type` ，以使返回的访问权限用于注册表。</span><span class="sxs-lookup"><span data-stu-id="ac82d-124">The third command uses the `ConvertFrom-SddlString` cmdlet with the `-Type` parameter, so the access rights returned are for registry.</span></span>

## <span data-ttu-id="ac82d-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ac82d-125">PARAMETERS</span></span>

### <span data-ttu-id="ac82d-126">-Sddl</span><span class="sxs-lookup"><span data-stu-id="ac82d-126">-Sddl</span></span>

<span data-ttu-id="ac82d-127">指定表示安全描述符的字符串（SDDL 语法）。</span><span class="sxs-lookup"><span data-stu-id="ac82d-127">Specifies the string representing the security descriptor in SDDL syntax.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ac82d-128">-Type</span><span class="sxs-lookup"><span data-stu-id="ac82d-128">-Type</span></span>

<span data-ttu-id="ac82d-129">指定 SDDL 字符串表示的权限类型。</span><span class="sxs-lookup"><span data-stu-id="ac82d-129">Specifies the type of rights that SDDL string represents.</span></span>

<span data-ttu-id="ac82d-130">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ac82d-130">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ac82d-131">FileSystemRights</span><span class="sxs-lookup"><span data-stu-id="ac82d-131">FileSystemRights</span></span>
- <span data-ttu-id="ac82d-132">RegistryRights</span><span class="sxs-lookup"><span data-stu-id="ac82d-132">RegistryRights</span></span>
- <span data-ttu-id="ac82d-133">ActiveDirectoryRights</span><span class="sxs-lookup"><span data-stu-id="ac82d-133">ActiveDirectoryRights</span></span>
- <span data-ttu-id="ac82d-134">MutexRights</span><span class="sxs-lookup"><span data-stu-id="ac82d-134">MutexRights</span></span>
- <span data-ttu-id="ac82d-135">SemaphoreRights</span><span class="sxs-lookup"><span data-stu-id="ac82d-135">SemaphoreRights</span></span>
- <span data-ttu-id="ac82d-136">CryptoKeyRights</span><span class="sxs-lookup"><span data-stu-id="ac82d-136">CryptoKeyRights</span></span>
- <span data-ttu-id="ac82d-137">EventWaitHandleRights</span><span class="sxs-lookup"><span data-stu-id="ac82d-137">EventWaitHandleRights</span></span>

<span data-ttu-id="ac82d-138">默认情况下，cmdlet 使用文件系统权限。</span><span class="sxs-lookup"><span data-stu-id="ac82d-138">By default cmdlet uses file system rights.</span></span>

<span data-ttu-id="ac82d-139">CryptoKeyRights 和 ActiveDirectoryRights 在 PowerShell Core 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="ac82d-139">CryptoKeyRights and ActiveDirectoryRights are not supported in PowerShell Core.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ConvertFromSddlStringCommand+AccessRightTypeNames
Parameter Sets: (All)
Aliases:
Accepted values: FileSystemRights, RegistryRights, ActiveDirectoryRights, MutexRights, SemaphoreRights, CryptoKeyRights, EventWaitHandleRights

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ac82d-140">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ac82d-140">CommonParameters</span></span>

<span data-ttu-id="ac82d-141">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ac82d-141">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ac82d-142">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ac82d-142">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ac82d-143">输入</span><span class="sxs-lookup"><span data-stu-id="ac82d-143">INPUTS</span></span>

### <span data-ttu-id="ac82d-144">System.String</span><span class="sxs-lookup"><span data-stu-id="ac82d-144">System.String</span></span>

<span data-ttu-id="ac82d-145">可以通过管道将 SDDL 字符串传递给 `ConvertFrom-SddlString` 。</span><span class="sxs-lookup"><span data-stu-id="ac82d-145">You can pipe a SDDL string to `ConvertFrom-SddlString`.</span></span>

## <span data-ttu-id="ac82d-146">输出</span><span class="sxs-lookup"><span data-stu-id="ac82d-146">OUTPUTS</span></span>

## <span data-ttu-id="ac82d-147">注释</span><span class="sxs-lookup"><span data-stu-id="ac82d-147">NOTES</span></span>

<span data-ttu-id="ac82d-148">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="ac82d-148">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="ac82d-149">相关链接</span><span class="sxs-lookup"><span data-stu-id="ac82d-149">RELATED LINKS</span></span>

[<span data-ttu-id="ac82d-150">安全描述符定义语言</span><span class="sxs-lookup"><span data-stu-id="ac82d-150">Security Descriptor Definition Language</span></span>](/windows/win32/secauthz/security-descriptor-definition-language)
