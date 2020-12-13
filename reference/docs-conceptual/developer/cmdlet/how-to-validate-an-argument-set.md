---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数集
description: 如何验证参数集
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650366"
---
# <a name="how-to-validate-an-argument-set"></a>如何验证参数集

此示例演示如何在运行 cmdlet 之前指定 Windows PowerShell 运行时可用于检查参数参数的验证规则。 此验证规则为参数参数提供了一组有效值。

> [!NOTE]
> 有关用于定义此属性的类的详细信息，请参阅 [Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)。

## <a name="to-validate-an-argument-set"></a>验证参数集

- 添加 ValidateSet 特性，如下面的代码所示。 此示例为参数指定了三个可能的值集 `UserName` 。

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

有关如何声明此特性的详细信息，请参阅 [ValidateSet 特性声明](./validateset-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[System.web. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[ValidateSet 属性声明](./validateset-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
