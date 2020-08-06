---
title: Cmdlet 参数的类型 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e704aae6e23568be9935e228752f652929863a98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786367"
---
# <a name="types-of-cmdlet-parameters"></a>Cmdlet 参数的类型

本主题介绍可在 cmdlet 中声明的不同类型的参数。 Cmdlet 参数可以是位置、命名、必需、可选或切换参数。

## <a name="positional-and-named-parameters"></a>位置和命名参数

所有 cmdlet 参数都是命名参数或位置参数。 命名参数要求在调用 cmdlet 时键入参数名称和参数。 位置参数只要求按相对顺序键入参数。 然后，系统将第一个未命名的参数映射到第一个位置参数。 系统会将第二个未命名的参数映射到第二个未命名的参数，依此类推。 默认情况下，所有 cmdlet 参数均为命名参数。

若要定义命名参数，请 `Position` 在**参数**属性声明中省略关键字，如下面的参数声明中所示。

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

若要定义位置参数，请 `Position` 在参数属性声明中添加关键字，然后指定位置。 在下面的示例中，将 `UserName` 参数声明为位置为0的位置参数。 这意味着调用的第一个参数将自动绑定到此参数。

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> 良好的 cmdlet 设计建议将最常使用的参数声明为位置参数，使用户无需在运行 cmdlet 时输入参数名称。

位置和命名参数接受单个参数或用逗号分隔的多个参数。 仅当参数接受集合（如字符串数组）时，才允许使用多个参数。 可以在同一个 cmdlet 中混合位置和命名参数。 在这种情况下，系统首先检索命名参数，然后尝试将其余未命名参数映射到位置参数。

以下命令显示了可为 cmdlet 的参数指定单个和多个参数的不同方法 `Get-Command` 。 请注意，在最后两个示例中， **-name**不需要指定，因为 `Name` 参数被定义为位置参数。

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a>必需参数和可选参数

你还可以将 cmdlet 参数定义为必需或可选参数。  (必须在 Windows PowerShell 运行时调用 cmdlet 之前指定必需参数。 ) 默认情况下，将参数定义为可选。

若要定义强制参数，请 `Mandatory` 在参数属性声明中添加关键字，并将其设置为 `true` ，如下面的参数声明中所示。

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

若要定义可选参数，请 `Mandatory` 在**参数**属性声明中省略关键字，如下面的参数声明中所示。

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a>开关参数

Windows PowerShell 提供[SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)类型，该类型允许您定义一个参数， `false` 如果在调用 cmdlet 时未指定参数，则此参数的值将自动设置为。 请尽可能使用开关参数代替布尔参数。

请考虑以下示例。 默认情况下，多个 Windows PowerShell cmdlet 不会将输出对象沿管道向下传递。 但是，这些 cmdlet 具有一个 `PassThru` 用于替代默认行为的开关参数。 如果在 `PassThru` 调用这些 cmdlet 时指定了参数，则该 cmdlet 会将输出对象返回到管道。

如果在调用中未指定参数时，需要参数的默认值为 `true` ，请考虑反转参数的意义。 对于示例，请将属性声明为 SwitchParameter 类型，而不是将参数特性设置为的布尔值， `true` 然后将参数的[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)默认值设置为 `false` 。

若要定义开关参数，请将属性声明为[SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)类型，如下面的示例中所示。

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

若要使 cmdlet 在指定时对参数执行操作，请在其中一个输入处理方法中使用以下结构。

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
