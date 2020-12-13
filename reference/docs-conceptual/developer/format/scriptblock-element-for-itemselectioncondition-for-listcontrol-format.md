---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ItemSelectionCondition for ListControl (Format)
description: ScriptBlock Element for ItemSelectionCondition for ListControl (Format)
ms.openlocfilehash: 1e518f898e0e1e62ca64f9897b1323cc6dd89ae9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665049"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="360dd-103">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="360dd-103">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="360dd-104">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="360dd-104">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="360dd-105">将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。</span><span class="sxs-lookup"><span data-stu-id="360dd-105">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="360dd-106">定义列表视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="360dd-106">This element is used when defining a list view.</span></span>

<span data-ttu-id="360dd-107">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素，适用于 ListControl (格式) ListEntry for ListEntries 的 ListControl 元素 (ListItems 的 ListEntry 的 ListControl 元素) ListItems 的 ItemSelectionCondition (格式) ListControl (格式) ItemSelectionCondition 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="360dd-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="360dd-108">语法</span><span class="sxs-lookup"><span data-stu-id="360dd-108">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="360dd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="360dd-109">Attributes and Elements</span></span>

<span data-ttu-id="360dd-110">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="360dd-110">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="360dd-111">特性</span><span class="sxs-lookup"><span data-stu-id="360dd-111">Attributes</span></span>

<span data-ttu-id="360dd-112">无。</span><span class="sxs-lookup"><span data-stu-id="360dd-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="360dd-113">子元素</span><span class="sxs-lookup"><span data-stu-id="360dd-113">Child Elements</span></span>

<span data-ttu-id="360dd-114">无。</span><span class="sxs-lookup"><span data-stu-id="360dd-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="360dd-115">父元素</span><span class="sxs-lookup"><span data-stu-id="360dd-115">Parent Elements</span></span>

|<span data-ttu-id="360dd-116">元素</span><span class="sxs-lookup"><span data-stu-id="360dd-116">Element</span></span>|<span data-ttu-id="360dd-117">描述</span><span class="sxs-lookup"><span data-stu-id="360dd-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="360dd-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="360dd-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="360dd-119">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="360dd-119">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="360dd-120">文本值</span><span class="sxs-lookup"><span data-stu-id="360dd-120">Text Value</span></span>

<span data-ttu-id="360dd-121">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="360dd-121">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="360dd-122">备注</span><span class="sxs-lookup"><span data-stu-id="360dd-122">Remarks</span></span>

<span data-ttu-id="360dd-123">如果使用此元素，则在 `PropertyName` 定义选择条件时，不能指定元素。</span><span class="sxs-lookup"><span data-stu-id="360dd-123">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="360dd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="360dd-124">See Also</span></span>

[<span data-ttu-id="360dd-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="360dd-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
