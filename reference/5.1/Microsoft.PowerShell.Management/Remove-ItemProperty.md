---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 9ae9c0e7c17a6a63da5487cce138ddce129b975b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198067"
---
# <span data-ttu-id="b269b-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="b269b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b269b-104">SYNOPSIS</span></span>
<span data-ttu-id="b269b-105">从注册表项中删除属性及其值。</span><span class="sxs-lookup"><span data-stu-id="b269b-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="b269b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b269b-106">SYNTAX</span></span>

### <span data-ttu-id="b269b-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="b269b-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="b269b-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b269b-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="b269b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b269b-109">DESCRIPTION</span></span>

<span data-ttu-id="b269b-110">`Remove-ItemProperty`Cmdlet 可从项中删除属性及其值。</span><span class="sxs-lookup"><span data-stu-id="b269b-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="b269b-111">你可以使用它删除注册表值及其存储的数据。</span><span class="sxs-lookup"><span data-stu-id="b269b-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="b269b-112">示例</span><span class="sxs-lookup"><span data-stu-id="b269b-112">EXAMPLES</span></span>

### <span data-ttu-id="b269b-113">示例 1：删除注册表值</span><span class="sxs-lookup"><span data-stu-id="b269b-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="b269b-114">此命令从 "HKEY_LOCAL_MACHINE\Software" 注册表项的 "SmpApplication" 子项中删除 "SmpProperty" 注册表值及其数据。</span><span class="sxs-lookup"><span data-stu-id="b269b-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the "HKEY_LOCAL_MACHINE\Software" registry key.</span></span>

<span data-ttu-id="b269b-115">由于命令是从文件系统驱动器 `PS C:\>` （ () ）发出的，因此它包括 "SmpApplication" 子项的完全限定路径，包括驱动器、 `HKLM:` 和 "软件" 键。</span><span class="sxs-lookup"><span data-stu-id="b269b-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

<span data-ttu-id="b269b-116">它使用 **Name** 参数来标识要删除的注册表值。</span><span class="sxs-lookup"><span data-stu-id="b269b-116">It uses the **Name** parameter to identify the registry value that is being deleted.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

### <span data-ttu-id="b269b-117">示例 2：从 HKCU 位置删除注册表值</span><span class="sxs-lookup"><span data-stu-id="b269b-117">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="b269b-118">这些命令从 "HKEY_CURRENT_USER\Software\MyCompany" 的 "MyApp" 子项删除 "Options" 注册表值及其数据。</span><span class="sxs-lookup"><span data-stu-id="b269b-118">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

<span data-ttu-id="b269b-119">第一个命令使用 `Set-Location` cmdlet 将当前位置更改为 **HKEY_CURRENT_USER** 驱动器 (`HKCU:`) 和 "Software\MyCompany\MyApp" 子项。</span><span class="sxs-lookup"><span data-stu-id="b269b-119">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the "Software\MyCompany\MyApp" subkey.</span></span>

<span data-ttu-id="b269b-120">第二个命令使用 `Remove-ItemProperty` 从 "MyApp" 子项中删除 "Options" 注册表值及其数据。</span><span class="sxs-lookup"><span data-stu-id="b269b-120">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span>
<span data-ttu-id="b269b-121">由于 **路径** 是必需的，因此该命令使用点 ( "。") 指示当前位置。</span><span class="sxs-lookup"><span data-stu-id="b269b-121">Because **Path** is required, the command uses a dot ('.') to indicate the current location.</span></span>
<span data-ttu-id="b269b-122">它使用 Name  来指定要删除的注册表值。</span><span class="sxs-lookup"><span data-stu-id="b269b-122">It uses **Name** to specify which registry value to delete.</span></span>
<span data-ttu-id="b269b-123">它使用 **Confirm** 参数在删除值之前请求用户提示。</span><span class="sxs-lookup"><span data-stu-id="b269b-123">It uses the **Confirm** parameter to request a user prompt before deleting the value.</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

### <span data-ttu-id="b269b-124">示例 3：使用管道删除注册表值</span><span class="sxs-lookup"><span data-stu-id="b269b-124">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="b269b-125">此命令从 "HKLM\Software\MyCompany" 注册表项中删除 "NoOfEmployees" 注册表值及其数据。</span><span class="sxs-lookup"><span data-stu-id="b269b-125">This command deletes the "NoOfEmployees" registry value, and its data, from the "HKLM\Software\MyCompany" registry key.</span></span>

<span data-ttu-id="b269b-126">该命令使用 `Get-Item` cmdlet 来获取表示该注册表项的项。</span><span class="sxs-lookup"><span data-stu-id="b269b-126">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="b269b-127">它使用管道运算符 (`|`) 将对象发送到 `Remove-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="b269b-127">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="b269b-128">然后，它使用的 **name** 参数 `Remove-ItemProperty` 来指定注册表值的名称。</span><span class="sxs-lookup"><span data-stu-id="b269b-128">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

## <span data-ttu-id="b269b-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b269b-129">PARAMETERS</span></span>

### <span data-ttu-id="b269b-130">-Credential</span><span class="sxs-lookup"><span data-stu-id="b269b-130">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="b269b-131">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="b269b-131">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="b269b-132">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="b269b-132">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="b269b-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="b269b-133">-Exclude</span></span>

<span data-ttu-id="b269b-134">指定此 cmdlet 省略的项。</span><span class="sxs-lookup"><span data-stu-id="b269b-134">Specifies items that this cmdlet omits.</span></span>
<span data-ttu-id="b269b-135">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b269b-135">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="b269b-136">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="b269b-136">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="b269b-137">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b269b-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b269b-138">-Filter</span><span class="sxs-lookup"><span data-stu-id="b269b-138">-Filter</span></span>

<span data-ttu-id="b269b-139">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="b269b-139">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="b269b-140">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b269b-140">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="b269b-141">筛选器的语法（包括通配符字符的使用），具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="b269b-141">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="b269b-142">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b269b-142">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="b269b-143">-Force</span><span class="sxs-lookup"><span data-stu-id="b269b-143">-Force</span></span>

<span data-ttu-id="b269b-144">强制 cmdlet 删除用户非此不能访问的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="b269b-144">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="b269b-145">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="b269b-145">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="b269b-146">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="b269b-146">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="b269b-147">-Include</span><span class="sxs-lookup"><span data-stu-id="b269b-147">-Include</span></span>

<span data-ttu-id="b269b-148">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="b269b-148">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="b269b-149">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="b269b-149">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="b269b-150">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="b269b-150">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="b269b-151">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b269b-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b269b-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="b269b-152">-LiteralPath</span></span>

<span data-ttu-id="b269b-153">指定此属性的当前位置的路径。</span><span class="sxs-lookup"><span data-stu-id="b269b-153">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="b269b-154">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="b269b-154">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="b269b-155">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="b269b-155">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="b269b-156">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="b269b-156">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="b269b-157">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="b269b-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="b269b-158">-Name</span><span class="sxs-lookup"><span data-stu-id="b269b-158">-Name</span></span>

<span data-ttu-id="b269b-159">指定要删除的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="b269b-159">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="b269b-160">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b269b-160">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b269b-161">-Path</span><span class="sxs-lookup"><span data-stu-id="b269b-161">-Path</span></span>

<span data-ttu-id="b269b-162">指定要删除其属性的项的路径。</span><span class="sxs-lookup"><span data-stu-id="b269b-162">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="b269b-163">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b269b-163">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="b269b-164">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="b269b-164">-UseTransaction</span></span>

<span data-ttu-id="b269b-165">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="b269b-165">Includes the command in the active transaction.</span></span>
<span data-ttu-id="b269b-166">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="b269b-166">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="b269b-167">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="b269b-167">For more information, see about_Transactions.</span></span>

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

### <span data-ttu-id="b269b-168">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b269b-168">-Confirm</span></span>

<span data-ttu-id="b269b-169">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="b269b-169">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b269b-170">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b269b-170">-WhatIf</span></span>

<span data-ttu-id="b269b-171">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="b269b-171">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b269b-172">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="b269b-172">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b269b-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b269b-173">CommonParameters</span></span>

<span data-ttu-id="b269b-174">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="b269b-174">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="b269b-175">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b269b-175">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b269b-176">输入</span><span class="sxs-lookup"><span data-stu-id="b269b-176">INPUTS</span></span>

### <span data-ttu-id="b269b-177">System.String</span><span class="sxs-lookup"><span data-stu-id="b269b-177">System.String</span></span>

<span data-ttu-id="b269b-178">可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b269b-178">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="b269b-179">输出</span><span class="sxs-lookup"><span data-stu-id="b269b-179">OUTPUTS</span></span>

### <span data-ttu-id="b269b-180">无</span><span class="sxs-lookup"><span data-stu-id="b269b-180">None</span></span>

<span data-ttu-id="b269b-181">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="b269b-181">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="b269b-182">注释</span><span class="sxs-lookup"><span data-stu-id="b269b-182">NOTES</span></span>

<span data-ttu-id="b269b-183">在 PowerShell 注册表提供程序中，注册表值被视为注册表项或子项的属性。</span><span class="sxs-lookup"><span data-stu-id="b269b-183">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="b269b-184">可以使用 **set-itemproperty** cmdlet 来管理这些值。</span><span class="sxs-lookup"><span data-stu-id="b269b-184">You can use the **ItemProperty** cmdlets to manage these values.</span></span>

<span data-ttu-id="b269b-185">`Remove-ItemProperty` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="b269b-185">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="b269b-186">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="b269b-186">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="b269b-187">有关详细信息，请参阅 about_Providers。</span><span class="sxs-lookup"><span data-stu-id="b269b-187">For more information, see about_Providers.</span></span>

## <span data-ttu-id="b269b-188">相关链接</span><span class="sxs-lookup"><span data-stu-id="b269b-188">RELATED LINKS</span></span>

[<span data-ttu-id="b269b-189">Get-Item</span><span class="sxs-lookup"><span data-stu-id="b269b-189">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="b269b-190">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-190">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="b269b-191">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-191">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="b269b-192">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-192">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="b269b-193">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-193">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="b269b-194">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-194">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="b269b-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="b269b-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="b269b-196">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-196">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="b269b-197">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="b269b-197">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="b269b-198">about_Providers</span><span class="sxs-lookup"><span data-stu-id="b269b-198">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
