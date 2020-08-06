---
title: View (Format) 的控件的 CustomControl 的 CustomEntries 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a52bd2368044c34a0b73da331785d55597e30260
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783698"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-view-format"></a><span data-ttu-id="dcbdc-102">CustomEntries Element for CustomControl for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dcbdc-102">CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

<span data-ttu-id="dcbdc-103">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-103">Provides the definitions for the control.</span></span> <span data-ttu-id="dcbdc-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="dcbdc-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="dcbdc-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="dcbdc-106">语法</span><span class="sxs-lookup"><span data-stu-id="dcbdc-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dcbdc-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dcbdc-107">Attributes and Elements</span></span>

<span data-ttu-id="dcbdc-108">以下各节描述了元素的属性、子元素和父元素 `CustomEntries` 。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-108">The following sections describe attributes, child elements, and parent elements of the `CustomEntries` element.</span></span> <span data-ttu-id="dcbdc-109">对于可指定的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-109">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="dcbdc-110">特性</span><span class="sxs-lookup"><span data-stu-id="dcbdc-110">Attributes</span></span>

<span data-ttu-id="dcbdc-111">无。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="dcbdc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="dcbdc-112">Child Elements</span></span>

|<span data-ttu-id="dcbdc-113">元素</span><span class="sxs-lookup"><span data-stu-id="dcbdc-113">Element</span></span>|<span data-ttu-id="dcbdc-114">描述</span><span class="sxs-lookup"><span data-stu-id="dcbdc-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dcbdc-115">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dcbdc-115">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="dcbdc-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-116">Required element.</span></span><br /><br /> <span data-ttu-id="dcbdc-117">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-117">Provides a definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="dcbdc-118">父元素</span><span class="sxs-lookup"><span data-stu-id="dcbdc-118">Parent Elements</span></span>

|<span data-ttu-id="dcbdc-119">元素</span><span class="sxs-lookup"><span data-stu-id="dcbdc-119">Element</span></span>|<span data-ttu-id="dcbdc-120">描述</span><span class="sxs-lookup"><span data-stu-id="dcbdc-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="dcbdc-121">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dcbdc-121">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="dcbdc-122">定义视图使用的控件。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-122">Defines the control used by the view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dcbdc-123">备注</span><span class="sxs-lookup"><span data-stu-id="dcbdc-123">Remarks</span></span>

<span data-ttu-id="dcbdc-124">在大多数情况下，控件只有一个定义，该定义是在单个元素中指定的 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-124">In most cases, a control has only one definition, which is specified in a single `CustomEntry` element.</span></span> <span data-ttu-id="dcbdc-125">但是，如果您希望使用同一控件显示不同的 .NET 对象，则可以提供多个定义。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-125">However, it is possible to provide multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="dcbdc-126">在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。</span><span class="sxs-lookup"><span data-stu-id="dcbdc-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="dcbdc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcbdc-127">See Also</span></span>

[<span data-ttu-id="dcbdc-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dcbdc-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="dcbdc-129">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="dcbdc-129">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="dcbdc-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="dcbdc-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
