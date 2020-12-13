---
ms.date: 09/13/2016
ms.topic: reference
title: EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)
description: EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)
ms.openlocfilehash: fadcdb69ac71269ba2f2f80baf139bb363d4acba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666665"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="c6e7b-103">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-103">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="c6e7b-104">定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-104">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="c6e7b-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="c6e7b-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 的控件) </span><span class="sxs-lookup"><span data-stu-id="c6e7b-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c6e7b-107">语法</span><span class="sxs-lookup"><span data-stu-id="c6e7b-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c6e7b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c6e7b-108">Attributes and Elements</span></span>

<span data-ttu-id="c6e7b-109">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-109">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c6e7b-110">特性</span><span class="sxs-lookup"><span data-stu-id="c6e7b-110">Attributes</span></span>

<span data-ttu-id="c6e7b-111">无。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c6e7b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="c6e7b-112">Child Elements</span></span>

|<span data-ttu-id="c6e7b-113">元素</span><span class="sxs-lookup"><span data-stu-id="c6e7b-113">Element</span></span>|<span data-ttu-id="c6e7b-114">描述</span><span class="sxs-lookup"><span data-stu-id="c6e7b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c6e7b-115">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-115">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="c6e7b-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-116">Optional element.</span></span><br /><br /> <span data-ttu-id="c6e7b-117">定义要使用的公共控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-117">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="c6e7b-118">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-118">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="c6e7b-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-119">Optional element.</span></span><br /><br /> <span data-ttu-id="c6e7b-120">指定一组使用此公共控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-120">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="c6e7b-121">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-121">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="c6e7b-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-122">Optional element.</span></span><br /><br /> <span data-ttu-id="c6e7b-123">指定使用此公共控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-123">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c6e7b-124">父元素</span><span class="sxs-lookup"><span data-stu-id="c6e7b-124">Parent Elements</span></span>

|<span data-ttu-id="c6e7b-125">元素</span><span class="sxs-lookup"><span data-stu-id="c6e7b-125">Element</span></span>|<span data-ttu-id="c6e7b-126">描述</span><span class="sxs-lookup"><span data-stu-id="c6e7b-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c6e7b-127">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-127">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="c6e7b-128">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-128">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c6e7b-129">备注</span><span class="sxs-lookup"><span data-stu-id="c6e7b-129">Remarks</span></span>

<span data-ttu-id="c6e7b-130">每个定义至少必须指定一个 .NET 类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-130">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="c6e7b-131">对于可以指定的类型、选择集或选择条件的数量没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="c6e7b-131">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6e7b-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6e7b-132">See Also</span></span>

[<span data-ttu-id="c6e7b-133">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-133">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="c6e7b-134">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-134">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c6e7b-135">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-135">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="c6e7b-136">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="c6e7b-136">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="c6e7b-137">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="c6e7b-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
