---
ms.date: 09/13/2016
ms.topic: reference
title: Label Element for TableColumnHeader for TableControl (Format)
description: Label Element for TableColumnHeader for TableControl (Format)
ms.openlocfilehash: fe4c209903c04e683b44e2bdcbf381adb6874ace
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667787"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="dbb82-103">Label Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb82-103">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="dbb82-104">定义在列顶部显示的标签。</span><span class="sxs-lookup"><span data-stu-id="dbb82-104">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="dbb82-105">定义表视图时使用此元素。</span><span class="sxs-lookup"><span data-stu-id="dbb82-105">This element is used when defining a table view.</span></span>

<span data-ttu-id="dbb82-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (TableColumnHeader 的 TableControl) 格式 (TableHeaders TableControl 的 TableColumnHeader 元素) TableControl (格式) </span><span class="sxs-lookup"><span data-stu-id="dbb82-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dbb82-107">语法</span><span class="sxs-lookup"><span data-stu-id="dbb82-107">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="dbb82-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dbb82-108">Attributes and Elements</span></span>

<span data-ttu-id="dbb82-109">以下各节描述了元素的属性、子元素和父元素 `Label` 。</span><span class="sxs-lookup"><span data-stu-id="dbb82-109">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="dbb82-110">每个列只允许有一个标签。</span><span class="sxs-lookup"><span data-stu-id="dbb82-110">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="dbb82-111">特性</span><span class="sxs-lookup"><span data-stu-id="dbb82-111">Attributes</span></span>

<span data-ttu-id="dbb82-112">无。</span><span class="sxs-lookup"><span data-stu-id="dbb82-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dbb82-113">子元素</span><span class="sxs-lookup"><span data-stu-id="dbb82-113">Child Elements</span></span>

<span data-ttu-id="dbb82-114">无。</span><span class="sxs-lookup"><span data-stu-id="dbb82-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dbb82-115">父元素</span><span class="sxs-lookup"><span data-stu-id="dbb82-115">Parent Elements</span></span>

|<span data-ttu-id="dbb82-116">元素</span><span class="sxs-lookup"><span data-stu-id="dbb82-116">Element</span></span>|<span data-ttu-id="dbb82-117">描述</span><span class="sxs-lookup"><span data-stu-id="dbb82-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dbb82-118">TableControl (格式的 TableHeaders 的 TableColumnHeader 元素) </span><span class="sxs-lookup"><span data-stu-id="dbb82-118">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="dbb82-119">定义表中某一列的数据的标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="dbb82-119">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="dbb82-120">文本值</span><span class="sxs-lookup"><span data-stu-id="dbb82-120">Text Value</span></span>

<span data-ttu-id="dbb82-121">指定在表的列顶部显示的文本。</span><span class="sxs-lookup"><span data-stu-id="dbb82-121">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="dbb82-122">列标签没有受限制的字符。</span><span class="sxs-lookup"><span data-stu-id="dbb82-122">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbb82-123">备注</span><span class="sxs-lookup"><span data-stu-id="dbb82-123">Remarks</span></span>

<span data-ttu-id="dbb82-124">如果未指定标签，则使用在行中显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="dbb82-124">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="dbb82-125">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb82-125">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="dbb82-126">示例</span><span class="sxs-lookup"><span data-stu-id="dbb82-126">Example</span></span>

<span data-ttu-id="dbb82-127">此示例显示了一个 `TableColumnHeader` 其标签为 "Column 1" 的元素。</span><span class="sxs-lookup"><span data-stu-id="dbb82-127">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="dbb82-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbb82-128">See Also</span></span>

[<span data-ttu-id="dbb82-129">创建表视图</span><span class="sxs-lookup"><span data-stu-id="dbb82-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="dbb82-130">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="dbb82-130">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="dbb82-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="dbb82-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
