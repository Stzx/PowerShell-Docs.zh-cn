---
title: 资源参数 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e618951d57ff1cf303b38f0278858144df31afaf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786520"
---
# <a name="resource-parameters"></a>资源参数

下表列出了资源参数的建议名称和功能。 对于这些参数，资源可以是包含 cmdlet 类的程序集，也可以是运行 cmdlet 的主机应用程序。

|参数|功能|
|---|---|
|**应用程序**<br>数据类型：字符串|实现此参数，以便用户可以指定应用程序。|
|**件**<br>数据类型：字符串|实现此参数，以便用户可以指定程序集。|
|**特性**<br>数据类型：字符串|实现此参数，以便用户可以指定属性。|
|**类**<br>数据类型：字符串|实现此参数，以便用户可以指定 Microsoft .NET 框架类。|
|**Cluster**<br>数据类型：字符串|实现此参数，以便用户可以指定群集。|
|**区域性**<br>数据类型：字符串|实现此参数，以便用户可以指定要在其中运行 cmdlet 的区域性。|
|**Domain**<br>数据类型：字符串|实现此参数，以便用户可以指定域名。|
|**驱动器**<br>数据类型：字符串|实现此参数，以便用户可以指定驱动器名称。|
|**事件**<br>数据类型：字符串|实现此参数，以便用户可以指定事件名称。|
|**Interface**<br>数据类型：字符串|实现此参数，以便用户可以指定网络接口名称。|
|**IpAddress**<br>数据类型：字符串|实现此参数，以便用户可以指定 IP 地址。|
|**作业**<br>数据类型：字符串|实现此参数，以便用户可以指定作业。|
|**LiteralPath**<br>数据类型：字符串|实现此参数，以便在不支持通配符时，用户可以指定资源的路径。 支持通配符时 (使用**Path**参数。 ) |
|**Mac**<br>数据类型：字符串|实现此参数，以便用户可以 (MAC) 地址指定媒体访问控制器。|
|**ParentId**<br>数据类型：字符串|实现此参数，以便用户可以指定父标识符。|
|**路径**<br>数据类型： String，String []|实现此参数，以便用户可以在支持通配符时指示资源的路径。 当不支持通配符时， (使用**LiteralPath**参数。 ) 建议你开发此参数以支持 `provider:path` 提供程序使用的完整语法。 我们还建议你对其进行开发，使其适用于尽可能多的提供程序。|
|**Port**<br>数据类型： Integer、String|实现此参数，以便用户可以为网络指定整数值或为其他类型的端口指定一个字符串值（如 "biztalk"）。|
|**打印机**<br>数据类型： Integer、String|实现此参数，以便用户可以指定要使用的 cmdlet 的打印机。|
|**大小**<br>数据类型： Int32|实现此参数，以便用户可以指定大小。|
|**TID**<br>数据类型：字符串|实现此参数，以便用户可以为 cmdlet 指定 (TID) 的事务标识符。|
|**Type**<br>数据类型：字符串|实现此参数，以便用户可以指定要在其上操作的资源的类型。|
|**URL**<br>数据类型：字符串|实现此参数，以便用户可以 (URL) 指定统一资源定位器。|
|**用户**<br>数据类型：字符串|实现此参数，以便用户可以指定其名称或其他用户的名称。|

## <a name="see-also"></a>另请参阅

[Cmdlet 参数](./cmdlet-parameters.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
