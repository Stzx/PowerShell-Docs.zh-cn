---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/05/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-rolecapability?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-RoleCapability
ms.openlocfilehash: d3300e0f378139cc873ffef1e798326100644d94
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94889804"
---
# <span data-ttu-id="c00da-103">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="c00da-103">Find-RoleCapability</span></span>

## <span data-ttu-id="c00da-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c00da-104">SYNOPSIS</span></span>
<span data-ttu-id="c00da-105">在模块中查找角色功能。</span><span class="sxs-lookup"><span data-stu-id="c00da-105">Finds role capabilities in modules.</span></span>

## <span data-ttu-id="c00da-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c00da-106">SYNTAX</span></span>

### <span data-ttu-id="c00da-107">全部</span><span class="sxs-lookup"><span data-stu-id="c00da-107">All</span></span>

```
Find-RoleCapability [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
[-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
[-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
[-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="c00da-108">说明</span><span class="sxs-lookup"><span data-stu-id="c00da-108">DESCRIPTION</span></span>

<span data-ttu-id="c00da-109">`Find-RoleCapability`Cmdlet 可搜索已注册的存储库，以便查找 PowerShell 角色功能和模块。</span><span class="sxs-lookup"><span data-stu-id="c00da-109">The `Find-RoleCapability` cmdlet searches registered repositories to find PowerShell role capabilities and modules.</span></span>

<span data-ttu-id="c00da-110">对于找到的每个角色功能 `Find-RoleCapability` ，都将返回 **PSGetRoleCapabilityInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="c00da-110">For each role capability found by `Find-RoleCapability`, a **PSGetRoleCapabilityInfo** object is returned.</span></span> <span data-ttu-id="c00da-111">可以通过管道将 **PSGetRoleCapabilityInfo** 对象发送到 `Install-Module` 或 `Save-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c00da-111">**PSGetRoleCapabilityInfo** objects can be sent down the pipeline to the `Install-Module` or `Save-Module` cmdlets.</span></span>

<span data-ttu-id="c00da-112">PowerShell 角色功能定义 (JEA) 终结点上的足够管理的用户可使用哪些命令和应用程序。</span><span class="sxs-lookup"><span data-stu-id="c00da-112">PowerShell role capabilities define which commands and applications are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="c00da-113">角色功能由扩展名为的文件定义 `.psrc` 。</span><span class="sxs-lookup"><span data-stu-id="c00da-113">Role capabilities are defined by files with a `.psrc` extension.</span></span>

## <span data-ttu-id="c00da-114">示例</span><span class="sxs-lookup"><span data-stu-id="c00da-114">EXAMPLES</span></span>

### <span data-ttu-id="c00da-115">示例1：查找角色功能</span><span class="sxs-lookup"><span data-stu-id="c00da-115">Example 1: Find role capabilities</span></span>

<span data-ttu-id="c00da-116">`Find-RoleCapability` 查找每个已注册存储库中的角色功能。</span><span class="sxs-lookup"><span data-stu-id="c00da-116">`Find-RoleCapability` finds role capabilities in each registered repository.</span></span> <span data-ttu-id="c00da-117">若要搜索特定存储库，请使用 **存储库** 参数。</span><span class="sxs-lookup"><span data-stu-id="c00da-117">To search a specific repository, use the **Repository** parameter.</span></span>

```powershell
Find-RoleCapability
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
General-Lev2     1.0        JeaExamples    PSGallery
IIS-Lev1         1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="c00da-118">示例2：按名称查找角色功能</span><span class="sxs-lookup"><span data-stu-id="c00da-118">Example 2: Find role capabilities by name</span></span>

<span data-ttu-id="c00da-119">`Find-RoleCapability` 按名称查找角色功能。</span><span class="sxs-lookup"><span data-stu-id="c00da-119">`Find-RoleCapability` finds role capabilities by name.</span></span> <span data-ttu-id="c00da-120">使用逗号分隔名称数组。</span><span class="sxs-lookup"><span data-stu-id="c00da-120">Use commas to separate an array of names.</span></span>

```powershell
Find-RoleCapability -Name General-Lev1, IIS-Lev2
```

```output
Name             Version    ModuleName     Repository
----             -------    ----------     ----------
General-Lev1     1.0        JeaExamples    PSGallery
IIS-Lev2         1.0        JeaExamples    PSGallery
```

### <span data-ttu-id="c00da-121">示例3：查找并保存角色功能的模块</span><span class="sxs-lookup"><span data-stu-id="c00da-121">Example 3: Find and save a role capability's module</span></span>

<span data-ttu-id="c00da-122">`Find-RoleCapability`Cmdlet 查找角色功能，并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="c00da-122">The `Find-RoleCapability` cmdlet finds a role capability and sends the object down the pipeline.</span></span>
<span data-ttu-id="c00da-123">`Save-Module` 将角色功能的模块保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="c00da-123">`Save-Module` saves the role capability's module to a file system.</span></span> <span data-ttu-id="c00da-124">`Get-ChildItem` 显示模块目录的内容。</span><span class="sxs-lookup"><span data-stu-id="c00da-124">`Get-ChildItem` displays the contents of the module's directory.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Save-Module -Path C:\Test\Modules

PS> Get-ChildItem -Path C:\Test\Modules\JeaExamples\1.0\

    Directory: C:\Test\Modules\JeaExamples\1.0

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----          6/4/2019    16:37                RoleCapabilities
-a----          2/5/2019    18:46           1702 CreateRegisterPSSC.ps1
-a----          2/5/2019    18:46           7656 JeaExamples.psd1
-a----         10/1/2018    08:16            595 JeaExamples.psm1
```

<span data-ttu-id="c00da-125">`Find-RoleCapability` 使用 **Name** 参数指定 **一般的 Lev1** 角色功能。</span><span class="sxs-lookup"><span data-stu-id="c00da-125">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="c00da-126">对象沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="c00da-126">The object is sent down the pipeline.</span></span> <span data-ttu-id="c00da-127">`Save-Module` 使用文件系统位置的 **Path** 参数保存模块。</span><span class="sxs-lookup"><span data-stu-id="c00da-127">`Save-Module` uses the **Path** parameter for the file system location to save the module.</span></span> <span data-ttu-id="c00da-128">保存该模块后，将 `Get-ChildItem` 指定该模块的 **路径** 并显示 **JeaExamples** 模块的目录的内容。</span><span class="sxs-lookup"><span data-stu-id="c00da-128">After the module is saved, `Get-ChildItem` specifies the module's **Path** and displays the contents of the **JeaExamples** module's directory.</span></span>

### <span data-ttu-id="c00da-129">示例4：查找和安装角色功能的模块</span><span class="sxs-lookup"><span data-stu-id="c00da-129">Example 4: Find and install a role capability's module</span></span>

<span data-ttu-id="c00da-130">`Find-RoleCapability` 查找模块并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="c00da-130">`Find-RoleCapability` finds the module and sends the object down the pipeline.</span></span> <span data-ttu-id="c00da-131">`Install-Module` 安装模块。</span><span class="sxs-lookup"><span data-stu-id="c00da-131">`Install-Module` installs the module.</span></span> <span data-ttu-id="c00da-132">安装后，请使用 `Get-InstalledModule` 查看结果。</span><span class="sxs-lookup"><span data-stu-id="c00da-132">After the installation, use `Get-InstalledModule` to see the results.</span></span>

```
PS> Find-RoleCapability -Name General-Lev1 | Install-Module -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/JeaExamples/1.0.0'.
VERBOSE: Completed downloading 'JeaExamples'.
VERBOSE: InstallPackageLocal' - name='JeaExamples', version='1.0',
VERBOSE: Validating the 'JeaExamples' module contents
VERBOSE: Test-ModuleManifest successfully validated the module manifest file
VERBOSE: Module 'JeaExamples' was installed successfully to path

PS> Get-InstalledModule

Version    Name            Repository     Description
-------    ----            ----------     -----------
1.0        JeaExamples     PSGallery      Some example Jea roles for general server maintenance...
```

<span data-ttu-id="c00da-133">`Find-RoleCapability` 使用 **Name** 参数指定 **一般的 Lev1** 角色功能。</span><span class="sxs-lookup"><span data-stu-id="c00da-133">`Find-RoleCapability` uses the **Name** parameter to specify the **General-Lev1** role capability.</span></span>
<span data-ttu-id="c00da-134">对象沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="c00da-134">The object is sent down the pipeline.</span></span> <span data-ttu-id="c00da-135">`Install-Module` 使用 **Verbose** 参数显示安装过程中的状态消息。</span><span class="sxs-lookup"><span data-stu-id="c00da-135">`Install-Module` uses the **Verbose** parameter to display status messages during the installation.</span></span> <span data-ttu-id="c00da-136">安装完成后， `Get-InstalledModule` 输出确认已安装 **JeaExamples** 模块。</span><span class="sxs-lookup"><span data-stu-id="c00da-136">After the install is finished, the `Get-InstalledModule` output confirms that the **JeaExamples** module was installed.</span></span>

## <span data-ttu-id="c00da-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c00da-137">PARAMETERS</span></span>

### <span data-ttu-id="c00da-138">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="c00da-138">-AllowPrerelease</span></span>

<span data-ttu-id="c00da-139">在结果中包括标记为预发行的资源。</span><span class="sxs-lookup"><span data-stu-id="c00da-139">Includes resources marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="c00da-140">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="c00da-140">-AllVersions</span></span>

<span data-ttu-id="c00da-141">指示此 cmdlet 获取模块的所有版本。</span><span class="sxs-lookup"><span data-stu-id="c00da-141">Indicates that this cmdlet gets all versions of a module.</span></span> <span data-ttu-id="c00da-142">**AllVersions** 参数显示模块的每个可用版本。</span><span class="sxs-lookup"><span data-stu-id="c00da-142">The **AllVersions** parameter displays each of a module's available versions.</span></span>

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

### <span data-ttu-id="c00da-143">-Filter</span><span class="sxs-lookup"><span data-stu-id="c00da-143">-Filter</span></span>

<span data-ttu-id="c00da-144">基于 **PackageManagement** 提供程序的搜索语法查找资源。</span><span class="sxs-lookup"><span data-stu-id="c00da-144">Finds resources based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="c00da-145">例如，指定要在 **ModuleName** 和 **Description** 属性内搜索的字词。</span><span class="sxs-lookup"><span data-stu-id="c00da-145">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="c00da-146">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="c00da-146">-MaximumVersion</span></span>

<span data-ttu-id="c00da-147">指定要包含在结果中的模块的最高版本。</span><span class="sxs-lookup"><span data-stu-id="c00da-147">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="c00da-148">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="c00da-148">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c00da-149">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="c00da-149">-MinimumVersion</span></span>

<span data-ttu-id="c00da-150">指定要包括在结果中的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="c00da-150">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="c00da-151">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="c00da-151">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c00da-152">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="c00da-152">-ModuleName</span></span>

<span data-ttu-id="c00da-153">指定要在其中搜索角色功能的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="c00da-153">Specifies the name of the module in which to search for role capabilities.</span></span> <span data-ttu-id="c00da-154">默认值为所有模块。</span><span class="sxs-lookup"><span data-stu-id="c00da-154">The default is all modules.</span></span>

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

### <span data-ttu-id="c00da-155">-Name</span><span class="sxs-lookup"><span data-stu-id="c00da-155">-Name</span></span>

<span data-ttu-id="c00da-156">指定角色功能的名称。</span><span class="sxs-lookup"><span data-stu-id="c00da-156">Specifies the name of a role capability.</span></span> <span data-ttu-id="c00da-157">默认值为所有角色功能。</span><span class="sxs-lookup"><span data-stu-id="c00da-157">The default is all role capabilities.</span></span> <span data-ttu-id="c00da-158">使用逗号分隔资源名称的数组。</span><span class="sxs-lookup"><span data-stu-id="c00da-158">Use commas to separate an array of resource names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c00da-159">-Proxy</span><span class="sxs-lookup"><span data-stu-id="c00da-159">-Proxy</span></span>

<span data-ttu-id="c00da-160">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="c00da-160">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="c00da-161">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="c00da-161">-ProxyCredential</span></span>

<span data-ttu-id="c00da-162">指定有权使用 **代理** 参数中指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c00da-162">Specifies a user account with permission to use the proxy server specified in the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="c00da-163">-Repository</span><span class="sxs-lookup"><span data-stu-id="c00da-163">-Repository</span></span>

<span data-ttu-id="c00da-164">指定用于搜索角色功能的存储库。</span><span class="sxs-lookup"><span data-stu-id="c00da-164">Specifies a repository to search for role capabilities.</span></span> <span data-ttu-id="c00da-165">使用逗号分隔存储库名称数组。</span><span class="sxs-lookup"><span data-stu-id="c00da-165">Use commas to separate an array of repository names.</span></span>

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

### <span data-ttu-id="c00da-166">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="c00da-166">-RequiredVersion</span></span>

<span data-ttu-id="c00da-167">指定要包含在结果中的模块的确切版本号。</span><span class="sxs-lookup"><span data-stu-id="c00da-167">Specifies the module's exact version number to include in the results.</span></span> <span data-ttu-id="c00da-168">无法在同一命令中使用 **RequiredVersion** 和 **MinimumVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="c00da-168">The **RequiredVersion** and the **MinimumVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="c00da-169">-Tag</span><span class="sxs-lookup"><span data-stu-id="c00da-169">-Tag</span></span>

<span data-ttu-id="c00da-170">指定对存储库中的模块进行分类的标记。</span><span class="sxs-lookup"><span data-stu-id="c00da-170">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="c00da-171">使用逗号分隔标记数组。</span><span class="sxs-lookup"><span data-stu-id="c00da-171">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="c00da-172">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c00da-172">CommonParameters</span></span>

<span data-ttu-id="c00da-173">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c00da-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c00da-174">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c00da-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c00da-175">输入</span><span class="sxs-lookup"><span data-stu-id="c00da-175">INPUTS</span></span>

## <span data-ttu-id="c00da-176">输出</span><span class="sxs-lookup"><span data-stu-id="c00da-176">OUTPUTS</span></span>

### <span data-ttu-id="c00da-177">PSGetRoleCapabilityInfo</span><span class="sxs-lookup"><span data-stu-id="c00da-177">PSGetRoleCapabilityInfo</span></span>

<span data-ttu-id="c00da-178">`Find-RoleCapability`Cmdlet 将返回 **PSGetRoleCapabilityInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="c00da-178">The `Find-RoleCapability` cmdlet returns a **PSGetRoleCapabilityInfo** object.</span></span>

## <span data-ttu-id="c00da-179">注释</span><span class="sxs-lookup"><span data-stu-id="c00da-179">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c00da-180">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="c00da-180">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="c00da-181">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="c00da-181">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="c00da-182">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="c00da-182">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="c00da-183">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="c00da-183">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="c00da-184">相关链接</span><span class="sxs-lookup"><span data-stu-id="c00da-184">RELATED LINKS</span></span>

[<span data-ttu-id="c00da-185">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="c00da-185">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="c00da-186">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="c00da-186">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="c00da-187">Install-Module</span><span class="sxs-lookup"><span data-stu-id="c00da-187">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="c00da-188">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="c00da-188">New-PSRoleCapabilityFile</span></span>](../Microsoft.PowerShell.Core/New-PSRoleCapabilityFile.md)

[<span data-ttu-id="c00da-189">Save-Module</span><span class="sxs-lookup"><span data-stu-id="c00da-189">Save-Module</span></span>](Save-Module.md)
