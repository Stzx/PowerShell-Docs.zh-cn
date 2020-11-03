---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/08/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-modulemanifest?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ModuleManifest
ms.openlocfilehash: 2977992a04e5a94f5124ec85abd980dc3d4f129f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198762"
---
# <span data-ttu-id="aac81-103">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="aac81-103">Update-ModuleManifest</span></span>

## <span data-ttu-id="aac81-104">摘要</span><span class="sxs-lookup"><span data-stu-id="aac81-104">SYNOPSIS</span></span>
<span data-ttu-id="aac81-105">更新模块清单文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-105">Updates a module manifest file.</span></span>

## <span data-ttu-id="aac81-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aac81-106">SYNTAX</span></span>

### <span data-ttu-id="aac81-107">全部</span><span class="sxs-lookup"><span data-stu-id="aac81-107">All</span></span>

```
Update-ModuleManifest [-Path] <String> [-NestedModules <Object[]>] [-Guid <Guid>] [-Author <String>]
 [-CompanyName <String>] [-Copyright <String>] [-RootModule <String>] [-ModuleVersion <Version>]
 [-Description <String>] [-ProcessorArchitecture <ProcessorArchitecture>]
 [-CompatiblePSEditions <String[]>] [-PowerShellVersion <Version>] [-ClrVersion <Version>]
 [-DotNetFrameworkVersion <Version>] [-PowerShellHostName <String>]
 [-PowerShellHostVersion <Version>] [-RequiredModules <Object[]>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-ScriptsToProcess <String[]>] [-RequiredAssemblies <String[]>]
 [-FileList <String[]>] [-ModuleList <Object[]>] [-FunctionsToExport <String[]>]
 [-AliasesToExport <String[]>] [-VariablesToExport <String[]>] [-CmdletsToExport <String[]>]
 [-DscResourcesToExport <String[]>] [-PrivateData <Hashtable>] [-Tags <String[]>]
 [-ProjectUri <Uri>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ReleaseNotes <String[]>]
 [-Prerelease <String>] [-HelpInfoUri <Uri>] [-PassThru] [-DefaultCommandPrefix <String>]
 [-ExternalModuleDependencies <String[]>] [-PackageManagementProviders <String[]>]
 [-RequireLicenseAcceptance] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="aac81-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="aac81-108">DESCRIPTION</span></span>

<span data-ttu-id="aac81-109">`Update-ModuleManifest`Cmdlet () 文件更新模块清单 `.psd1` 。</span><span class="sxs-lookup"><span data-stu-id="aac81-109">The `Update-ModuleManifest` cmdlet updates a module manifest (`.psd1`) file.</span></span>

## <span data-ttu-id="aac81-110">示例</span><span class="sxs-lookup"><span data-stu-id="aac81-110">EXAMPLES</span></span>

### <span data-ttu-id="aac81-111">示例1：更新模块清单</span><span class="sxs-lookup"><span data-stu-id="aac81-111">Example 1: Update a module manifest</span></span>

<span data-ttu-id="aac81-112">此示例更新现有的模块清单文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-112">This example updates an existing module manifest file.</span></span> <span data-ttu-id="aac81-113">展开用于将参数值传递给 `Update-ModuleManifest` 。</span><span class="sxs-lookup"><span data-stu-id="aac81-113">Splatting is used to pass parameter values to `Update-ModuleManifest`.</span></span> <span data-ttu-id="aac81-114">有关详细信息，请参阅 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="aac81-114">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\TestManifest.psd1"
  Author = "TestUser1"
  CompanyName = "Contoso Corporation"
  Copyright = "(c) 2019 Contoso Corporation. All rights reserved."
}

Update-ModuleManifest @Parms
```

<span data-ttu-id="aac81-115">`$Parms` 是存储 **路径** 、 **作者** 、 **公司名称** 和 **版权** 的参数值的 splat。</span><span class="sxs-lookup"><span data-stu-id="aac81-115">`$Parms` is a splat that stores the parameter values for **Path** , **Author** , **CompanyName** , and **Copyright** .</span></span> <span data-ttu-id="aac81-116">`Update-ModuleManifest` 从获取参数值， `@Parms` 并更新 **TestManifest.psd1** 的模块清单。</span><span class="sxs-lookup"><span data-stu-id="aac81-116">`Update-ModuleManifest` gets the parameter values from `@Parms` and updates the module manifest, **TestManifest.psd1** .</span></span>

## <span data-ttu-id="aac81-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aac81-117">PARAMETERS</span></span>

### <span data-ttu-id="aac81-118">-AliasesToExport</span><span class="sxs-lookup"><span data-stu-id="aac81-118">-AliasesToExport</span></span>

<span data-ttu-id="aac81-119">指定模块导出的别名。</span><span class="sxs-lookup"><span data-stu-id="aac81-119">Specifies the aliases that the module exports.</span></span> <span data-ttu-id="aac81-120">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="aac81-120">Wildcards are permitted.</span></span>

<span data-ttu-id="aac81-121">使用此参数来限制由模块导出的别名。</span><span class="sxs-lookup"><span data-stu-id="aac81-121">Use this parameter to restrict the aliases that are exported by the module.</span></span> <span data-ttu-id="aac81-122">**AliasesToExport** 可以从导出的别名列表中删除别名，但不能将别名添加到该列表中。</span><span class="sxs-lookup"><span data-stu-id="aac81-122">**AliasesToExport** can remove aliases from the list of exported aliases, but it can't add aliases to the list.</span></span>

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

### <span data-ttu-id="aac81-123">-作者</span><span class="sxs-lookup"><span data-stu-id="aac81-123">-Author</span></span>

<span data-ttu-id="aac81-124">指定模块作者。</span><span class="sxs-lookup"><span data-stu-id="aac81-124">Specifies the module author.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-125">-ClrVersion</span><span class="sxs-lookup"><span data-stu-id="aac81-125">-ClrVersion</span></span>

<span data-ttu-id="aac81-126">指定模块需要的 Microsoft .NET Framework 的公共语言运行时 (CLR) 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="aac81-126">Specifies the minimum version of the Common Language Runtime (CLR) of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-127">-CmdletsToExport</span><span class="sxs-lookup"><span data-stu-id="aac81-127">-CmdletsToExport</span></span>

<span data-ttu-id="aac81-128">指定模块导出的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aac81-128">Specifies the cmdlets that the module exports.</span></span> <span data-ttu-id="aac81-129">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="aac81-129">Wildcards are permitted.</span></span>

<span data-ttu-id="aac81-130">使用此参数来限制由模块导出的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aac81-130">Use this parameter to restrict the cmdlets that are exported by the module.</span></span> <span data-ttu-id="aac81-131">**CmdletsToExport** 可以从导出的 cmdlet 列表中删除 cmdlet，但不能将 cmdlet 添加到该列表中。</span><span class="sxs-lookup"><span data-stu-id="aac81-131">**CmdletsToExport** can remove cmdlets from the list of exported cmdlets, but it can't add cmdlets to the list.</span></span>

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

### <span data-ttu-id="aac81-132">-公司名称</span><span class="sxs-lookup"><span data-stu-id="aac81-132">-CompanyName</span></span>

<span data-ttu-id="aac81-133">指定创建该模块的公司或供应商。</span><span class="sxs-lookup"><span data-stu-id="aac81-133">Specifies the company or vendor who created the module.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-134">-CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="aac81-134">-CompatiblePSEditions</span></span>

<span data-ttu-id="aac81-135">指定模块的兼容 **PSEditions** 。</span><span class="sxs-lookup"><span data-stu-id="aac81-135">Specifies the compatible **PSEditions** of the module.</span></span> <span data-ttu-id="aac81-136">有关 **PSEdition** 的信息，请参阅 [具有兼容的 PowerShell 版本的模块](/powershell/scripting/gallery/concepts/module-psedition-support)。</span><span class="sxs-lookup"><span data-stu-id="aac81-136">For information about **PSEdition** , see [Modules with compatible PowerShell Editions](/powershell/scripting/gallery/concepts/module-psedition-support).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Desktop, Core

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-137">-Confirm</span><span class="sxs-lookup"><span data-stu-id="aac81-137">-Confirm</span></span>

<span data-ttu-id="aac81-138">在运行之前提示你进行确认 `Update-ModuleManifest` 。</span><span class="sxs-lookup"><span data-stu-id="aac81-138">Prompts you for confirmation before running `Update-ModuleManifest`.</span></span>

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

### <span data-ttu-id="aac81-139">-版权所有</span><span class="sxs-lookup"><span data-stu-id="aac81-139">-Copyright</span></span>

<span data-ttu-id="aac81-140">指定模块的版权声明。</span><span class="sxs-lookup"><span data-stu-id="aac81-140">Specifies a copyright statement for the module.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-141">-DefaultCommandPrefix</span><span class="sxs-lookup"><span data-stu-id="aac81-141">-DefaultCommandPrefix</span></span>

<span data-ttu-id="aac81-142">指定默认命令前缀。</span><span class="sxs-lookup"><span data-stu-id="aac81-142">Specifies the default command prefix.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-143">-Description</span><span class="sxs-lookup"><span data-stu-id="aac81-143">-Description</span></span>

<span data-ttu-id="aac81-144">指定模块的说明。</span><span class="sxs-lookup"><span data-stu-id="aac81-144">Specifies a description of the module.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-145">-DotNetFrameworkVersion</span><span class="sxs-lookup"><span data-stu-id="aac81-145">-DotNetFrameworkVersion</span></span>

<span data-ttu-id="aac81-146">指定模块需要的 Microsoft .NET Framework 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="aac81-146">Specifies the minimum version of the Microsoft .NET Framework that the module requires.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-147">-DscResourcesToExport</span><span class="sxs-lookup"><span data-stu-id="aac81-147">-DscResourcesToExport</span></span>

<span data-ttu-id="aac81-148">指定模块导出 (DSC) 资源的所需状态配置。</span><span class="sxs-lookup"><span data-stu-id="aac81-148">Specifies the Desired State Configuration (DSC) resources that the module exports.</span></span> <span data-ttu-id="aac81-149">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="aac81-149">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-150">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="aac81-150">-ExternalModuleDependencies</span></span>

<span data-ttu-id="aac81-151">指定外部模块依赖项的数组。</span><span class="sxs-lookup"><span data-stu-id="aac81-151">Specifies an array of external module dependencies.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-152">-FileList</span><span class="sxs-lookup"><span data-stu-id="aac81-152">-FileList</span></span>

<span data-ttu-id="aac81-153">指定模块中包括的所有项。</span><span class="sxs-lookup"><span data-stu-id="aac81-153">Specifies all items that are included in the module.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-154">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="aac81-154">-FormatsToProcess</span></span>

<span data-ttu-id="aac81-155">指定 `.ps1xml` 导入模块时运行)  (格式设置文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-155">Specifies the formatting files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="aac81-156">导入模块时，PowerShell 将 `Update-FormatData` 使用指定的文件运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aac81-156">When you import a module, PowerShell runs the `Update-FormatData` cmdlet with the specified files.</span></span>
<span data-ttu-id="aac81-157">由于格式设置文件没有作用域，因此它们会影响会话中的所有会话状态。</span><span class="sxs-lookup"><span data-stu-id="aac81-157">Because formatting files aren't scoped, they affect all session states in the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-158">-FunctionsToExport</span><span class="sxs-lookup"><span data-stu-id="aac81-158">-FunctionsToExport</span></span>

<span data-ttu-id="aac81-159">指定模块导出的函数。</span><span class="sxs-lookup"><span data-stu-id="aac81-159">Specifies the functions that the module exports.</span></span> <span data-ttu-id="aac81-160">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="aac81-160">Wildcards are permitted.</span></span>

<span data-ttu-id="aac81-161">使用此参数来限制由模块导出的函数。</span><span class="sxs-lookup"><span data-stu-id="aac81-161">Use this parameter to restrict the functions that are exported by the module.</span></span> <span data-ttu-id="aac81-162">**FunctionsToExport** 可以从导出的别名列表中删除函数，但不能将函数添加到列表。</span><span class="sxs-lookup"><span data-stu-id="aac81-162">**FunctionsToExport** can remove functions from the list of exported aliases, but it can't add functions to the list.</span></span>

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

### <span data-ttu-id="aac81-163">-Guid</span><span class="sxs-lookup"><span data-stu-id="aac81-163">-Guid</span></span>

<span data-ttu-id="aac81-164">指定模块的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="aac81-164">Specifies a unique identifier for the module.</span></span> <span data-ttu-id="aac81-165">可以使用 GUID 来区分名称相同的模块。</span><span class="sxs-lookup"><span data-stu-id="aac81-165">The GUID can be used to distinguish among modules with the same name.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-166">-HelpInfoUri</span><span class="sxs-lookup"><span data-stu-id="aac81-166">-HelpInfoUri</span></span>

<span data-ttu-id="aac81-167">指定模块的 **HELPINFO XML** 文件的 internet 地址。</span><span class="sxs-lookup"><span data-stu-id="aac81-167">Specifies the internet address of the module's **HelpInfo XML** file.</span></span> <span data-ttu-id="aac81-168">输入以 **http** 或 **HTTPS** 开头 (URI) 的统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="aac81-168">Enter a Uniform Resource Identifier (URI) that begins with **http** or **https** .</span></span>

<span data-ttu-id="aac81-169">**HELPINFO XML** 文件支持 PowerShell 版本3.0 中引入的可更新帮助功能。</span><span class="sxs-lookup"><span data-stu-id="aac81-169">The **HelpInfo XML** file supports the Updatable Help feature that was introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="aac81-170">它包含有关该模块的可下载帮助文件的位置，以及每个支持的区域设置最新帮助文件的版本号的信息。</span><span class="sxs-lookup"><span data-stu-id="aac81-170">It contains information about the location of the module's downloadable help files and the version numbers of the newest help files for each supported locale.</span></span>

<span data-ttu-id="aac81-171">有关可更新帮助的信息，请参阅 [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md)。</span><span class="sxs-lookup"><span data-stu-id="aac81-171">For information about Updatable Help, see [about_Updatable_Help](../Microsoft.PowerShell.Core/About/about_Updatable_Help.md).</span></span>
<span data-ttu-id="aac81-172">有关 **HELPINFO XML** 文件的信息，请参阅 [支持可更新的帮助](/powershell/scripting/developer/module/supporting-updatable-help)。</span><span class="sxs-lookup"><span data-stu-id="aac81-172">For information about the **HelpInfo XML** file, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-173">-IconUri</span><span class="sxs-lookup"><span data-stu-id="aac81-173">-IconUri</span></span>

<span data-ttu-id="aac81-174">指定模块的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="aac81-174">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="aac81-175">指定的图标显示在模块的库网页上。</span><span class="sxs-lookup"><span data-stu-id="aac81-175">The specified icon is displayed on the gallery web page for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-176">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="aac81-176">-LicenseUri</span></span>

<span data-ttu-id="aac81-177">指定模块的许可条款 URL。</span><span class="sxs-lookup"><span data-stu-id="aac81-177">Specifies the URL of licensing terms for the module.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-178">-ModuleList</span><span class="sxs-lookup"><span data-stu-id="aac81-178">-ModuleList</span></span>

<span data-ttu-id="aac81-179">指定模块中包含的模块的数组。</span><span class="sxs-lookup"><span data-stu-id="aac81-179">Specifies an array of modules that are included in the module.</span></span>

<span data-ttu-id="aac81-180">以字符串形式或具有 **ModuleName** 和 **ModuleVersion** 键的哈希表形式输入每个模块名称。</span><span class="sxs-lookup"><span data-stu-id="aac81-180">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="aac81-181">哈希表也可能具有一个可选的 **GUID** 键。</span><span class="sxs-lookup"><span data-stu-id="aac81-181">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="aac81-182">可以将字符串和哈希表组合到参数值中。</span><span class="sxs-lookup"><span data-stu-id="aac81-182">You can combine strings and hash tables in the parameter value.</span></span>

<span data-ttu-id="aac81-183">此键专门用于充当模块清单。</span><span class="sxs-lookup"><span data-stu-id="aac81-183">This key is designed to act as a module inventory.</span></span> <span data-ttu-id="aac81-184">不会自动处理此键的值中列出的模块。</span><span class="sxs-lookup"><span data-stu-id="aac81-184">The modules that are listed in the value of this key aren't automatically processed.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-185">-ModuleVersion</span><span class="sxs-lookup"><span data-stu-id="aac81-185">-ModuleVersion</span></span>

<span data-ttu-id="aac81-186">指定模块的版本。</span><span class="sxs-lookup"><span data-stu-id="aac81-186">Specifies the version of the module.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-187">-NestedModules</span><span class="sxs-lookup"><span data-stu-id="aac81-187">-NestedModules</span></span>

<span data-ttu-id="aac81-188">指定脚本模块 (`.psm1` `.dll` 导入模块的会话状态中 () 的) 和二进制模块。</span><span class="sxs-lookup"><span data-stu-id="aac81-188">Specifies script modules (`.psm1`) and binary modules (`.dll`) that are imported into the module's session state.</span></span> <span data-ttu-id="aac81-189">**NestedModules** 键中的文件按照其在值中的列出顺序运行。</span><span class="sxs-lookup"><span data-stu-id="aac81-189">The files in the **NestedModules** key run in the order in which they're listed in the value.</span></span>

<span data-ttu-id="aac81-190">以字符串形式或具有 **ModuleName** 和 **ModuleVersion** 键的哈希表形式输入每个模块名称。</span><span class="sxs-lookup"><span data-stu-id="aac81-190">Enter each module name as a string or as a hash table with **ModuleName** and **ModuleVersion** keys.</span></span> <span data-ttu-id="aac81-191">哈希表也可能具有一个可选的 **GUID** 键。</span><span class="sxs-lookup"><span data-stu-id="aac81-191">The hash table can also have an optional **GUID** key.</span></span> <span data-ttu-id="aac81-192">可以将字符串和哈希表组合到参数值中。</span><span class="sxs-lookup"><span data-stu-id="aac81-192">You can combine strings and hash tables in the parameter value.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-193">-PackageManagementProviders</span><span class="sxs-lookup"><span data-stu-id="aac81-193">-PackageManagementProviders</span></span>

<span data-ttu-id="aac81-194">指定包管理提供程序的数组。</span><span class="sxs-lookup"><span data-stu-id="aac81-194">Specifies an array of package management providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-195">-PassThru</span><span class="sxs-lookup"><span data-stu-id="aac81-195">-PassThru</span></span>

<span data-ttu-id="aac81-196">返回一个对象，该对象表示正在处理的项。</span><span class="sxs-lookup"><span data-stu-id="aac81-196">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="aac81-197">默认情况下， `Update-ModuleManifest` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="aac81-197">By default, `Update-ModuleManifest` doesn't generate any output.</span></span>

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

### <span data-ttu-id="aac81-198">-Path</span><span class="sxs-lookup"><span data-stu-id="aac81-198">-Path</span></span>

<span data-ttu-id="aac81-199">指定模块清单的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="aac81-199">Specifies the path and file name of the module manifest.</span></span> <span data-ttu-id="aac81-200">输入文件扩展名为的路径和文件名 `.psd1` ，例如 `$PSHOME\Modules\MyModule\MyModule.psd1` 。</span><span class="sxs-lookup"><span data-stu-id="aac81-200">Enter a path and file name with a `.psd1` file name extension, such as `$PSHOME\Modules\MyModule\MyModule.psd1`.</span></span>

<span data-ttu-id="aac81-201">如果指定了现有文件的路径，则将 `Update-ModuleManifest` 替换该文件而不发出警告，除非该文件具有只读属性。</span><span class="sxs-lookup"><span data-stu-id="aac81-201">If you specify the path to an existing file, `Update-ModuleManifest` replaces the file without warning unless the file has the read-only attribute.</span></span>

<span data-ttu-id="aac81-202">清单应位于模块的目录中，清单文件的名称应与模块目录名称相同，但具有 `.psd1` 扩展名。</span><span class="sxs-lookup"><span data-stu-id="aac81-202">The manifest should be located in the module's directory, and the manifest file name should be the same as the module directory name, but with a `.psd1` extension.</span></span>

<span data-ttu-id="aac81-203">不能使用变量（如 `$PSHOME` 或 `$HOME` ）来响应 **Path** 参数值的提示。</span><span class="sxs-lookup"><span data-stu-id="aac81-203">You can't use variables, such as `$PSHOME` or `$HOME`, in response to a prompt for a **Path** parameter value.</span></span> <span data-ttu-id="aac81-204">若要使用变量，请将 **Path** 参数包含在命令中。</span><span class="sxs-lookup"><span data-stu-id="aac81-204">To use a variable, include the **Path** parameter in the command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-205">-PowerShellHostName</span><span class="sxs-lookup"><span data-stu-id="aac81-205">-PowerShellHostName</span></span>

<span data-ttu-id="aac81-206">指定模块所需的 PowerShell 主机程序的名称。</span><span class="sxs-lookup"><span data-stu-id="aac81-206">Specifies the name of the PowerShell host program that the module requires.</span></span> <span data-ttu-id="aac81-207">输入主机程序的名称，例如 PowerShell ISE Host 或 ConsoleHost。</span><span class="sxs-lookup"><span data-stu-id="aac81-207">Enter the name of the host program, such as PowerShell ISE Host or ConsoleHost.</span></span> <span data-ttu-id="aac81-208">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="aac81-208">Wildcards aren't permitted.</span></span>

<span data-ttu-id="aac81-209">若要查找主机程序的名称，请在 "程序" 中键入 `$Host.Name` 。</span><span class="sxs-lookup"><span data-stu-id="aac81-209">To find the name of a host program, in the program, type `$Host.Name`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-210">-PowerShellHostVersion</span><span class="sxs-lookup"><span data-stu-id="aac81-210">-PowerShellHostVersion</span></span>

<span data-ttu-id="aac81-211">指定适用于该模块的 PowerShell 主机程序的最低版本。</span><span class="sxs-lookup"><span data-stu-id="aac81-211">Specifies the minimum version of the PowerShell host program that works with the module.</span></span> <span data-ttu-id="aac81-212">输入版本号，例如 1.1。</span><span class="sxs-lookup"><span data-stu-id="aac81-212">Enter a version number, such as 1.1.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-213">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="aac81-213">-PowerShellVersion</span></span>

<span data-ttu-id="aac81-214">指定将用于此模块的 PowerShell 的最低版本。</span><span class="sxs-lookup"><span data-stu-id="aac81-214">Specifies the minimum version of PowerShell that will work with this module.</span></span> <span data-ttu-id="aac81-215">例如，可以将3.0、4.0 或5.0 指定为此参数的值。</span><span class="sxs-lookup"><span data-stu-id="aac81-215">For example, you can specify 3.0, 4.0, or 5.0 as the value of this parameter.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-216">-预发行版</span><span class="sxs-lookup"><span data-stu-id="aac81-216">-Prerelease</span></span>

<span data-ttu-id="aac81-217">指示模块为预发行版。</span><span class="sxs-lookup"><span data-stu-id="aac81-217">Indicates the module is prerelease.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-218">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="aac81-218">-PrivateData</span></span>

<span data-ttu-id="aac81-219">指定导入模块时传递给模块的数据。</span><span class="sxs-lookup"><span data-stu-id="aac81-219">Specifies data that is passed to the module when it's imported.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-220">-ProcessorArchitecture</span><span class="sxs-lookup"><span data-stu-id="aac81-220">-ProcessorArchitecture</span></span>

<span data-ttu-id="aac81-221">指定模块需要的处理器体系结构。</span><span class="sxs-lookup"><span data-stu-id="aac81-221">Specifies the processor architecture that the module requires.</span></span>

<span data-ttu-id="aac81-222">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="aac81-222">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="aac81-223">Amd64</span><span class="sxs-lookup"><span data-stu-id="aac81-223">Amd64</span></span>
- <span data-ttu-id="aac81-224">Arm</span><span class="sxs-lookup"><span data-stu-id="aac81-224">Arm</span></span>
- <span data-ttu-id="aac81-225">IA64</span><span class="sxs-lookup"><span data-stu-id="aac81-225">IA64</span></span>
- <span data-ttu-id="aac81-226">MSIL</span><span class="sxs-lookup"><span data-stu-id="aac81-226">MSIL</span></span>
- <span data-ttu-id="aac81-227">无 (未知或未指定的) </span><span class="sxs-lookup"><span data-stu-id="aac81-227">None (unknown or unspecified)</span></span>
- <span data-ttu-id="aac81-228">X86</span><span class="sxs-lookup"><span data-stu-id="aac81-228">X86</span></span>

```yaml
Type: System.Reflection.ProcessorArchitecture
Parameter Sets: (All)
Aliases:
Accepted values: None, MSIL, X86, IA64, Amd64, Arm

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-229">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="aac81-229">-ProjectUri</span></span>

<span data-ttu-id="aac81-230">指定有关此项目的网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="aac81-230">Specifies the URL of a web page about this project.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-231">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="aac81-231">-ReleaseNotes</span></span>

<span data-ttu-id="aac81-232">指定一个字符串数组，其中包含要用于此版本的脚本的发行说明或注释。</span><span class="sxs-lookup"><span data-stu-id="aac81-232">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-233">-RequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="aac81-233">-RequireLicenseAcceptance</span></span>

<span data-ttu-id="aac81-234">指定模块需要接受许可证。</span><span class="sxs-lookup"><span data-stu-id="aac81-234">Specifies that a license acceptance is required for the module.</span></span>

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

### <span data-ttu-id="aac81-235">-RequiredAssemblies</span><span class="sxs-lookup"><span data-stu-id="aac81-235">-RequiredAssemblies</span></span>

<span data-ttu-id="aac81-236">指定模块需要的程序集 (`.dll`) 文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-236">Specifies the assembly (`.dll`) files that the module requires.</span></span> <span data-ttu-id="aac81-237">输入程序集文件名。</span><span class="sxs-lookup"><span data-stu-id="aac81-237">Enter the assembly file names.</span></span>
<span data-ttu-id="aac81-238">PowerShell 在更新类型或格式、导入嵌套模块或导入在 **RootModule** 项的值中指定的模块文件之前加载指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="aac81-238">PowerShell loads the specified assemblies before updating types or formats, importing nested modules, or importing the module file that is specified in the value of the **RootModule** key.</span></span>

<span data-ttu-id="aac81-239">使用此参数可指定模块所需的所有程序集，包括必须加载以便更新 **FormatsToProcess** 或 **TypesToProcess** 键中列出的任何格式设置或类型文件的程序集，即使这些程序集也在 **NestedModules** 项中作为二进制模块列出也是如此。</span><span class="sxs-lookup"><span data-stu-id="aac81-239">Use this parameter to specify all the assemblies that the module requires, including assemblies that must be loaded to update any formatting or type files that are listed in the **FormatsToProcess** or **TypesToProcess** keys, even if those assemblies are also listed as binary modules in the **NestedModules** key.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-240">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="aac81-240">-RequiredModules</span></span>

<span data-ttu-id="aac81-241">指定必须处于全局会话状态的模块。</span><span class="sxs-lookup"><span data-stu-id="aac81-241">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="aac81-242">如果所需模块未处于全局会话状态，则 PowerShell 会将其导入。</span><span class="sxs-lookup"><span data-stu-id="aac81-242">If the required modules aren't in the global session state, PowerShell imports them.</span></span> <span data-ttu-id="aac81-243">如果所需模块不可用，则该 `Import-Module` 命令将失败。</span><span class="sxs-lookup"><span data-stu-id="aac81-243">If the required modules aren't available, the `Import-Module` command fails.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-244">-RootModule</span><span class="sxs-lookup"><span data-stu-id="aac81-244">-RootModule</span></span>

<span data-ttu-id="aac81-245">指定模块的主文件或根文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-245">Specifies the primary or root file of the module.</span></span> <span data-ttu-id="aac81-246">输入脚本的文件名 (`.ps1`) 、脚本模块 (`.psm1`) 、模块清单 () `.psd1` 、程序集 (`.dll`) 、cmdlet 定义 XML 文件 (`.cdxml`) 或 () 工作流 `.xaml` 。</span><span class="sxs-lookup"><span data-stu-id="aac81-246">Enter the file name of a script (`.ps1`), a script module (`.psm1`), a module manifest (`.psd1`), an assembly (`.dll`), a cmdlet definition XML file (`.cdxml`), or a workflow (`.xaml`).</span></span> <span data-ttu-id="aac81-247">导入模块时，从根模块文件导出的成员将导入到调用方的会话状态中。</span><span class="sxs-lookup"><span data-stu-id="aac81-247">When the module is imported, the members that are exported from the root module file are imported into the caller's session state.</span></span>

<span data-ttu-id="aac81-248">如果某个模块具有清单文件，并且未在 **RootModule** 项中指定任何根文件，则该清单将成为该模块的主文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-248">If a module has a manifest file and no root file has been specified in the **RootModule** key, the manifest becomes the primary file for the module.</span></span> <span data-ttu-id="aac81-249">而且，模块将成为清单模块 (ModuleType = Manifest) 。</span><span class="sxs-lookup"><span data-stu-id="aac81-249">And, the module becomes a manifest module (ModuleType = Manifest).</span></span>

<span data-ttu-id="aac81-250">若要从 `.psm1` `.dll` 具有清单的模块中的或文件中导出成员，必须在清单中的 **RootModule** 或 **NestedModules** 键的值中指定这些文件的名称。</span><span class="sxs-lookup"><span data-stu-id="aac81-250">To export members from `.psm1` or `.dll` files in a module that has a manifest, the names of those files must be specified in the values of the **RootModule** or **NestedModules** keys in the manifest.</span></span> <span data-ttu-id="aac81-251">否则，不会导出它们的成员。</span><span class="sxs-lookup"><span data-stu-id="aac81-251">Otherwise, their members aren't exported.</span></span>

<span data-ttu-id="aac81-252">在 PowerShell 2.0 中，此密钥称为 **ModuleToProcess** 。</span><span class="sxs-lookup"><span data-stu-id="aac81-252">In PowerShell 2.0, this key was called **ModuleToProcess** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-253">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="aac81-253">-ScriptsToProcess</span></span>

<span data-ttu-id="aac81-254">指定 `.ps1` 导入模块时，在调用方的会话状态中运行的脚本 () 文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-254">Specifies script (`.ps1`) files that run in the caller's session state when the module is imported.</span></span>
<span data-ttu-id="aac81-255">可以像使用登录脚本一样使用这些脚本来准备环境。</span><span class="sxs-lookup"><span data-stu-id="aac81-255">You can use these scripts to prepare an environment, just as you might use a login script.</span></span>

<span data-ttu-id="aac81-256">若要指定在模块的会话状态中运行的脚本，请使用 **NestedModules** 键。</span><span class="sxs-lookup"><span data-stu-id="aac81-256">To specify scripts that run in the module's session state, use the **NestedModules** key.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-257">-Tags</span><span class="sxs-lookup"><span data-stu-id="aac81-257">-Tags</span></span>

<span data-ttu-id="aac81-258">指定标记的数组。</span><span class="sxs-lookup"><span data-stu-id="aac81-258">Specifies an array of tags.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-259">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="aac81-259">-TypesToProcess</span></span>

<span data-ttu-id="aac81-260">指定 `.ps1xml` 导入模块时运行)  (类型文件。</span><span class="sxs-lookup"><span data-stu-id="aac81-260">Specifies the type files (`.ps1xml`) that run when the module is imported.</span></span>

<span data-ttu-id="aac81-261">导入模块时，PowerShell 将运行 `Update-TypeData` 具有指定文件的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aac81-261">When you import the module, PowerShell runs the `Update-TypeData` cmdlet with the specified files.</span></span>
<span data-ttu-id="aac81-262">由于类型文件不作用域，因此它们会影响会话中的所有会话状态。</span><span class="sxs-lookup"><span data-stu-id="aac81-262">Because type files aren't scoped, they affect all session states in the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aac81-263">-VariablesToExport</span><span class="sxs-lookup"><span data-stu-id="aac81-263">-VariablesToExport</span></span>

<span data-ttu-id="aac81-264">指定模块导出的变量。</span><span class="sxs-lookup"><span data-stu-id="aac81-264">Specifies the variables that the module exports.</span></span> <span data-ttu-id="aac81-265">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="aac81-265">Wildcards are permitted.</span></span>

<span data-ttu-id="aac81-266">使用此参数来限制由模块导出的变量。</span><span class="sxs-lookup"><span data-stu-id="aac81-266">Use this parameter to restrict the variables that are exported by the module.</span></span> <span data-ttu-id="aac81-267">**VariablesToExport** 可以从导出的变量列表中删除变量，但不能将变量添加到该列表中。</span><span class="sxs-lookup"><span data-stu-id="aac81-267">**VariablesToExport** can remove variables from the list of exported variables, but it can't add variables to the list.</span></span>

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

### <span data-ttu-id="aac81-268">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="aac81-268">-WhatIf</span></span>

<span data-ttu-id="aac81-269">显示运行时将发生 `Update-ModuleManifest` 的情况。</span><span class="sxs-lookup"><span data-stu-id="aac81-269">Shows what would happen if `Update-ModuleManifest` runs.</span></span> <span data-ttu-id="aac81-270">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="aac81-270">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="aac81-271">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="aac81-271">CommonParameters</span></span>

<span data-ttu-id="aac81-272">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="aac81-272">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aac81-273">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="aac81-273">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aac81-274">输入</span><span class="sxs-lookup"><span data-stu-id="aac81-274">INPUTS</span></span>

### <span data-ttu-id="aac81-275">System.String</span><span class="sxs-lookup"><span data-stu-id="aac81-275">System.String</span></span>

## <span data-ttu-id="aac81-276">输出</span><span class="sxs-lookup"><span data-stu-id="aac81-276">OUTPUTS</span></span>

### <span data-ttu-id="aac81-277">System.Object</span><span class="sxs-lookup"><span data-stu-id="aac81-277">System.Object</span></span>

## <span data-ttu-id="aac81-278">注释</span><span class="sxs-lookup"><span data-stu-id="aac81-278">NOTES</span></span>

## <span data-ttu-id="aac81-279">相关链接</span><span class="sxs-lookup"><span data-stu-id="aac81-279">RELATED LINKS</span></span>
