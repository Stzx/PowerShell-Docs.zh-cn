---
title: View (Format) 的控件的 CustomEntries 的 CustomEntry 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4fc960ab803580f684ce0f224b1db4d7d4af1720
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785891"
---
# <a name="customentry-element-for-customentries-for-controls-for-view-format"></a><span data-ttu-id="3d22c-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3d22c-102">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

<span data-ttu-id="3d22c-103">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="3d22c-103">Provides a definition of the control.</span></span> <span data-ttu-id="3d22c-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="3d22c-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="3d22c-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) CustomControl 元素，用于控件的视图 (格式) CustomEntries 元素 (CustomEntry 的控件) CustomEntries</span><span class="sxs-lookup"><span data-stu-id="3d22c-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="3d22c-106">语法</span><span class="sxs-lookup"><span data-stu-id="3d22c-106">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3d22c-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3d22c-107">Attributes and Elements</span></span>

<span data-ttu-id="3d22c-108">以下各节描述了元素的属性、子元素和父元素 `CustomEntry` 。</span><span class="sxs-lookup"><span data-stu-id="3d22c-108">The following sections describe attributes, child elements, and the parent elements of the `CustomEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="3d22c-109">特性</span><span class="sxs-lookup"><span data-stu-id="3d22c-109">Attributes</span></span>

<span data-ttu-id="3d22c-110">无。</span><span class="sxs-lookup"><span data-stu-id="3d22c-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="3d22c-111">子元素</span><span class="sxs-lookup"><span data-stu-id="3d22c-111">Child Elements</span></span>

|<span data-ttu-id="3d22c-112">元素</span><span class="sxs-lookup"><span data-stu-id="3d22c-112">Element</span></span>|<span data-ttu-id="3d22c-113">说明</span><span class="sxs-lookup"><span data-stu-id="3d22c-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3d22c-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3d22c-114">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="3d22c-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="3d22c-115">Optional element.</span></span><br /><br /> <span data-ttu-id="3d22c-116">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="3d22c-116">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="3d22c-117">CustomItem Element for CustomEntry for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3d22c-117">CustomItem Element for CustomEntry for Controls for View (Format)</span></span>](./customitem-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="3d22c-118">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="3d22c-118">Required element.</span></span><br /><br /> <span data-ttu-id="3d22c-119">定义控件显示数据的方式。</span><span class="sxs-lookup"><span data-stu-id="3d22c-119">Defines how the control displays the data.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3d22c-120">父元素</span><span class="sxs-lookup"><span data-stu-id="3d22c-120">Parent Elements</span></span>

|<span data-ttu-id="3d22c-121">元素</span><span class="sxs-lookup"><span data-stu-id="3d22c-121">Element</span></span>|<span data-ttu-id="3d22c-122">说明</span><span class="sxs-lookup"><span data-stu-id="3d22c-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3d22c-123">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3d22c-123">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="3d22c-124">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="3d22c-124">Provides the definitions for the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3d22c-125">备注</span><span class="sxs-lookup"><span data-stu-id="3d22c-125">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="3d22c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d22c-126">See Also</span></span>

[<span data-ttu-id="3d22c-127">CustomEntries Element for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="3d22c-127">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)

[<span data-ttu-id="3d22c-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="3d22c-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
