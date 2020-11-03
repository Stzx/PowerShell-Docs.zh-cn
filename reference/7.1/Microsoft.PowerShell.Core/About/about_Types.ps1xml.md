---
description: 介绍如何使用 `Types.ps1xml` 文件来扩展在 PowerShell 中使用的对象的类型。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_types.ps1xml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: 66c319a6f1e84fb2d7aeea60433a2ddea9fb4616
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200013"
---
# <a name="about-typesps1xml"></a><span data-ttu-id="78d9d-104">关于 Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="78d9d-104">About Types.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="78d9d-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="78d9d-105">Short description</span></span>
<span data-ttu-id="78d9d-106">介绍如何使用 `Types.ps1xml` 文件来扩展在 PowerShell 中使用的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="78d9d-106">Explains how to use `Types.ps1xml` files to extend the types of objects that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="78d9d-107">长说明</span><span class="sxs-lookup"><span data-stu-id="78d9d-107">Long description</span></span>

<span data-ttu-id="78d9d-108">扩展类型数据定义了 PowerShell 中对象类型的 "成员" )  ( 的附加属性和方法。</span><span class="sxs-lookup"><span data-stu-id="78d9d-108">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="78d9d-109">可通过两种方法将扩展类型数据添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="78d9d-109">There are two techniques for adding extended type data to a PowerShell session.</span></span>

- <span data-ttu-id="78d9d-110">`Types.ps1xml` 文件：定义扩展类型数据的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="78d9d-110">`Types.ps1xml` file: An XML file that defines extended type data.</span></span>
- <span data-ttu-id="78d9d-111">`Update-TypeData`：一个 cmdlet，用于重新加载 `Types.ps1xml` 文件并为当前会话中的类型定义扩展数据。</span><span class="sxs-lookup"><span data-stu-id="78d9d-111">`Update-TypeData`: A cmdlet that reloads `Types.ps1xml` files and defines extended data for types in the current session.</span></span>

<span data-ttu-id="78d9d-112">本主题描述 `Types.ps1xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="78d9d-112">This topic describes `Types.ps1xml` files.</span></span> <span data-ttu-id="78d9d-113">有关使用 `Update-TypeData` cmdlet 向当前会话添加动态扩展类型数据的详细信息，请参阅 [update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData)。</span><span class="sxs-lookup"><span data-stu-id="78d9d-113">For more information about using the `Update-TypeData` cmdlet to add dynamic extended type data to the current session see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

## <a name="about-extended-type-data"></a><span data-ttu-id="78d9d-114">关于扩展类型数据</span><span class="sxs-lookup"><span data-stu-id="78d9d-114">About extended type data</span></span>

<span data-ttu-id="78d9d-115">扩展类型数据定义了 PowerShell 中对象类型的 "成员" )  ( 的附加属性和方法。</span><span class="sxs-lookup"><span data-stu-id="78d9d-115">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="78d9d-116">你可以扩展 PowerShell 支持的任何类型，并使用已添加的属性和方法，其方式与你使用在对象类型上定义的属性相同。</span><span class="sxs-lookup"><span data-stu-id="78d9d-116">You can extend any type that is supported by PowerShell and use the added properties and methods in the same way that you use the properties that are defined on the object types.</span></span>

<span data-ttu-id="78d9d-117">例如，PowerShell 会将 **DateTime** 属性添加到所有 `System.DateTime` 对象，如 `Get-Date` cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="78d9d-117">For example, PowerShell adds a **DateTime** property to all `System.DateTime` objects, such as the ones that the `Get-Date` cmdlet returns.</span></span>

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

<span data-ttu-id="78d9d-118">不会在 [system.web](/dotnet/api/system.datetime)结构的描述中找到 **datetime** 属性，因为 powershell 会添加属性，它仅在 PowerShell 中可见。</span><span class="sxs-lookup"><span data-stu-id="78d9d-118">You won't find the **DateTime** property in the description of the [System.DateTime](/dotnet/api/system.datetime) structure, because PowerShell adds the property and it is visible only in PowerShell.</span></span>

<span data-ttu-id="78d9d-119">PowerShell 在内部定义一组默认的扩展类型。</span><span class="sxs-lookup"><span data-stu-id="78d9d-119">PowerShell internally defines a default set of extended types.</span></span> <span data-ttu-id="78d9d-120">此类型信息将在启动时在每个 PowerShell 会话中加载。</span><span class="sxs-lookup"><span data-stu-id="78d9d-120">This type information is loaded in every PowerShell session at startup.</span></span> <span data-ttu-id="78d9d-121">**DateTime** 属性是此默认集的一部分。</span><span class="sxs-lookup"><span data-stu-id="78d9d-121">The **DateTime** property is part of this default set.</span></span> <span data-ttu-id="78d9d-122">在 PowerShell 6 之前，类型定义存储 `Types.ps1xml` 在 powershell 安装目录中 (`$PSHOME`) 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-122">Prior to PowerShell 6, the type definitions were stored the `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`).</span></span>

## <a name="adding-extended-type-data-to-powershell"></a><span data-ttu-id="78d9d-123">将扩展类型数据添加到 PowerShell</span><span class="sxs-lookup"><span data-stu-id="78d9d-123">Adding extended type data to PowerShell</span></span>

<span data-ttu-id="78d9d-124">PowerShell 会话中有三个扩展类型数据源。</span><span class="sxs-lookup"><span data-stu-id="78d9d-124">There are three sources of extended type data in PowerShell sessions.</span></span>

- <span data-ttu-id="78d9d-125">由 PowerShell 定义并自动加载到每个 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-125">The defined by PowerShell and is loaded automatically into every PowerShell session.</span></span> <span data-ttu-id="78d9d-126">从 PowerShell 6 开始，此信息编译到 PowerShell 中，不再在文件中发送 `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-126">Beginning with PowerShell 6, this information is compiled into PowerShell and is no longer shipped in a `Types.ps1xml` file.</span></span>

- <span data-ttu-id="78d9d-127">模块 `Types.ps1xml` 导入到当前会话中时将加载模块导出的文件。</span><span class="sxs-lookup"><span data-stu-id="78d9d-127">The `Types.ps1xml` files that modules export are loaded when the module is imported into the current session.</span></span>

- <span data-ttu-id="78d9d-128">使用 cmdlet 定义的扩展类型数据 `Update-TypeData` 仅添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-128">Extended type data that is defined by using the `Update-TypeData` cmdlet is added only to the current session.</span></span> <span data-ttu-id="78d9d-129">它不保存在文件中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-129">It is not saved in a file.</span></span>

<span data-ttu-id="78d9d-130">在会话中，三个源中的扩展类型数据以相同的方式应用于对象，并可用于指定类型的所有对象。</span><span class="sxs-lookup"><span data-stu-id="78d9d-130">In the session, the extended type data from the three sources is applied to objects in the same way and is available on all objects of the specified types.</span></span>

## <a name="the-typedata-cmdlets"></a><span data-ttu-id="78d9d-131">Update-typedata cmdlet</span><span class="sxs-lookup"><span data-stu-id="78d9d-131">The TypeData cmdlets</span></span>

<span data-ttu-id="78d9d-132">以下 cmdlet 包含在 PowerShell 3.0 和更高版本的 **Microsoft. Utility** 模块中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-132">The following cmdlets are included in the **Microsoft.PowerShell.Utility** module in PowerShell 3.0 and later.</span></span>

- <span data-ttu-id="78d9d-133">`Get-TypeData`：获取当前会话中的扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="78d9d-133">`Get-TypeData`: Gets extended type data in the current session.</span></span>
- <span data-ttu-id="78d9d-134">`Update-TypeData`：重新加载 `Types.ps1xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="78d9d-134">`Update-TypeData`: Reloads `Types.ps1xml` files.</span></span> <span data-ttu-id="78d9d-135">将扩展类型数据添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-135">Adds extended type data to the current session.</span></span>
- <span data-ttu-id="78d9d-136">`Remove-TypeData`：从当前会话中删除扩展类型数据。</span><span class="sxs-lookup"><span data-stu-id="78d9d-136">`Remove-TypeData`: Removes extended type data from the current session.</span></span>

<span data-ttu-id="78d9d-137">有关这些 cmdlet 的详细信息，请参阅每个 cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="78d9d-137">For more information about these cmdlets, see the help topic for each cmdlet.</span></span>

## <a name="built-in-typesps1xml-files"></a><span data-ttu-id="78d9d-138">内置 Types.ps1xml 文件</span><span class="sxs-lookup"><span data-stu-id="78d9d-138">Built-in Types.ps1xml files</span></span>

<span data-ttu-id="78d9d-139">`Types.ps1xml`目录中的文件 `$PSHOME` 将自动添加到每个会话中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-139">The `Types.ps1xml` files in the `$PSHOME` directory are added automatically to every session.</span></span>

<span data-ttu-id="78d9d-140">`Types.ps1xml`Powershell 安装目录中的文件 (`$PSHOME`) 是基于 XML 的文本文件，可让你向 PowerShell 中使用的对象添加属性和方法。</span><span class="sxs-lookup"><span data-stu-id="78d9d-140">The `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`) is an XML-based text file that lets you add properties and methods to the objects that are used in PowerShell.</span></span> <span data-ttu-id="78d9d-141">PowerShell 具有 `Types.ps1xml` 将几个元素添加到 .net 类型的内置文件，但你可以创建其他 `Types.ps1xml` 文件来进一步扩展这些类型。</span><span class="sxs-lookup"><span data-stu-id="78d9d-141">PowerShell has built-in `Types.ps1xml` files that add several elements to the .NET types, but you can create additional `Types.ps1xml` files to further extend the types.</span></span>

<span data-ttu-id="78d9d-142">例如，默认情况下，数组对象 (`System.Array`) 的 **Length** 属性列出数组中对象的数量。</span><span class="sxs-lookup"><span data-stu-id="78d9d-142">For example, by default, array objects (`System.Array`) have a **Length** property that lists the number of objects in the array.</span></span> <span data-ttu-id="78d9d-143">但是，因为名称 **长度** 并不清楚地描述属性，所以 PowerShell 会添加一个别名属性 **，其中显示相同的值** 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-143">However, because the name **Length** does not clearly describe the property, PowerShell adds an alias property named **Count** that displays the same value.</span></span> <span data-ttu-id="78d9d-144">下面的 XML 将 **Count** 属性添加到该 `System.Array` 类型。</span><span class="sxs-lookup"><span data-stu-id="78d9d-144">The following XML adds the **Count** property to the `System.Array` type.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-145">若要获取新的 **AliasProperty** ，请 `Get-Member` 在任何数组上使用命令，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="78d9d-145">To get the new **AliasProperty** , use a `Get-Member` command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="78d9d-146">该命令将返回以下结果。</span><span class="sxs-lookup"><span data-stu-id="78d9d-146">The command returns the following results.</span></span>

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

<span data-ttu-id="78d9d-147">因此，可以在 PowerShell 中使用数组的 **Count** 属性或 **Length** 属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-147">As a result, you can use either the **Count** property or the **Length** property of arrays in PowerShell.</span></span> <span data-ttu-id="78d9d-148">例如：</span><span class="sxs-lookup"><span data-stu-id="78d9d-148">For example:</span></span>

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a><span data-ttu-id="78d9d-149">创建新的 Types.ps1xml 文件</span><span class="sxs-lookup"><span data-stu-id="78d9d-149">Creating new Types.ps1xml files</span></span>

<span data-ttu-id="78d9d-150">`.ps1xml`随 PowerShell 一起安装的文件已进行数字签名，以防止篡改，因为格式设置可以包括脚本块。</span><span class="sxs-lookup"><span data-stu-id="78d9d-150">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="78d9d-151">因此，若要将属性或方法添加到 .NET 类型，请创建自己的 `Types.ps1xml` 文件，然后将其添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="78d9d-151">Therefore, to add a property or method to a .NET type, create your own `Types.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="78d9d-152">若要创建新文件，请从复制现有 `Types.ps1xml` 文件开始。</span><span class="sxs-lookup"><span data-stu-id="78d9d-152">To create a new file, start by copying an existing `Types.ps1xml` file.</span></span> <span data-ttu-id="78d9d-153">新文件可以具有任何名称，但它必须具有 `.ps1xml` 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="78d9d-153">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="78d9d-154">可以将新文件放在 PowerShell 可访问的任何目录中，但将文件放在 PowerShell 安装目录中 (`$PSHOME`) 或安装目录的子目录中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-154">You can place the new file in any directory that is accessible to PowerShell, but it is useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="78d9d-155">保存新文件后，使用 `Update-TypeData` cmdlet 将新文件添加到 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="78d9d-155">When you have saved the new file, use the `Update-TypeData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="78d9d-156">如果你希望你的类型优先于定义的内置类型，请使用 cmdlet 的 **PrependData** 参数 `Update-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-156">If you want your types to take precedence over the built-in types that are defined, use the **PrependData** parameter of the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="78d9d-157">`Update-TypeData` 仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="78d9d-157">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="78d9d-158">若要对所有未来的会话进行更改，请导出控制台，或将 `Update-TypeData` 命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="78d9d-158">To make the change to all future sessions, export the console, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

## <a name="typesps1xml-and-add-member"></a><span data-ttu-id="78d9d-159">Types.ps1xml 和 Add-Member</span><span class="sxs-lookup"><span data-stu-id="78d9d-159">Types.ps1xml and Add-Member</span></span>

<span data-ttu-id="78d9d-160">`Types.ps1xml`文件将属性和方法添加到受影响的 PowerShell 会话中指定 .net 类型的对象的所有实例。</span><span class="sxs-lookup"><span data-stu-id="78d9d-160">The `Types.ps1xml` files add properties and methods to all the instances of the objects of the specified .NET type in the affected PowerShell session.</span></span> <span data-ttu-id="78d9d-161">但是，如果需要将属性或方法仅添加到对象的一个实例，请使用 `Add-Member` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78d9d-161">However, if you need to add properties or methods only to one instance of an object, use the `Add-Member` cmdlet.</span></span>

<span data-ttu-id="78d9d-162">有关详细信息，请参阅 [添加成员](xref:Microsoft.PowerShell.Utility.Add-Member)。</span><span class="sxs-lookup"><span data-stu-id="78d9d-162">For more information, see [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span></span>

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a><span data-ttu-id="78d9d-163">示例：将 Age 成员添加到 FileInfo 对象</span><span class="sxs-lookup"><span data-stu-id="78d9d-163">Example: Adding an Age member to FileInfo objects</span></span>

<span data-ttu-id="78d9d-164">此示例演示如何将 **Age** 属性添加到 **FileInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="78d9d-164">This example shows how to add an **Age** property to **System.IO.FileInfo** objects.</span></span> <span data-ttu-id="78d9d-165">文件的保留时间是其创建时间和当前时间之间的差异（以天为单位）。</span><span class="sxs-lookup"><span data-stu-id="78d9d-165">The age of a file is the difference between its creation time and the current time in days.</span></span>

<span data-ttu-id="78d9d-166">因为 **Age** 属性是通过使用脚本块进行计算的，所以请查找一个标记，将其 `<ScriptProperty>` 用作新的 **Age** 属性的模型。</span><span class="sxs-lookup"><span data-stu-id="78d9d-166">Because the **Age** property is calculated by using a script block, find a `<ScriptProperty>` tag to use as a model for the new **Age** property.</span></span>

<span data-ttu-id="78d9d-167">将以下 XML 代码保存到文件 `$PSHOME\MyTypes.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-167">Save the follow XML code to the file `$PSHOME\MyTypes.ps1xml`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

<span data-ttu-id="78d9d-168">运行 `Update-TypeData` 将新文件添加 `Types.ps1xml` 到当前会话。</span><span class="sxs-lookup"><span data-stu-id="78d9d-168">Run `Update-TypeData` to add the new `Types.ps1xml` file to the current session.</span></span> <span data-ttu-id="78d9d-169">该命令使用 **PrependData** 参数将新文件置于比原始定义更高的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="78d9d-169">The command uses the **PrependData** parameter to place the new file in a precedence order higher than the original definitions.</span></span>

<span data-ttu-id="78d9d-170">有关的详细信息 `Update-TypeData` ，请参阅 [update-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData)。</span><span class="sxs-lookup"><span data-stu-id="78d9d-170">For more information about `Update-TypeData`, see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

<span data-ttu-id="78d9d-171">若要测试更改，请运行 `Get-ChildItem` 命令以获取目录中的 PowerShell.exe 文件 `$PSHOME` ，然后通过管道将该文件传递给 `Format-List` cmdlet 以列出该文件的所有属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-171">To test the change, run a `Get-ChildItem` command to get the PowerShell.exe file in the `$PSHOME` directory, and then pipe the file to the `Format-List` cmdlet to list all of the properties of the file.</span></span> <span data-ttu-id="78d9d-172">更改后， **Age** 属性将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-172">As a result of the change, the **Age** property appears in the list.</span></span>

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a><span data-ttu-id="78d9d-173">Types.ps1xml 文件中的 XML</span><span class="sxs-lookup"><span data-stu-id="78d9d-173">The XML in Types.ps1xml files</span></span>

<span data-ttu-id="78d9d-174">在 GitHub 上的 PowerShell 源代码存储库 [中，](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) 可以找到完整的架构定义。</span><span class="sxs-lookup"><span data-stu-id="78d9d-174">The full schema definition can be found in [Types.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="78d9d-175">`<Types>`标记包含在文件中定义的所有类型。</span><span class="sxs-lookup"><span data-stu-id="78d9d-175">The `<Types>` tag encloses all of the types that are defined in the file.</span></span> <span data-ttu-id="78d9d-176">应该只有一个 `<Types>` 标记。</span><span class="sxs-lookup"><span data-stu-id="78d9d-176">There should be only one `<Types>` tag.</span></span>

<span data-ttu-id="78d9d-177">文件中提到的每个 .NET 类型都应由 `<Type>` 标记表示。</span><span class="sxs-lookup"><span data-stu-id="78d9d-177">Each .NET type mentioned in the file should be represented by a `<Type>` tag.</span></span>

<span data-ttu-id="78d9d-178">类型标记必须包含以下标记：</span><span class="sxs-lookup"><span data-stu-id="78d9d-178">The type tags must contain the following tags:</span></span>

<span data-ttu-id="78d9d-179">`<Name>`：包含受影响的 .NET 类型的名称。</span><span class="sxs-lookup"><span data-stu-id="78d9d-179">`<Name>`: Encloses the name of the affected .NET type.</span></span>

<span data-ttu-id="78d9d-180">`<Members>`：包含为 .NET 类型定义的新属性和方法的标记。</span><span class="sxs-lookup"><span data-stu-id="78d9d-180">`<Members>`: Encloses the tags for the new properties and methods that are defined for the .NET type.</span></span>

<span data-ttu-id="78d9d-181">以下任何成员标记可以位于 `<Members>` 标记内。</span><span class="sxs-lookup"><span data-stu-id="78d9d-181">Any of the following member tags can be inside the `<Members>` tag.</span></span>

<span data-ttu-id="78d9d-182">`<AliasProperty>`：定义现有属性的新名称。</span><span class="sxs-lookup"><span data-stu-id="78d9d-182">`<AliasProperty>`: Defines a new name for an existing property.</span></span>

<span data-ttu-id="78d9d-183">`<AliasProperty>`标记必须有一个 `<Name>` 标记，该标记指定新属性的名称和 `<ReferencedMemberName>` 指定现有属性的标记。</span><span class="sxs-lookup"><span data-stu-id="78d9d-183">The `<AliasProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<ReferencedMemberName>` tag that specifies the existing property.</span></span>

<span data-ttu-id="78d9d-184">例如， **Count** alias 属性是数组对象的 **Length** 属性的别名。</span><span class="sxs-lookup"><span data-stu-id="78d9d-184">For example, the **Count** alias property is an alias for the **Length** property of array objects.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-185">`<CodeMethod>`：引用 .NET 类的静态方法。</span><span class="sxs-lookup"><span data-stu-id="78d9d-185">`<CodeMethod>`:  References a static method of a .NET class.</span></span>

<span data-ttu-id="78d9d-186">`<CodeMethod>`标记必须有一个 `<Name>` 指定新方法的名称的标记和一个 `<GetCodeReference>` 标记，该标记指定在其中定义方法的代码。</span><span class="sxs-lookup"><span data-stu-id="78d9d-186">The `<CodeMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<GetCodeReference>` tag that specifies the code in which the method is defined.</span></span>

<span data-ttu-id="78d9d-187">例如，对象的 **Mode** 属性 `System.IO.DirectoryInfo` 是在 PowerShell FileSystem 提供程序中定义的代码属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-187">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-188">`<CodeProperty>`：引用 .NET 类的静态方法。</span><span class="sxs-lookup"><span data-stu-id="78d9d-188">`<CodeProperty>`: References a static method of a .NET class.</span></span>

<span data-ttu-id="78d9d-189">`<CodeProperty>`标记必须有一个 `<Name>` 指定新属性的名称的标记和一个 `<GetCodeReference>` 标记，该标记指定在其中定义属性的代码。</span><span class="sxs-lookup"><span data-stu-id="78d9d-189">The `<CodeProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetCodeReference>` tag that specifies the code in which the property is defined.</span></span>

<span data-ttu-id="78d9d-190">例如，对象的 **Mode** 属性 `System.IO.DirectoryInfo` 是在 PowerShell FileSystem 提供程序中定义的代码属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-190">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-191">`<MemberSet>`：定义)  (属性和方法的成员的集合。</span><span class="sxs-lookup"><span data-stu-id="78d9d-191">`<MemberSet>`: Defines a collection of members (properties and methods).</span></span>

<span data-ttu-id="78d9d-192">`<MemberSet>`标记出现在主标记中 `<Members>` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-192">The `<MemberSet>` tags appear within the primary `<Members>` tags.</span></span> <span data-ttu-id="78d9d-193">标记必须围绕成员集的名称加上一个 `<Name>` 标记，并在 `<Members>` 集合中包含成员 (属性和方法) 的辅助标记。</span><span class="sxs-lookup"><span data-stu-id="78d9d-193">The tags must enclose a `<Name>` tag surrounding the name of the member set and a secondary `<Members>` tag that surround the members (properties and methods) in the set.</span></span> <span data-ttu-id="78d9d-194">创建属性 (的任何标记（如 `<NoteProperty>` 或 `<ScriptProperty>`) 或 (如或) 的方法） `<Method>` `<ScriptMethod>` 都可以是集的成员。</span><span class="sxs-lookup"><span data-stu-id="78d9d-194">Any of the tags that create a property (such as `<NoteProperty>` or `<ScriptProperty>`) or a method (such as `<Method>` or `<ScriptMethod>`) can be members of the set.</span></span>

<span data-ttu-id="78d9d-195">在 `Types.ps1xml` 文件中， `<MemberSet>` 标记用于在 PowerShell 中定义 .net 对象的默认视图。</span><span class="sxs-lookup"><span data-stu-id="78d9d-195">In `Types.ps1xml` files, the `<MemberSet>` tag is used to define the default views of the .NET objects in PowerShell.</span></span> <span data-ttu-id="78d9d-196">在这种情况下，成员集的名称 (标记) 内的值 `<Name>` 始终是 **PsStandardMembers** 的，并且 () 标记值的属性的名称 `<Name>` 是以下值之一：</span><span class="sxs-lookup"><span data-stu-id="78d9d-196">In this case, the name of the member set (the value within the `<Name>` tags) is always **PsStandardMembers** , and the names of the properties (the value of the `<Name>` tag) are one of the following:</span></span>

- <span data-ttu-id="78d9d-197">`DefaultDisplayProperty`：对象的单个属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-197">`DefaultDisplayProperty`: A single property of an object.</span></span>

- <span data-ttu-id="78d9d-198">`DefaultDisplayPropertySet`：对象的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-198">`DefaultDisplayPropertySet`: One or more properties of an object.</span></span>

- <span data-ttu-id="78d9d-199">`DefaultKeyPropertySet`：对象的一个或多个键属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-199">`DefaultKeyPropertySet`: One or more key properties of an object.</span></span> <span data-ttu-id="78d9d-200">键属性标识属性值的实例，如会话历史记录中项目的 ID。</span><span class="sxs-lookup"><span data-stu-id="78d9d-200">A key property identifies instances of property values, such as the ID number of items in a session history.</span></span>

<span data-ttu-id="78d9d-201">例如，下面的 XML 定义了服务的默认显示 (`System.ServiceProcess.ServiceController` 对象) 由 `Get-Service` cmdlet 返回。</span><span class="sxs-lookup"><span data-stu-id="78d9d-201">For example, the following XML defines the default display of services (`System.ServiceProcess.ServiceController` objects) that are returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="78d9d-202">它定义了一个名为 **PsStandardMembers** 的成员集，其中包含具有 **Status** 、 **Name** 和 **DisplayName** 属性的默认属性集。</span><span class="sxs-lookup"><span data-stu-id="78d9d-202">It defines a member set named **PsStandardMembers** that consists of a default property set with the **Status** , **Name** , and **DisplayName** properties.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-203">`<Method>`：引用基础对象的本机方法。</span><span class="sxs-lookup"><span data-stu-id="78d9d-203">`<Method>`: References a native method of the underlying object.</span></span>

<span data-ttu-id="78d9d-204">`<Methods>`：对象的方法的集合。</span><span class="sxs-lookup"><span data-stu-id="78d9d-204">`<Methods>`: A collection of the methods of the object.</span></span>

<span data-ttu-id="78d9d-205">`<NoteProperty>`：定义具有静态值的属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-205">`<NoteProperty>`: Defines a property with a static value.</span></span>

<span data-ttu-id="78d9d-206">`<NoteProperty>`标记必须有一个 `<Name>` 标记，该标记指定新属性的名称和 `<Value>` 指定属性值的标记。</span><span class="sxs-lookup"><span data-stu-id="78d9d-206">The `<NoteProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<Value>` tag that specifies the value of the property.</span></span>

<span data-ttu-id="78d9d-207">例如，以下 XML 将为 **DirectoryInfo** 对象创建 **Status** 属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-207">For example, the following XML creates a **Status** property for **System.IO.DirectoryInfo** objects.</span></span> <span data-ttu-id="78d9d-208">**Status** 属性的值始终为 **Success** 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-208">The value of the **Status** property is always **Success** .</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-209">`<ParameterizedProperty>`：采用参数并返回值的属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-209">`<ParameterizedProperty>`: Properties that take arguments and return a value.</span></span>

<span data-ttu-id="78d9d-210">`<Properties>`：对象的属性的集合。</span><span class="sxs-lookup"><span data-stu-id="78d9d-210">`<Properties>`: A collection of the properties of the object.</span></span>

<span data-ttu-id="78d9d-211">`<Property>`：基对象的一个属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-211">`<Property>`: A property of the base object.</span></span>

<span data-ttu-id="78d9d-212">`<PropertySet>`：定义对象的属性的集合。</span><span class="sxs-lookup"><span data-stu-id="78d9d-212">`<PropertySet>`: Defines a collection of properties of the object.</span></span>

<span data-ttu-id="78d9d-213">`<PropertySet>`标记必须有一个 `<Name>` 标记，该标记指定属性集的名称和 `<ReferencedProperty>` 指定属性的标记。</span><span class="sxs-lookup"><span data-stu-id="78d9d-213">The `<PropertySet>` tag must have a `<Name>` tag that specifies the name of the property set and a `<ReferencedProperty>` tag that specifies the properties.</span></span> <span data-ttu-id="78d9d-214">属性的名称括在 `<Name>` 标记中。</span><span class="sxs-lookup"><span data-stu-id="78d9d-214">The names of the properties are enclosed in `<Name>` tag.</span></span>

<span data-ttu-id="78d9d-215">在中 `Types.ps1xml` ， `<PropertySet>` 使用标记来定义对象默认显示的属性集。</span><span class="sxs-lookup"><span data-stu-id="78d9d-215">In `Types.ps1xml`, `<PropertySet>` tags are used to define sets of properties for the default display of an object.</span></span> <span data-ttu-id="78d9d-216">可以通过标记的标记中的值 **PsStandardMembers** 标识默认显示 `<Name>` `<MemberSet>` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-216">You can identify the default displays by the value **PsStandardMembers** in the `<Name>` tag of a `<MemberSet>` tag.</span></span>

<span data-ttu-id="78d9d-217">例如，下面的 XML 为对象创建了一个 **状态** 属性 `System.IO.DirectoryInfo` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-217">For example, the following XML creates a **Status** property for the `System.IO.DirectoryInfo` object.</span></span> <span data-ttu-id="78d9d-218">**Status** 属性的值始终为 **Success** 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-218">The value of the **Status** property is always **Success** .</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-219">`<ScriptMethod>`：定义一个方法，其值为脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="78d9d-219">`<ScriptMethod>`: Defines a method whose value is the output of a script.</span></span>

<span data-ttu-id="78d9d-220">`<ScriptMethod>`标记必须有一个 `<Name>` 标记，该标记指定新方法的名称，并具有一个标记，该标记包含 `<Script>` 返回方法结果的脚本块。</span><span class="sxs-lookup"><span data-stu-id="78d9d-220">The `<ScriptMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<Script>` tag that encloses the script block that returns the method result.</span></span>

<span data-ttu-id="78d9d-221">例如， `ConvertToDateTime` `ConvertFromDateTime` () 的管理对象的和方法 `System.System.Management.ManagementObject` 是使用 `ToDateTime` 类的和静态方法的脚本方法 `ToDmtfDateTime` `System.Management.ManagementDateTimeConverter` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-221">For example, the `ConvertToDateTime` and `ConvertFromDateTime` methods of management objects (`System.System.Management.ManagementObject`) are script methods that use the `ToDateTime` and `ToDmtfDateTime` static methods of the `System.Management.ManagementDateTimeConverter` class.</span></span>

```xml
<Type>
 <Name>System.Management.ManagementObject</Name>
 <Members>
 <ScriptMethod>
   <Name>ConvertToDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
   </Script>
 </ScriptMethod>
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

<span data-ttu-id="78d9d-222">`<ScriptProperty>`：定义一个属性，其值为脚本的输出。</span><span class="sxs-lookup"><span data-stu-id="78d9d-222">`<ScriptProperty>`: Defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="78d9d-223">`<ScriptProperty>`标记必须有一个 `<Name>` 标记，该标记指定新属性的名称，以及一个包含 `<GetScriptBlock>` 返回属性值的脚本块的标记。</span><span class="sxs-lookup"><span data-stu-id="78d9d-223">The `<ScriptProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetScriptBlock>` tag that encloses the script block that returns the property value.</span></span>

<span data-ttu-id="78d9d-224">例如， **FileInfo** 对象的 **VersionInfo** 属性是一个脚本属性，该属性是使用 **GetVersionInfo** 静态方法的 **FullName** 属性（ **FileVersionInfo** 对象）生成的。</span><span class="sxs-lookup"><span data-stu-id="78d9d-224">For example, the **VersionInfo** property of the **System.IO.FileInfo** object is a script property that results from using the **FullName** property of the **GetVersionInfo** static method of **System.Diagnostics.FileVersionInfo** objects.</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
      [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

<span data-ttu-id="78d9d-225">有关详细信息，请参阅 [Windows PowerShell 软件开发工具包 (SDK) ](/powershell/scripting/developer/windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="78d9d-225">For more information, see the [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span></span>

## <a name="update-typedata"></a><span data-ttu-id="78d9d-226">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="78d9d-226">Update-TypeData</span></span>

<span data-ttu-id="78d9d-227">若要将 `Types.ps1xml` 文件加载到 PowerShell 会话，请运行 `Update-TypeData` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78d9d-227">To load your `Types.ps1xml` files into a PowerShell session, run the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="78d9d-228">如果希望文件中的类型优先于内置文件中的类型 `Types.ps1xml` ，请添加的 **PrependData** 参数 `Update-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-228">If you want the types in your file to take precedence over types in the built-in `Types.ps1xml` file, add the **PrependData** parameter of `Update-TypeData`.</span></span> <span data-ttu-id="78d9d-229">`Update-TypeData` 仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="78d9d-229">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="78d9d-230">若要对所有未来的会话进行更改，请导出会话，或者将 `Update-TypeData` 命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="78d9d-230">To make the change to all future sessions, export the session, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

<span data-ttu-id="78d9d-231">在属性中发生的异常或通过将属性添加到 `Update-TypeData` 命令中时，不会将错误报告给 `StdErr` 。</span><span class="sxs-lookup"><span data-stu-id="78d9d-231">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors to `StdErr`.</span></span> <span data-ttu-id="78d9d-232">这是为了取消显示在格式设置和输出期间在许多常见类型中发生的异常。</span><span class="sxs-lookup"><span data-stu-id="78d9d-232">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="78d9d-233">如果你正在获取 .NET 属性，则可以通过使用方法语法来解决禁止显示异常的情况，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="78d9d-233">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

```powershell
"hello".get_Length()
```

<span data-ttu-id="78d9d-234">请注意，方法语法仅可用于 .NET 属性。</span><span class="sxs-lookup"><span data-stu-id="78d9d-234">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="78d9d-235">通过运行 cmdlet 添加的属性 `Update-TypeData` 不能使用方法语法。</span><span class="sxs-lookup"><span data-stu-id="78d9d-235">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

## <a name="signing-a-typesps1xml-file"></a><span data-ttu-id="78d9d-236">对 Types.ps1xml 文件进行签名</span><span class="sxs-lookup"><span data-stu-id="78d9d-236">Signing a Types.ps1xml file</span></span>

<span data-ttu-id="78d9d-237">若要保护文件的用户 `Types.ps1xml` ，可以使用数字签名对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="78d9d-237">To protect users of your `Types.ps1xml` file, you can sign the file using a digital signature.</span></span> <span data-ttu-id="78d9d-238">有关详细信息，请参阅 [about_Signing](about_Signing.md)。</span><span class="sxs-lookup"><span data-stu-id="78d9d-238">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="78d9d-239">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78d9d-239">See also</span></span>

[<span data-ttu-id="78d9d-240">about_Signing</span><span class="sxs-lookup"><span data-stu-id="78d9d-240">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="78d9d-241">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="78d9d-241">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)

[<span data-ttu-id="78d9d-242">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="78d9d-242">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[<span data-ttu-id="78d9d-243">Get-Member</span><span class="sxs-lookup"><span data-stu-id="78d9d-243">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="78d9d-244">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="78d9d-244">Get-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[<span data-ttu-id="78d9d-245">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="78d9d-245">Remove-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[<span data-ttu-id="78d9d-246">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="78d9d-246">Update-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Update-TypeData)

