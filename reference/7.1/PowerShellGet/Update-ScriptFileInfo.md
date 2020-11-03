---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-scriptfileinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-ScriptFileInfo
ms.openlocfilehash: 443186a63819809a42d953b60232c9745818fb4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198761"
---
# <span data-ttu-id="ab272-103">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="ab272-103">Update-ScriptFileInfo</span></span>

## <span data-ttu-id="ab272-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ab272-104">SYNOPSIS</span></span>
<span data-ttu-id="ab272-105">更新脚本的信息。</span><span class="sxs-lookup"><span data-stu-id="ab272-105">Updates information for a script.</span></span>

## <span data-ttu-id="ab272-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab272-106">SYNTAX</span></span>

### <span data-ttu-id="ab272-107">PathParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="ab272-107">PathParameterSet (Default)</span></span>

```
Update-ScriptFileInfo [-Path] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ab272-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="ab272-108">LiteralPathParameterSet</span></span>

```
Update-ScriptFileInfo [-LiteralPath] <String> [-Version <String>] [-Author <String>] [-Guid <Guid>]
 [-Description <String>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ab272-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab272-109">DESCRIPTION</span></span>

<span data-ttu-id="ab272-110">`Update-ScriptFileInfo`Cmdlet 将更新脚本的属性值。</span><span class="sxs-lookup"><span data-stu-id="ab272-110">The `Update-ScriptFileInfo` cmdlet updates a script's property values.</span></span> <span data-ttu-id="ab272-111">例如，"版本"、"作者" 或 "说明" 的值。</span><span class="sxs-lookup"><span data-stu-id="ab272-111">For example, the values for version, author, or description.</span></span>

## <span data-ttu-id="ab272-112">示例</span><span class="sxs-lookup"><span data-stu-id="ab272-112">EXAMPLES</span></span>

### <span data-ttu-id="ab272-113">示例1：更新脚本文件的版本</span><span class="sxs-lookup"><span data-stu-id="ab272-113">Example 1: Update the version of a script file</span></span>

<span data-ttu-id="ab272-114">在此示例中，使用新属性值更新现有脚本文件。</span><span class="sxs-lookup"><span data-stu-id="ab272-114">In this example, an existing script file is updated with new property values.</span></span>

<span data-ttu-id="ab272-115">展开用于将参数传递给 `Update-ScriptFileInfo` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ab272-115">Splatting is used to pass parameters to the `Update-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="ab272-116">有关详细信息，请参阅 [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="ab272-116">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "2.0"
  Author = "bob@contoso.com"
  CompanyName = "Contoso"
  Description = "This is the updated description"
  }
Update-ScriptFileInfo @Parms -PassThru
```

```Output
<#PSScriptInfo

.VERSION 2.0

.GUID 4609f00c-e850-4d3f-9c69-3741e56e4133

.AUTHOR bob@contoso.com

.COMPANYNAME Contoso

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

.PRIVATEDATA

#>

<#

.DESCRIPTION
This is the updated description

#>
Param()
```

<span data-ttu-id="ab272-117">`$Parms` 存储 **路径** 、 **版本** 、 **作者** 、 **公司名称** 和 **说明** 的参数值。</span><span class="sxs-lookup"><span data-stu-id="ab272-117">`$Parms` stores the parameter values for **Path** , **Version** , **Author** , **CompanyName** , and **Description** .</span></span> <span data-ttu-id="ab272-118">`Update-ScriptFileInfo` 从获取参数值 `@Parms` ，并更新脚本。</span><span class="sxs-lookup"><span data-stu-id="ab272-118">`Update-ScriptFileInfo` gets the parameter values from `@Parms` and updates the script.</span></span> <span data-ttu-id="ab272-119">**PassThru** 参数显示 PowerShell 控制台中的脚本内容。</span><span class="sxs-lookup"><span data-stu-id="ab272-119">The **PassThru** parameter displays the script's contents in the PowerShell console.</span></span>

## <span data-ttu-id="ab272-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab272-120">PARAMETERS</span></span>

### <span data-ttu-id="ab272-121">-作者</span><span class="sxs-lookup"><span data-stu-id="ab272-121">-Author</span></span>

<span data-ttu-id="ab272-122">指定脚本作者。</span><span class="sxs-lookup"><span data-stu-id="ab272-122">Specifies the script author.</span></span>

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

### <span data-ttu-id="ab272-123">-公司名称</span><span class="sxs-lookup"><span data-stu-id="ab272-123">-CompanyName</span></span>

<span data-ttu-id="ab272-124">指定创建脚本的公司或供应商。</span><span class="sxs-lookup"><span data-stu-id="ab272-124">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="ab272-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ab272-125">-Confirm</span></span>

<span data-ttu-id="ab272-126">在运行之前提示你进行确认 `Update-ScriptFileInfo` 。</span><span class="sxs-lookup"><span data-stu-id="ab272-126">Prompts you for confirmation before running `Update-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="ab272-127">-版权所有</span><span class="sxs-lookup"><span data-stu-id="ab272-127">-Copyright</span></span>

<span data-ttu-id="ab272-128">指定脚本的版权声明。</span><span class="sxs-lookup"><span data-stu-id="ab272-128">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="ab272-129">-Description</span><span class="sxs-lookup"><span data-stu-id="ab272-129">-Description</span></span>

<span data-ttu-id="ab272-130">指定脚本的描述。</span><span class="sxs-lookup"><span data-stu-id="ab272-130">Specifies a description for the script.</span></span>

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

### <span data-ttu-id="ab272-131">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="ab272-131">-ExternalModuleDependencies</span></span>

<span data-ttu-id="ab272-132">指定外部模块依赖项的数组。</span><span class="sxs-lookup"><span data-stu-id="ab272-132">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="ab272-133">-ExternalScriptDependencies</span><span class="sxs-lookup"><span data-stu-id="ab272-133">-ExternalScriptDependencies</span></span>

<span data-ttu-id="ab272-134">指定外部脚本依赖项的数组。</span><span class="sxs-lookup"><span data-stu-id="ab272-134">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="ab272-135">-Force</span><span class="sxs-lookup"><span data-stu-id="ab272-135">-Force</span></span>

<span data-ttu-id="ab272-136">强制 `Update-ScriptFileInfo` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="ab272-136">Forces `Update-ScriptFileInfo` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ab272-137">-Guid</span><span class="sxs-lookup"><span data-stu-id="ab272-137">-Guid</span></span>

<span data-ttu-id="ab272-138">指定脚本的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ab272-138">Specifies a unique ID for a script.</span></span>

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

### <span data-ttu-id="ab272-139">-IconUri</span><span class="sxs-lookup"><span data-stu-id="ab272-139">-IconUri</span></span>

<span data-ttu-id="ab272-140">指定脚本的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="ab272-140">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="ab272-141">指定的图标将显示在该脚本的库网页上。</span><span class="sxs-lookup"><span data-stu-id="ab272-141">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="ab272-142">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="ab272-142">-LicenseUri</span></span>

<span data-ttu-id="ab272-143">指定许可条款的 URL。</span><span class="sxs-lookup"><span data-stu-id="ab272-143">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="ab272-144">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ab272-144">-LiteralPath</span></span>

<span data-ttu-id="ab272-145">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="ab272-145">Specifies a path to one or more locations.</span></span> <span data-ttu-id="ab272-146">**LiteralPath** 参数的值完全按输入方式使用。</span><span class="sxs-lookup"><span data-stu-id="ab272-146">The **LiteralPath** parameter's value is used exactly as it's entered.</span></span> <span data-ttu-id="ab272-147">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="ab272-147">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ab272-148">如果路径包含转义符，请将其括在单引号内。</span><span class="sxs-lookup"><span data-stu-id="ab272-148">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="ab272-149">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="ab272-149">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ab272-150">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ab272-150">-PassThru</span></span>

<span data-ttu-id="ab272-151">返回一个对象，该对象表示正在处理的项。</span><span class="sxs-lookup"><span data-stu-id="ab272-151">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="ab272-152">默认情况下， `Update-ScriptFileInfo` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ab272-152">By default, `Update-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="ab272-153">-Path</span><span class="sxs-lookup"><span data-stu-id="ab272-153">-Path</span></span>

<span data-ttu-id="ab272-154">指定脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="ab272-154">Specifies the script file's location.</span></span> <span data-ttu-id="ab272-155">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ab272-155">Wildcards are permitted.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ab272-156">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="ab272-156">-PrivateData</span></span>

<span data-ttu-id="ab272-157">指定脚本的专用数据。</span><span class="sxs-lookup"><span data-stu-id="ab272-157">Specifies the private data for the script.</span></span>

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

### <span data-ttu-id="ab272-158">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="ab272-158">-ProjectUri</span></span>

<span data-ttu-id="ab272-159">指定有关此项目的网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="ab272-159">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="ab272-160">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="ab272-160">-ReleaseNotes</span></span>

<span data-ttu-id="ab272-161">指定一个字符串数组，其中包含要用于此版本的脚本的发行说明或注释。</span><span class="sxs-lookup"><span data-stu-id="ab272-161">Specifies a string array that contains release notes or comments that you want available for this version of the script.</span></span>

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

### <span data-ttu-id="ab272-162">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="ab272-162">-RequiredModules</span></span>

<span data-ttu-id="ab272-163">指定必须处于全局会话状态的模块。</span><span class="sxs-lookup"><span data-stu-id="ab272-163">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="ab272-164">如果所需模块未处于全局会话状态，则 PowerShell 会将其导入。</span><span class="sxs-lookup"><span data-stu-id="ab272-164">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="ab272-165">-RequiredScripts</span><span class="sxs-lookup"><span data-stu-id="ab272-165">-RequiredScripts</span></span>

<span data-ttu-id="ab272-166">指定所需脚本的数组。</span><span class="sxs-lookup"><span data-stu-id="ab272-166">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="ab272-167">-Tags</span><span class="sxs-lookup"><span data-stu-id="ab272-167">-Tags</span></span>

<span data-ttu-id="ab272-168">指定标记的数组。</span><span class="sxs-lookup"><span data-stu-id="ab272-168">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="ab272-169">-Version</span><span class="sxs-lookup"><span data-stu-id="ab272-169">-Version</span></span>

<span data-ttu-id="ab272-170">指定脚本的版本。</span><span class="sxs-lookup"><span data-stu-id="ab272-170">Specifies the script's version.</span></span>

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

### <span data-ttu-id="ab272-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ab272-171">-WhatIf</span></span>

<span data-ttu-id="ab272-172">显示运行时将发生 `Update-ScriptFileInfo` 的情况。</span><span class="sxs-lookup"><span data-stu-id="ab272-172">Shows what would happen if `Update-ScriptFileInfo` runs.</span></span> <span data-ttu-id="ab272-173">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ab272-173">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="ab272-174">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ab272-174">CommonParameters</span></span>

<span data-ttu-id="ab272-175">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ab272-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab272-176">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ab272-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab272-177">输入</span><span class="sxs-lookup"><span data-stu-id="ab272-177">INPUTS</span></span>

### <span data-ttu-id="ab272-178">System.String</span><span class="sxs-lookup"><span data-stu-id="ab272-178">System.String</span></span>

## <span data-ttu-id="ab272-179">输出</span><span class="sxs-lookup"><span data-stu-id="ab272-179">OUTPUTS</span></span>

### <span data-ttu-id="ab272-180">System.Object</span><span class="sxs-lookup"><span data-stu-id="ab272-180">System.Object</span></span>

## <span data-ttu-id="ab272-181">注释</span><span class="sxs-lookup"><span data-stu-id="ab272-181">NOTES</span></span>

<span data-ttu-id="ab272-182">使用 `Test-ScriptFileInfo` cmdlet 验证脚本的元数据。</span><span class="sxs-lookup"><span data-stu-id="ab272-182">Use the `Test-ScriptFileInfo` cmdlet to validate a script's metadata.</span></span> <span data-ttu-id="ab272-183">脚本必须包含版本、GUID、说明和作者的值。</span><span class="sxs-lookup"><span data-stu-id="ab272-183">Scripts must include values for version, GUID, description, and author.</span></span>

## <span data-ttu-id="ab272-184">相关链接</span><span class="sxs-lookup"><span data-stu-id="ab272-184">RELATED LINKS</span></span>

[<span data-ttu-id="ab272-185">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="ab272-185">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="ab272-186">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="ab272-186">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

