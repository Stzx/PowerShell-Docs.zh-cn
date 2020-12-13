---
ms.date: 09/13/2016
ms.topic: reference
title: 如何从 Cmdlet 内部调用 Cmdlet
description: 如何从 Cmdlet 内部调用 Cmdlet
ms.openlocfilehash: d137ac895f66000329de76a2c16a74b02c0e82ca
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667039"
---
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a>如何从 Cmdlet 内部调用 Cmdlet

此示例演示如何从另一个 cmdlet 中调用 cmdlet，这允许你将调用的 cmdlet 的功能添加到正在开发的 cmdlet。 在此示例中， `Get-Process` 调用了 cmdlet 来获取本地计算机上运行的进程。 对此 cmdlet 的调用 `Get-Process` 等效于以下命令。 此命令检索其名称以字符 "a" 到 "t" 开头的所有进程。

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> 你可以仅调用直接从 [system.web](/dotnet/api/System.Management.Automation.Cmdlet) 类派生的 cmdlet。 不能调用派生自 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 类的 cmdlet。

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a>从 cmdlet 内调用 cmdlet

1. 确保引用定义要调用的 cmdlet 的程序集，并且添加了相应的 `using` 语句。 在此示例中，添加了以下命名空间。

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. 在 cmdlet 的输入处理方法中，创建要调用的 cmdlet 的新实例。 在此示例中，将创建一个类型为 [Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) 的对象，并在其中包含调用 cmdlet 时使用的参数的字符串。

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. 调用 " [system.object](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) " 方法来调用该 `Get-Process` Cmdlet。

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a>示例

在此示例中， `Get-Process` cmdlet 是从 cmdlet 的 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 方法中调用的。

```csharp
using System;
using System.Diagnostics;
using System.Management.Automation;   // Windows PowerShell assembly.
using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify an
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "GreetingInvoke")]
  public class SendGreetingInvokeCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the BeginProcessing method to invoke
    // the Get-Process cmdlet.
    protected override void BeginProcessing()
    {
      GetProcessCommand gp = new GetProcessCommand();
      gp.Name = new string[] { "[a-t]*" };
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
