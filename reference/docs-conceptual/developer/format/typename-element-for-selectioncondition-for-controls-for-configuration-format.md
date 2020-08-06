---
title: " (格式的控件的 SelectionCondition 的 TypeName 元素) |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 2db856d1b84dded315204d8c8574ae86acb63515
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780060"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-configuration-format"></a><span data-ttu-id="74bfb-102">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="74bfb-102">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

<span data-ttu-id="74bfb-103">指定触发条件的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="74bfb-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="74bfb-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="74bfb-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="74bfb-105">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素对于配置 (格式) 用于控件的 CustomControl 的控件 (CustomEntries 元素) CustomEntry 元素对于 CustomControl for control for control (format) EntrySelectedBy 元素 For CustomEntry For configuration (格式的 For EntrySelectedBy for CustomEntry 的 SelectionCondition 元素 ()  (格式的控件) 的 TypeName 元素) </span><span class="sxs-lookup"><span data-stu-id="74bfb-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format) TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="74bfb-106">语法</span><span class="sxs-lookup"><span data-stu-id="74bfb-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="74bfb-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="74bfb-107">Attributes and Elements</span></span>

<span data-ttu-id="74bfb-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="74bfb-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` Element.</span></span>

### <a name="attributes"></a><span data-ttu-id="74bfb-109">特性</span><span class="sxs-lookup"><span data-stu-id="74bfb-109">Attributes</span></span>

<span data-ttu-id="74bfb-110">无。</span><span class="sxs-lookup"><span data-stu-id="74bfb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="74bfb-111">子元素</span><span class="sxs-lookup"><span data-stu-id="74bfb-111">Child Elements</span></span>

<span data-ttu-id="74bfb-112">无。</span><span class="sxs-lookup"><span data-stu-id="74bfb-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="74bfb-113">父元素</span><span class="sxs-lookup"><span data-stu-id="74bfb-113">Parent Elements</span></span>

|<span data-ttu-id="74bfb-114">元素</span><span class="sxs-lookup"><span data-stu-id="74bfb-114">Element</span></span>|<span data-ttu-id="74bfb-115">描述</span><span class="sxs-lookup"><span data-stu-id="74bfb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74bfb-116">用于 CustomEntry) 配置 (格式的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="74bfb-116">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)|<span data-ttu-id="74bfb-117">定义要使用的控件定义必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="74bfb-117">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="74bfb-118">文本值</span><span class="sxs-lookup"><span data-stu-id="74bfb-118">Text Value</span></span>

<span data-ttu-id="74bfb-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="74bfb-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="74bfb-120">备注</span><span class="sxs-lookup"><span data-stu-id="74bfb-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="74bfb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74bfb-121">See Also</span></span>

[<span data-ttu-id="74bfb-122">用于 CustomEntry) 配置 (格式的 EntrySelectedBy 的 SelectionCondition 元素</span><span class="sxs-lookup"><span data-stu-id="74bfb-122">SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

[<span data-ttu-id="74bfb-123">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="74bfb-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
