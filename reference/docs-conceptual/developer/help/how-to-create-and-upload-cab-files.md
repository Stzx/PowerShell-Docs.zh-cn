---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建和上传 CAB 文件
description: 如何创建和上传 CAB 文件
ms.openlocfilehash: bdcf534f48cff27b403d82440ad4ec6a3212b67d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653885"
---
# <a name="how-to-create-and-upload-cab-files"></a><span data-ttu-id="2e136-103">如何创建和上传 CAB 文件</span><span class="sxs-lookup"><span data-stu-id="2e136-103">How to Create and Upload CAB Files</span></span>

<span data-ttu-id="2e136-104">本主题说明如何创建可更新的帮助 CAB 文件，并将其上载到可更新的帮助 cmdlet 可以找到它们的位置。</span><span class="sxs-lookup"><span data-stu-id="2e136-104">This topic explains how to create Updatable Help CAB files and upload them to the location where the Updatable Help cmdlets can find them.</span></span>

## <a name="how-to-create-and-upload-updatable-help-cab-files"></a><span data-ttu-id="2e136-105">如何创建和上传可更新的帮助 CAB 文件</span><span class="sxs-lookup"><span data-stu-id="2e136-105">How to Create and Upload Updatable Help CAB Files</span></span>

<span data-ttu-id="2e136-106">您可以使用 "可更新的帮助" 功能，为多语言和区域性中的模块提供新的或更新的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-106">You can use the Updatable Help feature to deliver new or updated help files for a module in multiple languages and cultures.</span></span> <span data-ttu-id="2e136-107">模块的可更新帮助包包括一个 HelpInfo XML 文件和一个或多个 cabinet (`.CAB`) 文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-107">An Updatable Help package for a module consists of one HelpInfo XML file and one or more cabinet (`.CAB`) files.</span></span> <span data-ttu-id="2e136-108">每个 CAB 文件都包含一个 UI 区域性中的模块的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-108">Each CAB file contains help files for the module in one UI culture.</span></span> <span data-ttu-id="2e136-109">使用以下过程来创建可更新帮助的 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-109">Use the following procedure to create CAB files for Updatable Help.</span></span>

1. <span data-ttu-id="2e136-110">按 UI 区域性组织模块的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-110">Organize the help files for the module by UI culture.</span></span> <span data-ttu-id="2e136-111">每个可更新帮助 CAB 文件都包含一个 UI 区域性中某个模块的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-111">Each Updatable Help CAB file contains the help files for one module in one UI culture.</span></span> <span data-ttu-id="2e136-112">可以为模块提供多个帮助 CAB 文件，每个文件都适用于不同的 UI 区域性。</span><span class="sxs-lookup"><span data-stu-id="2e136-112">You can deliver multiple help CAB files for the module, each for a different UI culture.</span></span>

1. <span data-ttu-id="2e136-113">验证 "帮助" 文件只包含可更新帮助所允许的文件类型，并根据帮助文件架构对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="2e136-113">Verify that help files include only the file types permitted for Updatable Help and validate them against a help file schema.</span></span> <span data-ttu-id="2e136-114">如果此 `Update-Help` cmdlet 遇到无效的文件或不是允许的类型，则它不会安装无效文件，也不会停止从 CAB 安装文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-114">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB.</span></span> <span data-ttu-id="2e136-115">有关允许的文件类型的列表，请参阅 [可更新的帮助 CAB 文件中允许的文件类型](./file-types-permitted-in-an-updatable-help-cab-file.md)。</span><span class="sxs-lookup"><span data-stu-id="2e136-115">For a list of permitted file types, see [File Types Permitted in an Updatable Help CAB File](./file-types-permitted-in-an-updatable-help-cab-file.md).</span></span>

1. <span data-ttu-id="2e136-116">对帮助文件进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="2e136-116">Digitally sign the help files.</span></span> <span data-ttu-id="2e136-117">不需要数字签名，但这是最佳做法。</span><span class="sxs-lookup"><span data-stu-id="2e136-117">Digital signatures are not required, but they are a best practice.</span></span>

1. <span data-ttu-id="2e136-118">包括 UI 区域性中的模块的所有帮助文件，而不仅是新的或已更改的文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-118">Include all of help files for the module in the UI culture, not only files that are new or have changed.</span></span> <span data-ttu-id="2e136-119">如果 CAB 文件不完整，则首次下载帮助文件或不下载每个更新的用户将不会获得所有的模块帮助文件。</span><span class="sxs-lookup"><span data-stu-id="2e136-119">If the CAB file is incomplete, users who download help files for the first time or do not download every update, will not have all of the module help files.</span></span>

1. <span data-ttu-id="2e136-120">使用创建 cabinet 文件的实用工具，如 `MakeCab.exe` 。</span><span class="sxs-lookup"><span data-stu-id="2e136-120">Use a utility that creates cabinet files, such as `MakeCab.exe`.</span></span> <span data-ttu-id="2e136-121">PowerShell 不包含用于创建 CAB 文件的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2e136-121">PowerShell does not include cmdlets that create CAB files.</span></span>

1. <span data-ttu-id="2e136-122">将 CAB 文件命名为。</span><span class="sxs-lookup"><span data-stu-id="2e136-122">Name the CAB files.</span></span> <span data-ttu-id="2e136-123">有关详细信息，请参阅 [如何命名可更新的帮助 CAB 文件](./how-to-name-an-updatable-help-cab-file.md)。</span><span class="sxs-lookup"><span data-stu-id="2e136-123">For more information, see [How to Name an Updatable Help CAB File](./how-to-name-an-updatable-help-cab-file.md).</span></span>

1. <span data-ttu-id="2e136-124">将模块的 CAB 文件上传到模块的 HelpInfo XML 文件中的 **HelpContentUri** 元素指定的位置。</span><span class="sxs-lookup"><span data-stu-id="2e136-124">Upload the CAB files for the module to the location that is specified by the **HelpContentUri** element in the HelpInfo XML file for the module.</span></span> <span data-ttu-id="2e136-125">然后，将 HelpInfo XML 文件上传到模块清单的 **HelpInfoUri** 键指定的位置。</span><span class="sxs-lookup"><span data-stu-id="2e136-125">Then upload the HelpInfo XML file to the location that is specified by the **HelpInfoUri** key of the module manifest.</span></span> <span data-ttu-id="2e136-126">**HelpContentUri** 和 **HelpInfoUri** 可以指向相同的位置。</span><span class="sxs-lookup"><span data-stu-id="2e136-126">The **HelpContentUri** and **HelpInfoUri** can point to the same location.</span></span>

> [!CAUTION]
> <span data-ttu-id="2e136-127">**HelpInfoUri** 键和 **HelpContentUri** 元素的值必须以 `http` 或开头 `https` 。</span><span class="sxs-lookup"><span data-stu-id="2e136-127">The value of the **HelpInfoUri** key and the **HelpContentUri** element must begin with `http` or `https`.</span></span> <span data-ttu-id="2e136-128">该值必须指示 Internet 位置，并且不能包含文件名。</span><span class="sxs-lookup"><span data-stu-id="2e136-128">The value must indicate an Internet location and it must not include a filename.</span></span>
