---
title: 属性类型 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 96fdd38ba10eb748ab0762f0c910463dd472494d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782372"
---
# <a name="attribute-types"></a>属性类型

Cmdlet 属性可以按功能分组。
以下各节介绍了可用的属性，并说明了在调用特性时运行时的作用。

## <a name="cmdlet-attributes"></a>Cmdlet 属性

### <a name="cmdlet"></a>Cmdlet

将 .NET Framework 类标识为 cmdlet。
这是必需的基本属性。
有关详细信息，请参阅[Cmdlet 特性声明](./cmdlet-attribute-declaration.md)。

## <a name="parameter-attributes"></a>参数属性

### <a name="parameter"></a>参数

将 cmdlet 类中的公共属性标识为 cmdlet 参数。
有关详细信息，请参阅[参数属性声明](./parameter-attribute-declaration.md)。

### <a name="alias"></a>Alias

指定参数的一个或多个别名。
有关详细信息，请参阅[Alias 特性声明](./alias-attribute-declaration.md)。

## <a name="argument-validation-attributes"></a>参数验证特性

### <a name="validatecount"></a>ValidateCount

指定 cmdlet 参数允许的最小和最大参数数量。
有关详细信息，请参阅[ValidateCount 特性声明](./validatecount-attribute-declaration.md)。

### <a name="validatelength"></a>ValidateLength

指定 cmdlet 参数参数的最小和最大字符数。
有关详细信息，请参阅[ValidateLength 特性声明](./validatelength-attribute-declaration.md)。

### <a name="validatepattern"></a>ValidatePattern

指定 cmdlet 参数参数必须匹配的正则表达式模式。
有关详细信息，请参阅[ValidatePattern 特性声明](./validatepattern-attribute-declaration.md)。

### <a name="validaterange"></a>ValidateRange

指定 cmdlet 参数参数的最小值和最大值。
有关详细信息，请参阅[ValidateRange 特性声明](./validaterange-attribute-declaration.md)。

### <a name="validateset"></a>ValidateSet

为 cmdlet 参数参数指定一组有效值。
有关详细信息，请参阅[ValidateSet 特性声明](./validateset-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
