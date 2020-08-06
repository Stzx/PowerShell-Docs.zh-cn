---
title: ListControl (Format) 的 ListEntry 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d6ab1c08dd353da74d1a7d27c569d2fa86e083c3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774110"
---
# <a name="entryselectedby-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="1f0d7-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-102">EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="1f0d7-103">定义使用此列表视图定义或要使用此定义必须存在的条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-103">Defines the .NET types that use this list view definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="1f0d7-104">在大多数情况下，列表视图只需要一个定义。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-104">In most cases only one definition is needed for a list view.</span></span> <span data-ttu-id="1f0d7-105">但是，如果您希望使用同一列表视图为不同对象显示不同的数据，则可以为列表视图提供多个定义。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-105">However, you can provide multiple definitions for the list view if you want to use the same list view to display different data for different objects.</span></span>

<span data-ttu-id="1f0d7-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntry ListControl EntrySelectedBy 的 ListEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="1f0d7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntry for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1f0d7-107">语法</span><span class="sxs-lookup"><span data-stu-id="1f0d7-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1f0d7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1f0d7-108">Attributes and Elements</span></span>

<span data-ttu-id="1f0d7-109">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-109">The following sections describe the attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1f0d7-110">特性</span><span class="sxs-lookup"><span data-stu-id="1f0d7-110">Attributes</span></span>

<span data-ttu-id="1f0d7-111">无。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1f0d7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1f0d7-112">Child Elements</span></span>

|<span data-ttu-id="1f0d7-113">元素</span><span class="sxs-lookup"><span data-stu-id="1f0d7-113">Element</span></span>|<span data-ttu-id="1f0d7-114">说明</span><span class="sxs-lookup"><span data-stu-id="1f0d7-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1f0d7-115">ListControl (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="1f0d7-115">SelectionCondition Element for EntrySelectedBy for ListControl  (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="1f0d7-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-116">Optional element.</span></span><br /><br /> <span data-ttu-id="1f0d7-117">定义要使用此列表视图定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-117">Defines the condition that must exist for this list view definition to be used.</span></span>|
|[<span data-ttu-id="1f0d7-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-118">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="1f0d7-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-119">Optional element.</span></span><br /><br /> <span data-ttu-id="1f0d7-120">指定一组使用此列表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-120">Specifies a set of .NET types that use this list view definition.</span></span>|
|[<span data-ttu-id="1f0d7-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-121">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="1f0d7-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-122">Optional element.</span></span><br /><br /> <span data-ttu-id="1f0d7-123">指定使用此列表视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-123">Specifies a .NET type that uses this list view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1f0d7-124">父元素</span><span class="sxs-lookup"><span data-stu-id="1f0d7-124">Parent Elements</span></span>

|<span data-ttu-id="1f0d7-125">元素</span><span class="sxs-lookup"><span data-stu-id="1f0d7-125">Element</span></span>|<span data-ttu-id="1f0d7-126">说明</span><span class="sxs-lookup"><span data-stu-id="1f0d7-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1f0d7-127">ListEntry Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-127">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="1f0d7-128">定义列表行的显示方式。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-128">Defines how the rows of the list are displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1f0d7-129">备注</span><span class="sxs-lookup"><span data-stu-id="1f0d7-129">Remarks</span></span>

<span data-ttu-id="1f0d7-130">对于列表视图定义，必须至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-130">You must specify at least one type, selection set, or selection condition for a list view definition.</span></span> <span data-ttu-id="1f0d7-131">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-131">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="1f0d7-132">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="1f0d7-133">有关选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-133">For more information about selection conditions, see [Defining Conditions for when Data is displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="1f0d7-134">有关列表视图组件的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-134">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="1f0d7-135">示例</span><span class="sxs-lookup"><span data-stu-id="1f0d7-135">Example</span></span>

<span data-ttu-id="1f0d7-136">下面的示例演示如何使用 .NET 类型名称定义列表视图的对象。</span><span class="sxs-lookup"><span data-stu-id="1f0d7-136">The following example shows how to define the objects for a list view using their .NET type name.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>NameofDotNetType</TypeName>>
  </EntrySelectedBy>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="1f0d7-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f0d7-137">See Also</span></span>

[<span data-ttu-id="1f0d7-138">ListEntry Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-138">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="1f0d7-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-139">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1f0d7-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1f0d7-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1f0d7-141">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>](./typename-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1f0d7-142">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="1f0d7-142">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1f0d7-143">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="1f0d7-143">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1f0d7-144">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="1f0d7-144">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
