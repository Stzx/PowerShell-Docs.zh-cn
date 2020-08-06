---
title: GroupBy (格式) 的 CustomControlName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4e3102f12cd37fa72a2de1bf1db5d1f82db31222
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783732"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="08b7a-102">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="08b7a-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="08b7a-103">指定用于显示新组的自定义控件的名称。</span><span class="sxs-lookup"><span data-stu-id="08b7a-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="08b7a-104">定义表、列表、宽或自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="08b7a-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="08b7a-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (GroupBy) 格式的 CustomControlName 元素 (</span><span class="sxs-lookup"><span data-stu-id="08b7a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="08b7a-106">语法</span><span class="sxs-lookup"><span data-stu-id="08b7a-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="08b7a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="08b7a-107">Attributes and Elements</span></span>

<span data-ttu-id="08b7a-108">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="08b7a-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="08b7a-109">特性</span><span class="sxs-lookup"><span data-stu-id="08b7a-109">Attributes</span></span>

<span data-ttu-id="08b7a-110">无。</span><span class="sxs-lookup"><span data-stu-id="08b7a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="08b7a-111">子元素</span><span class="sxs-lookup"><span data-stu-id="08b7a-111">Child Elements</span></span>

<span data-ttu-id="08b7a-112">无。</span><span class="sxs-lookup"><span data-stu-id="08b7a-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="08b7a-113">父元素</span><span class="sxs-lookup"><span data-stu-id="08b7a-113">Parent Elements</span></span>

|<span data-ttu-id="08b7a-114">元素</span><span class="sxs-lookup"><span data-stu-id="08b7a-114">Element</span></span>|<span data-ttu-id="08b7a-115">描述</span><span class="sxs-lookup"><span data-stu-id="08b7a-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="08b7a-116">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="08b7a-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="08b7a-117">定义 Windows PowerShell 如何显示一组新的对象。</span><span class="sxs-lookup"><span data-stu-id="08b7a-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="08b7a-118">文本值</span><span class="sxs-lookup"><span data-stu-id="08b7a-118">Text Value</span></span>

<span data-ttu-id="08b7a-119">指定用于显示新组的自定义控件的名称。</span><span class="sxs-lookup"><span data-stu-id="08b7a-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="08b7a-120">备注</span><span class="sxs-lookup"><span data-stu-id="08b7a-120">Remarks</span></span>

<span data-ttu-id="08b7a-121">您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="08b7a-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="08b7a-122">以下元素指定这些自定义控件的名称：</span><span class="sxs-lookup"><span data-stu-id="08b7a-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="08b7a-123">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="08b7a-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="08b7a-124">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="08b7a-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="08b7a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08b7a-125">See Also</span></span>

[<span data-ttu-id="08b7a-126">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="08b7a-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="08b7a-127">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="08b7a-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="08b7a-128">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="08b7a-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="08b7a-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="08b7a-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
