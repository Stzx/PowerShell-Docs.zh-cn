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
# <a name="creating-a-constrained-runspace"></a><span data-ttu-id="83a1b-103">创建受限运行空间</span><span class="sxs-lookup"><span data-stu-id="83a1b-103">Creating a constrained runspace</span></span>

<span data-ttu-id="83a1b-104">出于性能或安全方面的考虑，可能需要限制可用于主机应用程序的 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="83a1b-104">For performance or security reasons, you might want to restrict the Windows PowerShell commands available to your host application.</span></span> <span data-ttu-id="83a1b-105">为此，可以通过调用System.Management.Automation.Runspaces.Initialsessionstate 创建一个空的 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) [ 。Create \*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method，然后仅添加所需的命令。</span><span class="sxs-lookup"><span data-stu-id="83a1b-105">To do this you create an empty [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) by calling the [System.Management.Automation.Runspaces.Initialsessionstate.Create\*](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add only the commands you want available.</span></span>

 <span data-ttu-id="83a1b-106">使用仅加载您指定的命令的运行空间可显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="83a1b-106">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

 <span data-ttu-id="83a1b-107">你可以使用 [Sessionstatecmdletentry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) 类的方法来定义初始会话状态的 cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="83a1b-107">You use the methods of the [System.Management.Automation.Runspaces.Sessionstatecmdletentry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span>

 <span data-ttu-id="83a1b-108">你还可以将命令设置为私有。</span><span class="sxs-lookup"><span data-stu-id="83a1b-108">You can also make commands private.</span></span> <span data-ttu-id="83a1b-109">专用命令可由主机应用程序使用，但不能由应用程序的用户使用。</span><span class="sxs-lookup"><span data-stu-id="83a1b-109">Private commands can be used by the host application, but not by users of the application.</span></span>

## <a name="adding-commands-to-an-empty-runspace"></a><span data-ttu-id="83a1b-110">将命令添加到空的运行空间</span><span class="sxs-lookup"><span data-stu-id="83a1b-110">Adding commands to an empty runspace</span></span>

 <span data-ttu-id="83a1b-111">下面的示例演示如何创建一个空的 InitialSessionState 并向其中添加命令。</span><span class="sxs-lookup"><span data-stu-id="83a1b-111">The following example demonstrates how to create an empty InitialSessionState and add commands to it.</span></span>

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

## <a name="making-commands-private"></a><span data-ttu-id="83a1b-112">使命令私有</span><span class="sxs-lookup"><span data-stu-id="83a1b-112">Making commands private</span></span>

 <span data-ttu-id="83a1b-113">你还可以通过将命令的 [Commandinfo](/dotnet/api/System.Management.Automation.CommandInfo.Visibility) 属性设置为 private，使其成为私有命令。 [SessionStateEntryVisibility](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility) **私有**。</span><span class="sxs-lookup"><span data-stu-id="83a1b-113">You can also make a command private, by setting it's [System.Management.Automation.Commandinfo.Visibility](/dotnet/api/System.Management.Automation.CommandInfo.Visibility) property to [System.Management.Automation.SessionStateEntryVisibility](/dotnet/api/System.Management.Automation.SessionStateEntryVisibility) **Private**.</span></span> <span data-ttu-id="83a1b-114">宿主应用程序和其他命令可以调用该命令，但应用程序的用户不能。</span><span class="sxs-lookup"><span data-stu-id="83a1b-114">The host application and other commands can call that command, but the user of the application cannot.</span></span> <span data-ttu-id="83a1b-115">在下面的示例中， [get-childitem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) 命令是私有的。</span><span class="sxs-lookup"><span data-stu-id="83a1b-115">In the following example, the [Get-ChildItem](/powershell/module/Microsoft.PowerShell.Management/Get-ChildItem) command is private.</span></span>

```csharp
defaultSessionState = InitialSessionState.CreateDefault();
commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;

this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
this.runspace.Open();
```

## <a name="see-also"></a><span data-ttu-id="83a1b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83a1b-116">See Also</span></span>

 [<span data-ttu-id="83a1b-117">创建 InitialSessionState</span><span class="sxs-lookup"><span data-stu-id="83a1b-117">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)
