---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for WideEntry (Format)
description: TypeName Element for EntrySelectedBy for WideEntry (Format)
ms.openlocfilehash: 2e0facd6ff7c6fec96dabf488449a8502429bcff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654796"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="eeb0e-103">TypeName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="eeb0e-103">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="eeb0e-104">为定义指定 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-104">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="eeb0e-105">只要显示此对象，就会使用定义。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-105">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="eeb0e-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (WideEntry) 格式</span><span class="sxs-lookup"><span data-stu-id="eeb0e-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="eeb0e-107">语法</span><span class="sxs-lookup"><span data-stu-id="eeb0e-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eeb0e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eeb0e-108">Attributes and Elements</span></span>

<span data-ttu-id="eeb0e-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-109">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="eeb0e-110">特性</span><span class="sxs-lookup"><span data-stu-id="eeb0e-110">Attributes</span></span>

<span data-ttu-id="eeb0e-111">无。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="eeb0e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="eeb0e-112">Child Elements</span></span>

<span data-ttu-id="eeb0e-113">无。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eeb0e-114">父元素</span><span class="sxs-lookup"><span data-stu-id="eeb0e-114">Parent Elements</span></span>

|<span data-ttu-id="eeb0e-115">元素</span><span class="sxs-lookup"><span data-stu-id="eeb0e-115">Element</span></span>|<span data-ttu-id="eeb0e-116">描述</span><span class="sxs-lookup"><span data-stu-id="eeb0e-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eeb0e-117">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="eeb0e-117">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="eeb0e-118">定义使用此宽项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-118">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="eeb0e-119">文本值</span><span class="sxs-lookup"><span data-stu-id="eeb0e-119">Text Value</span></span>

<span data-ttu-id="eeb0e-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="eeb0e-121">备注</span><span class="sxs-lookup"><span data-stu-id="eeb0e-121">Remarks</span></span>

<span data-ttu-id="eeb0e-122">每个宽条目都必须指定一个或多个 .NET 类型、选择集或必须为要使用的定义提供的选择条件。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-122">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="eeb0e-123">有关大视图的其他组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="eeb0e-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eeb0e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eeb0e-124">See Also</span></span>

[<span data-ttu-id="eeb0e-125">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="eeb0e-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="eeb0e-126">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="eeb0e-126">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="eeb0e-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="eeb0e-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
