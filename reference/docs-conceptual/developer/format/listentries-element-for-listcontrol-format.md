---
ms.date: 09/13/2016
ms.topic: reference
title: ListEntries Element for ListControl (Format)
description: ListEntries Element for ListControl (Format)
ms.openlocfilehash: d4d6625bb92ea27863fc30d5bf5625f9275e4f69
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666597"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="7521c-103">ListEntries Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="7521c-103">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="7521c-104">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="7521c-104">Provides the definitions of the list view.</span></span> <span data-ttu-id="7521c-105">列表视图必须指定一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="7521c-105">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="7521c-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7521c-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7521c-107">语法</span><span class="sxs-lookup"><span data-stu-id="7521c-107">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7521c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7521c-108">Attributes and Elements</span></span>

<span data-ttu-id="7521c-109">以下各节描述了元素的属性、子元素和父元素 `ListEntries` 。</span><span class="sxs-lookup"><span data-stu-id="7521c-109">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="7521c-110">必须至少指定一个子元素。</span><span class="sxs-lookup"><span data-stu-id="7521c-110">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="7521c-111">特性</span><span class="sxs-lookup"><span data-stu-id="7521c-111">Attributes</span></span>

<span data-ttu-id="7521c-112">无。</span><span class="sxs-lookup"><span data-stu-id="7521c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7521c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="7521c-113">Child Elements</span></span>

|<span data-ttu-id="7521c-114">元素</span><span class="sxs-lookup"><span data-stu-id="7521c-114">Element</span></span>|<span data-ttu-id="7521c-115">描述</span><span class="sxs-lookup"><span data-stu-id="7521c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7521c-116">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7521c-116">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="7521c-117">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="7521c-117">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7521c-118">父元素</span><span class="sxs-lookup"><span data-stu-id="7521c-118">Parent Elements</span></span>

|<span data-ttu-id="7521c-119">元素</span><span class="sxs-lookup"><span data-stu-id="7521c-119">Element</span></span>|<span data-ttu-id="7521c-120">描述</span><span class="sxs-lookup"><span data-stu-id="7521c-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7521c-121">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7521c-121">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="7521c-122">定义视图的列表格式。</span><span class="sxs-lookup"><span data-stu-id="7521c-122">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7521c-123">备注</span><span class="sxs-lookup"><span data-stu-id="7521c-123">Remarks</span></span>

<span data-ttu-id="7521c-124">有关列表视图的详细信息，请参阅 [列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="7521c-124">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="7521c-125">示例</span><span class="sxs-lookup"><span data-stu-id="7521c-125">Example</span></span>

<span data-ttu-id="7521c-126">此示例显示了为 [system.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象定义列表视图的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="7521c-126">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7521c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7521c-127">See Also</span></span>

[<span data-ttu-id="7521c-128">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7521c-128">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="7521c-129">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7521c-129">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="7521c-130">列表视图</span><span class="sxs-lookup"><span data-stu-id="7521c-130">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7521c-131">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="7521c-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
