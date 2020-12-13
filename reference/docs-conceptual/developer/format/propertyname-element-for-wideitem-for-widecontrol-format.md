---
ms.date: 09/13/2016
ms.topic: reference
title: PropertyName Element for WideItem for WideControl (Format)
description: PropertyName Element for WideItem for WideControl (Format)
ms.openlocfilehash: 1d4d5eaf7708dfbd7997122fac156a36487538ea
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665611"
---
# <a name="propertyname-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="786d8-103">PropertyName Element for WideItem for WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="786d8-103">PropertyName Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="786d8-104">指定对象的属性，其值显示在宽视图中。</span><span class="sxs-lookup"><span data-stu-id="786d8-104">Specifies the property of the object whose value is displayed in the wide view.</span></span>

<span data-ttu-id="786d8-105">配置元素 (格式) ViewDefinitions 元素 (格式) View 元素 (格式) WideControl 元素 (格式) WideEntries 元素 (格式) WideEntry 元素 (格式) WideItem 元素 (格式) WideItem (格式) </span><span class="sxs-lookup"><span data-stu-id="786d8-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) PropertyName Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="786d8-106">语法</span><span class="sxs-lookup"><span data-stu-id="786d8-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="786d8-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="786d8-107">Attributes and Elements</span></span>

<span data-ttu-id="786d8-108">以下各节描述了元素的属性、子元素和父元素 `PropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="786d8-108">The following sections describe the attributes, child elements, and parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="786d8-109">特性</span><span class="sxs-lookup"><span data-stu-id="786d8-109">Attributes</span></span>

<span data-ttu-id="786d8-110">无。</span><span class="sxs-lookup"><span data-stu-id="786d8-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="786d8-111">子元素</span><span class="sxs-lookup"><span data-stu-id="786d8-111">Child Elements</span></span>

<span data-ttu-id="786d8-112">无。</span><span class="sxs-lookup"><span data-stu-id="786d8-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="786d8-113">父元素</span><span class="sxs-lookup"><span data-stu-id="786d8-113">Parent Elements</span></span>

|<span data-ttu-id="786d8-114">元素</span><span class="sxs-lookup"><span data-stu-id="786d8-114">Element</span></span>|<span data-ttu-id="786d8-115">描述</span><span class="sxs-lookup"><span data-stu-id="786d8-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="786d8-116">WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="786d8-116">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="786d8-117">定义其值在宽视图中显示的属性或脚本。</span><span class="sxs-lookup"><span data-stu-id="786d8-117">Defines the property or script whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="786d8-118">文本值</span><span class="sxs-lookup"><span data-stu-id="786d8-118">Text Value</span></span>

<span data-ttu-id="786d8-119">指定显示其值的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="786d8-119">Specify the name of the property whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="786d8-120">备注</span><span class="sxs-lookup"><span data-stu-id="786d8-120">Remarks</span></span>

<span data-ttu-id="786d8-121">有关宽视图组件的详细信息，请参阅 [创建宽视图](./creating-a-wide-view.md)。</span><span class="sxs-lookup"><span data-stu-id="786d8-121">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="786d8-122">示例</span><span class="sxs-lookup"><span data-stu-id="786d8-122">Example</span></span>

<span data-ttu-id="786d8-123">此示例显示了一个宽视图，其中 [显示了 ProcessName 对象的](/dotnet/api/System.Diagnostics.Process) "" 属性的值。</span><span class="sxs-lookup"><span data-stu-id="786d8-123">This example shows a wide view that displays the value of the ProcessName property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
View>
  <Name>process</Name>
  <ViewSelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </ViewSelectedBy>
  <WideControl>
    <WideEntries>
      <WideEntry>
        <WideItem>
          <PropertyName>ProcessName</PropertyName>
        </WideItem>
      </WideEntry>
    </WideEntries>
  </WideControl>
</View>

```

## <a name="see-also"></a><span data-ttu-id="786d8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="786d8-124">See Also</span></span>

[<span data-ttu-id="786d8-125">WideItem 元素 (格式) </span><span class="sxs-lookup"><span data-stu-id="786d8-125">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="786d8-126">创建宽视图</span><span class="sxs-lookup"><span data-stu-id="786d8-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="786d8-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="786d8-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
