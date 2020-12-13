---
ms.date: 09/13/2016
ms.topic: reference
title: AutoSize Element for WideControl (Format)
description: AutoSize Element for WideControl (Format)
ms.openlocfilehash: 42dfae337ba8805e1ddcff4269401afdb3e281f6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650008"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="345b7-103">AutoSize Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="345b7-103">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="345b7-104">指定是否根据数据大小调整列大小和列数。</span><span class="sxs-lookup"><span data-stu-id="345b7-104">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="345b7-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl (格式) Autosize 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="345b7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="345b7-106">语法</span><span class="sxs-lookup"><span data-stu-id="345b7-106">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="345b7-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="345b7-107">Attributes and Elements</span></span>

<span data-ttu-id="345b7-108">以下各节描述了元素的属性、子元素和父元素 `AutoSize` 。</span><span class="sxs-lookup"><span data-stu-id="345b7-108">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="345b7-109">特性</span><span class="sxs-lookup"><span data-stu-id="345b7-109">Attributes</span></span>

<span data-ttu-id="345b7-110">无。</span><span class="sxs-lookup"><span data-stu-id="345b7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="345b7-111">子元素</span><span class="sxs-lookup"><span data-stu-id="345b7-111">Child Elements</span></span>

<span data-ttu-id="345b7-112">无</span><span class="sxs-lookup"><span data-stu-id="345b7-112">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="345b7-113">父元素</span><span class="sxs-lookup"><span data-stu-id="345b7-113">Parent Elements</span></span>

|<span data-ttu-id="345b7-114">元素</span><span class="sxs-lookup"><span data-stu-id="345b7-114">Element</span></span>|<span data-ttu-id="345b7-115">描述</span><span class="sxs-lookup"><span data-stu-id="345b7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="345b7-116">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="345b7-116">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="345b7-117">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="345b7-117">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="345b7-118">备注</span><span class="sxs-lookup"><span data-stu-id="345b7-118">Remarks</span></span>

<span data-ttu-id="345b7-119">定义宽视图时，可以添加 `AutoSize` 元素或 [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) 元素，但不能同时添加这两个元素。</span><span class="sxs-lookup"><span data-stu-id="345b7-119">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="345b7-120">有关宽视图组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="345b7-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="345b7-121">有关宽视图的示例，请参阅 [宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="345b7-121">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="345b7-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="345b7-122">See Also</span></span>

[<span data-ttu-id="345b7-123">ColumnNumber Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="345b7-123">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="345b7-124">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="345b7-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="345b7-125">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="345b7-125">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="345b7-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="345b7-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
