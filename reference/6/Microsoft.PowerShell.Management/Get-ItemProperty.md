---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: abf6a5ef365a606b6ca501e9cb924528763a8754
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198513"
---
# <span data-ttu-id="666cf-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-103">Get-ItemProperty</span></span>

## <span data-ttu-id="666cf-104">摘要</span><span class="sxs-lookup"><span data-stu-id="666cf-104">SYNOPSIS</span></span>
<span data-ttu-id="666cf-105">获取指定项的属性。</span><span class="sxs-lookup"><span data-stu-id="666cf-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="666cf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="666cf-106">SYNTAX</span></span>

### <span data-ttu-id="666cf-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="666cf-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="666cf-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="666cf-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="666cf-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="666cf-109">DESCRIPTION</span></span>

<span data-ttu-id="666cf-110">`Get-ItemProperty`Cmdlet 将获取指定项的属性。</span><span class="sxs-lookup"><span data-stu-id="666cf-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="666cf-111">例如，你可以使用此 cmdlet 来获取文件对象的 LastAccessTime 属性的值。</span><span class="sxs-lookup"><span data-stu-id="666cf-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span> <span data-ttu-id="666cf-112">你还可以使用此 cmdlet 查看注册表项及其值。</span><span class="sxs-lookup"><span data-stu-id="666cf-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="666cf-113">示例</span><span class="sxs-lookup"><span data-stu-id="666cf-113">EXAMPLES</span></span>

### <span data-ttu-id="666cf-114">示例1：获取有关特定目录的信息</span><span class="sxs-lookup"><span data-stu-id="666cf-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="666cf-115">此命令获取有关目录的信息 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="666cf-115">This command gets information about the `C:\Windows` directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="666cf-116">示例2：获取特定文件的属性</span><span class="sxs-lookup"><span data-stu-id="666cf-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="666cf-117">此命令获取文件的属性 `C:\Test\Weather.xls` 。</span><span class="sxs-lookup"><span data-stu-id="666cf-117">This command gets the properties of the `C:\Test\Weather.xls` file.</span></span>
<span data-ttu-id="666cf-118">将结果输送到 cmdlet， `Format-List` 以将输出显示为列表。</span><span class="sxs-lookup"><span data-stu-id="666cf-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="666cf-119">示例3：在注册表子项中显示注册表项的值名称和数据</span><span class="sxs-lookup"><span data-stu-id="666cf-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="666cf-120">此命令显示 "CurrentVersion" 注册表子项中包含的每个注册表项的值名称和数据。</span><span class="sxs-lookup"><span data-stu-id="666cf-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

> [!NOTE]
> <span data-ttu-id="666cf-121">此命令要求有一个名为的 PowerShell 驱动器 `HKLM:` ，该驱动器映射到注册表的 "HKEY_LOCAL_MACHINE" hive。</span><span class="sxs-lookup"><span data-stu-id="666cf-121">This command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
>
> <span data-ttu-id="666cf-122">默认情况下，具有该名称和映射的驱动器在 PowerShell 中可用。</span><span class="sxs-lookup"><span data-stu-id="666cf-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
> <span data-ttu-id="666cf-123">或者，可以通过使用以下替代路径指定此注册表子项的路径（替代路径以提供程序名称开头，后跟两个冒号）：</span><span class="sxs-lookup"><span data-stu-id="666cf-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>
>
> <span data-ttu-id="666cf-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span><span class="sxs-lookup"><span data-stu-id="666cf-124">`Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

### <span data-ttu-id="666cf-125">示例4：获取注册表子项中的注册表项的值名称和数据</span><span class="sxs-lookup"><span data-stu-id="666cf-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="666cf-126">此命令将获取 "CurrentVersion" 注册表子项中的 "ProgramFilesDir" 注册表项的值名称和数据。</span><span class="sxs-lookup"><span data-stu-id="666cf-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="666cf-127">**路径** 指定子项， **Name** 参数指定条目的值名称。</span><span class="sxs-lookup"><span data-stu-id="666cf-127">The **Path** specifies the subkey and the **Name** parameter specifies the value name of the entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="666cf-128">示例5：获取注册表项中的注册表项的值名称和数据</span><span class="sxs-lookup"><span data-stu-id="666cf-128">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="666cf-129">此命令将获取 "PowerShellEngine" 注册表项中的注册表项的值名称和数据。</span><span class="sxs-lookup"><span data-stu-id="666cf-129">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span> <span data-ttu-id="666cf-130">结果显示在下面的示例输出中。</span><span class="sxs-lookup"><span data-stu-id="666cf-130">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

## <span data-ttu-id="666cf-131">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="666cf-131">PARAMETERS</span></span>

### <span data-ttu-id="666cf-132">-Credential</span><span class="sxs-lookup"><span data-stu-id="666cf-132">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="666cf-133">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="666cf-133">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="666cf-134">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="666cf-134">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="666cf-135">-Exclude</span><span class="sxs-lookup"><span data-stu-id="666cf-135">-Exclude</span></span>

<span data-ttu-id="666cf-136">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="666cf-136">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="666cf-137">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="666cf-137">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="666cf-138">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="666cf-138">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="666cf-139">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="666cf-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="666cf-140">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="666cf-140">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="666cf-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="666cf-141">-Filter</span></span>

<span data-ttu-id="666cf-142">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="666cf-142">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="666cf-143">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="666cf-143">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="666cf-144">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="666cf-144">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="666cf-145">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="666cf-145">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="666cf-146">-Include</span><span class="sxs-lookup"><span data-stu-id="666cf-146">-Include</span></span>

<span data-ttu-id="666cf-147">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="666cf-147">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="666cf-148">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="666cf-148">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="666cf-149">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="666cf-149">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="666cf-150">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="666cf-150">Wildcard characters are permitted.</span></span> <span data-ttu-id="666cf-151">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="666cf-151">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="666cf-152">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="666cf-152">-LiteralPath</span></span>

<span data-ttu-id="666cf-153">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="666cf-153">Specifies a path to one or more locations.</span></span> <span data-ttu-id="666cf-154">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="666cf-154">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="666cf-155">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="666cf-155">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="666cf-156">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="666cf-156">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="666cf-157">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="666cf-157">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="666cf-158">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="666cf-158">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="666cf-159">-Name</span><span class="sxs-lookup"><span data-stu-id="666cf-159">-Name</span></span>

<span data-ttu-id="666cf-160">指定要检索的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="666cf-160">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="666cf-161">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="666cf-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="666cf-162">-Path</span><span class="sxs-lookup"><span data-stu-id="666cf-162">-Path</span></span>

<span data-ttu-id="666cf-163">指定一个或多个项的路径。</span><span class="sxs-lookup"><span data-stu-id="666cf-163">Specifies the path to the item or items.</span></span>
<span data-ttu-id="666cf-164">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="666cf-164">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="666cf-165">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="666cf-165">CommonParameters</span></span>

<span data-ttu-id="666cf-166">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="666cf-166">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="666cf-167">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="666cf-167">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="666cf-168">输入</span><span class="sxs-lookup"><span data-stu-id="666cf-168">INPUTS</span></span>

### <span data-ttu-id="666cf-169">System.String</span><span class="sxs-lookup"><span data-stu-id="666cf-169">System.String</span></span>

<span data-ttu-id="666cf-170">可以通过管道将包含路径的字符串传递给 `Get-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="666cf-170">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="666cf-171">输出</span><span class="sxs-lookup"><span data-stu-id="666cf-171">OUTPUTS</span></span>

### <span data-ttu-id="666cf-172">System.Boolean、System.String、System.DateTime</span><span class="sxs-lookup"><span data-stu-id="666cf-172">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="666cf-173">`Get-ItemProperty` 为它获取的每个项属性返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="666cf-173">`Get-ItemProperty` returns an object for each item property that it gets.</span></span> <span data-ttu-id="666cf-174">对象类型取决于检索的对象。</span><span class="sxs-lookup"><span data-stu-id="666cf-174">The object type depends on the object that is retrieved.</span></span> <span data-ttu-id="666cf-175">例如，在文件系统驱动器中，它可能会返回一个文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="666cf-175">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="666cf-176">注释</span><span class="sxs-lookup"><span data-stu-id="666cf-176">NOTES</span></span>

<span data-ttu-id="666cf-177">`Get-ItemProperty`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="666cf-177">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="666cf-178">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="666cf-178">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="666cf-179">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="666cf-179">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="666cf-180">相关链接</span><span class="sxs-lookup"><span data-stu-id="666cf-180">RELATED LINKS</span></span>

[<span data-ttu-id="666cf-181">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-181">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="666cf-182">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-182">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="666cf-183">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-183">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="666cf-184">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-184">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="666cf-185">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-185">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="666cf-186">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-186">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="666cf-187">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="666cf-187">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="666cf-188">about_Providers</span><span class="sxs-lookup"><span data-stu-id="666cf-188">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
