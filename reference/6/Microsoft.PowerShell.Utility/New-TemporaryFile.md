---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 566a8bf22815e55457da430a02af391bb308b50c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198572"
---
# <span data-ttu-id="63406-103">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="63406-103">New-TemporaryFile</span></span>

## <span data-ttu-id="63406-104">摘要</span><span class="sxs-lookup"><span data-stu-id="63406-104">SYNOPSIS</span></span>
<span data-ttu-id="63406-105">创建临时文件。</span><span class="sxs-lookup"><span data-stu-id="63406-105">Creates a temporary file.</span></span>

## <span data-ttu-id="63406-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="63406-106">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="63406-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="63406-107">DESCRIPTION</span></span>

<span data-ttu-id="63406-108">此 cmdlet 创建可以在脚本中使用的临时文件。</span><span class="sxs-lookup"><span data-stu-id="63406-108">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="63406-109">`New-TemporaryFile`Cmdlet 将创建一个具有文件扩展名的空文件 `.tmp` 。</span><span class="sxs-lookup"><span data-stu-id="63406-109">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="63406-110">此 cmdlet 将文件命名 `tmp<NNNN>.tmp` 为，其中 `<NNNN>` 是一个随机十六进制数。</span><span class="sxs-lookup"><span data-stu-id="63406-110">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="63406-111">Cmdlet 将在 **临时** 文件夹中创建文件。</span><span class="sxs-lookup"><span data-stu-id="63406-111">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="63406-112">此 cmdlet 使用 [GetTempPath ( # B1](/dotnet/api/system.io.path.gettemppath) 方法查找 **临时** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="63406-112">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="63406-113">此方法按以下顺序检查环境变量是否存在，并使用找到的第一个路径：</span><span class="sxs-lookup"><span data-stu-id="63406-113">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="63406-114">在 Windows 平台上：</span><span class="sxs-lookup"><span data-stu-id="63406-114">On Windows platforms:</span></span>

  1. <span data-ttu-id="63406-115">TMP 环境变量指定的路径。</span><span class="sxs-lookup"><span data-stu-id="63406-115">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="63406-116">由 TEMP 环境变量指定的路径。</span><span class="sxs-lookup"><span data-stu-id="63406-116">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="63406-117">USERPROFILE 环境变量指定的路径。</span><span class="sxs-lookup"><span data-stu-id="63406-117">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="63406-118">Windows 目录。</span><span class="sxs-lookup"><span data-stu-id="63406-118">The Windows directory.</span></span>

- <span data-ttu-id="63406-119">在非 Windows 平台上：使用由 TMPDIR 环境变量指定的路径。</span><span class="sxs-lookup"><span data-stu-id="63406-119">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="63406-120">示例</span><span class="sxs-lookup"><span data-stu-id="63406-120">EXAMPLES</span></span>

### <span data-ttu-id="63406-121">示例 1：创建临时文件</span><span class="sxs-lookup"><span data-stu-id="63406-121">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="63406-122">此命令会 `.tmp` 在临时文件夹中生成文件，然后在变量中存储对文件的引用 `$TempFile` 。</span><span class="sxs-lookup"><span data-stu-id="63406-122">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="63406-123">以后可以在脚本中使用此文件。</span><span class="sxs-lookup"><span data-stu-id="63406-123">You can use this file later in your script.</span></span>

## <span data-ttu-id="63406-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="63406-124">PARAMETERS</span></span>

### <span data-ttu-id="63406-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="63406-125">-Confirm</span></span>

<span data-ttu-id="63406-126">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="63406-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="63406-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="63406-127">-WhatIf</span></span>

<span data-ttu-id="63406-128">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="63406-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="63406-129">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="63406-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="63406-130">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="63406-130">CommonParameters</span></span>

<span data-ttu-id="63406-131">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="63406-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="63406-132">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="63406-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="63406-133">输入</span><span class="sxs-lookup"><span data-stu-id="63406-133">INPUTS</span></span>

## <span data-ttu-id="63406-134">输出</span><span class="sxs-lookup"><span data-stu-id="63406-134">OUTPUTS</span></span>

### <span data-ttu-id="63406-135">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="63406-135">System.IO.FileInfo</span></span>

<span data-ttu-id="63406-136">此 cmdlet 返回表示临时文件的 **FileInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="63406-136">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="63406-137">注释</span><span class="sxs-lookup"><span data-stu-id="63406-137">NOTES</span></span>

## <span data-ttu-id="63406-138">相关链接</span><span class="sxs-lookup"><span data-stu-id="63406-138">RELATED LINKS</span></span>
