---
ms.date: 09/13/2016
ms.topic: reference
title: CustomControlName Element for GroupBy (Format)
description: CustomControlName Element for GroupBy (Format)
ms.openlocfilehash: 03664fe4d5559312e2720a3892493c90c15f7501
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655422"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="4f2a7-103">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="4f2a7-103">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="4f2a7-104">指定用于显示新组的自定义控件的名称。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-104">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="4f2a7-105">定义表、列表、宽或自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-105">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="4f2a7-106">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (GroupBy) 格式的 CustomControlName 元素 (</span><span class="sxs-lookup"><span data-stu-id="4f2a7-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f2a7-107">语法</span><span class="sxs-lookup"><span data-stu-id="4f2a7-107">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4f2a7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4f2a7-108">Attributes and Elements</span></span>

<span data-ttu-id="4f2a7-109">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-109">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="4f2a7-110">特性</span><span class="sxs-lookup"><span data-stu-id="4f2a7-110">Attributes</span></span>

<span data-ttu-id="4f2a7-111">无。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4f2a7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4f2a7-112">Child Elements</span></span>

<span data-ttu-id="4f2a7-113">无。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4f2a7-114">父元素</span><span class="sxs-lookup"><span data-stu-id="4f2a7-114">Parent Elements</span></span>

|<span data-ttu-id="4f2a7-115">元素</span><span class="sxs-lookup"><span data-stu-id="4f2a7-115">Element</span></span>|<span data-ttu-id="4f2a7-116">描述</span><span class="sxs-lookup"><span data-stu-id="4f2a7-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4f2a7-117">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4f2a7-117">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="4f2a7-118">定义 Windows PowerShell 如何显示一组新的对象。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-118">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="4f2a7-119">文本值</span><span class="sxs-lookup"><span data-stu-id="4f2a7-119">Text Value</span></span>

<span data-ttu-id="4f2a7-120">指定用于显示新组的自定义控件的名称。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-120">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f2a7-121">备注</span><span class="sxs-lookup"><span data-stu-id="4f2a7-121">Remarks</span></span>

<span data-ttu-id="4f2a7-122">您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="4f2a7-122">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="4f2a7-123">以下元素指定这些自定义控件的名称：</span><span class="sxs-lookup"><span data-stu-id="4f2a7-123">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="4f2a7-124">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4f2a7-124">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="4f2a7-125">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4f2a7-125">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="4f2a7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f2a7-126">See Also</span></span>

[<span data-ttu-id="4f2a7-127">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4f2a7-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="4f2a7-128">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4f2a7-128">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="4f2a7-129">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="4f2a7-129">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="4f2a7-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4f2a7-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
