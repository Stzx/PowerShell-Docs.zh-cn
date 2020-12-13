---
ms.date: 09/13/2016
ms.topic: reference
title: 定义选项集
description: 定义选项集
ms.openlocfilehash: d709a368a45623d56fdbf4e98a11a5e5f8a193fa
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648257"
---
# <a name="defining-selection-sets"></a><span data-ttu-id="755ff-103">定义选项集</span><span class="sxs-lookup"><span data-stu-id="755ff-103">Defining Selection Sets</span></span>

<span data-ttu-id="755ff-104">在创建多个视图和控件时，可以定义称为选择集的对象集。</span><span class="sxs-lookup"><span data-stu-id="755ff-104">When creating multiple views and controls, you can define sets of objects that are referred to as selection sets.</span></span> <span data-ttu-id="755ff-105">通过选择集，您可以一次性定义对象，而无需为每个视图或控件重复定义对象。</span><span class="sxs-lookup"><span data-stu-id="755ff-105">A selection set enables you to define the objects one time, without having to define them repeatedly for each view or control.</span></span> <span data-ttu-id="755ff-106">通常，当您有一组相关的 .NET 对象时，将使用选择集。</span><span class="sxs-lookup"><span data-stu-id="755ff-106">Typically, selection sets are used when you have a set of related .NET objects.</span></span> <span data-ttu-id="755ff-107">例如， `FileSystem` 格式化文件 ( # B0 xml) 定义多个视图使用的一组文件系统类型。</span><span class="sxs-lookup"><span data-stu-id="755ff-107">For example, The `FileSystem` formatting file (FileSystem.format.ps1xml) defines a selection set of the file system types that several views use.</span></span>

## <a name="where-selection-sets-are-defined-and-referenced"></a><span data-ttu-id="755ff-108">定义和引用选择集的位置</span><span class="sxs-lookup"><span data-stu-id="755ff-108">Where Selection Sets are Defined and Referenced</span></span>

<span data-ttu-id="755ff-109">将选择集定义为可由格式设置文件中定义的所有视图和控件使用的通用数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="755ff-109">You define selection sets as part of the common data that can be used by all the views and controls defined in the formatting file.</span></span> <span data-ttu-id="755ff-110">下面的示例演示如何定义三个选择集。</span><span class="sxs-lookup"><span data-stu-id="755ff-110">The following example shows how to define three selection sets.</span></span>

```xml
<Configuration>
  <SelectionSets>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
    <SelectionSet>...</SelectionSet>
  </SelectionSets>
</Configuration>
```

<span data-ttu-id="755ff-111">可以通过以下方式引用选项集：</span><span class="sxs-lookup"><span data-stu-id="755ff-111">You can reference a selection sets in the following ways:</span></span>

- <span data-ttu-id="755ff-112">每个视图都有一个 `ViewSelectedBy` 元素，该元素定义使用视图显示的对象。</span><span class="sxs-lookup"><span data-stu-id="755ff-112">Each view has a `ViewSelectedBy` element that defines which objects are displayed by using the view.</span></span> <span data-ttu-id="755ff-113">`ViewSelectedBy`元素有一个 `SelectionSetName` 子元素，该元素指定视图的所有定义所使用的选择集。</span><span class="sxs-lookup"><span data-stu-id="755ff-113">The `ViewSelectedBy` element has a `SelectionSetName` child element that specifies the selection set that all the definitions of the view use.</span></span> <span data-ttu-id="755ff-114">对于可以从视图引用的选择集的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="755ff-114">There is no restriction on the number of selection sets that you can reference from a view.</span></span>

- <span data-ttu-id="755ff-115">在视图或控件的每个定义中， `EntrySelectedBy` 元素定义使用该定义显示的对象。</span><span class="sxs-lookup"><span data-stu-id="755ff-115">In each definition of a view or control, the `EntrySelectedBy` element defines which objects are displayed by using that definition.</span></span> <span data-ttu-id="755ff-116">通常，视图或控件只有一个定义，因此这些对象由 `ViewSelectedBy` 元素定义。</span><span class="sxs-lookup"><span data-stu-id="755ff-116">Typically a view or control has only one definition so the objects are defined by the `ViewSelectedBy` element.</span></span> <span data-ttu-id="755ff-117">`EntrySelectedBy`定义的元素包含一个 `SelectionSetName` 指定选择集的子元素。</span><span class="sxs-lookup"><span data-stu-id="755ff-117">The `EntrySelectedBy` element of the definition has a `SelectionSetName` child element that specifies the selection set.</span></span> <span data-ttu-id="755ff-118">如果为定义指定选择集，则不能指定元素的任何其他子元素 `EntrySelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="755ff-118">If you specify the selection set for a definition, you cannot specify any of the other child elements of the `EntrySelectedBy` element.</span></span>

- <span data-ttu-id="755ff-119">在视图或控件的每个定义中， `SelectionCondition` 元素可用于指定使用定义的条件。</span><span class="sxs-lookup"><span data-stu-id="755ff-119">In each definition of a view or control, the `SelectionCondition` element can be used to specify a condition for when the definition is used.</span></span> <span data-ttu-id="755ff-120">`SelectionCondition`元素有一个 `SelectionSetName` 子元素，该元素指定触发条件的选择集。</span><span class="sxs-lookup"><span data-stu-id="755ff-120">The `SelectionCondition` element has a `SelectionSetName` child element that specifies the selection set that triggers the condition.</span></span> <span data-ttu-id="755ff-121">当显示选择集中定义的任何对象时，将触发该条件。</span><span class="sxs-lookup"><span data-stu-id="755ff-121">The condition is triggered when any of the objects defined in the selection set are displayed.</span></span> <span data-ttu-id="755ff-122">有关如何设置这些条件的详细信息，请参阅为 [数据显示定义条件](./defining-conditions-for-displaying-data.md)。</span><span class="sxs-lookup"><span data-stu-id="755ff-122">For more information about how to set these conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="selection-set-example"></a><span data-ttu-id="755ff-123">选择集示例</span><span class="sxs-lookup"><span data-stu-id="755ff-123">Selection Set Example</span></span>

<span data-ttu-id="755ff-124">以下示例显示了直接从 `FileSystem` Windows PowerShell 提供的格式化文件中获取的选项集。</span><span class="sxs-lookup"><span data-stu-id="755ff-124">The following example shows a selection set that is taken directly from the `FileSystem` formatting file provided by Windows PowerShell.</span></span> <span data-ttu-id="755ff-125">有关其他 Windows PowerShell 格式设置文件的详细信息，请参阅 [Windows Powershell 格式设置文件](./powershell-formatting-files.md)。</span><span class="sxs-lookup"><span data-stu-id="755ff-125">For more information about other Windows PowerShell formatting files, see [Windows PowerShell Formatting Files](./powershell-formatting-files.md).</span></span>

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

<span data-ttu-id="755ff-126">在表视图的元素中引用了上一选择集 `ViewSelectedBy` 。</span><span class="sxs-lookup"><span data-stu-id="755ff-126">The previous selection set is referenced in the `ViewSelectedBy` element of a table view.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>Files</Name>
    <ViewSelectedBy>
      <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="xml-elements"></a><span data-ttu-id="755ff-127">XML 元素</span><span class="sxs-lookup"><span data-stu-id="755ff-127">XML Elements</span></span>

 <span data-ttu-id="755ff-128">您可以定义的选项集数没有限制。</span><span class="sxs-lookup"><span data-stu-id="755ff-128">There is no limit to the number of selection sets that you can define.</span></span> <span data-ttu-id="755ff-129">以下 XML 元素用于创建选择集。</span><span class="sxs-lookup"><span data-stu-id="755ff-129">The following XML elements are used to create a selection set.</span></span>

- <span data-ttu-id="755ff-130">[SelectionSets](./selectionsets-element-format.md)元素定义格式设置文件的视图和控件引用的 .net 对象集。</span><span class="sxs-lookup"><span data-stu-id="755ff-130">The [SelectionSets](./selectionsets-element-format.md) element defines the sets of .NET objects that are referenced by the views and controls of the formatting file.</span></span>

- <span data-ttu-id="755ff-131">[SelectionSet](./selectionset-element-format.md)元素定义一组 .net 对象。</span><span class="sxs-lookup"><span data-stu-id="755ff-131">The [SelectionSet](./selectionset-element-format.md) element defines a single set of .NET objects.</span></span>

- <span data-ttu-id="755ff-132">[Name](./name-element-for-selectionset-format.md)元素指定用于引用选项集的名称。</span><span class="sxs-lookup"><span data-stu-id="755ff-132">The [Name](./name-element-for-selectionset-format.md) element specifies the name that is used to reference the selection set.</span></span>

- <span data-ttu-id="755ff-133">[类型](./types-element-for-selectionset-format.md)元素指定选择集的对象的 .net 类型。</span><span class="sxs-lookup"><span data-stu-id="755ff-133">The [Types](./types-element-for-selectionset-format.md) element specifies the .NET types of the objects of the selection set.</span></span> <span data-ttu-id="755ff-134"> (在格式设置文件中，对象由其 .NET 类型指定。 ) </span><span class="sxs-lookup"><span data-stu-id="755ff-134">(Within formatting files, objects are specified by their .NET type.)</span></span>

 <span data-ttu-id="755ff-135">以下 XML 元素用于指定选择集。</span><span class="sxs-lookup"><span data-stu-id="755ff-135">The following XML elements are used to specify a selection set.</span></span>

- <span data-ttu-id="755ff-136">以下元素指定要在视图的所有定义中使用的选择集：</span><span class="sxs-lookup"><span data-stu-id="755ff-136">The following element specifies the selection set to use in all the definitions of the view:</span></span>

  - [<span data-ttu-id="755ff-137">SelectionSetName Element for ViewSelectedBy (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-137">SelectionSetName Element for ViewSelectedBy (Format)</span></span>](./selectionsetname-element-for-viewselectedby-format.md)

  - [<span data-ttu-id="755ff-138">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-138">SelectionSetName Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="755ff-139">以下元素指定单个视图定义使用的选择集：</span><span class="sxs-lookup"><span data-stu-id="755ff-139">The following elements specify the selection set used by a single view definition:</span></span>

  - [<span data-ttu-id="755ff-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-140">SelectionSetName Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="755ff-141">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-141">SelectionSetName Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="755ff-142">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-142">SelectionSetName Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="755ff-143">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-143">SelectionSetName Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

- <span data-ttu-id="755ff-144">以下元素指定 common 和 view 控件定义所使用的选择集：</span><span class="sxs-lookup"><span data-stu-id="755ff-144">The following elements specify the selection set used by common and view control definitions:</span></span>

  - [<span data-ttu-id="755ff-145">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-145">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)

  - [<span data-ttu-id="755ff-146">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-146">SelectionSetName Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-configuration-format.md)

- <span data-ttu-id="755ff-147">以下元素指定在定义要扩展的对象时所使用的选择集：</span><span class="sxs-lookup"><span data-stu-id="755ff-147">The following elements specify the selection set used when you define which object to expand:</span></span>

  - [<span data-ttu-id="755ff-148">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-148">SelectionSetName Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="755ff-149">以下元素指定选择条件使用的选择集。</span><span class="sxs-lookup"><span data-stu-id="755ff-149">The following elements specify the selection set used by selection conditions.</span></span>

  - [<span data-ttu-id="755ff-150">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-150">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="755ff-151">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-151">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

  - [<span data-ttu-id="755ff-152">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-152">SelectionSetName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

  - [<span data-ttu-id="755ff-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-153">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

  - [<span data-ttu-id="755ff-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-154">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)

  - [<span data-ttu-id="755ff-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-155">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableControl (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="755ff-156">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-156">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

  - [<span data-ttu-id="755ff-157">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="755ff-157">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="755ff-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="755ff-158">See Also</span></span>

[<span data-ttu-id="755ff-159">SelectionSets</span><span class="sxs-lookup"><span data-stu-id="755ff-159">SelectionSets</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="755ff-160">SelectionSet</span><span class="sxs-lookup"><span data-stu-id="755ff-160">SelectionSet</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="755ff-161">名称</span><span class="sxs-lookup"><span data-stu-id="755ff-161">Name</span></span>](./name-element-for-selectionset-format.md)

[<span data-ttu-id="755ff-162">类型</span><span class="sxs-lookup"><span data-stu-id="755ff-162">Types</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="755ff-163">PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="755ff-163">PowerShell Formatting Files</span></span>](./powershell-formatting-files.md)

[<span data-ttu-id="755ff-164">定义显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="755ff-164">Defining Conditions for when Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="755ff-165">编写 PowerShell 格式设置和类型文件</span><span class="sxs-lookup"><span data-stu-id="755ff-165">Writing a PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
