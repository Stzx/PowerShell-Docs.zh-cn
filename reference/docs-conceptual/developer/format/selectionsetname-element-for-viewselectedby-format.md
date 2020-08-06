---
title: ViewSelectedBy (Format) 的 SelectionSetName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: f6410b463bcb00d2758849c2f7e13cd839277e50
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772597"
---
# <a name="selectionsetname-element-for-viewselectedby-format"></a><span data-ttu-id="8cae5-102">SelectionSetName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="8cae5-102">SelectionSetName Element for ViewSelectedBy (Format)</span></span>

<span data-ttu-id="8cae5-103">指定视图显示的一组 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="8cae5-103">Specifies a set of .NET objects that are displayed by the view.</span></span>

<span data-ttu-id="8cae5-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ViewSelectedBy 元素 (格式) SelectionSetName 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="8cae5-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ViewSelectedBy Element (Format) SelectionSetName Element for ViewSelectedBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8cae5-105">语法</span><span class="sxs-lookup"><span data-stu-id="8cae5-105">Syntax</span></span>

```xml
<SelectionSetName>Name of selection set<SelectionSetName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8cae5-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8cae5-106">Attributes and Elements</span></span>

<span data-ttu-id="8cae5-107">以下各节描述了元素的属性、子元素和父元素 `SelectionSetName` 。</span><span class="sxs-lookup"><span data-stu-id="8cae5-107">The following sections describe the attributes, child elements, and the parent element of the `SelectionSetName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8cae5-108">特性</span><span class="sxs-lookup"><span data-stu-id="8cae5-108">Attributes</span></span>

<span data-ttu-id="8cae5-109">无。</span><span class="sxs-lookup"><span data-stu-id="8cae5-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8cae5-110">子元素</span><span class="sxs-lookup"><span data-stu-id="8cae5-110">Child Elements</span></span>

<span data-ttu-id="8cae5-111">无。</span><span class="sxs-lookup"><span data-stu-id="8cae5-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8cae5-112">父元素</span><span class="sxs-lookup"><span data-stu-id="8cae5-112">Parent Elements</span></span>

|<span data-ttu-id="8cae5-113">元素</span><span class="sxs-lookup"><span data-stu-id="8cae5-113">Element</span></span>|<span data-ttu-id="8cae5-114">描述</span><span class="sxs-lookup"><span data-stu-id="8cae5-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8cae5-115">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8cae5-115">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="8cae5-116">定义视图显示的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="8cae5-116">Defines the .NET objects that are displayed by the view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8cae5-117">文本值</span><span class="sxs-lookup"><span data-stu-id="8cae5-117">Text Value</span></span>

<span data-ttu-id="8cae5-118">为选择集指定由元素定义的选择集的名称 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="8cae5-118">Specify the name of the selection set that is defined by the `Name` element for the selection set.</span></span>

## <a name="remarks"></a><span data-ttu-id="8cae5-119">备注</span><span class="sxs-lookup"><span data-stu-id="8cae5-119">Remarks</span></span>

<span data-ttu-id="8cae5-120">如果你有一组要通过使用单个名称引用的相关对象（例如通过继承相关的一组对象），则可以使用选择集。</span><span class="sxs-lookup"><span data-stu-id="8cae5-120">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="8cae5-121">有关定义和引用选项集的详细信息，请参阅[定义对象集](./defining-selection-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="8cae5-121">For more information about defining and referencing selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="8cae5-122">示例</span><span class="sxs-lookup"><span data-stu-id="8cae5-122">Example</span></span>

<span data-ttu-id="8cae5-123">下面的示例演示如何为列表视图指定选择集。</span><span class="sxs-lookup"><span data-stu-id="8cae5-123">The following example shows how to specify a selection set for a list view.</span></span> <span data-ttu-id="8cae5-124">表、宽视图和自定义视图使用相同的架构。</span><span class="sxs-lookup"><span data-stu-id="8cae5-124">The same schema is used for table, wide, and custom views.</span></span>

```xml
<View>
  <Name>Name of View</Name>
  <ViewSelectedBy>
    <SelectionSetName>NameofSelectionSet</SelectionSetName>>
  </ViewSelectedBy>
  <ListControl>...</ListControl>
</View>
```

## <a name="see-also"></a><span data-ttu-id="8cae5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cae5-125">See Also</span></span>

[<span data-ttu-id="8cae5-126">定义选项集</span><span class="sxs-lookup"><span data-stu-id="8cae5-126">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="8cae5-127">ViewSelectedBy Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8cae5-127">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="8cae5-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="8cae5-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
