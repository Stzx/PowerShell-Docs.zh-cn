---
title: " (格式) 的控件的框架的 FirstLineHanging 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 6c0429a5caa5d20370acff72fa5707ed8cf7ad01
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773736"
---
# <a name="firstlinehanging-element-for-frame-for-controls-for-configuration-format"></a><span data-ttu-id="fd2af-102">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="fd2af-102">FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

<span data-ttu-id="fd2af-103">指定将第一行数据向左移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="fd2af-103">Specifies how many characters the first line of data is shifted to the left.</span></span> <span data-ttu-id="fd2af-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="fd2af-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="fd2af-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) CustomEntries 元素，用于 CustomControl 的 for configuration (格式) CustomEntry 元素对于 CustomControl for control for control (Format) CustomItem 元素 For CustomEntry For CustomItem For control for For control for For control for For control for For control for control (format 的控件，用于配置的控件 () </span><span class="sxs-lookup"><span data-stu-id="fd2af-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration Frame Element for CustomItem for Controls for Configuration (Format) FirstLineHanging Element for Frame for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fd2af-106">语法</span><span class="sxs-lookup"><span data-stu-id="fd2af-106">Syntax</span></span>

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fd2af-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fd2af-107">Attributes and Elements</span></span>

<span data-ttu-id="fd2af-108">以下各节描述了元素的属性、子元素和父元素 `FirstLineHanging` 。</span><span class="sxs-lookup"><span data-stu-id="fd2af-108">The following sections describe attributes, child elements, and parent element of the `FirstLineHanging` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fd2af-109">特性</span><span class="sxs-lookup"><span data-stu-id="fd2af-109">Attributes</span></span>

<span data-ttu-id="fd2af-110">无。</span><span class="sxs-lookup"><span data-stu-id="fd2af-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fd2af-111">子元素</span><span class="sxs-lookup"><span data-stu-id="fd2af-111">Child Elements</span></span>

<span data-ttu-id="fd2af-112">无。</span><span class="sxs-lookup"><span data-stu-id="fd2af-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fd2af-113">父元素</span><span class="sxs-lookup"><span data-stu-id="fd2af-113">Parent Elements</span></span>

|<span data-ttu-id="fd2af-114">元素</span><span class="sxs-lookup"><span data-stu-id="fd2af-114">Element</span></span>|<span data-ttu-id="fd2af-115">说明</span><span class="sxs-lookup"><span data-stu-id="fd2af-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fd2af-116">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="fd2af-116">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="fd2af-117">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="fd2af-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fd2af-118">文本值</span><span class="sxs-lookup"><span data-stu-id="fd2af-118">Text Value</span></span>

<span data-ttu-id="fd2af-119">指定要将数据的第一行移动到的字符数。</span><span class="sxs-lookup"><span data-stu-id="fd2af-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd2af-120">备注</span><span class="sxs-lookup"><span data-stu-id="fd2af-120">Remarks</span></span>

<span data-ttu-id="fd2af-121">如果指定此元素，则不能指定 `FirstLineIndent` 元素。</span><span class="sxs-lookup"><span data-stu-id="fd2af-121">If this element is specified, you cannot specify the `FirstLineIndent` element.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd2af-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd2af-122">See Also</span></span>

[<span data-ttu-id="fd2af-123">Frame Element for CustomItem for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="fd2af-123">Frame Element for CustomItem for Controls for Configuration (Format)</span></span>](./frame-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="fd2af-124">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="fd2af-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
