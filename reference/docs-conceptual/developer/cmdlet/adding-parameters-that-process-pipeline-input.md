---
ms.date: 09/13/2016
ms.topic: reference
title: 添加用于处理管道输入的参数
description: 添加用于处理管道输入的参数
ms.openlocfilehash: b150d5be93207d9c010a6d2d4de901b4526f1d79
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668348"
---
# <a name="adding-parameters-that-process-pipeline-input"></a>添加用于处理管道输入的参数

Cmdlet 的一个输入源是从上游 cmdlet 产生的管道上的对象。 本部分介绍如何将参数添加到 [创建第一个 cmdlet](./creating-a-cmdlet-without-parameters.md)) 中所述的 Get-Proc cmdlet (，以便该 cmdlet 可以处理管道对象。

此 Get-Proc cmdlet 使用一个 `Name` 参数，该参数接受来自管道对象的输入，基于提供的名称从本地计算机检索进程信息，然后在命令行中显示有关进程的信息。

## <a name="defining-the-cmdlet-class"></a>定义 Cmdlet 类

创建 cmdlet 的第一步是始终命名 cmdlet 并声明实现 cmdlet 的 .NET 类。 此 cmdlet 检索进程信息，因此此处选择的谓词名称为 "Get"。  (几乎任何支持检索信息的 cmdlet，都可以处理命令行输入。 ) 有关已批准的 cmdlet 动词的详细信息，请参阅 [Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)。

下面是此 Get-Proc cmdlet 的定义。 [创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)中提供了此定义的详细信息。

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a>定义管道的输入

本部分介绍如何为 cmdlet 定义管道中的输入。 此 Get-Proc cmdlet 定义了一个属性，该属性表示 `Name` 参数，如 [添加处理命令行输入的参数](./adding-parameters-that-process-command-line-input.md)中所述。
 (参见该主题，了解有关声明参数的一般信息。 ) 

但是，当某个 cmdlet 需要处理管道输入时，它必须将其参数与 Windows PowerShell 运行时绑定到输入值。 为此，必须添加 `ValueFromPipeline` 关键字，或将 `ValueFromPipelineByProperty` 关键字添加到 [Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) 特性声明。 `ValueFromPipeline`如果 cmdlet 访问完整的输入对象，则指定关键字。 `ValueFromPipelineByProperty`如果 cmdlet 仅访问对象的属性，请指定。

下面是 `Name` 接受管道输入的此 Get-Proc cmdlet 的参数声明。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="35-44":::

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

前面的声明将 `ValueFromPipeline` 关键字设置为， `true` 这样，如果对象与参数的类型相同，或者可以将参数强制转换为同一类型，则 Windows PowerShell 运行时会将参数绑定到传入对象。 `ValueFromPipelineByPropertyName`还将关键字设置为， `true` 以便 Windows PowerShell 运行时将检查属性的传入对象 `Name` 。 如果传入对象具有此类属性，则运行时将该 `Name` 参数绑定到 `Name` 传入对象的属性。

> [!NOTE]
> `ValueFromPipeline`参数的 attribute 关键字的设置优先于关键字的设置 `ValueFromPipelineByPropertyName` 。

## <a name="overriding-an-input-processing-method"></a>重写输入处理方法

如果 cmdlet 要处理管道输入，则需要重写适当的输入处理方法。 基本输入处理方法在 [创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)时引入。

此 Get-Proc cmdlet 将重写 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法，以处理 `Name` 用户或脚本提供的参数输入。 如果未提供任何名称，则此方法将获取每个请求的进程名称或所有进程的进程。 请注意，在 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)中，对 [WriteObject)  (](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 的调用是用于将输出对象发送到管道的输出机制的输出机制。 此调用的第二个参数将 `enumerateCollection` 设置为，以 `true` 指示 Windows PowerShell 运行时枚举进程对象的数组，并一次将一个进程写入命令行。

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
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a>代码示例

有关完整的 c # 示例代码，请参阅 [GetProcessSample03 示例](./getprocesssample03-sample.md)。

## <a name="defining-object-types-and-formatting"></a>定义对象类型和格式设置

Windows PowerShell 使用 .Net 对象在 cmdlet 之间传递信息。 因此，cmdlet 可能需要定义自己的类型，或者该 cmdlet 可能需要扩展另一个 cmdlet 提供的现有类型。 有关定义新类型或扩展现有类型的详细信息，请参阅 [扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))。

## <a name="building-the-cmdlet"></a>构建 Cmdlet

实现 cmdlet 后，必须通过 Windows PowerShell 管理单元向 Windows PowerShell 注册它。 有关注册 cmdlet 的详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))。

## <a name="testing-the-cmdlet"></a>测试 Cmdlet

向 Windows PowerShell 注册 cmdlet 后，通过在命令行上运行它来对其进行测试。 例如，测试示例 cmdlet 的代码。 有关从命令行使用 cmdlet 的详细信息，请参阅 [使用 Windows PowerShell 的入门](/powershell/scripting/getting-started/getting-started-with-windows-powershell)。

- 在 Windows PowerShell 提示符下，输入以下命令以通过管道检索进程名称。

  ```powershell
  PS> type ProcessNames | get-proc
  ```

  将显示以下输出。

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      809      21  40856    4448    147    9.50  2288  iexplore
      737      21  26036   16348    144   22.03  3860  iexplore
       39       2   1024     388     30    0.08  3396  notepad
     3927      62  71836   26984    467  195.19  1848  OUTLOOK
  ```

- 输入以下行，以获取进程对象，这些对象具有 `Name` 名为 "IEXPLORE" 的进程的属性。 此示例使用 `Get-Process` Windows PowerShell) 提供的 cmdlet (作为上游命令来检索 "IEXPLORE" 进程。

  ```powershell
  PS> get-process iexplore | get-proc
  ```

  将显示以下输出。

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
  ```

## <a name="see-also"></a>另请参阅

[添加处理命令行输入的参数](./adding-parameters-that-process-command-line-input.md)

[创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)

[扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))

[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))

[Windows PowerShell 参考](../windows-powershell-reference.md)

[Cmdlet 示例](./cmdlet-samples.md)
