---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Item
ms.openlocfilehash: 9b7ba6637574f769b1a2c55739c9989736a08c05
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197214"
---
# <span data-ttu-id="6e1e9-103">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-103">Clear-Item</span></span>

## <span data-ttu-id="6e1e9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6e1e9-104">SYNOPSIS</span></span>
<span data-ttu-id="6e1e9-105">清除项的内容，但不删除该项。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-105">Clears the contents of an item, but does not delete the item.</span></span>

## <span data-ttu-id="6e1e9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e1e9-106">SYNTAX</span></span>

### <span data-ttu-id="6e1e9-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="6e1e9-107">Path (Default)</span></span>

```
Clear-Item [-Path] <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6e1e9-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6e1e9-108">LiteralPath</span></span>

```
Clear-Item -LiteralPath <String[]> [-Force] [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6e1e9-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e1e9-109">DESCRIPTION</span></span>

<span data-ttu-id="6e1e9-110">`Clear-Item`Cmdlet 将清除项的内容，但不会删除该项。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-110">The `Clear-Item` cmdlet clears the content of an item, but it does not delete the item.</span></span>
<span data-ttu-id="6e1e9-111">例如，该 `Clear-Item` cmdlet 可以删除变量的值，但不会删除该变量。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-111">For example, the `Clear-Item` cmdlet can delete the value of a variable, but it does not delete the variable.</span></span> <span data-ttu-id="6e1e9-112">用于表示已清除项的值由每个 PowerShell 提供程序定义。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-112">The value that used to represent a cleared item is defined by each PowerShell provider.</span></span>
<span data-ttu-id="6e1e9-113">此 cmdlet 类似于 `Clear-Content` ，但它适用于别名和变量，而不是文件。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-113">This cmdlet is similar to `Clear-Content`, but it works on aliases and variables, instead of files.</span></span>

## <span data-ttu-id="6e1e9-114">示例</span><span class="sxs-lookup"><span data-stu-id="6e1e9-114">EXAMPLES</span></span>

### <span data-ttu-id="6e1e9-115">示例1：清除变量的值</span><span class="sxs-lookup"><span data-stu-id="6e1e9-115">Example 1: Clear the value of a variable</span></span>

<span data-ttu-id="6e1e9-116">此命令清除名为的变量的值 `TestVar1` 。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-116">This command clears the value of the variable named `TestVar1`.</span></span>
<span data-ttu-id="6e1e9-117">变量仍然有效，但其值设置为 `$null` 。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-117">The variable remains and is valid, but its value is set to `$null`.</span></span>
<span data-ttu-id="6e1e9-118">变量名称以为前缀， `Variable:` 以指示 PowerShell 变量提供程序。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-118">The variable name is prefixed with `Variable:` to indicate the PowerShell Variable provider.</span></span>

<span data-ttu-id="6e1e9-119">其他命令显示，若要获得相同的结果，可以切换到 PowerShell `Variable:` 驱动器，然后运行 `Clear-Item` 命令。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-119">The alternate commands show that, to get the same result, you can switch to the PowerShell `Variable:` drive and then run the `Clear-Item` command.</span></span>

```powershell
Clear-Item Variable:TestVar1
```

```
Set-Location Variable:
PS Variable:\> Clear-Item TestVar1
```

### <span data-ttu-id="6e1e9-120">示例2：清除所有注册表项</span><span class="sxs-lookup"><span data-stu-id="6e1e9-120">Example 2: Clear all registry entries</span></span>

<span data-ttu-id="6e1e9-121">此命令清除 "MyKey" 子项中的所有注册表项，但仅在提示你确认你的意图后才会清除。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-121">This command clears all registry entries in the "MyKey" subkey, but only after prompting you to confirm your intent.</span></span>
<span data-ttu-id="6e1e9-122">它不会删除 "MyKey" 子项，也不会影响任何其他注册表项或条目。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-122">It does not delete the "MyKey" subkey or affect any other registry keys or entries.</span></span>
<span data-ttu-id="6e1e9-123">可以使用 **Include** 参数和 **Exclude** 参数来标识特定的注册表项，但不能使用这两个参数来标识注册表条目。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-123">You can use the **Include** and **Exclude** parameters to identify particular registry keys, but you cannot use them to identify registry entries.</span></span>

- <span data-ttu-id="6e1e9-124">若要删除特定的注册表条目，请使用 `Remove-ItemProperty` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-124">To delete particular registry entries, use the `Remove-ItemProperty` cmdlet.</span></span>
- <span data-ttu-id="6e1e9-125">若要删除注册表条目的值，请使用 `Clear-ItemProperty cmdlet` 。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-125">To delete the value of a registry entry, use the `Clear-ItemProperty cmdlet`.</span></span>

```powershell
Clear-Item HKLM:\Software\MyCompany\MyKey -Confirm
```

## <span data-ttu-id="6e1e9-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e1e9-126">PARAMETERS</span></span>

### <span data-ttu-id="6e1e9-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="6e1e9-127">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="6e1e9-128">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-128">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="6e1e9-129">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-129">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e1e9-130">-Exclude</span><span class="sxs-lookup"><span data-stu-id="6e1e9-130">-Exclude</span></span>

<span data-ttu-id="6e1e9-131">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-131">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="6e1e9-132">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-132">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6e1e9-133">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-133">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="6e1e9-134">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-134">Wildcard characters are permitted.</span></span> <span data-ttu-id="6e1e9-135">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-135">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6e1e9-136">-Filter</span><span class="sxs-lookup"><span data-stu-id="6e1e9-136">-Filter</span></span>

<span data-ttu-id="6e1e9-137">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-137">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="6e1e9-138">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-138">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="6e1e9-139">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-139">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="6e1e9-140">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-140">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6e1e9-141">-Force</span><span class="sxs-lookup"><span data-stu-id="6e1e9-141">-Force</span></span>

<span data-ttu-id="6e1e9-142">指示该 cmdlet 清除不能更改的项（如只读别名）。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-142">Indicates that the cmdlet clears items that cannot otherwise be changed, such as read- only aliases.</span></span>
<span data-ttu-id="6e1e9-143">此 cmdlet 不能清除常量。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-143">The cmdlet cannot clear constants.</span></span>
<span data-ttu-id="6e1e9-144">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="6e1e9-145">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="6e1e9-146">即使使用了 **Force** 参数，该 cmdlet 也无法覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-146">The cmdlet cannot override security restrictions, even when the **Force** parameter is used.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e1e9-147">-Include</span><span class="sxs-lookup"><span data-stu-id="6e1e9-147">-Include</span></span>

<span data-ttu-id="6e1e9-148">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="6e1e9-149">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-149">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="6e1e9-150">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-150">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="6e1e9-151">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-151">Wildcard characters are permitted.</span></span> <span data-ttu-id="6e1e9-152">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-152">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6e1e9-153">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6e1e9-153">-LiteralPath</span></span>

<span data-ttu-id="6e1e9-154">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-154">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6e1e9-155">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-155">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="6e1e9-156">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-156">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6e1e9-157">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-157">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="6e1e9-158">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-158">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="6e1e9-159">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-159">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="6e1e9-160">-Path</span><span class="sxs-lookup"><span data-stu-id="6e1e9-160">-Path</span></span>

<span data-ttu-id="6e1e9-161">指定要清除的项的路径。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-161">Specifies the path to the items being cleared.</span></span>
<span data-ttu-id="6e1e9-162">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-162">Wildcard characters are permitted.</span></span>
<span data-ttu-id="6e1e9-163">此参数是必需的，但参数名称 **路径** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-163">This parameter is required, but the parameter name **Path** is optional.</span></span>

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

### <span data-ttu-id="6e1e9-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6e1e9-164">-Confirm</span></span>

<span data-ttu-id="6e1e9-165">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6e1e9-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6e1e9-166">-WhatIf</span></span>

<span data-ttu-id="6e1e9-167">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6e1e9-168">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6e1e9-169">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6e1e9-169">CommonParameters</span></span>

<span data-ttu-id="6e1e9-170">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="6e1e9-171">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="6e1e9-172">输入</span><span class="sxs-lookup"><span data-stu-id="6e1e9-172">INPUTS</span></span>

### <span data-ttu-id="6e1e9-173">System.String</span><span class="sxs-lookup"><span data-stu-id="6e1e9-173">System.String</span></span>

<span data-ttu-id="6e1e9-174">可以通过管道将路径字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-174">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="6e1e9-175">输出</span><span class="sxs-lookup"><span data-stu-id="6e1e9-175">OUTPUTS</span></span>

### <span data-ttu-id="6e1e9-176">无</span><span class="sxs-lookup"><span data-stu-id="6e1e9-176">None</span></span>

<span data-ttu-id="6e1e9-177">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-177">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6e1e9-178">注释</span><span class="sxs-lookup"><span data-stu-id="6e1e9-178">NOTES</span></span>

- <span data-ttu-id="6e1e9-179">`Clear-Item`只有几个 PowerShell 提供程序（包括 **别名** 、 **环境** 、 **函数** 、 **注册表** 和 **变量** 提供程序）支持 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-179">The `Clear-Item` cmdlet is supported only by several PowerShell providers, including the **Alias** , **Environment** , **Function** , **Registry** , and **Variable** providers.</span></span> <span data-ttu-id="6e1e9-180">因此，你可以使用 `Clear-Item` 删除提供程序命名空间中的项的内容。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-180">As such, you can use `Clear-Item` to delete the content of items in the provider namespaces.</span></span> <span data-ttu-id="6e1e9-181">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-181">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="6e1e9-182">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-182">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
- <span data-ttu-id="6e1e9-183">不能使用 `Clear-Item` 删除文件的内容，因为 PowerShell FileSystem 提供程序不支持此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-183">You cannot use `Clear-Item` to delete the contents of a file, because the PowerShell FileSystem provider does not support this cmdlet.</span></span> <span data-ttu-id="6e1e9-184">若要清除文件，请使用 `Clear-Content` 。</span><span class="sxs-lookup"><span data-stu-id="6e1e9-184">To clear files, use the `Clear-Content`.</span></span>

## <span data-ttu-id="6e1e9-185">相关链接</span><span class="sxs-lookup"><span data-stu-id="6e1e9-185">RELATED LINKS</span></span>

[<span data-ttu-id="6e1e9-186">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-186">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="6e1e9-187">Get-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-187">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="6e1e9-188">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-188">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="6e1e9-189">Move-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-189">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="6e1e9-190">New-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-190">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="6e1e9-191">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-191">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="6e1e9-192">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-192">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="6e1e9-193">Set-Item</span><span class="sxs-lookup"><span data-stu-id="6e1e9-193">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="6e1e9-194">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6e1e9-194">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
