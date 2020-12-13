---
ms.date: 09/13/2016
ms.topic: reference
title: 向 Cmdlet 添加参数集
description: 向 Cmdlet 添加参数集
ms.openlocfilehash: dd5ee2a880a4d516ea82e5afe0ced12369197243
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92648649"
---
# <a name="adding-parameter-sets-to-a-cmdlet"></a><span data-ttu-id="bfff3-103">向 Cmdlet 添加参数集</span><span class="sxs-lookup"><span data-stu-id="bfff3-103">Adding Parameter Sets to a Cmdlet</span></span>

## <a name="things-to-know-about-parameter-sets"></a><span data-ttu-id="bfff3-104">有关参数集的信息</span><span class="sxs-lookup"><span data-stu-id="bfff3-104">Things to Know About Parameter Sets</span></span>

<span data-ttu-id="bfff3-105">Windows PowerShell 将参数集定义为一组一起操作的参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-105">Windows PowerShell defines a parameter set as a group of parameters that operate together.</span></span> <span data-ttu-id="bfff3-106">通过对 cmdlet 的参数进行分组，可以创建单个 cmdlet，该 cmdlet 可以根据用户指定的参数组来更改其功能。</span><span class="sxs-lookup"><span data-stu-id="bfff3-106">By grouping the parameters of a cmdlet, you can create a single cmdlet that can change its functionality based on what group of parameters the user specifies.</span></span>

<span data-ttu-id="bfff3-107">Windows PowerShell 提供的 cmdlet 是使用两个参数集定义不同功能的 cmdlet 示例 `Get-EventLog` 。</span><span class="sxs-lookup"><span data-stu-id="bfff3-107">An example of a cmdlet that uses two parameter sets to define different functionalities is the `Get-EventLog` cmdlet that is provided by Windows PowerShell.</span></span> <span data-ttu-id="bfff3-108">当用户指定或参数时，此 cmdlet 将返回不同的信息 `List` `LogName` 。</span><span class="sxs-lookup"><span data-stu-id="bfff3-108">This cmdlet returns different information when the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="bfff3-109">如果 `LogName` 指定了参数，则该 cmdlet 将返回有关给定事件日志中的事件的信息。</span><span class="sxs-lookup"><span data-stu-id="bfff3-109">If the `LogName` parameter is specified, the cmdlet returns information about the events in a given event log.</span></span> <span data-ttu-id="bfff3-110">如果 `List` 指定了参数，则该 cmdlet 将返回有关日志文件本身的信息， (它们所包含的事件信息) 。</span><span class="sxs-lookup"><span data-stu-id="bfff3-110">If the `List` parameter is specified, the cmdlet returns information about the log files themselves (not the event information they contain).</span></span> <span data-ttu-id="bfff3-111">在这种情况下， `List` 和 `LogName` 参数标识两个单独的参数集。</span><span class="sxs-lookup"><span data-stu-id="bfff3-111">In this case, the `List` and `LogName` parameters identify two separate parameter sets.</span></span>

<span data-ttu-id="bfff3-112">有关参数集的两个重要事项是： Windows PowerShell 运行时仅对特定输入使用一个参数集，并且每个参数集必须至少有一个参数集唯一的参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-112">Two important things to remember about parameter sets is that the Windows PowerShell runtime uses only one parameter set for a particular input, and that each parameter set must have at least one parameter that is unique for that parameter set.</span></span>

<span data-ttu-id="bfff3-113">为了说明最后一点，此 Stop-Proc cmdlet 使用三个参数集： `ProcessName` 、 `ProcessId` 和 `InputObject` 。</span><span class="sxs-lookup"><span data-stu-id="bfff3-113">To illustrate that last point, this Stop-Proc cmdlet uses three parameter sets: `ProcessName`, `ProcessId`, and `InputObject`.</span></span> <span data-ttu-id="bfff3-114">其中每个参数集都具有一个不在其他参数集中的参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-114">Each of these parameter sets has one parameter that is not in the other parameter sets.</span></span> <span data-ttu-id="bfff3-115">参数集可能会共享其他参数，但该 cmdlet 使用唯一参数 `ProcessName` 、 `ProcessId` 和 `InputObject` 来确定 Windows PowerShell 运行时应使用的参数集。</span><span class="sxs-lookup"><span data-stu-id="bfff3-115">The parameter sets could share other parameters, but the cmdlet uses the unique parameters `ProcessName`, `ProcessId`, and `InputObject` to identify which set of parameters that the Windows PowerShell runtime should use.</span></span>

## <a name="declaring-the-cmdlet-class"></a><span data-ttu-id="bfff3-116">声明 Cmdlet 类</span><span class="sxs-lookup"><span data-stu-id="bfff3-116">Declaring the Cmdlet Class</span></span>

<span data-ttu-id="bfff3-117">创建 cmdlet 的第一步是始终命名 cmdlet 并声明实现 cmdlet 的 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="bfff3-117">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="bfff3-118">对于此 cmdlet，将使用生命周期谓词 "Stop"，因为该 cmdlet 将停止系统进程。</span><span class="sxs-lookup"><span data-stu-id="bfff3-118">For this cmdlet, the lifecycle verb "Stop" is used because the cmdlet stops system processes.</span></span> <span data-ttu-id="bfff3-119">之所以使用名词名称 "Proc"，是因为该 cmdlet 适用于进程。</span><span class="sxs-lookup"><span data-stu-id="bfff3-119">The noun name "Proc" is used because the cmdlet works on processes.</span></span> <span data-ttu-id="bfff3-120">请注意，在下面的声明中，cmdlet 谓词和名词名称反映在 cmdlet 类的名称中。</span><span class="sxs-lookup"><span data-stu-id="bfff3-120">In the declaration below, note that the cmdlet verb and noun name are reflected in the name of the cmdlet class.</span></span>

> [!NOTE]
> <span data-ttu-id="bfff3-121">有关已批准的 cmdlet 谓词名称的详细信息，请参阅 [Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="bfff3-121">For more information about approved cmdlet verb names, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="bfff3-122">下面的代码是此 Stop-Proc cmdlet 的类定义。</span><span class="sxs-lookup"><span data-stu-id="bfff3-122">The following code is the class definition for this Stop-Proc cmdlet.</span></span>

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        DefaultParameterSetName = "ProcessId",
        SupportsShouldProcess = true)]
public class StopProcCommand : PSCmdlet
```

```vb
<Cmdlet(VerbsLifecycle.Stop, "Proc", DefaultParameterSetName:="ProcessId", _
SupportsShouldProcess:=True)> _
Public Class StopProcCommand
    Inherits PSCmdlet
```

## <a name="declaring-the-parameters-of-the-cmdlet"></a><span data-ttu-id="bfff3-123">声明 Cmdlet 的参数</span><span class="sxs-lookup"><span data-stu-id="bfff3-123">Declaring the Parameters of the Cmdlet</span></span>

<span data-ttu-id="bfff3-124">此 cmdlet 将三个参数定义为 cmdlet 的输入 (这些参数也定义了参数集) ，以及用于管理 cmdlet 执行的操作的参数 `Force` 和 `PassThru` 用于确定 cmdlet 是否通过管道发送输出对象的参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-124">This cmdlet defines three parameters needed as input to the cmdlet (these parameters also define the parameter sets), as well as a `Force` parameter that manages what the cmdlet does and a `PassThru` parameter that determines whether the cmdlet sends an output object through the pipeline.</span></span> <span data-ttu-id="bfff3-125">默认情况下，此 cmdlet 不通过管道传递对象。</span><span class="sxs-lookup"><span data-stu-id="bfff3-125">By default, this cmdlet does not pass an object through the pipeline.</span></span> <span data-ttu-id="bfff3-126">有关最后两个参数的详细信息，请参阅 [创建修改系统的 Cmdlet](./creating-a-cmdlet-that-modifies-the-system.md)。</span><span class="sxs-lookup"><span data-stu-id="bfff3-126">For more information about these last two parameters, see [Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md).</span></span>

### <a name="declaring-the-name-parameter"></a><span data-ttu-id="bfff3-127">声明 Name 参数</span><span class="sxs-lookup"><span data-stu-id="bfff3-127">Declaring the Name Parameter</span></span>

<span data-ttu-id="bfff3-128">此输入参数允许用户指定要停止的进程的名称。</span><span class="sxs-lookup"><span data-stu-id="bfff3-128">This input parameter allows the user to specify the names of the processes to be stopped.</span></span> <span data-ttu-id="bfff3-129">请注意， `ParameterSetName` [Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) 属性的 attribute 关键字指定 `ProcessName` 为此参数设置的参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-129">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessName` parameter set for this parameter.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs" range="44-58":::

```vb
<Parameter(Position:=0, ParameterSetName:="ProcessName", _
Mandatory:=True, _
ValueFromPipeline:=True, ValueFromPipelineByPropertyName:=True, _
HelpMessage:="The name of one or more processes to stop. " & _
    "Wildcards are permitted."), [Alias]("ProcessName")> _
Public Property Name() As String()
    Get
        Return processNames
    End Get
    Set(ByVal value As String())
        processNames = value
    End Set
End Property

Private processNames() As String
```

<span data-ttu-id="bfff3-130">另请注意，将别名 "ProcessName" 提供给此参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-130">Note also that the alias "ProcessName" is given to this parameter.</span></span>

### <a name="declaring-the-id-parameter"></a><span data-ttu-id="bfff3-131">声明 Id 参数</span><span class="sxs-lookup"><span data-stu-id="bfff3-131">Declaring the Id Parameter</span></span>

<span data-ttu-id="bfff3-132">此输入参数允许用户指定要停止的进程的标识符。</span><span class="sxs-lookup"><span data-stu-id="bfff3-132">This input parameter allows the user to specify the identifiers of the processes to be stopped.</span></span> <span data-ttu-id="bfff3-133">请注意， `ParameterSetName` [Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) 属性的 attribute 关键字指定了 `ProcessId` 参数集。</span><span class="sxs-lookup"><span data-stu-id="bfff3-133">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `ProcessId` parameter set.</span></span>

```csharp
[Parameter(
           ParameterSetName = "ProcessId",
           Mandatory = true,
           ValueFromPipelineByPropertyName = true,
           ValueFromPipeline = true
)]
[Alias("ProcessId")]
public int[] Id
{
  get { return processIds; }
  set { processIds = value; }
}
private int[] processIds;
```

```vb
<Parameter(ParameterSetName:="ProcessId", _
Mandatory:=True, _
ValueFromPipelineByPropertyName:=True, _
ValueFromPipeline:=True), [Alias]("ProcessId")> _
Public Property Id() As Integer()
    Get
        Return processIds
    End Get
    Set(ByVal value As Integer())
        processIds = value
    End Set
End Property
Private processIds() As Integer
```

<span data-ttu-id="bfff3-134">另请注意，将别名 "ProcessId" 提供给此参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-134">Note also that the alias "ProcessId" is given to this parameter.</span></span>

### <a name="declaring-the-inputobject-parameter"></a><span data-ttu-id="bfff3-135">声明 InputObject 参数</span><span class="sxs-lookup"><span data-stu-id="bfff3-135">Declaring the InputObject Parameter</span></span>

<span data-ttu-id="bfff3-136">此输入参数允许用户指定输入对象，该对象包含要停止的进程的相关信息。</span><span class="sxs-lookup"><span data-stu-id="bfff3-136">This input parameter allows the user to specify an input object that contains information about the processes to be stopped.</span></span> <span data-ttu-id="bfff3-137">请注意， `ParameterSetName` [Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) 属性的 attribute 关键字指定 `InputObject` 为此参数设置的参数。</span><span class="sxs-lookup"><span data-stu-id="bfff3-137">Note that the `ParameterSetName` attribute keyword of the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute specifies the `InputObject` parameter set for this parameter.</span></span>

```csharp
[Parameter(
           ParameterSetName = "InputObject",
           Mandatory = true,
           ValueFromPipeline = true)]
public Process[] InputObject
{
  get { return inputObject; }
  set { inputObject = value; }
}
private Process[] inputObject;
```

```vb
<Parameter(ParameterSetName:="InputObject", _
Mandatory:=True, ValueFromPipeline:=True)> _
Public Property InputObject() As Process()
    Get
        Return myInputObject
    End Get
    Set(ByVal value As Process())
        myInputObject = value
    End Set
End Property
Private myInputObject() As Process
```

<span data-ttu-id="bfff3-138">另请注意，此参数没有别名。</span><span class="sxs-lookup"><span data-stu-id="bfff3-138">Note also that this parameter has no alias.</span></span>

### <a name="declaring-parameters-in-multiple-parameter-sets"></a><span data-ttu-id="bfff3-139">在多个参数集中声明参数</span><span class="sxs-lookup"><span data-stu-id="bfff3-139">Declaring Parameters in Multiple Parameter Sets</span></span>

<span data-ttu-id="bfff3-140">尽管每个参数集必须有一个唯一参数，但参数可以属于多个参数集。</span><span class="sxs-lookup"><span data-stu-id="bfff3-140">Although there must be a unique parameter for each parameter set, parameters can belong to more than one parameter set.</span></span> <span data-ttu-id="bfff3-141">在这些情况下，为共享参数提供参数所属的每个集合的 [Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) 特性声明。</span><span class="sxs-lookup"><span data-stu-id="bfff3-141">In these cases, give the shared parameter a [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration for each set to which that the parameter belongs.</span></span> <span data-ttu-id="bfff3-142">如果参数在所有参数集中，只需声明参数属性一次，且无需指定参数集名称。</span><span class="sxs-lookup"><span data-stu-id="bfff3-142">If a parameter is in all parameter sets, you only have to declare the parameter attribute once and do not need to specify the parameter set name.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="bfff3-143">重写输入处理方法</span><span class="sxs-lookup"><span data-stu-id="bfff3-143">Overriding an Input Processing Method</span></span>

<span data-ttu-id="bfff3-144">每个 cmdlet 都必须重写输入处理方法，这通常是 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法。</span><span class="sxs-lookup"><span data-stu-id="bfff3-144">Every cmdlet must override an input processing method, most often this will be the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method.</span></span> <span data-ttu-id="bfff3-145">在此 cmdlet 中，将重写 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法，以使 cmdlet 能够处理任意数量的进程。</span><span class="sxs-lookup"><span data-stu-id="bfff3-145">In this cmdlet, the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method is overridden so that the cmdlet can process any number of processes.</span></span> <span data-ttu-id="bfff3-146">它包含一个 Select 语句，该语句基于用户指定的参数来调用其他方法。</span><span class="sxs-lookup"><span data-stu-id="bfff3-146">It contains a Select statement that calls a different method based on which parameter set the user has specified.</span></span>

```csharp
protected override void ProcessRecord()
{
  switch (ParameterSetName)
  {
    case "ProcessName":
         ProcessByName();
         break;

    case "ProcessId":
         ProcessById();
         break;

    case "InputObject":
         foreach (Process process in inputObject)
         {
           SafeStopProcess(process);
         }
         break;

    default:
         throw new ArgumentException("Bad ParameterSet Name");
  } // switch (ParameterSetName...
} // ProcessRecord
```

```vb
Protected Overrides Sub ProcessRecord()
    Select Case ParameterSetName
        Case "ProcessName"
            ProcessByName()

        Case "ProcessId"
            ProcessById()

        Case "InputObject"
            Dim process As Process
            For Each process In myInputObject
                SafeStopProcess(process)
            Next process

        Case Else
            Throw New ArgumentException("Bad ParameterSet Name")
    End Select

End Sub 'ProcessRecord ' ProcessRecord
```

<span data-ttu-id="bfff3-147">此处未介绍 Select 语句调用的帮助器方法，但您可以在下一节的完整代码示例中看到它们的实现。</span><span class="sxs-lookup"><span data-stu-id="bfff3-147">The Helper methods called by the Select statement are not described here, but you can see their implementation in the complete code sample in the next section.</span></span>

## <a name="code-sample"></a><span data-ttu-id="bfff3-148">代码示例</span><span class="sxs-lookup"><span data-stu-id="bfff3-148">Code Sample</span></span>

<span data-ttu-id="bfff3-149">有关完整的 c # 示例代码，请参阅 [StopProcessSample04 示例](./stopprocesssample04-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="bfff3-149">For the complete C# sample code, see [StopProcessSample04 Sample](./stopprocesssample04-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="bfff3-150">定义对象类型和格式设置</span><span class="sxs-lookup"><span data-stu-id="bfff3-150">Defining Object Types and Formatting</span></span>

<span data-ttu-id="bfff3-151">Windows PowerShell 使用 .NET 对象在 cmdlet 之间传递信息。</span><span class="sxs-lookup"><span data-stu-id="bfff3-151">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="bfff3-152">因此，cmdlet 可能需要定义自己的类型，或者该 cmdlet 可能需要扩展另一个 cmdlet 提供的现有类型。</span><span class="sxs-lookup"><span data-stu-id="bfff3-152">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="bfff3-153">有关定义新类型或扩展现有类型的详细信息，请参阅 [扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="bfff3-153">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="bfff3-154">构建 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bfff3-154">Building the Cmdlet</span></span>

<span data-ttu-id="bfff3-155">实现 cmdlet 后，必须通过 Windows PowerShell 管理单元将其注册到 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="bfff3-155">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="bfff3-156">有关注册 cmdlet 的详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="bfff3-156">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="bfff3-157">测试 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bfff3-157">Testing the Cmdlet</span></span>

<span data-ttu-id="bfff3-158">向 Windows PowerShell 注册 cmdlet 后，通过在命令行上运行它来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="bfff3-158">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="bfff3-159">下面是一些测试，演示如何 `ProcessId` 使用和 `InputObject` 参数来测试它们的参数集以停止进程。</span><span class="sxs-lookup"><span data-stu-id="bfff3-159">Here are some tests that show how the `ProcessId` and `InputObject` parameters can be used to test their parameter sets to stop a process.</span></span>

- <span data-ttu-id="bfff3-160">启动 Windows PowerShell 后，运行 Stop-Proc cmdlet，并将 `ProcessId` 参数设置为基于其标识符停止进程。</span><span class="sxs-lookup"><span data-stu-id="bfff3-160">With Windows PowerShell started, run the Stop-Proc cmdlet with the `ProcessId` parameter set to stop a process based on its identifier.</span></span> <span data-ttu-id="bfff3-161">在这种情况下，该 cmdlet 使用 `ProcessId` 参数集来停止进程。</span><span class="sxs-lookup"><span data-stu-id="bfff3-161">In this case, the cmdlet is using the `ProcessId` parameter set to stop the process.</span></span>

  ```
  PS> stop-proc -Id 444
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
  ```

- <span data-ttu-id="bfff3-162">启动 Windows PowerShell 后，运行 Stop-Proc cmdlet，并将 `InputObject` 参数设置为 "停止" 命令检索的 Notepad 对象上的进程 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="bfff3-162">With Windows PowerShell started, run the Stop-Proc cmdlet with the `InputObject` parameter set to stop processes on the Notepad object retrieved by the `Get-Process` command.</span></span>

  ```
  PS> get-process notepad | stop-proc
  Confirm
  Are you sure you want to perform this action?
  Performing operation "stop-proc" on Target "notepad (444)".
  [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
  ```

## <a name="see-also"></a><span data-ttu-id="bfff3-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfff3-163">See Also</span></span>

[<span data-ttu-id="bfff3-164">创建用于修改系统的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bfff3-164">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="bfff3-165">如何创建 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="bfff3-165">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="bfff3-166">[扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="bfff3-166">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="bfff3-167">[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="bfff3-167">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="bfff3-168">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="bfff3-168">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
