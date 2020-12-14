---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/03/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/find-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Command
ms.openlocfilehash: eb305801bb6f8c84ffdf0ff34936ec3156ba5b0e
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891248"
---
# <span data-ttu-id="20f53-103">Find-Command</span><span class="sxs-lookup"><span data-stu-id="20f53-103">Find-Command</span></span>

## <span data-ttu-id="20f53-104">摘要</span><span class="sxs-lookup"><span data-stu-id="20f53-104">SYNOPSIS</span></span>
<span data-ttu-id="20f53-105">查找模块中的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="20f53-105">Finds PowerShell commands in modules.</span></span>

## <span data-ttu-id="20f53-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20f53-106">SYNTAX</span></span>

### <span data-ttu-id="20f53-107">全部</span><span class="sxs-lookup"><span data-stu-id="20f53-107">All</span></span>

```
Find-Command [[-Name] <String[]>] [-ModuleName <String>] [-MinimumVersion <String>]
 [-MaximumVersion <String>] [-RequiredVersion <String>] [-AllVersions] [-AllowPrerelease]
 [-Tag <String[]>] [-Filter <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Repository <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="20f53-108">说明</span><span class="sxs-lookup"><span data-stu-id="20f53-108">DESCRIPTION</span></span>

<span data-ttu-id="20f53-109">`Find-Command`Cmdlet 将查找 cmdlet、别名、函数和工作流等 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="20f53-109">The `Find-Command` cmdlet finds PowerShell commands such as cmdlets, aliases, functions, and workflows.</span></span> <span data-ttu-id="20f53-110">`Find-Command` 搜索已注册存储库中的模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-110">`Find-Command` searches modules in registered repositories.</span></span>

<span data-ttu-id="20f53-111">对于找到的每个命令 `Find-Command` ，将返回一个 **PSGetCommandInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="20f53-111">For each command found by `Find-Command`, a **PSGetCommandInfo** object is returned.</span></span> <span data-ttu-id="20f53-112">可以通过管道将 **PSGetCommandInfo** 对象发送到 `Install-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="20f53-112">The **PSGetCommandInfo** object can be sent down the pipeline to the `Install-Module` cmdlet.</span></span>
<span data-ttu-id="20f53-113">`Install-Module` 安装包含命令的模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-113">`Install-Module` installs the module that contains the command.</span></span>

## <span data-ttu-id="20f53-114">示例</span><span class="sxs-lookup"><span data-stu-id="20f53-114">EXAMPLES</span></span>

### <span data-ttu-id="20f53-115">示例 1：在指定存储库中查找所有命令</span><span class="sxs-lookup"><span data-stu-id="20f53-115">Example 1: Find all commands in a specified repository</span></span>

<span data-ttu-id="20f53-116">`Find-Command`Cmdlet 将在已注册的存储库中搜索模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-116">The `Find-Command` cmdlet searches a registered repository for modules.</span></span>

```powershell
Find-Command -Repository PSGallery | Select-Object -First 10
```

```output
Name                                Version    ModuleName          Repository
----                                -------    ----------          ----------
Disable-AzureRmDataCollection       5.8.3      AzureRM.profile     PSGallery
Disable-AzureRmContextAutosave      5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmDataCollection        5.8.3      AzureRM.profile     PSGallery
Enable-AzureRmContextAutosave       5.8.3      AzureRM.profile     PSGallery
Remove-AzureRmEnvironment           5.8.3      AzureRM.profile     PSGallery
Get-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Set-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Add-AzureRmEnvironment              5.8.3      AzureRM.profile     PSGallery
Get-AzureRmSubscription             5.8.3      AzureRM.profile     PSGallery
Connect-AzureRmAccount              5.8.3      AzureRM.profile     PSGallery
```

<span data-ttu-id="20f53-117">`Find-Command` 使用 **存储** 库参数指定已注册的存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="20f53-117">`Find-Command` uses the **Repository** parameter to specify a registered repository's name.</span></span> <span data-ttu-id="20f53-118">对象沿管道向下发送。</span><span class="sxs-lookup"><span data-stu-id="20f53-118">The objects are sent down the pipeline.</span></span> <span data-ttu-id="20f53-119">`Select-Object` 接收对象，并使用 **第** 一个参数来显示前10个结果。</span><span class="sxs-lookup"><span data-stu-id="20f53-119">`Select-Object` receives the objects and uses the **First** parameter to display the first 10 results.</span></span>

### <span data-ttu-id="20f53-120">示例 2：按名称查找命令</span><span class="sxs-lookup"><span data-stu-id="20f53-120">Example 2: Find a command by name</span></span>

<span data-ttu-id="20f53-121">`Find-Command` 可以使用命令名称在存储库中查找模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-121">`Find-Command` can use the name of a command to locate the module in a repository.</span></span> <span data-ttu-id="20f53-122">命令名称可能存在于多个 **ModuleNames** 中。</span><span class="sxs-lookup"><span data-stu-id="20f53-122">It's possible that a command name exists in multiple **ModuleNames**.</span></span>

```powershell
Find-Command -Repository PSGallery -Name Get-TargetResource
```

```Output
Name                  Version    ModuleName                      Repository
----                  -------    ----------                      ----------
Get-TargetResource    3.1.0.0    xPowerShellExecutionPolicy      PSGallery
Get-TargetResource    1.0.0      xInternetExplorerHomePage       PSGallery
Get-TargetResource    1.2.0.0    SystemLocaleDsc                 PSGallery
```

<span data-ttu-id="20f53-123">`Find-Command` 使用 **存储库** 参数搜索 **PSGallery**。</span><span class="sxs-lookup"><span data-stu-id="20f53-123">`Find-Command` uses the **Repository** parameter to search the **PSGallery**.</span></span> <span data-ttu-id="20f53-124">**Name** 参数指定命令 **test-targetresource**。</span><span class="sxs-lookup"><span data-stu-id="20f53-124">The **Name** parameter specifies the command **Get-TargetResource**.</span></span>

### <span data-ttu-id="20f53-125">示例3：按名称查找命令并安装模块</span><span class="sxs-lookup"><span data-stu-id="20f53-125">Example 3: Find commands by name and install the module</span></span>

<span data-ttu-id="20f53-126">`Find-Command` 可以找到命令和模块，然后将对象发送到 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="20f53-126">`Find-Command` can locate the command and module, then send the object to `Install-Module`.</span></span> <span data-ttu-id="20f53-127">如果在多个模块中包含一个命令，请使用 `Find-Command` Cmdlet **Module-Name** 参数。</span><span class="sxs-lookup"><span data-stu-id="20f53-127">If a command is included in multiple modules, use the `Find-Command` cmdlets **Module-Name** parameter.</span></span>
<span data-ttu-id="20f53-128">否则，可能会安装不希望安装的模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-128">Otherwise, modules might be installed that you didn't want to install.</span></span>

```powershell
PS> Find-Command -Name Get-TargetResource -Repository PSGallery -ModuleName SystemLocaleDsc |
    Install-Module

PS> Get-InstalledModule

Version   Name               Repository   Description
-------   ----               ----------   -----------
1.2.0.0   SystemLocaleDsc    PSGallery    This DSC Resource allows configuration of the Windows...
```

<span data-ttu-id="20f53-129">`Find-Command` 使用 **Name** 参数指定命令 **test-targetresource**。</span><span class="sxs-lookup"><span data-stu-id="20f53-129">`Find-Command` uses the **Name** parameter to specify the command **Get-TargetResource**.</span></span> <span data-ttu-id="20f53-130">**存储库** 参数搜索 **PSGallery**。</span><span class="sxs-lookup"><span data-stu-id="20f53-130">The **Repository** parameter searches the **PSGallery**.</span></span> <span data-ttu-id="20f53-131">**ModuleName** 参数指定要安装的模块 **SystemLocaleDsc**。</span><span class="sxs-lookup"><span data-stu-id="20f53-131">The **ModuleName** parameter specifies the module you want to install, **SystemLocaleDsc**.</span></span> <span data-ttu-id="20f53-132">将对象向下发送到 `Install-Module` ，并安装该模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-132">The object is sent down the pipeline to `Install-Module` and the module is installed.</span></span> <span data-ttu-id="20f53-133">安装完成后，可以使用 `Get-InstalledModule` 来显示结果。</span><span class="sxs-lookup"><span data-stu-id="20f53-133">After the installation finishes, you can use `Get-InstalledModule` to display the results.</span></span>

### <span data-ttu-id="20f53-134">示例 4：查找命令并保存其模块</span><span class="sxs-lookup"><span data-stu-id="20f53-134">Example 4: Find a command and save its module</span></span>

```
PS> Find-Command -Name Invoke-ScriptAnalyzer -Repository PSGallery | Save-Module -Path C:\Test\Modules -Verbose

VERBOSE: Downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'https://www.powershellgallery.com/api/v2/package/PSScriptAnalyzer/1.18.0'.
VERBOSE: Completed downloading 'PSScriptAnalyzer'.
VERBOSE: Module 'PSScriptAnalyzer' was saved successfully to path 'C:\Test\Modules\PSScriptAnalyzer\1.18.0'.
```

<span data-ttu-id="20f53-135">`Find-Command`使用 **Name** 和 **Repository** 参数在 **PSGallery** 存储库中搜索命令 **ScriptAnalyzer** 。</span><span class="sxs-lookup"><span data-stu-id="20f53-135">`Find-Command` uses the **Name** and **Repository** parameters to search for the command **Invoke-ScriptAnalyzer** in the **PSGallery** repository.</span></span> <span data-ttu-id="20f53-136">将对象向下发送到 `Save-Module` 。</span><span class="sxs-lookup"><span data-stu-id="20f53-136">The object is sent down the pipeline to `Save-Module`.</span></span> <span data-ttu-id="20f53-137">**Path** 参数确定保存模块的位置。</span><span class="sxs-lookup"><span data-stu-id="20f53-137">The **Path** parameter determines the location to save the module.</span></span> <span data-ttu-id="20f53-138">"**详细**" 是一个可选参数，但在 PowerShell 控制台中显示状态输出。</span><span class="sxs-lookup"><span data-stu-id="20f53-138">**Verbose** is an optional parameter, but displays status output in the PowerShell console.</span></span> <span data-ttu-id="20f53-139">详细输出对于故障排除非常有用。</span><span class="sxs-lookup"><span data-stu-id="20f53-139">The verbose output is beneficial for troubleshooting.</span></span>

## <span data-ttu-id="20f53-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20f53-140">PARAMETERS</span></span>

### <span data-ttu-id="20f53-141">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="20f53-141">-AllowPrerelease</span></span>

<span data-ttu-id="20f53-142">在结果中包括标记为预发行的模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-142">Includes modules marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="20f53-143">-AllVersions</span><span class="sxs-lookup"><span data-stu-id="20f53-143">-AllVersions</span></span>

<span data-ttu-id="20f53-144">指示此 cmdlet 获取模块的所有版本。</span><span class="sxs-lookup"><span data-stu-id="20f53-144">Indicates that this cmdlet gets all versions of a module.</span></span>

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

### <span data-ttu-id="20f53-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="20f53-145">-Filter</span></span>

<span data-ttu-id="20f53-146">基于 **PackageManagement** 提供程序的搜索语法查找模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-146">Finds modules based on the **PackageManagement** provider's search syntax.</span></span> <span data-ttu-id="20f53-147">例如，指定要在 **ModuleName** 和 **Description** 属性内搜索的字词。</span><span class="sxs-lookup"><span data-stu-id="20f53-147">For example, specify words to search for within the **ModuleName** and **Description** properties.</span></span>

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

### <span data-ttu-id="20f53-148">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="20f53-148">-MaximumVersion</span></span>

<span data-ttu-id="20f53-149">指定要包含在结果中的模块的最高版本。</span><span class="sxs-lookup"><span data-stu-id="20f53-149">Specifies the maximum version of the module to include in results.</span></span> <span data-ttu-id="20f53-150">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="20f53-150">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="20f53-151">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="20f53-151">-MinimumVersion</span></span>

<span data-ttu-id="20f53-152">指定要包括在结果中的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="20f53-152">Specifies the minimum version of the module to include in results.</span></span> <span data-ttu-id="20f53-153">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="20f53-153">The **MinimumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="20f53-154">-ModuleName</span><span class="sxs-lookup"><span data-stu-id="20f53-154">-ModuleName</span></span>

<span data-ttu-id="20f53-155">指定要在其中搜索命令的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="20f53-155">Specifies the name of a module to search for commands.</span></span> <span data-ttu-id="20f53-156">默认值为所有模块。</span><span class="sxs-lookup"><span data-stu-id="20f53-156">The default is all modules.</span></span>

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

### <span data-ttu-id="20f53-157">-Name</span><span class="sxs-lookup"><span data-stu-id="20f53-157">-Name</span></span>

<span data-ttu-id="20f53-158">指定要在存储库中搜索的命令名。</span><span class="sxs-lookup"><span data-stu-id="20f53-158">Specifies the command name to search for in a repository.</span></span> <span data-ttu-id="20f53-159">使用逗号分隔命令名称的数组。</span><span class="sxs-lookup"><span data-stu-id="20f53-159">Use commas to separate an array of command names.</span></span>

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

### <span data-ttu-id="20f53-160">-Proxy</span><span class="sxs-lookup"><span data-stu-id="20f53-160">-Proxy</span></span>

<span data-ttu-id="20f53-161">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="20f53-161">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

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

### <span data-ttu-id="20f53-162">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="20f53-162">-ProxyCredential</span></span>

<span data-ttu-id="20f53-163">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="20f53-163">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="20f53-164">-Repository</span><span class="sxs-lookup"><span data-stu-id="20f53-164">-Repository</span></span>

<span data-ttu-id="20f53-165">指定用于搜索命令的存储库。</span><span class="sxs-lookup"><span data-stu-id="20f53-165">Specifies the repository to search for commands.</span></span> <span data-ttu-id="20f53-166">使用逗号分隔存储库名称数组。</span><span class="sxs-lookup"><span data-stu-id="20f53-166">Use commas to separate an array of repository names.</span></span> <span data-ttu-id="20f53-167">默认值为所有存储库。</span><span class="sxs-lookup"><span data-stu-id="20f53-167">The default is all repositories.</span></span>

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

### <span data-ttu-id="20f53-168">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="20f53-168">-RequiredVersion</span></span>

<span data-ttu-id="20f53-169">指定要包括在结果中的模块的版本。</span><span class="sxs-lookup"><span data-stu-id="20f53-169">Specifies the version of the module to include in the results.</span></span>

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

### <span data-ttu-id="20f53-170">-Tag</span><span class="sxs-lookup"><span data-stu-id="20f53-170">-Tag</span></span>

<span data-ttu-id="20f53-171">指定对存储库中的模块进行分类的标记。</span><span class="sxs-lookup"><span data-stu-id="20f53-171">Specifies tags that categorize modules in a repository.</span></span> <span data-ttu-id="20f53-172">使用逗号分隔标记数组。</span><span class="sxs-lookup"><span data-stu-id="20f53-172">Use commas to separate an array of tags.</span></span>

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

### <span data-ttu-id="20f53-173">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20f53-173">CommonParameters</span></span>

<span data-ttu-id="20f53-174">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="20f53-174">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20f53-175">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="20f53-175">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20f53-176">输入</span><span class="sxs-lookup"><span data-stu-id="20f53-176">INPUTS</span></span>

## <span data-ttu-id="20f53-177">输出</span><span class="sxs-lookup"><span data-stu-id="20f53-177">OUTPUTS</span></span>

### <span data-ttu-id="20f53-178">PSGetCommandInfo</span><span class="sxs-lookup"><span data-stu-id="20f53-178">PSGetCommandInfo</span></span>

<span data-ttu-id="20f53-179">`Find-Command` 输出 **PSGetCommandInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="20f53-179">`Find-Command` outputs a **PSGetCommandInfo** object.</span></span>

## <span data-ttu-id="20f53-180">注释</span><span class="sxs-lookup"><span data-stu-id="20f53-180">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20f53-181">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="20f53-181">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="20f53-182">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="20f53-182">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="20f53-183">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="20f53-183">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="20f53-184">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="20f53-184">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="20f53-185">相关链接</span><span class="sxs-lookup"><span data-stu-id="20f53-185">RELATED LINKS</span></span>

[<span data-ttu-id="20f53-186">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="20f53-186">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="20f53-187">Install-Module</span><span class="sxs-lookup"><span data-stu-id="20f53-187">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="20f53-188">Save-Module</span><span class="sxs-lookup"><span data-stu-id="20f53-188">Save-Module</span></span>](Save-Module.md)

[<span data-ttu-id="20f53-189">Select-Object</span><span class="sxs-lookup"><span data-stu-id="20f53-189">Select-Object</span></span>](../Microsoft.PowerShell.Utility/Select-Object.md)

[<span data-ttu-id="20f53-190">Uninstall-模块</span><span class="sxs-lookup"><span data-stu-id="20f53-190">Uninstall-Module</span></span>](Uninstall-Module.md)
