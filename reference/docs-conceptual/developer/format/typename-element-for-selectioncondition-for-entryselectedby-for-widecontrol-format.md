---
title: WideControl (Format) 的 SelectionCondition for EntrySelectedBy 的 TypeName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 5021f665b994581f9ff982e13af922d7940ebf2b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783307"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="fcca7-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="fcca7-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="fcca7-103">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="fcca7-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="fcca7-104">如果存在此类型，则使用定义。</span><span class="sxs-lookup"><span data-stu-id="fcca7-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="fcca7-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy 的 WideEntry 元素 (SelectionCondition) 格式 (EntrySelectedBy 的 WideEntry 元素) 格式 (</span><span class="sxs-lookup"><span data-stu-id="fcca7-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="fcca7-106">语法</span><span class="sxs-lookup"><span data-stu-id="fcca7-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fcca7-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fcca7-107">Attributes and Elements</span></span>

<span data-ttu-id="fcca7-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="fcca7-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="fcca7-109">特性</span><span class="sxs-lookup"><span data-stu-id="fcca7-109">Attributes</span></span>

<span data-ttu-id="fcca7-110">无。</span><span class="sxs-lookup"><span data-stu-id="fcca7-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="fcca7-111">子元素</span><span class="sxs-lookup"><span data-stu-id="fcca7-111">Child Elements</span></span>

<span data-ttu-id="fcca7-112">无。</span><span class="sxs-lookup"><span data-stu-id="fcca7-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fcca7-113">父元素</span><span class="sxs-lookup"><span data-stu-id="fcca7-113">Parent Elements</span></span>

|<span data-ttu-id="fcca7-114">元素</span><span class="sxs-lookup"><span data-stu-id="fcca7-114">Element</span></span>|<span data-ttu-id="fcca7-115">说明</span><span class="sxs-lookup"><span data-stu-id="fcca7-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="fcca7-116">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="fcca7-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="fcca7-117">定义要使用此宽项时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="fcca7-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="fcca7-118">文本值</span><span class="sxs-lookup"><span data-stu-id="fcca7-118">Text Value</span></span>

<span data-ttu-id="fcca7-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="fcca7-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcca7-120">备注</span><span class="sxs-lookup"><span data-stu-id="fcca7-120">Remarks</span></span>

<span data-ttu-id="fcca7-121">选择条件可以指定 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="fcca7-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="fcca7-122">有关如何使用选择条件的详细信息，请参阅为[数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="fcca7-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="fcca7-123">有关大视图的其他组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="fcca7-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fcca7-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcca7-124">See Also</span></span>

[<span data-ttu-id="fcca7-125">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="fcca7-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="fcca7-126">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="fcca7-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="fcca7-127">WideEntry (格式的 EntrySelectedBy 的 SelectionCondition 元素) </span><span class="sxs-lookup"><span data-stu-id="fcca7-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="fcca7-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="fcca7-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="fcca7-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="fcca7-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
