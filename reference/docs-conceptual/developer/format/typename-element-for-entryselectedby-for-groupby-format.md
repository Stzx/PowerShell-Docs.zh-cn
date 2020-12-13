---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for GroupBy (Format)
description: TypeName Element for EntrySelectedBy for GroupBy (Format)
ms.openlocfilehash: 07cc92e9c501aa0eb2d219e416851be0fcd80f47
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645706"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="e3b14-103">TypeName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e3b14-103">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="e3b14-104">指定使用自定义控件的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="e3b14-104">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="e3b14-105">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="e3b14-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="e3b14-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomControl 元素 for CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="e3b14-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e3b14-107">语法</span><span class="sxs-lookup"><span data-stu-id="e3b14-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e3b14-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3b14-108">Attributes and Elements</span></span>

<span data-ttu-id="e3b14-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="e3b14-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e3b14-110">特性</span><span class="sxs-lookup"><span data-stu-id="e3b14-110">Attributes</span></span>

<span data-ttu-id="e3b14-111">无。</span><span class="sxs-lookup"><span data-stu-id="e3b14-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e3b14-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e3b14-112">Child Elements</span></span>

<span data-ttu-id="e3b14-113">无。</span><span class="sxs-lookup"><span data-stu-id="e3b14-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e3b14-114">父元素</span><span class="sxs-lookup"><span data-stu-id="e3b14-114">Parent Elements</span></span>

|<span data-ttu-id="e3b14-115">元素</span><span class="sxs-lookup"><span data-stu-id="e3b14-115">Element</span></span>|<span data-ttu-id="e3b14-116">描述</span><span class="sxs-lookup"><span data-stu-id="e3b14-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e3b14-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e3b14-117">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="e3b14-118">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="e3b14-118">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e3b14-119">文本值</span><span class="sxs-lookup"><span data-stu-id="e3b14-119">Text Value</span></span>

<span data-ttu-id="e3b14-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="e3b14-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3b14-121">备注</span><span class="sxs-lookup"><span data-stu-id="e3b14-121">Remarks</span></span>

<span data-ttu-id="e3b14-122">每个控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="e3b14-122">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="e3b14-123">有关自定义控件视图组件的详细信息，请参阅 [创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="e3b14-123">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e3b14-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3b14-124">See Also</span></span>

[<span data-ttu-id="e3b14-125">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="e3b14-125">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="e3b14-126">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="e3b14-126">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="e3b14-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e3b14-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
