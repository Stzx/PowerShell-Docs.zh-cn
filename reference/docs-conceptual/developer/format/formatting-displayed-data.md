---
title: 设置显示的数据的格式 |Microsoft Docs
ms.date: 09/12/2016
ms.openlocfilehash: 97d23b3079b2779e518b6b6d2f2ac0c5e9d1f3a3
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781505"
---
# <a name="formatting-displayed-data"></a><span data-ttu-id="08ebf-102">设置显示数据的格式</span><span class="sxs-lookup"><span data-stu-id="08ebf-102">Formatting Displayed Data</span></span>

<span data-ttu-id="08ebf-103">您可以指定如何显示列表、表或宽视图中的各个数据点。</span><span class="sxs-lookup"><span data-stu-id="08ebf-103">You can specify how the individual data points in your List, Table, or Wide view are displayed.</span></span> <span data-ttu-id="08ebf-104">在 `FormatString` 定义视图的项时可以使用元素，也可以使用 `ScriptBlock` 元素对 `FormatString` 数据调用方法。</span><span class="sxs-lookup"><span data-stu-id="08ebf-104">You can use the `FormatString` element when defining the items of your view, or you can use the `ScriptBlock` element to call the `FormatString` method on the data.</span></span>

## <a name="using-the-formatstring-element"></a><span data-ttu-id="08ebf-105">使用格式字符串元素</span><span class="sxs-lookup"><span data-stu-id="08ebf-105">Using the FormatString Element</span></span>

<span data-ttu-id="08ebf-106">在下面的示例中， `TotalProcessorTime` 使用 "格式字符串" 元素对 " [system.object](/dotnet/api/System.Diagnostics.Process) " 对象的属性值进行格式化。</span><span class="sxs-lookup"><span data-stu-id="08ebf-106">In the following example the value of the `TotalProcessorTime` property of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object is formatted using the FormatString element.</span></span> <span data-ttu-id="08ebf-107">`TotalProcessorTime`属性</span><span class="sxs-lookup"><span data-stu-id="08ebf-107">the `TotalProcessorTime` property</span></span>

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
