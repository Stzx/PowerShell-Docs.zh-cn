---
title: GroupBy (格式) 的 ScriptBlock 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e761e02a7910cd598449d564e827889162da9f25
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787676"
---
# <a name="scriptblock-element-for-groupby-format"></a><span data-ttu-id="13e2d-102">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e2d-102">ScriptBlock Element for GroupBy (Format)</span></span>

<span data-ttu-id="13e2d-103">指定在新组的值发生更改时启动新组的脚本。</span><span class="sxs-lookup"><span data-stu-id="13e2d-103">Specifies the script that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="13e2d-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (groupby) 格式的 ScriptBlock 元素 (</span><span class="sxs-lookup"><span data-stu-id="13e2d-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) ScriptBlock Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="13e2d-105">语法</span><span class="sxs-lookup"><span data-stu-id="13e2d-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="13e2d-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13e2d-106">Attributes and Elements</span></span>

<span data-ttu-id="13e2d-107">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="13e2d-107">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="13e2d-108">特性</span><span class="sxs-lookup"><span data-stu-id="13e2d-108">Attributes</span></span>

<span data-ttu-id="13e2d-109">无。</span><span class="sxs-lookup"><span data-stu-id="13e2d-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="13e2d-110">子元素</span><span class="sxs-lookup"><span data-stu-id="13e2d-110">Child Elements</span></span>

<span data-ttu-id="13e2d-111">无。</span><span class="sxs-lookup"><span data-stu-id="13e2d-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="13e2d-112">父元素</span><span class="sxs-lookup"><span data-stu-id="13e2d-112">Parent Elements</span></span>

|<span data-ttu-id="13e2d-113">元素</span><span class="sxs-lookup"><span data-stu-id="13e2d-113">Element</span></span>|<span data-ttu-id="13e2d-114">说明</span><span class="sxs-lookup"><span data-stu-id="13e2d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13e2d-115">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e2d-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="13e2d-116">定义一组 .NET 对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="13e2d-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="13e2d-117">文本值</span><span class="sxs-lookup"><span data-stu-id="13e2d-117">Text Value</span></span>

<span data-ttu-id="13e2d-118">指定要评估的脚本。</span><span class="sxs-lookup"><span data-stu-id="13e2d-118">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="13e2d-119">备注</span><span class="sxs-lookup"><span data-stu-id="13e2d-119">Remarks</span></span>

<span data-ttu-id="13e2d-120">每当此脚本的值发生更改时，PowerShell 就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="13e2d-120">PowerShell starts a new group whenever the value of this script changes.</span></span>

<span data-ttu-id="13e2d-121">如果指定此元素，则不能指定[PropertyName](propertyname-element-for-groupby-format.md)元素来启动新组。</span><span class="sxs-lookup"><span data-stu-id="13e2d-121">When this element is specified, you cannot specify the [PropertyName](propertyname-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="13e2d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13e2d-122">See Also</span></span>

[<span data-ttu-id="13e2d-123">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="13e2d-123">PropertyName Element for GroupBy (Format)</span></span>](propertyname-element-for-groupby-format.md)

[<span data-ttu-id="13e2d-124">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="13e2d-124">GroupBy Element for View (Format)</span></span>](groupby-element-for-view-format.md)

[<span data-ttu-id="13e2d-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="13e2d-125">Writing a PowerShell Formatting File</span></span>](writing-a-powershell-formatting-file.md)
