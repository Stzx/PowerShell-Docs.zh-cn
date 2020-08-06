---
title: 用于 ListControl (Format) 的 ItemSelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f5c388928668e03b96923130fb5849f637548f12
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783613"
---
# <a name="itemselectioncondition-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="d15b0-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d15b0-102">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="d15b0-103">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d15b0-103">Defines the condition that must exist for this list item to be used.</span></span>

<span data-ttu-id="d15b0-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntries for ListControl 的 ListItems 元素) ListEntry 的 ListControl 的 ListItems 元素 (ListControl) 格式 (ItemSelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="d15b0-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d15b0-105">语法</span><span class="sxs-lookup"><span data-stu-id="d15b0-105">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d15b0-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d15b0-106">Attributes and Elements</span></span>

<span data-ttu-id="d15b0-107">以下各节描述了元素的属性、子元素和父元素 `ItemSelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="d15b0-107">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d15b0-108">特性</span><span class="sxs-lookup"><span data-stu-id="d15b0-108">Attributes</span></span>

<span data-ttu-id="d15b0-109">无。</span><span class="sxs-lookup"><span data-stu-id="d15b0-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d15b0-110">子元素</span><span class="sxs-lookup"><span data-stu-id="d15b0-110">Child Elements</span></span>

|<span data-ttu-id="d15b0-111">元素</span><span class="sxs-lookup"><span data-stu-id="d15b0-111">Element</span></span>|<span data-ttu-id="d15b0-112">说明</span><span class="sxs-lookup"><span data-stu-id="d15b0-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d15b0-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d15b0-113">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="d15b0-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="d15b0-114">Optional element.</span></span><br /><br /> <span data-ttu-id="d15b0-115">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="d15b0-115">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d15b0-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d15b0-116">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)|<span data-ttu-id="d15b0-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="d15b0-117">Optional element.</span></span><br /><br /> <span data-ttu-id="d15b0-118">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="d15b0-118">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d15b0-119">父元素</span><span class="sxs-lookup"><span data-stu-id="d15b0-119">Parent Elements</span></span>

|<span data-ttu-id="d15b0-120">元素</span><span class="sxs-lookup"><span data-stu-id="d15b0-120">Element</span></span>|<span data-ttu-id="d15b0-121">说明</span><span class="sxs-lookup"><span data-stu-id="d15b0-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d15b0-122">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d15b0-122">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="d15b0-123">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="d15b0-123">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d15b0-124">备注</span><span class="sxs-lookup"><span data-stu-id="d15b0-124">Remarks</span></span>

<span data-ttu-id="d15b0-125">您可以为此条件指定一个属性名称或脚本，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="d15b0-125">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="d15b0-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d15b0-126">See Also</span></span>

[<span data-ttu-id="d15b0-127">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d15b0-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="d15b0-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d15b0-128">PropertyName Element for ItemSelectionCondition for ListControl (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="d15b0-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="d15b0-129">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-listcontrol-format.md)

[<span data-ttu-id="d15b0-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d15b0-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
