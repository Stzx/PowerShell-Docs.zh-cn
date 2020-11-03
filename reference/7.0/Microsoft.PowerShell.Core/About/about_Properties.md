---
description: 介绍如何在 PowerShell 中使用对象属性。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: a9ba35ea0a999b116f818bffa5fba3a1366687b1
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199600"
---
# <a name="about-properties"></a><span data-ttu-id="0dbae-104">关于属性</span><span class="sxs-lookup"><span data-stu-id="0dbae-104">About Properties</span></span>

## <a name="short-description"></a><span data-ttu-id="0dbae-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="0dbae-105">Short description</span></span>
<span data-ttu-id="0dbae-106">介绍如何在 PowerShell 中使用对象属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-106">Describes how to use object properties in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="0dbae-107">长说明</span><span class="sxs-lookup"><span data-stu-id="0dbae-107">Long description</span></span>

<span data-ttu-id="0dbae-108">PowerShell 使用称为对象的结构化集合来表示数据存储区中的项或计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="0dbae-108">PowerShell uses structured collections of information called objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="0dbae-109">通常，使用 Microsoft .NET 框架的一部分的对象，但也可以在 PowerShell 中创建自定义对象。</span><span class="sxs-lookup"><span data-stu-id="0dbae-109">Typically, you work with object that are part of the Microsoft .NET Framework, but you can also create custom objects in PowerShell.</span></span>

<span data-ttu-id="0dbae-110">项与其对象之间的关联非常接近。</span><span class="sxs-lookup"><span data-stu-id="0dbae-110">The association between an item and its object is very close.</span></span> <span data-ttu-id="0dbae-111">更改对象时，通常会更改其表示的项。</span><span class="sxs-lookup"><span data-stu-id="0dbae-111">When you change an object, you usually change the item that it represents.</span></span> <span data-ttu-id="0dbae-112">例如，在 PowerShell 中获取文件时，不会获得实际文件。</span><span class="sxs-lookup"><span data-stu-id="0dbae-112">For example, when you get a file in PowerShell, you do not get the actual file.</span></span> <span data-ttu-id="0dbae-113">相反，您将获得一个表示该文件的 FileInfo 对象。</span><span class="sxs-lookup"><span data-stu-id="0dbae-113">Instead, you get a FileInfo object that represents the file.</span></span> <span data-ttu-id="0dbae-114">更改 FileInfo 对象时，文件也会发生更改。</span><span class="sxs-lookup"><span data-stu-id="0dbae-114">When you change the FileInfo object, the file changes too.</span></span>

<span data-ttu-id="0dbae-115">大多数对象都具有属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-115">Most objects have properties.</span></span> <span data-ttu-id="0dbae-116">属性是与对象关联的数据。</span><span class="sxs-lookup"><span data-stu-id="0dbae-116">Properties are the data that is associated with an object.</span></span> <span data-ttu-id="0dbae-117">不同类型的对象具有不同的属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-117">Different types of object have different properties.</span></span> <span data-ttu-id="0dbae-118">例如，FileInfo 对象（表示文件）有一个 **IsReadOnly** 属性，该属性包含 $True 如果该属性为只读 $False 属性，则为; 如果文件不存在，则为。</span><span class="sxs-lookup"><span data-stu-id="0dbae-118">For example, a FileInfo object, which represents a file, has an **IsReadOnly** property that contains $True if the file the read-only attribute and $False if it does not.</span></span>
<span data-ttu-id="0dbae-119">表示文件系统目录的 DirectoryInfo 对象具有一个父属性，其中包含父目录的路径。</span><span class="sxs-lookup"><span data-stu-id="0dbae-119">A DirectoryInfo object, which represents a file system directory, has a Parent property that contains the path to the parent directory.</span></span>

### <a name="object-properties"></a><span data-ttu-id="0dbae-120">对象属性</span><span class="sxs-lookup"><span data-stu-id="0dbae-120">Object properties</span></span>

<span data-ttu-id="0dbae-121">若要获取对象的属性，请使用 `Get-Member` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0dbae-121">To get the properties of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="0dbae-122">例如，若要获取 **FileInfo** 对象的属性，请使用 `Get-ChildItem` cmdlet 获取表示文件的 FileInfo 对象。</span><span class="sxs-lookup"><span data-stu-id="0dbae-122">For example, to get the properties of a **FileInfo** object, use the `Get-ChildItem` cmdlet to get the FileInfo object that represents a file.</span></span> <span data-ttu-id="0dbae-123">然后，使用管道运算符 ( # A0) 将 **FileInfo** 对象发送到 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="0dbae-123">Then, use a pipeline operator (&#124;) to send the **FileInfo** object to `Get-Member`.</span></span> <span data-ttu-id="0dbae-124">下面的命令获取 PowerShell.exe 文件并将其发送到 `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="0dbae-124">The following command gets the PowerShell.exe file and sends it to `Get-Member`.</span></span>
<span data-ttu-id="0dbae-125">\$Pshome 自动变量包含 PowerShell 安装目录的路径。</span><span class="sxs-lookup"><span data-stu-id="0dbae-125">The \$Pshome automatic variable contains the path of the PowerShell installation directory.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

<span data-ttu-id="0dbae-126">此命令的输出列出 **FileInfo** 对象的成员。</span><span class="sxs-lookup"><span data-stu-id="0dbae-126">The output of the command lists the members of the **FileInfo** object.</span></span>
<span data-ttu-id="0dbae-127">成员同时包括属性和方法。</span><span class="sxs-lookup"><span data-stu-id="0dbae-127">Members include both properties and methods.</span></span> <span data-ttu-id="0dbae-128">在 PowerShell 中工作时，可以访问对象的所有成员。</span><span class="sxs-lookup"><span data-stu-id="0dbae-128">When you work in PowerShell, you have access to all the members of the objects.</span></span>

<span data-ttu-id="0dbae-129">若要仅获取对象的属性而不获取方法，请使用 cmdlet 的 MemberType 参数，其 `Get-Member` 值为 "property"，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="0dbae-129">To get only the properties of an object and not the methods, use the MemberType parameter of the `Get-Member` cmdlet with a value of "property", as shown in the following example.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member -MemberType property
```

```Output
TypeName: System.IO.FileInfo

Name              MemberType Definition
----              ---------- ----------
Attributes        Property   System.IO.FileAttributes Attributes {get;set;}
CreationTime      Property   System.DateTime CreationTime {get;set;}
CreationTimeUtc   Property   System.DateTime CreationTimeUtc {get;set;}
Directory         Property   System.IO.DirectoryInfo Directory {get;}
DirectoryName     Property   System.String DirectoryName {get;}
Exists            Property   System.Boolean Exists {get;}
Extension         Property   System.String Extension {get;}
FullName          Property   System.String FullName {get;}
IsReadOnly        Property   System.Boolean IsReadOnly {get;set;}
LastAccessTime    Property   System.DateTime LastAccessTime {get;set;}
LastAccessTimeUtc Property   System.DateTime LastAccessTimeUtc {get;set;}
LastWriteTime     Property   System.DateTime LastWriteTime {get;set;}
LastWriteTimeUtc  Property   System.DateTime LastWriteTimeUtc {get;set;}
Length            Property   System.Int64 Length {get;}
Name              Property   System.String Name {get;}
```

<span data-ttu-id="0dbae-130">找到属性后，可以在 PowerShell 命令中使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-130">After you find the properties, you can use them in your PowerShell commands.</span></span>

## <a name="property-values"></a><span data-ttu-id="0dbae-131">属性值</span><span class="sxs-lookup"><span data-stu-id="0dbae-131">Property values</span></span>

<span data-ttu-id="0dbae-132">尽管特定类型的每个对象都具有相同的属性，但这些属性的值会描述特定的对象。</span><span class="sxs-lookup"><span data-stu-id="0dbae-132">Although every object of a specific type has the same properties, the values of those properties describe the particular object.</span></span> <span data-ttu-id="0dbae-133">例如，每个 FileInfo 对象都有一个 CreationTime 属性，但该属性的值不同于每个文件。</span><span class="sxs-lookup"><span data-stu-id="0dbae-133">For example, every FileInfo object has a CreationTime property, but the value of that property differs for each file.</span></span>

<span data-ttu-id="0dbae-134">获取对象的属性值的最常见方法是使用点方法。</span><span class="sxs-lookup"><span data-stu-id="0dbae-134">The most common way to get the values of the properties of an object is to use the dot method.</span></span> <span data-ttu-id="0dbae-135">键入对对象的引用，如包含对象的变量或获取对象的命令。</span><span class="sxs-lookup"><span data-stu-id="0dbae-135">Type a reference to the object, such as a variable that contains the object, or a command that gets the object.</span></span> <span data-ttu-id="0dbae-136">然后，键入一个点 (。 ) 后跟属性名称。</span><span class="sxs-lookup"><span data-stu-id="0dbae-136">Then, type a dot (.) followed by the property name.</span></span>

<span data-ttu-id="0dbae-137">例如，下面的命令显示 PowerShell.exe 文件的 CreationTime 属性的值。</span><span class="sxs-lookup"><span data-stu-id="0dbae-137">For example, the following command displays the value of the CreationTime property of the PowerShell.exe file.</span></span> <span data-ttu-id="0dbae-138">该 `Get-ChildItem` 命令返回一个 FileInfo 对象，该对象表示 PowerShell.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="0dbae-138">The `Get-ChildItem` command returns a FileInfo object that represents the PowerShell.exe file.</span></span> <span data-ttu-id="0dbae-139">命令括在括号中，以确保在访问任何属性之前执行该命令。</span><span class="sxs-lookup"><span data-stu-id="0dbae-139">The command is enclosed in parentheses to make sure that it is executed before any properties are accessed.</span></span> <span data-ttu-id="0dbae-140">`Get-ChildItem`命令后跟一个点和 CreationTime 属性的名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0dbae-140">The `Get-ChildItem` command is followed by a dot and the name of the CreationTime property, as follows:</span></span>

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="0dbae-141">你还可以将对象保存在变量中，然后使用点方法获取其属性，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="0dbae-141">You can also save an object in a variable and then get its properties by using the dot method, as shown in the following example:</span></span>

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="0dbae-142">你还可以使用 `Select-Object` 和 `Format-List` cmdlet 显示对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="0dbae-142">You can also use the `Select-Object` and `Format-List` cmdlets to display the property values of an object.</span></span> <span data-ttu-id="0dbae-143">`Select-Object``Format-List`每个都有一个 **属性** 参数。</span><span class="sxs-lookup"><span data-stu-id="0dbae-143">`Select-Object` and `Format-List` each have a **Property** parameter.</span></span> <span data-ttu-id="0dbae-144">可以使用 **Property** 参数来指定一个或多个属性及其值。</span><span class="sxs-lookup"><span data-stu-id="0dbae-144">You can use the **Property** parameter to specify one or more properties and their values.</span></span> <span data-ttu-id="0dbae-145">或者，可以使用通配符 (\*) 来表示所有属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-145">Or, you can use the wildcard character (\*) to represent all the properties.</span></span>

<span data-ttu-id="0dbae-146">例如，下面的命令显示 PowerShell.exe 文件的所有属性的值。</span><span class="sxs-lookup"><span data-stu-id="0dbae-146">For example, the following command displays the values of all the properties of the PowerShell.exe file.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Format-List -Property *
```

```output
PSPath            : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0\PowerShell.exe
PSParentPath      : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0
PSChildName       : PowerShell.exe
PSDrive           : C
PSProvider        : Microsoft.PowerShell.Core\FileSystem
PSIsContainer     : False
Mode              : -a----
VersionInfo       : File:             C:\Windows\System32\WindowsPowerShell\
                    v1.0\PowerShell.exe
                    InternalName:     POWERSHELL
                    OriginalFilename: PowerShell.EXE.MUI
                    FileVersion:      10.0.16299.15 (WinBuild.160101.0800)
                    FileDescription:  Windows PowerShell
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.16299.15
                    Debug:            False
                    Patched:          False
                    PreRelease:       False
                    PrivateBuild:     False
                    SpecialBuild:     False
                    Language:         English (United States)

BaseName          : PowerShell
Target            : {C:\Windows\WinSxS\amd64_microsoft-windows-powershell-ex
                    e_31bf3856ad364e35_10.0.16299.15_none_8c022aa6735716ae\p
                    owershell.exe}
LinkType          : HardLink
Name              : PowerShell.exe
Length            : 449024
DirectoryName     : C:\Windows\System32\WindowsPowerShell\v1.0
Directory         : C:\Windows\System32\WindowsPowerShell\v1.0
IsReadOnly        : False
Exists            : True
FullName          : C:\Windows\System32\WindowsPowerShell\v1.0\PowerShell.ex
Extension         : .exe
CreationTime      : 9/29/2017 6:43:19 AM
CreationTimeUtc   : 9/29/2017 1:43:19 PM
LastAccessTime    : 9/29/2017 6:43:19 AM
LastAccessTimeUtc : 9/29/2017 1:43:19 PM
LastWriteTime     : 9/29/2017 6:43:19 AM
LastWriteTimeUtc  : 9/29/2017 1:43:19 PM
Attributes        : Archive
```

### <a name="static-properties"></a><span data-ttu-id="0dbae-147">静态属性</span><span class="sxs-lookup"><span data-stu-id="0dbae-147">Static properties</span></span>

<span data-ttu-id="0dbae-148">可以在 PowerShell 中使用 .NET 类的静态属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-148">You can use the static properties of .NET classes in PowerShell.</span></span> <span data-ttu-id="0dbae-149">静态属性是类的属性，这与作为对象属性的标准属性不同。</span><span class="sxs-lookup"><span data-stu-id="0dbae-149">Static properties are properties of class, unlike standard properties, which are properties of an object.</span></span>

<span data-ttu-id="0dbae-150">若要获取类的静态属性，请使用 Get-Member cmdlet 的静态参数。</span><span class="sxs-lookup"><span data-stu-id="0dbae-150">To get the static properties of an class, use the Static parameter of the Get-Member cmdlet.</span></span>

<span data-ttu-id="0dbae-151">例如，下面的命令获取类的静态属性 `System.DateTime` 。</span><span class="sxs-lookup"><span data-stu-id="0dbae-151">For example, the following command gets the static properties of the `System.DateTime` class.</span></span>

```powershell
Get-Date | Get-Member -MemberType Property -Static
```

```Output
TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

<span data-ttu-id="0dbae-152">若要获取静态属性的值，请使用以下语法。</span><span class="sxs-lookup"><span data-stu-id="0dbae-152">To get the value of a static property, use the following syntax.</span></span>

```
[<ClassName>]::<Property>
```

<span data-ttu-id="0dbae-153">例如，下面的命令获取类的 UtcNow 静态属性的值 `System.DateTime` 。</span><span class="sxs-lookup"><span data-stu-id="0dbae-153">For example, the following command gets the value of the UtcNow static property of the `System.DateTime` class.</span></span>

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a><span data-ttu-id="0dbae-154">标量对象和集合的属性</span><span class="sxs-lookup"><span data-stu-id="0dbae-154">Properties of scalar objects and collections</span></span>

<span data-ttu-id="0dbae-155">特定类型的一个 ( "标量" ) 对象的属性通常不同于同一类型的对象集合的属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-155">The properties of one ("scalar") object of a particular type are often different from the properties of a collection of objects of the same type.</span></span>
<span data-ttu-id="0dbae-156">例如，每个服务都有作为 **displayname** 属性，但服务集合没有 **displayname** 属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-156">For example, every service has as **DisplayName** property, but a collection of services does not have a **DisplayName** property.</span></span>

<span data-ttu-id="0dbae-157">以下命令将获取 "Audiosrv" 服务的 **DisplayName** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="0dbae-157">The following command gets the value of the **DisplayName** property of the 'Audiosrv' service.</span></span>

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

<span data-ttu-id="0dbae-158">从 PowerShell 3.0 开始，PowerShell 将尝试防止标量对象和集合的属性不同的脚本错误。</span><span class="sxs-lookup"><span data-stu-id="0dbae-158">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing properties of scalar objects and collections.</span></span> <span data-ttu-id="0dbae-159">同一命令返回返回的每个服务的 **DisplayName** 属性的值 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="0dbae-159">The same command returns the value of the **DisplayName** property of every service that `Get-Service` returns.</span></span>

```powershell
(Get-Service).DisplayName
```

```output
Application Experience
Application Layer Gateway Service
Windows All-User Install Agent
Application Identity
Application Information
...
```

<span data-ttu-id="0dbae-160">提交集合时，但请求仅存在于单个 ( "标量" ) 对象上的属性时，PowerShell 将返回集合中每个对象的该属性的值。</span><span class="sxs-lookup"><span data-stu-id="0dbae-160">When you submit a collection, but request a property that exists only on single ("scalar") objects, PowerShell returns the value of that property for every object in the collection.</span></span>

<span data-ttu-id="0dbae-161">所有集合都具有 **Count** 属性，该属性可返回集合中的对象数。</span><span class="sxs-lookup"><span data-stu-id="0dbae-161">All collections have a **Count** property that returns how many objects are in the collection.</span></span>

```powershell
(Get-Service).Count
```

```output
176
```

<span data-ttu-id="0dbae-162">从 PowerShell 3.0 开始，如果请求零个对象或一个对象的 Count 或 Length 属性，则 PowerShell 将返回正确的值。</span><span class="sxs-lookup"><span data-stu-id="0dbae-162">Beginning in PowerShell 3.0, if you request the Count or Length property of zero objects or one object, PowerShell returns the correct value.</span></span>

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

<span data-ttu-id="0dbae-163">如果属性存在于单个对象和集合上，则仅返回集合的属性。</span><span class="sxs-lookup"><span data-stu-id="0dbae-163">If a property exists on the individual objects and on the collection, only the collection's property is returned.</span></span>

 ```powershell
 $collection = @(
 [pscustomobject]@{length = "foo"}
 [pscustomobject]@{length = "bar"}
 )
 # PowerShell returns the collection's Length.
 $collection.length
 ```

 ```output
 2
 ```

<span data-ttu-id="0dbae-164">此功能也适用于标量对象和集合的方法。</span><span class="sxs-lookup"><span data-stu-id="0dbae-164">This feature also works on methods of scalar objects and collections.</span></span> <span data-ttu-id="0dbae-165">有关详细信息，请参阅 [about_Methods](about_methods.md)。</span><span class="sxs-lookup"><span data-stu-id="0dbae-165">For more information, see [about_Methods](about_methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0dbae-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dbae-166">See also</span></span>

[<span data-ttu-id="0dbae-167">about_Methods</span><span class="sxs-lookup"><span data-stu-id="0dbae-167">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="0dbae-168">about_Objects</span><span class="sxs-lookup"><span data-stu-id="0dbae-168">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="0dbae-169">Get-Member</span><span class="sxs-lookup"><span data-stu-id="0dbae-169">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="0dbae-170">Select-Object</span><span class="sxs-lookup"><span data-stu-id="0dbae-170">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="0dbae-171">Format-List</span><span class="sxs-lookup"><span data-stu-id="0dbae-171">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)
