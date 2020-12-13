---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell01 示例
description: Windows PowerShell01 示例
ms.openlocfilehash: 70ae67bfc2da9d3cc085ecb42de9cef4b163418d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657373"
---
# <a name="windows-powershell01-sample"></a><span data-ttu-id="28632-103">Windows PowerShell01 示例</span><span class="sxs-lookup"><span data-stu-id="28632-103">Windows PowerShell01 Sample</span></span>

<span data-ttu-id="28632-104">此示例演示如何使用 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象来限制运行空间的功能。</span><span class="sxs-lookup"><span data-stu-id="28632-104">This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="28632-105">此示例的输出演示如何限制运行空间的语言模式，如何将 cmdlet 标记为私有，如何添加和删除 cmdlet 和提供程序，如何添加代理命令等。</span><span class="sxs-lookup"><span data-stu-id="28632-105">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span> <span data-ttu-id="28632-106">此示例重点介绍如何以编程方式限制运行空间。</span><span class="sxs-lookup"><span data-stu-id="28632-106">This sample concentrates on how to restrict the runspace programmatically.</span></span> <span data-ttu-id="28632-107">用于限制运行空间的脚本替代方法包括 $ExecutionContext. LanguageMode 和 Set-pssessionconfiguration 命令。</span><span class="sxs-lookup"><span data-stu-id="28632-107">Scripting alternatives to restricting the runspace include the $ExecutionContext.SessionState.LanguageMode and PSSessionConfiguration commands.</span></span>

## <a name="requirements"></a><span data-ttu-id="28632-108">要求</span><span class="sxs-lookup"><span data-stu-id="28632-108">Requirements</span></span>

<span data-ttu-id="28632-109">此示例需要 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="28632-109">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="28632-110">演示</span><span class="sxs-lookup"><span data-stu-id="28632-110">Demonstrates</span></span>

<span data-ttu-id="28632-111">此示例对下列内容进行了说明：</span><span class="sxs-lookup"><span data-stu-id="28632-111">This sample demonstrates the following:</span></span>

- <span data-ttu-id="28632-112">通过设置System.Management.Automation.Runspaces.Initialsessionstate 来限制语言 [ 。Languagemode](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.LanguageMode) 属性。</span><span class="sxs-lookup"><span data-stu-id="28632-112">Restricting the language by setting the [System.Management.Automation.Runspaces.Initialsessionstate.Languagemode](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.LanguageMode) property.</span></span>

- <span data-ttu-id="28632-113">通过使用 Sessionstatealiasentry，将别名添加到初始会话状态 [？Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateAliasEntry) 对象。</span><span class="sxs-lookup"><span data-stu-id="28632-113">Adding aliases to the initial session state by using a [System.Management.Automation.Runspaces.Sessionstatealiasentry?Displayproperty=Fullname](/dotnet/api/System.Management.Automation.Runspaces.SessionStateAliasEntry) object.</span></span>

- <span data-ttu-id="28632-114">将命令标记为私有。</span><span class="sxs-lookup"><span data-stu-id="28632-114">Marking commands as private.</span></span>

- <span data-ttu-id="28632-115">使用System.Management.Automation.Runspaces.Initialsessionstate 从初始会话状态中删除提供程序 [ 。Providers](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Providers) 属性。</span><span class="sxs-lookup"><span data-stu-id="28632-115">Removing providers from the initial session state by using the [System.Management.Automation.Runspaces.Initialsessionstate.Providers](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Providers) property.</span></span>

- <span data-ttu-id="28632-116">使用 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Commands) 属性从初始会话状态删除命令。</span><span class="sxs-lookup"><span data-stu-id="28632-116">Removing commands from the initial session state by using the [System.Management.Automation.Runspaces.Initialsessionstate.Commands](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Commands) property.</span></span>

- <span data-ttu-id="28632-117">将命令和提供程序添加到 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。</span><span class="sxs-lookup"><span data-stu-id="28632-117">Adding commands and providers to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

## <a name="example"></a><span data-ttu-id="28632-118">示例</span><span class="sxs-lookup"><span data-stu-id="28632-118">Example</span></span>

<span data-ttu-id="28632-119">此示例显示了几种限制运行空间功能的方法。</span><span class="sxs-lookup"><span data-stu-id="28632-119">This sample shows several ways to limit the functionality of a runspace.</span></span>

```csharp
namespace Sample
{
  using System;
  using System.Collections.ObjectModel;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;

  /// <summary>
  /// This class contains the Main entry point for the application.
  /// </summary>
  internal class PowerShell01
  {
    /// <summary>
    /// The runspace used to run commands.
    /// </summary>
    private Runspace runspace;

    /// <summary>
    /// Return the first index of the entry in <paramref name="entries"/>
    /// with the name <paramref name="name"/>. Return -1 if it is not found.
    /// </summary>
    /// <typeparam name="T">Type of ConstrainedSessionStateEntry</typeparam>
    /// <param name="entries">Collection of entries to search for <paramref name="name"/> in.</param>
    /// <param name="name">Named of the entry we are looking for</param>
    /// <returns>
    /// The first index of the entry in <paramref name="entries"/> with the
    /// name <paramref name="name"/>, or return -1 if it is not found.
    /// </returns>
    private static int GetIndexOfEntry<T>(
            InitialSessionStateEntryCollection<T> entries,
            string name) where T : ConstrainedSessionStateEntry
    {
      int foundIndex = 0;
      foreach (T entry in entries)
      {
        if (entry.Name.Equals(name, StringComparison.OrdinalIgnoreCase))
        {
          return foundIndex;
        }

        foundIndex++;
      }

      return -1;
    }

    /// <summary>
    /// Run commands to demonstrate the ways to constrain the runspace.
    /// </summary>
    /// <param name="args">This parameter is unused.</param>
    private static void Main(string[] args)
    {
      new PowerShell01().RunCommands();
    }

    /// <summary>
    /// Run a script to display the results and errors.
    /// </summary>
    /// <param name="script">Script to be run.</param>
    /// <param name="scriptComment">Comment to be printed about
    /// the script.</param>
    private void RunScript(string script, string scriptComment)
    {
      Console.WriteLine("Running '{0}'\n{1}.\n\nPowerShell Output:", script, scriptComment);

      // Using a PowerShell object, create a pipeline, add the script to the
      //  pipeline, and specify the runspace where the pipeline is invoked.
      PowerShell powerShellCommand = PowerShell.Create();
      powerShellCommand.AddScript(script);
      powerShellCommand.Runspace = this.runspace;

      try
      {
        Collection<PSObject> results = powerShellCommand.Invoke();

        // Display the results.
        foreach (PSObject result in results)
        {
          Console.WriteLine(result);
        }

        // Display any non-terminating errors.
        foreach (ErrorRecord error in powerShellCommand.Streams.Error)
        {
          Console.WriteLine("PowerShell Error: {0}", error);
        }
      }
      catch (RuntimeException ex)
      {
        Console.WriteLine("PowerShell Error: {0}", ex.Message);
        Console.WriteLine();
      }

      Console.WriteLine("\n-----------------------------\n");
    }

    /// <summary>
    /// Run some commands to demonstrate the script capabilities.
    /// </summary>
    private void RunCommands()
    {
      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.Open();
      this.RunScript("$a=0;$a", "Assigning to a variable will work for a default InitialSessionState");
      this.runspace.Close();

      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.InitialSessionState.LanguageMode = PSLanguageMode.RestrictedLanguage;
      this.runspace.Open();
      this.RunScript("$a=0;$a", "Assigning to a variable will not work in RestrictedLanguage LanguageMode");
      this.runspace.Close();

      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.InitialSessionState.LanguageMode = PSLanguageMode.NoLanguage;
      this.runspace.Open();
      this.RunScript("10/2", "A script will not work in NoLanguage LanguageMode.");
      this.runspace.Close();

      this.runspace = RunspaceFactory.CreateRunspace(InitialSessionState.CreateDefault());
      this.runspace.Open();
      string scriptComment = "get-childitem with a default InitialSessionState will work since the standard \n" +
           "PowerShell cmdlets are included in the default InitialSessionState";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      InitialSessionState defaultSessionState = InitialSessionState.CreateDefault();
      defaultSessionState.Commands.Add(new SessionStateAliasEntry("dir2", "get-childitem"));
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      this.RunScript("dir2", "An alias, like dir2, can be added to InitialSessionState");
      this.runspace.Close();

      defaultSessionState = InitialSessionState.CreateDefault();
      int commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
      defaultSessionState.Commands.RemoveItem(commandIndex);
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      scriptComment = "get-childitem was removed from the list of commands so it\nwill no longer be found";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      defaultSessionState = InitialSessionState.CreateDefault();
      defaultSessionState.Providers.Clear();
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      this.RunScript("get-childitem", "There are no providers so get-childitem will not work");
      this.runspace.Close();

      // Marks a command as private, and then defines a proxy command
      // that uses the private command.  One reason to define a proxy for
      // a command is to remove a parameter of the original command.
      // For a more complete sample of a proxy command, see the Runspace11
      // sample.
      defaultSessionState = InitialSessionState.CreateDefault();
      commandIndex = GetIndexOfEntry(defaultSessionState.Commands, "get-childitem");
      defaultSessionState.Commands[commandIndex].Visibility = SessionStateEntryVisibility.Private;
      CommandMetadata getChildItemMetadata = new CommandMetadata(
           typeof(Microsoft.PowerShell.Commands.GetChildItemCommand));
      getChildItemMetadata.Parameters.Remove("Recurse");
      string getChildItemBody = ProxyCommand.Create(getChildItemMetadata);
      defaultSessionState.Commands.Add(new SessionStateFunctionEntry("get-childitem2", getChildItemBody));
      this.runspace = RunspaceFactory.CreateRunspace(defaultSessionState);
      this.runspace.Open();
      this.RunScript("get-childitem", "get-childitem is private so it will not be available");
      scriptComment = "get-childitem2 is a proxy to get-childitem. \n" +
                    "It works even when get-childitem is private.";
      this.RunScript("get-childitem2", scriptComment);
      scriptComment = "This will fail. Unlike get-childitem, get-childitem2 does not have -Recurse";
      this.RunScript("get-childitem2 -Recurse", scriptComment);

      InitialSessionState cleanSessionState = InitialSessionState.Create();
      this.runspace = RunspaceFactory.CreateRunspace(cleanSessionState);
      this.runspace.Open();
      scriptComment = "A script will not work because \n" +
                   "InitialSessionState.Create() will have the default LanguageMode of NoLanguage";
      this.RunScript("10/2", scriptComment);
      this.runspace.Close();

      cleanSessionState = InitialSessionState.Create();
      cleanSessionState.LanguageMode = PSLanguageMode.FullLanguage;
      this.runspace = RunspaceFactory.CreateRunspace(cleanSessionState);
      this.runspace.Open();
      scriptComment = "get-childitem, standard cmdlets and providers are not present \n" +
                   "in an InitialSessionState returned from InitialSessionState.Create()";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      cleanSessionState = InitialSessionState.Create();
      cleanSessionState.Commands.Add(
                new SessionStateCmdletEntry(
                    "Get-ChildItem",
                    typeof(Microsoft.PowerShell.Commands.GetChildItemCommand),
                    null));
      cleanSessionState.Providers.Add(
                new SessionStateProviderEntry(
                    "FileSystem",
                    typeof(Microsoft.PowerShell.Commands.FileSystemProvider),
                    null));
      cleanSessionState.LanguageMode = PSLanguageMode.FullLanguage;
      this.runspace = RunspaceFactory.CreateRunspace(cleanSessionState);
      this.runspace.Open();
      scriptComment = "get-childitem and the FileSystem provider were explicitly added\n" +
                "so get-childitem will work";
      this.RunScript("get-childitem", scriptComment);
      this.runspace.Close();

      Console.Write("Done...");
      Console.ReadLine();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="28632-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28632-120">See Also</span></span>

[<span data-ttu-id="28632-121">编写 Windows PowerShell 主机应用程序</span><span class="sxs-lookup"><span data-stu-id="28632-121">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
