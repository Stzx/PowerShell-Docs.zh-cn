---
title: 用于) 配置 (格式的控件的 CustomEntry 的 EntrySelectedBy 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9467c8c2d80e46c0a47c31569efbddbabe25bb1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774263"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-configuration-format"></a><span data-ttu-id="49c3f-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-102">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

<span data-ttu-id="49c3f-103">定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="49c3f-103">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span> <span data-ttu-id="49c3f-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="49c3f-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="49c3f-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的 CustomEntry 元素 (CustomControl 的控件) </span><span class="sxs-lookup"><span data-stu-id="49c3f-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="49c3f-106">语法</span><span class="sxs-lookup"><span data-stu-id="49c3f-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>SelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="49c3f-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="49c3f-107">Attributes and Elements</span></span>

<span data-ttu-id="49c3f-108">以下各节描述了元素的属性、子元素和父元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="49c3f-108">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="49c3f-109">特性</span><span class="sxs-lookup"><span data-stu-id="49c3f-109">Attributes</span></span>

<span data-ttu-id="49c3f-110">无。</span><span class="sxs-lookup"><span data-stu-id="49c3f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="49c3f-111">子元素</span><span class="sxs-lookup"><span data-stu-id="49c3f-111">Child Elements</span></span>

|<span data-ttu-id="49c3f-112">元素</span><span class="sxs-lookup"><span data-stu-id="49c3f-112">Element</span></span>|<span data-ttu-id="49c3f-113">说明</span><span class="sxs-lookup"><span data-stu-id="49c3f-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49c3f-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-114">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="49c3f-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="49c3f-115">Optional element.</span></span><br /><br /> <span data-ttu-id="49c3f-116">定义要使用的公共控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="49c3f-116">Defines the condition that must exist for the common control definition to be used.</span></span>|
|[<span data-ttu-id="49c3f-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-117">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="49c3f-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="49c3f-118">Optional element.</span></span><br /><br /> <span data-ttu-id="49c3f-119">指定一组使用此公共控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="49c3f-119">Specifies a set of .NET types that use this definition of the common control.</span></span>|
|[<span data-ttu-id="49c3f-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-120">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="49c3f-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="49c3f-121">Optional element.</span></span><br /><br /> <span data-ttu-id="49c3f-122">指定使用此公共控件定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="49c3f-122">Specifies a .NET type that uses this definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="49c3f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="49c3f-123">Parent Elements</span></span>

|<span data-ttu-id="49c3f-124">元素</span><span class="sxs-lookup"><span data-stu-id="49c3f-124">Element</span></span>|<span data-ttu-id="49c3f-125">说明</span><span class="sxs-lookup"><span data-stu-id="49c3f-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49c3f-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-126">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="49c3f-127">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="49c3f-127">Provides a definition of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="49c3f-128">备注</span><span class="sxs-lookup"><span data-stu-id="49c3f-128">Remarks</span></span>

<span data-ttu-id="49c3f-129">每个定义至少必须指定一个 .NET 类型、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="49c3f-129">At a minimum, each definition must have at least one .NET type, selection set, or selection condition specified.</span></span> <span data-ttu-id="49c3f-130">对于可以指定的类型、选择集或选择条件的数量没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="49c3f-130">There is no maximum limit to the number of types, selection sets, or selection conditions that you can specify.</span></span>

## <a name="see-also"></a><span data-ttu-id="49c3f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49c3f-131">See Also</span></span>

[<span data-ttu-id="49c3f-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-132">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="49c3f-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-133">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="49c3f-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-134">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="49c3f-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="49c3f-135">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="49c3f-136">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="49c3f-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
