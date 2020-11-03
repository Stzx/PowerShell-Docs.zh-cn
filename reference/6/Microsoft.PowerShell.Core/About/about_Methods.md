---
description: 描述如何使用方法对 PowerShell 中的对象执行操作。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 45a57efdf16779cfed0df627976270871068ed1f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199806"
---
# <a name="about-methods"></a><span data-ttu-id="118b6-104">关于方法</span><span class="sxs-lookup"><span data-stu-id="118b6-104">About methods</span></span>

## <a name="short-description"></a><span data-ttu-id="118b6-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="118b6-105">Short description</span></span>
<span data-ttu-id="118b6-106">描述如何使用方法对 PowerShell 中的对象执行操作。</span><span class="sxs-lookup"><span data-stu-id="118b6-106">Describes how to use methods to perform actions on objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="118b6-107">长说明</span><span class="sxs-lookup"><span data-stu-id="118b6-107">Long description</span></span>

<span data-ttu-id="118b6-108">PowerShell 使用对象来表示数据存储区中的项或计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="118b6-108">PowerShell uses objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="118b6-109">例如，FileInfo 对象表示文件系统驱动器中的文件，ProcessInfo 对象表示计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="118b6-109">For example, FileInfo objects represent the files in file system drives and ProcessInfo objects represent the processes on the computer.</span></span>

<span data-ttu-id="118b6-110">对象具有属性，这些属性存储有关对象的数据，以及用于更改对象的方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-110">Objects have properties, which store data about the object, and methods that let you change the object.</span></span>

<span data-ttu-id="118b6-111">"方法" 是指定可对对象执行的操作的一组指令。</span><span class="sxs-lookup"><span data-stu-id="118b6-111">A "method" is a set of instructions that specify an action you can perform on the object.</span></span> <span data-ttu-id="118b6-112">例如， `FileInfo` 对象包括 `CopyTo` 复制该对象所表示的文件的方法 `FileInfo` 。</span><span class="sxs-lookup"><span data-stu-id="118b6-112">For example, the `FileInfo` object includes the `CopyTo` method that copies the file that the `FileInfo` object represents.</span></span>

<span data-ttu-id="118b6-113">若要获取任何对象的方法，请使用 `Get-Member` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="118b6-113">To get the methods of any object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="118b6-114">使用值为 "Method" 的 **MemberType** 属性。</span><span class="sxs-lookup"><span data-stu-id="118b6-114">Use its **MemberType** property with a value of "Method".</span></span> <span data-ttu-id="118b6-115">以下命令获取进程对象的方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-115">The following command gets the methods of process objects.</span></span>

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

<span data-ttu-id="118b6-116">若要执行或 "调用" 对象的方法，请键入点 (. ) 、方法名称和一组括号 " ( # A3"。</span><span class="sxs-lookup"><span data-stu-id="118b6-116">To perform or "invoke" a method of an object, type a dot (.), the method name, and a set of parentheses "()".</span></span> <span data-ttu-id="118b6-117">如果该方法具有参数，请将参数值放在括号内。</span><span class="sxs-lookup"><span data-stu-id="118b6-117">If the method has arguments, place the argument values inside the parentheses.</span></span> <span data-ttu-id="118b6-118">每个方法调用都需要括号，即使没有参数时也是如此。</span><span class="sxs-lookup"><span data-stu-id="118b6-118">The parentheses are required for every method call, even when there are no arguments.</span></span> <span data-ttu-id="118b6-119">如果该方法采用多个参数，则应使用逗号分隔它们。</span><span class="sxs-lookup"><span data-stu-id="118b6-119">If the method takes multiple arguments, they should be separated by commas.</span></span>

<span data-ttu-id="118b6-120">例如，以下命令将调用进程的 Kill 方法，以结束计算机上的记事本进程。</span><span class="sxs-lookup"><span data-stu-id="118b6-120">For example, the following command invokes the Kill method of processes to end the Notepad process on the computer.</span></span>

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

<span data-ttu-id="118b6-121">可以通过组合以上语句来缩短此示例。</span><span class="sxs-lookup"><span data-stu-id="118b6-121">This example can be shortened by combining the above statements.</span></span>

```powershell
(Get-Process Notepad).Kill()
```

<span data-ttu-id="118b6-122">`Get-Process`命令括在括号中，以确保在调用 Kill 方法之前运行该命令。</span><span class="sxs-lookup"><span data-stu-id="118b6-122">The `Get-Process` command is enclosed in parentheses to ensure that it runs before the Kill method is invoked.</span></span> <span data-ttu-id="118b6-123">`Kill`然后，在返回的对象上调用方法 `Process` 。</span><span class="sxs-lookup"><span data-stu-id="118b6-123">The `Kill` method is then invoked on the returned `Process` object.</span></span>

<span data-ttu-id="118b6-124">另一种非常有用的方法是 `Replace` 字符串的方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-124">Another very useful method is the `Replace` method of strings.</span></span> <span data-ttu-id="118b6-125">`Replace`方法将替换字符串中的文本。</span><span class="sxs-lookup"><span data-stu-id="118b6-125">The `Replace` method, replaces text within a string.</span></span> <span data-ttu-id="118b6-126">在下面的示例中，点 (。 ) 可以紧跟在字符串的右引号之后。</span><span class="sxs-lookup"><span data-stu-id="118b6-126">In the example below, the dot (.) can be placed immediately after the end quote of the string.</span></span>

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

<span data-ttu-id="118b6-127">如前面的示例所示，您可以对通过使用命令、变量中的对象或导致对象 (如引号) 中的字符串的任何内容的对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-127">As shown in the previous examples, you can invoke a method on an object that you get by using a command, an object in a variable, or anything that results in an object (like a string in quotes).</span></span>

<span data-ttu-id="118b6-128">从 PowerShell 4.0 开始，支持通过使用动态方法名称进行方法调用。</span><span class="sxs-lookup"><span data-stu-id="118b6-128">Starting in PowerShell 4.0, method invocation by using dynamic method names is supported.</span></span>

### <a name="learning-about-methods"></a><span data-ttu-id="118b6-129">了解方法</span><span class="sxs-lookup"><span data-stu-id="118b6-129">Learning about methods</span></span>

<span data-ttu-id="118b6-130">若要查找对象的方法的定义，请在 MSDN 中的对象类型中转到 "帮助" 主题，并查找其 "方法" 页。</span><span class="sxs-lookup"><span data-stu-id="118b6-130">To find definitions of the methods of an object, go to help topic for the object type in MSDN and look for its methods page.</span></span> <span data-ttu-id="118b6-131">例如，下面的页描述[进程对象的处理方法。](/dotnet/api/system.diagnostics.process#methods)</span><span class="sxs-lookup"><span data-stu-id="118b6-131">For example, the following page describes the methods of process objects [System.Diagnostics.Process](/dotnet/api/system.diagnostics.process#methods).</span></span>

<span data-ttu-id="118b6-132">若要确定方法的参数，请查看方法定义，它类似于 PowerShell cmdlet 的语法关系图。</span><span class="sxs-lookup"><span data-stu-id="118b6-132">To determine the arguments of a method, review the method definition, which is like the syntax diagram of a PowerShell cmdlet.</span></span>

<span data-ttu-id="118b6-133">方法定义可能有一个或多个方法签名，如 PowerShell cmdlet 的参数集。</span><span class="sxs-lookup"><span data-stu-id="118b6-133">A method definition might have one or more method signatures, which are like the parameter sets of PowerShell cmdlets.</span></span> <span data-ttu-id="118b6-134">签名显示了用于调用方法的所有有效命令格式。</span><span class="sxs-lookup"><span data-stu-id="118b6-134">The signatures show all of the valid formats of commands to invoke the method.</span></span>

<span data-ttu-id="118b6-135">例如，类的 `CopyTo` 方法 `FileInfo` 包含以下两个方法签名：</span><span class="sxs-lookup"><span data-stu-id="118b6-135">For example, the `CopyTo` method of the `FileInfo` class contains the following two method signatures:</span></span>

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

<span data-ttu-id="118b6-136">第一种方法签名采用目标文件名 (，路径) 。</span><span class="sxs-lookup"><span data-stu-id="118b6-136">The first method signature takes the destination file name (and a path).</span></span> <span data-ttu-id="118b6-137">下面的示例使用第一 `CopyTo` 种方法将 `Final.txt` 文件复制到 `C:\Bin` 目录。</span><span class="sxs-lookup"><span data-stu-id="118b6-137">The following example uses the first `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> <span data-ttu-id="118b6-138">与 PowerShell 的 _参数_ 模式不同，对象方法以 _表达式_ 模式执行，后者是对生成 PowerShell 的 .net framework 的传递。</span><span class="sxs-lookup"><span data-stu-id="118b6-138">Unlike PowerShell's _argument_ mode, object methods execute in _expression_ mode, which is a pass-through to the .NET framework that PowerShell is built on.</span></span> <span data-ttu-id="118b6-139">_表达式_ 模式中的 **bareword** 参数 (不允许使用不带引号的字符串) 。</span><span class="sxs-lookup"><span data-stu-id="118b6-139">In _expression_ mode **bareword** arguments (unquoted strings) are not allowed.</span></span> <span data-ttu-id="118b6-140">使用路径作为参数，而将路径用作参数时，可以看到这种差异。</span><span class="sxs-lookup"><span data-stu-id="118b6-140">You can see this difference when using a the path as a parameter, versus the path as an argument.</span></span> <span data-ttu-id="118b6-141">可以在[about_Parsing](about_Parsing.md)中详细了解分析模式</span><span class="sxs-lookup"><span data-stu-id="118b6-141">You can read more about parsing modes in [about_Parsing](about_Parsing.md)</span></span>

<span data-ttu-id="118b6-142">第二个方法签名采用目标文件名和确定是否应覆盖目标文件（如果该文件已存在）的布尔值。</span><span class="sxs-lookup"><span data-stu-id="118b6-142">The second method signature takes a destination file name and a Boolean value that determines whether the destination file should be overwritten, if it already exists.</span></span>

<span data-ttu-id="118b6-143">下面的示例使用第二 `CopyTo` 种方法将 `Final.txt` 文件复制到 `C:\Bin` 目录，并覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="118b6-143">The following example uses the second `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory, and to overwrite existing files.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

### <a name="methods-of-scalar-objects-and-collections"></a><span data-ttu-id="118b6-144">标量对象和集合的方法</span><span class="sxs-lookup"><span data-stu-id="118b6-144">Methods of Scalar objects and Collections</span></span>

<span data-ttu-id="118b6-145">一个特定类型 ( "标量" ) 对象的方法通常不同于同一类型的对象集合的方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-145">The methods of one ("scalar") object of a particular type are often different from the methods of a collection of objects of the same type.</span></span>

<span data-ttu-id="118b6-146">例如，每个进程都有一 `Kill` 种方法，但进程集合没有 Kill 方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-146">For example, every process has a `Kill` method, but a collection of processes does not have a Kill method.</span></span>

<span data-ttu-id="118b6-147">从 PowerShell 3.0 开始，PowerShell 将尝试防止标量对象和集合的不同方法导致的脚本错误。</span><span class="sxs-lookup"><span data-stu-id="118b6-147">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing methods of scalar objects and collections.</span></span>

<span data-ttu-id="118b6-148">如果提交集合，但请求仅存在于单个 ( "标量" ) 对象中的方法，则 PowerShell 将对集合中的每个对象调用方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-148">If you submit a collection, but request a method that exists only on single ("scalar") objects, PowerShell invokes the method on every object in the collection.</span></span>

<span data-ttu-id="118b6-149">如果方法存在于单个对象和集合上，则只调用集合的方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-149">If the method exists on the individual objects and on the collection, only the collection's method is invoked.</span></span>

<span data-ttu-id="118b6-150">此功能也适用于标量对象和集合的属性。</span><span class="sxs-lookup"><span data-stu-id="118b6-150">This feature also works on properties of scalar objects and collections.</span></span> <span data-ttu-id="118b6-151">有关详细信息，请参阅 [about_Properties](about_Properties.md)。</span><span class="sxs-lookup"><span data-stu-id="118b6-151">For more information, see [about_Properties](about_Properties.md).</span></span>

### <a name="examples"></a><span data-ttu-id="118b6-152">示例</span><span class="sxs-lookup"><span data-stu-id="118b6-152">Examples</span></span>

<span data-ttu-id="118b6-153">下面的示例在对象集合中运行单个进程对象的 **Kill** 方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-153">The following example runs the **Kill** method of individual process objects in a collection of objects.</span></span>

<span data-ttu-id="118b6-154">第一条命令启动记事本进程的三个实例。</span><span class="sxs-lookup"><span data-stu-id="118b6-154">The first command starts three instances of the Notepad process.</span></span> <span data-ttu-id="118b6-155">`Get-Process` 获取记事本进程的所有三个实例，并将它们保存在 `$p` 变量中。</span><span class="sxs-lookup"><span data-stu-id="118b6-155">`Get-Process` gets all three instance of the Notepad process and saves them in the `$p` variable.</span></span>

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

<span data-ttu-id="118b6-156">下一个命令对变量中的所有三个进程运行 **Kill** 方法 `$p` 。</span><span class="sxs-lookup"><span data-stu-id="118b6-156">The next command runs the **Kill** method on all three processes in the `$p` variable.</span></span> <span data-ttu-id="118b6-157">即使进程集合没有方法，此命令也有效 `Kill` 。</span><span class="sxs-lookup"><span data-stu-id="118b6-157">This command works even though a collection of processes does not have a `Kill` method.</span></span>

```powershell
$p.Kill()
Get-Process Notepad
```

<span data-ttu-id="118b6-158">`Get-Process`命令确认 `Kill` 方法是否有效。</span><span class="sxs-lookup"><span data-stu-id="118b6-158">The `Get-Process` command confirms that the `Kill` method worked.</span></span>

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

<span data-ttu-id="118b6-159">此示例在功能上等效于使用 `Foreach-Object` cmdlet 对集合中的每个对象运行方法。</span><span class="sxs-lookup"><span data-stu-id="118b6-159">This example is functionally equivalent to using the `Foreach-Object` cmdlet to run the method on each object in the collection.</span></span>

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a><span data-ttu-id="118b6-160">ForEach 和 Where 方法</span><span class="sxs-lookup"><span data-stu-id="118b6-160">ForEach and Where methods</span></span>

<span data-ttu-id="118b6-161">从 PowerShell 4.0 开始，支持使用方法语法进行集合筛选。</span><span class="sxs-lookup"><span data-stu-id="118b6-161">Beginning in PowerShell 4.0, collection filtering by using a method syntax is supported.</span></span> <span data-ttu-id="118b6-162">这允许在处理集合和时使用两种新 `ForEach` 方法 `Where` 。</span><span class="sxs-lookup"><span data-stu-id="118b6-162">This allows use of two new methods when dealing with collections `ForEach` and `Where`.</span></span>

<span data-ttu-id="118b6-163">可阅读 [about_arrays](about_arrays.md) 了解有关这些方法的详细信息</span><span class="sxs-lookup"><span data-stu-id="118b6-163">You can read more about these methods in [about_arrays](about_arrays.md)</span></span>

### <a name="calling-a-specific-method-when-multiple-overloads-exist"></a><span data-ttu-id="118b6-164">当存在多个重载时调用特定方法</span><span class="sxs-lookup"><span data-stu-id="118b6-164">Calling a specific method when multiple overloads exist</span></span>

<span data-ttu-id="118b6-165">调用 .NET 方法时，请考虑以下方案。</span><span class="sxs-lookup"><span data-stu-id="118b6-165">Consider the following scenario when calling .NET methods.</span></span> <span data-ttu-id="118b6-166">如果某个方法接受一个对象，但通过使用更具体的类型的接口具有重载，则 PowerShell 将选择接受该对象的方法，除非你将其显式转换为该接口。</span><span class="sxs-lookup"><span data-stu-id="118b6-166">If a method takes an object but has an overload via an interface taking a more specific type, PowerShell chooses the method that accepts the object unless you explicitly cast it to that interface.</span></span>

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

<span data-ttu-id="118b6-167">在此示例中，选择的是更少的 `object` **Bar** 方法重载。</span><span class="sxs-lookup"><span data-stu-id="118b6-167">In this example the less specific `object` overload of the **Bar** method was chosen.</span></span>

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

<span data-ttu-id="118b6-168">在此示例中，我们将方法强制转换为接口 **IFoo** ，以选择更具体的 **Bar** 方法重载。</span><span class="sxs-lookup"><span data-stu-id="118b6-168">In this example we cast the method to the interface **IFoo** to select the more specific overload of the **Bar** method.</span></span>

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="see-also"></a><span data-ttu-id="118b6-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="118b6-169">See Also</span></span>

[<span data-ttu-id="118b6-170">about_Objects</span><span class="sxs-lookup"><span data-stu-id="118b6-170">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="118b6-171">about_Properties</span><span class="sxs-lookup"><span data-stu-id="118b6-171">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="118b6-172">Get-Member</span><span class="sxs-lookup"><span data-stu-id="118b6-172">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)