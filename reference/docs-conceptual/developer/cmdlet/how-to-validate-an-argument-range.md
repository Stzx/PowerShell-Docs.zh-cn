---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数范围
description: 如何验证参数范围
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666920"
---
# <a name="how-to-validate-an-argument-range"></a>如何验证参数范围

此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则在运行 cmdlet 之前检查参数参数的最小值和最大值。 可以通过声明 ValidateRange 属性设置此验证规则。

> [!NOTE]
> 有关用于定义此属性的类的详细信息，请参阅 [Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)。

### <a name="to-validate-an-argument-range"></a>验证参数范围

- 添加 ValidateRange 特性，如下面的代码所示。 此示例指定参数的范围为0到 5 `InputData` 。

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

有关如何声明此特性的详细信息，请参阅 [ValidateRange 特性声明](./validaterange-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[ValidateRange 属性声明](./validaterange-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
