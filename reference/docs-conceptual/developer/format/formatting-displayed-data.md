---
ms.date: 09/12/2016
ms.topic: reference
title: 设置显示数据的格式
description: 设置显示数据的格式
ms.openlocfilehash: 40f6b3b4fa36062ee0bad3f197ad159f571445c8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667855"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="2c03e-103">设置显示数据的格式</span><span class="sxs-lookup"><span data-stu-id="2c03e-103">Formatting Displayed Data</span></span>

<span data-ttu-id="2c03e-104">您可以指定如何显示列表、表或宽视图中的各个数据点。</span><span class="sxs-lookup"><span data-stu-id="2c03e-104">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="2c03e-105">在 `FormatString` 定义视图的项时可以使用元素，也可以使用 `ScriptBlock` 元素对 `FormatString` 数据调用方法。</span><span class="sxs-lookup"><span data-stu-id="2c03e-105">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="2c03e-106">使用格式字符串元素</span><span class="sxs-lookup"><span data-stu-id="2c03e-106">Using the FormatString Element</span></span>

<span data-ttu-id="2c03e-107">在下面的示例中， `TotalProcessorTime` 使用 "格式字符串" 元素对 " [system.object](/dotnet/api/System.Diagnostics.Process) " 对象的属性值进行格式化。</span><span class="sxs-lookup"><span data-stu-id="2c03e-107">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="2c03e-108">`TotalProcessorTime`属性</span><span class="sxs-lookup"><span data-stu-id="2c03e-108">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
