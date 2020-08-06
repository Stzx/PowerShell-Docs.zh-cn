---
title: 适用于 TableControl (Format) 的 TableColumnHeader 标签元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b7b1d6825d3bca0e36b230415d19c2ac48377a46
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785738"
---
# <a name="label-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="20058-102">Label Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="20058-102">Label Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="20058-103">定义在列顶部显示的标签。</span><span class="sxs-lookup"><span data-stu-id="20058-103">Defines the label that is displayed at the top of a column.</span></span> <span data-ttu-id="20058-104">定义表视图时使用此元素。</span><span class="sxs-lookup"><span data-stu-id="20058-104">This element is used when defining a table view.</span></span>

<span data-ttu-id="20058-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (TableColumnHeader 的 TableControl) 格式 (TableHeaders TableControl 的 TableColumnHeader 元素) TableControl (格式) </span><span class="sxs-lookup"><span data-stu-id="20058-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element for TableHeaders for TableControl (Format) Label Element  for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="20058-106">语法</span><span class="sxs-lookup"><span data-stu-id="20058-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="20058-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="20058-107">Attributes and Elements</span></span>

<span data-ttu-id="20058-108">以下各节描述了元素的属性、子元素和父元素 `Label` 。</span><span class="sxs-lookup"><span data-stu-id="20058-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span> <span data-ttu-id="20058-109">每个列只允许有一个标签。</span><span class="sxs-lookup"><span data-stu-id="20058-109">Only one label is allowed for each column.</span></span>

### <a name="attributes"></a><span data-ttu-id="20058-110">特性</span><span class="sxs-lookup"><span data-stu-id="20058-110">Attributes</span></span>

<span data-ttu-id="20058-111">无。</span><span class="sxs-lookup"><span data-stu-id="20058-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="20058-112">子元素</span><span class="sxs-lookup"><span data-stu-id="20058-112">Child Elements</span></span>

<span data-ttu-id="20058-113">无。</span><span class="sxs-lookup"><span data-stu-id="20058-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="20058-114">父元素</span><span class="sxs-lookup"><span data-stu-id="20058-114">Parent Elements</span></span>

|<span data-ttu-id="20058-115">元素</span><span class="sxs-lookup"><span data-stu-id="20058-115">Element</span></span>|<span data-ttu-id="20058-116">描述</span><span class="sxs-lookup"><span data-stu-id="20058-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="20058-117">TableControl (格式的 TableHeaders 的 TableColumnHeader 元素) </span><span class="sxs-lookup"><span data-stu-id="20058-117">TableColumnHeader Element for TableHeaders for TableControl  (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="20058-118">定义表中某一列的数据的标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="20058-118">Defines a label, the width, and the alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="20058-119">文本值</span><span class="sxs-lookup"><span data-stu-id="20058-119">Text Value</span></span>

<span data-ttu-id="20058-120">指定在表的列顶部显示的文本。</span><span class="sxs-lookup"><span data-stu-id="20058-120">Specify the text that is displayed at the top of the column of the table.</span></span> <span data-ttu-id="20058-121">列标签没有受限制的字符。</span><span class="sxs-lookup"><span data-stu-id="20058-121">There are no restricted characters for the column label.</span></span>

## <a name="remarks"></a><span data-ttu-id="20058-122">备注</span><span class="sxs-lookup"><span data-stu-id="20058-122">Remarks</span></span>

<span data-ttu-id="20058-123">如果未指定标签，则使用在行中显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="20058-123">If no label is specified, the name of the property whose value is displayed in the rows is used.</span></span>

<span data-ttu-id="20058-124">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="20058-124">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="20058-125">示例</span><span class="sxs-lookup"><span data-stu-id="20058-125">Example</span></span>

<span data-ttu-id="20058-126">此示例显示了一个 `TableColumnHeader` 其标签为 "Column 1" 的元素。</span><span class="sxs-lookup"><span data-stu-id="20058-126">This example shows a `TableColumnHeader` element whose label is "Column 1".</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="20058-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20058-127">See Also</span></span>

[<span data-ttu-id="20058-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="20058-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="20058-129">TableColumnHeader Element (Format)</span><span class="sxs-lookup"><span data-stu-id="20058-129">TableColumnHeader Element (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="20058-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="20058-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
