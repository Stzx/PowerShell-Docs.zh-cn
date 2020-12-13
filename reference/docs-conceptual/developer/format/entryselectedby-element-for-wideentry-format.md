---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for WideEntry (Format)
description: EntrySelectedBy Element for WideEntry (Format)
ms.openlocfilehash: 246a1967300ab0551f376c4799deac275068308c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660251"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="a86cf-103">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a86cf-103">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="a86cf-104">定义使用此类定义的 .NET 类型或使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a86cf-104">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="a86cf-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素</span><span class="sxs-lookup"><span data-stu-id="a86cf-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a86cf-106">语法</span><span class="sxs-lookup"><span data-stu-id="a86cf-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a86cf-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a86cf-107">Attributes and Elements</span></span>

<span data-ttu-id="a86cf-108">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="a86cf-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a86cf-109">特性</span><span class="sxs-lookup"><span data-stu-id="a86cf-109">Attributes</span></span>

<span data-ttu-id="a86cf-110">无。</span><span class="sxs-lookup"><span data-stu-id="a86cf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a86cf-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a86cf-111">Child Elements</span></span>

|<span data-ttu-id="a86cf-112">元素</span><span class="sxs-lookup"><span data-stu-id="a86cf-112">Element</span></span>|<span data-ttu-id="a86cf-113">描述</span><span class="sxs-lookup"><span data-stu-id="a86cf-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a86cf-114">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="a86cf-114">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a86cf-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a86cf-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a86cf-116">定义要使用此宽视图定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a86cf-116">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="a86cf-117">WideEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="a86cf-117">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a86cf-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a86cf-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a86cf-119">指定一组使用此宽视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="a86cf-119">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="a86cf-120">TypeName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a86cf-120">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="a86cf-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a86cf-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a86cf-122">指定使用此宽视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="a86cf-122">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a86cf-123">父元素</span><span class="sxs-lookup"><span data-stu-id="a86cf-123">Parent Elements</span></span>

|<span data-ttu-id="a86cf-124">元素</span><span class="sxs-lookup"><span data-stu-id="a86cf-124">Element</span></span>|<span data-ttu-id="a86cf-125">描述</span><span class="sxs-lookup"><span data-stu-id="a86cf-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a86cf-126">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a86cf-126">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="a86cf-127">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="a86cf-127">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a86cf-128">备注</span><span class="sxs-lookup"><span data-stu-id="a86cf-128">Remarks</span></span>

<span data-ttu-id="a86cf-129">对于宽视图定义，必须至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="a86cf-129">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="a86cf-130">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="a86cf-130">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="a86cf-131">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本值的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="a86cf-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="a86cf-132">有关选择条件的详细信息，请参阅 [定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a86cf-132">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a86cf-133">有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="a86cf-133">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a86cf-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a86cf-134">See Also</span></span>

[<span data-ttu-id="a86cf-135">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a86cf-135">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="a86cf-136">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="a86cf-136">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a86cf-137">WideEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="a86cf-137">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a86cf-138">TypeName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a86cf-138">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="a86cf-139">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="a86cf-139">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a86cf-140">定义用于显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="a86cf-140">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a86cf-141">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a86cf-141">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
