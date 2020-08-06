---
title: 创建 InitialSessionState |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 946adf1006d1afcad2810c85e39f14514e837327
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779720"
---
# <a name="creating-an-initialsessionstate"></a><span data-ttu-id="876a7-102">创建 InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="876a7-102">Creating an InitialSessionState</span></span>

<span data-ttu-id="876a7-103">PowerShell 命令在运行空间中运行。</span><span class="sxs-lookup"><span data-stu-id="876a7-103">PowerShell commands run in a runspace.</span></span>
<span data-ttu-id="876a7-104">若要在你的应用程序中托管 PowerShell，你必须[创建一个](/dotnet/api/System.Management.Automation.Runspaces.Runspace)</span><span class="sxs-lookup"><span data-stu-id="876a7-104">To host PowerShell in your application, you must create a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>
<span data-ttu-id="876a7-105">每个运行空间都有一个与其关联的[System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象。</span><span class="sxs-lookup"><span data-stu-id="876a7-105">Every runspace has an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object associated with it.</span></span>
<span data-ttu-id="876a7-106">InitialSessionState 指定运行空间的特征，例如，哪些命令、变量和模块可用于该运行空间。</span><span class="sxs-lookup"><span data-stu-id="876a7-106">The InitialSessionState specifies characteristics of the runspace, such as which commands, variables, and modules are available for that runspace.</span></span>

## <a name="create-a-default-initialsessionstate"></a><span data-ttu-id="876a7-107">创建默认 InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="876a7-107">Create a default InitialSessionState</span></span>

<span data-ttu-id="876a7-108">**InitialSessionState**类的[CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault)和[CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2)方法可用于创建**InitialSessionState**对象。</span><span class="sxs-lookup"><span data-stu-id="876a7-108">The [CreateDefault](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault) and [CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) methods of the **InitialSessionState** class can be used to create an **InitialSessionState** object.</span></span>
<span data-ttu-id="876a7-109">**CreateDefault**方法将创建一个**InitialSessionState** ，其中加载了所有内置命令，而**CreateDefault2**方法只加载承载 PowerShell (命令从模块) 的命令。</span><span class="sxs-lookup"><span data-stu-id="876a7-109">The **CreateDefault** method creates an **InitialSessionState** with all of the built-in commands loaded, while the **CreateDefault2** method loads only the commands required to host PowerShell (the commands from the Microsoft.PowerShell.Core module).</span></span>

<span data-ttu-id="876a7-110">若要进一步限制主机应用程序中可用的命令，需要创建受约束的运行空间。</span><span class="sxs-lookup"><span data-stu-id="876a7-110">If you want to further limit the commands available in your host application you need to create a constrained runspace.</span></span>
<span data-ttu-id="876a7-111">有关信息，请参阅[创建受限的运行空间](creating-a-constrained-runspace.md)。</span><span class="sxs-lookup"><span data-stu-id="876a7-111">For information, see [Creating a constrained runspace](creating-a-constrained-runspace.md).</span></span>

<span data-ttu-id="876a7-112">下面的代码演示如何创建**InitialSessionState**，将其分配给运行空间，将命令添加到该运行空间中的管道，以及调用命令。</span><span class="sxs-lookup"><span data-stu-id="876a7-112">The following code shows how to create an **InitialSessionState**, assign it to a runspace, add commands to the pipeline in that runspace, and invoke the commands.</span></span>
<span data-ttu-id="876a7-113">有关添加和调用命令的详细信息，请参阅[添加和调用命令](adding-and-invoking-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="876a7-113">For more information about adding and invoking commands, see [Adding and invoking commands](adding-and-invoking-commands.md).</span></span>

```csharp
namespace SampleHost
{
  using System;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  class HostP4b
  {
    static void Main(string[] args)
    {
      // Call the InitialSessionState.CreateDefault method to create
      // an empty InitialSessionState object, and then add the
      // elements that will be available when the runspace is opened.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      SessionStateVariableEntry var1 = new
          SessionStateVariableEntry("test1",
                                    "MyVar1",
                                    "Initial session state MyVar1 test");
      iss.Variables.Add(var1);

      SessionStateVariableEntry var2 = new
          SessionStateVariableEntry("test2",
                                    "MyVar2",
                                    "Initial session state MyVar2 test");
      iss.Variables.Add(var2);

      // Call the RunspaceFactory.CreateRunspace(InitialSessionState)
      // method to create the runspace where the pipeline is run.
      Runspace rs = RunspaceFactory.CreateRunspace(iss);
      rs.Open();

      // Call the PowerShell.Create() method to create the PowerShell object,
      // and then specify the runspace and commands to the pipeline.
      // and create the command pipeline.
      PowerShell ps = PowerShell.Create();
      ps.Runspace = rs;
      ps.AddCommand("Get-Variable");
      ps.AddArgument("test*");

      Console.WriteLine("Variable             Value");
      Console.WriteLine("--------------------------");

      // Call the PowerShell.Invoke() method to run
      // the pipeline synchronously.
      foreach (PSObject result in ps.Invoke())
      {
        Console.WriteLine("{0,-20}{1}",
            result.Members["Name"].Value,
            result.Members["Value"].Value);
      } // End foreach.

      // Close the runspace to free resources.
      rs.Close();

    } // End Main.
  } // End SampleHost.
}
```

## <a name="see-also"></a><span data-ttu-id="876a7-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="876a7-114">See Also</span></span>

[<span data-ttu-id="876a7-115">创建受限运行空间</span><span class="sxs-lookup"><span data-stu-id="876a7-115">Creating a constrained runspace</span></span>](creating-a-constrained-runspace.md)

[<span data-ttu-id="876a7-116">添加和调用命令</span><span class="sxs-lookup"><span data-stu-id="876a7-116">Adding and invoking commands</span></span>](adding-and-invoking-commands.md)
