---
ms.date: 09/13/2016
ms.topic: reference
title: ListItems Element for ListEntry for ListControl (Format)
description: ListItems Element for ListEntry for ListControl (Format)
ms.openlocfilehash: 1553c81bc559020223a3c1fea10336baf017c9a0
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666529"
---
# <a name="listitems-element-for-listentry-for-listcontrol-format"></a><span data-ttu-id="37093-103">ListItems Element for ListEntry for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="37093-103">ListItems Element for ListEntry for ListControl (Format)</span></span>

<span data-ttu-id="37093-104">定义其值显示在列表视图的行中的属性和脚本。</span><span class="sxs-lookup"><span data-stu-id="37093-104">Defines the properties and scripts whose values are displayed in the rows of the list view.</span></span>

<span data-ttu-id="37093-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素对于列表控件 (格式) ListControl (格式) ListItems 元素 (ListControl) 格式</span><span class="sxs-lookup"><span data-stu-id="37093-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for List Control (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="37093-106">语法</span><span class="sxs-lookup"><span data-stu-id="37093-106">Syntax</span></span>

```xml
<ListItems>
  <ListItem>...</ListItem>
</ListItems>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="37093-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="37093-107">Attributes and Elements</span></span>

<span data-ttu-id="37093-108">以下各节描述了元素的属性、子元素和父元素 `ListItems` 。</span><span class="sxs-lookup"><span data-stu-id="37093-108">The following sections describe the attributes, child elements, and parent element of the `ListItems` element.</span></span> <span data-ttu-id="37093-109">对于可以指定的子元素数没有限制。</span><span class="sxs-lookup"><span data-stu-id="37093-109">There is no limit to the number of child elements that can be specified.</span></span> <span data-ttu-id="37093-110">子元素的顺序定义值在列表视图中的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="37093-110">The order of the child elements defines the order that values are displayed in the list view.</span></span>

### <a name="attributes"></a><span data-ttu-id="37093-111">特性</span><span class="sxs-lookup"><span data-stu-id="37093-111">Attributes</span></span>

<span data-ttu-id="37093-112">无。</span><span class="sxs-lookup"><span data-stu-id="37093-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="37093-113">子元素</span><span class="sxs-lookup"><span data-stu-id="37093-113">Child Elements</span></span>

|<span data-ttu-id="37093-114">元素</span><span class="sxs-lookup"><span data-stu-id="37093-114">Element</span></span>|<span data-ttu-id="37093-115">描述</span><span class="sxs-lookup"><span data-stu-id="37093-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="37093-116">ListControl (格式的元素) </span><span class="sxs-lookup"><span data-stu-id="37093-116">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="37093-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="37093-117">Required element.</span></span><br /><br /> <span data-ttu-id="37093-118">定义其值由列表视图显示的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="37093-118">Defines the property or script whose value is displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="37093-119">父元素</span><span class="sxs-lookup"><span data-stu-id="37093-119">Parent Elements</span></span>

|<span data-ttu-id="37093-120">元素</span><span class="sxs-lookup"><span data-stu-id="37093-120">Element</span></span>|<span data-ttu-id="37093-121">描述</span><span class="sxs-lookup"><span data-stu-id="37093-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="37093-122">ListEntry Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="37093-122">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="37093-123">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="37093-123">Provides a definition of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="37093-124">备注</span><span class="sxs-lookup"><span data-stu-id="37093-124">Remarks</span></span>

<span data-ttu-id="37093-125">有关此类视图的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="37093-125">For more information about this type of view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="37093-126">示例</span><span class="sxs-lookup"><span data-stu-id="37093-126">Example</span></span>

<span data-ttu-id="37093-127">此示例显示了用于定义列表视图的三行的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="37093-127">This example shows the XML elements that define three rows of the list view.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>.NetTypeProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>.NetTypeProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
  </ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="37093-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37093-128">See Also</span></span>

[<span data-ttu-id="37093-129">ListEntry Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="37093-129">ListEntry Element for ListControl (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="37093-130">ListControl (格式的元素) </span><span class="sxs-lookup"><span data-stu-id="37093-130">ListItem Element for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="37093-131">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="37093-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="37093-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="37093-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
