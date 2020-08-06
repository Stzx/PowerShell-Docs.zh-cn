---
title: ListControl (Format) 的 ListEntries 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0fe07e739c2d2fec153599ec6c0c0b3ecc14df18
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785704"
---
# <a name="listentries-element-for-listcontrol-format"></a><span data-ttu-id="1ab52-102">ListEntries Element for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="1ab52-102">ListEntries Element for ListControl (Format)</span></span>

<span data-ttu-id="1ab52-103">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="1ab52-103">Provides the definitions of the list view.</span></span> <span data-ttu-id="1ab52-104">列表视图必须指定一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="1ab52-104">The list view must specify one or more definitions.</span></span>

<span data-ttu-id="1ab52-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="1ab52-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1ab52-106">语法</span><span class="sxs-lookup"><span data-stu-id="1ab52-106">Syntax</span></span>

```xml
<ListEntries>
  <ListEntry>...</ListEntry>
</ListEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ab52-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1ab52-107">Attributes and Elements</span></span>

<span data-ttu-id="1ab52-108">以下各节描述了元素的属性、子元素和父元素 `ListEntries` 。</span><span class="sxs-lookup"><span data-stu-id="1ab52-108">The following sections describe the attributes, child elements, and the parent element of the `ListEntries` element.</span></span> <span data-ttu-id="1ab52-109">必须至少指定一个子元素。</span><span class="sxs-lookup"><span data-stu-id="1ab52-109">At least one child element must be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ab52-110">特性</span><span class="sxs-lookup"><span data-stu-id="1ab52-110">Attributes</span></span>

<span data-ttu-id="1ab52-111">无。</span><span class="sxs-lookup"><span data-stu-id="1ab52-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1ab52-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1ab52-112">Child Elements</span></span>

|<span data-ttu-id="1ab52-113">元素</span><span class="sxs-lookup"><span data-stu-id="1ab52-113">Element</span></span>|<span data-ttu-id="1ab52-114">说明</span><span class="sxs-lookup"><span data-stu-id="1ab52-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ab52-115">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="1ab52-115">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)|<span data-ttu-id="1ab52-116">提供列表视图的定义。</span><span class="sxs-lookup"><span data-stu-id="1ab52-116">Provides a definition of the list view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="1ab52-117">父元素</span><span class="sxs-lookup"><span data-stu-id="1ab52-117">Parent Elements</span></span>

|<span data-ttu-id="1ab52-118">元素</span><span class="sxs-lookup"><span data-stu-id="1ab52-118">Element</span></span>|<span data-ttu-id="1ab52-119">说明</span><span class="sxs-lookup"><span data-stu-id="1ab52-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1ab52-120">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ab52-120">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="1ab52-121">定义视图的列表格式。</span><span class="sxs-lookup"><span data-stu-id="1ab52-121">Defines a list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1ab52-122">备注</span><span class="sxs-lookup"><span data-stu-id="1ab52-122">Remarks</span></span>

<span data-ttu-id="1ab52-123">有关列表视图的详细信息，请参阅[列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="1ab52-123">For more information about list views, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="1ab52-124">示例</span><span class="sxs-lookup"><span data-stu-id="1ab52-124">Example</span></span>

<span data-ttu-id="1ab52-125">此示例显示了为[system.serviceprocess. Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)对象定义列表视图的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="1ab52-125">This example shows the XML elements that define the list view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1ab52-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ab52-126">See Also</span></span>

[<span data-ttu-id="1ab52-127">ListControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="1ab52-127">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="1ab52-128">ListEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="1ab52-128">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="1ab52-129">列表视图</span><span class="sxs-lookup"><span data-stu-id="1ab52-129">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1ab52-130">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="1ab52-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
