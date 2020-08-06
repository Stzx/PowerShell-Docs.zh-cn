---
title: 属性参数 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0ded22dcda2b4eb957834ec092466767a4121f0e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781828"
---
# <a name="property-parameters"></a>属性参数

下表列出了属性参数的建议名称和功能。

|参数|功能|
|---|---|
|**Count**<br>数据类型： Int32|实现此参数，以便用户可以指定要处理的对象数。|
|**说明**<br>数据类型：字符串|实现此参数，以便用户可以为资源指定说明。|
|**From**<br>数据类型：字符串|实现此参数，以便用户可以指定要从中获取信息的引用对象。|
|Id<br>数据类型：资源相关|实现此参数，以便用户可以指定资源的标识符。|
|**输入**<br>数据类型：字符串|实现此参数，以便用户可以指定输入文件规范。|
|**位置**<br>数据类型：字符串|实现此参数，以便用户可以指定资源的位置。|
|**LogName**<br>数据类型：字符串|实现此参数，以便用户可以指定要处理或使用的日志文件的名称。|
|名称<br>数据类型：字符串|实现此参数，以便用户可以指定资源的名称。|
|**输出**<br>数据类型：字符串|实现此参数，以便用户可以指定输出文件。|
|**所有者**<br>数据类型：字符串|实现此参数，以便用户可以指定资源所有者的名称。|
|**Property**<br>数据类型：字符串|实现此参数，以便用户可以指定要使用的属性的名称或名称。|
|**Reason**<br>数据类型：字符串|实现此参数，以便用户可以指定调用此 cmdlet 的原因。|
|**Regex**<br>数据类型： SwitchParameter|实现此参数，以便在指定参数时使用正则表达式。 如果指定此参数，则不解析通配符。|
|**Speed**<br>数据类型： Int32|实现此参数，以便用户可以指定波特率。 用户将此参数设置为资源的速度。|
|**State**<br>数据类型：关键字数组|实现此参数，以便用户可以指定状态的名称，如 KEYDOWN。|
|**值**<br>数据类型：对象|实现此参数，以便用户可以指定要提供给 cmdlet 的值。|
|**版本**<br>数据类型：字符串|实现此参数，以便用户可以指定属性的版本。|

## <a name="see-also"></a>另请参阅

[Cmdlet 参数](./cmdlet-parameters.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
