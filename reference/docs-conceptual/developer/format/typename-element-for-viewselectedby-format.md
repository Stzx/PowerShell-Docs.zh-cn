---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for ViewSelectedBy (Format)
description: TypeName Element for ViewSelectedBy (Format)
ms.openlocfilehash: 62edc2fe4b4c1c5f1b17dd2f8b0943f28ff5dfb7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667719"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="7c5ee-103">TypeName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="7c5ee-103">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="7c5ee-104">指定视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-104">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="7c5ee-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ViewSelectedBy 元素 (格式) ViewSelectedBy (格式) TypeName 元素</span><span class="sxs-lookup"><span data-stu-id="7c5ee-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7c5ee-106">语法</span><span class="sxs-lookup"><span data-stu-id="7c5ee-106">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c5ee-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7c5ee-107">Attributes and Elements</span></span>

<span data-ttu-id="7c5ee-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-108">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c5ee-109">特性</span><span class="sxs-lookup"><span data-stu-id="7c5ee-109">Attributes</span></span>

<span data-ttu-id="7c5ee-110">无。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7c5ee-111">子元素</span><span class="sxs-lookup"><span data-stu-id="7c5ee-111">Child Elements</span></span>

<span data-ttu-id="7c5ee-112">无。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c5ee-113">父元素</span><span class="sxs-lookup"><span data-stu-id="7c5ee-113">Parent Elements</span></span>

|<span data-ttu-id="7c5ee-114">元素</span><span class="sxs-lookup"><span data-stu-id="7c5ee-114">Element</span></span>|<span data-ttu-id="7c5ee-115">描述</span><span class="sxs-lookup"><span data-stu-id="7c5ee-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7c5ee-116">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7c5ee-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="7c5ee-117">定义视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="7c5ee-118">文本值</span><span class="sxs-lookup"><span data-stu-id="7c5ee-118">Text Value</span></span>

<span data-ttu-id="7c5ee-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7c5ee-120">备注</span><span class="sxs-lookup"><span data-stu-id="7c5ee-120">Remarks</span></span>

<span data-ttu-id="7c5ee-121">有关此元素在不同视图中的使用方式的详细信息，请参阅 [创建表视图](./creating-a-table-view.md)、 [创建列表视图](./creating-a-list-view.md)、 [创建宽视图](./creating-a-wide-view.md)和 [自定义视图组件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-121">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="7c5ee-122">示例</span><span class="sxs-lookup"><span data-stu-id="7c5ee-122">Example</span></span>

<span data-ttu-id="7c5ee-123">下面的示例演示如何为列表视图指定 [Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) 对象。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-123">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="7c5ee-124">表、宽视图和自定义视图使用相同的架构。</span><span class="sxs-lookup"><span data-stu-id="7c5ee-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="7c5ee-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c5ee-125">See Also</span></span>

[<span data-ttu-id="7c5ee-126">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="7c5ee-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="7c5ee-127">创建表视图</span><span class="sxs-lookup"><span data-stu-id="7c5ee-127">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="7c5ee-128">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="7c5ee-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="7c5ee-129">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="7c5ee-129">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="7c5ee-130">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="7c5ee-130">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="7c5ee-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7c5ee-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
