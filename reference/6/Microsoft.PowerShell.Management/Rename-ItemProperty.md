---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-ItemProperty
ms.openlocfilehash: 3768a24438b0cc33711ebe61dc63c57c27bac976
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197508"
---
# <span data-ttu-id="50f5b-103">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-103">Rename-ItemProperty</span></span>

## <span data-ttu-id="50f5b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="50f5b-104">SYNOPSIS</span></span>
<span data-ttu-id="50f5b-105">重命名项的属性。</span><span class="sxs-lookup"><span data-stu-id="50f5b-105">Renames a property of an item.</span></span>

## <span data-ttu-id="50f5b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="50f5b-106">SYNTAX</span></span>

### <span data-ttu-id="50f5b-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="50f5b-107">Path (Default)</span></span>

```
Rename-ItemProperty [-Path] <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50f5b-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="50f5b-108">LiteralPath</span></span>

```
Rename-ItemProperty -LiteralPath <String> [-Name] <String> [-NewName] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="50f5b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="50f5b-109">DESCRIPTION</span></span>

<span data-ttu-id="50f5b-110">`Rename-ItemProperty`Cmdlet 更改指定项属性的名称。</span><span class="sxs-lookup"><span data-stu-id="50f5b-110">The `Rename-ItemProperty` cmdlet changes the name of a specified item property.</span></span>
<span data-ttu-id="50f5b-111">属性的值未更改。</span><span class="sxs-lookup"><span data-stu-id="50f5b-111">The value of the property is not changed.</span></span>
<span data-ttu-id="50f5b-112">例如，你可以使用 `Rename-ItemProperty` 来更改注册表项的名称。</span><span class="sxs-lookup"><span data-stu-id="50f5b-112">For example, you can use `Rename-ItemProperty` to change the name of a registry entry.</span></span>

## <span data-ttu-id="50f5b-113">示例</span><span class="sxs-lookup"><span data-stu-id="50f5b-113">EXAMPLES</span></span>

### <span data-ttu-id="50f5b-114">示例1：重命名注册表项</span><span class="sxs-lookup"><span data-stu-id="50f5b-114">Example 1: Rename a registry entry</span></span>

<span data-ttu-id="50f5b-115">此命令将密钥中包含的 config 注册表条目重命名 `HKEY_LOCAL_MACHINE\Software\SmpApplication` 为 "oldconfig"。</span><span class="sxs-lookup"><span data-stu-id="50f5b-115">This command renames the config registry entry that is contained in the `HKEY_LOCAL_MACHINE\Software\SmpApplication` key to "oldconfig".</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\Software\SmpApplication -Name config -NewName oldconfig
```

## <span data-ttu-id="50f5b-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="50f5b-116">PARAMETERS</span></span>

### <span data-ttu-id="50f5b-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="50f5b-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="50f5b-118">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="50f5b-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="50f5b-119">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="50f5b-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="50f5b-120">-Exclude</span><span class="sxs-lookup"><span data-stu-id="50f5b-120">-Exclude</span></span>

<span data-ttu-id="50f5b-121">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="50f5b-121">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="50f5b-122">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="50f5b-122">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="50f5b-123">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="50f5b-123">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="50f5b-124">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="50f5b-124">Wildcard characters are permitted.</span></span> <span data-ttu-id="50f5b-125">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="50f5b-125">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="50f5b-126">-Filter</span><span class="sxs-lookup"><span data-stu-id="50f5b-126">-Filter</span></span>

<span data-ttu-id="50f5b-127">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="50f5b-127">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="50f5b-128">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="50f5b-128">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="50f5b-129">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="50f5b-129">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="50f5b-130">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="50f5b-130">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="50f5b-131">-Force</span><span class="sxs-lookup"><span data-stu-id="50f5b-131">-Force</span></span>

<span data-ttu-id="50f5b-132">强制 cmdlet 重命名用户无法访问的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="50f5b-132">Forces the cmdlet to rename a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="50f5b-133">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="50f5b-133">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="50f5b-134">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="50f5b-134">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="50f5b-135">-Include</span><span class="sxs-lookup"><span data-stu-id="50f5b-135">-Include</span></span>

<span data-ttu-id="50f5b-136">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="50f5b-136">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="50f5b-137">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="50f5b-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="50f5b-138">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="50f5b-138">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="50f5b-139">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="50f5b-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="50f5b-140">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="50f5b-140">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="50f5b-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="50f5b-141">-LiteralPath</span></span>

<span data-ttu-id="50f5b-142">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="50f5b-142">Specifies a path to one or more locations.</span></span> <span data-ttu-id="50f5b-143">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="50f5b-143">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="50f5b-144">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="50f5b-144">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="50f5b-145">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="50f5b-145">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="50f5b-146">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="50f5b-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="50f5b-147">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="50f5b-147">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50f5b-148">-Name</span><span class="sxs-lookup"><span data-stu-id="50f5b-148">-Name</span></span>

<span data-ttu-id="50f5b-149">指定要重命名的属性的当前名称。</span><span class="sxs-lookup"><span data-stu-id="50f5b-149">Specifies the current name of the property to rename.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50f5b-150">-NewName</span><span class="sxs-lookup"><span data-stu-id="50f5b-150">-NewName</span></span>

<span data-ttu-id="50f5b-151">指定属性的新名称。</span><span class="sxs-lookup"><span data-stu-id="50f5b-151">Specifies the new name for the property.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50f5b-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="50f5b-152">-PassThru</span></span>

<span data-ttu-id="50f5b-153">返回一个表示项属性的对象。</span><span class="sxs-lookup"><span data-stu-id="50f5b-153">Returns an object that represents the item property.</span></span>
<span data-ttu-id="50f5b-154">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="50f5b-154">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="50f5b-155">-Path</span><span class="sxs-lookup"><span data-stu-id="50f5b-155">-Path</span></span>

<span data-ttu-id="50f5b-156">指定要重命名的项的路径。</span><span class="sxs-lookup"><span data-stu-id="50f5b-156">Specifies the path of the item to rename.</span></span>
<span data-ttu-id="50f5b-157">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="50f5b-157">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="50f5b-158">-Confirm</span><span class="sxs-lookup"><span data-stu-id="50f5b-158">-Confirm</span></span>

<span data-ttu-id="50f5b-159">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="50f5b-159">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="50f5b-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="50f5b-160">-WhatIf</span></span>

<span data-ttu-id="50f5b-161">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="50f5b-161">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="50f5b-162">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="50f5b-162">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="50f5b-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="50f5b-163">CommonParameters</span></span>

<span data-ttu-id="50f5b-164">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="50f5b-164">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="50f5b-165">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="50f5b-165">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="50f5b-166">输入</span><span class="sxs-lookup"><span data-stu-id="50f5b-166">INPUTS</span></span>

### <span data-ttu-id="50f5b-167">System.String</span><span class="sxs-lookup"><span data-stu-id="50f5b-167">System.String</span></span>

<span data-ttu-id="50f5b-168">可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50f5b-168">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="50f5b-169">输出</span><span class="sxs-lookup"><span data-stu-id="50f5b-169">OUTPUTS</span></span>

### <span data-ttu-id="50f5b-170">PSCustomObject （无）</span><span class="sxs-lookup"><span data-stu-id="50f5b-170">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="50f5b-171">如果指定 **PassThru** 参数，则此 cmdlet 将生成一个表示已重命名的 item 属性的 **PSCustomObject** 。</span><span class="sxs-lookup"><span data-stu-id="50f5b-171">This cmdlet generates a **PSCustomObject** that represents the renamed item property, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="50f5b-172">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="50f5b-172">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="50f5b-173">注释</span><span class="sxs-lookup"><span data-stu-id="50f5b-173">NOTES</span></span>

<span data-ttu-id="50f5b-174">`Remove-ItemProperty` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="50f5b-174">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="50f5b-175">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="50f5b-175">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="50f5b-176">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="50f5b-176">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="50f5b-177">相关链接</span><span class="sxs-lookup"><span data-stu-id="50f5b-177">RELATED LINKS</span></span>

[<span data-ttu-id="50f5b-178">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-178">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="50f5b-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="50f5b-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="50f5b-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="50f5b-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="50f5b-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="50f5b-184">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="50f5b-184">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="50f5b-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="50f5b-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="50f5b-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="50f5b-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
