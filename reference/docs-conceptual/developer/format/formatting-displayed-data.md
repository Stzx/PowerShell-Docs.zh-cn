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
# <a name="formatting-displayed-data"></a>设置显示数据的格式

您可以指定如何显示列表、表或宽视图中的各个数据点。 在 `FormatString` 定义视图的项时可以使用元素，也可以使用 `ScriptBlock` 元素对 `FormatString` 数据调用方法。

## <a name="using-the-formatstring-element"></a>使用格式字符串元素

在下面的示例中， `TotalProcessorTime` 使用 "格式字符串" 元素对 " [system.object](/dotnet/api/System.Diagnostics.Process) " 对象的属性值进行格式化。 `TotalProcessorTime`属性

```
<TableColumnItem>
  <PropertyName>TotalProcessorTime</PropertyName>
  <FormatString>{0:MMM}{0:dd}{0:HH}:{0:mm}</FormatString>
</TableColumnItem>
```
