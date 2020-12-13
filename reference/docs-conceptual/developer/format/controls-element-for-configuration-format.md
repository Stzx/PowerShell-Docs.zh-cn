---
ms.date: 09/13/2016
ms.topic: reference
title: Controls Element for Configuration (Format)
description: Controls Element for Configuration (Format)
ms.openlocfilehash: 53f874ddccf3b4f1f0a23aad608e786524bde830
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668093"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="be081-103">Controls Element for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="be081-103">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="be081-104">定义可供格式设置文件的所有视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="be081-104">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="be081-105">配置元素 (格式) 配置 (格式的元素) </span><span class="sxs-lookup"><span data-stu-id="be081-105">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="be081-106">语法</span><span class="sxs-lookup"><span data-stu-id="be081-106">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="be081-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="be081-107">Attributes and Elements</span></span>

<span data-ttu-id="be081-108">以下各节描述了元素的属性、子元素和父元素 `Controls` 。</span><span class="sxs-lookup"><span data-stu-id="be081-108">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="be081-109">特性</span><span class="sxs-lookup"><span data-stu-id="be081-109">Attributes</span></span>

<span data-ttu-id="be081-110">无。</span><span class="sxs-lookup"><span data-stu-id="be081-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="be081-111">子元素</span><span class="sxs-lookup"><span data-stu-id="be081-111">Child Elements</span></span>

|<span data-ttu-id="be081-112">元素</span><span class="sxs-lookup"><span data-stu-id="be081-112">Element</span></span>|<span data-ttu-id="be081-113">描述</span><span class="sxs-lookup"><span data-stu-id="be081-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="be081-114">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="be081-114">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="be081-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="be081-115">Required element.</span></span><br /><br /> <span data-ttu-id="be081-116">定义可供格式设置文件的所有视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="be081-116">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="be081-117">父元素</span><span class="sxs-lookup"><span data-stu-id="be081-117">Parent Elements</span></span>

|<span data-ttu-id="be081-118">元素</span><span class="sxs-lookup"><span data-stu-id="be081-118">Element</span></span>|<span data-ttu-id="be081-119">描述</span><span class="sxs-lookup"><span data-stu-id="be081-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="be081-120">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="be081-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="be081-121">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="be081-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="be081-122">备注</span><span class="sxs-lookup"><span data-stu-id="be081-122">Remarks</span></span>

<span data-ttu-id="be081-123">您可以创建任意数量的公共控件。</span><span class="sxs-lookup"><span data-stu-id="be081-123">You can create any number of common controls.</span></span> <span data-ttu-id="be081-124">对于每个控件，您必须指定用于引用控件和控件组件的名称。</span><span class="sxs-lookup"><span data-stu-id="be081-124">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="be081-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be081-125">See Also</span></span>

[<span data-ttu-id="be081-126">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="be081-126">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="be081-127">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="be081-127">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="be081-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="be081-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
