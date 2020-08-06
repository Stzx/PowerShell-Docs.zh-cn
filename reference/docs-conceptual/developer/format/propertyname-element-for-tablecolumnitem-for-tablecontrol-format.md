---
title: 用于 TableControl (Format) 的 TableColumnItem 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bf267eeb83aef59abea2d945af12e849252309c8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772971"
---
# <a name="propertyname-element-for-tablecolumnitem-for-tablecontrol-format"></a><span data-ttu-id="e8c67-102">PropertyName Element for TableColumnItem for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e8c67-102">PropertyName Element for TableColumnItem for TableControl (Format)</span></span>

<span data-ttu-id="e8c67-103">指定其值显示在行的列中的属性。</span><span class="sxs-lookup"><span data-stu-id="e8c67-103">Specifies the property whose value is displayed in the column of the row.</span></span>

<span data-ttu-id="e8c67-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) TableControl 元素 (格式) TableRowEntries 元素 (格式) TableRowEntry 元素 (格式) TableColumnItems 元素 (格式) TableColumnItem (格式) TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="e8c67-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) TableColumnItems Element (Format) TableColumnItem Element (Format) PropertyName Element for TableColumnItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e8c67-105">语法</span><span class="sxs-lookup"><span data-stu-id="e8c67-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8c67-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e8c67-106">Attributes and Elements</span></span>

<span data-ttu-id="e8c67-107">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="e8c67-107">The following sections describe attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e8c67-108">特性</span><span class="sxs-lookup"><span data-stu-id="e8c67-108">Attributes</span></span>

<span data-ttu-id="e8c67-109">无。</span><span class="sxs-lookup"><span data-stu-id="e8c67-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e8c67-110">子元素</span><span class="sxs-lookup"><span data-stu-id="e8c67-110">Child Elements</span></span>

<span data-ttu-id="e8c67-111">无。</span><span class="sxs-lookup"><span data-stu-id="e8c67-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e8c67-112">父元素</span><span class="sxs-lookup"><span data-stu-id="e8c67-112">Parent Elements</span></span>

|<span data-ttu-id="e8c67-113">元素</span><span class="sxs-lookup"><span data-stu-id="e8c67-113">Element</span></span>|<span data-ttu-id="e8c67-114">说明</span><span class="sxs-lookup"><span data-stu-id="e8c67-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e8c67-115">TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="e8c67-115">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)|<span data-ttu-id="e8c67-116">定义其值显示在行的列中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="e8c67-116">Defines the property or script whose value is displayed in the column of the row.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e8c67-117">文本值</span><span class="sxs-lookup"><span data-stu-id="e8c67-117">Text Value</span></span>

<span data-ttu-id="e8c67-118">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="e8c67-118">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8c67-119">备注</span><span class="sxs-lookup"><span data-stu-id="e8c67-119">Remarks</span></span>

<span data-ttu-id="e8c67-120">有关表视图的组件的详细信息，请参阅[创建表视图](./creating-a-table-view.md)。</span><span class="sxs-lookup"><span data-stu-id="e8c67-120">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e8c67-121">示例</span><span class="sxs-lookup"><span data-stu-id="e8c67-121">Example</span></span>

<span data-ttu-id="e8c67-122">此示例演示一个 `TableColumnItem` 元素，该元素指定了 `Status` [system.object](/dotnet/api/System.Diagnostics.Process)对象的属性。</span><span class="sxs-lookup"><span data-stu-id="e8c67-122">This example shows a `TableColumnItem` element that specifies the `Status` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableColumnItem>
   <Alignment>Centered</Alignment>
  <PropertyName>Status</PropertyName>
</TableColumnItem>

```

## <a name="see-also"></a><span data-ttu-id="e8c67-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8c67-123">See Also</span></span>

[<span data-ttu-id="e8c67-124">创建表视图</span><span class="sxs-lookup"><span data-stu-id="e8c67-124">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="e8c67-125">TableColumnItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="e8c67-125">TableColumnItem Element (Format)</span></span>](./tablecolumnitem-element-for-tablecolumnitems-for-tablecontrol-format.md)

[<span data-ttu-id="e8c67-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e8c67-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
