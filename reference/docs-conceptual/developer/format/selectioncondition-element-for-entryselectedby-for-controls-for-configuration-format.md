---
title: 用于) 配置 (格式的控件的 EntrySelectedBy 的 SelectionCondition 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 748aa1aa0ba603a44334d9401e9e2c0e68f14e03
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783409"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="a6703-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-102">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="a6703-103">定义要使用的公共控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a6703-103">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="a6703-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="a6703-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="a6703-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素，用于 for for for for for for for for for for for for for for for for CustomEntry CustomControl EntrySelectedBy CustomEntry) </span><span class="sxs-lookup"><span data-stu-id="a6703-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a6703-106">语法</span><span class="sxs-lookup"><span data-stu-id="a6703-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a6703-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a6703-107">Attributes and Elements</span></span>

<span data-ttu-id="a6703-108">以下各节描述了元素的属性、子元素和父元素 `SelectionCondition` 。</span><span class="sxs-lookup"><span data-stu-id="a6703-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a6703-109">特性</span><span class="sxs-lookup"><span data-stu-id="a6703-109">Attributes</span></span>

<span data-ttu-id="a6703-110">无。</span><span class="sxs-lookup"><span data-stu-id="a6703-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a6703-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a6703-111">Child Elements</span></span>

|<span data-ttu-id="a6703-112">元素</span><span class="sxs-lookup"><span data-stu-id="a6703-112">Element</span></span>|<span data-ttu-id="a6703-113">描述</span><span class="sxs-lookup"><span data-stu-id="a6703-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6703-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-114">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a6703-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a6703-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a6703-116">指定触发条件的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="a6703-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a6703-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-117">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a6703-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a6703-118">Optional element.</span></span><br /><br /> <span data-ttu-id="a6703-119">指定触发条件的脚本。</span><span class="sxs-lookup"><span data-stu-id="a6703-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="a6703-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-120">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a6703-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a6703-121">Optional element.</span></span><br /><br /> <span data-ttu-id="a6703-122">指定触发条件的 .NET 类型集。</span><span class="sxs-lookup"><span data-stu-id="a6703-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="a6703-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-123">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="a6703-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a6703-124">Optional element.</span></span><br /><br /> <span data-ttu-id="a6703-125">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="a6703-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a6703-126">父元素</span><span class="sxs-lookup"><span data-stu-id="a6703-126">Parent Elements</span></span>

|<span data-ttu-id="a6703-127">元素</span><span class="sxs-lookup"><span data-stu-id="a6703-127">Element</span></span>|<span data-ttu-id="a6703-128">描述</span><span class="sxs-lookup"><span data-stu-id="a6703-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a6703-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-129">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="a6703-130">定义使用此公共控件定义的此项的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="a6703-130">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a6703-131">备注</span><span class="sxs-lookup"><span data-stu-id="a6703-131">Remarks</span></span>

<span data-ttu-id="a6703-132">定义选择条件时，必须遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="a6703-132">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="a6703-133">选择条件必须指定至少一个属性名称或脚本块，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a6703-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="a6703-134">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="a6703-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="a6703-135">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="a6703-135">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a6703-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6703-136">See Also</span></span>

[<span data-ttu-id="a6703-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-137">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a6703-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-138">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a6703-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-139">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a6703-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-140">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="a6703-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="a6703-141">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="a6703-142">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="a6703-142">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
