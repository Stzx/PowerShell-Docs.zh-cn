---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/16/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Module
ms.openlocfilehash: ee94ba7808cb364306826325cfbc3df2cf9834a5
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94892580"
---
# <span data-ttu-id="4cbd9-103">Update-Module</span><span class="sxs-lookup"><span data-stu-id="4cbd9-103">Update-Module</span></span>

## <span data-ttu-id="4cbd9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4cbd9-104">SYNOPSIS</span></span>
<span data-ttu-id="4cbd9-105">从联机库中下载指定模块的最新版本，并将其安装到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-105">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

## <span data-ttu-id="4cbd9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4cbd9-106">SYNTAX</span></span>

### <span data-ttu-id="4cbd9-107">全部</span><span class="sxs-lookup"><span data-stu-id="4cbd9-107">All</span></span>

```
Update-Module [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Credential <PSCredential>] [-Scope <String>] [-Proxy <Uri>] [-ProxyCredential <PSCredential>]
 [-Force] [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4cbd9-108">说明</span><span class="sxs-lookup"><span data-stu-id="4cbd9-108">DESCRIPTION</span></span>

<span data-ttu-id="4cbd9-109">`Update-Module`Cmdlet 可从联机库中安装模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-109">The `Update-Module` cmdlet installs a module's newest version from an online gallery.</span></span> <span data-ttu-id="4cbd9-110">系统会在安装更新之前提示您确认。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-110">You're prompted to confirm the update before it's installed.</span></span> <span data-ttu-id="4cbd9-111">只会为在本地计算机上安装的模块安装更新 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-111">Updates are installed only for modules that were installed on the local computer with `Install-Module`.</span></span> <span data-ttu-id="4cbd9-112">`Update-Module` 搜索 `$env:PSModulePath` 已安装的模块。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-112">`Update-Module` searches `$env:PSModulePath` for installed modules.</span></span>

<span data-ttu-id="4cbd9-113">`Update-Module` 如果未指定参数，则将更新所有已安装的模块。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-113">`Update-Module` with no parameters specified updates all installed modules.</span></span> <span data-ttu-id="4cbd9-114">若要指定要更新的模块，请使用 **Name** 参数。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-114">To specify a module to update, use the **Name** parameter.</span></span> <span data-ttu-id="4cbd9-115">您可以通过使用 **RequiredVersion** 参数，更新为模块的特定版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-115">You can update to a module's specific version by using the **RequiredVersion** parameter.</span></span>

<span data-ttu-id="4cbd9-116">如果已安装的模块已经是最新版本，则不会更新该模块。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-116">If an installed module is already the newest version, the module isn't updated.</span></span> <span data-ttu-id="4cbd9-117">如果在中找不到该模块 `$env:PSModulePath` ，则会显示错误。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-117">If the module isn't found in `$env:PSModulePath`, an error is displayed.</span></span>

<span data-ttu-id="4cbd9-118">若要显示已安装的模块，请使用 `Get-InstalledModule` 。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-118">To display the installed modules, use `Get-InstalledModule`.</span></span>

## <span data-ttu-id="4cbd9-119">示例</span><span class="sxs-lookup"><span data-stu-id="4cbd9-119">EXAMPLES</span></span>

### <span data-ttu-id="4cbd9-120">示例1：更新所有模块</span><span class="sxs-lookup"><span data-stu-id="4cbd9-120">Example 1: Update all modules</span></span>

<span data-ttu-id="4cbd9-121">此示例将所有已安装的模块更新到联机库中的最新版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-121">This example updates all installed modules to the newest version in an online gallery.</span></span>

```powershell
Update-Module
```

### <span data-ttu-id="4cbd9-122">示例2：按名称更新模块</span><span class="sxs-lookup"><span data-stu-id="4cbd9-122">Example 2: Update a module by name</span></span>

<span data-ttu-id="4cbd9-123">此示例将特定模块更新到联机库中的最新版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-123">This example updates a specific module to the newest version in an online gallery.</span></span>

```powershell
Update-Module -Name SpeculationControl
```

<span data-ttu-id="4cbd9-124">`Update-Module` 使用 **Name** 参数更新特定模块 **SpeculationControl**。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-124">`Update-Module` uses the **Name** parameter to update a specific module, **SpeculationControl**.</span></span>

### <span data-ttu-id="4cbd9-125">示例3：查看模拟 Update-Module 运行</span><span class="sxs-lookup"><span data-stu-id="4cbd9-125">Example 3: View what-if Update-Module runs</span></span>

<span data-ttu-id="4cbd9-126">此示例执行一个假设方案来显示在运行时所发生 `Update-Module` 的情况。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-126">This example does a what-if scenario to show what happens if `Update-Module` is run.</span></span> <span data-ttu-id="4cbd9-127">此命令不会运行。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-127">The command isn't run.</span></span>

```powershell
Update-Module -WhatIf
```

```Output
What if: Performing the operation "Update-Module" on target "Version '2.8.0' of module
  'Carbon', updating to version '2.8.1'".
What if: Performing the operation "Update-Module" on target "Version '1.0.10' of module
  'SpeculationControl', updating to version '1.0.14'".
```

<span data-ttu-id="4cbd9-128">`Update-Module` 使用 **WhatIf** 参数显示在运行时将发生 `Update-Module` 的情况。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-128">`Update-Module` uses the **WhatIf** parameter display what would happen if `Update-Module` were run.</span></span>

### <span data-ttu-id="4cbd9-129">示例4：将模块更新到指定版本</span><span class="sxs-lookup"><span data-stu-id="4cbd9-129">Example 4: Update a module to a specified version</span></span>

<span data-ttu-id="4cbd9-130">在此示例中，模块更新为特定版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-130">In this example, a module is updated to a specific version.</span></span> <span data-ttu-id="4cbd9-131">该版本必须位于联机库中，否则将显示错误。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-131">The version must exist in the online gallery or an error is displayed.</span></span>

```powershell
Update-Module -Name SpeculationControl -RequiredVersion 1.0.14
```

<span data-ttu-id="4cbd9-132">`Update-Module` 使用 **Name** 参数指定模块 **SpeculationControl**。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-132">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="4cbd9-133">**RequiredVersion** 参数指定版本 **1.0.14**。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-133">The **RequiredVersion** parameter specifies the version, **1.0.14**.</span></span>

### <span data-ttu-id="4cbd9-134">示例5：更新模块而不进行确认</span><span class="sxs-lookup"><span data-stu-id="4cbd9-134">Example 5: Update a module without confirmation</span></span>

<span data-ttu-id="4cbd9-135">此示例不会请求确认将模块从联机库更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-135">This example doesn't request confirmation to update the module to the newest version from an online gallery.</span></span> <span data-ttu-id="4cbd9-136">如果已安装该模块，则 **Force** 参数会重新安装该模块。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-136">If the module is already installed, the **Force** parameter reinstalls the module.</span></span>

```powershell
Update-Module -Name SpeculationControl -Force
```

<span data-ttu-id="4cbd9-137">`Update-Module` 使用 **Name** 参数指定模块 **SpeculationControl**。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-137">`Update-Module` uses the **Name** parameter to specify the module, **SpeculationControl**.</span></span> <span data-ttu-id="4cbd9-138">**Force** 参数更新模块，而不请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-138">The **Force** parameter updates the module without requesting user confirmation.</span></span>

## <span data-ttu-id="4cbd9-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4cbd9-139">PARAMETERS</span></span>

### <span data-ttu-id="4cbd9-140">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="4cbd9-140">-AcceptLicense</span></span>

<span data-ttu-id="4cbd9-141">如果包需要许可协议，则在安装过程中自动接受该协议。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-141">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="4cbd9-142">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="4cbd9-142">-AllowPrerelease</span></span>

<span data-ttu-id="4cbd9-143">允许你使用标记为预发行版的新模块更新模块。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-143">Allows you to update a module with the newer module marked as a prerelease.</span></span>

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

### <span data-ttu-id="4cbd9-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4cbd9-144">-Confirm</span></span>

<span data-ttu-id="4cbd9-145">在运行之前提示你进行确认 `Update-Module` 。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-145">Prompts you for confirmation before running `Update-Module`.</span></span>

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

### <span data-ttu-id="4cbd9-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="4cbd9-146">-Credential</span></span>

<span data-ttu-id="4cbd9-147">指定有权更新模块的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-147">Specifies a user account that has permission to update a module.</span></span>

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

### <span data-ttu-id="4cbd9-148">-Force</span><span class="sxs-lookup"><span data-stu-id="4cbd9-148">-Force</span></span>

<span data-ttu-id="4cbd9-149">强制更新每个指定的模块，而不提示您请求确认。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-149">Forces an update of each specified module without a prompt to request confirmation.</span></span> <span data-ttu-id="4cbd9-150">如果已安装该模块，则 **强制** 重新安装该模块。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-150">If the module is already installed, **Force** reinstalls the module.</span></span>

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

### <span data-ttu-id="4cbd9-151">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="4cbd9-151">-MaximumVersion</span></span>

<span data-ttu-id="4cbd9-152">指定要更新的单个模块的最高版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-152">Specifies the maximum version of a single module to update.</span></span> <span data-ttu-id="4cbd9-153">如果尝试更新多个模块，则无法添加此参数。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-153">You can't add this parameter if you're attempting to update multiple modules.</span></span> <span data-ttu-id="4cbd9-154">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-154">The **MaximumVersion** and the **RequiredVersion** parameters can't be used in the same command.</span></span>

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

### <span data-ttu-id="4cbd9-155">-Name</span><span class="sxs-lookup"><span data-stu-id="4cbd9-155">-Name</span></span>

<span data-ttu-id="4cbd9-156">指定要更新的一个或多个模块的名称。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-156">Specifies the names of one or more modules to update.</span></span> <span data-ttu-id="4cbd9-157">`Update-Module` 搜索 `$env:PSModulePath` 要更新的模块。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-157">`Update-Module` searches `$env:PSModulePath` for the modules to update.</span></span> <span data-ttu-id="4cbd9-158">如果在指定的模块名称中找不到匹配项 `$env:PSModulePath` ，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-158">If no matches are found in `$env:PSModulePath` for the specified module name, an error occurs.</span></span>

<span data-ttu-id="4cbd9-159">模块名称中接受通配符。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-159">Wildcards are accepted in module names.</span></span> <span data-ttu-id="4cbd9-160">如果将通配符添加到指定的名称，但未找到匹配项，则不会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-160">If you add wildcard characters to the specified name and no matches are found, no error occurs.</span></span>

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

### <span data-ttu-id="4cbd9-161">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4cbd9-161">-PassThru</span></span>

<span data-ttu-id="4cbd9-162">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-162">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="4cbd9-163">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-163">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="4cbd9-164">在 **PowerShellGet** 2.0.0 中添加了 **PassThru** 参数支持</span><span class="sxs-lookup"><span data-stu-id="4cbd9-164">The **PassThru** parameter support was added in **PowerShellGet** 2.0.0</span></span>

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

### <span data-ttu-id="4cbd9-165">-Proxy</span><span class="sxs-lookup"><span data-stu-id="4cbd9-165">-Proxy</span></span>

<span data-ttu-id="4cbd9-166">为请求指定代理服务器，而不是直接连接到 internet 资源。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-166">Specifies a proxy server for the request, rather than connecting directly to an internet resource.</span></span>

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

### <span data-ttu-id="4cbd9-167">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="4cbd9-167">-ProxyCredential</span></span>

<span data-ttu-id="4cbd9-168">指定有权使用 **代理** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-168">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="4cbd9-169">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="4cbd9-169">-RequiredVersion</span></span>

<span data-ttu-id="4cbd9-170">指定将更新现有已安装模块的确切版本。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-170">Specifies the exact version to which the existing installed module will be updated.</span></span> <span data-ttu-id="4cbd9-171">**RequiredVersion** 指定的版本必须存在于联机库中，否则将显示错误。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-171">The version specified by **RequiredVersion** must exist in the online gallery or an error is displayed.</span></span> <span data-ttu-id="4cbd9-172">如果在单个命令中更新了多个模块，则不能使用 **RequiredVersion**。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-172">If more than one module is updated in a single command, you can't use **RequiredVersion**.</span></span>

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

### <span data-ttu-id="4cbd9-173">-Scope</span><span class="sxs-lookup"><span data-stu-id="4cbd9-173">-Scope</span></span>

<span data-ttu-id="4cbd9-174">指定模块的安装范围。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-174">Specifies the installation scope of the module.</span></span> <span data-ttu-id="4cbd9-175">此参数可接受的值为 **AllUsers** 和 **CurrentUser**。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-175">The acceptable values for this parameter are **AllUsers** and **CurrentUser**.</span></span> <span data-ttu-id="4cbd9-176">如果未指定 **作用域** ，则将在 **CurrentUser** 范围内安装更新。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-176">If **Scope** isn't specified, the update is installed in the **CurrentUser** scope.</span></span>

<span data-ttu-id="4cbd9-177">**AllUsers** 作用域需要提升的权限，并将模块安装在计算机的所有用户都可以访问的位置：</span><span class="sxs-lookup"><span data-stu-id="4cbd9-177">The **AllUsers** scope requires elevated permissions and installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="4cbd9-178">**CurrentUser** 不需要提升的权限，并且在只能由计算机的当前用户访问的位置中安装模块：</span><span class="sxs-lookup"><span data-stu-id="4cbd9-178">The **CurrentUser** doesn't require elevated permissions and installs modules in a location that is accessible only to the current user of the computer:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="4cbd9-179">如果未定义 **作用域** ，则将根据 PowerShellGet 版本设置默认值。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-179">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="4cbd9-180">在 PowerShellGet 版本2.0.0 及更高版本中，在运行提升的会话时默认为 **AllUsers** ，对所有其他版本为 **CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-180">In PowerShellGet versions 2.0.0 and above, the default is **AllUsers** when running an elevated session and **CurrentUser** for all others.</span></span>
- <span data-ttu-id="4cbd9-181">在 PowerShellGet 1.x 版本中，默认值为 **AllUsers**，这需要提升才能进行安装。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-181">In PowerShellGet 1.x versions, the default is **AllUsers**, which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: CurrentUser
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4cbd9-182">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4cbd9-182">-WhatIf</span></span>

<span data-ttu-id="4cbd9-183">显示运行时将发生 `Update-Module` 的情况。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-183">Shows what would happen if `Update-Module` runs.</span></span> <span data-ttu-id="4cbd9-184">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-184">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="4cbd9-185">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4cbd9-185">CommonParameters</span></span>

<span data-ttu-id="4cbd9-186">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-186">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4cbd9-187">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-187">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4cbd9-188">输入</span><span class="sxs-lookup"><span data-stu-id="4cbd9-188">INPUTS</span></span>

### <span data-ttu-id="4cbd9-189">System.String[]</span><span class="sxs-lookup"><span data-stu-id="4cbd9-189">System.String[]</span></span>

### <span data-ttu-id="4cbd9-190">System.String</span><span class="sxs-lookup"><span data-stu-id="4cbd9-190">System.String</span></span>

### <span data-ttu-id="4cbd9-191">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="4cbd9-191">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="4cbd9-192">System.Uri</span><span class="sxs-lookup"><span data-stu-id="4cbd9-192">System.Uri</span></span>

## <span data-ttu-id="4cbd9-193">输出</span><span class="sxs-lookup"><span data-stu-id="4cbd9-193">OUTPUTS</span></span>

### <span data-ttu-id="4cbd9-194">System.Object</span><span class="sxs-lookup"><span data-stu-id="4cbd9-194">System.Object</span></span>

## <span data-ttu-id="4cbd9-195">注释</span><span class="sxs-lookup"><span data-stu-id="4cbd9-195">NOTES</span></span>

<span data-ttu-id="4cbd9-196">对于 PowerShell 5.1 或更低的会话，提升会话中的默认作用域为 **AllUsers**，在非提升会话中为 **CurrentUser**。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-196">For PowerShell 5.1 or below, the default scope in an elevated session is **AllUsers**, and in a non-elevated session, **CurrentUser**.</span></span> <span data-ttu-id="4cbd9-197">**AllUsers** 的模块更新 `$env:ProgramFiles\PowerShell\Modules` 需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-197">Module updates for **AllUsers**, `$env:ProgramFiles\PowerShell\Modules`, need elevated permissions.</span></span> <span data-ttu-id="4cbd9-198">**CurrentUser**、的模块更新 `$home\Documents\PowerShell\Modules` 不需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-198">Module updates for **CurrentUser**, `$home\Documents\PowerShell\Modules`, don't need elevated permissions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cbd9-199">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-199">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="4cbd9-200">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-200">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="4cbd9-201">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="4cbd9-201">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="4cbd9-202">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-202">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

<span data-ttu-id="4cbd9-203">`Update-Module` 在 Windows 7 或 Windows 2008 R2 及更高版本的 Windows 上的 powershell 3.0 或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-203">`Update-Module` runs on PowerShell 3.0 or later releases of PowerShell, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="4cbd9-204">如果未使用安装通过 **Name** 参数指定的模块 `Install-Module` ，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-204">If the module that you specify with the **Name** parameter wasn't installed by using `Install-Module`, an error occurs.</span></span>

<span data-ttu-id="4cbd9-205">仅可 `Update-Module` 通过运行在从联机库安装的模块上运行 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-205">You can only run `Update-Module` on modules that you installed from the online gallery by running `Install-Module`.</span></span>

<span data-ttu-id="4cbd9-206">如果 `Update-Module` 尝试更新正在使用的二进制文件，则将 `Update-Module` 返回一个错误，用于识别问题的处理过程。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-206">If `Update-Module` attempts to update binaries that are in use, `Update-Module` returns an error that identifies the problem processes.</span></span> <span data-ttu-id="4cbd9-207">停止进程后，通知用户重试 `Update-Module` 。</span><span class="sxs-lookup"><span data-stu-id="4cbd9-207">The user is informed to retry `Update-Module` after the processes are stopped.</span></span>

## <span data-ttu-id="4cbd9-208">相关链接</span><span class="sxs-lookup"><span data-stu-id="4cbd9-208">RELATED LINKS</span></span>

[<span data-ttu-id="4cbd9-209">Find-Module</span><span class="sxs-lookup"><span data-stu-id="4cbd9-209">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="4cbd9-210">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="4cbd9-210">Get-InstalledModule</span></span>](Get-InstalledModule.md)

[<span data-ttu-id="4cbd9-211">Install-Module</span><span class="sxs-lookup"><span data-stu-id="4cbd9-211">Install-Module</span></span>](Install-Module.md)

[<span data-ttu-id="4cbd9-212">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="4cbd9-212">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="4cbd9-213">Uninstall-模块</span><span class="sxs-lookup"><span data-stu-id="4cbd9-213">Uninstall-Module</span></span>](Uninstall-Module.md)
