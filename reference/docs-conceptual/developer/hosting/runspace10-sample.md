---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace10 示例
description: Runspace10 示例
ms.openlocfilehash: fd58cea553e6b830a56df7edfa7901d39f46a06c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657570"
---
# <a name="runspace10-sample"></a><span data-ttu-id="1c2b9-103">Runspace10 示例</span><span class="sxs-lookup"><span data-stu-id="1c2b9-103">Runspace10 Sample</span></span>

<span data-ttu-id="1c2b9-104">此示例演示如何创建默认初始会话状态，如何将 cmdlet 添加到[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)，如何创建使用初始会话状态的运行空间，以及如何通过使用[system.exception 对象运行该命令。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="1c2b9-104">This sample shows how to create a default initial session state, how to add a cmdlet to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), how to create a runspace that uses the initial session state, and how to run the command by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c2b9-105">要求</span><span class="sxs-lookup"><span data-stu-id="1c2b9-105">Requirements</span></span>

<span data-ttu-id="1c2b9-106">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1c2b9-107">演示</span><span class="sxs-lookup"><span data-stu-id="1c2b9-107">Demonstrates</span></span>

<span data-ttu-id="1c2b9-108">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-108">This sample demonstrates the following.</span></span>

- <span data-ttu-id="1c2b9-109">创建 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-109">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="1c2b9-110">添加由主机应用程序定义的 cmdlet () 到 [System.Management.Automation.Runspaces.Ini的 tialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-110">Adding a cmdlet (defined by the Host application) to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="1c2b9-111">创建使用对象的 [system.object 工作空间](/dotnet/api/System.Management.Automation.Runspaces.Runspace) 对象。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-111">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the object.</span></span>

- <span data-ttu-id="1c2b9-112">创建使用 "system.servicemodel.[管理](/dotnet/api/System.Management.Automation.Runspaces.Runspace)" 对象的 "[管理](/dotnet/api/system.management.automation.powershell)对象" 对象。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-112">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>

- <span data-ttu-id="1c2b9-113">将命令添加到 [system.web](/dotnet/api/system.management.automation.powershell) 对象的管道。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-113">Adding the command to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="1c2b9-114">从命令返回的 [system.object](/dotnet/api/System.Management.Automation.PSObject) 对象中提取属性。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-114">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="1c2b9-115">示例</span><span class="sxs-lookup"><span data-stu-id="1c2b9-115">Example</span></span>

<span data-ttu-id="1c2b9-116">此示例将创建一个运行空间，该运行空间使用 [System.Management.Automation.Runspaces.Ini的 tialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象来定义打开运行空间时可用的元素。</span><span class="sxs-lookup"><span data-stu-id="1c2b9-116">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="1c2b9-117">在此示例中，由主机应用) 程序定义的 Get-Proc cmdlet (已添加到初始会话状态，该 cmdlet 通过使用[system.exception 对象进行同步运行。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="1c2b9-117">In this sample, the Get-Proc cmdlet (defined by the Host application) is added to the initial session state, and the cmdlet is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Diagnostics;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  #region GetProcCommand

  /// <summary>
  /// Class that implements the GetProcCommand.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Cmdlet Overrides

    /// <summary>
    /// For each of the requested process names, retrieve and write
    /// the associated processes.
    /// </summary>
    protected override void ProcessRecord()
    {
      // Get the current processes.
      Process[] processes = Process.GetProcesses();

      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument (true) tells the
      // system to enumerate the array, and send one process object
      // at a time to the pipeline.
      WriteObject(processes, true);
    }

    #endregion Overrides
  } // End GetProcCommand class.

  #endregion GetProcCommand

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace10
  {
    /// <summary>
    /// This sample shows how to create a default initial session state, how to add
    /// add a cmdlet to the InitialSessionState object, and then how to create
    /// a Runspace object.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// This sample demonstrates:
    /// 1. Creating an InitialSessionState object.
    /// 2. Adding a cmdlet to the InitialSessionState object.
    /// 3. Creating a runspace that uses the InitialSessionState object.
    /// 4. Creating a PowerShell object that uses the Runspace object.
    /// 5. Running the added command synchronously.
    /// 6. Working with PSObject objects to extract properties
    ///    from the objects returned by the pipeline.
    private static void Main(string[] args)
    {
      // Create a default InitialSessionState object. The default
      // InitialSessionState object contains all the elements provided
      // by Windows PowerShell.
      InitialSessionState iss = InitialSessionState.CreateDefault();

      // Add the get-proc cmdlet to the InitialSessionState object.
      SessionStateCmdletEntry ssce = new SessionStateCmdletEntry("get-proc", typeof(GetProcCommand), null);
      iss.Commands.Add(ssce);

      // Create a Runspace object that uses the InitialSessionState object.
      // Notice that no PSHost object is specified, so the default host is used.
      // See the Hosting samples for information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Add the get-proc cmdlet to the pipeline of the PowerShell object.
          powershell.AddCommand("get-proc");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the output of the pipeline.
          foreach (PSObject result in results)
          {
             Console.WriteLine(
                               "{0,-20} {1}",
                               result.Members["ProcessName"].Value,
                               result.Members["HandleCount"].Value);
          }
        }

        // Close the runspace to release resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="1c2b9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2b9-118">See Also</span></span>

[<span data-ttu-id="1c2b9-119">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="1c2b9-119">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
