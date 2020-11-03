---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-itemproperty?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ItemProperty
ms.openlocfilehash: 26f26ff48d0c2d68c9c814da192ce1846edfe9b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197317"
---
# <span data-ttu-id="ae63d-103">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-103">Set-ItemProperty</span></span>

## <span data-ttu-id="ae63d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ae63d-104">SYNOPSIS</span></span>
<span data-ttu-id="ae63d-105">创建或更改某一项的属性值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-105">Creates or changes the value of a property of an item.</span></span>

## <span data-ttu-id="ae63d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ae63d-106">SYNTAX</span></span>

### <span data-ttu-id="ae63d-107">propertyValuePathSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="ae63d-107">propertyValuePathSet (Default)</span></span>

```
Set-ItemProperty [-Path] <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="ae63d-108">propertyPSObjectPathSet</span><span class="sxs-lookup"><span data-stu-id="ae63d-108">propertyPSObjectPathSet</span></span>

```
Set-ItemProperty [-Path] <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="ae63d-109">propertyValueLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="ae63d-109">propertyValueLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> [-Name] <String> [-Value] <Object> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

### <span data-ttu-id="ae63d-110">propertyPSObjectLiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="ae63d-110">propertyPSObjectLiteralPathSet</span></span>

```
Set-ItemProperty -LiteralPath <String[]> -InputObject <PSObject> [-PassThru] [-Force] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-Type <RegistryValueKind>] [<CommonParameters>]
```

## <span data-ttu-id="ae63d-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ae63d-111">DESCRIPTION</span></span>

<span data-ttu-id="ae63d-112">`Set-ItemProperty`Cmdlet 更改指定项的属性的值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-112">The `Set-ItemProperty` cmdlet changes the value of the property of the specified item.</span></span>
<span data-ttu-id="ae63d-113">可以使用该 cmdlet 设定或更改项的属性。</span><span class="sxs-lookup"><span data-stu-id="ae63d-113">You can use the cmdlet to establish or change the properties of items.</span></span>
<span data-ttu-id="ae63d-114">例如，可以使用 `Set-ItemProperty` 将文件对象的 **IsReadOnly** 属性的值设置为 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-114">For example, you can use `Set-ItemProperty` to set the value of the **IsReadOnly** property of a file object to `$True`.</span></span>

<span data-ttu-id="ae63d-115">你还可以使用 `Set-ItemProperty` 来创建和更改注册表值和数据。</span><span class="sxs-lookup"><span data-stu-id="ae63d-115">You also use `Set-ItemProperty` to create and change registry values and data.</span></span>
<span data-ttu-id="ae63d-116">例如，可以向注册表项中添加新的注册表条目以及设定或更改该条目的值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-116">For example, you can add a new registry entry to a key and establish or change its value.</span></span>

## <span data-ttu-id="ae63d-117">示例</span><span class="sxs-lookup"><span data-stu-id="ae63d-117">EXAMPLES</span></span>

### <span data-ttu-id="ae63d-118">示例1：设置文件的属性</span><span class="sxs-lookup"><span data-stu-id="ae63d-118">Example 1: Set a property of a file</span></span>

<span data-ttu-id="ae63d-119">此命令将 "final.doc" 文件的 " **IsReadOnly** " 属性的值设置为 "true"。</span><span class="sxs-lookup"><span data-stu-id="ae63d-119">This command sets the value of the **IsReadOnly** property of the "final.doc" file to "true".</span></span>
<span data-ttu-id="ae63d-120">它使用 **路径** 指定文件的名称，使用 **name** 指定属性的名称，并使用 **Value** 参数指定新值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-120">It uses **Path** to specify the file, **Name** to specify the name of the property, and the **Value** parameter to specify the new value.</span></span>

<span data-ttu-id="ae63d-121">文件是 **FileInfo** 对象，而 **IsReadOnly** 只是它的一个属性。</span><span class="sxs-lookup"><span data-stu-id="ae63d-121">The file is a **System.IO.FileInfo** object and **IsReadOnly** is just one of its properties.</span></span>
<span data-ttu-id="ae63d-122">若要查看所有属性，请键入 `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-122">To see all of the properties, type `Get-Item C:\GroupFiles\final.doc | Get-Member -MemberType
Property`.</span></span>

<span data-ttu-id="ae63d-123">`$true`自动变量表示值 "TRUE"。</span><span class="sxs-lookup"><span data-stu-id="ae63d-123">The `$true` automatic variable represents a value of "TRUE".</span></span>
<span data-ttu-id="ae63d-124">有关详细信息，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="ae63d-124">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

```powershell
Set-ItemProperty -Path C:\GroupFiles\final.doc -Name IsReadOnly -Value $true
```

### <span data-ttu-id="ae63d-125">示例2：创建注册表项和值</span><span class="sxs-lookup"><span data-stu-id="ae63d-125">Example 2: Create a registry entry and value</span></span>

<span data-ttu-id="ae63d-126">此示例演示如何使用 `Set-ItemProperty` 来创建新的注册表项，并为该项分配值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-126">This example shows how to use `Set-ItemProperty` to create a new registry entry and to assign a value to the entry.</span></span> <span data-ttu-id="ae63d-127">它在密钥中的 "ContosoCompany" 键上创建 "NoOfEmployees" 条目 `HKLM\Software` ，并将其值设置为823。</span><span class="sxs-lookup"><span data-stu-id="ae63d-127">It creates the "NoOfEmployees" entry in the "ContosoCompany" key in `HKLM\Software` key and sets its value to 823.</span></span>

<span data-ttu-id="ae63d-128">因为注册表项被视为注册表项的属性（这些项是项），您可以使用这些项 `Set-ItemProperty` 创建注册表项，并建立和更改它们的值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-128">Because registry entries are considered to be properties of the registry keys, which are items, you use `Set-ItemProperty` to create registry entries, and to establish and change their values.</span></span>

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 823
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 823
```

```powershell
Set-ItemProperty -Path "HKLM:\Software\ContosoCompany" -Name "NoOfEmployees" -Value 824
Get-ItemProperty -Path "HKLM:\Software\ContosoCompany"
```

```Output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\contosocompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : contosocompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 824
```

<span data-ttu-id="ae63d-129">第一个命令创建注册表项。</span><span class="sxs-lookup"><span data-stu-id="ae63d-129">The first command creates the registry entry.</span></span>
<span data-ttu-id="ae63d-130">它使用 **path** 来指定驱动器的路径 `HKLM:` 和 "Software\MyCompany" 项。</span><span class="sxs-lookup"><span data-stu-id="ae63d-130">It uses **Path** to specify the path of the `HKLM:` drive and the "Software\MyCompany" key.</span></span>
<span data-ttu-id="ae63d-131">该命令使用 **name** 来指定输入值的名称和 **值** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-131">The command uses **Name** to specify the entry name and **Value** to specify a value.</span></span>

<span data-ttu-id="ae63d-132">第二个命令使用 `Get-ItemProperty` cmdlet 查看新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="ae63d-132">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>
<span data-ttu-id="ae63d-133">如果使用 `Get-Item` 或 `Get-ChildItem` cmdlet，则这些项将不会显示，因为它们是键的属性，而不是项或子项的属性。</span><span class="sxs-lookup"><span data-stu-id="ae63d-133">If you use the `Get-Item` or `Get-ChildItem` cmdlets, the entries do not appear because they are properties of a key, not items or child items.</span></span>

<span data-ttu-id="ae63d-134">第三个命令将 **NoOfEmployees** 条目的值更改为824。</span><span class="sxs-lookup"><span data-stu-id="ae63d-134">The third command changes the value of the **NoOfEmployees** entry to 824.</span></span>

<span data-ttu-id="ae63d-135">你还可以使用 `New-ItemProperty` cmdlet 来创建注册表项及其值，并使用 `Set-ItemProperty` 来更改值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-135">You can also use the `New-ItemProperty` cmdlet to create the registry entry and its value and then use `Set-ItemProperty` to change the value.</span></span>

<span data-ttu-id="ae63d-136">有关驱动器的详细信息 `HKLM:` ，请键入 `Get-Help Get-PSDrive` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-136">For more information about the `HKLM:` drive, type `Get-Help Get-PSDrive`.</span></span>
<span data-ttu-id="ae63d-137">有关如何使用 PowerShell 管理注册表的详细信息，请键入 `Get-Help Registry` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-137">For more information about how to use PowerShell to manage the registry, type `Get-Help Registry`.</span></span>

### <span data-ttu-id="ae63d-138">示例3：使用管道修改项</span><span class="sxs-lookup"><span data-stu-id="ae63d-138">Example 3: Modify an item by using the pipeline</span></span>

<span data-ttu-id="ae63d-139">这些命令演示如何使用管道运算符 () 将 `|` 项发送到 `Set-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-139">These commands show how to use a pipeline operator (`|`) to send an item to `Set-ItemProperty`.</span></span>

<span data-ttu-id="ae63d-140">该命令的第一部分使用 `Get-ChildItem` 来获取表示 "Weekly.txt" 文件的对象。</span><span class="sxs-lookup"><span data-stu-id="ae63d-140">The first part of the command uses `Get-ChildItem` to get an object that represents the "Weekly.txt" file.</span></span> <span data-ttu-id="ae63d-141">该命令使用管道运算符将文件对象发送到 `Set-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-141">The command uses a pipeline operator to send the file object to `Set-ItemProperty`.</span></span>
<span data-ttu-id="ae63d-142">该 `Set-ItemProperty` 命令使用 **Name** 和 **Value** 参数来指定属性及其新值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-142">The `Set-ItemProperty` command uses the **Name** and **Value** parameters to specify the property and its new value.</span></span>

<span data-ttu-id="ae63d-143">此命令等效于使用 **InputObject** 参数指定获取的对象 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-143">This command is equivalent to using the **InputObject** parameter to specify the object that `Get-ChildItem` gets.</span></span>

```powershell
Get-ChildItem weekly.txt | Set-ItemProperty -Name IsReadOnly -Value $True
```

## <span data-ttu-id="ae63d-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ae63d-144">PARAMETERS</span></span>

### <span data-ttu-id="ae63d-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="ae63d-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="ae63d-146">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="ae63d-146">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="ae63d-147">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="ae63d-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-148">-Exclude</span><span class="sxs-lookup"><span data-stu-id="ae63d-148">-Exclude</span></span>

<span data-ttu-id="ae63d-149">指定为字符串数组，此 cmdlet 在操作中排除的项。</span><span class="sxs-lookup"><span data-stu-id="ae63d-149">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="ae63d-150">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ae63d-150">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ae63d-151">请输入路径元素或模式，例如 `*.txt`。</span><span class="sxs-lookup"><span data-stu-id="ae63d-151">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="ae63d-152">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ae63d-152">Wildcard characters are permitted.</span></span> <span data-ttu-id="ae63d-153">仅 **Exclude** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Exclude 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-153">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ae63d-154">-Filter</span><span class="sxs-lookup"><span data-stu-id="ae63d-154">-Filter</span></span>

<span data-ttu-id="ae63d-155">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="ae63d-155">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="ae63d-156">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一一种支持使用筛选器的已安装 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="ae63d-156">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="ae63d-157">可以在 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)中找到 **文件系统** 筛选语言的语法。</span><span class="sxs-lookup"><span data-stu-id="ae63d-157">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="ae63d-158">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="ae63d-158">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ae63d-159">-Force</span><span class="sxs-lookup"><span data-stu-id="ae63d-159">-Force</span></span>

<span data-ttu-id="ae63d-160">强制 cmdlet 设置用户不能访问的项的属性。</span><span class="sxs-lookup"><span data-stu-id="ae63d-160">Forces the cmdlet to set a property on items that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="ae63d-161">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="ae63d-161">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="ae63d-162">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="ae63d-162">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="ae63d-163">-Include</span><span class="sxs-lookup"><span data-stu-id="ae63d-163">-Include</span></span>

<span data-ttu-id="ae63d-164">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="ae63d-164">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="ae63d-165">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ae63d-165">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="ae63d-166">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="ae63d-166">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="ae63d-167">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ae63d-167">Wildcard characters are permitted.</span></span> <span data-ttu-id="ae63d-168">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-168">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ae63d-169">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ae63d-169">-InputObject</span></span>

<span data-ttu-id="ae63d-170">指定具有此 cmdlet 更改的属性的对象。</span><span class="sxs-lookup"><span data-stu-id="ae63d-170">Specifies the object that has the properties that this cmdlet changes.</span></span>
<span data-ttu-id="ae63d-171">请输入包含对象的变量或可获取该对象的命令。</span><span class="sxs-lookup"><span data-stu-id="ae63d-171">Enter a variable that contains the object or a command that gets the object.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: propertyPSObjectPathSet, propertyPSObjectLiteralPathSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-172">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="ae63d-172">-LiteralPath</span></span>

<span data-ttu-id="ae63d-173">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="ae63d-173">Specifies a path to one or more locations.</span></span> <span data-ttu-id="ae63d-174">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="ae63d-174">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="ae63d-175">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="ae63d-175">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="ae63d-176">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="ae63d-176">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="ae63d-177">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="ae63d-177">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="ae63d-178">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="ae63d-178">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValueLiteralPathSet, propertyPSObjectLiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-179">-Name</span><span class="sxs-lookup"><span data-stu-id="ae63d-179">-Name</span></span>

<span data-ttu-id="ae63d-180">指定属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ae63d-180">Specifies the name of the property.</span></span>

```yaml
Type: System.String
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-181">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ae63d-181">-PassThru</span></span>

<span data-ttu-id="ae63d-182">返回一个表示项属性的对象。</span><span class="sxs-lookup"><span data-stu-id="ae63d-182">Returns an object that represents the item property.</span></span>
<span data-ttu-id="ae63d-183">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="ae63d-183">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ae63d-184">-Path</span><span class="sxs-lookup"><span data-stu-id="ae63d-184">-Path</span></span>

<span data-ttu-id="ae63d-185">指定包含要修改的属性的项的路径。</span><span class="sxs-lookup"><span data-stu-id="ae63d-185">Specifies the path of the items with the property to modify.</span></span>
<span data-ttu-id="ae63d-186">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ae63d-186">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: propertyValuePathSet, propertyPSObjectPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="ae63d-187">-Type</span><span class="sxs-lookup"><span data-stu-id="ae63d-187">-Type</span></span>

<span data-ttu-id="ae63d-188">**类型** 是注册表提供程序添加到 cmdlet 的动态参数 `Set-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-188">**Type** is a dynamic parameter that the Registry provider adds to the `Set-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="ae63d-189">此参数仅适用于注册表驱动器。</span><span class="sxs-lookup"><span data-stu-id="ae63d-189">This parameter only works in the registry drives.</span></span>

<span data-ttu-id="ae63d-190">指定此 cmdlet 添加的属性类型。</span><span class="sxs-lookup"><span data-stu-id="ae63d-190">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="ae63d-191">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ae63d-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ae63d-192">**String** ：指定以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="ae63d-192">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="ae63d-193">等效于 **REG_SZ** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-193">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="ae63d-194">**ExpandString** ：指定一个以 null 结尾的字符串，该字符串包含对在检索值时扩展的环境变量的未展开引用。</span><span class="sxs-lookup"><span data-stu-id="ae63d-194">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="ae63d-195">等效于 **REG_EXPAND_SZ** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-195">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="ae63d-196">**Binary** ：指定任意格式的二进制数据。</span><span class="sxs-lookup"><span data-stu-id="ae63d-196">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="ae63d-197">等效于 **REG_BINARY** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-197">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="ae63d-198">**DWord** ：指定32位二进制数。</span><span class="sxs-lookup"><span data-stu-id="ae63d-198">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="ae63d-199">等效于 **REG_DWORD** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-199">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="ae63d-200">**多字符串** ：指定以 null 结尾的字符串的数组，该数组以两个 null 字符结尾。</span><span class="sxs-lookup"><span data-stu-id="ae63d-200">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="ae63d-201">等效于 **REG_MULTI_SZ** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-201">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="ae63d-202">**Qword** ：指定64位二进制数。</span><span class="sxs-lookup"><span data-stu-id="ae63d-202">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="ae63d-203">等效于 **REG_QWORD** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-203">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="ae63d-204">**未知** ：指示不受支持的注册表数据类型，如 **REG_RESOURCE_LIST** 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-204">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

```yaml
Type: Microsoft.Win32.RegistryValueKind
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-205">-Value</span><span class="sxs-lookup"><span data-stu-id="ae63d-205">-Value</span></span>

<span data-ttu-id="ae63d-206">指定属性的值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-206">Specifies the value of the property.</span></span>

```yaml
Type: System.Object
Parameter Sets: propertyValuePathSet, propertyValueLiteralPathSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ae63d-207">-Confirm</span></span>

<span data-ttu-id="ae63d-208">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="ae63d-208">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ae63d-209">-WhatIf</span></span>

<span data-ttu-id="ae63d-210">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ae63d-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ae63d-211">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ae63d-211">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ae63d-212">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ae63d-212">CommonParameters</span></span>

<span data-ttu-id="ae63d-213">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="ae63d-213">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="ae63d-214">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="ae63d-214">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ae63d-215">输入</span><span class="sxs-lookup"><span data-stu-id="ae63d-215">INPUTS</span></span>

### <span data-ttu-id="ae63d-216">System.Management.Automation.PSObject</span><span class="sxs-lookup"><span data-stu-id="ae63d-216">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="ae63d-217">可以通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ae63d-217">You can pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ae63d-218">输出</span><span class="sxs-lookup"><span data-stu-id="ae63d-218">OUTPUTS</span></span>

### <span data-ttu-id="ae63d-219">PSCustomObject （无）</span><span class="sxs-lookup"><span data-stu-id="ae63d-219">None, System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="ae63d-220">如果指定 **PassThru** 参数，则此 cmdlet 将生成一个 **PSCustomObject** 对象，该对象表示已更改的项及其新的属性值。</span><span class="sxs-lookup"><span data-stu-id="ae63d-220">This cmdlet generates a **PSCustomObject** object that represents the item that was changed and its new property value, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="ae63d-221">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ae63d-221">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ae63d-222">注释</span><span class="sxs-lookup"><span data-stu-id="ae63d-222">NOTES</span></span>

<span data-ttu-id="ae63d-223">`Set-ItemProperty` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="ae63d-223">`Set-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="ae63d-224">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="ae63d-224">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="ae63d-225">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="ae63d-225">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="ae63d-226">相关链接</span><span class="sxs-lookup"><span data-stu-id="ae63d-226">RELATED LINKS</span></span>

[<span data-ttu-id="ae63d-227">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-227">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="ae63d-228">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-228">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="ae63d-229">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-229">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="ae63d-230">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-230">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="ae63d-231">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-231">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="ae63d-232">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-232">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="ae63d-233">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="ae63d-233">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="ae63d-234">about_Providers</span><span class="sxs-lookup"><span data-stu-id="ae63d-234">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

