---
title: 如何验证参数计数 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782117"
---
# <a name="how-to-validate-an-argument-count"></a>如何验证参数计数

此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则检查参数数目 (在运行 cmdlet 之前参数接受的计数) 。 可以通过声明 ValidateCount 属性设置此验证规则。

> [!NOTE]
> 有关用于定义此属性的类的详细信息，请参阅[Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute)。

## <a name="to-validate-an-argument-count"></a>验证参数计数

- 添加 Validate 特性，如下面的代码所示。 此示例指定参数将接受一个参数或多达三个参数。

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

有关如何声明此特性的详细信息，请参阅[ValidateCount 特性声明](./validatecount-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[ValidateCount 属性声明](./validatecount-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
