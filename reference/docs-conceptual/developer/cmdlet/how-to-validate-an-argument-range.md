---
title: 如何验证参数范围 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange attribute, example
ms.openlocfilehash: b48b1b87425add51e855c48ec700c78c3ae296c1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782066"
---
# <a name="how-to-validate-an-argument-range"></a>如何验证参数范围

此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则在运行 cmdlet 之前检查参数参数的最小值和最大值。 可以通过声明 ValidateRange 属性设置此验证规则。

> [!NOTE]
> 有关用于定义此属性的类的详细信息，请参阅[Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)。

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

有关如何声明此特性的详细信息，请参阅[ValidateRange 特性声明](./validaterange-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[ValidateRange 属性声明](./validaterange-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
