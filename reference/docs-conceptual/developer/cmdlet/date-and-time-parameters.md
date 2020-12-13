---
ms.date: 09/13/2016
ms.topic: reference
title: 日期和时间参数
description: 日期和时间参数
ms.openlocfilehash: 2f73d16ca8261ebc4ca8d2c18aff4176d7d7314c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653190"
---
# <a name="date-and-time-parameters"></a>日期和时间参数

下表列出了用于处理日期和时间信息的参数的建议名称和功能。 日期和时间参数通常用于在创建或访问某些内容时进行记录。

|参数|功能|
|---|---|
|**存取**<br>数据类型： SwitchParameter|实现此参数以便在指定时，该 cmdlet 将对基于 **前后****参数指定** 的日期和时间访问的资源进行操作。 如果指定此参数，则必须指定 **创建** 的参数和 **修改后** 的参数。|
|**之后**<br>数据类型： DateTime|实现此参数以指定使用 cmdlet 的日期和时间。 若要使 **After** 参数正常工作，cmdlet 还必须有一个已 **访问** 的、 **创建** 的或 **修改** 的参数。 而且，调用 cmdlet 时，必须将该参数设置为 **true** 。|
|**之前**<br>数据类型： DateTime|实现此参数以指定使用 cmdlet 之前的日期和时间。 若要使 **Before** 参数正常工作，cmdlet 还必须有一个已 **访问** 的、 **创建** 的或 **修改** 的参数。 而且，调用 cmdlet 时，必须将该参数设置为 **true** 。|
|**创建时间**<br>数据类型： SwitchParameter|实现此参数以便在指定时，该 cmdlet 将对基于 **前后****参数指定** 的日期和时间创建的资源进行操作。 如果指定此参数，则不能指定 **访问** 的参数和 **修改后** 的参数。|
|**Exact**<br>数据类型： SwitchParameter|实现此参数，以便在指定资源时，资源项必须与资源名称完全匹配。 如果未指定参数，则资源字词和名称不需要完全匹配。|
|**修改时间**<br>数据类型： DateTime|实现此参数以便在指定时，该 cmdlet 将对基于 **前后****参数指定** 的日期和时间已更改的资源进行操作。 如果指定此参数，则不得指定 **访问** 的和 **创建** 的参数。|
## <a name="see-also"></a>另请参阅

[Cmdlet 参数](./cmdlet-parameters.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
