---
ms.date: 09/13/2016
ms.topic: reference
title: TypeName Element for SelectionCondition for Controls for Configuration (Format)
description: TypeName Element for SelectionCondition for Controls for Configuration (Format)
ms.openlocfilehash: fddb8ddbac7c9292a05cadfa31f98db6439a557d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659669"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="89688-103">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="89688-103">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="89688-104">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="89688-104">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="89688-105">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="89688-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="89688-106">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 的控件 (CustomEntries 元素) CustomEntry 元素对于 CustomControl for control for control (format) EntrySelectedBy 元素 For CustomEntry For configuration (格式的 For EntrySelectedBy for CustomEntry 的 SelectionCondition 元素 ()  (格式的控件) 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="89688-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="89688-107">语法</span><span class="sxs-lookup"><span data-stu-id="89688-107">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="89688-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="89688-108">Attributes and Elements</span></span>

<span data-ttu-id="89688-109">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="89688-109">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="89688-110">特性</span><span class="sxs-lookup"><span data-stu-id="89688-110">Attributes</span></span>

<span data-ttu-id="89688-111">无。</span><span class="sxs-lookup"><span data-stu-id="89688-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="89688-112">子元素</span><span class="sxs-lookup"><span data-stu-id="89688-112">Child Elements</span></span>

<span data-ttu-id="89688-113">无。</span><span class="sxs-lookup"><span data-stu-id="89688-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="89688-114">父元素</span><span class="sxs-lookup"><span data-stu-id="89688-114">Parent Elements</span></span>

|<span data-ttu-id="89688-115">元素</span><span class="sxs-lookup"><span data-stu-id="89688-115">Element</span></span>|<span data-ttu-id="89688-116">描述</span><span class="sxs-lookup"><span data-stu-id="89688-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="89688-117">用于 CustomEntry) 配置 (格式的 EntrySelectedBy 的 SelectionCondition 元素 </span><span class="sxs-lookup"><span data-stu-id="89688-117">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="89688-118">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="89688-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="89688-119">文本值</span><span class="sxs-lookup"><span data-stu-id="89688-119">Text Value</span></span>

<span data-ttu-id="89688-120">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="89688-120">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="89688-121">备注</span><span class="sxs-lookup"><span data-stu-id="89688-121">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="89688-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89688-122">See Also</span></span>

[<span data-ttu-id="89688-123">用于 CustomEntry) 配置 (格式的 EntrySelectedBy 的 SelectionCondition 元素 </span><span class="sxs-lookup"><span data-stu-id="89688-123">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="89688-124">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="89688-124">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
