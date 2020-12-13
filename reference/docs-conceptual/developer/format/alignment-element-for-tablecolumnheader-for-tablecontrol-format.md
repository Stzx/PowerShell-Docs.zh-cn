---
ms.date: 09/13/2016
ms.topic: reference
title: Alignment Element for TableColumnHeader for TableControl (Format)
description: Alignment Element for TableColumnHeader for TableControl (Format)
ms.openlocfilehash: cf8b90c12c28951283b5870186e2c88d427318a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666818"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="c0612-103">Alignment Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c0612-103">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="c0612-104">定义列标题中的数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="c0612-104">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="c0612-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (格式) TableColumnHeader 元素 (格式) TableColumnHeader (格式的对齐元素) </span><span class="sxs-lookup"><span data-stu-id="c0612-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c0612-106">语法</span><span class="sxs-lookup"><span data-stu-id="c0612-106">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c0612-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c0612-107">Attributes and Elements</span></span>

<span data-ttu-id="c0612-108">以下各节描述了元素的属性、子元素和父元素 `Alignment` 。</span><span class="sxs-lookup"><span data-stu-id="c0612-108">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c0612-109">特性</span><span class="sxs-lookup"><span data-stu-id="c0612-109">Attributes</span></span>

<span data-ttu-id="c0612-110">无。</span><span class="sxs-lookup"><span data-stu-id="c0612-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c0612-111">子元素</span><span class="sxs-lookup"><span data-stu-id="c0612-111">Child Elements</span></span>

<span data-ttu-id="c0612-112">无。</span><span class="sxs-lookup"><span data-stu-id="c0612-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c0612-113">父元素</span><span class="sxs-lookup"><span data-stu-id="c0612-113">Parent Elements</span></span>

|<span data-ttu-id="c0612-114">元素</span><span class="sxs-lookup"><span data-stu-id="c0612-114">Element</span></span>|<span data-ttu-id="c0612-115">描述</span><span class="sxs-lookup"><span data-stu-id="c0612-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c0612-116">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c0612-116">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="c0612-117">定义表中某一列的数据的标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="c0612-117">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c0612-118">文本值</span><span class="sxs-lookup"><span data-stu-id="c0612-118">Text Value</span></span>

<span data-ttu-id="c0612-119">指定下列值之一。</span><span class="sxs-lookup"><span data-stu-id="c0612-119">Specify one of the following values.</span></span> <span data-ttu-id="c0612-120">这些值不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c0612-120">These values are not case-sensitive.</span></span>

<span data-ttu-id="c0612-121">如果未指定此元素，则在左侧的列中将显示数据左对齐。</span><span class="sxs-lookup"><span data-stu-id="c0612-121">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="c0612-122">右对齐显示在右侧列中的数据。</span><span class="sxs-lookup"><span data-stu-id="c0612-122">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="c0612-123">居中将列中显示的数据居中。</span><span class="sxs-lookup"><span data-stu-id="c0612-123">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="c0612-124">备注</span><span class="sxs-lookup"><span data-stu-id="c0612-124">Remarks</span></span>

<span data-ttu-id="c0612-125">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="c0612-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="c0612-126">示例</span><span class="sxs-lookup"><span data-stu-id="c0612-126">Example</span></span>

<span data-ttu-id="c0612-127">此示例演示一个 `TableColumnHeader` 元素，其数据在左侧对齐。</span><span class="sxs-lookup"><span data-stu-id="c0612-127">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="c0612-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0612-128">See Also</span></span>

[<span data-ttu-id="c0612-129">创建表视图</span><span class="sxs-lookup"><span data-stu-id="c0612-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c0612-130">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c0612-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="c0612-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="c0612-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
