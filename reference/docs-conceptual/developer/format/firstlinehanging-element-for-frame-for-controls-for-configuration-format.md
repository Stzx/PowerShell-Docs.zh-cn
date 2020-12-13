---
ms.date: 09/13/2016
ms.topic: reference
title: FirstLineHanging Element for Frame for Controls for Configuration (Format)
description: FirstLineHanging Element for Frame for Controls for Configuration (Format)
ms.openlocfilehash: 94d59ef7b54e036f76e38a3b06b769700443b9fb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655226"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="98323-103">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="98323-103">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="98323-104">指定将第一行数据向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="98323-104">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="98323-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="98323-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="98323-106">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) CustomEntries 元素，用于 CustomControl 的 for configuration (格式) CustomEntry 元素对于 CustomControl for control for control (Format) CustomItem 元素 For CustomEntry For CustomItem For control for For control for For control for For control for For control for control (format 的控件，用于配置的控件 () </span><span class="sxs-lookup"><span data-stu-id="98323-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="98323-107">语法</span><span class="sxs-lookup"><span data-stu-id="98323-107">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="98323-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="98323-108">Attributes and Elements</span></span>

<span data-ttu-id="98323-109">以下各节描述了元素的属性、子元素和父元素 `FirstLineHanging` 。</span><span class="sxs-lookup"><span data-stu-id="98323-109">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="98323-110">特性</span><span class="sxs-lookup"><span data-stu-id="98323-110">Attributes</span></span>

<span data-ttu-id="98323-111">无。</span><span class="sxs-lookup"><span data-stu-id="98323-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="98323-112">子元素</span><span class="sxs-lookup"><span data-stu-id="98323-112">Child Elements</span></span>

<span data-ttu-id="98323-113">无。</span><span class="sxs-lookup"><span data-stu-id="98323-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="98323-114">父元素</span><span class="sxs-lookup"><span data-stu-id="98323-114">Parent Elements</span></span>

|<span data-ttu-id="98323-115">元素</span><span class="sxs-lookup"><span data-stu-id="98323-115">Element</span></span>|<span data-ttu-id="98323-116">描述</span><span class="sxs-lookup"><span data-stu-id="98323-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="98323-117">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="98323-117">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="98323-118">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="98323-118">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="98323-119">文本值</span><span class="sxs-lookup"><span data-stu-id="98323-119">Text Value</span></span>

<span data-ttu-id="98323-120">指定要将数据的第一行移动到的字符数。</span><span class="sxs-lookup"><span data-stu-id="98323-120">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="98323-121">备注</span><span class="sxs-lookup"><span data-stu-id="98323-121">Remarks</span></span>

<span data-ttu-id="98323-122">如果指定此元素，则不能指定 `FirstLineIndent` 元素。</span><span class="sxs-lookup"><span data-stu-id="98323-122">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="98323-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98323-123">See Also</span></span>

[<span data-ttu-id="98323-124">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="98323-124">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="98323-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="98323-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
