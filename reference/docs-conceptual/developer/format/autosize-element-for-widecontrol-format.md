---
title: WideControl 的 AutoSize 元素)  (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 64e62142738916978b37eb1cd3a73536b0447099
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783868"
---
# <a name="autosize-element-for-widecontrol-format"></a><span data-ttu-id="b835d-102">AutoSize Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b835d-102">AutoSize Element for WideControl (Format)</span></span>

<span data-ttu-id="b835d-103">指定是否根据数据大小调整列大小和列数。</span><span class="sxs-lookup"><span data-stu-id="b835d-103">Specifies whether the column size and the number of columns are adjusted based on the size of the data.</span></span>

<span data-ttu-id="b835d-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl (格式) Autosize 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="b835d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) Autosize Element for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b835d-105">语法</span><span class="sxs-lookup"><span data-stu-id="b835d-105">Syntax</span></span>

```xml
<AutoSize/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b835d-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b835d-106">Attributes and Elements</span></span>

<span data-ttu-id="b835d-107">以下各节描述了元素的属性、子元素和父元素 `AutoSize` 。</span><span class="sxs-lookup"><span data-stu-id="b835d-107">The following sections describe attributes, child elements, and the parent element of the `AutoSize` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b835d-108">特性</span><span class="sxs-lookup"><span data-stu-id="b835d-108">Attributes</span></span>

<span data-ttu-id="b835d-109">无。</span><span class="sxs-lookup"><span data-stu-id="b835d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b835d-110">子元素</span><span class="sxs-lookup"><span data-stu-id="b835d-110">Child Elements</span></span>

<span data-ttu-id="b835d-111">None</span><span class="sxs-lookup"><span data-stu-id="b835d-111">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b835d-112">父元素</span><span class="sxs-lookup"><span data-stu-id="b835d-112">Parent Elements</span></span>

|<span data-ttu-id="b835d-113">元素</span><span class="sxs-lookup"><span data-stu-id="b835d-113">Element</span></span>|<span data-ttu-id="b835d-114">描述</span><span class="sxs-lookup"><span data-stu-id="b835d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b835d-115">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b835d-115">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="b835d-116">定义视图的宽 (单个值) 列表格式。</span><span class="sxs-lookup"><span data-stu-id="b835d-116">Defines a wide (single value) list format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b835d-117">备注</span><span class="sxs-lookup"><span data-stu-id="b835d-117">Remarks</span></span>

<span data-ttu-id="b835d-118">定义宽视图时，可以添加 `AutoSize` 元素或[ColumnNumber](./columnnumber-element-for-widecontrol-format.md)元素，但不能同时添加这两个元素。</span><span class="sxs-lookup"><span data-stu-id="b835d-118">When defining a wide view, you can add the `AutoSize` element or the [ColumnNumber](./columnnumber-element-for-widecontrol-format.md) element, but you cannot add both.</span></span>

<span data-ttu-id="b835d-119">有关宽视图组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="b835d-119">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

<span data-ttu-id="b835d-120">有关宽视图的示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="b835d-120">For an example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b835d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b835d-121">See Also</span></span>

[<span data-ttu-id="b835d-122">ColumnNumber Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b835d-122">ColumnNumber Element for WideControl (Format)</span></span>](./columnnumber-element-for-widecontrol-format.md)

[<span data-ttu-id="b835d-123">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="b835d-123">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b835d-124">WideControl Element (Format)</span><span class="sxs-lookup"><span data-stu-id="b835d-124">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="b835d-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b835d-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
