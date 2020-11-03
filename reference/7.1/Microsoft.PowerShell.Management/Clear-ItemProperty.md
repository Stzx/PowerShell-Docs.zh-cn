---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/clear-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-ItemProperty
ms.openlocfilehash: 8c992be609a37590ba6c8a513719cc81d0bfc9ca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198831"
---
# <span data-ttu-id="e9ba4-103">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e9ba4-103">Clear-ItemProperty</span></span>

## <span data-ttu-id="e9ba4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e9ba4-104">SYNOPSIS</span></span>
<span data-ttu-id="e9ba4-105">清除属性的值，但不删除该属性。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-105">Clears the value of a property but does not delete the property.</span></span>

## <span data-ttu-id="e9ba4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e9ba4-106">SYNTAX</span></span>

### <span data-ttu-id="e9ba4-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="e9ba4-107">Path (Default)</span></span>

```
Clear-ItemProperty [-Path] <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e9ba4-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e9ba4-108">LiteralPath</span></span>

```
Clear-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e9ba4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e9ba4-109">DESCRIPTION</span></span>

<span data-ttu-id="e9ba4-110">`Clear-ItemProperty`Cmdlet 将清除属性的值，但不会删除属性。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-110">The `Clear-ItemProperty` cmdlet clears the value of a property, but it does not delete the property.</span></span>
<span data-ttu-id="e9ba4-111">可以使用此 cmdlet 从注册表值中删除数据。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-111">You can use this cmdlet to delete the data from a registry value.</span></span>

## <span data-ttu-id="e9ba4-112">示例</span><span class="sxs-lookup"><span data-stu-id="e9ba4-112">EXAMPLES</span></span>

### <span data-ttu-id="e9ba4-113">示例1：清除注册表项的值</span><span class="sxs-lookup"><span data-stu-id="e9ba4-113">Example 1: Clear the value of registry key</span></span>

<span data-ttu-id="e9ba4-114">此命令清除的 "MyApp" 子项中的 "Options" 注册表值中的数据 `HKEY_LOCAL_MACHINE\Software\MyCompany` 。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-114">This command clears the data in the "Options" registry value in the "MyApp" subkey of `HKEY_LOCAL_MACHINE\Software\MyCompany`.</span></span>

```powershell
Clear-ItemProperty -Path "HKLM:\Software\MyCompany\MyApp" -Name "Options"
```

## <span data-ttu-id="e9ba4-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e9ba4-115">PARAMETERS</span></span>

### <span data-ttu-id="e9ba4-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="e9ba4-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="e9ba4-117">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="e9ba4-118">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="e9ba4-119">-Exclude</span><span class="sxs-lookup"><span data-stu-id="e9ba4-119">-Exclude</span></span>

<span data-ttu-id="e9ba4-120">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-120">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="e9ba4-121">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-121">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e9ba4-122">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-122">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="e9ba4-123">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-123">Wildcard characters are permitted.</span></span> <span data-ttu-id="e9ba4-124">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-124">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e9ba4-125">-Filter</span><span class="sxs-lookup"><span data-stu-id="e9ba4-125">-Filter</span></span>

<span data-ttu-id="e9ba4-126">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-126">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="e9ba4-127">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-127">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="e9ba4-128">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-128">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="e9ba4-129">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-129">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="e9ba4-130">-Force</span><span class="sxs-lookup"><span data-stu-id="e9ba4-130">-Force</span></span>

<span data-ttu-id="e9ba4-131">指示此 cmdlet 将从用户无法访问的项中删除属性。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-131">Indicates that this cmdlet deletes properties from items that cannot otherwise be accessed by the user.</span></span> <span data-ttu-id="e9ba4-132">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-132">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="e9ba4-133">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-133">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="e9ba4-134">-Include</span><span class="sxs-lookup"><span data-stu-id="e9ba4-134">-Include</span></span>

<span data-ttu-id="e9ba4-135">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-135">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="e9ba4-136">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-136">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="e9ba4-137">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-137">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="e9ba4-138">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-138">Wildcard characters are permitted.</span></span> <span data-ttu-id="e9ba4-139">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-139">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="e9ba4-140">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e9ba4-140">-LiteralPath</span></span>

<span data-ttu-id="e9ba4-141">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-141">Specifies a path to one or more locations.</span></span> <span data-ttu-id="e9ba4-142">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-142">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="e9ba4-143">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-143">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="e9ba4-144">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-144">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e9ba4-145">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-145">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="e9ba4-146">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-146">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="e9ba4-147">-Name</span><span class="sxs-lookup"><span data-stu-id="e9ba4-147">-Name</span></span>

<span data-ttu-id="e9ba4-148">指定要清除的属性的名称，例如，注册表值的名称。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-148">Specifies the name of the property to be cleared, such as the name of a registry value.</span></span>
<span data-ttu-id="e9ba4-149">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-149">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e9ba4-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e9ba4-150">-PassThru</span></span>

<span data-ttu-id="e9ba4-151">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-151">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="e9ba4-152">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-152">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e9ba4-153">-Path</span><span class="sxs-lookup"><span data-stu-id="e9ba4-153">-Path</span></span>

<span data-ttu-id="e9ba4-154">指定要清除的属性的路径。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-154">Specifies the path to the property being cleared.</span></span>
<span data-ttu-id="e9ba4-155">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-155">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e9ba4-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e9ba4-156">-Confirm</span></span>

<span data-ttu-id="e9ba4-157">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e9ba4-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e9ba4-158">-WhatIf</span></span>

<span data-ttu-id="e9ba4-159">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-159">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e9ba4-160">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e9ba4-161">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e9ba4-161">CommonParameters</span></span>

<span data-ttu-id="e9ba4-162">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-162">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="e9ba4-163">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-163">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e9ba4-164">输入</span><span class="sxs-lookup"><span data-stu-id="e9ba4-164">INPUTS</span></span>

### <span data-ttu-id="e9ba4-165">System.String</span><span class="sxs-lookup"><span data-stu-id="e9ba4-165">System.String</span></span>

<span data-ttu-id="e9ba4-166">可以通过管道将路径字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-166">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="e9ba4-167">输出</span><span class="sxs-lookup"><span data-stu-id="e9ba4-167">OUTPUTS</span></span>

### <span data-ttu-id="e9ba4-168">无或 System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="e9ba4-168">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="e9ba4-169">当使用 **PassThru** 参数时，将 `Clear-ItemProperty` 生成一个 **PSCustomObject** 对象，该对象表示已清除的项属性。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-169">When you use the **PassThru** parameter, `Clear-ItemProperty` generates a **PSCustomObject** object that represents the cleared item property.</span></span> <span data-ttu-id="e9ba4-170">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-170">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e9ba4-171">注释</span><span class="sxs-lookup"><span data-stu-id="e9ba4-171">NOTES</span></span>

- <span data-ttu-id="e9ba4-172">您可以使用 `Clear-ItemProperty` 删除注册表值中的数据，而不删除该值。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-172">You can use `Clear-ItemProperty` to delete the data in registry values without deleting the value.</span></span>
  <span data-ttu-id="e9ba4-173">如果该值的数据类型为 二进制 或 DWORD，则清除数据会将该值设置为零。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-173">If the data type of the value is Binary or DWORD, clearing the data sets the value to zero.</span></span>
  <span data-ttu-id="e9ba4-174">否则，该值为空。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-174">Otherwise, the value is empty.</span></span>
- <span data-ttu-id="e9ba4-175">`Clear-ItemProperty`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-175">The `Clear-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="e9ba4-176">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="e9ba4-177">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="e9ba4-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e9ba4-178">相关链接</span><span class="sxs-lookup"><span data-stu-id="e9ba4-178">RELATED LINKS</span></span>

[<span data-ttu-id="e9ba4-179">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e9ba4-179">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="e9ba4-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e9ba4-180">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="e9ba4-181">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e9ba4-181">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="e9ba4-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e9ba4-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="e9ba4-183">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="e9ba4-183">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="e9ba4-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e9ba4-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

