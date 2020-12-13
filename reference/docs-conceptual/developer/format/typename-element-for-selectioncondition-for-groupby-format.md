---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for GroupBy (Format)
description: TypeName Element for SelectionCondition for GroupBy (Format)
ms.openlocfilehash: 096d2355e113a7e44cc6ae31ea23efc3f01080a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664627"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="672a9-103">TypeName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="672a9-103">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="672a9-104">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="672a9-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="672a9-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="672a9-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="672a9-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="672a9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="672a9-107">语法</span><span class="sxs-lookup"><span data-stu-id="672a9-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="672a9-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="672a9-108">Attributes and Elements</span></span>

<span data-ttu-id="672a9-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="672a9-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="672a9-110">特性</span><span class="sxs-lookup"><span data-stu-id="672a9-110">Attributes</span></span>

<span data-ttu-id="672a9-111">无。</span><span class="sxs-lookup"><span data-stu-id="672a9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="672a9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="672a9-112">Child Elements</span></span>

<span data-ttu-id="672a9-113">无。</span><span class="sxs-lookup"><span data-stu-id="672a9-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="672a9-114">父元素</span><span class="sxs-lookup"><span data-stu-id="672a9-114">Parent Elements</span></span>

|<span data-ttu-id="672a9-115">元素</span><span class="sxs-lookup"><span data-stu-id="672a9-115">Element</span></span>|<span data-ttu-id="672a9-116">描述</span><span class="sxs-lookup"><span data-stu-id="672a9-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="672a9-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="672a9-117">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="672a9-118">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="672a9-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="672a9-119">文本值</span><span class="sxs-lookup"><span data-stu-id="672a9-119">Text Value</span></span>

<span data-ttu-id="672a9-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="672a9-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="672a9-121">备注</span><span class="sxs-lookup"><span data-stu-id="672a9-121">Remarks</span></span>

<span data-ttu-id="672a9-122">如果指定此元素，则不能指定 `SelectionSetName` 元素。</span><span class="sxs-lookup"><span data-stu-id="672a9-122">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="672a9-123">有关定义选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="672a9-123">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="672a9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="672a9-124">See Also</span></span>

[<span data-ttu-id="672a9-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="672a9-125">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="672a9-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="672a9-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
