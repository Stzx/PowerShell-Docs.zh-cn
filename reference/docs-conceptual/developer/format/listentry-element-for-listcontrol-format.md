---
ms.date: 09/13/2016
ms.topic: reference
title: ListEntry Element for ListControl (Format)
description: ListEntry Element for ListControl (Format)
ms.openlocfilehash: 96ae5fcdd837d2491d6c7ff6a375fef1d83ae3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666563"
---
# <a name="listentry-element-for-listcontrol-format"></a><span data-ttu-id="a89da-103">ListEntry Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="a89da-103">ListEntry Element for ListControl (Format)</span></span>

<span data-ttu-id="a89da-104">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="a89da-104">Provides a definition of the list view.</span></span>

<span data-ttu-id="a89da-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a89da-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a89da-106">语法</span><span class="sxs-lookup"><span data-stu-id="a89da-106">Syntax</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a89da-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a89da-107">Attributes and Elements</span></span>

<span data-ttu-id="a89da-108">以下各节描述了元素的属性、子元素和父元素 `ListEntry` 。</span><span class="sxs-lookup"><span data-stu-id="a89da-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a89da-109">特性</span><span class="sxs-lookup"><span data-stu-id="a89da-109">Attributes</span></span>

<span data-ttu-id="a89da-110">无。</span><span class="sxs-lookup"><span data-stu-id="a89da-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a89da-111">子元素</span><span class="sxs-lookup"><span data-stu-id="a89da-111">Child Elements</span></span>

|<span data-ttu-id="a89da-112">元素</span><span class="sxs-lookup"><span data-stu-id="a89da-112">Element</span></span>|<span data-ttu-id="a89da-113">描述</span><span class="sxs-lookup"><span data-stu-id="a89da-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a89da-114">ListEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a89da-114">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="a89da-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="a89da-115">Optional element.</span></span><br /><br /> <span data-ttu-id="a89da-116">定义使用此列表视图定义的 .NET 对象，或使用此定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="a89da-116">Defines the .NET objects that use this list view definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="a89da-117">ListItems 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a89da-117">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="a89da-118">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="a89da-118">Required element.</span></span><br /><br /> <span data-ttu-id="a89da-119">定义其值由列表视图显示的属性和脚本。</span><span class="sxs-lookup"><span data-stu-id="a89da-119">Defines the properties and scripts whose values are displayed by the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a89da-120">父元素</span><span class="sxs-lookup"><span data-stu-id="a89da-120">Parent Elements</span></span>

|<span data-ttu-id="a89da-121">元素</span><span class="sxs-lookup"><span data-stu-id="a89da-121">Element</span></span>|<span data-ttu-id="a89da-122">描述</span><span class="sxs-lookup"><span data-stu-id="a89da-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a89da-123">ListEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a89da-123">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="a89da-124">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="a89da-124">Provides the definitions of the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a89da-125">备注</span><span class="sxs-lookup"><span data-stu-id="a89da-125">Remarks</span></span>

<span data-ttu-id="a89da-126">列表视图是显示每个对象的属性值或脚本值的列表格式。</span><span class="sxs-lookup"><span data-stu-id="a89da-126">A list view is a list format that displays property values or script values for each object.</span></span> <span data-ttu-id="a89da-127">有关列表视图的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="a89da-127">For more information about list views, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a89da-128">示例</span><span class="sxs-lookup"><span data-stu-id="a89da-128">Example</span></span>

<span data-ttu-id="a89da-129">此示例显示了为 [system.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象定义列表视图的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="a89da-129">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>
        <ListItems>...</ListItems>
      </ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="a89da-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a89da-130">See Also</span></span>

[<span data-ttu-id="a89da-131">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="a89da-131">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a89da-132">ListEntry 的 EntrySelectedBy 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a89da-132">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="a89da-133">ListEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a89da-133">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="a89da-134">ListItems 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="a89da-134">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="a89da-135">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="a89da-135">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
