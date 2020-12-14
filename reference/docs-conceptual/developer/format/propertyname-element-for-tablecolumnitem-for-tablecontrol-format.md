---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for TableColumnItem for TableControl (Format)
description: PropertyName Element for TableColumnItem for TableControl (Format)
ms.openlocfilehash: e83bbdb96d2755013cb9fe065cb98731ba44917f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665577"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="3626a-103">PropertyName Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="3626a-103">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="3626a-104">指定其值显示在行的列中的属性。</span><span class="sxs-lookup"><span data-stu-id="3626a-104">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="3626a-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) TableColumnItems 元素 (格式) TableColumnItem (格式) TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3626a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3626a-106">语法</span><span class="sxs-lookup"><span data-stu-id="3626a-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3626a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3626a-107">Attributes and Elements</span></span>

<span data-ttu-id="3626a-108">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="3626a-108">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3626a-109">特性</span><span class="sxs-lookup"><span data-stu-id="3626a-109">Attributes</span></span>

<span data-ttu-id="3626a-110">无。</span><span class="sxs-lookup"><span data-stu-id="3626a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3626a-111">子元素</span><span class="sxs-lookup"><span data-stu-id="3626a-111">Child Elements</span></span>

<span data-ttu-id="3626a-112">无。</span><span class="sxs-lookup"><span data-stu-id="3626a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3626a-113">父元素</span><span class="sxs-lookup"><span data-stu-id="3626a-113">Parent Elements</span></span>

|<span data-ttu-id="3626a-114">元素</span><span class="sxs-lookup"><span data-stu-id="3626a-114">Element</span></span>|<span data-ttu-id="3626a-115">描述</span><span class="sxs-lookup"><span data-stu-id="3626a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3626a-116">TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3626a-116">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="3626a-117">定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="3626a-117">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="3626a-118">文本值</span><span class="sxs-lookup"><span data-stu-id="3626a-118">Text Value</span></span>

<span data-ttu-id="3626a-119">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="3626a-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="3626a-120">备注</span><span class="sxs-lookup"><span data-stu-id="3626a-120">Remarks</span></span>

<span data-ttu-id="3626a-121">有关表视图的组件的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="3626a-121">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="3626a-122">示例</span><span class="sxs-lookup"><span data-stu-id="3626a-122">Example</span></span>

<span data-ttu-id="3626a-123">此示例演示一个 `TableColumnItem` 元素，该元素指定了 `Status` [system.object](/dotnet/api/System.Diagnostics.Process) 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="3626a-123">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="3626a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3626a-124">See Also</span></span>

[<span data-ttu-id="3626a-125">创建表视图</span><span class="sxs-lookup"><span data-stu-id="3626a-125">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="3626a-126">TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="3626a-126">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="3626a-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3626a-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
