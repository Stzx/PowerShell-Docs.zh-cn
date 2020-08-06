---
title: View (Format) 的控件的 ExpressionBinding 的 CustomControlName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 871c6afd89db9360ea5012191b08863a9441f899
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786010"
---
# <a name="customcontrolname-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="50899-102">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50899-102">CustomControlName Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="50899-103">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="50899-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="50899-104">定义可由视图使用的控件时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="50899-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="50899-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) 控件元素 (格式) 用于控件的控件 (控件元素) 用于控件的控件 (CustomControl 的 CustomEntries 元素用于视图 (格式的控件的 CustomEntries) CustomEntry 元素的格式) CustomItem 元素 For CustomEntry 的控件 For view) 格式的控件 (ExpressionBinding 元素) CustomItem 元素 For CustomControlName 的控件 (ExpressionBindine)  (</span><span class="sxs-lookup"><span data-stu-id="50899-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) CustomControlName Element for ExpressionBindine for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="50899-106">语法</span><span class="sxs-lookup"><span data-stu-id="50899-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="50899-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="50899-107">Attributes and Elements</span></span>

<span data-ttu-id="50899-108">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="50899-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="50899-109">特性</span><span class="sxs-lookup"><span data-stu-id="50899-109">Attributes</span></span>

<span data-ttu-id="50899-110">无。</span><span class="sxs-lookup"><span data-stu-id="50899-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="50899-111">子元素</span><span class="sxs-lookup"><span data-stu-id="50899-111">Child Elements</span></span>

<span data-ttu-id="50899-112">无。</span><span class="sxs-lookup"><span data-stu-id="50899-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="50899-113">父元素</span><span class="sxs-lookup"><span data-stu-id="50899-113">Parent Elements</span></span>

|<span data-ttu-id="50899-114">元素</span><span class="sxs-lookup"><span data-stu-id="50899-114">Element</span></span>|<span data-ttu-id="50899-115">说明</span><span class="sxs-lookup"><span data-stu-id="50899-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="50899-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50899-116">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="50899-117">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="50899-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="50899-118">文本值</span><span class="sxs-lookup"><span data-stu-id="50899-118">Text Value</span></span>

<span data-ttu-id="50899-119">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="50899-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="50899-120">备注</span><span class="sxs-lookup"><span data-stu-id="50899-120">Remarks</span></span>

<span data-ttu-id="50899-121">您可以创建可供格式设置文件的所有视图使用的公共控件，还可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="50899-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="50899-122">以下元素指定这些控件的名称：</span><span class="sxs-lookup"><span data-stu-id="50899-122">The following elements specify the names of these controls:</span></span>

- [<span data-ttu-id="50899-123">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="50899-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="50899-124">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50899-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="50899-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50899-125">See Also</span></span>

[<span data-ttu-id="50899-126">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="50899-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="50899-127">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50899-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="50899-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="50899-128">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="50899-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="50899-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
