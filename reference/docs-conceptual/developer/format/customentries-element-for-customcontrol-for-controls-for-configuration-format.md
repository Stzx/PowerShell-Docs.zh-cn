---
title: 用于) 配置 (格式的控件的 CustomControl 的 CustomEntries 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b1f494cf1a254d71362830ba9eb0f4905a2a484d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785976"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="154b1-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="154b1-102">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="154b1-103">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="154b1-103">Provides the definitions of a common control.</span></span> <span data-ttu-id="154b1-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="154b1-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="154b1-105">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for for Configuration) 格式 (</span><span class="sxs-lookup"><span data-stu-id="154b1-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="154b1-106">语法</span><span class="sxs-lookup"><span data-stu-id="154b1-106">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="154b1-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="154b1-107">Attributes and Elements</span></span>

<span data-ttu-id="154b1-108">以下各节描述了元素的属性、子元素和父元素 `CustomEntries` 。</span><span class="sxs-lookup"><span data-stu-id="154b1-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="154b1-109">您必须指定一个或多个子元素。</span><span class="sxs-lookup"><span data-stu-id="154b1-109">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="154b1-110">特性</span><span class="sxs-lookup"><span data-stu-id="154b1-110">Attributes</span></span>

<span data-ttu-id="154b1-111">无。</span><span class="sxs-lookup"><span data-stu-id="154b1-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="154b1-112">子元素</span><span class="sxs-lookup"><span data-stu-id="154b1-112">Child Elements</span></span>

|<span data-ttu-id="154b1-113">元素</span><span class="sxs-lookup"><span data-stu-id="154b1-113">Element</span></span>|<span data-ttu-id="154b1-114">说明</span><span class="sxs-lookup"><span data-stu-id="154b1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="154b1-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="154b1-115">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="154b1-116">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="154b1-116">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="154b1-117">父元素</span><span class="sxs-lookup"><span data-stu-id="154b1-117">Parent Elements</span></span>

|<span data-ttu-id="154b1-118">元素</span><span class="sxs-lookup"><span data-stu-id="154b1-118">Element</span></span>|<span data-ttu-id="154b1-119">说明</span><span class="sxs-lookup"><span data-stu-id="154b1-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="154b1-120">用于控制配置 (格式的 CustomControl 元素) </span><span class="sxs-lookup"><span data-stu-id="154b1-120">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="154b1-121">定义公共控件。</span><span class="sxs-lookup"><span data-stu-id="154b1-121">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="154b1-122">备注</span><span class="sxs-lookup"><span data-stu-id="154b1-122">Remarks</span></span>

<span data-ttu-id="154b1-123">在大多数情况下，控件只有一个定义，该定义在单个元素中定义 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="154b1-123">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="154b1-124">但是，如果希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="154b1-124">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="154b1-125">在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。</span><span class="sxs-lookup"><span data-stu-id="154b1-125">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="154b1-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="154b1-126">See Also</span></span>

[<span data-ttu-id="154b1-127">用于控制配置 (格式的 CustomControl 元素) </span><span class="sxs-lookup"><span data-stu-id="154b1-127">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="154b1-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="154b1-128">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="154b1-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="154b1-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
