---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/import-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-Module
ms.openlocfilehash: 6b87074f6053189b20b5cc0983f978324420c99b
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564384"
---
# <span data-ttu-id="19515-102">Import-Module</span><span class="sxs-lookup"><span data-stu-id="19515-102">Import-Module</span></span>

## <span data-ttu-id="19515-103">摘要</span><span class="sxs-lookup"><span data-stu-id="19515-103">SYNOPSIS</span></span>
<span data-ttu-id="19515-104">将模块添加到当前会话。</span><span class="sxs-lookup"><span data-stu-id="19515-104">Adds modules to the current session.</span></span>

## <span data-ttu-id="19515-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="19515-105">SYNTAX</span></span>

### <span data-ttu-id="19515-106">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="19515-106">Name (Default)</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="19515-107">PSSession</span><span class="sxs-lookup"><span data-stu-id="19515-107">PSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="19515-108">CimSession</span><span class="sxs-lookup"><span data-stu-id="19515-108">CimSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Name] <String[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-MinimumVersion <Version>] [-MaximumVersion <String>]
 [-RequiredVersion <Version>] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="19515-109">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="19515-109">FullyQualifiedName</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

### <span data-ttu-id="19515-110">FullyQualifiedNameAndPSSession</span><span class="sxs-lookup"><span data-stu-id="19515-110">FullyQualifiedNameAndPSSession</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-FullyQualifiedName] <ModuleSpecification[]>
 [-Function <String[]>] [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force]
 [-PassThru] [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="19515-111">程序集</span><span class="sxs-lookup"><span data-stu-id="19515-111">Assembly</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Assembly] <Assembly[]> [-Function <String[]>]
 [-Cmdlet <String[]>] [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru]
 [-AsCustomObject] [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber] [-Scope <String>]
 [<CommonParameters>]
```

### <span data-ttu-id="19515-112">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="19515-112">ModuleInfo</span></span>

```
Import-Module [-Global] [-Prefix <String>] [-Function <String[]>] [-Cmdlet <String[]>]
 [-Variable <String[]>] [-Alias <String[]>] [-Force] [-PassThru] [-AsCustomObject]
 [-ModuleInfo] <PSModuleInfo[]> [-ArgumentList <Object[]>] [-DisableNameChecking] [-NoClobber]
 [-Scope <String>] [<CommonParameters>]
```

## <span data-ttu-id="19515-113">说明</span><span class="sxs-lookup"><span data-stu-id="19515-113">DESCRIPTION</span></span>

<span data-ttu-id="19515-114">`Import-Module`Cmdlet 可将一个或多个模块添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-114">The `Import-Module` cmdlet adds one or more modules to the current session.</span></span> <span data-ttu-id="19515-115">从 PowerShell 3.0 开始，当你使用模块中的任何命令或提供程序时，已安装的模块将自动导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-115">Starting in PowerShell 3.0, installed modules are automatically imported to the session when you use any commands or providers in the module.</span></span> <span data-ttu-id="19515-116">但是，您仍然可以使用 `Import-Module` 命令导入模块。</span><span class="sxs-lookup"><span data-stu-id="19515-116">However, you can still use the `Import-Module` command to import a module.</span></span>
<span data-ttu-id="19515-117">您可以使用首选项变量来禁用自动模块导入 `$PSModuleAutoloadingPreference` 。</span><span class="sxs-lookup"><span data-stu-id="19515-117">You can disable automatic module importing using the `$PSModuleAutoloadingPreference` preference variable.</span></span> <span data-ttu-id="19515-118">有关变量的详细信息 `$PSModuleAutoloadingPreference` ，请参阅 [about_Preference_Variables](About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="19515-118">For more information about the `$PSModuleAutoloadingPreference` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="19515-119">模块是一个包，其中包含可在 PowerShell 中使用的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-119">A module is a package that contains members that can be used in PowerShell.</span></span> <span data-ttu-id="19515-120">成员包括 cmdlet、提供程序、脚本、函数、变量和其他工具和文件。</span><span class="sxs-lookup"><span data-stu-id="19515-120">Members include cmdlets, providers, scripts, functions, variables, and other tools and files.</span></span> <span data-ttu-id="19515-121">导入模块后，你可以在会话中使用模块成员。</span><span class="sxs-lookup"><span data-stu-id="19515-121">After a module is imported, you can use the module members in your session.</span></span> <span data-ttu-id="19515-122">有关模块的详细信息，请参阅 [about_Modules](About/about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="19515-122">For more information about modules, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="19515-123">默认情况下， `Import-Module` 导入模块导出的所有成员，但是可以使用 **Alias**、 **Function**、 **Cmdlet** 和 **Variable** 参数来限制导入的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-123">By default, `Import-Module` imports all members that the module exports, but you can use the **Alias**, **Function**, **Cmdlet**, and **Variable** parameters to restrict which members are imported.</span></span> <span data-ttu-id="19515-124">**NoClobber** 参数阻止 `Import-Module` 导入与当前会话中的成员具有相同名称的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-124">The **NoClobber** parameter prevents `Import-Module` from importing members that have the same names as members in the current session.</span></span>

<span data-ttu-id="19515-125">`Import-Module` 仅将模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-125">`Import-Module` imports a module only into the current session.</span></span> <span data-ttu-id="19515-126">若要将模块导入到每个新会话中，请将 `Import-Module` 命令添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="19515-126">To import the module into every new session, add an `Import-Module` command to your PowerShell profile.</span></span> <span data-ttu-id="19515-127">有关配置文件的详细信息，请参阅 [about_Profiles](About/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="19515-127">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

<span data-ttu-id="19515-128">你可以通过在远程计算机上创建 **PSSession** 来管理启用了 PowerShell 远程处理的远程 Windows 计算机。</span><span class="sxs-lookup"><span data-stu-id="19515-128">You can manage remote Windows computers that have PowerShell remoting enabled by creating a **PSSession** on the remote computer.</span></span> <span data-ttu-id="19515-129">然后，使用的 **PSSession** 参数 `Import-Module` 导入远程计算机上安装的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-129">Then use the **PSSession** parameter of `Import-Module` to import the modules that are installed on the remote computer.</span></span> <span data-ttu-id="19515-130">在当前会话中使用导入的命令时，命令将在远程计算机上隐式运行。</span><span class="sxs-lookup"><span data-stu-id="19515-130">When you use the imported commands in the current session the commands implicitly run on the remote computer.</span></span>

<span data-ttu-id="19515-131">从 Windows PowerShell 3.0 开始，你可以使用 `Import-Module` 导入通用信息模型 (CIM) 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-131">Starting in Windows PowerShell 3.0, you can use `Import-Module` to import Common Information Model (CIM) modules.</span></span> <span data-ttu-id="19515-132">CIM 模块在 Cmdlet 定义 XML (CDXML) 文件中定义 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19515-132">CIM modules define cmdlets in Cmdlet Definition XML (CDXML) files.</span></span> <span data-ttu-id="19515-133">此功能允许你使用在非托管代码程序集中实现的 cmdlet，如用 c + + 编写的程序集。</span><span class="sxs-lookup"><span data-stu-id="19515-133">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="19515-134">对于未启用 PowerShell 远程处理的远程计算机，包括未运行 Windows 操作系统的计算机，可以使用的 **CIMSession** 参数 `Import-Module` 从远程计算机导入 CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-134">For remote computers that don't have PowerShell remoting enabled, including computers that aren't running the Windows operating system, you can use the **CIMSession** parameter of `Import-Module` to import CIM modules from the remote computer.</span></span> <span data-ttu-id="19515-135">导入的命令将在远程计算机上隐式运行。</span><span class="sxs-lookup"><span data-stu-id="19515-135">The imported commands run implicitly on the remote computer.</span></span> <span data-ttu-id="19515-136">**CIMSession** 是与远程计算机上的 WMI) Windows Management Instrumentation (的连接。</span><span class="sxs-lookup"><span data-stu-id="19515-136">A **CIMSession** is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>

## <span data-ttu-id="19515-137">示例</span><span class="sxs-lookup"><span data-stu-id="19515-137">EXAMPLES</span></span>

### <span data-ttu-id="19515-138">示例1：将模块的成员导入到当前会话中</span><span class="sxs-lookup"><span data-stu-id="19515-138">Example 1: Import the members of a module into the current session</span></span>

<span data-ttu-id="19515-139">此示例将 **PSDiagnostics** 模块的成员导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-139">This example imports the members of the **PSDiagnostics** module into the current session.</span></span>

```powershell
Import-Module -Name PSDiagnostics
```

### <span data-ttu-id="19515-140">示例2：导入模块路径指定的所有模块</span><span class="sxs-lookup"><span data-stu-id="19515-140">Example 2: Import all modules specified by the module path</span></span>

<span data-ttu-id="19515-141">此示例将环境变量指定的路径中的所有可用模块导入 `$env:PSModulePath` 到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-141">This example imports all available modules in the path specified by the `$env:PSModulePath` environment variable into the current session.</span></span>

```powershell
Get-Module -ListAvailable | Import-Module
```

### <span data-ttu-id="19515-142">示例3：将多个模块的成员导入到当前会话中</span><span class="sxs-lookup"><span data-stu-id="19515-142">Example 3: Import the members of several modules into the current session</span></span>

<span data-ttu-id="19515-143">此示例将 **PSDiagnostics** 和 **Dism** 模块的成员导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-143">This example imports the members of the **PSDiagnostics** and **Dism** modules into the current session.</span></span>

```powershell
$m = Get-Module -ListAvailable PSDiagnostics, Dism
Import-Module -ModuleInfo $m
```

<span data-ttu-id="19515-144">该 `Get-Module` cmdlet 将获取 **PSDiagnostics** 和 **Dism** 模块，并将对象保存在 `$m` 变量中。</span><span class="sxs-lookup"><span data-stu-id="19515-144">The `Get-Module` cmdlet gets the **PSDiagnostics** and **Dism** modules and saves the objects in the `$m` variable.</span></span> <span data-ttu-id="19515-145">当你获取尚未导入到会话中的模块时， **ListAvailable** 参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="19515-145">The **ListAvailable** parameter is required when you're getting modules that aren't yet imported into the session.</span></span>

<span data-ttu-id="19515-146">的 **ModuleInfo** 参数 `Import-Module` 用于将模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-146">The **ModuleInfo** parameter of `Import-Module` is used to import the modules into the current session.</span></span>

### <span data-ttu-id="19515-147">示例4：导入路径指定的所有模块</span><span class="sxs-lookup"><span data-stu-id="19515-147">Example 4: Import all modules specified by a path</span></span>

<span data-ttu-id="19515-148">此示例使用显式路径来标识要导入的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-148">This example uses an explicit path to identify the module to import.</span></span>

```powershell
Import-Module -Name c:\ps-test\modules\test -Verbose
```

```Output
VERBOSE: Loading module from path 'C:\ps-test\modules\Test\Test.psm1'.
VERBOSE: Exporting function 'my-parm'.
VERBOSE: Exporting function 'Get-Parameter'.
VERBOSE: Exporting function 'Get-Specification'.
VERBOSE: Exporting function 'Get-SpecDetails'.
```

<span data-ttu-id="19515-149">使用 **Verbose** 参数会导致在 `Import-Module` 加载模块时报告进度。</span><span class="sxs-lookup"><span data-stu-id="19515-149">Using the **Verbose** parameter causes `Import-Module` to report progress as it loads the module.</span></span>
<span data-ttu-id="19515-150">在导入模块时，如果没有 **Verbose**、 **PassThru** 或 **AsCustomObject** 参数， `Import-Module` 则不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="19515-150">Without the **Verbose**, **PassThru**, or **AsCustomObject** parameter, `Import-Module` does not generate any output when it imports a module.</span></span>

### <span data-ttu-id="19515-151">示例5：限制导入到会话中的模块成员</span><span class="sxs-lookup"><span data-stu-id="19515-151">Example 5: Restrict module members imported into a session</span></span>

<span data-ttu-id="19515-152">此示例显示了如何限制导入到会话中的模块成员以及此命令对会话的影响。</span><span class="sxs-lookup"><span data-stu-id="19515-152">This example shows how to restrict which module members are imported into the session and the effect of this command on the session.</span></span> <span data-ttu-id="19515-153">**函数** 参数限制从模块导入的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-153">The **Function** parameter limits the members that are imported from the module.</span></span> <span data-ttu-id="19515-154">你还可以使用 **别名**、 **变量** 和 **Cmdlet** 参数来限制模块导入的其他成员。</span><span class="sxs-lookup"><span data-stu-id="19515-154">You can also use the **Alias**, **Variable**, and **Cmdlet** parameters to restrict other members that a module imports.</span></span>

<span data-ttu-id="19515-155">`Get-Module`Cmdlet 可获取表示 **PSDiagnostics** 模块的对象。</span><span class="sxs-lookup"><span data-stu-id="19515-155">The `Get-Module` cmdlet gets the object that represents the **PSDiagnostics** module.</span></span> <span data-ttu-id="19515-156">**ExportedCmdlets** 属性列出模块导出的所有 cmdlet，即使它们并非全部导入。</span><span class="sxs-lookup"><span data-stu-id="19515-156">The **ExportedCmdlets** property lists all the cmdlets that the module exports, even though they were not all imported.</span></span>

```powershell
Import-Module PSDiagnostics -Function Disable-PSTrace, Enable-PSTrace
(Get-Module PSDiagnostics).ExportedCommands
```

```Output
Key                          Value
---                          -----
Disable-PSTrace              Disable-PSTrace
Disable-PSWSManCombinedTrace Disable-PSWSManCombinedTrace
Disable-WSManTrace           Disable-WSManTrace
Enable-PSTrace               Enable-PSTrace
Enable-PSWSManCombinedTrace  Enable-PSWSManCombinedTrace
Enable-WSManTrace            Enable-WSManTrace
Get-LogProperties            Get-LogProperties
Set-LogProperties            Set-LogProperties
Start-Trace                  Start-Trace
Stop-Trace                   Stop-Trace
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                 Version    Source
-----------     ----                 -------    ------
Function        Disable-PSTrace      6.1.0.0    PSDiagnostics
Function        Enable-PSTrace       6.1.0.0    PSDiagnostics
```

<span data-ttu-id="19515-157">使用 cmdlet 的 **Module** 参数 `Get-Command` 显示从 **PSDiagnostics** 模块导入的命令。</span><span class="sxs-lookup"><span data-stu-id="19515-157">Using the **Module** parameter of the `Get-Command` cmdlet shows the commands that were imported from the **PSDiagnostics** module.</span></span> <span data-ttu-id="19515-158">结果确认只 `Disable-PSTrace` 导入了和 `Enable-PSTrace` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19515-158">The results confirm that only the `Disable-PSTrace` and `Enable-PSTrace` cmdlets were imported.</span></span>

### <span data-ttu-id="19515-159">示例6：导入模块的成员并添加前缀</span><span class="sxs-lookup"><span data-stu-id="19515-159">Example 6: Import the members of a module and add a prefix</span></span>

<span data-ttu-id="19515-160">此示例将 **PSDiagnostics** 模块导入到当前会话中，将前缀添加到成员名称，然后显示前缀成员的名称。</span><span class="sxs-lookup"><span data-stu-id="19515-160">This example imports the **PSDiagnostics** module into the current session, adds a prefix to the member names, and then displays the prefixed member names.</span></span> <span data-ttu-id="19515-161">的 **前缀** 参数 `Import-Module` 将 **x** 前缀添加到从模块导入的所有成员。</span><span class="sxs-lookup"><span data-stu-id="19515-161">The **Prefix** parameter of `Import-Module` adds the **x** prefix to all members that are imported from the module.</span></span> <span data-ttu-id="19515-162">前缀仅适用于当前会话中的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-162">The prefix applies only to the members in the current session.</span></span> <span data-ttu-id="19515-163">它不会更改模块。</span><span class="sxs-lookup"><span data-stu-id="19515-163">It does not change the module.</span></span> <span data-ttu-id="19515-164">**PassThru** 参数返回一个 module 对象，该对象表示导入的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-164">The **PassThru** parameter returns a module object that represents the imported module.</span></span>

```powershell
Import-Module PSDiagnostics -Prefix x -PassThru
```

```Output
ModuleType Version    Name               ExportedCommands
---------- -------    ----               ----------------
Script     6.1.0.0    PSDiagnostics      {Disable-xPSTrace, Disable-xPSWSManCombinedTrace, Disable-xW...
```

```powershell
Get-Command -Module PSDiagnostics
```

```Output
CommandType     Name                                   Version    Source
-----------     ----                                   -------    ------
Function        Disable-xPSTrace                       6.1.0.0    PSDiagnostics
Function        Disable-xPSWSManCombinedTrace          6.1.0.0    PSDiagnostics
Function        Disable-xWSManTrace                    6.1.0.0    PSDiagnostics
Function        Enable-xPSTrace                        6.1.0.0    PSDiagnostics
Function        Enable-xPSWSManCombinedTrace           6.1.0.0    PSDiagnostics
Function        Enable-xWSManTrace                     6.1.0.0    PSDiagnostics
Function        Get-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Set-xLogProperties                     6.1.0.0    PSDiagnostics
Function        Start-xTrace                           6.1.0.0    PSDiagnostics
Function        Stop-xTrace                            6.1.0.0    PSDiagnostics
```

<span data-ttu-id="19515-165">`Get-Command` 获取已从模块导入的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-165">`Get-Command` gets the members that have been imported from the module.</span></span> <span data-ttu-id="19515-166">该输出显示模块成员已正确地添加了前缀。</span><span class="sxs-lookup"><span data-stu-id="19515-166">The output shows that the module members were correctly prefixed.</span></span>

### <span data-ttu-id="19515-167">示例7：获取并使用自定义对象</span><span class="sxs-lookup"><span data-stu-id="19515-167">Example 7: Get and use a custom object</span></span>

<span data-ttu-id="19515-168">此示例演示如何获取和使用由返回的自定义对象 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="19515-168">This example demonstrates how to get and use the custom object returned by `Import-Module`.</span></span>

<span data-ttu-id="19515-169">自定义对象包括表示每个导入的模块成员的合成成员。</span><span class="sxs-lookup"><span data-stu-id="19515-169">Custom objects include synthetic members that represent each of the imported module members.</span></span> <span data-ttu-id="19515-170">例如，模块中的 cmdlet 和函数将转换为自定义对象的脚本方法。</span><span class="sxs-lookup"><span data-stu-id="19515-170">For example, the cmdlets and functions in a module are converted to script methods of the custom object.</span></span>

<span data-ttu-id="19515-171">自定义对象在脚本编写中非常有用。</span><span class="sxs-lookup"><span data-stu-id="19515-171">Custom objects are useful in scripting.</span></span> <span data-ttu-id="19515-172">此外，当多个导入的对象具有相同的名称时，它们也非常有用。</span><span class="sxs-lookup"><span data-stu-id="19515-172">They are also useful when several imported objects have the same names.</span></span> <span data-ttu-id="19515-173">使用对象的脚本方法等效于指定已导入成员的完全限定名称（包括其模块名称）。</span><span class="sxs-lookup"><span data-stu-id="19515-173">Using the script method of an object is equivalent to specifying the fully qualified name of an imported member, including its module name.</span></span>

<span data-ttu-id="19515-174">**AsCustomObject** 参数只能在导入脚本模块时使用。</span><span class="sxs-lookup"><span data-stu-id="19515-174">The **AsCustomObject** parameter can be used only when importing a script module.</span></span> <span data-ttu-id="19515-175">使用 `Get-Module` 确定哪些可用模块是脚本模块。</span><span class="sxs-lookup"><span data-stu-id="19515-175">Use `Get-Module` to determine which of the available modules is a script module.</span></span>

```powershell
Get-Module -List | Format-Table -Property Name, ModuleType -AutoSize
```

```Output
Name          ModuleType
----          ----------
Show-Calendar     Script
BitsTransfer    Manifest
PSDiagnostics   Manifest
TestCmdlets       Script
...
```

```powershell
$a = Import-Module -Name Show-Calendar -AsCustomObject -Passthru
$a | Get-Member
```

```Output
    TypeName: System.Management.Automation.PSCustomObject
Name          MemberType   Definition
----          ----------   ----------
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
ToString      Method       string ToString()
Show-Calendar ScriptMethod System.Object Show-Calendar();
```

```powershell
$a."Show-Calendar"()
```

<span data-ttu-id="19515-176">`Show-Calendar`脚本模块是使用 **AsCustomObject** 参数导入的，用来请求自定义对象，使用 **PassThru** 参数来返回对象。</span><span class="sxs-lookup"><span data-stu-id="19515-176">The `Show-Calendar` script module is imported using the **AsCustomObject** parameter to request a custom object and the **PassThru** parameter to return the object.</span></span> <span data-ttu-id="19515-177">生成的自定义对象保存在 `$a` 变量中。</span><span class="sxs-lookup"><span data-stu-id="19515-177">The resulting custom object is saved in the `$a` variable.</span></span>

<span data-ttu-id="19515-178">将 `$a` 变量传递给 cmdlet 以 `Get-Member` 显示已保存对象的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="19515-178">The `$a` variable is piped to the `Get-Member` cmdlet to show the properties and methods of the saved object.</span></span> <span data-ttu-id="19515-179">输出显示 `Show-Calendar` 脚本方法。</span><span class="sxs-lookup"><span data-stu-id="19515-179">The output shows a `Show-Calendar` script method.</span></span>

<span data-ttu-id="19515-180">若要调用该 `Show-Calendar` 脚本方法，方法名称必须用引号引起来，因为该名称包含连字符。</span><span class="sxs-lookup"><span data-stu-id="19515-180">To call the `Show-Calendar` script method, the method name must be enclosed in quotation marks because the name includes a hyphen.</span></span>

### <span data-ttu-id="19515-181">示例8：将模块导入同一会话</span><span class="sxs-lookup"><span data-stu-id="19515-181">Example 8: Reimport a module into the same session</span></span>

<span data-ttu-id="19515-182">此示例演示如何在将 `Import-Module` 模块重新导入到同一会话中时使用 Force 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-182">This example shows how to use the **Force** parameter of `Import-Module` when you're reimporting a module into the same session.</span></span> <span data-ttu-id="19515-183">**Force** 参数将删除已加载的模块，然后再次导入它。</span><span class="sxs-lookup"><span data-stu-id="19515-183">The **Force** parameter removes the loaded module and then imports it again.</span></span>

```powershell
Import-Module PSDiagnostics
Import-Module PSDiagnostics -Force -Prefix PS
```

<span data-ttu-id="19515-184">第一个命令将导入 **PSDiagnostics** 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-184">The first command imports the **PSDiagnostics** module.</span></span> <span data-ttu-id="19515-185">第二个命令将再次导入该模块，这一次使用的是 **Prefix** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-185">The second command imports the module again, this time using the **Prefix** parameter.</span></span>

<span data-ttu-id="19515-186">如果没有 **Force** 参数，则会话将包含每个 **PSDiagnostics** cmdlet 的两个副本，一个具有标准名称，另一个带有前缀名称。</span><span class="sxs-lookup"><span data-stu-id="19515-186">Without the **Force** parameter, the session would include two copies of each **PSDiagnostics** cmdlet, one with the standard name and one with the prefixed name.</span></span>

### <span data-ttu-id="19515-187">示例9：运行已由导入的命令隐藏的命令</span><span class="sxs-lookup"><span data-stu-id="19515-187">Example 9: Run commands that have been hidden by imported commands</span></span>

<span data-ttu-id="19515-188">此示例显示了如何运行由导入的命令隐藏的命令。</span><span class="sxs-lookup"><span data-stu-id="19515-188">This example shows how to run commands that have been hidden by imported commands.</span></span> <span data-ttu-id="19515-189">**TestModule** 模块包括一个名为的函数，该函数 `Get-Date` 返回年份和年份。</span><span class="sxs-lookup"><span data-stu-id="19515-189">The **TestModule** module includes a function named `Get-Date` that returns the year and day of the year.</span></span>

```powershell
Get-Date
```

```Output
Thursday, August 15, 2019 2:26:12 PM
```

```powershell
Import-Module TestModule
Get-Date
```

```Output
19227
```

```powershell
Get-Command Get-Date -All | Format-Table -Property CommandType, Name, ModuleName -AutoSize
```

```Output
CommandType     Name         ModuleName
-----------     ----         ----------
Function        Get-Date     TestModule
Cmdlet          Get-Date     Microsoft.PowerShell.Utility
```

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

```Output
Thursday, August 15, 2019 2:28:31 PM
```

<span data-ttu-id="19515-190">第一个 `Get-Date` cmdlet 返回具有当前日期的 **DateTime** 对象。</span><span class="sxs-lookup"><span data-stu-id="19515-190">The first `Get-Date` cmdlet returns a **DateTime** object with the current date.</span></span> <span data-ttu-id="19515-191">导入 **TestModule** 模块后， `Get-Date` 返回年份和该年的第几天。</span><span class="sxs-lookup"><span data-stu-id="19515-191">After importing the **TestModule** module, `Get-Date` returns the year and day of the year.</span></span>

<span data-ttu-id="19515-192">使用的 **all** 参数 `Get-Command` 显示 `Get-Date` 会话中的所有命令。</span><span class="sxs-lookup"><span data-stu-id="19515-192">Using the **All** parameter of `Get-Command` show all the `Get-Date` commands in the session.</span></span> <span data-ttu-id="19515-193">结果显示会话中有两个 `Get-Date` 命令、 **TestModule** 模块中的一个函数和一个来自 **模块的** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19515-193">The results show that there are two `Get-Date` commands in the session, a function from the **TestModule** module and a cmdlet from the **Microsoft.PowerShell.Utility** module.</span></span>

<span data-ttu-id="19515-194">由于函数优先于 cmdlet，因此 `Get-Date` **TestModule** 模块中的函数会运行，而不是 `Get-Date` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19515-194">Because functions take precedence over cmdlets, the `Get-Date` function from the **TestModule** module runs, instead of the `Get-Date` cmdlet.</span></span> <span data-ttu-id="19515-195">若要运行的原始版本 `Get-Date` ，必须用模块名称限定命令名称。</span><span class="sxs-lookup"><span data-stu-id="19515-195">To run the original version of `Get-Date`, you must qualify the command name with the module name.</span></span>

<span data-ttu-id="19515-196">有关 PowerShell 中命令优先级的详细信息，请参阅 [about_Command_Precedence](about/about_Command_Precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="19515-196">For more information about command precedence in PowerShell, see [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="19515-197">示例10：导入模块的最低版本</span><span class="sxs-lookup"><span data-stu-id="19515-197">Example 10: Import a minimum version of a module</span></span>

<span data-ttu-id="19515-198">此示例导入 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-198">This example imports the **PowerShellGet** module.</span></span> <span data-ttu-id="19515-199">它使用的 **MinimumVersion** 参数 `Import-Module` 仅导入2.0.0 或更高版本的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-199">It uses the **MinimumVersion** parameter of `Import-Module` to import only version 2.0.0 or greater of the module.</span></span>

```powershell
Import-Module -Name PowerShellGet -MinimumVersion 2.0.0
```

<span data-ttu-id="19515-200">你还可以使用 **RequiredVersion** 参数导入特定版本的模块，或者使用关键字的 **module** 和 **version** 参数 `#Requires` 来要求在脚本中使用特定版本的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-200">You can also use the **RequiredVersion** parameter to import a particular version of a module, or use the **Module** and **Version** parameters of the `#Requires` keyword to require a particular version of a module in a script.</span></span>

### <span data-ttu-id="19515-201">示例11：使用完全限定名称导入</span><span class="sxs-lookup"><span data-stu-id="19515-201">Example 11: Import using a fully qualified name</span></span>

<span data-ttu-id="19515-202">此示例使用 FullyQualifiedName 导入特定版本的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-202">This example imports a specific version of a module using the FullyQualifiedName.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Name, Version

Name          Version
----          -------
PowerShellGet 2.2.1
PowerShellGet 2.1.3
PowerShellGet 2.1.2
PowerShellGet 1.0.0.1

PS> Import-Module -FullyQualifiedName @{ModuleName = 'PowerShellGet'; ModuleVersion = '2.1.3' }
```

### <span data-ttu-id="19515-203">示例12：使用完全限定的路径导入</span><span class="sxs-lookup"><span data-stu-id="19515-203">Example 12: Import using a fully qualified path</span></span>

<span data-ttu-id="19515-204">此示例使用完全限定的路径导入模块的特定版本。</span><span class="sxs-lookup"><span data-stu-id="19515-204">This example imports a specific version of a module using the fully qualified path.</span></span>

```powershell
PS> Get-Module -ListAvailable PowerShellGet | Select-Object Path

Path
----
C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1
C:\program files\powershell\6\Modules\PowerShellGet\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\2.1.2\PowerShellGet.psd1
C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.0.0.1\PowerShellGet.psd1

PS> Import-Module -Name 'C:\Program Files\PowerShell\Modules\PowerShellGet\2.2.1\PowerShellGet.psd1'
```

### <span data-ttu-id="19515-205">示例13：从远程计算机导入模块</span><span class="sxs-lookup"><span data-stu-id="19515-205">Example 13: Import a module from a remote computer</span></span>

<span data-ttu-id="19515-206">此示例演示如何使用 `Import-Module` cmdlet 从远程计算机导入模块。</span><span class="sxs-lookup"><span data-stu-id="19515-206">This example shows how to use the `Import-Module` cmdlet to import a module from a remote computer.</span></span>
<span data-ttu-id="19515-207">此命令使用 PowerShell 的隐式远程处理功能。</span><span class="sxs-lookup"><span data-stu-id="19515-207">This command uses the Implicit Remoting feature of PowerShell.</span></span>

<span data-ttu-id="19515-208">从另一个会话导入模块时，你可以使用当前会话中的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19515-208">When you import modules from another session, you can use the cmdlets in the current session.</span></span>
<span data-ttu-id="19515-209">但是，使用这些 cmdlet 的命令将在远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="19515-209">However, commands that use the cmdlets run in the remote session.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01
Get-Module -PSSession $s -ListAvailable -Name NetSecurity
```

```Output
ModuleType Name             ExportedCommands
---------- ----             ----------------
Manifest   NetSecurity      {New-NetIPsecAuthProposal, New-NetIPsecMainModeCryptoProposal, New-Ne...
```

```powershell
Import-Module -PSSession $s -Name NetSecurity
Get-Command -Module NetSecurity -Name Get-*Firewall*
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Get-NetFirewallAddressFilter                       NetSecurity
Function        Get-NetFirewallApplicationFilter                   NetSecurity
Function        Get-NetFirewallInterfaceFilter                     NetSecurity
Function        Get-NetFirewallInterfaceTypeFilter                 NetSecurity
Function        Get-NetFirewallPortFilter                          NetSecurity
Function        Get-NetFirewallProfile                             NetSecurity
Function        Get-NetFirewallRule                                NetSecurity
Function        Get-NetFirewallSecurityFilter                      NetSecurity
Function        Get-NetFirewallServiceFilter                       NetSecurity
Function        Get-NetFirewallSetting                             NetSecurity
```

```powershell
Get-NetFirewallRule -DisplayName "Windows Remote Management*" |
  Format-Table -Property DisplayName, Name -AutoSize
```

```Output
DisplayName                                              Name
-----------                                              ----
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP
Windows Remote Management (HTTP-In)                      WINRM-HTTP-In-TCP-PUBLIC
Windows Remote Management - Compatibility Mode (HTTP-In) WINRM-HTTP-Compat-In-TCP
```

<span data-ttu-id="19515-210">`New-PSSession` (**PSSession**) 创建到 Server01 计算机的远程会话。</span><span class="sxs-lookup"><span data-stu-id="19515-210">`New-PSSession` creates a remote session (**PSSession**) to the Server01 computer.</span></span> <span data-ttu-id="19515-211">**PSSession** 保存在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="19515-211">The **PSSession** is saved in the `$s` variable.</span></span>

<span data-ttu-id="19515-212">`Get-Module`使用 **PSSession** 参数运行时，将显示 **NetSecurity** 模块已安装并在远程计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="19515-212">Running `Get-Module` with the **PSSession** parameter shows that the **NetSecurity** module is installed and available on the remote computer.</span></span> <span data-ttu-id="19515-213">此命令等效于使用 `Invoke-Command` cmdlet `Get-Module` 在远程会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="19515-213">This command is equivalent to using the `Invoke-Command` cmdlet to run `Get-Module` command in the remote session.</span></span> <span data-ttu-id="19515-214">例如： (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span><span class="sxs-lookup"><span data-stu-id="19515-214">For example: (`Invoke-Command $s {Get-Module -ListAvailable -Name NetSecurity`</span></span>

<span data-ttu-id="19515-215">`Import-Module`用 **PSSession** 参数运行时，会将远程计算机中的 **NetSecurity** 模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-215">Running `Import-Module` with the **PSSession** parameter imports the **NetSecurity** module from the remote computer into the current session.</span></span> <span data-ttu-id="19515-216">`Get-Command`Cmdlet 用于获取以 **get** 开头的命令，并将 **防火墙** 包括在 **NetSecurity** 模块中。</span><span class="sxs-lookup"><span data-stu-id="19515-216">The `Get-Command` cmdlet is used to get commands that begin with **Get** and include **Firewall** from the **NetSecurity** module.</span></span> <span data-ttu-id="19515-217">输出确认模块及其 cmdlet 已导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-217">The output confirms that the module and its cmdlets were imported into the current session.</span></span>

<span data-ttu-id="19515-218">接下来，该 `Get-NetFirewallRule` cmdlet 将获取 Server01 计算机上 Windows 远程管理防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="19515-218">Next, the `Get-NetFirewallRule` cmdlet gets Windows Remote Management firewall rules on the Server01 computer.</span></span> <span data-ttu-id="19515-219">这等效于使用 `Invoke-Command` cmdlet `Get-NetFirewallRule` 在远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="19515-219">This is equivalent to using the `Invoke-Command` cmdlet to run `Get-NetFirewallRule` on the remote session.</span></span>

### <span data-ttu-id="19515-220">示例14：在没有 Windows 操作系统的情况下管理远程计算机上的存储</span><span class="sxs-lookup"><span data-stu-id="19515-220">Example 14: Manage storage on a remote computer without the Windows operating system</span></span>

<span data-ttu-id="19515-221">在此示例中，计算机的管理员已安装模块发现 WMI 提供程序，该提供程序允许你使用为提供程序设计的 CIM 命令。</span><span class="sxs-lookup"><span data-stu-id="19515-221">In this example, the administrator of the computer has installed the Module Discovery WMI provider, which allows you to use CIM commands that are designed for the provider.</span></span>

<span data-ttu-id="19515-222">`New-CimSession`Cmdlet 在远程计算机上创建一个名为 RSDGF03 的会话。</span><span class="sxs-lookup"><span data-stu-id="19515-222">The `New-CimSession` cmdlet creates a session on the remote computer named RSDGF03.</span></span> <span data-ttu-id="19515-223">会话连接到远程计算机上的 WMI 服务。</span><span class="sxs-lookup"><span data-stu-id="19515-223">The session connects to the WMI service on the remote computer.</span></span> <span data-ttu-id="19515-224">CIM 会话保存在 `$cs` 变量中。</span><span class="sxs-lookup"><span data-stu-id="19515-224">The CIM session is saved in the `$cs` variable.</span></span>
<span data-ttu-id="19515-225">`Import-Module`使用中的 CIMSESSION `$cs` 从 RSDGF03 计算机中导入 **存储** CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-225">`Import-Module` uses the **CimSession** in `$cs` to import the **Storage** CIM module from the RSDGF03 computer.</span></span>

<span data-ttu-id="19515-226">`Get-Command`Cmdlet 将 `Get-Disk` 在 **存储** 模块中显示该命令。</span><span class="sxs-lookup"><span data-stu-id="19515-226">The `Get-Command` cmdlet shows the `Get-Disk` command in the **Storage** module.</span></span> <span data-ttu-id="19515-227">将 CIM 模块导入到本地会话中时，PowerShell 会将每个命令的 CDXML 文件转换为 PowerShell 脚本，这些脚本在本地会话中显示为函数。</span><span class="sxs-lookup"><span data-stu-id="19515-227">When you import a CIM module into the local session, PowerShell converts the CDXML files for each command into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="19515-228">尽管 `Get-Disk` 在本地会话中键入，该 cmdlet 会在从中导入它的远程计算机上隐式运行。</span><span class="sxs-lookup"><span data-stu-id="19515-228">Although `Get-Disk` is typed in the local session, the cmdlet implicitly runs on the remote computer from which it was imported.</span></span> <span data-ttu-id="19515-229">此命令将从远程计算机向本地会话返回对象。</span><span class="sxs-lookup"><span data-stu-id="19515-229">The command returns objects from the remote computer to the local session.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Import-Module -CimSession $cs -Name Storage
# Importing a CIM module, converts the CDXML files for each command into PowerShell scripts.
# These appear as functions in the local session.
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
# Use implicit remoting to query disks on the remote computer from which the module was imported.
Get-Disk
```

```Output
Number Friendly Name           OperationalStatus  Total Size Partition Style
------ -------------           -----------------  ---------- ---------------
0      Virtual HD ATA Device   Online                  40 GB MBR
```

## <span data-ttu-id="19515-230">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="19515-230">PARAMETERS</span></span>

### <span data-ttu-id="19515-231">-Alias</span><span class="sxs-lookup"><span data-stu-id="19515-231">-Alias</span></span>

<span data-ttu-id="19515-232">指定此 cmdlet 从模块导入到当前会话中的别名。</span><span class="sxs-lookup"><span data-stu-id="19515-232">Specifies the aliases that this cmdlet imports from the module into the current session.</span></span> <span data-ttu-id="19515-233">输入以逗号分隔的别名列表。</span><span class="sxs-lookup"><span data-stu-id="19515-233">Enter a comma-separated list of aliases.</span></span> <span data-ttu-id="19515-234">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="19515-234">Wildcard characters are permitted.</span></span>

<span data-ttu-id="19515-235">在导入模块时，某些模块会自动将选定的别名导出到你的会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-235">Some modules automatically export selected aliases into your session when you import the module.</span></span>
<span data-ttu-id="19515-236">此参数允许你在导出的别名中进行选择。</span><span class="sxs-lookup"><span data-stu-id="19515-236">This parameter lets you select from among the exported aliases.</span></span>

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

### <span data-ttu-id="19515-237">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="19515-237">-ArgumentList</span></span>

<span data-ttu-id="19515-238">指定在命令期间传递给脚本模块的参数数组或参数值 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="19515-238">Specifies an array of arguments, or parameter values, that are passed to a script module during the `Import-Module` command.</span></span> <span data-ttu-id="19515-239">仅当你导入脚本模块时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="19515-239">This parameter is valid only when you're importing a script module.</span></span>

<span data-ttu-id="19515-240">还可以通过别名 **的参数引用** **ArgumentList** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-240">You can also refer to the **ArgumentList** parameter by its alias, **args**.</span></span> <span data-ttu-id="19515-241">有关 **ArgumentList** 行为的详细信息，请参阅 [about_Splatting](about/about_Splatting.md#splatting-with-arrays)。</span><span class="sxs-lookup"><span data-stu-id="19515-241">For more information about the behavior of **ArgumentList**, see [about_Splatting](about/about_Splatting.md#splatting-with-arrays).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-242">-AsCustomObject</span><span class="sxs-lookup"><span data-stu-id="19515-242">-AsCustomObject</span></span>

<span data-ttu-id="19515-243">指示此 cmdlet 返回一个自定义对象，该对象具有表示导入的模块成员的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-243">Indicates that this cmdlet returns a custom object with members that represent the imported module members.</span></span> <span data-ttu-id="19515-244">此参数仅对脚本模块有效。</span><span class="sxs-lookup"><span data-stu-id="19515-244">This parameter is valid only for script modules.</span></span>

<span data-ttu-id="19515-245">使用 **AsCustomObject** 参数时，会 `Import-Module` 将模块成员导入到会话中，然后返回 **PSCustomObject** 对象，而不是 **PSModuleInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="19515-245">When you use the **AsCustomObject** parameter, `Import-Module` imports the module members into the session and then returns a **PSCustomObject** object instead of a **PSModuleInfo** object.</span></span> <span data-ttu-id="19515-246">可以在变量中保存自定义对象，并使用点表示法来调用成员。</span><span class="sxs-lookup"><span data-stu-id="19515-246">You can save the custom object in a variable and use dot notation to invoke the members.</span></span>

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

### <span data-ttu-id="19515-247">-Assembly</span><span class="sxs-lookup"><span data-stu-id="19515-247">-Assembly</span></span>

<span data-ttu-id="19515-248">指定程序集对象的数组。</span><span class="sxs-lookup"><span data-stu-id="19515-248">Specifies an array of assembly objects.</span></span> <span data-ttu-id="19515-249">此 cmdlet 将导入在指定的程序集对象中实现的 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="19515-249">This cmdlet imports the cmdlets and providers implemented in the specified assembly objects.</span></span> <span data-ttu-id="19515-250">输入包含程序集对象的变量或可创建程序集对象的命令。</span><span class="sxs-lookup"><span data-stu-id="19515-250">Enter a variable that contains assembly objects or a command that creates assembly objects.</span></span> <span data-ttu-id="19515-251">还可以通过管道将程序集对象传递给 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="19515-251">You can also pipe an assembly object to `Import-Module`.</span></span>

<span data-ttu-id="19515-252">使用此参数时，将仅导入由指定的程序集实现的 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="19515-252">When you use this parameter, only the cmdlets and providers implemented by the specified assemblies are imported.</span></span> <span data-ttu-id="19515-253">如果模块包含其他文件，则不会导入它们，并且你可能会丢失模块的重要成员。</span><span class="sxs-lookup"><span data-stu-id="19515-253">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span> <span data-ttu-id="19515-254">此参数用于调试和测试模块，或者在模块作者指示你使用它时使用。</span><span class="sxs-lookup"><span data-stu-id="19515-254">Use this parameter for debugging and testing the module, or when you're instructed to use it by the module author.</span></span>

```yaml
Type: System.Reflection.Assembly[]
Parameter Sets: Assembly
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="19515-255">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="19515-255">-CimNamespace</span></span>

<span data-ttu-id="19515-256">指定可公开 CIM 模块的备用 CIM 提供程序的命名空间。</span><span class="sxs-lookup"><span data-stu-id="19515-256">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span> <span data-ttu-id="19515-257">默认值是模块发现 WMI 提供程序的命名空间。</span><span class="sxs-lookup"><span data-stu-id="19515-257">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="19515-258">使用此参数从未运行 Windows 操作系统的计算机和设备导入 CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-258">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="19515-259">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-259">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-260">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="19515-260">-CimResourceUri</span></span>

<span data-ttu-id="19515-261">指定 CIM 模块的备用位置。</span><span class="sxs-lookup"><span data-stu-id="19515-261">Specifies an alternate location for CIM modules.</span></span> <span data-ttu-id="19515-262">默认值是远程计算机上模块发现 WMI 提供程序的资源 URI。</span><span class="sxs-lookup"><span data-stu-id="19515-262">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="19515-263">使用此参数从未运行 Windows 操作系统的计算机和设备导入 CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-263">Use this parameter to import CIM modules from computers and devices that aren't running a Windows operating system.</span></span>

<span data-ttu-id="19515-264">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-264">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-265">-CimSession</span><span class="sxs-lookup"><span data-stu-id="19515-265">-CimSession</span></span>

<span data-ttu-id="19515-266">指定远程计算机上的 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="19515-266">Specifies a CIM session on the remote computer.</span></span> <span data-ttu-id="19515-267">输入包含 CIM 会话的变量或获取 CIM 会话的命令（如 [CimSession](../CimCmdlets/Get-CimSession.md) 命令）。</span><span class="sxs-lookup"><span data-stu-id="19515-267">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](../CimCmdlets/Get-CimSession.md) command.</span></span>

<span data-ttu-id="19515-268">`Import-Module` 使用 CIM 会话连接将远程计算机中的模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-268">`Import-Module` uses the CIM session connection to import modules from the remote computer into the current session.</span></span> <span data-ttu-id="19515-269">在当前会话中使用导入模块中的命令时，这些命令将在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="19515-269">When you use the commands from the imported module in the current session, the commands run on the remote computer.</span></span>

<span data-ttu-id="19515-270">你可以使用此参数从未运行 Windows 操作系统的计算机和设备以及具有 PowerShell 但未启用 PowerShell 远程处理的 Windows 计算机导入模块。</span><span class="sxs-lookup"><span data-stu-id="19515-270">You can use this parameter to import modules from computers and devices that aren't running the Windows operating system, and Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

<span data-ttu-id="19515-271">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-271">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession
Parameter Sets: CimSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-272">-Cmdlet</span><span class="sxs-lookup"><span data-stu-id="19515-272">-Cmdlet</span></span>

<span data-ttu-id="19515-273">指定此 cmdlet 从模块导入到当前会话中的 cmdlet 的数组。</span><span class="sxs-lookup"><span data-stu-id="19515-273">Specifies an array of cmdlets that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="19515-274">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="19515-274">Wildcard characters are permitted.</span></span>

<span data-ttu-id="19515-275">在导入模块时，某些模块会自动将选定的 cmdlet 导出到你的会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-275">Some modules automatically export selected cmdlets into your session when you import the module.</span></span>
<span data-ttu-id="19515-276">此参数允许你在导出的 cmdlet 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="19515-276">This parameter lets you select from among the exported cmdlets.</span></span>

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

### <span data-ttu-id="19515-277">-DisableNameChecking</span><span class="sxs-lookup"><span data-stu-id="19515-277">-DisableNameChecking</span></span>

<span data-ttu-id="19515-278">指示当你导入的 cmdlet 或函数名称包括未经批准的动词或禁止的字符时，此 cmdlet 将禁止显示警告你的消息。</span><span class="sxs-lookup"><span data-stu-id="19515-278">Indicates that this cmdlet suppresses the message that warns you when you import a cmdlet or function whose name includes an unapproved verb or a prohibited character.</span></span>

<span data-ttu-id="19515-279">默认情况下，当导入的模块导出名称中包含未经批准的谓词的 cmdlet 或函数时，PowerShell 将显示以下警告消息：</span><span class="sxs-lookup"><span data-stu-id="19515-279">By default, when a module that you import exports cmdlets or functions that have unapproved verbs in their names, PowerShell displays the following warning message:</span></span>

> <span data-ttu-id="19515-280">警告：某些导入的命令名称包括未经批准的动词，这可能会使它们更易发现。</span><span class="sxs-lookup"><span data-stu-id="19515-280">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="19515-281">请使用 Verbose 参数获取详细信息或者键入 Get-Verb 以查看批准的谓词列表。</span><span class="sxs-lookup"><span data-stu-id="19515-281">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="19515-282">此消息只是一个警告。</span><span class="sxs-lookup"><span data-stu-id="19515-282">This message is only a warning.</span></span> <span data-ttu-id="19515-283">仍将导入完整的模块，其中包括非一致性的命令。</span><span class="sxs-lookup"><span data-stu-id="19515-283">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="19515-284">尽管会向模块用户显示消息，但是模块作者应修复命名问题。</span><span class="sxs-lookup"><span data-stu-id="19515-284">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

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

### <span data-ttu-id="19515-285">-Force</span><span class="sxs-lookup"><span data-stu-id="19515-285">-Force</span></span>

<span data-ttu-id="19515-286">此参数会使模块加载或重新加载到当前模块的顶部。</span><span class="sxs-lookup"><span data-stu-id="19515-286">This parameter causes a module to be loaded, or reloaded, over top of the current one.</span></span>

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

### <span data-ttu-id="19515-287">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="19515-287">-FullyQualifiedName</span></span>

<span data-ttu-id="19515-288">指定模块的完全限定名作为哈希表。</span><span class="sxs-lookup"><span data-stu-id="19515-288">Specifies the fully qualified name of the module as a hash table.</span></span> <span data-ttu-id="19515-289">值可以是字符串和哈希表的组合。</span><span class="sxs-lookup"><span data-stu-id="19515-289">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="19515-290">此哈希表具有以下键。</span><span class="sxs-lookup"><span data-stu-id="19515-290">The hash table has the following keys.</span></span>

- <span data-ttu-id="19515-291">`ModuleName` - **必需** 指定模块名称。</span><span class="sxs-lookup"><span data-stu-id="19515-291">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="19515-292">`GUID` - **可选** 指定模块的 GUID。</span><span class="sxs-lookup"><span data-stu-id="19515-292">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="19515-293">还 **需要** 指定以下三个键中的一个。</span><span class="sxs-lookup"><span data-stu-id="19515-293">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="19515-294">这些密钥不能一起使用。</span><span class="sxs-lookup"><span data-stu-id="19515-294">These keys can't be used together.</span></span>
  - <span data-ttu-id="19515-295">`ModuleVersion` -指定模块的最低可接受版本。</span><span class="sxs-lookup"><span data-stu-id="19515-295">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="19515-296">`RequiredVersion` -指定模块的准确的必需版本。</span><span class="sxs-lookup"><span data-stu-id="19515-296">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="19515-297">`MaximumVersion` -指定模块可接受的最大版本。</span><span class="sxs-lookup"><span data-stu-id="19515-297">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="19515-298">-Function</span><span class="sxs-lookup"><span data-stu-id="19515-298">-Function</span></span>

<span data-ttu-id="19515-299">指定此 cmdlet 从模块导入到当前会话中的函数数组。</span><span class="sxs-lookup"><span data-stu-id="19515-299">Specifies an array of functions that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="19515-300">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="19515-300">Wildcard characters are permitted.</span></span> <span data-ttu-id="19515-301">在导入模块时，某些模块会自动将选定的函数导出到你的会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-301">Some modules automatically export selected functions into your session when you import the module.</span></span> <span data-ttu-id="19515-302">此参数允许你在导出的函数中进行选择。</span><span class="sxs-lookup"><span data-stu-id="19515-302">This parameter lets you select from among the exported functions.</span></span>

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

### <span data-ttu-id="19515-303">-全局</span><span class="sxs-lookup"><span data-stu-id="19515-303">-Global</span></span>

<span data-ttu-id="19515-304">指示此 cmdlet 将模块导入全局会话状态，以便它们可用于会话中的所有命令。</span><span class="sxs-lookup"><span data-stu-id="19515-304">Indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="19515-305">默认情况下，当 `Import-Module` 从命令提示符、脚本文件或 scriptblock 调用 cmdlet 时，所有命令都将导入全局会话状态。</span><span class="sxs-lookup"><span data-stu-id="19515-305">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span>

<span data-ttu-id="19515-306">从另一个模块调用时，cmdlet 会将 `Import-Module` 模块中的命令（包括来自嵌套模块的命令）导入到调用模块的会话状态中。</span><span class="sxs-lookup"><span data-stu-id="19515-306">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the calling module's session state.</span></span>

> [!TIP]
> <span data-ttu-id="19515-307">应避免 `Import-Module` 从模块中调用。</span><span class="sxs-lookup"><span data-stu-id="19515-307">You should avoid calling `Import-Module` from within a module.</span></span> <span data-ttu-id="19515-308">相反，将目标模块声明为父模块清单中的嵌套模块。</span><span class="sxs-lookup"><span data-stu-id="19515-308">Instead, declare the target module as a nested module in the parent module's manifest.</span></span> <span data-ttu-id="19515-309">声明嵌套模块可提高依赖项的可发现性。</span><span class="sxs-lookup"><span data-stu-id="19515-309">Declaring nested modules improves the discoverability of dependencies.</span></span>

<span data-ttu-id="19515-310">**Global** 参数等效于值为 **Global** 的 **Scope** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-310">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="19515-311">若要限制模块导出的命令，请 `Export-ModuleMember` 在脚本模块中使用命令。</span><span class="sxs-lookup"><span data-stu-id="19515-311">To restrict the commands that a module exports, use an `Export-ModuleMember` command in the script module.</span></span>

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

### <span data-ttu-id="19515-312">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="19515-312">-MaximumVersion</span></span>

<span data-ttu-id="19515-313">指定最高版本。</span><span class="sxs-lookup"><span data-stu-id="19515-313">Specifies a maximum version.</span></span> <span data-ttu-id="19515-314">此 cmdlet 仅导入小于或等于指定值的模块版本。</span><span class="sxs-lookup"><span data-stu-id="19515-314">This cmdlet imports only a version of the module that is less than or equal to the specified value.</span></span> <span data-ttu-id="19515-315">如果没有任何版本合格，则 `Import-Module` 返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="19515-315">If no version qualifies, `Import-Module` returns an error.</span></span>

```yaml
Type: System.String
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-316">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="19515-316">-MinimumVersion</span></span>

<span data-ttu-id="19515-317">指定最低版本。</span><span class="sxs-lookup"><span data-stu-id="19515-317">Specifies a minimum version.</span></span> <span data-ttu-id="19515-318">此 cmdlet 仅导入大于或等于指定值的模块版本。</span><span class="sxs-lookup"><span data-stu-id="19515-318">This cmdlet imports only a version of the module that is greater than or equal to the specified value.</span></span> <span data-ttu-id="19515-319">使用 **MinimumVersion** 参数名或它的别名 **Version**。</span><span class="sxs-lookup"><span data-stu-id="19515-319">Use the **MinimumVersion** parameter name or its alias, **Version**.</span></span> <span data-ttu-id="19515-320">如果没有合格的版本， `Import-Module` 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="19515-320">If no version qualifies, `Import-Module` generates an error.</span></span>

<span data-ttu-id="19515-321">若要指定确切的版本，请使用 **RequiredVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-321">To specify an exact version, use the **RequiredVersion** parameter.</span></span> <span data-ttu-id="19515-322">你还可以使用 **#Requires** 关键字的 **module** 和 **Version** 参数来要求在脚本中使用特定版本的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-322">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="19515-323">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-323">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases: Version

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-324">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="19515-324">-ModuleInfo</span></span>

<span data-ttu-id="19515-325">指定要导入的模块对象的数组。</span><span class="sxs-lookup"><span data-stu-id="19515-325">Specifies an array of module objects to import.</span></span> <span data-ttu-id="19515-326">输入包含模块对象的变量，或获取模块对象的命令，如以下命令： `Get-Module -ListAvailable` 。</span><span class="sxs-lookup"><span data-stu-id="19515-326">Enter a variable that contains the module objects, or a command that gets the module objects, such as the following command: `Get-Module -ListAvailable`.</span></span> <span data-ttu-id="19515-327">还可以通过管道将模块对象传递给 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="19515-327">You can also pipe module objects to `Import-Module`.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="19515-328">-Name</span><span class="sxs-lookup"><span data-stu-id="19515-328">-Name</span></span>

<span data-ttu-id="19515-329">指定要导入的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="19515-329">Specifies the names of the modules to import.</span></span> <span data-ttu-id="19515-330">输入模块名称或模块中的文件名称，例如 `.psd1` 、、 `.psm1` `.dll` 或 `.ps1` 文件。</span><span class="sxs-lookup"><span data-stu-id="19515-330">Enter the name of the module or the name of a file in the module, such as a `.psd1`, `.psm1`, `.dll`, or `.ps1` file.</span></span> <span data-ttu-id="19515-331">文件路径是可选的。</span><span class="sxs-lookup"><span data-stu-id="19515-331">File paths are optional.</span></span> <span data-ttu-id="19515-332">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="19515-332">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="19515-333">还可以通过管道将模块名称和文件名传递给 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="19515-333">You can also pipe module names and filenames to `Import-Module`.</span></span>

<span data-ttu-id="19515-334">如果省略路径，则会 `Import-Module` 在环境变量中保存的路径中查找模块 `$env:PSModulePath` 。</span><span class="sxs-lookup"><span data-stu-id="19515-334">If you omit a path, `Import-Module` looks for the module in the paths saved in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="19515-335">在可能的情况下，仅指定模块名称。</span><span class="sxs-lookup"><span data-stu-id="19515-335">Specify only the module name whenever possible.</span></span> <span data-ttu-id="19515-336">指定文件名时，将仅导入在该文件中实现的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-336">When you specify a file name, only the members that are implemented in that file are imported.</span></span> <span data-ttu-id="19515-337">如果模块包含其他文件，则不会导入它们，并且你可能会丢失模块的重要成员。</span><span class="sxs-lookup"><span data-stu-id="19515-337">If the module contains other files, they aren't imported, and you might be missing important members of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="19515-338">尽管可以导入脚本 (`.ps1`) 文件作为模块，但脚本文件通常不像脚本模块文件 () 文件中那样进行结构化 `.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="19515-338">While it is possible to import a script (`.ps1`) file as a module, script files are usually not structured like script modules file (`.psm1`) file.</span></span> <span data-ttu-id="19515-339">导入脚本文件并不能保证它可用作模块。</span><span class="sxs-lookup"><span data-stu-id="19515-339">Importing a script file does not guarantee that it is usable as a module.</span></span> <span data-ttu-id="19515-340">有关详细信息，请参阅 [about_Modules](about/about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="19515-340">For more information, see [about_Modules](about/about_Modules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="19515-341">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="19515-341">-NoClobber</span></span>

<span data-ttu-id="19515-342">禁止导入与当前会话中的现有命令名称相同的命令。</span><span class="sxs-lookup"><span data-stu-id="19515-342">Prevents importing commands that have the same names as existing commands in the current session.</span></span> <span data-ttu-id="19515-343">默认情况下，会 `Import-Module` 导入所有导出的模块命令。</span><span class="sxs-lookup"><span data-stu-id="19515-343">By default, `Import-Module` imports all exported module commands.</span></span>

<span data-ttu-id="19515-344">具有相同名称的命令可以隐藏或替换会话中的命令。</span><span class="sxs-lookup"><span data-stu-id="19515-344">Commands that have the same names can hide or replace commands in the session.</span></span> <span data-ttu-id="19515-345">若要避免会话中出现命令名称冲突，请使用 **Prefix** 或 **NoClobber** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-345">To avoid command name conflicts in a session, use the **Prefix** or **NoClobber** parameters.</span></span> <span data-ttu-id="19515-346">有关名称冲突和命令优先顺序的详细信息，请参阅 [about_Modules](about/about_Modules.md) 和 [about_Command_Precedence](about/about_Command_Precedence.md) 中的“模块和名称冲突”。</span><span class="sxs-lookup"><span data-stu-id="19515-346">For more information about name conflicts and command precedence, see "Modules and Name Conflicts" in [about_Modules](about/about_Modules.md) and [about_Command_Precedence](about/about_Command_Precedence.md).</span></span>

<span data-ttu-id="19515-347">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-347">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-348">-PassThru</span><span class="sxs-lookup"><span data-stu-id="19515-348">-PassThru</span></span>

<span data-ttu-id="19515-349">返回一个对象，该对象表示正在处理的项。</span><span class="sxs-lookup"><span data-stu-id="19515-349">Returns an object representing the item with which you're working.</span></span> <span data-ttu-id="19515-350">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="19515-350">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="19515-351">-Prefix</span><span class="sxs-lookup"><span data-stu-id="19515-351">-Prefix</span></span>

<span data-ttu-id="19515-352">指定此 cmdlet 添加到导入的模块成员的名称中的名词的前缀。</span><span class="sxs-lookup"><span data-stu-id="19515-352">Specifies a prefix that this cmdlet adds to the nouns in the names of imported module members.</span></span>

<span data-ttu-id="19515-353">使用此参数避免当会话中不同的成员具有相同的名称时，可能出现的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="19515-353">Use this parameter to avoid name conflicts that might occur when different members in the session have the same name.</span></span> <span data-ttu-id="19515-354">此参数不会更改模块，并且不会影响模块导入的、供自己使用的文件。</span><span class="sxs-lookup"><span data-stu-id="19515-354">This parameter does not change the module, and it does not affect files that the module imports for its own use.</span></span> <span data-ttu-id="19515-355">它们称为嵌套模块。</span><span class="sxs-lookup"><span data-stu-id="19515-355">These are known as nested modules.</span></span> <span data-ttu-id="19515-356">此 cmdlet 只影响当前会话中成员的名称。</span><span class="sxs-lookup"><span data-stu-id="19515-356">This cmdlet affects only the names of members in the current session.</span></span>

<span data-ttu-id="19515-357">例如，如果指定前缀 UTC，然后导入 `Get-Date` cmdlet，则该 cmdlet 将在会话中称为 `Get-UTCDate` ，而不会与原始 `Get-Date` cmdlet 混淆。</span><span class="sxs-lookup"><span data-stu-id="19515-357">For example, if you specify the prefix UTC and then import a `Get-Date` cmdlet, the cmdlet is known in the session as `Get-UTCDate`, and it is not confused with the original `Get-Date` cmdlet.</span></span>

<span data-ttu-id="19515-358">此参数的值将优先于模块的 **DefaultCommandPrefix** 属性，该属性指定默认的前缀。</span><span class="sxs-lookup"><span data-stu-id="19515-358">The value of this parameter takes precedence over the **DefaultCommandPrefix** property of the module, which specifies the default prefix.</span></span>

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

### <span data-ttu-id="19515-359">-PSSession</span><span class="sxs-lookup"><span data-stu-id="19515-359">-PSSession</span></span>

<span data-ttu-id="19515-360">指定 (**PSSession**) 的 PowerShell 用户管理的会话，此 cmdlet 从中将模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-360">Specifies a PowerShell user-managed session (**PSSession**) from which this cmdlet imports modules into the current session.</span></span> <span data-ttu-id="19515-361">输入包含 **pssession** 的变量或获取 **pssession** 的命令（如 `Get-PSSession` 命令）。</span><span class="sxs-lookup"><span data-stu-id="19515-361">Enter a variable that contains a **PSSession** or a command that gets a **PSSession**, such as a `Get-PSSession` command.</span></span>

<span data-ttu-id="19515-362">将其他会话中的模块导入当前会话中时，你可以在当前会话中使用来自模块的 cmdlet，就像你使用来自本地模块的 cmdlet 一样。</span><span class="sxs-lookup"><span data-stu-id="19515-362">When you import a module from a different session into the current session, you can use the cmdlets from the module in the current session, just as you would use cmdlets from a local module.</span></span> <span data-ttu-id="19515-363">使用远程 cmdlet 的命令在远程会话中运行，但是远程处理详细信息由 PowerShell 在后台进行管理。</span><span class="sxs-lookup"><span data-stu-id="19515-363">Commands that use the remote cmdlets run in the remote session, but the remoting details are managed in the background by PowerShell.</span></span>

<span data-ttu-id="19515-364">此参数使用 PowerShell 的隐式远程处理功能。</span><span class="sxs-lookup"><span data-stu-id="19515-364">This parameter uses the Implicit Remoting feature of PowerShell.</span></span> <span data-ttu-id="19515-365">它相当于使用 `Import-PSSession` cmdlet 从会话导入特定模块。</span><span class="sxs-lookup"><span data-stu-id="19515-365">It is equivalent to using the `Import-PSSession` cmdlet to import particular modules from a session.</span></span>

<span data-ttu-id="19515-366">`Import-Module` 无法从另一个会话导入 PowerShell Core 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-366">`Import-Module` cannot import PowerShell Core modules from another session.</span></span> <span data-ttu-id="19515-367">PowerShell Core 模块的名称以 Microsoft PowerShell 开头。</span><span class="sxs-lookup"><span data-stu-id="19515-367">The PowerShell Core modules have names that begin with Microsoft.PowerShell.</span></span>

<span data-ttu-id="19515-368">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-368">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PSSession, FullyQualifiedNameAndPSSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-369">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="19515-369">-RequiredVersion</span></span>

<span data-ttu-id="19515-370">指定此 cmdlet 导入的模块的版本。</span><span class="sxs-lookup"><span data-stu-id="19515-370">Specifies a version of the module that this cmdlet imports.</span></span> <span data-ttu-id="19515-371">如果未安装该版本，将 `Import-Module` 生成一个错误。</span><span class="sxs-lookup"><span data-stu-id="19515-371">If the version is not installed, `Import-Module` generates an error.</span></span>

<span data-ttu-id="19515-372">默认情况下， `Import-Module` 将导入该模块，而不检查版本号。</span><span class="sxs-lookup"><span data-stu-id="19515-372">By default, `Import-Module` imports the module without checking the version number.</span></span>

<span data-ttu-id="19515-373">若要指定最低版本，请使用 **MinimumVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-373">To specify a minimum version, use the **MinimumVersion** parameter.</span></span> <span data-ttu-id="19515-374">你还可以使用 **#Requires** 关键字的 **module** 和 **Version** 参数来要求在脚本中使用特定版本的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-374">You can also use the **Module** and **Version** parameters of the **#Requires** keyword to require a specific version of a module in a script.</span></span>

<span data-ttu-id="19515-375">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-375">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="19515-376">使用 **RequiredVersion** 导入现有 windows 操作系统版本随附的模块的脚本不会在将来版本的 windows 操作系统中自动运行。</span><span class="sxs-lookup"><span data-stu-id="19515-376">Scripts that use **RequiredVersion** to import modules that are included with existing releases of the Windows operating system don't automatically run in future releases of the Windows operating system.</span></span> <span data-ttu-id="19515-377">这是因为 Windows 操作系统未来版本中的 PowerShell 模块版本号高于 Windows 操作系统现有版本中的模块版本号。</span><span class="sxs-lookup"><span data-stu-id="19515-377">This is because PowerShell module version numbers in future releases of the Windows operating system are higher than module version numbers in existing releases of the Windows operating system.</span></span>

```yaml
Type: System.Version
Parameter Sets: Name, PSSession, CimSession
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-378">-Scope</span><span class="sxs-lookup"><span data-stu-id="19515-378">-Scope</span></span>

<span data-ttu-id="19515-379">指定此 cmdlet 将模块导入到其中的作用域。</span><span class="sxs-lookup"><span data-stu-id="19515-379">Specifies a scope into which this cmdlet imports the module.</span></span>

<span data-ttu-id="19515-380">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="19515-380">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="19515-381">**全局**。</span><span class="sxs-lookup"><span data-stu-id="19515-381">**Global**.</span></span> <span data-ttu-id="19515-382">可供会话中所有的命令使用。</span><span class="sxs-lookup"><span data-stu-id="19515-382">Available to all commands in the session.</span></span> <span data-ttu-id="19515-383">等效于 **Global** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-383">Equivalent to the **Global** parameter.</span></span>
- <span data-ttu-id="19515-384">**Local**。</span><span class="sxs-lookup"><span data-stu-id="19515-384">**Local**.</span></span> <span data-ttu-id="19515-385">仅在当前作用域中可用。</span><span class="sxs-lookup"><span data-stu-id="19515-385">Available only in the current scope.</span></span>

<span data-ttu-id="19515-386">默认情况下，当 `Import-Module` 从命令提示符、脚本文件或 scriptblock 调用 cmdlet 时，所有命令都将导入全局会话状态。</span><span class="sxs-lookup"><span data-stu-id="19515-386">By default, when `Import-Module` cmdlet is called from the command prompt, script file, or scriptblock, all the commands are imported into the global session state.</span></span> <span data-ttu-id="19515-387">可以使用参数将 `-Scope Local` 模块内容导入到脚本或 scriptblock 范围。</span><span class="sxs-lookup"><span data-stu-id="19515-387">You can use the `-Scope Local` parameter to import module content into the script or scriptblock scope.</span></span>

<span data-ttu-id="19515-388">从另一个模块调用时，cmdlet 会将 `Import-Module` 模块中的命令（包括来自嵌套模块的命令）导入到调用方的会话状态中。</span><span class="sxs-lookup"><span data-stu-id="19515-388">When invoked from another module, `Import-Module` cmdlet imports the commands in a module, including commands from nested modules, into the caller's session state.</span></span> <span data-ttu-id="19515-389">指定 `-Scope Global` 或 `-Global` 指示此 cmdlet 将模块导入全局会话状态，以便它们可用于会话中的所有命令。</span><span class="sxs-lookup"><span data-stu-id="19515-389">Specifying `-Scope Global` or `-Global` indicates that this cmdlet imports modules into the global session state so they are available to all commands in the session.</span></span>

<span data-ttu-id="19515-390">**Global** 参数等效于值为 **Global** 的 **Scope** 参数。</span><span class="sxs-lookup"><span data-stu-id="19515-390">The **Global** parameter is equivalent to the **Scope** parameter with a value of **Global**.</span></span>

<span data-ttu-id="19515-391">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="19515-391">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Local, Global

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="19515-392">-Variable</span><span class="sxs-lookup"><span data-stu-id="19515-392">-Variable</span></span>

<span data-ttu-id="19515-393">指定此 cmdlet 从模块导入到当前会话中的变量的数组。</span><span class="sxs-lookup"><span data-stu-id="19515-393">Specifies an array of variables that this cmdlet imports from the module into the current session.</span></span>
<span data-ttu-id="19515-394">输入变量的列表。</span><span class="sxs-lookup"><span data-stu-id="19515-394">Enter a list of variables.</span></span> <span data-ttu-id="19515-395">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="19515-395">Wildcard characters are permitted.</span></span>

<span data-ttu-id="19515-396">在导入模块时，某些变量会自动将选定的变量导出到你的会话中。</span><span class="sxs-lookup"><span data-stu-id="19515-396">Some modules automatically export selected variables into your session when you import the module.</span></span>
<span data-ttu-id="19515-397">此参数允许你在导出的变量中进行选择。</span><span class="sxs-lookup"><span data-stu-id="19515-397">This parameter lets you select from among the exported variables.</span></span>

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

### <span data-ttu-id="19515-398">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="19515-398">CommonParameters</span></span>
<span data-ttu-id="19515-399">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="19515-399">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="19515-400">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="19515-400">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="19515-401">输入</span><span class="sxs-lookup"><span data-stu-id="19515-401">INPUTS</span></span>

### <span data-ttu-id="19515-402">System.web、PSModuleInfo、System.string 和程序集。</span><span class="sxs-lookup"><span data-stu-id="19515-402">System.String, System.Management.Automation.PSModuleInfo, System.Reflection.Assembly</span></span>

<span data-ttu-id="19515-403">可以通过管道将模块名称、模块对象或程序集对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19515-403">You can pipe a module name, module object, or assembly object to this cmdlet.</span></span>

## <span data-ttu-id="19515-404">输出</span><span class="sxs-lookup"><span data-stu-id="19515-404">OUTPUTS</span></span>

### <span data-ttu-id="19515-405">"无"、"PSModuleInfo" 或 "PSCustomObject"</span><span class="sxs-lookup"><span data-stu-id="19515-405">None, System.Management.Automation.PSModuleInfo, or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="19515-406">默认情况下，不 `Import-Module` 会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="19515-406">By default, `Import-Module` does not generate any output.</span></span> <span data-ttu-id="19515-407">如果指定 **PassThru** 参数，则该 cmdlet 将生成表示该模块的 **PSModuleInfo** 对象。</span><span class="sxs-lookup"><span data-stu-id="19515-407">If you specify the **PassThru** parameter, the cmdlet generates a **System.Management.Automation.PSModuleInfo** object that represents the module.</span></span> <span data-ttu-id="19515-408">如果指定 **AsCustomObject** 参数，则会生成 **PSCustomObject** 对象。</span><span class="sxs-lookup"><span data-stu-id="19515-408">If you specify the **AsCustomObject** parameter, it generates a **PSCustomObject** object.</span></span>

## <span data-ttu-id="19515-409">注释</span><span class="sxs-lookup"><span data-stu-id="19515-409">NOTES</span></span>

- <span data-ttu-id="19515-410">在导入模块之前，必须在本地计算机上安装该模块。</span><span class="sxs-lookup"><span data-stu-id="19515-410">Before you can import a module, the module must be installed on the local computer.</span></span> <span data-ttu-id="19515-411">也就是说，必须将模块目录复制到本地计算机可以访问的目录中。</span><span class="sxs-lookup"><span data-stu-id="19515-411">That is, the module directory must be copied to a directory that is accessible to your local computer.</span></span> <span data-ttu-id="19515-412">有关详细信息，请参阅 [about_Modules](About/about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="19515-412">For more information, see [about_Modules](About/about_Modules.md).</span></span>

  <span data-ttu-id="19515-413">你还可以使用 **PSSession** 和 **CIMSession** 参数导入远程计算机上安装的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-413">You can also use the **PSSession** and **CIMSession** parameters to import modules that are installed on remote computers.</span></span> <span data-ttu-id="19515-414">但是，在这些模块中使用这些 cmdlet 的命令将在远程计算机上的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="19515-414">However, commands that use the cmdlets in these modules run in the remote session on the remote computer.</span></span>

- <span data-ttu-id="19515-415">如果将具有相同名称和相同类型的成员导入到会话中，则默认情况下，PowerShell 将使用上次导入的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-415">If you import members with the same name and the same type into your session, PowerShell uses the member imported last by default.</span></span> <span data-ttu-id="19515-416">将替换变量和别名，并且原始不可访问。</span><span class="sxs-lookup"><span data-stu-id="19515-416">Variables and aliases are replaced, and the originals aren't accessible.</span></span> <span data-ttu-id="19515-417">函数、cmdlet 和提供程序仅由新成员隐藏。</span><span class="sxs-lookup"><span data-stu-id="19515-417">Functions, cmdlets, and providers are merely shadowed by the new members.</span></span> <span data-ttu-id="19515-418">可以通过使用其管理单元、模块或函数路径的名称限定命令名称来访问它们。</span><span class="sxs-lookup"><span data-stu-id="19515-418">They can be accessed by qualifying the command name with the name of its snap-in, module, or function path.</span></span>

- <span data-ttu-id="19515-419">若要更新已从模块导入的命令的格式设置数据，请使用 `Update-FormatData` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19515-419">To update the formatting data for commands that have been imported from a module, use the `Update-FormatData` cmdlet.</span></span> <span data-ttu-id="19515-420">`Update-FormatData` 还会更新会话中从模块导入的命令的格式设置数据。</span><span class="sxs-lookup"><span data-stu-id="19515-420">`Update-FormatData` also updates the formatting data for commands in the session that were imported from modules.</span></span> <span data-ttu-id="19515-421">如果模块的格式化文件发生更改，则可以运行 `Update-FormatData` 命令来更新导入命令的格式设置数据。</span><span class="sxs-lookup"><span data-stu-id="19515-421">If the formatting file for a module changes, you can run an `Update-FormatData` command to update the formatting data for imported commands.</span></span> <span data-ttu-id="19515-422">不需要再次导入该模块。</span><span class="sxs-lookup"><span data-stu-id="19515-422">You don't need to import the module again.</span></span>

- <span data-ttu-id="19515-423">从 Windows PowerShell 3.0 开始，随 PowerShell 一起安装的核心命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="19515-423">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="19515-424">在 Windows PowerShell 2.0 和在 PowerShell 的更高版本中创建旧样式会话的主机程序中，核心命令打包在 (**PSSnapins**) 的管理单元中。</span><span class="sxs-lookup"><span data-stu-id="19515-424">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins (**PSSnapins**).</span></span> <span data-ttu-id="19515-425">**Microsoft.PowerShell.Core** 是例外情况，它始终是一个管理单元。</span><span class="sxs-lookup"><span data-stu-id="19515-425">The exception is **Microsoft.PowerShell.Core**, which is always a snap-in.</span></span> <span data-ttu-id="19515-426">远程会话（如 cmdlet 启动的会话） `New-PSSession` 是包含核心管理单元的旧样式会话。</span><span class="sxs-lookup"><span data-stu-id="19515-426">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="19515-427">有关 **CreateDefault2** 方法的信息，该方法可创建带有核心模块的更新样式的会话，请参阅 [CreateDefault2 方法](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2)。</span><span class="sxs-lookup"><span data-stu-id="19515-427">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see the [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2).</span></span>

- <span data-ttu-id="19515-428">在 Windows PowerShell 2.0 中，在导入模块之前，不会填充 module 对象的某些属性值，例如 **ExportedCmdlets** 和 **NestedModules** 属性值。</span><span class="sxs-lookup"><span data-stu-id="19515-428">In Windows PowerShell 2.0, some of the property values of the module object, such as the **ExportedCmdlets** and **NestedModules** property values, were not populated until the module was imported.</span></span>

- <span data-ttu-id="19515-429">如果尝试导入的模块包含与 Windows PowerShell 3.0 + 不兼容的混合模式程序集，将 `Import-Module` 返回如下错误消息。</span><span class="sxs-lookup"><span data-stu-id="19515-429">If you attempt to import a module that contains mixed-mode assemblies that aren't compatible with Windows PowerShell 3.0+, `Import-Module` returns an error message like the following one.</span></span>

  > <span data-ttu-id="19515-430">Import-Module：混合模式程序集是根据运行时的版本 "2.0.50727" 生成的，无法在4.0 运行时中加载，无需其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="19515-430">Import-Module : Mixed mode assembly is built against version 'v2.0.50727' of the runtime and cannot be loaded in the 4.0 runtime without additional configuration information.</span></span>

  <span data-ttu-id="19515-431">如果为 Windows PowerShell 2.0 设计的模块至少包含一个混合模块程序集，则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="19515-431">This error occurs when a module that is designed for Windows PowerShell 2.0 contains at least one mixed-module assembly.</span></span> <span data-ttu-id="19515-432">混合模块程序集，其中包括托管和非托管代码，例如 c + + 和 c #。</span><span class="sxs-lookup"><span data-stu-id="19515-432">A mixed-module assembly that includes both managed and non-managed code, such as C++ and C#.</span></span>

  <span data-ttu-id="19515-433">若要导入包含混合模式程序集的模块，请使用以下命令启动 Windows PowerShell 2.0，然后重试该 `Import-Module` 命令。</span><span class="sxs-lookup"><span data-stu-id="19515-433">To import a module that contains mixed-mode assemblies, start Windows PowerShell 2.0 by using the following command, and then try the `Import-Module` command again.</span></span>

  `PowerShell.exe -Version 2.0`

- <span data-ttu-id="19515-434">若要使用 CIM 会话功能，远程计算机必须具有 WS-Management 远程处理和 Windows Management Instrumentation (WMI)，后者是通用信息模型 (CIM) 标准的 Microsoft 实现。</span><span class="sxs-lookup"><span data-stu-id="19515-434">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="19515-435">计算机还必须具有具有相同基本功能的模拟发现 WMI 提供程序和备用 CIM 提供程序。</span><span class="sxs-lookup"><span data-stu-id="19515-435">The computer must also have the Module Discovery WMI provider or an alternate CIM provider that has the same basic features.</span></span>

  <span data-ttu-id="19515-436">你可以在未运行 Windows 操作系统的计算机上以及在具有 PowerShell 但未启用 PowerShell 远程处理的 Windows 计算机上使用 CIM 会话功能。</span><span class="sxs-lookup"><span data-stu-id="19515-436">You can use the CIM session feature on computers that aren't running a Windows operating system and on Windows computers that have PowerShell, but don't have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="19515-437">你还可以使用 CIM 参数从启用了 PowerShell 远程处理的计算机（包括本地计算机）中获取 CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="19515-437">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled, including the local computer.</span></span> <span data-ttu-id="19515-438">在本地计算机上创建 CIM 会话时，PowerShell 将使用 DCOM 而不是 WMI 来创建会话。</span><span class="sxs-lookup"><span data-stu-id="19515-438">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

- <span data-ttu-id="19515-439">默认情况下， `Import-Module` 即使从子代范围中调用，也会导入全局范围内的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-439">By default, `Import-Module` imports modules in the global scope even when called from a descendant scope.</span></span> <span data-ttu-id="19515-440">顶级范围和所有后代范围均有权访问模块的导出元素。</span><span class="sxs-lookup"><span data-stu-id="19515-440">The top-level scope and all descendant scopes have access to the module's exported elements.</span></span>

  <span data-ttu-id="19515-441">在后代范围内， `-Scope Local` 将导入限制为该作用域及其所有后代作用域。</span><span class="sxs-lookup"><span data-stu-id="19515-441">In a descendant scope, `-Scope Local` limits the import to that scope and all its descendant scopes.</span></span> <span data-ttu-id="19515-442">父作用域后，看不到导入的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-442">Parent scopes then do not see the imported members.</span></span>

  > [!NOTE]
  > <span data-ttu-id="19515-443">`Get-Module` 显示当前会话中加载的所有模块。</span><span class="sxs-lookup"><span data-stu-id="19515-443">`Get-Module` shows all modules loaded in the current session.</span></span> <span data-ttu-id="19515-444">这包括在后代范围本地加载的模块。</span><span class="sxs-lookup"><span data-stu-id="19515-444">This includes modules loaded locally in a descendant scope.</span></span> <span data-ttu-id="19515-445">使用 `Get-Command -Module modulename` 查看当前范围中加载的成员。</span><span class="sxs-lookup"><span data-stu-id="19515-445">Use `Get-Command -Module modulename` to see which members are loaded in the current scope.</span></span>

  <span data-ttu-id="19515-446">`Import-Module` 不加载模块中的类和枚举定义。</span><span class="sxs-lookup"><span data-stu-id="19515-446">`Import-Module` does not load class and enum definitions in the module.</span></span> <span data-ttu-id="19515-447">使用 `using module` 脚本开头的语句。</span><span class="sxs-lookup"><span data-stu-id="19515-447">Use the `using module` statement at the beginning of your script.</span></span> <span data-ttu-id="19515-448">这会导入模块，包括类和枚举定义。</span><span class="sxs-lookup"><span data-stu-id="19515-448">This imports the module, including the class and enum definitions.</span></span> <span data-ttu-id="19515-449">有关详细信息，请参阅 [about_Using](About/about_Using.md)。</span><span class="sxs-lookup"><span data-stu-id="19515-449">For more information, see [about_Using](About/about_Using.md).</span></span>

## <span data-ttu-id="19515-450">相关链接</span><span class="sxs-lookup"><span data-stu-id="19515-450">RELATED LINKS</span></span>

[<span data-ttu-id="19515-451">about_Modules</span><span class="sxs-lookup"><span data-stu-id="19515-451">about_Modules</span></span>](about/about_Modules.md)

[<span data-ttu-id="19515-452">Export-ModuleMember</span><span class="sxs-lookup"><span data-stu-id="19515-452">Export-ModuleMember</span></span>](Export-ModuleMember.md)

[<span data-ttu-id="19515-453">Get-Module</span><span class="sxs-lookup"><span data-stu-id="19515-453">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="19515-454">New-Module</span><span class="sxs-lookup"><span data-stu-id="19515-454">New-Module</span></span>](New-Module.md)

[<span data-ttu-id="19515-455">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="19515-455">Remove-Module</span></span>](Remove-Module.md)
