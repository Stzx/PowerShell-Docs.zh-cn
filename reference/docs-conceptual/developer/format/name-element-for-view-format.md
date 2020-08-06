---
title: View (Format) 的 Name 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 670b089f850fa4b39b7b100ca1e1ce45b05ea72d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773226"
---
# <a name="name-element-for-view-format"></a><span data-ttu-id="59c68-102">Name Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="59c68-102">Name Element for View (Format)</span></span>

<span data-ttu-id="59c68-103">指定用于标识视图的名称。</span><span class="sxs-lookup"><span data-stu-id="59c68-103">Specifies the name that is used to identify the view.</span></span>

<span data-ttu-id="59c68-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) Name 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="59c68-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Name Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="59c68-105">语法</span><span class="sxs-lookup"><span data-stu-id="59c68-105">Syntax</span></span>

```xml
<Name>ViewName</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="59c68-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59c68-106">Attributes and Elements</span></span>

<span data-ttu-id="59c68-107">以下各节描述了元素的属性、子元素和父元素 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="59c68-107">The following sections describe attributes, child elements, and the parent element of the `Name` element.</span></span> <span data-ttu-id="59c68-108">`Name`每个视图只允许有一个元素。</span><span class="sxs-lookup"><span data-stu-id="59c68-108">Only one `Name` element is allowed for each view.</span></span>

### <a name="attributes"></a><span data-ttu-id="59c68-109">特性</span><span class="sxs-lookup"><span data-stu-id="59c68-109">Attributes</span></span>

<span data-ttu-id="59c68-110">无。</span><span class="sxs-lookup"><span data-stu-id="59c68-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="59c68-111">子元素</span><span class="sxs-lookup"><span data-stu-id="59c68-111">Child Elements</span></span>

<span data-ttu-id="59c68-112">无。</span><span class="sxs-lookup"><span data-stu-id="59c68-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="59c68-113">父元素</span><span class="sxs-lookup"><span data-stu-id="59c68-113">Parent Elements</span></span>

|<span data-ttu-id="59c68-114">元素</span><span class="sxs-lookup"><span data-stu-id="59c68-114">Element</span></span>|<span data-ttu-id="59c68-115">说明</span><span class="sxs-lookup"><span data-stu-id="59c68-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="59c68-116">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="59c68-116">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="59c68-117">定义一个视图，该视图用于显示一个或多个 .NET 对象的成员。</span><span class="sxs-lookup"><span data-stu-id="59c68-117">Defines a view that is used to display the members of one or more .NET objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="59c68-118">文本值</span><span class="sxs-lookup"><span data-stu-id="59c68-118">Text Value</span></span>

<span data-ttu-id="59c68-119">为视图指定唯一的友好名称。</span><span class="sxs-lookup"><span data-stu-id="59c68-119">Specify a unique friendly name for the view.</span></span> <span data-ttu-id="59c68-120">此名称可以包含对视图类型的引用 (例如表视图或列表视图) 、使用视图的对象或对象集、返回对象的命令或这些对象的组合。</span><span class="sxs-lookup"><span data-stu-id="59c68-120">This name can include a reference to the type of the view (such as a table view or list view), which object or set of objects use the view, what command returns the objects, or a combination of these.</span></span>

## <a name="remarks"></a><span data-ttu-id="59c68-121">备注</span><span class="sxs-lookup"><span data-stu-id="59c68-121">Remarks</span></span>

<span data-ttu-id="59c68-122">有关不同视图类型的详细信息，请参阅下列主题：[表视图](./creating-a-table-view.md)、[列表视图](./creating-a-list-view.md)、[宽视图](./creating-a-wide-view.md)和[自定义视图](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="59c68-122">For more information about the different types of views, see the following topics: [Table View](./creating-a-table-view.md), [List View](./creating-a-list-view.md), [Wide View](./creating-a-wide-view.md), and [Custom View](./creating-custom-controls.md).</span></span>

## <a name="example"></a><span data-ttu-id="59c68-123">示例</span><span class="sxs-lookup"><span data-stu-id="59c68-123">Example</span></span>

<span data-ttu-id="59c68-124">下面的示例演示一个 `View` 元素，该元素定义[System.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)对象的表视图。</span><span class="sxs-lookup"><span data-stu-id="59c68-124">The following example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span> <span data-ttu-id="59c68-125">视图的名称为 "service"。</span><span class="sxs-lookup"><span data-stu-id="59c68-125">The name of the view is "service".</span></span>

```xml
<View>
  <Name>service</Name>
  <ViewSelectedBy>
    <TypeName>System.ServiceProcess.ServiceController</TypeName>
  </ViewSelectedBy>
  <TableControl>...</TableControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="59c68-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59c68-126">See Also</span></span>

[<span data-ttu-id="59c68-127">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="59c68-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="59c68-128">创建表视图</span><span class="sxs-lookup"><span data-stu-id="59c68-128">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="59c68-129">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="59c68-129">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="59c68-130">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="59c68-130">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="59c68-131">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="59c68-131">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="59c68-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="59c68-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
