---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 代码中的属性
description: Cmdlet 代码中的属性
ms.openlocfilehash: 296bb8bcb06ef660e97dc792d1ecf596cc7c2930
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653656"
---
# <a name="attributes-in-cmdlet-code"></a>Cmdlet 代码中的属性

若要使用 Windows PowerShell 提供的通用功能，请使用属性修饰 cmdlet 代码中定义的类和公共属性。 例如，下面的类定义使用 Cmdlet 特性来标识实现了 **get-help** Cmdlet 的 Microsoft .NET 框架类。  (此 cmdlet 用作本文档中的示例，类似于 `Get-Process` Windows PowerShell 提供的 cmdlet。 ) 

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

这些属性被视为元数据，因为它们的实现与 cmdlet 代码的实现不同。 当 Windows PowerShell 运行时运行该 cmdlet 时，它会识别这些属性，然后针对每个属性执行相应的操作。

尽管你可能想要实现这些属性提供的功能版本，但良好的 cmdlet 设计则使用这些常见功能。

有关可在 cmdlet 中声明的不同属性的详细信息，请参阅 [属性类型](./attribute-types.md)。

## <a name="see-also"></a>另请参阅

[属性类型](./attribute-types.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
