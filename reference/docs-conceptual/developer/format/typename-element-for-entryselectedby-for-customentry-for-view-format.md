---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for CustomEntry for View (Format)
description: TypeName Element for EntrySelectedBy for CustomEntry for View (Format)
ms.openlocfilehash: 72bb88bccc2bbd62f7ed160b820cf9169cb69341
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645738"
---
# <a name="typename-element-for-entryselectedby-for-customentry-for-view-format"></a><span data-ttu-id="084d7-103">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span><span class="sxs-lookup"><span data-stu-id="084d7-103">TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

<span data-ttu-id="084d7-104">指定使用自定义控件视图的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="084d7-104">Specifies a .NET type that uses this definition of the custom control view.</span></span> <span data-ttu-id="084d7-105">对于可以为定义指定的类型数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="084d7-105">There is no limit to the number of types that can be specified for a definition.</span></span>

<span data-ttu-id="084d7-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素 (CustomEntry 的 CustomControl 的元素) CustomEntries 的 EntrySelectedBy 元素 (CustomEntry for view) 格式 (的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="084d7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format) TypeName Element for EntrySelectedBy for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="084d7-107">语法</span><span class="sxs-lookup"><span data-stu-id="084d7-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="084d7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="084d7-108">Attributes and Elements</span></span>

<span data-ttu-id="084d7-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="084d7-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="084d7-110">特性</span><span class="sxs-lookup"><span data-stu-id="084d7-110">Attributes</span></span>

<span data-ttu-id="084d7-111">无。</span><span class="sxs-lookup"><span data-stu-id="084d7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="084d7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="084d7-112">Child Elements</span></span>

<span data-ttu-id="084d7-113">无。</span><span class="sxs-lookup"><span data-stu-id="084d7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="084d7-114">父元素</span><span class="sxs-lookup"><span data-stu-id="084d7-114">Parent Elements</span></span>

|<span data-ttu-id="084d7-115">元素</span><span class="sxs-lookup"><span data-stu-id="084d7-115">Element</span></span>|<span data-ttu-id="084d7-116">描述</span><span class="sxs-lookup"><span data-stu-id="084d7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="084d7-117">View (格式的 CustomEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="084d7-117">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="084d7-118">定义使用此自定义控件视图定义或要使用此定义必须存在的条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="084d7-118">Defines the .NET types that use this custom control view definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="084d7-119">文本值</span><span class="sxs-lookup"><span data-stu-id="084d7-119">Text Value</span></span>

<span data-ttu-id="084d7-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="084d7-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="084d7-121">备注</span><span class="sxs-lookup"><span data-stu-id="084d7-121">Remarks</span></span>

<span data-ttu-id="084d7-122">每个自定义控件视图定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="084d7-122">Each custom control view definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="084d7-123">有关自定义控件视图组件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="084d7-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="084d7-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="084d7-124">See Also</span></span>

[<span data-ttu-id="084d7-125">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="084d7-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="084d7-126">View (格式的 CustomEntry 的 EntrySelectedBy 元素) </span><span class="sxs-lookup"><span data-stu-id="084d7-126">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="084d7-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="084d7-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
