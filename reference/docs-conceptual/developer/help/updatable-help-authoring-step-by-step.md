---
ms.date: 09/13/2016
ms.topic: reference
title: 可更新的帮助创作-分步
description: 可更新的帮助创作-分步
ms.openlocfilehash: c4aecdb801cac16c9cb07853317835fd87e6a0a8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658816"
---
# <a name="updatable-help-authoring-step-by-step"></a><span data-ttu-id="7cb86-103">可更新帮助创作：分步指南</span><span class="sxs-lookup"><span data-stu-id="7cb86-103">Updatable Help Authoring: Step-by-Step</span></span>

<span data-ttu-id="7cb86-104">此文档列出了创作可更新帮助的过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="7cb86-104">This documents lists the steps in the process of authoring Updatable Help.</span></span>

## <a name="authoring-updatable-help-step-by-step"></a><span data-ttu-id="7cb86-105">创作可更新帮助：分步</span><span class="sxs-lookup"><span data-stu-id="7cb86-105">Authoring Updatable Help: Step-by-Step</span></span>

<span data-ttu-id="7cb86-106">可更新的帮助是为最终用户设计的，但它还为模块作者和帮助编写人员提供了极大的优势，包括添加内容、修复错误、在多个 UI 区域性中交付以及响应用户注释和请求的能力，长时间已发送到模块。</span><span class="sxs-lookup"><span data-stu-id="7cb86-106">Updatable Help is designed for end-users, but it also provides significant benefits to module authors and help writers, including the ability to add content, fix errors, deliver in multiple UI cultures, and respond to user comments and requests, long after the module has shipped.</span></span> <span data-ttu-id="7cb86-107">本主题介绍如何打包和上传帮助文件，以便用户可以使用 [update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) 和 [get-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 下载和安装帮助文件。</span><span class="sxs-lookup"><span data-stu-id="7cb86-107">This topic explains how you package and upload help files so that users can download and install them by using the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="7cb86-108">以下步骤概述了支持可更新帮助的过程。</span><span class="sxs-lookup"><span data-stu-id="7cb86-108">The following steps provide an overview of the process of supporting Updatable Help.</span></span>

### <a name="step-1-find-an-internet-site-for-your-help-files"></a><span data-ttu-id="7cb86-109">步骤1：查找帮助文件的 internet 站点</span><span class="sxs-lookup"><span data-stu-id="7cb86-109">Step 1: Find an internet site for your help files</span></span>

<span data-ttu-id="7cb86-110">创建可更新帮助的第一步是在 internet 位置查找模块的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="7cb86-110">The first step in creating updatable help is to find an internet location for your module's help files.</span></span> <span data-ttu-id="7cb86-111">实际上，可以使用两个不同的位置。</span><span class="sxs-lookup"><span data-stu-id="7cb86-111">Actually, you can use two different locations.</span></span> <span data-ttu-id="7cb86-112">你可以保留模块的帮助信息文件 (下面的 HelpInfo XML) 在一个 internet 位置，并将帮助内容 CAB 文件放在另一个 internet 位置。</span><span class="sxs-lookup"><span data-stu-id="7cb86-112">You can keep your module's help information file (HelpInfo XML - described below) at one internet location and the help content CAB files at another internet location.</span></span> <span data-ttu-id="7cb86-113">模块的所有帮助内容 CAB 文件都必须位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="7cb86-113">All help content CAB files for a module must be in the same location.</span></span> <span data-ttu-id="7cb86-114">可以将不同模块的帮助内容 CAB 文件放置在同一位置。</span><span class="sxs-lookup"><span data-stu-id="7cb86-114">You can place help content CAB files for different modules in the same location.</span></span>

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a><span data-ttu-id="7cb86-115">步骤2：将 HelpInfoURI 键添加到模块清单</span><span class="sxs-lookup"><span data-stu-id="7cb86-115">Step 2: Add a HelpInfoURI key to your module manifest</span></span>

<span data-ttu-id="7cb86-116">将 **HelpInfoURI** 键添加到模块清单中。</span><span class="sxs-lookup"><span data-stu-id="7cb86-116">Add a **HelpInfoURI** key to your module manifest.</span></span> <span data-ttu-id="7cb86-117">键的值是模块的 HelpInfo XML 信息文件位置 (URI) 的统一资源标识符。</span><span class="sxs-lookup"><span data-stu-id="7cb86-117">The value of the key is the Uniform Resource Identifier (URI) of the location of the HelpInfo XML information file for your module.</span></span> <span data-ttu-id="7cb86-118">为安全，该地址必须以 "http" 或 "https" 开头。</span><span class="sxs-lookup"><span data-stu-id="7cb86-118">For security, the address must begin with "http" or "https".</span></span> <span data-ttu-id="7cb86-119">URI 应指定 internet 位置，但不得包含 HelpInfo XML 文件名。</span><span class="sxs-lookup"><span data-stu-id="7cb86-119">The URI should specify an internet location, but must not include the HelpInfo XML filename.</span></span>

<span data-ttu-id="7cb86-120">例如：</span><span class="sxs-lookup"><span data-stu-id="7cb86-120">For example:</span></span>

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'https://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a><span data-ttu-id="7cb86-121">步骤3：创建 HelpInfo XML 文件</span><span class="sxs-lookup"><span data-stu-id="7cb86-121">Step 3: Create a HelpInfo XML file</span></span>

<span data-ttu-id="7cb86-122">HelpInfo XML 信息文件包含帮助文件的 internet 位置的 URI，以及每个受支持的 UI 区域性中的模块的最新帮助文件的版本号。</span><span class="sxs-lookup"><span data-stu-id="7cb86-122">The HelpInfo XML information file contains the URI of the internet location of your help files and the version numbers of the newest help files for your module in each supported UI culture.</span></span> <span data-ttu-id="7cb86-123">每个 Windows PowerShell 模块都有一个 HelpInfo XML 文件。</span><span class="sxs-lookup"><span data-stu-id="7cb86-123">Every Windows PowerShell module has one HelpInfo XML file.</span></span> <span data-ttu-id="7cb86-124">更新帮助文件时，请编辑或替换 HelpInfo XML 文件;不添加另一个。</span><span class="sxs-lookup"><span data-stu-id="7cb86-124">When you update your help files, you edit or replace the HelpInfo XML file; you do not add another one.</span></span> <span data-ttu-id="7cb86-125">有关详细信息，请参阅 [如何创建 HELPINFO XML 文件](./how-to-create-a-helpinfo-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="7cb86-125">For more information, see [How to Create a HelpInfo XML File](./how-to-create-a-helpinfo-xml-file.md).</span></span>

### <a name="step-4-create-cab-files"></a><span data-ttu-id="7cb86-126">步骤4：创建 CAB 文件</span><span class="sxs-lookup"><span data-stu-id="7cb86-126">Step 4: Create CAB files</span></span>

<span data-ttu-id="7cb86-127">使用创建 cabinet () 文件的工具（ `.cab` 如 `MakeCab.exe` ）创建包含模块帮助文件的 cab 文件。</span><span class="sxs-lookup"><span data-stu-id="7cb86-127">Use a tool that creates cabinet (`.cab`) files, such as `MakeCab.exe`, to create a CAB file that contains the help files for your module.</span></span> <span data-ttu-id="7cb86-128">为每个支持的 UI 区域性中的帮助文件创建单独的 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="7cb86-128">Create a separate CAB file for the help files in each supported UI culture.</span></span> <span data-ttu-id="7cb86-129">有关详细信息，请参阅 [如何准备可更新的帮助 CAB 文件](./how-to-prepare-updatable-help-cab-files.md)。</span><span class="sxs-lookup"><span data-stu-id="7cb86-129">For more information, see [How to Prepare Updatable Help CAB Files](./how-to-prepare-updatable-help-cab-files.md).</span></span>

### <a name="step-5-upload-your-files"></a><span data-ttu-id="7cb86-130">步骤5：上传文件</span><span class="sxs-lookup"><span data-stu-id="7cb86-130">Step 5: Upload your files</span></span>

<span data-ttu-id="7cb86-131">若要发布新的或更新的帮助文件，请将 CAB 文件上传到 HelpInfo XML 文件中的 **HelpContentUri** 元素所指定的 internet 位置。</span><span class="sxs-lookup"><span data-stu-id="7cb86-131">To publish new or updated help files, upload the CAB files to the internet location that is specified by the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="7cb86-132">然后，将 HelpInfo XML 文件上传到由模块清单中的 **HelpInfoUri** 键的值指定的 internet 位置。</span><span class="sxs-lookup"><span data-stu-id="7cb86-132">Then, upload the HelpInfo XML file to the internet location that is specified by the value of the **HelpInfoUri** key in the module manifest.</span></span>
