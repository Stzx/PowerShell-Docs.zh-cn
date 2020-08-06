---
title: ValidateRange 特性声明 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.openlocfilehash: 9aeaa6f03c170389ff61a058b505dbcf74df6958
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787778"
---
# <a name="validaterange-attribute-declaration"></a>ValidateRange 属性声明

ValidateRange 属性指定 cmdlet 参数参数 (范围) 的最小值和最大值。 此属性也可由 Windows PowerShell 函数使用。

## <a name="syntax"></a>语法

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>parameters

`MinRange`需要[ () 。](/dotnet/api/system.object) 指定允许的最小值。

`MaxRange`需要[ () 。](/dotnet/api/system.object) 指定允许的最大值。

## <a name="remarks"></a>备注

- 当参数的值大于参数的值时，Windows PowerShell 运行时将引发构造错误 `MinRange` `MaxRange` 。

- Windows PowerShell 运行时在以下条件下引发验证错误：

  - 当参数的值小于 `MinRange` 或大于限制时 `MaxRange` 。

  - 参数的类型与 `MinRange` 和 `MaxRange` 参数不同。

- ValidateRange 特性是由[Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)类定义的。

## <a name="see-also"></a>另请参阅

[System.web. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
