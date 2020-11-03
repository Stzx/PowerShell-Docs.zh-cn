---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/02/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/save-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Script
ms.openlocfilehash: aefc9103b182ab232cb986a2ebb2b51f7cd09767
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198235"
---
# <span data-ttu-id="74c01-103">Save-Script</span><span class="sxs-lookup"><span data-stu-id="74c01-103">Save-Script</span></span>

## <span data-ttu-id="74c01-104">摘要</span><span class="sxs-lookup"><span data-stu-id="74c01-104">SYNOPSIS</span></span>
<span data-ttu-id="74c01-105">保存脚本。</span><span class="sxs-lookup"><span data-stu-id="74c01-105">Saves a script.</span></span>

## <span data-ttu-id="74c01-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74c01-106">SYNTAX</span></span>

### <span data-ttu-id="74c01-107">NameAndPathParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="74c01-107">NameAndPathParameterSet (Default)</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="74c01-108">NameAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="74c01-108">NameAndLiteralPathParameterSet</span></span>

```
Save-Script [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AllowPrerelease]
 [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="74c01-109">InputObjectAndLiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="74c01-109">InputObjectAndLiteralPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> -LiteralPath <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="74c01-110">InputObjectAndPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="74c01-110">InputObjectAndPathParameterSet</span></span>

```
Save-Script [-InputObject] <PSObject[]> [-Path] <String> [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force] [-AcceptLicense] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="74c01-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="74c01-111">DESCRIPTION</span></span>

<span data-ttu-id="74c01-112">`Save-Script`Cmdlet 将保存指定的脚本。</span><span class="sxs-lookup"><span data-stu-id="74c01-112">The `Save-Script` cmdlet saves the specified script.</span></span>

## <span data-ttu-id="74c01-113">示例</span><span class="sxs-lookup"><span data-stu-id="74c01-113">EXAMPLES</span></span>

### <span data-ttu-id="74c01-114">示例1：保存脚本并验证脚本的元数据</span><span class="sxs-lookup"><span data-stu-id="74c01-114">Example 1: Save a script and validate the script's metadata</span></span>

<span data-ttu-id="74c01-115">在此示例中，存储库中的脚本保存到本地计算机，并验证脚本的元数据。</span><span class="sxs-lookup"><span data-stu-id="74c01-115">In this example, a script from a repository is saved to the local computer and the script's metadata is validated.</span></span>

```powershell
Save-Script -Name Install-VSCode -Repository PSGallery -Path C:\Test\Scripts
Test-ScriptFileInfo -Path C:\Test\Scripts\Install-VSCode.ps1
```

```Output
Version   Name              Author      Description
-------   ----              ------      -----------
1.3       Install-VSCode    Microsoft   This script can be used to easily install Visual Studio Code
```

<span data-ttu-id="74c01-116">`Save-Script` 使用 **Name** 参数来指定脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="74c01-116">`Save-Script` uses the **Name** parameter to specify the script's name.</span></span> <span data-ttu-id="74c01-117">**存储库** 参数指定要查找脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="74c01-117">The **Repository** parameter specifies where to find the script.</span></span> <span data-ttu-id="74c01-118">脚本保存在 **Path** 参数指定的位置。</span><span class="sxs-lookup"><span data-stu-id="74c01-118">The script is saved in the location specified by the **Path** parameter.</span></span> <span data-ttu-id="74c01-119">`Test-ScriptFileInfo` 指定 **路径** 并验证脚本的元数据。</span><span class="sxs-lookup"><span data-stu-id="74c01-119">`Test-ScriptFileInfo` specifies the **Path** and validates the script's metadata.</span></span>

## <span data-ttu-id="74c01-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74c01-120">PARAMETERS</span></span>

### <span data-ttu-id="74c01-121">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="74c01-121">-AcceptLicense</span></span>

<span data-ttu-id="74c01-122">如果脚本需要许可协议，则自动接受该协议。</span><span class="sxs-lookup"><span data-stu-id="74c01-122">Automatically accept the license agreement if the script requires it.</span></span>

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

### <span data-ttu-id="74c01-123">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="74c01-123">-AllowPrerelease</span></span>

<span data-ttu-id="74c01-124">允许您保存标记为预发行版的脚本。</span><span class="sxs-lookup"><span data-stu-id="74c01-124">Allows you to save a script marked as a prerelease.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="74c01-125">-Confirm</span></span>

<span data-ttu-id="74c01-126">在运行之前提示你进行确认 `Save-Script` 。</span><span class="sxs-lookup"><span data-stu-id="74c01-126">Prompts you for confirmation before running `Save-Script`.</span></span>

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

### <span data-ttu-id="74c01-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="74c01-127">-Credential</span></span>

<span data-ttu-id="74c01-128">指定有权保存脚本的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="74c01-128">Specifies a user account that has permission to save a script.</span></span>

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

### <span data-ttu-id="74c01-129">-Force</span><span class="sxs-lookup"><span data-stu-id="74c01-129">-Force</span></span>

<span data-ttu-id="74c01-130">强制 `Save-Script` 运行而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="74c01-130">Forces `Save-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="74c01-131">-InputObject</span><span class="sxs-lookup"><span data-stu-id="74c01-131">-InputObject</span></span>

<span data-ttu-id="74c01-132">接受 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="74c01-132">Accepts a **PSRepositoryItemInfo** object.</span></span> <span data-ttu-id="74c01-133">例如，输出 `Find-Script` 到变量，并将该变量用作 **InputObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="74c01-133">For example, output `Find-Script` to a variable and use that variable as the **InputObject** argument.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObjectAndLiteralPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-134">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="74c01-134">-LiteralPath</span></span>

<span data-ttu-id="74c01-135">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="74c01-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="74c01-136">**LiteralPath** 参数的值完全按输入方式使用。</span><span class="sxs-lookup"><span data-stu-id="74c01-136">The value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="74c01-137">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="74c01-137">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="74c01-138">如果路径中包含转义符，请将路径用单引号引起来。</span><span class="sxs-lookup"><span data-stu-id="74c01-138">If the path includes escape characters, enclose the path within single quotation marks.</span></span> <span data-ttu-id="74c01-139">PowerShell 不会将括在单引号中的任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="74c01-139">PowerShell doesn't interpret any characters enclosed in single quotation marks as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndLiteralPathParameterSet, InputObjectAndLiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-140">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="74c01-140">-MaximumVersion</span></span>

<span data-ttu-id="74c01-141">指定要保存的最大或最新版本的脚本。</span><span class="sxs-lookup"><span data-stu-id="74c01-141">Specifies the maximum, or newest version of the script to save.</span></span> <span data-ttu-id="74c01-142">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="74c01-142">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-143">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="74c01-143">-MinimumVersion</span></span>

<span data-ttu-id="74c01-144">指定要保存的脚本的最低版本。</span><span class="sxs-lookup"><span data-stu-id="74c01-144">Specifies the minimum version of a script to save.</span></span> <span data-ttu-id="74c01-145">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="74c01-145">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-146">-Name</span><span class="sxs-lookup"><span data-stu-id="74c01-146">-Name</span></span>

<span data-ttu-id="74c01-147">指定要保存的脚本名称的数组。</span><span class="sxs-lookup"><span data-stu-id="74c01-147">Specifies an array of script names to save.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-148">-Path</span><span class="sxs-lookup"><span data-stu-id="74c01-148">-Path</span></span>

<span data-ttu-id="74c01-149">指定本地计算机上存储已保存模块的位置。</span><span class="sxs-lookup"><span data-stu-id="74c01-149">Specifies the location on the local computer to store a saved module.</span></span> <span data-ttu-id="74c01-150">接受通配符。</span><span class="sxs-lookup"><span data-stu-id="74c01-150">Accepts wildcard characters.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, InputObjectAndPathParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="74c01-151">-Proxy</span><span class="sxs-lookup"><span data-stu-id="74c01-151">-Proxy</span></span>

<span data-ttu-id="74c01-152">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="74c01-152">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-153">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="74c01-153">-ProxyCredential</span></span>

<span data-ttu-id="74c01-154">指定有权使用 **代理** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="74c01-154">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="74c01-155">-Repository</span><span class="sxs-lookup"><span data-stu-id="74c01-155">-Repository</span></span>

<span data-ttu-id="74c01-156">指定已通过运行注册的存储库的友好名称 `Register-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="74c01-156">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span> <span data-ttu-id="74c01-157">用于 `Get-PSRepository` 显示已注册的存储库。</span><span class="sxs-lookup"><span data-stu-id="74c01-157">Use `Get-PSRepository` to display registered repositories.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-158">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="74c01-158">-RequiredVersion</span></span>

<span data-ttu-id="74c01-159">指定要保存的脚本的准确版本号。</span><span class="sxs-lookup"><span data-stu-id="74c01-159">Specifies the exact version number of the script to save.</span></span>

```yaml
Type: System.String
Parameter Sets: NameAndPathParameterSet, NameAndLiteralPathParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="74c01-160">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="74c01-160">-WhatIf</span></span>

<span data-ttu-id="74c01-161">显示运行时将发生 `Save-Script` 的情况。</span><span class="sxs-lookup"><span data-stu-id="74c01-161">Shows what would happen if `Save-Script` runs.</span></span> <span data-ttu-id="74c01-162">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="74c01-162">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="74c01-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="74c01-163">CommonParameters</span></span>

<span data-ttu-id="74c01-164">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="74c01-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="74c01-165">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="74c01-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="74c01-166">输入</span><span class="sxs-lookup"><span data-stu-id="74c01-166">INPUTS</span></span>

## <span data-ttu-id="74c01-167">输出</span><span class="sxs-lookup"><span data-stu-id="74c01-167">OUTPUTS</span></span>

## <span data-ttu-id="74c01-168">注释</span><span class="sxs-lookup"><span data-stu-id="74c01-168">NOTES</span></span>

## <span data-ttu-id="74c01-169">相关链接</span><span class="sxs-lookup"><span data-stu-id="74c01-169">RELATED LINKS</span></span>

[<span data-ttu-id="74c01-170">Find-Script</span><span class="sxs-lookup"><span data-stu-id="74c01-170">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="74c01-171">Install-Script</span><span class="sxs-lookup"><span data-stu-id="74c01-171">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="74c01-172">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="74c01-172">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="74c01-173">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="74c01-173">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)

[<span data-ttu-id="74c01-174">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="74c01-174">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="74c01-175">Update-Script</span><span class="sxs-lookup"><span data-stu-id="74c01-175">Update-Script</span></span>](Update-Script.md)
