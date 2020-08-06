---
title: View (Format) 的 CustomControl 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 660e8fd6531862790a2af7ab27a82e073c230693
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786044"
---
# <a name="customcontrol-element-for-view-format"></a><span data-ttu-id="cc334-102">CustomControl Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="cc334-102">CustomControl Element for View (Format)</span></span>

<span data-ttu-id="cc334-103">定义视图的自定义控件格式。</span><span class="sxs-lookup"><span data-stu-id="cc334-103">Defines a custom control format for the view.</span></span>

<span data-ttu-id="cc334-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="cc334-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cc334-105">语法</span><span class="sxs-lookup"><span data-stu-id="cc334-105">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc334-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cc334-106">Attributes and Elements</span></span>

<span data-ttu-id="cc334-107">以下各节描述了元素的属性、子元素和父元素 `CustomControl` 。</span><span class="sxs-lookup"><span data-stu-id="cc334-107">The following sections describe attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="cc334-108">您必须指定一个子元素。</span><span class="sxs-lookup"><span data-stu-id="cc334-108">You must specify one child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cc334-109">特性</span><span class="sxs-lookup"><span data-stu-id="cc334-109">Attributes</span></span>

<span data-ttu-id="cc334-110">无。</span><span class="sxs-lookup"><span data-stu-id="cc334-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cc334-111">子元素</span><span class="sxs-lookup"><span data-stu-id="cc334-111">Child Elements</span></span>

|<span data-ttu-id="cc334-112">元素</span><span class="sxs-lookup"><span data-stu-id="cc334-112">Element</span></span>|<span data-ttu-id="cc334-113">说明</span><span class="sxs-lookup"><span data-stu-id="cc334-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc334-114">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="cc334-114">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="cc334-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="cc334-115">Required element.</span></span><br /><br /> <span data-ttu-id="cc334-116">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="cc334-116">Provides the definitions of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="cc334-117">父元素</span><span class="sxs-lookup"><span data-stu-id="cc334-117">Parent Elements</span></span>

|<span data-ttu-id="cc334-118">元素</span><span class="sxs-lookup"><span data-stu-id="cc334-118">Element</span></span>|<span data-ttu-id="cc334-119">说明</span><span class="sxs-lookup"><span data-stu-id="cc334-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cc334-120">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cc334-120">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="cc334-121">定义用于显示一个或多个 .NET 对象的视图。</span><span class="sxs-lookup"><span data-stu-id="cc334-121">Defines a view that is used to display one or more .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cc334-122">备注</span><span class="sxs-lookup"><span data-stu-id="cc334-122">Remarks</span></span>

<span data-ttu-id="cc334-123">在大多数情况下，每个控件视图只需要一个定义，但如果您希望使用同一视图显示不同的 .NET 对象，则可以提供多个定义。</span><span class="sxs-lookup"><span data-stu-id="cc334-123">In most cases, only one definition is required for each control view, but it is possible to provide multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="cc334-124">在这些情况下，可以为每个对象或一组对象提供单独的定义。</span><span class="sxs-lookup"><span data-stu-id="cc334-124">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc334-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc334-125">See Also</span></span>

[<span data-ttu-id="cc334-126">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="cc334-126">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="cc334-127">View Element (Format)</span><span class="sxs-lookup"><span data-stu-id="cc334-127">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="cc334-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="cc334-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
