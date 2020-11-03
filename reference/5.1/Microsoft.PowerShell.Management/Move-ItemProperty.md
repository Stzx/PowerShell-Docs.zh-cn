---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 4cf883964e1ff86487bf5abca8789af62b274c8a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198086"
---
# <span data-ttu-id="59db8-103">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-103">Move-ItemProperty</span></span>

## <span data-ttu-id="59db8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="59db8-104">Synopsis</span></span>
<span data-ttu-id="59db8-105">将属性从一个位置移动到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="59db8-105">Moves a property from one location to another.</span></span>

## <span data-ttu-id="59db8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="59db8-106">SYNTAX</span></span>

### <span data-ttu-id="59db8-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="59db8-107">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="59db8-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="59db8-108">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="59db8-109">说明</span><span class="sxs-lookup"><span data-stu-id="59db8-109">Description</span></span>

<span data-ttu-id="59db8-110">`Move-ItemProperty`Cmdlet 将项的属性从一个项移动到另一个项。</span><span class="sxs-lookup"><span data-stu-id="59db8-110">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="59db8-111">例如，它可以将注册表条目从一个注册表项移到另一个注册表项。</span><span class="sxs-lookup"><span data-stu-id="59db8-111">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="59db8-112">在你移动某个项属性时，该属性将被添加到新位置，并从其原来的位置删除。</span><span class="sxs-lookup"><span data-stu-id="59db8-112">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="59db8-113">示例</span><span class="sxs-lookup"><span data-stu-id="59db8-113">EXAMPLES</span></span>

### <span data-ttu-id="59db8-114">示例1：将注册表值及其数据移动到另一个键</span><span class="sxs-lookup"><span data-stu-id="59db8-114">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="59db8-115">此命令将版本注册表值及其数据从 "MyApp" 子项移动到注册表项的 Newapp.siteconfig.numberofworkers 子项 `HKLM\Software\MyCompany` 。</span><span class="sxs-lookup"><span data-stu-id="59db8-115">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="59db8-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="59db8-116">PARAMETERS</span></span>

### <span data-ttu-id="59db8-117">-Credential</span><span class="sxs-lookup"><span data-stu-id="59db8-117">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="59db8-118">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="59db8-118">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="59db8-119">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="59db8-119">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="59db8-120">-Destination</span><span class="sxs-lookup"><span data-stu-id="59db8-120">-Destination</span></span>

<span data-ttu-id="59db8-121">指定目标位置的路径。</span><span class="sxs-lookup"><span data-stu-id="59db8-121">Specifies the path to the destination location.</span></span>

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

### <span data-ttu-id="59db8-122">-Exclude</span><span class="sxs-lookup"><span data-stu-id="59db8-122">-Exclude</span></span>

<span data-ttu-id="59db8-123">指定为字符串数组，此 cmdlet 从操作中排除的属性或属性。</span><span class="sxs-lookup"><span data-stu-id="59db8-123">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="59db8-124">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="59db8-124">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="59db8-125">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="59db8-125">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="59db8-126">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="59db8-126">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="59db8-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="59db8-127">-Filter</span></span>

<span data-ttu-id="59db8-128">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="59db8-128">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="59db8-129">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="59db8-129">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="59db8-130">筛选器的语法（包括通配符字符的使用），具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="59db8-130">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="59db8-131">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="59db8-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="59db8-132">-Force</span><span class="sxs-lookup"><span data-stu-id="59db8-132">-Force</span></span>

<span data-ttu-id="59db8-133">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="59db8-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="59db8-134">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="59db8-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="59db8-135">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="59db8-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="59db8-136">-Include</span><span class="sxs-lookup"><span data-stu-id="59db8-136">-Include</span></span>

<span data-ttu-id="59db8-137">指定为字符串数组，此 cmdlet 包含在操作中的属性或属性。</span><span class="sxs-lookup"><span data-stu-id="59db8-137">Specifies, as a string array, a property or property that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="59db8-138">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="59db8-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="59db8-139">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="59db8-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="59db8-140">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="59db8-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="59db8-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="59db8-141">-LiteralPath</span></span>

<span data-ttu-id="59db8-142">指定此属性的当前位置的路径。</span><span class="sxs-lookup"><span data-stu-id="59db8-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="59db8-143">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="59db8-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="59db8-144">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="59db8-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="59db8-145">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="59db8-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="59db8-146">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="59db8-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="59db8-147">-Name</span><span class="sxs-lookup"><span data-stu-id="59db8-147">-Name</span></span>

<span data-ttu-id="59db8-148">指定要移动的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="59db8-148">Specifies the name of the property to be moved.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="59db8-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="59db8-149">-PassThru</span></span>

<span data-ttu-id="59db8-150">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="59db8-150">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="59db8-151">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="59db8-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="59db8-152">-Path</span><span class="sxs-lookup"><span data-stu-id="59db8-152">-Path</span></span>

<span data-ttu-id="59db8-153">指定此属性的当前位置的路径。</span><span class="sxs-lookup"><span data-stu-id="59db8-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="59db8-154">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="59db8-154">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="59db8-155">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="59db8-155">-UseTransaction</span></span>

<span data-ttu-id="59db8-156">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="59db8-156">Includes the command in the active transaction.</span></span>
<span data-ttu-id="59db8-157">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="59db8-157">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="59db8-158">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="59db8-158">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="59db8-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="59db8-159">-Confirm</span></span>

<span data-ttu-id="59db8-160">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="59db8-160">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="59db8-161">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="59db8-161">-WhatIf</span></span>

<span data-ttu-id="59db8-162">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="59db8-162">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="59db8-163">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="59db8-163">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="59db8-164">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="59db8-164">CommonParameters</span></span>

<span data-ttu-id="59db8-165">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="59db8-165">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="59db8-166">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="59db8-166">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="59db8-167">输入</span><span class="sxs-lookup"><span data-stu-id="59db8-167">INPUTS</span></span>

### <span data-ttu-id="59db8-168">System.String</span><span class="sxs-lookup"><span data-stu-id="59db8-168">System.String</span></span>

<span data-ttu-id="59db8-169">可以通过管道将包含路径的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="59db8-169">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="59db8-170">输出</span><span class="sxs-lookup"><span data-stu-id="59db8-170">OUTPUTS</span></span>

### <span data-ttu-id="59db8-171">无或 System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="59db8-171">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="59db8-172">当使用 **PassThru** 参数时，此 cmdlet 将生成一个表示已移动项属性的 **PSCustomObject** 。</span><span class="sxs-lookup"><span data-stu-id="59db8-172">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span>
<span data-ttu-id="59db8-173">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="59db8-173">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="59db8-174">注释</span><span class="sxs-lookup"><span data-stu-id="59db8-174">NOTES</span></span>

<span data-ttu-id="59db8-175">此 cmdlet 用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="59db8-175">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="59db8-176">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="59db8-176">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="59db8-177">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="59db8-177">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="59db8-178">相关链接</span><span class="sxs-lookup"><span data-stu-id="59db8-178">RELATED LINKS</span></span>

[<span data-ttu-id="59db8-179">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-179">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="59db8-180">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-180">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="59db8-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-181">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="59db8-182">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-182">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="59db8-183">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-183">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="59db8-184">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-184">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="59db8-185">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="59db8-185">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="59db8-186">about_Providers</span><span class="sxs-lookup"><span data-stu-id="59db8-186">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
