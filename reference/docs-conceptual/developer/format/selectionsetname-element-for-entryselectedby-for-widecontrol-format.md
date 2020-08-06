---
title: WideControl (Format) 的 EntrySelectedBy 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 546225b0619ebec83d04a7e27bbc298ffef0a14d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785245"
---
# <a name="selectionsetname-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="6035d-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6035d-102">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="6035d-103">为定义指定一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="6035d-103">Specifies a set of .NET objects for the definition.</span></span> <span data-ttu-id="6035d-104">当显示其中一个对象时，将使用该定义。</span><span class="sxs-lookup"><span data-stu-id="6035d-104">The definition is used whenever one of these objects is displayed.</span></span>

<span data-ttu-id="6035d-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (SelectionSetName) 格式</span><span class="sxs-lookup"><span data-stu-id="6035d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6035d-106">语法</span><span class="sxs-lookup"><span data-stu-id="6035d-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="6035d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6035d-107">Attributes and Elements</span></span>

<span data-ttu-id="6035d-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="6035d-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6035d-109">特性</span><span class="sxs-lookup"><span data-stu-id="6035d-109">Attributes</span></span>

<span data-ttu-id="6035d-110">无。</span><span class="sxs-lookup"><span data-stu-id="6035d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6035d-111">子元素</span><span class="sxs-lookup"><span data-stu-id="6035d-111">Child Elements</span></span>

<span data-ttu-id="6035d-112">无。</span><span class="sxs-lookup"><span data-stu-id="6035d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6035d-113">父元素</span><span class="sxs-lookup"><span data-stu-id="6035d-113">Parent Elements</span></span>

|<span data-ttu-id="6035d-114">元素</span><span class="sxs-lookup"><span data-stu-id="6035d-114">Element</span></span>|<span data-ttu-id="6035d-115">描述</span><span class="sxs-lookup"><span data-stu-id="6035d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6035d-116">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6035d-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="6035d-117">定义使用此宽项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="6035d-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6035d-118">文本值</span><span class="sxs-lookup"><span data-stu-id="6035d-118">Text Value</span></span>

<span data-ttu-id="6035d-119">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="6035d-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="6035d-120">备注</span><span class="sxs-lookup"><span data-stu-id="6035d-120">Remarks</span></span>

<span data-ttu-id="6035d-121">每个定义必须指定一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="6035d-121">Each definition must specify one type name, selection set, or selection condition.</span></span>

<span data-ttu-id="6035d-122">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="6035d-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="6035d-123">例如，您可能希望为同一组对象创建表视图和列表视图。</span><span class="sxs-lookup"><span data-stu-id="6035d-123">For example, you might want to create a table view and a list view for the same set of objects.</span></span> <span data-ttu-id="6035d-124">有关定义选择集的详细信息，请参阅为[视图定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="6035d-124">For more information about defining selection sets, see [Defining Sets of Objects for a View](./defining-selection-sets.md).</span></span>

<span data-ttu-id="6035d-125">有关大视图的其他组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="6035d-125">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6035d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6035d-126">See Also</span></span>

[<span data-ttu-id="6035d-127">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="6035d-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="6035d-128">定义选项集</span><span class="sxs-lookup"><span data-stu-id="6035d-128">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="6035d-129">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="6035d-129">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="6035d-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="6035d-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
