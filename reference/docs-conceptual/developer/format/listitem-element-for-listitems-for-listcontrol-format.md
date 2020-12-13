---
ms.date: 09/13/2016
ms.topic: reference
title: ListItem Element for ListItems for ListControl (Format)
description: ListItem Element for ListItems for ListControl (Format)
ms.openlocfilehash: 999491b7851aa4fa21667ad376d7e9853500ca08
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666546"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="13347-103">ListItem Element for ListItems for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="13347-103">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="13347-104">定义其值显示在列表视图的行中的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="13347-104">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="13347-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) ListControl 元素 (格式) ListEntries 元素 (ListEntry) 格式 (ListControl 元素) ListItems (格式) ListControl 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="13347-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="13347-106">语法</span><span class="sxs-lookup"><span data-stu-id="13347-106">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="13347-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13347-107">Attributes and Elements</span></span>

<span data-ttu-id="13347-108">以下各节描述了元素的属性、子元素和父元素 `ListItem` 。</span><span class="sxs-lookup"><span data-stu-id="13347-108">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="13347-109">只能指定一个属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="13347-109">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="13347-110">特性</span><span class="sxs-lookup"><span data-stu-id="13347-110">Attributes</span></span>

<span data-ttu-id="13347-111">无</span><span class="sxs-lookup"><span data-stu-id="13347-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="13347-112">子元素</span><span class="sxs-lookup"><span data-stu-id="13347-112">Child Elements</span></span>

|<span data-ttu-id="13347-113">元素</span><span class="sxs-lookup"><span data-stu-id="13347-113">Element</span></span>|<span data-ttu-id="13347-114">描述</span><span class="sxs-lookup"><span data-stu-id="13347-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13347-115">ListControl (格式的输入字符串的格式字符串元素) </span><span class="sxs-lookup"><span data-stu-id="13347-115">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="13347-116">可选元素。</span><span class="sxs-lookup"><span data-stu-id="13347-116">Optional element.</span></span><br /><br /> <span data-ttu-id="13347-117">指定定义属性或脚本值显示方式的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="13347-117">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="13347-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="13347-118">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="13347-119">可选元素。</span><span class="sxs-lookup"><span data-stu-id="13347-119">Optional element.</span></span><br /><br /> <span data-ttu-id="13347-120">定义要使用此列表项必须存在的条件。</span><span class="sxs-lookup"><span data-stu-id="13347-120">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="13347-121">Label Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="13347-121">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="13347-122">可选元素</span><span class="sxs-lookup"><span data-stu-id="13347-122">Optional element</span></span><br /><br /> <span data-ttu-id="13347-123">指定在行的属性或脚本值左侧显示的标签。</span><span class="sxs-lookup"><span data-stu-id="13347-123">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="13347-124">PropertyName Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="13347-124">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="13347-125">可选元素。</span><span class="sxs-lookup"><span data-stu-id="13347-125">Optional element.</span></span><br /><br /> <span data-ttu-id="13347-126">指定其值显示在行中的 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="13347-126">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="13347-127">ScriptBlock Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="13347-127">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="13347-128">可选元素。</span><span class="sxs-lookup"><span data-stu-id="13347-128">Optional element.</span></span><br /><br /> <span data-ttu-id="13347-129">指定其值在行中显示的脚本。</span><span class="sxs-lookup"><span data-stu-id="13347-129">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="13347-130">父元素</span><span class="sxs-lookup"><span data-stu-id="13347-130">Parent Elements</span></span>

|<span data-ttu-id="13347-131">元素</span><span class="sxs-lookup"><span data-stu-id="13347-131">Element</span></span>|<span data-ttu-id="13347-132">描述</span><span class="sxs-lookup"><span data-stu-id="13347-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13347-133"> (格式的列表控件的 ListItems 元素) </span><span class="sxs-lookup"><span data-stu-id="13347-133">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="13347-134">定义其值在列表视图中显示的属性和脚本。</span><span class="sxs-lookup"><span data-stu-id="13347-134">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="13347-135">备注</span><span class="sxs-lookup"><span data-stu-id="13347-135">Remarks</span></span>

<span data-ttu-id="13347-136">有关列表视图组件的详细信息，请参阅 [创建列表视图](./creating-a-list-view.md)。</span><span class="sxs-lookup"><span data-stu-id="13347-136">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="13347-137">示例</span><span class="sxs-lookup"><span data-stu-id="13347-137">Example</span></span>

<span data-ttu-id="13347-138">此示例显示了用于定义列表视图的三行的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="13347-138">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="13347-139">前两行显示 .NET 属性的值，最后一行显示脚本生成的值。</span><span class="sxs-lookup"><span data-stu-id="13347-139">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a><span data-ttu-id="13347-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13347-140">See Also</span></span>

[<span data-ttu-id="13347-141">ListItems 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="13347-141">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="13347-142">输入 (格式的格式字符串元素) </span><span class="sxs-lookup"><span data-stu-id="13347-142">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="13347-143">标志元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="13347-143">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="13347-144"> (格式的名称名称元素) </span><span class="sxs-lookup"><span data-stu-id="13347-144">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="13347-145">输入 (格式的 ScriptBlock 元素) </span><span class="sxs-lookup"><span data-stu-id="13347-145">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="13347-146">创建列表视图</span><span class="sxs-lookup"><span data-stu-id="13347-146">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="13347-147">编写 Windows PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="13347-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
