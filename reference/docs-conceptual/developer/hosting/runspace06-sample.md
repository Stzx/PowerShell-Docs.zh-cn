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
# <a name="runspace06-sample"></a>Runspace06 示例

此示例演示如何将模块添加到 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象，以便在打开运行空间时加载模块。 该模块提供了一个 Get-Proc cmdlet (由[GetProcessSample02 示例](../cmdlet/getprocesssample02-sample.md)) 定义，该示例通过使用[system.exception 对象进行同步。](/dotnet/api/system.management.automation.powershell)

## <a name="requirements"></a>要求

此示例需要 Windows PowerShell 2.0。

## <a name="demonstrates"></a>演示

此示例演示以下各项。

- 创建 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。

- 将模块添加到 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。

- 创建使用[System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)对象的[system.object 工作空间](/dotnet/api/System.Management.Automation.Runspaces.Runspace)对象。

- 创建使用运行空间的 [system.web](/dotnet/api/system.management.automation.powershell) 对象。

- 将模块的进程 cmdlet 添加到 [系统管理](/dotnet/api/system.management.automation.powershell) 对象的管道。

- 同步运行命令。

- 从命令返回的 [system.object](/dotnet/api/System.Management.Automation.PSObject) 对象中提取属性。

## <a name="example"></a>示例

此示例将创建一个运行空间，该运行空间使用 [System.Management.Automation.Runspaces.Ini的 tialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象来定义打开运行空间时可用的元素。 在此示例中，将一个定义 Get-Proc cmdlet 的模块添加到初始会话状态。

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

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 主机应用程序](./writing-a-windows-powershell-host-application.md)
