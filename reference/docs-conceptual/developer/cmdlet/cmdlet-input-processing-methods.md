---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 输入处理方法
description: Cmdlet 输入处理方法
ms.openlocfilehash: e1a7b58517d6285250edbf16d14810388c242218
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653387"
---
# <a name="cmdlet-input-processing-methods"></a>Cmdlet 输入处理方法

Cmdlet 必须重写本主题中描述的一个或多个输入处理方法，以执行其工作。
这些方法允许 cmdlet 执行预处理、输入处理和后期处理操作。
这些方法还允许你停止 cmdlet 处理。
有关如何使用这些方法的更详细示例，请参阅 [SelectStr 教程](selectstr-tutorial.md)。

## <a name="pre-processing-operations"></a>预处理操作

Cmdlet 应重写 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 方法，以添加对将在以后由 Cmdlet 处理的所有记录有效的任何预处理操作。
当 PowerShell 处理命令管道时，PowerShell 将为管道中的每个 cmdlet 实例调用一次此方法。
有关 PowerShell 如何调用命令管道的详细信息，请参阅 [Cmdlet 处理生命周期](/previous-versions/ms714429(v=vs.85))。

下面的代码演示 BeginProcessing 方法的实现。

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a>输入处理操作

Cmdlet 可以重写 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法，以处理发送到 Cmdlet 的输入的。
当 PowerShell 处理命令管道时，PowerShell 将为 cmdlet 处理的每个输入记录调用此方法。
有关 PowerShell 如何调用命令管道的详细信息，请参阅 [Cmdlet 处理生命周期](/previous-versions/ms714429(v=vs.85))。

下面的代码演示 ProcessRecord 方法的实现。

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a>后处理操作

Cmdlet 应重写 [system.exception 方法，](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 以添加对 Cmdlet 所处理的所有记录有效的任何后续处理后操作。
例如，你的 cmdlet 可能需要在完成处理后清理对象变量。

当 PowerShell 处理命令管道时，PowerShell 将为管道中的每个 cmdlet 实例调用一次此方法。
但是，请务必记住，如果通过其输入处理中途取消 cmdlet，或者在 cmdlet 的任何部分中发生终止错误，则 PowerShell 运行时将不会调用 EndProcessing 方法。
出于此原因，需要对象清理的 cmdlet 应该实现完整的 [IDisposable](/dotnet/api/System.IDisposable) 模式（包括终结器），以便运行时可以在处理结束时调用 EndProcessing 和 [IDisposable](/dotnet/api/System.IDisposable.Dispose) 方法。
有关 PowerShell 如何调用命令管道的详细信息，请参阅 [Cmdlet 处理生命周期](/previous-versions/ms714429(v=vs.85))。

下面的代码演示了 EndProcessing 方法的实现。

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a>另请参阅

["BeginProcessing"。](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

["ProcessRecord"。](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.web. EndProcessing. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[SelectStr 教程](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
