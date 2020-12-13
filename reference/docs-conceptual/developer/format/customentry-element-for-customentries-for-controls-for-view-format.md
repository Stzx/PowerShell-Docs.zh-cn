---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntry Element for CustomEntries for Controls for View (Format)
description: CustomEntry Element for CustomEntries for Controls for View (Format)
ms.openlocfilehash: a525b198c8f595e04dc0804d36b5533b94f43c6b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646081"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="9c9d9-103">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9c9d9-103">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="9c9d9-104">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-104">Provides a definition of the control.</span></span> <span data-ttu-id="9c9d9-105">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="9c9d9-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomControl 元素，用于控件的视图 (格式) CustomEntries 元素 (CustomEntry 的控件) CustomEntries</span><span class="sxs-lookup"><span data-stu-id="9c9d9-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9c9d9-107">语法</span><span class="sxs-lookup"><span data-stu-id="9c9d9-107">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9c9d9-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9c9d9-108">Attributes and Elements</span></span>

<span data-ttu-id="9c9d9-109">以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-109">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9c9d9-110">特性</span><span class="sxs-lookup"><span data-stu-id="9c9d9-110">Attributes</span></span>

<span data-ttu-id="9c9d9-111">无。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9c9d9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9c9d9-112">Child Elements</span></span>

|<span data-ttu-id="9c9d9-113">元素</span><span class="sxs-lookup"><span data-stu-id="9c9d9-113">Element</span></span>|<span data-ttu-id="9c9d9-114">描述</span><span class="sxs-lookup"><span data-stu-id="9c9d9-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9c9d9-115">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9c9d9-115">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="9c9d9-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-116">Optional element.</span></span><br /><br /> <span data-ttu-id="9c9d9-117">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="9c9d9-118">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9c9d9-118">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="9c9d9-119">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-119">Required element.</span></span><br /><br /> <span data-ttu-id="9c9d9-120">定义控件显示数据的方式。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-120">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9c9d9-121">父元素</span><span class="sxs-lookup"><span data-stu-id="9c9d9-121">Parent Elements</span></span>

|<span data-ttu-id="9c9d9-122">元素</span><span class="sxs-lookup"><span data-stu-id="9c9d9-122">Element</span></span>|<span data-ttu-id="9c9d9-123">描述</span><span class="sxs-lookup"><span data-stu-id="9c9d9-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9c9d9-124">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9c9d9-124">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="9c9d9-125">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="9c9d9-125">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9c9d9-126">备注</span><span class="sxs-lookup"><span data-stu-id="9c9d9-126">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="9c9d9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c9d9-127">See Also</span></span>

[<span data-ttu-id="9c9d9-128">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9c9d9-128">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9c9d9-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9c9d9-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
