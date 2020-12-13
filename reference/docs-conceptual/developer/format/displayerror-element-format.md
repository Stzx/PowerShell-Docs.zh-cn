---
ms.date: 09/13/2016
ms.topic: reference
title: DisplayError Element (Format)
description: DisplayError Element (Format)
ms.openlocfilehash: fb54df86a3558263687a8c417870495b7066f563
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649933"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="071b0-103">DisplayError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="071b0-103">DisplayError Element (Format)</span></span>

<span data-ttu-id="071b0-104">指定在显示一段数据时出现错误时显示字符串 #ERR。</span><span class="sxs-lookup"><span data-stu-id="071b0-104">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="071b0-105">配置元素 (格式) DefaultSettings 元素 (格式) DisplayError 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="071b0-105">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="071b0-106">语法</span><span class="sxs-lookup"><span data-stu-id="071b0-106">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="071b0-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="071b0-107">Attributes and Elements</span></span>

<span data-ttu-id="071b0-108">以下各节描述了元素的属性、子元素和父元素 `DisplayError` 。</span><span class="sxs-lookup"><span data-stu-id="071b0-108">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="071b0-109">特性</span><span class="sxs-lookup"><span data-stu-id="071b0-109">Attributes</span></span>

<span data-ttu-id="071b0-110">无。</span><span class="sxs-lookup"><span data-stu-id="071b0-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="071b0-111">子元素</span><span class="sxs-lookup"><span data-stu-id="071b0-111">Child Elements</span></span>

<span data-ttu-id="071b0-112">无。</span><span class="sxs-lookup"><span data-stu-id="071b0-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="071b0-113">父元素</span><span class="sxs-lookup"><span data-stu-id="071b0-113">Parent Elements</span></span>

|<span data-ttu-id="071b0-114">元素</span><span class="sxs-lookup"><span data-stu-id="071b0-114">Element</span></span>|<span data-ttu-id="071b0-115">描述</span><span class="sxs-lookup"><span data-stu-id="071b0-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="071b0-116">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="071b0-116">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="071b0-117">定义适用于格式设置文件的所有视图的常见设置。</span><span class="sxs-lookup"><span data-stu-id="071b0-117">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="071b0-118">备注</span><span class="sxs-lookup"><span data-stu-id="071b0-118">Remarks</span></span>

<span data-ttu-id="071b0-119">默认情况下，在尝试显示一段数据的过程中出现错误时，数据的位置将保留为空。</span><span class="sxs-lookup"><span data-stu-id="071b0-119">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="071b0-120">如果此元素设置为 true，则将显示 #ERR 字符串。</span><span class="sxs-lookup"><span data-stu-id="071b0-120">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="071b0-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="071b0-121">See Also</span></span>

[<span data-ttu-id="071b0-122">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="071b0-122">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="071b0-123">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="071b0-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
