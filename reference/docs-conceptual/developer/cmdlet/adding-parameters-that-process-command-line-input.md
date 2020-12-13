---
ms.date: 09/13/2016
ms.topic: reference
title: 添加用于处理命令行输入的参数
description: 添加用于处理命令行输入的参数
ms.openlocfilehash: f20469d366330aa787fbc16e4f0a76e67fc7c6db
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "93354603"
---
# <a name="adding-parameters-that-process-command-line-input"></a>添加用于处理命令行输入的参数

一个 cmdlet 的输入源是命令行。 本主题介绍了如何将参数添加到 `Get-Proc` cmdlet， (在 [创建第一个 cmdlet](./creating-a-cmdlet-without-parameters.md)) 中介绍了如何根据传递给 cmdlet 的显式对象处理本地计算机输入。 `Get-Proc`此处所述的 cmdlet 会根据名称检索进程，然后在命令提示符下显示有关进程的信息。

## <a name="defining-the-cmdlet-class"></a>定义 Cmdlet 类

Cmdlet 创建的第一步是 cmdlet 命名和实现 cmdlet .NET Framework 类的声明。 此 cmdlet 检索进程信息，因此此处选择的谓词名称为 "Get"。  (几乎任何支持检索信息的 cmdlet，都可以处理命令行输入。 ) 有关已批准的 cmdlet 动词的详细信息，请参阅 [Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)。

下面是 cmdlet 的类声明 `Get-Proc` 。 [创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)中提供了有关此定义的详细信息。

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand: Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="declaring-parameters"></a>声明参数

Cmdlet 参数使用户能够向 cmdlet 提供输入。 在下面的示例中， `Get-Proc` 和 `Get-Member` 是管线 cmdlet 的名称，并且 `MemberType` 是 cmdlet 的参数 `Get-Member` 。 参数的参数为 "属性"。

**PS> `get-member` -membertype 属性**

若要声明 cmdlet 的参数，必须首先定义表示参数的属性。 在 `Get-Proc` cmdlet 中，唯一的参数是 `Name` ，在此示例中，它表示要检索的 .NET Framework 进程对象的名称。 因此，cmdlet 类定义类型字符串的属性以接受名称数组。

下面是 `Name` cmdlet 的参数声明 `Get-Proc` 。

```csharp
/// <summary>
/// Specify the cmdlet Name parameter.
/// </summary>
  [Parameter(Position = 0)]
  [ValidateNotNullOrEmpty]
  public string[] Name
  {
    get { return processNames; }
    set { processNames = value; }
  }
  private string[] processNames;

  #endregion Parameters
```

```vb
<Parameter(Position:=0), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

若要通知 Windows PowerShell 运行时此属性为 `Name` 参数，请将 [Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) 特性添加到属性定义。 用于声明此属性的基本语法是 `[Parameter()]` 。

> [!NOTE]
> 参数必须显式标记为公共。 未标记为 "公共" 的参数默认为内部参数，而不是由 Windows PowerShell 运行时找到。

此 cmdlet 使用参数的字符串数组 `Name` 。 如果可能，cmdlet 还应将参数定义为数组，因为这允许 cmdlet 接受多个项。

#### <a name="things-to-remember-about-parameter-definitions"></a>有关参数定义的注意事项

- 应尽可能多地重复使用预定义的 Windows PowerShell 参数名称和数据类型，确保 cmdlet 与 Windows PowerShell cmdlet 兼容。 例如，如果所有 cmdlet 都使用预定义的 `Id` 参数名称来标识资源，则无论使用哪种 cmdlet，用户都可以轻松地了解参数的含义。 基本上，参数名称与公共语言运行时中用于变量名称的规则 (CLR) 相同。 有关参数命名的详细信息，请参阅 [Cmdlet 参数名称](/previous-versions/ms714468(v=vs.85))。

- Windows PowerShell 保留了几个参数名称，以便提供一致的用户体验。 不要使用以下参数名称： `WhatIf` 、 `Confirm` 、 `Verbose` 、、、、、 `Debug` `Warn` `ErrorAction` `ErrorVariable` `OutVariable` 和 `OutBuffer` 。 此外，还保留了这些参数名称的以下别名： `vb` 、 `db` 、 `ea` 、 `ev` 、 `ov` 和 `ob` 。

- `Name` 是一个简单的通用参数名称，建议在 cmdlet 中使用。 最好选择与特定 cmdlet 唯一的复杂名称类似的参数名称，并且很难记住。

- 默认情况下，参数在 Windows PowerShell 中不区分大小写，但在默认情况下，shell 保留大小写。 参数的区分大小写取决于 cmdlet 的操作。 参数会传递到命令行中指定的参数。

- 有关其他参数声明的示例，请参阅 [Cmdlet 参数](./cmdlet-parameters.md)。

## <a name="declaring-parameters-as-positional-or-named"></a>将参数声明为位置或命名

Cmdlet 必须将每个参数都设置为位置或命名参数。 这两种参数都接受单个参数、用逗号分隔的多个参数以及布尔值设置。 布尔参数（也称为 *开关*）仅处理布尔值设置。 开关用于确定参数的状态。 建议的默认值为 `false` 。

示例 `Get-Proc` cmdlet 将参数定义 `Name` 为位置参数
0. 这意味着，用户在命令行中输入的第一个参数会自动插入此参数。 如果要定义命名参数（用户必须从命令行指定参数名称），请将关键字保留在 `Position` 属性声明之外。

> [!NOTE]
> 除非参数必须命名，否则建议您将最常用的参数设置为 "位置"，以使用户不必键入参数名称。

## <a name="declaring-parameters-as-mandatory-or-optional"></a>将参数声明为必需或可选

Cmdlet 必须将每个参数都设置为可选参数或强制参数。 在示例 `Get-Proc` cmdlet 中， `Name` 参数定义为可选，因为 `Mandatory` 未在属性声明中设置关键字。

## <a name="supporting-parameter-validation"></a>支持参数验证

示例 `Get-Proc` cmdlet 将输入验证特性 [Validatenotnulloremptyattribute](/dotnet/api/System.Management.Automation.ValidateNotNullOrEmptyAttribute)添加到 `Name` 参数，以允许验证输入既不是也不是 `null` 空的。 此属性是 Windows PowerShell 提供的多个验证属性之一。 有关其他验证属性的示例，请参阅 [验证参数输入](./validating-parameter-input.md)。

```
[Parameter(Position = 0)]
[ValidateNotNullOrEmpty]
public string[] Name
```

## <a name="overriding-an-input-processing-method"></a>重写输入处理方法

如果 cmdlet 要处理命令行输入，则必须重写相应的输入处理方法。 基本输入处理方法在 [创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)时引入。

该 `Get-Proc` cmdlet 将重写 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法，以处理 `Name` 用户或脚本提供的参数输入。 此方法获取每个请求的进程名称的进程，如果未提供任何名称，则获取所有进程的进程。 请注意，在 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)中，对 [WriteObject% 28system.object% 2csystem.string% %29](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 的调用是用于将输出对象发送到管道的输出的机制。）。 此调用的第二个参数 `enumerateCollection` 设置为， `true` 通知 Windows PowerShell 运行时枚举进程对象的输出数组，并一次将一个进程写入命令行。

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
    // Write the processes to the pipeline making them available
    // to the next cmdlet. The second argument of this call tells
    // PowerShell to enumerate the array, and send one process at a
    // time to the pipeline.
    WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    }
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        Dim processes As Process()
        processes = Process.GetProcesses()
    End If

    '/ If process names are specified, write the processes to the
    '/ pipeline to display them or make them available to the next cmdlet.

    For Each name As String In processNames
        '/ The second parameter of this call tells PowerShell to enumerate the
        '/ array, and send one process at a time to the pipeline.
        WriteObject(Process.GetProcessesByName(name), True)
    Next

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>代码示例

有关完整的 c # 示例代码，请参阅 [GetProcessSample02 示例](./getprocesssample02-sample.md)。

## <a name="defining-object-types-and-formatting"></a>定义对象类型和格式设置

Windows PowerShell 通过使用 .NET Framework 对象在 cmdlet 之间传递信息。 因此，cmdlet 可能需要定义自己的类型，或者 cmdlet 可能需要扩展另一个 cmdlet 提供的现有类型。 有关定义新类型或扩展现有类型的详细信息，请参阅 [扩展对象类型和格式](/previous-versions/ms714665(v=vs.85))。

## <a name="building-the-cmdlet"></a>构建 Cmdlet

实现 cmdlet 后，必须使用 Windows PowerShell 管理单元将其注册到 Windows PowerShell。 有关注册 cmdlet 的详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))。

## <a name="testing-the-cmdlet"></a>测试 Cmdlet

向 Windows PowerShell 注册 cmdlet 后，可以通过在命令行上运行 cmdlet 来对其进行测试。 可以通过两种方法来测试示例 cmdlet 的代码。 有关从命令行使用 cmdlet 的详细信息，请参阅 [使用 Windows PowerShell 入门](/powershell/scripting/getting-started/getting-started-with-windows-powershell)。

- 在 Windows PowerShell 提示符下，使用以下命令列出名为 "IEXPLORE" 的 Internet Explorer 进程。

  ```powershell
  get-proc -name iexplore
  ```

  将显示以下输出。

  ```Output
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----   ------ --   -----------
      354      11  10036   18992    85   0.67   3284   iexplore
  ```

- 若要列出名为 "IEXPLORE"、"OUTLOOK" 和 "NOTEPAD" 的 Internet Explorer、Outlook 和记事本进程，请使用以下命令。 如果有多个进程，则显示所有进程。

  ```powershell
  get-proc -name iexplore, outlook, notepad
  ```

  将显示以下输出。

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)   Id   ProcessName
  -------  ------  -----   -----  -----  ------   --   -----------
      732      21  24696    5000    138   2.25  2288   iexplore
      715      19  20556   14116    136   1.78  3860   iexplore
     3917      62  74096   58112    468 191.56  1848   OUTLOOK
       39       2   1024    3280     30   0.09  1444   notepad
       39       2   1024     356     30   0.08  3396   notepad
  ```

## <a name="see-also"></a>另请参阅

[添加用于处理管道输入的参数](./adding-parameters-that-process-pipeline-input.md)

[创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)

[扩展对象类型和格式](/previous-versions/ms714665(v=vs.85))

[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions/ms714644(v=vs.85))

[Windows PowerShell 参考](../windows-powershell-reference.md)

[Cmdlet 示例](./cmdlet-samples.md)
