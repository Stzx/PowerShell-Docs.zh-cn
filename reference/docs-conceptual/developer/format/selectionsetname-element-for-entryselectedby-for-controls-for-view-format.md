---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for Controls for View (Format)
description: SelectionSetName Element for EntrySelectedBy for Controls for View (Format)
ms.openlocfilehash: 3211b7cacd7e57770b48b03f4aade33da506f180
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664738"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="d4b5c-103">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="d4b5c-103">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="d4b5c-104">指定一组使用此控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-104">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="d4b5c-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="d4b5c-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (格式) CustomEntries 元素 CustomControl For view (format) CustomEntry 元素 For CustomEntries For view (Format 的控件的 EntrySelectedBy 元素 (CustomEntry for view) 格式的控件 (SelectionSetName 元素) ) </span><span class="sxs-lookup"><span data-stu-id="d4b5c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d4b5c-107">语法</span><span class="sxs-lookup"><span data-stu-id="d4b5c-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4b5c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d4b5c-108">Attributes and Elements</span></span>

<span data-ttu-id="d4b5c-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4b5c-110">特性</span><span class="sxs-lookup"><span data-stu-id="d4b5c-110">Attributes</span></span>

<span data-ttu-id="d4b5c-111">无</span><span class="sxs-lookup"><span data-stu-id="d4b5c-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d4b5c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d4b5c-112">Child Elements</span></span>

<span data-ttu-id="d4b5c-113">无。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d4b5c-114">父元素</span><span class="sxs-lookup"><span data-stu-id="d4b5c-114">Parent Elements</span></span>

|<span data-ttu-id="d4b5c-115">元素</span><span class="sxs-lookup"><span data-stu-id="d4b5c-115">Element</span></span>|<span data-ttu-id="d4b5c-116">描述</span><span class="sxs-lookup"><span data-stu-id="d4b5c-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d4b5c-117">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="d4b5c-117">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="d4b5c-118">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d4b5c-119">文本值</span><span class="sxs-lookup"><span data-stu-id="d4b5c-119">Text Value</span></span>

<span data-ttu-id="d4b5c-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4b5c-121">备注</span><span class="sxs-lookup"><span data-stu-id="d4b5c-121">Remarks</span></span>

<span data-ttu-id="d4b5c-122">每个控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="d4b5c-123">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="d4b5c-124">有关定义选择集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b5c-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4b5c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4b5c-125">See Also</span></span>

[<span data-ttu-id="d4b5c-126">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="d4b5c-126">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="d4b5c-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d4b5c-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
