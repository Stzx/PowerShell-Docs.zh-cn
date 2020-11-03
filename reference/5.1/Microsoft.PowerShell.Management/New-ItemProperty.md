---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-ItemProperty
ms.openlocfilehash: 2569f4778f54f6cdad22e10cf92e727b73c323e3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198083"
---
# <span data-ttu-id="9d1a3-103">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-103">New-ItemProperty</span></span>

## <span data-ttu-id="9d1a3-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9d1a3-104">SYNOPSIS</span></span>
<span data-ttu-id="9d1a3-105">为项创建新属性并设置该属性的值。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-105">Creates a new property for an item and sets its value.</span></span>

## <span data-ttu-id="9d1a3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9d1a3-106">SYNTAX</span></span>

### <span data-ttu-id="9d1a3-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="9d1a3-107">Path (Default)</span></span>

```
New-ItemProperty [-Path] <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="9d1a3-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d1a3-108">LiteralPath</span></span>

```
New-ItemProperty -LiteralPath <String[]> [-Name] <String> [-PropertyType <String>] [-Value <Object>] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="9d1a3-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9d1a3-109">DESCRIPTION</span></span>

<span data-ttu-id="9d1a3-110">`New-ItemProperty`Cmdlet 为指定项创建新属性并设置其值。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-110">The `New-ItemProperty` cmdlet creates a new property for a specified item and sets its value.</span></span>
<span data-ttu-id="9d1a3-111">此 cmdlet 通常用于创建新注册表值，因为注册表值是注册表项的属性。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-111">Typically, this cmdlet is used to create new registry values, because registry values are properties of a registry key item.</span></span>

<span data-ttu-id="9d1a3-112">此 cmdlet 不能向对象添加属性。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-112">This cmdlet does not add properties to an object.</span></span>

- <span data-ttu-id="9d1a3-113">若要将属性添加到对象的实例，请使用 `Add-Member` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-113">To add a property to an instance of an object, use the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="9d1a3-114">若要向特定类型的所有对象添加属性，请修改 Types.ps1xml 文件。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-114">To add a property to all objects of a particular type, modify the Types.ps1xml file.</span></span>

## <span data-ttu-id="9d1a3-115">示例</span><span class="sxs-lookup"><span data-stu-id="9d1a3-115">EXAMPLES</span></span>

### <span data-ttu-id="9d1a3-116">示例 1：添加注册表项</span><span class="sxs-lookup"><span data-stu-id="9d1a3-116">Example 1: Add a registry entry</span></span>

<span data-ttu-id="9d1a3-117">此命令将新的注册表项 "NoOfEmployees" 添加到 "HKLM： \ 软件 hive" 的 "MyCompany" 键。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-117">This command adds a new registry entry, "NoOfEmployees", to the "MyCompany" key of the "HKLM:\Software hive".</span></span>

<span data-ttu-id="9d1a3-118">第一个命令使用 **Path** 参数来指定 "MyCompany" 注册表项的路径。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-118">The first command uses the **Path** parameter to specify the path of the "MyCompany" registry key.</span></span>
<span data-ttu-id="9d1a3-119">它使用 **name** 参数指定该条目的名称，使用 **value** 参数指定其值。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-119">It uses the **Name** parameter to specify a name for the entry and the **Value** parameter to specify its value.</span></span>

<span data-ttu-id="9d1a3-120">第二个命令使用 `Get-ItemProperty` cmdlet 查看新的注册表项。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-120">The second command uses the `Get-ItemProperty` cmdlet to see the new registry entry.</span></span>

```powershell
New-ItemProperty -Path "HKLM:\Software\MyCompany" -Name "NoOfEmployees" -Value 822
Get-ItemProperty "HKLM:\Software\MyCompany"
```

```output
PSPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software\mycompany
PSParentPath  : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\software
PSChildName   : mycompany
PSDrive       : HKLM
PSProvider    : Microsoft.PowerShell.Core\Registry
NoOfLocations : 2
NoOfEmployees : 822
```

### <span data-ttu-id="9d1a3-121">示例 2：将注册表项添加到键</span><span class="sxs-lookup"><span data-stu-id="9d1a3-121">Example 2: Add a registry entry to a key</span></span>

<span data-ttu-id="9d1a3-122">此命令向注册表项添加新的注册表条目。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-122">This command adds a new registry entry to a registry key.</span></span> <span data-ttu-id="9d1a3-123">为了指定密钥，它使用管道运算符 (|) ，则将表示密钥的对象发送到 `New-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-123">To specify the key, it uses a pipeline operator (|) to send an object that represents the key to `New-ItemProperty`.</span></span>

<span data-ttu-id="9d1a3-124">该命令的第一部分使用 `Get-Item` cmdlet 来获取 "MyCompany" 注册表项。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-124">The first part of the command uses the `Get-Item` cmdlet to get the "MyCompany" registry key.</span></span> <span data-ttu-id="9d1a3-125">管道运算符将命令的结果发送到 `New-ItemProperty` ，这会将新的注册表项 ( "NoOfLocations" ) ，并将其值 (3) 添加到 "MyCompany" 键。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-125">The pipeline operator sends the results of the command to `New-ItemProperty`, which adds the new registry entry ("NoOfLocations"), and its value (3), to the "MyCompany" key.</span></span>

```powershell
Get-Item -Path "HKLM:\Software\MyCompany" | New-ItemProperty -Name NoOfLocations -Value 3
```

<span data-ttu-id="9d1a3-126">此命令有效，因为 Windows PowerShell 的参数绑定功能将返回的对象的路径 `RegistryKey` 与的 `Get-Item` **LiteralPath** 参数相关联 `New-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-126">This command works because the parameter-binding feature of Windows PowerShell associates the path of the `RegistryKey` object that `Get-Item` returns with the **LiteralPath** parameter of `New-ItemProperty`.</span></span> <span data-ttu-id="9d1a3-127">有关详细信息，请参阅 [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md)。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-127">For more information, see [about_Pipelines](../Microsoft.PowerShell.Core/About/about_pipelines.md).</span></span>

### <span data-ttu-id="9d1a3-128">示例3：使用 Here-String 在注册表中创建多字符串值</span><span class="sxs-lookup"><span data-stu-id="9d1a3-128">Example 3: Create a MultiString value in the registry using a Here-String</span></span>

<span data-ttu-id="9d1a3-129">此示例使用多字符串创建一个值。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-129">This example creates a MultiString value using a Here-String.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'HereString' -PropertyType MultiString -Value @"
This is text which contains newlines
It can also contain "quoted" strings
"@
$newValue.multistring
```

```output
This is text which contains newlines
It can also contain "quoted" strings
```

### <span data-ttu-id="9d1a3-130">示例4：使用数组在注册表中创建多字符串值</span><span class="sxs-lookup"><span data-stu-id="9d1a3-130">Example 4: Create a MultiString value in the registry using an array</span></span>

<span data-ttu-id="9d1a3-131">该示例演示如何使用值数组创建 `MultiString` 值。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-131">The example shows how to use an array of values to create the `MultiString` value.</span></span>

```powershell
$newValue = New-ItemProperty -Path "HKLM:\SOFTWARE\ContosoCompany\" -Name 'MultiString' -PropertyType MultiString -Value ('a','b','c')
$newValue.multistring[0]
```

```output
a
```

## <span data-ttu-id="9d1a3-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9d1a3-132">PARAMETERS</span></span>

### <span data-ttu-id="9d1a3-133">-Credential</span><span class="sxs-lookup"><span data-stu-id="9d1a3-133">-Credential</span></span>

<span data-ttu-id="9d1a3-134">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-134">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="9d1a3-135">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-135">The default is the current user.</span></span>

<span data-ttu-id="9d1a3-136">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-136">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="9d1a3-137">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-137">If you type a user name, you are prompted for a password.</span></span>

> [!NOTE]
> <span data-ttu-id="9d1a3-138">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-138">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9d1a3-139">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 [Invoke 命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-139">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="9d1a3-140">-Exclude</span><span class="sxs-lookup"><span data-stu-id="9d1a3-140">-Exclude</span></span>

<span data-ttu-id="9d1a3-141">指定为字符串数组，此 cmdlet 从操作中排除的属性或属性。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-141">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="9d1a3-142">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-142">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="9d1a3-143">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-143">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="9d1a3-144">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-144">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-145">-Filter</span><span class="sxs-lookup"><span data-stu-id="9d1a3-145">-Filter</span></span>

<span data-ttu-id="9d1a3-146">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-146">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="9d1a3-147">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-147">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="9d1a3-148">筛选器的语法（包括通配符字符的使用），具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-148">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span> <span data-ttu-id="9d1a3-149">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-149">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-150">-Force</span><span class="sxs-lookup"><span data-stu-id="9d1a3-150">-Force</span></span>

<span data-ttu-id="9d1a3-151">强制 cmdlet 创建用户非此不能访问的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-151">Forces the cmdlet to create a property on an object that cannot otherwise be accessed by the user.</span></span>
<span data-ttu-id="9d1a3-152">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-152">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="9d1a3-153">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-153">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="9d1a3-154">-Include</span><span class="sxs-lookup"><span data-stu-id="9d1a3-154">-Include</span></span>

<span data-ttu-id="9d1a3-155">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-155">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="9d1a3-156">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-156">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="9d1a3-157">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-157">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="9d1a3-158">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-158">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-159">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9d1a3-159">-LiteralPath</span></span>

<span data-ttu-id="9d1a3-160">指定此属性的当前位置的路径。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-160">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="9d1a3-161">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-161">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="9d1a3-162">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-162">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="9d1a3-163">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-163">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="9d1a3-164">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-164">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-165">-Name</span><span class="sxs-lookup"><span data-stu-id="9d1a3-165">-Name</span></span>

<span data-ttu-id="9d1a3-166">指定新属性的名称。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-166">Specifies a name for the new property.</span></span>
<span data-ttu-id="9d1a3-167">如果该属性是注册表条目，则此参数指定该条目的名称。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-167">If the property is a registry entry, this parameter specifies the name of the entry.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-168">-Path</span><span class="sxs-lookup"><span data-stu-id="9d1a3-168">-Path</span></span>

<span data-ttu-id="9d1a3-169">指定项的路径。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-169">Specifies the path of the item.</span></span>
<span data-ttu-id="9d1a3-170">此参数标识此 cmdlet 要向其添加新属性的项。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-170">This parameter identifies the item to which this cmdlet adds the new property.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-171">-PropertyType</span><span class="sxs-lookup"><span data-stu-id="9d1a3-171">-PropertyType</span></span>

<span data-ttu-id="9d1a3-172">指定此 cmdlet 添加的属性类型。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-172">Specifies the type of property that this cmdlet adds.</span></span>
<span data-ttu-id="9d1a3-173">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="9d1a3-173">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9d1a3-174">**String** ：指定以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-174">**String** : Specifies a null-terminated string.</span></span> <span data-ttu-id="9d1a3-175">等效于 **REG_SZ** 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-175">Equivalent to **REG_SZ** .</span></span>
- <span data-ttu-id="9d1a3-176">**ExpandString** ：指定一个以 null 结尾的字符串，该字符串包含对在检索值时扩展的环境变量的未展开引用。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-176">**ExpandString** : Specifies a null-terminated string that contains unexpanded references to environment variables that are expanded when the value is retrieved.</span></span> <span data-ttu-id="9d1a3-177">等效于 **REG_EXPAND_SZ** 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-177">Equivalent to **REG_EXPAND_SZ** .</span></span>
- <span data-ttu-id="9d1a3-178">**Binary** ：指定任意格式的二进制数据。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-178">**Binary** : Specifies binary data in any form.</span></span> <span data-ttu-id="9d1a3-179">等效于 **REG_BINARY** 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-179">Equivalent to **REG_BINARY** .</span></span>
- <span data-ttu-id="9d1a3-180">**DWord** ：指定32位二进制数。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-180">**DWord** : Specifies a 32-bit binary number.</span></span> <span data-ttu-id="9d1a3-181">等效于 **REG_DWORD** 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-181">Equivalent to **REG_DWORD** .</span></span>
- <span data-ttu-id="9d1a3-182">**多字符串** ：指定以 null 结尾的字符串的数组，该数组以两个 null 字符结尾。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-182">**MultiString** : Specifies an array of null-terminated strings terminated by two null characters.</span></span>
  <span data-ttu-id="9d1a3-183">等效于 **REG_MULTI_SZ** 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-183">Equivalent to **REG_MULTI_SZ** .</span></span>
- <span data-ttu-id="9d1a3-184">**Qword** ：指定64位二进制数。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-184">**Qword** : Specifies a 64-bit binary number.</span></span> <span data-ttu-id="9d1a3-185">等效于 **REG_QWORD** 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-185">Equivalent to **REG_QWORD** .</span></span>
- <span data-ttu-id="9d1a3-186">**未知** ：指示不受支持的注册表数据类型，如 **REG_RESOURCE_LIST** 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-186">**Unknown** : Indicates an unsupported registry data type, such as **REG_RESOURCE_LIST** .</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-187">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="9d1a3-187">-UseTransaction</span></span>

<span data-ttu-id="9d1a3-188">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-188">Includes the command in the active transaction.</span></span>
<span data-ttu-id="9d1a3-189">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-189">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="9d1a3-190">有关详细信息，请参阅 about_Transactions。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-190">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-191">-Value</span><span class="sxs-lookup"><span data-stu-id="9d1a3-191">-Value</span></span>

<span data-ttu-id="9d1a3-192">指定属性值。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-192">Specifies the property value.</span></span>
<span data-ttu-id="9d1a3-193">如果该属性是注册表条目，则此参数指定该条目的值。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-193">If the property is a registry entry, this parameter specifies the value of the entry.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9d1a3-194">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9d1a3-194">-Confirm</span></span>

<span data-ttu-id="9d1a3-195">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-195">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9d1a3-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9d1a3-196">-WhatIf</span></span>

<span data-ttu-id="9d1a3-197">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-197">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9d1a3-198">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-198">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9d1a3-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9d1a3-199">CommonParameters</span></span>

<span data-ttu-id="9d1a3-200">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-200">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9d1a3-201">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-201">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9d1a3-202">输入</span><span class="sxs-lookup"><span data-stu-id="9d1a3-202">INPUTS</span></span>

### <span data-ttu-id="9d1a3-203">无</span><span class="sxs-lookup"><span data-stu-id="9d1a3-203">None</span></span>

<span data-ttu-id="9d1a3-204">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-204">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="9d1a3-205">输出</span><span class="sxs-lookup"><span data-stu-id="9d1a3-205">OUTPUTS</span></span>

### <span data-ttu-id="9d1a3-206">System.Management.Automation.PSCustomObject</span><span class="sxs-lookup"><span data-stu-id="9d1a3-206">System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="9d1a3-207">`New-ItemProperty` 返回一个包含新属性的自定义对象。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-207">`New-ItemProperty` returns a custom object that contains the new property.</span></span>

## <span data-ttu-id="9d1a3-208">注释</span><span class="sxs-lookup"><span data-stu-id="9d1a3-208">NOTES</span></span>

<span data-ttu-id="9d1a3-209">`New-ItemProperty` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-209">`New-ItemProperty` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9d1a3-210">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-210">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="9d1a3-211">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="9d1a3-211">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9d1a3-212">相关链接</span><span class="sxs-lookup"><span data-stu-id="9d1a3-212">RELATED LINKS</span></span>

[<span data-ttu-id="9d1a3-213">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-213">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="9d1a3-214">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-214">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="9d1a3-215">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-215">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="9d1a3-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-216">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="9d1a3-217">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-217">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="9d1a3-218">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-218">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="9d1a3-219">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9d1a3-219">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="9d1a3-220">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9d1a3-220">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
