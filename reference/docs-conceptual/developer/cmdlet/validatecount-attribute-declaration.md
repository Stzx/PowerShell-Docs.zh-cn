---
title: ValidateCount 特性声明 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes, ValidateCount
- ValidateCount attribute, described
- ValidateCount attribute
ms.assetid: 516af1ef-2c2e-408d-84bc-865f5bccf761
caps.latest.revision: 11
ms.openlocfilehash: 3cae95fab30a4abe4e544ed5cb7dadc9f4debf02
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692369"
---
# <a name="validatecount-attribute-declaration"></a>ValidateCount 属性声明

ValidateCount 属性指定 cmdlet 参数允许的最小和最大参数数量。

## <a name="syntax"></a>语法

```csharp
[ValidateCount(int minLength, int maxlength)]
```

#### <a name="parameters"></a>参数

`MinLength`必需[System.Int32][]。 指定参数的最小数目。

`MaxLength`必需[System.Int32][]。 指定参数的最大数目。

## <a name="remarks"></a>备注

- 有关如何声明此属性的详细信息，请参阅[如何验证参数计数][]。

- 如果未调用此属性，则对应的 cmdlet 参数可以有任意数量的参数。

- Windows PowerShell 运行时在以下条件下引发错误：

  - `MinLength`和 `MaxLength` 特性参数的类型不是[system.object][]。

  - Attribute 参数的值 `MaxLength` 小于 `MinLength` attribute 参数的值。

- ValidateCount 特性是由[ValidateCountAttribute][]类定义的。

## <a name="see-also"></a>另请参阅

[System.web. ValidateCountAttribute][]

[如何验证参数计数][]

[编写 Windows PowerShell Cmdlet][]

[如何验证参数计数]: how-to-validate-an-argument-count.md
[编写 Windows PowerShell Cmdlet]: writing-a-windows-powershell-cmdlet.md

[System.Int32]: /dotnet/api/System.Int32
[System.web. ValidateCountAttribute]: /dotnet/api/System.Management.Automation.ValidateCountAttribute
