---
title: ValidatePattern 特性声明 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- attributes, ValidatePattern
- ValidatePattern attribute, described
- ValidatePattern attribute
ms.openlocfilehash: 713fa7a46a8eeefdbfd679a5e8436285fac085f8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787795"
---
# <a name="validatepattern-attribute-declaration"></a>ValidatePattern 属性声明

ValidatePattern 属性指定用于验证 cmdlet 参数的参数的正则表达式模式。 此属性也可由 Windows PowerShell 函数使用。

在 cmdlet 中调用 ValidatePattern 时，Windows PowerShell 运行时将 cmdlet 参数的参数转换为字符串，然后将该字符串与 ValidatePattern 特性提供的模式进行比较。 仅当参数的转换字符串表示形式和提供的模式匹配时，才运行 cmdlet。 如果二者不匹配，则 Windows PowerShell 运行时将引发错误。

## <a name="syntax"></a>语法

```csharp
[ValidatePattern(string regexString)]
[ValidatePattern(string regexString, Named Parameters)]
```

#### <a name="parameters"></a>parameters

`RegexString`需要[ () 。](/dotnet/api/System.String) 指定用于验证参数参数的正则表达式。

选项 ([system.text.regularexpressions.regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)) 可选的命名参数。 指定指定正则表达式选项的[system.text.regularexpressions. system.text.regularexpressions.regexoptions](/dotnet/api/System.Text.RegularExpressions.RegexOptions)标志的按位组合。

## <a name="remarks"></a>备注

- 此属性仅可用于每个参数一次。

- 可以使用特性的 `Option` 参数进一步定义模式。 例如，可以使模式区分大小写。

- 如果将此特性应用于集合，则集合中的每个元素都必须与模式匹配。

- ValidatePattern 特性是由[Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)类定义的。

## <a name="see-also"></a>另请参阅

[System.web. Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
