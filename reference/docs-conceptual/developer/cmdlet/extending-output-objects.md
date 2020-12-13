---
ms.date: 09/13/2016
ms.topic: reference
title: 扩展输出对象
description: 扩展输出对象
ms.openlocfilehash: 9fea476e3032002bd206609313581cc6373dfddc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652900"
---
# <a name="extending-output-objects"></a><span data-ttu-id="f96a1-103">扩展输出对象</span><span class="sxs-lookup"><span data-stu-id="f96a1-103">Extending Output Objects</span></span>

<span data-ttu-id="f96a1-104">您可以通过使用类型文件 ( types.ps1xml) 扩展由 cmdlet、函数和脚本返回的 .NET Framework 对象。</span><span class="sxs-lookup"><span data-stu-id="f96a1-104">You can extend the .NET Framework objects that are returned by cmdlets, functions, and scripts by using types files (.ps1xml).</span></span> <span data-ttu-id="f96a1-105">类型文件是基于 XML 的文件，可用于向现有对象添加属性和方法。</span><span class="sxs-lookup"><span data-stu-id="f96a1-105">Types files are XML-based files that let you add properties and methods to existing objects.</span></span> <span data-ttu-id="f96a1-106">例如，Windows PowerShell 提供 Types.ps1xml 文件，该文件将元素添加到多个现有 .NET Framework 对象中。</span><span class="sxs-lookup"><span data-stu-id="f96a1-106">For example, Windows PowerShell provides the Types.ps1xml file, which adds elements to several existing .NET Framework objects.</span></span> <span data-ttu-id="f96a1-107">Types.ps1xml 文件位于 Windows PowerShell 安装目录中 (`$pshome`) 。</span><span class="sxs-lookup"><span data-stu-id="f96a1-107">The Types.ps1xml file is located in the Windows PowerShell installation directory (`$pshome`).</span></span> <span data-ttu-id="f96a1-108">您可以创建自己的类型文件，以便进一步扩展这些对象或扩展其他对象。</span><span class="sxs-lookup"><span data-stu-id="f96a1-108">You can create your own types file to further extend those objects or to extend other objects.</span></span> <span data-ttu-id="f96a1-109">使用类型文件扩展对象时，会使用新元素扩展对象的任何实例。</span><span class="sxs-lookup"><span data-stu-id="f96a1-109">When you extend an object by using a types file, any instance of the object is extended with the new elements.</span></span>

## <a name="extending-the-systemarray-object"></a><span data-ttu-id="f96a1-110">扩展 System.object 对象</span><span class="sxs-lookup"><span data-stu-id="f96a1-110">Extending the System.Array Object</span></span>

<span data-ttu-id="f96a1-111">下面的示例演示 Windows PowerShell 如何在 Types.ps1xml 文件中扩展 [system.object](/dotnet/api/System.Array) 对象。</span><span class="sxs-lookup"><span data-stu-id="f96a1-111">The following example shows how Windows PowerShell extends the [System.Array](/dotnet/api/System.Array) object in the Types.ps1xml file.</span></span> <span data-ttu-id="f96a1-112">默认情况下， [system.object](/dotnet/api/System.Array) 对象具有 `Length` 属性，该属性列出数组中对象的数量。</span><span class="sxs-lookup"><span data-stu-id="f96a1-112">By default, [System.Array](/dotnet/api/System.Array) objects have a `Length` property that lists the number of objects in the array.</span></span> <span data-ttu-id="f96a1-113">但是，由于名称 "length" 未清楚地描述属性，因此 Windows PowerShell 将添加 `Count` alias 属性，该属性显示与属性相同的值 `Length` 。</span><span class="sxs-lookup"><span data-stu-id="f96a1-113">However, because the name "length" does not clearly describe the property, Windows PowerShell adds the `Count` alias property, which displays the same value as the `Length` property.</span></span> <span data-ttu-id="f96a1-114">下面的 XML 将 `Count` 属性添加到 [系统数组](/dotnet/api/System.Array) 类型。</span><span class="sxs-lookup"><span data-stu-id="f96a1-114">The following XML adds the `Count` property to the [System.Array](/dotnet/api/System.Array) type.</span></span>

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

<span data-ttu-id="f96a1-115">若要查看此新的别名属性，请在任何数组上使用 [Get 成员](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) 命令，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f96a1-115">To see this new alias property, use a [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="f96a1-116">该命令将返回以下结果。</span><span class="sxs-lookup"><span data-stu-id="f96a1-116">The command returns the following results.</span></span>

```output
Name           MemberType    Definition
----           ----------    ----------
Count          AliasProperty Count = Length
Address        Method        System.Object& Address(Int32 )
Clone          Method        System.Object Clone()
CopyTo         Method        System.Void CopyTo(Array array, Int32 index):
Equals         Method        System.Boolean Equals(Object obj)
Get            Method        System.Object Get(Int32 )
...
Length         Property      System.Int32 Length {get;}
```

<span data-ttu-id="f96a1-117">您可以使用 `Count` 属性或 `Length` 属性来确定数组中有多少个对象。</span><span class="sxs-lookup"><span data-stu-id="f96a1-117">You can use either the `Count` property or the `Length` property to determine how many objects are in an array.</span></span> <span data-ttu-id="f96a1-118">例如：</span><span class="sxs-lookup"><span data-stu-id="f96a1-118">For example:</span></span>

```powershell
PS> (1, 2, 3, 4).Count
```

```output
4
```

```powershell
PS> (1, 2, 3, 4).Length
```

```output
4
```

## <a name="custom-types-files"></a><span data-ttu-id="f96a1-119">自定义类型文件</span><span class="sxs-lookup"><span data-stu-id="f96a1-119">Custom Types Files</span></span>

<span data-ttu-id="f96a1-120">若要创建自定义类型文件，请首先复制现有的类型文件。</span><span class="sxs-lookup"><span data-stu-id="f96a1-120">To create a custom types file, start by copying an existing types file.</span></span> <span data-ttu-id="f96a1-121">新文件可以具有任何名称，但它必须具有 types.ps1xml 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="f96a1-121">The new file can have any name, but it must have a .ps1xml file name extension.</span></span> <span data-ttu-id="f96a1-122">复制文件时，您可以将新文件放置在可供 Windows PowerShell 访问的任何目录中，但将文件放在 Windows PowerShell 安装目录中 (`$pshome`) 或安装目录的子目录中都很有用。</span><span class="sxs-lookup"><span data-stu-id="f96a1-122">When you copy the file, you can place the new file in any directory that is accessible to Windows PowerShell, but it is useful to place the files in the Windows PowerShell installation directory (`$pshome`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="f96a1-123">若要将自己的扩展类型添加到文件中，请为要扩展的每个对象添加类型元素。</span><span class="sxs-lookup"><span data-stu-id="f96a1-123">To add your own extended types to the file, add a types element for each object that you want to extend.</span></span> <span data-ttu-id="f96a1-124">以下主题提供了示例。</span><span class="sxs-lookup"><span data-stu-id="f96a1-124">The following topics provide examples.</span></span>

- <span data-ttu-id="f96a1-125">有关添加属性和属性集的详细信息，请参阅 [扩展属性](./extending-properties-for-objects.md)</span><span class="sxs-lookup"><span data-stu-id="f96a1-125">For more information about adding properties and property sets, see [Extended Properties](./extending-properties-for-objects.md)</span></span>

- <span data-ttu-id="f96a1-126">有关添加方法的详细信息，请参阅 [扩展方法](./defining-default-methods-for-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a1-126">For more information about adding methods, see [Extended Methods](./defining-default-methods-for-objects.md).</span></span>

- <span data-ttu-id="f96a1-127">有关添加成员集的详细信息，请参阅 [扩展成员集](./defining-default-member-sets-for-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a1-127">For more information about adding member sets, see [Extended Member Sets](./defining-default-member-sets-for-objects.md).</span></span>

<span data-ttu-id="f96a1-128">定义自己的扩展类型后，请使用以下方法之一来使扩展对象可用：</span><span class="sxs-lookup"><span data-stu-id="f96a1-128">After you define your own extended types, use one of the following methods to make your extended objects available:</span></span>

- <span data-ttu-id="f96a1-129">若要使扩展类型文件可用于当前会话，请使用 [update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet 添加新的文件。</span><span class="sxs-lookup"><span data-stu-id="f96a1-129">To make your extended types file available to the current session, use the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet to add the new file.</span></span> <span data-ttu-id="f96a1-130">如果你希望你的类型优先于其他类型文件中定义的类型 (包括 Types.ps1xml 文件) ，请使用 `PrependData` [update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet 的参数。</span><span class="sxs-lookup"><span data-stu-id="f96a1-130">If you want your types to take precedence over the types that are defined in other types files (including the Types.ps1xml file), use the `PrependData` parameter of the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet.</span></span>
- <span data-ttu-id="f96a1-131">若要使扩展类型文件可供所有未来会话使用，请将类型文件添加到模块，导出当前会话，或将 [update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) 命令添加到 Windows PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="f96a1-131">To make your extended types file available to all future sessions, add the types file to a module, export the current session, or add the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) command to your Windows PowerShell profile.</span></span>

## <a name="signing-types-files"></a><span data-ttu-id="f96a1-132">签名类型文件</span><span class="sxs-lookup"><span data-stu-id="f96a1-132">Signing Types Files</span></span>

<span data-ttu-id="f96a1-133">应对类型文件进行数字签名以防止篡改，因为 XML 可以包含脚本块。</span><span class="sxs-lookup"><span data-stu-id="f96a1-133">Types files should be digitally signed to prevent tampering because the XML can include script blocks.</span></span> <span data-ttu-id="f96a1-134">有关添加数字签名的详细信息，请参阅 [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span><span class="sxs-lookup"><span data-stu-id="f96a1-134">For more information about adding digital signatures, see [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span></span>

## <a name="see-also"></a><span data-ttu-id="f96a1-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f96a1-135">See Also</span></span>

[<span data-ttu-id="f96a1-136">定义对象的默认属性</span><span class="sxs-lookup"><span data-stu-id="f96a1-136">Defining Default Properties for Objects</span></span>](./extending-properties-for-objects.md)

[<span data-ttu-id="f96a1-137">定义对象的默认方法</span><span class="sxs-lookup"><span data-stu-id="f96a1-137">Defining Default Methods for Objects</span></span>](./defining-default-methods-for-objects.md)

[<span data-ttu-id="f96a1-138">定义对象的默认成员集</span><span class="sxs-lookup"><span data-stu-id="f96a1-138">Defining Default Member Sets for Objects</span></span>](./defining-default-member-sets-for-objects.md)

[<span data-ttu-id="f96a1-139">编写 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f96a1-139">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
