---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/test-scriptfileinfo?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ScriptFileInfo
ms.openlocfilehash: d7e70c9bff9e5c33edd1fd8eeb9d8fb7e15605da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198226"
---
# <span data-ttu-id="12dc4-103">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="12dc4-103">Test-ScriptFileInfo</span></span>

## <span data-ttu-id="12dc4-104">摘要</span><span class="sxs-lookup"><span data-stu-id="12dc4-104">SYNOPSIS</span></span>
<span data-ttu-id="12dc4-105">验证脚本的注释块。</span><span class="sxs-lookup"><span data-stu-id="12dc4-105">Validates a comment block for a script.</span></span>

## <span data-ttu-id="12dc4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="12dc4-106">SYNTAX</span></span>

### <span data-ttu-id="12dc4-107">PathParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="12dc4-107">PathParameterSet (Default)</span></span>

```
Test-ScriptFileInfo [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="12dc4-108">LiteralPathParameterSet</span><span class="sxs-lookup"><span data-stu-id="12dc4-108">LiteralPathParameterSet</span></span>

```
Test-ScriptFileInfo -LiteralPath <String> [<CommonParameters>]
```

## <span data-ttu-id="12dc4-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="12dc4-109">DESCRIPTION</span></span>

<span data-ttu-id="12dc4-110">**New-scriptfileinfo** cmdlet 验证将使用 Publish-Script cmdlet 发布的脚本开头的注释块。</span><span class="sxs-lookup"><span data-stu-id="12dc4-110">The **Test-ScriptFileInfo** cmdlet validates the comment block at the beginning of a script that will be published with the Publish-Script cmdlet.</span></span>
<span data-ttu-id="12dc4-111">如果注释块出现错误，则此 cmdlet 将返回有关错误所在位置的信息或纠正方法。</span><span class="sxs-lookup"><span data-stu-id="12dc4-111">If the comment block has an error, this cmdlet returns information about where the error is located or how to correct it.</span></span>

## <span data-ttu-id="12dc4-112">示例</span><span class="sxs-lookup"><span data-stu-id="12dc4-112">EXAMPLES</span></span>

### <span data-ttu-id="12dc4-113">示例1：测试脚本文件</span><span class="sxs-lookup"><span data-stu-id="12dc4-113">Example 1: Test a script file</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "C:\temp\temp_scripts\New-ScriptFile.ps1"
Version    Name                      Author               Description
-------    ----                      ------               -----------
1.0        New-ScriptFile            pattif               my new script file test
```

<span data-ttu-id="12dc4-114">此命令测试 New-ScriptFile.ps1 脚本文件并显示结果。</span><span class="sxs-lookup"><span data-stu-id="12dc4-114">This command tests the New-ScriptFile.ps1 script file and displays the results.</span></span>
<span data-ttu-id="12dc4-115">脚本文件包含有效的元数据。</span><span class="sxs-lookup"><span data-stu-id="12dc4-115">The script file includes valid metadata.</span></span>

### <span data-ttu-id="12dc4-116">示例2：测试包含所有元数据属性值的脚本文件</span><span class="sxs-lookup"><span data-stu-id="12dc4-116">Example 2: Test a script file that has values for all metadata properties</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Test-Runbook.ps1" | Format-List *
Name                       : Test-Runbook
Path                       : D:\code\Test-Runbook.ps1
ScriptBase                 : D:\code
ReleaseNotes               : {contoso script now supports following features, Feature 1, Feature 2, Feature 3...}
Version                    : 1.0
Guid                       : eb246b19-17da-4392-8c89-7c280f69ad0e
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
Tags                       : {Tag1, Tag2, Tag3}
LicenseUri                 : https://contoso.com/License
ProjectUri                 : https://contoso.com/
IconUri                    : https://contoso.com/MyScriptIcon
ExternalModuleDependencies : ExternalModule1
RequiredScripts            : {Start-WFContosoServer, Stop-ContosoServerScript}
ExternalScriptDependencies : Stop-ContosoServerScript
Description                : Contoso Script example
RequiredModules            : {RequiredModule1, @{ ModuleName = 'RequiredModule2'; ModuleVersion = '1.0' }, @{ ModuleName = 'RequiredModule3'; RequiredVersion = '2.0' }, ExternalModule1}
ExportedCommands           : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-Workflow...}
ExportedFunctions          : {Test-WebUri, ValidateAndAdd-PSScriptInfoEntry, Get-PSScriptInfo, My-AdvPSCmdlet}
ExportedWorkflows          : My-Workflow
```

<span data-ttu-id="12dc4-117">此命令 Test-Runbook.ps1 测试脚本文件，并使用管道运算符将结果传递给 Format-List cmdlet 以设置结果的格式。</span><span class="sxs-lookup"><span data-stu-id="12dc4-117">This command tests the script file Test-Runbook.ps1 and uses the pipeline operator to pass the results to the Format-List cmdlet to format the results.</span></span>

### <span data-ttu-id="12dc4-118">示例3：测试没有元数据的脚本文件</span><span class="sxs-lookup"><span data-stu-id="12dc4-118">Example 3: Test a script file that has no metadata</span></span>

```
PS C:\> Test-ScriptFileInfo -Path "D:\code\Hello-World.ps1"
Test-ScriptFileInfo : Script 'D:\code\Hello-World.ps1' is missing required metadata properties. Verify that the script file has Version, Description
and Author properties. You can use the Update-ScriptFileInfo or New-ScriptFileInfo cmdlet to add or update the PSScriptInfo to the script file.
At line:1 char:1
+ Test-ScriptFileInfo D:\code\Hello-World.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidArgument: (D:\code\Hello-World.ps1:String) [Test-ScriptFileInfo], ArgumentException

+ FullyQualifiedErrorId : MissingRequiredPSScriptInfoProperties,Test-ScriptFile
```

<span data-ttu-id="12dc4-119">此命令测试 Hello-World.ps1 的脚本文件，该文件没有关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="12dc4-119">This command tests the script file Hello-World.ps1, which has no metadata associated with it.</span></span>

## <span data-ttu-id="12dc4-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="12dc4-120">PARAMETERS</span></span>

### <span data-ttu-id="12dc4-121">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="12dc4-121">-LiteralPath</span></span>

<span data-ttu-id="12dc4-122">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="12dc4-122">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="12dc4-123">与 *Path* 参数不同， *LiteralPath* 参数的值严格按照输入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="12dc4-123">Unlike the *Path* parameter, the value of the *LiteralPath* parameter is used exactly as it is entered.</span></span>
<span data-ttu-id="12dc4-124">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="12dc4-124">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="12dc4-125">如果路径包含转义符，请将其括在单引号内。</span><span class="sxs-lookup"><span data-stu-id="12dc4-125">If the path includes escape characters, enclose them in single quotation marks.</span></span>
<span data-ttu-id="12dc4-126">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="12dc4-126">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="12dc4-127">-Path</span><span class="sxs-lookup"><span data-stu-id="12dc4-127">-Path</span></span>

<span data-ttu-id="12dc4-128">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="12dc4-128">Specifies a path to one or more locations.</span></span>
<span data-ttu-id="12dc4-129">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="12dc4-129">Wildcards are permitted.</span></span>
<span data-ttu-id="12dc4-130">默认位置为当前目录 (.)。</span><span class="sxs-lookup"><span data-stu-id="12dc4-130">The default location is the current directory (.).</span></span>

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

### <span data-ttu-id="12dc4-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="12dc4-131">CommonParameters</span></span>

<span data-ttu-id="12dc4-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="12dc4-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="12dc4-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="12dc4-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="12dc4-134">输入</span><span class="sxs-lookup"><span data-stu-id="12dc4-134">INPUTS</span></span>

## <span data-ttu-id="12dc4-135">输出</span><span class="sxs-lookup"><span data-stu-id="12dc4-135">OUTPUTS</span></span>

## <span data-ttu-id="12dc4-136">注释</span><span class="sxs-lookup"><span data-stu-id="12dc4-136">NOTES</span></span>

## <span data-ttu-id="12dc4-137">相关链接</span><span class="sxs-lookup"><span data-stu-id="12dc4-137">RELATED LINKS</span></span>

[<span data-ttu-id="12dc4-138">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="12dc4-138">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)

[<span data-ttu-id="12dc4-139">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="12dc4-139">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="12dc4-140">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="12dc4-140">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
