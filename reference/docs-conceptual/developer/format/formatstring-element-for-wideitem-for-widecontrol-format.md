---
ms.date: 09/13/2016
ms.topic: reference
title: FormatString Element for WideItem for WideControl (Format)
description: FormatString Element for WideItem for WideControl (Format)
ms.openlocfilehash: f67a18e3ec4f1323e7f9be8904db518c679d53e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667872"
---
# <a name="formatstring-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="b1af8-103">FormatString Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b1af8-103">FormatString Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="b1af8-104">指定定义属性或脚本值在视图中显示方式的格式模式。</span><span class="sxs-lookup"><span data-stu-id="b1af8-104">Specifies a format pattern that defines how the property or script value is displayed in the view.</span></span>

<span data-ttu-id="b1af8-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (WideControl) 格式 (WideItem) 格式的元素 (WideControl) 格式</span><span class="sxs-lookup"><span data-stu-id="b1af8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element for WideControl (Format) WideItem Element for WideControl (Format) FormatString Element for WideItem for WideControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b1af8-106">语法</span><span class="sxs-lookup"><span data-stu-id="b1af8-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b1af8-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b1af8-107">Attributes and Elements</span></span>

<span data-ttu-id="b1af8-108">以下各节描述了元素的属性、子元素和父元素 `FormatString` 。</span><span class="sxs-lookup"><span data-stu-id="b1af8-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b1af8-109">特性</span><span class="sxs-lookup"><span data-stu-id="b1af8-109">Attributes</span></span>

<span data-ttu-id="b1af8-110">无。</span><span class="sxs-lookup"><span data-stu-id="b1af8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b1af8-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b1af8-111">Child Elements</span></span>

<span data-ttu-id="b1af8-112">无。</span><span class="sxs-lookup"><span data-stu-id="b1af8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b1af8-113">父元素</span><span class="sxs-lookup"><span data-stu-id="b1af8-113">Parent Elements</span></span>

|<span data-ttu-id="b1af8-114">元素</span><span class="sxs-lookup"><span data-stu-id="b1af8-114">Element</span></span>|<span data-ttu-id="b1af8-115">描述</span><span class="sxs-lookup"><span data-stu-id="b1af8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1af8-116">WideItem Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b1af8-116">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="b1af8-117">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="b1af8-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b1af8-118">文本值</span><span class="sxs-lookup"><span data-stu-id="b1af8-118">Text Value</span></span>

<span data-ttu-id="b1af8-119">指定用于设置数据格式的模式。</span><span class="sxs-lookup"><span data-stu-id="b1af8-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="b1af8-120">例如，你可以使用此模式来 [设置类型为](/dotnet/api/System.TimeSpan)system.string： {0： MMM} {0： dd} {0： HH}： {0： mm} 的任何属性的值的格式。</span><span class="sxs-lookup"><span data-stu-id="b1af8-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1af8-121">备注</span><span class="sxs-lookup"><span data-stu-id="b1af8-121">Remarks</span></span>

<span data-ttu-id="b1af8-122">创建表视图、列表视图、宽视图或自定义视图时，可以使用格式字符串。</span><span class="sxs-lookup"><span data-stu-id="b1af8-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="b1af8-123">有关设置视图中显示的值的格式的详细信息，请参阅 [设置显示的数据的格式](./formatting-displayed-data.md)。</span><span class="sxs-lookup"><span data-stu-id="b1af8-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="b1af8-124">有关在宽视图中使用格式字符串的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="b1af8-124">For more information about using format strings in wide views, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="b1af8-125">示例</span><span class="sxs-lookup"><span data-stu-id="b1af8-125">Example</span></span>

<span data-ttu-id="b1af8-126">下面的示例演示如何为属性的值定义格式字符串 `StartTime` 。</span><span class="sxs-lookup"><span data-stu-id="b1af8-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<WideItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="b1af8-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1af8-127">See Also</span></span>

[<span data-ttu-id="b1af8-128">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="b1af8-128">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="b1af8-129">WideItem Element for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="b1af8-129">WideItem Element for WideControl (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="b1af8-130">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="b1af8-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
