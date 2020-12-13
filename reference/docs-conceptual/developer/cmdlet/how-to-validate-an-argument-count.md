---
ms.date: 09/13/2016
ms.topic: reference
title: 如何验证参数计数
description: 如何验证参数计数
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666937"
---
# <a name="how-to-validate-an-argument-count"></a>如何验证参数计数

此示例演示如何指定一个验证规则，Windows PowerShell 运行时可使用该规则检查参数数目 (在运行 cmdlet 之前参数接受的计数) 。 可以通过声明 ValidateCount 属性设置此验证规则。

> [!NOTE]
> 有关用于定义此属性的类的详细信息，请参阅 [Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute)。

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

有关如何声明此特性的详细信息，请参阅 [ValidateCount 特性声明](./validatecount-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[ValidateCount 属性声明](./validatecount-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
