---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: 139ebf10cd0097d55eac521cd81016f8f168d2bd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197985"
---
# <span data-ttu-id="7184e-103">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="7184e-103">New-FileCatalog</span></span>

## <span data-ttu-id="7184e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="7184e-104">SYNOPSIS</span></span>

<span data-ttu-id="7184e-105">`New-FileCatalog` 创建文件哈希的目录文件，这些文件哈希可用于验证文件的真实性。</span><span class="sxs-lookup"><span data-stu-id="7184e-105">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="7184e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7184e-106">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="7184e-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="7184e-107">DESCRIPTION</span></span>

<span data-ttu-id="7184e-108">`New-FileCatalog` 为一组文件夹和文件创建 [Windows 目录文件](/windows-hardware/drivers/install/catalog-files) 。</span><span class="sxs-lookup"><span data-stu-id="7184e-108">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span>
<span data-ttu-id="7184e-109">此目录文件包含提供的路径中的所有文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="7184e-109">This catalog file contains hashes for all files in the provided paths.</span></span>
<span data-ttu-id="7184e-110">然后，用户可以使用其文件分发目录，以便用户可以验证自目录创建后是否对文件夹进行了任何更改。</span><span class="sxs-lookup"><span data-stu-id="7184e-110">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="7184e-111">支持目录版本 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="7184e-111">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="7184e-112">版本1使用 (弃用) SHA1 哈希算法来创建文件哈希，版本2使用 SHA256。</span><span class="sxs-lookup"><span data-stu-id="7184e-112">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span>
<span data-ttu-id="7184e-113">Windows Server 2008 R2 或 Windows 7 不支持目录版本 2。</span><span class="sxs-lookup"><span data-stu-id="7184e-113">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span>
<span data-ttu-id="7184e-114">你应在 Windows 8、Windows Server 2012 及更高版本的操作系统上使用目录版本 2。</span><span class="sxs-lookup"><span data-stu-id="7184e-114">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="7184e-115">示例</span><span class="sxs-lookup"><span data-stu-id="7184e-115">EXAMPLES</span></span>

### <span data-ttu-id="7184e-116">示例1：为创建文件目录 `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="7184e-116">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="7184e-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7184e-117">PARAMETERS</span></span>

### <span data-ttu-id="7184e-118">-CatalogFilePath</span><span class="sxs-lookup"><span data-stu-id="7184e-118">-CatalogFilePath</span></span>

<span data-ttu-id="7184e-119">应放置目录文件)  ( 的文件或文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="7184e-119">A path to a file or folder where the catalog file (.cat) should be placed.</span></span>
<span data-ttu-id="7184e-120">如果指定了文件夹路径，则 `catalog.cat` 将使用默认文件名。</span><span class="sxs-lookup"><span data-stu-id="7184e-120">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

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

### <span data-ttu-id="7184e-121">-CatalogVersion</span><span class="sxs-lookup"><span data-stu-id="7184e-121">-CatalogVersion</span></span>

<span data-ttu-id="7184e-122">接受 `1.0` 或 `2.0` 作为指定目录版本的可能值。</span><span class="sxs-lookup"><span data-stu-id="7184e-122">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span>
<span data-ttu-id="7184e-123">`1.0` 应尽可能避免使用，因为它使用不安全的 SHA-1 哈希算法，而 `2.0` 使用 SECURE sha-256 算法，但在 `1.0` Windows 7 和 Server 2008R2 上是唯一受支持的算法。</span><span class="sxs-lookup"><span data-stu-id="7184e-123">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="7184e-124">-Path</span><span class="sxs-lookup"><span data-stu-id="7184e-124">-Path</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7184e-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="7184e-125">-Confirm</span></span>

<span data-ttu-id="7184e-126">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="7184e-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="7184e-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="7184e-127">-WhatIf</span></span>

<span data-ttu-id="7184e-128">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="7184e-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="7184e-129">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="7184e-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="7184e-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7184e-130">CommonParameters</span></span>
<span data-ttu-id="7184e-131">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="7184e-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7184e-132">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="7184e-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="7184e-133">输入</span><span class="sxs-lookup"><span data-stu-id="7184e-133">INPUTS</span></span>

### <span data-ttu-id="7184e-134">System.String</span><span class="sxs-lookup"><span data-stu-id="7184e-134">System.String</span></span>

<span data-ttu-id="7184e-135">管道采用用作目录文件名的字符串。</span><span class="sxs-lookup"><span data-stu-id="7184e-135">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="7184e-136">输出</span><span class="sxs-lookup"><span data-stu-id="7184e-136">OUTPUTS</span></span>

### <span data-ttu-id="7184e-137">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="7184e-137">System.IO.FileInfo</span></span>

## <span data-ttu-id="7184e-138">注释</span><span class="sxs-lookup"><span data-stu-id="7184e-138">NOTES</span></span>

## <span data-ttu-id="7184e-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="7184e-139">RELATED LINKS</span></span>

[<span data-ttu-id="7184e-140">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="7184e-140">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="7184e-141">立即</span><span class="sxs-lookup"><span data-stu-id="7184e-141">PowerShellGet</span></span>](/powerShell/module/powershellget)