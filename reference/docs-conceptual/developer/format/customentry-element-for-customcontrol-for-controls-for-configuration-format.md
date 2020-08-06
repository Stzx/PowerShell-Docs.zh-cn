---
title: 用于) 配置 (格式的控件的 CustomControl 的 CustomEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8b9d18bbb1abce8135f4c27418ad54a1736eb5a6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785925"
---
# <a name="customentry-element-for-customcontrol-for-controls-for-configuration-format"></a><span data-ttu-id="4360e-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4360e-102">CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

<span data-ttu-id="4360e-103">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="4360e-103">Provides a definition of the common control.</span></span> <span data-ttu-id="4360e-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="4360e-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="4360e-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的控件 (CustomEntry 元素) </span><span class="sxs-lookup"><span data-stu-id="4360e-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="4360e-106">语法</span><span class="sxs-lookup"><span data-stu-id="4360e-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="4360e-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4360e-107">Attributes and Elements</span></span>

<span data-ttu-id="4360e-108">以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="4360e-108">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="4360e-109">您必须指定由定义显示的项。</span><span class="sxs-lookup"><span data-stu-id="4360e-109">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="4360e-110">特性</span><span class="sxs-lookup"><span data-stu-id="4360e-110">Attributes</span></span>

<span data-ttu-id="4360e-111">无。</span><span class="sxs-lookup"><span data-stu-id="4360e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4360e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4360e-112">Child Elements</span></span>

|<span data-ttu-id="4360e-113">元素</span><span class="sxs-lookup"><span data-stu-id="4360e-113">Element</span></span>|<span data-ttu-id="4360e-114">说明</span><span class="sxs-lookup"><span data-stu-id="4360e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4360e-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="4360e-115">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="4360e-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="4360e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="4360e-117">定义使用公共控件定义的 .NET 类型或要使用此控件必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="4360e-117">Defines the .NET types that use the definition of the common control or the condition that must exist for this control to be used.</span></span>|
|[<span data-ttu-id="4360e-118">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="4360e-118">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="4360e-119">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="4360e-119">Required element.</span></span><br /><br /> <span data-ttu-id="4360e-120">定义控件显示的数据及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="4360e-120">Defines what data is displayed by the control and how it is displayed.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4360e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="4360e-121">Parent Elements</span></span>

|<span data-ttu-id="4360e-122">元素</span><span class="sxs-lookup"><span data-stu-id="4360e-122">Element</span></span>|<span data-ttu-id="4360e-123">说明</span><span class="sxs-lookup"><span data-stu-id="4360e-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4360e-124">用于配置 (格式的 CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="4360e-124">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="4360e-125">提供公共控件的定义。</span><span class="sxs-lookup"><span data-stu-id="4360e-125">Provides the definitions of the common control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4360e-126">备注</span><span class="sxs-lookup"><span data-stu-id="4360e-126">Remarks</span></span>

<span data-ttu-id="4360e-127">在大多数情况下，每个公共自定义控件只需要一个定义，但如果您希望使用同一控件显示不同的 .NET 对象，则可以有多个定义。</span><span class="sxs-lookup"><span data-stu-id="4360e-127">In most cases, only one definition is required for each common custom control, but it is possible to have multiple definitions if you want to use the same control to display different .NET objects.</span></span> <span data-ttu-id="4360e-128">在这些情况下，可以为每个对象或一组对象提供单独的定义。</span><span class="sxs-lookup"><span data-stu-id="4360e-128">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="4360e-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4360e-129">See Also</span></span>

[<span data-ttu-id="4360e-130">用于配置 (格式的 CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="4360e-130">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="4360e-131">用于配置控件的 CustomEntry 的 CustomItem 元素</span><span class="sxs-lookup"><span data-stu-id="4360e-131">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="4360e-132">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="4360e-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
