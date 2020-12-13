---
ms.date: 09/13/2016
ms.topic: reference
title: OutputType 属性声明
description: OutputType 属性声明
ms.openlocfilehash: b5e33346e9ac29c13323781d62daffab892573a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646457"
---
# <a name="outputtype-attribute-declaration"></a>OutputType 属性声明

`OutputType`属性标识由 cmdlet、函数或脚本返回的 .NET Framework 类型。

## <a name="syntax"></a>语法

```csharp
[OutputType(params string[] type)]
[OutputType(params Type[] type)]
[OutputType(params string[] type, Named Parameters...)]
[OutputType(params Type[] type, Named Parameters...)]
```

#### <a name="parameters"></a>parameters

需要键入 (`string[]` 或 `Type[]`) 。 指定由 cmdlet 函数或脚本返回的类型。

ParameterSetName (string [] ) 可选的。 指定返回参数中指定的类型的参数集 `type` 。

providerCmdlet 可选。 指定提供程序 cmdlet，该 cmdlet 返回参数中指定的类型 `type` 。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
