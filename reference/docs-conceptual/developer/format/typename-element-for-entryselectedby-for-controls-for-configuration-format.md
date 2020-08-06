---
title: " (格式的控件的 EntrySelectedBy 的 TypeName 元素) |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 994cd368872392abe47b4e9422c661cd8c03e05c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783341"
---
# <a name="typename-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="b04fe-102">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b04fe-102">TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="b04fe-103">指定使用控件的此定义的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="b04fe-103">Specifies a .NET type that uses this definition of the control.</span></span> <span data-ttu-id="b04fe-104">此元素在定义可供格式设置文件中的所有视图使用的公共控件时使用。</span><span class="sxs-lookup"><span data-stu-id="b04fe-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="b04fe-105">配置元素 (格式) 控制配置 (格式的控件) 控件元素，用于控件的配置 (格式) 用于控件的配置 (格式) CustomEntries 元素 (用于配置) 格式的 CustomControl 的的 CustomEntry 元素 (CustomControl 的元素) EntrySelectedBy 的控件 (格式) </span><span class="sxs-lookup"><span data-stu-id="b04fe-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) TypeName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b04fe-106">语法</span><span class="sxs-lookup"><span data-stu-id="b04fe-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a><span data-ttu-id="b04fe-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b04fe-107">Attributes and Elements</span></span>

<span data-ttu-id="b04fe-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="b04fe-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b04fe-109">特性</span><span class="sxs-lookup"><span data-stu-id="b04fe-109">Attributes</span></span>

<span data-ttu-id="b04fe-110">无。</span><span class="sxs-lookup"><span data-stu-id="b04fe-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b04fe-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b04fe-111">Child Elements</span></span>

<span data-ttu-id="b04fe-112">无。</span><span class="sxs-lookup"><span data-stu-id="b04fe-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b04fe-113">父元素</span><span class="sxs-lookup"><span data-stu-id="b04fe-113">Parent Elements</span></span>

|<span data-ttu-id="b04fe-114">元素</span><span class="sxs-lookup"><span data-stu-id="b04fe-114">Element</span></span>|<span data-ttu-id="b04fe-115">描述</span><span class="sxs-lookup"><span data-stu-id="b04fe-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b04fe-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b04fe-116">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="b04fe-117">定义使用此控件定义的 .NET 类型或要使用此定义时必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="b04fe-117">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b04fe-118">文本值</span><span class="sxs-lookup"><span data-stu-id="b04fe-118">Text Value</span></span>

<span data-ttu-id="b04fe-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="b04fe-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b04fe-120">备注</span><span class="sxs-lookup"><span data-stu-id="b04fe-120">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="b04fe-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b04fe-121">See Also</span></span>

[<span data-ttu-id="b04fe-122">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="b04fe-122">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="b04fe-123">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="b04fe-123">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
