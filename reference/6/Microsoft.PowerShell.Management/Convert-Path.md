---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: c7ab1143b406af08c921d2ce27c5c60470b2f11e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197567"
---
# <span data-ttu-id="a06c9-103">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="a06c9-103">Convert-Path</span></span>

## <span data-ttu-id="a06c9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="a06c9-104">SYNOPSIS</span></span>
<span data-ttu-id="a06c9-105">将路径从 PowerShell 路径转换为 PowerShell 提供程序路径。</span><span class="sxs-lookup"><span data-stu-id="a06c9-105">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="a06c9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a06c9-106">SYNTAX</span></span>

### <span data-ttu-id="a06c9-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="a06c9-107">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="a06c9-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a06c9-108">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## <span data-ttu-id="a06c9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a06c9-109">DESCRIPTION</span></span>

<span data-ttu-id="a06c9-110">`Convert-Path`Cmdlet 可将路径从 powershell 路径转换为 powershell 提供程序路径。</span><span class="sxs-lookup"><span data-stu-id="a06c9-110">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="a06c9-111">示例</span><span class="sxs-lookup"><span data-stu-id="a06c9-111">EXAMPLES</span></span>

### <span data-ttu-id="a06c9-112">示例 1：将工作目录转换为标准文件系统路径</span><span class="sxs-lookup"><span data-stu-id="a06c9-112">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="a06c9-113">此示例将当前工作目录（由点 (`.`) 表示）转换为标准文件系统路径。</span><span class="sxs-lookup"><span data-stu-id="a06c9-113">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="a06c9-114">示例 2：将提供程序路径转换为标准注册表路径</span><span class="sxs-lookup"><span data-stu-id="a06c9-114">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="a06c9-115">此示例将 PowerShell 提供程序路径转换为标准的注册表路径。</span><span class="sxs-lookup"><span data-stu-id="a06c9-115">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="a06c9-116">示例 3：将路径转换为字符串</span><span class="sxs-lookup"><span data-stu-id="a06c9-116">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="a06c9-117">此示例将当前提供程序（FileSystem 提供程序）主目录的路径转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="a06c9-117">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="a06c9-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a06c9-118">PARAMETERS</span></span>

### <span data-ttu-id="a06c9-119">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a06c9-119">-LiteralPath</span></span>

<span data-ttu-id="a06c9-120">指定要转换的路径（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="a06c9-120">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="a06c9-121">**LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="a06c9-121">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="a06c9-122">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="a06c9-122">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="a06c9-123">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="a06c9-123">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a06c9-124">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="a06c9-124">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a06c9-125">-Path</span><span class="sxs-lookup"><span data-stu-id="a06c9-125">-Path</span></span>

<span data-ttu-id="a06c9-126">指定要转换的 PowerShell 路径。</span><span class="sxs-lookup"><span data-stu-id="a06c9-126">Specifies the PowerShell path to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a06c9-127">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a06c9-127">CommonParameters</span></span>

<span data-ttu-id="a06c9-128">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="a06c9-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a06c9-129">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="a06c9-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a06c9-130">输入</span><span class="sxs-lookup"><span data-stu-id="a06c9-130">INPUTS</span></span>

### <span data-ttu-id="a06c9-131">System.String</span><span class="sxs-lookup"><span data-stu-id="a06c9-131">System.String</span></span>

<span data-ttu-id="a06c9-132">可以通过管道将路径（但不是文本路径）传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a06c9-132">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="a06c9-133">输出</span><span class="sxs-lookup"><span data-stu-id="a06c9-133">OUTPUTS</span></span>

### <span data-ttu-id="a06c9-134">System.String</span><span class="sxs-lookup"><span data-stu-id="a06c9-134">System.String</span></span>

<span data-ttu-id="a06c9-135">此 cmdlet 返回一个包含已转换的路径的字符串。</span><span class="sxs-lookup"><span data-stu-id="a06c9-135">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="a06c9-136">注释</span><span class="sxs-lookup"><span data-stu-id="a06c9-136">NOTES</span></span>

<span data-ttu-id="a06c9-137">包含 Path 名词的 cmdlet 操作路径名称，并以所有 PowerShell 提供程序可解释的简明格式返回名称。</span><span class="sxs-lookup"><span data-stu-id="a06c9-137">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="a06c9-138">这些 cmdlet 用于需要在其中以特定格式显示全部或部分路径名称的程序或脚本中。</span><span class="sxs-lookup"><span data-stu-id="a06c9-138">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="a06c9-139">像使用 **Dirname** 、 **Normpath** 、 **Realpath** 、 **Join** 或其他路径操控器一样使用它们。</span><span class="sxs-lookup"><span data-stu-id="a06c9-139">Use them like you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="a06c9-140">可以将路径 cmdlet 与某些提供程序一起使用，包括 FileSystem、Registry 和 Certificate 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a06c9-140">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="a06c9-141">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="a06c9-141">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a06c9-142">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="a06c9-142">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a06c9-143">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="a06c9-143">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="a06c9-144">`Convert-Path` 仅转换现有路径。</span><span class="sxs-lookup"><span data-stu-id="a06c9-144">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="a06c9-145">它不能用于转换尚不存在的位置。</span><span class="sxs-lookup"><span data-stu-id="a06c9-145">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="a06c9-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="a06c9-146">RELATED LINKS</span></span>

[<span data-ttu-id="a06c9-147">Join-Path</span><span class="sxs-lookup"><span data-stu-id="a06c9-147">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="a06c9-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="a06c9-148">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="a06c9-149">Split-Path</span><span class="sxs-lookup"><span data-stu-id="a06c9-149">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="a06c9-150">Test-Path</span><span class="sxs-lookup"><span data-stu-id="a06c9-150">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="a06c9-151">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="a06c9-151">Get-PSProvider</span></span>](Get-PSProvider.md)
