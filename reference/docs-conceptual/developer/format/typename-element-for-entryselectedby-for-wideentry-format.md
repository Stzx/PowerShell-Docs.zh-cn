---
title: EntrySelectedBy for WideEntry (Format) 的 TypeName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9af443067467f590df824b28636f57b807a4fc94
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780179"
---
# <a name="typename-element-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="8c291-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8c291-102">TypeName Element for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="8c291-103">为定义指定 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="8c291-103">Specifies a .NET type for the definition.</span></span> <span data-ttu-id="8c291-104">只要显示此对象，就会使用定义。</span><span class="sxs-lookup"><span data-stu-id="8c291-104">The definition is used whenever this object is displayed.</span></span>

<span data-ttu-id="8c291-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) EntrySelectedBy (格式) WideEntry 元素 (WideEntry) 格式</span><span class="sxs-lookup"><span data-stu-id="8c291-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) TypeName Element for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c291-106">语法</span><span class="sxs-lookup"><span data-stu-id="8c291-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c291-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8c291-107">Attributes and Elements</span></span>

<span data-ttu-id="8c291-108">以下各节描述了元素的属性、子元素和父元素 `TypeName` 。</span><span class="sxs-lookup"><span data-stu-id="8c291-108">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c291-109">特性</span><span class="sxs-lookup"><span data-stu-id="8c291-109">Attributes</span></span>

<span data-ttu-id="8c291-110">无。</span><span class="sxs-lookup"><span data-stu-id="8c291-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c291-111">子元素</span><span class="sxs-lookup"><span data-stu-id="8c291-111">Child Elements</span></span>

<span data-ttu-id="8c291-112">无。</span><span class="sxs-lookup"><span data-stu-id="8c291-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8c291-113">父元素</span><span class="sxs-lookup"><span data-stu-id="8c291-113">Parent Elements</span></span>

|<span data-ttu-id="8c291-114">元素</span><span class="sxs-lookup"><span data-stu-id="8c291-114">Element</span></span>|<span data-ttu-id="8c291-115">描述</span><span class="sxs-lookup"><span data-stu-id="8c291-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c291-116">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8c291-116">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="8c291-117">定义使用此宽项的 .NET 类型或此项要使用的条件。</span><span class="sxs-lookup"><span data-stu-id="8c291-117">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="8c291-118">文本值</span><span class="sxs-lookup"><span data-stu-id="8c291-118">Text Value</span></span>

<span data-ttu-id="8c291-119">指定 .NET 类型的完全限定名，如 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="8c291-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c291-120">备注</span><span class="sxs-lookup"><span data-stu-id="8c291-120">Remarks</span></span>

<span data-ttu-id="8c291-121">每个宽条目都必须指定一个或多个 .NET 类型、选择集或必须为要使用的定义提供的选择条件。</span><span class="sxs-lookup"><span data-stu-id="8c291-121">Each wide entry must specify one or more .NET types, a selection set, or the selection condition that must exist for the definition to be used.</span></span>

<span data-ttu-id="8c291-122">有关大视图的其他组件的详细信息，请参阅[创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="8c291-122">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c291-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c291-123">See Also</span></span>

[<span data-ttu-id="8c291-124">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="8c291-124">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="8c291-125">EntrySelectedBy Element for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="8c291-125">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="8c291-126">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="8c291-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
