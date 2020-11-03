---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ItemProperty
ms.openlocfilehash: 335f1f5b3e40eaf39cee7213b7bb02dbfa69ee3c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197314"
---
# <span data-ttu-id="0fc48-103">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-103">Remove-ItemProperty</span></span>

## <span data-ttu-id="0fc48-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0fc48-104">SYNOPSIS</span></span>
<span data-ttu-id="0fc48-105">从注册表项中删除属性及其值。</span><span class="sxs-lookup"><span data-stu-id="0fc48-105">Deletes the property and its value from an item.</span></span>

## <span data-ttu-id="0fc48-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0fc48-106">SYNTAX</span></span>

### <span data-ttu-id="0fc48-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="0fc48-107">Path (Default)</span></span>

```
Remove-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Force] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0fc48-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0fc48-108">LiteralPath</span></span>

```
Remove-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0fc48-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fc48-109">DESCRIPTION</span></span>

<span data-ttu-id="0fc48-110">`Remove-ItemProperty`Cmdlet 可从项中删除属性及其值。</span><span class="sxs-lookup"><span data-stu-id="0fc48-110">The `Remove-ItemProperty` cmdlet deletes a property and its value from an item.</span></span>
<span data-ttu-id="0fc48-111">你可以使用它删除注册表值及其存储的数据。</span><span class="sxs-lookup"><span data-stu-id="0fc48-111">You can use it to delete registry values and the data that they store.</span></span>

## <span data-ttu-id="0fc48-112">示例</span><span class="sxs-lookup"><span data-stu-id="0fc48-112">EXAMPLES</span></span>

### <span data-ttu-id="0fc48-113">示例 1：删除注册表值</span><span class="sxs-lookup"><span data-stu-id="0fc48-113">Example 1: Delete a registry value</span></span>

<span data-ttu-id="0fc48-114">此命令从注册表项的 "SmpApplication" 子项中删除 "SmpProperty" 注册表值及其数据 `HKEY_LOCAL_MACHINE\Software` 。</span><span class="sxs-lookup"><span data-stu-id="0fc48-114">This command deletes the "SmpProperty" registry value, and its data, from the "SmpApplication" subkey of the `HKEY_LOCAL_MACHINE\Software` registry key.</span></span>

```powershell
Remove-ItemProperty -Path "HKLM:\Software\SmpApplication" -Name "SmpProperty"
```

<span data-ttu-id="0fc48-115">由于命令是从文件系统驱动器 `PS C:\>` （ () ）发出的，因此它包括 "SmpApplication" 子项的完全限定路径，包括驱动器、 `HKLM:` 和 "软件" 键。</span><span class="sxs-lookup"><span data-stu-id="0fc48-115">Because the command is issued from a file system drive (`PS C:\>`), it includes the fully qualified path of the "SmpApplication" subkey, including the drive, `HKLM:`, and the "Software" key.</span></span>

### <span data-ttu-id="0fc48-116">示例 2：从 HKCU 位置删除注册表值</span><span class="sxs-lookup"><span data-stu-id="0fc48-116">Example 2: Delete a registry value from the HKCU location</span></span>

<span data-ttu-id="0fc48-117">这些命令从 "HKEY_CURRENT_USER\Software\MyCompany" 的 "MyApp" 子项删除 "Options" 注册表值及其数据。</span><span class="sxs-lookup"><span data-stu-id="0fc48-117">These commands delete the "Options" registry value, and its data, from the "MyApp" subkey of "HKEY_CURRENT_USER\Software\MyCompany".</span></span>

```
PS C:\> Set-Location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> Remove-ItemProperty -Path . -Name "Options" -Confirm
```

<span data-ttu-id="0fc48-118">第一个命令使用 `Set-Location` cmdlet 将当前位置更改为 **HKEY_CURRENT_USER** 驱动器 (`HKCU:`) 和 `Software\MyCompany\MyApp` 子项。</span><span class="sxs-lookup"><span data-stu-id="0fc48-118">The first command uses the `Set-Location` cmdlet to change the current location to the **HKEY_CURRENT_USER** drive (`HKCU:`) and the `Software\MyCompany\MyApp` subkey.</span></span>

<span data-ttu-id="0fc48-119">第二个命令使用 `Remove-ItemProperty` 从 "MyApp" 子项中删除 "Options" 注册表值及其数据。</span><span class="sxs-lookup"><span data-stu-id="0fc48-119">The second command uses `Remove-ItemProperty` to remove the "Options" registry value, and its data, from the "MyApp" subkey.</span></span> <span data-ttu-id="0fc48-120">由于 **路径** 是必需的，因此该命令使用点 (`.`) 来指示当前位置。</span><span class="sxs-lookup"><span data-stu-id="0fc48-120">Because **Path** is required, the command uses a dot (`.`) to indicate the current location.</span></span> <span data-ttu-id="0fc48-121">**Confirm** 参数在删除值之前请求用户提示。</span><span class="sxs-lookup"><span data-stu-id="0fc48-121">The **Confirm** parameter requests a user prompt before deleting the value.</span></span>

### <span data-ttu-id="0fc48-122">示例 3：使用管道删除注册表值</span><span class="sxs-lookup"><span data-stu-id="0fc48-122">Example 3: Remove a registry value by using the pipeline</span></span>

<span data-ttu-id="0fc48-123">此命令从注册表项中删除 "NoOfEmployees" 注册表值及其数据 `HKLM\Software\MyCompany` 。</span><span class="sxs-lookup"><span data-stu-id="0fc48-123">This command deletes the "NoOfEmployees" registry value, and its data, from the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany | Remove-ItemProperty -Name NoOfEmployees
```

<span data-ttu-id="0fc48-124">该命令使用 `Get-Item` cmdlet 来获取表示该注册表项的项。</span><span class="sxs-lookup"><span data-stu-id="0fc48-124">The command uses the `Get-Item` cmdlet to get an item that represents the registry key.</span></span>
<span data-ttu-id="0fc48-125">它使用管道运算符 (`|`) 将对象发送到 `Remove-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="0fc48-125">It uses a pipeline operator (`|`) to send the object to `Remove-ItemProperty`.</span></span>
<span data-ttu-id="0fc48-126">然后，它使用的 **name** 参数 `Remove-ItemProperty` 来指定注册表值的名称。</span><span class="sxs-lookup"><span data-stu-id="0fc48-126">Then, it uses the **Name** parameter of `Remove-ItemProperty` to specify the name of the registry value.</span></span>

## <span data-ttu-id="0fc48-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0fc48-127">PARAMETERS</span></span>

### <span data-ttu-id="0fc48-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="0fc48-128">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="0fc48-129">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="0fc48-129">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="0fc48-130">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="0fc48-130">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="0fc48-131">-Exclude</span><span class="sxs-lookup"><span data-stu-id="0fc48-131">-Exclude</span></span>

<span data-ttu-id="0fc48-132">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="0fc48-132">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="0fc48-133">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="0fc48-133">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0fc48-134">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="0fc48-134">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="0fc48-135">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0fc48-135">Wildcard characters are permitted.</span></span> <span data-ttu-id="0fc48-136">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="0fc48-136">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0fc48-137">-Filter</span><span class="sxs-lookup"><span data-stu-id="0fc48-137">-Filter</span></span>

<span data-ttu-id="0fc48-138">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="0fc48-138">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="0fc48-139">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0fc48-139">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="0fc48-140">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="0fc48-140">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="0fc48-141">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0fc48-141">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="0fc48-142">-Force</span><span class="sxs-lookup"><span data-stu-id="0fc48-142">-Force</span></span>

<span data-ttu-id="0fc48-143">强制 cmdlet 删除用户非此不能访问的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="0fc48-143">Forces the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="0fc48-144">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="0fc48-144">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="0fc48-145">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="0fc48-145">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="0fc48-146">-Include</span><span class="sxs-lookup"><span data-stu-id="0fc48-146">-Include</span></span>

<span data-ttu-id="0fc48-147">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="0fc48-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="0fc48-148">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="0fc48-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="0fc48-149">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="0fc48-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="0fc48-150">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0fc48-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="0fc48-151">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="0fc48-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="0fc48-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0fc48-152">-LiteralPath</span></span>

<span data-ttu-id="0fc48-153">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="0fc48-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="0fc48-154">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="0fc48-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="0fc48-155">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="0fc48-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="0fc48-156">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="0fc48-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="0fc48-157">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="0fc48-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="0fc48-158">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="0fc48-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="0fc48-159">-Name</span><span class="sxs-lookup"><span data-stu-id="0fc48-159">-Name</span></span>

<span data-ttu-id="0fc48-160">指定要删除的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="0fc48-160">Specifies the names of the properties to remove.</span></span>
<span data-ttu-id="0fc48-161">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0fc48-161">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0fc48-162">-Path</span><span class="sxs-lookup"><span data-stu-id="0fc48-162">-Path</span></span>

<span data-ttu-id="0fc48-163">指定要删除其属性的项的路径。</span><span class="sxs-lookup"><span data-stu-id="0fc48-163">Specifies the path of the item whose properties are being removed.</span></span>
<span data-ttu-id="0fc48-164">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0fc48-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0fc48-165">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0fc48-165">-Confirm</span></span>

<span data-ttu-id="0fc48-166">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="0fc48-166">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0fc48-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0fc48-167">-WhatIf</span></span>

<span data-ttu-id="0fc48-168">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="0fc48-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0fc48-169">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="0fc48-169">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0fc48-170">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0fc48-170">CommonParameters</span></span>

<span data-ttu-id="0fc48-171">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="0fc48-171">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="0fc48-172">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="0fc48-172">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0fc48-173">输入</span><span class="sxs-lookup"><span data-stu-id="0fc48-173">INPUTS</span></span>

### <span data-ttu-id="0fc48-174">System.String</span><span class="sxs-lookup"><span data-stu-id="0fc48-174">System.String</span></span>

<span data-ttu-id="0fc48-175">可以通过管道将包含路径（但不是文本路径）的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0fc48-175">You can pipe a string that contains a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="0fc48-176">输出</span><span class="sxs-lookup"><span data-stu-id="0fc48-176">OUTPUTS</span></span>

### <span data-ttu-id="0fc48-177">无</span><span class="sxs-lookup"><span data-stu-id="0fc48-177">None</span></span>

<span data-ttu-id="0fc48-178">此 cmdlet 不返回任何输出。</span><span class="sxs-lookup"><span data-stu-id="0fc48-178">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="0fc48-179">注释</span><span class="sxs-lookup"><span data-stu-id="0fc48-179">NOTES</span></span>

- <span data-ttu-id="0fc48-180">在 PowerShell 注册表提供程序中，注册表值被视为注册表项或子项的属性。</span><span class="sxs-lookup"><span data-stu-id="0fc48-180">In the PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.</span></span> <span data-ttu-id="0fc48-181">可以使用 **set-itemproperty** cmdlet 来管理这些值。</span><span class="sxs-lookup"><span data-stu-id="0fc48-181">You can use the **ItemProperty** cmdlets to manage these values.</span></span>
- <span data-ttu-id="0fc48-182">`Remove-ItemProperty` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="0fc48-182">`Remove-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0fc48-183">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="0fc48-183">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="0fc48-184">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="0fc48-184">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0fc48-185">相关链接</span><span class="sxs-lookup"><span data-stu-id="0fc48-185">RELATED LINKS</span></span>

[<span data-ttu-id="0fc48-186">Get-Item</span><span class="sxs-lookup"><span data-stu-id="0fc48-186">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="0fc48-187">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-187">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="0fc48-188">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-188">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="0fc48-189">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-189">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="0fc48-190">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-190">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="0fc48-191">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-191">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="0fc48-192">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="0fc48-192">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="0fc48-193">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-193">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="0fc48-194">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0fc48-194">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="0fc48-195">Set-Location</span><span class="sxs-lookup"><span data-stu-id="0fc48-195">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="0fc48-196">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0fc48-196">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

