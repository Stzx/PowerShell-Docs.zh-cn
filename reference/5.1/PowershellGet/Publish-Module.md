---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: 50f873e6691ead7c220b6250458f4fdf8a90af22
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198239"
---
# <span data-ttu-id="281df-103">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="281df-103">Publish-Module</span></span>

## <span data-ttu-id="281df-104">摘要</span><span class="sxs-lookup"><span data-stu-id="281df-104">SYNOPSIS</span></span>
<span data-ttu-id="281df-105">将指定模块从本机计算机发布到联机库。</span><span class="sxs-lookup"><span data-stu-id="281df-105">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="281df-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="281df-106">SYNTAX</span></span>

### <span data-ttu-id="281df-107">ModuleNameParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="281df-107">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="281df-108">ModulePathParameterSet</span><span class="sxs-lookup"><span data-stu-id="281df-108">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="281df-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="281df-109">DESCRIPTION</span></span>

<span data-ttu-id="281df-110">该 `Publish-Module` cmdlet 通过使用 API 密钥（存储在库中的用户配置文件的一部分），将模块发布到基于 NuGet 的联机库。</span><span class="sxs-lookup"><span data-stu-id="281df-110">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="281df-111">可根据模块的名称或包含模块的文件夹路径指定要发布的模块。</span><span class="sxs-lookup"><span data-stu-id="281df-111">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="281df-112">按名称指定模块时，将 `Publish-Module` 发布通过运行找到的第一个模块 `Get-Module -ListAvailable <Name>` 。</span><span class="sxs-lookup"><span data-stu-id="281df-112">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="281df-113">如果您指定要发布的模块的最低版本，将 `Publish-Module` 发布第一个版本大于或等于您指定的最低版本的模块。</span><span class="sxs-lookup"><span data-stu-id="281df-113">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="281df-114">发布模块需要在库页面显示的模块的元数据。</span><span class="sxs-lookup"><span data-stu-id="281df-114">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="281df-115">所需元数据包括模块名称、版本、说明和作者。</span><span class="sxs-lookup"><span data-stu-id="281df-115">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="281df-116">尽管大多数元数据都是从模块清单获取的，但必须在参数中指定某些元数据（如 `Publish-Module` **标记** 、 **ReleaseNote** 、 **IconUri** 、 **ProjectUri** 和 **LicenseUri** ），因为这些参数与基于 NuGet 的库中的字段匹配。</span><span class="sxs-lookup"><span data-stu-id="281df-116">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag** , **ReleaseNote** , **IconUri** , **ProjectUri** , and **LicenseUri** , because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="281df-117">示例</span><span class="sxs-lookup"><span data-stu-id="281df-117">EXAMPLES</span></span>

### <span data-ttu-id="281df-118">示例1：发布模块</span><span class="sxs-lookup"><span data-stu-id="281df-118">Example 1: Publish a module</span></span>

<span data-ttu-id="281df-119">在此示例中，使用 API 密钥将 MyDscModule 发布到联机库，以指示模块所有者的联机库帐户。</span><span class="sxs-lookup"><span data-stu-id="281df-119">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="281df-120">如果 MyDscModule 不是指定名称、版本、说明和作者的有效清单模块，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="281df-120">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="281df-121">示例2：使用库元数据发布模块</span><span class="sxs-lookup"><span data-stu-id="281df-121">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="281df-122">在此示例中，使用 API 密钥将 MyDscModule 发布到联机库，以指示模块所有者的库帐户。</span><span class="sxs-lookup"><span data-stu-id="281df-122">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="281df-123">提供的其他元数据将显示在库中模块的网页上。</span><span class="sxs-lookup"><span data-stu-id="281df-123">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="281df-124">所有者添加了两个用于模块的搜索标记，并将其与 Active Directory 相关联。已添加简短的发行说明。</span><span class="sxs-lookup"><span data-stu-id="281df-124">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="281df-125">如果 MyDscModule 不是指定名称、版本、说明和作者的有效清单模块，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="281df-125">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="281df-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="281df-126">PARAMETERS</span></span>

### <span data-ttu-id="281df-127">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="281df-127">-AllowPrerelease</span></span>

<span data-ttu-id="281df-128">允许发布标记为预发行的模块。</span><span class="sxs-lookup"><span data-stu-id="281df-128">Allows modules marked as prerelease to be published.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="281df-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="281df-129">-Confirm</span></span>

<span data-ttu-id="281df-130">提示你在运行之前进行确认 `Publish-Module` 。</span><span class="sxs-lookup"><span data-stu-id="281df-130">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="281df-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="281df-131">-Credential</span></span>

<span data-ttu-id="281df-132">指定有权为指定的包提供程序或源发布模块的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="281df-132">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="281df-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="281df-133">-Exclude</span></span>

<span data-ttu-id="281df-134">定义要从已发布的模块中排除的文件。</span><span class="sxs-lookup"><span data-stu-id="281df-134">Defines files to exclude from the published module.</span></span> <span data-ttu-id="281df-135">**排除** 参数支持是在 **PowershellGet** 版本2.0.0 中添加的。</span><span class="sxs-lookup"><span data-stu-id="281df-135">**Exclude** parameter support is add in **PowershellGet** version 2.0.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="281df-136">-Force</span><span class="sxs-lookup"><span data-stu-id="281df-136">-Force</span></span>

<span data-ttu-id="281df-137">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="281df-137">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="281df-138">-FormatVersion</span><span class="sxs-lookup"><span data-stu-id="281df-138">-FormatVersion</span></span>

<span data-ttu-id="281df-139">仅接受 **ValidateSet** 属性指定的有效值。</span><span class="sxs-lookup"><span data-stu-id="281df-139">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="281df-140">有关详细信息，请参阅 [ValidateSet 特性声明](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) 和 [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute)。</span><span class="sxs-lookup"><span data-stu-id="281df-140">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:
Accepted values: 2.0

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="281df-141">-IconUri</span><span class="sxs-lookup"><span data-stu-id="281df-141">-IconUri</span></span>

<span data-ttu-id="281df-142">指定模块的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="281df-142">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="281df-143">指定的图标显示在模块的库网页上。</span><span class="sxs-lookup"><span data-stu-id="281df-143">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="281df-144">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="281df-144">-LicenseUri</span></span>

<span data-ttu-id="281df-145">指定要发布的模块的许可条款 URL。</span><span class="sxs-lookup"><span data-stu-id="281df-145">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="281df-146">-Name</span><span class="sxs-lookup"><span data-stu-id="281df-146">-Name</span></span>

<span data-ttu-id="281df-147">指定要发布的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="281df-147">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="281df-148">`Publish-Module` 在中搜索指定的模块名称 `$Env:PSModulePath` 。</span><span class="sxs-lookup"><span data-stu-id="281df-148">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="281df-149">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="281df-149">-NuGetApiKey</span></span>

<span data-ttu-id="281df-150">指定要用于将模块发布到联机库的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="281df-150">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="281df-151">API 密钥是你的个人资料中的配置文件的一部分，可以在库中的用户帐户页面上找到。</span><span class="sxs-lookup"><span data-stu-id="281df-151">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="281df-152">API 密钥是 NuGet 特定的功能。</span><span class="sxs-lookup"><span data-stu-id="281df-152">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="281df-153">-Path</span><span class="sxs-lookup"><span data-stu-id="281df-153">-Path</span></span>

<span data-ttu-id="281df-154">指定要发布的模块的路径。</span><span class="sxs-lookup"><span data-stu-id="281df-154">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="281df-155">此参数接受包含模块的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="281df-155">This parameter accepts the path to the folder that contains the module.</span></span>

```yaml
Type: System.String
Parameter Sets: ModulePathParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="281df-156">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="281df-156">-ProjectUri</span></span>

<span data-ttu-id="281df-157">指定有关此项目的网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="281df-157">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="281df-158">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="281df-158">-ReleaseNotes</span></span>

<span data-ttu-id="281df-159">指定一个字符串，该字符串包含此版本的模块的用户要使用的发行说明或注释。</span><span class="sxs-lookup"><span data-stu-id="281df-159">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

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

### <span data-ttu-id="281df-160">-Repository</span><span class="sxs-lookup"><span data-stu-id="281df-160">-Repository</span></span>

<span data-ttu-id="281df-161">指定已通过运行注册的存储库的友好名称 `Register-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="281df-161">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="281df-162">存储库必须具有 **PublishLocation** ，这是一个有效的 NuGet URI。</span><span class="sxs-lookup"><span data-stu-id="281df-162">The repository must have a **PublishLocation** , which is a valid NuGet URI.</span></span>
<span data-ttu-id="281df-163">可以通过运行来设置 **PublishLocation** `Set-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="281df-163">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="281df-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="281df-164">-RequiredVersion</span></span>

<span data-ttu-id="281df-165">指定要发布的单个模块的确切版本。</span><span class="sxs-lookup"><span data-stu-id="281df-165">Specifies the exact version of a single module to publish.</span></span>

```yaml
Type: System.String
Parameter Sets: ModuleNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="281df-166">-SkipAutomaticTags</span><span class="sxs-lookup"><span data-stu-id="281df-166">-SkipAutomaticTags</span></span>

<span data-ttu-id="281df-167">删除作为标记包含的命令和资源。</span><span class="sxs-lookup"><span data-stu-id="281df-167">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="281df-168">跳过自动向模块添加标记。</span><span class="sxs-lookup"><span data-stu-id="281df-168">Skips automatically adding tags to a module.</span></span> <span data-ttu-id="281df-169">在 **PowerShellGet** 版本2.0.0 中添加了 **SkipAutomaticTags** 参数支持</span><span class="sxs-lookup"><span data-stu-id="281df-169">**SkipAutomaticTags** parameter support is added in **PowerShellGet** version 2.0.0</span></span>

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

### <span data-ttu-id="281df-170">-Tags</span><span class="sxs-lookup"><span data-stu-id="281df-170">-Tags</span></span>

<span data-ttu-id="281df-171">将一个或多个标记添加到要发布的模块。</span><span class="sxs-lookup"><span data-stu-id="281df-171">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="281df-172">示例标记包括 DesiredStateConfiguration、DSC、DSCResourceKit 或 PSModule。</span><span class="sxs-lookup"><span data-stu-id="281df-172">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="281df-173">用逗号分隔多个标记。</span><span class="sxs-lookup"><span data-stu-id="281df-173">Separate multiple tags with commas.</span></span>

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

### <span data-ttu-id="281df-174">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="281df-174">-WhatIf</span></span>

<span data-ttu-id="281df-175">显示运行时将发生的情况 `Publish-Module` 。</span><span class="sxs-lookup"><span data-stu-id="281df-175">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="281df-176">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="281df-176">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="281df-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="281df-177">CommonParameters</span></span>

<span data-ttu-id="281df-178">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="281df-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="281df-179">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="281df-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="281df-180">输入</span><span class="sxs-lookup"><span data-stu-id="281df-180">INPUTS</span></span>

### <span data-ttu-id="281df-181">System.String</span><span class="sxs-lookup"><span data-stu-id="281df-181">System.String</span></span>

### <span data-ttu-id="281df-182">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="281df-182">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="281df-183">输出</span><span class="sxs-lookup"><span data-stu-id="281df-183">OUTPUTS</span></span>

### <span data-ttu-id="281df-184">System.Object</span><span class="sxs-lookup"><span data-stu-id="281df-184">System.Object</span></span>

## <span data-ttu-id="281df-185">注释</span><span class="sxs-lookup"><span data-stu-id="281df-185">NOTES</span></span>

<span data-ttu-id="281df-186">`Publish-Module` 在 Windows 7 或 Windows 2008 R2 及更高版本的 Windows 上的 powershell 3.0 或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="281df-186">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="281df-187">发布模块需要在库页面显示的模块的元数据。</span><span class="sxs-lookup"><span data-stu-id="281df-187">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="281df-188">所需元数据包括模块名称、版本、说明和作者。</span><span class="sxs-lookup"><span data-stu-id="281df-188">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="281df-189">大多数元数据都是从模块清单获取的，但是可以在参数中指定某些元数据， `Publish-Module` 例如 **标记** 、 **ReleaseNote** 、 **IconUri** 、 **ProjectUri** 和 **LicenseUri** 。</span><span class="sxs-lookup"><span data-stu-id="281df-189">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag** , **ReleaseNote** , **IconUri** , **ProjectUri** , and **LicenseUri** .</span></span> <span data-ttu-id="281df-190">有关详细信息，请参阅 [影响 POWERSHELL 库 UI 的包清单值](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui)。</span><span class="sxs-lookup"><span data-stu-id="281df-190">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="281df-191">相关链接</span><span class="sxs-lookup"><span data-stu-id="281df-191">RELATED LINKS</span></span>

[<span data-ttu-id="281df-192">Find-Module</span><span class="sxs-lookup"><span data-stu-id="281df-192">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="281df-193">Install-Module</span><span class="sxs-lookup"><span data-stu-id="281df-193">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="281df-194">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="281df-194">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="281df-195">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="281df-195">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="281df-196">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="281df-196">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="281df-197">Update-Module</span><span class="sxs-lookup"><span data-stu-id="281df-197">Update-Module</span></span>](Update-Module.md)
