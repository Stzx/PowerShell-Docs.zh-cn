---
ms.date: 09/13/2016
ms.topic: reference
title: Label Element for ListItem for ListControl (Format)
description: Label Element for ListItem for ListControl (Format)
ms.openlocfilehash: 01ff34c4129abe2c76a0a21794e756b77bff12bf
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666648"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="6bf72-103">Label Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6bf72-103">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="6bf72-104">指定在行的属性或脚本值左侧显示的标签。</span><span class="sxs-lookup"><span data-stu-id="6bf72-104">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="6bf72-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry) 格式 (ListControl ListItems 的 ListEntry 元素) ListControl 的 ListItems 元素 (ListControl) 格式 (ListControl) 格式 (</span><span class="sxs-lookup"><span data-stu-id="6bf72-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6bf72-106">语法</span><span class="sxs-lookup"><span data-stu-id="6bf72-106">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6bf72-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6bf72-107">Attributes and Elements</span></span>

<span data-ttu-id="6bf72-108">以下各节描述了元素的属性、子元素和父元素 `Label` 。</span><span class="sxs-lookup"><span data-stu-id="6bf72-108">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6bf72-109">特性</span><span class="sxs-lookup"><span data-stu-id="6bf72-109">Attributes</span></span>

<span data-ttu-id="6bf72-110">无。</span><span class="sxs-lookup"><span data-stu-id="6bf72-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6bf72-111">子元素</span><span class="sxs-lookup"><span data-stu-id="6bf72-111">Child Elements</span></span>

<span data-ttu-id="6bf72-112">无。</span><span class="sxs-lookup"><span data-stu-id="6bf72-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6bf72-113">父元素</span><span class="sxs-lookup"><span data-stu-id="6bf72-113">Parent Elements</span></span>

|<span data-ttu-id="6bf72-114">元素</span><span class="sxs-lookup"><span data-stu-id="6bf72-114">Element</span></span>|<span data-ttu-id="6bf72-115">描述</span><span class="sxs-lookup"><span data-stu-id="6bf72-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6bf72-116">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="6bf72-116">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="6bf72-117">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="6bf72-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="6bf72-118">文本值</span><span class="sxs-lookup"><span data-stu-id="6bf72-118">Text Value</span></span>

<span data-ttu-id="6bf72-119">指定要在属性或脚本值左侧显示的标签。</span><span class="sxs-lookup"><span data-stu-id="6bf72-119">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="6bf72-120">备注</span><span class="sxs-lookup"><span data-stu-id="6bf72-120">Remarks</span></span>

<span data-ttu-id="6bf72-121">如果未指定标签，则显示属性或脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="6bf72-121">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="6bf72-122">有关在列表视图中使用标签的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="6bf72-122">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="6bf72-123">示例</span><span class="sxs-lookup"><span data-stu-id="6bf72-123">Example</span></span>

<span data-ttu-id="6bf72-124">下面的示例演示如何向行中添加标签。</span><span class="sxs-lookup"><span data-stu-id="6bf72-124">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="6bf72-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bf72-125">See Also</span></span>

[<span data-ttu-id="6bf72-126">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="6bf72-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="6bf72-127"> (格式的) 元素元素 </span><span class="sxs-lookup"><span data-stu-id="6bf72-127">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="6bf72-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="6bf72-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
