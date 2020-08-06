---
title: View (Format) 控件的控件元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 13ea2f09aec7fea8e5460197f133b5f5219cd369
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783800"
---
# <a name="control-element-for-controls-for-view--format"></a><span data-ttu-id="ae391-102">Control Element for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-102">Control Element for Controls for View  (Format)</span></span>

<span data-ttu-id="ae391-103">定义可供视图使用的控件以及用于引用控件的名称。</span><span class="sxs-lookup"><span data-stu-id="ae391-103">Defines a control that can be used by the view and the name that is used to reference the control.</span></span>

<span data-ttu-id="ae391-104">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 控件 (格式) 控件元素</span><span class="sxs-lookup"><span data-stu-id="ae391-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ae391-105">语法</span><span class="sxs-lookup"><span data-stu-id="ae391-105">Syntax</span></span>

```xml
<Control>
  <Name>NameOfControl</Name>
  <CustomControl>...</CustomControl>
</Control>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ae391-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ae391-106">Attributes and Elements</span></span>

<span data-ttu-id="ae391-107">以下各节描述了元素的属性、子元素和父元素 `Control` 。</span><span class="sxs-lookup"><span data-stu-id="ae391-107">The following sections describe the attributes, child elements, and the parent element of the `Control` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae391-108">特性</span><span class="sxs-lookup"><span data-stu-id="ae391-108">Attributes</span></span>

<span data-ttu-id="ae391-109">无。</span><span class="sxs-lookup"><span data-stu-id="ae391-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ae391-110">子元素</span><span class="sxs-lookup"><span data-stu-id="ae391-110">Child Elements</span></span>

|<span data-ttu-id="ae391-111">元素</span><span class="sxs-lookup"><span data-stu-id="ae391-111">Element</span></span>|<span data-ttu-id="ae391-112">描述</span><span class="sxs-lookup"><span data-stu-id="ae391-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae391-113">用于控件的名称元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="ae391-113">Name Element for Control for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="ae391-114">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="ae391-114">Required element.</span></span><br /><br /> <span data-ttu-id="ae391-115">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="ae391-115">Specifies the name of the control.</span></span>|
|[<span data-ttu-id="ae391-116">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-116">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)|<span data-ttu-id="ae391-117">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="ae391-117">Required element.</span></span><br /><br /> <span data-ttu-id="ae391-118">定义此视图使用的控件。</span><span class="sxs-lookup"><span data-stu-id="ae391-118">Defines the control used by this view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ae391-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ae391-119">Parent Elements</span></span>

|<span data-ttu-id="ae391-120">元素</span><span class="sxs-lookup"><span data-stu-id="ae391-120">Element</span></span>|<span data-ttu-id="ae391-121">描述</span><span class="sxs-lookup"><span data-stu-id="ae391-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae391-122">控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="ae391-122">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="ae391-123">定义可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="ae391-123">Defines the view controls that can be used by a specific view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ae391-124">备注</span><span class="sxs-lookup"><span data-stu-id="ae391-124">Remarks</span></span>

<span data-ttu-id="ae391-125">此控件可由以下元素指定：</span><span class="sxs-lookup"><span data-stu-id="ae391-125">This control can be specified by the following elements:</span></span>

- [<span data-ttu-id="ae391-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-126">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

- [<span data-ttu-id="ae391-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-127">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

- [<span data-ttu-id="ae391-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-128">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

- [<span data-ttu-id="ae391-129">CustomControlName Element for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-129">CustomControlName Element for GroupBy (Format)</span></span>](./customcontrolname-element-for-groupby-format.md)

## <a name="see-also"></a><span data-ttu-id="ae391-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae391-130">See Also</span></span>

[<span data-ttu-id="ae391-131">CustomControl Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-131">CustomControl Element for Control for Controls for View (Format)</span></span>](./customcontrol-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ae391-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-132">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-view-format.md)

[<span data-ttu-id="ae391-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-133">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[<span data-ttu-id="ae391-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-134">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ae391-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-135">CustomControlName Element for ExpressionBinding for GroupBy (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-groupby-format.md)

[<span data-ttu-id="ae391-136">控件元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="ae391-136">Controls Element (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="ae391-137">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="ae391-137">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="ae391-138">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="ae391-138">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
