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
# <a name="how-to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="8cac0-103">如何从 Cmdlet 内部调用 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8cac0-103">How to Invoke a Cmdlet from Within a Cmdlet</span></span>

<span data-ttu-id="8cac0-104">此示例演示如何从另一个 cmdlet 中调用 cmdlet，这允许你将调用的 cmdlet 的功能添加到正在开发的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8cac0-104">This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span> <span data-ttu-id="8cac0-105">在此示例中， `Get-Process` 调用了 cmdlet 来获取本地计算机上运行的进程。</span><span class="sxs-lookup"><span data-stu-id="8cac0-105">In this example, the `Get-Process` cmdlet is invoked to get the processes that are running on the local computer.</span></span> <span data-ttu-id="8cac0-106">对此 cmdlet 的调用 `Get-Process` 等效于以下命令。</span><span class="sxs-lookup"><span data-stu-id="8cac0-106">The call to the `Get-Process` cmdlet is equivalent to the following command.</span></span> <span data-ttu-id="8cac0-107">此命令检索其名称以字符 "a" 到 "t" 开头的所有进程。</span><span class="sxs-lookup"><span data-stu-id="8cac0-107">This command retrieves all the processes whose names start with the characters "a" through "t".</span></span>

```powershell
Get-Process -name [a-t]
```

> [!IMPORTANT]
> <span data-ttu-id="8cac0-108">你可以仅调用直接从 [system.web](/dotnet/api/System.Management.Automation.Cmdlet) 类派生的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8cac0-108">You can invoke only those cmdlets that derive directly from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class.</span></span> <span data-ttu-id="8cac0-109">不能调用派生自 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 类的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8cac0-109">You cannot invoke a cmdlet that derives from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) class.</span></span>

## <a name="to-invoke-a-cmdlet-from-within-a-cmdlet"></a><span data-ttu-id="8cac0-110">从 cmdlet 内调用 cmdlet</span><span class="sxs-lookup"><span data-stu-id="8cac0-110">To invoke a cmdlet from within a cmdlet</span></span>

1. <span data-ttu-id="8cac0-111">确保引用定义要调用的 cmdlet 的程序集，并且添加了相应的 `using` 语句。</span><span class="sxs-lookup"><span data-stu-id="8cac0-111">Ensure that the assembly that defines the cmdlet to be invoked is referenced and that the appropriate `using` statement is added.</span></span> <span data-ttu-id="8cac0-112">在此示例中，添加了以下命名空间。</span><span class="sxs-lookup"><span data-stu-id="8cac0-112">In this example, the following namespaces are added.</span></span>

    ```csharp
    using System.Diagnostics;
    using System.Management.Automation;   // Windows PowerShell assembly.
    using Microsoft.PowerShell.Commands;  // Windows PowerShell assembly.
    ```

2. <span data-ttu-id="8cac0-113">在 cmdlet 的输入处理方法中，创建要调用的 cmdlet 的新实例。</span><span class="sxs-lookup"><span data-stu-id="8cac0-113">In the input processing method of the cmdlet, create a new instance of the cmdlet to be invoked.</span></span> <span data-ttu-id="8cac0-114">在此示例中，将创建一个类型为 [Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) 的对象，并在其中包含调用 cmdlet 时使用的参数的字符串。</span><span class="sxs-lookup"><span data-stu-id="8cac0-114">In this example, an object of type [Microsoft.PowerShell.Commands.Getprocesscommand](/dotnet/api/Microsoft.PowerShell.Commands.GetProcessCommand) is created along with the string that contains the arguments that are used when the cmdlet is invoked.</span></span>

    ```csharp
    GetProcessCommand gp = new GetProcessCommand();
    gp.Name = new string[] { "[a-t]*" };
    ```

3. <span data-ttu-id="8cac0-115">调用 " [system.object](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) " 方法来调用该 `Get-Process` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8cac0-115">Call the [System.Management.Automation.Cmdlet.Invoke\*](/dotnet/api/System.Management.Automation.Cmdlet.Invoke) method to invoke the `Get-Process` cmdlet.</span></span>

    ```csharp
      foreach (Process p in gp.Invoke<Process>())
      {
        Console.WriteLine(p.ToString());
      }
    }
    ```

## <a name="example"></a><span data-ttu-id="8cac0-116">示例</span><span class="sxs-lookup"><span data-stu-id="8cac0-116">Example</span></span>

<span data-ttu-id="8cac0-117">在此示例中， `Get-Process` cmdlet 是从 cmdlet 的 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 方法中调用的。</span><span class="sxs-lookup"><span data-stu-id="8cac0-117">In this example, the `Get-Process` cmdlet is invoked from within the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method of a cmdlet.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8cac0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cac0-118">See Also</span></span>

[<span data-ttu-id="8cac0-119">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8cac0-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
