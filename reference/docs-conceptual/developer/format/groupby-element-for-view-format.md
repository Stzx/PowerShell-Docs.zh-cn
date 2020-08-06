---
title: View (Format) 的 GroupBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2f9071a3ebbc7cc2ccb7721dd518e82723e9cc4e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781420"
---
# <a name="groupby-element-for-view-format"></a><span data-ttu-id="3862d-102">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-102">GroupBy Element for View (Format)</span></span>

<span data-ttu-id="3862d-103">定义如何显示新的对象组。</span><span class="sxs-lookup"><span data-stu-id="3862d-103">Defines how a new group of objects is displayed.</span></span> <span data-ttu-id="3862d-104">定义表、列表、宽或自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="3862d-104">This element is used when defining a table, list, wide, or custom control view.</span></span>

<span data-ttu-id="3862d-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式)  (的 GroupBy 元素) 格式</span><span class="sxs-lookup"><span data-stu-id="3862d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3862d-106">语法</span><span class="sxs-lookup"><span data-stu-id="3862d-106">Syntax</span></span>

```xml
<GroupBy>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  <Label>TextToDisplay</Label>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameOfControl</CustomControlName>
</GroupBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3862d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3862d-107">Attributes and Elements</span></span>

<span data-ttu-id="3862d-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3862d-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3862d-109">特性</span><span class="sxs-lookup"><span data-stu-id="3862d-109">Attributes</span></span>

<span data-ttu-id="3862d-110">无。</span><span class="sxs-lookup"><span data-stu-id="3862d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3862d-111">子元素</span><span class="sxs-lookup"><span data-stu-id="3862d-111">Child Elements</span></span>

|<span data-ttu-id="3862d-112">元素</span><span class="sxs-lookup"><span data-stu-id="3862d-112">Element</span></span>|<span data-ttu-id="3862d-113">说明</span><span class="sxs-lookup"><span data-stu-id="3862d-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3862d-114">CustomControl Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-114">CustomControl Element for GroupBy (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="3862d-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3862d-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3862d-116">定义显示新组的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="3862d-116">Defines the custom control that display new groups.</span></span>|
|[<span data-ttu-id="3862d-117">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-117">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)|<span data-ttu-id="3862d-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3862d-118">Optional element.</span></span><br /><br /> <span data-ttu-id="3862d-119">指定用于显示新组的控件的名称。</span><span class="sxs-lookup"><span data-stu-id="3862d-119">Specifies the name of a control that is used to display the new group.</span></span>|
|[<span data-ttu-id="3862d-120">Label Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-120">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)|<span data-ttu-id="3862d-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3862d-121">Optional element.</span></span><br /><br /> <span data-ttu-id="3862d-122">指定在遇到新组时显示的标签。</span><span class="sxs-lookup"><span data-stu-id="3862d-122">Specifies a label that is displayed when a new group is encountered.</span></span>|
|[<span data-ttu-id="3862d-123">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-123">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)|<span data-ttu-id="3862d-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3862d-124">Optional element.</span></span><br /><br /> <span data-ttu-id="3862d-125">指定 .NET 属性，在新组的值发生更改时启动新组。</span><span class="sxs-lookup"><span data-stu-id="3862d-125">Specifies the .NET property the starts a new group whenever its value changes.</span></span>|
|[<span data-ttu-id="3862d-126">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-126">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)|<span data-ttu-id="3862d-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3862d-127">Optional element.</span></span><br /><br /> <span data-ttu-id="3862d-128">指定在新组的值发生更改时启动新组的脚本。</span><span class="sxs-lookup"><span data-stu-id="3862d-128">Specifies the script that starts a new group whenever its value changes.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3862d-129">父元素</span><span class="sxs-lookup"><span data-stu-id="3862d-129">Parent Elements</span></span>

|<span data-ttu-id="3862d-130">元素</span><span class="sxs-lookup"><span data-stu-id="3862d-130">Element</span></span>|<span data-ttu-id="3862d-131">说明</span><span class="sxs-lookup"><span data-stu-id="3862d-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3862d-132">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-132">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="3862d-133">定义一个视图，该视图显示一个或多个 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="3862d-133">Defines a view that displays one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3862d-134">备注</span><span class="sxs-lookup"><span data-stu-id="3862d-134">Remarks</span></span>

<span data-ttu-id="3862d-135">定义如何显示新的对象组时，您必须指定将启动新组的属性或脚本。但是，不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="3862d-135">When defining how a new group of objects is displayed, you must specify the property or script that will start the new group; however, you cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="3862d-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3862d-136">See Also</span></span>

[<span data-ttu-id="3862d-137">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-137">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

[<span data-ttu-id="3862d-138">Label Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-138">Label Element for GroupBy (Format)</span></span>](./label-element-for-groupby-format.md)

[<span data-ttu-id="3862d-139">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-139">PropertyName Element for GroupBy (Format)</span></span>](./propertyname-element-for-groupby-format.md)

[<span data-ttu-id="3862d-140">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-140">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="3862d-141">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="3862d-141">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="3862d-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3862d-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
