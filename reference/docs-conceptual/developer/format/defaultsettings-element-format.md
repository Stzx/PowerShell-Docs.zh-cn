---
title: " (格式) 的 DefaultSettings 元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 7da7948fc0814e38a8f3910596e223470ec27d75
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787727"
---
# <a name="defaultsettings-element-format"></a><span data-ttu-id="732b4-102">DefaultSettings Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-102">DefaultSettings Element (Format)</span></span>

<span data-ttu-id="732b4-103">定义适用于格式设置文件的所有视图的常见设置。</span><span class="sxs-lookup"><span data-stu-id="732b4-103">Defines common settings that apply to all the views of the formatting file.</span></span> <span data-ttu-id="732b4-104">常见的设置包括显示错误、在表中环绕文本、定义集合的展开方式等。</span><span class="sxs-lookup"><span data-stu-id="732b4-104">Common settings include displaying errors, wrapping text in tables, defining how collections are expanded, and more.</span></span>

<span data-ttu-id="732b4-105">配置元素 (格式) DefaultSettings 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="732b4-105">Configuration Element (Format) DefaultSettings Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="732b4-106">语法</span><span class="sxs-lookup"><span data-stu-id="732b4-106">Syntax</span></span>

```xml
<DefaultSettings>
  <ShowError/>
  <DisplayError/>
 <PropertyCountForTable>NumberOfProperties</PropertyCountFortable>
  <WrapTables/>
  <EnumerableExpansions>...</EnumerableExpansions>
</DefaultSettings>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="732b4-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="732b4-107">Attributes and Elements</span></span>

<span data-ttu-id="732b4-108">以下各节描述了元素的属性、子元素和父元素 `DefaultSettings` 。</span><span class="sxs-lookup"><span data-stu-id="732b4-108">The following sections describe attributes, child elements, and the parent element of the `DefaultSettings` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="732b4-109">特性</span><span class="sxs-lookup"><span data-stu-id="732b4-109">Attributes</span></span>

<span data-ttu-id="732b4-110">无。</span><span class="sxs-lookup"><span data-stu-id="732b4-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="732b4-111">子元素</span><span class="sxs-lookup"><span data-stu-id="732b4-111">Child Elements</span></span>

|<span data-ttu-id="732b4-112">元素</span><span class="sxs-lookup"><span data-stu-id="732b4-112">Element</span></span>|<span data-ttu-id="732b4-113">说明</span><span class="sxs-lookup"><span data-stu-id="732b4-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="732b4-114">DisplayError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-114">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)|<span data-ttu-id="732b4-115">可选元素。</span><span class="sxs-lookup"><span data-stu-id="732b4-115">Optional element.</span></span><br /><br /> <span data-ttu-id="732b4-116">指定在显示一段数据的过程中出现错误时，显示字符串 #ERR。</span><span class="sxs-lookup"><span data-stu-id="732b4-116">Specifies that the string #ERR is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="732b4-117">EnumerableExpansions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-117">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)|<span data-ttu-id="732b4-118">可选元素。</span><span class="sxs-lookup"><span data-stu-id="732b4-118">Optional element.</span></span><br /><br /> <span data-ttu-id="732b4-119">定义 .NET 对象显示在视图中时的不同显示方式。</span><span class="sxs-lookup"><span data-stu-id="732b4-119">Defines the different ways that .NET objects are expanded when they are displayed in a view.</span></span>|
|[<span data-ttu-id="732b4-120">PropertyCountForTable (格式) </span><span class="sxs-lookup"><span data-stu-id="732b4-120">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)|<span data-ttu-id="732b4-121">可选元素。</span><span class="sxs-lookup"><span data-stu-id="732b4-121">Optional element.</span></span><br /><br /> <span data-ttu-id="732b4-122">指定在表视图中显示对象时必须包含的属性的最小数目。</span><span class="sxs-lookup"><span data-stu-id="732b4-122">Specifies the minimum number of properties that an object must have to display the object in a table view.</span></span>|
|[<span data-ttu-id="732b4-123">ShowError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-123">ShowError Element (Format)</span></span>](./showerror-element-format.md)|<span data-ttu-id="732b4-124">可选元素。</span><span class="sxs-lookup"><span data-stu-id="732b4-124">Optional element.</span></span><br /><br /> <span data-ttu-id="732b4-125">指定在显示一段数据的过程中出现错误时，显示完整的错误记录。</span><span class="sxs-lookup"><span data-stu-id="732b4-125">Specifies that the full error record is displayed when an error occurs while displaying a piece of data.</span></span>|
|[<span data-ttu-id="732b4-126">WrapTables Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-126">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)|<span data-ttu-id="732b4-127">可选元素。</span><span class="sxs-lookup"><span data-stu-id="732b4-127">Optional element.</span></span><br /><br /> <span data-ttu-id="732b4-128">指定如果表中的数据无法适应列的宽度，则将其移到下一行。</span><span class="sxs-lookup"><span data-stu-id="732b4-128">Specifies that data in a table is moved to the next line if it does not fit into the width of the column.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="732b4-129">父元素</span><span class="sxs-lookup"><span data-stu-id="732b4-129">Parent Elements</span></span>

|<span data-ttu-id="732b4-130">元素</span><span class="sxs-lookup"><span data-stu-id="732b4-130">Element</span></span>|<span data-ttu-id="732b4-131">说明</span><span class="sxs-lookup"><span data-stu-id="732b4-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="732b4-132">配置元素</span><span class="sxs-lookup"><span data-stu-id="732b4-132">Configuration Element</span></span>](./configuration-element-format.md)|<span data-ttu-id="732b4-133">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="732b4-133">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="732b4-134">备注</span><span class="sxs-lookup"><span data-stu-id="732b4-134">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="732b4-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="732b4-135">See Also</span></span>

[<span data-ttu-id="732b4-136">配置元素</span><span class="sxs-lookup"><span data-stu-id="732b4-136">Configuration Element</span></span>](./configuration-element-format.md)

[<span data-ttu-id="732b4-137">DisplayError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-137">DisplayError Element (Format)</span></span>](./displayerror-element-format.md)

[<span data-ttu-id="732b4-138">EnumerableExpansions Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-138">EnumerableExpansions Element (Format)</span></span>](./enumerableexpansions-element-format.md)

[<span data-ttu-id="732b4-139">PropertyCountForTable (格式) </span><span class="sxs-lookup"><span data-stu-id="732b4-139">PropertyCountForTable (Format)</span></span>](./propertycountfortable-element-format.md)

[<span data-ttu-id="732b4-140">ShowError Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-140">ShowError Element (Format)</span></span>](./showerror-element-format.md)

[<span data-ttu-id="732b4-141">WrapTables Element (Format)</span><span class="sxs-lookup"><span data-stu-id="732b4-141">WrapTables Element (Format)</span></span>](./wraptables-element-format.md)

[<span data-ttu-id="732b4-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="732b4-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
