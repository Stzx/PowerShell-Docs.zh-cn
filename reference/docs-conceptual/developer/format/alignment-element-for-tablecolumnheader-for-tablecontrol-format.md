---
title: TableControl 的 TableColumnHeader 的对齐元素 (格式) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1bf395b84af90d725c14b2f0ef569f72b5fcc613
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783919"
---
# <a name="alignment-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="154aa-102">Alignment Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="154aa-102">Alignment Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="154aa-103">定义列标题中的数据的显示方式。</span><span class="sxs-lookup"><span data-stu-id="154aa-103">Defines how the data in a column header is displayed.</span></span>

<span data-ttu-id="154aa-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (格式) TableColumnHeader 元素 (格式) TableColumnHeader (格式的对齐元素) </span><span class="sxs-lookup"><span data-stu-id="154aa-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element (Format) TableColumnHeader Element (Format) Alignment Element for TableColumnHeader (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="154aa-105">语法</span><span class="sxs-lookup"><span data-stu-id="154aa-105">Syntax</span></span>

```xml
<Alignment>AlignmentType</Alignment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="154aa-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="154aa-106">Attributes and Elements</span></span>

<span data-ttu-id="154aa-107">以下各节描述了元素的属性、子元素和父元素 `Alignment` 。</span><span class="sxs-lookup"><span data-stu-id="154aa-107">The following sections describe the attributes, child elements, and parent element of the `Alignment` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="154aa-108">特性</span><span class="sxs-lookup"><span data-stu-id="154aa-108">Attributes</span></span>

<span data-ttu-id="154aa-109">无。</span><span class="sxs-lookup"><span data-stu-id="154aa-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="154aa-110">子元素</span><span class="sxs-lookup"><span data-stu-id="154aa-110">Child Elements</span></span>

<span data-ttu-id="154aa-111">无。</span><span class="sxs-lookup"><span data-stu-id="154aa-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="154aa-112">父元素</span><span class="sxs-lookup"><span data-stu-id="154aa-112">Parent Elements</span></span>

|<span data-ttu-id="154aa-113">元素</span><span class="sxs-lookup"><span data-stu-id="154aa-113">Element</span></span>|<span data-ttu-id="154aa-114">描述</span><span class="sxs-lookup"><span data-stu-id="154aa-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="154aa-115">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="154aa-115">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="154aa-116">定义表中某一列的数据的标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="154aa-116">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="154aa-117">文本值</span><span class="sxs-lookup"><span data-stu-id="154aa-117">Text Value</span></span>

<span data-ttu-id="154aa-118">指定下列值之一。</span><span class="sxs-lookup"><span data-stu-id="154aa-118">Specify one of the following values.</span></span> <span data-ttu-id="154aa-119">这些值不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="154aa-119">These values are not case-sensitive.</span></span>

<span data-ttu-id="154aa-120">如果未指定此元素，则在左侧的列中将显示数据左对齐。</span><span class="sxs-lookup"><span data-stu-id="154aa-120">Left Aligns the data displayed in the column on the left This is the default if this element is not specified.</span></span>

<span data-ttu-id="154aa-121">右对齐显示在右侧列中的数据。</span><span class="sxs-lookup"><span data-stu-id="154aa-121">Right Aligns the data displayed in the column on the right.</span></span>

<span data-ttu-id="154aa-122">居中将列中显示的数据居中。</span><span class="sxs-lookup"><span data-stu-id="154aa-122">Center Centers the data displayed in the column.</span></span>

## <a name="remarks"></a><span data-ttu-id="154aa-123">备注</span><span class="sxs-lookup"><span data-stu-id="154aa-123">Remarks</span></span>

<span data-ttu-id="154aa-124">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="154aa-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="154aa-125">示例</span><span class="sxs-lookup"><span data-stu-id="154aa-125">Example</span></span>

<span data-ttu-id="154aa-126">此示例演示一个 `TableColumnHeader` 元素，其数据在左侧对齐。</span><span class="sxs-lookup"><span data-stu-id="154aa-126">This example shows a `TableColumnHeader` element whose data is aligned on the left.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="154aa-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="154aa-127">See Also</span></span>

[<span data-ttu-id="154aa-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="154aa-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="154aa-129">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="154aa-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="154aa-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="154aa-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
