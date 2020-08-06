---
title: WideControl (Format) 的 ColumnNumber 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5f151bb0e629efcebe6295cdcae6cebcbbb1b39b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783851"
---
# <a name="columnnumber-element-for-widecontrol-format"></a><span data-ttu-id="9ca75-102">ColumnNumber Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9ca75-102">ColumnNumber Element for WideControl (Format)</span></span>

<span data-ttu-id="9ca75-103">指定宽视图中显示的列数。</span><span class="sxs-lookup"><span data-stu-id="9ca75-103">Specifies the number of columns displayed in the wide view.</span></span>

<span data-ttu-id="9ca75-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) ColumnNumber 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9ca75-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) ColumnNumber Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9ca75-105">语法</span><span class="sxs-lookup"><span data-stu-id="9ca75-105">Syntax</span></span>

```xml
<ColumnNumber>PositiveInteger</ColumnNumber>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9ca75-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9ca75-106">Attributes and Elements</span></span>

<span data-ttu-id="9ca75-107">以下各节描述了元素的属性、子元素和父元素 `ColumnNumber` 。</span><span class="sxs-lookup"><span data-stu-id="9ca75-107">The following sections describe attributes, child elements, and the parent element of the `ColumnNumber` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ca75-108">特性</span><span class="sxs-lookup"><span data-stu-id="9ca75-108">Attributes</span></span>

<span data-ttu-id="9ca75-109">无。</span><span class="sxs-lookup"><span data-stu-id="9ca75-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9ca75-110">子元素</span><span class="sxs-lookup"><span data-stu-id="9ca75-110">Child Elements</span></span>

<span data-ttu-id="9ca75-111">无。</span><span class="sxs-lookup"><span data-stu-id="9ca75-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9ca75-112">父元素</span><span class="sxs-lookup"><span data-stu-id="9ca75-112">Parent Elements</span></span>

|<span data-ttu-id="9ca75-113">元素</span><span class="sxs-lookup"><span data-stu-id="9ca75-113">Element</span></span>|<span data-ttu-id="9ca75-114">描述</span><span class="sxs-lookup"><span data-stu-id="9ca75-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9ca75-115">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="9ca75-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="9ca75-116">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="9ca75-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9ca75-117">文本值</span><span class="sxs-lookup"><span data-stu-id="9ca75-117">Text Value</span></span>

<span data-ttu-id="9ca75-118">指定一个正整数值。</span><span class="sxs-lookup"><span data-stu-id="9ca75-118">Specify a positive integer value.</span></span>

## <a name="remarks"></a><span data-ttu-id="9ca75-119">备注</span><span class="sxs-lookup"><span data-stu-id="9ca75-119">Remarks</span></span>

<span data-ttu-id="9ca75-120">定义宽视图时，可以添加 `AutoSize` 元素或 `ColumnNumber` 元素，但不能同时添加这两个元素。</span><span class="sxs-lookup"><span data-stu-id="9ca75-120">When defining a wide view, you can add the `AutoSize` element or the `ColumnNumber` element, but you cannot add both.</span></span>

<span data-ttu-id="9ca75-121">有关宽视图组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca75-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="9ca75-122">有关宽视图的示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca75-122">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9ca75-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ca75-123">See Also</span></span>

[<span data-ttu-id="9ca75-124">WideControl 的 Autosize 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="9ca75-124">Autosize Element for WideControl (Format)</span></span>](./autosize-element-for-widecontrol-format.md)

[<span data-ttu-id="9ca75-125">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="9ca75-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9ca75-126">宽视图 (Basic)</span><span class="sxs-lookup"><span data-stu-id="9ca75-126">Wide View (Basic)</span></span>](./wide-view-basic.md)

[<span data-ttu-id="9ca75-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="9ca75-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
