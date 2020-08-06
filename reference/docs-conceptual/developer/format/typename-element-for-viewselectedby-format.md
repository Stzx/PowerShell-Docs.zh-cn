---
title: ViewSelectedBy (Format) 的 TypeName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e9a391565c3e66041dd9a340455dccfce9ce929b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780026"
---
# <a name="typename-element-for-viewselectedby-format"></a><span data-ttu-id="bd444-102">TypeName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="bd444-102">TypeName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="bd444-103">指定视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="bd444-103">Specifies a .NET object that is displayed by the view.</span></span>

<span data-ttu-id="bd444-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ViewSelectedBy 元素 (格式) ViewSelectedBy (格式) TypeName 元素</span><span class="sxs-lookup"><span data-stu-id="bd444-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) TypeName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="bd444-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd444-105">Syntax</span></span>

```xml
<TypeName>FullyQualifiedTypeName</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bd444-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bd444-106">Attributes and Elements</span></span>

<span data-ttu-id="bd444-107">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="bd444-107">The following sections describe attributes, child elements, and the parent elements of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="bd444-108">特性</span><span class="sxs-lookup"><span data-stu-id="bd444-108">Attributes</span></span>

<span data-ttu-id="bd444-109">无。</span><span class="sxs-lookup"><span data-stu-id="bd444-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="bd444-110">子元素</span><span class="sxs-lookup"><span data-stu-id="bd444-110">Child Elements</span></span>

<span data-ttu-id="bd444-111">无。</span><span class="sxs-lookup"><span data-stu-id="bd444-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bd444-112">父元素</span><span class="sxs-lookup"><span data-stu-id="bd444-112">Parent Elements</span></span>

|<span data-ttu-id="bd444-113">元素</span><span class="sxs-lookup"><span data-stu-id="bd444-113">Element</span></span>|<span data-ttu-id="bd444-114">描述</span><span class="sxs-lookup"><span data-stu-id="bd444-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="bd444-115">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bd444-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="bd444-116">定义视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="bd444-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="bd444-117">文本值</span><span class="sxs-lookup"><span data-stu-id="bd444-117">Text Value</span></span>

<span data-ttu-id="bd444-118">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="bd444-118">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd444-119">备注</span><span class="sxs-lookup"><span data-stu-id="bd444-119">Remarks</span></span>

<span data-ttu-id="bd444-120">有关此元素在不同视图中的使用方式的详细信息，请参阅[创建表视图](./creating-a-table-view.md)、[创建列表视图](./creating-a-list-view.md)、[创建宽视图](./creating-a-wide-view.md)和[自定义视图组件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="bd444-120">For more information about how this element is used in different views, see [Creating a Table View](./creating-a-table-view.md), [Creating a List View](./creating-a-list-view.md), [Creating a Wide View](./creating-a-wide-view.md), and [Custom View Components](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="bd444-121">示例</span><span class="sxs-lookup"><span data-stu-id="bd444-121">Example</span></span>

<span data-ttu-id="bd444-122">下面的示例演示如何为列表视图指定[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)对象。</span><span class="sxs-lookup"><span data-stu-id="bd444-122">The following example shows how to specify the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object for a list view.</span></span> <span data-ttu-id="bd444-123">表、宽视图和自定义视图使用相同的架构。</span><span class="sxs-lookup"><span data-stu-id="bd444-123">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>System.ServiceProcess.ServiceController</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="bd444-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd444-124">See Also</span></span>

[<span data-ttu-id="bd444-125">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="bd444-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="bd444-126">创建表视图</span><span class="sxs-lookup"><span data-stu-id="bd444-126">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="bd444-127">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="bd444-127">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="bd444-128">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="bd444-128">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="bd444-129">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="bd444-129">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="bd444-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="bd444-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
