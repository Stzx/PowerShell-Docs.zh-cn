---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 4/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: cbac0c87ea58acc198fcf981edfd934679e4b3cf
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198648"
---
# <span data-ttu-id="4d851-103">Add-Member</span><span class="sxs-lookup"><span data-stu-id="4d851-103">Add-Member</span></span>

## <span data-ttu-id="4d851-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4d851-104">SYNOPSIS</span></span>
<span data-ttu-id="4d851-105">将自定义属性和方法添加到 PowerShell 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="4d851-105">Adds custom properties and methods to an instance of a PowerShell object.</span></span>

## <span data-ttu-id="4d851-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4d851-106">SYNTAX</span></span>

### <span data-ttu-id="4d851-107">TypeNameSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="4d851-107">TypeNameSet (Default)</span></span>

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="4d851-108">NotePropertyMultiMemberSet</span><span class="sxs-lookup"><span data-stu-id="4d851-108">NotePropertyMultiMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### <span data-ttu-id="4d851-109">NotePropertySingleMemberSet</span><span class="sxs-lookup"><span data-stu-id="4d851-109">NotePropertySingleMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### <span data-ttu-id="4d851-110">集</span><span class="sxs-lookup"><span data-stu-id="4d851-110">MemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="4d851-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4d851-111">DESCRIPTION</span></span>

<span data-ttu-id="4d851-112">`Add-Member`Cmdlet 允许你向 PowerShell 对象的实例 (属性和方法) 添加成员。</span><span class="sxs-lookup"><span data-stu-id="4d851-112">The `Add-Member` cmdlet lets you add members (properties and methods) to an instance of a PowerShell object.</span></span> <span data-ttu-id="4d851-113">例如，可以添加包含对象说明的 NoteProperty 成员或运行脚本的 **ScriptMethod** 成员，以更改对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-113">For instance, you can add a NoteProperty member that contains a description of the object or a **ScriptMethod** member that runs a script to change the object.</span></span>

<span data-ttu-id="4d851-114">若要使用 `Add-Member` ，请将对象传递给 `Add-Member` ，或使用 **InputObject** 参数来指定对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-114">To use `Add-Member`, pipe the object to `Add-Member`, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="4d851-115">**MemberType** 参数指示要添加的成员的类型。</span><span class="sxs-lookup"><span data-stu-id="4d851-115">The **MemberType** parameter indicates the type of member that you want to add.</span></span> <span data-ttu-id="4d851-116">**Name** 参数将名称分配给新成员， **值** 参数设置成员的值。</span><span class="sxs-lookup"><span data-stu-id="4d851-116">The **Name** parameter assigns a name to the new member, and the **Value** parameter sets the value of the member.</span></span>

<span data-ttu-id="4d851-117">你添加的属性和方法只会添加到你指定的对象的特定实例中。</span><span class="sxs-lookup"><span data-stu-id="4d851-117">The properties and methods that you add are added only to the particular instance of the object that you specify.</span></span> <span data-ttu-id="4d851-118">`Add-Member` 不会更改对象类型。</span><span class="sxs-lookup"><span data-stu-id="4d851-118">`Add-Member` does not change the object type.</span></span> <span data-ttu-id="4d851-119">若要创建新的对象类型，请使用 `Add-Type` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4d851-119">To create a new object type, use the `Add-Type` cmdlet.</span></span>

<span data-ttu-id="4d851-120">你还可以使用 `Export-Clixml` cmdlet 在文件中保存对象的实例，包括其他成员。</span><span class="sxs-lookup"><span data-stu-id="4d851-120">You can also use the `Export-Clixml` cmdlet to save the instance of the object, including the additional members, in a file.</span></span> <span data-ttu-id="4d851-121">然后，可以使用 `Import-Clixml` cmdlet 从导出文件中存储的信息重新创建对象的实例。</span><span class="sxs-lookup"><span data-stu-id="4d851-121">Then you can use the `Import-Clixml` cmdlet to re-create the instance of the object from the information that is stored in the exported file.</span></span>

<span data-ttu-id="4d851-122">从 Windows PowerShell 3.0 开始， `Add-Member` 具有新功能，使你可以更轻松地向对象添加注释属性。</span><span class="sxs-lookup"><span data-stu-id="4d851-122">Beginning in Windows PowerShell 3.0, `Add-Member` has new features that make it easier to add note properties to objects.</span></span>
<span data-ttu-id="4d851-123">可以使用 **NotePropertyName** 和 **NotePropertyValue** 参数定义附注属性，或使用 **NotePropertyMembers** 参数，该参数采用包含附注属性名称和值的哈希表。</span><span class="sxs-lookup"><span data-stu-id="4d851-123">You can use the **NotePropertyName** and **NotePropertyValue** parameters to define a note property or use the **NotePropertyMembers** parameter, which takes a hash table of note property names and values.</span></span>

<span data-ttu-id="4d851-124">此外，从 Windows PowerShell 3.0 开始，将很少需要使用用于生成输出对象的 **PassThru** 参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-124">Also, beginning in Windows PowerShell 3.0, the **PassThru** parameter, which generates an output object, is needed less frequently.</span></span> <span data-ttu-id="4d851-125">`Add-Member` 现在将新成员直接添加到更多类型的输入对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-125">`Add-Member` now adds the new members directly to the input object of more types.</span></span> <span data-ttu-id="4d851-126">有关详细信息，请参阅 **PassThru** 参数说明。</span><span class="sxs-lookup"><span data-stu-id="4d851-126">For more information, see the **PassThru** parameter description.</span></span>

## <span data-ttu-id="4d851-127">示例</span><span class="sxs-lookup"><span data-stu-id="4d851-127">EXAMPLES</span></span>

### <span data-ttu-id="4d851-128">示例1：向 PSObject 添加注释属性</span><span class="sxs-lookup"><span data-stu-id="4d851-128">Example 1: Add a note property to a PSObject</span></span>

<span data-ttu-id="4d851-129">下面的示例将值为 "Done" 的 **状态** 注释属性添加到表示该文件的 **FileInfo** 对象 `Test.txt` 。</span><span class="sxs-lookup"><span data-stu-id="4d851-129">The following example adds a **Status** note property with a value of "Done" to the **FileInfo** object that represents the `Test.txt` file.</span></span>

<span data-ttu-id="4d851-130">第一个命令使用 `Get-ChildItem` cmdlet 来获取表示该文件的 **FileInfo** 对象 `Test.txt` 。</span><span class="sxs-lookup"><span data-stu-id="4d851-130">The first command uses the `Get-ChildItem` cmdlet to get a **FileInfo** object representing the `Test.txt` file.</span></span> <span data-ttu-id="4d851-131">它将其保存在 `$a` 变量中。</span><span class="sxs-lookup"><span data-stu-id="4d851-131">It saves it in the `$a` variable.</span></span>

<span data-ttu-id="4d851-132">第二个命令将 note 属性添加到中的对象 `$a` 。</span><span class="sxs-lookup"><span data-stu-id="4d851-132">The second command adds the note property to the object in `$a`.</span></span>

<span data-ttu-id="4d851-133">第三个命令使用点表示法来获取中对象的 **Status** 属性的值 `$a` 。</span><span class="sxs-lookup"><span data-stu-id="4d851-133">The third command uses dot notation to get the value of the **Status** property of the object in `$a`.</span></span> <span data-ttu-id="4d851-134">如输出所示，值为 "Done"。</span><span class="sxs-lookup"><span data-stu-id="4d851-134">As the output shows, the value is "Done".</span></span>

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### <span data-ttu-id="4d851-135">示例2：向 PSObject 添加 alias 属性</span><span class="sxs-lookup"><span data-stu-id="4d851-135">Example 2: Add an alias property to a PSObject</span></span>

<span data-ttu-id="4d851-136">下面的示例将一个 **Size** alias 属性添加到表示该文件的对象 `Test.txt` 。</span><span class="sxs-lookup"><span data-stu-id="4d851-136">The following example adds a **Size** alias property to the object that represents the `Test.txt` file.</span></span> <span data-ttu-id="4d851-137">新属性是 **Length** 属性的别名。</span><span class="sxs-lookup"><span data-stu-id="4d851-137">The new property is an alias for the **Length** property.</span></span>

<span data-ttu-id="4d851-138">第一个命令使用 `Get-ChildItem` cmdlet 来获取 `Test.txt` **FileInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-138">The first command uses the `Get-ChildItem` cmdlet to get the `Test.txt` **FileInfo** object.</span></span>

<span data-ttu-id="4d851-139">第二个命令添加 **Size** alias 属性。</span><span class="sxs-lookup"><span data-stu-id="4d851-139">The second command adds the **Size** alias property.</span></span>
<span data-ttu-id="4d851-140">第三个命令使用点表示法来获取新的 **Size** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="4d851-140">The third command uses dot notation to get the value of the new **Size** property.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### <span data-ttu-id="4d851-141">示例3：向字符串添加 StringUse 注释属性</span><span class="sxs-lookup"><span data-stu-id="4d851-141">Example 3: Add a StringUse note property to a string</span></span>

<span data-ttu-id="4d851-142">此示例将 **StringUse** note 属性添加到字符串。</span><span class="sxs-lookup"><span data-stu-id="4d851-142">This example adds the **StringUse** note property to a string.</span></span>
<span data-ttu-id="4d851-143">由于 `Add-Member` 无法将类型添加到 **字符串** 输入对象，因此可以指定 **PassThru** 参数来生成输出对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-143">Because `Add-Member` cannot add types to **String** input objects, you can specify the **PassThru** parameter to generate an output object.</span></span> <span data-ttu-id="4d851-144">示例中的最后一个命令将显示新属性。</span><span class="sxs-lookup"><span data-stu-id="4d851-144">The last command in the example displays the new property.</span></span>

<span data-ttu-id="4d851-145">此示例使用 **NotePropertyMembers** 参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-145">This example uses the **NotePropertyMembers** parameter.</span></span> <span data-ttu-id="4d851-146">**NotePropertyMembers** 参数的值是一个哈希表。</span><span class="sxs-lookup"><span data-stu-id="4d851-146">The value of the **NotePropertyMembers** parameter is a hash table.</span></span> <span data-ttu-id="4d851-147">键为便笺属性名称 **StringUse** ，值为 "注释" 属性值 " **显示** "。</span><span class="sxs-lookup"><span data-stu-id="4d851-147">The key is the note property name, **StringUse** , and the value is the note property value, **Display** .</span></span>

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### <span data-ttu-id="4d851-148">示例4：将脚本方法添加到 FileInfo 对象</span><span class="sxs-lookup"><span data-stu-id="4d851-148">Example 4: Add a script method to a FileInfo object</span></span>

<span data-ttu-id="4d851-149">此示例将 **SizeInMB** 脚本方法添加到 **FileInfo** 对象，该对象将文件大小计算为最接近的兆字节。</span><span class="sxs-lookup"><span data-stu-id="4d851-149">This example adds the **SizeInMB** script method to a **FileInfo** object which calculates the file size to the nearest MegaByte.</span></span> <span data-ttu-id="4d851-150">第二个命令创建一个 **ScriptBlock** ，该 ScriptBlock 使用类型中的 **循环** 静态方法将 `[math]` 文件大小舍入到第二个小数位。</span><span class="sxs-lookup"><span data-stu-id="4d851-150">The second command creates a **ScriptBlock** that uses the **Round** static method from the `[math]` type to round the file size to the second decimal place.</span></span>

<span data-ttu-id="4d851-151">**Value** 参数还使用 `$This` 自动变量，它表示当前的对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-151">The **Value** parameter also uses the `$This` automatic variable, which represents the current object.</span></span> <span data-ttu-id="4d851-152">`$This`变量仅在定义新属性和方法的脚本块中有效。</span><span class="sxs-lookup"><span data-stu-id="4d851-152">The `$This` variable is valid only in script blocks that define new properties and methods.</span></span>

<span data-ttu-id="4d851-153">最后一个命令使用点表示法对变量中的对象调用新的 **SizeInMB** 脚本方法 `$A` 。</span><span class="sxs-lookup"><span data-stu-id="4d851-153">The last command uses dot notation to call the new **SizeInMB** script method on the object in the `$A` variable.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### <span data-ttu-id="4d851-154">示例5：将对象的所有属性复制到另一个</span><span class="sxs-lookup"><span data-stu-id="4d851-154">Example 5: Copy all properties of an object to another</span></span>

<span data-ttu-id="4d851-155">此函数将一个对象的所有属性复制到另一个对象中。</span><span class="sxs-lookup"><span data-stu-id="4d851-155">This function copies all of the properties of one object to another object.</span></span>

<span data-ttu-id="4d851-156">`foreach`循环使用 `Get-Member` cmdlet **从** 对象获取的每个属性。</span><span class="sxs-lookup"><span data-stu-id="4d851-156">The `foreach` loop uses the `Get-Member` cmdlet to get each of the properties of the **From** object.</span></span> <span data-ttu-id="4d851-157">循环内的命令 `foreach` 在每个属性上以序列的顺序执行。</span><span class="sxs-lookup"><span data-stu-id="4d851-157">The commands within the `foreach` loop are performed in series on each of the properties.</span></span>

<span data-ttu-id="4d851-158">`Add-Member`命令将 **从** 对象的属性作为 **NoteProperty** 添加到对象 **To** 。</span><span class="sxs-lookup"><span data-stu-id="4d851-158">The `Add-Member` command adds the property of the **From** object to the **To** object as a **NoteProperty** .</span></span> <span data-ttu-id="4d851-159">使用 **value** 参数复制值。</span><span class="sxs-lookup"><span data-stu-id="4d851-159">The value is copied using the **Value** parameter.</span></span> <span data-ttu-id="4d851-160">它使用 **Force** 参数添加具有相同成员名称的成员。</span><span class="sxs-lookup"><span data-stu-id="4d851-160">It uses the **Force** parameter to add members with the same member name.</span></span>

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### <span data-ttu-id="4d851-161">示例6：创建自定义对象</span><span class="sxs-lookup"><span data-stu-id="4d851-161">Example 6: Create a custom object</span></span>

<span data-ttu-id="4d851-162">此示例将创建一个 **资产** 自定义对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-162">This example creates an **Asset** custom object.</span></span>

<span data-ttu-id="4d851-163">`New-Object`Cmdlet 将创建 **PSObject** 。</span><span class="sxs-lookup"><span data-stu-id="4d851-163">The `New-Object` cmdlet creates a **PSObject** .</span></span> <span data-ttu-id="4d851-164">该示例将 **PSObject** 保存在 `$Asset` 变量中。</span><span class="sxs-lookup"><span data-stu-id="4d851-164">The example saves the **PSObject** in the `$Asset` variable.</span></span>

<span data-ttu-id="4d851-165">第二个命令使用 `[ordered]` 类型加速器创建名称和值的有序字典。</span><span class="sxs-lookup"><span data-stu-id="4d851-165">The second command uses the `[ordered]` type accelerator to create an ordered dictionary of names and values.</span></span> <span data-ttu-id="4d851-166">该命令将结果保存在 `$D` 变量中。</span><span class="sxs-lookup"><span data-stu-id="4d851-166">The command saves the result in the `$D` variable.</span></span>

<span data-ttu-id="4d851-167">第三个命令使用 cmdlet 的 **NotePropertyMembers** 参数 `Add-Member` 将变量中的字典添加 `$D` 到 **PSObject** 。</span><span class="sxs-lookup"><span data-stu-id="4d851-167">The third command uses the **NotePropertyMembers** parameter of the `Add-Member` cmdlet to add the dictionary in the `$D` variable to the **PSObject** .</span></span>
<span data-ttu-id="4d851-168">**TypeName** 属性将新名称、 **资产** 分配给 **PSObject** 。</span><span class="sxs-lookup"><span data-stu-id="4d851-168">The **TypeName** property assigns a new name, **Asset** , to the **PSObject** .</span></span>

<span data-ttu-id="4d851-169">最后一个命令通过管道将新的 **资产** 对象传递给 `Get-Member` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4d851-169">The last command pipes the new **Asset** object to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="4d851-170">该输出显示该对象具有类型名称 " **资产** " 和在 "排序字典" 中定义的附注属性。</span><span class="sxs-lookup"><span data-stu-id="4d851-170">The output shows that the object has a type name of **Asset** and the note properties that we defined in the ordered dictionary.</span></span>

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## <span data-ttu-id="4d851-171">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4d851-171">PARAMETERS</span></span>

### <span data-ttu-id="4d851-172">-Force</span><span class="sxs-lookup"><span data-stu-id="4d851-172">-Force</span></span>

<span data-ttu-id="4d851-173">指示此 cmdlet 添加新成员，即使该对象具有同名的自定义成员。</span><span class="sxs-lookup"><span data-stu-id="4d851-173">Indicates that this cmdlet adds a new member even the object has a custom member with the same name.</span></span>
<span data-ttu-id="4d851-174">不能使用 **Force** 参数来替换类型的标准成员。</span><span class="sxs-lookup"><span data-stu-id="4d851-174">You cannot use the **Force** parameter to replace a standard member of a type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-175">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4d851-175">-InputObject</span></span>

<span data-ttu-id="4d851-176">指定要向其添加新成员的对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-176">Specifies the object to which the new member is added.</span></span>
<span data-ttu-id="4d851-177">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="4d851-177">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-178">-MemberType</span><span class="sxs-lookup"><span data-stu-id="4d851-178">-MemberType</span></span>

<span data-ttu-id="4d851-179">指定要添加的成员的类型。</span><span class="sxs-lookup"><span data-stu-id="4d851-179">Specifies the type of the member to add.</span></span>
<span data-ttu-id="4d851-180">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="4d851-180">This parameter is required.</span></span>
<span data-ttu-id="4d851-181">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="4d851-181">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4d851-182">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="4d851-182">NoteProperty</span></span>
- <span data-ttu-id="4d851-183">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="4d851-183">AliasProperty</span></span>
- <span data-ttu-id="4d851-184">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="4d851-184">ScriptProperty</span></span>
- <span data-ttu-id="4d851-185">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="4d851-185">CodeProperty</span></span>
- <span data-ttu-id="4d851-186">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="4d851-186">ScriptMethod</span></span>
- <span data-ttu-id="4d851-187">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="4d851-187">CodeMethod</span></span>

<span data-ttu-id="4d851-188">有关这些值的信息，请参阅 MSDN 库中的 [PSMemberTypes 枚举](/dotnet/api/system.management.automation.psmembertypes) 。</span><span class="sxs-lookup"><span data-stu-id="4d851-188">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes) in the MSDN library.</span></span>

<span data-ttu-id="4d851-189">并非所有对象都具有每种类型的成员。</span><span class="sxs-lookup"><span data-stu-id="4d851-189">Not all objects have every type of member.</span></span>
<span data-ttu-id="4d851-190">如果指定了对象不具有的成员类型，则 PowerShell 将返回错误。</span><span class="sxs-lookup"><span data-stu-id="4d851-190">If you specify a member type that the object does not have, PowerShell returns an error.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-191">-Name</span><span class="sxs-lookup"><span data-stu-id="4d851-191">-Name</span></span>

<span data-ttu-id="4d851-192">指定此 cmdlet 添加的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="4d851-192">Specifies the name of the member that this cmdlet adds.</span></span>

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-193">-NotePropertyMembers</span><span class="sxs-lookup"><span data-stu-id="4d851-193">-NotePropertyMembers</span></span>

<span data-ttu-id="4d851-194">指定附注属性名称和值的哈希表或有序字典。</span><span class="sxs-lookup"><span data-stu-id="4d851-194">Specifies a hash table or ordered dictionary of note property names and values.</span></span>
<span data-ttu-id="4d851-195">键入哈希表或字典，其中的键为附注属性名称，值为附注属性值。</span><span class="sxs-lookup"><span data-stu-id="4d851-195">Type a hash table or dictionary in which the keys are note property names and the values are note property values.</span></span>

<span data-ttu-id="4d851-196">有关 PowerShell 中的哈希表和有序字典的详细信息，请参阅 [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)。</span><span class="sxs-lookup"><span data-stu-id="4d851-196">For more information about hash tables and ordered dictionaries in PowerShell, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="4d851-197">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-197">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-198">-NotePropertyName</span><span class="sxs-lookup"><span data-stu-id="4d851-198">-NotePropertyName</span></span>

<span data-ttu-id="4d851-199">指定便笺属性名称。</span><span class="sxs-lookup"><span data-stu-id="4d851-199">Specifies the note property name.</span></span>

<span data-ttu-id="4d851-200">将此参数与 **NotePropertyValue** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="4d851-200">Use this parameter with the **NotePropertyValue** parameter.</span></span>
<span data-ttu-id="4d851-201">此参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d851-201">This parameter is optional.</span></span>

<span data-ttu-id="4d851-202">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-203">-NotePropertyValue</span><span class="sxs-lookup"><span data-stu-id="4d851-203">-NotePropertyValue</span></span>

<span data-ttu-id="4d851-204">指定 note 属性值。</span><span class="sxs-lookup"><span data-stu-id="4d851-204">Specifies the note property value.</span></span>

<span data-ttu-id="4d851-205">将此参数与 **NotePropertyName** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="4d851-205">Use this parameter with the **NotePropertyName** parameter.</span></span>
<span data-ttu-id="4d851-206">此参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d851-206">This parameter is optional.</span></span>

<span data-ttu-id="4d851-207">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-208">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4d851-208">-PassThru</span></span>

<span data-ttu-id="4d851-209">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-209">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="4d851-210">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="4d851-210">By default, this cmdlet does not generate any output.</span></span>

<span data-ttu-id="4d851-211">对于大多数对象，会 `Add-Member` 将新成员添加到输入对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-211">For most objects, `Add-Member` adds the new members to the input object.</span></span>
<span data-ttu-id="4d851-212">但是，当输入对象是一个字符串时， `Add-Member` 不能将该成员添加到 input 对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-212">However, when the input object is a string, `Add-Member` cannot add the member to the input object.</span></span>
<span data-ttu-id="4d851-213">对于这些对象，请使用 **PassThru** 参数来创建输出对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-213">For these objects, use the **PassThru** parameter to create an output object.</span></span>

<span data-ttu-id="4d851-214">在 Windows PowerShell 2.0 中， `Add-Member` 只将成员添加到了对象的 **PSObject** 包装，而不是添加到对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-214">In Windows PowerShell 2.0, `Add-Member` added members only to the **PSObject** wrapper of objects, not to the object.</span></span>
<span data-ttu-id="4d851-215">使用 **PassThru** 参数为具有 **PSObject** 包装器的任何对象创建输出对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-215">Use the **PassThru** parameter to create an output object for any object that has a **PSObject** wrapper.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-216">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="4d851-216">-SecondValue</span></span>

<span data-ttu-id="4d851-217">指定有关 **AliasProperty** 、 **ScriptProperty** 、 **CodeProperty** 或 **CodeMethod** 成员的可选附加信息。</span><span class="sxs-lookup"><span data-stu-id="4d851-217">Specifies optional additional information about **AliasProperty** , **ScriptProperty** , **CodeProperty** , or **CodeMethod** members.</span></span>

<span data-ttu-id="4d851-218">如果在添加 **AliasProperty** 时使用此参数，则此参数必须为数据类型。</span><span class="sxs-lookup"><span data-stu-id="4d851-218">If used when adding an **AliasProperty** , this parameter must be a data type.</span></span>
<span data-ttu-id="4d851-219">到指定数据类型的转换将添加到 **AliasProperty** 的值中。</span><span class="sxs-lookup"><span data-stu-id="4d851-219">A conversion to the specified data type is added to the value of the **AliasProperty** .</span></span>

<span data-ttu-id="4d851-220">例如，如果添加了为字符串属性提供备用名称的 **AliasProperty** ，则还可以指定 **SecondValue** 参数，以指示在使用相应的 **AliasProperty** 进行访问时，应将该字符串属性的值转换为 **整数。**</span><span class="sxs-lookup"><span data-stu-id="4d851-220">For example, if you add an **AliasProperty** that provides an alternate name for a string property, you can also specify a **SecondValue** parameter of **System.Int32** to indicate that the value of that string property should be converted to an integer when accessed by using the corresponding **AliasProperty** .</span></span>

<span data-ttu-id="4d851-221">添加 **ScriptProperty** 成员时，可以使用 **SecondValue** 参数来指定其他 **ScriptBlock** 。</span><span class="sxs-lookup"><span data-stu-id="4d851-221">You can use the **SecondValue** parameter to specify an additional **ScriptBlock** when adding a **ScriptProperty** member.</span></span> <span data-ttu-id="4d851-222">在 **Value** 参数中指定的第一个 **ScriptBlock** 用于获取变量的值。</span><span class="sxs-lookup"><span data-stu-id="4d851-222">The first **ScriptBlock** , specified in the **Value** parameter, is used to get the value of a variable.</span></span> <span data-ttu-id="4d851-223">在 **SecondValue** 参数中指定的第二个 **ScriptBlock** 用于设置变量的值。</span><span class="sxs-lookup"><span data-stu-id="4d851-223">The second **ScriptBlock** , specified in the **SecondValue** parameter, is used to set the value of a variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-224">-Value</span><span class="sxs-lookup"><span data-stu-id="4d851-224">-Value</span></span>

<span data-ttu-id="4d851-225">指定已添加成员的初始值。</span><span class="sxs-lookup"><span data-stu-id="4d851-225">Specifies the initial value of the added member.</span></span>
<span data-ttu-id="4d851-226">如果添加了 **AliasProperty** 、 **CodeProperty** 、 **ScriptProperty** 或 **CodeMethod** 成员，则可以使用 **SecondValue** 参数提供可选的附加信息。</span><span class="sxs-lookup"><span data-stu-id="4d851-226">If you add an **AliasProperty** , **CodeProperty** , **ScriptProperty** or **CodeMethod** member, you can supply optional, additional information by using the **SecondValue** parameter.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-227">-TypeName</span><span class="sxs-lookup"><span data-stu-id="4d851-227">-TypeName</span></span>

<span data-ttu-id="4d851-228">指定类型的名称。</span><span class="sxs-lookup"><span data-stu-id="4d851-228">Specifies a name for the type.</span></span>

<span data-ttu-id="4d851-229">如果类型是 **System** 命名空间中的类或具有类型加速器的类型，则可以输入类型的短名称。</span><span class="sxs-lookup"><span data-stu-id="4d851-229">When the type is a class in the **System** namespace or a type that has a type accelerator, you can enter the short name of the type.</span></span> <span data-ttu-id="4d851-230">否则，必须输入完整类型名称。</span><span class="sxs-lookup"><span data-stu-id="4d851-230">Otherwise, the full type name is required.</span></span>
<span data-ttu-id="4d851-231">仅当 **InputObject** 为 **PSObject** 时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="4d851-231">This parameter is effective only when the **InputObject** is a **PSObject** .</span></span>

<span data-ttu-id="4d851-232">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="4d851-232">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4d851-233">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4d851-233">CommonParameters</span></span>

<span data-ttu-id="4d851-234">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4d851-234">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4d851-235">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="4d851-235">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="4d851-236">输入</span><span class="sxs-lookup"><span data-stu-id="4d851-236">INPUTS</span></span>

### <span data-ttu-id="4d851-237">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="4d851-237">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="4d851-238">可以通过管道将任何对象类型传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4d851-238">You can pipe any object type to this cmdlet.</span></span>

## <span data-ttu-id="4d851-239">输出</span><span class="sxs-lookup"><span data-stu-id="4d851-239">OUTPUTS</span></span>

### <span data-ttu-id="4d851-240">None 或 system.string</span><span class="sxs-lookup"><span data-stu-id="4d851-240">None or System.Object</span></span>

<span data-ttu-id="4d851-241">当使用 **PassThru** 参数时，此 cmdlet 将返回新扩展的对象。</span><span class="sxs-lookup"><span data-stu-id="4d851-241">When you use the **PassThru** parameter, this cmdlet returns the newly-extended object.</span></span>
<span data-ttu-id="4d851-242">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="4d851-242">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4d851-243">注释</span><span class="sxs-lookup"><span data-stu-id="4d851-243">NOTES</span></span>

<span data-ttu-id="4d851-244">只能向 **PSObject** 对象添加成员。</span><span class="sxs-lookup"><span data-stu-id="4d851-244">You can add members only to **PSObject** objects.</span></span> <span data-ttu-id="4d851-245">若要确定某个对象是否为 **PSObject** 对象，请使用 `-is` 运算符。</span><span class="sxs-lookup"><span data-stu-id="4d851-245">To determine whether an object is a **PSObject** object, use the `-is` operator.</span></span>

<span data-ttu-id="4d851-246">例如，若要测试变量中存储的对象 `$obj` ，请键入 `$obj -is [PSObject]` 。</span><span class="sxs-lookup"><span data-stu-id="4d851-246">For instance, to test an object stored in the `$obj` variable, type `$obj -is [PSObject]`.</span></span>

<span data-ttu-id="4d851-247">**MemberType** 、 **Name** 、 **Value** 和 **SecondValue** 参数的名称是可选的。</span><span class="sxs-lookup"><span data-stu-id="4d851-247">The names of the **MemberType** , **Name** , **Value** , and **SecondValue** parameters are optional.</span></span>
<span data-ttu-id="4d851-248">如果省略参数名称，则未命名参数值必须按以下顺序出现： " **MemberType** "、" **Name** "、" **Value** " 和 " **SecondValue** "。</span><span class="sxs-lookup"><span data-stu-id="4d851-248">If you omit the parameter names, the unnamed parameter values must appear in this order: **MemberType** , **Name** , **Value** , and **SecondValue** .</span></span>

<span data-ttu-id="4d851-249">如果包括参数名称，则参数能够以任何顺序出现。</span><span class="sxs-lookup"><span data-stu-id="4d851-249">If you include the parameter names, the parameters can appear in any order.</span></span>

<span data-ttu-id="4d851-250">可以 `$this` 在定义新属性和方法的值的脚本块中使用自动变量。</span><span class="sxs-lookup"><span data-stu-id="4d851-250">You can use the `$this` automatic variable in script blocks that define the values of new properties and methods.</span></span>
<span data-ttu-id="4d851-251">`$this`变量引用要向其中添加属性和方法的对象的实例。</span><span class="sxs-lookup"><span data-stu-id="4d851-251">The `$this` variable refers to the instance of the object to which the properties and methods are being added.</span></span> <span data-ttu-id="4d851-252">有关变量的详细信息 `$this` ，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="4d851-252">For more information about the `$this` variable, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="4d851-253">相关链接</span><span class="sxs-lookup"><span data-stu-id="4d851-253">RELATED LINKS</span></span>

[<span data-ttu-id="4d851-254">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="4d851-254">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="4d851-255">Get-Member</span><span class="sxs-lookup"><span data-stu-id="4d851-255">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="4d851-256">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="4d851-256">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="4d851-257">New-Object</span><span class="sxs-lookup"><span data-stu-id="4d851-257">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="4d851-258">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="4d851-258">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)
