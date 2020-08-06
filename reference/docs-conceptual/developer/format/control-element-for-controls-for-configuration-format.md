---
title: " (格式) 的控件控件元素 |Microsoft Docs"
ms.date: 09/13/2016
ms.openlocfilehash: 9447efac84cff3cc33468aeebc97a8bdd6137518
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783817"
---
# <a name="control-element-for-controls-for-configuration-format"></a><span data-ttu-id="d9ddb-102">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d9ddb-102">Control Element for Controls for Configuration (Format)</span></span>

<span data-ttu-id="d9ddb-103">定义一个公共控件，该控件可供格式设置文件的所有视图和用于引用控件的名称使用。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-103">Defines a common control that can be used by all the views of the formatting file and the name that is used to reference the control.</span></span>

<span data-ttu-id="d9ddb-104">配置元素 (格式) 控制配置的元素 (格式) 控件的控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-104">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d9ddb-105">语法</span><span class="sxs-lookup"><span data-stu-id="d9ddb-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9ddb-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d9ddb-106">Attributes and Elements</span></span>

<span data-ttu-id="d9ddb-107">以下各节描述了元素的属性、子元素和父元素 `Control` 。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-107">The following sections describe the attributes, child elements, and the parent element for the `Control` element.</span></span> <span data-ttu-id="d9ddb-108">必须仅指定每个子元素中的一个。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-108">You must specify only one of each child element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9ddb-109">特性</span><span class="sxs-lookup"><span data-stu-id="d9ddb-109">Attributes</span></span>

<span data-ttu-id="d9ddb-110">无。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9ddb-111">子元素</span><span class="sxs-lookup"><span data-stu-id="d9ddb-111">Child Elements</span></span>

|<span data-ttu-id="d9ddb-112">元素</span><span class="sxs-lookup"><span data-stu-id="d9ddb-112">Element</span></span>|<span data-ttu-id="d9ddb-113">描述</span><span class="sxs-lookup"><span data-stu-id="d9ddb-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9ddb-114">CustomControl Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d9ddb-114">CustomControl Element for Control for Controls for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="d9ddb-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-115">Required element.</span></span><br /><br /> <span data-ttu-id="d9ddb-116">定义控件。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-116">Defines the control.</span></span>|
|[<span data-ttu-id="d9ddb-117">用于控件的名称元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-117">Name Element for Control for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)|<span data-ttu-id="d9ddb-118">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-118">Required element.</span></span><br /><br /> <span data-ttu-id="d9ddb-119">指定用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-119">Specifies the name used to reference the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d9ddb-120">父元素</span><span class="sxs-lookup"><span data-stu-id="d9ddb-120">Parent Elements</span></span>

|<span data-ttu-id="d9ddb-121">元素</span><span class="sxs-lookup"><span data-stu-id="d9ddb-121">Element</span></span>|<span data-ttu-id="d9ddb-122">描述</span><span class="sxs-lookup"><span data-stu-id="d9ddb-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9ddb-123">控件的控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-123">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)|<span data-ttu-id="d9ddb-124">定义可由格式设置文件的所有视图或其他控件使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="d9ddb-124">Defines the common controls that can be used by all views of the formatting file or by other controls.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9ddb-125">备注</span><span class="sxs-lookup"><span data-stu-id="d9ddb-125">Remarks</span></span>

<span data-ttu-id="d9ddb-126">可以在以下元素中引用为此控件指定的名称：</span><span class="sxs-lookup"><span data-stu-id="d9ddb-126">The name given to this control can be referenced in the following elements:</span></span>

- [<span data-ttu-id="d9ddb-127">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-127">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

- [<span data-ttu-id="d9ddb-128">View (格式的 GroupBy 元素) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-128">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="d9ddb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9ddb-129">See Also</span></span>

[<span data-ttu-id="d9ddb-130">控件的控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-130">Controls Element of Configuration (Format)</span></span>](./controls-element-for-configuration-format.md)

[<span data-ttu-id="d9ddb-131">用于控制配置 (格式的 CustomControl 元素) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-131">CustomControl element for Control for Configuration (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="d9ddb-132">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-132">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="d9ddb-133">View (格式的 GroupBy 元素) </span><span class="sxs-lookup"><span data-stu-id="d9ddb-133">GroupBy Element for View(Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="d9ddb-134">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="d9ddb-134">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="d9ddb-135">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="d9ddb-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
