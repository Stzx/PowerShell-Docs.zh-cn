---
title: GroupBy (Format) 的 CustomControl 的 CustomEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4df8e5b96868b3814c6d84fa329950bb5345ef6e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785908"
---
# <a name="customentry-element-for-customcontrol-for-groupby-format"></a><span data-ttu-id="b170a-102">CustomEntry Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b170a-102">CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

<span data-ttu-id="b170a-103">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="b170a-103">Provides a definition of the control.</span></span> <span data-ttu-id="b170a-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="b170a-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="b170a-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素 (格式) CustomEntries 元素 for CustomControl for groupby (format) CustomEntry 元素 for CustomControl for GroupBy (格式) </span><span class="sxs-lookup"><span data-stu-id="b170a-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b170a-106">语法</span><span class="sxs-lookup"><span data-stu-id="b170a-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b170a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b170a-107">Attributes and Elements</span></span>

<span data-ttu-id="b170a-108">以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="b170a-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b170a-109">特性</span><span class="sxs-lookup"><span data-stu-id="b170a-109">Attributes</span></span>

<span data-ttu-id="b170a-110">无。</span><span class="sxs-lookup"><span data-stu-id="b170a-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b170a-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b170a-111">Child Elements</span></span>

|<span data-ttu-id="b170a-112">元素</span><span class="sxs-lookup"><span data-stu-id="b170a-112">Element</span></span>|<span data-ttu-id="b170a-113">说明</span><span class="sxs-lookup"><span data-stu-id="b170a-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b170a-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b170a-114">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="b170a-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="b170a-115">Optional element.</span></span><br /><br /> <span data-ttu-id="b170a-116">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="b170a-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="b170a-117">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b170a-117">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="b170a-118">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="b170a-118">Required element.</span></span><br /><br /> <span data-ttu-id="b170a-119">定义控件显示数据的方式。</span><span class="sxs-lookup"><span data-stu-id="b170a-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b170a-120">父元素</span><span class="sxs-lookup"><span data-stu-id="b170a-120">Parent Elements</span></span>

|<span data-ttu-id="b170a-121">元素</span><span class="sxs-lookup"><span data-stu-id="b170a-121">Element</span></span>|<span data-ttu-id="b170a-122">说明</span><span class="sxs-lookup"><span data-stu-id="b170a-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b170a-123">CustomEntries Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b170a-123">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)|<span data-ttu-id="b170a-124">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="b170a-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b170a-125">备注</span><span class="sxs-lookup"><span data-stu-id="b170a-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b170a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b170a-126">See Also</span></span>

[<span data-ttu-id="b170a-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b170a-127">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="b170a-128">CustomItem Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b170a-128">CustomItem Element for CustomEntry for GroupBy (Format)</span></span>](./customitem-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="b170a-129">CustomEntries Element for CustomControl for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="b170a-129">CustomEntries Element for CustomControl for GroupBy (Format)</span></span>](./customentries-element-for-customcontrol-for-groupby-format.md)

[<span data-ttu-id="b170a-130">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b170a-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
