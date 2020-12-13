---
ms.date: 09/13/2016
ms.topic: reference
title: SelectionSetName Element for ViewSelectedBy (Format)
description: SelectionSetName Element for ViewSelectedBy (Format)
ms.openlocfilehash: a1a1816761715a138bcb3c2bd4cb9dbbb2f9cb92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654908"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="19579-103">SelectionSetName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="19579-103">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="19579-104">指定视图显示的一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="19579-104">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="19579-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ViewSelectedBy 元素 (格式) SelectionSetName 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="19579-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="19579-106">语法</span><span class="sxs-lookup"><span data-stu-id="19579-106">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="19579-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="19579-107">Attributes and Elements</span></span>

<span data-ttu-id="19579-108">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="19579-108">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="19579-109">特性</span><span class="sxs-lookup"><span data-stu-id="19579-109">Attributes</span></span>

<span data-ttu-id="19579-110">无。</span><span class="sxs-lookup"><span data-stu-id="19579-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="19579-111">子元素</span><span class="sxs-lookup"><span data-stu-id="19579-111">Child Elements</span></span>

<span data-ttu-id="19579-112">无。</span><span class="sxs-lookup"><span data-stu-id="19579-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="19579-113">父元素</span><span class="sxs-lookup"><span data-stu-id="19579-113">Parent Elements</span></span>

|<span data-ttu-id="19579-114">元素</span><span class="sxs-lookup"><span data-stu-id="19579-114">Element</span></span>|<span data-ttu-id="19579-115">描述</span><span class="sxs-lookup"><span data-stu-id="19579-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="19579-116">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="19579-116">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="19579-117">定义视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="19579-117">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="19579-118">文本值</span><span class="sxs-lookup"><span data-stu-id="19579-118">Text Value</span></span>

<span data-ttu-id="19579-119">为选择集指定由元素定义的选择集的名称 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="19579-119">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="19579-120">备注</span><span class="sxs-lookup"><span data-stu-id="19579-120">Remarks</span></span>

<span data-ttu-id="19579-121">如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。</span><span class="sxs-lookup"><span data-stu-id="19579-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="19579-122">有关定义和引用选项集的详细信息，请参阅 [定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="19579-122">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="19579-123">示例</span><span class="sxs-lookup"><span data-stu-id="19579-123">Example</span></span>

<span data-ttu-id="19579-124">下面的示例演示如何为列表视图指定选择集。</span><span class="sxs-lookup"><span data-stu-id="19579-124">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="19579-125">表、宽视图和自定义视图使用相同的架构。</span><span class="sxs-lookup"><span data-stu-id="19579-125">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="19579-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19579-126">See Also</span></span>

[<span data-ttu-id="19579-127">定义选项集</span><span class="sxs-lookup"><span data-stu-id="19579-127">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="19579-128">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="19579-128">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="19579-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="19579-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
