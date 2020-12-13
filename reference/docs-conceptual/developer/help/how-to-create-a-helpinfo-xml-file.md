---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建 HelpInfo XML 文件
description: 如何创建 HelpInfo XML 文件
ms.openlocfilehash: d5a24306aa6488fdefad0b7b1ea9e2978a93a7b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647710"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="69f34-103">如何创建 HelpInfo XML 文件</span><span class="sxs-lookup"><span data-stu-id="69f34-103">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="69f34-104">本部分中的主题介绍如何创建和填充帮助信息文件（通常称为 "HelpInfo XML 文件"）以获取 PowerShell 可更新的帮助功能。</span><span class="sxs-lookup"><span data-stu-id="69f34-104">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="69f34-105">HelpInfo XML 文件概述</span><span class="sxs-lookup"><span data-stu-id="69f34-105">HelpInfo XML File Overview</span></span>

<span data-ttu-id="69f34-106">HelpInfo XML 文件是有关模块的可更新帮助的主要信息来源。</span><span class="sxs-lookup"><span data-stu-id="69f34-106">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="69f34-107">它包括模块的帮助文件的位置、支持的 UI 区域性以及可更新帮助用于确定用户是否具有最新帮助文件的版本号。</span><span class="sxs-lookup"><span data-stu-id="69f34-107">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="69f34-108">每个模块都只有一个 HelpInfo XML 文件，即使该模块包含多个 UI 区域性的多个帮助文件也是如此。</span><span class="sxs-lookup"><span data-stu-id="69f34-108">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="69f34-109">模块作者创建 HelpInfo XML 文件，并将其放置在由模块清单中的 **HelpInfoUri** 键指定的 internet 位置。</span><span class="sxs-lookup"><span data-stu-id="69f34-109">The module author creates the HelpInfo XML file and places it in the internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="69f34-110">当模块帮助文件更新并上传时，模块作者将更新 HelpInfo XML 文件，并将原始 HelpInfo XML 文件替换为新版本。</span><span class="sxs-lookup"><span data-stu-id="69f34-110">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="69f34-111">仔细维护 HelpInfo XML 文件非常重要。</span><span class="sxs-lookup"><span data-stu-id="69f34-111">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="69f34-112">如果上传新文件，但忘记增加版本号，则可更新帮助不会将新文件下载到用户的计算机。</span><span class="sxs-lookup"><span data-stu-id="69f34-112">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="69f34-113">如果为新的 UI 区域性添加帮助文件，但不更新 HelpInfo XML 文件或将其放在正确的位置，则可更新的帮助将不会下载新文件。</span><span class="sxs-lookup"><span data-stu-id="69f34-113">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="69f34-114">在本节中</span><span class="sxs-lookup"><span data-stu-id="69f34-114">In this section</span></span>

<span data-ttu-id="69f34-115">本部分包括以下主题。</span><span class="sxs-lookup"><span data-stu-id="69f34-115">This section includes the following topics.</span></span>

- [<span data-ttu-id="69f34-116">HelpInfo XML 架构</span><span class="sxs-lookup"><span data-stu-id="69f34-116">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="69f34-117">HelpInfo XML 示例文件</span><span class="sxs-lookup"><span data-stu-id="69f34-117">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="69f34-118">如何命名 HelpInfo XML 文件</span><span class="sxs-lookup"><span data-stu-id="69f34-118">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="69f34-119">如何设置 HelpInfo XML 版本号</span><span class="sxs-lookup"><span data-stu-id="69f34-119">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="69f34-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69f34-120">See Also</span></span>

[<span data-ttu-id="69f34-121">支持可更新帮助</span><span class="sxs-lookup"><span data-stu-id="69f34-121">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)
