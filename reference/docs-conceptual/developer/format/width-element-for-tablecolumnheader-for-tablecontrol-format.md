---
ms.date: 09/13/2016
ms.topic: reference
title: Width Element for TableColumnHeader for TableControl (Format)
description: Width Element for TableColumnHeader for TableControl (Format)
ms.openlocfilehash: bde84f1d33b3d6b3b8c4462f870f978611cb434b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658252"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="f50f5-103">Width Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f50f5-103">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="f50f5-104">定义列的字符)  (的宽度。</span><span class="sxs-lookup"><span data-stu-id="f50f5-104">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="f50f5-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (TableColumnHeader) 格式 (TableHeaders) 格式 (Width 元素 TableControl) 格式</span><span class="sxs-lookup"><span data-stu-id="f50f5-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f50f5-106">语法</span><span class="sxs-lookup"><span data-stu-id="f50f5-106">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f50f5-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f50f5-107">Attributes and Elements</span></span>

<span data-ttu-id="f50f5-108">以下各节描述 `Width` 定义列标题时使用的元素的属性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f50f5-108">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="f50f5-109">特性</span><span class="sxs-lookup"><span data-stu-id="f50f5-109">Attributes</span></span>

<span data-ttu-id="f50f5-110">无。</span><span class="sxs-lookup"><span data-stu-id="f50f5-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f50f5-111">子元素</span><span class="sxs-lookup"><span data-stu-id="f50f5-111">Child Elements</span></span>

<span data-ttu-id="f50f5-112">无。</span><span class="sxs-lookup"><span data-stu-id="f50f5-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f50f5-113">父元素</span><span class="sxs-lookup"><span data-stu-id="f50f5-113">Parent Elements</span></span>

|<span data-ttu-id="f50f5-114">元素</span><span class="sxs-lookup"><span data-stu-id="f50f5-114">Element</span></span>|<span data-ttu-id="f50f5-115">描述</span><span class="sxs-lookup"><span data-stu-id="f50f5-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f50f5-116">TableControl (格式的 TableHeaders 的 TableColumnHeader 元素) </span><span class="sxs-lookup"><span data-stu-id="f50f5-116">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="f50f5-117">定义表的列的数据的标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="f50f5-117">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f50f5-118">文本值</span><span class="sxs-lookup"><span data-stu-id="f50f5-118">Text Value</span></span>

<span data-ttu-id="f50f5-119">如果出现这种情况，请指定一个大于所显示属性值长度的 (字符) 宽度。</span><span class="sxs-lookup"><span data-stu-id="f50f5-119">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="f50f5-120">备注</span><span class="sxs-lookup"><span data-stu-id="f50f5-120">Remarks</span></span>

<span data-ttu-id="f50f5-121">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f50f5-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f50f5-122">示例</span><span class="sxs-lookup"><span data-stu-id="f50f5-122">Example</span></span>

<span data-ttu-id="f50f5-123">下面的示例演示一个 `TableColumnHeader` 宽度为16个字符的元素。</span><span class="sxs-lookup"><span data-stu-id="f50f5-123">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="f50f5-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f50f5-124">See Also</span></span>

[<span data-ttu-id="f50f5-125">创建表视图</span><span class="sxs-lookup"><span data-stu-id="f50f5-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="f50f5-126">TableControl (格式的 TableHeader 的 TableColumnHeader 元素) </span><span class="sxs-lookup"><span data-stu-id="f50f5-126">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="f50f5-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f50f5-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
