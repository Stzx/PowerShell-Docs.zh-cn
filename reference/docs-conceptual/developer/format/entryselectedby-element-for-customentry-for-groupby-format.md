---
title: GroupBy (Format) 的 CustomEntry 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 75a0f42e7722b54791a873200a35c8fcbbd665b1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774127"
---
# <a name="entryselectedby-element-for-customentry-for-groupby-format"></a><span data-ttu-id="2f0c4-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-102">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

<span data-ttu-id="2f0c4-103">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="2f0c4-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="2f0c4-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for 元素 for CustomControl for groupby (format) CustomEntry 元素 for CustomControl for groupby (格式) EntrySelectedBy 元素</span><span class="sxs-lookup"><span data-stu-id="2f0c4-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2f0c4-106">语法</span><span class="sxs-lookup"><span data-stu-id="2f0c4-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2f0c4-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2f0c4-107">Attributes and Elements</span></span>

<span data-ttu-id="2f0c4-108">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="2f0c4-109">必须为定义至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="2f0c4-110">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="2f0c4-111">特性</span><span class="sxs-lookup"><span data-stu-id="2f0c4-111">Attributes</span></span>

<span data-ttu-id="2f0c4-112">无。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2f0c4-113">子元素</span><span class="sxs-lookup"><span data-stu-id="2f0c4-113">Child Elements</span></span>

|<span data-ttu-id="2f0c4-114">元素</span><span class="sxs-lookup"><span data-stu-id="2f0c4-114">Element</span></span>|<span data-ttu-id="2f0c4-115">说明</span><span class="sxs-lookup"><span data-stu-id="2f0c4-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2f0c4-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="2f0c4-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-117">Optional element.</span></span><br /><br /> <span data-ttu-id="2f0c4-118">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="2f0c4-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-119">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="2f0c4-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-120">Optional element.</span></span><br /><br /> <span data-ttu-id="2f0c4-121">指定一组使用此控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="2f0c4-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-122">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="2f0c4-123">可选元素。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-123">Optional element.</span></span><br /><br /> <span data-ttu-id="2f0c4-124">指定使用控件的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2f0c4-125">父元素</span><span class="sxs-lookup"><span data-stu-id="2f0c4-125">Parent Elements</span></span>

|<span data-ttu-id="2f0c4-126">元素</span><span class="sxs-lookup"><span data-stu-id="2f0c4-126">Element</span></span>|<span data-ttu-id="2f0c4-127">说明</span><span class="sxs-lookup"><span data-stu-id="2f0c4-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2f0c4-128">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-128">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>](./customentry-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="2f0c4-129">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2f0c4-130">备注</span><span class="sxs-lookup"><span data-stu-id="2f0c4-130">Remarks</span></span>

<span data-ttu-id="2f0c4-131">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="2f0c4-132">有关选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2f0c4-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f0c4-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f0c4-133">See Also</span></span>

[<span data-ttu-id="2f0c4-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="2f0c4-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-135">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="2f0c4-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-136">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./typename-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="2f0c4-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="2f0c4-137">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="2f0c4-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="2f0c4-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
