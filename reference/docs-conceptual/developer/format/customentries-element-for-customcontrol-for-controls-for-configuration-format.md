---
ms.date: 09/13/2016
ms.topic: reference
title: CustomEntries Element for CustomControl for Controls for Configuration (Format)
description: CustomEntries Element for CustomControl for Controls for Configuration (Format)
ms.openlocfilehash: 86c2b517d0d7075a355a3190a14e25d9dd4fe374
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655387"
---
# <a name="customentries-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="d366b-103">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d366b-103">CustomEntries Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d366b-104">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="d366b-104">Provides the definitions of a common control.</span></span> <span data-ttu-id="d366b-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="d366b-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="d366b-106">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 控件元素 (CustomEntries 元素 for for Configuration) 格式 (</span><span class="sxs-lookup"><span data-stu-id="d366b-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d366b-107">语法</span><span class="sxs-lookup"><span data-stu-id="d366b-107">Syntax</span></span>

```xml
<CustomEntries>
  <CustomEntry>...</CustomEntry>
</CustomEntries>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="d366b-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d366b-108">Attributes and Elements</span></span>

<span data-ttu-id="d366b-109">以下各节描述了元素的属性、子元素和父元素 `CustomEntries` 。</span><span class="sxs-lookup"><span data-stu-id="d366b-109">The following sections describe attributes, child elements, and the parent element of the `CustomEntries` element.</span></span> <span data-ttu-id="d366b-110">您必须指定一个或多个子元素。</span><span class="sxs-lookup"><span data-stu-id="d366b-110">You must specify one or more child elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d366b-111">特性</span><span class="sxs-lookup"><span data-stu-id="d366b-111">Attributes</span></span>

<span data-ttu-id="d366b-112">无。</span><span class="sxs-lookup"><span data-stu-id="d366b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d366b-113">子元素</span><span class="sxs-lookup"><span data-stu-id="d366b-113">Child Elements</span></span>

|<span data-ttu-id="d366b-114">元素</span><span class="sxs-lookup"><span data-stu-id="d366b-114">Element</span></span>|<span data-ttu-id="d366b-115">描述</span><span class="sxs-lookup"><span data-stu-id="d366b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d366b-116">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d366b-116">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="d366b-117">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="d366b-117">Provides a definition of the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d366b-118">父元素</span><span class="sxs-lookup"><span data-stu-id="d366b-118">Parent Elements</span></span>

|<span data-ttu-id="d366b-119">元素</span><span class="sxs-lookup"><span data-stu-id="d366b-119">Element</span></span>|<span data-ttu-id="d366b-120">描述</span><span class="sxs-lookup"><span data-stu-id="d366b-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d366b-121">用于控制配置 (格式的 CustomControl 元素) </span><span class="sxs-lookup"><span data-stu-id="d366b-121">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="d366b-122">定义公共控件。</span><span class="sxs-lookup"><span data-stu-id="d366b-122">Defines a common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d366b-123">备注</span><span class="sxs-lookup"><span data-stu-id="d366b-123">Remarks</span></span>

<span data-ttu-id="d366b-124">在大多数情况下，控件只有一个定义，该定义在单个元素中定义 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="d366b-124">In most cases, a control has only one definition, which is defined in a single `CustomEntry` element.</span></span> <span data-ttu-id="d366b-125">但是，如果希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="d366b-125">However it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="d366b-126">在这些情况下，可以 `CustomEntry` 为每个对象或一组对象定义一个元素。</span><span class="sxs-lookup"><span data-stu-id="d366b-126">In those cases, you can define a `CustomEntry` element for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="d366b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d366b-127">See Also</span></span>

[<span data-ttu-id="d366b-128">用于控制配置 (格式的 CustomControl 元素) </span><span class="sxs-lookup"><span data-stu-id="d366b-128">CustomControl Element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="d366b-129">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d366b-129">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>](./customentry-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="d366b-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d366b-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
