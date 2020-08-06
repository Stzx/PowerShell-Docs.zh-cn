---
title: View (Format) 的控件的 EntrySelectedBy 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5c762a626fff746266919d1f7fcb991a8cdbcdf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787540"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="e240b-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e240b-102">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="e240b-103">指定一组使用此控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="e240b-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="e240b-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="e240b-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="e240b-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (格式) CustomEntries 元素 CustomControl For view (format) CustomEntry 元素 For CustomEntries For view (Format 的控件的 EntrySelectedBy 元素 (CustomEntry for view) 格式的控件 (SelectionSetName 元素) ) </span><span class="sxs-lookup"><span data-stu-id="e240b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e240b-106">语法</span><span class="sxs-lookup"><span data-stu-id="e240b-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e240b-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e240b-107">Attributes and Elements</span></span>

<span data-ttu-id="e240b-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="e240b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e240b-109">属性</span><span class="sxs-lookup"><span data-stu-id="e240b-109">Attributes</span></span>

<span data-ttu-id="e240b-110">None</span><span class="sxs-lookup"><span data-stu-id="e240b-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="e240b-111">子元素</span><span class="sxs-lookup"><span data-stu-id="e240b-111">Child Elements</span></span>

<span data-ttu-id="e240b-112">无。</span><span class="sxs-lookup"><span data-stu-id="e240b-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e240b-113">父元素</span><span class="sxs-lookup"><span data-stu-id="e240b-113">Parent Elements</span></span>

|<span data-ttu-id="e240b-114">元素</span><span class="sxs-lookup"><span data-stu-id="e240b-114">Element</span></span>|<span data-ttu-id="e240b-115">说明</span><span class="sxs-lookup"><span data-stu-id="e240b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e240b-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e240b-116">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="e240b-117">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e240b-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e240b-118">文本值</span><span class="sxs-lookup"><span data-stu-id="e240b-118">Text Value</span></span>

<span data-ttu-id="e240b-119">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="e240b-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="e240b-120">备注</span><span class="sxs-lookup"><span data-stu-id="e240b-120">Remarks</span></span>

<span data-ttu-id="e240b-121">每个控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="e240b-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e240b-122">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="e240b-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="e240b-123">有关定义选择集的详细信息，请参阅[定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="e240b-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e240b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e240b-124">See Also</span></span>

[<span data-ttu-id="e240b-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e240b-125">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="e240b-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e240b-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
