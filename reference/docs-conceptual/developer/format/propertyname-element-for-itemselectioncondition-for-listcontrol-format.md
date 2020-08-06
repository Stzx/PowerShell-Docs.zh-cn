---
title: 用于 ListControl (Format) 的 ItemSelectionCondition 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8bdbb05326f7ff5ccffa46215631a5c954080dc1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780859"
---
# <a name="propertyname-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="53636-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="53636-102">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="53636-103">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="53636-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="53636-104">如果该属性存在或其计算结果为 `true` ，则满足条件，并使用视图。</span><span class="sxs-lookup"><span data-stu-id="53636-104">When this property is present or when it evaluates to `true`, the condition is met, and the view is used.</span></span> <span data-ttu-id="53636-105">定义列表视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="53636-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="53636-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListControl (格式) ListEntry 元素 (ListItems 的 ListEntry 的元素) ListControl 的 ListItems PropertyName 元素 ListControl (格式) ItemSelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="53636-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControls PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="53636-107">语法</span><span class="sxs-lookup"><span data-stu-id="53636-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="53636-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="53636-108">Attributes and Elements</span></span>

<span data-ttu-id="53636-109">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="53636-109">The following sections describe attributes, child elements, and the parent elements of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="53636-110">特性</span><span class="sxs-lookup"><span data-stu-id="53636-110">Attributes</span></span>

<span data-ttu-id="53636-111">无。</span><span class="sxs-lookup"><span data-stu-id="53636-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="53636-112">子元素</span><span class="sxs-lookup"><span data-stu-id="53636-112">Child Elements</span></span>

<span data-ttu-id="53636-113">无。</span><span class="sxs-lookup"><span data-stu-id="53636-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="53636-114">父元素</span><span class="sxs-lookup"><span data-stu-id="53636-114">Parent Elements</span></span>

|<span data-ttu-id="53636-115">元素</span><span class="sxs-lookup"><span data-stu-id="53636-115">Element</span></span>|<span data-ttu-id="53636-116">说明</span><span class="sxs-lookup"><span data-stu-id="53636-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53636-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="53636-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)||

## <a name="text-value"></a><span data-ttu-id="53636-118">文本值</span><span class="sxs-lookup"><span data-stu-id="53636-118">Text Value</span></span>

<span data-ttu-id="53636-119">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="53636-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="53636-120">备注</span><span class="sxs-lookup"><span data-stu-id="53636-120">Remarks</span></span>

<span data-ttu-id="53636-121">如果使用此元素，则在定义选择条件时，不能指定[ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="53636-121">If this element is used, you cannot specify the [ScriptBlock](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md) element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="53636-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53636-122">See Also</span></span>

[<span data-ttu-id="53636-123">ListIControl (格式的 ItemSelectionCondition 的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="53636-123">ScriptBlock Element for ItemSelectionCondition for ListIControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="53636-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="53636-124">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="53636-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="53636-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
