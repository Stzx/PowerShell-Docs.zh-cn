---
ms.date: 09/13/2016
ms.topic: reference
title: Configuration Element (Format)
description: Configuration Element (Format)
ms.openlocfilehash: 0524736d40dd7a7acb0b6fb61d1438b75672c240
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655687"
---
# <a name="configuration-element-format"></a><span data-ttu-id="76e2b-103">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-103">Configuration Element (Format)</span></span>

<span data-ttu-id="76e2b-104">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="76e2b-104">Represents the top-level element of a formatting file.</span></span>

<span data-ttu-id="76e2b-105">配置元素</span><span class="sxs-lookup"><span data-stu-id="76e2b-105">Configuration Element</span></span>

## <a name="syntax"></a><span data-ttu-id="76e2b-106">语法</span><span class="sxs-lookup"><span data-stu-id="76e2b-106">Syntax</span></span>

```xml
<Configuration>
  <DefaultSettings>...</DefaultSettings>
  <SelectionSets>...</SelectionSets>
  <Controls>...</Controls>
  <ViewDefinitions>...</ViewDefinitions>
</Configuration>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="76e2b-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="76e2b-107">Attributes and Elements</span></span>

<span data-ttu-id="76e2b-108">以下各节描述了元素的属性、子元素和父元素 `Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="76e2b-108">The following sections describe the attributes, child elements, and the parent element of the `Configuration` element.</span></span> <span data-ttu-id="76e2b-109">此元素必须是每个格式化文件的根元素，并且此元素必须包含至少一个子元素。</span><span class="sxs-lookup"><span data-stu-id="76e2b-109">This element must be the root element for each formatting file, and this element must contain at least one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="76e2b-110">特性</span><span class="sxs-lookup"><span data-stu-id="76e2b-110">Attributes</span></span>

<span data-ttu-id="76e2b-111">无。</span><span class="sxs-lookup"><span data-stu-id="76e2b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="76e2b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="76e2b-112">Child Elements</span></span>

|<span data-ttu-id="76e2b-113">元素</span><span class="sxs-lookup"><span data-stu-id="76e2b-113">Element</span></span>|<span data-ttu-id="76e2b-114">描述</span><span class="sxs-lookup"><span data-stu-id="76e2b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="76e2b-115">Controls Element for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-115">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="76e2b-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="76e2b-116">Optional element.</span></span><br /><br /> <span data-ttu-id="76e2b-117">定义可供格式设置文件的所有视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="76e2b-117">Defines the common controls that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="76e2b-118">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-118">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="76e2b-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="76e2b-119">Optional element.</span></span><br /><br /> <span data-ttu-id="76e2b-120">定义适用于格式设置文件的所有视图的常见设置。</span><span class="sxs-lookup"><span data-stu-id="76e2b-120">Defines common settings that apply to all the views of the formatting file.</span></span>|
|[<span data-ttu-id="76e2b-121">SelectionSets 元素格式</span><span class="sxs-lookup"><span data-stu-id="76e2b-121">SelectionSets Element Format</span></span>](./selectionsets-element-format.md)|<span data-ttu-id="76e2b-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="76e2b-122">Optional element.</span></span><br /><br /> <span data-ttu-id="76e2b-123">定义可供格式设置文件的所有视图使用的常用 .NET 对象集。</span><span class="sxs-lookup"><span data-stu-id="76e2b-123">Defines the common sets of .NET objects that can be used by all views of the formatting file.</span></span>|
|[<span data-ttu-id="76e2b-124">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-124">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="76e2b-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="76e2b-125">Optional element.</span></span><br /><br /> <span data-ttu-id="76e2b-126">定义用于显示对象的视图。</span><span class="sxs-lookup"><span data-stu-id="76e2b-126">Defines the views used to display objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="76e2b-127">父元素</span><span class="sxs-lookup"><span data-stu-id="76e2b-127">Parent Elements</span></span>

<span data-ttu-id="76e2b-128">无。</span><span class="sxs-lookup"><span data-stu-id="76e2b-128">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="76e2b-129">备注</span><span class="sxs-lookup"><span data-stu-id="76e2b-129">Remarks</span></span>

<span data-ttu-id="76e2b-130">格式化文件定义对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="76e2b-130">Formatting files define how objects are displayed.</span></span> <span data-ttu-id="76e2b-131">在大多数情况下，此根元素包含一个 [ViewDefinitions](./viewdefinitions-element-format.md) 元素，该元素定义格式设置文件的表、列表和宽视图。</span><span class="sxs-lookup"><span data-stu-id="76e2b-131">In most cases, this root element contains a [ViewDefinitions](./viewdefinitions-element-format.md) element that defines the table, list, and wide views of the formatting file.</span></span> <span data-ttu-id="76e2b-132">除了视图定义以外，格式设置文件还可以定义这些视图可以使用的常用选择集、设置和控件。</span><span class="sxs-lookup"><span data-stu-id="76e2b-132">In addition to the view definitions, the formatting file can define common selection sets, settings, and controls that those views can use.</span></span>

## <a name="see-also"></a><span data-ttu-id="76e2b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76e2b-133">See Also</span></span>

[<span data-ttu-id="76e2b-134">Controls Element for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-134">Controls Element for Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="76e2b-135">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-135">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="76e2b-136">SelectionSets Element (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-136">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="76e2b-137">ViewDefinitions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="76e2b-137">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="76e2b-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="76e2b-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
