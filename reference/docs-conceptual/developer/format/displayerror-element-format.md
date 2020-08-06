---
title: " (格式) 的 DisplayError 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 5d46c2fbd48f592db5ba1b33eb6cead8dc1c4698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774280"
---
# <a name="displayerror-element-format"></a><span data-ttu-id="853f4-102">DisplayError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="853f4-102">DisplayError Element (Format)</span></span>

<span data-ttu-id="853f4-103">指定在显示一段数据时出现错误时显示字符串 #ERR。</span><span class="sxs-lookup"><span data-stu-id="853f4-103">Specifies that the string #ERR is displayed when an error occurs displaying a piece of data.</span></span>

<span data-ttu-id="853f4-104">配置元素 (格式) DefaultSettings 元素 (格式) DisplayError 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="853f4-104">Configuration Element (Format) DefaultSettings Element (Format) DisplayError Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="853f4-105">语法</span><span class="sxs-lookup"><span data-stu-id="853f4-105">Syntax</span></span>

```xml
<DisplayError/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="853f4-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="853f4-106">Attributes and Elements</span></span>

<span data-ttu-id="853f4-107">以下各节描述了元素的属性、子元素和父元素 `DisplayError` 。</span><span class="sxs-lookup"><span data-stu-id="853f4-107">The following sections describe attributes, child elements, and the parent element of the `DisplayError` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="853f4-108">特性</span><span class="sxs-lookup"><span data-stu-id="853f4-108">Attributes</span></span>

<span data-ttu-id="853f4-109">无。</span><span class="sxs-lookup"><span data-stu-id="853f4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="853f4-110">子元素</span><span class="sxs-lookup"><span data-stu-id="853f4-110">Child Elements</span></span>

<span data-ttu-id="853f4-111">无。</span><span class="sxs-lookup"><span data-stu-id="853f4-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="853f4-112">父元素</span><span class="sxs-lookup"><span data-stu-id="853f4-112">Parent Elements</span></span>

|<span data-ttu-id="853f4-113">元素</span><span class="sxs-lookup"><span data-stu-id="853f4-113">Element</span></span>|<span data-ttu-id="853f4-114">说明</span><span class="sxs-lookup"><span data-stu-id="853f4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="853f4-115">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="853f4-115">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)|<span data-ttu-id="853f4-116">定义适用于格式设置文件的所有视图的常见设置。</span><span class="sxs-lookup"><span data-stu-id="853f4-116">Defines common settings that apply to all the views of the formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="853f4-117">备注</span><span class="sxs-lookup"><span data-stu-id="853f4-117">Remarks</span></span>

<span data-ttu-id="853f4-118">默认情况下，在尝试显示一段数据的过程中出现错误时，数据的位置将保留为空。</span><span class="sxs-lookup"><span data-stu-id="853f4-118">By default, when an error occurs while trying to display a piece of data, the location of the data is left blank.</span></span> <span data-ttu-id="853f4-119">如果此元素设置为 true，则将显示 #ERR 字符串。</span><span class="sxs-lookup"><span data-stu-id="853f4-119">When this element is set to true, the #ERR string will be displayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="853f4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="853f4-120">See Also</span></span>

[<span data-ttu-id="853f4-121">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="853f4-121">DefaultSettings Element (Format)</span></span>](./defaultsettings-element-format.md)

[<span data-ttu-id="853f4-122">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="853f4-122">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
