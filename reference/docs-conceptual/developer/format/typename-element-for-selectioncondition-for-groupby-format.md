---
title: 对于 GroupBy (Format) ，为 SelectionCondition 的 TypeName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ea1e0cb50c3a749f6c26d13fff4b001240ce6b95
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772546"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="cbacd-102">TypeName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cbacd-102">TypeName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="cbacd-103">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="cbacd-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="cbacd-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="cbacd-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="cbacd-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，用于 CustomEntries 的元素，适用于 CustomControl for groupby (格式) 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="cbacd-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cbacd-106">语法</span><span class="sxs-lookup"><span data-stu-id="cbacd-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="cbacd-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cbacd-107">Attributes and Elements</span></span>

<span data-ttu-id="cbacd-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="cbacd-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cbacd-109">特性</span><span class="sxs-lookup"><span data-stu-id="cbacd-109">Attributes</span></span>

<span data-ttu-id="cbacd-110">无。</span><span class="sxs-lookup"><span data-stu-id="cbacd-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cbacd-111">子元素</span><span class="sxs-lookup"><span data-stu-id="cbacd-111">Child Elements</span></span>

<span data-ttu-id="cbacd-112">无。</span><span class="sxs-lookup"><span data-stu-id="cbacd-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cbacd-113">父元素</span><span class="sxs-lookup"><span data-stu-id="cbacd-113">Parent Elements</span></span>

|<span data-ttu-id="cbacd-114">元素</span><span class="sxs-lookup"><span data-stu-id="cbacd-114">Element</span></span>|<span data-ttu-id="cbacd-115">描述</span><span class="sxs-lookup"><span data-stu-id="cbacd-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cbacd-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cbacd-116">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="cbacd-117">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="cbacd-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cbacd-118">文本值</span><span class="sxs-lookup"><span data-stu-id="cbacd-118">Text Value</span></span>

<span data-ttu-id="cbacd-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="cbacd-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cbacd-120">备注</span><span class="sxs-lookup"><span data-stu-id="cbacd-120">Remarks</span></span>

<span data-ttu-id="cbacd-121">如果指定此元素，则不能指定 `SelectionSetName` 元素。</span><span class="sxs-lookup"><span data-stu-id="cbacd-121">When this element is specified, you cannot specify the `SelectionSetName` element.</span></span> <span data-ttu-id="cbacd-122">有关定义选择条件的详细信息，请参阅[定义用于显示数据的条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="cbacd-122">For more information about defining selection conditions, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cbacd-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbacd-123">See Also</span></span>

[<span data-ttu-id="cbacd-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="cbacd-124">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="cbacd-125">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="cbacd-125">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
