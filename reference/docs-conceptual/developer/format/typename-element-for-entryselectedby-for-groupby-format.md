---
title: 对于 GroupBy (Format) ，为 EntrySelectedBy 的 TypeName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e62762cf142bd2d20b21ad8f4249285bd3679280
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780257"
---
# <a name="typename-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="d82a6-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d82a6-102">TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="d82a6-103">指定使用自定义控件的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="d82a6-103">Specifies a .NET type that uses this definition of the custom control.</span></span> <span data-ttu-id="d82a6-104">此元素在定义如何显示新的对象组时使用。</span><span class="sxs-lookup"><span data-stu-id="d82a6-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="d82a6-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) GroupBy 元素，适用于 CustomControl for groupby (格式) CustomControl 元素 for CustomEntries 元素 for for groupby (format) CustomEntry 元素 for CustomControl for groupby (format) EntrySelectedBy 元素 for CustomEntry for groupby (format) </span><span class="sxs-lookup"><span data-stu-id="d82a6-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) TypeName Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d82a6-106">语法</span><span class="sxs-lookup"><span data-stu-id="d82a6-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d82a6-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d82a6-107">Attributes and Elements</span></span>

<span data-ttu-id="d82a6-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="d82a6-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d82a6-109">特性</span><span class="sxs-lookup"><span data-stu-id="d82a6-109">Attributes</span></span>

<span data-ttu-id="d82a6-110">无。</span><span class="sxs-lookup"><span data-stu-id="d82a6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d82a6-111">子元素</span><span class="sxs-lookup"><span data-stu-id="d82a6-111">Child Elements</span></span>

<span data-ttu-id="d82a6-112">无。</span><span class="sxs-lookup"><span data-stu-id="d82a6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d82a6-113">父元素</span><span class="sxs-lookup"><span data-stu-id="d82a6-113">Parent Elements</span></span>

|<span data-ttu-id="d82a6-114">元素</span><span class="sxs-lookup"><span data-stu-id="d82a6-114">Element</span></span>|<span data-ttu-id="d82a6-115">描述</span><span class="sxs-lookup"><span data-stu-id="d82a6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d82a6-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d82a6-116">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="d82a6-117">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="d82a6-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="d82a6-118">文本值</span><span class="sxs-lookup"><span data-stu-id="d82a6-118">Text Value</span></span>

<span data-ttu-id="d82a6-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="d82a6-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d82a6-120">备注</span><span class="sxs-lookup"><span data-stu-id="d82a6-120">Remarks</span></span>

<span data-ttu-id="d82a6-121">每个控件定义都必须定义至少一个类型名称、选择集或选择条件。</span><span class="sxs-lookup"><span data-stu-id="d82a6-121">Each control definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="d82a6-122">有关自定义控件视图组件的详细信息，请参阅[创建自定义控件](./creating-custom-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="d82a6-122">For more information about the components of a custom control view, see [Creating Custom Controls](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d82a6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d82a6-123">See Also</span></span>

[<span data-ttu-id="d82a6-124">创建自定义控件</span><span class="sxs-lookup"><span data-stu-id="d82a6-124">Creating Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="d82a6-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="d82a6-125">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="d82a6-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d82a6-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
