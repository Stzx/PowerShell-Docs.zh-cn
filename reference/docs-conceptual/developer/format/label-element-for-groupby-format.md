---
ms.date: 09/13/2016
ms.topic: reference
title: Label Element for GroupBy (Format)
description: Label Element for GroupBy (Format)
ms.openlocfilehash: ff4b0dec01bb5b472b1813540661791b91568eed
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649785"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="1cf62-103">Label Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="1cf62-103">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="1cf62-104">指定在遇到新组时显示的标签。</span><span class="sxs-lookup"><span data-stu-id="1cf62-104">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="1cf62-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) GroupBy 元素 () 格式 (标签元素) </span><span class="sxs-lookup"><span data-stu-id="1cf62-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1cf62-106">语法</span><span class="sxs-lookup"><span data-stu-id="1cf62-106">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1cf62-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1cf62-107">Attributes and Elements</span></span>

<span data-ttu-id="1cf62-108">以下各节描述了元素的属性、子元素和父元素 `Label` 。</span><span class="sxs-lookup"><span data-stu-id="1cf62-108">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1cf62-109">特性</span><span class="sxs-lookup"><span data-stu-id="1cf62-109">Attributes</span></span>

<span data-ttu-id="1cf62-110">无。</span><span class="sxs-lookup"><span data-stu-id="1cf62-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1cf62-111">子元素</span><span class="sxs-lookup"><span data-stu-id="1cf62-111">Child Elements</span></span>

<span data-ttu-id="1cf62-112">无。</span><span class="sxs-lookup"><span data-stu-id="1cf62-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1cf62-113">父元素</span><span class="sxs-lookup"><span data-stu-id="1cf62-113">Parent Elements</span></span>

|<span data-ttu-id="1cf62-114">元素</span><span class="sxs-lookup"><span data-stu-id="1cf62-114">Element</span></span>|<span data-ttu-id="1cf62-115">描述</span><span class="sxs-lookup"><span data-stu-id="1cf62-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1cf62-116">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="1cf62-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="1cf62-117">定义如何显示新的对象组。</span><span class="sxs-lookup"><span data-stu-id="1cf62-117">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1cf62-118">文本值</span><span class="sxs-lookup"><span data-stu-id="1cf62-118">Text Value</span></span>

<span data-ttu-id="1cf62-119">指定每当 Windows PowerShell 遇到新的属性或脚本值时所显示的文本。</span><span class="sxs-lookup"><span data-stu-id="1cf62-119">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="1cf62-120">备注</span><span class="sxs-lookup"><span data-stu-id="1cf62-120">Remarks</span></span>

<span data-ttu-id="1cf62-121">除了此元素指定的文本，Windows PowerShell 还显示启动组的新值，并在组的前面和后面添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="1cf62-121">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="1cf62-122">示例</span><span class="sxs-lookup"><span data-stu-id="1cf62-122">Example</span></span>

<span data-ttu-id="1cf62-123">下面的示例显示了新组的标签。</span><span class="sxs-lookup"><span data-stu-id="1cf62-123">The following example shows the label for a new group.</span></span> <span data-ttu-id="1cf62-124">显示的标签如下所示： `Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="1cf62-124">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="1cf62-125">有关包括此元素的完整格式化文件的示例，请参阅 [ (GroupBy) 的宽视图 ](./wide-view-groupby.md)。</span><span class="sxs-lookup"><span data-stu-id="1cf62-125">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1cf62-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cf62-126">See Also</span></span>

[<span data-ttu-id="1cf62-127">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="1cf62-127">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="1cf62-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="1cf62-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
