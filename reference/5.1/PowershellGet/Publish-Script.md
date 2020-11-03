---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 2b9bfccddcd44cb0a87a7d93ae014fda5770d8d4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198238"
---
# <span data-ttu-id="6196f-103">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="6196f-103">Publish-Script</span></span>

## <span data-ttu-id="6196f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6196f-104">SYNOPSIS</span></span>
<span data-ttu-id="6196f-105">发布脚本。</span><span class="sxs-lookup"><span data-stu-id="6196f-105">Publishes a script.</span></span>

## <span data-ttu-id="6196f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6196f-106">SYNTAX</span></span>

### <span data-ttu-id="6196f-107">PathParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="6196f-107">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6196f-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="6196f-108">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6196f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6196f-109">DESCRIPTION</span></span>

<span data-ttu-id="6196f-110">`Publish-Script`Cmdlet 可将指定的脚本发布到联机库。</span><span class="sxs-lookup"><span data-stu-id="6196f-110">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="6196f-111">示例</span><span class="sxs-lookup"><span data-stu-id="6196f-111">EXAMPLES</span></span>

### <span data-ttu-id="6196f-112">示例1：创建一个脚本文件，向其中添加内容并将其发布</span><span class="sxs-lookup"><span data-stu-id="6196f-112">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="6196f-113">`New-ScriptFileInfo`Cmdlet 将创建一个名为的脚本文件 `Demo-Script.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="6196f-113">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="6196f-114">`Get-Content` 显示的内容 `Demo-Script.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="6196f-114">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="6196f-115">`Add-Content`Cmdlet 可向添加函数和工作流 `Demo-Script.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="6196f-115">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

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
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

<span data-ttu-id="6196f-116">Cmdlet 将进行 `Test-ScriptFileInfo` 验证 `Demo-Script.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="6196f-116">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="6196f-117">`Publish-Script`Cmdlet 将脚本发布到 **LocalRepo1** 存储库。</span><span class="sxs-lookup"><span data-stu-id="6196f-117">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="6196f-118">最后，</span><span class="sxs-lookup"><span data-stu-id="6196f-118">Finally.</span></span> <span data-ttu-id="6196f-119">`Find-Script` 用于 `Demo-Script.ps1` 在 **LocalRepo1** 存储库中搜索。</span><span class="sxs-lookup"><span data-stu-id="6196f-119">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="6196f-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6196f-120">PARAMETERS</span></span>

### <span data-ttu-id="6196f-121">-Credential</span><span class="sxs-lookup"><span data-stu-id="6196f-121">-Credential</span></span>

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

### <span data-ttu-id="6196f-122">-Force</span><span class="sxs-lookup"><span data-stu-id="6196f-122">-Force</span></span>

<span data-ttu-id="6196f-123">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="6196f-123">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="6196f-124">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6196f-124">-LiteralPath</span></span>

<span data-ttu-id="6196f-125">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="6196f-125">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6196f-126">与 **Path** 参数不同， **LiteralPath** 参数的值完全按输入方式使用。</span><span class="sxs-lookup"><span data-stu-id="6196f-126">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="6196f-127">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="6196f-127">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6196f-128">如果路径包含转义符，请将其括在单引号内。</span><span class="sxs-lookup"><span data-stu-id="6196f-128">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="6196f-129">单引号会告知 Windows PowerShell 不要将所有字符都解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="6196f-129">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6196f-130">-NuGetApiKey</span><span class="sxs-lookup"><span data-stu-id="6196f-130">-NuGetApiKey</span></span>

<span data-ttu-id="6196f-131">指定要用于将脚本发布到联机库的 API 密钥。</span><span class="sxs-lookup"><span data-stu-id="6196f-131">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="6196f-132">API 密钥是你的个人资料中的配置文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="6196f-132">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="6196f-133">有关详细信息，请参阅 [管理 API 密钥](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys)。</span><span class="sxs-lookup"><span data-stu-id="6196f-133">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

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

### <span data-ttu-id="6196f-134">-Path</span><span class="sxs-lookup"><span data-stu-id="6196f-134">-Path</span></span>

<span data-ttu-id="6196f-135">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="6196f-135">Specifies a path to one or more locations.</span></span> <span data-ttu-id="6196f-136">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="6196f-136">Wildcards are permitted.</span></span> <span data-ttu-id="6196f-137">默认位置为当前目录。</span><span class="sxs-lookup"><span data-stu-id="6196f-137">The default location is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="6196f-138">-Repository</span><span class="sxs-lookup"><span data-stu-id="6196f-138">-Repository</span></span>

<span data-ttu-id="6196f-139">指定已通过运行注册的存储库的友好名称 `Register-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="6196f-139">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

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

### <span data-ttu-id="6196f-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6196f-140">-Confirm</span></span>

<span data-ttu-id="6196f-141">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="6196f-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6196f-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6196f-142">-WhatIf</span></span>

<span data-ttu-id="6196f-143">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="6196f-143">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6196f-144">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="6196f-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6196f-145">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6196f-145">CommonParameters</span></span>

<span data-ttu-id="6196f-146">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6196f-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6196f-147">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6196f-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6196f-148">输入</span><span class="sxs-lookup"><span data-stu-id="6196f-148">INPUTS</span></span>

### <span data-ttu-id="6196f-149">System.String</span><span class="sxs-lookup"><span data-stu-id="6196f-149">System.String</span></span>

### <span data-ttu-id="6196f-150">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="6196f-150">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="6196f-151">输出</span><span class="sxs-lookup"><span data-stu-id="6196f-151">OUTPUTS</span></span>

### <span data-ttu-id="6196f-152">System.Object</span><span class="sxs-lookup"><span data-stu-id="6196f-152">System.Object</span></span>

## <span data-ttu-id="6196f-153">注释</span><span class="sxs-lookup"><span data-stu-id="6196f-153">NOTES</span></span>

## <span data-ttu-id="6196f-154">相关链接</span><span class="sxs-lookup"><span data-stu-id="6196f-154">RELATED LINKS</span></span>

[<span data-ttu-id="6196f-155">Find-Script</span><span class="sxs-lookup"><span data-stu-id="6196f-155">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="6196f-156">Install-Script</span><span class="sxs-lookup"><span data-stu-id="6196f-156">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="6196f-157">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="6196f-157">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="6196f-158">Save-Script</span><span class="sxs-lookup"><span data-stu-id="6196f-158">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="6196f-159">Update-Script</span><span class="sxs-lookup"><span data-stu-id="6196f-159">Update-Script</span></span>](Update-Script.md)
