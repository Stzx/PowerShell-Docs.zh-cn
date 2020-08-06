---
title: 用于控件 (Format) 的控件的 CustomControl 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5aacf824421dfce19f1f495fc0a95e766cdbaf8b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786078"
---
# <a name="customcontrol-element-for-control-for-controls-for-configuration-format"></a><span data-ttu-id="17a5c-102">CustomControl Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="17a5c-102">CustomControl Element for Control for Controls for Configuration (Format)</span></span>

<span data-ttu-id="17a5c-103">定义控件。</span><span class="sxs-lookup"><span data-stu-id="17a5c-103">Defines a control.</span></span> <span data-ttu-id="17a5c-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="17a5c-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="17a5c-105">配置元素 (格式) 控制配置 (格式) 控件元素，用于配置 (格式的控件) CustomControl 元素，以控制配置 (格式) </span><span class="sxs-lookup"><span data-stu-id="17a5c-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="17a5c-106">语法</span><span class="sxs-lookup"><span data-stu-id="17a5c-106">Syntax</span></span>

```xml
<CustomControl>
  <CustomEntries>...</CustomEntries>
</CustomControl>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="17a5c-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="17a5c-107">Attributes and Elements</span></span>

<span data-ttu-id="17a5c-108">以下各节描述了元素的属性、子元素和父元素 `CustomControl` 。</span><span class="sxs-lookup"><span data-stu-id="17a5c-108">The following sections describe the attributes, child elements, and the parent element of the `CustomControl` element.</span></span> <span data-ttu-id="17a5c-109">此元素必须至少有一个子元素。</span><span class="sxs-lookup"><span data-stu-id="17a5c-109">This element must have at least one child element.</span></span> <span data-ttu-id="17a5c-110">对于可指定的子元素数没有最大限制。</span><span class="sxs-lookup"><span data-stu-id="17a5c-110">There is no maximum limit to the number of child elements that can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="17a5c-111">特性</span><span class="sxs-lookup"><span data-stu-id="17a5c-111">Attributes</span></span>

<span data-ttu-id="17a5c-112">无。</span><span class="sxs-lookup"><span data-stu-id="17a5c-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="17a5c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="17a5c-113">Child Elements</span></span>

|<span data-ttu-id="17a5c-114">元素</span><span class="sxs-lookup"><span data-stu-id="17a5c-114">Element</span></span>|<span data-ttu-id="17a5c-115">说明</span><span class="sxs-lookup"><span data-stu-id="17a5c-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="17a5c-116">用于配置 (格式的 CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="17a5c-116">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)|<span data-ttu-id="17a5c-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="17a5c-117">Required element.</span></span><br /><br /> <span data-ttu-id="17a5c-118">提供控件的定义。</span><span class="sxs-lookup"><span data-stu-id="17a5c-118">Provides the definitions of a control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="17a5c-119">父元素</span><span class="sxs-lookup"><span data-stu-id="17a5c-119">Parent Elements</span></span>

|<span data-ttu-id="17a5c-120">元素</span><span class="sxs-lookup"><span data-stu-id="17a5c-120">Element</span></span>|<span data-ttu-id="17a5c-121">说明</span><span class="sxs-lookup"><span data-stu-id="17a5c-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="17a5c-122">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="17a5c-122">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="17a5c-123">定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。</span><span class="sxs-lookup"><span data-stu-id="17a5c-123">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="17a5c-124">备注</span><span class="sxs-lookup"><span data-stu-id="17a5c-124">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="17a5c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17a5c-125">See Also</span></span>

[<span data-ttu-id="17a5c-126">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="17a5c-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="17a5c-127">用于配置 (格式的 CustomControl 的 CustomEntries 元素) </span><span class="sxs-lookup"><span data-stu-id="17a5c-127">CustomEntries Element for CustomControl for Configuration (Format)</span></span>](./customentries-element-for-customcontrol-for-controls-for-configuration-format.md)

[<span data-ttu-id="17a5c-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="17a5c-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
