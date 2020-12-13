---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数长度
description: 如何验证参数长度
ms.openlocfilehash: 460aedbe6847033f976cb7bf70b6c77ac5a3a3c9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652626"
---
# <a name="how-to-validate-the-argument-length"></a>如何验证参数长度

此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则检查在运行 cmdlet 之前 (参数参数长度) 的字符数。 可以通过声明 ValidateLength 属性设置此验证规则。

> [!NOTE]
> 有关用于定义此属性的类的详细信息，请参阅 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)。

## <a name="to-validate-the-argument-length"></a>验证参数长度

- 添加 Validate 特性，如下面的代码所示。 此示例指定参数的长度应为0到10个字符。

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

有关如何声明此特性的详细信息，请参阅 [ValidateLength 特性声明](./validatelength-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[ValidateLength 属性声明](./validatelength-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
