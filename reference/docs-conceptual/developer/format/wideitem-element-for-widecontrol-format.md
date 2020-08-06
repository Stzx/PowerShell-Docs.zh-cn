---
title: WideControl (Format) 的 WideItem 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6b2f7c97978c20350caeec894589c5995ae7ccc4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779890"
---
# <a name="wideitem-element-for-widecontrol-format"></a><span data-ttu-id="f826e-102">WideItem Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f826e-102">WideItem Element for WideControl (Format)</span></span>

<span data-ttu-id="f826e-103">定义要显示其值的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="f826e-103">Defines the property or script whose value is displayed.</span></span>

<span data-ttu-id="f826e-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f826e-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f826e-105">语法</span><span class="sxs-lookup"><span data-stu-id="f826e-105">Syntax</span></span>

```xml
<WideItem>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <FormatString>FormatPattern</FormatString>
</WideItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f826e-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f826e-106">Attributes and Elements</span></span>

<span data-ttu-id="f826e-107">以下各节描述了元素的属性、子元素和父元素 `WideItem` 。</span><span class="sxs-lookup"><span data-stu-id="f826e-107">The following sections describe the attributes, child elements, and the parent element of the `WideItem` element.</span></span> <span data-ttu-id="f826e-108">`FormatString` 元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="f826e-108">The `FormatString` element is optional.</span></span> <span data-ttu-id="f826e-109">但是，您必须指定 `PropertyName` 或 `ScriptBlock` 元素，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="f826e-109">However, you must specify a `PropertyName` or `ScriptBlock` element, but you cannot specify both.</span></span>

### <a name="attributes"></a><span data-ttu-id="f826e-110">特性</span><span class="sxs-lookup"><span data-stu-id="f826e-110">Attributes</span></span>

<span data-ttu-id="f826e-111">无。</span><span class="sxs-lookup"><span data-stu-id="f826e-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f826e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f826e-112">Child Elements</span></span>

|<span data-ttu-id="f826e-113">元素</span><span class="sxs-lookup"><span data-stu-id="f826e-113">Element</span></span>|<span data-ttu-id="f826e-114">描述</span><span class="sxs-lookup"><span data-stu-id="f826e-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f826e-115">FormatString Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f826e-115">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="f826e-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="f826e-116">Optional element.</span></span><br /><br /> <span data-ttu-id="f826e-117">指定定义属性或脚本值在视图中显示方式的格式模式。</span><span class="sxs-lookup"><span data-stu-id="f826e-117">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>|
|[<span data-ttu-id="f826e-118">WideItem (格式的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="f826e-118">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="f826e-119">指定对象的属性，其值显示在宽视图中。</span><span class="sxs-lookup"><span data-stu-id="f826e-119">Specifies the property of the object whose value is displayed in the wide view.</span></span>|
|[<span data-ttu-id="f826e-120">WideItem 的 ScriptBlock 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f826e-120">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)|<span data-ttu-id="f826e-121">指定其值在宽视图中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="f826e-121">Specifies the script whose value is displayed in the wide view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f826e-122">父元素</span><span class="sxs-lookup"><span data-stu-id="f826e-122">Parent Elements</span></span>

|<span data-ttu-id="f826e-123">元素</span><span class="sxs-lookup"><span data-stu-id="f826e-123">Element</span></span>|<span data-ttu-id="f826e-124">描述</span><span class="sxs-lookup"><span data-stu-id="f826e-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f826e-125">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f826e-125">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)|<span data-ttu-id="f826e-126">提供宽视图的定义。</span><span class="sxs-lookup"><span data-stu-id="f826e-126">Provides a definition of the wide view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f826e-127">备注</span><span class="sxs-lookup"><span data-stu-id="f826e-127">Remarks</span></span>

<span data-ttu-id="f826e-128">有关宽视图组件的详细信息，请参阅[宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f826e-128">For more information about the components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f826e-129">示例</span><span class="sxs-lookup"><span data-stu-id="f826e-129">Example</span></span>

<span data-ttu-id="f826e-130">下面的示例演示一个 `WideEntry` 元素，该元素定义单个 `WideItem` 元素。</span><span class="sxs-lookup"><span data-stu-id="f826e-130">The following example shows a `WideEntry` element that defines a single `WideItem` element.</span></span> <span data-ttu-id="f826e-131">`WideItem`元素定义其值在视图中显示的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="f826e-131">The `WideItem` element defines the property or script whose value is displayed in the view.</span></span>

```xml
<WideEntry>
  <WideItem>
    <PropertyName>ProcessName</PropertyName>
  </WideItem>
</WideEntry>
```

<span data-ttu-id="f826e-132">有关宽视图的完整示例，请参阅[宽视图 (基本) ](./wide-view-basic.md)。</span><span class="sxs-lookup"><span data-stu-id="f826e-132">For a complete example of a wide view, see [Wide View (Basic)](./wide-view-basic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f826e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f826e-133">See Also</span></span>

[<span data-ttu-id="f826e-134">FormatString Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f826e-134">FormatString Element for WideItem for WideControl (Format)</span></span>](./formatstring-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="f826e-135">WideItem (格式的 PropertyName 元素) </span><span class="sxs-lookup"><span data-stu-id="f826e-135">PropertyName Element for WideItem (Format)</span></span>](./propertyname-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="f826e-136">WideItem 的 ScriptBlock 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f826e-136">ScriptBlock Element for WideItem (Format)</span></span>](./scriptblock-element-for-wideitem-for-widecontrol-format.md)

[<span data-ttu-id="f826e-137">WideEntry 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="f826e-137">WideEntry Element (Format)</span></span>](./wideentry-element-for-widecontrol-format.md)

[<span data-ttu-id="f826e-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f826e-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
