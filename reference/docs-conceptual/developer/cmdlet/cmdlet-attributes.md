---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 属性
description: Cmdlet 属性
ms.openlocfilehash: 6a106f33cb34c6c33b88a981815543bc9af4e4ba
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653521"
---
# <a name="cmdlet-attributes"></a>Cmdlet 属性

Windows PowerShell 定义多个属性，可用于向 cmdlet 添加常见功能，而无需在自己的代码中实现该功能。 这包括 Cmdlet 属性，该属性用于将 Microsoft .NET 框架类标识为 cmdlet 类、指定 cmdlet 返回的 .NET Framework 类型的 OutputType 属性、用于将公共属性标识为 cmdlet 参数的参数属性等。

## <a name="in-this-section"></a>本节内容

[Cmdlet 代码中的属性](./attributes-in-cmdlet-code.md) 介绍使用 cmdlet 代码中的属性的好处。

[特性类型](./attribute-types.md) 描述可以修饰 cmdlet 类的不同属性。

[Alias 特性声明](./alias-attribute-declaration.md) 描述如何为 cmdlet 参数名称定义别名。

[Cmdlet 特性声明](./cmdlet-attribute-declaration.md) 描述如何将 .NET Framework 类定义为 cmdlet。

[Credential 特性声明](./credential-attribute-declaration.md) 介绍如何添加对将字符串输入转换为 [system.web](/dotnet/api/System.Management.Automation.PSCredential) 对象的支持。

[OutputType 特性声明](./outputtype-attribute-declaration.md) 描述如何指定 cmdlet 返回的 .NET Framework 类型。

[参数属性声明](./parameter-attribute-declaration.md) 描述如何定义 cmdlet 的参数。

[ValidateCount 特性声明](./validatecount-attribute-declaration.md) 描述如何定义参数允许的参数数量。

[ValidateLength 特性声明](./validatelength-attribute-declaration.md) 描述如何定义参数参数的长度 (以字符) 。

[ValidatePattern 特性声明](./validatepattern-attribute-declaration.md) 描述如何定义参数参数的有效模式。

[ValidateRange 特性声明](./validaterange-attribute-declaration.md) 描述如何定义参数参数的有效范围。

[ValidateSet 特性声明](./validateset-attribute-declaration.md) 描述如何定义参数参数的可能值。

## <a name="reference"></a>参考

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
