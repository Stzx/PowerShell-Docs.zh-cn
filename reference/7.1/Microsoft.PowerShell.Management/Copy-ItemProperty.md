---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/copy-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-ItemProperty
ms.openlocfilehash: 22c55ab07b5524e9552808ebaf385b18e22106ef
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198907"
---
# <span data-ttu-id="b6fde-103">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b6fde-103">Copy-ItemProperty</span></span>

## <span data-ttu-id="b6fde-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b6fde-104">SYNOPSIS</span></span>
<span data-ttu-id="b6fde-105">将属性和值从指定的位置复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="b6fde-105">Copies a property and value from a specified location to another location.</span></span>

## <span data-ttu-id="b6fde-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6fde-106">SYNTAX</span></span>

### <span data-ttu-id="b6fde-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="b6fde-107">Path (Default)</span></span>

```
Copy-ItemProperty [-Path] <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b6fde-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b6fde-108">LiteralPath</span></span>

```
Copy-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b6fde-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6fde-109">DESCRIPTION</span></span>

<span data-ttu-id="b6fde-110">`Copy-ItemProperty`Cmdlet 将属性和值从指定的位置复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="b6fde-110">The `Copy-ItemProperty` cmdlet copies a property and value from a specified location to another location.</span></span>
<span data-ttu-id="b6fde-111">例如，可以使用此 cmdlet 将一个或多个注册表条目从一个注册表项复制到另一个注册表项。</span><span class="sxs-lookup"><span data-stu-id="b6fde-111">For instance, you can use this cmdlet to copy one or more registry entries from one registry key to another registry key.</span></span>

## <span data-ttu-id="b6fde-112">示例</span><span class="sxs-lookup"><span data-stu-id="b6fde-112">EXAMPLES</span></span>

### <span data-ttu-id="b6fde-113">示例 1：将属性从一个注册表项复制到另一个注册表项</span><span class="sxs-lookup"><span data-stu-id="b6fde-113">Example 1: Copy a property from a registry key to another registry key</span></span>

<span data-ttu-id="b6fde-114">此命令会将名为 "T.myproperty" 的属性从 "MyApplication" 注册表项复制到 "MyApplicationRev2" 注册表项。</span><span class="sxs-lookup"><span data-stu-id="b6fde-114">This command copies the property named "MyProperty" from the "MyApplication" registry key to the "MyApplicationRev2" registry key.</span></span>

```powershell
Copy-ItemProperty -Path "MyApplication" -Destination "HKLM:\Software\MyApplicationRev2" -Name "MyProperty"
```

## <span data-ttu-id="b6fde-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6fde-115">PARAMETERS</span></span>

### <span data-ttu-id="b6fde-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="b6fde-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b6fde-117">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="b6fde-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b6fde-118">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fde-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b6fde-119">-Destination</span><span class="sxs-lookup"><span data-stu-id="b6fde-119">-Destination</span></span>

<span data-ttu-id="b6fde-120">指定目标位置的路径。</span><span class="sxs-lookup"><span data-stu-id="b6fde-120">Specifies the path to the destination location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6fde-121">-Exclude</span><span class="sxs-lookup"><span data-stu-id="b6fde-121">-Exclude</span></span>

<span data-ttu-id="b6fde-122">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="b6fde-122">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="b6fde-123">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b6fde-123">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b6fde-124">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="b6fde-124">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="b6fde-125">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b6fde-125">Wildcard characters are permitted.</span></span> <span data-ttu-id="b6fde-126">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="b6fde-126">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b6fde-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="b6fde-127">-Filter</span></span>

<span data-ttu-id="b6fde-128">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="b6fde-128">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="b6fde-129">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="b6fde-129">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="b6fde-130">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="b6fde-130">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="b6fde-131">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b6fde-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="b6fde-132">-Force</span><span class="sxs-lookup"><span data-stu-id="b6fde-132">-Force</span></span>

<span data-ttu-id="b6fde-133">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="b6fde-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="b6fde-134">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="b6fde-134">Implementation varies from provider to provider.</span></span>

<span data-ttu-id="b6fde-135">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fde-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="b6fde-136">-Include</span><span class="sxs-lookup"><span data-stu-id="b6fde-136">-Include</span></span>

<span data-ttu-id="b6fde-137">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="b6fde-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="b6fde-138">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b6fde-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="b6fde-139">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="b6fde-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="b6fde-140">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b6fde-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="b6fde-141">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="b6fde-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="b6fde-142">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b6fde-142">-LiteralPath</span></span>

<span data-ttu-id="b6fde-143">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="b6fde-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="b6fde-144">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="b6fde-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="b6fde-145">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="b6fde-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="b6fde-146">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="b6fde-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="b6fde-147">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="b6fde-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="b6fde-148">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fde-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="b6fde-149">-Name</span><span class="sxs-lookup"><span data-stu-id="b6fde-149">-Name</span></span>

<span data-ttu-id="b6fde-150">指定要复制的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="b6fde-150">Specifies the name of the property to be copied.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b6fde-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b6fde-151">-PassThru</span></span>

<span data-ttu-id="b6fde-152">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="b6fde-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="b6fde-153">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="b6fde-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b6fde-154">-Path</span><span class="sxs-lookup"><span data-stu-id="b6fde-154">-Path</span></span>

<span data-ttu-id="b6fde-155">指定要复制的属性的路径（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="b6fde-155">Specifies, as a string array, the path to the property to be copied.</span></span>
<span data-ttu-id="b6fde-156">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b6fde-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b6fde-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b6fde-157">-Confirm</span></span>

<span data-ttu-id="b6fde-158">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="b6fde-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b6fde-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b6fde-159">-WhatIf</span></span>

<span data-ttu-id="b6fde-160">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="b6fde-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b6fde-161">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="b6fde-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b6fde-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b6fde-162">CommonParameters</span></span>

<span data-ttu-id="b6fde-163">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="b6fde-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b6fde-164">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fde-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b6fde-165">输入</span><span class="sxs-lookup"><span data-stu-id="b6fde-165">INPUTS</span></span>

### <span data-ttu-id="b6fde-166">System.String</span><span class="sxs-lookup"><span data-stu-id="b6fde-166">System.String</span></span>

<span data-ttu-id="b6fde-167">可以通过管道将包含路径的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6fde-167">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="b6fde-168">输出</span><span class="sxs-lookup"><span data-stu-id="b6fde-168">OUTPUTS</span></span>

### <span data-ttu-id="b6fde-169">无或 System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="b6fde-169">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="b6fde-170">如果使用 Passthru 参数，则此 cmdlet 生成一个 **PsCustomObject** 对象，该对象表示已复制的项属性。</span><span class="sxs-lookup"><span data-stu-id="b6fde-170">When you use the **Passthru** parameter, this cmdlet generates a **PsCustomObject** representing the copied item property.</span></span> <span data-ttu-id="b6fde-171">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="b6fde-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b6fde-172">注释</span><span class="sxs-lookup"><span data-stu-id="b6fde-172">NOTES</span></span>

<span data-ttu-id="b6fde-173">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="b6fde-173">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b6fde-174">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="b6fde-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b6fde-175">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="b6fde-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="b6fde-176">相关链接</span><span class="sxs-lookup"><span data-stu-id="b6fde-176">RELATED LINKS</span></span>

[<span data-ttu-id="b6fde-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b6fde-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="b6fde-178">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b6fde-178">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="b6fde-179">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b6fde-179">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="b6fde-180">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b6fde-180">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="b6fde-181">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b6fde-181">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="b6fde-182">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b6fde-182">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="b6fde-183">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="b6fde-183">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="b6fde-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b6fde-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

