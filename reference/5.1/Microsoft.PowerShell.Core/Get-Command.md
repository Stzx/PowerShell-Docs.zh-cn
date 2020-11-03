---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: daa58a732dafb11fa8f6ce3c20965aebcce55844
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197444"
---
# <span data-ttu-id="9585f-103">Get-Command</span><span class="sxs-lookup"><span data-stu-id="9585f-103">Get-Command</span></span>

## <span data-ttu-id="9585f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9585f-104">SYNOPSIS</span></span>
<span data-ttu-id="9585f-105">获取所有命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-105">Gets all commands.</span></span>

## <span data-ttu-id="9585f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9585f-106">SYNTAX</span></span>

### <span data-ttu-id="9585f-107">CmdletSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="9585f-107">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="9585f-108">AllCommandSet</span><span class="sxs-lookup"><span data-stu-id="9585f-108">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-CommandType <CommandTypes>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>]
 [-All] [-ListImported] [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

## <span data-ttu-id="9585f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9585f-109">DESCRIPTION</span></span>

<span data-ttu-id="9585f-110">该 `Get-Command` cmdlet 将获取安装在计算机上的所有命令，包括 cmdlet、别名、函数、筛选器、脚本和应用程序。</span><span class="sxs-lookup"><span data-stu-id="9585f-110">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="9585f-111">`Get-Command` 从 PowerShell 模块中获取命令，以及从其他会话导入的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-111">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="9585f-112">若要仅获取已导入到当前会话中的命令，请使用 **ListImported** 参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-112">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="9585f-113">如果没有参数，则将 `Get-Command` 获取计算机上安装的所有 cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-113">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="9585f-114">`Get-Command *` 获取所有类型的命令，包括 Path 环境变量中的所有非 PowerShell 文件 (`$env:Path`) ，它将在应用程序命令类型中列出。</span><span class="sxs-lookup"><span data-stu-id="9585f-114">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="9585f-115">`Get-Command` 如果使用命令的确切名称（不包含通配符），则会自动导入包含命令的模块，以便你可以立即使用命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-115">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="9585f-116">若要启用、禁用和配置模块的自动导入，请使用 `$PSModuleAutoLoadingPreference` 首选项变量。</span><span class="sxs-lookup"><span data-stu-id="9585f-116">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="9585f-117">有关详细信息，请参阅 [about_Preference_Variables](About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-117">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="9585f-118">`Get-Command` 直接从命令代码获取其数据，这不同于 `Get-Help` ，它从帮助主题中获取其信息。</span><span class="sxs-lookup"><span data-stu-id="9585f-118">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="9585f-119">从 Windows PowerShell 5.0 开始， `Get-Command` 默认情况下，cmdlet 的结果显示 **版本** 列。</span><span class="sxs-lookup"><span data-stu-id="9585f-119">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="9585f-120">新 **版本** 属性已添加到 **CommandInfo** 类。</span><span class="sxs-lookup"><span data-stu-id="9585f-120">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="9585f-121">示例</span><span class="sxs-lookup"><span data-stu-id="9585f-121">EXAMPLES</span></span>

### <span data-ttu-id="9585f-122">示例1：获取 cmdlet、函数和别名</span><span class="sxs-lookup"><span data-stu-id="9585f-122">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="9585f-123">此命令将获取安装在计算机上的 PowerShell cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-123">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="9585f-124">示例2：获取当前会话中的命令</span><span class="sxs-lookup"><span data-stu-id="9585f-124">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="9585f-125">此命令使用 **ListImported** 参数来仅获取当前会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-125">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="9585f-126">示例3：获取 cmdlet 并按顺序显示</span><span class="sxs-lookup"><span data-stu-id="9585f-126">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="9585f-127">此命令将获取所有的 cmdlet、通过 cmdlet 名称中的名词按字母顺序对其进行排序，然后将其显示在基于名词的组中。</span><span class="sxs-lookup"><span data-stu-id="9585f-127">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="9585f-128">此显示内容可帮助你在任务中查找 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-128">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="9585f-129">示例4：获取模块中的命令</span><span class="sxs-lookup"><span data-stu-id="9585f-129">Example 4: Get commands in a module</span></span>

<span data-ttu-id="9585f-130">此命令使用 **Module** 参数来获取 Microsoft. Security 和 Microsoft. Utility 模块中的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-130">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="9585f-131">示例5：获取有关 cmdlet 的信息</span><span class="sxs-lookup"><span data-stu-id="9585f-131">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="9585f-132">此命令获取有关 cmdlet 的信息 `Get-AppLockerPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="9585f-132">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="9585f-133">它还会导入 **AppLocker** 模块，该模块可将 **AppLocker** 模块中的所有命令添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="9585f-133">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="9585f-134">自动导入模块后，效果与使用 Import-Module cmdlet 相同。</span><span class="sxs-lookup"><span data-stu-id="9585f-134">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="9585f-135">该模块可以添加命令、类型和格式设置文件，并在会话中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="9585f-135">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="9585f-136">若要启用、禁用和配置自动导入模块，请使用 `$PSModuleAutoLoadingPreference` 首选项变量。</span><span class="sxs-lookup"><span data-stu-id="9585f-136">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="9585f-137">有关详细信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-137">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="9585f-138">示例6：获取 cmdlet 的语法</span><span class="sxs-lookup"><span data-stu-id="9585f-138">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="9585f-139">**Syntax** 当在 Cert： **ArgumentList** `Get-ChildItem` 驱动器中使用 cmdlet 时，此命令将使用 ArgumentList 和句法参数获取该 cmdlet 的语法。</span><span class="sxs-lookup"><span data-stu-id="9585f-139">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="9585f-140">Cert：驱动器是证书提供程序添加到会话中的 PowerShell 驱动器。</span><span class="sxs-lookup"><span data-stu-id="9585f-140">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="9585f-141">当你将输出中显示的语法与省略 **Args** ( **ArgumentList** ) 参数时显示的语法进行比较时，你会看到 **证书提供程序** 将动态参数 **CodeSigningCert** 添加到 `Get-ChildItem` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-141">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** ( **ArgumentList** ) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert** , to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="9585f-142">有关证书提供程序的详细信息，请参阅 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-142">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="9585f-143">示例7：获取动态参数</span><span class="sxs-lookup"><span data-stu-id="9585f-143">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="9585f-144">该示例中的命令使用 `Get-DynamicParameters` 函数获取证书提供程序在证书 `Get-ChildItem` ：驱动器中使用时添加到 cmdlet 的动态参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-144">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="9585f-145">`Get-DynamicParameters`此示例中的函数获取 cmdlet 的动态参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-145">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="9585f-146">这是上一示例中所用方法的替代方法。</span><span class="sxs-lookup"><span data-stu-id="9585f-146">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="9585f-147">可以通过另一个 cmdlet 或提供程序将 Dynamic 参数添加到 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-147">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="9585f-148">示例8：获取所有类型的所有命令</span><span class="sxs-lookup"><span data-stu-id="9585f-148">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="9585f-149">此命令将获取本地计算机上所有类型的所有命令，包括 **Path** 环境变量路径中的可执行文件 (`$env:path`) 。</span><span class="sxs-lookup"><span data-stu-id="9585f-149">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="9585f-150">它将为每个文件返回一个 **ApplicationInfo** 对象 (System.Management.Automation.ApplicationInfo)，而不是 **FileInfo** 对象 (System.IO.FileInfo)。</span><span class="sxs-lookup"><span data-stu-id="9585f-150">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="9585f-151">示例9：使用参数名称和类型获取 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9585f-151">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="9585f-152">此命令将获取其名称包含 authentication 且类型为 **system.management.automation.runspaces.authenticationmechanism** 的参数的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-152">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism** .</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="9585f-153">可以使用类似此命令的命令查找允许你指定用于对用户进行身份验证的方法的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-153">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="9585f-154">即使采用 **AuthenticationMechanism** 值的参数和采用 **AuthenticationLevel** 参数的参数具有类似名称， **ParameterType** 参数也可区分它们。</span><span class="sxs-lookup"><span data-stu-id="9585f-154">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="9585f-155">示例10：获取别名</span><span class="sxs-lookup"><span data-stu-id="9585f-155">Example 10: Get an alias</span></span>

<span data-ttu-id="9585f-156">此示例演示如何使用 `Get-Command` 带有别名的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-156">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="9585f-157">虽然它通常用于 cmdlet 和函数，但 `Get-Command` 也可获取脚本、函数、别名和可执行文件。</span><span class="sxs-lookup"><span data-stu-id="9585f-157">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="9585f-158">命令的输出将显示别名的 **Name** 属性值的特殊视图。</span><span class="sxs-lookup"><span data-stu-id="9585f-158">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="9585f-159">该视图将显示别名以及完整的命令名称。</span><span class="sxs-lookup"><span data-stu-id="9585f-159">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="9585f-160">示例11：获取记事本命令的所有实例</span><span class="sxs-lookup"><span data-stu-id="9585f-160">Example 11: Get all instances of the Notepad command</span></span>

<span data-ttu-id="9585f-161">此示例使用 cmdlet 的 **all** 参数 `Get-Command` 显示本地计算机上 "Notepad" 命令的所有实例。</span><span class="sxs-lookup"><span data-stu-id="9585f-161">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the "Notepad" command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="9585f-162">当会话中的多个命令具有相同名称时， **All** 参数非常有用。</span><span class="sxs-lookup"><span data-stu-id="9585f-162">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="9585f-163">从 Windows PowerShell 3.0 开始，默认情况下，当会话中包含具有相同名称的多个命令时， `Get-Command` 仅获取键入命令名称时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-163">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="9585f-164">对于 **all** 参数， `Get-Command` 获取具有指定名称的所有命令，并按执行优先级顺序返回它们。</span><span class="sxs-lookup"><span data-stu-id="9585f-164">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="9585f-165">若要运行除列表中第一个命令以外的某个命令，请键入该命令的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="9585f-165">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="9585f-166">有关命令优先级的详细信息，请参阅 [about_Command_Precedence](About/about_Command_Precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-166">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="9585f-167">示例12：获取包含 cmdlet 的模块的名称</span><span class="sxs-lookup"><span data-stu-id="9585f-167">Example 12: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="9585f-168">此命令获取该 cmdlet 所源自的模块的名称 `Get-Date` 。</span><span class="sxs-lookup"><span data-stu-id="9585f-168">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="9585f-169">该命令使用所有命令的 **ModuleName** 属性。</span><span class="sxs-lookup"><span data-stu-id="9585f-169">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="9585f-170">此命令格式适用于 PowerShell 模块中的命令，即使未将它们导入到会话中也是如此。</span><span class="sxs-lookup"><span data-stu-id="9585f-170">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="9585f-171">示例13：获取具有输出类型的 cmdlet 和函数</span><span class="sxs-lookup"><span data-stu-id="9585f-171">Example 13: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="9585f-172">此命令将获取具有输出类型及其返回的对象类型的 cmdlet 和函数。</span><span class="sxs-lookup"><span data-stu-id="9585f-172">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="9585f-173">该命令的第一部分将获取所有 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-173">The first part of the command gets all cmdlets.</span></span>
<span data-ttu-id="9585f-174">管道运算符 (|) 将 cmdlet 发送到 `Where-Object` cmdlet，该 cmdlet 只选择在其中填充 **OutputType** 属性的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-174">A pipeline operator (|) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span>
<span data-ttu-id="9585f-175">另一个管道运算符将选定的 cmdlet 对象发送到 `Format-List` cmdlet，该 cmdlet 将在列表中显示每个 cmdlet 的名称和输出类型。</span><span class="sxs-lookup"><span data-stu-id="9585f-175">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="9585f-176">仅当 cmdlet 代码为 cmdlet 定义了 **OutputType** 属性时， **CommandInfo** 对象的 **OutputType** 属性的值才为非 null。</span><span class="sxs-lookup"><span data-stu-id="9585f-176">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="9585f-177">示例14：获取采用特定对象类型作为输入的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9585f-177">Example 14: Get cmdlets that take a specific object type as input</span></span>

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

<span data-ttu-id="9585f-178">此命令可查找将网络适配器对象用作输入的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-178">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="9585f-179">可以使用此命令格式查找接受任何命令返回的对象类型的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-179">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="9585f-180">该命令使用所有对象的 **PSTypeNames** 内部属性，它将获取用于描述该对象的类型。</span><span class="sxs-lookup"><span data-stu-id="9585f-180">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="9585f-181">若要获取网络适配器的 **PSTypeNames** 属性，而不是网络适配器集合的 **PSTypeNames** 属性，该命令将使用数组表示法来获取该 cmdlet 返回的第一个网络适配器。</span><span class="sxs-lookup"><span data-stu-id="9585f-181">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>
<span data-ttu-id="9585f-182">若要获取网络适配器的 **PSTypeNames** 属性，而不是网络适配器集合的 **PSTypeNames** 属性，该命令将使用数组表示法来获取该 cmdlet 返回的第一个网络适配器。</span><span class="sxs-lookup"><span data-stu-id="9585f-182">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

## <span data-ttu-id="9585f-183">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9585f-183">PARAMETERS</span></span>

### <span data-ttu-id="9585f-184">-All</span><span class="sxs-lookup"><span data-stu-id="9585f-184">-All</span></span>

<span data-ttu-id="9585f-185">指示此 cmdlet 获取所有命令，包括具有相同名称的相同类型的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-185">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="9585f-186">默认情况下， `Get-Command` 仅获取键入命令名称时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-186">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="9585f-187">有关当多个命令具有相同名称时 PowerShell 用于选择要运行的命令的方法的详细信息，请参阅 [about_Command_Precedence](About/about_Command_Precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-187">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="9585f-188">有关由于名称冲突而默认情况下不会运行的模块限定命令名称和运行命令的信息，请参阅 [about_Modules](About/about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-188">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="9585f-189">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-189">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="9585f-190">在 Windows PowerShell 2.0 中， `Get-Command` 默认情况下获取所有命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-190">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9585f-191">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="9585f-191">-ArgumentList</span></span>

<span data-ttu-id="9585f-192">指定参数数组。</span><span class="sxs-lookup"><span data-stu-id="9585f-192">Specifies an array of arguments.</span></span> <span data-ttu-id="9585f-193">此 cmdlet 将获取有关 cmdlet 或函数的信息，与指定参数一起使用时， ( "arguments" ) 。</span><span class="sxs-lookup"><span data-stu-id="9585f-193">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="9585f-194">**ArgumentList** 的别名是 **Args** 。</span><span class="sxs-lookup"><span data-stu-id="9585f-194">The alias for **ArgumentList** is **Args** .</span></span>

<span data-ttu-id="9585f-195">若要检测仅当使用某些其他参数时才可用的动态参数，请将 **ArgumentList** 的值设置为触发动态参数的参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-195">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="9585f-196">若要检测提供程序添加到 cmdlet 的动态参数，请将 **ArgumentList** 参数的值设置为提供程序驱动器中的路径，例如 WSMan：、HKLM：或 Cert：。</span><span class="sxs-lookup"><span data-stu-id="9585f-196">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="9585f-197">如果命令是 PowerShell 提供程序 cmdlet，请在每个命令中仅输入一个路径。</span><span class="sxs-lookup"><span data-stu-id="9585f-197">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="9585f-198">提供程序 cmdlet 只为第一个路径返回值为 **ArgumentList** 的动态参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-198">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList** .</span></span> <span data-ttu-id="9585f-199">有关提供程序 cmdlet 的信息，请参阅 [about_Providers](About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-199">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9585f-200">-CommandType</span><span class="sxs-lookup"><span data-stu-id="9585f-200">-CommandType</span></span>

<span data-ttu-id="9585f-201">指定此 cmdlet 获取的命令类型。</span><span class="sxs-lookup"><span data-stu-id="9585f-201">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="9585f-202">输入一个或多个命令类型。</span><span class="sxs-lookup"><span data-stu-id="9585f-202">Enter one or more command types.</span></span> <span data-ttu-id="9585f-203">使用 **CommandType** 或其别名 **Type** 。</span><span class="sxs-lookup"><span data-stu-id="9585f-203">Use **CommandType** or its alias, **Type** .</span></span> <span data-ttu-id="9585f-204">默认情况下，将 `Get-Command` 获取所有 cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-204">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="9585f-205">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="9585f-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9585f-206">A.</span><span class="sxs-lookup"><span data-stu-id="9585f-206">Alias.</span></span> <span data-ttu-id="9585f-207">获取所有 PowerShell 命令的别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-207">Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="9585f-208">有关详细信息，请参阅 [about_Aliases](About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-208">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="9585f-209">全部。</span><span class="sxs-lookup"><span data-stu-id="9585f-209">All.</span></span> <span data-ttu-id="9585f-210">获取所有命令类型。</span><span class="sxs-lookup"><span data-stu-id="9585f-210">Gets all command types.</span></span> <span data-ttu-id="9585f-211">此参数值等效于 `Get-Command *` 。</span><span class="sxs-lookup"><span data-stu-id="9585f-211">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="9585f-212">应用程序。</span><span class="sxs-lookup"><span data-stu-id="9585f-212">Application.</span></span> <span data-ttu-id="9585f-213">获取 **Path** 环境变量中列出的路径中的非 PowerShell 文件 ($env:p a) ，包括 .txt、.exe 和 .dll 文件。</span><span class="sxs-lookup"><span data-stu-id="9585f-213">Gets non-PowerShell files in paths listed in the **Path** environment variable ($env:path), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="9585f-214">有关 **Path** 环境变量的详细信息，请参阅 about_Environment_Variables。</span><span class="sxs-lookup"><span data-stu-id="9585f-214">For more information about the **Path** environment variable, see about_Environment_Variables.</span></span>
- <span data-ttu-id="9585f-215">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9585f-215">Cmdlet.</span></span> <span data-ttu-id="9585f-216">获取所有 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-216">Gets all cmdlets.</span></span>
- <span data-ttu-id="9585f-217">ExternalScript.</span><span class="sxs-lookup"><span data-stu-id="9585f-217">ExternalScript.</span></span> <span data-ttu-id="9585f-218">获取在 **Path** 环境变量 ($env:path) 中列出的路径中的所有 .ps1 文件。</span><span class="sxs-lookup"><span data-stu-id="9585f-218">Gets all .ps1 files in the paths listed in the **Path** environment variable ($env:path).</span></span>
- <span data-ttu-id="9585f-219">Filter 和 Function。</span><span class="sxs-lookup"><span data-stu-id="9585f-219">Filter and Function.</span></span> <span data-ttu-id="9585f-220">获取所有 PowerShell 高级和简单函数和筛选器。</span><span class="sxs-lookup"><span data-stu-id="9585f-220">Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="9585f-221">脚本。</span><span class="sxs-lookup"><span data-stu-id="9585f-221">Script.</span></span> <span data-ttu-id="9585f-222">获取所有脚本块。</span><span class="sxs-lookup"><span data-stu-id="9585f-222">Gets all script blocks.</span></span> <span data-ttu-id="9585f-223">若要)  ( ps1 文件获取 PowerShell 脚本，请使用 ExternalScript 值。</span><span class="sxs-lookup"><span data-stu-id="9585f-223">To get PowerShell scripts (.ps1 files), use the ExternalScript value.</span></span>
- <span data-ttu-id="9585f-224">Workflow.</span><span class="sxs-lookup"><span data-stu-id="9585f-224">Workflow.</span></span> <span data-ttu-id="9585f-225">获取所有工作流。</span><span class="sxs-lookup"><span data-stu-id="9585f-225">Gets all workflows.</span></span> <span data-ttu-id="9585f-226">有关工作流的详细信息，请参阅 Introducing Windows PowerShell Workflow。</span><span class="sxs-lookup"><span data-stu-id="9585f-226">For more information about workflows, see Introducing Windows PowerShell Workflow.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9585f-227">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="9585f-227">-FullyQualifiedModule</span></span>

<span data-ttu-id="9585f-228">指定以 **ModuleSpecification** 对象的形式指定的模块，在 ModuleSpecification 构造函数的 " **备注** " 部分中介绍 [ (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)。</span><span class="sxs-lookup"><span data-stu-id="9585f-228">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="9585f-229">例如， **FullyQualifiedModule** 参数接受以下格式之一指定的模块名称：</span><span class="sxs-lookup"><span data-stu-id="9585f-229">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="9585f-230">**ModuleName** 和 **ModuleVersion** 是必需的，但 **Guid** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="9585f-230">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="9585f-231">不能在与 **Module** 参数相同的命令中指定 **FullyQualifiedModule** 参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-231">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="9585f-232">这两个参数是互斥的。</span><span class="sxs-lookup"><span data-stu-id="9585f-232">The two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9585f-233">-ListImported</span><span class="sxs-lookup"><span data-stu-id="9585f-233">-ListImported</span></span>

<span data-ttu-id="9585f-234">指示此 cmdlet 仅获取当前会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-234">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="9585f-235">从 PowerShell 3.0 开始，默认情况下， `Get-Command` 会获取所有已安装的命令，包括但不限于当前会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-235">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="9585f-236">在 PowerShell 2.0 中，它只获取当前会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-236">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="9585f-237">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-237">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9585f-238">-Module</span><span class="sxs-lookup"><span data-stu-id="9585f-238">-Module</span></span>

<span data-ttu-id="9585f-239">指定模块的数组。</span><span class="sxs-lookup"><span data-stu-id="9585f-239">Specifies an array of modules.</span></span> <span data-ttu-id="9585f-240">此 cmdlet 将获取来自指定模块或管理单元的命令。输入模块或管理单元的名称。</span><span class="sxs-lookup"><span data-stu-id="9585f-240">This cmdlet gets the commands that came from the specified modules or snap-ins. Enter the names of modules or snap-ins.</span></span>

<span data-ttu-id="9585f-241">此参数采用字符串值，但此参数的值还可以是 **PSModuleInfo** 或 **PSSnapinInfo** 对象，如 `Get-Module` 、 `Get-PSSnapin` 和 `Import-PSSession` cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="9585f-241">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** or **PSSnapinInfo** object, such as the objects that the `Get-Module`, `Get-PSSnapin`, and `Import-PSSession` cmdlets return.</span></span>

<span data-ttu-id="9585f-242">可以使用此参数的名称 **Module** 或其别名 **PSSnapin** 对其进行引用。</span><span class="sxs-lookup"><span data-stu-id="9585f-242">You can refer to this parameter by its name, **Module** , or by its alias, **PSSnapin** .</span></span>
<span data-ttu-id="9585f-243">选择的参数名不会影响命令输出。</span><span class="sxs-lookup"><span data-stu-id="9585f-243">The parameter name that you choose has no effect on the command output.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9585f-244">-Name</span><span class="sxs-lookup"><span data-stu-id="9585f-244">-Name</span></span>

<span data-ttu-id="9585f-245">指定一个名称数组。</span><span class="sxs-lookup"><span data-stu-id="9585f-245">Specifies an array of names.</span></span> <span data-ttu-id="9585f-246">此 cmdlet 仅获取具有指定名称的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-246">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="9585f-247">输入一个名称或名称模式。</span><span class="sxs-lookup"><span data-stu-id="9585f-247">Enter a name or name pattern.</span></span> <span data-ttu-id="9585f-248">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9585f-248">Wildcard characters are permitted.</span></span>

<span data-ttu-id="9585f-249">若要获取具有相同名称的命令，请使用 **All** 参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-249">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="9585f-250">如果两个命令具有相同的名称，则默认情况下，将 `Get-Command` 获取键入命令名称时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-250">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="9585f-251">-名词</span><span class="sxs-lookup"><span data-stu-id="9585f-251">-Noun</span></span>

<span data-ttu-id="9585f-252">指定一个命令名词的数组。</span><span class="sxs-lookup"><span data-stu-id="9585f-252">Specifies an array of command nouns.</span></span> <span data-ttu-id="9585f-253">此 cmdlet 将获取包含具有指定名词的名称的命令，其中包括 cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-253">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="9585f-254">输入一个或多个名词或名词模式。</span><span class="sxs-lookup"><span data-stu-id="9585f-254">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="9585f-255">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9585f-255">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9585f-256">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="9585f-256">-ParameterName</span></span>

<span data-ttu-id="9585f-257">指定参数名称的数组。</span><span class="sxs-lookup"><span data-stu-id="9585f-257">Specifies an array of parameter names.</span></span> <span data-ttu-id="9585f-258">此 cmdlet 将获取会话中具有指定参数的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-258">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="9585f-259">输入参数名称或参数别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-259">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="9585f-260">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9585f-260">Wildcard characters are supported.</span></span>

<span data-ttu-id="9585f-261">**ParameterName** 和 **ParameterType** 参数仅搜索当前会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-261">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="9585f-262">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-262">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="9585f-263">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="9585f-263">-ParameterType</span></span>

<span data-ttu-id="9585f-264">指定参数名称的数组。</span><span class="sxs-lookup"><span data-stu-id="9585f-264">Specifies an array of parameter names.</span></span> <span data-ttu-id="9585f-265">此 cmdlet 将获取会话中具有指定类型的参数的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-265">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="9585f-266">输入参数类型的全名或部分名称。</span><span class="sxs-lookup"><span data-stu-id="9585f-266">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="9585f-267">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9585f-267">Wildcard characters are supported.</span></span>

<span data-ttu-id="9585f-268">**ParameterName** 和 **ParameterType** 参数仅搜索当前会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-268">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="9585f-269">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-269">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9585f-270">-ShowCommandInfo</span><span class="sxs-lookup"><span data-stu-id="9585f-270">-ShowCommandInfo</span></span>

<span data-ttu-id="9585f-271">指示此 cmdlet 显示命令信息。</span><span class="sxs-lookup"><span data-stu-id="9585f-271">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="9585f-272">此参数是在 Windows PowerShell 5.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9585f-272">This parameter was introduced in Windows PowerShell 5.0.</span></span>

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

### <span data-ttu-id="9585f-273">-语法</span><span class="sxs-lookup"><span data-stu-id="9585f-273">-Syntax</span></span>

<span data-ttu-id="9585f-274">指示此 cmdlet 仅获取有关该命令的下列指定数据：</span><span class="sxs-lookup"><span data-stu-id="9585f-274">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="9585f-275">别名.</span><span class="sxs-lookup"><span data-stu-id="9585f-275">Aliases.</span></span> <span data-ttu-id="9585f-276">获取标准名称。</span><span class="sxs-lookup"><span data-stu-id="9585f-276">Gets the standard name.</span></span>
- <span data-ttu-id="9585f-277">Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9585f-277">Cmdlets.</span></span> <span data-ttu-id="9585f-278">获取语法。</span><span class="sxs-lookup"><span data-stu-id="9585f-278">Gets the syntax.</span></span>
- <span data-ttu-id="9585f-279">函数和筛选器。</span><span class="sxs-lookup"><span data-stu-id="9585f-279">Functions and filters.</span></span> <span data-ttu-id="9585f-280">获取函数定义。</span><span class="sxs-lookup"><span data-stu-id="9585f-280">Gets the function definition.</span></span>
- <span data-ttu-id="9585f-281">脚本和应用程序或文件。</span><span class="sxs-lookup"><span data-stu-id="9585f-281">Scripts and applications or files.</span></span> <span data-ttu-id="9585f-282">获取路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="9585f-282">Gets the path and filename.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9585f-283">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="9585f-283">-TotalCount</span></span>

<span data-ttu-id="9585f-284">指定要获取的命令数。</span><span class="sxs-lookup"><span data-stu-id="9585f-284">Specifies the number of commands to get.</span></span> <span data-ttu-id="9585f-285">可以使用此参数来限制命令的输出。</span><span class="sxs-lookup"><span data-stu-id="9585f-285">You can use this parameter to limit the output of a command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9585f-286">-Verb</span><span class="sxs-lookup"><span data-stu-id="9585f-286">-Verb</span></span>

<span data-ttu-id="9585f-287">指定命令谓词的数组。</span><span class="sxs-lookup"><span data-stu-id="9585f-287">Specifies an array of command verbs.</span></span> <span data-ttu-id="9585f-288">此 cmdlet 将获取包含包含指定谓词的名称的命令，其中包括 cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-288">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="9585f-289">输入一个或多个谓词或谓词模式。</span><span class="sxs-lookup"><span data-stu-id="9585f-289">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="9585f-290">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="9585f-290">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="9585f-291">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9585f-291">CommonParameters</span></span>

<span data-ttu-id="9585f-292">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9585f-292">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9585f-293">有关详细信息，请参阅 [about_CommonParameters](About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-293">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9585f-294">输入</span><span class="sxs-lookup"><span data-stu-id="9585f-294">INPUTS</span></span>

### <span data-ttu-id="9585f-295">System.String</span><span class="sxs-lookup"><span data-stu-id="9585f-295">System.String</span></span>

<span data-ttu-id="9585f-296">可以通过管道将命令名称传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-296">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="9585f-297">输出</span><span class="sxs-lookup"><span data-stu-id="9585f-297">OUTPUTS</span></span>

### <span data-ttu-id="9585f-298">System.web. CommandInfo</span><span class="sxs-lookup"><span data-stu-id="9585f-298">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="9585f-299">此 cmdlet 返回派生自 **CommandInfo** 类的对象。</span><span class="sxs-lookup"><span data-stu-id="9585f-299">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="9585f-300">返回的对象类型取决于获取的命令类型 `Get-Command` 。</span><span class="sxs-lookup"><span data-stu-id="9585f-300">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="9585f-301">System.Management.Automation.AliasInfo</span><span class="sxs-lookup"><span data-stu-id="9585f-301">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="9585f-302">表示别名。</span><span class="sxs-lookup"><span data-stu-id="9585f-302">Represents aliases.</span></span>

### <span data-ttu-id="9585f-303">System.web. ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="9585f-303">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="9585f-304">表示应用程序和文件。</span><span class="sxs-lookup"><span data-stu-id="9585f-304">Represents applications and files.</span></span>

### <span data-ttu-id="9585f-305">System.web. CmdletInfo</span><span class="sxs-lookup"><span data-stu-id="9585f-305">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="9585f-306">表示 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9585f-306">Represents cmdlets.</span></span>

### <span data-ttu-id="9585f-307">System.web. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="9585f-307">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="9585f-308">表示函数和筛选器。</span><span class="sxs-lookup"><span data-stu-id="9585f-308">Represents functions and filters.</span></span>

### <span data-ttu-id="9585f-309">System.web. WorkflowInfo</span><span class="sxs-lookup"><span data-stu-id="9585f-309">System.Management.Automation.WorkflowInfo</span></span>

<span data-ttu-id="9585f-310">表示工作流。</span><span class="sxs-lookup"><span data-stu-id="9585f-310">Represents workflows.</span></span>

## <span data-ttu-id="9585f-311">注释</span><span class="sxs-lookup"><span data-stu-id="9585f-311">NOTES</span></span>

* <span data-ttu-id="9585f-312">当具有相同名称的多个命令可用于会话时，将返回在 `Get-Command` 键入命令名称时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="9585f-312">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="9585f-313">若要获取具有相同名称的命令（按运行顺序列出），请使用 **All** 参数。</span><span class="sxs-lookup"><span data-stu-id="9585f-313">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="9585f-314">有关详细信息，请参阅 [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-314">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
* <span data-ttu-id="9585f-315">自动导入模块后，效果与使用 `Import-Module` cmdlet 相同。</span><span class="sxs-lookup"><span data-stu-id="9585f-315">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="9585f-316">该模块可以添加命令、类型和格式设置文件，并在会话中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="9585f-316">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="9585f-317">若要启用、禁用和配置自动导入模块，请使用 `$PSModuleAutoLoadingPreference` 首选项变量。</span><span class="sxs-lookup"><span data-stu-id="9585f-317">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="9585f-318">有关详细信息，请参阅 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="9585f-318">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="9585f-319">相关链接</span><span class="sxs-lookup"><span data-stu-id="9585f-319">RELATED LINKS</span></span>

[<span data-ttu-id="9585f-320">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="9585f-320">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="9585f-321">Get-Help</span><span class="sxs-lookup"><span data-stu-id="9585f-321">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="9585f-322">Get-Member</span><span class="sxs-lookup"><span data-stu-id="9585f-322">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="9585f-323">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="9585f-323">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="9585f-324">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="9585f-324">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="9585f-325">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="9585f-325">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)
