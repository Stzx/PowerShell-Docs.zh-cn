---
ms.date: 09/13/2016
ms.topic: reference
title: FormatString Element for ListItem for ListControl (Format)
description: FormatString Element for ListItem for ListControl (Format)
ms.openlocfilehash: 1c16da92928ea632241942f4f2c63390c4fea706
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667906"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="63faf-103">FormatString Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="63faf-103">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="63faf-104">指定一个定义如何显示属性或脚本值的格式模式。</span><span class="sxs-lookup"><span data-stu-id="63faf-104">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="63faf-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry) 格式 (ListControl 元素 for ListControl) format (ListItems 元素 for ListControl) 格式 (元素 for ListControl) 格式 (</span><span class="sxs-lookup"><span data-stu-id="63faf-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="63faf-106">语法</span><span class="sxs-lookup"><span data-stu-id="63faf-106">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="63faf-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63faf-107">Attributes and Elements</span></span>

<span data-ttu-id="63faf-108">以下各节描述了元素的属性、子元素和父元素 `FormatString` 。</span><span class="sxs-lookup"><span data-stu-id="63faf-108">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="63faf-109">特性</span><span class="sxs-lookup"><span data-stu-id="63faf-109">Attributes</span></span>

<span data-ttu-id="63faf-110">无。</span><span class="sxs-lookup"><span data-stu-id="63faf-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="63faf-111">子元素</span><span class="sxs-lookup"><span data-stu-id="63faf-111">Child Elements</span></span>

<span data-ttu-id="63faf-112">无。</span><span class="sxs-lookup"><span data-stu-id="63faf-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="63faf-113">父元素</span><span class="sxs-lookup"><span data-stu-id="63faf-113">Parent Elements</span></span>

|<span data-ttu-id="63faf-114">元素</span><span class="sxs-lookup"><span data-stu-id="63faf-114">Element</span></span>|<span data-ttu-id="63faf-115">描述</span><span class="sxs-lookup"><span data-stu-id="63faf-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="63faf-116"> (格式的) 元素元素 </span><span class="sxs-lookup"><span data-stu-id="63faf-116">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="63faf-117">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="63faf-117">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="63faf-118">文本值</span><span class="sxs-lookup"><span data-stu-id="63faf-118">Text Value</span></span>

<span data-ttu-id="63faf-119">指定用于设置数据格式的模式。</span><span class="sxs-lookup"><span data-stu-id="63faf-119">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="63faf-120">例如，你可以使用此模式来 [设置类型为](/dotnet/api/System.TimeSpan)system.string： {0： MMM} {0： dd} {0： HH}： {0： mm} 的任何属性的值的格式。</span><span class="sxs-lookup"><span data-stu-id="63faf-120">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="63faf-121">备注</span><span class="sxs-lookup"><span data-stu-id="63faf-121">Remarks</span></span>

<span data-ttu-id="63faf-122">创建表视图、列表视图、宽视图或自定义视图时，可以使用格式字符串。</span><span class="sxs-lookup"><span data-stu-id="63faf-122">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="63faf-123">有关设置视图中显示的值的格式的详细信息，请参阅 [设置显示的数据的格式](./formatting-displayed-data.md)。</span><span class="sxs-lookup"><span data-stu-id="63faf-123">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="63faf-124">有关在列表视图中使用格式字符串的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="63faf-124">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="63faf-125">示例</span><span class="sxs-lookup"><span data-stu-id="63faf-125">Example</span></span>

<span data-ttu-id="63faf-126">下面的示例演示如何为属性的值定义格式字符串 `StartTime` 。</span><span class="sxs-lookup"><span data-stu-id="63faf-126">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="63faf-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63faf-127">See Also</span></span>

[<span data-ttu-id="63faf-128">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="63faf-128">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="63faf-129"> (格式的) 元素元素 </span><span class="sxs-lookup"><span data-stu-id="63faf-129">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="63faf-130">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="63faf-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
