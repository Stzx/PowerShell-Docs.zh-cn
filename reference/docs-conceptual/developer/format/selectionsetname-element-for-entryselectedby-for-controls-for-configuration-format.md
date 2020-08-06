---
title: 用于) 配置 (格式的控件的 EntrySelectedBy 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 72072d8d13e6ca22afdb9bca2e0237d29ba0594f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787557"
---
# <a name="selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="ba6e3-102">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba6e3-102">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ba6e3-103">指定一组使用此控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-103">Specifies a set of .NET types that use this definition of the control.</span></span> <span data-ttu-id="ba6e3-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ba6e3-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl) 格式的控件 (EntrySelectedBy 的控件) CustomEntry 元素， (</span><span class="sxs-lookup"><span data-stu-id="ba6e3-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ba6e3-106">语法</span><span class="sxs-lookup"><span data-stu-id="ba6e3-106">Syntax</span></span>

```xml
<SelectionSetName>NameofSelectionSet</SelectionSetName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="ba6e3-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ba6e3-107">Attributes and Elements</span></span>

<span data-ttu-id="ba6e3-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-108">The following sections describe attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ba6e3-109">属性</span><span class="sxs-lookup"><span data-stu-id="ba6e3-109">Attributes</span></span>

<span data-ttu-id="ba6e3-110">None</span><span class="sxs-lookup"><span data-stu-id="ba6e3-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="ba6e3-111">子元素</span><span class="sxs-lookup"><span data-stu-id="ba6e3-111">Child Elements</span></span>

<span data-ttu-id="ba6e3-112">无。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ba6e3-113">父元素</span><span class="sxs-lookup"><span data-stu-id="ba6e3-113">Parent Elements</span></span>

|<span data-ttu-id="ba6e3-114">元素</span><span class="sxs-lookup"><span data-stu-id="ba6e3-114">Element</span></span>|<span data-ttu-id="ba6e3-115">说明</span><span class="sxs-lookup"><span data-stu-id="ba6e3-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ba6e3-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba6e3-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="ba6e3-117">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="ba6e3-118">文本值</span><span class="sxs-lookup"><span data-stu-id="ba6e3-118">Text Value</span></span>

<span data-ttu-id="ba6e3-119">指定选择集的名称。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-119">Specify the name of the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba6e3-120">备注</span><span class="sxs-lookup"><span data-stu-id="ba6e3-120">Remarks</span></span>

<span data-ttu-id="ba6e3-121">每个控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="ba6e3-122">当要定义在多个视图中使用的一组对象时，通常使用选择集。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-122">Selection sets are typically used when you want to define a group of objects that are used in multiple views.</span></span> <span data-ttu-id="ba6e3-123">有关定义选择集的详细信息，请参阅[定义选择集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="ba6e3-123">For more information about defining selection sets, see [Defining Selection Sets](./defining-selection-sets.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba6e3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba6e3-124">See Also</span></span>

[<span data-ttu-id="ba6e3-125">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ba6e3-125">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="ba6e3-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ba6e3-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
