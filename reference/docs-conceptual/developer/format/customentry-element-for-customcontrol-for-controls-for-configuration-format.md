---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntry Element for CustomControl for Controls for Configuration (Format)
description: CustomEntry Element for CustomControl for Controls for Configuration (Format)
ms.openlocfilehash: 3967be86a1d6c12c7215ef19d50bac9fafd5ad6d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648280"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="e020d-103">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e020d-103">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="e020d-104">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="e020d-104">Provides a definition of the common control.</span></span> <span data-ttu-id="e020d-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="e020d-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="e020d-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的控件 (CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="e020d-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e020d-107">语法</span><span class="sxs-lookup"><span data-stu-id="e020d-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="e020d-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e020d-108">Attributes and Elements</span></span>

<span data-ttu-id="e020d-109">以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="e020d-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="e020d-110">您必须指定由定义显示的项。</span><span class="sxs-lookup"><span data-stu-id="e020d-110">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="e020d-111">特性</span><span class="sxs-lookup"><span data-stu-id="e020d-111">Attributes</span></span>

<span data-ttu-id="e020d-112">无。</span><span class="sxs-lookup"><span data-stu-id="e020d-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e020d-113">子元素</span><span class="sxs-lookup"><span data-stu-id="e020d-113">Child Elements</span></span>

|<span data-ttu-id="e020d-114">元素</span><span class="sxs-lookup"><span data-stu-id="e020d-114">Element</span></span>|<span data-ttu-id="e020d-115">描述</span><span class="sxs-lookup"><span data-stu-id="e020d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e020d-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="e020d-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="e020d-117">可选元素。</span><span class="sxs-lookup"><span data-stu-id="e020d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="e020d-118">定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e020d-118">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="e020d-119">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="e020d-119">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="e020d-120">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="e020d-120">Required element.</span></span><br /><br /> <span data-ttu-id="e020d-121">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="e020d-121">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e020d-122">父元素</span><span class="sxs-lookup"><span data-stu-id="e020d-122">Parent Elements</span></span>

|<span data-ttu-id="e020d-123">元素</span><span class="sxs-lookup"><span data-stu-id="e020d-123">Element</span></span>|<span data-ttu-id="e020d-124">描述</span><span class="sxs-lookup"><span data-stu-id="e020d-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e020d-125">用于配置 (格式的 CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="e020d-125">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="e020d-126">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="e020d-126">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e020d-127">备注</span><span class="sxs-lookup"><span data-stu-id="e020d-127">Remarks</span></span>

<span data-ttu-id="e020d-128">在大多数情况下，每个公共自定义控件只需要一个定义，但如果您希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="e020d-128">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="e020d-129">在这些情况下，可以为每个对象或一组对象提供单独的定义。</span><span class="sxs-lookup"><span data-stu-id="e020d-129">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="e020d-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e020d-130">See Also</span></span>

[<span data-ttu-id="e020d-131">用于配置 (格式的 CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="e020d-131">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="e020d-132">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="e020d-132">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="e020d-133">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e020d-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
