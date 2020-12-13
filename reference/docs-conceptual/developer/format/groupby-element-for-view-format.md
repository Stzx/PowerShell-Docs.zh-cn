---
ms.date: 09/13/2016
ms.topic: reference
title: GroupBy Element for View (Format)
description: GroupBy Element for View (Format)
ms.openlocfilehash: d8ca93a3b2c1490928885579919c07f5eb274cd8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652105"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="856d5-103">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-103">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="856d5-104">定义如何显示新的对象组。</span><span class="sxs-lookup"><span data-stu-id="856d5-104">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="856d5-105">定义表、列表、宽或自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="856d5-105">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="856d5-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式)  (的 GroupBy 元素) 格式</span><span class="sxs-lookup"><span data-stu-id="856d5-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="856d5-107">语法</span><span class="sxs-lookup"><span data-stu-id="856d5-107">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="856d5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="856d5-108">Attributes and Elements</span></span>

<span data-ttu-id="856d5-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="856d5-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="856d5-110">特性</span><span class="sxs-lookup"><span data-stu-id="856d5-110">Attributes</span></span>

<span data-ttu-id="856d5-111">无。</span><span class="sxs-lookup"><span data-stu-id="856d5-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="856d5-112">子元素</span><span class="sxs-lookup"><span data-stu-id="856d5-112">Child Elements</span></span>

|<span data-ttu-id="856d5-113">元素</span><span class="sxs-lookup"><span data-stu-id="856d5-113">Element</span></span>|<span data-ttu-id="856d5-114">描述</span><span class="sxs-lookup"><span data-stu-id="856d5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="856d5-115">CustomControl Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-115">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="856d5-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="856d5-116">Optional element.</span></span><br /><br /> <span data-ttu-id="856d5-117">定义显示新组的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="856d5-117">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="856d5-118">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-118">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="856d5-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="856d5-119">Optional element.</span></span><br /><br /> <span data-ttu-id="856d5-120">指定用于显示新组的控件的名称。</span><span class="sxs-lookup"><span data-stu-id="856d5-120">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="856d5-121">Label Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-121">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="856d5-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="856d5-122">Optional element.</span></span><br /><br /> <span data-ttu-id="856d5-123">指定在遇到新组时显示的标签。</span><span class="sxs-lookup"><span data-stu-id="856d5-123">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="856d5-124">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-124">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="856d5-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="856d5-125">Optional element.</span></span><br /><br /> <span data-ttu-id="856d5-126">指定 .NET 属性，在新组的值发生更改时启动新组。</span><span class="sxs-lookup"><span data-stu-id="856d5-126">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="856d5-127">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="856d5-128">可选元素。</span><span class="sxs-lookup"><span data-stu-id="856d5-128">Optional element.</span></span><br /><br /> <span data-ttu-id="856d5-129">指定在新组的值发生更改时启动新组的脚本。</span><span class="sxs-lookup"><span data-stu-id="856d5-129">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="856d5-130">父元素</span><span class="sxs-lookup"><span data-stu-id="856d5-130">Parent Elements</span></span>

|<span data-ttu-id="856d5-131">元素</span><span class="sxs-lookup"><span data-stu-id="856d5-131">Element</span></span>|<span data-ttu-id="856d5-132">描述</span><span class="sxs-lookup"><span data-stu-id="856d5-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="856d5-133">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-133">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="856d5-134">定义一个视图，该视图显示一个或多个 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="856d5-134">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="856d5-135">备注</span><span class="sxs-lookup"><span data-stu-id="856d5-135">Remarks</span></span>

<span data-ttu-id="856d5-136">定义如何显示新的对象组时，您必须指定将启动新组的属性或脚本。但是，不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="856d5-136">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="856d5-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="856d5-137">See Also</span></span>

[<span data-ttu-id="856d5-138">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-138">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="856d5-139">Label Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-139">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="856d5-140">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-140">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="856d5-141">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-141">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="856d5-142">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="856d5-142">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="856d5-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="856d5-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
