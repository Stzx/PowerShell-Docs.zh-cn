---
ms.date: 09/13/2016
ms.topic: reference
title: ScriptBlock Element for ListItem for ListControl (Format)
description: ScriptBlock Element for ListItem for ListControl (Format)
ms.openlocfilehash: 0635ac2622cc203a2dc895873621901d956f87da
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664971"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="f7a51-103">ScriptBlock Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f7a51-103">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="f7a51-104">指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="f7a51-104">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="f7a51-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntries for ListControl 的 ListItems 元素) ListEntry (的 ScriptBlock 元素) ListControl (格式) 的 ScriptBlock 元素 (</span><span class="sxs-lookup"><span data-stu-id="f7a51-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f7a51-106">语法</span><span class="sxs-lookup"><span data-stu-id="f7a51-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f7a51-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f7a51-107">Attributes and Elements</span></span>

<span data-ttu-id="f7a51-108">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="f7a51-108">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="f7a51-109">特性</span><span class="sxs-lookup"><span data-stu-id="f7a51-109">Attributes</span></span>

<span data-ttu-id="f7a51-110">无。</span><span class="sxs-lookup"><span data-stu-id="f7a51-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="f7a51-111">子元素</span><span class="sxs-lookup"><span data-stu-id="f7a51-111">Child Elements</span></span>

<span data-ttu-id="f7a51-112">无。</span><span class="sxs-lookup"><span data-stu-id="f7a51-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f7a51-113">父元素</span><span class="sxs-lookup"><span data-stu-id="f7a51-113">Parent Elements</span></span>

|<span data-ttu-id="f7a51-114">元素</span><span class="sxs-lookup"><span data-stu-id="f7a51-114">Element</span></span>|<span data-ttu-id="f7a51-115">描述</span><span class="sxs-lookup"><span data-stu-id="f7a51-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f7a51-116"> (格式的) 元素元素 </span><span class="sxs-lookup"><span data-stu-id="f7a51-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="f7a51-117">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="f7a51-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="f7a51-118">文本值</span><span class="sxs-lookup"><span data-stu-id="f7a51-118">Text Value</span></span>

<span data-ttu-id="f7a51-119">指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="f7a51-119">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7a51-120">备注</span><span class="sxs-lookup"><span data-stu-id="f7a51-120">Remarks</span></span>

<span data-ttu-id="f7a51-121">如果指定此元素，则不能指定 [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="f7a51-121">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="f7a51-122">有关在列表视图中指定脚本的详细信息，请参阅 [列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="f7a51-122">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f7a51-123">示例</span><span class="sxs-lookup"><span data-stu-id="f7a51-123">Example</span></span>

<span data-ttu-id="f7a51-124">下面的示例演示如何指定显示其值的属性。</span><span class="sxs-lookup"><span data-stu-id="f7a51-124">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="f7a51-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7a51-125">See Also</span></span>

[<span data-ttu-id="f7a51-126">PropertyName Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f7a51-126">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="f7a51-127">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="f7a51-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f7a51-128">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f7a51-128">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="f7a51-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="f7a51-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
