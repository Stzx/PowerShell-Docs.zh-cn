---
description: 说明如何在 PowerShell 中创建对象。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_object_creation?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Object_Creation
ms.openlocfilehash: 57cc45640879aa80142c27c27a7810dcc5f31a9c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200456"
---
# <a name="about-object-creation"></a><span data-ttu-id="18ec6-104">关于对象创建</span><span class="sxs-lookup"><span data-stu-id="18ec6-104">About Object Creation</span></span>

## <a name="short-description"></a><span data-ttu-id="18ec6-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="18ec6-105">Short description</span></span>

<span data-ttu-id="18ec6-106">说明如何在 PowerShell 中创建对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-106">Explains how to create objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="18ec6-107">长说明</span><span class="sxs-lookup"><span data-stu-id="18ec6-107">Long description</span></span>

<span data-ttu-id="18ec6-108">可以在 PowerShell 中创建对象，并使用在命令和脚本中创建的对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-108">You can create objects in PowerShell and use the objects that you create in commands and scripts.</span></span>

<span data-ttu-id="18ec6-109">有多种方法可以创建对象，此列表并不是明确的：</span><span class="sxs-lookup"><span data-stu-id="18ec6-109">There are many ways to create objects, this list is not definitive:</span></span>

- <span data-ttu-id="18ec6-110">[New-object](xref:Microsoft.PowerShell.Utility.New-Object)：创建 .NET Framework 对象或 COM 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="18ec6-110">[New-Object](xref:Microsoft.PowerShell.Utility.New-Object): Creates an instance of a .NET Framework object or COM object.</span></span>
- <span data-ttu-id="18ec6-111">[导入-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv) /
  [Convertfrom-csv](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv)：从定义为逗号分隔值的项 ( **PSCustomObject** ) 创建自定义对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-111">[Import-Csv](xref:Microsoft.PowerShell.Utility.Import-Csv)/
  [ConvertFrom-CSV](xref:Microsoft.PowerShell.Utility.ConvertFrom-Csv): Creates custom objects ( **PSCustomObject** ) from the items defined as comma separated values.</span></span>
- <span data-ttu-id="18ec6-112">[Convertfrom-csv-json](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json)：创建 (Json) JavaScript 对象表示法中定义的自定义对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-112">[ConvertFrom-Json](xref:Microsoft.PowerShell.Utility.ConvertFrom-Json): Creates custom objects defined in JavaScript Object Notation (JSON).</span></span>
- <span data-ttu-id="18ec6-113">[Convertfrom-csv-convertfrom-stringdata](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)：创建定义为键值对的自定义对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-113">[ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData): Creates custom objects defined as key value pairs.</span></span>
- <span data-ttu-id="18ec6-114">[添加类型](xref:Microsoft.PowerShell.Utility.Add-Type)：允许你在 PowerShell 会话中定义可使用实例化的类 `New-Object` 。</span><span class="sxs-lookup"><span data-stu-id="18ec6-114">[Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type): Allows you to define a class in your PowerShell session that you can instantiate with `New-Object`.</span></span>
- <span data-ttu-id="18ec6-115">[New-Module](xref:Microsoft.PowerShell.Core.New-Module)： **AsCustomObject** 参数创建使用脚本块定义的自定义对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-115">[New-Module](xref:Microsoft.PowerShell.Core.New-Module): The **AsCustomObject** parameter creates a custom object you define using script block.</span></span>
- <span data-ttu-id="18ec6-116">[添加成员](xref:Microsoft.PowerShell.Utility.Add-Member)：向现有对象添加属性。</span><span class="sxs-lookup"><span data-stu-id="18ec6-116">[Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member): Adds properties to existing objects.</span></span> <span data-ttu-id="18ec6-117">您可以使用 `Add-Member` 创建一个简单类型的自定义对象，例如 `[System.Int32]` 。</span><span class="sxs-lookup"><span data-stu-id="18ec6-117">You can use `Add-Member` to create a custom object out of a simple type, like `[System.Int32]`.</span></span>
- <span data-ttu-id="18ec6-118">[选择-对象](xref:Microsoft.PowerShell.Utility.Select-Object)：选择对象的属性。</span><span class="sxs-lookup"><span data-stu-id="18ec6-118">[Select-Object](xref:Microsoft.PowerShell.Utility.Select-Object): Selects properties on an object.</span></span> <span data-ttu-id="18ec6-119">您可以使用 `Select-Object` 来对已实例化的对象创建自定义和计算属性。</span><span class="sxs-lookup"><span data-stu-id="18ec6-119">You can use `Select-Object` to create custom and calculated properties on an already instantiated object.</span></span>

<span data-ttu-id="18ec6-120">本文介绍了以下附加方法：</span><span class="sxs-lookup"><span data-stu-id="18ec6-120">The following additional methods are covered in this article:</span></span>

- <span data-ttu-id="18ec6-121">通过使用静态方法调用类型的构造函数 `new()`</span><span class="sxs-lookup"><span data-stu-id="18ec6-121">By calling a type's constructor using a static `new()` method</span></span>
- <span data-ttu-id="18ec6-122">通过 typecasting 属性名称和属性值的哈希表</span><span class="sxs-lookup"><span data-stu-id="18ec6-122">By typecasting hash tables of property names and property values</span></span>

## <a name="static-new-method"></a><span data-ttu-id="18ec6-123">静态 new ( # A1 方法</span><span class="sxs-lookup"><span data-stu-id="18ec6-123">Static new() method</span></span>

<span data-ttu-id="18ec6-124">所有 .NET 类型都有一 `new()` 种方法，使您可以更轻松地构造实例。</span><span class="sxs-lookup"><span data-stu-id="18ec6-124">All .NET types have a `new()` method that allows you to construct instances more easily.</span></span> <span data-ttu-id="18ec6-125">你还可以查看给定类型的所有可用构造函数。</span><span class="sxs-lookup"><span data-stu-id="18ec6-125">You can also see all the available constructors for a given type.</span></span>

<span data-ttu-id="18ec6-126">若要查看类型的构造函数，请在 `new` 类型名称后指定方法名称，然后按 `<ENTER>` 。</span><span class="sxs-lookup"><span data-stu-id="18ec6-126">To see the constructors for a type, specify the `new` method name after the type name and press `<ENTER>`.</span></span>

```powershell
[System.Uri]::new
```

```Output
OverloadDefinitions
-------------------
uri new(string uriString)
uri new(string uriString, bool dontEscape)
uri new(uri baseUri, string relativeUri, bool dontEscape)
uri new(string uriString, System.UriKind uriKind)
uri new(uri baseUri, string relativeUri)
uri new(uri baseUri, uri relativeUri)
```

<span data-ttu-id="18ec6-127">现在，可以通过指定适当的构造函数来创建一个 **system.web。**</span><span class="sxs-lookup"><span data-stu-id="18ec6-127">Now, you can create a **System.Uri** by specifying the appropriate constructor.</span></span>

```powershell
[System.Uri]::new("https://www.bing.com")
```

```Output
AbsolutePath   : /
AbsoluteUri    : https://www.bing.com/
LocalPath      : /
Authority      : www.bing.com
...
```

<span data-ttu-id="18ec6-128">您可以使用以下示例来确定当前加载哪些 .NET 类型以供您实例化。</span><span class="sxs-lookup"><span data-stu-id="18ec6-128">You can use the following sample to determine what .NET types are currently loaded for you to instantiate.</span></span>

```powershell
[AppDomain]::CurrentDomain.GetAssemblies() |
  ForEach-Object {
    $_.GetExportedTypes() |
      ForEach-Object { $_.FullName }
  }
```

<span data-ttu-id="18ec6-129">使用方法创建的对象 `new()` 可能与 PowerShell cmdlet 创建的相同类型的对象具有不同的属性。</span><span class="sxs-lookup"><span data-stu-id="18ec6-129">Objects created using the `new()` method may not have the same properties as objects of the same type that are created by PowerShell cmdlets.</span></span> <span data-ttu-id="18ec6-130">PowerShell cmdlet、提供程序和扩展类型系统可以将额外的属性添加到实例中。</span><span class="sxs-lookup"><span data-stu-id="18ec6-130">PowerShell cmdlets, providers, and Extended Type System can add extra properties to the instance.</span></span>

<span data-ttu-id="18ec6-131">例如，PowerShell 中的 FileSystem 提供程序将六个 **NoteProperty** 值添加到返回的 **DirectoryInfo** 对象 `Get-Item` 。</span><span class="sxs-lookup"><span data-stu-id="18ec6-131">For example, the FileSystem provider in PowerShell adds six **NoteProperty** values to the **DirectoryInfo** object returned by `Get-Item`.</span></span>

```powershell
$PSDirInfo = Get-Item /
$PSDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    6 NoteProperty
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="18ec6-132">直接创建 **DirectoryInfo** 对象时，该对象没有这6个 **NoteProperty** 值。</span><span class="sxs-lookup"><span data-stu-id="18ec6-132">When you create a **DirectoryInfo** object directly, it does not have those six **NoteProperty** values.</span></span>

```powershell
$NewDirInfo = [System.IO.DirectoryInfo]::new('/')
$NewDirInfo | Get-Member | Group-Object MemberType | Select-Object Count, Name
```

```Output
Count Name
----- ----
    4 CodeProperty
   13 Property
    1 ScriptProperty
   18 Method
```

<span data-ttu-id="18ec6-133">有关扩展类型系统的详细信息，请参阅 [about_Types.ps1xml](about_Types.ps1xml.md)。</span><span class="sxs-lookup"><span data-stu-id="18ec6-133">For more information about the Extended Type System, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

<span data-ttu-id="18ec6-134">此功能已添加到 PowerShell 5。0</span><span class="sxs-lookup"><span data-stu-id="18ec6-134">This feature was added in PowerShell 5.0</span></span>

## <a name="create-objects-from-hash-tables"></a><span data-ttu-id="18ec6-135">从哈希表创建对象</span><span class="sxs-lookup"><span data-stu-id="18ec6-135">Create objects from hash tables</span></span>

<span data-ttu-id="18ec6-136">可以从属性和属性值的哈希表创建对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-136">You can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="18ec6-137">语法如下：</span><span class="sxs-lookup"><span data-stu-id="18ec6-137">The syntax is as follows:</span></span>

```
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="18ec6-138">此方法仅适用于具有无参数构造函数的类。</span><span class="sxs-lookup"><span data-stu-id="18ec6-138">This method works only for classes that have a parameterless constructor.</span></span> <span data-ttu-id="18ec6-139">对象属性必须是公共且可设置的。</span><span class="sxs-lookup"><span data-stu-id="18ec6-139">The object properties must be public and settable.</span></span>

<span data-ttu-id="18ec6-140">此功能是在 PowerShell 版本3.0 中添加的。</span><span class="sxs-lookup"><span data-stu-id="18ec6-140">This feature was added in PowerShell version 3.0</span></span>

## <a name="create-custom-objects-from-hash-tables"></a><span data-ttu-id="18ec6-141">从哈希表创建自定义对象</span><span class="sxs-lookup"><span data-stu-id="18ec6-141">Create custom objects from hash tables</span></span>

<span data-ttu-id="18ec6-142">自定义对象非常有用，使用哈希表方法可以轻松地创建自定义对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-142">Custom objects are very useful and are easy to create using the hash table method.</span></span> <span data-ttu-id="18ec6-143">**PSCustomObject** 类专门为此目的而设计。</span><span class="sxs-lookup"><span data-stu-id="18ec6-143">The **PSCustomObject** class is designed specifically for this purpose.</span></span>

<span data-ttu-id="18ec6-144">自定义对象是一种从函数或脚本返回自定义输出的极好方法。</span><span class="sxs-lookup"><span data-stu-id="18ec6-144">Custom objects are an excellent way to return customized output from a function or script.</span></span> <span data-ttu-id="18ec6-145">这更适用于返回无法重新格式化的格式化输出和其他命令的管道。</span><span class="sxs-lookup"><span data-stu-id="18ec6-145">This is more useful than returning formatted output that cannot be reformatted or piped to other commands.</span></span>

<span data-ttu-id="18ec6-146">中的命令 `Test-Object function` 设置一些变量值，然后使用这些值创建自定义对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-146">The commands in the `Test-Object function` set some variable values and then use those values to create a custom object.</span></span> <span data-ttu-id="18ec6-147">可以在 cmdlet 帮助主题的 "示例" 部分中查看使用此对象 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="18ec6-147">You can see this object in use in the example section of the `Update-Help` cmdlet help topic.</span></span>

```powershell
function Test-Object {
  $ModuleName = "PSScheduledJob"
  $HelpCulture = "en-us"
  $HelpVersion = "3.1.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
  $ModuleName = "PSWorkflow"
  $HelpCulture = "en-us"
  $HelpVersion = "3.0.0.0"
  [PSCustomObject]@{
    "ModuleName"=$ModuleName
    "UICulture"=$HelpCulture
    "Version"=$HelpVersion
  }
}
Test-Object
```

<span data-ttu-id="18ec6-148">此函数的输出在默认情况下是格式化为表的自定义对象集合。</span><span class="sxs-lookup"><span data-stu-id="18ec6-148">The output of this function is a collection of custom objects formatted as a table by default.</span></span>

```Output
ModuleName        UICulture      Version
---------         ---------      -------
PSScheduledJob    en-us          3.1.0.0
PSWorkflow        en-us          3.0.0.0
```

<span data-ttu-id="18ec6-149">用户可以如同标准对象一样管理自定义对象的属性。</span><span class="sxs-lookup"><span data-stu-id="18ec6-149">Users can manage the properties of the custom objects just as they do with standard objects.</span></span>

```powershell
(Test-Object).ModuleName
```

```Output
 PSScheduledJob
 PSWorkflow
```

## <a name="create-non-custom-objects-from-hash-tables"></a><span data-ttu-id="18ec6-150">从哈希表创建非自定义对象</span><span class="sxs-lookup"><span data-stu-id="18ec6-150">Create non-custom objects from hash tables</span></span>

<span data-ttu-id="18ec6-151">还可以使用哈希表为非自定义类创建对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-151">You can also use hash tables to create objects for non-custom classes.</span></span> <span data-ttu-id="18ec6-152">为非自定义类创建对象时，命名空间限定的类型名称是必需的，不过您可以省略任何初始 **系统** 命名空间组件。</span><span class="sxs-lookup"><span data-stu-id="18ec6-152">When you create an object for a non-custom class, the namespace-qualified type name is required, although you may omit any initial **System** namespace component.</span></span>

<span data-ttu-id="18ec6-153">例如，以下命令会创建一个会话选项对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-153">For example, the following command creates a session option object.</span></span>

```powershell
[System.Management.Automation.Remoting.PSSessionOption]@{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
```

<span data-ttu-id="18ec6-154">哈希表功能的要求尤其是无参数构造函数要求，消除了许多现有的类。</span><span class="sxs-lookup"><span data-stu-id="18ec6-154">The requirements of the hash table feature, especially the parameterless constructor requirement, eliminate many existing classes.</span></span> <span data-ttu-id="18ec6-155">但是，大多数 PowerShell _选项_ 类旨在使用此功能和其他非常有用的类，例如 **ProcessStartInfo** 类。</span><span class="sxs-lookup"><span data-stu-id="18ec6-155">However, most PowerShell _option_ classes are designed to work with this feature, as well as other very useful classes, such as the **ProcessStartInfo** class.</span></span>

```powershell
[System.Diagnostics.ProcessStartInfo]@{
  CreateNoWindow="$true"
  Verb="run as"
}
```

```Output
Arguments               :
ArgumentList            : {}
CreateNoWindow          : True
EnvironmentVariables    : {OneDriveConsumer, PROCESSOR_ARCHITECTURE,
                           CommonProgramFiles(x86), APPDATA...}
Environment             : {[OneDriveConsumer, C:\Users\user1\OneDrive],
                           [PROCESSOR_ARCHITECTURE, AMD64],
                           [CommonProgramFiles(x86),
                           C:\Program Files (x86)\Common Files],
                           [APPDATA, C:\Users\user1\AppData\Roaming]...}
RedirectStandardInput   : False
RedirectStandardOutput  : False
RedirectStandardError   : False
...
```

<span data-ttu-id="18ec6-156">设置参数值时，也可以使用哈希表功能。</span><span class="sxs-lookup"><span data-stu-id="18ec6-156">You can also use the hash table feature when setting parameter values.</span></span> <span data-ttu-id="18ec6-157">例如，的 **SessionOption** 参数的值 `New-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="18ec6-157">For example, the value of the **SessionOption** parameter of the `New-PSSession`.</span></span>
<span data-ttu-id="18ec6-158">cmdlet 可以是哈希表。</span><span class="sxs-lookup"><span data-stu-id="18ec6-158">cmdlet can be a hash table.</span></span>

```powershell
New-PSSession -ComputerName Server01 -SessionOption @{
  IdleTimeout=43200000
  SkipCnCheck=$True
}
Register-ScheduledJob Name Test -FilePath .\Get-Inventory.ps1 -Trigger @{
  Frequency="Daily"
  At="15:00"
}
```

## <a name="generic-objects"></a><span data-ttu-id="18ec6-159">泛型对象</span><span class="sxs-lookup"><span data-stu-id="18ec6-159">Generic objects</span></span>

<span data-ttu-id="18ec6-160">你还可以在 PowerShell 中创建泛型对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-160">You can also create generic objects in PowerShell.</span></span> <span data-ttu-id="18ec6-161">泛型是为所存储或使用的一个或多个类型具有占位符（类型形参）的类、结构、接口和方法。</span><span class="sxs-lookup"><span data-stu-id="18ec6-161">Generics are classes, structures, interfaces, and methods that have placeholders (type parameters) for one or more of the types that they store or use.</span></span>

<span data-ttu-id="18ec6-162">下面的示例创建一个 **字典** 对象。</span><span class="sxs-lookup"><span data-stu-id="18ec6-162">The following example creates a **Dictionary** object.</span></span>

```powershell
$dict = New-Object 'System.Collections.Generic.Dictionary[String,Int]'
$dict.Add("One", 1)
$dict
```

```Output
Key Value
--- -----
One     1
```

<span data-ttu-id="18ec6-163">有关泛型的详细信息，请参阅 [.net 中的泛型](/dotnet/standard/generics)。</span><span class="sxs-lookup"><span data-stu-id="18ec6-163">For more information on Generics, see [Generics in .NET](/dotnet/standard/generics).</span></span>

## <a name="see-also"></a><span data-ttu-id="18ec6-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18ec6-164">See also</span></span>

[<span data-ttu-id="18ec6-165">about_Objects</span><span class="sxs-lookup"><span data-stu-id="18ec6-165">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="18ec6-166">about_Methods</span><span class="sxs-lookup"><span data-stu-id="18ec6-166">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="18ec6-167">about_Properties</span><span class="sxs-lookup"><span data-stu-id="18ec6-167">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="18ec6-168">about_pipelines</span><span class="sxs-lookup"><span data-stu-id="18ec6-168">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="18ec6-169">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="18ec6-169">about_Types.ps1xml</span></span>](about_Types.ps1xml.md)
