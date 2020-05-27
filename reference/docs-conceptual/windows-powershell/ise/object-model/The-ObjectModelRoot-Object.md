---
ms.date: 08/25/2017
keywords: powershell,cmdlet
title: ObjectModelRoot 对象
ms.openlocfilehash: cd94e69de2e62f7ce9fac413e15458ae9986540e
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809563"
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="c96f2-103">ObjectModelRoot 对象</span><span class="sxs-lookup"><span data-stu-id="c96f2-103">The ObjectModelRoot Object</span></span>

<span data-ttu-id="c96f2-104">Windows PowerShell® 集成脚本环境 (ISE) 中的主体根对象（`$psISE` 对象）是 Microsoft.PowerShell.Host.ISE.ObjectModelRoot 类的实例。</span><span class="sxs-lookup"><span data-stu-id="c96f2-104">The `$psISE` object, which is the principal root object in Windows PowerShell® Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span> <span data-ttu-id="c96f2-105">本主题介绍 **ObjectModelRoot** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c96f2-105">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="c96f2-106">属性</span><span class="sxs-lookup"><span data-stu-id="c96f2-106">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="c96f2-107">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="c96f2-107">CurrentFile</span></span>

> <span data-ttu-id="c96f2-108">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="c96f2-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c96f2-109">只读属性，可获取与该主机对象相关联的当前具有焦点的文件。</span><span class="sxs-lookup"><span data-stu-id="c96f2-109">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="c96f2-110">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="c96f2-110">CurrentPowerShellTab</span></span>

> <span data-ttu-id="c96f2-111">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="c96f2-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c96f2-112">只读属性，可获取具有焦点的 PowerShell 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c96f2-112">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="c96f2-113">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="c96f2-113">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="c96f2-114">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="c96f2-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c96f2-115">只读属性，可获取位于编辑器底部水平工具窗格中、当前可见的 Windows PowerShell ISE 加载项工具。</span><span class="sxs-lookup"><span data-stu-id="c96f2-115">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="c96f2-116">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="c96f2-116">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="c96f2-117">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="c96f2-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c96f2-118">只读属性，可获取位于编辑器右侧竖直工具窗格中、当前可见的 Windows PowerShell ISE 加载项工具。</span><span class="sxs-lookup"><span data-stu-id="c96f2-118">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="c96f2-119">选项</span><span class="sxs-lookup"><span data-stu-id="c96f2-119">Options</span></span>

> <span data-ttu-id="c96f2-120">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="c96f2-120">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c96f2-121">只读属性，可获取可以更改 Windows PowerShell ISE 中设置的各种选项。</span><span class="sxs-lookup"><span data-stu-id="c96f2-121">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="c96f2-122">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="c96f2-122">PowerShellTabs</span></span>

> <span data-ttu-id="c96f2-123">在 Windows PowerShell ISE 2.0 和更高版本中受支持。</span><span class="sxs-lookup"><span data-stu-id="c96f2-123">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="c96f2-124">只读属性，可获取 Windows PowerShell ISE 中打开的 PowerShell 选项卡的集合。</span><span class="sxs-lookup"><span data-stu-id="c96f2-124">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="c96f2-125">默认情况下，此对象包含一个 PowerShell 选项卡。但是，可以将更多 PowerShell 选项卡添加到此对象中，方法是通过使用脚本或者使用 Windows PowerShell ISE 中的菜单。</span><span class="sxs-lookup"><span data-stu-id="c96f2-125">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="c96f2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c96f2-126">See Also</span></span>

- [<span data-ttu-id="c96f2-127">Windows PowerShell ISE 脚本对象模型的用途</span><span class="sxs-lookup"><span data-stu-id="c96f2-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="c96f2-128">ISE 对象模型层次结构</span><span class="sxs-lookup"><span data-stu-id="c96f2-128">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
