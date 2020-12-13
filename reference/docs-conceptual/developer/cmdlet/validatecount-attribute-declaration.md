---
ms.date: 09/13/2016
ms.topic: reference
title: ValidateCount 属性声明
description: ValidateCount 属性声明
ms.openlocfilehash: 6acdd02a10ecc1bc2be0e6be88cf2f42a3673eb8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646267"
---
# <a name="validatecount-attribute-declaration"></a>ValidateCount 属性声明

ValidateCount 属性指定 cmdlet 参数允许的最小和最大参数数量。

## <a name="syntax"></a>语法

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>parameters

`MinLength`需要[ () 。][] 指定参数的最小数目。

`MaxLength`需要[ () 。][] 指定参数的最大数目。

## <a name="remarks"></a>备注

- 有关如何声明此属性的详细信息，请参阅 [如何验证参数计数][]。

- 如果未调用此属性，则对应的 cmdlet 参数可以有任意数量的参数。

- Windows PowerShell 运行时在以下条件下引发错误：

  - `MinLength`和 `MaxLength` 特性参数的类型不是[system.object][]。

  - Attribute 参数的值 `MaxLength` 小于 `MinLength` attribute 参数的值。

- ValidateCount 特性是由 [ValidateCountAttribute][] 类定义的。

## <a name="see-also"></a>另请参阅

[System.web. ValidateCountAttribute][]

[如何验证参数计数][]

[编写 Windows PowerShell Cmdlet][]

[如何验证参数计数]: how-to-validate-an-argument-count.md
[编写 Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.web. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
