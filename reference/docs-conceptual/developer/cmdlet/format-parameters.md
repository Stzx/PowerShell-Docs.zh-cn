---
title: 格式参数 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8e031f62aa8bcb0e9d5b900b2eace7187b1f3dd
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784276"
---
# <a name="format-parameters"></a>格式参数

下表列出了用于格式化或生成数据的参数的建议名称和功能。

|参数|功能|
|---|---|
|**方式**<br>数据类型：关键字|实现此参数以指定 cmdlet 输出格式。 例如，可能的值可以是文本或脚本。|
|**二进制**<br>数据类型： SwitchParameter|实现此参数以指示该 cmdlet 处理二进制值。|
|**编码**<br>数据类型：关键字|实现此参数可指定支持的编码类型。 例如，可能的值可能是 ASCII、UTF8、Unicode、UTF7、BigEndianUnicode、Byte 和 String。|
|**换**<br>数据类型： SwitchParameter|实现此参数，以便在指定参数时支持换行字符。|
|**ShortName**<br>数据类型： SwitchParameter|实现此参数以便在指定参数时支持短名称。|
|Width<br>数据类型： Int32|实现此参数，以便用户可以指定输出设备的宽度。|
|**包装**<br>数据类型： SwitchParameter|实现此参数以便在指定参数时支持文本换行。|
## <a name="see-also"></a>另请参阅

[Cmdlet 参数](./cmdlet-parameters.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
