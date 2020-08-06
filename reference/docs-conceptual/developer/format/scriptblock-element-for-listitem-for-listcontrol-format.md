---
title: ListControl 的 ScriptBlock 元素) 的 (格式 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 249d3e36b4246b7baa410815122f8e30340f1862
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785449"
---
# <a name="scriptblock-element-for-listitem-for-listcontrol-format"></a><span data-ttu-id="e87c1-102">ScriptBlock Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e87c1-102">ScriptBlock Element for ListItem for ListControl (Format)</span></span>

<span data-ttu-id="e87c1-103">指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="e87c1-103">Specifies the script whose value is displayed in the row.</span></span>

<span data-ttu-id="e87c1-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry 的 ListControl) 格式 (ListEntries for ListControl 的 ListItems 元素) ListEntry (的 ScriptBlock 元素) ListControl (格式) 的 ScriptBlock 元素 (</span><span class="sxs-lookup"><span data-stu-id="e87c1-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) ListItems Element for ListEntry for ListControl (Format) ListItem Element for ListItems for ListControl (Format) ScriptBlock Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e87c1-105">语法</span><span class="sxs-lookup"><span data-stu-id="e87c1-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e87c1-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e87c1-106">Attributes and Elements</span></span>

<span data-ttu-id="e87c1-107">以下各节描述了元素的属性、子元素和父元素 `ScriptBlock` 。</span><span class="sxs-lookup"><span data-stu-id="e87c1-107">The following sections describe the attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e87c1-108">特性</span><span class="sxs-lookup"><span data-stu-id="e87c1-108">Attributes</span></span>

<span data-ttu-id="e87c1-109">无。</span><span class="sxs-lookup"><span data-stu-id="e87c1-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e87c1-110">子元素</span><span class="sxs-lookup"><span data-stu-id="e87c1-110">Child Elements</span></span>

<span data-ttu-id="e87c1-111">无。</span><span class="sxs-lookup"><span data-stu-id="e87c1-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e87c1-112">父元素</span><span class="sxs-lookup"><span data-stu-id="e87c1-112">Parent Elements</span></span>

|<span data-ttu-id="e87c1-113">元素</span><span class="sxs-lookup"><span data-stu-id="e87c1-113">Element</span></span>|<span data-ttu-id="e87c1-114">说明</span><span class="sxs-lookup"><span data-stu-id="e87c1-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e87c1-115"> (格式的) 元素元素</span><span class="sxs-lookup"><span data-stu-id="e87c1-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="e87c1-116">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="e87c1-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e87c1-117">文本值</span><span class="sxs-lookup"><span data-stu-id="e87c1-117">Text Value</span></span>

<span data-ttu-id="e87c1-118">指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="e87c1-118">Specify the script whose value is displayed in the row.</span></span>

## <a name="remarks"></a><span data-ttu-id="e87c1-119">备注</span><span class="sxs-lookup"><span data-stu-id="e87c1-119">Remarks</span></span>

<span data-ttu-id="e87c1-120">如果指定此元素，则不能指定[PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md)元素。</span><span class="sxs-lookup"><span data-stu-id="e87c1-120">When this element is specified, you cannot specify the [PropertyName](./propertyname-element-for-listitem-for-listcontrol-format.md) element.</span></span>

<span data-ttu-id="e87c1-121">有关在列表视图中指定脚本的详细信息，请参阅[列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="e87c1-121">For more information about specifying scripts in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="e87c1-122">示例</span><span class="sxs-lookup"><span data-stu-id="e87c1-122">Example</span></span>

<span data-ttu-id="e87c1-123">下面的示例演示如何指定显示其值的属性。</span><span class="sxs-lookup"><span data-stu-id="e87c1-123">The following example shows how to specify the property whose value is displayed.</span></span>

```xml
<ListItem>
  <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
</ListItem>

```

## <a name="see-also"></a><span data-ttu-id="e87c1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e87c1-124">See Also</span></span>

[<span data-ttu-id="e87c1-125">PropertyName Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e87c1-125">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="e87c1-126">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="e87c1-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="e87c1-127">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e87c1-127">ListItem Element for ListItems for ListControl (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="e87c1-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="e87c1-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
