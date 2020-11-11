---
ms.openlocfilehash: d94024926a8ff8c33df08b4a8b58e9f8b0430f9b
ms.sourcegitcommit: fcf7bd222f5ee3fdbe21ffddcae47050cffe7e42
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "93239878"
---
# <a name="microsoft-open-source-code-of-conduct"></a><span data-ttu-id="abc4b-101">Microsoft 开放源代码行为准则</span><span class="sxs-lookup"><span data-stu-id="abc4b-101">Microsoft Open Source Code of Conduct</span></span>

> <span data-ttu-id="abc4b-102">更新时间：2020/11/02</span><span class="sxs-lookup"><span data-stu-id="abc4b-102">Updated: 11/02/2020</span></span>

<span data-ttu-id="abc4b-103">此项目采用了 [Microsoft 开放源代码行为准则](https://opensource.microsoft.com/codeofconduct/)。</span><span class="sxs-lookup"><span data-stu-id="abc4b-103">This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span> <span data-ttu-id="abc4b-104">有关详细信息，请参阅[行为准则常见问题](https://opensource.microsoft.com/codeofconduct/faq/)，或如果有任何其他问题或意见，请与 [opencode@microsoft.com](mailto:opencode@microsoft.com) 联系。</span><span class="sxs-lookup"><span data-stu-id="abc4b-104">For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.</span></span>

[live-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=live
[staging-badge]: https://powershell.visualstudio.com/PowerShell-Docs/_apis/build/status/PowerShell-Docs-CI?branchName=staging

## <a name="build-status"></a><span data-ttu-id="abc4b-107">生成状态</span><span class="sxs-lookup"><span data-stu-id="abc4b-107">Build Status</span></span>

|          <span data-ttu-id="abc4b-108">活动分支</span><span class="sxs-lookup"><span data-stu-id="abc4b-108">Live Branch</span></span>          |           <span data-ttu-id="abc4b-109">临时分支</span><span class="sxs-lookup"><span data-stu-id="abc4b-109">Staging Branch</span></span>            |
| :---------------------------- | :---------------------------------- |
| <span data-ttu-id="abc4b-110">[![live-badge][]][live-badge]</span><span class="sxs-lookup"><span data-stu-id="abc4b-110">[![live-badge][]][live-badge]</span></span> | <span data-ttu-id="abc4b-111">[![staging-badge][]][staging-badge]</span><span class="sxs-lookup"><span data-stu-id="abc4b-111">[![staging-badge][]][staging-badge]</span></span> |

## <a name="powershell-documentation"></a><span data-ttu-id="abc4b-112">PowerShell 文档</span><span class="sxs-lookup"><span data-stu-id="abc4b-112">PowerShell Documentation</span></span>

<span data-ttu-id="abc4b-113">欢迎使用 PowerShell 文档存储库，其中包含官方 PowerShell 文档。</span><span class="sxs-lookup"><span data-stu-id="abc4b-113">Welcome to the PowerShell-Docs repository, the home of the official PowerShell documentation.</span></span>

## <a name="repository-structure"></a><span data-ttu-id="abc4b-114">存储库结构</span><span class="sxs-lookup"><span data-stu-id="abc4b-114">Repository Structure</span></span>

<span data-ttu-id="abc4b-115">以下列表列出了此存储库中的主文件夹。</span><span class="sxs-lookup"><span data-stu-id="abc4b-115">The following list describes the main folders in this repository.</span></span>

- <span data-ttu-id="abc4b-116">`.github` -包含 GitHub 用于此存储库的配置设置</span><span class="sxs-lookup"><span data-stu-id="abc4b-116">`.github` - contains configuration settings used by GitHub for this repository</span></span>
- <span data-ttu-id="abc4b-117">`.vscode` - 包含 Visual Studio Code (VS Code) 的配置设置和建议扩展</span><span class="sxs-lookup"><span data-stu-id="abc4b-117">`.vscode` - contains configuration settings and recommended extensions for Visual Studio Code (VS Code)</span></span>
- <span data-ttu-id="abc4b-118">`assets` - 包含文档中链接的可下载文件</span><span class="sxs-lookup"><span data-stu-id="abc4b-118">`assets` - contains downloadable files linked in the documentation</span></span>
- <span data-ttu-id="abc4b-119">`reference` - 包含发布到 [docs.microsoft.com]([https://docs.microsoft.com/powershell/scripting/) 的文档。</span><span class="sxs-lookup"><span data-stu-id="abc4b-119">`reference` - contains the documentation published to [docs.microsoft.com]([https://docs.microsoft.com/powershell/scripting/).</span></span> <span data-ttu-id="abc4b-120">这包括引用和概念内容。</span><span class="sxs-lookup"><span data-stu-id="abc4b-120">This includes both reference and conceptual content.</span></span>
  - <span data-ttu-id="abc4b-121">`5.1` - 包含 PowerShell 5.1 的 cmdlet 参考和“关于”主题</span><span class="sxs-lookup"><span data-stu-id="abc4b-121">`5.1` - contains the cmdlet reference and about topics for PowerShell 5.1</span></span>
  - <span data-ttu-id="abc4b-122">`6` - 包含 PowerShell 6 的 cmdlet 参考和“关于”主题</span><span class="sxs-lookup"><span data-stu-id="abc4b-122">`6` - contains the cmdlet reference and about topics for PowerShell 6</span></span>
  - <span data-ttu-id="abc4b-123">`7.0` - 包含 PowerShell 7.0 的 cmdlet 参考和“关于”主题</span><span class="sxs-lookup"><span data-stu-id="abc4b-123">`7.0` - contains the cmdlet reference and about topics for PowerShell 7.0</span></span>
  - <span data-ttu-id="abc4b-124">`7.1` - 包含 PowerShell 7.1 的 cmdlet 参考和“关于”主题</span><span class="sxs-lookup"><span data-stu-id="abc4b-124">`7.1` - contains the cmdlet reference and about topics for PowerShell 7.1</span></span>
  - <span data-ttu-id="abc4b-125">`bread` - 包含用于痕迹导航的 TOC</span><span class="sxs-lookup"><span data-stu-id="abc4b-125">`bread` - contains the TOC used for breadcrumb navigation</span></span>
  - <span data-ttu-id="abc4b-126">`docs-conceptual` - 包含发布到 Docs 站点的概念文章。</span><span class="sxs-lookup"><span data-stu-id="abc4b-126">`docs-conceptual` - contains the conceptual articles that are published to the Docs site.</span></span> <span data-ttu-id="abc4b-127">通常，文件夹结构会建立目录 (TOC) 镜像。</span><span class="sxs-lookup"><span data-stu-id="abc4b-127">In general, the folder structure mirrors the Table of Contents (TOC).</span></span>
  - <span data-ttu-id="abc4b-128">`mapping` - 包含生成系统使用的版本映射配置</span><span class="sxs-lookup"><span data-stu-id="abc4b-128">`mapping` - contains the version mapping configuration used by the build system</span></span>
  - <span data-ttu-id="abc4b-129">`media` - 包含文档中使用的图像文件。</span><span class="sxs-lookup"><span data-stu-id="abc4b-129">`media` - contains image files used in documentation.</span></span> <span data-ttu-id="abc4b-130">`docs-conceptual` 内容中有媒体文件夹。</span><span class="sxs-lookup"><span data-stu-id="abc4b-130">There are media folders throughout the `docs-conceptual` content.</span></span> <span data-ttu-id="abc4b-131">有关在文档中使用图像的信息，请参阅“参与者指南”。</span><span class="sxs-lookup"><span data-stu-id="abc4b-131">See the Contributor Guide for information on using images in documentation.</span></span>
  - <span data-ttu-id="abc4b-132">`module` - 包含“模块浏览器”页面的 markdown 源</span><span class="sxs-lookup"><span data-stu-id="abc4b-132">`module` - contains the markdown source for the Module Browser page</span></span>
- <span data-ttu-id="abc4b-133">`tests` - 包含生成系统使用的 Pester 测试</span><span class="sxs-lookup"><span data-stu-id="abc4b-133">`tests` - contains the Pester tests used by the build system</span></span>
- <span data-ttu-id="abc4b-134">`tools` - 包含生成系统使用的其他工具</span><span class="sxs-lookup"><span data-stu-id="abc4b-134">`tools` - contains other tools used by the build system</span></span>

> <span data-ttu-id="abc4b-135">注意：参考内容（在编号文件夹中）用于在 Docs 站点上创建网页，也可用作针对 PowerShell 的可更新帮助。</span><span class="sxs-lookup"><span data-stu-id="abc4b-135">NOTE: The reference content (in the numbered folders) is used to create the webpages on the Docs site as well as the updateable help used by PowerShell.</span></span>
> <span data-ttu-id="abc4b-136">`docs-conceptual` 文件夹中的文章仅发布到 Docs 网站。</span><span class="sxs-lookup"><span data-stu-id="abc4b-136">The articles in the `docs-conceptual` folder are only published to the Docs website.</span></span>

## <a name="contributing"></a><span data-ttu-id="abc4b-137">供稿</span><span class="sxs-lookup"><span data-stu-id="abc4b-137">Contributing</span></span>

<span data-ttu-id="abc4b-138">通过[拉取请求](https://help.github.com/articles/using-pull-requests/)到临时分支，我们欢迎将贡献的公共文档并入此存储库。</span><span class="sxs-lookup"><span data-stu-id="abc4b-138">We welcome public contributions into this repository via [pull requests](https://help.github.com/articles/using-pull-requests/) into the _staging_ branch.</span></span>
<span data-ttu-id="abc4b-139">请注意，必须签署我们的[贡献许可协议](https://cla.microsoft.com/)，我们才会接受你的拉取请求。</span><span class="sxs-lookup"><span data-stu-id="abc4b-139">Please note that before we can accept your pull request you must sign our [Contribution License Agreement](https://cla.microsoft.com/).</span></span> <span data-ttu-id="abc4b-140">只需执行此操作一次。</span><span class="sxs-lookup"><span data-stu-id="abc4b-140">This is a one-time requirement.</span></span>

<span data-ttu-id="abc4b-141">若要详细了解如何参与，请阅读[参与者指南](https://aka.ms/PSDocsContributor)。</span><span class="sxs-lookup"><span data-stu-id="abc4b-141">For more information on contributing, read our [contributor's guide](https://aka.ms/PSDocsContributor).</span></span> <span data-ttu-id="abc4b-142">参与者指南详细介绍了如何参与撰写文档、推荐的工具以及样式和格式设置要求。</span><span class="sxs-lookup"><span data-stu-id="abc4b-142">The contributor's guide contains detail information about how to contribute documentation, suggested tools, and style and formatting requirements.</span></span> <span data-ttu-id="abc4b-143">请使用“问题和提取请求”模板来帮助文档在各版本之间保持一致性。</span><span class="sxs-lookup"><span data-stu-id="abc4b-143">Please use the Issue and Pull Request templates to help keep documentation consistent across versions.</span></span>

## <a name="licenses"></a><span data-ttu-id="abc4b-144">许可证</span><span class="sxs-lookup"><span data-stu-id="abc4b-144">Licenses</span></span>

<span data-ttu-id="abc4b-145">此项目有两个许可证文件。</span><span class="sxs-lookup"><span data-stu-id="abc4b-145">There are two license files for this project.</span></span> <span data-ttu-id="abc4b-146">MIT 许可证适用于包含在此存储库中的代码。</span><span class="sxs-lookup"><span data-stu-id="abc4b-146">The MIT License applies to the code contained in this repo.</span></span> <span data-ttu-id="abc4b-147">Creative Commons 许可证适用于文档。</span><span class="sxs-lookup"><span data-stu-id="abc4b-147">The Creative Commons license applies to the documentation.</span></span>
