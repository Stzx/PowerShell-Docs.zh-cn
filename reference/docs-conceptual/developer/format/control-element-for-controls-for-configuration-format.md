---
ms.date: 09/13/2016
ms.topic: reference
title: Control Element for Controls for Configuration (Format)
description: Control Element for Controls for Configuration (Format)
ms.openlocfilehash: 43424de025cb89d81533e973abd7c39c09533747
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655658"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="db2cd-103">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="db2cd-103">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="db2cd-104">定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。</span><span class="sxs-lookup"><span data-stu-id="db2cd-104">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="db2cd-105">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="db2cd-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db2cd-106">语法</span><span class="sxs-lookup"><span data-stu-id="db2cd-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db2cd-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="db2cd-107">Attributes and Elements</span></span>

<span data-ttu-id="db2cd-108">以下各节描述了元素的属性、子元素和父元素 `Control` 。</span><span class="sxs-lookup"><span data-stu-id="db2cd-108">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="db2cd-109">必须仅指定每个子元素中的一个。</span><span class="sxs-lookup"><span data-stu-id="db2cd-109">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db2cd-110">特性</span><span class="sxs-lookup"><span data-stu-id="db2cd-110">Attributes</span></span>

<span data-ttu-id="db2cd-111">无。</span><span class="sxs-lookup"><span data-stu-id="db2cd-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db2cd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="db2cd-112">Child Elements</span></span>

|<span data-ttu-id="db2cd-113">元素</span><span class="sxs-lookup"><span data-stu-id="db2cd-113">Element</span></span>|<span data-ttu-id="db2cd-114">描述</span><span class="sxs-lookup"><span data-stu-id="db2cd-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db2cd-115">CustomControl Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="db2cd-115">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="db2cd-116">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="db2cd-116">Required element.</span></span><br /><br /> <span data-ttu-id="db2cd-117">定义控件。</span><span class="sxs-lookup"><span data-stu-id="db2cd-117">Defines the control.</span></span>|
|[<span data-ttu-id="db2cd-118">用于控件的名称元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="db2cd-118">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="db2cd-119">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="db2cd-119">Required element.</span></span><br /><br /> <span data-ttu-id="db2cd-120">指定用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="db2cd-120">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="db2cd-121">父元素</span><span class="sxs-lookup"><span data-stu-id="db2cd-121">Parent Elements</span></span>

|<span data-ttu-id="db2cd-122">元素</span><span class="sxs-lookup"><span data-stu-id="db2cd-122">Element</span></span>|<span data-ttu-id="db2cd-123">描述</span><span class="sxs-lookup"><span data-stu-id="db2cd-123">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db2cd-124">控件的控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="db2cd-124">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="db2cd-125">定义可由格式设置文件的所有视图或其他控件使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="db2cd-125">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="db2cd-126">备注</span><span class="sxs-lookup"><span data-stu-id="db2cd-126">Remarks</span></span>

<span data-ttu-id="db2cd-127">可以在以下元素中引用为此控件指定的名称：</span><span class="sxs-lookup"><span data-stu-id="db2cd-127">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="db2cd-128">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="db2cd-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="db2cd-129">View (格式的 GroupBy 元素) </span><span class="sxs-lookup"><span data-stu-id="db2cd-129">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="db2cd-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db2cd-130">See Also</span></span>

[<span data-ttu-id="db2cd-131">控件的控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="db2cd-131">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="db2cd-132">用于控制配置 (格式的 CustomControl 元素) </span><span class="sxs-lookup"><span data-stu-id="db2cd-132">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="db2cd-133">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="db2cd-133">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="db2cd-134">View (格式的 GroupBy 元素) </span><span class="sxs-lookup"><span data-stu-id="db2cd-134">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="db2cd-135">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="db2cd-135">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="db2cd-136">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="db2cd-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
