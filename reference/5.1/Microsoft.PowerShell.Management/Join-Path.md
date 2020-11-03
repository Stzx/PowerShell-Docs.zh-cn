---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: bcba432fb52b327695b61a4475d4a93903a688a5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198097"
---
# <span data-ttu-id="27f72-103">Join-Path</span><span class="sxs-lookup"><span data-stu-id="27f72-103">Join-Path</span></span>

## <span data-ttu-id="27f72-104">摘要</span><span class="sxs-lookup"><span data-stu-id="27f72-104">SYNOPSIS</span></span>
<span data-ttu-id="27f72-105">将路径和子路径合并到单个路径中。</span><span class="sxs-lookup"><span data-stu-id="27f72-105">Combines a path and a child path into a single path.</span></span>

## <span data-ttu-id="27f72-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="27f72-106">SYNTAX</span></span>

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="27f72-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="27f72-107">DESCRIPTION</span></span>

<span data-ttu-id="27f72-108">`Join-Path`Cmdlet 将路径和子路径合并到单个路径中。</span><span class="sxs-lookup"><span data-stu-id="27f72-108">The `Join-Path` cmdlet combines a path and child-path into a single path.</span></span>
<span data-ttu-id="27f72-109">提供程序将提供路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="27f72-109">The provider supplies the path delimiters.</span></span>

## <span data-ttu-id="27f72-110">示例</span><span class="sxs-lookup"><span data-stu-id="27f72-110">EXAMPLES</span></span>

### <span data-ttu-id="27f72-111">示例1：将路径与子路径组合</span><span class="sxs-lookup"><span data-stu-id="27f72-111">Example 1: Combine a path with a child path</span></span>

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

<span data-ttu-id="27f72-112">此命令使用 `Join-Path` 将路径与 childpath 进行组合。</span><span class="sxs-lookup"><span data-stu-id="27f72-112">This command uses `Join-Path` to combine a path with a childpath.</span></span>

<span data-ttu-id="27f72-113">由于命令是从 `FileSystem` 提供程序执行的，因此提供了 `\` 分隔符来联接路径。</span><span class="sxs-lookup"><span data-stu-id="27f72-113">Since the command is executed from the `FileSystem` provider, it provides the `\` delimiter to join the paths.</span></span>

### <span data-ttu-id="27f72-114">示例2：合并已包含目录分隔符的路径</span><span class="sxs-lookup"><span data-stu-id="27f72-114">Example 2: Combine paths that already contain directory separators</span></span>

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

<span data-ttu-id="27f72-115">现有的目录分隔符 `\` 和已处理，因此与之间只有一个分隔符 `Path``ChildPath`</span><span class="sxs-lookup"><span data-stu-id="27f72-115">Existing directory separators `\` and handled so there is only one separator between `Path` and `ChildPath`</span></span>

### <span data-ttu-id="27f72-116">示例3：通过将路径与子路径联接来显示文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="27f72-116">Example 3: Display files and folders by joining a path with a child path</span></span>

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

<span data-ttu-id="27f72-117">此命令显示通过联接 C:\Win \* 路径和系统子路径而引用的文件和文件夹 \* 。</span><span class="sxs-lookup"><span data-stu-id="27f72-117">This command displays the files and folders that are referenced by joining the C:\Win\* path and the System\* child path.</span></span>
<span data-ttu-id="27f72-118">它显示与相同的文件和文件夹 `Get-ChildItem` ，但它显示每个项目的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="27f72-118">It displays the same files and folders as `Get-ChildItem`, but it displays the fully qualified path to each item.</span></span>
<span data-ttu-id="27f72-119">在此命令中， `Path` 省略了和 `ChildPath` 可选的参数名称。</span><span class="sxs-lookup"><span data-stu-id="27f72-119">In this command, the `Path` and `ChildPath` optional parameter names are omitted.</span></span>

### <span data-ttu-id="27f72-120">示例4：将 Join-Path 与 PowerShell 注册表提供程序一起使用</span><span class="sxs-lookup"><span data-stu-id="27f72-120">Example 4: Use Join-Path with the PowerShell registry provider</span></span>

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

<span data-ttu-id="27f72-121">此命令显示注册表子项中包含的注册表项 `HKLM\System` `ControlSet` 。</span><span class="sxs-lookup"><span data-stu-id="27f72-121">This command displays the registry keys in the `HKLM\System` registry subkey that include `ControlSet`.</span></span>

<span data-ttu-id="27f72-122">`Resolve`参数尝试解析联接的路径，包括当前提供程序路径中的通配符`HKLM:\`</span><span class="sxs-lookup"><span data-stu-id="27f72-122">The `Resolve` parameter, attempts to resolve the joined path, including wildcards from the current provider path `HKLM:\`</span></span>

### <span data-ttu-id="27f72-123">示例5：将多个路径根与一个子路径组合在一起</span><span class="sxs-lookup"><span data-stu-id="27f72-123">Example 5: Combine multiple path roots with a child path</span></span>

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

<span data-ttu-id="27f72-124">此命令使用 `Join-Path` 将多个路径根与一个子路径组合在一起。</span><span class="sxs-lookup"><span data-stu-id="27f72-124">This command uses `Join-Path` to combine multiple path roots with a child path.</span></span>

> [!NOTE]
> <span data-ttu-id="27f72-125">指定的驱动器 `Path` 必须存在，否则该条目的联接将失败。</span><span class="sxs-lookup"><span data-stu-id="27f72-125">The Drives specified by `Path` must exist or the join of that entry will fail.</span></span>

### <span data-ttu-id="27f72-126">示例6：合并带有子路径的文件系统驱动器的根</span><span class="sxs-lookup"><span data-stu-id="27f72-126">Example 6: Combine the roots of a file system drive with a child path</span></span>

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

<span data-ttu-id="27f72-127">此命令将控制台中每个 PowerShell 文件系统驱动器的根与 Subdir 子路径组合在一起。</span><span class="sxs-lookup"><span data-stu-id="27f72-127">This command combines the roots of each PowerShell file system drive in the console with the Subdir child path.</span></span>

<span data-ttu-id="27f72-128">该命令使用 `Get-PSDrive` cmdlet 来获取 FileSystem 提供程序支持的 PowerShell 驱动器。</span><span class="sxs-lookup"><span data-stu-id="27f72-128">The command uses the `Get-PSDrive` cmdlet to get the PowerShell drives supported by the FileSystem provider.</span></span>
<span data-ttu-id="27f72-129">`ForEach-Object`语句仅选择对象的根属性 `PSDriveInfo` ，并将其与指定的子路径组合在一起。</span><span class="sxs-lookup"><span data-stu-id="27f72-129">The `ForEach-Object` statement selects only the Root property of the `PSDriveInfo` objects and combines it with the specified child path.</span></span>

<span data-ttu-id="27f72-130">输出显示计算机上的 PowerShell 驱动器包含映射到 C:\Program Files 目录的驱动器。</span><span class="sxs-lookup"><span data-stu-id="27f72-130">The output shows that the PowerShell drives on the computer included a drive mapped to the C:\Program Files directory.</span></span>

## <span data-ttu-id="27f72-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="27f72-131">PARAMETERS</span></span>

### <span data-ttu-id="27f72-132">-ChildPath</span><span class="sxs-lookup"><span data-stu-id="27f72-132">-ChildPath</span></span>

<span data-ttu-id="27f72-133">指定要追加到参数值的元素 `Path` 。</span><span class="sxs-lookup"><span data-stu-id="27f72-133">Specifies the elements to append to the value of the `Path` parameter.</span></span>
<span data-ttu-id="27f72-134">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="27f72-134">Wildcards are permitted.</span></span>
<span data-ttu-id="27f72-135">`ChildPath`参数是必需的，但参数名称 ( "ChildPath" ) 是可选的。</span><span class="sxs-lookup"><span data-stu-id="27f72-135">The `ChildPath` parameter is required, although the parameter name ("ChildPath") is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="27f72-136">-Credential</span><span class="sxs-lookup"><span data-stu-id="27f72-136">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="27f72-137">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="27f72-137">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="27f72-138">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="27f72-138">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="27f72-139">-Path</span><span class="sxs-lookup"><span data-stu-id="27f72-139">-Path</span></span>

<span data-ttu-id="27f72-140">指定子路径追加到的主路径。</span><span class="sxs-lookup"><span data-stu-id="27f72-140">Specifies the main path (or paths) to which the child-path is appended.</span></span>
<span data-ttu-id="27f72-141">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="27f72-141">Wildcards are permitted.</span></span>

<span data-ttu-id="27f72-142">的值 `Path` 确定哪些提供程序联接路径并添加路径分隔符。</span><span class="sxs-lookup"><span data-stu-id="27f72-142">The value of `Path` determines which provider joins the paths and adds the path delimiters.</span></span>
<span data-ttu-id="27f72-143">`Path`尽管参数名称 ( "Path" ) 是可选的，但参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="27f72-143">The `Path` parameter is required, although the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="27f72-144">-Resolve</span><span class="sxs-lookup"><span data-stu-id="27f72-144">-Resolve</span></span>

<span data-ttu-id="27f72-145">指示此 cmdlet 应尝试解析来自当前提供程序的联接路径。</span><span class="sxs-lookup"><span data-stu-id="27f72-145">Indicates that this cmdlet should attempt to resolve the joined path from the current provider.</span></span>

- <span data-ttu-id="27f72-146">如果使用通配符，则该 cmdlet 将返回与联接路径匹配的所有路径。</span><span class="sxs-lookup"><span data-stu-id="27f72-146">If wildcards are used, the cmdlet returns all paths that match the joined path.</span></span>
- <span data-ttu-id="27f72-147">如果 **不使用通配符，** 则如果路径不存在，则该 cmdlet 将出错。</span><span class="sxs-lookup"><span data-stu-id="27f72-147">If **no** wildcards are used, the cmdlet will error if the path does not exist.</span></span>

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

### <span data-ttu-id="27f72-148">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="27f72-148">-UseTransaction</span></span>

<span data-ttu-id="27f72-149">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="27f72-149">Includes the command in the active transaction.</span></span>
<span data-ttu-id="27f72-150">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="27f72-150">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="27f72-151">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="27f72-151">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="27f72-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="27f72-152">CommonParameters</span></span>

<span data-ttu-id="27f72-153">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="27f72-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="27f72-154">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="27f72-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="27f72-155">输入</span><span class="sxs-lookup"><span data-stu-id="27f72-155">INPUTS</span></span>

### <span data-ttu-id="27f72-156">System.String</span><span class="sxs-lookup"><span data-stu-id="27f72-156">System.String</span></span>

<span data-ttu-id="27f72-157">可以通过管道将包含路径的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27f72-157">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="27f72-158">输出</span><span class="sxs-lookup"><span data-stu-id="27f72-158">OUTPUTS</span></span>

### <span data-ttu-id="27f72-159">System.String</span><span class="sxs-lookup"><span data-stu-id="27f72-159">System.String</span></span>

<span data-ttu-id="27f72-160">此 cmdlet 将返回包含生成的路径的字符串。</span><span class="sxs-lookup"><span data-stu-id="27f72-160">This cmdlet returns a string that contains the resulting path.</span></span>

## <span data-ttu-id="27f72-161">注释</span><span class="sxs-lookup"><span data-stu-id="27f72-161">NOTES</span></span>

<span data-ttu-id="27f72-162">在路径 cmdlet (包含 Path 名词的 cmdlet) 操作路径名，并以所有 PowerShell 提供程序可解释的简明格式返回名称。</span><span class="sxs-lookup"><span data-stu-id="27f72-162">The cmdlets that contain the Path noun (the Path cmdlets) manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="27f72-163">这些 cmdlet 用于需要在其中以特定格式显示全部或部分路径名称的程序或脚本中。</span><span class="sxs-lookup"><span data-stu-id="27f72-163">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="27f72-164">你可以像使用 Dirname、Normpath、Realpath、Join 或其他路径操作程序那样使用这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27f72-164">Use them like you would use Dirname, Normpath, Realpath, Join, or other path manipulators.</span></span>

<span data-ttu-id="27f72-165">可以将路径 cmdlet 用于多个提供程序，包括 `FileSystem` 、 `Registry` 和 `Certificate` 提供程序。</span><span class="sxs-lookup"><span data-stu-id="27f72-165">You can use the path cmdlets with several providers, including the `FileSystem`, `Registry`, and `Certificate` providers.</span></span>

<span data-ttu-id="27f72-166">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="27f72-166">This cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="27f72-167">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="27f72-167">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="27f72-168">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="27f72-168">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="27f72-169">相关链接</span><span class="sxs-lookup"><span data-stu-id="27f72-169">RELATED LINKS</span></span>

[<span data-ttu-id="27f72-170">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="27f72-170">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="27f72-171">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="27f72-171">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="27f72-172">Split-Path</span><span class="sxs-lookup"><span data-stu-id="27f72-172">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="27f72-173">Test-Path</span><span class="sxs-lookup"><span data-stu-id="27f72-173">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="27f72-174">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="27f72-174">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="27f72-175">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="27f72-175">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="27f72-176">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="27f72-176">Get-PSDrive</span></span>](Get-PSDrive.md)
