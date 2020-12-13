---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for ListItem for ListControl (Format)
description: PropertyName Element for ListItem for ListControl (Format)
ms.openlocfilehash: 30cd48f9549e1a091776cd5f8395e1a71314ea1b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665968"
---
# <a name="propertyname-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="a2044-103">PropertyName Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a2044-103">PropertyName Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="a2044-104">指定其值显示在列表中的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="a2044-104">Specifies the .NET property whose value is displayed in the list.</span></span>

<span data-ttu-id="a2044-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) ListItems 元素 (格式) 名称 (格式) </span><span class="sxs-lookup"><span data-stu-id="a2044-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) ListItems Element (Format) ListItem Element (Format) PropertyName Element for ListItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a2044-106">语法</span><span class="sxs-lookup"><span data-stu-id="a2044-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a2044-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a2044-107">Attributes and Elements</span></span>

<span data-ttu-id="a2044-108">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="a2044-108">The following sections describe the attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a2044-109">特性</span><span class="sxs-lookup"><span data-stu-id="a2044-109">Attributes</span></span>

<span data-ttu-id="a2044-110">无。</span><span class="sxs-lookup"><span data-stu-id="a2044-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a2044-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a2044-111">Child Elements</span></span>

<span data-ttu-id="a2044-112">无。</span><span class="sxs-lookup"><span data-stu-id="a2044-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a2044-113">父元素</span><span class="sxs-lookup"><span data-stu-id="a2044-113">Parent Elements</span></span>

|<span data-ttu-id="a2044-114">元素</span><span class="sxs-lookup"><span data-stu-id="a2044-114">Element</span></span>|<span data-ttu-id="a2044-115">描述</span><span class="sxs-lookup"><span data-stu-id="a2044-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a2044-116"> (格式的) 元素元素 </span><span class="sxs-lookup"><span data-stu-id="a2044-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="a2044-117">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="a2044-117">Defines the property or script whose value is displayed in the row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a2044-118">文本值</span><span class="sxs-lookup"><span data-stu-id="a2044-118">Text Value</span></span>

<span data-ttu-id="a2044-119">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="a2044-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2044-120">备注</span><span class="sxs-lookup"><span data-stu-id="a2044-120">Remarks</span></span>

<span data-ttu-id="a2044-121">如果指定此元素，则不能指定 [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="a2044-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="a2044-122">除了显示属性值以外，还可以指定值的标签或可用于更改值显示的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="a2044-122">In addition to displaying the property value, you can also specify a label for the value or a format string that can be used to change the display of the value.</span></span> <span data-ttu-id="a2044-123">有关在列表视图中指定数据的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="a2044-123">For more information about specifying data in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a2044-124">示例</span><span class="sxs-lookup"><span data-stu-id="a2044-124">Example</span></span>

<span data-ttu-id="a2044-125">下面的示例演示如何指定显示其值的标签和属性。</span><span class="sxs-lookup"><span data-stu-id="a2044-125">The following example shows how to specify the label and property whose value is displayed.</span></span>

```xml
ListItem>
  <Label>NameOfProperty</Label>
  <PropertyName>.NetTypeProperty</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="a2044-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2044-126">See Also</span></span>

[<span data-ttu-id="a2044-127">ScriptBlock Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a2044-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="a2044-128">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="a2044-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a2044-129">ListControl (格式的元素) </span><span class="sxs-lookup"><span data-stu-id="a2044-129">ListItem Element for ListControl(Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="a2044-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="a2044-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
