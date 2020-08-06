---
title: 配置 (格式) 的控件元素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 44b9db0d3523e5e9086da9911882b258a2a54ca6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783783"
---
# <a name="controls-element-for-configuration-format"></a><span data-ttu-id="8b29b-102">Controls Element for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="8b29b-102">Controls Element for Configuration (Format)</span></span>

<span data-ttu-id="8b29b-103">定义可供格式设置文件的所有视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="8b29b-103">Defines the common controls that can be used by all views of the formatting file.</span></span>

<span data-ttu-id="8b29b-104">配置元素 (格式) 配置 (格式的元素) </span><span class="sxs-lookup"><span data-stu-id="8b29b-104">Configuration Element (Format) Controls Element of Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8b29b-105">语法</span><span class="sxs-lookup"><span data-stu-id="8b29b-105">Syntax</span></span>

```xml
<Controls>
  <Control>...</Control>
</Controls>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8b29b-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8b29b-106">Attributes and Elements</span></span>

<span data-ttu-id="8b29b-107">以下各节描述了元素的属性、子元素和父元素 `Controls` 。</span><span class="sxs-lookup"><span data-stu-id="8b29b-107">The following sections describe the attributes, child elements, and the parent element of the `Controls` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="8b29b-108">特性</span><span class="sxs-lookup"><span data-stu-id="8b29b-108">Attributes</span></span>

<span data-ttu-id="8b29b-109">无。</span><span class="sxs-lookup"><span data-stu-id="8b29b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8b29b-110">子元素</span><span class="sxs-lookup"><span data-stu-id="8b29b-110">Child Elements</span></span>

|<span data-ttu-id="8b29b-111">元素</span><span class="sxs-lookup"><span data-stu-id="8b29b-111">Element</span></span>|<span data-ttu-id="8b29b-112">描述</span><span class="sxs-lookup"><span data-stu-id="8b29b-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8b29b-113">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="8b29b-113">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)|<span data-ttu-id="8b29b-114">必需的元素。</span><span class="sxs-lookup"><span data-stu-id="8b29b-114">Required element.</span></span><br /><br /> <span data-ttu-id="8b29b-115">定义可供格式设置文件的所有视图使用的公共控件。</span><span class="sxs-lookup"><span data-stu-id="8b29b-115">Defines a common control that can be used by all views of the formatting file.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8b29b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="8b29b-116">Parent Elements</span></span>

|<span data-ttu-id="8b29b-117">元素</span><span class="sxs-lookup"><span data-stu-id="8b29b-117">Element</span></span>|<span data-ttu-id="8b29b-118">描述</span><span class="sxs-lookup"><span data-stu-id="8b29b-118">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8b29b-119">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8b29b-119">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="8b29b-120">表示格式设置文件的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="8b29b-120">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8b29b-121">备注</span><span class="sxs-lookup"><span data-stu-id="8b29b-121">Remarks</span></span>

<span data-ttu-id="8b29b-122">您可以创建任意数量的公共控件。</span><span class="sxs-lookup"><span data-stu-id="8b29b-122">You can create any number of common controls.</span></span> <span data-ttu-id="8b29b-123">对于每个控件，您必须指定用于引用控件和控件组件的名称。</span><span class="sxs-lookup"><span data-stu-id="8b29b-123">For each control, you must specify the name that is used to reference the control and the components of the control.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b29b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b29b-124">See Also</span></span>

[<span data-ttu-id="8b29b-125">Configuration Element (Format)</span><span class="sxs-lookup"><span data-stu-id="8b29b-125">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="8b29b-126">Control Element for Controls for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="8b29b-126">Control Element for Controls for Configuration (Format)</span></span>](./control-element-for-controls-for-configuration-format.md)

[<span data-ttu-id="8b29b-127">编写 PowerShell 格式设置文件</span><span class="sxs-lookup"><span data-stu-id="8b29b-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
