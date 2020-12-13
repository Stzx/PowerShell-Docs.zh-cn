---
ms.date: 09/13/2016
ms.topic: reference
title: 如何声明 Cmdlet 参数
description: 如何声明 Cmdlet 参数
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667090"
---
# <a name="how-to-declare-cmdlet-parameters"></a>如何声明 Cmdlet 参数

这些示例演示如何声明命名、位置、必需、可选参数和开关参数。 这些示例还演示如何定义参数别名。

## <a name="how-to-declare-a-named-parameter"></a>如何声明命名参数

- 定义公共属性，如下面的代码所示。 添加参数特性时，请 `Position` 从特性中省略关键字。

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。

## <a name="how-to-declare-a-positional-parameter"></a>如何声明位置参数

- 定义公共属性，如下面的代码所示。 添加参数特性时，请将关键字设置 `Position` 为参数位置。 值0指示第一个位置。

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。

## <a name="how-to-declare-a-mandatory-parameter"></a>如何声明必需参数

- 定义公共属性，如下面的代码所示。 添加参数特性时，请将关键字设置 `Mandatory` 为 `true` 。

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。

## <a name="how-to-declare-an-optional-parameter"></a>如何声明可选参数

- 定义公共属性，如下面的代码所示。 添加参数属性时，请省略 `Mandatory` 关键字。

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a>如何声明开关参数

- 将公共属性定义为 [SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)类型，然后声明参数属性。

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

有关参数属性的详细信息，请参阅 [参数属性声明](./parameter-attribute-declaration.md)。

## <a name="how-to-declare-a-parameter-with-aliases"></a>如何使用别名声明参数

- 定义公共属性，如下面的代码所示。 添加一个别名属性，其中列出了参数的别名。 在此示例中，为同一参数定义了三个别名。 第一个别名提供快捷方式。 第二个和第三个别名提供了可用于不同方案的名称。

    ```csharp
    [Alias("UN","Writer","Editor")]
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

有关 Alias 特性的详细信息，请参阅 [Alias 特性声明](./alias-attribute-declaration.md)。

## <a name="see-also"></a>另请参阅

[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)

[参数属性声明](./parameter-attribute-declaration.md)

[别名属性声明](./alias-attribute-declaration.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
