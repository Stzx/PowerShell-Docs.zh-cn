---
ms.date: 09/13/2016
ms.topic: reference
title: ListControl Element (Format)
description: ListControl Element (Format)
ms.openlocfilehash: cd5687ac8e94e2245d1ae2de8b2206185e5b8ca4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666580"
---
# <a name="listcontrol-element-format"></a><span data-ttu-id="9faf2-103">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9faf2-103">ListControl Element (Format)</span></span>

<span data-ttu-id="9faf2-104">定义视图的列表格式。</span><span class="sxs-lookup"><span data-stu-id="9faf2-104">Defines a list format for the view.</span></span>

<span data-ttu-id="9faf2-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9faf2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9faf2-106">语法</span><span class="sxs-lookup"><span data-stu-id="9faf2-106">Syntax</span></span>

```xml
<ListControl>
  <ListEntries>...</ListEntries>
</ListControl>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="9faf2-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9faf2-107">Attributes and Elements</span></span>

<span data-ttu-id="9faf2-108">以下各节描述了元素的属性、子元素和父元素 `ListControl` 。</span><span class="sxs-lookup"><span data-stu-id="9faf2-108">The following sections describe the attributes, child elements, and the parent element of the `ListControl` element.</span></span> <span data-ttu-id="9faf2-109">此元素必须只包含一个子元素。</span><span class="sxs-lookup"><span data-stu-id="9faf2-109">This element must contain only a single child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9faf2-110">特性</span><span class="sxs-lookup"><span data-stu-id="9faf2-110">Attributes</span></span>

<span data-ttu-id="9faf2-111">无。</span><span class="sxs-lookup"><span data-stu-id="9faf2-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9faf2-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9faf2-112">Child Elements</span></span>

|<span data-ttu-id="9faf2-113">元素</span><span class="sxs-lookup"><span data-stu-id="9faf2-113">Element</span></span>|<span data-ttu-id="9faf2-114">描述</span><span class="sxs-lookup"><span data-stu-id="9faf2-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9faf2-115">ListEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9faf2-115">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)|<span data-ttu-id="9faf2-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="9faf2-116">Required element.</span></span><br /><br /> <span data-ttu-id="9faf2-117">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="9faf2-117">Provides the definitions of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9faf2-118">父元素</span><span class="sxs-lookup"><span data-stu-id="9faf2-118">Parent Elements</span></span>

|<span data-ttu-id="9faf2-119">元素</span><span class="sxs-lookup"><span data-stu-id="9faf2-119">Element</span></span>|<span data-ttu-id="9faf2-120">描述</span><span class="sxs-lookup"><span data-stu-id="9faf2-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9faf2-121">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9faf2-121">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="9faf2-122">定义一个视图，该视图用于显示一个或多个对象的成员。</span><span class="sxs-lookup"><span data-stu-id="9faf2-122">Defines a view that is used to display the members of one or more objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9faf2-123">备注</span><span class="sxs-lookup"><span data-stu-id="9faf2-123">Remarks</span></span>

<span data-ttu-id="9faf2-124">有关创建列表视图的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="9faf2-124">For more information about creating a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="9faf2-125">示例</span><span class="sxs-lookup"><span data-stu-id="9faf2-125">Example</span></span>

<span data-ttu-id="9faf2-126">此示例显示了 [system.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象的列表视图。</span><span class="sxs-lookup"><span data-stu-id="9faf2-126">This example shows a list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>
    <ListEntries>
      <ListEntry>...</ListEntry>
    </ListEntries>
  </ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="9faf2-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9faf2-127">See Also</span></span>

[<span data-ttu-id="9faf2-128">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9faf2-128">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="9faf2-129">ListEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9faf2-129">ListEntries Element (Format)</span></span>](./listentries-element-for-listcontrol-format.md)

[<span data-ttu-id="9faf2-130">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="9faf2-130">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="9faf2-131">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="9faf2-131">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
