---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateLength 属性声明
description: ValidateLength 属性声明
ms.openlocfilehash: b35fe24c6fc44aaca6a39d819d6e3fc2d8a2cade
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646186"
---
# <a name="validatelength-attribute-declaration"></a>ValidateLength 属性声明

ValidateLength 属性指定 cmdlet 参数参数的最小和最大字符数。 此属性也可由 Windows PowerShell 函数使用。

## <a name="syntax"></a>语法

```csharp
[ValidateLength(int minLength, int maxlength)]
```

#### <a name="parameters"></a>parameters

`MinLength`需要[ () 。](/dotnet/api/System.Int32) 指定允许的最小字符数。

`MaxLength`需要[ () 。](/dotnet/api/System.Int32) 指定允许的最大字符数。

## <a name="remarks"></a>备注

- 有关如何声明此属性的详细信息，请参阅 [如何声明输入验证规则](./how-to-validate-parameter-input.md)。

- 如果未使用此属性，则相应的参数参数可以为任意长度。

- Windows PowerShell 运行时在以下条件下引发错误：

  - 当 attribute 参数的值 `MaxLength` 小于 attribute 参数的值时 `MinLength` 。

  - 如果 `MaxLength` 特性参数设置为0，则为。

  - 如果参数不是字符串，则为。

- ValidateLength 特性是由 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute) 类定义的。

## <a name="see-also"></a>另请参阅

[System.web. Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
