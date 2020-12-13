---
ms.date: 09/12/2016
ms.topic: reference
title: 如何命名 HelpInfo XML 文件
description: 如何命名 HelpInfo XML 文件
ms.openlocfilehash: 55bc2ef9530fc457e4d9ddf18e79e7226c991663
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659041"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="6eb67-103">如何命名 HelpInfo XML 文件</span><span class="sxs-lookup"><span data-stu-id="6eb67-103">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="6eb67-104">本主题介绍可更新帮助信息文件（通常称为 HelpInfo XML 文件）所需的名称格式。</span><span class="sxs-lookup"><span data-stu-id="6eb67-104">This topic explains the required name format for the Updatable Help Information files, commonly known as HelpInfo XML files.</span></span>

## <a name="how-to-name-a-helpinfo-xml-file"></a><span data-ttu-id="6eb67-105">如何命名 HelpInfo XML 文件</span><span class="sxs-lookup"><span data-stu-id="6eb67-105">How to Name a HelpInfo XML File</span></span>

<span data-ttu-id="6eb67-106">HelpInfo XML 文件必须具有以下格式的名称。</span><span class="sxs-lookup"><span data-stu-id="6eb67-106">A HelpInfo XML file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

<span data-ttu-id="6eb67-107">名称的元素如下所示。</span><span class="sxs-lookup"><span data-stu-id="6eb67-107">The elements of the name are as follows.</span></span>

- <span data-ttu-id="6eb67-108">`<ModuleName>`- [Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 返回的 **ModuleInfo** 对象的 **Name** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="6eb67-108">`<ModuleName>` - The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

- <span data-ttu-id="6eb67-109">`<ModuleGUID>` -模块清单中的 **GUID** 键的值。</span><span class="sxs-lookup"><span data-stu-id="6eb67-109">`<ModuleGUID>` - The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="6eb67-110">例如，如果模块名称为 "TestModule"，并且模块 GUID 为 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9，则该模块的 HelpInfo XML 文件的名称将为：</span><span class="sxs-lookup"><span data-stu-id="6eb67-110">For example, if the module name is "TestModule" and the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, the name of the HelpInfo XML file for the module would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
