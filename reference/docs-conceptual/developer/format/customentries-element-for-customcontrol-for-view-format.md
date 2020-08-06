---
title: CustomControl 的 CustomEntries 元素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c89eb25f6922a92e2c18298d0128c4c2ca93df3d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785959"
---
# <a name="customentries-element-for-customcontrol-for-view-format"></a><span data-ttu-id="7d245-102">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="7d245-102">CustomEntries Element for CustomControl for View (Format)</span></span>

<span data-ttu-id="7d245-103">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="7d245-103">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="7d245-104">自定义控件视图必须指定一个或多个定义。</span><span class="sxs-lookup"><span data-stu-id="7d245-104">The custom control view must specify one or more definitions.</span></span>

<span data-ttu-id="7d245-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) CustomControl 元素 (格式) CustomEntries 元素，CustomControl 的元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="7d245-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d245-106">语法</span><span class="sxs-lookup"><span data-stu-id="7d245-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7d245-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7d245-107">Attributes and Elements</span></span>

<span data-ttu-id="7d245-108">以下各节描述了元素的属性、子元素和父元素 `CustomControlEntries` 。</span><span class="sxs-lookup"><span data-stu-id="7d245-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlEntries` element.</span></span> <span data-ttu-id="7d245-109">您必须指定一个或多个子元素。</span><span class="sxs-lookup"><span data-stu-id="7d245-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7d245-110">特性</span><span class="sxs-lookup"><span data-stu-id="7d245-110">Attributes</span></span>

<span data-ttu-id="7d245-111">无。</span><span class="sxs-lookup"><span data-stu-id="7d245-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="7d245-112">子元素</span><span class="sxs-lookup"><span data-stu-id="7d245-112">Child Elements</span></span>

|<span data-ttu-id="7d245-113">元素</span><span class="sxs-lookup"><span data-stu-id="7d245-113">Element</span></span>|<span data-ttu-id="7d245-114">说明</span><span class="sxs-lookup"><span data-stu-id="7d245-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d245-115">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="7d245-115">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="7d245-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="7d245-116">Required element.</span></span><br /><br /> <span data-ttu-id="7d245-117">提供自定义控件视图的定义。</span><span class="sxs-lookup"><span data-stu-id="7d245-117">Provides a definition of the custom control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7d245-118">父元素</span><span class="sxs-lookup"><span data-stu-id="7d245-118">Parent Elements</span></span>

|<span data-ttu-id="7d245-119">元素</span><span class="sxs-lookup"><span data-stu-id="7d245-119">Element</span></span>|<span data-ttu-id="7d245-120">说明</span><span class="sxs-lookup"><span data-stu-id="7d245-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7d245-121">CustomControl Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="7d245-121">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)|<span data-ttu-id="7d245-122">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="7d245-122">Required element.</span></span><br /><br /> <span data-ttu-id="7d245-123">定义视图的自定义控件格式。</span><span class="sxs-lookup"><span data-stu-id="7d245-123">Defines a custom control format for the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7d245-124">备注</span><span class="sxs-lookup"><span data-stu-id="7d245-124">Remarks</span></span>

<span data-ttu-id="7d245-125">在大多数情况下，控件只有一个定义，该定义在单个元素中定义 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="7d245-125">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="7d245-126">但是，如果希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="7d245-126">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="7d245-127">在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。</span><span class="sxs-lookup"><span data-stu-id="7d245-127">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d245-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d245-128">See Also</span></span>

[<span data-ttu-id="7d245-129">CustomControl Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="7d245-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="7d245-130">View (格式的 CustomEntries 的 CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="7d245-130">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="7d245-131">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="7d245-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
