---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: 3246d33174f39bf52dfa68b2dbe1e7b76a320b61
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198574"
---
# <span data-ttu-id="e0e5f-103">New-Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-103">New-Object</span></span>

## <span data-ttu-id="e0e5f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e0e5f-104">SYNOPSIS</span></span>
<span data-ttu-id="e0e5f-105">创建 Microsoft .NET Framework 或 COM 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-105">Creates an instance of a Microsoft .NET Framework or COM object.</span></span>

## <span data-ttu-id="e0e5f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e0e5f-106">SYNTAX</span></span>

### <span data-ttu-id="e0e5f-107">Net（默认值）</span><span class="sxs-lookup"><span data-stu-id="e0e5f-107">Net (Default)</span></span>

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### <span data-ttu-id="e0e5f-108">Com</span><span class="sxs-lookup"><span data-stu-id="e0e5f-108">Com</span></span>

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## <span data-ttu-id="e0e5f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e0e5f-109">DESCRIPTION</span></span>

<span data-ttu-id="e0e5f-110">`New-Object`Cmdlet 可创建 .NET Framework 或 COM 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-110">The `New-Object` cmdlet creates an instance of a .NET Framework or COM object.</span></span>

<span data-ttu-id="e0e5f-111">可以指定 .NET Framework 类的类型或 COM 对象的 ProgID。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-111">You can specify either the type of a .NET Framework class or a ProgID of a COM object.</span></span> <span data-ttu-id="e0e5f-112">默认情况下，键入 .NET Framework 类的完全限定名后，此 cmdlet 将返回对该类的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-112">By default, you type the fully qualified name of a .NET Framework class and the cmdlet returns a reference to an instance of that class.</span></span> <span data-ttu-id="e0e5f-113">若要创建 COM 对象的实例，请使用 **ComObject** 参数并将对象的 ProgID 指定为其值。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-113">To create an instance of a COM object, use the **ComObject** parameter and specify the ProgID of the object as its value.</span></span>

## <span data-ttu-id="e0e5f-114">示例</span><span class="sxs-lookup"><span data-stu-id="e0e5f-114">EXAMPLES</span></span>

### <span data-ttu-id="e0e5f-115">示例1：创建一个 System.web 对象</span><span class="sxs-lookup"><span data-stu-id="e0e5f-115">Example 1: Create a System.Version object</span></span>

<span data-ttu-id="e0e5f-116">此示例使用 "1.2.3.4" 字符串作为构造函数创建一个 **system.web** 对象。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-116">This example creates a **System.Version** object using the "1.2.3.4" string as the constructor.</span></span>

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### <span data-ttu-id="e0e5f-117">示例2：创建 Internet Explorer COM 对象</span><span class="sxs-lookup"><span data-stu-id="e0e5f-117">Example 2: Create an Internet Explorer COM object</span></span>

<span data-ttu-id="e0e5f-118">此示例创建表示 Internet Explorer 应用程序的 COM 对象的两个实例。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-118">This example creates two instances of the COM object that represents the Internet Explorer application.</span></span> <span data-ttu-id="e0e5f-119">第一个实例使用 **属性** 参数 hash 表调用 **Navigate2** 方法，并将该对象的 **Visible** 属性设置为， `$True` 以使该应用程序可见。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-119">The first instance uses the **Property** parameter hash table to call the **Navigate2** method and set the **Visible** property of the object to `$True` to make the application visible.</span></span>
<span data-ttu-id="e0e5f-120">第二个实例获取的结果与单独的命令相同。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-120">The second instance gets the same results with individual commands.</span></span>

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### <span data-ttu-id="e0e5f-121">示例3：使用 Strict 参数生成非终止错误</span><span class="sxs-lookup"><span data-stu-id="e0e5f-121">Example 3: Use the Strict parameter to generate a non-terminating error</span></span>

<span data-ttu-id="e0e5f-122">此示例演示添加 **Strict** 参数会导致 `New-Object` cmdlet 在 COM 对象使用互操作程序集时生成非终止错误。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-122">This example demonstrates that adding the **Strict** parameter causes the `New-Object` cmdlet to generate a non-terminating error when the COM object uses an interop assembly.</span></span>

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### <span data-ttu-id="e0e5f-123">示例4：创建 COM 对象来管理 Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="e0e5f-123">Example 4: Create a COM object to manage Windows desktop</span></span>

<span data-ttu-id="e0e5f-124">此示例显示如何创建和使用 COM 对象来管理 Windows 桌面。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-124">This example shows how to create and use a COM object to manage your Windows desktop.</span></span>

<span data-ttu-id="e0e5f-125">第一个命令使用 cmdlet 的 **ComObject** 参数 `New-Object` 创建具有 **Shell** 的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-125">The first command uses the **ComObject** parameter of the `New-Object` cmdlet to create a COM object with the **Shell.Application** ProgID.</span></span> <span data-ttu-id="e0e5f-126">它将生成的对象存储在 `$ObjShell` 变量中。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-126">It stores the resulting object in the `$ObjShell` variable.</span></span> <span data-ttu-id="e0e5f-127">第二个命令将 `$ObjShell` 变量传递给 `Get-Member` cmdlet，后者显示 COM 对象的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-127">The second command pipes the `$ObjShell` variable to the `Get-Member` cmdlet, which displays the properties and methods of the COM object.</span></span> <span data-ttu-id="e0e5f-128">在方法中，是 **ToggleDesktop** 方法。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-128">Among the methods is the **ToggleDesktop** method.</span></span> <span data-ttu-id="e0e5f-129">第三个命令调用对象的 **ToggleDesktop** 方法来最小化桌面上打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-129">The third command calls the **ToggleDesktop** method of the object to minimize the open windows on your desktop.</span></span>

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### <span data-ttu-id="e0e5f-130">示例5：将多个自变量传递给构造函数</span><span class="sxs-lookup"><span data-stu-id="e0e5f-130">Example 5: Pass multiple arguments to a constructor</span></span>

<span data-ttu-id="e0e5f-131">此示例演示如何使用采用多个参数的构造函数创建对象。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-131">This example shows how to create an object with a constructor that takes multiple parameters.</span></span> <span data-ttu-id="e0e5f-132">使用 **ArgumentList** 参数时，必须将参数放入数组中。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-132">The parameters must be put in an array when using **ArgumentList** parameter.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

<span data-ttu-id="e0e5f-133">PowerShell 将数组的每个成员绑定到构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-133">PowerShell binds each member of the array to a parameter of the constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="e0e5f-134">此示例使用参数展开以提高可读性。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-134">This example uses parameter splatting for readability.</span></span> <span data-ttu-id="e0e5f-135">有关详细信息，请参阅 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-135">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

### <span data-ttu-id="e0e5f-136">示例6：调用采用数组作为单个参数的构造函数</span><span class="sxs-lookup"><span data-stu-id="e0e5f-136">Example 6: Calling a constructor that takes an array as a single parameter</span></span>

<span data-ttu-id="e0e5f-137">此示例演示如何使用构造函数创建一个对象，该对象采用作为数组或集合的参数。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-137">This example shows how to create an object with a constructor that takes a parameter that is an array or collection.</span></span> <span data-ttu-id="e0e5f-138">数组参数必须放入到另一个数组中。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-138">The array parameter must be put in wrapped inside another array.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

<span data-ttu-id="e0e5f-139">在此示例中，第一次尝试创建对象时失败。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-139">The first attempt to create the object in this example fails.</span></span> <span data-ttu-id="e0e5f-140">PowerShell 尝试将三个成员绑定 `$array` 到构造函数的参数，但构造函数不采用三个参数。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-140">PowerShell attempted to bind the three members of `$array` to parameters of the constructor but the constructor does not take three parameter.</span></span> <span data-ttu-id="e0e5f-141">包装 `$array` 在另一个数组中会阻止 PowerShell 尝试将的三个成员绑定 `$array` 到构造函数的参数。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-141">Wrapping `$array` in another array prevents PowerShell from attempting to bind the three members of `$array` to parameters of the constructor.</span></span>

## <span data-ttu-id="e0e5f-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e0e5f-142">PARAMETERS</span></span>

### <span data-ttu-id="e0e5f-143">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="e0e5f-143">-ArgumentList</span></span>

<span data-ttu-id="e0e5f-144">指定要传递给 .NET Framework 类的构造函数的参数数组。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-144">Specifies an array of arguments to pass to the constructor of the .NET Framework class.</span></span> <span data-ttu-id="e0e5f-145">如果构造函数采用单个参数作为数组，则必须将该参数包装在另一个数组中。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-145">If the constructor takes a single parameter that is an array, you must wrap that parameter inside another array.</span></span> <span data-ttu-id="e0e5f-146">例如：</span><span class="sxs-lookup"><span data-stu-id="e0e5f-146">For example:</span></span>

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

<span data-ttu-id="e0e5f-147">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-147">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="e0e5f-148">**ArgumentList** 的别名是 **Args** 。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-148">The alias for **ArgumentList** is **Args** .</span></span>

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0e5f-149">-ComObject</span><span class="sxs-lookup"><span data-stu-id="e0e5f-149">-ComObject</span></span>

<span data-ttu-id="e0e5f-150">指定 COM 对象的编程标识符 (ProgID)。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-150">Specifies the programmatic identifier (ProgID) of the COM object.</span></span>

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0e5f-151">-Property</span><span class="sxs-lookup"><span data-stu-id="e0e5f-151">-Property</span></span>

<span data-ttu-id="e0e5f-152">设置新对象的属性值并调用其方法。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-152">Sets property values and invokes methods of the new object.</span></span>

<span data-ttu-id="e0e5f-153">输入哈希表，其中键为属性或方法的名称，值为属性值或方法参数。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-153">Enter a hash table in which the keys are the names of properties or methods and the values are property values or method arguments.</span></span> <span data-ttu-id="e0e5f-154">`New-Object` 创建对象并设置每个属性值，并按它们在哈希表中出现的顺序调用每个方法。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-154">`New-Object` creates the object and sets each property value and invokes each method in the order that they appear in the hash table.</span></span>

<span data-ttu-id="e0e5f-155">如果新的对象派生自 **PSObject** 类，并且指定了对象上不存在的属性，则会 `New-Object` 将指定的属性作为 NoteProperty 添加到该对象。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-155">If the new object is derived from the **PSObject** class, and you specify a property that does not exist on the object, `New-Object` adds the specified property to the object as a NoteProperty.</span></span> <span data-ttu-id="e0e5f-156">如果对象不是 **PSObject** ，则该命令将生成一个非终止错误。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-156">If the object is not a **PSObject** , the command generates a non-terminating error.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0e5f-157">-Strict</span><span class="sxs-lookup"><span data-stu-id="e0e5f-157">-Strict</span></span>

<span data-ttu-id="e0e5f-158">指示当你尝试创建的 COM 对象使用互操作程序集时，该 cmdlet 将生成一个非终止错误。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-158">Indicates that the cmdlet generates a non-terminating error when a COM object that you attempt to create uses an interop assembly.</span></span> <span data-ttu-id="e0e5f-159">此功能可将实际的 COM 对象与具有 COM 可调用包装器的 .NET Framework 对象区分开来。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-159">This feature distinguishes actual COM objects from .NET Framework objects with COM-callable wrappers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0e5f-160">-TypeName</span><span class="sxs-lookup"><span data-stu-id="e0e5f-160">-TypeName</span></span>

<span data-ttu-id="e0e5f-161">指定 .NET Framework 类的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-161">Specifies the fully qualified name of the .NET Framework class.</span></span> <span data-ttu-id="e0e5f-162">不能同时指定 **TypeName** 参数和 **ComObject** 参数。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-162">You cannot specify both the **TypeName** parameter and the **ComObject** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0e5f-163">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e0e5f-163">CommonParameters</span></span>

<span data-ttu-id="e0e5f-164">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e0e5f-165">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e0e5f-166">输入</span><span class="sxs-lookup"><span data-stu-id="e0e5f-166">INPUTS</span></span>

### <span data-ttu-id="e0e5f-167">无</span><span class="sxs-lookup"><span data-stu-id="e0e5f-167">None</span></span>

<span data-ttu-id="e0e5f-168">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="e0e5f-169">输出</span><span class="sxs-lookup"><span data-stu-id="e0e5f-169">OUTPUTS</span></span>

### <span data-ttu-id="e0e5f-170">Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-170">Object</span></span>

<span data-ttu-id="e0e5f-171">`New-Object` 返回创建的对象。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-171">`New-Object` returns the object that is created.</span></span>

## <span data-ttu-id="e0e5f-172">注释</span><span class="sxs-lookup"><span data-stu-id="e0e5f-172">NOTES</span></span>

- <span data-ttu-id="e0e5f-173">`New-Object` 提供 VBScript CreateObject 函数最常使用的功能。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-173">`New-Object` provides the most commonly-used functionality of the VBScript CreateObject function.</span></span> <span data-ttu-id="e0e5f-174">`Set objShell = CreateObject("Shell.Application")`可在 PowerShell 中将 VBScript 中的语句转换为 `$objShell = New-Object -COMObject "Shell.Application"` 。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-174">A statement like `Set objShell = CreateObject("Shell.Application")` in VBScript can be translated to `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell.</span></span>
- <span data-ttu-id="e0e5f-175">`New-Object` 通过从命令行和脚本内轻松处理 .NET Framework 的对象，扩展了 Windows 脚本宿主环境中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="e0e5f-175">`New-Object` expands upon the functionality available in the Windows Script Host environment by making it easy to work with .NET Framework objects from the command line and within scripts.</span></span>

## <span data-ttu-id="e0e5f-176">相关链接</span><span class="sxs-lookup"><span data-stu-id="e0e5f-176">RELATED LINKS</span></span>

[<span data-ttu-id="e0e5f-177">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="e0e5f-177">about_Object_Creation</span></span>](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[<span data-ttu-id="e0e5f-178">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-178">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="e0e5f-179">Group-Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-179">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="e0e5f-180">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-180">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="e0e5f-181">Select-Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-181">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="e0e5f-182">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-182">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="e0e5f-183">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="e0e5f-183">Tee-Object</span></span>](Tee-Object.md)
