---
ms.date: 09/13/2016
ms.topic: reference
title: Name Element for View (Format)
description: Name Element for View (Format)
ms.openlocfilehash: 5781bcdf7a0e1eb5e9c7e97bb6acc0a383dc0262
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666446"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="4560f-103">Name Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4560f-103">Name Element for View (Format)</span></span>

<span data-ttu-id="4560f-104">指定用于标识视图的名称。</span><span class="sxs-lookup"><span data-stu-id="4560f-104">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="4560f-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) Name 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="4560f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4560f-106">语法</span><span class="sxs-lookup"><span data-stu-id="4560f-106">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4560f-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4560f-107">Attributes and Elements</span></span>

<span data-ttu-id="4560f-108">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="4560f-108">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="4560f-109">`Name`每个视图只允许有一个元素。</span><span class="sxs-lookup"><span data-stu-id="4560f-109">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="4560f-110">特性</span><span class="sxs-lookup"><span data-stu-id="4560f-110">Attributes</span></span>

<span data-ttu-id="4560f-111">无。</span><span class="sxs-lookup"><span data-stu-id="4560f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4560f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4560f-112">Child Elements</span></span>

<span data-ttu-id="4560f-113">无。</span><span class="sxs-lookup"><span data-stu-id="4560f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4560f-114">父元素</span><span class="sxs-lookup"><span data-stu-id="4560f-114">Parent Elements</span></span>

|<span data-ttu-id="4560f-115">元素</span><span class="sxs-lookup"><span data-stu-id="4560f-115">Element</span></span>|<span data-ttu-id="4560f-116">描述</span><span class="sxs-lookup"><span data-stu-id="4560f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4560f-117">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4560f-117">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="4560f-118">定义一个视图，该视图用于显示一个或多个 .NET 对象的成员。</span><span class="sxs-lookup"><span data-stu-id="4560f-118">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4560f-119">文本值</span><span class="sxs-lookup"><span data-stu-id="4560f-119">Text Value</span></span>

<span data-ttu-id="4560f-120">为视图指定唯一的友好名称。</span><span class="sxs-lookup"><span data-stu-id="4560f-120">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="4560f-121">此名称可以包含对视图类型的引用 (例如表视图或列表视图) 、使用视图的对象或对象集、返回对象的命令或这些对象的组合。</span><span class="sxs-lookup"><span data-stu-id="4560f-121">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="4560f-122">备注</span><span class="sxs-lookup"><span data-stu-id="4560f-122">Remarks</span></span>

<span data-ttu-id="4560f-123">有关不同视图类型的详细信息，请参阅下列主题： [表视图](./creating-a-table-view.md)、 [列表视图](./creating-a-list-view.md)、 [宽视图](./creating-a-wide-view.md)和 [自定义视图](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="4560f-123">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="4560f-124">示例</span><span class="sxs-lookup"><span data-stu-id="4560f-124">Example</span></span>

<span data-ttu-id="4560f-125">下面的示例演示一个 `View` 元素，该元素定义 [System.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象的表视图。</span><span class="sxs-lookup"><span data-stu-id="4560f-125">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="4560f-126">视图的名称为 "service"。</span><span class="sxs-lookup"><span data-stu-id="4560f-126">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="4560f-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4560f-127">See Also</span></span>

[<span data-ttu-id="4560f-128">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="4560f-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="4560f-129">创建表视图</span><span class="sxs-lookup"><span data-stu-id="4560f-129">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="4560f-130">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="4560f-130">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="4560f-131">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="4560f-131">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="4560f-132">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="4560f-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="4560f-133">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4560f-133">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
