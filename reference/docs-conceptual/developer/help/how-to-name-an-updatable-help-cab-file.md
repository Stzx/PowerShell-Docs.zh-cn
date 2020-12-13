---
ms.date: 09/12/2016
ms.topic: reference
title: 如何命名可更新帮助 CAB 文件
description: 如何命名可更新帮助 CAB 文件
ms.openlocfilehash: 57ea188d07a382d1a986a49c9ae22c5919dafa8e
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658925"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="66bcc-103">如何命名可更新帮助 CAB 文件</span><span class="sxs-lookup"><span data-stu-id="66bcc-103">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="66bcc-104">本主题介绍了可更新的帮助 cabinet () 文件所需的名称格式 `.CAB` 。</span><span class="sxs-lookup"><span data-stu-id="66bcc-104">This topic explains the required name format for the Updatable Help cabinet (`.CAB`) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="66bcc-105">如何命名可更新帮助 CAB 文件</span><span class="sxs-lookup"><span data-stu-id="66bcc-105">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="66bcc-106">) 文件 (可更新的 cab `.CAB` 文件必须具有以下格式的名称。</span><span class="sxs-lookup"><span data-stu-id="66bcc-106">A Updatable cabinet (`.CAB`) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="66bcc-107">名称的元素如下所示。</span><span class="sxs-lookup"><span data-stu-id="66bcc-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="66bcc-108">`<ModuleName>`- [Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 返回的 **ModuleInfo** 对象的 **Name** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="66bcc-108">`<ModuleName>` -The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
- <span data-ttu-id="66bcc-109">`<ModuleGUID>` -模块清单中的 **GUID** 键的值。</span><span class="sxs-lookup"><span data-stu-id="66bcc-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>
- <span data-ttu-id="66bcc-110">`<UICulture>` -CAB 文件中的帮助文件的 UI 区域性。</span><span class="sxs-lookup"><span data-stu-id="66bcc-110">`<UICulture>` - The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="66bcc-111">此值必须与模块的 HelpInfo XML 文件中的一个 **UICulture** 元素的值匹配。</span><span class="sxs-lookup"><span data-stu-id="66bcc-111">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="66bcc-112">例如，如果模块名称为 "TestModule"，则模块 GUID 为 9cabb9ad-f2ac 4914-a46b-bfc1bebf07f9，而 UI 区域性为 "en-us"，则 CAB 文件的名称将为：</span><span class="sxs-lookup"><span data-stu-id="66bcc-112">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
