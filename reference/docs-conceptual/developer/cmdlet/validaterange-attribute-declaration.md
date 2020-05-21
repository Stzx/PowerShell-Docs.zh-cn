---
title: ValidateRange 特性声明 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.assetid: 1f8066e6-e5d3-4f4e-8948-a90af5dace82
caps.latest.revision: 11
ms.openlocfilehash: 560fa105ac3f93ae6334df0112f5290dfa20576c
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692014"
---
# <a name="validaterange-attribute-declaration"></a>ValidateRange 属性声明

ValidateRange 属性指定 cmdlet 参数参数的最小值和最大值（范围）。 此属性也可由 Windows PowerShell 函数使用。

## <a name="syntax"></a>语法

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a>参数

`MinRange`（[System.string）。](/dotnet/api/system.object) 指定允许的最小值。

`MaxRange`（[System.string）。](/dotnet/api/system.object) 指定允许的最大值。

## <a name="remarks"></a>备注

- 当参数的值大于参数的值时，Windows PowerShell 运行时将引发构造错误 `MinRange` `MaxRange` 。

- Windows PowerShell 运行时在以下条件下引发验证错误：

  - 当参数的值小于 `MinRange` 或大于限制时 `MaxRange` 。

  - 参数的类型与 `MinRange` 和 `MaxRange` 参数不同。

- ValidateRange 特性是由[Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)类定义的。

## <a name="see-also"></a>另请参阅

[System.web. Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
