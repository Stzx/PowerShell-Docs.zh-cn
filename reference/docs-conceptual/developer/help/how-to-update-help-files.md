---
ms.date: 09/12/2016
ms.topic: reference
title: 如何更新帮助文件
description: 如何更新帮助文件
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649583"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="57af1-103">如何更新帮助文件</span><span class="sxs-lookup"><span data-stu-id="57af1-103">How to Update Help Files</span></span>

<span data-ttu-id="57af1-104">本主题说明如何为支持可更新帮助的模块更新帮助文件。</span><span class="sxs-lookup"><span data-stu-id="57af1-104">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="57af1-105">正在更新帮助文件</span><span class="sxs-lookup"><span data-stu-id="57af1-105">Updating Help Files</span></span>

<span data-ttu-id="57af1-106">更新帮助文件的原因有很多，例如，纠正错误、阐明概念、回答经常询问的问题、添加新文件，或者添加更好的更好的示例。</span><span class="sxs-lookup"><span data-stu-id="57af1-106">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="57af1-107">更新帮助文件：</span><span class="sxs-lookup"><span data-stu-id="57af1-107">To update a help file:</span></span>

1. <span data-ttu-id="57af1-108">更改文件。</span><span class="sxs-lookup"><span data-stu-id="57af1-108">Change the files.</span></span>
1. <span data-ttu-id="57af1-109">将文件转换为其他 UI 区域性。</span><span class="sxs-lookup"><span data-stu-id="57af1-109">Translate the files into other UI cultures.</span></span>
1. <span data-ttu-id="57af1-110">对于每个 UI 区域性中的模块，收集所有帮助文件 (新的、更改和未更改的) 。</span><span class="sxs-lookup"><span data-stu-id="57af1-110">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>
1. <span data-ttu-id="57af1-111">对照 XML 架构验证文件。</span><span class="sxs-lookup"><span data-stu-id="57af1-111">Validate the files against the XML schema.</span></span>
1. <span data-ttu-id="57af1-112">重新生成每个 UI 区域性的 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="57af1-112">Rebuild the CAB files for each UI culture.</span></span>
1. <span data-ttu-id="57af1-113">在 HelpInfo XML 文件中，为每个 UI 区域性递增 CAB 文件的版本号。</span><span class="sxs-lookup"><span data-stu-id="57af1-113">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>
1. <span data-ttu-id="57af1-114">将新的 CAB 文件上传到 HelpInfo XML 文件中的 **HelpContentUri** 元素的值指定的位置。</span><span class="sxs-lookup"><span data-stu-id="57af1-114">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="57af1-115">将较旧的 CAB 文件替换为新的 CAB 文件。</span><span class="sxs-lookup"><span data-stu-id="57af1-115">Replace the older CAB files with the new CAB files.</span></span>
1. <span data-ttu-id="57af1-116">将更新后的 HelpInfo XML 文件上传到模块清单中的 **HelpInfoUri** 键指定的位置。</span><span class="sxs-lookup"><span data-stu-id="57af1-116">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="57af1-117">用新文件替换旧的 HelpInfo XML 文件。</span><span class="sxs-lookup"><span data-stu-id="57af1-117">Replace the older HelpInfo XML file with the new file.</span></span>
