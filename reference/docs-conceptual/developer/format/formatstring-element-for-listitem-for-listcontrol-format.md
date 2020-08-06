---
title: ListControl (Format) 的输入的格式字符串元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 9ec73aa1c2e8180258722627e30344de4e67bda5
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781573"
---
# <a name="formatstring-element-for-listitem-for-listcontrol--format"></a><span data-ttu-id="28b89-102">FormatString Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="28b89-102">FormatString Element for ListItem for ListControl  (Format)</span></span>

<span data-ttu-id="28b89-103">指定一个定义如何显示属性或脚本值的格式模式。</span><span class="sxs-lookup"><span data-stu-id="28b89-103">Specifies a format pattern that defines how the property or script value is displayed.</span></span>

<span data-ttu-id="28b89-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry) 格式 (ListControl 元素 for ListControl) format (ListItems 元素 for ListControl) 格式 (元素 for ListControl) 格式 (</span><span class="sxs-lookup"><span data-stu-id="28b89-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem Element for ListControl (Format) FormatString Element for ListItem for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="28b89-105">语法</span><span class="sxs-lookup"><span data-stu-id="28b89-105">Syntax</span></span>

```xml
<FormatString>PropertyPattern</FormatString>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="28b89-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28b89-106">Attributes and Elements</span></span>

<span data-ttu-id="28b89-107">以下各节描述了元素的属性、子元素和父元素 `FormatString` 。</span><span class="sxs-lookup"><span data-stu-id="28b89-107">The following sections describe the attributes, child elements, and the parent element of the `FormatString` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="28b89-108">特性</span><span class="sxs-lookup"><span data-stu-id="28b89-108">Attributes</span></span>

<span data-ttu-id="28b89-109">无。</span><span class="sxs-lookup"><span data-stu-id="28b89-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="28b89-110">子元素</span><span class="sxs-lookup"><span data-stu-id="28b89-110">Child Elements</span></span>

<span data-ttu-id="28b89-111">无。</span><span class="sxs-lookup"><span data-stu-id="28b89-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="28b89-112">父元素</span><span class="sxs-lookup"><span data-stu-id="28b89-112">Parent Elements</span></span>

|<span data-ttu-id="28b89-113">元素</span><span class="sxs-lookup"><span data-stu-id="28b89-113">Element</span></span>|<span data-ttu-id="28b89-114">描述</span><span class="sxs-lookup"><span data-stu-id="28b89-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="28b89-115"> (格式的) 元素元素</span><span class="sxs-lookup"><span data-stu-id="28b89-115">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)|<span data-ttu-id="28b89-116">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="28b89-116">Defines the property or script whose value is displayed in a row of the list view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="28b89-117">文本值</span><span class="sxs-lookup"><span data-stu-id="28b89-117">Text Value</span></span>

<span data-ttu-id="28b89-118">指定用于设置数据格式的模式。</span><span class="sxs-lookup"><span data-stu-id="28b89-118">Specify the pattern that is used to format the data.</span></span> <span data-ttu-id="28b89-119">例如，你可以使用此模式来[设置类型为](/dotnet/api/System.TimeSpan)system.string： {0： MMM} {0： dd} {0： HH}： {0： mm} 的任何属性的值的格式。</span><span class="sxs-lookup"><span data-stu-id="28b89-119">For example, you can use this pattern to format the value of any property that is of type [System.Timespan](/dotnet/api/System.TimeSpan): {0:MMM}{0:dd}{0:HH}:{0:mm}.</span></span>

## <a name="remarks"></a><span data-ttu-id="28b89-120">备注</span><span class="sxs-lookup"><span data-stu-id="28b89-120">Remarks</span></span>

<span data-ttu-id="28b89-121">创建表视图、列表视图、宽视图或自定义视图时，可以使用格式字符串。</span><span class="sxs-lookup"><span data-stu-id="28b89-121">Format strings can be used when creating table views, list views, wide views, or custom views.</span></span> <span data-ttu-id="28b89-122">有关设置视图中显示的值的格式的详细信息，请参阅[设置显示的数据的格式](./formatting-displayed-data.md)。</span><span class="sxs-lookup"><span data-stu-id="28b89-122">For more information about formatting a value displayed in a view, see [Formatting Displayed Data](./formatting-displayed-data.md).</span></span>

<span data-ttu-id="28b89-123">有关在列表视图中使用格式字符串的详细信息，请参阅[创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="28b89-123">For more information about using format strings in list views, see [Creating List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="28b89-124">示例</span><span class="sxs-lookup"><span data-stu-id="28b89-124">Example</span></span>

<span data-ttu-id="28b89-125">下面的示例演示如何为属性的值定义格式字符串 `StartTime` 。</span><span class="sxs-lookup"><span data-stu-id="28b89-125">The following example shows how to define a formatting string for the value of the `StartTime` property.</span></span>

```xml
<ListItem>
  <PropertyName>StartTime</PropertyName>
  <FormatString>{0:MMM} (0:DD) (0:HH):(0:MM)</FormatString>
</ListItem>
```

## <a name="see-also"></a><span data-ttu-id="28b89-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28b89-126">See Also</span></span>

[<span data-ttu-id="28b89-127">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="28b89-127">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="28b89-128"> (格式的) 元素元素</span><span class="sxs-lookup"><span data-stu-id="28b89-128">ListItem Element (Format)</span></span>](./listitem-element-for-listitems-for-listcontrol-format.md)

[<span data-ttu-id="28b89-129">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="28b89-129">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
