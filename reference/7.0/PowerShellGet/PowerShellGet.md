---
Download Help Link: https://go.microsoft.com/fwlink/?linkid=2113539
Help Version: 7.0.1.0
keywords: powershell,cmdlet
Locale: en-US
Module Guid: 1d73a601-4a6c-43c5-ba3f-619b18bbb404
Module Name: PowerShellGet
ms.date: 06/09/2017
schema: 2.0.0
title: PowerShellGet
ms.openlocfilehash: 6da6adf79693929f75d82e1925eb67496dd9b6ef
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "93199509"
---
# <span data-ttu-id="9c97e-103">PowerShellGet 模块</span><span class="sxs-lookup"><span data-stu-id="9c97e-103">PowerShellGet Module</span></span>

## <span data-ttu-id="9c97e-104">说明</span><span class="sxs-lookup"><span data-stu-id="9c97e-104">Description</span></span>

<span data-ttu-id="9c97e-105">PowerShellGet 是一个模块，其中包含用于发现、安装、更新和发布 PowerShell 项目（如模块、DSC 资源、角色功能和脚本）的命令。</span><span class="sxs-lookup"><span data-stu-id="9c97e-105">PowerShellGet is a module with commands for discovering, installing, updating and publishing PowerShell artifacts like Modules, DSC Resources, Role Capabilities, and Scripts.</span></span>

## <span data-ttu-id="9c97e-106">PowerShellGet Cmdlets</span><span class="sxs-lookup"><span data-stu-id="9c97e-106">PowerShellGet Cmdlets</span></span>

### [<span data-ttu-id="9c97e-107">Find-Command</span><span class="sxs-lookup"><span data-stu-id="9c97e-107">Find-Command</span></span>](Find-Command.md)
<span data-ttu-id="9c97e-108">查找模块中的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="9c97e-108">Finds PowerShell commands in modules.</span></span>

### [<span data-ttu-id="9c97e-109">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="9c97e-109">Find-DscResource</span></span>](Find-DscResource.md)
<span data-ttu-id="9c97e-110"> (DSC) 资源中查找所需的状态配置。</span><span class="sxs-lookup"><span data-stu-id="9c97e-110">Finds Desired State Configuration (DSC) resources.</span></span>

### [<span data-ttu-id="9c97e-111">Find-Module</span><span class="sxs-lookup"><span data-stu-id="9c97e-111">Find-Module</span></span>](Find-Module.md)
<span data-ttu-id="9c97e-112">查找存储库中与指定条件匹配的模块。</span><span class="sxs-lookup"><span data-stu-id="9c97e-112">Finds modules in a repository that match specified criteria.</span></span>

### [<span data-ttu-id="9c97e-113">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="9c97e-113">Find-RoleCapability</span></span>](Find-RoleCapability.md)
<span data-ttu-id="9c97e-114">在模块中查找角色功能。</span><span class="sxs-lookup"><span data-stu-id="9c97e-114">Finds role capabilities in modules.</span></span>

### [<span data-ttu-id="9c97e-115">Find-Script</span><span class="sxs-lookup"><span data-stu-id="9c97e-115">Find-Script</span></span>](Find-Script.md)
<span data-ttu-id="9c97e-116">查找脚本。</span><span class="sxs-lookup"><span data-stu-id="9c97e-116">Finds a script.</span></span>

### [<span data-ttu-id="9c97e-117">Get-InstalledModule</span><span class="sxs-lookup"><span data-stu-id="9c97e-117">Get-InstalledModule</span></span>](Get-InstalledModule.md)
<span data-ttu-id="9c97e-118">获取由 PowerShellGet 安装的计算机上的模块列表。</span><span class="sxs-lookup"><span data-stu-id="9c97e-118">Gets a list of modules on the computer that were installed by PowerShellGet.</span></span>

### [<span data-ttu-id="9c97e-119">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="9c97e-119">Get-InstalledScript</span></span>](Get-InstalledScript.md)
<span data-ttu-id="9c97e-120">获取已安装的脚本。</span><span class="sxs-lookup"><span data-stu-id="9c97e-120">Gets an installed script.</span></span>

### [<span data-ttu-id="9c97e-121">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9c97e-121">Get-PSRepository</span></span>](Get-PSRepository.md)
<span data-ttu-id="9c97e-122">获取 PowerShell 存储库。</span><span class="sxs-lookup"><span data-stu-id="9c97e-122">Gets PowerShell repositories.</span></span>

### [<span data-ttu-id="9c97e-123">Install-Module</span><span class="sxs-lookup"><span data-stu-id="9c97e-123">Install-Module</span></span>](Install-Module.md)
<span data-ttu-id="9c97e-124">从存储库中下载一个或多个模块，并将其安装在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="9c97e-124">Downloads one or more modules from a repository, and installs them on the local computer.</span></span>

### [<span data-ttu-id="9c97e-125">Install-Script</span><span class="sxs-lookup"><span data-stu-id="9c97e-125">Install-Script</span></span>](Install-Script.md)
<span data-ttu-id="9c97e-126">安装脚本。</span><span class="sxs-lookup"><span data-stu-id="9c97e-126">Installs a script.</span></span>

### [<span data-ttu-id="9c97e-127">New-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="9c97e-127">New-ScriptFileInfo</span></span>](New-ScriptFileInfo.md)
<span data-ttu-id="9c97e-128">使用元数据创建脚本文件。</span><span class="sxs-lookup"><span data-stu-id="9c97e-128">Creates a script file with metadata.</span></span>

### [<span data-ttu-id="9c97e-129">Publish-Module</span><span class="sxs-lookup"><span data-stu-id="9c97e-129">Publish-Module</span></span>](Publish-Module.md)
<span data-ttu-id="9c97e-130">将指定模块从本机计算机发布到联机库。</span><span class="sxs-lookup"><span data-stu-id="9c97e-130">Publishes a specified module from the local computer to an online gallery.</span></span>

### [<span data-ttu-id="9c97e-131">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="9c97e-131">Publish-Script</span></span>](Publish-Script.md)
<span data-ttu-id="9c97e-132">发布脚本。</span><span class="sxs-lookup"><span data-stu-id="9c97e-132">Publishes a script.</span></span>

### [<span data-ttu-id="9c97e-133">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9c97e-133">Register-PSRepository</span></span>](Register-PSRepository.md)
<span data-ttu-id="9c97e-134">注册 PowerShell 存储库。</span><span class="sxs-lookup"><span data-stu-id="9c97e-134">Registers a PowerShell repository.</span></span>

### [<span data-ttu-id="9c97e-135">Save-Module</span><span class="sxs-lookup"><span data-stu-id="9c97e-135">Save-Module</span></span>](Save-Module.md)
<span data-ttu-id="9c97e-136">将模块及其依赖项保存在本地计算机上，但不会安装该模块。</span><span class="sxs-lookup"><span data-stu-id="9c97e-136">Saves a module and its dependencies on the local computer but doesn't install the module.</span></span>

### [<span data-ttu-id="9c97e-137">Save-Script</span><span class="sxs-lookup"><span data-stu-id="9c97e-137">Save-Script</span></span>](Save-Script.md)
<span data-ttu-id="9c97e-138">保存脚本。</span><span class="sxs-lookup"><span data-stu-id="9c97e-138">Saves a script.</span></span>

### [<span data-ttu-id="9c97e-139">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9c97e-139">Set-PSRepository</span></span>](Set-PSRepository.md)
<span data-ttu-id="9c97e-140">为已注册的存储库设置值。</span><span class="sxs-lookup"><span data-stu-id="9c97e-140">Sets values for a registered repository.</span></span>

### [<span data-ttu-id="9c97e-141">Test-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="9c97e-141">Test-ScriptFileInfo</span></span>](Test-ScriptFileInfo.md)
<span data-ttu-id="9c97e-142">验证脚本的注释块。</span><span class="sxs-lookup"><span data-stu-id="9c97e-142">Validates a comment block for a script.</span></span>

### [<span data-ttu-id="9c97e-143">Uninstall-Module</span><span class="sxs-lookup"><span data-stu-id="9c97e-143">Uninstall-Module</span></span>](Uninstall-Module.md)
<span data-ttu-id="9c97e-144">卸载模块。</span><span class="sxs-lookup"><span data-stu-id="9c97e-144">Uninstalls a module.</span></span>

### [<span data-ttu-id="9c97e-145">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="9c97e-145">Uninstall-Script</span></span>](Uninstall-Script.md)
<span data-ttu-id="9c97e-146">卸载脚本。</span><span class="sxs-lookup"><span data-stu-id="9c97e-146">Uninstalls a script.</span></span>

### [<span data-ttu-id="9c97e-147">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="9c97e-147">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
<span data-ttu-id="9c97e-148">取消注册存储库。</span><span class="sxs-lookup"><span data-stu-id="9c97e-148">Unregisters a repository.</span></span>

### [<span data-ttu-id="9c97e-149">Update-Module</span><span class="sxs-lookup"><span data-stu-id="9c97e-149">Update-Module</span></span>](Update-Module.md)
<span data-ttu-id="9c97e-150">从联机库中下载指定模块的最新版本，并将其安装到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9c97e-150">Downloads and installs the newest version of specified modules from an online gallery to the local computer.</span></span>

### [<span data-ttu-id="9c97e-151">Update-ModuleManifest</span><span class="sxs-lookup"><span data-stu-id="9c97e-151">Update-ModuleManifest</span></span>](Update-ModuleManifest.md)
<span data-ttu-id="9c97e-152">更新模块清单文件。</span><span class="sxs-lookup"><span data-stu-id="9c97e-152">Updates a module manifest file.</span></span>

### [<span data-ttu-id="9c97e-153">Update-Script</span><span class="sxs-lookup"><span data-stu-id="9c97e-153">Update-Script</span></span>](Update-Script.md)
<span data-ttu-id="9c97e-154">更新脚本。</span><span class="sxs-lookup"><span data-stu-id="9c97e-154">Updates a script.</span></span>

### [<span data-ttu-id="9c97e-155">Update-ScriptFileInfo</span><span class="sxs-lookup"><span data-stu-id="9c97e-155">Update-ScriptFileInfo</span></span>](Update-ScriptFileInfo.md)
<span data-ttu-id="9c97e-156">更新脚本的信息。</span><span class="sxs-lookup"><span data-stu-id="9c97e-156">Updates information for a script.</span></span>

