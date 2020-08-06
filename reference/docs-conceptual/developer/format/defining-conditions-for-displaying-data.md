---
title: 定义用于显示数据的条件 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13de078e681708b02e378b2c7d531032b2ffdc05
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774331"
---
# <a name="defining-conditions-for-displaying-data"></a><span data-ttu-id="ea284-102">定义用于显示数据的条件</span><span class="sxs-lookup"><span data-stu-id="ea284-102">Defining Conditions for Displaying Data</span></span>

<span data-ttu-id="ea284-103">定义视图或控件显示的数据时，您可以指定一个必须存在的条件，以便显示数据。</span><span class="sxs-lookup"><span data-stu-id="ea284-103">When defining what data is displayed by a view or a control, you can specify a condition that must exist for the data to be displayed.</span></span> <span data-ttu-id="ea284-104">条件可由特定属性触发，或者在脚本或属性值的计算结果为时触发 `true` 。</span><span class="sxs-lookup"><span data-stu-id="ea284-104">The condition can be triggered by a specific property, or when a script or property value evaluates to `true`.</span></span> <span data-ttu-id="ea284-105">如果满足选择条件，将使用视图或控件的定义。</span><span class="sxs-lookup"><span data-stu-id="ea284-105">When the selection condition is met, the definition of the view or control is used.</span></span>

## <a name="specifying-a-selection-condition-for-a-definition"></a><span data-ttu-id="ea284-106">为定义指定选择条件</span><span class="sxs-lookup"><span data-stu-id="ea284-106">Specifying a Selection Condition for a Definition</span></span>

<span data-ttu-id="ea284-107">创建视图或控件的定义时， `EntrySelectedBy` 元素用于指定将使用定义的对象或必须存在的条件才能使用定义。</span><span class="sxs-lookup"><span data-stu-id="ea284-107">When creating a definition for a view or control, the `EntrySelectedBy` element is used to specify which objects will use the definition or what condition must exist for the definition to be used.</span></span> <span data-ttu-id="ea284-108">条件由 `SelectionCondition` 元素指定。</span><span class="sxs-lookup"><span data-stu-id="ea284-108">The condition is specified by the `SelectionCondition` element.</span></span>

<span data-ttu-id="ea284-109">在下面的示例中，将为表视图的定义指定选择条件。</span><span class="sxs-lookup"><span data-stu-id="ea284-109">In the following example, a selection condition is specified for a definition of a table view.</span></span> <span data-ttu-id="ea284-110">在此示例中，仅当指定的脚本的计算结果为时，才会使用定义 `true` 。</span><span class="sxs-lookup"><span data-stu-id="ea284-110">In this example, the definition is used only when the specified script is evaluated to `true`.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <SelectionCondition>
      <ScriptBlock>ScriptToEvaluate</ScriptBlock>
    </SelectionCondition>
  </EntrySelectedBy>
  <TableColumnItems>
  </TableColumnItems>
</TableRowEntry>

```

<span data-ttu-id="ea284-111">对于您可以为视图或控件的定义指定的选择条件数没有限制。</span><span class="sxs-lookup"><span data-stu-id="ea284-111">There is no limit to the number of selection conditions that you can specify for a definition of a view or control.</span></span> <span data-ttu-id="ea284-112">唯一的要求如下：</span><span class="sxs-lookup"><span data-stu-id="ea284-112">The only requirements are the following:</span></span>

- <span data-ttu-id="ea284-113">选择条件必须指定一个属性名称或脚本来触发条件，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ea284-113">The selection condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

- <span data-ttu-id="ea284-114">选择条件可以指定任意数量的 .NET 类型或选择集，但是不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ea284-114">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

## <a name="specifying-a-selection-condition-for-an-item"></a><span data-ttu-id="ea284-115">指定项的选择条件</span><span class="sxs-lookup"><span data-stu-id="ea284-115">Specifying a Selection Condition for an Item</span></span>

<span data-ttu-id="ea284-116">你还可以通过 `ItemSelectionCondition` 在项定义中包含元素来指定何时使用列表视图或控件的项。</span><span class="sxs-lookup"><span data-stu-id="ea284-116">You can also specify when an item of a list view or control is used by including the `ItemSelectionCondition` element in the item definition.</span></span> <span data-ttu-id="ea284-117">在下面的示例中，为列表视图的项指定了选择条件。</span><span class="sxs-lookup"><span data-stu-id="ea284-117">In the following example, a selection condition is specified for an item of a list view.</span></span> <span data-ttu-id="ea284-118">在此示例中，仅当将脚本计算为时，才使用项 `true` 。</span><span class="sxs-lookup"><span data-stu-id="ea284-118">In this example, the item is used only when the script is evaluated to `true`.</span></span>

```xml
<ListItem>
  <ItemSelectionCondition>
    <ScriptBlock>ScriptToEvaluate</ScriptBlock>
  </ItemSelectionCondition>
</ListItem>

```

<span data-ttu-id="ea284-119">只能为项指定一个选择条件。</span><span class="sxs-lookup"><span data-stu-id="ea284-119">You can specify only one selection condition for an item.</span></span> <span data-ttu-id="ea284-120">条件必须指定一个属性名称或脚本来触发条件，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="ea284-120">And the condition must specify one property name or script to trigger the condition, but cannot specify both.</span></span>

## <a name="xml-elements"></a><span data-ttu-id="ea284-121">XML 元素</span><span class="sxs-lookup"><span data-stu-id="ea284-121">XML Elements</span></span>

 <span data-ttu-id="ea284-122">以下 XML 元素用于创建选择条件。</span><span class="sxs-lookup"><span data-stu-id="ea284-122">The following XML elements are used to create a selection condition.</span></span>

- <span data-ttu-id="ea284-123">以下元素指定了视图定义的选择条件：</span><span class="sxs-lookup"><span data-stu-id="ea284-123">The following elements specify selection conditions for view definitions:</span></span>

  - [<span data-ttu-id="ea284-124">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-124">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-tablecontrol-format.md)

  - [<span data-ttu-id="ea284-125">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-125">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

  - [<span data-ttu-id="ea284-126">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-126">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

  - [<span data-ttu-id="ea284-127">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-127">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

- <span data-ttu-id="ea284-128">以下元素指定常用和视图控件定义的选择条件：</span><span class="sxs-lookup"><span data-stu-id="ea284-128">The following elements specify selection conditions for common and view control definitions:</span></span>

  - [<span data-ttu-id="ea284-129">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-129">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="ea284-130">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-130">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

- <span data-ttu-id="ea284-131">以下元素指定展开集合对象的选择条件：</span><span class="sxs-lookup"><span data-stu-id="ea284-131">The following element specifies the selection condition for expanding collection objects:</span></span>

  - [<span data-ttu-id="ea284-132">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-132">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

- <span data-ttu-id="ea284-133">以下元素指定用于显示新数据组的选择条件：</span><span class="sxs-lookup"><span data-stu-id="ea284-133">The following element specifies the selection condition for displaying a new group of data:</span></span>

  - [<span data-ttu-id="ea284-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-134">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

- <span data-ttu-id="ea284-135">以下元素为列表视图指定项选择条件：</span><span class="sxs-lookup"><span data-stu-id="ea284-135">The following element specifies an item selection condition for a list view:</span></span>

  - [<span data-ttu-id="ea284-136">ItemSelectionCondition Element for ListItem for ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-136">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)

- <span data-ttu-id="ea284-137">以下元素为控件指定项选择条件：</span><span class="sxs-lookup"><span data-stu-id="ea284-137">The following elements specify an item selection condition for controls:</span></span>

  - [<span data-ttu-id="ea284-138">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-138">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)

  - [<span data-ttu-id="ea284-139">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-139">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format.md)

  - [<span data-ttu-id="ea284-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="ea284-140">ItemSelectionCondition Element for ExpressionBinding for CustomControl (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

## <a name="see-also"></a><span data-ttu-id="ea284-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea284-141">See Also</span></span>

[<span data-ttu-id="ea284-142">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ea284-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
