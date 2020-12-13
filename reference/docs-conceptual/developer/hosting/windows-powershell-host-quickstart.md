---
ms.date: 09/12/2016
ms.topic: reference
title: Windows PowerShell 主机快速入门
description: Windows PowerShell 主机快速入门
ms.openlocfilehash: 4cb7dae60342abb40bd7a989a27a692826b360e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657420"
---
# <a name="windows-powershell-host-quickstart"></a><span data-ttu-id="1274a-103">Windows PowerShell 主机快速入门</span><span class="sxs-lookup"><span data-stu-id="1274a-103">Windows PowerShell Host Quickstart</span></span>

<span data-ttu-id="1274a-104">若要在应用程序中托管 Windows PowerShell，请使用 [system.web](/dotnet/api/System.Management.Automation.PowerShell) 类。</span><span class="sxs-lookup"><span data-stu-id="1274a-104">To host Windows PowerShell in your application, you use the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class.</span></span>
<span data-ttu-id="1274a-105">此类提供创建命令管道，然后在运行空间中执行这些命令的方法。</span><span class="sxs-lookup"><span data-stu-id="1274a-105">This class provides methods that create a pipeline of commands and then execute those commands in a runspace.</span></span>
<span data-ttu-id="1274a-106">创建主机应用程序的最简单方法是使用默认的运行空间。</span><span class="sxs-lookup"><span data-stu-id="1274a-106">The simplest way to create a host application is to use the default runspace.</span></span>
<span data-ttu-id="1274a-107">默认运行空间包含所有核心 Windows PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="1274a-107">The default runspace contains all of the core Windows PowerShell commands.</span></span>
<span data-ttu-id="1274a-108">如果希望应用程序仅公开部分 Windows PowerShell 命令，则必须创建自定义运行空间。</span><span class="sxs-lookup"><span data-stu-id="1274a-108">If you want your application to expose only a subset of the Windows PowerShell commands, you must create a custom runspace.</span></span>

## <a name="using-the-default-runspace"></a><span data-ttu-id="1274a-109">使用默认运行空间</span><span class="sxs-lookup"><span data-stu-id="1274a-109">Using the default runspace</span></span>

<span data-ttu-id="1274a-110">首先，我们将使用默认的运行空间，并使用 [system.web](/dotnet/api/System.Management.Automation.PowerShell) 类的方法向管道添加命令、参数、语句和脚本。</span><span class="sxs-lookup"><span data-stu-id="1274a-110">To start, we'll use the default runspace, and use the methods of the [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) class to add commands, parameters, statements, and scripts to a pipeline.</span></span>

### <a name="addcommand"></a><span data-ttu-id="1274a-111">AddCommand</span><span class="sxs-lookup"><span data-stu-id="1274a-111">AddCommand</span></span>

<span data-ttu-id="1274a-112">您可以使用 [AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) 方法将命令添加到管道中。</span><span class="sxs-lookup"><span data-stu-id="1274a-112">You use the [System.Management.Automation.Powershell.AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) method to add commands to the pipeline.</span></span>
<span data-ttu-id="1274a-113">例如，假设您希望获取计算机上正在运行的进程的列表。</span><span class="sxs-lookup"><span data-stu-id="1274a-113">For example, suppose you want to get the list of running processes on the machine.</span></span>
<span data-ttu-id="1274a-114">运行此命令的方法如下所示。</span><span class="sxs-lookup"><span data-stu-id="1274a-114">The way to run this command is as follows.</span></span>

1. <span data-ttu-id="1274a-115">创建一个 " [管理](/dotnet/api/System.Management.Automation.PowerShell) " 对象。</span><span class="sxs-lookup"><span data-stu-id="1274a-115">Create a [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) object.</span></span>

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. <span data-ttu-id="1274a-116">添加要执行的命令。</span><span class="sxs-lookup"><span data-stu-id="1274a-116">Add the command that you want to execute.</span></span>

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. <span data-ttu-id="1274a-117">调用命令。</span><span class="sxs-lookup"><span data-stu-id="1274a-117">Invoke the command.</span></span>

   ```csharp
   ps.Invoke();
   ```

<span data-ttu-id="1274a-118">如果在调用 [AddCommand 方法之前](/dotnet/api/System.Management.Automation.PowerShell.Invoke) 多次调用了方法，则第一个命令的结果将通过管道传递到第二个命令，依此类推。</span><span class="sxs-lookup"><span data-stu-id="1274a-118">If you call the AddCommand method more than once before you call the [System.Management.Automation.Powershell.Invoke](/dotnet/api/System.Management.Automation.PowerShell.Invoke) method, the result of the first command is piped to the second, and so on.</span></span>
<span data-ttu-id="1274a-119">如果你不想通过管道将前一个命令的结果传递给命令，请改为通过调用 [AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) 来添加它。</span><span class="sxs-lookup"><span data-stu-id="1274a-119">If you do not want to pipe the result of a previous command to a command, add it by calling the [System.Management.Automation.Powershell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) instead.</span></span>

### <a name="addparameter"></a><span data-ttu-id="1274a-120">AddParameter</span><span class="sxs-lookup"><span data-stu-id="1274a-120">AddParameter</span></span>

<span data-ttu-id="1274a-121">前面的示例执行一个不带任何参数的命令。</span><span class="sxs-lookup"><span data-stu-id="1274a-121">The previous example executes a single command without any parameters.</span></span>
<span data-ttu-id="1274a-122">可以使用 [PSCommand. AddParameter](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) 方法将参数添加到命令中。</span><span class="sxs-lookup"><span data-stu-id="1274a-122">You can add parameters to the command by using the [System.Management.Automation.PSCommand.AddParameter](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) method.</span></span>
<span data-ttu-id="1274a-123">例如，下面的代码获取在计算机上运行的所有名为的进程的列表 `PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="1274a-123">For example, the following code gets a list of all of the processes that are named `PowerShell` running on the machine.</span></span>

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

<span data-ttu-id="1274a-124">可以通过重复调用 AddParameter 方法来添加其他参数。</span><span class="sxs-lookup"><span data-stu-id="1274a-124">You can add additional parameters by calling the AddParameter method repeatedly.</span></span>

```csharp                   
PowerShell.Create().AddCommand("Get-ChildItem")
                   .AddParameter("Path", @"c:\Windows")
                   .AddParameter("Filter", "*.exe")
                   .Invoke();
```

<span data-ttu-id="1274a-125">你还可以通过调用 [AddParameters](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) 方法来添加参数名称和值的字典。</span><span class="sxs-lookup"><span data-stu-id="1274a-125">You can also add a dictionary of parameter names and values by calling the [System.Management.Automation.PowerShell.AddParameters](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) method.</span></span>

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Path", @"c:\Windows");
parameters.Add("Filter", "*.exe");

PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a><span data-ttu-id="1274a-126">AddStatement</span><span class="sxs-lookup"><span data-stu-id="1274a-126">AddStatement</span></span>

<span data-ttu-id="1274a-127">您可以使用 [AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) 方法来模拟批处理，该方法将附加语句添加到管道的末尾。</span><span class="sxs-lookup"><span data-stu-id="1274a-127">You can simulate batching by using the [System.Management.Automation.PowerShell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) method, which adds an additional statement to the end of the pipeline.</span></span>
<span data-ttu-id="1274a-128">下面的代码获取名为的正在运行的进程的列表 `PowerShell` ，然后获取正在运行的服务的列表。</span><span class="sxs-lookup"><span data-stu-id="1274a-128">The following code gets a list of running processes with the name `PowerShell`, and then gets the list of running services.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a><span data-ttu-id="1274a-129">AddScript</span><span class="sxs-lookup"><span data-stu-id="1274a-129">AddScript</span></span>

<span data-ttu-id="1274a-130">您可以通过调用 [AddScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) 方法来运行现有的脚本。</span><span class="sxs-lookup"><span data-stu-id="1274a-130">You can run an existing script by calling the [System.Management.Automation.PowerShell.AddScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) method.</span></span>
<span data-ttu-id="1274a-131">下面的示例向管道添加一个脚本并运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="1274a-131">The following example adds a script to the pipeline and runs it.</span></span>
<span data-ttu-id="1274a-132">此示例假定在名为的文件夹中已有一个名为的脚本 `MyScript.ps1` `D:\PSScripts` 。</span><span class="sxs-lookup"><span data-stu-id="1274a-132">This example assumes there is already a script named `MyScript.ps1` in a folder named `D:\PSScripts`.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

<span data-ttu-id="1274a-133">还有一个 AddScript 方法版本，该方法采用名为的布尔参数 `useLocalScope` 。</span><span class="sxs-lookup"><span data-stu-id="1274a-133">There is also a version of the AddScript method that takes a boolean parameter named `useLocalScope`.</span></span>
<span data-ttu-id="1274a-134">如果将此参数设置为 `true` ，则脚本将在本地作用域中运行。</span><span class="sxs-lookup"><span data-stu-id="1274a-134">If this parameter is set to `true`, then the script is run in the local scope.</span></span>
<span data-ttu-id="1274a-135">以下代码将在本地作用域中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="1274a-135">The following code will run the script in the local scope.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a><span data-ttu-id="1274a-136">创建自定义运行空间</span><span class="sxs-lookup"><span data-stu-id="1274a-136">Creating a custom runspace</span></span>

<span data-ttu-id="1274a-137">虽然前面的示例中使用的默认运行空间加载了所有核心 Windows PowerShell 命令，但你可以创建一个自定义的运行空间，该运行空间仅加载指定的所有命令子集。</span><span class="sxs-lookup"><span data-stu-id="1274a-137">While the default runspace used in the previous examples loads all of the core Windows PowerShell commands, you can create a custom runspace that loads only a specified subset of all commands.</span></span>
<span data-ttu-id="1274a-138">你可能想要执行此操作来提高性能 (加载更多命令) 性能下降或限制用户执行操作的能力。</span><span class="sxs-lookup"><span data-stu-id="1274a-138">You might want to do this to improve performance (loading a larger number of commands is a performance hit), or to restrict the capability of the user to perform operations.</span></span>
<span data-ttu-id="1274a-139">仅公开有限数量的命令的运行空间称为受限制的运行空间。</span><span class="sxs-lookup"><span data-stu-id="1274a-139">A runspace that exposes only a limited number of commands is called a constrained runspace.</span></span>
<span data-ttu-id="1274a-140">若要创建受限制的 [运行空间，](/dotnet/api/System.Management.Automation.Runspaces.Runspace) 请使用 [ tialSessionState 和System.Management.Automation.Runspaces.Ini](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 的类。</span><span class="sxs-lookup"><span data-stu-id="1274a-140">To create a constrained runspace, you use the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) and [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) classes.</span></span>

### <a name="creating-an-initialsessionstate-object"></a><span data-ttu-id="1274a-141">创建 InitialSessionState 对象</span><span class="sxs-lookup"><span data-stu-id="1274a-141">Creating an InitialSessionState object</span></span>

<span data-ttu-id="1274a-142">若要创建自定义运行空间，必须首先创建一个 [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象。</span><span class="sxs-lookup"><span data-stu-id="1274a-142">To create a custom runspace, you must first create an [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>
<span data-ttu-id="1274a-143">在下面的示例中，我们将使用 [RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) 来创建默认的 InitialSessionState 对象之后的运行空间。</span><span class="sxs-lookup"><span data-stu-id="1274a-143">In the following example, we use the [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) to create a runspace after creating a default InitialSessionState object.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a><span data-ttu-id="1274a-144">约束运行空间</span><span class="sxs-lookup"><span data-stu-id="1274a-144">Constraining the runspace</span></span>

<span data-ttu-id="1274a-145">在上面的示例中，我们创建了一个默认 [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象，该对象加载所有内置核心 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1274a-145">In the previous example, we created a default [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object that loads all of the built-in core Windows PowerShell.</span></span>
<span data-ttu-id="1274a-146">我们还可以调用 [System.Management.Automation.Runspaces.IniCreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) 方法来创建一个 InitialSessionState 对象，该对象只加载 tialSessionState 管理单元中的命令。</span><span class="sxs-lookup"><span data-stu-id="1274a-146">We could also have called the [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) method to create an InitialSessionState object that would load only the commands in the Microsoft.PowerShell.Core snapin.</span></span>
<span data-ttu-id="1274a-147">若要创建更受限制的运行空间，必须通过调用 [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) 方法创建一个空的 InitialSessionState 对象，然后将命令添加到 InitialSessionState。</span><span class="sxs-lookup"><span data-stu-id="1274a-147">To create a more constrained runspace, you must create an empty InitialSessionState object by calling the [System.Management.Automation.Runspaces.InitialSessionState.Create](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) method, and then add commands to the InitialSessionState.</span></span>

<span data-ttu-id="1274a-148">使用仅加载您指定的命令的运行空间可显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="1274a-148">Using a runspace that loads only the commands that you specify provides significantly improved performance.</span></span>

<span data-ttu-id="1274a-149">你可以使用 [SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) 类的方法来定义初始会话状态的 cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="1274a-149">You use the methods of the [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) class to define cmdlets for the initial session state.</span></span>
<span data-ttu-id="1274a-150">下面的示例创建一个空的初始会话状态，然后将和命令定义并添加 `Get-Command` `Import-Module` 到初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="1274a-150">The following example creates an empty initial session state, then defines and adds the `Get-Command` and `Import-Module` commands to the initial session state.</span></span>
<span data-ttu-id="1274a-151">然后创建一个受该初始会话状态约束的运行空间，并执行该运行空间中的命令。</span><span class="sxs-lookup"><span data-stu-id="1274a-151">We then create a runspace constrained by that initial session state, and execute the commands in that runspace.</span></span>

<span data-ttu-id="1274a-152">创建初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="1274a-152">Create the initial session state.</span></span>

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

<span data-ttu-id="1274a-153">定义命令并将其添加到初始会话状态。</span><span class="sxs-lookup"><span data-stu-id="1274a-153">Define and add commands to the initial session state.</span></span>

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

<span data-ttu-id="1274a-154">创建并打开运行空间。</span><span class="sxs-lookup"><span data-stu-id="1274a-154">Create and open the runspace.</span></span>

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

<span data-ttu-id="1274a-155">执行命令并显示结果。</span><span class="sxs-lookup"><span data-stu-id="1274a-155">Execute a command and show the result.</span></span>

```csharp
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
Collection<CommandInfo> result = ps.Invoke<CommandInfo>();
foreach (var entry in result)
{
       Console.WriteLine(entry.Name);
}
```

<span data-ttu-id="1274a-156">运行时，此代码的输出将如下所示。</span><span class="sxs-lookup"><span data-stu-id="1274a-156">When run, the output of this code will look as follows.</span></span>

```powershell
Get-Command
Import-Module
```
