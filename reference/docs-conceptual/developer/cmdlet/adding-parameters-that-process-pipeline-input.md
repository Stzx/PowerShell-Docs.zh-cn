---
ms.date: 09/13/2016
ms.topic: reference
title: 添加用于处理管道输入的参数
description: 添加用于处理管道输入的参数
ms.openlocfilehash: b150d5be93207d9c010a6d2d4de901b4526f1d79
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668348"
---
# <a name="adding-parameters-that-process-pipeline-input"></a><span data-ttu-id="c117a-103">添加用于处理管道输入的参数</span><span class="sxs-lookup"><span data-stu-id="c117a-103">Adding Parameters that Process Pipeline Input</span></span>

<span data-ttu-id="c117a-104">Cmdlet 的一个输入源是从上游 cmdlet 产生的管道上的对象。</span><span class="sxs-lookup"><span data-stu-id="c117a-104">One source of input for a cmdlet is an object on the pipeline that originates from an upstream cmdlet.</span></span> <span data-ttu-id="c117a-105">本部分介绍如何将参数添加到 [创建第一个 cmdlet](./creating-a-cmdlet-without-parameters.md)) 中所述的 Get-Proc cmdlet (，以便该 cmdlet 可以处理管道对象。</span><span class="sxs-lookup"><span data-stu-id="c117a-105">This section describes how to add a parameter to the Get-Proc cmdlet (described in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md)) so that the cmdlet can process pipeline objects.</span></span>

<span data-ttu-id="c117a-106">此 Get-Proc cmdlet 使用一个 `Name` 参数，该参数接受来自管道对象的输入，基于提供的名称从本地计算机检索进程信息，然后在命令行中显示有关进程的信息。</span><span class="sxs-lookup"><span data-stu-id="c117a-106">This Get-Proc cmdlet uses a `Name` parameter that accepts input from a pipeline object, retrieves process information from the local computer based on the supplied names, and then displays information about the processes at the command line.</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="c117a-107">定义 Cmdlet 类</span><span class="sxs-lookup"><span data-stu-id="c117a-107">Defining the Cmdlet Class</span></span>

<span data-ttu-id="c117a-108">创建 cmdlet 的第一步是始终命名 cmdlet 并声明实现 cmdlet 的 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="c117a-108">The first step in cmdlet creation is always naming the cmdlet and declaring the .NET class that implements the cmdlet.</span></span> <span data-ttu-id="c117a-109">此 cmdlet 检索进程信息，因此此处选择的谓词名称为 "Get"。</span><span class="sxs-lookup"><span data-stu-id="c117a-109">This cmdlet retrieves process information, so the verb name chosen here is "Get".</span></span> <span data-ttu-id="c117a-110"> (几乎任何支持检索信息的 cmdlet，都可以处理命令行输入。 ) 有关已批准的 cmdlet 动词的详细信息，请参阅 [Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="c117a-110">(Almost any sort of cmdlet that is capable of retrieving information can process command-line input.) For more information about approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

<span data-ttu-id="c117a-111">下面是此 Get-Proc cmdlet 的定义。</span><span class="sxs-lookup"><span data-stu-id="c117a-111">The following is the definition for this Get-Proc cmdlet.</span></span> <span data-ttu-id="c117a-112">[创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)中提供了此定义的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c117a-112">Details of this definition are given in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "proc")]
public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

## <a name="defining-input-from-the-pipeline"></a><span data-ttu-id="c117a-113">定义管道的输入</span><span class="sxs-lookup"><span data-stu-id="c117a-113">Defining Input from the Pipeline</span></span>

<span data-ttu-id="c117a-114">本部分介绍如何为 cmdlet 定义管道中的输入。</span><span class="sxs-lookup"><span data-stu-id="c117a-114">This section describes how to define input from the pipeline for a cmdlet.</span></span> <span data-ttu-id="c117a-115">此 Get-Proc cmdlet 定义了一个属性，该属性表示 `Name` 参数，如 [添加处理命令行输入的参数](./adding-parameters-that-process-command-line-input.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="c117a-115">This Get-Proc cmdlet defines a property that represents the `Name` parameter as described in [Adding Parameters that Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>
<span data-ttu-id="c117a-116"> (参见该主题，了解有关声明参数的一般信息。 ) </span><span class="sxs-lookup"><span data-stu-id="c117a-116">(See that topic for general information about declaring parameters.)</span></span>

<span data-ttu-id="c117a-117">但是，当某个 cmdlet 需要处理管道输入时，它必须将其参数与 Windows PowerShell 运行时绑定到输入值。</span><span class="sxs-lookup"><span data-stu-id="c117a-117">However, when a cmdlet needs to process pipeline input, it must have its parameters bound to input values by the Windows PowerShell runtime.</span></span> <span data-ttu-id="c117a-118">为此，必须添加 `ValueFromPipeline` 关键字，或将 `ValueFromPipelineByProperty` 关键字添加到 [Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) 特性声明。</span><span class="sxs-lookup"><span data-stu-id="c117a-118">To do this, you must add the `ValueFromPipeline` keyword or add the `ValueFromPipelineByProperty` keyword to the [System.Management.Automation.Parameterattribute](/dotnet/api/System.Management.Automation.ParameterAttribute) attribute declaration.</span></span> <span data-ttu-id="c117a-119">`ValueFromPipeline`如果 cmdlet 访问完整的输入对象，则指定关键字。</span><span class="sxs-lookup"><span data-stu-id="c117a-119">Specify the `ValueFromPipeline` keyword if the cmdlet accesses the complete input object.</span></span> <span data-ttu-id="c117a-120">`ValueFromPipelineByProperty`如果 cmdlet 仅访问对象的属性，请指定。</span><span class="sxs-lookup"><span data-stu-id="c117a-120">Specify the `ValueFromPipelineByProperty` if the cmdlet accesses only a property of the object.</span></span>

<span data-ttu-id="c117a-121">下面是 `Name` 接受管道输入的此 Get-Proc cmdlet 的参数声明。</span><span class="sxs-lookup"><span data-stu-id="c117a-121">Here is the parameter declaration for the `Name` parameter of this Get-Proc cmdlet that accepts pipeline input.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample03/GetProcessSample03.cs" range="35-44":::

```vb
<Parameter(Position:=0, ValueFromPipeline:=True, _
ValueFromPipelineByPropertyName:=True), ValidateNotNullOrEmpty()> _
Public Property Name() As String()
    Get
        Return processNames
    End Get

    Set(ByVal value As String())
        processNames = value
    End Set

End Property
```

<!-- TODO!!!: review snippet reference  [!CODE [Msh_samplesgetproc03#GetProc03VBNameParameter](Msh_samplesgetproc03#GetProc03VBNameParameter)]  -->

<span data-ttu-id="c117a-122">前面的声明将 `ValueFromPipeline` 关键字设置为， `true` 这样，如果对象与参数的类型相同，或者可以将参数强制转换为同一类型，则 Windows PowerShell 运行时会将参数绑定到传入对象。</span><span class="sxs-lookup"><span data-stu-id="c117a-122">The previous declaration sets the `ValueFromPipeline` keyword to `true` so that the Windows PowerShell runtime will bind the parameter to the incoming object if the object is the same type as the parameter, or if it can be coerced to the same type.</span></span> <span data-ttu-id="c117a-123">`ValueFromPipelineByPropertyName`还将关键字设置为， `true` 以便 Windows PowerShell 运行时将检查属性的传入对象 `Name` 。</span><span class="sxs-lookup"><span data-stu-id="c117a-123">The `ValueFromPipelineByPropertyName` keyword is also set to `true` so that the Windows PowerShell runtime will check the incoming object for a `Name` property.</span></span> <span data-ttu-id="c117a-124">如果传入对象具有此类属性，则运行时将该 `Name` 参数绑定到 `Name` 传入对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c117a-124">If the incoming object has such a property, the runtime will bind the `Name` parameter to the `Name` property of the incoming object.</span></span>

> [!NOTE]
> <span data-ttu-id="c117a-125">`ValueFromPipeline`参数的 attribute 关键字的设置优先于关键字的设置 `ValueFromPipelineByPropertyName` 。</span><span class="sxs-lookup"><span data-stu-id="c117a-125">The setting of the `ValueFromPipeline` attribute keyword for a parameter takes precedence over the setting for the `ValueFromPipelineByPropertyName` keyword.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="c117a-126">重写输入处理方法</span><span class="sxs-lookup"><span data-stu-id="c117a-126">Overriding an Input Processing Method</span></span>

<span data-ttu-id="c117a-127">如果 cmdlet 要处理管道输入，则需要重写适当的输入处理方法。</span><span class="sxs-lookup"><span data-stu-id="c117a-127">If your cmdlet is to handle pipeline input, it needs to override the appropriate input processing methods.</span></span> <span data-ttu-id="c117a-128">基本输入处理方法在 [创建第一个 Cmdlet](./creating-a-cmdlet-without-parameters.md)时引入。</span><span class="sxs-lookup"><span data-stu-id="c117a-128">The basic input processing methods are introduced in [Creating Your First Cmdlet](./creating-a-cmdlet-without-parameters.md).</span></span>

<span data-ttu-id="c117a-129">此 Get-Proc cmdlet 将重写 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 方法，以处理 `Name` 用户或脚本提供的参数输入。</span><span class="sxs-lookup"><span data-stu-id="c117a-129">This Get-Proc cmdlet overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to handle the `Name` parameter input provided by the user or a script.</span></span> <span data-ttu-id="c117a-130">如果未提供任何名称，则此方法将获取每个请求的进程名称或所有进程的进程。</span><span class="sxs-lookup"><span data-stu-id="c117a-130">This method will get the processes for each requested process name or all processes if no name is provided.</span></span> <span data-ttu-id="c117a-131">请注意，在 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)中，对 [WriteObject)  (](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) 的调用是用于将输出对象发送到管道的输出机制的输出机制。</span><span class="sxs-lookup"><span data-stu-id="c117a-131">Notice that within [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), the call to [WriteObject(System.Object,System.Boolean)](/dotnet/api/system.management.automation.cmdlet.writeobject#System_Management_Automation_Cmdlet_WriteObject_System_Object_System_Boolean_) is the output mechanism for sending output objects to the pipeline.</span></span> <span data-ttu-id="c117a-132">此调用的第二个参数将 `enumerateCollection` 设置为，以 `true` 指示 Windows PowerShell 运行时枚举进程对象的数组，并一次将一个进程写入命令行。</span><span class="sxs-lookup"><span data-stu-id="c117a-132">The second parameter of this call, `enumerateCollection`, is set to `true` to tell the Windows PowerShell runtime to enumerate the array of process objects, and write one process at a time to the command line.</span></span>

```csharp
protected override void ProcessRecord()
{
  // If no process names are passed to the cmdlet, get all processes.
  if (processNames == null)
  {
      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument of this call tells
      // PowerShell to enumerate the array, and send one process at a
      // time to the pipeline.
      WriteObject(Process.GetProcesses(), true);
  }
  else
  {
    // If process names are passed to the cmdlet, get and write
    // the associated processes.
    foreach (string name in processNames)
    {
      WriteObject(Process.GetProcessesByName(name), true);
    } // End foreach (string name...).
  }
}
```

```vb
Protected Overrides Sub ProcessRecord()
    Dim processes As Process()

    '/ If no process names are passed to the cmdlet, get all processes.
    If processNames Is Nothing Then
        processes = Process.GetProcesses()
    Else

        '/ If process names are specified, write the processes to the
        '/ pipeline to display them or make them available to the next cmdlet.
        For Each name As String In processNames
            '/ The second parameter of this call tells PowerShell to enumerate the
            '/ array, and send one process at a time to the pipeline.
            WriteObject(Process.GetProcessesByName(name), True)
        Next
    End If

End Sub 'ProcessRecord
```

## <a name="code-sample"></a><span data-ttu-id="c117a-133">代码示例</span><span class="sxs-lookup"><span data-stu-id="c117a-133">Code Sample</span></span>

<span data-ttu-id="c117a-134">有关完整的 c # 示例代码，请参阅 [GetProcessSample03 示例](./getprocesssample03-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="c117a-134">For the complete C# sample code, see [GetProcessSample03 Sample](./getprocesssample03-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="c117a-135">定义对象类型和格式设置</span><span class="sxs-lookup"><span data-stu-id="c117a-135">Defining Object Types and Formatting</span></span>

<span data-ttu-id="c117a-136">Windows PowerShell 使用 .Net 对象在 cmdlet 之间传递信息。</span><span class="sxs-lookup"><span data-stu-id="c117a-136">Windows PowerShell passes information between cmdlets using .Net objects.</span></span> <span data-ttu-id="c117a-137">因此，cmdlet 可能需要定义自己的类型，或者该 cmdlet 可能需要扩展另一个 cmdlet 提供的现有类型。</span><span class="sxs-lookup"><span data-stu-id="c117a-137">Consequently, a cmdlet may need to define its own type, or the cmdlet may need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="c117a-138">有关定义新类型或扩展现有类型的详细信息，请参阅 [扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="c117a-138">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="c117a-139">构建 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c117a-139">Building the Cmdlet</span></span>

<span data-ttu-id="c117a-140">实现 cmdlet 后，必须通过 Windows PowerShell 管理单元向 Windows PowerShell 注册它。</span><span class="sxs-lookup"><span data-stu-id="c117a-140">After implementing a cmdlet it must be registered with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="c117a-141">有关注册 cmdlet 的详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="c117a-141">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="c117a-142">测试 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c117a-142">Testing the Cmdlet</span></span>

<span data-ttu-id="c117a-143">向 Windows PowerShell 注册 cmdlet 后，通过在命令行上运行它来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="c117a-143">When your cmdlet has been registered with Windows PowerShell, test it by running it on the command line.</span></span> <span data-ttu-id="c117a-144">例如，测试示例 cmdlet 的代码。</span><span class="sxs-lookup"><span data-stu-id="c117a-144">For example, test the code for the sample cmdlet.</span></span> <span data-ttu-id="c117a-145">有关从命令行使用 cmdlet 的详细信息，请参阅 [使用 Windows PowerShell 的入门](/powershell/scripting/getting-started/getting-started-with-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c117a-145">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

- <span data-ttu-id="c117a-146">在 Windows PowerShell 提示符下，输入以下命令以通过管道检索进程名称。</span><span class="sxs-lookup"><span data-stu-id="c117a-146">At the Windows PowerShell prompt, enter the following commands to retrieve the process names through the pipeline.</span></span>

  ```powershell
  PS> type ProcessNames | get-proc
  ```

  <span data-ttu-id="c117a-147">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="c117a-147">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      809      21  40856    4448    147    9.50  2288  iexplore
      737      21  26036   16348    144   22.03  3860  iexplore
       39       2   1024     388     30    0.08  3396  notepad
     3927      62  71836   26984    467  195.19  1848  OUTLOOK
  ```

- <span data-ttu-id="c117a-148">输入以下行，以获取进程对象，这些对象具有 `Name` 名为 "IEXPLORE" 的进程的属性。</span><span class="sxs-lookup"><span data-stu-id="c117a-148">Enter the following lines to get the process objects that have a `Name` property from the processes called "IEXPLORE".</span></span> <span data-ttu-id="c117a-149">此示例使用 `Get-Process` Windows PowerShell) 提供的 cmdlet (作为上游命令来检索 "IEXPLORE" 进程。</span><span class="sxs-lookup"><span data-stu-id="c117a-149">This example uses the `Get-Process` cmdlet (provided by Windows PowerShell) as an upstream command to retrieve the "IEXPLORE" processes.</span></span>

  ```powershell
  PS> get-process iexplore | get-proc
  ```

  <span data-ttu-id="c117a-150">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="c117a-150">The following output appears.</span></span>

  ```
  Handles  NPM(K)  PM(K)   WS(K)  VS(M)  CPU(s)    Id  ProcessName
  -------  ------  -----   ----- -----   ------    --  -----------
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
      801      21  40720    6544    142    9.52  2288  iexplore
      726      21  25872   16652    138   22.09  3860  iexplore
  ```

## <a name="see-also"></a><span data-ttu-id="c117a-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c117a-151">See Also</span></span>

[<span data-ttu-id="c117a-152">添加处理命令行输入的参数</span><span class="sxs-lookup"><span data-stu-id="c117a-152">Adding Parameters that Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="c117a-153">创建第一个 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c117a-153">Creating Your First Cmdlet</span></span>](./creating-a-cmdlet-without-parameters.md)

<span data-ttu-id="c117a-154">[扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="c117a-154">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="c117a-155">[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="c117a-155">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="c117a-156">Windows PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="c117a-156">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="c117a-157">Cmdlet 示例</span><span class="sxs-lookup"><span data-stu-id="c117a-157">Cmdlet Samples</span></span>](./cmdlet-samples.md)
