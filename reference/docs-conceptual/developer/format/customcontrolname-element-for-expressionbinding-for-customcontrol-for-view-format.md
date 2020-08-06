---
title: 用于 CustomControl for View (Format) 的 ExpressionBinding 的 CustomControlName 元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6f1ffca045b7efcecb4dce4e788a8c508fa6ef08
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783749"
---
# <a name="customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format"></a><span data-ttu-id="2522f-102">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="2522f-102">CustomControlName Element for ExpressionBinding for CustomControl for View (Format)</span></span>

<span data-ttu-id="2522f-103">指定公共控件或视图控件的名称。</span><span class="sxs-lookup"><span data-stu-id="2522f-103">Specifies the name of a common control or a view control.</span></span> <span data-ttu-id="2522f-104">定义自定义控件视图时，将使用此元素。</span><span class="sxs-lookup"><span data-stu-id="2522f-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="2522f-105">配置元素 (格式) ViewDefinitions 元素 (格式) 视图元素 (格式) 用于视图 (格式的 CustomEntries 元素) CustomEntry 的 CustomControl 的元素 (CustomEntries 的 CustomItem 的 CustomEntry 元素) ExpressionBinding 元素 for CustomItem 的 CustomControlName 元素 (CustomItem) 格式的元素 (</span><span class="sxs-lookup"><span data-stu-id="2522f-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) CustomItem Element for CustomEntry for View (Format) ExpressionBinding Element for CustomItem (Format) CustomControlName Element for Expression Binding for CustomItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="2522f-106">语法</span><span class="sxs-lookup"><span data-stu-id="2522f-106">Syntax</span></span>

```xml
<CustomControlName>NameofCustomControl</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2522f-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2522f-107">Attributes and Elements</span></span>

<span data-ttu-id="2522f-108">以下各节描述了元素的属性、子元素和父元素 `CustomControlName` 。</span><span class="sxs-lookup"><span data-stu-id="2522f-108">The following sections describe attributes, child elements, and the parent element of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="2522f-109">特性</span><span class="sxs-lookup"><span data-stu-id="2522f-109">Attributes</span></span>

<span data-ttu-id="2522f-110">无。</span><span class="sxs-lookup"><span data-stu-id="2522f-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="2522f-111">子元素</span><span class="sxs-lookup"><span data-stu-id="2522f-111">Child Elements</span></span>

<span data-ttu-id="2522f-112">无。</span><span class="sxs-lookup"><span data-stu-id="2522f-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2522f-113">父元素</span><span class="sxs-lookup"><span data-stu-id="2522f-113">Parent Elements</span></span>

|<span data-ttu-id="2522f-114">元素</span><span class="sxs-lookup"><span data-stu-id="2522f-114">Element</span></span>|<span data-ttu-id="2522f-115">描述</span><span class="sxs-lookup"><span data-stu-id="2522f-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2522f-116">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="2522f-116">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)|<span data-ttu-id="2522f-117">定义控件显示的数据。</span><span class="sxs-lookup"><span data-stu-id="2522f-117">Defines the data that is displayed by the control.</span></span>|

## <a name="text-value"></a><span data-ttu-id="2522f-118">文本值</span><span class="sxs-lookup"><span data-stu-id="2522f-118">Text Value</span></span>

<span data-ttu-id="2522f-119">指定控件的名称。</span><span class="sxs-lookup"><span data-stu-id="2522f-119">Specify the name of the control.</span></span>

## <a name="remarks"></a><span data-ttu-id="2522f-120">备注</span><span class="sxs-lookup"><span data-stu-id="2522f-120">Remarks</span></span>

<span data-ttu-id="2522f-121">您可以创建可供格式设置文件的所有视图使用的公共控件，并可以创建可供特定视图使用的视图控件。</span><span class="sxs-lookup"><span data-stu-id="2522f-121">You can create common controls that can be used by all the views of a formatting file and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="2522f-122">以下元素指定这些控件的名称。</span><span class="sxs-lookup"><span data-stu-id="2522f-122">The names of these controls are specified by the following elements.</span></span>

- [<span data-ttu-id="2522f-123">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="2522f-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="2522f-124">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="2522f-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="2522f-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2522f-125">See Also</span></span>

[<span data-ttu-id="2522f-126">Name Element for Control for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="2522f-126">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="2522f-127">Name Element for Control for Controls for View (Format)</span><span class="sxs-lookup"><span data-stu-id="2522f-127">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="2522f-128">CustomItem 的 ExpressionBinding 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="2522f-128">ExpressionBinding Element for CustomItem (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-configuration-format.md)

[<span data-ttu-id="2522f-129">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="2522f-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
