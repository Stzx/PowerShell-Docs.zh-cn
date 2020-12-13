---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for GroupBy (Format)
description: ScriptBlock Element for GroupBy (Format)
ms.openlocfilehash: 117cbef93889046626741449886a1caaa39815cb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665241"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="85490-103">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="85490-103">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="85490-104">指定在新组的值发生更改时启动新组的脚本。</span><span class="sxs-lookup"><span data-stu-id="85490-104">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="85490-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (groupby) 格式的 ScriptBlock 元素 (</span><span class="sxs-lookup"><span data-stu-id="85490-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="85490-106">语法</span><span class="sxs-lookup"><span data-stu-id="85490-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="85490-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="85490-107">Attributes and Elements</span></span>

<span data-ttu-id="85490-108">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="85490-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="85490-109">特性</span><span class="sxs-lookup"><span data-stu-id="85490-109">Attributes</span></span>

<span data-ttu-id="85490-110">无。</span><span class="sxs-lookup"><span data-stu-id="85490-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="85490-111">子元素</span><span class="sxs-lookup"><span data-stu-id="85490-111">Child Elements</span></span>

<span data-ttu-id="85490-112">无。</span><span class="sxs-lookup"><span data-stu-id="85490-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="85490-113">父元素</span><span class="sxs-lookup"><span data-stu-id="85490-113">Parent Elements</span></span>

|<span data-ttu-id="85490-114">元素</span><span class="sxs-lookup"><span data-stu-id="85490-114">Element</span></span>|<span data-ttu-id="85490-115">描述</span><span class="sxs-lookup"><span data-stu-id="85490-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="85490-116">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="85490-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="85490-117">定义一组 .NET 对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="85490-117">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="85490-118">文本值</span><span class="sxs-lookup"><span data-stu-id="85490-118">Text Value</span></span>

<span data-ttu-id="85490-119">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="85490-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="85490-120">备注</span><span class="sxs-lookup"><span data-stu-id="85490-120">Remarks</span></span>

<span data-ttu-id="85490-121">每当此脚本的值发生更改时，PowerShell 就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="85490-121">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="85490-122">如果指定此元素，则不能指定 [PropertyName](propertyname-element-for-groupby-format.md) 元素来启动新组。</span><span class="sxs-lookup"><span data-stu-id="85490-122">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="85490-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85490-123">See Also</span></span>

[<span data-ttu-id="85490-124">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="85490-124">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="85490-125">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="85490-125">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="85490-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="85490-126">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
