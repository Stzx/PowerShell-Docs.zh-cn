---
title: GroupBy (Format) 的 EntrySelectedBy 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 362f7844c09a52494387a62e329adfb309767427
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785279"
---
# <a name="selectionsetname-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="58520-102">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="58520-102">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="58520-103">为列表条目指定一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="58520-103">Specifies a set of .NET objects for the list entry.</span></span> <span data-ttu-id="58520-104">对于可为条目指定的选项集数没有限制。</span><span class="sxs-lookup"><span data-stu-id="58520-104">There is no limit to the number of selection sets that can be specified for an entry.</span></span> <span data-ttu-id="58520-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="58520-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="58520-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (格式) </span><span class="sxs-lookup"><span data-stu-id="58520-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="58520-107">语法</span><span class="sxs-lookup"><span data-stu-id="58520-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58520-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="58520-108">Attributes and Elements</span></span>

<span data-ttu-id="58520-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="58520-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="58520-110">特性</span><span class="sxs-lookup"><span data-stu-id="58520-110">Attributes</span></span>

<span data-ttu-id="58520-111">无。</span><span class="sxs-lookup"><span data-stu-id="58520-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="58520-112">子元素</span><span class="sxs-lookup"><span data-stu-id="58520-112">Child Elements</span></span>

<span data-ttu-id="58520-113">无。</span><span class="sxs-lookup"><span data-stu-id="58520-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58520-114">父元素</span><span class="sxs-lookup"><span data-stu-id="58520-114">Parent Elements</span></span>

|<span data-ttu-id="58520-115">元素</span><span class="sxs-lookup"><span data-stu-id="58520-115">Element</span></span>|<span data-ttu-id="58520-116">描述</span><span class="sxs-lookup"><span data-stu-id="58520-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="58520-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="58520-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="58520-118">定义使用此自定义项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="58520-118">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="58520-119">文本值</span><span class="sxs-lookup"><span data-stu-id="58520-119">Text Value</span></span>

<span data-ttu-id="58520-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="58520-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="58520-121">备注</span><span class="sxs-lookup"><span data-stu-id="58520-121">Remarks</span></span>

<span data-ttu-id="58520-122">每个自定义控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="58520-122">Each custom control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="58520-123">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="58520-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="58520-124">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="58520-124">For example, you may want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="58520-125">有关定义选择集的详细信息，请参阅[定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="58520-125">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

<span data-ttu-id="58520-126">有关自定义控件视图组件的详细信息，请参阅[创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="58520-126">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58520-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58520-127">See Also</span></span>

[<span data-ttu-id="58520-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="58520-128">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="58520-129">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="58520-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="58520-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="58520-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
