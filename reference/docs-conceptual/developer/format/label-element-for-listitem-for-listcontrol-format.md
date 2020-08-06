---
title: ListControl (Format) 的输入标记元素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ad80cc0478e7567b12d264ab661d843248ba48e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783630"
---
# <a name="label-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="13898-102">Label Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="13898-102">Label Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="13898-103">指定在行的属性或脚本值左侧显示的标签。</span><span class="sxs-lookup"><span data-stu-id="13898-103">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>

<span data-ttu-id="13898-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry) 格式 (ListControl ListItems 的 ListEntry 元素) ListControl 的 ListItems 元素 (ListControl) 格式 (ListControl) 格式 (</span><span class="sxs-lookup"><span data-stu-id="13898-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems for ListEntry for ListControl Element (Format) ListItem Element for ListItems for ListControl (Format) Label Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="13898-105">语法</span><span class="sxs-lookup"><span data-stu-id="13898-105">Syntax</span></span>

```xml
<Label>Label for displayed value</Label>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="13898-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13898-106">Attributes and Elements</span></span>

<span data-ttu-id="13898-107">以下各节描述了元素的属性、子元素和父元素 `Label` 。</span><span class="sxs-lookup"><span data-stu-id="13898-107">The following sections describe the attributes, child elements, and the parent element of the `Label` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="13898-108">特性</span><span class="sxs-lookup"><span data-stu-id="13898-108">Attributes</span></span>

<span data-ttu-id="13898-109">无。</span><span class="sxs-lookup"><span data-stu-id="13898-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="13898-110">子元素</span><span class="sxs-lookup"><span data-stu-id="13898-110">Child Elements</span></span>

<span data-ttu-id="13898-111">无。</span><span class="sxs-lookup"><span data-stu-id="13898-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="13898-112">父元素</span><span class="sxs-lookup"><span data-stu-id="13898-112">Parent Elements</span></span>

|<span data-ttu-id="13898-113">元素</span><span class="sxs-lookup"><span data-stu-id="13898-113">Element</span></span>|<span data-ttu-id="13898-114">说明</span><span class="sxs-lookup"><span data-stu-id="13898-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13898-115">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="13898-115">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="13898-116">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="13898-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="13898-117">文本值</span><span class="sxs-lookup"><span data-stu-id="13898-117">Text Value</span></span>

<span data-ttu-id="13898-118">指定要在属性或脚本值左侧显示的标签。</span><span class="sxs-lookup"><span data-stu-id="13898-118">Specify the label to be display to the left of the property or script value.</span></span>

## <a name="remarks"></a><span data-ttu-id="13898-119">备注</span><span class="sxs-lookup"><span data-stu-id="13898-119">Remarks</span></span>

<span data-ttu-id="13898-120">如果未指定标签，则显示属性或脚本的名称。</span><span class="sxs-lookup"><span data-stu-id="13898-120">If a label is not specified, the name of the property or the script is displayed.</span></span> <span data-ttu-id="13898-121">有关在列表视图中使用标签的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="13898-121">For more information about using labels in a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="13898-122">示例</span><span class="sxs-lookup"><span data-stu-id="13898-122">Example</span></span>

<span data-ttu-id="13898-123">下面的示例演示如何向行中添加标签。</span><span class="sxs-lookup"><span data-stu-id="13898-123">The following example shows how to add a label to a row.</span></span>

```xml
<ListItem>
  <Label>Property1: </Label>
  <PropertyName>DotNetProperty1</PropertyName>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="13898-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13898-124">See Also</span></span>

[<span data-ttu-id="13898-125">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="13898-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="13898-126"> (格式的) 元素元素</span><span class="sxs-lookup"><span data-stu-id="13898-126">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="13898-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="13898-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
