---
title: 设置显示的数据的格式 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38971643-2a3d-4f5b-a1fa-6334c162b8ed
caps.latest.revision: 4
ms.openlocfilehash: 9f3a3176ae16ac7c014cadce6b4e856f9bd3b5da
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560383"
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
