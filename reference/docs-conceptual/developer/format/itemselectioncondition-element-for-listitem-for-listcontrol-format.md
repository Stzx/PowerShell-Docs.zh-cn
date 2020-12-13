---
ms.date: 09/13/2016
ms.topic: reference
title: ItemSelectionCondition Element for ListItem for ListControl (Format)
description: ItemSelectionCondition Element for ListItem for ListControl (Format)
ms.openlocfilehash: 13d925da10c2386123983d52b109c03a0c3c63ab
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667804"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="aadc3-103">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aadc3-103">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="aadc3-104">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="aadc3-104">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="aadc3-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntries for ListControl 的 ListItems 元素) ListEntry 的 ListControl 的 ListItems 元素 (ListControl) 格式 (ItemSelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="aadc3-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aadc3-106">语法</span><span class="sxs-lookup"><span data-stu-id="aadc3-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aadc3-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aadc3-107">Attributes and Elements</span></span>

<span data-ttu-id="aadc3-108">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="aadc3-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aadc3-109">特性</span><span class="sxs-lookup"><span data-stu-id="aadc3-109">Attributes</span></span>

<span data-ttu-id="aadc3-110">无。</span><span class="sxs-lookup"><span data-stu-id="aadc3-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aadc3-111">子元素</span><span class="sxs-lookup"><span data-stu-id="aadc3-111">Child Elements</span></span>

|<span data-ttu-id="aadc3-112">元素</span><span class="sxs-lookup"><span data-stu-id="aadc3-112">Element</span></span>|<span data-ttu-id="aadc3-113">描述</span><span class="sxs-lookup"><span data-stu-id="aadc3-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aadc3-114">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aadc3-114">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="aadc3-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="aadc3-115">Optional element.</span></span><br /><br /> <span data-ttu-id="aadc3-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="aadc3-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="aadc3-117">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aadc3-117">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="aadc3-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="aadc3-118">Optional element.</span></span><br /><br /> <span data-ttu-id="aadc3-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="aadc3-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aadc3-120">父元素</span><span class="sxs-lookup"><span data-stu-id="aadc3-120">Parent Elements</span></span>

|<span data-ttu-id="aadc3-121">元素</span><span class="sxs-lookup"><span data-stu-id="aadc3-121">Element</span></span>|<span data-ttu-id="aadc3-122">描述</span><span class="sxs-lookup"><span data-stu-id="aadc3-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aadc3-123">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aadc3-123">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="aadc3-124">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="aadc3-124">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aadc3-125">备注</span><span class="sxs-lookup"><span data-stu-id="aadc3-125">Remarks</span></span>

<span data-ttu-id="aadc3-126">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="aadc3-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="aadc3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aadc3-127">See Also</span></span>

[<span data-ttu-id="aadc3-128">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aadc3-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="aadc3-129">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aadc3-129">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="aadc3-130">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aadc3-130">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="aadc3-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="aadc3-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
