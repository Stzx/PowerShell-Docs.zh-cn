---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/find-script?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Script
ms.openlocfilehash: 6eb617987b437337dc3c42c33f55033b64ec8a79
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93196992"
---
# <span data-ttu-id="1dffc-103">Find-Script</span><span class="sxs-lookup"><span data-stu-id="1dffc-103">Find-Script</span></span>

## <span data-ttu-id="1dffc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="1dffc-104">SYNOPSIS</span></span>
<span data-ttu-id="1dffc-105">查找脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-105">Finds a script.</span></span>

## <span data-ttu-id="1dffc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1dffc-106">SYNTAX</span></span>

```
Find-Script [[-Name] <String[]>] [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-AllVersions] [-IncludeDependencies] [-Filter <String>] [-Tag <String[]>]
 [-Includes <String[]>] [-Command <String[]>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [-Credential <PSCredential>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="1dffc-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1dffc-107">DESCRIPTION</span></span>

<span data-ttu-id="1dffc-108">**Find-Script** cmdlet 在已注册的存储库中查找指定的脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-108">The **Find-Script** cmdlet finds a specified script in registered repositories.</span></span>

## <span data-ttu-id="1dffc-109">示例</span><span class="sxs-lookup"><span data-stu-id="1dffc-109">EXAMPLES</span></span>

### <span data-ttu-id="1dffc-110">示例1：查找所有可用脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-110">Example 1: Find all available scripts</span></span>

```
PS C:\> Find-Script
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
2.5        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
2.5        Fabrikam-ServerScript               Script     LocalRepo1           Description for the Fabrikam-ServerScript script
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        Script-WithDependencies2            Script     LocalRepo1           Description for the Script-WithDependencies2 script
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
2.1        Test-Script1                        Script     LocalRepo1           Test-Script1 Script example
2.0        Test-Script2                        Script     LocalRepo1           Test-Script2 Script example
1.0        TestRunbook                         Script     LocalRepo1           Contoso Script example
```

<span data-ttu-id="1dffc-111">此命令查找所有可用脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-111">This command finds all available scripts.</span></span>

### <span data-ttu-id="1dffc-112">示例2：按名称查找脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-112">Example 2: Find a script by name</span></span>

```
PS C:\> Find-Script -Name "Start-WFContosoServer"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.0        Start-WFContosoServer               Script     LocalRepo1           Start-WFContosoServer Script example
```

<span data-ttu-id="1dffc-113">此命令查找名为 WFContosoServer 的脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-113">This command find the script named Start-WFContosoServer.</span></span>

### <span data-ttu-id="1dffc-114">示例3：按名称、所需版本和指定的存储库查找脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-114">Example 3: Find a script by name, required version, and from a specified repository</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo01"
```

<span data-ttu-id="1dffc-115">此命令在 LocalRepo01 存储库中按名称和所需版本查找脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-115">This command finds a script by name and required version in the LocalRepo01 repository.</span></span>

### <span data-ttu-id="1dffc-116">示例4：查找脚本并将输出的格式设置为列表</span><span class="sxs-lookup"><span data-stu-id="1dffc-116">Example 4: Find a script and format the output as a list</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -RequiredVersion 2.0 -Repository "LocalRepo1" | Format-List * -Force
Name                       : Required-Script2
Version                    : 2.0
Type                       : Script
Description                : Description for the Required-Script2 script
Author                     : pattif
CompanyName                : Microsoft Corporation
Copyright                  : 2015 Microsoft Corporation. All rights reserved.
PublishedDate              : 8/14/2015 2:37:01 PM
LicenseUri                 : http://required-script2.com/license
ProjectUri                 : http://required-script2.com/
IconUri                    : http://required-script2.com/icon
Tags                       : {, Tag1, Tag2, Tag-Required-Script2-2.0...}
Includes                   : {Function, DscResource, Cmdlet, Command}
PowerShellGetFormatVersion :
ReleaseNotes               : Required-Script2 release notes
Dependencies               : {}
RepositorySourceLocation   : C:\MyLocalRepo
Repository                 : LocalRepo01
PackageManagementProvider  : NuGet
```

<span data-ttu-id="1dffc-117">此命令在 LocalRepo1 存储库中查找 Required-Script2，然后将生成的 **PSRepositoryItemInfo** 对象传递给 Format-List cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1dffc-117">This command finds Required-Script2 in the LocalRepo1 repository, and then passes the resulting **PSRepositoryItemInfo** object to the Format-List cmdlet.</span></span>

### <span data-ttu-id="1dffc-118">示例5：在指定的版本范围内查找脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-118">Example 5: Find a script in the specified version range</span></span>

```
PS C:\> Find-Script -Name "Required-Script2" -MinimumVersion 2.1 -MaximumVersion 2.5 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="1dffc-119">此命令在 LocalRepo1 存储库中查找版本2.1 和2.5 之间的所有 RequiredScript2 版本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-119">This command finds all versions of RequiredScript2 between versions 2.1 and 2.5 in the LocalRepo1 respository.</span></span>

### <span data-ttu-id="1dffc-120">示例6：查找脚本的所有版本</span><span class="sxs-lookup"><span data-stu-id="1dffc-120">Example 6: Find all versions of a script</span></span>

```
PS C:\> Find-Script -Name "Required-Script02" -AllVersions
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
1.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.0        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="1dffc-121">此命令查找所需的所有版本-Script02。</span><span class="sxs-lookup"><span data-stu-id="1dffc-121">This command finds all versions of Required-Script02.</span></span>

### <span data-ttu-id="1dffc-122">示例7：查找脚本及其依赖项</span><span class="sxs-lookup"><span data-stu-id="1dffc-122">Example 7: Find a script and its dependencies</span></span>

```
PS C:\> Find-Script -Name "Script-WithDependencies1" -IncludeDependencies -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Script-WithDependencies1            Script     LocalRepo1           Description for the Script-WithDependencies1 script
2.0        RequiredModule3                     Script     LocalRepo1           RequiredModule3 module
2.5        Required-Script1                    Script     LocalRepo1           Description for the Required-Script1 script
2.5        Required-Script2                    Script     LocalRepo1           Description for the Required-Script2 script
```

<span data-ttu-id="1dffc-123">此命令查找脚本及其依赖项。</span><span class="sxs-lookup"><span data-stu-id="1dffc-123">This command finds a script and its dependencies.</span></span>

### <span data-ttu-id="1dffc-124">示例8：查找具有指定标记的脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-124">Example 8: Find scripts with the specified tag</span></span>

```
PS C:\> Find-Script -Tag "Tag1" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
1.0        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
```

<span data-ttu-id="1dffc-125">此命令在 LocalRepo1 存储库中查找具有标记 Tag1 的脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-125">This command finds scripts that have the tag Tag1 in the LocalRepo1 repository</span></span>

### <span data-ttu-id="1dffc-126">示例9：查找具有指定命令名的脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-126">Example 9: Find scripts with specified command name</span></span>

```
PS C:\> Find-Script -Command Test-FunctionFromScript_Required-Script3 -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script3                    Script     LocalRepo1           Description for the Required-Script3 script
```

<span data-ttu-id="1dffc-127">此命令查找包含指定命令名称的脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-127">This command finds a script that contains the specified command name.</span></span>

### <span data-ttu-id="1dffc-128">示例10：查找包含工作流的脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-128">Example 10: Find scripts with workflows</span></span>

```
PS C:\> Find-Script -Includes "Workflow" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Fabrikam-ClientScript               Script     LocalRepo1           Description for the Fabrikam-ClientScript script
1.0        Fabrikam-Script                     Script     LocalRepo1           Description for the Fabrikam-Script script
```

<span data-ttu-id="1dffc-129">此命令在 LocalRepo1 存储库中查找工作流脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-129">This command finds workflow scripts in the LocalRepo1 repository.</span></span>

### <span data-ttu-id="1dffc-130">示例11：使用通配符查找脚本</span><span class="sxs-lookup"><span data-stu-id="1dffc-130">Example 11: Find scripts using wildcards</span></span>

```
PS C:\> Find-Script -Name "Required-Script*" -Repository "LocalRepo1"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="1dffc-131">此命令使用通配符 ( \* ) 查找以必需-Script 开头的脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-131">This command uses the wildcard character (\*) to find scripts that begin with Required-Script.</span></span>

## <span data-ttu-id="1dffc-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1dffc-132">PARAMETERS</span></span>

### <span data-ttu-id="1dffc-133">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="1dffc-133">-AllowPrerelease</span></span>

<span data-ttu-id="1dffc-134">包括标记为预发行的结果脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-134">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="1dffc-135">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="1dffc-135">-AllVersions</span></span>

<span data-ttu-id="1dffc-136">指示此操作查找所有脚本版本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-136">Indicates that this operation finds all script versions.</span></span>

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

### <span data-ttu-id="1dffc-137">-Command</span><span class="sxs-lookup"><span data-stu-id="1dffc-137">-Command</span></span>

<span data-ttu-id="1dffc-138">指定要在脚本中查找的命令数组。</span><span class="sxs-lookup"><span data-stu-id="1dffc-138">Specifies an array of commands to find in scripts.</span></span>
<span data-ttu-id="1dffc-139">命令可以是函数或工作流。</span><span class="sxs-lookup"><span data-stu-id="1dffc-139">A command can be a function or workflow.</span></span>

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

### <span data-ttu-id="1dffc-140">-Credential</span><span class="sxs-lookup"><span data-stu-id="1dffc-140">-Credential</span></span>

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

### <span data-ttu-id="1dffc-141">-Filter</span><span class="sxs-lookup"><span data-stu-id="1dffc-141">-Filter</span></span>

<span data-ttu-id="1dffc-142">基于 PackageManagement 提供程序特定的搜索语法查找脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-142">Finds scripts based on the PackageManagement provider-specific search syntax.</span></span>

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

### <span data-ttu-id="1dffc-143">-IncludeDependencies</span><span class="sxs-lookup"><span data-stu-id="1dffc-143">-IncludeDependencies</span></span>

<span data-ttu-id="1dffc-144">指示此操作获取所有依赖于 *Name* 参数中指定的脚本的脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-144">Indicates that this operation gets all scripts that are dependent upon the script specified in the *Name* parameter.</span></span>

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

### <span data-ttu-id="1dffc-145">-Includes</span><span class="sxs-lookup"><span data-stu-id="1dffc-145">-Includes</span></span>

<span data-ttu-id="1dffc-146">指定要获取的脚本类型。</span><span class="sxs-lookup"><span data-stu-id="1dffc-146">Specifies type of script to get.</span></span>
<span data-ttu-id="1dffc-147">此参数的可接受值为： Function，Workflow。</span><span class="sxs-lookup"><span data-stu-id="1dffc-147">The acceptable values for this parameter are: Function, Workflow.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Function, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1dffc-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="1dffc-148">-MaximumVersion</span></span>

<span data-ttu-id="1dffc-149">指定要查找的最大或最新版本的脚本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-149">Specifies the maximum, or newest, version of the script to find.</span></span>
<span data-ttu-id="1dffc-150">MaximumVersion  和 RequiredVersion  参数互斥，不能在同一命令中使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="1dffc-150">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1dffc-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1dffc-151">-MinimumVersion</span></span>

<span data-ttu-id="1dffc-152">指定要查找的脚本的最低版本。</span><span class="sxs-lookup"><span data-stu-id="1dffc-152">Specifies the minimum version of the script to find.</span></span>
<span data-ttu-id="1dffc-153">MinimumVersion  和 RequiredVersion  参数互斥，不能在同一命令中使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="1dffc-153">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1dffc-154">-Name</span><span class="sxs-lookup"><span data-stu-id="1dffc-154">-Name</span></span>

<span data-ttu-id="1dffc-155">指定要查找的脚本的名称数组。</span><span class="sxs-lookup"><span data-stu-id="1dffc-155">Specifies an array of names of scripts to find.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="1dffc-156">-Proxy</span><span class="sxs-lookup"><span data-stu-id="1dffc-156">-Proxy</span></span>

<span data-ttu-id="1dffc-157">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="1dffc-157">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="1dffc-158">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="1dffc-158">-ProxyCredential</span></span>

<span data-ttu-id="1dffc-159">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1dffc-159">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="1dffc-160">-Repository</span><span class="sxs-lookup"><span data-stu-id="1dffc-160">-Repository</span></span>

<span data-ttu-id="1dffc-161">指定已通过运行 Register-psrepository 注册的存储库的友好名称。</span><span class="sxs-lookup"><span data-stu-id="1dffc-161">Specifies the friendly name of a repository that has been registered by running Register-PSRepository.</span></span>

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

### <span data-ttu-id="1dffc-162">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="1dffc-162">-RequiredVersion</span></span>

<span data-ttu-id="1dffc-163">指定要查找的脚本的准确版本号。</span><span class="sxs-lookup"><span data-stu-id="1dffc-163">Specifies the exact version number of the script to find.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1dffc-164">-Tag</span><span class="sxs-lookup"><span data-stu-id="1dffc-164">-Tag</span></span>

<span data-ttu-id="1dffc-165">指定标记的数组。</span><span class="sxs-lookup"><span data-stu-id="1dffc-165">Specifies an array of tags.</span></span>

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

### <span data-ttu-id="1dffc-166">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1dffc-166">CommonParameters</span></span>

<span data-ttu-id="1dffc-167">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="1dffc-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1dffc-168">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="1dffc-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1dffc-169">输入</span><span class="sxs-lookup"><span data-stu-id="1dffc-169">INPUTS</span></span>

### <span data-ttu-id="1dffc-170">System.String[]</span><span class="sxs-lookup"><span data-stu-id="1dffc-170">System.String[]</span></span>

### <span data-ttu-id="1dffc-171">System.String</span><span class="sxs-lookup"><span data-stu-id="1dffc-171">System.String</span></span>

### <span data-ttu-id="1dffc-172">System.Uri</span><span class="sxs-lookup"><span data-stu-id="1dffc-172">System.Uri</span></span>

### <span data-ttu-id="1dffc-173">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="1dffc-173">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="1dffc-174">输出</span><span class="sxs-lookup"><span data-stu-id="1dffc-174">OUTPUTS</span></span>

### <span data-ttu-id="1dffc-175">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="1dffc-175">PSRepositoryItemInfo</span></span>

## <span data-ttu-id="1dffc-176">注释</span><span class="sxs-lookup"><span data-stu-id="1dffc-176">NOTES</span></span>

## <span data-ttu-id="1dffc-177">相关链接</span><span class="sxs-lookup"><span data-stu-id="1dffc-177">RELATED LINKS</span></span>

[<span data-ttu-id="1dffc-178">Install-Script</span><span class="sxs-lookup"><span data-stu-id="1dffc-178">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="1dffc-179">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="1dffc-179">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="1dffc-180">Save-Script</span><span class="sxs-lookup"><span data-stu-id="1dffc-180">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="1dffc-181">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="1dffc-181">Uninstall-Script</span></span>](Uninstall-Script.md)

[<span data-ttu-id="1dffc-182">Update-Script</span><span class="sxs-lookup"><span data-stu-id="1dffc-182">Update-Script</span></span>](Update-Script.md)
