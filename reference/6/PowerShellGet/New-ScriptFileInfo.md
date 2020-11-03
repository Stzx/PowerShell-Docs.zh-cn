---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/01/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/new-scriptfileinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ScriptFileInfo
ms.openlocfilehash: 649110ddb4147587dbff31d7b8410b706decca89
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198414"
---
# <span data-ttu-id="9a143-103">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="9a143-103">New-ScriptFileInfo</span></span>

## <span data-ttu-id="9a143-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9a143-104">SYNOPSIS</span></span>
<span data-ttu-id="9a143-105">使用元数据创建脚本文件。</span><span class="sxs-lookup"><span data-stu-id="9a143-105">Creates a script file with metadata.</span></span>

## <span data-ttu-id="9a143-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9a143-106">SYNTAX</span></span>

### <span data-ttu-id="9a143-107">全部</span><span class="sxs-lookup"><span data-stu-id="9a143-107">All</span></span>

```
New-ScriptFileInfo [[-Path] <String>] [-Version <String>] [-Author <String>] -Description <String>
 [-Guid <Guid>] [-CompanyName <String>] [-Copyright <String>] [-RequiredModules <Object[]>]
 [-ExternalModuleDependencies <String[]>] [-RequiredScripts <String[]>]
 [-ExternalScriptDependencies <String[]>] [-Tags <String[]>] [-ProjectUri <Uri>] [-LicenseUri <Uri>]
 [-IconUri <Uri>] [-ReleaseNotes <String[]>] [-PrivateData <String>] [-PassThru] [-Force] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9a143-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9a143-108">DESCRIPTION</span></span>

<span data-ttu-id="9a143-109">`New-ScriptFileInfo`Cmdlet 将创建一个 PowerShell 脚本文件，包括有关该脚本的元数据。</span><span class="sxs-lookup"><span data-stu-id="9a143-109">The `New-ScriptFileInfo` cmdlet creates a PowerShell script file, including metadata about the script.</span></span>

<span data-ttu-id="9a143-110">这些示例使用展开将参数传递给 `New-ScriptFileInfo` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a143-110">The examples use splatting to pass parameters to the `New-ScriptFileInfo` cmdlet.</span></span> <span data-ttu-id="9a143-111">有关详细信息，请参阅 [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="9a143-111">For more information, see [about_Splatting](../Microsoft.Powershell.Core/About/about_splatting.md).</span></span>

## <span data-ttu-id="9a143-112">示例</span><span class="sxs-lookup"><span data-stu-id="9a143-112">EXAMPLES</span></span>

### <span data-ttu-id="9a143-113">示例1：创建脚本文件并指定其版本、作者和说明</span><span class="sxs-lookup"><span data-stu-id="9a143-113">Example 1: Create a script file and specify its version, author, and description</span></span>

<span data-ttu-id="9a143-114">在此示例中，将创建一个脚本文件，并在 PowerShell 控制台中显示其内容。</span><span class="sxs-lookup"><span data-stu-id="9a143-114">In this example, a script file is created and its contents are displayed in the PowerShell console.</span></span>

```powershell
$Parms = @{
  Path = "C:\Test\Temp-Scriptfile.ps1"
  Version = "1.0"
  Author = "pattif@contoso.com"
  Description = "My test script file description goes here"
  }
New-ScriptFileInfo @Parms
Get-Content -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
<#PSScriptInfo

.VERSION 1.0

.GUID 3bb10ee7-38c1-41b9-88ea-16899164fc19

.AUTHOR pattif@contoso.com

.COMPANYNAME

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
 My test script file description goes here

#>
Param()
```

<span data-ttu-id="9a143-115">`New-ScriptFileInfo`Cmdlet 使用展开为脚本配置多个参数。</span><span class="sxs-lookup"><span data-stu-id="9a143-115">The `New-ScriptFileInfo` cmdlet uses splatting to configure several parameters for the script.</span></span>
<span data-ttu-id="9a143-116">**路径** 设置脚本的位置和名称。</span><span class="sxs-lookup"><span data-stu-id="9a143-116">**Path** sets the location and name of the script.</span></span> <span data-ttu-id="9a143-117">**版本** 指定脚本的版本号。</span><span class="sxs-lookup"><span data-stu-id="9a143-117">**Version** specifies the script's version number.</span></span> <span data-ttu-id="9a143-118">**Author** 是创建脚本的人员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9a143-118">**Author** is the email address of the person who created the script.</span></span> <span data-ttu-id="9a143-119">**说明** 说明了该脚本的用途。</span><span class="sxs-lookup"><span data-stu-id="9a143-119">**Description** explains the script's purpose.</span></span>

<span data-ttu-id="9a143-120">创建脚本后， `Get-Content` 使用 **Path** 参数查找该脚本。</span><span class="sxs-lookup"><span data-stu-id="9a143-120">After the script is created, `Get-Content` uses the **Path** parameter to locate the script.</span></span> <span data-ttu-id="9a143-121">该脚本的内容将显示在 PowerShell 控制台中。</span><span class="sxs-lookup"><span data-stu-id="9a143-121">The script's contents are displayed in the PowerShell console.</span></span>

### <span data-ttu-id="9a143-122">示例2：测试脚本文件</span><span class="sxs-lookup"><span data-stu-id="9a143-122">Example 2: Test a script file</span></span>

<span data-ttu-id="9a143-123">在此示例中，对在 **示例 1** 中创建的脚本的元数据进行测试。</span><span class="sxs-lookup"><span data-stu-id="9a143-123">In this example, the metadata for the script created in **Example 1** is tested.</span></span>

```powershell
Test-ScriptFileInfo -Path C:\Test\Temp-Scriptfile.ps1
```

```Output
Version   Name                  Author               Description
-------   ----                  ------               -----------
1.0       Temp-Scriptfile       pattif@contoso.com   My test script file description goes here
```

<span data-ttu-id="9a143-124">`Test-ScriptFileInfo`Cmdlet 使用 **Path** 参数指定脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9a143-124">The `Test-ScriptFileInfo` cmdlet uses the **Path** parameter to specify the script file's location.</span></span>

### <span data-ttu-id="9a143-125">示例3：创建包含所有元数据属性的脚本文件</span><span class="sxs-lookup"><span data-stu-id="9a143-125">Example 3: Create a script file with all the metadata properties</span></span>

<span data-ttu-id="9a143-126">此示例使用展开创建一个名为的脚本文件 `New-ScriptFile.ps1` ，其中包含所有元数据属性。</span><span class="sxs-lookup"><span data-stu-id="9a143-126">This example uses splatting to create a script file named `New-ScriptFile.ps1` that includes all its metadata properties.</span></span> <span data-ttu-id="9a143-127">**Verbose** 参数指定在创建脚本时显示详细输出。</span><span class="sxs-lookup"><span data-stu-id="9a143-127">The **Verbose** parameter specifies that verbose output is displayed as the script is created.</span></span>

```powershell
$Parms = @{
 Path = "C:\Test\New-ScriptFile.ps1"
 Verbose = $True
 Version = "1.0"
 Author = "pattif@contoso.com"
 Description = "My new script file test"
 CompanyName = "Contoso Corporation"
 Copyright = "2019 Contoso Corporation. All rights reserved."
 ExternalModuleDependencies = "ff","bb"
 RequiredScripts = "Start-WFContosoServer", "Stop-ContosoServerScript"
 ExternalScriptDependencies = "Stop-ContosoServerScript"
 Tags = @("Tag1", "Tag2", "Tag3")
 ProjectUri = "https://contoso.com"
 LicenseUri = "https://contoso.com/License"
 IconUri = "https://contoso.com/Icon"
 PassThru = $True
 ReleaseNotes = @("Contoso script now supports the following features:",
   "Feature 1",
   "Feature 2",
   "Feature 3",
   "Feature 4",
   "Feature 5")
 RequiredModules =
   "1",
   "2",
   "RequiredModule1",
   @{ModuleName="RequiredModule2";ModuleVersion="1.0"},
   @{ModuleName="RequiredModule3";RequiredVersion="2.0"},
   "ExternalModule1"
 }
New-ScriptFileInfo @Parms
```

```Output
VERBOSE: Performing the operation "Creating the 'C:\Test\New-ScriptFile.ps1'
  PowerShell Script file" on target "C:\Test\New-ScriptFile.ps1".

<#PSScriptInfo

.VERSION 1.0

.GUID 4fabe8c7-7862-45b1-a72e-1352a433b77d

.AUTHOR pattif@contoso.com

.COMPANYNAME Contoso Corporation

.COPYRIGHT 2019 Contoso Corporation. All rights reserved.

.TAGS Tag1 Tag2 Tag3

.LICENSEURI https://contoso.com/License

.PROJECTURI https://contoso.com/

.ICONURI https://contoso.com/Icon

.EXTERNALMODULEDEPENDENCIES ff,bb

.REQUIREDSCRIPTS Start-WFContosoServer,Stop-ContosoServerScript

.EXTERNALSCRIPTDEPENDENCIES Stop-ContosoServerScript

.RELEASENOTES
Contoso script now supports the following features:
Feature 1
Feature 2
Feature 3
Feature 4
Feature 5

.PRIVATEDATA

#>

#Requires -Module 1
#Requires -Module 2
#Requires -Module RequiredModule1
#Requires -Module @{ModuleName = 'RequiredModule2'; ModuleVersion = '1.0'}
#Requires -Module @{RequiredVersion = '2.0'; ModuleName = 'RequiredModule3'}
#Requires -Module ExternalModule1

<#

.DESCRIPTION
 My new script file test

#>
Param()
```

## <span data-ttu-id="9a143-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9a143-128">PARAMETERS</span></span>

### <span data-ttu-id="9a143-129">-作者</span><span class="sxs-lookup"><span data-stu-id="9a143-129">-Author</span></span>

<span data-ttu-id="9a143-130">指定脚本作者。</span><span class="sxs-lookup"><span data-stu-id="9a143-130">Specifies the script author.</span></span>

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

### <span data-ttu-id="9a143-131">-公司名称</span><span class="sxs-lookup"><span data-stu-id="9a143-131">-CompanyName</span></span>

<span data-ttu-id="9a143-132">指定创建脚本的公司或供应商。</span><span class="sxs-lookup"><span data-stu-id="9a143-132">Specifies the company or vendor who created the script.</span></span>

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

### <span data-ttu-id="9a143-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9a143-133">-Confirm</span></span>

<span data-ttu-id="9a143-134">提示你在运行之前进行确认 `New-ScriptFileInfo` 。</span><span class="sxs-lookup"><span data-stu-id="9a143-134">Prompts you for confirmation before running the `New-ScriptFileInfo`.</span></span>

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

### <span data-ttu-id="9a143-135">-版权所有</span><span class="sxs-lookup"><span data-stu-id="9a143-135">-Copyright</span></span>

<span data-ttu-id="9a143-136">指定脚本的版权声明。</span><span class="sxs-lookup"><span data-stu-id="9a143-136">Specifies a copyright statement for the script.</span></span>

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

### <span data-ttu-id="9a143-137">-Description</span><span class="sxs-lookup"><span data-stu-id="9a143-137">-Description</span></span>

<span data-ttu-id="9a143-138">指定脚本的描述。</span><span class="sxs-lookup"><span data-stu-id="9a143-138">Specifies a description for the script.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9a143-139">-ExternalModuleDependencies</span><span class="sxs-lookup"><span data-stu-id="9a143-139">-ExternalModuleDependencies</span></span>

<span data-ttu-id="9a143-140">指定外部模块依赖项的数组。</span><span class="sxs-lookup"><span data-stu-id="9a143-140">Specifies an array of external module dependencies.</span></span>

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

### <span data-ttu-id="9a143-141">-ExternalScriptDependencies</span><span class="sxs-lookup"><span data-stu-id="9a143-141">-ExternalScriptDependencies</span></span>

<span data-ttu-id="9a143-142">指定外部脚本依赖项的数组。</span><span class="sxs-lookup"><span data-stu-id="9a143-142">Specifies an array of external script dependencies.</span></span>

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

### <span data-ttu-id="9a143-143">-Force</span><span class="sxs-lookup"><span data-stu-id="9a143-143">-Force</span></span>

<span data-ttu-id="9a143-144">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="9a143-144">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="9a143-145">-Guid</span><span class="sxs-lookup"><span data-stu-id="9a143-145">-Guid</span></span>

<span data-ttu-id="9a143-146">指定脚本的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9a143-146">Specifies a unique ID for the script.</span></span>

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

### <span data-ttu-id="9a143-147">-IconUri</span><span class="sxs-lookup"><span data-stu-id="9a143-147">-IconUri</span></span>

<span data-ttu-id="9a143-148">指定脚本的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="9a143-148">Specifies the URL of an icon for the script.</span></span> <span data-ttu-id="9a143-149">指定的图标将显示在该脚本的库网页上。</span><span class="sxs-lookup"><span data-stu-id="9a143-149">The specified icon is displayed on the gallery web page for the script.</span></span>

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

### <span data-ttu-id="9a143-150">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="9a143-150">-LicenseUri</span></span>

<span data-ttu-id="9a143-151">指定许可条款的 URL。</span><span class="sxs-lookup"><span data-stu-id="9a143-151">Specifies the URL of licensing terms.</span></span>

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

### <span data-ttu-id="9a143-152">-PassThru</span><span class="sxs-lookup"><span data-stu-id="9a143-152">-PassThru</span></span>

<span data-ttu-id="9a143-153">返回一个对象，该对象表示正在处理的项。</span><span class="sxs-lookup"><span data-stu-id="9a143-153">Returns an object that represents the item with which you're working.</span></span> <span data-ttu-id="9a143-154">默认情况下， `New-ScriptFileInfo` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="9a143-154">By default, `New-ScriptFileInfo` doesn't generate any output.</span></span>

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

### <span data-ttu-id="9a143-155">-Path</span><span class="sxs-lookup"><span data-stu-id="9a143-155">-Path</span></span>

<span data-ttu-id="9a143-156">指定保存脚本文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9a143-156">Specifies the location where the script file is saved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9a143-157">-PrivateData</span><span class="sxs-lookup"><span data-stu-id="9a143-157">-PrivateData</span></span>

<span data-ttu-id="9a143-158">指定脚本的专用数据。</span><span class="sxs-lookup"><span data-stu-id="9a143-158">Specifies private data for the script.</span></span>

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

### <span data-ttu-id="9a143-159">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="9a143-159">-ProjectUri</span></span>

<span data-ttu-id="9a143-160">指定有关此项目的网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="9a143-160">Specifies the URL of a web page about this project.</span></span>

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

### <span data-ttu-id="9a143-161">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="9a143-161">-ReleaseNotes</span></span>

<span data-ttu-id="9a143-162">指定一个字符串数组，其中包含此版本的脚本的用户要使用的发行说明或注释。</span><span class="sxs-lookup"><span data-stu-id="9a143-162">Specifies a string array that contains release notes or comments that you want available to users of this version of the script.</span></span>

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

### <span data-ttu-id="9a143-163">-RequiredModules</span><span class="sxs-lookup"><span data-stu-id="9a143-163">-RequiredModules</span></span>

<span data-ttu-id="9a143-164">指定必须处于全局会话状态的模块。</span><span class="sxs-lookup"><span data-stu-id="9a143-164">Specifies modules that must be in the global session state.</span></span> <span data-ttu-id="9a143-165">如果所需模块未处于全局会话状态，则 PowerShell 会将其导入。</span><span class="sxs-lookup"><span data-stu-id="9a143-165">If the required modules aren't in the global session state, PowerShell imports them.</span></span>

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

### <span data-ttu-id="9a143-166">-RequiredScripts</span><span class="sxs-lookup"><span data-stu-id="9a143-166">-RequiredScripts</span></span>

<span data-ttu-id="9a143-167">指定所需脚本的数组。</span><span class="sxs-lookup"><span data-stu-id="9a143-167">Specifies an array of required scripts.</span></span>

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

### <span data-ttu-id="9a143-168">-Tags</span><span class="sxs-lookup"><span data-stu-id="9a143-168">-Tags</span></span>

<span data-ttu-id="9a143-169">指定标记的数组。</span><span class="sxs-lookup"><span data-stu-id="9a143-169">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="9a143-170">-Version</span><span class="sxs-lookup"><span data-stu-id="9a143-170">-Version</span></span>

<span data-ttu-id="9a143-171">指定脚本的版本。</span><span class="sxs-lookup"><span data-stu-id="9a143-171">Specifies the version of the script.</span></span>

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

### <span data-ttu-id="9a143-172">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9a143-172">-WhatIf</span></span>

<span data-ttu-id="9a143-173">显示运行时将发生 `New-ScriptFileInfo` 的情况。</span><span class="sxs-lookup"><span data-stu-id="9a143-173">Shows what would happen if `New-ScriptFileInfo` runs.</span></span> <span data-ttu-id="9a143-174">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="9a143-174">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="9a143-175">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9a143-175">CommonParameters</span></span>

<span data-ttu-id="9a143-176">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9a143-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9a143-177">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9a143-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9a143-178">输入</span><span class="sxs-lookup"><span data-stu-id="9a143-178">INPUTS</span></span>

### <span data-ttu-id="9a143-179">System.String</span><span class="sxs-lookup"><span data-stu-id="9a143-179">System.String</span></span>

## <span data-ttu-id="9a143-180">输出</span><span class="sxs-lookup"><span data-stu-id="9a143-180">OUTPUTS</span></span>

### <span data-ttu-id="9a143-181">System.Object</span><span class="sxs-lookup"><span data-stu-id="9a143-181">System.Object</span></span>

## <span data-ttu-id="9a143-182">注释</span><span class="sxs-lookup"><span data-stu-id="9a143-182">NOTES</span></span>

## <span data-ttu-id="9a143-183">相关链接</span><span class="sxs-lookup"><span data-stu-id="9a143-183">RELATED LINKS</span></span>

[<span data-ttu-id="9a143-184">about_Splatting</span><span class="sxs-lookup"><span data-stu-id="9a143-184">about_Splatting</span></span>](../Microsoft.Powershell.Core/About/about_splatting.md)

[<span data-ttu-id="9a143-185">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="9a143-185">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="9a143-186">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="9a143-186">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
