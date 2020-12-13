---
ms.date: 09/13/2016
ms.topic: reference
title: DefaultSettings Element (Format)
description: DefaultSettings Element (Format)
ms.openlocfilehash: 1c2055b38a416fe2d75fa20c6c87e92d9eed4285
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666716"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="38ba4-103">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-103">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="38ba4-104">定义适用于格式设置文件的所有视图的常见设置。</span><span class="sxs-lookup"><span data-stu-id="38ba4-104">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="38ba4-105">常见的设置包括显示错误、在表中环绕文本、定义集合的展开方式等。</span><span class="sxs-lookup"><span data-stu-id="38ba4-105">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="38ba4-106">配置元素 (格式) DefaultSettings 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="38ba4-106">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="38ba4-107">语法</span><span class="sxs-lookup"><span data-stu-id="38ba4-107">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="38ba4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="38ba4-108">Attributes and Elements</span></span>

<span data-ttu-id="38ba4-109">以下各节描述了元素的属性、子元素和父元素 `DefaultSettings` 。</span><span class="sxs-lookup"><span data-stu-id="38ba4-109">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="38ba4-110">特性</span><span class="sxs-lookup"><span data-stu-id="38ba4-110">Attributes</span></span>

<span data-ttu-id="38ba4-111">无。</span><span class="sxs-lookup"><span data-stu-id="38ba4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="38ba4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="38ba4-112">Child Elements</span></span>

|<span data-ttu-id="38ba4-113">元素</span><span class="sxs-lookup"><span data-stu-id="38ba4-113">Element</span></span>|<span data-ttu-id="38ba4-114">描述</span><span class="sxs-lookup"><span data-stu-id="38ba4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="38ba4-115">DisplayError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-115">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="38ba4-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="38ba4-116">Optional element.</span></span><br /><br /> <span data-ttu-id="38ba4-117">指定在显示一段数据的过程中出现错误时，显示字符串 #ERR。</span><span class="sxs-lookup"><span data-stu-id="38ba4-117">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="38ba4-118">EnumerableExpansions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-118">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="38ba4-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="38ba4-119">Optional element.</span></span><br /><br /> <span data-ttu-id="38ba4-120">定义 .NET 对象显示在视图中时的不同显示方式。</span><span class="sxs-lookup"><span data-stu-id="38ba4-120">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="38ba4-121">PropertyCountForTable (格式) </span><span class="sxs-lookup"><span data-stu-id="38ba4-121">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="38ba4-122">可选元素。</span><span class="sxs-lookup"><span data-stu-id="38ba4-122">Optional element.</span></span><br /><br /> <span data-ttu-id="38ba4-123">指定在表视图中显示对象时必须包含的属性的最小数目。</span><span class="sxs-lookup"><span data-stu-id="38ba4-123">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="38ba4-124">ShowError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-124">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="38ba4-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="38ba4-125">Optional element.</span></span><br /><br /> <span data-ttu-id="38ba4-126">指定在显示一段数据的过程中出现错误时，显示完整的错误记录。</span><span class="sxs-lookup"><span data-stu-id="38ba4-126">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="38ba4-127">WrapTables Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-127">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="38ba4-128">可选元素。</span><span class="sxs-lookup"><span data-stu-id="38ba4-128">Optional element.</span></span><br /><br /> <span data-ttu-id="38ba4-129">指定如果表中的数据无法适应列的宽度，则将其移到下一行。</span><span class="sxs-lookup"><span data-stu-id="38ba4-129">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="38ba4-130">父元素</span><span class="sxs-lookup"><span data-stu-id="38ba4-130">Parent Elements</span></span>

|<span data-ttu-id="38ba4-131">元素</span><span class="sxs-lookup"><span data-stu-id="38ba4-131">Element</span></span>|<span data-ttu-id="38ba4-132">描述</span><span class="sxs-lookup"><span data-stu-id="38ba4-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="38ba4-133">配置元素</span><span class="sxs-lookup"><span data-stu-id="38ba4-133">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="38ba4-134">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="38ba4-134">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="38ba4-135">备注</span><span class="sxs-lookup"><span data-stu-id="38ba4-135">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="38ba4-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38ba4-136">See Also</span></span>

[<span data-ttu-id="38ba4-137">配置元素</span><span class="sxs-lookup"><span data-stu-id="38ba4-137">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="38ba4-138">DisplayError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-138">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="38ba4-139">EnumerableExpansions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-139">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="38ba4-140">PropertyCountForTable (格式) </span><span class="sxs-lookup"><span data-stu-id="38ba4-140">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="38ba4-141">ShowError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-141">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="38ba4-142">WrapTables Element (Format)</span><span class="sxs-lookup"><span data-stu-id="38ba4-142">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="38ba4-143">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="38ba4-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
