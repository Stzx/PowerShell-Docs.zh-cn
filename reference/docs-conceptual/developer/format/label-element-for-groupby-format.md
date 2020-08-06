---
title: GroupBy (格式) 的标签元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 07b4d037472a9dd2329e94576ec10f5b82f46b34
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785772"
---
# <a name="label-element-for-groupby-format"></a><span data-ttu-id="fda5c-102">Label Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="fda5c-102">Label Element for GroupBy (Format)</span></span>

<span data-ttu-id="fda5c-103">指定在遇到新组时显示的标签。</span><span class="sxs-lookup"><span data-stu-id="fda5c-103">Specifies a label that is displayed when a new group is encountered.</span></span>

<span data-ttu-id="fda5c-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (Format) GroupBy 元素 () 格式 (标签元素) </span><span class="sxs-lookup"><span data-stu-id="fda5c-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) Label Element for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fda5c-105">语法</span><span class="sxs-lookup"><span data-stu-id="fda5c-105">Syntax</span></span>

```xml
<Label>DisplayedLabel</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fda5c-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fda5c-106">Attributes and Elements</span></span>

<span data-ttu-id="fda5c-107">以下各节描述了元素的属性、子元素和父元素 `Label` 。</span><span class="sxs-lookup"><span data-stu-id="fda5c-107">The following sections describe the attributes, child elements, and parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fda5c-108">特性</span><span class="sxs-lookup"><span data-stu-id="fda5c-108">Attributes</span></span>

<span data-ttu-id="fda5c-109">无。</span><span class="sxs-lookup"><span data-stu-id="fda5c-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fda5c-110">子元素</span><span class="sxs-lookup"><span data-stu-id="fda5c-110">Child Elements</span></span>

<span data-ttu-id="fda5c-111">无。</span><span class="sxs-lookup"><span data-stu-id="fda5c-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fda5c-112">父元素</span><span class="sxs-lookup"><span data-stu-id="fda5c-112">Parent Elements</span></span>

|<span data-ttu-id="fda5c-113">元素</span><span class="sxs-lookup"><span data-stu-id="fda5c-113">Element</span></span>|<span data-ttu-id="fda5c-114">描述</span><span class="sxs-lookup"><span data-stu-id="fda5c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fda5c-115">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="fda5c-115">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="fda5c-116">定义如何显示新的对象组。</span><span class="sxs-lookup"><span data-stu-id="fda5c-116">Defines how a new group of objects is displayed.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fda5c-117">文本值</span><span class="sxs-lookup"><span data-stu-id="fda5c-117">Text Value</span></span>

<span data-ttu-id="fda5c-118">指定每当 Windows PowerShell 遇到新的属性或脚本值时所显示的文本。</span><span class="sxs-lookup"><span data-stu-id="fda5c-118">Specify the text that is displayed whenever Windows PowerShell encounters a new property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="fda5c-119">备注</span><span class="sxs-lookup"><span data-stu-id="fda5c-119">Remarks</span></span>

<span data-ttu-id="fda5c-120">除了此元素指定的文本，Windows PowerShell 还显示启动组的新值，并在组的前面和后面添加一个空白行。</span><span class="sxs-lookup"><span data-stu-id="fda5c-120">In addition to the text specified by this element, Windows PowerShell displays the new value that starts the group, and adds a blank line before and after the group.</span></span>

## <a name="example"></a><span data-ttu-id="fda5c-121">示例</span><span class="sxs-lookup"><span data-stu-id="fda5c-121">Example</span></span>

<span data-ttu-id="fda5c-122">下面的示例显示了新组的标签。</span><span class="sxs-lookup"><span data-stu-id="fda5c-122">The following example shows the label for a new group.</span></span> <span data-ttu-id="fda5c-123">显示的标签如下所示：`Service Type: NewValueofProperty`</span><span class="sxs-lookup"><span data-stu-id="fda5c-123">The displayed label would look similar to this: `Service Type: NewValueofProperty`</span></span>

```xml
<GroupBy>
  <Label>Service Type</Label>
  <PropertyName>ServiceType</PropertyName>
</GroupBy>

```

<span data-ttu-id="fda5c-124">有关包括此元素的完整格式化文件的示例，请参阅[ (GroupBy) 的宽视图](./wide-view-groupby.md)。</span><span class="sxs-lookup"><span data-stu-id="fda5c-124">For an example of a complete formatting file that includes this element, see [Wide View (GroupBy)](./wide-view-groupby.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fda5c-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fda5c-125">See Also</span></span>

[<span data-ttu-id="fda5c-126">GroupBy Element for View (Format)</span><span class="sxs-lookup"><span data-stu-id="fda5c-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="fda5c-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="fda5c-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
