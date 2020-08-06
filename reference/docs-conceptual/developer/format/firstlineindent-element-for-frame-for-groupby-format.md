---
title: GroupBy (Format) 的帧的 FirstLineIndent 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: def5b4e9ca98a15edbb36675ca506e886de567dc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781658"
---
# <a name="firstlineindent-element-for-frame-for-groupby-format"></a><span data-ttu-id="1571d-102">FirstLineIndent Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1571d-102">FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

<span data-ttu-id="1571d-103">指定第一行数据向右移动的字符数。</span><span class="sxs-lookup"><span data-stu-id="1571d-103">Specifies how many characters the first line of data is shifted to the right.</span></span> <span data-ttu-id="1571d-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="1571d-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="1571d-105">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) CustomItem 元素 for CustomEntry for groupby (格式) </span><span class="sxs-lookup"><span data-stu-id="1571d-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) CustomItem Element for CustomEntry for GroupBy (Format) Frame Element for CustomItem for GroupBy (Format) FirstLineIndent Element for Frame for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1571d-106">语法</span><span class="sxs-lookup"><span data-stu-id="1571d-106">Syntax</span></span>

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1571d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1571d-107">Attributes and Elements</span></span>

<span data-ttu-id="1571d-108">以下各节描述了元素的属性、子元素和父元素 `FirstLineIndent` 。</span><span class="sxs-lookup"><span data-stu-id="1571d-108">The following sections describe attributes, child elements, and parent element of the `FirstLineIndent` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1571d-109">特性</span><span class="sxs-lookup"><span data-stu-id="1571d-109">Attributes</span></span>

<span data-ttu-id="1571d-110">无。</span><span class="sxs-lookup"><span data-stu-id="1571d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1571d-111">子元素</span><span class="sxs-lookup"><span data-stu-id="1571d-111">Child Elements</span></span>

<span data-ttu-id="1571d-112">无。</span><span class="sxs-lookup"><span data-stu-id="1571d-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1571d-113">父元素</span><span class="sxs-lookup"><span data-stu-id="1571d-113">Parent Elements</span></span>

|<span data-ttu-id="1571d-114">元素</span><span class="sxs-lookup"><span data-stu-id="1571d-114">Element</span></span>|<span data-ttu-id="1571d-115">描述</span><span class="sxs-lookup"><span data-stu-id="1571d-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1571d-116">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1571d-116">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)|<span data-ttu-id="1571d-117">定义数据的显示方式，例如，将数据向左或向右移动。</span><span class="sxs-lookup"><span data-stu-id="1571d-117">Defines how the data is displayed, such as shifting the data to the left or right.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1571d-118">文本值</span><span class="sxs-lookup"><span data-stu-id="1571d-118">Text Value</span></span>

<span data-ttu-id="1571d-119">指定要将数据的第一行移动到的字符数。</span><span class="sxs-lookup"><span data-stu-id="1571d-119">Specify the number of characters that you want to shift the first line of the data.</span></span>

## <a name="remarks"></a><span data-ttu-id="1571d-120">备注</span><span class="sxs-lookup"><span data-stu-id="1571d-120">Remarks</span></span>

<span data-ttu-id="1571d-121">如果指定此元素，则不能指定[FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="1571d-121">If this element is specified, you cannot specify the [FirstLineHanging](./firstlinehanging-element-for-frame-for-groupby-format.md) element.</span></span>

## <a name="see-also"></a><span data-ttu-id="1571d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1571d-122">See Also</span></span>

[<span data-ttu-id="1571d-123">FirstLineHanging Element for Frame for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1571d-123">FirstLineHanging Element for Frame for GroupBy (Format)</span></span>](./firstlinehanging-element-for-frame-for-groupby-format.md)

[<span data-ttu-id="1571d-124">Frame Element for CustomItem for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1571d-124">Frame Element for CustomItem for GroupBy (Format)</span></span>](./frame-element-for-customitem-for-groupby-format.md)

[<span data-ttu-id="1571d-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="1571d-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
