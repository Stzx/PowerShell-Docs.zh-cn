---
ms.date: 09/13/2016
ms.topic: reference
title: Runspace06 示例
description: Runspace06 示例
ms.openlocfilehash: 39841478f115eda089e4d4b1f822954b6ba7d09b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657671"
---
# <a name="runspace06-sample"></a><span data-ttu-id="adde7-103">Runspace06 示例</span><span class="sxs-lookup"><span data-stu-id="adde7-103">Runspace06 Sample</span></span>

<span data-ttu-id="adde7-104">此示例演示如何将模块添加到 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象，以便在打开运行空间时加载模块。</span><span class="sxs-lookup"><span data-stu-id="adde7-104">This sample shows how to add a module to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the module is loaded when the runspace is opened.</span></span> <span data-ttu-id="adde7-105">该模块提供了一个 Get-Proc cmdlet (由[GetProcessSample02 示例](../cmdlet/getprocesssample02-sample.md)) 定义，该示例通过使用[system.exception 对象进行同步。](/dotnet/api/system.management.automation.powershell)</span><span class="sxs-lookup"><span data-stu-id="adde7-105">The module provides a Get-Proc cmdlet (defined by the [GetProcessSample02 Sample](../cmdlet/getprocesssample02-sample.md)) that is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="adde7-106">要求</span><span class="sxs-lookup"><span data-stu-id="adde7-106">Requirements</span></span>

<span data-ttu-id="adde7-107">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="adde7-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="adde7-108">演示</span><span class="sxs-lookup"><span data-stu-id="adde7-108">Demonstrates</span></span>

<span data-ttu-id="adde7-109">此示例演示以下各项。</span><span class="sxs-lookup"><span data-stu-id="adde7-109">This sample demonstrates the following.</span></span>

- <span data-ttu-id="adde7-110">创建 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。</span><span class="sxs-lookup"><span data-stu-id="adde7-110">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="adde7-111">将模块添加到 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。</span><span class="sxs-lookup"><span data-stu-id="adde7-111">Adding the module to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="adde7-112">创建使用[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象的[system.object 工作空间](/dotnet/api/System.Management.Automation.Runspaces.Runspace)对象。</span><span class="sxs-lookup"><span data-stu-id="adde7-112">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="adde7-113">创建使用运行空间的 [system.web](/dotnet/api/system.management.automation.powershell) 对象。</span><span class="sxs-lookup"><span data-stu-id="adde7-113">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the runspace.</span></span>

- <span data-ttu-id="adde7-114">将模块的进程 cmdlet 添加到 [系统管理](/dotnet/api/system.management.automation.powershell) 对象的管道。</span><span class="sxs-lookup"><span data-stu-id="adde7-114">Adding the module's get-proc cmdlet to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="adde7-115">同步运行命令。</span><span class="sxs-lookup"><span data-stu-id="adde7-115">Running the command synchronously.</span></span>

- <span data-ttu-id="adde7-116">从命令返回的 [system.object](/dotnet/api/System.Management.Automation.PSObject) 对象中提取属性。</span><span class="sxs-lookup"><span data-stu-id="adde7-116">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="adde7-117">示例</span><span class="sxs-lookup"><span data-stu-id="adde7-117">Example</span></span>

<span data-ttu-id="adde7-118">此示例将创建一个运行空间，该运行空间使用 [System.Management.Automation.Runspaces.Ini的 tialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象来定义打开运行空间时可用的元素。</span><span class="sxs-lookup"><span data-stu-id="adde7-118">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="adde7-119">在此示例中，将一个定义 Get-Proc cmdlet 的模块添加到初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="adde7-119">In this sample, a module that defines a Get-Proc cmdlet is added to the initial session state.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace06
  {
    /// <summary>
    /// This sample shows how to define an initial session state that is
    /// used when creating a runspace. The sample invokes a command from
    /// a binary module that is loaded by the initial session state.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample assumes that user has coppied the GetProcessSample02.dll
    /// that is produced by the GetProcessSample02 sample to the current
    /// directory.
    /// This sample demonstrates the following:
    /// 1. Creating a default initial session state.
    /// 2. Adding a module to the initial session state.
    /// 3. Creating a runspace that uses the initial session state.
    /// 4. Creating a PowerShell object that uses the runspace.
    /// 5. Adding the module's get-proc cmdlet to the PowerShell object.
    /// 6. Running the command synchronously.
    /// 7. Using PSObject objects to extract and display properties from
    ///    the objects returned by the cmdlet.
    /// </remarks>
    private static void Main(string[] args)
    {
        // Create the default initial session state and add the module.
      InitialSessionState iss = InitialSessionState.CreateDefault();
      iss.ImportPSModule(new string[] { @".\GetProcessSample02.dll" });

      // Create a runspace. Notice that no PSHost object is supplied to the
      // CreateRunspace method so the default host is used. See the Host
      // samples for more information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        // Create a PowerShell object.
        using (PowerShell powershell = PowerShell.Create())
        {
          // Add the cmdlet and specify the runspace.
          powershell.AddCommand(@"GetProcessSample02\get-proc");
          powershell.Runspace = myRunSpace;

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the results.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                              "{0,-20} {1}",
                              result.Members["ProcessName"].Value,
                              result.Members["HandleCount"].Value);
          }
        }

        // Close the runspace to release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="adde7-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adde7-120">See Also</span></span>

[<span data-ttu-id="adde7-121">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="adde7-121">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
