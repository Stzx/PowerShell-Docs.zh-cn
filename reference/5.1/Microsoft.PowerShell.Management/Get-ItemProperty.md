---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198285"
---
# <span data-ttu-id="0bffc-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-103">Get-ItemProperty</span></span>

## <span data-ttu-id="0bffc-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0bffc-104">SYNOPSIS</span></span>
<span data-ttu-id="0bffc-105">获取指定项的属性。</span><span class="sxs-lookup"><span data-stu-id="0bffc-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="0bffc-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bffc-106">SYNTAX</span></span>

### <span data-ttu-id="0bffc-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="0bffc-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="0bffc-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0bffc-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="0bffc-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bffc-109">DESCRIPTION</span></span>

<span data-ttu-id="0bffc-110">`Get-ItemProperty`Cmdlet 将获取指定项的属性。</span><span class="sxs-lookup"><span data-stu-id="0bffc-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="0bffc-111">例如，你可以使用此 cmdlet 来获取文件对象的 LastAccessTime 属性的值。</span><span class="sxs-lookup"><span data-stu-id="0bffc-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span>
<span data-ttu-id="0bffc-112">你还可以使用此 cmdlet 查看注册表项及其值。</span><span class="sxs-lookup"><span data-stu-id="0bffc-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="0bffc-113">示例</span><span class="sxs-lookup"><span data-stu-id="0bffc-113">EXAMPLES</span></span>

### <span data-ttu-id="0bffc-114">示例1：获取有关特定目录的信息</span><span class="sxs-lookup"><span data-stu-id="0bffc-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="0bffc-115">此命令获取有关 "C：\Windows" 目录的信息。</span><span class="sxs-lookup"><span data-stu-id="0bffc-115">This command gets information about the "C:\Windows" directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="0bffc-116">示例2：获取特定文件的属性</span><span class="sxs-lookup"><span data-stu-id="0bffc-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="0bffc-117">此命令将获取 "C:\Test\Weather.xls" 文件的属性。</span><span class="sxs-lookup"><span data-stu-id="0bffc-117">This command gets the properties of the "C:\Test\Weather.xls" file.</span></span>
<span data-ttu-id="0bffc-118">将结果输送到 cmdlet， `Format-List` 以将输出显示为列表。</span><span class="sxs-lookup"><span data-stu-id="0bffc-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="0bffc-119">示例3：在注册表子项中显示注册表项的值名称和数据</span><span class="sxs-lookup"><span data-stu-id="0bffc-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="0bffc-120">此命令显示 "CurrentVersion" 注册表子项中包含的每个注册表项的值名称和数据。</span><span class="sxs-lookup"><span data-stu-id="0bffc-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="0bffc-121">请注意，该命令要求有一个名为的 PowerShell 驱动器 `HKLM:` ，该驱动器映射到注册表的 "HKEY_LOCAL_MACHINE" hive。</span><span class="sxs-lookup"><span data-stu-id="0bffc-121">Note that the command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
<span data-ttu-id="0bffc-122">默认情况下，具有该名称和映射的驱动器在 PowerShell 中可用。</span><span class="sxs-lookup"><span data-stu-id="0bffc-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
<span data-ttu-id="0bffc-123">或者，可以通过使用以下替代路径指定此注册表子项的路径（替代路径以提供程序名称开头，后跟两个冒号）：</span><span class="sxs-lookup"><span data-stu-id="0bffc-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>

<span data-ttu-id="0bffc-124">"Registry：： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion"。</span><span class="sxs-lookup"><span data-stu-id="0bffc-124">"Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### <span data-ttu-id="0bffc-125">示例4：获取注册表子项中的注册表项的值名称和数据</span><span class="sxs-lookup"><span data-stu-id="0bffc-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="0bffc-126">此命令将获取 "CurrentVersion" 注册表子项中的 "ProgramFilesDir" 注册表项的值名称和数据。</span><span class="sxs-lookup"><span data-stu-id="0bffc-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="0bffc-127">该命令使用 **Path** 参数来指定子项，使用 name 参数来指定条目的值名称。</span><span class="sxs-lookup"><span data-stu-id="0bffc-127">The command uses the **Path** parameter to specify the subkey and the Name parameter to specify the value name of the entry.</span></span>

<span data-ttu-id="0bffc-128">该命令使用后退计时或重音符 (\`) （PowerShell 继续符）在第二行继续执行命令。</span><span class="sxs-lookup"><span data-stu-id="0bffc-128">The command uses a back tick or grave accent (\`), the PowerShell continuation character, to continue the command on the second line.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="0bffc-129">示例5：获取注册表项中的注册表项的值名称和数据</span><span class="sxs-lookup"><span data-stu-id="0bffc-129">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="0bffc-130">此命令将获取 "PowerShellEngine" 注册表项中的注册表项的值名称和数据。</span><span class="sxs-lookup"><span data-stu-id="0bffc-130">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span>
<span data-ttu-id="0bffc-131">结果显示在下面的示例输出中。</span><span class="sxs-lookup"><span data-stu-id="0bffc-131">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### <span data-ttu-id="0bffc-132">示例6：获取、格式化和显示注册表值和数据的结果</span><span class="sxs-lookup"><span data-stu-id="0bffc-132">Example 6: Get, format, and display the results of registry values and data</span></span>

<span data-ttu-id="0bffc-133">此示例演示如何设置列表中命令的输出的格式， `Get-ItemProperty` 以方便查看注册表值和数据，并使其易于解释结果。</span><span class="sxs-lookup"><span data-stu-id="0bffc-133">This example shows how to format the output of a `Get-ItemProperty` command in a list to make it easy to see the registry values and data and to make it easy to interpret the results.</span></span>

<span data-ttu-id="0bffc-134">第一个命令使用 `Get-ItemProperty` cmdlet 来获取 **Microsoft PowerShell** 子项中的注册表项。</span><span class="sxs-lookup"><span data-stu-id="0bffc-134">The first command uses the `Get-ItemProperty` cmdlet to get the registry entries in the **Microsoft.PowerShell** subkey.</span></span>
<span data-ttu-id="0bffc-135">此子项存储用于 PowerShell 的默认 shell 的选项。</span><span class="sxs-lookup"><span data-stu-id="0bffc-135">This subkey stores options for the default shell for PowerShell.</span></span>
<span data-ttu-id="0bffc-136">结果显示在下面的示例输出中。</span><span class="sxs-lookup"><span data-stu-id="0bffc-136">The results are shown in the following sample output.</span></span>

<span data-ttu-id="0bffc-137">输出显示有两个注册表项： "路径" 和 "Set-executionpolicy"。</span><span class="sxs-lookup"><span data-stu-id="0bffc-137">The output shows that there are two registry entries, "Path" and "ExecutionPolicy".</span></span>
<span data-ttu-id="0bffc-138">如果注册表项中包含的条目少于 5 个，则默认情况下，将以表的形式显示它，但通常列表形式更易于查看。</span><span class="sxs-lookup"><span data-stu-id="0bffc-138">When a registry key contains fewer than five entries, by default it is displayed in a table, but it is often easier to view in a list.</span></span>

<span data-ttu-id="0bffc-139">第二个命令使用相同的 `Get-ItemProperty` 命令。</span><span class="sxs-lookup"><span data-stu-id="0bffc-139">The second command uses the same `Get-ItemProperty` command.</span></span>
<span data-ttu-id="0bffc-140">但这次，该命令使用管道运算符 () 将 `|` 命令的结果发送到 `Format-List` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0bffc-140">However, this time, the command uses a pipeline operator (`|`) to send the results of the command to the `Format-List` cmdlet.</span></span>
<span data-ttu-id="0bffc-141">该 `Format-List` 命令使用值为 "\*" 的属性参数 (所有) 在列表中显示对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="0bffc-141">The `Format-List` command uses the Property parameter with a value of '\*' (all) to display all of the properties of the objects in a list.</span></span>
<span data-ttu-id="0bffc-142">结果显示在下面的示例输出中。</span><span class="sxs-lookup"><span data-stu-id="0bffc-142">The results are shown in the following sample output.</span></span>

<span data-ttu-id="0bffc-143">生成的显示将显示 "路径" 和 "Set-executionpolicy" 注册表项，以及注册表项对象的几个不太熟悉的属性。</span><span class="sxs-lookup"><span data-stu-id="0bffc-143">The resulting display shows the "Path" and "ExecutionPolicy" registry entries, along with several less familiar properties of the registry key object.</span></span>
<span data-ttu-id="0bffc-144">以 PS 为前缀的其他属性是 PowerShell 自定义对象（例如表示注册表项的对象）的属性。</span><span class="sxs-lookup"><span data-stu-id="0bffc-144">The other properties, prefixed with PS, are properties of PowerShell custom objects, such as the objects that represent the registry keys.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## <span data-ttu-id="0bffc-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bffc-145">PARAMETERS</span></span>

### <span data-ttu-id="0bffc-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="0bffc-146">-Credential</span></span>

<span data-ttu-id="0bffc-147">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0bffc-147">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="0bffc-148">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="0bffc-148">The default is the current user.</span></span>

<span data-ttu-id="0bffc-149">键入用户名，如“User01”或“Domain01\User01”；或输入 **PSCredential** 对象，如 `Get-Credential` cmdlet 生成的一个 PSCredential 对象。</span><span class="sxs-lookup"><span data-stu-id="0bffc-149">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="0bffc-150">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="0bffc-150">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="0bffc-151">随同 Windows PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="0bffc-151">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="0bffc-152">-Exclude</span><span class="sxs-lookup"><span data-stu-id="0bffc-152">-Exclude</span></span>

<span data-ttu-id="0bffc-153">指定此 cmdlet 将从操作中排除的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="0bffc-153">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="0bffc-154">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="0bffc-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="0bffc-155">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="0bffc-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="0bffc-156">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0bffc-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0bffc-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="0bffc-157">-Filter</span></span>

<span data-ttu-id="0bffc-158">以提供程序的格式或语言指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="0bffc-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="0bffc-159">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="0bffc-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="0bffc-160">筛选器的语法（包括通配符字符的使用），具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="0bffc-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="0bffc-161">筛选器比其他参数更有效，因为提供程序在 cmdlet 获取对象时应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0bffc-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="0bffc-162">-Include</span><span class="sxs-lookup"><span data-stu-id="0bffc-162">-Include</span></span>

<span data-ttu-id="0bffc-163">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="0bffc-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="0bffc-164">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="0bffc-164">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="0bffc-165">请输入路径元素或模式，例如“\*.txt”。</span><span class="sxs-lookup"><span data-stu-id="0bffc-165">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="0bffc-166">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0bffc-166">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="0bffc-167">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="0bffc-167">-LiteralPath</span></span>

<span data-ttu-id="0bffc-168">指定此属性的当前位置的路径。</span><span class="sxs-lookup"><span data-stu-id="0bffc-168">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="0bffc-169">与 **Path** 参数不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="0bffc-169">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="0bffc-170">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="0bffc-170">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="0bffc-171">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="0bffc-171">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="0bffc-172">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="0bffc-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="0bffc-173">-Name</span><span class="sxs-lookup"><span data-stu-id="0bffc-173">-Name</span></span>

<span data-ttu-id="0bffc-174">指定要检索的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="0bffc-174">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bffc-175">-Path</span><span class="sxs-lookup"><span data-stu-id="0bffc-175">-Path</span></span>

<span data-ttu-id="0bffc-176">指定一个或多个项的路径。</span><span class="sxs-lookup"><span data-stu-id="0bffc-176">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0bffc-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="0bffc-177">-UseTransaction</span></span>

<span data-ttu-id="0bffc-178">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="0bffc-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="0bffc-179">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="0bffc-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="0bffc-180">有关详细信息，请参阅“在活动事务中使用该命令”。</span><span class="sxs-lookup"><span data-stu-id="0bffc-180">For more information, see Includes the command in the active transaction.</span></span>
<span data-ttu-id="0bffc-181">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="0bffc-181">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="0bffc-182">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="0bffc-182">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="0bffc-183">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bffc-183">CommonParameters</span></span>

<span data-ttu-id="0bffc-184">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="0bffc-184">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="0bffc-185">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="0bffc-185">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0bffc-186">输入</span><span class="sxs-lookup"><span data-stu-id="0bffc-186">INPUTS</span></span>

### <span data-ttu-id="0bffc-187">System.String</span><span class="sxs-lookup"><span data-stu-id="0bffc-187">System.String</span></span>

<span data-ttu-id="0bffc-188">可以通过管道将包含路径的字符串传递给 `Get-ItemProperty` 。</span><span class="sxs-lookup"><span data-stu-id="0bffc-188">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="0bffc-189">输出</span><span class="sxs-lookup"><span data-stu-id="0bffc-189">OUTPUTS</span></span>

### <span data-ttu-id="0bffc-190">System.Boolean、System.String、System.DateTime</span><span class="sxs-lookup"><span data-stu-id="0bffc-190">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="0bffc-191">`Get-ItemProperty` 为它获取的每个项属性返回一个对象。</span><span class="sxs-lookup"><span data-stu-id="0bffc-191">`Get-ItemProperty` returns an object for each item property that it gets.</span></span>
<span data-ttu-id="0bffc-192">对象类型取决于检索的对象。</span><span class="sxs-lookup"><span data-stu-id="0bffc-192">The object type depends on the object that is retrieved.</span></span>
<span data-ttu-id="0bffc-193">例如，在文件系统驱动器中，它可能会返回一个文件或文件夹。</span><span class="sxs-lookup"><span data-stu-id="0bffc-193">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="0bffc-194">注释</span><span class="sxs-lookup"><span data-stu-id="0bffc-194">NOTES</span></span>

<span data-ttu-id="0bffc-195">`Get-ItemProperty`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="0bffc-195">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0bffc-196">若要列出会话中可用的提供程序，请键入 " `Get-PSProvider` "。</span><span class="sxs-lookup"><span data-stu-id="0bffc-196">To list the providers available in your session, type "`Get-PSProvider`".</span></span> <span data-ttu-id="0bffc-197">有关详细信息，请参阅 about_Providers。</span><span class="sxs-lookup"><span data-stu-id="0bffc-197">For more information, see about_Providers.</span></span>

## <span data-ttu-id="0bffc-198">相关链接</span><span class="sxs-lookup"><span data-stu-id="0bffc-198">RELATED LINKS</span></span>

[<span data-ttu-id="0bffc-199">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-199">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="0bffc-200">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-200">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="0bffc-201">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-201">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="0bffc-202">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-202">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="0bffc-203">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-203">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="0bffc-204">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-204">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="0bffc-205">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="0bffc-205">Set-ItemProperty</span></span>](Set-ItemProperty.md)
