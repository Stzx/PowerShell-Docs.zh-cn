---
title: GroupBy (格式) 的 CustomControl 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b8265e872d34ea5dbcedfaa1668d21df8c3b35eb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786061"
---
# <a name="customcontrol-element-for-groupby-format"></a><span data-ttu-id="48dae-102">CustomControl Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="48dae-102">CustomControl Element for GroupBy (Format)</span></span>

<span data-ttu-id="48dae-103">定义显示新组的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="48dae-103">Defines the custom control that displays the new group.</span></span>

<span data-ttu-id="48dae-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (CustomControl 元素 for GroupBy) 格式 (</span><span class="sxs-lookup"><span data-stu-id="48dae-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="48dae-105">语法</span><span class="sxs-lookup"><span data-stu-id="48dae-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
<CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="48dae-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48dae-106">Attributes and Elements</span></span>

<span data-ttu-id="48dae-107">以下各节描述了元素的属性、子元素和父元素 `CustomControl` 。</span><span class="sxs-lookup"><span data-stu-id="48dae-107">The following sections describe the attributes, child elements, and parent element of the `CustomControl` element.</span></span> <span data-ttu-id="48dae-108">可以指定任意数量的子元素，并以任意顺序列出它们。</span><span class="sxs-lookup"><span data-stu-id="48dae-108">You can specify any number of child elements and list them in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="48dae-109">特性</span><span class="sxs-lookup"><span data-stu-id="48dae-109">Attributes</span></span>

<span data-ttu-id="48dae-110">无。</span><span class="sxs-lookup"><span data-stu-id="48dae-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="48dae-111">子元素</span><span class="sxs-lookup"><span data-stu-id="48dae-111">Child Elements</span></span>

|<span data-ttu-id="48dae-112">元素</span><span class="sxs-lookup"><span data-stu-id="48dae-112">Element</span></span>|<span data-ttu-id="48dae-113">说明</span><span class="sxs-lookup"><span data-stu-id="48dae-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48dae-114">CustomEntries Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="48dae-114">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="48dae-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="48dae-115">Required element.</span></span><br /><br /> <span data-ttu-id="48dae-116">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="48dae-116">Provides the definitions for the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="48dae-117">父元素</span><span class="sxs-lookup"><span data-stu-id="48dae-117">Parent Elements</span></span>

|<span data-ttu-id="48dae-118">元素</span><span class="sxs-lookup"><span data-stu-id="48dae-118">Element</span></span>|<span data-ttu-id="48dae-119">说明</span><span class="sxs-lookup"><span data-stu-id="48dae-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="48dae-120">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="48dae-120">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="48dae-121">定义 Windows PowerShell 如何显示一组新的对象。</span><span class="sxs-lookup"><span data-stu-id="48dae-121">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="48dae-122">备注</span><span class="sxs-lookup"><span data-stu-id="48dae-122">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="48dae-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48dae-123">See Also</span></span>

[<span data-ttu-id="48dae-124">CustomEntries Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="48dae-124">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="48dae-125">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="48dae-125">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="48dae-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="48dae-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
