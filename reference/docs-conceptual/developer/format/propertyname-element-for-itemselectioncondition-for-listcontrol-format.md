---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for ItemSelectionCondition for ListControl (Format)
description: PropertyName Element for ItemSelectionCondition for ListControl (Format)
ms.openlocfilehash: c515efe70afdb1c1186c0a07fe1f52dc49ad57b9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665985"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="36b8f-103">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="36b8f-103">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="36b8f-104">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="36b8f-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="36b8f-105">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用视图。</span><span class="sxs-lookup"><span data-stu-id="36b8f-105">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="36b8f-106">定义列表视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="36b8f-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="36b8f-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListControl (格式) ListEntry 元素 (ListItems 的 ListEntry 的元素) ListControl 的 ListItems PropertyName 元素 ListControl (格式) ItemSelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="36b8f-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="36b8f-108">语法</span><span class="sxs-lookup"><span data-stu-id="36b8f-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="36b8f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="36b8f-109">Attributes and Elements</span></span>

<span data-ttu-id="36b8f-110">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="36b8f-110">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="36b8f-111">特性</span><span class="sxs-lookup"><span data-stu-id="36b8f-111">Attributes</span></span>

<span data-ttu-id="36b8f-112">无。</span><span class="sxs-lookup"><span data-stu-id="36b8f-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="36b8f-113">子元素</span><span class="sxs-lookup"><span data-stu-id="36b8f-113">Child Elements</span></span>

<span data-ttu-id="36b8f-114">无。</span><span class="sxs-lookup"><span data-stu-id="36b8f-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36b8f-115">父元素</span><span class="sxs-lookup"><span data-stu-id="36b8f-115">Parent Elements</span></span>

|<span data-ttu-id="36b8f-116">元素</span><span class="sxs-lookup"><span data-stu-id="36b8f-116">Element</span></span>|<span data-ttu-id="36b8f-117">描述</span><span class="sxs-lookup"><span data-stu-id="36b8f-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="36b8f-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="36b8f-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="36b8f-119">文本值</span><span class="sxs-lookup"><span data-stu-id="36b8f-119">Text Value</span></span>

<span data-ttu-id="36b8f-120">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="36b8f-120">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="36b8f-121">备注</span><span class="sxs-lookup"><span data-stu-id="36b8f-121">Remarks</span></span>

<span data-ttu-id="36b8f-122">如果使用此元素，则在定义选择条件时，不能指定 [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="36b8f-122">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="36b8f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36b8f-123">See Also</span></span>

[<span data-ttu-id="36b8f-124">ListIControl (格式的 ItemSelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="36b8f-124">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="36b8f-125">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="36b8f-125">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="36b8f-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="36b8f-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
