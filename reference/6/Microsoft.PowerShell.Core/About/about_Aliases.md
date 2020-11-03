---
description: 介绍如何在 PowerShell 中使用 cmdlet 和命令的备用名称。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Aliases
ms.openlocfilehash: 5595c1595a36ebbc6ae7c77afb45f95996815f8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199888"
---
# <a name="about-aliases"></a><span data-ttu-id="86874-104">关于别名</span><span class="sxs-lookup"><span data-stu-id="86874-104">About Aliases</span></span>

## <a name="short-description"></a><span data-ttu-id="86874-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="86874-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="86874-106">介绍如何在 PowerShell 中使用 cmdlet 和命令的备用名称。</span><span class="sxs-lookup"><span data-stu-id="86874-106">Describes how to use alternate names for cmdlets and commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="86874-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="86874-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="86874-108">别名是 cmdlet 或命令元素（例如函数、脚本、文件或可执行文件）的替代名称或昵称。</span><span class="sxs-lookup"><span data-stu-id="86874-108">An alias is an alternate name or nickname for a cmdlet or for a command element, such as a function, script, file, or executable file.</span></span> <span data-ttu-id="86874-109">可以在任何 PowerShell 命令中使用别名，而不是命令名。</span><span class="sxs-lookup"><span data-stu-id="86874-109">You can use the alias instead of the command name in any PowerShell commands.</span></span>

<span data-ttu-id="86874-110">若要创建别名，请使用 New-Alias cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86874-110">To create an alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="86874-111">例如，以下命令为 cmdlet 创建 "气体" 别名 `Get-AuthenticodeSignature` ：</span><span class="sxs-lookup"><span data-stu-id="86874-111">For example, the following command creates the "gas" alias for the `Get-AuthenticodeSignature` cmdlet:</span></span>

```powershell
New-Alias -Name gas -Value Get-AuthenticodeSignature
```

<span data-ttu-id="86874-112">为 cmdlet 名称创建别名后，可以使用别名，而不是 cmdlet 名称。</span><span class="sxs-lookup"><span data-stu-id="86874-112">After you create the alias for the cmdlet name, you can use the alias instead of the cmdlet name.</span></span> <span data-ttu-id="86874-113">例如，若要获取 SqlScript.ps1 文件的 Authenticode 签名，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-113">For example, to get the Authenticode signature for the SqlScript.ps1 file, type:</span></span>

```powershell
Get-AuthenticodeSignature SqlScript.ps1
```

<span data-ttu-id="86874-114">或者键入：</span><span class="sxs-lookup"><span data-stu-id="86874-114">Or, type:</span></span>

```powershell
gas SqlScript.ps1
```

<span data-ttu-id="86874-115">如果创建 "word" 作为 Microsoft Office Word 的别名，则可以键入 "word" 而不是以下内容：</span><span class="sxs-lookup"><span data-stu-id="86874-115">If you create "word" as the alias for Microsoft Office Word, you can type "word" instead of the following:</span></span>

```powershell
"C:\Program Files\Microsoft Office\Office11\Winword.exe"
```

## <a name="built-in-aliases"></a><span data-ttu-id="86874-116">内置别名</span><span class="sxs-lookup"><span data-stu-id="86874-116">BUILT-IN ALIASES</span></span>

<span data-ttu-id="86874-117">PowerShell 包括一组内置别名，其中包括用于 Set-Location cmdlet 的 "cd" 和 "chdir"，以及 Get-ChildItem cmdlet 的 "ls" 和 "dir"。</span><span class="sxs-lookup"><span data-stu-id="86874-117">PowerShell includes a set of built-in aliases, including "cd" and "chdir" for the Set-Location cmdlet, and "ls" and "dir" for the Get-ChildItem cmdlet.</span></span>

<span data-ttu-id="86874-118">若要获取计算机上的所有别名（包括内置的别名），请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-118">To get all the aliases on the computer, including the built-in aliases, type:</span></span>

```powershell
Get-Alias
```

## <a name="alias-cmdlets"></a><span data-ttu-id="86874-119">别名 CMDLET</span><span class="sxs-lookup"><span data-stu-id="86874-119">ALIAS CMDLETS</span></span>

<span data-ttu-id="86874-120">PowerShell 包含以下 cmdlet，这些 cmdlet 设计用于使用别名：</span><span class="sxs-lookup"><span data-stu-id="86874-120">PowerShell includes the following cmdlets, which are designed for working with aliases:</span></span>

- <span data-ttu-id="86874-121">`Get-Alias` -获取当前会话中的所有别名。</span><span class="sxs-lookup"><span data-stu-id="86874-121">`Get-Alias` - Gets all the aliases in the current session.</span></span>
- <span data-ttu-id="86874-122">`New-Alias` -创建新别名。</span><span class="sxs-lookup"><span data-stu-id="86874-122">`New-Alias` - Creates a new alias.</span></span>
- <span data-ttu-id="86874-123">`Set-Alias` -创建或更改别名。</span><span class="sxs-lookup"><span data-stu-id="86874-123">`Set-Alias` - Creates or changes an alias.</span></span>
- <span data-ttu-id="86874-124">`Export-Alias` -将一个或多个别名导出到文件。</span><span class="sxs-lookup"><span data-stu-id="86874-124">`Export-Alias` - Exports one or more aliases to a file.</span></span>
- <span data-ttu-id="86874-125">`Import-Alias` -将别名文件导入 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="86874-125">`Import-Alias` - Imports an alias file into PowerShell.</span></span>

<span data-ttu-id="86874-126">有关 cmdlet 的详细信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-126">For detailed information about the cmdlets, type:</span></span>

```powershell
Get-Help <cmdlet-Name> -Detailed
```

<span data-ttu-id="86874-127">例如，键入：</span><span class="sxs-lookup"><span data-stu-id="86874-127">For example, type:</span></span>

```powershell
Get-Help Export-Alias -Detailed
```

## <a name="creating-an-alias"></a><span data-ttu-id="86874-128">创建别名</span><span class="sxs-lookup"><span data-stu-id="86874-128">CREATING AN ALIAS</span></span>

<span data-ttu-id="86874-129">若要创建新别名，请使用 New-Alias cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86874-129">To create a new alias, use the New-Alias cmdlet.</span></span> <span data-ttu-id="86874-130">例如，若要创建 Get-help 的 "gh" 别名，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-130">For example, to create the "gh" alias for Get-Help, type:</span></span>

```powershell
New-Alias -Name gh -Value Get-Help
```

<span data-ttu-id="86874-131">您可以使用命令中的别名，就像使用完整的 cmdlet 名称一样，可以将别名用于参数。</span><span class="sxs-lookup"><span data-stu-id="86874-131">You can use the alias in commands, just as you would use the full cmdlet name, and you can use the alias with parameters.</span></span>

<span data-ttu-id="86874-132">例如，若要获取 Get-WmiObject cmdlet 的详细帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-132">For example, to get detailed Help for the Get-WmiObject cmdlet, type:</span></span>

```powershell
Get-Help Get-WmiObject -Detailed
```

<span data-ttu-id="86874-133">或者键入：</span><span class="sxs-lookup"><span data-stu-id="86874-133">Or, type:</span></span>

```powershell
gh Get-WmiObject -Detailed
```

## <a name="saving-aliases"></a><span data-ttu-id="86874-134">保存别名</span><span class="sxs-lookup"><span data-stu-id="86874-134">SAVING ALIASES</span></span>

<span data-ttu-id="86874-135">你创建的别名仅保存在当前会话中。</span><span class="sxs-lookup"><span data-stu-id="86874-135">The aliases that you create are saved only in the current session.</span></span> <span data-ttu-id="86874-136">若要在其他会话中使用别名，请将别名添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="86874-136">To use the aliases in a different session, add the alias to your PowerShell profile.</span></span> <span data-ttu-id="86874-137">或者使用 Export-Alias cmdlet 将别名保存到文件。</span><span class="sxs-lookup"><span data-stu-id="86874-137">Or, use the Export-Alias cmdlet to save the aliases to a file.</span></span>

<span data-ttu-id="86874-138">有关详细信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-138">For more information, type:</span></span>

```powershell
Get-Help about_Profiles
```

## <a name="getting-aliases"></a><span data-ttu-id="86874-139">获取别名</span><span class="sxs-lookup"><span data-stu-id="86874-139">GETTING ALIASES</span></span>

<span data-ttu-id="86874-140">若要获取当前会话中的所有别名（包括内置别名、PowerShell 配置文件中的别名以及在当前会话中创建的别名），请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-140">To get all the aliases in the current session, including the built-in aliases, the aliases in your PowerShell profiles, and the aliases that you have created in the current session, type:</span></span>

```powershell
Get-Alias
```

<span data-ttu-id="86874-141">若要获取特定别名，请使用 Get-Alias cmdlet 的 Name 参数。</span><span class="sxs-lookup"><span data-stu-id="86874-141">To get particular aliases, use the Name parameter of the Get-Alias cmdlet.</span></span> <span data-ttu-id="86874-142">例如，若要获取以 "p" 开头的别名，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-142">For example, to get aliases that begin with "p", type:</span></span>

```powershell
Get-Alias -Name p*
```

<span data-ttu-id="86874-143">若要获取特定项的别名，请使用定义参数。</span><span class="sxs-lookup"><span data-stu-id="86874-143">To get the aliases for a particular item, use the Definition parameter.</span></span> <span data-ttu-id="86874-144">例如，若要获取 Get-ChildItem cmdlet 类型的别名：</span><span class="sxs-lookup"><span data-stu-id="86874-144">For example, to get the aliases for the Get-ChildItem cmdlet type:</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

### <a name="get-alias-output"></a><span data-ttu-id="86874-145">获取别名输出</span><span class="sxs-lookup"><span data-stu-id="86874-145">GET-ALIAS OUTPUT</span></span>

<span data-ttu-id="86874-146">Get-Alias 仅返回一种类型的对象，System.management.automation.aliasinfo) 的 System.management.automation.aliasinfo (对象。</span><span class="sxs-lookup"><span data-stu-id="86874-146">Get-Alias returns only one type of object, an AliasInfo object (System.Management.Automation.AliasInfo).</span></span> <span data-ttu-id="86874-147">不包含连字符的别名名称（如 "cd"）将按以下格式显示：</span><span class="sxs-lookup"><span data-stu-id="86874-147">The name of aliases that don't include a hyphen, such as "cd" are displayed in the following format:</span></span>

```powershell
Get-Alias ac
```

```Output
CommandType     Name                    Version    Source
-----------     ----                    -------    ------
Alias           ac -> Add-Content
```

<span data-ttu-id="86874-148">这样，就可以非常快捷地获取所需的信息。</span><span class="sxs-lookup"><span data-stu-id="86874-148">This makes it very quick and easy to get the information that you need.</span></span>

<span data-ttu-id="86874-149">基于箭头的别名名称格式不适用于含有连字符的别名。</span><span class="sxs-lookup"><span data-stu-id="86874-149">The arrow-based alias name format is not used for aliases that include a hyphen.</span></span> <span data-ttu-id="86874-150">它们可能是 cmdlet 和函数（而不是典型的缩写或昵称）的首选替代名称，并且作者可能不希望它们明显。</span><span class="sxs-lookup"><span data-stu-id="86874-150">These are likely to be preferred substitute names for cmdlets and functions, instead of typical abbreviations or nicknames, and the author might not want them to be as evident.</span></span>

## <a name="alternate-names-for-commands-with-parameters"></a><span data-ttu-id="86874-151">带参数的命令的替换名称</span><span class="sxs-lookup"><span data-stu-id="86874-151">ALTERNATE NAMES FOR COMMANDS WITH PARAMETERS</span></span>

<span data-ttu-id="86874-152">可以为 cmdlet、脚本、函数或可执行文件指定别名。</span><span class="sxs-lookup"><span data-stu-id="86874-152">You can assign an alias to a cmdlet, script, function, or executable file.</span></span> <span data-ttu-id="86874-153">不能为命令及其参数分配别名。</span><span class="sxs-lookup"><span data-stu-id="86874-153">You cannot assign an alias to a command and its parameters.</span></span> <span data-ttu-id="86874-154">例如，可以将别名分配给该 `Get-Eventlog` cmdlet，但不能为该命令分配别名 `Get-Eventlog -LogName System` 。</span><span class="sxs-lookup"><span data-stu-id="86874-154">For example, you can assign an alias to the `Get-Eventlog` cmdlet, but you cannot assign an alias to the `Get-Eventlog -LogName System` command.</span></span>

<span data-ttu-id="86874-155">你可以创建包含命令的函数。</span><span class="sxs-lookup"><span data-stu-id="86874-155">You can create a function that includes the command.</span></span> <span data-ttu-id="86874-156">若要创建函数，请键入单词 "function"，后跟函数的名称。</span><span class="sxs-lookup"><span data-stu-id="86874-156">To create a function, type the word "function" followed by a name for the function.</span></span> <span data-ttu-id="86874-157">键入命令，并将其括在大括号中， ({}) 。</span><span class="sxs-lookup"><span data-stu-id="86874-157">Type the command, and enclose it in braces ({}).</span></span>

<span data-ttu-id="86874-158">例如，以下命令将创建 syslog 函数。</span><span class="sxs-lookup"><span data-stu-id="86874-158">For example, the following command creates the syslog function.</span></span> <span data-ttu-id="86874-159">此函数表示 `Get-Eventlog -LogName System` 命令：</span><span class="sxs-lookup"><span data-stu-id="86874-159">This function represents the `Get-Eventlog -LogName System` command:</span></span>

```powershell
function Get-SystemEventlog {Get-Eventlog -LogName System}
Set-Alias -Name syslog -Value Get-SystemEventlog
```

<span data-ttu-id="86874-160">现在可以键入 "syslog" 而不是命令。</span><span class="sxs-lookup"><span data-stu-id="86874-160">You can now type "syslog" instead of the command.</span></span> <span data-ttu-id="86874-161">而且，你可以为新函数创建别名。</span><span class="sxs-lookup"><span data-stu-id="86874-161">And, you can create aliases for the new function.</span></span>

<span data-ttu-id="86874-162">有关函数的详细信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-162">For more information about functions, type:</span></span>

```powershell
Get-Help about_Functions
```

## <a name="alias-objects"></a><span data-ttu-id="86874-163">别名对象</span><span class="sxs-lookup"><span data-stu-id="86874-163">ALIAS OBJECTS</span></span>

<span data-ttu-id="86874-164">PowerShell 别名由作为 System.management.automation.aliasinfo 类的实例的对象表示。</span><span class="sxs-lookup"><span data-stu-id="86874-164">PowerShell aliases are represented by objects that are instances of the System.Management.Automation.AliasInfo class.</span></span> <span data-ttu-id="86874-165">有关此类对象的详细信息，请参阅 Microsoft Developer Network (MSDN) 库中的 [System.management.automation.aliasinfo 类][aliasinfo] 。</span><span class="sxs-lookup"><span data-stu-id="86874-165">For more information about this type of object, see [AliasInfo Class][aliasinfo] in the Microsoft Developer Network (MSDN) library.</span></span>

<span data-ttu-id="86874-166">若要查看 alias 对象的属性和方法，请获取别名。</span><span class="sxs-lookup"><span data-stu-id="86874-166">To view the properties and methods of the alias objects, get the aliases.</span></span>
<span data-ttu-id="86874-167">然后，将它们传递给 Get-Member cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86874-167">Then, pipe them to the Get-Member cmdlet.</span></span> <span data-ttu-id="86874-168">例如：</span><span class="sxs-lookup"><span data-stu-id="86874-168">For example:</span></span>

```powershell
Get-Alias | Get-Member
```

<span data-ttu-id="86874-169">若要查看特定别名的属性值（如 `dir` 别名），请获取别名。</span><span class="sxs-lookup"><span data-stu-id="86874-169">To view the values of the properties of a specific alias, such as the `dir` alias, get the alias.</span></span> <span data-ttu-id="86874-170">然后，通过管道将它传递给 Format-List cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86874-170">Then, pipe it to the Format-List cmdlet.</span></span> <span data-ttu-id="86874-171">例如，以下命令将获取 "dir" 别名。</span><span class="sxs-lookup"><span data-stu-id="86874-171">For example, the following command gets the "dir" alias.</span></span> <span data-ttu-id="86874-172">接下来，该命令通过管道将别名传输到 Format-List cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86874-172">Next, the command pipes the alias to the Format-List cmdlet.</span></span> <span data-ttu-id="86874-173">然后，该命令将 Format-List 的属性参数与通配符 (\*) ，以显示该别名的所有属性 `dir` 。</span><span class="sxs-lookup"><span data-stu-id="86874-173">Then, the command uses the Property parameter of Format-List with a wildcard character (\*) to display all the properties of the `dir` alias.</span></span> <span data-ttu-id="86874-174">以下命令执行这些任务：</span><span class="sxs-lookup"><span data-stu-id="86874-174">The following command performs these tasks:</span></span>

```powershell
Get-Alias -Name dir | Format-List -Property *
```

## <a name="powershell-alias-provider"></a><span data-ttu-id="86874-175">PowerShell 别名提供程序</span><span class="sxs-lookup"><span data-stu-id="86874-175">PowerShell ALIAS PROVIDER</span></span>

<span data-ttu-id="86874-176">PowerShell 包含别名提供程序。</span><span class="sxs-lookup"><span data-stu-id="86874-176">PowerShell includes the Alias provider.</span></span> <span data-ttu-id="86874-177">别名提供程序允许你查看 PowerShell 中的别名，就好像它们位于文件系统驱动器上一样。</span><span class="sxs-lookup"><span data-stu-id="86874-177">The Alias provider lets you view the aliases in PowerShell as though they were on a file system drive.</span></span>

<span data-ttu-id="86874-178">别名提供程序公开 Alias：驱动器。</span><span class="sxs-lookup"><span data-stu-id="86874-178">The Alias provider exposes the Alias: drive.</span></span> <span data-ttu-id="86874-179">若要进入 Alias：驱动器，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-179">To go into the Alias: drive, type:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="86874-180">若要查看驱动器的内容，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-180">To view the contents of the drive, type:</span></span>

```powershell
Get-ChildItem
```

<span data-ttu-id="86874-181">若要查看另一 PowerShell 驱动器中的驱动器内容，请以驱动器名称开头。</span><span class="sxs-lookup"><span data-stu-id="86874-181">To view the contents of the drive from another PowerShell drive, begin the path with the drive name.</span></span> <span data-ttu-id="86874-182">包括冒号 (： ) 。</span><span class="sxs-lookup"><span data-stu-id="86874-182">Include the colon (:).</span></span> <span data-ttu-id="86874-183">例如：</span><span class="sxs-lookup"><span data-stu-id="86874-183">For example:</span></span>

```powershell
Get-ChildItem -Path Alias:
```

<span data-ttu-id="86874-184">若要获取有关特定别名的信息，请键入驱动器名称和别名。</span><span class="sxs-lookup"><span data-stu-id="86874-184">To get information about a particular alias, type the drive name and the alias name.</span></span> <span data-ttu-id="86874-185">或者，键入名称模式。</span><span class="sxs-lookup"><span data-stu-id="86874-185">Or, type a name pattern.</span></span> <span data-ttu-id="86874-186">例如，若要获取以 "p" 开头的所有别名，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-186">For example, to get all the aliases that begin with "p", type:</span></span>

```powershell
Get-ChildItem -Path Alias:p*
```

<span data-ttu-id="86874-187">有关 PowerShell 别名提供程序的详细信息，请键入：</span><span class="sxs-lookup"><span data-stu-id="86874-187">For more information about the PowerShell Alias provider, type:</span></span>

```powershell
Get-Help Alias
```

## <a name="see-also"></a><span data-ttu-id="86874-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86874-188">SEE ALSO</span></span>

- [<span data-ttu-id="86874-189">New-Alias</span><span class="sxs-lookup"><span data-stu-id="86874-189">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="86874-190">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="86874-190">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="86874-191">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="86874-191">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)
- [<span data-ttu-id="86874-192">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="86874-192">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="86874-193">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="86874-193">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="86874-194">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="86874-194">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)
- [<span data-ttu-id="86874-195">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="86874-195">Get-PSDrive</span></span>](xref:Microsoft.PowerShell.Management.Get-PSDrive)
- [<span data-ttu-id="86874-196">about_functions</span><span class="sxs-lookup"><span data-stu-id="86874-196">about_functions</span></span>](about_functions.md)
- [<span data-ttu-id="86874-197">about_profiles</span><span class="sxs-lookup"><span data-stu-id="86874-197">about_profiles</span></span>](about_profiles.md)
- [<span data-ttu-id="86874-198">about_providers</span><span class="sxs-lookup"><span data-stu-id="86874-198">about_providers</span></span>](about_providers.md)

<!-- External links -->
[aliasinfo]: /dotnet/api/system.management.automation.aliasinfo
