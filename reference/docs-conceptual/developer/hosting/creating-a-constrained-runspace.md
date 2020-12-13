---
ms.date: 09/13/2016
ms.topic: reference
title: 创建受限运行空间
description: 创建受限运行空间
ms.openlocfilehash: 53fee3cc7d8625425bc6a73196aee9eee7f17ed6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651169"
---
# <a name="creating-a-constrained-runspace"></a>创建受限运行空间

出于性能或安全方面的考虑，可能需要限制可用于主机应用程序的 Windows PowerShell 命令。 为此，可以通过调用System.Management.Automation.Runspaces.Initialsessionstate 创建一个空的 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) [ 。Create *](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method，然后仅添加所需的命令。

 使用仅加载您指定的命令的运行空间可显著提高性能。

 你可以使用 [Sessionstatecmdletentry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) 类的方法来定义初始会话状态的 cmdlet）。

 你还可以将命令设置为私有。 专用命令可由主机应用程序使用，但不能由应用程序的用户使用。

## <a name="adding-commands-to-an-empty-runspace"></a>将命令添加到空的运行空间

 下面的示例演示如何创建一个空的 InitialSessionState 并向其中添加命令。

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using Microsoft.PowerShell.Commands;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class Runspace10b
  {
    /// <summary>
    /// This sample shows how to create an empty initial session state,
    /// how to add commands to the session state, and then how to create a
    /// runspace that has only those two commands. A PowerShell object
    /// is used to run the Get-Command cmdlet to show that only two commands
    /// are available.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    private static void Main(string[] args)
    {
      // Create an empty InitialSessionState and then add two commands.
      InitialSessionState iss = InitialSessionState.Create();

      // Add the Get-Process and Get-Command cmdlets to the session state.
      SessionStateCmdletEntry ssce1 = new SessionStateCmdletEntry(
                                                            "get-process",
                                                            typeof(GetProcessCommand),
                                                            null);
      iss.Commands.Add(ssce1);

      SessionStateCmdletEntry ssce2 = new SessionStateCmdletEntry(
                                                            "get-command",
                                                            typeof(GetCommandCommand),
                                                            null);
      iss.Commands.Add(ssce2);

      // Create a runspace.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();
        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Create a pipeline with the Get-Command command.
          powershell.AddCommand("get-command");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Verb                 Noun");
          Console.WriteLine("----------------------------");

          // Display each result object.
          foreach (PSObject result in results)
          {
            Console.WriteLine(
                             "{0,-20} {1}",
                             result.Members["verb"].Value,
                             result.Members["Noun"].Value);
          }
        }

        // Close the runspace and release any resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="making-commands-private"></a>使命令私有

 你还可以通过将命令的 [Commandinfo](/dotnet/api/System.Management.Automation.CommandInfo.Visibility) 属性设置为 private，使其成为私有命令。 [SessionStateEntryVisibility](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility) **私有**。 宿主应用程序和其他命令可以调用该命令，但应用程序的用户不能。 在下面的示例中， [get-childitem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) 命令是私有的。

```csharp
defaultSessionState = InitialSessionState.CreateDefault();
commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;

this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
this.runspace.Open();
```

## <a name="see-also"></a>另请参阅

 [创建 InitialSessionState](./creating-an-initialsessionstate.md)
