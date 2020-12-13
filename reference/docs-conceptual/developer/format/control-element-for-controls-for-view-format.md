---
ms.date: 09/13/2016
ms.topic: reference
title: Control Element for Controls for View (Format)
description: Control Element for Controls for View (Format)
ms.openlocfilehash: c48b8b7ecaebfde5e6ed2123b837d92561551766
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668076"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="6e176-103">Control Element for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-103">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="6e176-104">定义可供视图使用的控件以及用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="6e176-104">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="6e176-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 控件 (格式) 控件元素</span><span class="sxs-lookup"><span data-stu-id="6e176-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="6e176-106">语法</span><span class="sxs-lookup"><span data-stu-id="6e176-106">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6e176-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6e176-107">Attributes and Elements</span></span>

<span data-ttu-id="6e176-108">以下各节描述了元素的属性、子元素和父元素 `Control` 。</span><span class="sxs-lookup"><span data-stu-id="6e176-108">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="6e176-109">特性</span><span class="sxs-lookup"><span data-stu-id="6e176-109">Attributes</span></span>

<span data-ttu-id="6e176-110">无。</span><span class="sxs-lookup"><span data-stu-id="6e176-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6e176-111">子元素</span><span class="sxs-lookup"><span data-stu-id="6e176-111">Child Elements</span></span>

|<span data-ttu-id="6e176-112">元素</span><span class="sxs-lookup"><span data-stu-id="6e176-112">Element</span></span>|<span data-ttu-id="6e176-113">描述</span><span class="sxs-lookup"><span data-stu-id="6e176-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e176-114">用于控件的名称元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="6e176-114">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="6e176-115">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="6e176-115">Required element.</span></span><br /><br /> <span data-ttu-id="6e176-116">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="6e176-116">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="6e176-117">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-117">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="6e176-118">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="6e176-118">Required element.</span></span><br /><br /> <span data-ttu-id="6e176-119">定义此视图使用的控件。</span><span class="sxs-lookup"><span data-stu-id="6e176-119">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6e176-120">父元素</span><span class="sxs-lookup"><span data-stu-id="6e176-120">Parent Elements</span></span>

|<span data-ttu-id="6e176-121">元素</span><span class="sxs-lookup"><span data-stu-id="6e176-121">Element</span></span>|<span data-ttu-id="6e176-122">描述</span><span class="sxs-lookup"><span data-stu-id="6e176-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6e176-123">控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="6e176-123">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="6e176-124">定义可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="6e176-124">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6e176-125">备注</span><span class="sxs-lookup"><span data-stu-id="6e176-125">Remarks</span></span>

<span data-ttu-id="6e176-126">此控件可由以下元素指定：</span><span class="sxs-lookup"><span data-stu-id="6e176-126">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="6e176-127">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-127">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="6e176-128">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-128">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="6e176-129">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-129">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="6e176-130">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-130">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="6e176-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e176-131">See Also</span></span>

[<span data-ttu-id="6e176-132">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-132">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="6e176-133">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-133">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="6e176-134">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-134">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="6e176-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6e176-136">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-136">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="6e176-137">控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="6e176-137">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="6e176-138">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="6e176-138">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="6e176-139">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="6e176-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
