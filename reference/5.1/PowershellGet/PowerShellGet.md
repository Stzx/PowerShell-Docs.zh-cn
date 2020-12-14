---
Download Help Link: https://go.microsoft.com/fwlink/?LinkId=393271
Help Version: 5.2.0.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 130582b1b9f18a8f6ada7c009c6d25a7dab75e46
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890706"
---
# <span data-ttu-id="5f673-103">PowerShellGet 模块</span><span class="sxs-lookup"><span data-stu-id="5f673-103">PowerShellGet Module</span></span>

## <span data-ttu-id="5f673-104">描述</span><span class="sxs-lookup"><span data-stu-id="5f673-104">Description</span></span>

<span data-ttu-id="5f673-105">PowerShellGet 是一个模块，其中包含用于发现、安装、更新和发布 PowerShell 项目（如模块、DSC 资源、角色功能和脚本）的命令。</span><span class="sxs-lookup"><span data-stu-id="5f673-105">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f673-106">从2020年4月起，PowerShell 库不再支持传输层安全 (TLS) 版本1.0 和1.1。</span><span class="sxs-lookup"><span data-stu-id="5f673-106">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="5f673-107">如果使用的不是 TLS 1.2 或更高版本，则在尝试访问 PowerShell 库时，会收到错误。</span><span class="sxs-lookup"><span data-stu-id="5f673-107">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="5f673-108">使用以下命令确保使用的是 TLS 1.2：</span><span class="sxs-lookup"><span data-stu-id="5f673-108">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="5f673-109">有关详细信息，请参阅 PowerShell 博客中的 [公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) 。</span><span class="sxs-lookup"><span data-stu-id="5f673-109">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="5f673-110">PowerShellGet Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5f673-110">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="5f673-111">Find-Command</span><span class="sxs-lookup"><span data-stu-id="5f673-111">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="5f673-112">查找模块中的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="5f673-112">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="5f673-113">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="5f673-113">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="5f673-114">查找 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="5f673-114">Finds a DSC resource.</span></span>

### [<span data-ttu-id="5f673-115">Find-Module</span><span class="sxs-lookup"><span data-stu-id="5f673-115">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="5f673-116">查找存储库中与指定条件匹配的模块。</span><span class="sxs-lookup"><span data-stu-id="5f673-116">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="5f673-117">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="5f673-117">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="5f673-118">在模块中查找角色功能。</span><span class="sxs-lookup"><span data-stu-id="5f673-118">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="5f673-119">Find-Script</span><span class="sxs-lookup"><span data-stu-id="5f673-119">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="5f673-120">查找脚本。</span><span class="sxs-lookup"><span data-stu-id="5f673-120">Finds a script.</span></span>

### [<span data-ttu-id="5f673-121">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="5f673-121">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="5f673-122">获取由 PowerShellGet 安装的计算机上的模块列表。</span><span class="sxs-lookup"><span data-stu-id="5f673-122">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="5f673-123">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="5f673-123">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="5f673-124">获取已安装的脚本。</span><span class="sxs-lookup"><span data-stu-id="5f673-124">Gets an installed script.</span></span>

### [<span data-ttu-id="5f673-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5f673-125">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="5f673-126">获取 PowerShell 存储库。</span><span class="sxs-lookup"><span data-stu-id="5f673-126">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="5f673-127">Install-Module</span><span class="sxs-lookup"><span data-stu-id="5f673-127">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="5f673-128">从存储库中下载一个或多个模块，并将其安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="5f673-128">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="5f673-129">Install-Script</span><span class="sxs-lookup"><span data-stu-id="5f673-129">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="5f673-130">安装脚本。</span><span class="sxs-lookup"><span data-stu-id="5f673-130">Installs a script.</span></span>

### [<span data-ttu-id="5f673-131">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="5f673-131">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="5f673-132">使用元数据创建脚本文件。</span><span class="sxs-lookup"><span data-stu-id="5f673-132">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="5f673-133">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="5f673-133">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="5f673-134">将指定模块从本机计算机发布到联机库。</span><span class="sxs-lookup"><span data-stu-id="5f673-134">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="5f673-135">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="5f673-135">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="5f673-136">发布脚本。</span><span class="sxs-lookup"><span data-stu-id="5f673-136">Publishes a script.</span></span>

### [<span data-ttu-id="5f673-137">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5f673-137">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="5f673-138">注册 PowerShell 存储库。</span><span class="sxs-lookup"><span data-stu-id="5f673-138">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="5f673-139">Save-Module</span><span class="sxs-lookup"><span data-stu-id="5f673-139">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="5f673-140">将模块及其依赖项保存在本地计算机上，但不会安装该模块。</span><span class="sxs-lookup"><span data-stu-id="5f673-140">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="5f673-141">Save-Script</span><span class="sxs-lookup"><span data-stu-id="5f673-141">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="5f673-142">保存脚本。</span><span class="sxs-lookup"><span data-stu-id="5f673-142">Saves a script.</span></span>

### [<span data-ttu-id="5f673-143">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5f673-143">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="5f673-144">为已注册的存储库设置值。</span><span class="sxs-lookup"><span data-stu-id="5f673-144">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="5f673-145">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="5f673-145">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="5f673-146">验证脚本的注释块。</span><span class="sxs-lookup"><span data-stu-id="5f673-146">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="5f673-147">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="5f673-147">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="5f673-148">卸载模块。</span><span class="sxs-lookup"><span data-stu-id="5f673-148">Uninstalls a module.</span></span>

### [<span data-ttu-id="5f673-149">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="5f673-149">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="5f673-150">卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="5f673-150">Uninstalls a script.</span></span>

### [<span data-ttu-id="5f673-151">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="5f673-151">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="5f673-152">取消注册存储库。</span><span class="sxs-lookup"><span data-stu-id="5f673-152">Unregisters a repository.</span></span>

### [<span data-ttu-id="5f673-153">Update-Module</span><span class="sxs-lookup"><span data-stu-id="5f673-153">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="5f673-154">从联机库中下载指定模块的最新版本，并将其安装到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="5f673-154">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="5f673-155">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="5f673-155">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="5f673-156">更新模块清单文件。</span><span class="sxs-lookup"><span data-stu-id="5f673-156">Updates a module manifest file.</span></span>

### [<span data-ttu-id="5f673-157">Update-Script</span><span class="sxs-lookup"><span data-stu-id="5f673-157">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="5f673-158">更新脚本。</span><span class="sxs-lookup"><span data-stu-id="5f673-158">Updates a script.</span></span>

### [<span data-ttu-id="5f673-159">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="5f673-159">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="5f673-160">更新脚本的信息。</span><span class="sxs-lookup"><span data-stu-id="5f673-160">Updates information for a script.</span></span>
