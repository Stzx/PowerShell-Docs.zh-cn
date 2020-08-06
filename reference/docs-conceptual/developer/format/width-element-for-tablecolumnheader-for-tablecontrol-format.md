---
title: TableControl (Format) 的 Width 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9540d3d351041ad7cb98a21bb360ebea7eca117
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779907"
---
# <a name="width-element-for-tablecolumnheader-for-tablecontrol-format"></a><span data-ttu-id="096ba-102">Width Element for TableColumnHeader for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="096ba-102">Width Element for TableColumnHeader for TableControl (Format)</span></span>

<span data-ttu-id="096ba-103">定义列的字符)  (的宽度。</span><span class="sxs-lookup"><span data-stu-id="096ba-103">Defines the width (in characters) of a column.</span></span>

<span data-ttu-id="096ba-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableHeaders 元素 (TableColumnHeader) 格式 (TableHeaders) 格式 (Width 元素 TableControl) 格式</span><span class="sxs-lookup"><span data-stu-id="096ba-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableHeaders Element for TableControl (Format) TableColumnHeader Element TableHeaders for TableControl (Format) Width Element for TableColumnHeader for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="096ba-105">语法</span><span class="sxs-lookup"><span data-stu-id="096ba-105">Syntax</span></span>

```xml
<Width>NumberOfCharacters</Width>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="096ba-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="096ba-106">Attributes and Elements</span></span>

<span data-ttu-id="096ba-107">以下各节描述 `Width` 定义列标题时使用的元素的属性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="096ba-107">The following sections describe the attributes, child elements, and parent element of the `Width` element used when defining column headers.</span></span>

### <a name="attributes"></a><span data-ttu-id="096ba-108">特性</span><span class="sxs-lookup"><span data-stu-id="096ba-108">Attributes</span></span>

<span data-ttu-id="096ba-109">无。</span><span class="sxs-lookup"><span data-stu-id="096ba-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="096ba-110">子元素</span><span class="sxs-lookup"><span data-stu-id="096ba-110">Child Elements</span></span>

<span data-ttu-id="096ba-111">无。</span><span class="sxs-lookup"><span data-stu-id="096ba-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="096ba-112">父元素</span><span class="sxs-lookup"><span data-stu-id="096ba-112">Parent Elements</span></span>

|<span data-ttu-id="096ba-113">元素</span><span class="sxs-lookup"><span data-stu-id="096ba-113">Element</span></span>|<span data-ttu-id="096ba-114">说明</span><span class="sxs-lookup"><span data-stu-id="096ba-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="096ba-115">TableControl (格式的 TableHeaders 的 TableColumnHeader 元素) </span><span class="sxs-lookup"><span data-stu-id="096ba-115">TableColumnHeader Element for TableHeaders for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)|<span data-ttu-id="096ba-116">定义表的列的数据的标签、宽度和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="096ba-116">Defines a label, width, and alignment of the data for a column of the table.</span></span>|

## <a name="text-value"></a><span data-ttu-id="096ba-117">文本值</span><span class="sxs-lookup"><span data-stu-id="096ba-117">Text Value</span></span>

<span data-ttu-id="096ba-118">如果出现这种情况，请指定一个大于所显示属性值长度的 (字符) 宽度。</span><span class="sxs-lookup"><span data-stu-id="096ba-118">When at all possible, specify a width (in characters) that is greater than the length of the displayed property values.</span></span>

## <a name="remarks"></a><span data-ttu-id="096ba-119">备注</span><span class="sxs-lookup"><span data-stu-id="096ba-119">Remarks</span></span>

<span data-ttu-id="096ba-120">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="096ba-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="096ba-121">示例</span><span class="sxs-lookup"><span data-stu-id="096ba-121">Example</span></span>

<span data-ttu-id="096ba-122">下面的示例演示一个 `TableColumnHeader` 宽度为16个字符的元素。</span><span class="sxs-lookup"><span data-stu-id="096ba-122">The following example shows a `TableColumnHeader` element whose width is 16 characters.</span></span>

```xml
<TableColumnHeader>
  <Label>Column 1</Label)
  <Width>16</Width>
  <Alignment>Left</Alignment>
</TableColumnHeader>
```

## <a name="see-also"></a><span data-ttu-id="096ba-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="096ba-123">See Also</span></span>

[<span data-ttu-id="096ba-124">创建表视图</span><span class="sxs-lookup"><span data-stu-id="096ba-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="096ba-125">TableControl (格式的 TableHeader 的 TableColumnHeader 元素) </span><span class="sxs-lookup"><span data-stu-id="096ba-125">TableColumnHeader Element for TableHeader for TableControl (Format)</span></span>](./tablecolumnheader-element-format.md)

[<span data-ttu-id="096ba-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="096ba-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
