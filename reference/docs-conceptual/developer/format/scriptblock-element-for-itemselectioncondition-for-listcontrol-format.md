---
title: ListControl 的 ItemSelectionCondition 的 ScriptBlock 元素 (格式) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 38dc952bfadd6aed24bae8cbef05adcd22e61dd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787625"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-listcontrol-format"></a><span data-ttu-id="4f148-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4f148-102">ScriptBlock Element for ItemSelectionCondition for ListControl (Format)</span></span>

<span data-ttu-id="4f148-103">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="4f148-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="4f148-104">将此脚本的计算结果为时 `true` ，将满足条件，并使用列表项。</span><span class="sxs-lookup"><span data-stu-id="4f148-104">When this script is evaluated to `true`, the condition is met, and the list item is used.</span></span> <span data-ttu-id="4f148-105">定义列表视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="4f148-105">This element is used when defining a list view.</span></span>

<span data-ttu-id="4f148-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素，适用于 ListControl (格式) ListEntry for ListEntries 的 ListControl 元素 (ListItems 的 ListEntry 的 ListControl 元素) ListItems 的 ItemSelectionCondition (格式) ListControl (格式) ItemSelectionCondition 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="4f148-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for List Control (Format) ItemSelectionCondition Element for ListItem for ListControl (Format) ScriptBlock Element for ItemSelectionCondition for ListControl  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f148-107">语法</span><span class="sxs-lookup"><span data-stu-id="4f148-107">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f148-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4f148-108">Attributes and Elements</span></span>

<span data-ttu-id="4f148-109">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="4f148-109">The following sections describe attributes, child elements, and the parent elements of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f148-110">特性</span><span class="sxs-lookup"><span data-stu-id="4f148-110">Attributes</span></span>

<span data-ttu-id="4f148-111">无。</span><span class="sxs-lookup"><span data-stu-id="4f148-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f148-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4f148-112">Child Elements</span></span>

<span data-ttu-id="4f148-113">无。</span><span class="sxs-lookup"><span data-stu-id="4f148-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4f148-114">父元素</span><span class="sxs-lookup"><span data-stu-id="4f148-114">Parent Elements</span></span>

|<span data-ttu-id="4f148-115">元素</span><span class="sxs-lookup"><span data-stu-id="4f148-115">Element</span></span>|<span data-ttu-id="4f148-116">说明</span><span class="sxs-lookup"><span data-stu-id="4f148-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f148-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="4f148-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="4f148-118">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="4f148-118">Defines the condition that must exist for this list item to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4f148-119">文本值</span><span class="sxs-lookup"><span data-stu-id="4f148-119">Text Value</span></span>

<span data-ttu-id="4f148-120">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="4f148-120">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f148-121">备注</span><span class="sxs-lookup"><span data-stu-id="4f148-121">Remarks</span></span>

<span data-ttu-id="4f148-122">如果使用此元素，则在 `PropertyName` 定义选择条件时，不能指定元素。</span><span class="sxs-lookup"><span data-stu-id="4f148-122">If this element is used, you cannot specify the `PropertyName` element when defining the selection condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f148-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f148-123">See Also</span></span>

[<span data-ttu-id="4f148-124">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4f148-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
