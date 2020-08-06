---
title: WideEntry (Format) 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ba0a776839c39d753d12859335388c5326639fd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774076"
---
# <a name="entryselectedby-element-for-wideentry-format"></a><span data-ttu-id="42b8e-102">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="42b8e-102">EntrySelectedBy Element for WideEntry (Format)</span></span>

<span data-ttu-id="42b8e-103">定义使用此类定义的 .NET 类型或使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="42b8e-103">Defines the .NET types that use this definition of the wide view or the condition that must exist for this definition to be used.</span></span>

<span data-ttu-id="42b8e-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素</span><span class="sxs-lookup"><span data-stu-id="42b8e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="42b8e-105">语法</span><span class="sxs-lookup"><span data-stu-id="42b8e-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="42b8e-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="42b8e-106">Attributes and Elements</span></span>

<span data-ttu-id="42b8e-107">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="42b8e-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="42b8e-108">特性</span><span class="sxs-lookup"><span data-stu-id="42b8e-108">Attributes</span></span>

<span data-ttu-id="42b8e-109">无。</span><span class="sxs-lookup"><span data-stu-id="42b8e-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="42b8e-110">子元素</span><span class="sxs-lookup"><span data-stu-id="42b8e-110">Child Elements</span></span>

|<span data-ttu-id="42b8e-111">元素</span><span class="sxs-lookup"><span data-stu-id="42b8e-111">Element</span></span>|<span data-ttu-id="42b8e-112">说明</span><span class="sxs-lookup"><span data-stu-id="42b8e-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42b8e-113">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="42b8e-113">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="42b8e-114">可选元素。</span><span class="sxs-lookup"><span data-stu-id="42b8e-114">Optional element.</span></span><br /><br /> <span data-ttu-id="42b8e-115">定义要使用此宽视图定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="42b8e-115">Defines the condition that must exist for this wide view definition to be used.</span></span>|
|[<span data-ttu-id="42b8e-116">WideEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="42b8e-116">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="42b8e-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="42b8e-117">Optional element.</span></span><br /><br /> <span data-ttu-id="42b8e-118">指定一组使用此宽视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="42b8e-118">Specifies a set of .NET types that use this wide view definition.</span></span>|
|[<span data-ttu-id="42b8e-119">TypeName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="42b8e-119">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="42b8e-120">可选元素。</span><span class="sxs-lookup"><span data-stu-id="42b8e-120">Optional element.</span></span><br /><br /> <span data-ttu-id="42b8e-121">指定使用此宽视图定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="42b8e-121">Specifies a .NET type that uses this wide view definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="42b8e-122">父元素</span><span class="sxs-lookup"><span data-stu-id="42b8e-122">Parent Elements</span></span>

|<span data-ttu-id="42b8e-123">元素</span><span class="sxs-lookup"><span data-stu-id="42b8e-123">Element</span></span>|<span data-ttu-id="42b8e-124">说明</span><span class="sxs-lookup"><span data-stu-id="42b8e-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="42b8e-125">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="42b8e-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="42b8e-126">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="42b8e-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="42b8e-127">备注</span><span class="sxs-lookup"><span data-stu-id="42b8e-127">Remarks</span></span>

<span data-ttu-id="42b8e-128">对于宽视图定义，必须至少指定一个类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="42b8e-128">You must specify at least one type, selection set, or selection condition for a wide view definition.</span></span> <span data-ttu-id="42b8e-129">您可以使用的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="42b8e-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="42b8e-130">选择条件用于定义要使用的定义必须存在的条件，例如当对象具有特定属性或特定属性值或脚本值的计算结果为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="42b8e-130">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or that a specific property value or script value evaluates to `true`.</span></span> <span data-ttu-id="42b8e-131">有关选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="42b8e-131">For more information about selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="42b8e-132">有关大视图的其他组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="42b8e-132">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="42b8e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42b8e-133">See Also</span></span>

[<span data-ttu-id="42b8e-134">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="42b8e-134">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="42b8e-135">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="42b8e-135">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="42b8e-136">WideEntry (格式的 EntrySelectedBy 的 SelectionSetName 元素) </span><span class="sxs-lookup"><span data-stu-id="42b8e-136">SelectionSetName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="42b8e-137">TypeName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="42b8e-137">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="42b8e-138">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="42b8e-138">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="42b8e-139">定义用于显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="42b8e-139">Defining Conditions for Displaying Data</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="42b8e-140">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="42b8e-140">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
