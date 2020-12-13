---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for EntrySelectedBy for TableControl (Format)
description: TypeName Element for EntrySelectedBy for TableControl (Format)
ms.openlocfilehash: 5a9f5cda1810d461d19ffb48a1cfa2d41f87ca96
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651424"
---
# <a name="typename-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="80ece-103">TypeName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="80ece-103">TypeName Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="80ece-104">指定使用此表视图项的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="80ece-104">Specifies a .NET type that uses this entry of the table view.</span></span> <span data-ttu-id="80ece-105">对于可为表条目指定的类型数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="80ece-105">There is no limit to the number of types that can be specified for a table entry.</span></span>

<span data-ttu-id="80ece-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) EntrySelectedBy (格式)  (TypeName 元素) 格式</span><span class="sxs-lookup"><span data-stu-id="80ece-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element (Format) TypeName Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="80ece-107">语法</span><span class="sxs-lookup"><span data-stu-id="80ece-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="80ece-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="80ece-108">Attributes and Elements</span></span>

<span data-ttu-id="80ece-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="80ece-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="80ece-110">特性</span><span class="sxs-lookup"><span data-stu-id="80ece-110">Attributes</span></span>

<span data-ttu-id="80ece-111">无。</span><span class="sxs-lookup"><span data-stu-id="80ece-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="80ece-112">子元素</span><span class="sxs-lookup"><span data-stu-id="80ece-112">Child Elements</span></span>

<span data-ttu-id="80ece-113">无。</span><span class="sxs-lookup"><span data-stu-id="80ece-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="80ece-114">父元素</span><span class="sxs-lookup"><span data-stu-id="80ece-114">Parent Elements</span></span>

|<span data-ttu-id="80ece-115">元素</span><span class="sxs-lookup"><span data-stu-id="80ece-115">Element</span></span>|<span data-ttu-id="80ece-116">描述</span><span class="sxs-lookup"><span data-stu-id="80ece-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="80ece-117">EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="80ece-117">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="80ece-118">定义使用此项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="80ece-118">Defines the .NET types that use this entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="80ece-119">文本值</span><span class="sxs-lookup"><span data-stu-id="80ece-119">Text Value</span></span>

<span data-ttu-id="80ece-120">指定 .NET 类型的名称。</span><span class="sxs-lookup"><span data-stu-id="80ece-120">Specify the name of the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="80ece-121">备注</span><span class="sxs-lookup"><span data-stu-id="80ece-121">Remarks</span></span>

<span data-ttu-id="80ece-122">每个列表项必须至少定义一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="80ece-122">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="80ece-123">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="80ece-123">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="80ece-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80ece-124">See Also</span></span>

[<span data-ttu-id="80ece-125">创建表视图</span><span class="sxs-lookup"><span data-stu-id="80ece-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="80ece-126">EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="80ece-126">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="80ece-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="80ece-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
