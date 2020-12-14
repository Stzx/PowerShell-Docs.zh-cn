---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 10/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Module
ms.openlocfilehash: 602d160a4cc7fd4e8a806d2c3d2772ee5053535d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889685"
---
# <span data-ttu-id="ccd4e-103">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="ccd4e-103">Publish-Module</span></span>

## <span data-ttu-id="ccd4e-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ccd4e-104">SYNOPSIS</span></span>
<span data-ttu-id="ccd4e-105">将指定模块从本机计算机发布到联机库。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-105">Publishes a specified module from the local computer to an online gallery.</span></span>

## <span data-ttu-id="ccd4e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ccd4e-106">SYNTAX</span></span>

### <span data-ttu-id="ccd4e-107">ModuleNameParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="ccd4e-107">ModuleNameParameterSet (Default)</span></span>

```
Publish-Module -Name <String> [-RequiredVersion <String>] [-NuGetApiKey <String>]
 [-Repository <String>] [-Credential <PSCredential>] [-FormatVersion <Version>]
 [-ReleaseNotes <String[]>] [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>]
 [-ProjectUri <Uri>] [-Exclude <String[]>] [-Force] [-AllowPrerelease] [-SkipAutomaticTags]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ccd4e-108">ModulePathParameterSet</span><span class="sxs-lookup"><span data-stu-id="ccd4e-108">ModulePathParameterSet</span></span>

```
Publish-Module -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-FormatVersion <Version>] [-ReleaseNotes <String[]>]
 [-Tags <String[]>] [-LicenseUri <Uri>] [-IconUri <Uri>] [-ProjectUri <Uri>] [-Force]
 [-SkipAutomaticTags] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ccd4e-109">说明</span><span class="sxs-lookup"><span data-stu-id="ccd4e-109">DESCRIPTION</span></span>

<span data-ttu-id="ccd4e-110">该 `Publish-Module` cmdlet 通过使用 API 密钥（存储在库中的用户配置文件的一部分），将模块发布到基于 NuGet 的联机库。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-110">The `Publish-Module` cmdlet publishes a module to an online NuGet-based gallery by using an API key, stored as part of a user's profile in the gallery.</span></span> <span data-ttu-id="ccd4e-111">可根据模块的名称或包含模块的文件夹路径指定要发布的模块。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-111">You can specify the module to publish either by the module's name, or by the path to the folder containing the module.</span></span>

<span data-ttu-id="ccd4e-112">按名称指定模块时，将 `Publish-Module` 发布通过运行找到的第一个模块 `Get-Module -ListAvailable <Name>` 。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-112">When you specify a module by name, `Publish-Module` publishes the first module that would be found by running `Get-Module -ListAvailable <Name>`.</span></span> <span data-ttu-id="ccd4e-113">如果您指定要发布的模块的最低版本，将 `Publish-Module` 发布第一个版本大于或等于您指定的最低版本的模块。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-113">If you specify a minimum version of a module to publish, `Publish-Module` publishes the first module with a version that is greater than or equal to the minimum version that you have specified.</span></span>

<span data-ttu-id="ccd4e-114">发布模块需要在库页面显示的模块的元数据。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-114">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="ccd4e-115">所需元数据包括模块名称、版本、说明和作者。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-115">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="ccd4e-116">尽管大多数元数据都是从模块清单获取的，但必须在参数中指定某些元数据（如 `Publish-Module` **标记**、 **ReleaseNote**、 **IconUri**、 **ProjectUri** 和 **LicenseUri**），因为这些参数与基于 NuGet 的库中的字段匹配。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-116">Although most metadata is taken from the module manifest, some metadata must be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**, because these parameters match fields in a NuGet-based gallery.</span></span>

## <span data-ttu-id="ccd4e-117">示例</span><span class="sxs-lookup"><span data-stu-id="ccd4e-117">EXAMPLES</span></span>

### <span data-ttu-id="ccd4e-118">示例1：发布模块</span><span class="sxs-lookup"><span data-stu-id="ccd4e-118">Example 1: Publish a module</span></span>

<span data-ttu-id="ccd4e-119">在此示例中，使用 API 密钥将 MyDscModule 发布到联机库，以指示模块所有者的联机库帐户。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-119">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's online gallery account.</span></span> <span data-ttu-id="ccd4e-120">如果 MyDscModule 不是指定名称、版本、说明和作者的有效清单模块，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-120">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73"
```

### <span data-ttu-id="ccd4e-121">示例2：使用库元数据发布模块</span><span class="sxs-lookup"><span data-stu-id="ccd4e-121">Example 2: Publish a module with gallery metadata</span></span>

<span data-ttu-id="ccd4e-122">在此示例中，使用 API 密钥将 MyDscModule 发布到联机库，以指示模块所有者的库帐户。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-122">In this example, MyDscModule is published to the online gallery by using the API key to indicate the module owner's gallery account.</span></span> <span data-ttu-id="ccd4e-123">提供的其他元数据将显示在库中模块的网页上。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-123">The additional metadata provided is displayed on the webpage for the module in the gallery.</span></span> <span data-ttu-id="ccd4e-124">所有者添加了两个用于模块的搜索标记，并将其与 Active Directory 相关联。已添加简短的发行说明。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-124">The owner adds two search tags for the module, relating it to Active Directory; a brief release note is added.</span></span> <span data-ttu-id="ccd4e-125">如果 MyDscModule 不是指定名称、版本、说明和作者的有效清单模块，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-125">If MyDscModule is not a valid manifest module that specifies a name, version, description, and author, an error occurs.</span></span>

```powershell
Publish-Module -Name "MyDscModule" -NuGetApiKey "11e4b435-6cb4-4bf7-8611-5162ed75eb73" -LicenseUri "http://contoso.com/license" -Tag "Active Directory","DSC" -ReleaseNote "Updated the ActiveDirectory DSC Resources to support adding users."
```

## <span data-ttu-id="ccd4e-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ccd4e-126">PARAMETERS</span></span>

### <span data-ttu-id="ccd4e-127">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="ccd4e-127">-AllowPrerelease</span></span>

<span data-ttu-id="ccd4e-128">允许发布标记为预发行的模块。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-128">Allows modules marked as prerelease to be published.</span></span>

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

### <span data-ttu-id="ccd4e-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ccd4e-129">-Confirm</span></span>

<span data-ttu-id="ccd4e-130">提示你在运行之前进行确认 `Publish-Module` 。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-130">Prompts you for confirmation before running the `Publish-Module`.</span></span>

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

### <span data-ttu-id="ccd4e-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="ccd4e-131">-Credential</span></span>

<span data-ttu-id="ccd4e-132">指定有权为指定的包提供程序或源发布模块的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-132">Specifies a user account that has rights to publish a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="ccd4e-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="ccd4e-133">-Exclude</span></span>

<span data-ttu-id="ccd4e-134">定义要从已发布的模块中排除的文件。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-134">Defines files to exclude from the published module.</span></span> <span data-ttu-id="ccd4e-135">**排除** 参数支持是在 **PowershellGet** 版本2.0.0 中添加的。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-135">**Exclude** parameter support is add in **PowershellGet** version 2.0.0.</span></span>

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

### <span data-ttu-id="ccd4e-136">-Force</span><span class="sxs-lookup"><span data-stu-id="ccd4e-136">-Force</span></span>

<span data-ttu-id="ccd4e-137">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-137">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ccd4e-138">-FormatVersion</span><span class="sxs-lookup"><span data-stu-id="ccd4e-138">-FormatVersion</span></span>

<span data-ttu-id="ccd4e-139">仅接受 **ValidateSet** 属性指定的有效值。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-139">Accepts only valid values specified by the **ValidateSet** attribute.</span></span>

<span data-ttu-id="ccd4e-140">有关详细信息，请参阅 [ValidateSet 特性声明](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) 和 [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute)。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-140">For more information, see [ValidateSet Attribute Declaration](/powershell/scripting/developer/cmdlet/validateset-attribute-declaration) and [ValidateSetAttribute](/dotnet/api/system.management.automation.validatesetattribute).</span></span>

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

### <span data-ttu-id="ccd4e-141">-IconUri</span><span class="sxs-lookup"><span data-stu-id="ccd4e-141">-IconUri</span></span>

<span data-ttu-id="ccd4e-142">指定模块的图标的 URL。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-142">Specifies the URL of an icon for the module.</span></span> <span data-ttu-id="ccd4e-143">指定的图标显示在模块的库网页上。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-143">The specified icon is displayed on the gallery webpage for the module.</span></span>

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

### <span data-ttu-id="ccd4e-144">-LicenseUri</span><span class="sxs-lookup"><span data-stu-id="ccd4e-144">-LicenseUri</span></span>

<span data-ttu-id="ccd4e-145">指定要发布的模块的许可条款 URL。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-145">Specifies the URL of licensing terms for the module you want to publish.</span></span>

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

### <span data-ttu-id="ccd4e-146">-Name</span><span class="sxs-lookup"><span data-stu-id="ccd4e-146">-Name</span></span>

<span data-ttu-id="ccd4e-147">指定要发布的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-147">Specifies the name of the module that you want to publish.</span></span> <span data-ttu-id="ccd4e-148">`Publish-Module` 在中搜索指定的模块名称 `$Env:PSModulePath` 。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-148">`Publish-Module` searches for the specified module name in `$Env:PSModulePath`.</span></span>

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

### <span data-ttu-id="ccd4e-149">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="ccd4e-149">-NuGetApiKey</span></span>

<span data-ttu-id="ccd4e-150">指定要用于将模块发布到联机库的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-150">Specifies the API key that you want to use to publish a module to the online gallery.</span></span> <span data-ttu-id="ccd4e-151">API 密钥是你的个人资料中的配置文件的一部分，可以在库中的用户帐户页面上找到。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-151">The API key is part of your profile in the online gallery, and can be found on your user account page in the gallery.</span></span> <span data-ttu-id="ccd4e-152">API 密钥是 NuGet 特定的功能。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-152">The API key is NuGet-specific functionality.</span></span>

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

### <span data-ttu-id="ccd4e-153">-Path</span><span class="sxs-lookup"><span data-stu-id="ccd4e-153">-Path</span></span>

<span data-ttu-id="ccd4e-154">指定要发布的模块的路径。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-154">Specifies the path to the module that you want to publish.</span></span> <span data-ttu-id="ccd4e-155">此参数接受包含模块的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-155">This parameter accepts the path to the folder that contains the module.</span></span>

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

### <span data-ttu-id="ccd4e-156">-ProjectUri</span><span class="sxs-lookup"><span data-stu-id="ccd4e-156">-ProjectUri</span></span>

<span data-ttu-id="ccd4e-157">指定有关此项目的网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-157">Specifies the URL of a webpage about this project.</span></span>

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

### <span data-ttu-id="ccd4e-158">-ReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="ccd4e-158">-ReleaseNotes</span></span>

<span data-ttu-id="ccd4e-159">指定一个字符串，该字符串包含此版本的模块的用户要使用的发行说明或注释。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-159">Specifies a string containing release notes or comments that you want to be available to users of this version of the module.</span></span>

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

### <span data-ttu-id="ccd4e-160">-Repository</span><span class="sxs-lookup"><span data-stu-id="ccd4e-160">-Repository</span></span>

<span data-ttu-id="ccd4e-161">指定已通过运行注册的存储库的友好名称 `Register-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-161">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="ccd4e-162">存储库必须具有 **PublishLocation**，这是一个有效的 NuGet URI。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-162">The repository must have a **PublishLocation**, which is a valid NuGet URI.</span></span>
<span data-ttu-id="ccd4e-163">可以通过运行来设置 **PublishLocation** `Set-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-163">The **PublishLocation** can be set by running `Set-PSRepository`.</span></span>

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

### <span data-ttu-id="ccd4e-164">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="ccd4e-164">-RequiredVersion</span></span>

<span data-ttu-id="ccd4e-165">指定要发布的单个模块的确切版本。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-165">Specifies the exact version of a single module to publish.</span></span>

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

### <span data-ttu-id="ccd4e-166">-SkipAutomaticTags</span><span class="sxs-lookup"><span data-stu-id="ccd4e-166">-SkipAutomaticTags</span></span>

<span data-ttu-id="ccd4e-167">删除作为标记包含的命令和资源。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-167">Removes commands and resources from being included as tags.</span></span> <span data-ttu-id="ccd4e-168">跳过自动向模块添加标记。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-168">Skips automatically adding tags to a module.</span></span> <span data-ttu-id="ccd4e-169">在 **PowerShellGet** 版本2.0.0 中添加了 **SkipAutomaticTags** 参数支持</span><span class="sxs-lookup"><span data-stu-id="ccd4e-169">**SkipAutomaticTags** parameter support is added in **PowerShellGet** version 2.0.0</span></span>

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

### <span data-ttu-id="ccd4e-170">-Tags</span><span class="sxs-lookup"><span data-stu-id="ccd4e-170">-Tags</span></span>

<span data-ttu-id="ccd4e-171">将一个或多个标记添加到要发布的模块。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-171">Adds one or more tags to the module that you are publishing.</span></span> <span data-ttu-id="ccd4e-172">示例标记包括 DesiredStateConfiguration、DSC、DSCResourceKit 或 PSModule。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-172">Example tags include DesiredStateConfiguration, DSC, DSCResourceKit, or PSModule.</span></span> <span data-ttu-id="ccd4e-173">用逗号分隔多个标记。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-173">Separate multiple tags with commas.</span></span>

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

### <span data-ttu-id="ccd4e-174">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ccd4e-174">-WhatIf</span></span>

<span data-ttu-id="ccd4e-175">显示运行时将发生的情况 `Publish-Module` 。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-175">Shows what would happen if the `Publish-Module` runs.</span></span> <span data-ttu-id="ccd4e-176">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-176">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ccd4e-177">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ccd4e-177">CommonParameters</span></span>

<span data-ttu-id="ccd4e-178">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ccd4e-179">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ccd4e-180">输入</span><span class="sxs-lookup"><span data-stu-id="ccd4e-180">INPUTS</span></span>

### <span data-ttu-id="ccd4e-181">System.String</span><span class="sxs-lookup"><span data-stu-id="ccd4e-181">System.String</span></span>

### <span data-ttu-id="ccd4e-182">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="ccd4e-182">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="ccd4e-183">输出</span><span class="sxs-lookup"><span data-stu-id="ccd4e-183">OUTPUTS</span></span>

### <span data-ttu-id="ccd4e-184">System.Object</span><span class="sxs-lookup"><span data-stu-id="ccd4e-184">System.Object</span></span>

## <span data-ttu-id="ccd4e-185">注释</span><span class="sxs-lookup"><span data-stu-id="ccd4e-185">NOTES</span></span>

<span data-ttu-id="ccd4e-186">`Publish-Module` 在 Windows 7 或 Windows 2008 R2 及更高版本的 Windows 上的 powershell 3.0 或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-186">`Publish-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ccd4e-187">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-187">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="ccd4e-188">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-188">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="ccd4e-189">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="ccd4e-189">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="ccd4e-190">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-190">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="ccd4e-191">发布模块需要在库页面显示的模块的元数据。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-191">Publishing a module requires metadata that is displayed on the gallery page for the module.</span></span> <span data-ttu-id="ccd4e-192">所需元数据包括模块名称、版本、说明和作者。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-192">Required metadata includes the module name, version, description, and author.</span></span> <span data-ttu-id="ccd4e-193">大多数元数据都是从模块清单获取的，但是可以在参数中指定某些元数据， `Publish-Module` 例如 **标记**、 **ReleaseNote**、 **IconUri**、 **ProjectUri** 和 **LicenseUri**。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-193">Most metadata is taken from the module manifest, but some metadata can be specified in `Publish-Module` parameters, such as **Tag**, **ReleaseNote**, **IconUri**, **ProjectUri**, and **LicenseUri**.</span></span> <span data-ttu-id="ccd4e-194">有关详细信息，请参阅 [影响 POWERSHELL 库 UI 的包清单值](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui)。</span><span class="sxs-lookup"><span data-stu-id="ccd4e-194">For more information, see [Package manifest values that impact the PowerShell Gallery UI](/powershell/scripting/gallery/concepts/package-manifest-affecting-ui).</span></span>

## <span data-ttu-id="ccd4e-195">相关链接</span><span class="sxs-lookup"><span data-stu-id="ccd4e-195">RELATED LINKS</span></span>

[<span data-ttu-id="ccd4e-196">Find-Module</span><span class="sxs-lookup"><span data-stu-id="ccd4e-196">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="ccd4e-197">Install-Module</span><span class="sxs-lookup"><span data-stu-id="ccd4e-197">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="ccd4e-198">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ccd4e-198">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="ccd4e-199">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="ccd4e-199">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="ccd4e-200">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="ccd4e-200">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="ccd4e-201">Update-Module</span><span class="sxs-lookup"><span data-stu-id="ccd4e-201">Update-Module</span></span>](Update-Module.md)
