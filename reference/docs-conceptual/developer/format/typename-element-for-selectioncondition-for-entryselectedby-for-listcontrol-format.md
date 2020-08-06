---
title: ListControl (Format) 的 SelectionCondition for EntrySelectedBy 的 TypeName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: bc58d630e65b316f9223bf3c529f928358e38ebc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787368"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="2bdf1-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2bdf1-102">TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="2bdf1-103">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="2bdf1-104">如果存在此类型，则使用列表项。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-104">When this type is present, the list entry is used.</span></span>

<span data-ttu-id="2bdf1-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素用于 ListControl (格式) ListEntry for ListEntries 的 ListControl 元素 (EntrySelectedBy ListEntry 的 ListControl 元素) SelectionCondition 的 EntrySelectedBy 的 ListControl (格式) SelectionCondition (</span><span class="sxs-lookup"><span data-stu-id="2bdf1-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListEntries for ListControl (Format) EntrySelectedBy Element for ListEntry for ListControl (Format) SelectionCondition Element for EntrySelectedBy for ListControl (Format) TypeName Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2bdf1-106">语法</span><span class="sxs-lookup"><span data-stu-id="2bdf1-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2bdf1-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2bdf1-107">Attributes and Elements</span></span>

<span data-ttu-id="2bdf1-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2bdf1-109">特性</span><span class="sxs-lookup"><span data-stu-id="2bdf1-109">Attributes</span></span>

<span data-ttu-id="2bdf1-110">无。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2bdf1-111">子元素</span><span class="sxs-lookup"><span data-stu-id="2bdf1-111">Child Elements</span></span>

<span data-ttu-id="2bdf1-112">无。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2bdf1-113">父元素</span><span class="sxs-lookup"><span data-stu-id="2bdf1-113">Parent Elements</span></span>

|<span data-ttu-id="2bdf1-114">元素</span><span class="sxs-lookup"><span data-stu-id="2bdf1-114">Element</span></span>|<span data-ttu-id="2bdf1-115">描述</span><span class="sxs-lookup"><span data-stu-id="2bdf1-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2bdf1-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2bdf1-116">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="2bdf1-117">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2bdf1-118">文本值</span><span class="sxs-lookup"><span data-stu-id="2bdf1-118">Text Value</span></span>

<span data-ttu-id="2bdf1-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2bdf1-120">备注</span><span class="sxs-lookup"><span data-stu-id="2bdf1-120">Remarks</span></span>

<span data-ttu-id="2bdf1-121">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-121">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span> <span data-ttu-id="2bdf1-122">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="2bdf1-123">有关列表视图的其他组件的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="2bdf1-123">For more information about other the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2bdf1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bdf1-124">See Also</span></span>

[<span data-ttu-id="2bdf1-125">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="2bdf1-125">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="2bdf1-126">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="2bdf1-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="2bdf1-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="2bdf1-127">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="2bdf1-128">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="2bdf1-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
