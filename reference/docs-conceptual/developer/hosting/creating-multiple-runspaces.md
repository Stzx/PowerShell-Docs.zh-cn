---
ms.date: 09/13/2016
ms.topic: reference
title: 创建多个运行空间
description: 创建多个运行空间
ms.openlocfilehash: 2dc9cc0397178d679a4d418b7b19fb0895a4e1b7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649405"
---
# <a name="creating-multiple-runspaces"></a><span data-ttu-id="e81b4-103">创建多个运行空间</span><span class="sxs-lookup"><span data-stu-id="e81b4-103">Creating multiple runspaces</span></span>

<span data-ttu-id="e81b4-104">如果创建大量的运行空间，则可以考虑创建运行空间池。</span><span class="sxs-lookup"><span data-stu-id="e81b4-104">If you create a large number of runspaces, you might consider creating a runspace pool.</span></span> <span data-ttu-id="e81b4-105">使用 [Runspacepool](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool) 对象，而不是创建具有相同特征的大量单个运行空间，可以提高性能。</span><span class="sxs-lookup"><span data-stu-id="e81b4-105">Using a [System.Management.Automation.Runspaces.Runspacepool](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool) object, rather than creating a large number of individual runspaces with the same characteristics, can improve performance.</span></span>

## <a name="creating-and-using-a-runspace-pool"></a><span data-ttu-id="e81b4-106">创建和使用运行空间池。</span><span class="sxs-lookup"><span data-stu-id="e81b4-106">Creating and using a runspace pool.</span></span>

 <span data-ttu-id="e81b4-107">下面的示例演示如何创建运行空间池，以及如何在池中的运行空间中以异步方式运行命令。</span><span class="sxs-lookup"><span data-stu-id="e81b4-107">The following example shows how to create a runspace pool and how to run a command asynchronously in a runspace of the pool.</span></span>

```csharp
namespace HostRunspacePool
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  /// <summary>
  /// This class provides the Main entry point for the Host application.
  /// </summary>
  internal class HostRunspacePool
  {
    /// <summary>
    /// This sample demonstrates the following.
    /// 1. Creating and opening a runspace pool.
    /// 2. Creating a PowerShell object.
    /// 3. Adding commands and arguments to the PowerShell object.
    /// 4. Running the commands asynchronously using the runspace
    ///    of the runspace pool.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    private static void Main(string[] args)
    {
      // Create a pool of runspaces.
      using (RunspacePool rsp = RunspaceFactory.CreateRunspacePool())
      {
        rsp.Open();

        // Create a PowerShell object to run the following command.
        //  get-process wmi*
        PowerShell gpc = PowerShell.Create();
        // Specify the runspace to use and add commands.
        gpc.RunspacePool = rsp;
        gpc.AddCommand("Get-Process").AddArgument("wmi*");

        // Invoke the command asynchronously.
        IAsyncResult gpcAsyncResult = gpc.BeginInvoke();
        // Get the results of running the command.
        PSDataCollection<PSObject> gpcOutput = gpc.EndInvoke(gpcAsyncResult);

        // Process the output.
        Console.WriteLine("The output from running the command: get-process wmi*");
        for (int i= 0; i < gpcOutput.Count; i++)
        {
         Console.WriteLine(
                           "Process Name: {0} Process Id: {1}",
                           gpcOutput[i].Properties["ProcessName"].Value,
                           gpcOutput[i].Properties["Id"].Value);
        }
      } // End using.
    } // End Main entry point.
  } // End HostPs5 class.
}
```

## <a name="see-also"></a><span data-ttu-id="e81b4-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e81b4-108">See Also</span></span>

 [<span data-ttu-id="e81b4-109">创建 InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="e81b4-109">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)
