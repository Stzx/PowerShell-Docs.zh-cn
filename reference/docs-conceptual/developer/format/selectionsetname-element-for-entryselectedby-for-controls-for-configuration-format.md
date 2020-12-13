---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)
description: SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)
ms.openlocfilehash: b775aa8a3184aa3ebcbda17a8e3191c69d67a700
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645733"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="81ab9-103">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="81ab9-103">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="81ab9-104">指定一组使用此控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="81ab9-104">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="81ab9-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="81ab9-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="81ab9-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl) 格式的控件 (EntrySelectedBy 的控件) CustomEntry 元素， (</span><span class="sxs-lookup"><span data-stu-id="81ab9-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="81ab9-107">语法</span><span class="sxs-lookup"><span data-stu-id="81ab9-107">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="81ab9-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="81ab9-108">Attributes and Elements</span></span>

<span data-ttu-id="81ab9-109">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="81ab9-109">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="81ab9-110">特性</span><span class="sxs-lookup"><span data-stu-id="81ab9-110">Attributes</span></span>

<span data-ttu-id="81ab9-111">无</span><span class="sxs-lookup"><span data-stu-id="81ab9-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="81ab9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="81ab9-112">Child Elements</span></span>

<span data-ttu-id="81ab9-113">无。</span><span class="sxs-lookup"><span data-stu-id="81ab9-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="81ab9-114">父元素</span><span class="sxs-lookup"><span data-stu-id="81ab9-114">Parent Elements</span></span>

|<span data-ttu-id="81ab9-115">元素</span><span class="sxs-lookup"><span data-stu-id="81ab9-115">Element</span></span>|<span data-ttu-id="81ab9-116">描述</span><span class="sxs-lookup"><span data-stu-id="81ab9-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="81ab9-117">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="81ab9-117">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="81ab9-118">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="81ab9-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="81ab9-119">文本值</span><span class="sxs-lookup"><span data-stu-id="81ab9-119">Text Value</span></span>

<span data-ttu-id="81ab9-120">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="81ab9-120">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="81ab9-121">备注</span><span class="sxs-lookup"><span data-stu-id="81ab9-121">Remarks</span></span>

<span data-ttu-id="81ab9-122">每个控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="81ab9-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="81ab9-123">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="81ab9-123">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="81ab9-124">有关定义选择集的详细信息，请参阅 [定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="81ab9-124">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="81ab9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81ab9-125">See Also</span></span>

[<span data-ttu-id="81ab9-126">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="81ab9-126">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="81ab9-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="81ab9-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
