---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: d5a4e16f06ae98532f9716deb87dcadac50f8081
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197312"
---
# <span data-ttu-id="af65e-103">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="af65e-103">Resolve-Path</span></span>

## <span data-ttu-id="af65e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="af65e-104">SYNOPSIS</span></span>
<span data-ttu-id="af65e-105">解析路径中的通配符并显示路径内容。</span><span class="sxs-lookup"><span data-stu-id="af65e-105">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="af65e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="af65e-106">SYNTAX</span></span>

### <span data-ttu-id="af65e-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="af65e-107">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="af65e-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="af65e-108">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="af65e-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="af65e-109">DESCRIPTION</span></span>

<span data-ttu-id="af65e-110">`Resolve-Path`Cmdlet 将在指定位置显示与通配符模式匹配的项和容器。</span><span class="sxs-lookup"><span data-stu-id="af65e-110">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="af65e-111">匹配可以包括文件、文件夹、注册表项或可从 New-psdrive 提供程序访问的任何其他对象。</span><span class="sxs-lookup"><span data-stu-id="af65e-111">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="af65e-112">示例</span><span class="sxs-lookup"><span data-stu-id="af65e-112">EXAMPLES</span></span>

### <span data-ttu-id="af65e-113">示例1：解析主文件夹路径</span><span class="sxs-lookup"><span data-stu-id="af65e-113">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="af65e-114">颚化符 (~) 是当前用户的主文件夹的速记表示法。</span><span class="sxs-lookup"><span data-stu-id="af65e-114">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="af65e-115">此示例显示了如何 `Resolve-Path` 返回完全限定的路径值。</span><span class="sxs-lookup"><span data-stu-id="af65e-115">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="af65e-116">示例2：解析 Windows 文件夹的路径</span><span class="sxs-lookup"><span data-stu-id="af65e-116">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="af65e-117">从 C：驱动器的根目录运行时，此命令将返回 C：驱动器中 Windows 文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="af65e-117">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="af65e-118">示例3：获取 Windows 文件夹中的所有路径</span><span class="sxs-lookup"><span data-stu-id="af65e-118">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="af65e-119">此命令返回 C：\Windows 文件夹中的所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="af65e-119">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="af65e-120">该命令使用管道运算符 (|) 将路径字符串发送到 `Resolve-Path` 。</span><span class="sxs-lookup"><span data-stu-id="af65e-120">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="af65e-121">示例4：解析 UNC 路径</span><span class="sxs-lookup"><span data-stu-id="af65e-121">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="af65e-122">此命令解析通用命名约定 (UNC) 路径并返回路径中的共享部分。</span><span class="sxs-lookup"><span data-stu-id="af65e-122">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="af65e-123">示例5：获取相对路径</span><span class="sxs-lookup"><span data-stu-id="af65e-123">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="af65e-124">此命令返回 C: 驱动器根目录中目录的相对路径。</span><span class="sxs-lookup"><span data-stu-id="af65e-124">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="af65e-125">示例6：解析包含括号的路径</span><span class="sxs-lookup"><span data-stu-id="af65e-125">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="af65e-126">此示例使用 **LiteralPath** 参数解析测试 \[ xml \] 子文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="af65e-126">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="af65e-127">使用 **LiteralPath** 会导致将方括号视为普通字符，而不是正则表达式。</span><span class="sxs-lookup"><span data-stu-id="af65e-127">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="af65e-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="af65e-128">PARAMETERS</span></span>

### <span data-ttu-id="af65e-129">-Credential</span><span class="sxs-lookup"><span data-stu-id="af65e-129">-Credential</span></span>

<span data-ttu-id="af65e-130">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="af65e-130">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="af65e-131">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="af65e-131">The default is the current user.</span></span>

<span data-ttu-id="af65e-132">键入用户名（如 User01 或 Domain01\User01）或传递 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="af65e-132">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="af65e-133">可以使用 cmdlet 创建 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="af65e-133">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="af65e-134">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="af65e-134">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="af65e-135">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="af65e-135">This parameter is not supported by any providers installed with PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="af65e-136">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="af65e-136">-LiteralPath</span></span>

<span data-ttu-id="af65e-137">指定要解析的路径。</span><span class="sxs-lookup"><span data-stu-id="af65e-137">Specifies the path to be resolved.</span></span>
<span data-ttu-id="af65e-138">**LiteralPath** 参数的值完全按类型使用。</span><span class="sxs-lookup"><span data-stu-id="af65e-138">The value of the **LiteralPath** parameter is used exactly as typed.</span></span>
<span data-ttu-id="af65e-139">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="af65e-139">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="af65e-140">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="af65e-140">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="af65e-141">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="af65e-141">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="af65e-142">-Path</span><span class="sxs-lookup"><span data-stu-id="af65e-142">-Path</span></span>

<span data-ttu-id="af65e-143">指定要解析的 PowerShell 路径。</span><span class="sxs-lookup"><span data-stu-id="af65e-143">Specifies the PowerShell path to resolve.</span></span>
<span data-ttu-id="af65e-144">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="af65e-144">This parameter is required.</span></span>
<span data-ttu-id="af65e-145">还可以通过管道将路径字符串传递给 `Resolve-Path` 。</span><span class="sxs-lookup"><span data-stu-id="af65e-145">You can also pipe a path string to `Resolve-Path`.</span></span>
<span data-ttu-id="af65e-146">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="af65e-146">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="af65e-147">-Relative</span><span class="sxs-lookup"><span data-stu-id="af65e-147">-Relative</span></span>

<span data-ttu-id="af65e-148">指示此 cmdlet 返回相对路径。</span><span class="sxs-lookup"><span data-stu-id="af65e-148">Indicates that this cmdlet returns a relative path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="af65e-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="af65e-149">CommonParameters</span></span>

<span data-ttu-id="af65e-150">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="af65e-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="af65e-151">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="af65e-151">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="af65e-152">输入</span><span class="sxs-lookup"><span data-stu-id="af65e-152">INPUTS</span></span>

### <span data-ttu-id="af65e-153">System.String</span><span class="sxs-lookup"><span data-stu-id="af65e-153">System.String</span></span>

<span data-ttu-id="af65e-154">可以通过管道将包含路径的字符串传递给此 cmdlet</span><span class="sxs-lookup"><span data-stu-id="af65e-154">You can pipe a string that contains a path to this cmdlet</span></span>

## <span data-ttu-id="af65e-155">输出</span><span class="sxs-lookup"><span data-stu-id="af65e-155">OUTPUTS</span></span>

### <span data-ttu-id="af65e-156">PathInfo，System.web. String</span><span class="sxs-lookup"><span data-stu-id="af65e-156">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="af65e-157">返回 **PathInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="af65e-157">Returns a **PathInfo** object.</span></span> <span data-ttu-id="af65e-158">如果指定 **相对** 参数，则返回解析的路径的字符串值。</span><span class="sxs-lookup"><span data-stu-id="af65e-158">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="af65e-159">注释</span><span class="sxs-lookup"><span data-stu-id="af65e-159">NOTES</span></span>

<span data-ttu-id="af65e-160">这些 `*-Path` cmdlet 适用于 FileSystem、Registry 和 Certificate 提供程序。</span><span class="sxs-lookup"><span data-stu-id="af65e-160">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="af65e-161">`Resolve-Path` 适用于任何提供程序。</span><span class="sxs-lookup"><span data-stu-id="af65e-161">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="af65e-162">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="af65e-162">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="af65e-163">有关详细信息，请参阅 [about_providers](../microsoft.powershell.core/about/about_providers.md)。</span><span class="sxs-lookup"><span data-stu-id="af65e-163">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="af65e-164">`Resolve-Path` 仅解析现有路径。</span><span class="sxs-lookup"><span data-stu-id="af65e-164">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="af65e-165">它无法用于解析尚不存在的位置。</span><span class="sxs-lookup"><span data-stu-id="af65e-165">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="af65e-166">相关链接</span><span class="sxs-lookup"><span data-stu-id="af65e-166">RELATED LINKS</span></span>

[<span data-ttu-id="af65e-167">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="af65e-167">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="af65e-168">Join-Path</span><span class="sxs-lookup"><span data-stu-id="af65e-168">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="af65e-169">Split-Path</span><span class="sxs-lookup"><span data-stu-id="af65e-169">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="af65e-170">Test-Path</span><span class="sxs-lookup"><span data-stu-id="af65e-170">Test-Path</span></span>](Test-Path.md)

