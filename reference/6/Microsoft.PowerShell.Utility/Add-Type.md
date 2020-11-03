---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: 9a51c97def7cddf45c391ed91ff67ad97fbedf77
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "93199406"
---
# <span data-ttu-id="23dac-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="23dac-103">Add-Type</span></span>

## <span data-ttu-id="23dac-104">摘要</span><span class="sxs-lookup"><span data-stu-id="23dac-104">SYNOPSIS</span></span>
<span data-ttu-id="23dac-105">将 Microsoft .NET Core 类添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="23dac-105">Adds a Microsoft .NET Core class to a PowerShell session.</span></span>

## <span data-ttu-id="23dac-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="23dac-106">SYNTAX</span></span>

### <span data-ttu-id="23dac-107">FromSource (默认值) </span><span class="sxs-lookup"><span data-stu-id="23dac-107">FromSource (Default)</span></span>

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="23dac-108">FromMember</span><span class="sxs-lookup"><span data-stu-id="23dac-108">FromMember</span></span>

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="23dac-109">FromPath</span><span class="sxs-lookup"><span data-stu-id="23dac-109">FromPath</span></span>

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="23dac-110">FromLiteralPath</span><span class="sxs-lookup"><span data-stu-id="23dac-110">FromLiteralPath</span></span>

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="23dac-111">FromAssemblyName</span><span class="sxs-lookup"><span data-stu-id="23dac-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="23dac-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="23dac-112">DESCRIPTION</span></span>

<span data-ttu-id="23dac-113">`Add-Type`Cmdlet 可让你在 PowerShell 会话中定义 Microsoft .NET 核心类。</span><span class="sxs-lookup"><span data-stu-id="23dac-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session.</span></span> <span data-ttu-id="23dac-114">然后，可以使用 cmdlet 实例化对象， `New-Object` 并像使用任何 .Net Core 对象一样使用对象。</span><span class="sxs-lookup"><span data-stu-id="23dac-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object.</span></span> <span data-ttu-id="23dac-115">如果将命令添加 `Add-Type` 到 powershell 配置文件，则该类可用于所有 powershell 会话。</span><span class="sxs-lookup"><span data-stu-id="23dac-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="23dac-116">你可以通过指定现有程序集或源代码文件来指定类型，也可以指定内联源代码或保存在变量中的源代码。</span><span class="sxs-lookup"><span data-stu-id="23dac-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="23dac-117">甚至可以仅指定方法，并 `Add-Type` 定义和生成类。</span><span class="sxs-lookup"><span data-stu-id="23dac-117">You can even specify only a method and `Add-Type` defines and generates the class.</span></span> <span data-ttu-id="23dac-118">在 Windows 上，可以使用此功能在 PowerShell 中将平台调用 (P/Invoke) 调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="23dac-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="23dac-119">如果指定源代码，将 `Add-Type` 编译指定的源代码，并生成包含新 .Net Core 类型的内存中程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Core types.</span></span>

<span data-ttu-id="23dac-120">您可以使用的参数 `Add-Type` 指定替代语言和编译器，c # 是默认值、编译器选项、程序集依赖项、类命名空间、类型名称和生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="23dac-121">示例</span><span class="sxs-lookup"><span data-stu-id="23dac-121">EXAMPLES</span></span>

### <span data-ttu-id="23dac-122">示例1：向会话添加 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="23dac-122">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="23dac-123">此示例通过指定存储在变量中的源代码，将 **BasicTest** 类添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="23dac-123">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="23dac-124">**BasicTest** 类用于添加整数、创建对象和将整数相乘。</span><span class="sxs-lookup"><span data-stu-id="23dac-124">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

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

<span data-ttu-id="23dac-125">`$Source`变量存储类的源代码。</span><span class="sxs-lookup"><span data-stu-id="23dac-125">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="23dac-126">该类型具有一个名为的静态方法 `Add` 和一个名为的非静态方法 `Multiply` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-126">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="23dac-127">`Add-Type`Cmdlet 可将类添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="23dac-127">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="23dac-128">由于它使用内联源代码，因此该命令使用 **TypeDefinition** 参数来指定变量中的代码 `$Source` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-128">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="23dac-129">`Add` **BasicTest** 类的静态方法使用双冒号字符 (`::`) 来指定类的静态成员。</span><span class="sxs-lookup"><span data-stu-id="23dac-129">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="23dac-130">添加整数并显示总和。</span><span class="sxs-lookup"><span data-stu-id="23dac-130">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="23dac-131">`New-Object`Cmdlet 实例化 **BasicTest** 类的实例。</span><span class="sxs-lookup"><span data-stu-id="23dac-131">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="23dac-132">它将新对象保存在 `$BasicTestObject` 变量中。</span><span class="sxs-lookup"><span data-stu-id="23dac-132">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="23dac-133">`$BasicTestObject` 使用 `Multiply` 方法。</span><span class="sxs-lookup"><span data-stu-id="23dac-133">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="23dac-134">整数相乘并显示产品。</span><span class="sxs-lookup"><span data-stu-id="23dac-134">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="23dac-135">示例2：检查添加的类型</span><span class="sxs-lookup"><span data-stu-id="23dac-135">Example 2: Examine an added type</span></span>

<span data-ttu-id="23dac-136">此示例使用 `Get-Member` cmdlet 检查在 `Add-Type` `New-Object` **示例 1** 中创建的和 cmdlet 的对象。</span><span class="sxs-lookup"><span data-stu-id="23dac-136">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1** .</span></span>

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

<span data-ttu-id="23dac-137">`Get-Member`Cmdlet 可获取添加到会话中的 **BasicTest** 类的类型和成员 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-137">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="23dac-138">该 `Get-Member` 命令显示它是一个派生自 **system.object** 类的 **RuntimeType** 对象。</span><span class="sxs-lookup"><span data-stu-id="23dac-138">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="23dac-139">`Get-Member`**静态** 参数获取 **BasicTest** 类的静态属性和方法。</span><span class="sxs-lookup"><span data-stu-id="23dac-139">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="23dac-140">输出显示此 `Add` 方法已包括在内。</span><span class="sxs-lookup"><span data-stu-id="23dac-140">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="23dac-141">`Get-Member`Cmdlet 将获取存储在变量中的对象的成员 `$BasicTestObject` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-141">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="23dac-142">`$BasicTestObject` 是通过对 `New-Object` **BasicTest** 类使用 cmdlet 创建的。</span><span class="sxs-lookup"><span data-stu-id="23dac-142">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="23dac-143">输出显示变量的值 `$BasicTestObject` 是 **BasicTest** 类的一个实例，并且它包括一个名为的成员 `Multiply` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-143">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="23dac-144">示例3：从程序集添加类型</span><span class="sxs-lookup"><span data-stu-id="23dac-144">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="23dac-145">此示例将程序集的类添加 `NJsonSchema.dll` 到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="23dac-145">This example adds the classes from the `NJsonSchema.dll` assembly to the current session.</span></span>

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

<span data-ttu-id="23dac-146">`Set-Location` 使用 **Path** 参数指定 `$PSHOME` 变量。</span><span class="sxs-lookup"><span data-stu-id="23dac-146">`Set-Location` uses the **Path** parameter to specify the `$PSHOME` variable.</span></span> <span data-ttu-id="23dac-147">变量引用 DLL 文件所在的 PowerShell 安装目录。</span><span class="sxs-lookup"><span data-stu-id="23dac-147">The variable references the PowerShell installation directory where the DLL file is located.</span></span>

<span data-ttu-id="23dac-148">`$AccType`变量存储使用 cmdlet 创建的对象 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-148">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="23dac-149">`Add-Type` 使用 **AssemblyName** 参数指定程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="23dac-149">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="23dac-150">星号 (`*`) 通配符允许您获取正确的程序集，即使您不确定名称或其拼写时也是如此。</span><span class="sxs-lookup"><span data-stu-id="23dac-150">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="23dac-151">**PassThru** 参数生成对象，这些对象表示添加到会话中的类。</span><span class="sxs-lookup"><span data-stu-id="23dac-151">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="23dac-152">示例4：调用本机 Windows Api</span><span class="sxs-lookup"><span data-stu-id="23dac-152">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="23dac-153">此示例演示如何在 PowerShell 中调用本机 Windows Api。</span><span class="sxs-lookup"><span data-stu-id="23dac-153">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="23dac-154">`Add-Type` 使用平台调用 (P/Invoke) 机制从 PowerShell 调用中的函数 `User32.dll` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-154">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="23dac-155">此示例仅适用于运行 Windows 操作系统的计算机。</span><span class="sxs-lookup"><span data-stu-id="23dac-155">This example only works on computers running the Windows operating system.</span></span>

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

<span data-ttu-id="23dac-156">`$Signature`变量存储函数的 c # 签名 `ShowWindowAsync` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-156">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="23dac-157">为了确保生成的方法在 PowerShell 会话中可见， `public` 关键字已添加到标准签名中。</span><span class="sxs-lookup"><span data-stu-id="23dac-157">To ensure that the resulting method is visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="23dac-158">有关详细信息，请参阅 [ShowWindowAsync 函数](/windows/win32/api/winuser/nf-winuser-showwindowasync)。</span><span class="sxs-lookup"><span data-stu-id="23dac-158">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="23dac-159">`$ShowWindowAsync`变量存储通过 `Add-Type` **PassThru** 参数创建的对象。</span><span class="sxs-lookup"><span data-stu-id="23dac-159">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="23dac-160">`Add-Type`Cmdlet 将 `ShowWindowAsync` 函数作为静态方法添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="23dac-160">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="23dac-161">该命令使用 **MemberDefinition** 参数来指定保存在变量中的方法定义 `$Signature` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-161">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="23dac-162">该命令使用 **Name** 和 **Namespace** 参数来指定类的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="23dac-162">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="23dac-163">**PassThru** 参数生成一个表示类型的对象。</span><span class="sxs-lookup"><span data-stu-id="23dac-163">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="23dac-164">`ShowWindowAsync`在命令中使用新的静态方法来最小化和还原 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="23dac-164">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="23dac-165">此方法采用两个参数：窗口句柄和指定如何显示窗口的整数。</span><span class="sxs-lookup"><span data-stu-id="23dac-165">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="23dac-166">若要最大程度地减少 PowerShell 控制台，请 `ShowWindowAsync` 将 `Get-Process` cmdlet 与自动变量一起使用， `$PID` 以获取托管当前 PowerShell 会话的进程。</span><span class="sxs-lookup"><span data-stu-id="23dac-166">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="23dac-167">然后，它使用当前进程的 **MainWindowHandle** 属性和值 `2` （表示 `SW_MINIMIZE` 值）。</span><span class="sxs-lookup"><span data-stu-id="23dac-167">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="23dac-168">若要还原窗口，请将的 `ShowWindowAsync` 值 `4` 用于窗口位置，它表示 `SW_RESTORE` 值。</span><span class="sxs-lookup"><span data-stu-id="23dac-168">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="23dac-169">若要最大化窗口，请使用 `3` 表示的值 `SW_MAXIMIZE` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-169">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

## <span data-ttu-id="23dac-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="23dac-170">PARAMETERS</span></span>

### <span data-ttu-id="23dac-171">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="23dac-171">-AssemblyName</span></span>

<span data-ttu-id="23dac-172">指定包含类型的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="23dac-172">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="23dac-173">`Add-Type` 采用指定程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-173">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="23dac-174">基于程序集名称创建类型时，此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="23dac-174">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="23dac-175">输入程序集的完整名称或简单名称（也称为 "部分名称"）。</span><span class="sxs-lookup"><span data-stu-id="23dac-175">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="23dac-176">在程序集名称中允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="23dac-176">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="23dac-177">如果输入简单名称或部分名称，则将 `Add-Type` 其解析为完整名称，然后使用完整名称加载程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-177">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="23dac-178">此参数不接受路径或文件名。</span><span class="sxs-lookup"><span data-stu-id="23dac-178">This parameter doesn't accept a path or a filename.</span></span> <span data-ttu-id="23dac-179">若要输入程序集动态链接库的路径 (DLL) 文件，请使用 **path** 参数。</span><span class="sxs-lookup"><span data-stu-id="23dac-179">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

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

### <span data-ttu-id="23dac-180">-CompilerOptions</span><span class="sxs-lookup"><span data-stu-id="23dac-180">-CompilerOptions</span></span>

<span data-ttu-id="23dac-181">指定用于源代码编译器的选项。</span><span class="sxs-lookup"><span data-stu-id="23dac-181">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="23dac-182">这些选项无需修改即可发送到编译器。</span><span class="sxs-lookup"><span data-stu-id="23dac-182">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="23dac-183">此参数允许指示编译器生成可执行文件、嵌入资源或设置命令行选项，如 `/unsafe` 选项。</span><span class="sxs-lookup"><span data-stu-id="23dac-183">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span>

<span data-ttu-id="23dac-184">不能在同一命令中使用 **CompilerOptions** 和 **ReferencedAssemblies** 参数。</span><span class="sxs-lookup"><span data-stu-id="23dac-184">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dac-185">-IgnoreWarnings</span><span class="sxs-lookup"><span data-stu-id="23dac-185">-IgnoreWarnings</span></span>

<span data-ttu-id="23dac-186">忽略编译器警告。</span><span class="sxs-lookup"><span data-stu-id="23dac-186">Ignores compiler warnings.</span></span> <span data-ttu-id="23dac-187">使用此参数可防止将 `Add-Type` 编译器警告作为错误处理。</span><span class="sxs-lookup"><span data-stu-id="23dac-187">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dac-188">-Language</span><span class="sxs-lookup"><span data-stu-id="23dac-188">-Language</span></span>

<span data-ttu-id="23dac-189">指定在源代码中使用的语言。</span><span class="sxs-lookup"><span data-stu-id="23dac-189">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="23dac-190">此参数可接受的值为 **CSharp** 。</span><span class="sxs-lookup"><span data-stu-id="23dac-190">The acceptable value for this parameter is **CSharp** .</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dac-191">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="23dac-191">-LiteralPath</span></span>

<span data-ttu-id="23dac-192">指定包含类型的源代码文件或程序集 DLL 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="23dac-192">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="23dac-193">与 **Path** 不同， **LiteralPath** 参数的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="23dac-193">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="23dac-194">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="23dac-194">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="23dac-195">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="23dac-195">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="23dac-196">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="23dac-196">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="23dac-197">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="23dac-197">-MemberDefinition</span></span>

<span data-ttu-id="23dac-198">指定类的新属性或方法。</span><span class="sxs-lookup"><span data-stu-id="23dac-198">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="23dac-199">`Add-Type` 生成支持属性或方法所需的模板代码。</span><span class="sxs-lookup"><span data-stu-id="23dac-199">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="23dac-200">在 Windows 上，可以使用此功能在 PowerShell 中将平台调用 (P/Invoke) 调用非托管函数。</span><span class="sxs-lookup"><span data-stu-id="23dac-200">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

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

### <span data-ttu-id="23dac-201">-Name</span><span class="sxs-lookup"><span data-stu-id="23dac-201">-Name</span></span>

<span data-ttu-id="23dac-202">指定要创建的类的名称。</span><span class="sxs-lookup"><span data-stu-id="23dac-202">Specifies the name of the class to create.</span></span> <span data-ttu-id="23dac-203">当从成员定义生成类型时，此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="23dac-203">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="23dac-204">类型名称和命名空间在一个会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="23dac-204">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="23dac-205">不能卸载或更改类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-205">You can't unload a type or change it.</span></span>
<span data-ttu-id="23dac-206">若要更改类型的代码，必须更改名称或启动新的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="23dac-206">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="23dac-207">否则，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="23dac-207">Otherwise, the command fails.</span></span>

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

### <span data-ttu-id="23dac-208">-Namespace</span><span class="sxs-lookup"><span data-stu-id="23dac-208">-Namespace</span></span>

<span data-ttu-id="23dac-209">指定类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="23dac-209">Specifies a namespace for the type.</span></span>

<span data-ttu-id="23dac-210">如果此参数不包括在命令中，则会在 **将. microsoft.powershell.commands.newwebserviceproxy.autogeneratedtypes 和** 命名空间中创建该类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-210">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="23dac-211">如果参数包含在包含空字符串值或值的命令中 `$Null` ，则将在全局命名空间中生成类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-211">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

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

### <span data-ttu-id="23dac-212">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="23dac-212">-OutputAssembly</span></span>

<span data-ttu-id="23dac-213">在该位置中为具有指定名称的程序集生成 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="23dac-213">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="23dac-214">输入可选的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="23dac-214">Enter an optional path and filename.</span></span> <span data-ttu-id="23dac-215">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="23dac-215">Wildcard characters are permitted.</span></span> <span data-ttu-id="23dac-216">默认情况下， `Add-Type` 仅在内存中生成程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-216">By default, `Add-Type` generates the assembly only in memory.</span></span>

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

### <span data-ttu-id="23dac-217">-OutputType</span><span class="sxs-lookup"><span data-stu-id="23dac-217">-OutputType</span></span>

<span data-ttu-id="23dac-218">指定输出程序集的输出类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-218">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="23dac-219">默认情况下，不指定输出类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-219">By default, no output type is specified.</span></span> <span data-ttu-id="23dac-220">仅当命令中指定了输出程序集时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="23dac-220">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="23dac-221">有关这些值的详细信息，请参阅 [OutputAssemblyType 枚举](/dotnet/api/microsoft.powershell.commands.outputassemblytype)。</span><span class="sxs-lookup"><span data-stu-id="23dac-221">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="23dac-222">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="23dac-222">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="23dac-223">控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="23dac-223">ConsoleApplication</span></span>
- <span data-ttu-id="23dac-224">库</span><span class="sxs-lookup"><span data-stu-id="23dac-224">Library</span></span>
- <span data-ttu-id="23dac-225">Windowsapplication.zip</span><span class="sxs-lookup"><span data-stu-id="23dac-225">WindowsApplication</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23dac-226">`ConsoleApplication`和 `WindowsApplication` 值不生成工作输出，因此不应使用。</span><span class="sxs-lookup"><span data-stu-id="23dac-226">The `ConsoleApplication` and `WindowsApplication` values don't produce working output and should not be used.</span></span>

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

### <span data-ttu-id="23dac-227">-PassThru</span><span class="sxs-lookup"><span data-stu-id="23dac-227">-PassThru</span></span>

<span data-ttu-id="23dac-228">返回表示已添加的类型的 **System.Runtime** 对象。</span><span class="sxs-lookup"><span data-stu-id="23dac-228">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="23dac-229">默认情况下，此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="23dac-229">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="23dac-230">-Path</span><span class="sxs-lookup"><span data-stu-id="23dac-230">-Path</span></span>

<span data-ttu-id="23dac-231">指定包含类型的源代码文件或程序集 DLL 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="23dac-231">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="23dac-232">如果提交源代码文件，则会在 `Add-Type` 文件中编译代码，并创建类型的内存中程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-232">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="23dac-233">**Path** 的值中指定的文件扩展名确定使用的编译器 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-233">The file extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="23dac-234">如果提交程序集文件，则 `Add-Type` 从程序集中获取类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-234">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="23dac-235">若要指定内存中程序集或全局程序集缓存，请使用 **AssemblyName** 参数。</span><span class="sxs-lookup"><span data-stu-id="23dac-235">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="23dac-236">-ReferencedAssemblies</span><span class="sxs-lookup"><span data-stu-id="23dac-236">-ReferencedAssemblies</span></span>

<span data-ttu-id="23dac-237">指定类型所依赖的程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-237">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="23dac-238">默认情况下， `Add-Type` 引用 `System.dll` 和 `System.Management.Automation.dll` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-238">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="23dac-239">除了引用默认程序集之外，还将引用你通过使用此参数指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-239">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="23dac-240">从 PowerShell 6 开始， **ReferencedAssemblies** 不包括默认的 .net 程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-240">Beginning in PowerShell 6, **ReferencedAssemblies** doesn't include the default .NET assemblies.</span></span> <span data-ttu-id="23dac-241">必须在传递给此参数的值中包含对它们的特定引用。</span><span class="sxs-lookup"><span data-stu-id="23dac-241">You must include a specific reference to them in the value passed to this parameter.</span></span>

<span data-ttu-id="23dac-242">不能在同一命令中使用 **CompilerOptions** 和 **ReferencedAssemblies** 参数。</span><span class="sxs-lookup"><span data-stu-id="23dac-242">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="23dac-243">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="23dac-243">-TypeDefinition</span></span>

<span data-ttu-id="23dac-244">指定包含类型定义的源代码。</span><span class="sxs-lookup"><span data-stu-id="23dac-244">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="23dac-245">以字符串或 here-string 的形式输入源代码或输入一个包含源代码的变量。</span><span class="sxs-lookup"><span data-stu-id="23dac-245">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="23dac-246">有关字符串的详细信息，请参阅 [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="23dac-246">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="23dac-247">在类型定义中包括命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="23dac-247">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="23dac-248">如果省略命名空间声明，则你的类型可能会与其他类型或其他类型的快捷方式同名，从而导致意外覆盖。</span><span class="sxs-lookup"><span data-stu-id="23dac-248">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="23dac-249">例如，如果定义了一个名为 **exception** 的类型，则使用 **exception** 作为 system.exception 的快捷 **方式的脚本将失败** 。</span><span class="sxs-lookup"><span data-stu-id="23dac-249">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

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

### <span data-ttu-id="23dac-250">-UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="23dac-250">-UsingNamespace</span></span>

<span data-ttu-id="23dac-251">指定类所需的其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="23dac-251">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="23dac-252">这非常类似于 c # 关键字 `Using` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-252">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="23dac-253">默认情况下， `Add-Type` 引用 **系统** 命名空间。</span><span class="sxs-lookup"><span data-stu-id="23dac-253">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="23dac-254">如果使用 **MemberDefinition** 参数，则 `Add-Type` 默认情况下也会引用 **InteropServices** 命名空间。</span><span class="sxs-lookup"><span data-stu-id="23dac-254">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="23dac-255">除了引用默认命名空间之外，还将引用你通过使用 **UsingNamespace** 参数添加的命名空间。</span><span class="sxs-lookup"><span data-stu-id="23dac-255">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

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

### <span data-ttu-id="23dac-256">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="23dac-256">CommonParameters</span></span>

<span data-ttu-id="23dac-257">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="23dac-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="23dac-258">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="23dac-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="23dac-259">输入</span><span class="sxs-lookup"><span data-stu-id="23dac-259">INPUTS</span></span>

### <span data-ttu-id="23dac-260">无</span><span class="sxs-lookup"><span data-stu-id="23dac-260">None</span></span>

<span data-ttu-id="23dac-261">不能将对象向下发送到 `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-261">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="23dac-262">输出</span><span class="sxs-lookup"><span data-stu-id="23dac-262">OUTPUTS</span></span>

### <span data-ttu-id="23dac-263">None 或 system.string</span><span class="sxs-lookup"><span data-stu-id="23dac-263">None or System.Type</span></span>

<span data-ttu-id="23dac-264">当使用 **PassThru** 参数时，将 `Add-Type` 返回表示新类型的 **system.object** 对象。</span><span class="sxs-lookup"><span data-stu-id="23dac-264">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="23dac-265">否则，此 cmdlet 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="23dac-265">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="23dac-266">注释</span><span class="sxs-lookup"><span data-stu-id="23dac-266">NOTES</span></span>

<span data-ttu-id="23dac-267">你添加的类型仅存在当前会话中。</span><span class="sxs-lookup"><span data-stu-id="23dac-267">The types that you add exist only in the current session.</span></span> <span data-ttu-id="23dac-268">若要在所有会话中使用这些类型，请将它们添加到 PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="23dac-268">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="23dac-269">有关配置文件的详细信息，请参阅 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="23dac-269">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="23dac-270">类型名称和命名空间在一个会话中必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="23dac-270">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="23dac-271">不能卸载或更改类型。</span><span class="sxs-lookup"><span data-stu-id="23dac-271">You can't unload a type or change it.</span></span> <span data-ttu-id="23dac-272">如果需要更改类型的代码，则必须更改名称或启动新的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="23dac-272">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="23dac-273">否则，该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="23dac-273">Otherwise, the command fails.</span></span>

<span data-ttu-id="23dac-274">在 Windows PowerShell 中 (版本5.1 及更低版本) ，你需要 `Add-Type` 对尚未加载的任何内容使用。</span><span class="sxs-lookup"><span data-stu-id="23dac-274">In Windows PowerShell (version 5.1 and below), you need to use `Add-Type` for anything that isn't already loaded.</span></span> <span data-ttu-id="23dac-275">最常见的情况是，这适用于在全局程序集缓存 (GAC) 中找到的程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-275">Most commonly, this applies to assemblies found in the Global Assembly Cache (GAC).</span></span>
<span data-ttu-id="23dac-276">在 PowerShell 6 及更高版本中，没有 GAC，因此 PowerShell 在中安装其自己的程序集 `$PSHome` 。</span><span class="sxs-lookup"><span data-stu-id="23dac-276">In PowerShell 6 and higher, there is no GAC, so PowerShell installs its own assemblies in `$PSHome`.</span></span>
<span data-ttu-id="23dac-277">这些程序集是在请求时自动加载的，因此无需使用 `Add-Type` 来加载这些程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-277">These assemblies are automatically loaded on request, so there's no need to use `Add-Type` to load them.</span></span> <span data-ttu-id="23dac-278">但是， `Add-Type` 仍允许使用来允许脚本与任何 PowerShell 版本隐式兼容。</span><span class="sxs-lookup"><span data-stu-id="23dac-278">However, using `Add-Type` is still permitted to allow scripts to be implicitly compatible with any version of PowerShell.</span></span>

<span data-ttu-id="23dac-279">GAC 中的程序集可以按类型名称而不是按路径进行加载。</span><span class="sxs-lookup"><span data-stu-id="23dac-279">Assemblies in the GAC can be loaded by type name, rather than by path.</span></span> <span data-ttu-id="23dac-280">从任意路径加载程序集需要 `Add-Type` ，因为不能自动加载这些程序集。</span><span class="sxs-lookup"><span data-stu-id="23dac-280">Loading assemblies from an arbitrary path requires `Add-Type`, since those assemblies cannot not be loaded automatically.</span></span>

## <span data-ttu-id="23dac-281">相关链接</span><span class="sxs-lookup"><span data-stu-id="23dac-281">RELATED LINKS</span></span>

[<span data-ttu-id="23dac-282">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="23dac-282">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="23dac-283">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="23dac-283">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="23dac-284">Add-Member</span><span class="sxs-lookup"><span data-stu-id="23dac-284">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="23dac-285">New-Object</span><span class="sxs-lookup"><span data-stu-id="23dac-285">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="23dac-286">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="23dac-286">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="23dac-287">平台调用 (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="23dac-287">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="23dac-288">Where-Object</span><span class="sxs-lookup"><span data-stu-id="23dac-288">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
