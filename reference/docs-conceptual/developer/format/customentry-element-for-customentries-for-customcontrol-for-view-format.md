---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntry Element for CustomEntries for CustomControl for View (Format)
description: CustomEntry Element for CustomEntries for CustomControl for View (Format)
ms.openlocfilehash: ff481f13e6f16267bdda4c3053faebc96d9a6d3a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646053"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="dc4f9-103">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dc4f9-103">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="dc4f9-104">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-104">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="dc4f9-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的 CustomEntries 元素)  (格式) </span><span class="sxs-lookup"><span data-stu-id="dc4f9-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dc4f9-106">语法</span><span class="sxs-lookup"><span data-stu-id="dc4f9-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dc4f9-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dc4f9-107">Attributes and Elements</span></span>

<span data-ttu-id="dc4f9-108">以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="dc4f9-109">您必须指定由定义显示的项。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="dc4f9-110">特性</span><span class="sxs-lookup"><span data-stu-id="dc4f9-110">Attributes</span></span>

<span data-ttu-id="dc4f9-111">无。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dc4f9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="dc4f9-112">Child Elements</span></span>

|<span data-ttu-id="dc4f9-113">元素</span><span class="sxs-lookup"><span data-stu-id="dc4f9-113">Element</span></span>|<span data-ttu-id="dc4f9-114">描述</span><span class="sxs-lookup"><span data-stu-id="dc4f9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dc4f9-115">View (格式的 CustomEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="dc4f9-115">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="dc4f9-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="dc4f9-117">定义使用自定义控件视图的定义或要使用此定义必须存在的条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-117">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="dc4f9-118">View (格式的 CustomEntry 的 CustomItem 元素) </span><span class="sxs-lookup"><span data-stu-id="dc4f9-118">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="dc4f9-119">定义自定义控件定义的控件。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-119">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dc4f9-120">父元素</span><span class="sxs-lookup"><span data-stu-id="dc4f9-120">Parent Elements</span></span>

|<span data-ttu-id="dc4f9-121">元素</span><span class="sxs-lookup"><span data-stu-id="dc4f9-121">Element</span></span>|<span data-ttu-id="dc4f9-122">描述</span><span class="sxs-lookup"><span data-stu-id="dc4f9-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dc4f9-123">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dc4f9-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="dc4f9-124">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-124">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="dc4f9-125">自定义控件视图必须指定一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-125">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dc4f9-126">备注</span><span class="sxs-lookup"><span data-stu-id="dc4f9-126">Remarks</span></span>

<span data-ttu-id="dc4f9-127">在大多数情况下，每个自定义控件视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-127">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="dc4f9-128">在这些情况下，可以为每个对象或一组对象提供单独的定义。</span><span class="sxs-lookup"><span data-stu-id="dc4f9-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc4f9-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc4f9-129">See Also</span></span>

[<span data-ttu-id="dc4f9-130">CustomControl Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dc4f9-130">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="dc4f9-131">View (格式的 CustomEntry 的 CustomItem 元素) </span><span class="sxs-lookup"><span data-stu-id="dc4f9-131">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dc4f9-132">View (格式的 CustomEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="dc4f9-132">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="dc4f9-133">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="dc4f9-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
