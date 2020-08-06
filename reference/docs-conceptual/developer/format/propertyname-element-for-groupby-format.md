---
title: GroupBy (Format) 的 PropertyName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e83ebd49e4f3087c817b3cc8772889dbe85113aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785602"
---
# <a name="propertyname-element-for-groupby-format"></a><span data-ttu-id="56561-102">PropertyName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="56561-102">PropertyName Element for GroupBy (Format)</span></span>

<span data-ttu-id="56561-103">指定在新组的值发生更改时启动新组的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="56561-103">Specifies the .NET property that starts a new group whenever its value changes.</span></span>

<span data-ttu-id="56561-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) GroupBy 元素 (groupby) 格式的 PropertyName 元素 (</span><span class="sxs-lookup"><span data-stu-id="56561-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) PropertyName Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="56561-105">语法</span><span class="sxs-lookup"><span data-stu-id="56561-105">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="56561-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="56561-106">Attributes and Elements</span></span>

<span data-ttu-id="56561-107">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="56561-107">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="56561-108">特性</span><span class="sxs-lookup"><span data-stu-id="56561-108">Attributes</span></span>

<span data-ttu-id="56561-109">无。</span><span class="sxs-lookup"><span data-stu-id="56561-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="56561-110">子元素</span><span class="sxs-lookup"><span data-stu-id="56561-110">Child Elements</span></span>

<span data-ttu-id="56561-111">无。</span><span class="sxs-lookup"><span data-stu-id="56561-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="56561-112">父元素</span><span class="sxs-lookup"><span data-stu-id="56561-112">Parent Elements</span></span>

|<span data-ttu-id="56561-113">元素</span><span class="sxs-lookup"><span data-stu-id="56561-113">Element</span></span>|<span data-ttu-id="56561-114">说明</span><span class="sxs-lookup"><span data-stu-id="56561-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="56561-115">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="56561-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="56561-116">定义一组 .NET 对象的显示方式。</span><span class="sxs-lookup"><span data-stu-id="56561-116">Defines how a group of .NET objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="56561-117">文本值</span><span class="sxs-lookup"><span data-stu-id="56561-117">Text Value</span></span>

<span data-ttu-id="56561-118">指定 .NET 属性名称。</span><span class="sxs-lookup"><span data-stu-id="56561-118">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="56561-119">备注</span><span class="sxs-lookup"><span data-stu-id="56561-119">Remarks</span></span>

<span data-ttu-id="56561-120">每当此属性的值发生更改时，Windows PowerShell 就会启动一个新组。</span><span class="sxs-lookup"><span data-stu-id="56561-120">Windows PowerShell starts a new group whenever the value of this property changes.</span></span>

<span data-ttu-id="56561-121">如果指定此元素，则不能指定[ScriptBlock](./scriptblock-element-for-groupby-format.md)元素来启动新组。</span><span class="sxs-lookup"><span data-stu-id="56561-121">When this element is specified, you cannot specify the [ScriptBlock](./scriptblock-element-for-groupby-format.md) element to start a new group.</span></span>

## <a name="example"></a><span data-ttu-id="56561-122">示例</span><span class="sxs-lookup"><span data-stu-id="56561-122">Example</span></span>

<span data-ttu-id="56561-123">下面的示例演示如何在属性的值更改时启动新组。</span><span class="sxs-lookup"><span data-stu-id="56561-123">The following example shows how to start a new group when the value of a property changes.</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="56561-124">有关包括此元素的完整格式化文件的示例，请参阅[ (GroupBy) 的宽视图](./wide-view-groupby.md)。</span><span class="sxs-lookup"><span data-stu-id="56561-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="56561-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56561-125">See Also</span></span>

[<span data-ttu-id="56561-126">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="56561-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="56561-127">ScriptBlock Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="56561-127">ScriptBlock Element for GroupBy (Format)</span></span>](./scriptblock-element-for-groupby-format.md)

[<span data-ttu-id="56561-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="56561-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
