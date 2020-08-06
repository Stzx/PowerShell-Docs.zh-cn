---
title: 如何验证参数集 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateSet attribute, example
ms.openlocfilehash: 6173f1380583f5b27e2b188990a5ea041f447c57
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781998"
---
# <a name="how-to-validate-an-argument-set"></a>如何验证参数集

此示例演示如何在运行 cmdlet 之前指定 Windows PowerShell 运行时可用于检查参数参数的验证规则。 此验证规则为参数参数提供了一组有效值。

> [!NOTE]
> 有关用于定义此属性的类的详细信息，请参阅[Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)。

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

有关如何声明此特性的详细信息，请参阅[ValidateSet 特性声明](./validateset-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[System.web. Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[ValidateSet 属性声明](./validateset-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
