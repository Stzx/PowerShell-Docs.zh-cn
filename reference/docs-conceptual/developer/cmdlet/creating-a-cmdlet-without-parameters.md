---
ms.date: 09/13/2016
ms.topic: reference
title: 创建不具有参数的 Cmdlet
description: 创建不具有参数的 Cmdlet
ms.openlocfilehash: 5df27ac4c1f6dfcc3e7596d93f8db0f97aae71c1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646541"
---
# <a name="creating-a-cmdlet-without-parameters"></a><span data-ttu-id="8fc51-103">创建不具有参数的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8fc51-103">Creating a Cmdlet without Parameters</span></span>

<span data-ttu-id="8fc51-104">本部分介绍如何创建一个 cmdlet，用于在不使用参数的情况下从本地计算机检索信息，然后将该信息写入管道。</span><span class="sxs-lookup"><span data-stu-id="8fc51-104">This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span> <span data-ttu-id="8fc51-105">此处所述的 cmdlet 是 Get-Proc cmdlet，它检索有关本地计算机的进程的信息，然后在命令行中显示该信息。</span><span class="sxs-lookup"><span data-stu-id="8fc51-105">The cmdlet described here is a Get-Proc cmdlet that retrieves information about the processes of the local computer, and then displays that information at the command line.</span></span>

> [!NOTE]
> <span data-ttu-id="8fc51-106">请注意，在编写 cmdlet 时，默认情况下，Windows PowerShell®引用程序集下载到磁盘 (上的 C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0) 。</span><span class="sxs-lookup"><span data-stu-id="8fc51-106">Be aware that when writing cmdlets, the Windows PowerShell® reference assemblies are downloaded onto disk (by default at C:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\v1.0).</span></span> <span data-ttu-id="8fc51-107">它们未安装在全局程序集缓存 (GAC) 。</span><span class="sxs-lookup"><span data-stu-id="8fc51-107">They are not installed in the Global Assembly Cache (GAC).</span></span>

## <a name="naming-the-cmdlet"></a><span data-ttu-id="8fc51-108">命名 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8fc51-108">Naming the Cmdlet</span></span>

<span data-ttu-id="8fc51-109">Cmdlet 名称由指示 cmdlet 所采用的操作的谓词和指示该 cmdlet 操作的项的名词组成。</span><span class="sxs-lookup"><span data-stu-id="8fc51-109">A cmdlet name consists of a verb that indicates the action the cmdlet takes and a noun that indicates the items that the cmdlet acts upon.</span></span> <span data-ttu-id="8fc51-110">由于此示例 Get-Proc cmdlet 检索进程对象，因此它使用由 [Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) 枚举定义的谓词 "Get"，并使用名词 "Proc" 指示该 cmdlet 处理进程项。</span><span class="sxs-lookup"><span data-stu-id="8fc51-110">Because this sample Get-Proc cmdlet retrieves process objects, it uses the verb "Get", defined by the [System.Management.Automation.Verbscommon](/dotnet/api/System.Management.Automation.VerbsCommon) enumeration, and the noun "Proc" to indicate that the cmdlet works on process items.</span></span>

<span data-ttu-id="8fc51-111">命名 cmdlet 时，请不要使用以下任何字符： #、 ( # A2 {} [] &-/\ $;： "" <> &#124; ？</span><span class="sxs-lookup"><span data-stu-id="8fc51-111">When naming cmdlets, do not use any of the following characters: # , () {} [] & - /\ $ ; : " '<> &#124; ?</span></span> <span data-ttu-id="8fc51-112">@ \` .</span><span class="sxs-lookup"><span data-stu-id="8fc51-112">@ \` .</span></span>

### <a name="choosing-a-noun"></a><span data-ttu-id="8fc51-113">选择名词</span><span class="sxs-lookup"><span data-stu-id="8fc51-113">Choosing a Noun</span></span>

<span data-ttu-id="8fc51-114">应选择特定的名词。</span><span class="sxs-lookup"><span data-stu-id="8fc51-114">You should choose a noun that is specific.</span></span> <span data-ttu-id="8fc51-115">最好使用带有缩写形式的产品名称的单数名词。</span><span class="sxs-lookup"><span data-stu-id="8fc51-115">It is best to use a singular noun prefixed with a shortened version of the product name.</span></span> <span data-ttu-id="8fc51-116">此类型的示例 cmdlet 名称为 " `Get-SQLServer` "。</span><span class="sxs-lookup"><span data-stu-id="8fc51-116">An example cmdlet name of this type is "`Get-SQLServer`".</span></span>

### <a name="choosing-a-verb"></a><span data-ttu-id="8fc51-117">选择谓词</span><span class="sxs-lookup"><span data-stu-id="8fc51-117">Choosing a Verb</span></span>

<span data-ttu-id="8fc51-118">应使用已批准的 cmdlet 动词名称集中的动词。</span><span class="sxs-lookup"><span data-stu-id="8fc51-118">You should use a verb from the set of approved cmdlet verb names.</span></span> <span data-ttu-id="8fc51-119">有关批准的 cmdlet 谓词的详细信息，请参阅 [Cmdlet 谓词名称](./approved-verbs-for-windows-powershell-commands.md)。</span><span class="sxs-lookup"><span data-stu-id="8fc51-119">For more information about the approved cmdlet verbs, see [Cmdlet Verb Names](./approved-verbs-for-windows-powershell-commands.md).</span></span>

## <a name="defining-the-cmdlet-class"></a><span data-ttu-id="8fc51-120">定义 Cmdlet 类</span><span class="sxs-lookup"><span data-stu-id="8fc51-120">Defining the Cmdlet Class</span></span>

<span data-ttu-id="8fc51-121">选择了 cmdlet 名称后，定义一个 .NET 类来实现该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8fc51-121">Once you have chosen a cmdlet name, define a .NET class to implement the cmdlet.</span></span> <span data-ttu-id="8fc51-122">下面是此示例的类定义 Get-Proc cmdlet：</span><span class="sxs-lookup"><span data-stu-id="8fc51-122">Here is the class definition for this sample Get-Proc cmdlet:</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
```

```vb
<Cmdlet(VerbsCommon.Get, "Proc")> _
Public Class GetProcCommand
    Inherits Cmdlet
```

<span data-ttu-id="8fc51-123">请注意，在类定义的前面，使用语法的 [CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) 属性 `[Cmdlet(verb, noun, ...)]` 用于将此类标识为 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8fc51-123">Notice that previous to the class definition, the [System.Management.Automation.CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) attribute, with the syntax `[Cmdlet(verb, noun, ...)]`, is used to identify this class as a cmdlet.</span></span> <span data-ttu-id="8fc51-124">这是所有 cmdlet 的唯一必需的属性，它允许 Windows PowerShell 运行时正确调用它们。</span><span class="sxs-lookup"><span data-stu-id="8fc51-124">This is the only required attribute for all cmdlets, and it allows the Windows PowerShell runtime to call them correctly.</span></span> <span data-ttu-id="8fc51-125">如有必要，可以设置属性关键字以进一步声明该类。</span><span class="sxs-lookup"><span data-stu-id="8fc51-125">You can set attribute keywords to further declare the class if necessary.</span></span> <span data-ttu-id="8fc51-126">请注意，我们的示例 GetProcCommand 类的属性声明仅声明 Get-Proc cmdlet 的名词和动词名称。</span><span class="sxs-lookup"><span data-stu-id="8fc51-126">Be aware that the attribute declaration for our sample GetProcCommand class declares only the noun and verb names for the Get-Proc cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="8fc51-127">对于所有 Windows PowerShell 特性类，可以设置的关键字与特性类的属性相对应。</span><span class="sxs-lookup"><span data-stu-id="8fc51-127">For all Windows PowerShell attribute classes, the keywords that you can set correspond to properties of the attribute class.</span></span>

<span data-ttu-id="8fc51-128">命名 cmdlet 的类时，最好在类名称中反映 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="8fc51-128">When naming the class of the cmdlet, it is a good practice to reflect the cmdlet name in the class name.</span></span> <span data-ttu-id="8fc51-129">为此，请使用格式 "VerbNounCommand"，并将 "Verb" 和 "名词" 替换为 cmdlet 名称中使用的动词和名词。</span><span class="sxs-lookup"><span data-stu-id="8fc51-129">To do this, use the form "VerbNounCommand" and replace "Verb" and "Noun" with the verb and noun used in the cmdlet name.</span></span> <span data-ttu-id="8fc51-130">如上一类定义中所示，示例 Get-Proc cmdlet 定义了一个名为 [GetProcCommand 的类](/dotnet/api/System.Management.Automation.Cmdlet) ，该类派生自一个</span><span class="sxs-lookup"><span data-stu-id="8fc51-130">As is shown in the previous class definition, the sample Get-Proc cmdlet defines a class called GetProcCommand, which derives from the [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) base class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fc51-131">如果要定义直接访问 Windows PowerShell 运行时的 cmdlet，你的 .NET 类应派生自 [PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) 基类。</span><span class="sxs-lookup"><span data-stu-id="8fc51-131">If you want to define a cmdlet that accesses the Windows PowerShell runtime directly, your .NET class should derive from the [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet) base class.</span></span> <span data-ttu-id="8fc51-132">有关此类的详细信息，请参阅 [创建定义参数集的 Cmdlet](./adding-parameter-sets-to-a-cmdlet.md)。</span><span class="sxs-lookup"><span data-stu-id="8fc51-132">For more information about this class, see [Creating a Cmdlet that Defines Parameter Sets](./adding-parameter-sets-to-a-cmdlet.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8fc51-133">Cmdlet 的类必须显式标记为公共。</span><span class="sxs-lookup"><span data-stu-id="8fc51-133">The class for a cmdlet must be explicitly marked as public.</span></span> <span data-ttu-id="8fc51-134">未标记为 "公共" 的类将默认为内部类，且不会由 Windows PowerShell 运行时找到。</span><span class="sxs-lookup"><span data-stu-id="8fc51-134">Classes that are not marked as public will default to internal and will not be found by the Windows PowerShell runtime.</span></span>

<span data-ttu-id="8fc51-135">Windows PowerShell 使用其 cmdlet 类 [的 "the](/dotnet/api/Microsoft.PowerShell.Commands) " 命名空间。</span><span class="sxs-lookup"><span data-stu-id="8fc51-135">Windows PowerShell uses the [Microsoft.PowerShell.Commands](/dotnet/api/Microsoft.PowerShell.Commands) namespace for its cmdlet classes.</span></span> <span data-ttu-id="8fc51-136">建议将 cmdlet 类放在 API 命名空间的命令命名空间中，例如，xxx。</span><span class="sxs-lookup"><span data-stu-id="8fc51-136">It is recommended to place your cmdlet classes in a Commands namespace of your API namespace, for example, xxx.PS.Commands.</span></span>

## <a name="overriding-an-input-processing-method"></a><span data-ttu-id="8fc51-137">重写输入处理方法</span><span class="sxs-lookup"><span data-stu-id="8fc51-137">Overriding an Input Processing Method</span></span>

<span data-ttu-id="8fc51-138">[System.web](/dotnet/api/System.Management.Automation.Cmdlet)类提供三个主要的输入处理方法，其中至少有一个 Cmdlet 必须重写。</span><span class="sxs-lookup"><span data-stu-id="8fc51-138">The [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet) class provides three main input processing methods, at least one of which your cmdlet must override.</span></span> <span data-ttu-id="8fc51-139">有关 Windows PowerShell 如何处理记录的详细信息，请参阅 [Windows powershell 的工作](/previous-versions//ms714658(v=vs.85))原理。</span><span class="sxs-lookup"><span data-stu-id="8fc51-139">For more information about how Windows PowerShell processes records, see [How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85)).</span></span>

<span data-ttu-id="8fc51-140">对于所有类型的输入，Windows PowerShell 运行时都会调用 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 来启用处理。</span><span class="sxs-lookup"><span data-stu-id="8fc51-140">For all types of input, the Windows PowerShell runtime calls [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) to enable processing.</span></span> <span data-ttu-id="8fc51-141">如果 cmdlet 必须执行一些预处理或设置，则可以通过重写此方法来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8fc51-141">If your cmdlet must perform some preprocessing or setup, it can do this by overriding this method.</span></span>

> [!NOTE]
> <span data-ttu-id="8fc51-142">Windows PowerShell 使用术语 "记录" 来描述在调用 cmdlet 时提供的参数值集。</span><span class="sxs-lookup"><span data-stu-id="8fc51-142">Windows PowerShell uses the term "record" to describe the set of parameter values supplied when a cmdlet is called.</span></span>

<span data-ttu-id="8fc51-143">如果你的 cmdlet 接受管道输入，则它必须重写[ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法，还可以重[写方法（可选）。](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)</span><span class="sxs-lookup"><span data-stu-id="8fc51-143">If your cmdlet accepts pipeline input, it must override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method, and optionally the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="8fc51-144">例如，如果 cmdlet 使用 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) 收集所有输入，则它可能会重写这两种方法，然后在输入上作为一个整体而不是一个元素进行操作，就像 `Sort-Object` cmdlet 一样。</span><span class="sxs-lookup"><span data-stu-id="8fc51-144">For example, a cmdlet might override both methods if it gathers all input using [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) and then operates on the input as a whole rather than one element at a time, as the `Sort-Object` cmdlet does.</span></span>

<span data-ttu-id="8fc51-145">如果 cmdlet 不接受管道输入，则它应重写 [system.web](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 方法。</span><span class="sxs-lookup"><span data-stu-id="8fc51-145">If your cmdlet does not take pipeline input, it should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method.</span></span> <span data-ttu-id="8fc51-146">请注意，当 cmdlet 无法一次对一个元素进行操作时，此方法经常用于替代 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) ，这与排序 Cmdlet 的情况相同。</span><span class="sxs-lookup"><span data-stu-id="8fc51-146">Be aware that this method is frequently used in place of [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) when the cmdlet cannot operate on one element at a time, as is the case for a sorting cmdlet.</span></span>

<span data-ttu-id="8fc51-147">由于此示例 Get-Proc cmdlet 必须接收管道输入，因此它会重写[ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)方法，并使用[BeginProcessing 和](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)的默认实现方法来重写该方法，并使用该[方法。](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)</span><span class="sxs-lookup"><span data-stu-id="8fc51-147">Because this sample Get-Proc cmdlet must receive pipeline input, it overrides the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method and uses the default implementations for [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) and [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing).</span></span> <span data-ttu-id="8fc51-148">[ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)重写将检索进程，并使用[WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)方法将这些进程写入命令行的命令行中。</span><span class="sxs-lookup"><span data-stu-id="8fc51-148">The [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) override retrieves processes and writes them to the command line using the [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Get the current processes
  Process[] processes = Process.GetProcesses();

  // Write the processes to the pipeline making them available
  // to the next cmdlet. The second parameter of this call tells
  // PowerShell to enumerate the array, and send one process at a
  // time to the pipeline.
  WriteObject(processes, true);
}
```

```vb
Protected Overrides Sub ProcessRecord()

    '/ Get the current processes.
    Dim processes As Process()
    processes = Process.GetProcesses()

    '/ Write the processes to the pipeline making them available
    '/ to the next cmdlet. The second parameter of this call tells
    '/ PowerShell to enumerate the array, and send one process at a
    '/ time to the pipeline.
    WriteObject(processes, True)

End Sub 'ProcessRecord
```

#### <a name="things-to-remember-about-input-processing"></a><span data-ttu-id="8fc51-149">有关输入处理的注意事项</span><span class="sxs-lookup"><span data-stu-id="8fc51-149">Things to Remember About Input Processing</span></span>

- <span data-ttu-id="8fc51-150">输入的默认源是一个显式对象 (例如，在命令行中由用户提供的字符串) 。</span><span class="sxs-lookup"><span data-stu-id="8fc51-150">The default source for input is an explicit object (for example, a string) provided by the user on the command line.</span></span> <span data-ttu-id="8fc51-151">有关详细信息，请参阅 [创建 Cmdlet 来处理命令行输入](./adding-parameters-that-process-command-line-input.md)。</span><span class="sxs-lookup"><span data-stu-id="8fc51-151">For more information, see [Creating a Cmdlet to Process Command Line Input](./adding-parameters-that-process-command-line-input.md).</span></span>

- <span data-ttu-id="8fc51-152">输入处理方法还可以从管道上的上游 cmdlet 的输出对象接收输入。</span><span class="sxs-lookup"><span data-stu-id="8fc51-152">An input processing method can also receive input from the output object of an upstream cmdlet on the pipeline.</span></span> <span data-ttu-id="8fc51-153">有关详细信息，请参阅 [创建用于处理管道输入的 Cmdlet](./adding-parameters-that-process-pipeline-input.md)。</span><span class="sxs-lookup"><span data-stu-id="8fc51-153">For more information, see [Creating a Cmdlet to Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md).</span></span> <span data-ttu-id="8fc51-154">请注意，cmdlet 可以从命令行和管道源的组合接收输入。</span><span class="sxs-lookup"><span data-stu-id="8fc51-154">Be aware that your cmdlet can receive input from a combination of command-line and pipeline sources.</span></span>

- <span data-ttu-id="8fc51-155">下游 cmdlet 可能不会长时间返回，或者根本不会返回。</span><span class="sxs-lookup"><span data-stu-id="8fc51-155">The downstream cmdlet might not return for a long time, or not at all.</span></span> <span data-ttu-id="8fc51-156">出于此原因，在调用 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)期间，cmdlet 中的输入处理方法不应持有锁，尤其是范围超出 cmdlet 实例的锁。</span><span class="sxs-lookup"><span data-stu-id="8fc51-156">For that reason, the input processing method in your cmdlet should not hold locks during calls to [System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), especially locks for which the scope extends beyond the cmdlet instance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fc51-157">Cmdlet 不应调用 system.exception [\*](/dotnet/api/System.Console.WriteLine) 或其等效的。</span><span class="sxs-lookup"><span data-stu-id="8fc51-157">Cmdlets should never call [System.Console.Writeline\*](/dotnet/api/System.Console.WriteLine) or its equivalent.</span></span>

- <span data-ttu-id="8fc51-158">Cmdlet 在处理完后可能会有要清理的对象变量 (例如，如果它打开 [BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) 方法中的文件句柄，并使该句柄处于打开状态以供 [ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)) 使用。</span><span class="sxs-lookup"><span data-stu-id="8fc51-158">Your cmdlet might have object variables to clean up when it is finished processing (for example, if it opens a file handle in the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method and keeps the handle open for use by [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)).</span></span> <span data-ttu-id="8fc51-159">请记住，Windows PowerShell 运行时并不总是调用应执行对象清理的 [system.web](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 方法，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="8fc51-159">It is important to remember that the Windows PowerShell runtime does not always call the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method, which should perform object cleanup.</span></span>

<span data-ttu-id="8fc51-160">例如，如果 cmdlet 在中间取消或在 cmdlet 的任何部分中出现终止错误，则可能不会调用 [system.object](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) 。</span><span class="sxs-lookup"><span data-stu-id="8fc51-160">For example, [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) might not be called if the cmdlet is canceled midway or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="8fc51-161">因此，需要对象清理的 cmdlet 应该实现完整的[IDisposable](/dotnet/api/System.IDisposable)模式（包括终结器），以便运行时可以在处理结束时调用[IDisposable \* 和 \*](/dotnet/api/System.IDisposable.Dispose)的项[操作。](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)</span><span class="sxs-lookup"><span data-stu-id="8fc51-161">Therefore, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including the finalizer, so that the runtime can call both [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) and [System.IDisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) at the end of processing.</span></span>

## <a name="code-sample"></a><span data-ttu-id="8fc51-162">代码示例</span><span class="sxs-lookup"><span data-stu-id="8fc51-162">Code Sample</span></span>

<span data-ttu-id="8fc51-163">有关完整的 c # 示例代码，请参阅 [GetProcessSample01 示例](./getprocesssample01-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="8fc51-163">For the complete C# sample code, see [GetProcessSample01 Sample](./getprocesssample01-sample.md).</span></span>

## <a name="defining-object-types-and-formatting"></a><span data-ttu-id="8fc51-164">定义对象类型和格式设置</span><span class="sxs-lookup"><span data-stu-id="8fc51-164">Defining Object Types and Formatting</span></span>

<span data-ttu-id="8fc51-165">Windows PowerShell 使用 .NET 对象在 cmdlet 之间传递信息。</span><span class="sxs-lookup"><span data-stu-id="8fc51-165">Windows PowerShell passes information between cmdlets using .NET objects.</span></span> <span data-ttu-id="8fc51-166">因此，cmdlet 可能需要定义自己的类型，或者该 cmdlet 可能需要扩展另一个 cmdlet 提供的现有类型。</span><span class="sxs-lookup"><span data-stu-id="8fc51-166">Consequently, a cmdlet might need to define its own type, or the cmdlet might need to extend an existing type provided by another cmdlet.</span></span> <span data-ttu-id="8fc51-167">有关定义新类型或扩展现有类型的详细信息，请参阅 [扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="8fc51-167">For more information about defining new types or extending existing types, see [Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85)).</span></span>

## <a name="building-the-cmdlet"></a><span data-ttu-id="8fc51-168">构建 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8fc51-168">Building the Cmdlet</span></span>

<span data-ttu-id="8fc51-169">实现 cmdlet 后，必须通过 Windows PowerShell 管理单元将其注册到 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8fc51-169">After implementing a cmdlet, you must register it with Windows PowerShell through a Windows PowerShell snap-in.</span></span> <span data-ttu-id="8fc51-170">有关注册 cmdlet 的详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="8fc51-170">For more information about registering cmdlets, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

## <a name="testing-the-cmdlet"></a><span data-ttu-id="8fc51-171">测试 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8fc51-171">Testing the Cmdlet</span></span>

<span data-ttu-id="8fc51-172">向 Windows PowerShell 注册 cmdlet 后，可以通过在命令行上运行 cmdlet 来对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="8fc51-172">When your cmdlet has been registered with Windows PowerShell, you can test it by running it on the command line.</span></span> <span data-ttu-id="8fc51-173">示例 Get-Proc cmdlet 的代码很小，但它仍使用 Windows PowerShell 运行时和现有的 .NET 对象，这足以使它非常有用。</span><span class="sxs-lookup"><span data-stu-id="8fc51-173">The code for our sample Get-Proc cmdlet is small, but it still uses the Windows PowerShell runtime and an existing .NET object, which is enough to make it useful.</span></span> <span data-ttu-id="8fc51-174">让我们对它进行测试，以便更好地了解 Get-Proc 可以执行哪些操作以及如何使用其输出。</span><span class="sxs-lookup"><span data-stu-id="8fc51-174">Let's test it to better understand what Get-Proc can do and how its output can be used.</span></span> <span data-ttu-id="8fc51-175">有关从命令行使用 cmdlet 的详细信息，请参阅 [使用 Windows PowerShell 的入门](/powershell/scripting/getting-started/getting-started-with-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8fc51-175">For more information about using cmdlets from the command line, see the [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).</span></span>

1. <span data-ttu-id="8fc51-176">启动 Windows PowerShell，并获取正在计算机上运行的当前进程。</span><span class="sxs-lookup"><span data-stu-id="8fc51-176">Start Windows PowerShell, and get the current processes running on the computer.</span></span>

    ```powershell
    get-proc
    ```

    <span data-ttu-id="8fc51-177">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="8fc51-177">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    254      7       7664   12048  66     173.75  1200  QCTRAY
    32       2       1372   2628   31       0.04  1860  DLG
    271      6       1216   3688   33       0.03  3816  lg
    27       2       560    1920   24       0.01  1768  TpScrex
    ...
    ```

2. <span data-ttu-id="8fc51-178">将一个变量分配给 cmdlet 结果，以便更轻松地执行操作。</span><span class="sxs-lookup"><span data-stu-id="8fc51-178">Assign a variable to the cmdlet results for easier manipulation.</span></span>

    ```powershell
    $p=get-proc
    ```

3. <span data-ttu-id="8fc51-179">获取进程数。</span><span class="sxs-lookup"><span data-stu-id="8fc51-179">Get the number of processes.</span></span>

    ```powershell
    $p.length
    ```

    <span data-ttu-id="8fc51-180">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="8fc51-180">The following output appears.</span></span>

    ```output
    63
    ```

4. <span data-ttu-id="8fc51-181">检索特定进程。</span><span class="sxs-lookup"><span data-stu-id="8fc51-181">Retrieve a specific process.</span></span>

    ```powershell
    $p[6]
    ```

    <span data-ttu-id="8fc51-182">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="8fc51-182">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id    ProcessName
    -------  ------  -----  -----  -----  ------  --    -----------
    1033     3       2400   3336   35     0.53    1588  rundll32
    ```

5. <span data-ttu-id="8fc51-183">获取此过程的开始时间。</span><span class="sxs-lookup"><span data-stu-id="8fc51-183">Get the start time of this process.</span></span>

    ```powershell
    $p[6].starttime
    ```

    <span data-ttu-id="8fc51-184">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="8fc51-184">The following output appears.</span></span>

    ```output
    Tuesday, July 26, 2005 9:34:15 AM
    ```

    ```powershell
    $p[6].starttime.dayofyear
    ```

    ```output
    207
    ```

6. <span data-ttu-id="8fc51-185">获取句柄计数大于500的进程，并对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="8fc51-185">Get the processes for which the handle count is greater than 500, and sort the result.</span></span>

    ```powershell
    $p | Where-Object {$_.HandleCount -gt 500 } | Sort-Object HandleCount
    ```

    <span data-ttu-id="8fc51-186">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="8fc51-186">The following output appears.</span></span>

    ```output
    Handles  NPM(K)  PM(K)  WS(K)  VS(M)  CPU(s)  Id   ProcessName
    -------  ------  -----  -----  -----  ------  --   ----------
    568      14      2164   4972   39     5.55    824  svchost
    716       7      2080   5332   28    25.38    468  csrss
    761      21      33060  56608  440  393.56    3300 WINWORD
    791      71      7412   4540   59     3.31    492  winlogon
    ...
    ```

7. <span data-ttu-id="8fc51-187">使用 `Get-Member` cmdlet 列出可用于每个进程的属性。</span><span class="sxs-lookup"><span data-stu-id="8fc51-187">Use the `Get-Member` cmdlet to list the properties available for each process.</span></span>

    ```powershell
    $p | Get-Member -MemberType property
    ```

    ```output
        TypeName: System.Diagnostics.Process
    ```

    <span data-ttu-id="8fc51-188">将显示以下输出。</span><span class="sxs-lookup"><span data-stu-id="8fc51-188">The following output appears.</span></span>

    ```output
    Name                     MemberType Definition
    ----                     ---------- ----------
    BasePriority             Property   System.Int32 BasePriority {get;}
    Container                Property   System.ComponentModel.IContainer Conta...
    EnableRaisingEvents      Property   System.Boolean EnableRaisingEvents {ge...
    ...
    ```

## <a name="see-also"></a><span data-ttu-id="8fc51-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fc51-189">See Also</span></span>

[<span data-ttu-id="8fc51-190">创建 Cmdlet 来处理命令行输入</span><span class="sxs-lookup"><span data-stu-id="8fc51-190">Creating a Cmdlet to Process Command Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="8fc51-191">创建用于处理管道输入的 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8fc51-191">Creating a Cmdlet to Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="8fc51-192">如何创建 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8fc51-192">How to Create a Windows PowerShell Cmdlet</span></span>](/powershell/scripting/developer/cmdlet/writing-a-windows-powershell-cmdlet)

<span data-ttu-id="8fc51-193">[扩展对象类型和格式](/previous-versions//ms714665(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="8fc51-193">[Extending Object Types and Formatting](/previous-versions//ms714665(v=vs.85))</span></span>

<span data-ttu-id="8fc51-194">[Windows PowerShell 的工作原理](/previous-versions//ms714658(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="8fc51-194">[How Windows PowerShell Works](/previous-versions//ms714658(v=vs.85))</span></span>

<span data-ttu-id="8fc51-195">[如何注册 Cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="8fc51-195">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85))</span></span>

[<span data-ttu-id="8fc51-196">Windows PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="8fc51-196">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)

[<span data-ttu-id="8fc51-197">Cmdlet 示例</span><span class="sxs-lookup"><span data-stu-id="8fc51-197">Cmdlet Samples</span></span>](./cmdlet-samples.md)
