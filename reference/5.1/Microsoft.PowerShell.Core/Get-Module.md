---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-module?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Module
ms.openlocfilehash: 4098b40c01085b266fa279107e5795b1283705cd
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197437"
---
# <span data-ttu-id="0d128-103">Get-Module</span><span class="sxs-lookup"><span data-stu-id="0d128-103">Get-Module</span></span>

## <span data-ttu-id="0d128-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0d128-104">SYNOPSIS</span></span>
<span data-ttu-id="0d128-105">获取已导入或可导入到当前会话的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-105">Gets the modules that have been imported or that can be imported into the current session.</span></span>

## <span data-ttu-id="0d128-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0d128-106">SYNTAX</span></span>

### <span data-ttu-id="0d128-107">加载 (默认值) </span><span class="sxs-lookup"><span data-stu-id="0d128-107">Loaded (Default)</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [<CommonParameters>]
```

### <span data-ttu-id="0d128-108">可用</span><span class="sxs-lookup"><span data-stu-id="0d128-108">Available</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-All] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] [<CommonParameters>]
```

### <span data-ttu-id="0d128-109">PsSession</span><span class="sxs-lookup"><span data-stu-id="0d128-109">PsSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable]
 [-PSEdition <String>] [-Refresh] -PSSession <PSSession> [<CommonParameters>]
```

### <span data-ttu-id="0d128-110">CimSession</span><span class="sxs-lookup"><span data-stu-id="0d128-110">CimSession</span></span>

```
Get-Module [[-Name] <String[]>] [-FullyQualifiedName <ModuleSpecification[]>] [-ListAvailable] [-Refresh]
 -CimSession <CimSession> [-CimResourceUri <Uri>] [-CimNamespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="0d128-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0d128-111">DESCRIPTION</span></span>

<span data-ttu-id="0d128-112">该 `Get-Module` cmdlet 将获取已导入或可导入到 powershell 会话中的 powershell 模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-112">The `Get-Module` cmdlet gets the PowerShell modules that have been imported, or that can be imported, into a PowerShell session.</span></span>
<span data-ttu-id="0d128-113">返回的 module 对象 `Get-Module` 包含有关模块的重要信息。</span><span class="sxs-lookup"><span data-stu-id="0d128-113">The module object that `Get-Module` returns contains valuable information about the module.</span></span>
<span data-ttu-id="0d128-114">还可以通过管道将模块对象传递给其他 cmdlet，如 `Import-Module` 和 `Remove-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d128-114">You can also pipe the module objects to other cmdlets, such as the `Import-Module` and `Remove-Module` cmdlets.</span></span>

<span data-ttu-id="0d128-115">如果没有参数， `Get-Module` 将获取已导入到当前会话中的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-115">Without parameters, `Get-Module` gets modules that have been imported into the current session.</span></span>
<span data-ttu-id="0d128-116">若要获取所有已安装的模块，请指定 **ListAvailable** 参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-116">To get all installed modules, specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="0d128-117">`Get-Module` 获取模块，但不导入它们。</span><span class="sxs-lookup"><span data-stu-id="0d128-117">`Get-Module` gets modules, but it does not import them.</span></span>
<span data-ttu-id="0d128-118">从 Windows PowerShell 3.0 开始，当你使用模块中的命令时，将自动导入模块，但命令不会 `Get-Module` 触发自动导入。</span><span class="sxs-lookup"><span data-stu-id="0d128-118">Starting in Windows PowerShell 3.0, modules are automatically imported when you use a command in the module, but a `Get-Module` command does not trigger an automatic import.</span></span>
<span data-ttu-id="0d128-119">你还可以使用 cmdlet 将模块导入到会话中 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="0d128-119">You can also import the modules into your session by using the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="0d128-120">从 Windows PowerShell 3.0 开始，可以从远程会话中获取模块，然后将其导入到本地会话中。</span><span class="sxs-lookup"><span data-stu-id="0d128-120">Starting in Windows PowerShell 3.0, you can get and then, import modules from remote sessions into the local session.</span></span>
<span data-ttu-id="0d128-121">此策略使用 PowerShell 的隐式远程处理功能，等效于使用 `Import-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d128-121">This strategy uses the Implicit Remoting feature of PowerShell and is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="0d128-122">当你在从另一个会话导入的模块中使用命令时，这些命令将在远程会话中隐式运行。</span><span class="sxs-lookup"><span data-stu-id="0d128-122">When you use commands in modules imported from another session, the commands run implicitly in the remote session.</span></span> <span data-ttu-id="0d128-123">此功能使你可以从本地会话管理远程计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-123">This feature lets you manage the remote computer from the local session.</span></span>

<span data-ttu-id="0d128-124">此外，从 Windows PowerShell 3.0 开始，你可以使用 `Get-Module` 和 `Import-Module` 来获取和导入通用信息模型 (CIM) 模块，其中 Cmdlet 在 CMDLET 定义 XML (CDXML) 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="0d128-124">Also, starting in Windows PowerShell 3.0, you can use `Get-Module` and `Import-Module` to get and import Common Information Model (CIM) modules, in which the cmdlets are defined in Cmdlet Definition XML (CDXML) files.</span></span>
<span data-ttu-id="0d128-125">此功能允许你使用在非托管代码程序集中实现的 cmdlet，如用 c + + 编写的程序集。</span><span class="sxs-lookup"><span data-stu-id="0d128-125">This feature lets you use cmdlets that are implemented in non-managed code assemblies, such as those written in C++.</span></span>

<span data-ttu-id="0d128-126">借助这些新功能， `Get-Module` 和 `Import-Module` cmdlet 成为管理异类企业的主要工具，包括运行 Windows 操作系统的计算机和运行其他操作系统的计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-126">With these new features, the `Get-Module` and `Import-Module` cmdlets become primary tools for managing heterogeneous enterprises that include computers that run the Windows operating system and computers that run other operating systems.</span></span>

<span data-ttu-id="0d128-127">若要管理运行启用了 PowerShell 和 PowerShell 远程处理的 Windows 操作系统的远程计算机，请在远程计算机上创建 **PSSession** ，然后使用的 **Pssession** 参数 `Get-Module` 获取 **pssession** 中的 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-127">To manage remote computers that run the Windows operating system that have PowerShell and PowerShell remoting enabled, create a **PSSession** on the remote computer and then use the **PSSession** parameter of `Get-Module` to get the PowerShell modules in the **PSSession** .</span></span>
<span data-ttu-id="0d128-128">在导入模块，然后在当前会话中使用导入的命令时，命令将在远程计算机上的 **PSSession** 中隐式运行。</span><span class="sxs-lookup"><span data-stu-id="0d128-128">When you import the modules, and then use the imported commands in the current session, the commands run implicitly in the **PSSession** on the remote computer.</span></span>
<span data-ttu-id="0d128-129">你可以将此策略用于管理远程计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-129">You can use this strategy to manage the remote computer.</span></span>

<span data-ttu-id="0d128-130">你可以使用类似的策略来管理未启用 PowerShell 远程处理的计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-130">You can use a similar strategy to manage computers that do not have PowerShell remoting enabled.</span></span>
<span data-ttu-id="0d128-131">其中包括未运行 Windows 操作系统的计算机，以及安装了 PowerShell 但未启用 PowerShell 远程处理的计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-131">These include computers that are not running the Windows operating system, and computers that have PowerShell but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="0d128-132">首先，在远程计算机上创建 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="0d128-132">Start by creating a CIM session on the remote computer.</span></span>
<span data-ttu-id="0d128-133">CIM 会话是指与远程计算机上的 WMI) Windows Management Instrumentation (的连接。</span><span class="sxs-lookup"><span data-stu-id="0d128-133">A CIM session is a connection to Windows Management Instrumentation (WMI) on the remote computer.</span></span>
<span data-ttu-id="0d128-134">然后，使用的 **CIMSession** 参数 `Get-Module` 从 cim 会话中获取 cim 模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-134">Then use the **CIMSession** parameter of `Get-Module` to get CIM modules from the CIM session.</span></span>
<span data-ttu-id="0d128-135">使用 cmdlet 导入 CIM 模块， `Import-Module` 然后运行导入的命令时，命令将在远程计算机上隐式运行。</span><span class="sxs-lookup"><span data-stu-id="0d128-135">When you import a CIM module by using the `Import-Module` cmdlet and then run the imported commands, the commands run implicitly on the remote computer.</span></span>
<span data-ttu-id="0d128-136">你可以将此 WMI 和 CIM 策略用于管理远程计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-136">You can use this WMI and CIM strategy to manage the remote computer.</span></span>

## <span data-ttu-id="0d128-137">示例</span><span class="sxs-lookup"><span data-stu-id="0d128-137">EXAMPLES</span></span>

### <span data-ttu-id="0d128-138">示例1：获取导入到当前会话中的模块</span><span class="sxs-lookup"><span data-stu-id="0d128-138">Example 1: Get modules imported into the current session</span></span>

```powershell
Get-Module
```

<span data-ttu-id="0d128-139">此命令将获取已导入当前会话的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-139">This command gets modules that have been imported into the current session.</span></span>

### <span data-ttu-id="0d128-140">示例2：获取已安装模块和可用模块</span><span class="sxs-lookup"><span data-stu-id="0d128-140">Example 2: Get installed modules and available modules</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="0d128-141">此命令将获取已安装在计算机上的且可导入当前会话的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-141">This command gets the modules that are installed on the computer and can be imported into the current session.</span></span>

<span data-ttu-id="0d128-142">`Get-Module` 查找 **$env:P smodulepath** 环境变量指定的路径中的可用模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-142">`Get-Module` looks for available modules in the path specified by the **$env:PSModulePath** environment variable.</span></span>
<span data-ttu-id="0d128-143">有关 **PSModulePath** 的详细信息，请参阅 [about_Modules](About/about_Modules.md) 和 [about_Environment_Variables](About/about_Environment_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="0d128-143">For more information about **PSModulePath** , see [about_Modules](About/about_Modules.md) and [about_Environment_Variables](About/about_Environment_Variables.md).</span></span>

### <span data-ttu-id="0d128-144">示例3：获取所有导出的文件</span><span class="sxs-lookup"><span data-stu-id="0d128-144">Example 3: Get all exported files</span></span>

```powershell
Get-Module -ListAvailable -All
```

<span data-ttu-id="0d128-145">此命令将获取所有可用模块的所有导出的文件。</span><span class="sxs-lookup"><span data-stu-id="0d128-145">This command gets all of the exported files for all available modules.</span></span>

### <span data-ttu-id="0d128-146">示例4：按其完全限定名称获取模块</span><span class="sxs-lookup"><span data-stu-id="0d128-146">Example 4: Get a module by its fully qualified name</span></span>

```powershell
$FullyQualifedName = @{ModuleName="Microsoft.PowerShell.Management";ModuleVersion="3.1.0.0"}
Get-Module -FullyQualifiedName $FullyQualifedName | Format-Table -Property Name,Version
```

```Output
Name                             Version
----                             -------
Microsoft.PowerShell.Management  3.1.0.0
```

<span data-ttu-id="0d128-147">此命令通过使用 **FullyQualifiedName** 参数指定模块的完全限定名称来 **获取该模块。**</span><span class="sxs-lookup"><span data-stu-id="0d128-147">This command gets the **Microsoft.PowerShell.Management** module by specifying the fully qualified name of the module by using the **FullyQualifiedName** parameter.</span></span>
<span data-ttu-id="0d128-148">然后，该命令通过管道将结果传递 `Format-Table` 给 cmdlet，以将结果的格式设置为表，并将其 **名称** 和 **版本** 作为列标题。</span><span class="sxs-lookup"><span data-stu-id="0d128-148">The command then pipes the results into the `Format-Table` cmdlet to format the results as a table with **Name** and **Version** as the column headings.</span></span>

### <span data-ttu-id="0d128-149">示例5：获取模块的属性</span><span class="sxs-lookup"><span data-stu-id="0d128-149">Example 5: Get properties of a module</span></span>

```powershell
Get-Module | Get-Member -MemberType Property | Format-Table Name
```

```Output
Name
----
AccessMode
Author
ClrVersion
CompanyName
Copyright
Definition
Description
DotNetFrameworkVersion
ExportedAliases
ExportedCmdlets
ExportedCommands
ExportedFormatFiles
ExportedFunctions
ExportedTypeFiles
ExportedVariables
ExportedWorkflows
FileList
Guid
HelpInfoUri
LogPipelineExecutionDetails
ModuleBase
ModuleList
ModuleType
Name
NestedModules
OnRemove
Path
PowerShellHostName
PowerShellHostVersion
PowerShellVersion
PrivateData
ProcessorArchitecture
RequiredAssemblies
RequiredModules
RootModule
Scripts
SessionState
Version
```

<span data-ttu-id="0d128-150">此命令获取返回的 **PSModuleInfo** 对象的属性 `Get-Module` 。</span><span class="sxs-lookup"><span data-stu-id="0d128-150">This command gets the properties of the **PSModuleInfo** object that `Get-Module` returns.</span></span>
<span data-ttu-id="0d128-151">每个模块文件都有一个对应对象。</span><span class="sxs-lookup"><span data-stu-id="0d128-151">There is one object for each module file.</span></span>

<span data-ttu-id="0d128-152">可以使用属性来对模块对象进行格式设置和筛选。</span><span class="sxs-lookup"><span data-stu-id="0d128-152">You can use the properties to format and filter the module objects.</span></span>
<span data-ttu-id="0d128-153">有关属性的详细信息，请参阅 [PSModuleInfo properties](/dotnet/api/system.management.automation.psmoduleinfo)。</span><span class="sxs-lookup"><span data-stu-id="0d128-153">For more information about the properties, see [PSModuleInfo Properties](/dotnet/api/system.management.automation.psmoduleinfo).</span></span>

<span data-ttu-id="0d128-154">输出包含 Windows PowerShell 3.0 中引入的新属性（如 **Author** 和 **公司名称** ）。</span><span class="sxs-lookup"><span data-stu-id="0d128-154">The output includes the new properties, such as **Author** and **CompanyName** , that were introduced in Windows PowerShell 3.0.</span></span>

### <span data-ttu-id="0d128-155">示例6：按名称对所有模块分组</span><span class="sxs-lookup"><span data-stu-id="0d128-155">Example 6: Group all modules by name</span></span>

```powershell
Get-Module -ListAvailable -All | Format-Table -Property Name, Moduletype, Path -Groupby Name
```

```Output
Name: AppLocker

Name      ModuleType Path
----      ---------- ----
AppLocker   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\AppLocker\AppLocker.psd1


   Name: Appx

Name ModuleType Path
---- ---------- ----
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\en-US\Appx.psd1
Appx   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psd1
Appx     Script C:\Windows\system32\WindowsPowerShell\v1.0\Modules\Appx\Appx.psm1


   Name: BestPractices

Name          ModuleType Path
----          ---------- ----
BestPractices   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BestPractices\BestPractices.psd1


   Name: BitsTransfer

Name         ModuleType Path
----         ---------- ----
BitsTransfer   Manifest C:\Windows\system32\WindowsPowerShell\v1.0\Modules\BitsTransfer\BitsTransfer.psd1
```

<span data-ttu-id="0d128-156">此命令将获取所有模块文件（已导入并可用），然后按模块名称对其进行分组。</span><span class="sxs-lookup"><span data-stu-id="0d128-156">This command gets all module files, both imported and available, and then groups them by module name.</span></span> <span data-ttu-id="0d128-157">这使你能够查看每个脚本将要导出的模块文件。</span><span class="sxs-lookup"><span data-stu-id="0d128-157">This lets you see the module files that each script is exporting.</span></span>

### <span data-ttu-id="0d128-158">示例7：显示模块清单的内容</span><span class="sxs-lookup"><span data-stu-id="0d128-158">Example 7: Display the contents of a module manifest</span></span>

<span data-ttu-id="0d128-159">这些命令显示 Windows PowerShell **BitsTransfer** 模块的模块清单的内容。</span><span class="sxs-lookup"><span data-stu-id="0d128-159">These commands display the contents of the module manifest for the Windows PowerShell **BitsTransfer** module.</span></span>

<span data-ttu-id="0d128-160">模块不需要具有清单文件。</span><span class="sxs-lookup"><span data-stu-id="0d128-160">Modules are not required to have manifest files.</span></span>
<span data-ttu-id="0d128-161">如果它们具有清单文件，则需要清单文件才能包含版本号。</span><span class="sxs-lookup"><span data-stu-id="0d128-161">When they do have a manifest file, the manifest file is required only to include a version number.</span></span>
<span data-ttu-id="0d128-162">但是，清单文件通常可提供有关模块、模块要求和模块内容的有用信息。</span><span class="sxs-lookup"><span data-stu-id="0d128-162">However, manifest files often provide useful information about a module, its requirements, and its contents.</span></span>

```powershell
# First command
$m = Get-Module -list -Name BitsTransfer

# Second command
Get-Content $m.Path
```

```Output
@ {
    GUID               = "{8FA5064B-8479-4c5c-86EA-0D311FE48875}"
    Author             = "Microsoft Corporation"
    CompanyName        = "Microsoft Corporation"
    Copyright          = "Microsoft Corporation. All rights reserved."
    ModuleVersion      = "1.0.0.0"
    Description        = "Windows PowerShell File Transfer Module"
    PowerShellVersion  = "2.0"
    CLRVersion         = "2.0"
    NestedModules      = "Microsoft.BackgroundIntelligentTransfer.Management"
    FormatsToProcess   = "FileTransfer.Format.ps1xml"
    RequiredAssemblies = Join-Path $psScriptRoot "Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll"
}
```

<span data-ttu-id="0d128-163">第一个命令将获取表示 BitsTransfer 模块的 PSModuleInfo 对象。</span><span class="sxs-lookup"><span data-stu-id="0d128-163">The first command gets the PSModuleInfo object that represents BitsTransfer module.</span></span> <span data-ttu-id="0d128-164">它将对象保存在 `$m` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0d128-164">It saves the object in the `$m` variable.</span></span>

<span data-ttu-id="0d128-165">第二个命令使用 `Get-Content` cmdlet 获取指定路径中的清单文件的内容。</span><span class="sxs-lookup"><span data-stu-id="0d128-165">The second command uses the `Get-Content` cmdlet to get the content of the manifest file in the specified path.</span></span> <span data-ttu-id="0d128-166">它使用点表示法来获取存储在该对象的 Path 属性中的清单文件的路径。</span><span class="sxs-lookup"><span data-stu-id="0d128-166">It uses dot notation to get the path to the manifest file, which is stored in the Path property of the object.</span></span> <span data-ttu-id="0d128-167">输出显示了模块清单中的内容。</span><span class="sxs-lookup"><span data-stu-id="0d128-167">The output shows the contents of the module manifest.</span></span>

### <span data-ttu-id="0d128-168">示例8：列出模块目录中的文件</span><span class="sxs-lookup"><span data-stu-id="0d128-168">Example 8: List files in module directory</span></span>

```powershell
dir (Get-Module -ListAvailable FileTransfer).ModuleBase
```

```Output
Directory: C:\Windows\system32\WindowsPowerShell\v1.0\Modules\FileTransfer
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d----        12/16/2008  12:36 PM            en-US
-a---        11/19/2008  11:30 PM      16184 FileTransfer.Format.ps1xml
-a---        11/20/2008  11:30 PM       1044 FileTransfer.psd1
-a---        12/16/2008  12:20 AM     108544 Microsoft.BackgroundIntelligentTransfer.Management.Interop.dll
```

<span data-ttu-id="0d128-169">此命令将列出模块的目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="0d128-169">This command lists the files in the directory of the module.</span></span>
<span data-ttu-id="0d128-170">这是另一种用于在导入模块之前确定模块中的内容的方法。</span><span class="sxs-lookup"><span data-stu-id="0d128-170">This is another way to determine what is in a module before you import it.</span></span>
<span data-ttu-id="0d128-171">某些模块可能具有帮助文件或描述该模板的自述文件。</span><span class="sxs-lookup"><span data-stu-id="0d128-171">Some modules might have help files or ReadMe files that describe the module.</span></span>

### <span data-ttu-id="0d128-172">示例9：获取安装在计算机上的模块</span><span class="sxs-lookup"><span data-stu-id="0d128-172">Example 9: Get modules installed on a computer</span></span>

```powershell
$s = New-PSSession -ComputerName Server01

Get-Module -PSSession $s -ListAvailable
```

<span data-ttu-id="0d128-173">这些命令将获取安装在 Server01 计算机上的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-173">These commands get the modules that are installed on the Server01 computer.</span></span>

<span data-ttu-id="0d128-174">第一个命令使用 `New-PSSession` cmdlet 在 Server01 计算机上创建 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="0d128-174">The first command uses the `New-PSSession` cmdlet to create a **PSSession** on the Server01 computer.</span></span> <span data-ttu-id="0d128-175">该命令将 **PSSession** 保存在 $s 的变量中。</span><span class="sxs-lookup"><span data-stu-id="0d128-175">The command saves the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="0d128-176">第二个命令使用的 **pssession** 和 **ListAvailable** 参数 `Get-Module` 来获取 $s 变量的 **pssession** 中的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-176">The second command uses the **PSSession** and **ListAvailable** parameters of `Get-Module` to get the modules in the **PSSession** in the $s variable.</span></span>

<span data-ttu-id="0d128-177">如果通过管道将模块从其他会话传递到 `Import-Module` cmdlet，请 `Import-Module` 使用隐式远程处理功能将模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="0d128-177">If you pipe modules from other sessions to the `Import-Module` cmdlet, `Import-Module` imports the module into the current session by using the implicit remoting feature.</span></span>
<span data-ttu-id="0d128-178">这等效于使用 `Import-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d128-178">This is equivalent to using the `Import-PSSession` cmdlet.</span></span>
<span data-ttu-id="0d128-179">可以在当前会话中使用模块中的 cmdlet，但使用这些 cmdlet 的命令实际在远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="0d128-179">You can use the cmdlets from the module in the current session, but commands that use these cmdlets actually run the remote session.</span></span>
<span data-ttu-id="0d128-180">有关详细信息，请参阅 [`Import-Module`](Import-Module.md) 和 [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md)。</span><span class="sxs-lookup"><span data-stu-id="0d128-180">For more information, see [`Import-Module`](Import-Module.md) and [`Import-PSSession`](../Microsoft.PowerShell.Utility/Import-PSSession.md).</span></span>

### <span data-ttu-id="0d128-181">示例10：管理未运行 Windows 操作系统的计算机</span><span class="sxs-lookup"><span data-stu-id="0d128-181">Example 10: Manage a computer that does not run the Windows operating system</span></span>

<span data-ttu-id="0d128-182">此示例中的命令使你能够管理未运行 Windows 操作系统的远程计算机的存储系统。</span><span class="sxs-lookup"><span data-stu-id="0d128-182">The commands in this example enable you to manage the storage systems of a remote computer that is not running the Windows operating system.</span></span>
<span data-ttu-id="0d128-183">在此示例中，由于计算机的管理员已安装模块发现 WMI 提供程序，因此 CIM 命令可以使用专门用于该提供程序的默认值。</span><span class="sxs-lookup"><span data-stu-id="0d128-183">In this example, because the administrator of the computer has installed the Module Discovery WMI provider, the CIM commands can use the default values, which are designed for the provider.</span></span>

```powershell
$cs = New-CimSession -ComputerName RSDGF03
Get-Module -CimSession $cs -Name Storage | Import-Module
Get-Command Get-Disk
```

```Output
CommandType     Name                  ModuleName
-----------     ----                  ----------
Function        Get-Disk              Storage
```

```powershell
Get-Disk
```

```Output
Number Friendly Name              OperationalStatus          Total Size Partition Style
------ -------------              -----------------          ---------- ---------------
0      Virtual HD ATA Device      Online                          40 GB MBR
```

<span data-ttu-id="0d128-184">第一个命令使用 `New-CimSession` cmdlet 在 RSDGF03 远程计算机上创建会话。</span><span class="sxs-lookup"><span data-stu-id="0d128-184">The first command uses the `New-CimSession` cmdlet to create a session on the RSDGF03 remote computer.</span></span> <span data-ttu-id="0d128-185">该会话将连接到远程计算机上的 WMI。</span><span class="sxs-lookup"><span data-stu-id="0d128-185">The session connects to WMI on the remote computer.</span></span> <span data-ttu-id="0d128-186">此命令将 CIM 会话保存在 `$cs` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0d128-186">The command saves the CIM session in the `$cs` variable.</span></span>

<span data-ttu-id="0d128-187">第二个命令使用变量中的 CIM 会话在 `$cs` `Get-Module` RSDGF03 计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="0d128-187">The second command uses the CIM session in the `$cs` variable to run a `Get-Module` command on the RSDGF03 computer.</span></span> <span data-ttu-id="0d128-188">该命令使用 Name 参数指定 Storage 模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-188">The command uses the Name parameter to specify the Storage module.</span></span> <span data-ttu-id="0d128-189">该命令使用管道运算符 (|) 将存储模块发送到 `Import-Module` cmdlet，后者将其导入到本地会话中。</span><span class="sxs-lookup"><span data-stu-id="0d128-189">The command uses a pipeline operator (|) to send the Storage module to the `Import-Module` cmdlet, which imports it into the local session.</span></span>

<span data-ttu-id="0d128-190">第三个命令在 `Get-Command` `Get-Disk` 存储模块的命令中运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d128-190">The third command runs the `Get-Command` cmdlet on the `Get-Disk` command in the Storage module.</span></span>
<span data-ttu-id="0d128-191">将 CIM 模块导入到本地会话中时，PowerShell 会将表示 CIM 模块的 CDXML 文件转换为 PowerShell 脚本，这些脚本在本地会话中显示为函数。</span><span class="sxs-lookup"><span data-stu-id="0d128-191">When you import a CIM module into the local session, PowerShell converts the CDXML files that represent the CIM module into PowerShell scripts, which appear as functions in the local session.</span></span>

<span data-ttu-id="0d128-192">第四个命令运行 `Get-Disk` 命令。</span><span class="sxs-lookup"><span data-stu-id="0d128-192">The fourth command runs the `Get-Disk` command.</span></span> <span data-ttu-id="0d128-193">尽管该命令是在本地会话中键入的，但它实际在导入它的远程计算机上隐式运行。</span><span class="sxs-lookup"><span data-stu-id="0d128-193">Although the command is typed in the local session, it runs implicitly on the remote computer from which it was imported.</span></span> <span data-ttu-id="0d128-194">该命令将获取远程计算机中的对象，并将它们返回到本地会话。</span><span class="sxs-lookup"><span data-stu-id="0d128-194">The command gets objects from the remote computer and returns them to the local session.</span></span>

## <span data-ttu-id="0d128-195">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0d128-195">PARAMETERS</span></span>

### <span data-ttu-id="0d128-196">-All</span><span class="sxs-lookup"><span data-stu-id="0d128-196">-All</span></span>

<span data-ttu-id="0d128-197">指示此 cmdlet 获取每个模块文件夹中的所有模块（包括嵌套模块、清单 ( psd1) 文件、脚本模块 () 文件）和二进制模块 ( 文件。</span><span class="sxs-lookup"><span data-stu-id="0d128-197">Indicates that this cmdlet gets all modules in each module folder, including nested modules, manifest (.psd1) files, script module (.psm1) files, and binary module (.dll) files.</span></span>
<span data-ttu-id="0d128-198">如果没有此参数， `Get-Module` 则仅获取每个模块文件夹中的默认模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-198">Without this parameter, `Get-Module` gets only the default module in each module folder.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Loaded, Available
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d128-199">-CimNamespace</span><span class="sxs-lookup"><span data-stu-id="0d128-199">-CimNamespace</span></span>

<span data-ttu-id="0d128-200">指定可公开 CIM 模块的备用 CIM 提供程序的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0d128-200">Specifies the namespace of an alternate CIM provider that exposes CIM modules.</span></span>
<span data-ttu-id="0d128-201">默认值是模块发现 WMI 提供程序的命名空间。</span><span class="sxs-lookup"><span data-stu-id="0d128-201">The default value is the namespace of the Module Discovery WMI provider.</span></span>

<span data-ttu-id="0d128-202">使用此参数从未运行 Windows 操作系统的计算机和设备获取 CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-202">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="0d128-203">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0d128-204">-CimResourceUri</span><span class="sxs-lookup"><span data-stu-id="0d128-204">-CimResourceUri</span></span>

<span data-ttu-id="0d128-205">指定 CIM 模块的备用位置。</span><span class="sxs-lookup"><span data-stu-id="0d128-205">Specifies an alternate location for CIM modules.</span></span>
<span data-ttu-id="0d128-206">默认值是远程计算机上模块发现 WMI 提供程序的资源 URI。</span><span class="sxs-lookup"><span data-stu-id="0d128-206">The default value is the resource URI of the Module Discovery WMI provider on the remote computer.</span></span>

<span data-ttu-id="0d128-207">使用此参数从未运行 Windows 操作系统的计算机和设备获取 CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-207">Use this parameter to get CIM modules from computers and devices that are not running the Windows operating system.</span></span>

<span data-ttu-id="0d128-208">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-208">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0d128-209">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0d128-209">-CimSession</span></span>

<span data-ttu-id="0d128-210">指定远程计算机上的 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="0d128-210">Specifies a CIM session on the remote computer.</span></span>
<span data-ttu-id="0d128-211">输入包含 CIM 会话的变量或获取 CIM 会话的命令（如 [CimSession](/powershell/module/cimcmdlets/get-cimsession) 命令）。</span><span class="sxs-lookup"><span data-stu-id="0d128-211">Enter a variable that contains the CIM session or a command that gets the CIM session, such as a [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) command.</span></span>

<span data-ttu-id="0d128-212">`Get-Module` 使用 CIM 会话连接从远程计算机获取模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-212">`Get-Module` uses the CIM session connection to get modules from the remote computer.</span></span>
<span data-ttu-id="0d128-213">使用 cmdlet 导入模块 `Import-Module` 并在当前会话中使用导入模块中的命令时，命令实际上在远程计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="0d128-213">When you import the module by using the `Import-Module` cmdlet and use the commands from the imported module in the current session, the commands actually run on the remote computer.</span></span>

<span data-ttu-id="0d128-214">你可以使用此参数从未运行 Windows 操作系统的计算机和设备中获取模块，并使用具有 PowerShell 但未启用 PowerShell 远程处理的计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-214">You can use this parameter to get modules from computers and devices that are not running the Windows operating system, and computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

<span data-ttu-id="0d128-215">**CimSession** 参数可获取 **CIMSession** 中的所有模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-215">The **CimSession** parameter gets all modules in the **CIMSession** .</span></span>
<span data-ttu-id="0d128-216">但是，你只能导入基于 CIM 和基于 Cmdlet 定义 XML (CDXML) 的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-216">However, you can import only CIM-based and Cmdlet Definition XML (CDXML)-based modules.</span></span>

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

### <span data-ttu-id="0d128-217">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="0d128-217">-FullyQualifiedName</span></span>

<span data-ttu-id="0d128-218">以 **ModuleSpecification** 对象的形式指定模块的名称。</span><span class="sxs-lookup"><span data-stu-id="0d128-218">Specifies names of modules in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="0d128-219">此类对象在 ModuleSpecification 构造函数的 "备注" 部分中进行了介绍， [ (哈希表 ](https://msdn.microsoft.com/library/jj136290) 在 MSDN library 中) 。</span><span class="sxs-lookup"><span data-stu-id="0d128-219">These objects are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290) in the MSDN library.</span></span>
<span data-ttu-id="0d128-220">例如， **FullyQualifiedName** 参数接受以下格式指定的模块名称：</span><span class="sxs-lookup"><span data-stu-id="0d128-220">For example, the **FullyQualifiedName** parameter accepts a module name that is specified in the following formats:</span></span>

- <span data-ttu-id="0d128-221">@ {ModuleName = "ModuleName";ModuleVersion = "version_number"}</span><span class="sxs-lookup"><span data-stu-id="0d128-221">@{ModuleName = "modulename"; ModuleVersion = "version_number"}</span></span>
- <span data-ttu-id="0d128-222">@ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}</span><span class="sxs-lookup"><span data-stu-id="0d128-222">@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}</span></span>

<span data-ttu-id="0d128-223">**ModuleName** 和 **ModuleVersion** 是必需的，但 **Guid** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="0d128-223">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="0d128-224">不能在与 **Name** 参数相同的命令中指定 **FullyQualifiedName** 参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-224">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

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

### <span data-ttu-id="0d128-225">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="0d128-225">-ListAvailable</span></span>

<span data-ttu-id="0d128-226">指示此 cmdlet 获取所有已安装的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-226">Indicates that this cmdlet gets all installed modules.</span></span>
<span data-ttu-id="0d128-227">`Get-Module` 获取 **PSModulePath** 环境变量中列出的路径中的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-227">`Get-Module` gets modules in paths listed in the **PSModulePath** environment variable.</span></span>
<span data-ttu-id="0d128-228">如果没有此参数，则 `Get-Module` 仅获取在 **PSModulePath** 环境变量中列出的、在当前会话中加载的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-228">Without this parameter, `Get-Module` gets only the modules that are both listed in the **PSModulePath** environment variable, and that are loaded in the current session.</span></span>
<span data-ttu-id="0d128-229">**ListAvailable** 不会返回未在 **PSModulePath** 环境变量中找到的模块的相关信息，即使在当前会话中加载了这些模块也是如此。</span><span class="sxs-lookup"><span data-stu-id="0d128-229">**ListAvailable** does not return information about modules that are not found in the **PSModulePath** environment variable, even if those modules are loaded in the current session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Available, PsSession, CimSession
Aliases:

Required: True (Available), False (PsSession, CimSession)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d128-230">-Name</span><span class="sxs-lookup"><span data-stu-id="0d128-230">-Name</span></span>

<span data-ttu-id="0d128-231">指定此 cmdlet 获取的模块的名称或名称模式。</span><span class="sxs-lookup"><span data-stu-id="0d128-231">Specifies names or name patterns of modules that this cmdlet gets.</span></span>
<span data-ttu-id="0d128-232">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="0d128-232">Wildcard characters are permitted.</span></span>
<span data-ttu-id="0d128-233">还可以通过管道将名称传递给 `Get-Module` 。</span><span class="sxs-lookup"><span data-stu-id="0d128-233">You can also pipe the names to `Get-Module`.</span></span>
<span data-ttu-id="0d128-234">不能在与 **Name** 参数相同的命令中指定 **FullyQualifiedName** 参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-234">You cannot specify the **FullyQualifiedName** parameter in the same command as a **Name** parameter.</span></span>

<span data-ttu-id="0d128-235">**名称** 不能接受模块 GUID 作为值。</span><span class="sxs-lookup"><span data-stu-id="0d128-235">**Name** cannot accept a module GUID as a value.</span></span>
<span data-ttu-id="0d128-236">若要通过指定 GUID 来返回模块，请改用 **FullyQualifiedName** 。</span><span class="sxs-lookup"><span data-stu-id="0d128-236">To return modules by specifying a GUID, use **FullyQualifiedName** instead.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="0d128-237">-PSEdition</span><span class="sxs-lookup"><span data-stu-id="0d128-237">-PSEdition</span></span>

<span data-ttu-id="0d128-238">获取支持指定的 PowerShell 版本的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-238">Gets the modules that support specified edition of PowerShell.</span></span>

<span data-ttu-id="0d128-239">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="0d128-239">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0d128-240">桌面型</span><span class="sxs-lookup"><span data-stu-id="0d128-240">Desktop</span></span>
- <span data-ttu-id="0d128-241">核心</span><span class="sxs-lookup"><span data-stu-id="0d128-241">Core</span></span>

<span data-ttu-id="0d128-242">Get-Module cmdlet 检查 **PSModuleInfo** 对象的 **CompatiblePSEditions** 属性中是否存在指定的值，并仅返回已设置了该属性的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-242">The Get-Module cmdlet checks **CompatiblePSEditions** property of **PSModuleInfo** object for the specified value and returns only those modules that have it set.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0d128-243">**桌面版：** 以 .NET Framework 为基础构建，提供与面向在完整功能 Windows 版本（如服务器核心和 Windows 桌面）上运行的 PowerShell 版本的脚本和模块的兼容性。</span><span class="sxs-lookup"><span data-stu-id="0d128-243">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
> - <span data-ttu-id="0d128-244">**核心版：** 以 .NET Core 为基础构建，提供与面向在缩减功能 Windows 版本（如 Nano Server 和 Windows IoT）上运行的 PowerShell 版本的脚本和模块的兼容性。</span><span class="sxs-lookup"><span data-stu-id="0d128-244">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

```yaml
Type: System.String
Parameter Sets: PsSession, Available
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d128-245">-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d128-245">-PSSession</span></span>

<span data-ttu-id="0d128-246">获取 ( **PSSession** ) 的指定用户管理的 PowerShell 会话中的模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-246">Gets the modules in the specified user-managed PowerShell session ( **PSSession** ).</span></span>
<span data-ttu-id="0d128-247">输入包含会话的变量、获取会话的命令（如 `Get-PSSession` 命令）或创建会话的命令（如 `New-PSSession` 命令）。</span><span class="sxs-lookup"><span data-stu-id="0d128-247">Enter a variable that contains the session, a command that gets the session, such as a `Get-PSSession` command, or a command that creates the session, such as a `New-PSSession` command.</span></span>

<span data-ttu-id="0d128-248">如果会话连接到远程计算机，则必须指定 **ListAvailable** 参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-248">When the session is connected to a remote computer, you must specify the **ListAvailable** parameter.</span></span>

<span data-ttu-id="0d128-249">`Get-Module`使用 **pssession** 参数的命令等效于使用 `Invoke-Command` cmdlet `Get-Module -ListAvailable` 在 **PSSession** 中运行命令。</span><span class="sxs-lookup"><span data-stu-id="0d128-249">A `Get-Module` command that uses the **PSSession** parameter is equivalent to using the `Invoke-Command` cmdlet to run a `Get-Module -ListAvailable` command in a **PSSession** .</span></span>

<span data-ttu-id="0d128-250">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-250">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: PsSession
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d128-251">-刷新</span><span class="sxs-lookup"><span data-stu-id="0d128-251">-Refresh</span></span>

<span data-ttu-id="0d128-252">指示此 cmdlet 刷新已安装命令的缓存。</span><span class="sxs-lookup"><span data-stu-id="0d128-252">Indicates that this cmdlet refreshes the cache of installed commands.</span></span>
<span data-ttu-id="0d128-253">命令缓存是在会话启动时创建的。</span><span class="sxs-lookup"><span data-stu-id="0d128-253">The command cache is created when the session starts.</span></span>
<span data-ttu-id="0d128-254">它使 `Get-Command` cmdlet 能够从未导入到会话中的模块中获取命令。</span><span class="sxs-lookup"><span data-stu-id="0d128-254">It enables the `Get-Command` cmdlet to get commands from modules that are not imported into the session.</span></span>

<span data-ttu-id="0d128-255">此参数旨在用于开发和测试方案，在这些方案中，模块的内容自会话启动后已发生更改。</span><span class="sxs-lookup"><span data-stu-id="0d128-255">This parameter is designed for development and testing scenarios in which the contents of modules have changed since the session started.</span></span>

<span data-ttu-id="0d128-256">在命令中指定 **Refresh** 参数时，必须指定 **ListAvailable** 。</span><span class="sxs-lookup"><span data-stu-id="0d128-256">When you specify the **Refresh** parameter in a command, you must specify **ListAvailable** .</span></span>

<span data-ttu-id="0d128-257">已在 Windows PowerShell 3.0 中引入了此参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-257">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PsSession, Available, CimSession
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0d128-258">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0d128-258">CommonParameters</span></span>

<span data-ttu-id="0d128-259">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0d128-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0d128-260">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0d128-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0d128-261">输入</span><span class="sxs-lookup"><span data-stu-id="0d128-261">INPUTS</span></span>

### <span data-ttu-id="0d128-262">System.String</span><span class="sxs-lookup"><span data-stu-id="0d128-262">System.String</span></span>

<span data-ttu-id="0d128-263">可以通过管道将模块名称传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0d128-263">You can pipe module names to this cmdlet.</span></span>

## <span data-ttu-id="0d128-264">输出</span><span class="sxs-lookup"><span data-stu-id="0d128-264">OUTPUTS</span></span>

### <span data-ttu-id="0d128-265">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="0d128-265">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="0d128-266">此 cmdlet 返回表示模块的对象。</span><span class="sxs-lookup"><span data-stu-id="0d128-266">This cmdlet returns objects that represent modules.</span></span>
<span data-ttu-id="0d128-267">指定 **ListAvailable** 参数时，将 `Get-Module` 返回 **ModuleInfoGrouping** 对象，该对象是具有相同属性和方法的 **PSModuleInfo** 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="0d128-267">When you specify the **ListAvailable** parameter, `Get-Module` returns a **ModuleInfoGrouping** object, which is a type of **PSModuleInfo** object that has the same properties and methods.</span></span>

## <span data-ttu-id="0d128-268">注释</span><span class="sxs-lookup"><span data-stu-id="0d128-268">NOTES</span></span>

- <span data-ttu-id="0d128-269">从 Windows PowerShell 3.0 开始，PowerShell 中包含的核心命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="0d128-269">Beginning in Windows PowerShell 3.0, the core commands that are included in PowerShell are packaged in modules.</span></span> <span data-ttu-id="0d128-270">异常是 Add-pssnapin **，它是一个** 管理单元， ( **PSSnapin** ) 。</span><span class="sxs-lookup"><span data-stu-id="0d128-270">The exception is **Microsoft.PowerShell.Core** , which is a snap-in ( **PSSnapin** ).</span></span> <span data-ttu-id="0d128-271">默认情况下，仅将 **Microsoft.PowerShell.Core** 管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="0d128-271">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="0d128-272">首次使用时自动导入模块，你可以使用 `Import-Module` cmdlet 将其导入。</span><span class="sxs-lookup"><span data-stu-id="0d128-272">Modules are imported automatically on first use and you can use the `Import-Module` cmdlet to import them.</span></span>
- <span data-ttu-id="0d128-273">从 Windows PowerShell 3.0 开始，随 PowerShell 一起安装的核心命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="0d128-273">Starting in Windows PowerShell 3.0, the core commands that are installed with PowerShell are packaged in modules.</span></span> <span data-ttu-id="0d128-274">在 Windows PowerShell 2.0 和在 PowerShell 的更高版本中创建旧样式会话的主机程序中，核心命令打包在 ( **PSSnapins** ) 的管理单元中。</span><span class="sxs-lookup"><span data-stu-id="0d128-274">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of PowerShell, the core commands are packaged in snap-ins ( **PSSnapins** ).</span></span> <span data-ttu-id="0d128-275">**Microsoft.PowerShell.Core** 是例外情况，它始终是一个管理单元。</span><span class="sxs-lookup"><span data-stu-id="0d128-275">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="0d128-276">远程会话（如 cmdlet 启动的会话） `New-PSSession` 是包含核心管理单元的旧样式会话。</span><span class="sxs-lookup"><span data-stu-id="0d128-276">Also, remote sessions, such as those started by the `New-PSSession` cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="0d128-277">有关 **CreateDefault2** 方法的详细信息，请参阅 MSDN library 中的 [CreateDefault2 方法](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) 。</span><span class="sxs-lookup"><span data-stu-id="0d128-277">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](/dotnet/api/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

- <span data-ttu-id="0d128-278">`Get-Module` 仅在存储在 **PSModulePath** 环境变量的值中的位置获取模块 ($Env:P smodulepath) 。</span><span class="sxs-lookup"><span data-stu-id="0d128-278">`Get-Module` only gets modules in locations that are stored in the value of the **PSModulePath** environment variable ($env:PSModulePath).</span></span> <span data-ttu-id="0d128-279">您可以使用该 cmdlet 的 **Path** 参数将 `Import-Module` 模块导入其他位置，但不能使用 `Get-Module` cmdlet 来获取它们。</span><span class="sxs-lookup"><span data-stu-id="0d128-279">You can use the **Path** parameter of the `Import-Module` cmdlet to import modules in other locations, but you cannot use the `Get-Module` cmdlet to get them.</span></span>
- <span data-ttu-id="0d128-280">此外，从 PowerShell 3.0 开始，新的属性已添加到返回的对象，以便在 `Get-Module` 导入模块之前更容易了解模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-280">Also, starting in PowerShell 3.0, new properties have been added to the object that `Get-Module` returns that make it easier to learn about modules even before they are imported.</span></span> <span data-ttu-id="0d128-281">导入之前会填充所有属性。</span><span class="sxs-lookup"><span data-stu-id="0d128-281">All properties are populated before importing.</span></span> <span data-ttu-id="0d128-282">其中包括列出模块导出的命令的 **ExportedCommands** 、 **ExportedCmdlets** 和 **ExportedFunctions** 属性。</span><span class="sxs-lookup"><span data-stu-id="0d128-282">These include the **ExportedCommands** , **ExportedCmdlets** and **ExportedFunctions** properties that list the commands that the module exports.</span></span>
- <span data-ttu-id="0d128-283">**ListAvailable** 参数仅获取格式正确的模块，即包含至少一个文件（其基名称与模块文件夹的名称相同）的文件夹。</span><span class="sxs-lookup"><span data-stu-id="0d128-283">The **ListAvailable** parameter gets only well-formed modules, that is, folders that contain at least one file whose base name is the same as the name of the module folder.</span></span> <span data-ttu-id="0d128-284">基名称是不带文件扩展名的名称。</span><span class="sxs-lookup"><span data-stu-id="0d128-284">The base name is the name without the file name extension.</span></span> <span data-ttu-id="0d128-285">如果文件夹包含具有不同名称的文件，则这些文件夹将被视为容器，而不是模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-285">Folders that contain files that have different names are considered to be containers, but not modules.</span></span>

  <span data-ttu-id="0d128-286">若要获取作为 .dll 文件实现但未包含在模块文件夹中的模块，请同时指定 **ListAvailable** 和 **All** 参数。</span><span class="sxs-lookup"><span data-stu-id="0d128-286">To get modules that are implemented as .dll files, but are not enclosed in a module folder, specify both the **ListAvailable** and **All** parameters.</span></span>

- <span data-ttu-id="0d128-287">若要使用 CIM 会话功能，远程计算机必须具有 WS-Management 远程处理和 Windows Management Instrumentation (WMI)，后者是通用信息模型 (CIM) 标准的 Microsoft 实现。</span><span class="sxs-lookup"><span data-stu-id="0d128-287">To use the CIM session feature, the remote computer must have WS-Management remoting and Windows Management Instrumentation (WMI), which is the Microsoft implementation of the Common Information Model (CIM) standard.</span></span> <span data-ttu-id="0d128-288">计算机必须还具有模块发现 WMI 提供程序或具有相同基本功能的备用 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="0d128-288">The computer must also have the Module Discovery WMI provider or an alternate WMI provider that has the same basic features.</span></span>

  <span data-ttu-id="0d128-289">你可以在未运行 Windows 操作系统的计算机和具有 PowerShell 但未启用 PowerShell 远程处理的 Windows 计算机上使用 CIM 会话功能。</span><span class="sxs-lookup"><span data-stu-id="0d128-289">You can use the CIM session feature on computers that are not running the Windows operating system and on Windows computers that have PowerShell, but do not have PowerShell remoting enabled.</span></span>

  <span data-ttu-id="0d128-290">你还可以使用 CIM 参数从启用了 PowerShell 远程处理的计算机中获取 CIM 模块。</span><span class="sxs-lookup"><span data-stu-id="0d128-290">You can also use the CIM parameters to get CIM modules from computers that have PowerShell remoting enabled.</span></span> <span data-ttu-id="0d128-291">这包括本地计算机。</span><span class="sxs-lookup"><span data-stu-id="0d128-291">This includes the local computer.</span></span>
<span data-ttu-id="0d128-292">在本地计算机上创建 CIM 会话时，PowerShell 将使用 DCOM 而不是 WMI 来创建会话。</span><span class="sxs-lookup"><span data-stu-id="0d128-292">When you create a CIM session on the local computer, PowerShell uses DCOM, instead of WMI, to create the session.</span></span>

## <span data-ttu-id="0d128-293">相关链接</span><span class="sxs-lookup"><span data-stu-id="0d128-293">RELATED LINKS</span></span>

[<span data-ttu-id="0d128-294">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="0d128-294">Get-CimSession</span></span>](../CimCmdlets/Get-CimSession.md)

[<span data-ttu-id="0d128-295">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="0d128-295">New-CimSession</span></span>](../CimCmdlets/New-CimSession.md)

[<span data-ttu-id="0d128-296">about_Modules</span><span class="sxs-lookup"><span data-stu-id="0d128-296">about_Modules</span></span>](About/about_Modules.md)

[<span data-ttu-id="0d128-297">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d128-297">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="0d128-298">Import-Module</span><span class="sxs-lookup"><span data-stu-id="0d128-298">Import-Module</span></span>](Import-Module.md)

[<span data-ttu-id="0d128-299">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d128-299">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="0d128-300">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="0d128-300">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="0d128-301">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="0d128-301">Remove-Module</span></span>](Remove-Module.md)
