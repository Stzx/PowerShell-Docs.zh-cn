---
ms.date: 06/12/2017
title: PowerShell 库入门
description: 本文介绍如何开始使用 PowerShell 库和 PowerShellGet cmdlet
ms.openlocfilehash: a5045e4ecee2eb8bc9aa373a6b8ec3a940b4de33
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913266"
---
# <a name="getting-started-with-the-powershell-gallery"></a><span data-ttu-id="1d64e-103">PowerShell 库入门</span><span class="sxs-lookup"><span data-stu-id="1d64e-103">Getting Started with the PowerShell Gallery</span></span>

<span data-ttu-id="1d64e-104">PowerShell 库是一个包存储库，包含脚本、模块以及可供下载和使用的 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="1d64e-104">The PowerShell Gallery is a package repository containing scripts, modules, and DSC resources you can download and leverage.</span></span> <span data-ttu-id="1d64e-105">可以使用 [PowerShellGet](/powershell/module/powershellget) 模块中的 cmdlet 从 PowerShell 库安装包。</span><span class="sxs-lookup"><span data-stu-id="1d64e-105">You use the cmdlets in the [PowerShellGet](/powershell/module/powershellget) module to install packages from the PowerShell Gallery.</span></span> <span data-ttu-id="1d64e-106">从 PowerShell 库下载项时无需登录。</span><span class="sxs-lookup"><span data-stu-id="1d64e-106">You do not need to sign in to download items from the PowerShell Gallery.</span></span>

> [!NOTE]
> <span data-ttu-id="1d64e-107">可直接从 PowerShell 库下载包，但不推荐此方法。</span><span class="sxs-lookup"><span data-stu-id="1d64e-107">It is possible to download a package from the PowerShell Gallery directly, but this is not a recommended approach.</span></span> <span data-ttu-id="1d64e-108">有关详细信息，请参阅[手动包下载](how-to/working-with-packages/manual-download.md)。</span><span class="sxs-lookup"><span data-stu-id="1d64e-108">For more details, see [Manual Package Download](how-to/working-with-packages/manual-download.md).</span></span>

## <a name="discovering-packages-from-the-powershell-gallery"></a><span data-ttu-id="1d64e-109">从 PowerShell 库中发现包</span><span class="sxs-lookup"><span data-stu-id="1d64e-109">Discovering packages from the PowerShell Gallery</span></span>

<span data-ttu-id="1d64e-110">可通过使用 PowerShell 库[主页](https://www.powershellgallery.com)上的“搜索”控件或浏览[程序包页](https://www.powershellgallery.com/packages)中的“模块和脚本”来查找 PowerShell 库中的包。</span><span class="sxs-lookup"><span data-stu-id="1d64e-110">You can find packages in the PowerShell Gallery by using the **Search** control on the PowerShell Gallery's [home page](https://www.powershellgallery.com), or by browsing through the Modules and Scripts from the [Packages page](https://www.powershellgallery.com/packages).</span></span> <span data-ttu-id="1d64e-111">还可以使用 `-Repository PSGallery` 运行 [Find-Module][]、[Find-DscResource] 和 [Find-Script][] cmdlet（具体视包类型而定），来查找 PowerShell 库中的包。</span><span class="sxs-lookup"><span data-stu-id="1d64e-111">You can also find packages from the PowerShell Gallery by running the [Find-Module][], [Find-DscResource], and [Find-Script][] cmdlets, depending on the package type, with `-Repository PSGallery`.</span></span>

<span data-ttu-id="1d64e-112">可使用以下参数筛选库中的结果：</span><span class="sxs-lookup"><span data-stu-id="1d64e-112">You can filter results from the Gallery by using the following parameters:</span></span>

- <span data-ttu-id="1d64e-113">名称</span><span class="sxs-lookup"><span data-stu-id="1d64e-113">Name</span></span>
- <span data-ttu-id="1d64e-114">AllVersions</span><span class="sxs-lookup"><span data-stu-id="1d64e-114">AllVersions</span></span>
- <span data-ttu-id="1d64e-115">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="1d64e-115">MinimumVersion</span></span>
- <span data-ttu-id="1d64e-116">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="1d64e-116">RequiredVersion</span></span>
- <span data-ttu-id="1d64e-117">标记</span><span class="sxs-lookup"><span data-stu-id="1d64e-117">Tag</span></span>
- <span data-ttu-id="1d64e-118">包括</span><span class="sxs-lookup"><span data-stu-id="1d64e-118">Includes</span></span>
- <span data-ttu-id="1d64e-119">DscResource</span><span class="sxs-lookup"><span data-stu-id="1d64e-119">DscResource</span></span>
- <span data-ttu-id="1d64e-120">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="1d64e-120">RoleCapability</span></span>
- <span data-ttu-id="1d64e-121">Command</span><span class="sxs-lookup"><span data-stu-id="1d64e-121">Command</span></span>
- <span data-ttu-id="1d64e-122">筛选器</span><span class="sxs-lookup"><span data-stu-id="1d64e-122">Filter</span></span>

<span data-ttu-id="1d64e-123">如果只想发现库中的特定 DSC 资源，可运行 [Find-DscResource][] cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1d64e-123">If you're only interested in discovering specific DSC resources in the Gallery, you can run the [Find-DscResource][] cmdlet.</span></span> <span data-ttu-id="1d64e-124">Find-DscResource 会返回库中 DSC 资源的相关数据。</span><span class="sxs-lookup"><span data-stu-id="1d64e-124">Find-DscResource returns data on DSC resources contained in the Gallery.</span></span> <span data-ttu-id="1d64e-125">由于 DSC 资源始终作为模块的一部分进行传递，因此仍需要运行 Install-Module[][] 来安装这些 DSC 资源。</span><span class="sxs-lookup"><span data-stu-id="1d64e-125">Because DSC resources are always delivered as part of a module, you still need to run [Install-Module][] to install those DSC resources.</span></span>

## <a name="learning-about-packages-in-the-powershell-gallery"></a><span data-ttu-id="1d64e-126">了解 PowerShell 库中的包</span><span class="sxs-lookup"><span data-stu-id="1d64e-126">Learning about packages in the PowerShell Gallery</span></span>

<span data-ttu-id="1d64e-127">找到感兴趣的包后，你可能想要了解更多有关信息。</span><span class="sxs-lookup"><span data-stu-id="1d64e-127">Once you've identified a package that you're interested in, you may want to learn more about it.</span></span> <span data-ttu-id="1d64e-128">可检查库中该包的特定页来了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1d64e-128">You can do this by examining that package's specific page on the Gallery.</span></span> <span data-ttu-id="1d64e-129">在该页上可查看该包中上载的所有元数据。</span><span class="sxs-lookup"><span data-stu-id="1d64e-129">On that page, you'll be able to see all of the metadata uploaded with the package.</span></span> <span data-ttu-id="1d64e-130">此元数据由包作者提供，Microsoft 不会对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="1d64e-130">This metadata is provided by the package's author, and is not verified by Microsoft.</span></span> <span data-ttu-id="1d64e-131">包的所有者紧密关联到用于发布该包的 PowerShell 库帐户，比“作者”字段更可信。</span><span class="sxs-lookup"><span data-stu-id="1d64e-131">The Owner of the package is strongly tied to the Gallery account used to publish the package, and is more trustworthy than the Author field.</span></span>

<span data-ttu-id="1d64e-132">如果发现发布的包不可信，请单击该包页面上的“报告滥用行为”。</span><span class="sxs-lookup"><span data-stu-id="1d64e-132">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

<span data-ttu-id="1d64e-133">如果运行的是 Find-Module[][] 或 Find-Script[][]，可以在返回的 PSGetModuleInfo 对象中查看此数据。</span><span class="sxs-lookup"><span data-stu-id="1d64e-133">If you're running [Find-Module][] or [Find-Script][], you can view this data in the returned PSGetModuleInfo object.</span></span> <span data-ttu-id="1d64e-134">例如，运行 `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` 会返回库中 PSReadLine 模块的相关数据。</span><span class="sxs-lookup"><span data-stu-id="1d64e-134">For example, running `Find-Module -Name PSReadLine -Repository PSGallery |Get-Member` returns data on the PSReadLine module in the Gallery.</span></span>

## <a name="downloading-packages-from-the-powershell-gallery"></a><span data-ttu-id="1d64e-135">从 PowerShell 库下载包</span><span class="sxs-lookup"><span data-stu-id="1d64e-135">Downloading packages from the PowerShell Gallery</span></span>

<span data-ttu-id="1d64e-136">从 PowerShell 库下载包时，建议执行下列过程：</span><span class="sxs-lookup"><span data-stu-id="1d64e-136">We encourage the following process when downloading packages from the PowerShell Gallery:</span></span>

### <a name="inspect"></a><span data-ttu-id="1d64e-137">检查</span><span class="sxs-lookup"><span data-stu-id="1d64e-137">Inspect</span></span>

<span data-ttu-id="1d64e-138">若要下载库中的包以供检查，请运行 [Save-Module][] 或 [Save-Script][] cmdlet，具体视包类型而定。</span><span class="sxs-lookup"><span data-stu-id="1d64e-138">To download a package from the Gallery for inspection, run either the [Save-Module][] or [Save-Script][] cmdlet, depending on the package type.</span></span> <span data-ttu-id="1d64e-139">此操作可本地保存包而不进行安装，并且可以检查包内容。</span><span class="sxs-lookup"><span data-stu-id="1d64e-139">This lets you save the package locally without installing it, and inspect the package contents.</span></span> <span data-ttu-id="1d64e-140">请记得手动删除已保存的包。</span><span class="sxs-lookup"><span data-stu-id="1d64e-140">Remember to delete the saved package manually.</span></span>

<span data-ttu-id="1d64e-141">其中一些包由 Microsoft 编写，另一些包由 PowerShell 社区编写。</span><span class="sxs-lookup"><span data-stu-id="1d64e-141">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span> <span data-ttu-id="1d64e-142">Microsoft 建议安装前检查库中包的内容和代码。</span><span class="sxs-lookup"><span data-stu-id="1d64e-142">Microsoft recommends that you review the contents and code of packages on this gallery prior to installation.</span></span>

<span data-ttu-id="1d64e-143">如果发现发布的包不可信，请单击该包页面上的“报告滥用行为”。</span><span class="sxs-lookup"><span data-stu-id="1d64e-143">If you discover a package that you feel is not published in good faith, click **Report Abuse** on that package's page.</span></span>

### <a name="install"></a><span data-ttu-id="1d64e-144">安装</span><span class="sxs-lookup"><span data-stu-id="1d64e-144">Install</span></span>

<span data-ttu-id="1d64e-145">若要安装库中的包以供使用，请运行 [Install-Module][] 或 [Install-Script][] cmdlet，具体视包类型而定。</span><span class="sxs-lookup"><span data-stu-id="1d64e-145">To install a package from the Gallery for use, run either the [Install-Module][] or [Install-Script][] cmdlet, depending on the package type.</span></span>

<span data-ttu-id="1d64e-146">默认情况下，Install-Module[][] 将模块安装到 `$env:ProgramFiles\WindowsPowerShell\Modules`。</span><span class="sxs-lookup"><span data-stu-id="1d64e-146">[Install-Module][] installs the module to `$env:ProgramFiles\WindowsPowerShell\Modules` by default.</span></span>
<span data-ttu-id="1d64e-147">此操作需要管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="1d64e-147">This requires an administrator account.</span></span> <span data-ttu-id="1d64e-148">如果添加 `-Scope CurrentUser` 参数，模块将安装到 `$env:USERPROFILE\Documents\WindowsPowerShell\Modules`。</span><span class="sxs-lookup"><span data-stu-id="1d64e-148">If you add the `-Scope CurrentUser` parameter, the module is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Modules` .</span></span>

<span data-ttu-id="1d64e-149">默认情况下，Install-Script[][] 将脚本安装到 `$env:ProgramFiles\WindowsPowerShell\Scripts`。</span><span class="sxs-lookup"><span data-stu-id="1d64e-149">[Install-Script][] installs the script to `$env:ProgramFiles\WindowsPowerShell\Scripts` by default.</span></span>
<span data-ttu-id="1d64e-150">此操作需要管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="1d64e-150">This requires an administrator account.</span></span> <span data-ttu-id="1d64e-151">如果添加 `-Scope CurrentUser` 参数，脚本将安装到 `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts`。</span><span class="sxs-lookup"><span data-stu-id="1d64e-151">If you add the `-Scope CurrentUser` parameter, the script is installed to `$env:USERPROFILE\Documents\WindowsPowerShell\Scripts` .</span></span>

<span data-ttu-id="1d64e-152">默认情况下，[Install-Module][] 和 [Install-Script][] 安装最新版包。</span><span class="sxs-lookup"><span data-stu-id="1d64e-152">By default, [Install-Module][] and [Install-Script][] installs the most current version of a package.</span></span> <span data-ttu-id="1d64e-153">若要安装旧版包，请添加 `-RequiredVersion` 参数。</span><span class="sxs-lookup"><span data-stu-id="1d64e-153">To install an older version of the package, add the `-RequiredVersion` parameter.</span></span>

### <a name="deploy"></a><span data-ttu-id="1d64e-154">部署</span><span class="sxs-lookup"><span data-stu-id="1d64e-154">Deploy</span></span>

<span data-ttu-id="1d64e-155">若要将包从 PowerShell 库部署到 Azure 自动化，请单击“Azure 自动化”，然后单击包详细信息页上的“部署到 Azure 自动化”。</span><span class="sxs-lookup"><span data-stu-id="1d64e-155">To deploy a package from the PowerShell Gallery to Azure Automation, click **Azure Automation**, then click **Deploy to Azure Automation** on the package details page.</span></span> <span data-ttu-id="1d64e-156">这会将你重定向到 Azure 管理门户，可使用 Azure 帐户凭据登录该门户。</span><span class="sxs-lookup"><span data-stu-id="1d64e-156">You are redirected to the Azure Management Portal where you sign in by using your Azure account credentials.</span></span> <span data-ttu-id="1d64e-157">请注意，部署具有依赖关系的包会将所有依赖关系部署到 Azure 自动化。</span><span class="sxs-lookup"><span data-stu-id="1d64e-157">Note that deploying packages with dependencies deploys all the dependencies to Azure Automation.</span></span> <span data-ttu-id="1d64e-158">通过将 AzureAutomationNotSupported 标记添加到包元数据可禁用“部署到 Azure 自动化”按钮。</span><span class="sxs-lookup"><span data-stu-id="1d64e-158">The 'Deploy to Azure Automation' button can be disabled by adding the **AzureAutomationNotSupported** tag to your package metadata.</span></span>

<span data-ttu-id="1d64e-159">若要了解有关 Azure 自动化的详细信息，请参阅 [Azure 自动化](/azure/automation)文档。</span><span class="sxs-lookup"><span data-stu-id="1d64e-159">To learn more about Azure Automation, see the [Azure Automation](/azure/automation) documentation.</span></span>

## <a name="updating-packages-from-the-powershell-gallery"></a><span data-ttu-id="1d64e-160">从 PowerShell 库更新包</span><span class="sxs-lookup"><span data-stu-id="1d64e-160">Updating packages from the PowerShell Gallery</span></span>

<span data-ttu-id="1d64e-161">若要更新从 PowerShell 库安装的包，请运行 Update-Module[][] 或 Update-Script[][] cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1d64e-161">To update packages installed from the PowerShell Gallery, run either the [Update-Module][] or [Update-Script][] cmdlet.</span></span> <span data-ttu-id="1d64e-162">如果不使用其他任何参数运行，Update-Module[][] 会尝试更新所有通过运行 Install-Module[][] 来安装的模块。</span><span class="sxs-lookup"><span data-stu-id="1d64e-162">When run without any additional parameters, [Update-Module][] attempts to update all modules installed by running [Install-Module][].</span></span> <span data-ttu-id="1d64e-163">若要选择性地更新模块，请添加 `-Name` 参数。</span><span class="sxs-lookup"><span data-stu-id="1d64e-163">To selectively update modules, add the `-Name` parameter.</span></span>

<span data-ttu-id="1d64e-164">同样，如果不使用其他任何参数运行，Update-Script[][] 也会尝试更新所有通过运行 Install-Script[][] 来安装的脚本。</span><span class="sxs-lookup"><span data-stu-id="1d64e-164">Similarly, when run without any additional parameters, [Update-Script][] also attempts to update all scripts installed by running [Install-Script][].</span></span> <span data-ttu-id="1d64e-165">若要选择性地更新脚本，请添加 `-Name` 参数。</span><span class="sxs-lookup"><span data-stu-id="1d64e-165">To selectively update scripts, add the `-Name` parameter.</span></span>

## <a name="list-packages-that-you-have-installed-from-the-powershell-gallery"></a><span data-ttu-id="1d64e-166">列出从 PowerShell 库安装的包</span><span class="sxs-lookup"><span data-stu-id="1d64e-166">List packages that you have installed from the PowerShell Gallery</span></span>

<span data-ttu-id="1d64e-167">若要查找从 PowerShell 库中安装的模块，请运行 [Get-InstalledModule][] cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1d64e-167">To find out which modules you have installed from the PowerShell Gallery, run the [Get-InstalledModule][] cmdlet.</span></span> <span data-ttu-id="1d64e-168">该命令会列出系统上所有已直接从 PowerShell 库安装的模块。</span><span class="sxs-lookup"><span data-stu-id="1d64e-168">This command lists all of the modules you have on your system that were installed directly from the PowerShell Gallery.</span></span>

<span data-ttu-id="1d64e-169">同样，若要查找从 PowerShell 库已安装的脚本，请运行 [Get-InstalledScript][] cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1d64e-169">Similarly, to find out which scripts you have installed from the PowerShell Gallery, run the [Get-InstalledScript][] cmdlet.</span></span> <span data-ttu-id="1d64e-170">此命令会列出系统上所有已直接从 PowerShell 库安装的脚本。</span><span class="sxs-lookup"><span data-stu-id="1d64e-170">This command lists all the scripts you have on your system that were installed directly from the PowerShell Gallery.</span></span>

## <a name="network-access-to-the-powershell-gallery"></a><span data-ttu-id="1d64e-171">对 PowerShell 库的网络访问</span><span class="sxs-lookup"><span data-stu-id="1d64e-171">Network access to the PowerShell Gallery</span></span>

<span data-ttu-id="1d64e-172">PowerShell 库使用以下主机名。</span><span class="sxs-lookup"><span data-stu-id="1d64e-172">The PowerShell Gallery uses the following hostnames.</span></span>

- <span data-ttu-id="1d64e-173">`psg-prod-eastus.azureedge.net` - CDN 主机名</span><span class="sxs-lookup"><span data-stu-id="1d64e-173">`psg-prod-eastus.azureedge.net` - CDN hostname</span></span>
- <span data-ttu-id="1d64e-174">`az818661.vo.msecnd.net` - CDN 主机名</span><span class="sxs-lookup"><span data-stu-id="1d64e-174">`az818661.vo.msecnd.net` - CDN hostname</span></span>
- <span data-ttu-id="1d64e-175">`devopsgallerystorage.blob.core.windows.net` - 存储帐户主机名</span><span class="sxs-lookup"><span data-stu-id="1d64e-175">`devopsgallerystorage.blob.core.windows.net` - storage account hostname</span></span>
- <span data-ttu-id="1d64e-176">`*.powershellgallery.com` - 网站</span><span class="sxs-lookup"><span data-stu-id="1d64e-176">`*.powershellgallery.com` - website</span></span>
- <span data-ttu-id="1d64e-177">`go.microsoft.com` - 重定向服务</span><span class="sxs-lookup"><span data-stu-id="1d64e-177">`go.microsoft.com` - redirection service</span></span>

<span data-ttu-id="1d64e-178">应将这些主机名添加到控制网络访问权限的允许列表中。</span><span class="sxs-lookup"><span data-stu-id="1d64e-178">These hostnames should be added to the allow lists that control access from your network.</span></span>

[!INCLUDE [TLS 1.2 Requirement](../../includes/tls-gallery.md)]

[Find-DscResource]: /powershell/module/powershellget/Find-DscResource
[Find-Module]: /powershell/module/powershellget/Find-Module
[Find-Script]: /powershell/module/powershellget/Find-Script
[Get-InstalledModule]: /powershell/module/powershellget/Get-InstalledModule
[Get-InstalledScript]: /powershell/module/powershellget/Get-InstalledScript
[Install-Module]: /powershell/module/powershellget/Install-Module
[Install-Script]: /powershell/module/powershellget/Install-Script
[Publish-Module]: /powershell/module/powershellget/Publish-Module
[Publish-Script]: /powershell/module/powershellget/Publish-Script
[Register-PSRepository]: /powershell/module/powershellget/Register-Repository
[Save-Module]: /powershell/module/powershellget/Save-Module
[Save-Script]: /powershell/module/powershellget/Save-Script
[Update-Module]: /powershell/module/powershellget/Update-Module
[Update-Script]: /powershell/module/powershellget/Update-Script
