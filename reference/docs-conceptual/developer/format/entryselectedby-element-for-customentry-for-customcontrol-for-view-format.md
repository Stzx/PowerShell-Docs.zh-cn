---
title: 用于 CustomControl for View (Format) 的 CustomEntry 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4d4900cefb0d499397fc9dff7e037ce0a541f72f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783681"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="7e544-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="7e544-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="7e544-103">定义使用此自定义项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="7e544-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="7e544-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomControl for view (格式) CustomEntries 元素 (CustomEntry 的 CustomEntries 元素) EntrySelectedBy 的 CustomEntry 元素 (</span><span class="sxs-lookup"><span data-stu-id="7e544-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7e544-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e544-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7e544-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7e544-106">Attributes and Elements</span></span>

<span data-ttu-id="7e544-107">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="7e544-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7e544-108">特性</span><span class="sxs-lookup"><span data-stu-id="7e544-108">Attributes</span></span>

<span data-ttu-id="7e544-109">无。</span><span class="sxs-lookup"><span data-stu-id="7e544-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7e544-110">子元素</span><span class="sxs-lookup"><span data-stu-id="7e544-110">Child Elements</span></span>

|<span data-ttu-id="7e544-111">元素</span><span class="sxs-lookup"><span data-stu-id="7e544-111">Element</span></span>|<span data-ttu-id="7e544-112">描述</span><span class="sxs-lookup"><span data-stu-id="7e544-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7e544-113">CustomEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="7e544-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7e544-114">Optional element.</span></span><br /><br /> <span data-ttu-id="7e544-115">定义要使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="7e544-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="7e544-116">CustomEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="7e544-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7e544-117">Optional element.</span></span><br /><br /> <span data-ttu-id="7e544-118">指定一组使用控件视图的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="7e544-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="7e544-119">CustomEntry (格式的 EntrySelectedBy 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="7e544-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="7e544-120">Optional element.</span></span><br /><br /> <span data-ttu-id="7e544-121">指定使用控件视图的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="7e544-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7e544-122">父元素</span><span class="sxs-lookup"><span data-stu-id="7e544-122">Parent Elements</span></span>

|<span data-ttu-id="7e544-123">元素</span><span class="sxs-lookup"><span data-stu-id="7e544-123">Element</span></span>|<span data-ttu-id="7e544-124">描述</span><span class="sxs-lookup"><span data-stu-id="7e544-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7e544-125">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="7e544-126">定义特定 .NET 对象使用的控件。</span><span class="sxs-lookup"><span data-stu-id="7e544-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7e544-127">备注</span><span class="sxs-lookup"><span data-stu-id="7e544-127">Remarks</span></span>

<span data-ttu-id="7e544-128">您必须为某个条目指定至少一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="7e544-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="7e544-129">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="7e544-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="7e544-130">选择条件用于定义要使用的项必须存在的条件，例如当对象具有特定属性或特定属性值或脚本计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="7e544-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="7e544-131">有关选择条件的详细信息，请参阅[定义使用视图条目或项的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="7e544-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="7e544-132">有关自定义控件视图组件的详细信息，请参阅[自定义控件视图](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="7e544-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e544-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e544-133">See Also</span></span>

[<span data-ttu-id="7e544-134">CustomEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="7e544-135">CustomEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7e544-136">CustomEntry (格式的 EntrySelectedBy 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7e544-137">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="7e544-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7e544-138">自定义控件视图</span><span class="sxs-lookup"><span data-stu-id="7e544-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7e544-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7e544-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
