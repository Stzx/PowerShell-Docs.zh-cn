---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for WideItem for WideControl (Format)
description: ScriptBlock Element for WideItem for WideControl (Format)
ms.openlocfilehash: 68e47926e5e6b846c8a0a3dbc16d1f0d59f11dee
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659872"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="92056-103">ScriptBlock Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="92056-103">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="92056-104">指定其值在宽视图中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="92056-104">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="92056-105">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) WideItem 元素 (格式) 的 ScriptBlock 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="92056-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="92056-106">语法</span><span class="sxs-lookup"><span data-stu-id="92056-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="92056-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="92056-107">Attributes and Elements</span></span>

<span data-ttu-id="92056-108">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="92056-108">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="92056-109">特性</span><span class="sxs-lookup"><span data-stu-id="92056-109">Attributes</span></span>

<span data-ttu-id="92056-110">无。</span><span class="sxs-lookup"><span data-stu-id="92056-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="92056-111">子元素</span><span class="sxs-lookup"><span data-stu-id="92056-111">Child Elements</span></span>

<span data-ttu-id="92056-112">无。</span><span class="sxs-lookup"><span data-stu-id="92056-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="92056-113">父元素</span><span class="sxs-lookup"><span data-stu-id="92056-113">Parent Elements</span></span>

|<span data-ttu-id="92056-114">元素</span><span class="sxs-lookup"><span data-stu-id="92056-114">Element</span></span>|<span data-ttu-id="92056-115">描述</span><span class="sxs-lookup"><span data-stu-id="92056-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="92056-116">WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="92056-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="92056-117">定义其值在宽视图中显示的属性或脚本块。</span><span class="sxs-lookup"><span data-stu-id="92056-117">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="92056-118">文本值</span><span class="sxs-lookup"><span data-stu-id="92056-118">Text Value</span></span>

<span data-ttu-id="92056-119">指定显示其值的脚本。</span><span class="sxs-lookup"><span data-stu-id="92056-119">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="92056-120">备注</span><span class="sxs-lookup"><span data-stu-id="92056-120">Remarks</span></span>

<span data-ttu-id="92056-121">有关宽视图组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="92056-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="92056-122">示例</span><span class="sxs-lookup"><span data-stu-id="92056-122">Example</span></span>

<span data-ttu-id="92056-123">此示例演示一个 `WideItem` 元素，该元素定义一个其值在视图中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="92056-123">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="92056-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92056-124">See Also</span></span>

[<span data-ttu-id="92056-125">WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="92056-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="92056-126">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="92056-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="92056-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="92056-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
