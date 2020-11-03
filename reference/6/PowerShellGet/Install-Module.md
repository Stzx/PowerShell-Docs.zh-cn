---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/install-module?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Install-Module
ms.openlocfilehash: 67d68427ba8e3c305b50ccbc19c6d48d574e3351
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2020
ms.locfileid: "93199206"
---
# <span data-ttu-id="877d1-103">Install-Module</span><span class="sxs-lookup"><span data-stu-id="877d1-103">Install-Module</span></span>

## <span data-ttu-id="877d1-104">摘要</span><span class="sxs-lookup"><span data-stu-id="877d1-104">SYNOPSIS</span></span>
<span data-ttu-id="877d1-105">从存储库中下载一个或多个模块，并将其安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="877d1-105">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

## <span data-ttu-id="877d1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="877d1-106">SYNTAX</span></span>

### <span data-ttu-id="877d1-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="877d1-107">NameParameterSet (Default)</span></span>

```
Install-Module [-Name] <String[]> [-MinimumVersion <String>] [-MaximumVersion <String>]
 [-RequiredVersion <String>] [-Repository <String[]>] [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="877d1-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="877d1-108">InputObject</span></span>

```
Install-Module [-InputObject] <PSObject[]> [-Credential <PSCredential>] [-Scope <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-AllowClobber] [-SkipPublisherCheck] [-Force]
 [-AcceptLicense] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="877d1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="877d1-109">DESCRIPTION</span></span>

<span data-ttu-id="877d1-110">`Install-Module`Cmdlet 从联机存储库中获取一个或多个满足指定条件的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-110">The `Install-Module` cmdlet gets one or more modules that meet specified criteria from an online repository.</span></span> <span data-ttu-id="877d1-111">Cmdlet 验证搜索结果是否为有效的模块，并将模块文件夹复制到安装位置。</span><span class="sxs-lookup"><span data-stu-id="877d1-111">The cmdlet verifies that search results are valid modules and copies the module folders to the installation location.</span></span> <span data-ttu-id="877d1-112">安装后，不会自动导入已安装的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-112">Installed modules are not automatically imported after installation.</span></span>
<span data-ttu-id="877d1-113">您可以根据指定模块的最小、最大和确切版本来筛选安装的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-113">You can filter which module is installed based on the minimum, maximum, and exact versions of specified modules.</span></span>

<span data-ttu-id="877d1-114">如果正在安装的模块具有相同的名称或版本，或包含现有模块中的命令，则会显示警告消息。</span><span class="sxs-lookup"><span data-stu-id="877d1-114">If the module being installed has the same name or version, or contains commands in an existing module, warning messages are displayed.</span></span> <span data-ttu-id="877d1-115">确认要安装该模块并覆盖警告后，请使用 `-Force` 和 `-AllowClobber` 参数。</span><span class="sxs-lookup"><span data-stu-id="877d1-115">After you confirm that you want to install the module and override the warnings, use the `-Force` and `-AllowClobber` parameters.</span></span> <span data-ttu-id="877d1-116">取决于存储库设置，你可能需要回答提示以继续安装模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-116">Dependent upon your repository settings, you might need to answer a prompt for the module installation to continue.</span></span>

<span data-ttu-id="877d1-117">这些示例使用 [PowerShell 库](https://www.powershellgallery.com/) 作为仅已注册的存储库。</span><span class="sxs-lookup"><span data-stu-id="877d1-117">These examples use the [PowerShell Gallery](https://www.powershellgallery.com/) as the only registered repository.</span></span> <span data-ttu-id="877d1-118">`Get-PSRepository` 显示已注册的存储库。</span><span class="sxs-lookup"><span data-stu-id="877d1-118">`Get-PSRepository` displays the registered repositories.</span></span> <span data-ttu-id="877d1-119">如果有多个已注册的存储库，请使用 `-Repository` 参数指定存储库的名称。</span><span class="sxs-lookup"><span data-stu-id="877d1-119">If you have multiple registered repositories, use the `-Repository` parameter to specify the repository's name.</span></span>

## <span data-ttu-id="877d1-120">示例</span><span class="sxs-lookup"><span data-stu-id="877d1-120">EXAMPLES</span></span>

### <span data-ttu-id="877d1-121">示例1：查找和安装模块</span><span class="sxs-lookup"><span data-stu-id="877d1-121">Example 1: Find and install a module</span></span>

<span data-ttu-id="877d1-122">此示例查找存储库中的模块并安装该模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-122">This example finds a module in the repository and installs the module.</span></span>

```powershell
Find-Module -Name PowerShellGet | Install-Module
```

<span data-ttu-id="877d1-123">`Find-Module`使用 **Name** 参数指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-123">The `Find-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="877d1-124">默认情况下，将从存储库下载模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-124">By default, the newest version of the module is downloaded from the repository.</span></span> <span data-ttu-id="877d1-125">对象通过管道向下发送到 `Install-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="877d1-125">The object is sent down the pipeline to the `Install-Module` cmdlet.</span></span> <span data-ttu-id="877d1-126">`Install-Module` 为中的所有用户安装该模块 `$env:ProgramFiles\PowerShell\Modules` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-126">`Install-Module` installs the module for all users in `$env:ProgramFiles\PowerShell\Modules`.</span></span>

### <span data-ttu-id="877d1-127">示例2：按名称安装模块</span><span class="sxs-lookup"><span data-stu-id="877d1-127">Example 2: Install a module by name</span></span>

<span data-ttu-id="877d1-128">在此示例中，将安装 **PowerShellGet** 模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-128">In this example, the newest version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet
```

<span data-ttu-id="877d1-129">`Install-Module`使用 **Name** 参数指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-129">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="877d1-130">默认情况下，将从存储库下载并安装最新版本的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-130">By default, the newest version of the module is downloaded from the repository and installed.</span></span>

### <span data-ttu-id="877d1-131">示例3：使用最低版本安装模块</span><span class="sxs-lookup"><span data-stu-id="877d1-131">Example 3: Install a module using its minimum version</span></span>

<span data-ttu-id="877d1-132">在此示例中，将安装 **PowerShellGet** 模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-132">In this example, the minimum version of the **PowerShellGet** module is installed.</span></span> <span data-ttu-id="877d1-133">**MinimumVersion** 参数指定应安装的模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-133">The **MinimumVersion** parameter specifies the lowest version of the module that should be installed.</span></span> <span data-ttu-id="877d1-134">如果模块的更新版本可用，则会为所有用户下载并安装该版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-134">If a newer version of the module is available, that version is downloaded and installed for all users.</span></span>

```powershell
Install-Module -Name PowerShellGet -MinimumVersion 2.0.1
```

<span data-ttu-id="877d1-135">`Install-Module`使用 **Name** 参数指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-135">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="877d1-136">**MinimumVersion** 参数指定从存储库下载并安装版本 **2.0.1** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-136">The **MinimumVersion** parameter specifies that version **2.0.1** is downloaded from the repository and installed.</span></span> <span data-ttu-id="877d1-137">由于版本 **2.0.4** 可用，因此会为所有用户下载和安装该版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-137">Because version **2.0.4** is available, that version is downloaded and installed for all users.</span></span>

### <span data-ttu-id="877d1-138">示例4：安装特定版本的模块</span><span class="sxs-lookup"><span data-stu-id="877d1-138">Example 4: Install a specific version of a module</span></span>

<span data-ttu-id="877d1-139">在此示例中，安装了 **PowerShellGet** 模块的特定版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-139">In this example, a specific version of the **PowerShellGet** module is installed.</span></span>

```powershell
Install-Module -Name PowerShellGet -RequiredVersion 2.0.0
```

<span data-ttu-id="877d1-140">`Install-Module`使用 **Name** 参数指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-140">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span> <span data-ttu-id="877d1-141">**RequiredVersion** 参数指定为所有用户下载和安装版本 **2.0.0** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-141">The **RequiredVersion** parameter specifies that version **2.0.0** is downloaded and installed for all users.</span></span>

### <span data-ttu-id="877d1-142">示例5：仅为当前用户安装模块</span><span class="sxs-lookup"><span data-stu-id="877d1-142">Example 5: Install a module only for the current user</span></span>

<span data-ttu-id="877d1-143">此示例仅为当前用户下载并安装最新版本的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-143">This example downloads and installs the newest version of a module, only for the current user.</span></span>

```powershell
Install-Module -Name PowerShellGet -Scope CurrentUser
```

<span data-ttu-id="877d1-144">`Install-Module`使用 **Name** 参数指定 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-144">The `Install-Module` uses the **Name** parameter to specify the **PowerShellGet** module.</span></span>
<span data-ttu-id="877d1-145">`Install-Module` 下载最新版本的 **PowerShellGet** 并将其安装到当前用户的目录中 `$home\Documents\PowerShell\Modules` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-145">`Install-Module` downloads and installs the newest version of **PowerShellGet** into the current user's directory, `$home\Documents\PowerShell\Modules`.</span></span>

## <span data-ttu-id="877d1-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="877d1-146">PARAMETERS</span></span>

### <span data-ttu-id="877d1-147">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="877d1-147">-AcceptLicense</span></span>

<span data-ttu-id="877d1-148">对于需要许可证的模块， **AcceptLicense** 会在安装过程中自动接受许可协议。</span><span class="sxs-lookup"><span data-stu-id="877d1-148">For modules that require a license, **AcceptLicense** automatically accepts the license agreement during installation.</span></span> <span data-ttu-id="877d1-149">有关详细信息，请参阅 [需要接受许可证的模块](/powershell/scripting/gallery/concepts/module-license-acceptance)。</span><span class="sxs-lookup"><span data-stu-id="877d1-149">For more information, see [Modules Requiring License Acceptance](/powershell/scripting/gallery/concepts/module-license-acceptance).</span></span>

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

### <span data-ttu-id="877d1-150">-AllowClobber</span><span class="sxs-lookup"><span data-stu-id="877d1-150">-AllowClobber</span></span>

<span data-ttu-id="877d1-151">覆盖有关计算机上的现有命令的安装冲突的警告消息。</span><span class="sxs-lookup"><span data-stu-id="877d1-151">Overrides warning messages about installation conflicts about existing commands on a computer.</span></span>
<span data-ttu-id="877d1-152">覆盖与模块安装的命令同名的现有命令。</span><span class="sxs-lookup"><span data-stu-id="877d1-152">Overwrites existing commands that have the same name as commands being installed by a module.</span></span>
<span data-ttu-id="877d1-153">在命令中，可以将 **AllowClobber** 和 **Force** 一起使用 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-153">**AllowClobber** and **Force** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="877d1-154">-AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="877d1-154">-AllowPrerelease</span></span>

<span data-ttu-id="877d1-155">允许你安装标记为预发行版的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-155">Allows you to install a module marked as a pre-release.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="877d1-156">-Confirm</span></span>

<span data-ttu-id="877d1-157">提示你在运行 cmdlet 之前进行确认 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-157">Prompts you for confirmation before running the `Install-Module` cmdlet.</span></span>

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

### <span data-ttu-id="877d1-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="877d1-158">-Credential</span></span>

<span data-ttu-id="877d1-159">指定有权为指定的包提供程序或源安装模块的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="877d1-159">Specifies a user account that has rights to install a module for a specified package provider or source.</span></span>

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

### <span data-ttu-id="877d1-160">-Force</span><span class="sxs-lookup"><span data-stu-id="877d1-160">-Force</span></span>

<span data-ttu-id="877d1-161">安装模块并覆盖有关模块安装冲突的警告消息。</span><span class="sxs-lookup"><span data-stu-id="877d1-161">Installs a module and overrides warning messages about module installation conflicts.</span></span> <span data-ttu-id="877d1-162">如果计算机上已存在具有相同名称的模块，则 **强制** 允许安装多个版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-162">If a module with the same name already exists on the computer, **Force** allows for multiple versions to be installed.</span></span> <span data-ttu-id="877d1-163">如果存在具有相同名称和版本的现有模块，则 **强制** 覆盖该版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-163">If there is an existing module with the same name and version, **Force** overwrites that version.</span></span> <span data-ttu-id="877d1-164">在命令中，可以将 **Force** 和 **AllowClobber** 一起使用 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-164">**Force** and **AllowClobber** can be used together in an `Install-Module` command.</span></span>

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

### <span data-ttu-id="877d1-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="877d1-165">-InputObject</span></span>

<span data-ttu-id="877d1-166">用于管道输入。</span><span class="sxs-lookup"><span data-stu-id="877d1-166">Used for pipeline input.</span></span>

```yaml
Type: System.Management.Automation.PSObject[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-167">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="877d1-167">-MaximumVersion</span></span>

<span data-ttu-id="877d1-168">指定要安装的单个模块的最高版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-168">Specifies the maximum version of a single module to install.</span></span> <span data-ttu-id="877d1-169">安装的版本必须小于或等于 **MaximumVersion** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-169">The version installed must be less than or equal to **MaximumVersion** .</span></span> <span data-ttu-id="877d1-170">如果要安装多个模块，则不能使用 **MaximumVersion** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-170">If you want to install multiple modules, you cannot use **MaximumVersion** .</span></span> <span data-ttu-id="877d1-171">不能在同一命令中使用 **MaximumVersion** 和 **RequiredVersion** `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-171">**MaximumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-172">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="877d1-172">-MinimumVersion</span></span>

<span data-ttu-id="877d1-173">指定要安装的单个模块的最低版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-173">Specifies the minimum version of a single module to install.</span></span> <span data-ttu-id="877d1-174">安装的版本必须大于或等于 **MinimumVersion** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-174">The version installed must be greater than or equal to **MinimumVersion** .</span></span> <span data-ttu-id="877d1-175">如果模块的更新版本可用，则会安装较新版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-175">If there is a newer version of the module available, the newer version is installed.</span></span> <span data-ttu-id="877d1-176">如果要安装多个模块，则不能使用 **MinimumVersion** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-176">If you want to install multiple modules, you cannot use **MinimumVersion** .</span></span>
<span data-ttu-id="877d1-177">不能在同一命令中使用 **MinimumVersion** 和 **RequiredVersion** `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-177">**MinimumVersion** and **RequiredVersion** cannot be used in the same `Install-Module` command.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-178">-Name</span><span class="sxs-lookup"><span data-stu-id="877d1-178">-Name</span></span>

<span data-ttu-id="877d1-179">指定要从联机库中安装的模块的确切名称。</span><span class="sxs-lookup"><span data-stu-id="877d1-179">Specifies the exact names of modules to install from the online gallery.</span></span> <span data-ttu-id="877d1-180">接受以逗号分隔的模块名称列表。</span><span class="sxs-lookup"><span data-stu-id="877d1-180">A comma-separated list of module names is accepted.</span></span> <span data-ttu-id="877d1-181">模块名称必须与存储库中的模块名称匹配。</span><span class="sxs-lookup"><span data-stu-id="877d1-181">The module name must match the module name in the repository.</span></span> <span data-ttu-id="877d1-182">使用 `Find-Module` 获取模块名称的列表。</span><span class="sxs-lookup"><span data-stu-id="877d1-182">Use `Find-Module` to get a list of module names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-183">-PassThru</span><span class="sxs-lookup"><span data-stu-id="877d1-183">-PassThru</span></span>

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

### <span data-ttu-id="877d1-184">-Proxy</span><span class="sxs-lookup"><span data-stu-id="877d1-184">-Proxy</span></span>

<span data-ttu-id="877d1-185">为请求指定代理服务器，而不是直接连接到 Internet 资源。</span><span class="sxs-lookup"><span data-stu-id="877d1-185">Specifies a proxy server for the request, rather than connecting directly to the Internet resource.</span></span>

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

### <span data-ttu-id="877d1-186">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="877d1-186">-ProxyCredential</span></span>

<span data-ttu-id="877d1-187">指定有权使用由 **Proxy** 参数指定的代理服务器的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="877d1-187">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="877d1-188">-Repository</span><span class="sxs-lookup"><span data-stu-id="877d1-188">-Repository</span></span>

<span data-ttu-id="877d1-189">使用 **存储库** 参数可指定用于下载和安装模块的存储库。</span><span class="sxs-lookup"><span data-stu-id="877d1-189">Use the **Repository** parameter to specify which repository is used to download and install a module.</span></span> <span data-ttu-id="877d1-190">当注册多个存储库时使用。</span><span class="sxs-lookup"><span data-stu-id="877d1-190">Used when multiple repositories are registered.</span></span> <span data-ttu-id="877d1-191">在命令中指定已注册的存储库的名称 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-191">Specifies the name of a registered repository in the `Install-Module` command.</span></span> <span data-ttu-id="877d1-192">若要注册存储库，请使用 `Register-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-192">To register a repository, use `Register-PSRepository`.</span></span>
<span data-ttu-id="877d1-193">若要显示已注册的存储库，请使用 `Get-PSRepository` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-193">To display registered repositories, use `Get-PSRepository`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-194">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="877d1-194">-RequiredVersion</span></span>

<span data-ttu-id="877d1-195">指定要安装的单个模块的确切版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-195">Specifies the exact version of a single module to install.</span></span> <span data-ttu-id="877d1-196">如果指定版本的存储库中没有匹配项，则会显示错误。</span><span class="sxs-lookup"><span data-stu-id="877d1-196">If there is no match in the repository for the specified version, an error is displayed.</span></span> <span data-ttu-id="877d1-197">如果要安装多个模块，则不能使用 **RequiredVersion** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-197">If you want to install multiple modules, you cannot use **RequiredVersion** .</span></span> <span data-ttu-id="877d1-198">**RequiredVersion** 对于 `Install-Module` **MinimumVersion** 或 **MaximumVersion** ，不能在同一命令中使用 RequiredVersion。</span><span class="sxs-lookup"><span data-stu-id="877d1-198">**RequiredVersion** cannot be used in the same `Install-Module` command as **MinimumVersion** or **MaximumVersion** .</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-199">-Scope</span><span class="sxs-lookup"><span data-stu-id="877d1-199">-Scope</span></span>

<span data-ttu-id="877d1-200">指定模块的安装范围。</span><span class="sxs-lookup"><span data-stu-id="877d1-200">Specifies the installation scope of the module.</span></span> <span data-ttu-id="877d1-201">此参数可接受的值为 **AllUsers** 和 **CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-201">The acceptable values for this parameter are **AllUsers** and **CurrentUser** .</span></span>

<span data-ttu-id="877d1-202">**AllUsers** 作用域在计算机的所有用户都可以访问的位置中安装模块：</span><span class="sxs-lookup"><span data-stu-id="877d1-202">The **AllUsers** scope installs modules in a location that is accessible to all users of the computer:</span></span>

`$env:ProgramFiles\PowerShell\Modules`

<span data-ttu-id="877d1-203">**CurrentUser** 在只能由计算机的当前用户访问的位置中安装模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-203">The **CurrentUser** installs modules in a location that is accessible only to the current user of the computer.</span></span> <span data-ttu-id="877d1-204">例如：</span><span class="sxs-lookup"><span data-stu-id="877d1-204">For example:</span></span>

`$home\Documents\PowerShell\Modules`

<span data-ttu-id="877d1-205">如果未定义 **作用域** ，则将根据 PowerShellGet 版本设置默认值。</span><span class="sxs-lookup"><span data-stu-id="877d1-205">When no **Scope** is defined, the default is set based on the PowerShellGet version.</span></span>

- <span data-ttu-id="877d1-206">在 PowerShellGet 版本2.0.0 及更高版本中，默认值为 **CurrentUser** ，无需进行提升即可安装。</span><span class="sxs-lookup"><span data-stu-id="877d1-206">In PowerShellGet versions 2.0.0 and above, the default is **CurrentUser** , which does not require elevation for install.</span></span>
- <span data-ttu-id="877d1-207">在 PowerShellGet 1.x 版本中，默认值为 **AllUsers** ，这需要提升才能进行安装。</span><span class="sxs-lookup"><span data-stu-id="877d1-207">In PowerShellGet 1.x versions, the default is **AllUsers** , which requires elevation for install.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, AllUsers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="877d1-208">-SkipPublisherCheck</span><span class="sxs-lookup"><span data-stu-id="877d1-208">-SkipPublisherCheck</span></span>

<span data-ttu-id="877d1-209">允许您安装计算机上已存在的较新版本的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-209">Allows you to install a newer version of a module that already exists on your computer.</span></span> <span data-ttu-id="877d1-210">例如，如果现有模块由受信任的发布者进行数字签名，但新版本不由受信任的发布者进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="877d1-210">For example, when an existing module is digitally signed by a trusted publisher but the new version is not digitally signed by a trusted publisher.</span></span>

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

### <span data-ttu-id="877d1-211">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="877d1-211">-WhatIf</span></span>

<span data-ttu-id="877d1-212">显示运行命令时将发生的情况 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-212">Shows what would happen if an `Install-Module` command was run.</span></span> <span data-ttu-id="877d1-213">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="877d1-213">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="877d1-214">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="877d1-214">CommonParameters</span></span>

<span data-ttu-id="877d1-215">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="877d1-215">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="877d1-216">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="877d1-216">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="877d1-217">输入</span><span class="sxs-lookup"><span data-stu-id="877d1-217">INPUTS</span></span>

### <span data-ttu-id="877d1-218">PSRepositoryItemInfo</span><span class="sxs-lookup"><span data-stu-id="877d1-218">PSRepositoryItemInfo</span></span>

<span data-ttu-id="877d1-219">`Find-Module` 创建可通过管道向下发送的 **PSRepositoryItemInfo** 对象 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-219">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span>

### <span data-ttu-id="877d1-220">System.String[]</span><span class="sxs-lookup"><span data-stu-id="877d1-220">System.String[]</span></span>

### <span data-ttu-id="877d1-221">System.web. system.exception []</span><span class="sxs-lookup"><span data-stu-id="877d1-221">System.Management.Automation.PSObject[]</span></span>

### <span data-ttu-id="877d1-222">System.String</span><span class="sxs-lookup"><span data-stu-id="877d1-222">System.String</span></span>

### <span data-ttu-id="877d1-223">System.Management.Automation.PSCredential</span><span class="sxs-lookup"><span data-stu-id="877d1-223">System.Management.Automation.PSCredential</span></span>

### <span data-ttu-id="877d1-224">System.Uri</span><span class="sxs-lookup"><span data-stu-id="877d1-224">System.Uri</span></span>

## <span data-ttu-id="877d1-225">输出</span><span class="sxs-lookup"><span data-stu-id="877d1-225">OUTPUTS</span></span>

### <span data-ttu-id="877d1-226">PSRepositoryItemInfo。</span><span class="sxs-lookup"><span data-stu-id="877d1-226">Microsoft.PowerShell.Commands.PSRepositoryItemInfo</span></span>

<span data-ttu-id="877d1-227">当使用 **PassThru** 参数时， `Install-Module` 输出该模块的 **PSRepositoryItemInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="877d1-227">When using the **PassThru** parameter, `Install-Module` outputs a **PSRepositoryItemInfo** object for the module.</span></span> <span data-ttu-id="877d1-228">这与你从 cmdlet 获取的信息相同 `Find-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-228">This is the same information that you get from the `Find-Module` cmdlet.</span></span>

## <span data-ttu-id="877d1-229">注释</span><span class="sxs-lookup"><span data-stu-id="877d1-229">NOTES</span></span>

<span data-ttu-id="877d1-230">`Install-Module` 在 Windows 7 或 Windows 2008 R2 及更高版本的 Windows 上的 PowerShell 5.0 或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="877d1-230">`Install-Module` runs on PowerShell 5.0 or later releases, on Windows 7 or Windows 2008 R2 and later releases of Windows.</span></span>

<span data-ttu-id="877d1-231">作为最佳安全方案，请在首次运行任何 cmdlet 或函数之前评估模块的代码。</span><span class="sxs-lookup"><span data-stu-id="877d1-231">As a security best practice, evaluate a module's code before running any cmdlets or functions for the first time.</span></span> <span data-ttu-id="877d1-232">为防止运行包含恶意代码的模块，安装后不会自动导入已安装的模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-232">To prevent running modules that contain malicious code, installed modules are not automatically imported after installation.</span></span>

<span data-ttu-id="877d1-233">如果存储库中不存在 **name** 参数指定的模块名称，则会 `Install-Module` 返回错误。</span><span class="sxs-lookup"><span data-stu-id="877d1-233">If the module name specified by the **Name** parameter does not exist in the repository, `Install-Module` returns an error.</span></span>

<span data-ttu-id="877d1-234">若要安装多个模块，请使用 **Name** 参数，并指定一个逗号分隔的模块名称数组。</span><span class="sxs-lookup"><span data-stu-id="877d1-234">To install multiple modules, use the **Name** parameter and specify a comma-separated array of module names.</span></span> <span data-ttu-id="877d1-235">如果指定多个模块名称，则不能使用 **MinimumVersion** 、 **MaximumVersion** 或 **RequiredVersion** 。</span><span class="sxs-lookup"><span data-stu-id="877d1-235">If you specify multiple module names, you cannot use **MinimumVersion** , **MaximumVersion** , or **RequiredVersion** .</span></span> <span data-ttu-id="877d1-236">`Find-Module` 创建可通过管道向下发送的 **PSRepositoryItemInfo** 对象 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-236">`Find-Module` creates **PSRepositoryItemInfo** objects that can be sent down the pipeline to `Install-Module`.</span></span> <span data-ttu-id="877d1-237">管道是在单个命令中指定要安装的多个模块的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="877d1-237">The pipeline is another way to specify multiple modules to install in a single command.</span></span>

<span data-ttu-id="877d1-238">默认情况下， **AllUsers** 作用域的模块安装在中 `$env:ProgramFiles\PowerShell\Modules` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-238">By default, modules for the scope of **AllUsers** are installed in `$env:ProgramFiles\PowerShell\Modules`.</span></span> <span data-ttu-id="877d1-239">默认情况下，在 (DSC) 资源中安装 PowerShell Desired State Configuration 时，会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="877d1-239">The default prevents confusion when you install PowerShell Desired State Configuration (DSC) resources.</span></span>

<span data-ttu-id="877d1-240">如果模块安装失败，并且在该 `.psm1` `.psd1` 文件夹内没有相同名称的、或，则无法导入 `.dll` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-240">A module installation fails and cannot be imported if it does not have a `.psm1`, `.psd1`, or `.dll` of the same name within the folder.</span></span> <span data-ttu-id="877d1-241">使用 **Force** 参数安装模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-241">Use the **Force** parameter to install the module.</span></span>

<span data-ttu-id="877d1-242">如果现有模块的版本与 **name** 参数指定的名称相匹配，并且未使用 **MinimumVersion** 或 **RequiredVersion** 参数，则将以 `Install-Module` 无提示方式继续，但不会安装该模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-242">If an existing module's version matches the name specified by the **Name** parameter, and the **MinimumVersion** or **RequiredVersion** parameter are not used, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="877d1-243">如果现有模块的版本大于 **MinimumVersion** 参数的值，或者等于 **RequiredVersion** 参数的值，则会以静默方式继续， `Install-Module` 但不会安装该模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-243">If an existing module's version is greater than the value of the **MinimumVersion** parameter, or equal to the value of the **RequiredVersion** parameter, `Install-Module` silently continues but does not install the module.</span></span>

<span data-ttu-id="877d1-244">如果现有模块与 **MinimumVersion** 或 **RequiredVersion** 参数指定的值不匹配，则会在命令中出现错误 `Install-Module` 。</span><span class="sxs-lookup"><span data-stu-id="877d1-244">If the existing module does not match the values specified by the **MinimumVersion** or **RequiredVersion** parameters, an error occurs in the `Install-Module` command.</span></span> <span data-ttu-id="877d1-245">例如，如果现有的已安装模块的版本低于 **MinimumVersion** 值或不等于 **RequiredVersion** 值。</span><span class="sxs-lookup"><span data-stu-id="877d1-245">For example, if the version of the existing installed module is lower than the **MinimumVersion** value or not equal to the **RequiredVersion** value.</span></span>

<span data-ttu-id="877d1-246">模块安装还将安装模块发布程序所需的任何指定的相关模块。</span><span class="sxs-lookup"><span data-stu-id="877d1-246">A module installation will also install any dependent modules specified as required by the module publisher.</span></span>
<span data-ttu-id="877d1-247">发布者将在模块清单中指定必需的模块及其版本。</span><span class="sxs-lookup"><span data-stu-id="877d1-247">The publisher will specify the required modules and their versions in the module manifest.</span></span>

## <span data-ttu-id="877d1-248">相关链接</span><span class="sxs-lookup"><span data-stu-id="877d1-248">RELATED LINKS</span></span>

[<span data-ttu-id="877d1-249">Find-Module</span><span class="sxs-lookup"><span data-stu-id="877d1-249">Find-Module</span></span>](Find-Module.md)

[<span data-ttu-id="877d1-250">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="877d1-250">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="877d1-251">Import-Module</span><span class="sxs-lookup"><span data-stu-id="877d1-251">Import-Module</span></span>](../Microsoft.PowerShell.Core/Import-Module.md)

[<span data-ttu-id="877d1-252">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="877d1-252">Publish-Module</span></span>](Publish-Module.md)

[<span data-ttu-id="877d1-253">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="877d1-253">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="877d1-254">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="877d1-254">Uninstall-Module</span></span>](Uninstall-Module.md)

[<span data-ttu-id="877d1-255">Update-Module</span><span class="sxs-lookup"><span data-stu-id="877d1-255">Update-Module</span></span>](Update-Module.md)

[<span data-ttu-id="877d1-256">about_Module</span><span class="sxs-lookup"><span data-stu-id="877d1-256">about_Module</span></span>](../Microsoft.PowerShell.Core/About/about_Modules.md)