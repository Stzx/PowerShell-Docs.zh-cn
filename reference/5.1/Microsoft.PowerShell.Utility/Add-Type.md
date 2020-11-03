---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: af7cd937ccfc7c5f05fd0213764ed51a3ba9f2bb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197970"
---
# <span data-ttu-id="de73b-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="de73b-103">Add-Type</span></span>

## <span data-ttu-id="de73b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="de73b-104">SYNOPSIS</span></span>
<span data-ttu-id="de73b-105">将 Microsoft .NET 框架类添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="de73b-105">Adds a Microsoft .NET Framework class to a PowerShell session.</span></span>

## <span data-ttu-id="de73b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de73b-106">SYNTAX</span></span>

### <span data-ttu-id="de73b-107">FromSource (默认值) </span><span class="sxs-lookup"><span data-stu-id="de73b-107">FromSource (Default)</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [<CommonParameters>]
```

### <span data-ttu-id="de73b-108">FromMember</span><span class="sxs-lookup"><span data-stu-id="de73b-108">FromMember</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>] [-UsingNamespace <String[]>]
 [-Language <Language>] [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="de73b-109">FromPath</span><span class="sxs-lookup"><span data-stu-id="de73b-109">FromPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] [-Path] <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="de73b-110">FromLiteralPath</span><span class="sxs-lookup"><span data-stu-id="de73b-110">FromLiteralPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] -LiteralPath <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="de73b-111">FromAssemblyName</span><span class="sxs-lookup"><span data-stu-id="de73b-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

## <span data-ttu-id="de73b-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="de73b-112">DESCRIPTION</span></span>

<span data-ttu-id="de73b-113">`Add-Type`Cmdlet 可用于在 PowerShell 会话中定义 Microsoft .NET 框架类。</span><span class="sxs-lookup"><span data-stu-id="de73b-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Framework class in your PowerShell session.</span></span>
<span data-ttu-id="de73b-114">然后，可以使用 cmdlet 实例化对象， `New-Object` 并像使用任何 .NET Framework 对象一样使用对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Framework object.</span></span> <span data-ttu-id="de73b-115">如果将命令添加 `Add-Type` 到 powershell 配置文件，则该类可用于所有 powershell 会话。</span><span class="sxs-lookup"><span data-stu-id="de73b-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="de73b-116">你可以通过指定现有程序集或源代码文件来指定类型，也可以指定内联源代码或保存在变量中的源代码。</span><span class="sxs-lookup"><span data-stu-id="de73b-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="de73b-117">甚至可以仅指定方法，并 `Add-Type` 定义和生成类。</span><span class="sxs-lookup"><span data-stu-id="de73b-117">You can even specify only a method and `Add-Type` will define and generate the class.</span></span> <span data-ttu-id="de73b-118">在 Windows 上，可以使用此功能在 PowerShell 中将平台调用 (P/Invoke) 调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="de73b-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="de73b-119">如果指定源代码，将 `Add-Type` 编译指定的源代码，并生成包含新的 .NET Framework 类型的内存中程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Framework types.</span></span>

<span data-ttu-id="de73b-120">您可以使用的参数 `Add-Type` 指定替代语言和编译器，c # 是默认值、编译器选项、程序集依赖项、类命名空间、类型名称和生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="de73b-121">示例</span><span class="sxs-lookup"><span data-stu-id="de73b-121">EXAMPLES</span></span>

### <span data-ttu-id="de73b-122">示例1：向会话添加 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="de73b-122">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="de73b-123">此示例通过指定存储在变量中的源代码，将 **BasicTest** 类添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="de73b-123">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="de73b-124">**BasicTest** 类用于添加整数、创建对象和将整数相乘。</span><span class="sxs-lookup"><span data-stu-id="de73b-124">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

<span data-ttu-id="de73b-125">`$Source`变量存储类的源代码。</span><span class="sxs-lookup"><span data-stu-id="de73b-125">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="de73b-126">该类型具有一个名为的静态方法 `Add` 和一个名为的非静态方法 `Multiply` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-126">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="de73b-127">`Add-Type`Cmdlet 可将类添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="de73b-127">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="de73b-128">由于它使用内联源代码，因此该命令使用 **TypeDefinition** 参数来指定变量中的代码 `$Source` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-128">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="de73b-129">`Add` **BasicTest** 类的静态方法使用双冒号字符 (`::`) 来指定类的静态成员。</span><span class="sxs-lookup"><span data-stu-id="de73b-129">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="de73b-130">添加整数并显示总和。</span><span class="sxs-lookup"><span data-stu-id="de73b-130">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="de73b-131">`New-Object`Cmdlet 实例化 **BasicTest** 类的实例。</span><span class="sxs-lookup"><span data-stu-id="de73b-131">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="de73b-132">它将新对象保存在 `$BasicTestObject` 变量中。</span><span class="sxs-lookup"><span data-stu-id="de73b-132">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="de73b-133">`$BasicTestObject` 使用 `Multiply` 方法。</span><span class="sxs-lookup"><span data-stu-id="de73b-133">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="de73b-134">整数相乘并显示产品。</span><span class="sxs-lookup"><span data-stu-id="de73b-134">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="de73b-135">示例2：检查添加的类型</span><span class="sxs-lookup"><span data-stu-id="de73b-135">Example 2: Examine an added type</span></span>

<span data-ttu-id="de73b-136">此示例使用 `Get-Member` cmdlet 检查在 `Add-Type` `New-Object` **示例 1** 中创建的和 cmdlet 的对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-136">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1** .</span></span>

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

<span data-ttu-id="de73b-137">`Get-Member`Cmdlet 可获取添加到会话中的 **BasicTest** 类的类型和成员 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-137">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="de73b-138">该 `Get-Member` 命令显示它是一个派生自 **system.object** 类的 **RuntimeType** 对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-138">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="de73b-139">`Get-Member`**静态** 参数获取 **BasicTest** 类的静态属性和方法。</span><span class="sxs-lookup"><span data-stu-id="de73b-139">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="de73b-140">输出显示此 `Add` 方法已包括在内。</span><span class="sxs-lookup"><span data-stu-id="de73b-140">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="de73b-141">`Get-Member`Cmdlet 将获取存储在变量中的对象的成员 `$BasicTestObject` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-141">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="de73b-142">`$BasicTestObject` 是通过对 `New-Object` **BasicTest** 类使用 cmdlet 创建的。</span><span class="sxs-lookup"><span data-stu-id="de73b-142">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="de73b-143">输出显示变量的值 `$BasicTestObject` 是 **BasicTest** 类的一个实例，并且它包括一个名为的成员 `Multiply` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-143">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="de73b-144">示例3：从程序集添加类型</span><span class="sxs-lookup"><span data-stu-id="de73b-144">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="de73b-145">此示例将程序集的类添加 `Accessibility.dll` 到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="de73b-145">This example adds the classes from the `Accessibility.dll` assembly to the current session.</span></span>

```powershell
$AccType = Add-Type -AssemblyName "accessib*" -PassThru
```

<span data-ttu-id="de73b-146">`$AccType`变量存储使用 cmdlet 创建的对象 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-146">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="de73b-147">`Add-Type` 使用 **AssemblyName** 参数指定程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="de73b-147">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="de73b-148">星号 (`*`) 通配符允许您获取正确的程序集，即使您不确定名称或其拼写时也是如此。</span><span class="sxs-lookup"><span data-stu-id="de73b-148">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="de73b-149">**PassThru** 参数生成对象，这些对象表示添加到会话中的类。</span><span class="sxs-lookup"><span data-stu-id="de73b-149">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="de73b-150">示例4：调用本机 Windows Api</span><span class="sxs-lookup"><span data-stu-id="de73b-150">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="de73b-151">此示例演示如何在 PowerShell 中调用本机 Windows Api。</span><span class="sxs-lookup"><span data-stu-id="de73b-151">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="de73b-152">`Add-Type` 使用平台调用 (P/Invoke) 机制从 PowerShell 调用中的函数 `User32.dll` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-152">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="de73b-153">此示例仅适用于运行 Windows 操作系统的计算机。</span><span class="sxs-lookup"><span data-stu-id="de73b-153">This example only works on computers running the Windows operating system.</span></span>

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

<span data-ttu-id="de73b-154">`$Signature`变量存储函数的 c # 签名 `ShowWindowAsync` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-154">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="de73b-155">为了确保生成的方法将在 PowerShell 会话中可见， `public` 关键字已添加到标准签名中。</span><span class="sxs-lookup"><span data-stu-id="de73b-155">To ensure that the resulting method will be visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="de73b-156">有关详细信息，请参阅 [ShowWindowAsync 函数](/windows/win32/api/winuser/nf-winuser-showwindowasync)。</span><span class="sxs-lookup"><span data-stu-id="de73b-156">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="de73b-157">`$ShowWindowAsync`变量存储通过 `Add-Type` **PassThru** 参数创建的对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-157">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="de73b-158">`Add-Type`Cmdlet 将 `ShowWindowAsync` 函数作为静态方法添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="de73b-158">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="de73b-159">该命令使用 **MemberDefinition** 参数来指定保存在变量中的方法定义 `$Signature` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-159">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="de73b-160">该命令使用 **Name** 和 **Namespace** 参数来指定类的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="de73b-160">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="de73b-161">**PassThru** 参数生成一个表示类型的对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-161">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="de73b-162">`ShowWindowAsync`在命令中使用新的静态方法来最小化和还原 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="de73b-162">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="de73b-163">此方法采用两个参数：窗口句柄和指定如何显示窗口的整数。</span><span class="sxs-lookup"><span data-stu-id="de73b-163">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="de73b-164">若要最大程度地减少 PowerShell 控制台，请 `ShowWindowAsync` 将 `Get-Process` cmdlet 与自动变量一起使用， `$PID` 以获取托管当前 PowerShell 会话的进程。</span><span class="sxs-lookup"><span data-stu-id="de73b-164">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="de73b-165">然后，它使用当前进程的 **MainWindowHandle** 属性和值 `2` （表示 `SW_MINIMIZE` 值）。</span><span class="sxs-lookup"><span data-stu-id="de73b-165">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="de73b-166">若要还原窗口，请将的 `ShowWindowAsync` 值 `4` 用于窗口位置，它表示 `SW_RESTORE` 值。</span><span class="sxs-lookup"><span data-stu-id="de73b-166">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="de73b-167">若要最大化窗口，请使用 `3` 表示的值 `SW_MAXIMIZE` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-167">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

### <span data-ttu-id="de73b-168">示例5：从 Visual Basic 文件中添加类型</span><span class="sxs-lookup"><span data-stu-id="de73b-168">Example 5: Add a type from a Visual Basic file</span></span>

<span data-ttu-id="de73b-169">此示例使用 `Add-Type` cmdlet 将在文件中定义的 **VBFromFile** 类添加 `Hello.vb` 到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="de73b-169">This example uses the `Add-Type` cmdlet to add the **VBFromFile** class that's defined in the `Hello.vb` file to the current session.</span></span> <span data-ttu-id="de73b-170">`Hello.vb`文件文本显示在命令输出中。</span><span class="sxs-lookup"><span data-stu-id="de73b-170">The text of the `Hello.vb` file is shown in the command output.</span></span>

```powershell
Add-Type -Path "C:\PS-Test\Hello.vb"
[VBFromFile]::SayHello(", World")

# From Hello.vb

Public Class VBFromFile
  Public Shared Function SayHello(sourceName As String) As String
    Dim myValue As String = "Hello"
    return myValue + sourceName
  End Function
End Class
```

```Output
Hello, World
```

<span data-ttu-id="de73b-171">`Add-Type` 使用 **Path** 参数指定源文件， `Hello.vb` 并添加在文件中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-171">`Add-Type` uses the **Path** parameter to specify the source file, `Hello.vb`, and adds the type defined in the file.</span></span> <span data-ttu-id="de73b-172">此 `SayHello` 函数作为 **VBFromFile** 类的静态方法进行调用。</span><span class="sxs-lookup"><span data-stu-id="de73b-172">The `SayHello` function is called as a static method of the **VBFromFile** class.</span></span>

### <span data-ttu-id="de73b-173">示例6：使用 JScript.NET 添加类</span><span class="sxs-lookup"><span data-stu-id="de73b-173">Example 6: Add a class with JScript.NET</span></span>

<span data-ttu-id="de73b-174">此示例使用 JScript.NET 在 PowerShell 会话中创建新的 **FRectangle** 类。</span><span class="sxs-lookup"><span data-stu-id="de73b-174">This example uses JScript.NET to create a new class, **FRectangle** , in your PowerShell session.</span></span>

```powershell
Add-Type @'
 class FRectangle {
   var Length : double;
   var Height : double;
   function Perimeter() : double {
       return (Length + Height) * 2; }
   function Area() : double {
       return Length * Height;  } }
'@ -Language JScript

$rect = [FRectangle]::new()
$rect
```

```Output
Length Height
------ ------
     0      0
```

### <span data-ttu-id="de73b-175">示例7：添加 F # 编译器</span><span class="sxs-lookup"><span data-stu-id="de73b-175">Example 7: Add an F# compiler</span></span>

<span data-ttu-id="de73b-176">此示例演示如何使用 `Add-Type` cmdlet 将 F # 代码编译器添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="de73b-176">This example shows how to use the `Add-Type` cmdlet to add an F# code compiler to your PowerShell session.</span></span> <span data-ttu-id="de73b-177">若要在 PowerShell 中运行此示例，必须 `FSharp.Compiler.CodeDom.dll` 安装有 F # 语言的。</span><span class="sxs-lookup"><span data-stu-id="de73b-177">To run this example in PowerShell, you must have the `FSharp.Compiler.CodeDom.dll` that is installed with the F# language.</span></span>

```powershell
Add-Type -Path "FSharp.Compiler.CodeDom.dll"
$Provider = New-Object Microsoft.FSharp.Compiler.CodeDom.FSharpCodeProvider
$FSharpCode = @"
let rec loop n =if n <= 0 then () else beginprint_endline (string_of_int n);loop (n-1)end
"@
$FSharpType = Add-Type -TypeDefinition $FSharpCode -CodeDomProvider $Provider -PassThru |
   Where-Object { $_.IsPublic }
$FSharpType::loop(4)
```

```Output
4
3
2
1
```

<span data-ttu-id="de73b-178">`Add-Type` 使用 **Path** 参数指定程序集并获取程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-178">`Add-Type` uses the **Path** parameter to specify an assembly and gets the types in the assembly.</span></span>
<span data-ttu-id="de73b-179">`New-Object` 创建 F # 代码提供程序的实例，并将结果保存在 `$Provider` 变量中。</span><span class="sxs-lookup"><span data-stu-id="de73b-179">`New-Object` creates an instance of the F# code provider and saves the result in the `$Provider` variable.</span></span> <span data-ttu-id="de73b-180">`$FSharpCode`变量保存定义 **Loop** 方法的 F # 代码。</span><span class="sxs-lookup"><span data-stu-id="de73b-180">The `$FSharpCode` variable saves the F# code that defines the **Loop** method.</span></span>

<span data-ttu-id="de73b-181">`$FSharpType`变量存储 cmdlet 的结果 `Add-Type` ，这些结果保存在中定义的公共类型 `$FSharpCode` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-181">The the `$FSharpType` variable stores the results of the `Add-Type` cmdlet that saves the public types defined in `$FSharpCode`.</span></span> <span data-ttu-id="de73b-182">**TypeDefinition** 参数指定定义类型的源代码。</span><span class="sxs-lookup"><span data-stu-id="de73b-182">The **TypeDefinition** parameter specifies the source code that defines the types.</span></span> <span data-ttu-id="de73b-183">**CodeDomProvider** 参数指定源代码编译器。</span><span class="sxs-lookup"><span data-stu-id="de73b-183">The **CodeDomProvider** parameter specifies the source code compiler.</span></span> <span data-ttu-id="de73b-184">**PassThru** 参数指示 `Add-Type` 返回表示类型的 **运行时** 对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-184">The **PassThru** parameter directs `Add-Type` to return a **Runtime** object that represents the types.</span></span>
<span data-ttu-id="de73b-185">对象通过管道向下发送到 `Where-Object` cmdlet，后者只返回公共类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-185">The objects are sent down the pipeline to the `Where-Object` cmdlet, which returns only the public types.</span></span> <span data-ttu-id="de73b-186">使用 **Where-Object** cmdlet，因为 F # 提供程序生成非公共类型以支持生成的公共类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-186">The **Where-Object** cmdlet is used because the F# provider generates non-public types to support the resulting public type.</span></span>

<span data-ttu-id="de73b-187">循环方法被调用为变量中存储的类型的静态方法 `$FSharpType` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-187">The Loop method is called as a static method of the type stored in the `$FSharpType` variable.</span></span>

## <span data-ttu-id="de73b-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de73b-188">PARAMETERS</span></span>

### <span data-ttu-id="de73b-189">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="de73b-189">-AssemblyName</span></span>

<span data-ttu-id="de73b-190">指定包含类型的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="de73b-190">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="de73b-191">`Add-Type` 采用指定程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-191">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="de73b-192">基于程序集名称创建类型时，此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="de73b-192">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="de73b-193">输入程序集的完整名称或简单名称（也称为 "部分名称"）。</span><span class="sxs-lookup"><span data-stu-id="de73b-193">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="de73b-194">在程序集名称中允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="de73b-194">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="de73b-195">如果输入简单名称或部分名称，则将 `Add-Type` 其解析为完整名称，然后使用完整名称加载程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-195">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="de73b-196">此参数不接受路径或文件名。</span><span class="sxs-lookup"><span data-stu-id="de73b-196">This parameter doesn't accept a path or a file name.</span></span> <span data-ttu-id="de73b-197">若要输入程序集动态链接库的路径 (DLL) 文件，请使用 **path** 参数。</span><span class="sxs-lookup"><span data-stu-id="de73b-197">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="de73b-198">-CodeDomProvider</span><span class="sxs-lookup"><span data-stu-id="de73b-198">-CodeDomProvider</span></span>

<span data-ttu-id="de73b-199">指定代码生成器或编译器。</span><span class="sxs-lookup"><span data-stu-id="de73b-199">Specifies a code generator or compiler.</span></span> <span data-ttu-id="de73b-200">`Add-Type` 使用指定的编译器来编译源代码。</span><span class="sxs-lookup"><span data-stu-id="de73b-200">`Add-Type` uses the specified compiler to compile the source code.</span></span> <span data-ttu-id="de73b-201">默认值为 c # 编译器。</span><span class="sxs-lookup"><span data-stu-id="de73b-201">The default is the C# compiler.</span></span> <span data-ttu-id="de73b-202">如果你使用的是不能使用 **language** 参数指定的语言，请使用此参数。</span><span class="sxs-lookup"><span data-stu-id="de73b-202">Use this parameter if you're using a language that can't be specified by using the **Language** parameter.</span></span> <span data-ttu-id="de73b-203">指定的 **CodeDomProvider** 必须能够从源代码生成程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-203">The **CodeDomProvider** that you specify must be able to generate assemblies from source code.</span></span>

```yaml
Type: System.CodeDom.Compiler.CodeDomProvider
Parameter Sets: FromSource, FromMember
Aliases: Provider

Required: False
Position: Named
Default value: C# compiler
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-204">-CompilerParameters</span><span class="sxs-lookup"><span data-stu-id="de73b-204">-CompilerParameters</span></span>

<span data-ttu-id="de73b-205">指定用于源代码编译器的选项。</span><span class="sxs-lookup"><span data-stu-id="de73b-205">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="de73b-206">这些选项无需修改即可发送到编译器。</span><span class="sxs-lookup"><span data-stu-id="de73b-206">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="de73b-207">此参数允许指示编译器生成可执行文件、嵌入资源或设置命令行选项，如 `/unsafe` 选项。</span><span class="sxs-lookup"><span data-stu-id="de73b-207">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span> <span data-ttu-id="de73b-208">此参数实现 **CompilerParameters** 类（ **CompilerParameters** ）。</span><span class="sxs-lookup"><span data-stu-id="de73b-208">This parameter implements the **CompilerParameters** class, **System.CodeDom.Compiler.CompilerParameters** .</span></span>

<span data-ttu-id="de73b-209">不能在同一命令中使用 **CompilerParameters** 和 **ReferencedAssemblies** 参数。</span><span class="sxs-lookup"><span data-stu-id="de73b-209">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.CodeDom.Compiler.CompilerParameters
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: CP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-210">-IgnoreWarnings</span><span class="sxs-lookup"><span data-stu-id="de73b-210">-IgnoreWarnings</span></span>

<span data-ttu-id="de73b-211">忽略编译器警告。</span><span class="sxs-lookup"><span data-stu-id="de73b-211">Ignores compiler warnings.</span></span> <span data-ttu-id="de73b-212">使用此参数可防止将 `Add-Type` 编译器警告作为错误处理。</span><span class="sxs-lookup"><span data-stu-id="de73b-212">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-213">-Language</span><span class="sxs-lookup"><span data-stu-id="de73b-213">-Language</span></span>

<span data-ttu-id="de73b-214">指定在源代码中使用的语言。</span><span class="sxs-lookup"><span data-stu-id="de73b-214">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="de73b-215">`Add-Type`Cmdlet 使用此参数的值来选择适当的 **CodeDomProvider** 。</span><span class="sxs-lookup"><span data-stu-id="de73b-215">The `Add-Type` cmdlet uses the value of this parameter to select the appropriate **CodeDomProvider** .</span></span> <span data-ttu-id="de73b-216">CSharp 为默认值。</span><span class="sxs-lookup"><span data-stu-id="de73b-216">CSharp is the default value.</span></span> <span data-ttu-id="de73b-217">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="de73b-217">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="de73b-218">CSharp</span><span class="sxs-lookup"><span data-stu-id="de73b-218">CSharp</span></span>
- <span data-ttu-id="de73b-219">CSharpVersion2</span><span class="sxs-lookup"><span data-stu-id="de73b-219">CSharpVersion2</span></span>
- <span data-ttu-id="de73b-220">CSharpVersion3</span><span class="sxs-lookup"><span data-stu-id="de73b-220">CSharpVersion3</span></span>
- <span data-ttu-id="de73b-221">JScript</span><span class="sxs-lookup"><span data-stu-id="de73b-221">JScript</span></span>
- <span data-ttu-id="de73b-222">VisualBasic</span><span class="sxs-lookup"><span data-stu-id="de73b-222">VisualBasic</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp, CSharpVersion2, CSharpVersion3, JScript, VisualBasic

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-223">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="de73b-223">-LiteralPath</span></span>

<span data-ttu-id="de73b-224">指定包含类型的源代码文件或程序集 DLL 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="de73b-224">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="de73b-225">与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="de73b-225">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="de73b-226">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="de73b-226">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="de73b-227">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="de73b-227">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="de73b-228">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="de73b-228">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-229">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="de73b-229">-MemberDefinition</span></span>

<span data-ttu-id="de73b-230">指定类的新属性或方法。</span><span class="sxs-lookup"><span data-stu-id="de73b-230">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="de73b-231">`Add-Type` 生成支持属性或方法所需的模板代码。</span><span class="sxs-lookup"><span data-stu-id="de73b-231">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="de73b-232">在 Windows 上，可以使用此功能在 PowerShell 中将平台调用 (P/Invoke) 调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="de73b-232">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-233">-Name</span><span class="sxs-lookup"><span data-stu-id="de73b-233">-Name</span></span>

<span data-ttu-id="de73b-234">指定要创建的类的名称。</span><span class="sxs-lookup"><span data-stu-id="de73b-234">Specifies the name of the class to create.</span></span> <span data-ttu-id="de73b-235">当从成员定义生成类型时，此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="de73b-235">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="de73b-236">类型名称和命名空间在一个会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="de73b-236">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="de73b-237">不能卸载或更改类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-237">You can't unload a type or change it.</span></span>
<span data-ttu-id="de73b-238">若要更改类型的代码，必须更改名称或启动新的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="de73b-238">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="de73b-239">否则，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="de73b-239">Otherwise, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-240">-Namespace</span><span class="sxs-lookup"><span data-stu-id="de73b-240">-Namespace</span></span>

<span data-ttu-id="de73b-241">指定类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="de73b-241">Specifies a namespace for the type.</span></span>

<span data-ttu-id="de73b-242">如果此参数不包括在命令中，则会在 **将. microsoft.powershell.commands.newwebserviceproxy.autogeneratedtypes 和** 命名空间中创建该类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-242">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="de73b-243">如果参数包含在包含空字符串值或值的命令中 `$Null` ，则将在全局命名空间中生成类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-243">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-244">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="de73b-244">-OutputAssembly</span></span>

<span data-ttu-id="de73b-245">在该位置中为具有指定名称的程序集生成 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="de73b-245">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="de73b-246">输入可选的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="de73b-246">Enter an optional path and file name.</span></span> <span data-ttu-id="de73b-247">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="de73b-247">Wildcard characters are permitted.</span></span> <span data-ttu-id="de73b-248">默认情况下， `Add-Type` 仅在内存中生成程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-248">By default, `Add-Type` generates the assembly only in memory.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="de73b-249">-OutputType</span><span class="sxs-lookup"><span data-stu-id="de73b-249">-OutputType</span></span>

<span data-ttu-id="de73b-250">指定输出程序集的输出类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-250">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="de73b-251">默认情况下，不指定输出类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-251">By default, no output type is specified.</span></span> <span data-ttu-id="de73b-252">仅当命令中指定了输出程序集时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="de73b-252">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="de73b-253">有关这些值的详细信息，请参阅 [OutputAssemblyType 枚举](/dotnet/api/microsoft.powershell.commands.outputassemblytype)。</span><span class="sxs-lookup"><span data-stu-id="de73b-253">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="de73b-254">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="de73b-254">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="de73b-255">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="de73b-255">ConsoleApplication</span></span>
- <span data-ttu-id="de73b-256">库</span><span class="sxs-lookup"><span data-stu-id="de73b-256">Library</span></span>
- <span data-ttu-id="de73b-257">Windowsapplication.zip</span><span class="sxs-lookup"><span data-stu-id="de73b-257">WindowsApplication</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-258">-PassThru</span><span class="sxs-lookup"><span data-stu-id="de73b-258">-PassThru</span></span>

<span data-ttu-id="de73b-259">返回表示已添加的类型的 **System.Runtime** 对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-259">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="de73b-260">默认情况下，此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="de73b-260">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-261">-Path</span><span class="sxs-lookup"><span data-stu-id="de73b-261">-Path</span></span>

<span data-ttu-id="de73b-262">指定包含类型的源代码文件或程序集 DLL 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="de73b-262">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="de73b-263">如果提交源代码文件，则会在 `Add-Type` 文件中编译代码，并创建类型的内存中程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-263">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="de73b-264">**Path** 的值中指定的文件扩展名确定使用的编译器 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-264">The file name extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="de73b-265">如果提交程序集文件，则 `Add-Type` 从程序集中获取类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-265">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="de73b-266">若要指定内存中程序集或全局程序集缓存，请使用 **AssemblyName** 参数。</span><span class="sxs-lookup"><span data-stu-id="de73b-266">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-267">-ReferencedAssemblies</span><span class="sxs-lookup"><span data-stu-id="de73b-267">-ReferencedAssemblies</span></span>

<span data-ttu-id="de73b-268">指定类型所依赖的程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-268">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="de73b-269">默认情况下， `Add-Type` 引用 `System.dll` 和 `System.Management.Automation.dll` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-269">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="de73b-270">除了引用默认程序集之外，还将引用你通过使用此参数指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="de73b-270">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="de73b-271">不能在同一命令中使用 **CompilerParameters** 和 **ReferencedAssemblies** 参数。</span><span class="sxs-lookup"><span data-stu-id="de73b-271">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-272">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="de73b-272">-TypeDefinition</span></span>

<span data-ttu-id="de73b-273">指定包含类型定义的源代码。</span><span class="sxs-lookup"><span data-stu-id="de73b-273">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="de73b-274">以字符串或 here-string 的形式输入源代码或输入一个包含源代码的变量。</span><span class="sxs-lookup"><span data-stu-id="de73b-274">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="de73b-275">有关字符串的详细信息，请参阅 [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="de73b-275">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="de73b-276">在类型定义中包括命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="de73b-276">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="de73b-277">如果省略命名空间声明，则你的类型可能会与其他类型或其他类型的快捷方式同名，从而导致意外覆盖。</span><span class="sxs-lookup"><span data-stu-id="de73b-277">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="de73b-278">例如，如果定义了一个名为 **exception** 的类型，则使用 **exception** 作为 system.exception 的快捷 **方式的脚本将失败** 。</span><span class="sxs-lookup"><span data-stu-id="de73b-278">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-279">-UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="de73b-279">-UsingNamespace</span></span>

<span data-ttu-id="de73b-280">指定类所需的其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="de73b-280">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="de73b-281">这非常类似于 c # 关键字 `Using` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-281">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="de73b-282">默认情况下， `Add-Type` 引用 **系统** 命名空间。</span><span class="sxs-lookup"><span data-stu-id="de73b-282">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="de73b-283">如果使用 **MemberDefinition** 参数，则 `Add-Type` 默认情况下也会引用 **InteropServices** 命名空间。</span><span class="sxs-lookup"><span data-stu-id="de73b-283">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="de73b-284">除了引用默认命名空间之外，还将引用你通过使用 **UsingNamespace** 参数添加的命名空间。</span><span class="sxs-lookup"><span data-stu-id="de73b-284">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="de73b-285">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="de73b-285">CommonParameters</span></span>

<span data-ttu-id="de73b-286">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="de73b-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de73b-287">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="de73b-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de73b-288">输入</span><span class="sxs-lookup"><span data-stu-id="de73b-288">INPUTS</span></span>

### <span data-ttu-id="de73b-289">无</span><span class="sxs-lookup"><span data-stu-id="de73b-289">None</span></span>

<span data-ttu-id="de73b-290">不能将对象向下发送到 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-290">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="de73b-291">输出</span><span class="sxs-lookup"><span data-stu-id="de73b-291">OUTPUTS</span></span>

### <span data-ttu-id="de73b-292">None 或 system.string</span><span class="sxs-lookup"><span data-stu-id="de73b-292">None or System.Type</span></span>

<span data-ttu-id="de73b-293">当使用 **PassThru** 参数时，将 `Add-Type` 返回表示新类型的 **system.object** 对象。</span><span class="sxs-lookup"><span data-stu-id="de73b-293">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="de73b-294">否则，此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="de73b-294">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="de73b-295">注释</span><span class="sxs-lookup"><span data-stu-id="de73b-295">NOTES</span></span>

<span data-ttu-id="de73b-296">你添加的类型仅存在当前会话中。</span><span class="sxs-lookup"><span data-stu-id="de73b-296">The types that you add exist only in the current session.</span></span> <span data-ttu-id="de73b-297">若要在所有会话中使用这些类型，请将它们添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="de73b-297">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="de73b-298">有关配置文件的详细信息，请参阅 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="de73b-298">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="de73b-299">类型名称和命名空间在一个会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="de73b-299">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="de73b-300">不能卸载或更改类型。</span><span class="sxs-lookup"><span data-stu-id="de73b-300">You can't unload a type or change it.</span></span> <span data-ttu-id="de73b-301">如果需要更改类型的代码，则必须更改名称或启动新的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="de73b-301">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="de73b-302">否则，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="de73b-302">Otherwise, the command fails.</span></span>

<span data-ttu-id="de73b-303">某些语言（如 IronPython 和 j #）的 **CodeDomProvider** 类不生成输出。</span><span class="sxs-lookup"><span data-stu-id="de73b-303">The **CodeDomProvider** class for some languages, such as IronPython and J#, doesn't generate output.</span></span> <span data-ttu-id="de73b-304">因此，使用这些语言编写的类型不能与一起使用 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="de73b-304">As a result, types written in these languages can't be used with `Add-Type`.</span></span>

<span data-ttu-id="de73b-305">此 cmdlet 基于 Microsoft .NET Framework [CodeDomProvider 类](/dotnet/api/system.codedom.compiler.codedomprovider)。</span><span class="sxs-lookup"><span data-stu-id="de73b-305">This cmdlet is based on the Microsoft .NET Framework [CodeDomProvider Class](/dotnet/api/system.codedom.compiler.codedomprovider).</span></span>

## <span data-ttu-id="de73b-306">相关链接</span><span class="sxs-lookup"><span data-stu-id="de73b-306">RELATED LINKS</span></span>

[<span data-ttu-id="de73b-307">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="de73b-307">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="de73b-308">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="de73b-308">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="de73b-309">Add-Member</span><span class="sxs-lookup"><span data-stu-id="de73b-309">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="de73b-310">New-Object</span><span class="sxs-lookup"><span data-stu-id="de73b-310">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="de73b-311">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="de73b-311">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="de73b-312">平台调用 (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="de73b-312">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="de73b-313">Where-Object</span><span class="sxs-lookup"><span data-stu-id="de73b-313">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
