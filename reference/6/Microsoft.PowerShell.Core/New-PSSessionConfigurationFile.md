---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: 1045c22cdaadb9fe1a45ec01ea86d5d8a276b05a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198533"
---
# <span data-ttu-id="ea654-103">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ea654-103">New-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="ea654-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ea654-104">SYNOPSIS</span></span>
<span data-ttu-id="ea654-105">创建用于定义会话配置的文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-105">Creates a file that defines a session configuration.</span></span>

## <span data-ttu-id="ea654-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ea654-106">SYNTAX</span></span>

```
New-PSSessionConfigurationFile [-Path] <String> [-SchemaVersion <Version>] [-Guid <Guid>]
 [-Author <String>] [-Description <String>] [-CompanyName <String>] [-Copyright <String>]
 [-SessionType <SessionType>] [-TranscriptDirectory <String>] [-RunAsVirtualAccount]
 [-RunAsVirtualAccountGroups <String[]>] [-MountUserDrive] [-UserDriveMaximumSize <Int64>]
 [-GroupManagedServiceAccount <String>] [-ScriptsToProcess <String[]>]
 [-RoleDefinitions <IDictionary>] [-RequiredGroups <IDictionary>] [-LanguageMode <PSLanguageMode>]
 [-ExecutionPolicy <ExecutionPolicy>] [-PowerShellVersion <Version>] [-ModulesToImport <Object[]>]
 [-VisibleAliases <String[]>] [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>]
 [-VisibleExternalCommands <String[]>] [-VisibleProviders <String[]>]
 [-AliasDefinitions <IDictionary[]>] [-FunctionDefinitions <IDictionary[]>]
 [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>] [-Full] [<CommonParameters>]
```

## <span data-ttu-id="ea654-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ea654-107">DESCRIPTION</span></span>

<span data-ttu-id="ea654-108">`New-PSSessionConfigurationFile`Cmdlet 将创建一个设置文件，用于定义会话配置，以及使用会话配置创建的会话的环境。</span><span class="sxs-lookup"><span data-stu-id="ea654-108">The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration.</span></span>
<span data-ttu-id="ea654-109">若要在会话配置中使用该文件，请使用或 cmdlet 的 **Path** 参数 `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-109">To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="ea654-110">创建的会话配置文件 `New-PSSessionConfigurationFile` 是一个可读的文本文件，其中包含会话配置属性和值的哈希表。</span><span class="sxs-lookup"><span data-stu-id="ea654-110">The session configuration file that `New-PSSessionConfigurationFile` creates is a human-readable text file that contains a hash table of the session configuration properties and values.</span></span> <span data-ttu-id="ea654-111">文件具有文件 `.pssc` 扩展名。</span><span class="sxs-lookup"><span data-stu-id="ea654-111">The file has a `.pssc` filename extension.</span></span>

<span data-ttu-id="ea654-112">`New-PSSessionConfigurationFile`除 **Path** 参数外，所有参数都是可选的。</span><span class="sxs-lookup"><span data-stu-id="ea654-112">All parameters of `New-PSSessionConfigurationFile` are optional, except for the **Path** parameter.</span></span>
<span data-ttu-id="ea654-113">如果省略一个参数，则将注释掉会话配置文件中的相应键，已在参数说明中注明的除外。</span><span class="sxs-lookup"><span data-stu-id="ea654-113">If you omit a parameter, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span>

<span data-ttu-id="ea654-114">会话配置（也称为终结点）是本地计算机上的一组设置，用于定义连接到计算机 ( **pssession** ) 的 PowerShell 会话的环境。</span><span class="sxs-lookup"><span data-stu-id="ea654-114">A session configuration, also known as an endpoint, is a collection of settings on the local computer that define the environment for PowerShell sessions ( **PSSessions** ) that connect to the computer.</span></span> <span data-ttu-id="ea654-115">所有 **pssession** 都使用会话配置。</span><span class="sxs-lookup"><span data-stu-id="ea654-115">All **PSSessions** use a session configuration.</span></span> <span data-ttu-id="ea654-116">若要指定特定的会话配置，请使用 cmdlet 的 **ConfigurationName** 参数，该参数可创建一个会话（如 `New-PSSession` cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="ea654-116">To specify a particular session configuration, use the **ConfigurationName** parameter of cmdlets that create a session, such as the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="ea654-117">session configuration file 可以轻松地定义会话配置，无需复杂的脚本或代码程序集。</span><span class="sxs-lookup"><span data-stu-id="ea654-117">A session configuration file makes it easy to define a session configuration without complex scripts or code assemblies.</span></span> <span data-ttu-id="ea654-118">该文件中的设置与可选的启动脚本和会话配置中的任何程序集一起使用。</span><span class="sxs-lookup"><span data-stu-id="ea654-118">The settings in the file are used with the optional startup script and any assemblies in the session configuration.</span></span>

<span data-ttu-id="ea654-119">有关会话配置和会话配置文件的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md) 和 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)。</span><span class="sxs-lookup"><span data-stu-id="ea654-119">For more information about session configurations and session configuration files, see [about_Session_Configurations](About/about_Session_Configurations.md) and [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="ea654-120">此 cmdlet 是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ea654-120">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="ea654-121">示例</span><span class="sxs-lookup"><span data-stu-id="ea654-121">EXAMPLES</span></span>

### <span data-ttu-id="ea654-122">示例1：创建和使用 NoLanguage 会话</span><span class="sxs-lookup"><span data-stu-id="ea654-122">Example 1: Creating and using a NoLanguage session</span></span>

<span data-ttu-id="ea654-123">此示例演示如何创建和使用无语言会话的效果。</span><span class="sxs-lookup"><span data-stu-id="ea654-123">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="ea654-124">步骤包括：</span><span class="sxs-lookup"><span data-stu-id="ea654-124">The steps include:</span></span>

1. <span data-ttu-id="ea654-125">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-125">Create a new configuration file.</span></span>
1. <span data-ttu-id="ea654-126">注册配置。</span><span class="sxs-lookup"><span data-stu-id="ea654-126">Register the configuration.</span></span>
1. <span data-ttu-id="ea654-127">创建使用该配置的新会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-127">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="ea654-128">在该新会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="ea654-128">Run commands in that new session.</span></span>

<span data-ttu-id="ea654-129">若要运行此示例中的命令，请使用 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ea654-129">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="ea654-130">运行 cmdlet 需要此选项 `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-130">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode NoLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name NoLanguage -Force
$NoLanguageSession = New-PSSession -ComputerName Srv01 -ConfigurationName NoLanguage
Invoke-Command -Session $NoLanguageSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
The syntax is not supported by this runspace. This might be because it is in no-language mode.
    + CategoryInfo          : ParserError: (if ((Get-Date) ...') {'Before'}  :String) [], ParseException
    + FullyQualifiedErrorId : ScriptsNotAllowed
    + PSComputerName        : localhost
```

<span data-ttu-id="ea654-131">在此示例中， `Invoke-Command` 失败的原因是 **LanguageMode** 设置为 **NoLanguage** 。</span><span class="sxs-lookup"><span data-stu-id="ea654-131">In this example, the `Invoke-Command` fails because the **LanguageMode** is set to **NoLanguage** .</span></span>

### <span data-ttu-id="ea654-132">示例2：创建和使用 RestrictedLanguage 会话</span><span class="sxs-lookup"><span data-stu-id="ea654-132">Example 2: Creating and using a RestrictedLanguage session</span></span>

<span data-ttu-id="ea654-133">此示例演示如何创建和使用无语言会话的效果。</span><span class="sxs-lookup"><span data-stu-id="ea654-133">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="ea654-134">步骤包括：</span><span class="sxs-lookup"><span data-stu-id="ea654-134">The steps include:</span></span>

1. <span data-ttu-id="ea654-135">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-135">Create a new configuration file.</span></span>
1. <span data-ttu-id="ea654-136">注册配置。</span><span class="sxs-lookup"><span data-stu-id="ea654-136">Register the configuration.</span></span>
1. <span data-ttu-id="ea654-137">创建使用该配置的新会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-137">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="ea654-138">在该新会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="ea654-138">Run commands in that new session.</span></span>

<span data-ttu-id="ea654-139">若要运行此示例中的命令，请使用 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ea654-139">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="ea654-140">运行 cmdlet 需要此选项 `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-140">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode RestrictedLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name RestrictedLanguage -Force
$RestrictedSession = New-PSSession -ComputerName Srv01 -ConfigurationName RestrictedLanguage
Invoke-Command -Session $RestrictedSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
Before
```

<span data-ttu-id="ea654-141">在此示例中，将 `Invoke-Command` 成功，因为 **LanguageMode** 设置为 **RestrictedLanguage** 。</span><span class="sxs-lookup"><span data-stu-id="ea654-141">In this example, the `Invoke-Command` succeeds because the **LanguageMode** is set to **RestrictedLanguage** .</span></span>

### <span data-ttu-id="ea654-142">示例3：更改会话配置文件</span><span class="sxs-lookup"><span data-stu-id="ea654-142">Example 3: Changing a Session Configuration File</span></span>

<span data-ttu-id="ea654-143">此示例演示如何更改在名为 "ITTasks" 的现有会话中使用的会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-143">This example shows how to change the session configuration file that is used in an existing session named "ITTasks".</span></span> <span data-ttu-id="ea654-144">以前，这些会话仅具有核心模块和内部 **ITTasks** 模块。</span><span class="sxs-lookup"><span data-stu-id="ea654-144">Previously, these sessions had only the core modules and an internal **ITTasks** module.</span></span> <span data-ttu-id="ea654-145">管理员想要将 **PSScheduledJob** 模块添加到使用 ITTasks 会话配置创建的会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-145">The administrator wants to add the **PSScheduledJob** module to sessions created by using the ITTasks session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

<span data-ttu-id="ea654-146">`New-PSSessionConfigurationFile`Cmdlet 来创建导入所需模块的会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-146">The `New-PSSessionConfigurationFile` cmdlet to create a session configuration file that imports the required modules.</span></span> <span data-ttu-id="ea654-147">`Set-PSSessionConfiguration`Cmdlet 用新的配置文件替换当前的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-147">The `Set-PSSessionConfiguration` cmdlet replaces the current configuration file with the new one.</span></span> <span data-ttu-id="ea654-148">这一新配置仅影响在更改后创建的新会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-148">This new configuration only affects new sessions created after the change.</span></span>
<span data-ttu-id="ea654-149">现有 "ITTasks" 会话不受影响。</span><span class="sxs-lookup"><span data-stu-id="ea654-149">Existing "ITTasks" sessions are not affected.</span></span>

### <span data-ttu-id="ea654-150">示例4：编辑会话配置文件</span><span class="sxs-lookup"><span data-stu-id="ea654-150">Example 4: Editing a Session Configuration File</span></span>

<span data-ttu-id="ea654-151">此示例显示了如何通过编辑配置文件的主动会话配置副本来更改会话配置。</span><span class="sxs-lookup"><span data-stu-id="ea654-151">This example shows how to change a session configuration by editing the active session configuration copy of the configuration file.</span></span> <span data-ttu-id="ea654-152">若要修改配置文件的会话配置副本，您必须对该文件具有完全控制访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea654-152">To modify the session configuration copy of the configuration file, you must have full control access to the file.</span></span> <span data-ttu-id="ea654-153">这可能需要更改对文件的权限。</span><span class="sxs-lookup"><span data-stu-id="ea654-153">This may require you to change the permissions on the file.</span></span>

<span data-ttu-id="ea654-154">在此方案中，我们想要 `Select-String` 通过编辑活动配置文件来添加 cmdlet 的新别名。</span><span class="sxs-lookup"><span data-stu-id="ea654-154">In this scenario, we want to add a new alias for the `Select-String` cmdlet by editing the active configuration file.</span></span>

<span data-ttu-id="ea654-155">下面的示例代码执行以下步骤来进行此更改：</span><span class="sxs-lookup"><span data-stu-id="ea654-155">The example code below performs the following steps to make this change:</span></span>

1. <span data-ttu-id="ea654-156">获取 ITConfig 会话的配置文件路径。</span><span class="sxs-lookup"><span data-stu-id="ea654-156">Get the configuration file path for the ITConfig session.</span></span>
1. <span data-ttu-id="ea654-157">用户使用 **Notepad.exe** 编辑配置文件以更改 **AliasDefinitions** 值，如下所示： `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-157">The user edits the configuration file using **Notepad.exe** to change the **AliasDefinitions** value as follows: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})`.</span></span>
1. <span data-ttu-id="ea654-158">测试更新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-158">Test the updated configuration file.</span></span>

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

<span data-ttu-id="ea654-159">结合使用 **Verbose** 参数 `Test-PSSessionConfigurationFile` 来显示检测到的任何错误。</span><span class="sxs-lookup"><span data-stu-id="ea654-159">Use the **Verbose** parameter with `Test-PSSessionConfigurationFile` to display any errors that are detected.</span></span> <span data-ttu-id="ea654-160">`$True`如果文件中未检测到任何错误，则该 cmdlet 将返回。</span><span class="sxs-lookup"><span data-stu-id="ea654-160">The cmdlet returns `$True` if no errors are detected in the file.</span></span>

### <span data-ttu-id="ea654-161">示例5：创建示例配置文件</span><span class="sxs-lookup"><span data-stu-id="ea654-161">Example 5: Create a sample configuration file</span></span>

<span data-ttu-id="ea654-162">此示例显示了一个 `New-PSSessionConfigurationFile` 使用所有 cmdlet 参数的命令。</span><span class="sxs-lookup"><span data-stu-id="ea654-162">This example shows a `New-PSSessionConfigurationFile` command that uses all the cmdlet parameters.</span></span>
<span data-ttu-id="ea654-163">包含此示例以显示每个参数对应的正确输入格式。</span><span class="sxs-lookup"><span data-stu-id="ea654-163">It is included to show the correct input format for each parameter.</span></span>

<span data-ttu-id="ea654-164">生成的 SampleFile.pssc 将显示在输出中。</span><span class="sxs-lookup"><span data-stu-id="ea654-164">The resulting SampleFile.pssc is displayed in the output.</span></span>

```powershell
$configSettings = @{
    Path = '.\SampleFile.pssc'
    SchemaVersion = '1.0.0.0'
    Author = 'User01'
    Copyright = '(c) Fabrikam Corporation. All rights reserved.'
    CompanyName = 'Fabrikam Corporation'
    Description = 'This is a sample file.'
    ExecutionPolicy = 'AllSigned'
    PowerShellVersion = '3.0'
    LanguageMode = 'FullLanguage'
    SessionType = 'Default'
    EnvironmentVariables = @{TESTSHARE='\\Test2\Test'}
    ModulesToImport = @{ModuleName='PSScheduledJob'; ModuleVersion='1.0.0.0'; GUID='50cdb55f-5ab7-489f-9e94-4ec21ff51e59'},'PSDiagnostics'
    AssembliesToLoad = 'System.Web.Services','FSharp.Compiler.CodeDom.dll'
    TypesToProcess = 'Types1.ps1xml','Types2.ps1xml'
    FormatsToProcess = 'CustomFormats.ps1xml'
    ScriptsToProcess = 'Get-Inputs.ps1'
    AliasDefinitions = @{Name='hlp';Value='Get-Help';Description='Gets help.';Options='AllScope'},
        @{Name='Update';Value='Update-Help';Description='Updates help';Options='ReadOnly'}
    FunctionDefinitions = @{Name='Get-Function';ScriptBlock={Get-Command -CommandType Function};Options='ReadOnly'}
    VariableDefinitions = @{Name='WarningPreference';Value='SilentlyContinue'}
    VisibleAliases = 'c*','g*','i*','s*'
    VisibleCmdlets = 'Get*'
    VisibleFunctions = 'Get*'
    VisibleProviders = 'FileSystem','Function','Variable'
    RunAsVirtualAccount = $true
    RunAsVirtualAccountGroups = 'Backup Operators'
}
New-PSSessionConfigurationFile @configSettings
Get-Content SampleFile.pssc
```

```Output
@{

# Version number of the schema used for this document
SchemaVersion = '1.0.0.0'

# ID used to uniquely identify this document
GUID = '1caeff7f-27ca-4360-97cf-37846f594235'

# Author of this document
Author = 'User01'

# Description of the functionality provided by these settings
Description = 'This is a sample file.'

# Company associated with this document
CompanyName = 'Fabrikam Corporation'

# Copyright statement for this document
Copyright = '(c) Fabrikam Corporation. All rights reserved.'

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'Default'

# Directory to place session transcripts for this session configuration
# TranscriptDirectory = 'C:\Transcripts\'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
RunAsVirtualAccountGroups = 'Backup Operators'

# Scripts to run when applied to a session
ScriptsToProcess = 'Get-Inputs.ps1'

# User roles (security groups), and the role capabilities that should be applied to them when applied to a session
# RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\SqlManaged' = @{ RoleCapabilityFiles = 'C:\RoleCapability\SqlManaged.psrc' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }

# Language mode to apply when applied to a session. Can be 'NoLanguage' (recommended), 'RestrictedLanguage', 'ConstrainedLanguage', or 'FullLanguage'
LanguageMode = 'FullLanguage'

# Execution policy to apply when applied to a session
ExecutionPolicy = 'AllSigned'

# Version of the PowerShell engine to use when applied to a session
PowerShellVersion = '3.0'

# Modules to import when applied to a session
ModulesToImport = @{
    'GUID' = '50cdb55f-5ab7-489f-9e94-4ec21ff51e59'
    'ModuleName' = 'PSScheduledJob'
    'ModuleVersion' = '1.0.0.0' }, 'PSDiagnostics'

# Aliases to make visible when applied to a session
VisibleAliases = 'c*', 'g*', 'i*', 's*'

# Cmdlets to make visible when applied to a session
VisibleCmdlets = 'Get*'

# Functions to make visible when applied to a session
VisibleFunctions = 'Get*'

# Providers to make visible when applied to a session
VisibleProviders = 'FileSystem', 'Function', 'Variable'

# Aliases to be defined when applied to a session
AliasDefinitions = @{
    'Description' = 'Gets help.'
    'Name' = 'hlp'
    'Options' = 'AllScope'
    'Value' = 'Get-Help' }, @{
    'Description' = 'Updates help'
    'Name' = 'Update'
    'Options' = 'ReadOnly'
    'Value' = 'Update-Help' }

# Functions to define when applied to a session
FunctionDefinitions = @{
    'Name' = 'Get-Function'
    'Options' = 'ReadOnly'
    'ScriptBlock' = {Get-Command -CommandType Function} }

# Variables to define when applied to a session
VariableDefinitions = @{
    'Name' = 'WarningPreference'
    'Value' = 'SilentlyContinue' }

# Environment variables to define when applied to a session
EnvironmentVariables = @{
    'TESTSHARE' = '\\Test2\Test' }

# Type files (.ps1xml) to load when applied to a session
TypesToProcess = 'Types1.ps1xml', 'Types2.ps1xml'

# Format files (.ps1xml) to load when applied to a session
FormatsToProcess = 'CustomFormats.ps1xml'

# Assemblies to load when applied to a session
AssembliesToLoad = 'System.Web.Services', 'FSharp.Compiler.CodeDom.dll'

}
```

## <span data-ttu-id="ea654-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ea654-165">PARAMETERS</span></span>

### <span data-ttu-id="ea654-166">-AliasDefinitions</span><span class="sxs-lookup"><span data-stu-id="ea654-166">-AliasDefinitions</span></span>

<span data-ttu-id="ea654-167">将指定的别名添加到使用该会话配置的会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-167">Adds the specified aliases to sessions that use the session configuration.</span></span> <span data-ttu-id="ea654-168">输入一个包含以下键的哈希表：</span><span class="sxs-lookup"><span data-stu-id="ea654-168">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="ea654-169">名称-别名的名称。</span><span class="sxs-lookup"><span data-stu-id="ea654-169">Name - Name of the alias.</span></span> <span data-ttu-id="ea654-170">此键是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea654-170">This key is required.</span></span>
- <span data-ttu-id="ea654-171">Value-别名表示的命令。</span><span class="sxs-lookup"><span data-stu-id="ea654-171">Value - The command that the alias represents.</span></span> <span data-ttu-id="ea654-172">此键是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea654-172">This key is required.</span></span>
- <span data-ttu-id="ea654-173">说明-描述别名的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="ea654-173">Description - A text string that describes the alias.</span></span> <span data-ttu-id="ea654-174">此键是可选的。</span><span class="sxs-lookup"><span data-stu-id="ea654-174">This key is optional.</span></span>
- <span data-ttu-id="ea654-175">选项-别名选项。</span><span class="sxs-lookup"><span data-stu-id="ea654-175">Options - Alias options.</span></span> <span data-ttu-id="ea654-176">此键是可选的。</span><span class="sxs-lookup"><span data-stu-id="ea654-176">This key is optional.</span></span> <span data-ttu-id="ea654-177">默认值为 " **无** "。</span><span class="sxs-lookup"><span data-stu-id="ea654-177">The default value is **None** .</span></span> <span data-ttu-id="ea654-178">此参数的可接受值为： None、ReadOnly、常量、Private 或 AllScope。</span><span class="sxs-lookup"><span data-stu-id="ea654-178">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="ea654-179">例如：`@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span><span class="sxs-lookup"><span data-stu-id="ea654-179">For example: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-180">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="ea654-180">-AssembliesToLoad</span></span>

<span data-ttu-id="ea654-181">指定要加载到使用该会话配置的会话中的程序集。</span><span class="sxs-lookup"><span data-stu-id="ea654-181">Specifies the assemblies to load into the sessions that use the session configuration.</span></span>

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

### <span data-ttu-id="ea654-182">-作者</span><span class="sxs-lookup"><span data-stu-id="ea654-182">-Author</span></span>

<span data-ttu-id="ea654-183">指定会话配置或配置文件的作者。</span><span class="sxs-lookup"><span data-stu-id="ea654-183">Specifies the author of the session configuration or the configuration file.</span></span> <span data-ttu-id="ea654-184">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="ea654-184">The default is the current user.</span></span> <span data-ttu-id="ea654-185">此参数的值在会话配置文件中可见，但是它不是会话配置对象的属性。</span><span class="sxs-lookup"><span data-stu-id="ea654-185">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="ea654-186">-公司名称</span><span class="sxs-lookup"><span data-stu-id="ea654-186">-CompanyName</span></span>

<span data-ttu-id="ea654-187">指定创建了会话配置或配置文件的公司。</span><span class="sxs-lookup"><span data-stu-id="ea654-187">Specifies the company that created the session configuration or the configuration file.</span></span> <span data-ttu-id="ea654-188">默认值是“未知”  。</span><span class="sxs-lookup"><span data-stu-id="ea654-188">The default value is **Unknown** .</span></span> <span data-ttu-id="ea654-189">此参数的值在会话配置文件中可见，但是它不是会话配置对象的属性。</span><span class="sxs-lookup"><span data-stu-id="ea654-189">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Unknown
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-190">-版权所有</span><span class="sxs-lookup"><span data-stu-id="ea654-190">-Copyright</span></span>

<span data-ttu-id="ea654-191">指定会话配置文件的版权。</span><span class="sxs-lookup"><span data-stu-id="ea654-191">Specifies a copyright the session configuration file.</span></span> <span data-ttu-id="ea654-192">此参数的值在会话配置文件中可见，但是它不是会话配置对象的属性。</span><span class="sxs-lookup"><span data-stu-id="ea654-192">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

<span data-ttu-id="ea654-193">如果省略此参数，则 `New-PSSessionConfigurationFile` 使用 **Author** 参数的值生成版权声明。</span><span class="sxs-lookup"><span data-stu-id="ea654-193">If you omit this parameter, `New-PSSessionConfigurationFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="ea654-194">-Description</span><span class="sxs-lookup"><span data-stu-id="ea654-194">-Description</span></span>

<span data-ttu-id="ea654-195">指定会话配置或会话配置文件的描述。</span><span class="sxs-lookup"><span data-stu-id="ea654-195">Specifies a description of the session configuration or the session configuration file.</span></span> <span data-ttu-id="ea654-196">此参数的值在会话配置文件中可见，但是它不是会话配置对象的属性。</span><span class="sxs-lookup"><span data-stu-id="ea654-196">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

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

### <span data-ttu-id="ea654-197">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="ea654-197">-EnvironmentVariables</span></span>

<span data-ttu-id="ea654-198">将环境变量添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-198">Adds environment variables to the session.</span></span> <span data-ttu-id="ea654-199">输入一个哈希表，其中的键是环境变量名称，而值是环境变量值。</span><span class="sxs-lookup"><span data-stu-id="ea654-199">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="ea654-200">例如：`EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span><span class="sxs-lookup"><span data-stu-id="ea654-200">For example: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-201">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ea654-201">-ExecutionPolicy</span></span>

<span data-ttu-id="ea654-202">指定使用该会话配置的会话的执行策略。</span><span class="sxs-lookup"><span data-stu-id="ea654-202">Specifies the execution policy of sessions that use the session configuration.</span></span> <span data-ttu-id="ea654-203">如果省略此参数，则会 **限制** 会话配置文件中 **set-executionpolicy** 键的值。</span><span class="sxs-lookup"><span data-stu-id="ea654-203">If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted** .</span></span> <span data-ttu-id="ea654-204">有关 PowerShell 中的执行策略的信息，请参阅 [about_Execution_Policies](about/about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ea654-204">For information about execution policies in PowerShell, see [about_Execution_Policies](about/about_Execution_Policies.md).</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Unrestricted, RemoteSigned, AllSigned, Restricted, Default, Bypass, Undefined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-205">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="ea654-205">-FormatsToProcess</span></span>

<span data-ttu-id="ea654-206">指定在使用该会话配置的会话中运行的格式设置文件 (.ps1xml)。</span><span class="sxs-lookup"><span data-stu-id="ea654-206">Specifies the formatting files (.ps1xml) that run in sessions that use the session configuration.</span></span>
<span data-ttu-id="ea654-207">此参数的值必须是格式设置文件的完整或绝对路径。</span><span class="sxs-lookup"><span data-stu-id="ea654-207">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

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

### <span data-ttu-id="ea654-208">-Full</span><span class="sxs-lookup"><span data-stu-id="ea654-208">-Full</span></span>

<span data-ttu-id="ea654-209">指示此操作包括会话配置文件中所有可能的配置属性。</span><span class="sxs-lookup"><span data-stu-id="ea654-209">Indicates that this operation includes all possible configuration properties in the session configuration file.</span></span>

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

### <span data-ttu-id="ea654-210">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="ea654-210">-FunctionDefinitions</span></span>

<span data-ttu-id="ea654-211">将指定函数添加到使用该会话配置的会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-211">Adds the specified functions to sessions that use the session configuration.</span></span> <span data-ttu-id="ea654-212">输入一个包含以下键的哈希表：</span><span class="sxs-lookup"><span data-stu-id="ea654-212">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="ea654-213">名称-函数的名称。</span><span class="sxs-lookup"><span data-stu-id="ea654-213">Name - Name of the function.</span></span> <span data-ttu-id="ea654-214">此键是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea654-214">This key is required.</span></span>
- <span data-ttu-id="ea654-215">ScriptBlock 函数体。</span><span class="sxs-lookup"><span data-stu-id="ea654-215">ScriptBlock - Function body.</span></span> <span data-ttu-id="ea654-216">输入一个脚本块。</span><span class="sxs-lookup"><span data-stu-id="ea654-216">Enter a script block.</span></span> <span data-ttu-id="ea654-217">此键是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea654-217">This key is required.</span></span>
- <span data-ttu-id="ea654-218">Options-函数选项。</span><span class="sxs-lookup"><span data-stu-id="ea654-218">Options - Function options.</span></span> <span data-ttu-id="ea654-219">此键是可选的。</span><span class="sxs-lookup"><span data-stu-id="ea654-219">This key is optional.</span></span> <span data-ttu-id="ea654-220">默认值为 " **无** "。</span><span class="sxs-lookup"><span data-stu-id="ea654-220">The default value is **None** .</span></span> <span data-ttu-id="ea654-221">此参数的可接受值为： None、ReadOnly、常量、Private 或 AllScope。</span><span class="sxs-lookup"><span data-stu-id="ea654-221">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="ea654-222">例如：`@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="ea654-222">For example: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-223">-Msds-groupmanagedserviceaccount</span><span class="sxs-lookup"><span data-stu-id="ea654-223">-GroupManagedServiceAccount</span></span>

<span data-ttu-id="ea654-224">将使用此会话配置的会话配置为在指定的组托管服务帐户的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="ea654-224">Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account.</span></span> <span data-ttu-id="ea654-225">注册此会话配置的计算机必须有权请求 gMSA 密码才能成功创建会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-225">The machine where this session configuration is registered must have permission to request the gMSA password in order for sessions to be created successfully.</span></span> <span data-ttu-id="ea654-226">此字段不能与 **将 runasvirtualaccount 设置** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="ea654-226">This field cannot be used with the **RunAsVirtualAccount** parameter.</span></span>

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

### <span data-ttu-id="ea654-227">-Guid</span><span class="sxs-lookup"><span data-stu-id="ea654-227">-Guid</span></span>

<span data-ttu-id="ea654-228">为会话配置文件指定唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ea654-228">Specifies a unique identifier for the session configuration file.</span></span> <span data-ttu-id="ea654-229">如果省略此参数，则 `New-PSSessionConfigurationFile` 将为文件生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="ea654-229">If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file.</span></span> <span data-ttu-id="ea654-230">若要在 PowerShell 中创建新的 GUID，请键入 `New-Guid` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-230">To create a new GUID in PowerShell, type `New-Guid`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-231">-LanguageMode</span><span class="sxs-lookup"><span data-stu-id="ea654-231">-LanguageMode</span></span>

<span data-ttu-id="ea654-232">确定在使用此会话配置的会话中允许使用 PowerShell 语言的哪些元素。</span><span class="sxs-lookup"><span data-stu-id="ea654-232">Determines which elements of the PowerShell language are permitted in sessions that use this session configuration.</span></span> <span data-ttu-id="ea654-233">可以使用此参数来限制特定用户可以在计算机上运行的命令。</span><span class="sxs-lookup"><span data-stu-id="ea654-233">You can use this parameter to restrict the commands that particular users can run on the computer.</span></span>

<span data-ttu-id="ea654-234">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ea654-234">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ea654-235">FullLanguage-允许所有语言元素。</span><span class="sxs-lookup"><span data-stu-id="ea654-235">FullLanguage - All language elements are permitted.</span></span>
- <span data-ttu-id="ea654-236">ConstrainedLanguage-不允许包含要计算的脚本的命令。</span><span class="sxs-lookup"><span data-stu-id="ea654-236">ConstrainedLanguage - Commands that contain scripts to be evaluated are not allowed.</span></span> <span data-ttu-id="ea654-237">ConstrainedLanguage 模式限制用户对 Microsoft .NET Framework 类型、对象或方法的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea654-237">The ConstrainedLanguage mode restricts user access to Microsoft .NET Framework types, objects, or methods.</span></span>
- <span data-ttu-id="ea654-238">NoLanguage-用户可以运行 cmdlet 和函数，但是不允许使用任何语言元素，如脚本块、变量或运算符。</span><span class="sxs-lookup"><span data-stu-id="ea654-238">NoLanguage - Users may run cmdlets and functions, but are not permitted to use any language elements, such as script blocks, variables, or operators.</span></span>
- <span data-ttu-id="ea654-239">RestrictedLanguage-用户可以运行 cmdlet 和函数，但不允许使用除以下允许变量以外的脚本块或变量： `$PSCulture` 、、、 `$PSUICulture` `$True` `$False` 和 `$Null` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-239">RestrictedLanguage - Users may run cmdlets and functions, but are not permitted to use script blocks or variables except for the following permitted variables: `$PSCulture`, `$PSUICulture`, `$True`, `$False`, and `$Null`.</span></span> <span data-ttu-id="ea654-240">用户可以只使用基本比较运算符， (`-eq` ， `-gt` `-lt`) 。</span><span class="sxs-lookup"><span data-stu-id="ea654-240">Users may use only the basic comparison operators (`-eq`, `-gt`, `-lt`).</span></span> <span data-ttu-id="ea654-241">不允许使用赋值语句、属性引用和方法调用。</span><span class="sxs-lookup"><span data-stu-id="ea654-241">Assignment statements, property references, and method calls are not permitted.</span></span>

<span data-ttu-id="ea654-242">**LanguageMode** 参数的默认值取决于 **SessionType** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="ea654-242">The default value of the **LanguageMode** parameter depends on the value of the **SessionType** parameter.</span></span>

- <span data-ttu-id="ea654-243">空-NoLanguage</span><span class="sxs-lookup"><span data-stu-id="ea654-243">Empty - NoLanguage</span></span>
- <span data-ttu-id="ea654-244">RestrictedRemoteServer-NoLanguage</span><span class="sxs-lookup"><span data-stu-id="ea654-244">RestrictedRemoteServer - NoLanguage</span></span>
- <span data-ttu-id="ea654-245">默认值-FullLanguage</span><span class="sxs-lookup"><span data-stu-id="ea654-245">Default - FullLanguage</span></span>

```yaml
Type: System.Management.Automation.PSLanguageMode
Parameter Sets: (All)
Aliases:
Accepted values: FullLanguage, RestrictedLanguage, NoLanguage, ConstrainedLanguage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-246">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="ea654-246">-ModulesToImport</span></span>

<span data-ttu-id="ea654-247">指定自动导入使用该会话配置的会话的模块和管理单元。</span><span class="sxs-lookup"><span data-stu-id="ea654-247">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="ea654-248">默认情况下，只会将 **Microsoft. Core** 管理单元导入远程会话，但除非排除 cmdlet，否则用户可以使用 `Import-Module` 和 `Add-PSSnapin` cmdlet 将模块和管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-248">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into remote sessions, but unless the cmdlets are excluded, users can use the `Import-Module` and `Add-PSSnapin` cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="ea654-249">此参数的值中的每个模块或管理单元都可以由字符串表示或以哈希表的形式表示。</span><span class="sxs-lookup"><span data-stu-id="ea654-249">Each module or snap-in in the value of this parameter can be represented by a string or as a hash table.</span></span> <span data-ttu-id="ea654-250">模块字符串只包含模块或管理单元的名称。</span><span class="sxs-lookup"><span data-stu-id="ea654-250">A module string consists only of the name of the module or snap-in.</span></span> <span data-ttu-id="ea654-251">模块哈希表可以包含 **ModuleName** 、 **ModuleVersion** 和 **GUID** 键。</span><span class="sxs-lookup"><span data-stu-id="ea654-251">A module hash table can include **ModuleName** , **ModuleVersion** , and **GUID** keys.</span></span> <span data-ttu-id="ea654-252">仅 **ModuleName** 键是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea654-252">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="ea654-253">例如，下面的值由字符串和哈希表组成。</span><span class="sxs-lookup"><span data-stu-id="ea654-253">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="ea654-254">字符串和哈希表的任何组合（采用任何顺序）都是有效的。</span><span class="sxs-lookup"><span data-stu-id="ea654-254">Any combination of strings and hash tables, in any order, is valid.</span></span>

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

<span data-ttu-id="ea654-255">Cmdlet 的 **ModulesToImport** 参数的值 `Register-PSSessionConfiguration` 优先于会话配置文件中的 **ModulesToImport** 键的值。</span><span class="sxs-lookup"><span data-stu-id="ea654-255">The value of the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **ModulesToImport** key in the session configuration file.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-256">-MountUserDrive</span><span class="sxs-lookup"><span data-stu-id="ea654-256">-MountUserDrive</span></span>

<span data-ttu-id="ea654-257">配置使用此会话配置公开 New-psdrive 的会话 `User:` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-257">Configures sessions that use this session configuration to expose the `User:` PSDrive.</span></span> <span data-ttu-id="ea654-258">用户驱动器对于每个连接用户都是唯一的，并允许用户在不公开文件系统提供程序的情况上向/从 PowerShell 终结点复制数据。</span><span class="sxs-lookup"><span data-stu-id="ea654-258">User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints even if the File System provider is not exposed.</span></span> <span data-ttu-id="ea654-259">用户驱动器根在下创建 `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-259">User drive roots are created under `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="ea654-260">对于连接到终结点的每位用户，将创建一个具有 `$env:USERDOMAIN_$env:USERNAME` 名称的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea654-260">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="ea654-261">用户驱动器中的内容跨用户会话保持不变，不会自动删除。</span><span class="sxs-lookup"><span data-stu-id="ea654-261">Contents in the user drive persist across user sessions and are not automatically removed.</span></span> <span data-ttu-id="ea654-262">默认情况下，用户只能在用户驱动器中存储最多50MB 数据。</span><span class="sxs-lookup"><span data-stu-id="ea654-262">By default, users can only store up to 50MB of data in the user drive.</span></span> <span data-ttu-id="ea654-263">可以通过 **UserDriveMaximumSize** 参数自定义此参数。</span><span class="sxs-lookup"><span data-stu-id="ea654-263">This can be customized with the **UserDriveMaximumSize** parameter.</span></span>

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

### <span data-ttu-id="ea654-264">-Path</span><span class="sxs-lookup"><span data-stu-id="ea654-264">-Path</span></span>

<span data-ttu-id="ea654-265">指定会话配置文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="ea654-265">Specifies the path and filename of the session configuration file.</span></span> <span data-ttu-id="ea654-266">文件必须具有 `.pssc` 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="ea654-266">The file must have a `.pssc` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-267">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="ea654-267">-PowerShellVersion</span></span>

<span data-ttu-id="ea654-268">指定使用会话配置的会话中的 PowerShell 引擎版本。</span><span class="sxs-lookup"><span data-stu-id="ea654-268">Specifies the version of the PowerShell engine in sessions that use the session configuration.</span></span> <span data-ttu-id="ea654-269">此参数可接受的值为：2.0 和3.0。</span><span class="sxs-lookup"><span data-stu-id="ea654-269">The acceptable values for this parameter are: 2.0 and 3.0.</span></span> <span data-ttu-id="ea654-270">如果省略此参数，则会在会话中注释掉 **PowerShellVersion** 键，并在会话中运行最新版本的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ea654-270">If you omit this parameter, the **PowerShellVersion** key is commented-out and newest version of PowerShell runs in the session.</span></span>

<span data-ttu-id="ea654-271">Cmdlet 的 **PSVersion** 参数的值 `Register-PSSessionConfiguration` 优先于会话配置文件中的 **PowerShellVersion** 键的值。</span><span class="sxs-lookup"><span data-stu-id="ea654-271">The value of the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-272">-RequiredGroups</span><span class="sxs-lookup"><span data-stu-id="ea654-272">-RequiredGroups</span></span>

<span data-ttu-id="ea654-273">指定连接到使用此会话配置的会话的用户的条件性访问规则。</span><span class="sxs-lookup"><span data-stu-id="ea654-273">Specifies conditional access rules for users connecting to sessions that use this session configuration.</span></span>

<span data-ttu-id="ea654-274">输入一个哈希表以使用每个哈希表、' 和 ' 或 ' 或 ' 仅使用1个密钥来编写规则列表，并将值设置为安全组名称或附加哈希表的数组。</span><span class="sxs-lookup"><span data-stu-id="ea654-274">Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or 'Or', and set the value to an array of security group names or additional hashtables.</span></span>

<span data-ttu-id="ea654-275">要求将用户连接到单个组成员的示例： `@{ And = 'MyRequiredGroup' }`</span><span class="sxs-lookup"><span data-stu-id="ea654-275">Example requiring connecting users to be members of a single group: `@{ And = 'MyRequiredGroup' }`</span></span>

<span data-ttu-id="ea654-276">要求用户属于组 A 或同时属于组 B 和 C 的示例，用于访问终结点： `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span><span class="sxs-lookup"><span data-stu-id="ea654-276">Example requiring users to belong to group A, or both groups B and C, to access the endpoint: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-277">-RoleDefinitions</span><span class="sxs-lookup"><span data-stu-id="ea654-277">-RoleDefinitions</span></span>

<span data-ttu-id="ea654-278">指定安全组之间的映射 (或用户) 和角色功能。</span><span class="sxs-lookup"><span data-stu-id="ea654-278">Specifies the mapping between security groups (or users) and role capabilities.</span></span> <span data-ttu-id="ea654-279">在创建会话时，将向用户授予对其组成员资格适用的所有角色功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ea654-279">Users will be granted access to all role capabilities which apply to their group membership at the time the session is created.</span></span>

<span data-ttu-id="ea654-280">输入一个哈希表，其中的键是安全组的名称，值是包含应对安全组可用的角色功能列表的哈希表。</span><span class="sxs-lookup"><span data-stu-id="ea654-280">Enter a hash table in which the keys are the name of the security group and the values are hash tables that contain a list of role capabilities that should be made available to the security group.</span></span>

<span data-ttu-id="ea654-281">例如：`@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span><span class="sxs-lookup"><span data-stu-id="ea654-281">For example: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-282">-将 runasvirtualaccount 设置</span><span class="sxs-lookup"><span data-stu-id="ea654-282">-RunAsVirtualAccount</span></span>

<span data-ttu-id="ea654-283">使用此会话配置配置要作为计算机 (虚拟) 管理员帐户运行的会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-283">Configures sessions using this session configuration to be run as the computer's (virtual) administrator account.</span></span> <span data-ttu-id="ea654-284">此字段不能与 **msds-groupmanagedserviceaccount** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="ea654-284">This field cannot be used with the **GroupManagedServiceAccount** parameter.</span></span>

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

### <span data-ttu-id="ea654-285">-RunAsVirtualAccountGroups</span><span class="sxs-lookup"><span data-stu-id="ea654-285">-RunAsVirtualAccountGroups</span></span>

<span data-ttu-id="ea654-286">指定在使用会话配置的会话作为虚拟帐户运行时要与虚拟帐户关联的安全组。</span><span class="sxs-lookup"><span data-stu-id="ea654-286">Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account.</span></span> <span data-ttu-id="ea654-287">如果省略，则虚拟帐户属于域控制器上的域管理员和所有其他计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="ea654-287">If omitted, the virtual account belongs to Domain Admins on domain controllers and Administrators on all other computers.</span></span>

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

### <span data-ttu-id="ea654-288">-SchemaVersion</span><span class="sxs-lookup"><span data-stu-id="ea654-288">-SchemaVersion</span></span>

<span data-ttu-id="ea654-289">指定会话配置文件架构的版本。</span><span class="sxs-lookup"><span data-stu-id="ea654-289">Specifies the version of the session configuration file schema.</span></span> <span data-ttu-id="ea654-290">默认值为“1.0.0.0”。</span><span class="sxs-lookup"><span data-stu-id="ea654-290">The default value is "1.0.0.0".</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-291">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="ea654-291">-ScriptsToProcess</span></span>

<span data-ttu-id="ea654-292">将指定脚本添加到使用该会话配置的会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-292">Adds the specified scripts to sessions that use the session configuration.</span></span> <span data-ttu-id="ea654-293">请输入脚本的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="ea654-293">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="ea654-294">此参数的值必须为脚本文件名的完整或绝对路径。</span><span class="sxs-lookup"><span data-stu-id="ea654-294">The value of this parameter must be a full or absolute path of script file names.</span></span>

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

### <span data-ttu-id="ea654-295">-SessionType</span><span class="sxs-lookup"><span data-stu-id="ea654-295">-SessionType</span></span>

<span data-ttu-id="ea654-296">指定通过使用该会话配置创建的会话的类型。</span><span class="sxs-lookup"><span data-stu-id="ea654-296">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="ea654-297">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="ea654-297">The default value is Default.</span></span> <span data-ttu-id="ea654-298">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="ea654-298">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="ea654-299">空-默认情况下，不向会话添加任何模块。</span><span class="sxs-lookup"><span data-stu-id="ea654-299">Empty - No modules are added to session by default.</span></span> <span data-ttu-id="ea654-300">使用此 cmdlet 的参数将模块、函数、脚本和其他功能添加到会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-300">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span> <span data-ttu-id="ea654-301">此选项可用于通过添加所选命令创建自定义会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-301">This option is designed for you to create custom sessions by adding selected commands.</span></span> <span data-ttu-id="ea654-302">如果没有将命令添加到空会话中，则该会话将限于表达式，并且可能不可用。</span><span class="sxs-lookup"><span data-stu-id="ea654-302">If you do not add commands to an empty session, the session is limited to expressions and might not be usable.</span></span>
- <span data-ttu-id="ea654-303">默认-将 Microsoft. Core 模块添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-303">Default - Adds the Microsoft.PowerShell.Core module to the session.</span></span> <span data-ttu-id="ea654-304">此模块包括 `Import-Module` cmdlet，用户可以使用该 cmdlet 导入其他模块，除非显式禁止此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea654-304">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit this cmdlet.</span></span>
- <span data-ttu-id="ea654-305">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="ea654-305">RestrictedRemoteServer.</span></span> <span data-ttu-id="ea654-306">仅包括以下代理函数： `Exit-PSSession` 、 `Get-Command` 、 `Get-FormatData` 、、、 `Get-Help` `Measure-Object` `Out-Default` 和 `Select-Object` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-306">Includes only the following proxy functions: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span>
  <span data-ttu-id="ea654-307">使用此 cmdlet 的参数将模块、函数、脚本和其他功能添加到会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-307">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>

```yaml
Type: System.Management.Automation.Remoting.SessionType
Parameter Sets: (All)
Aliases:
Accepted values: Empty, RestrictedRemoteServer, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-308">-TranscriptDirectory</span><span class="sxs-lookup"><span data-stu-id="ea654-308">-TranscriptDirectory</span></span>

<span data-ttu-id="ea654-309">指定要为使用此会话配置的会话放置会话脚本的目录。</span><span class="sxs-lookup"><span data-stu-id="ea654-309">Specifies the directory to place session transcripts for sessions using this session configuration.</span></span>

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

### <span data-ttu-id="ea654-310">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="ea654-310">-TypesToProcess</span></span>

<span data-ttu-id="ea654-311">将指定的 `.ps1xml` 类型文件添加到使用会话配置的会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-311">Adds the specified `.ps1xml` type files to sessions that use the session configuration.</span></span> <span data-ttu-id="ea654-312">输入类型文件名。</span><span class="sxs-lookup"><span data-stu-id="ea654-312">Enter the type filenames.</span></span> <span data-ttu-id="ea654-313">此参数的值必须为类型文件名的完整或绝对路径。</span><span class="sxs-lookup"><span data-stu-id="ea654-313">The value of this parameter must be a full or absolute path to type filenames.</span></span>

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

### <span data-ttu-id="ea654-314">-UserDriveMaximumSize</span><span class="sxs-lookup"><span data-stu-id="ea654-314">-UserDriveMaximumSize</span></span>

<span data-ttu-id="ea654-315">指定在使用此会话配置的会话中公开的用户驱动器的最大大小。</span><span class="sxs-lookup"><span data-stu-id="ea654-315">Specifies the maximum size for user drives exposed in sessions that use this session configuration.</span></span>
<span data-ttu-id="ea654-316">如果省略，则每个驱动器根的默认大小 `User:` 为50MB。</span><span class="sxs-lookup"><span data-stu-id="ea654-316">When omitted, the default size of each `User:` drive root is 50MB.</span></span>

<span data-ttu-id="ea654-317">应将此参数与 **MountUserDrive** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ea654-317">This parameter should be used with **MountUserDrive** .</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-318">-VariableDefinitions</span><span class="sxs-lookup"><span data-stu-id="ea654-318">-VariableDefinitions</span></span>

<span data-ttu-id="ea654-319">将指定变量添加到使用该会话配置的会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-319">Adds the specified variables to sessions that use the session configuration.</span></span> <span data-ttu-id="ea654-320">输入一个包含以下键的哈希表：</span><span class="sxs-lookup"><span data-stu-id="ea654-320">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="ea654-321">名称-变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ea654-321">Name - Name of the variable.</span></span> <span data-ttu-id="ea654-322">此键是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea654-322">This key is required.</span></span>
- <span data-ttu-id="ea654-323">值-变量值。</span><span class="sxs-lookup"><span data-stu-id="ea654-323">Value - Variable value.</span></span> <span data-ttu-id="ea654-324">此键是必需的。</span><span class="sxs-lookup"><span data-stu-id="ea654-324">This key is required.</span></span>
- <span data-ttu-id="ea654-325">选项-变量选项。</span><span class="sxs-lookup"><span data-stu-id="ea654-325">Options - Variable options.</span></span> <span data-ttu-id="ea654-326">此键是可选的。</span><span class="sxs-lookup"><span data-stu-id="ea654-326">This key is optional.</span></span> <span data-ttu-id="ea654-327">默认值为 " **无** "。</span><span class="sxs-lookup"><span data-stu-id="ea654-327">The default value is **None** .</span></span> <span data-ttu-id="ea654-328">此参数的可接受值为： None、ReadOnly、常量、Private 或 AllScope。</span><span class="sxs-lookup"><span data-stu-id="ea654-328">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="ea654-329">例如：`@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="ea654-329">For example: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-330">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="ea654-330">-VisibleAliases</span></span>

<span data-ttu-id="ea654-331">将会话中的别名限制为在此参数的值中指定的别名以及在 **AliasDefinition** 参数中定义的任何别名。</span><span class="sxs-lookup"><span data-stu-id="ea654-331">Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="ea654-332">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ea654-332">Wildcard characters are supported.</span></span> <span data-ttu-id="ea654-333">默认情况下，PowerShell 引擎定义的所有别名和模块导出的所有别名都在会话中可见。</span><span class="sxs-lookup"><span data-stu-id="ea654-333">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="ea654-334">例如：`VisibleAliases='gcm', 'gp'`</span><span class="sxs-lookup"><span data-stu-id="ea654-334">For example: `VisibleAliases='gcm', 'gp'`</span></span>

<span data-ttu-id="ea654-335">当会话配置文件中包含任何 **可见** 参数时，PowerShell 会从会话中删除该 `Import-Module` cmdlet 及其 ipmo 别名。</span><span class="sxs-lookup"><span data-stu-id="ea654-335">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="ea654-336">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="ea654-336">-VisibleCmdlets</span></span>

<span data-ttu-id="ea654-337">将会话中的 cmdlet 限制为在此参数的值中指定的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea654-337">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="ea654-338">支持通配符和模块限定名称。</span><span class="sxs-lookup"><span data-stu-id="ea654-338">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="ea654-339">默认情况下，会话中的模块导出的所有 cmdlet 都在该会话中可见。</span><span class="sxs-lookup"><span data-stu-id="ea654-339">By default, all cmdlets that modules in the session export are visible in the session.</span></span> <span data-ttu-id="ea654-340">使用 **SessionType** 和 **ModulesToImport** 参数来确定哪些模块和管理单元已导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-340">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="ea654-341">如果 **ModulesToImport** 中没有任何模块公开 cmdlet，则相应的模块将尝试加载。</span><span class="sxs-lookup"><span data-stu-id="ea654-341">If no modules in **ModulesToImport** expose the cmdlet, the appropriate module will attempt to be autoloaded.</span></span>

<span data-ttu-id="ea654-342">当会话配置文件中包含任何 **可见** 参数时，PowerShell 会从会话中删除该 `Import-Module` cmdlet 及其 ipmo 别名。</span><span class="sxs-lookup"><span data-stu-id="ea654-342">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ea654-343">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="ea654-343">-VisibleExternalCommands</span></span>

<span data-ttu-id="ea654-344">将可以在会话中执行的外部二进制文件、脚本和命令限制为在此参数的值中指定的文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-344">Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="ea654-345">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ea654-345">Wildcard characters are supported.</span></span>

<span data-ttu-id="ea654-346">默认情况下，会话中不显示任何外部命令。</span><span class="sxs-lookup"><span data-stu-id="ea654-346">By default, no external commands are visible in the session.</span></span>

<span data-ttu-id="ea654-347">如果会话配置文件中包含任何 **可见** 参数，则 PowerShell 会 `Import-Module` 从会话中删除该 cmdlet 及其 ipmo 别名。</span><span class="sxs-lookup"><span data-stu-id="ea654-347">When any **Visible** parameter is included in the session configuration file, PowerShell, removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

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

### <span data-ttu-id="ea654-348">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="ea654-348">-VisibleFunctions</span></span>

<span data-ttu-id="ea654-349">将会话中的函数限制为在此参数的值中指定的函数以及在 **FunctionDefinition** 参数中定义的任何函数。</span><span class="sxs-lookup"><span data-stu-id="ea654-349">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter.</span></span> <span data-ttu-id="ea654-350">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ea654-350">Wildcard characters are supported.</span></span>

<span data-ttu-id="ea654-351">默认情况下，会话中的模块导出的所有函数都在该会话中可见。</span><span class="sxs-lookup"><span data-stu-id="ea654-351">By default, all functions that modules in the session export are visible in the session.</span></span> <span data-ttu-id="ea654-352">使用 **SessionType** 和 **ModulesToImport** 参数来确定哪些模块和管理单元已导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-352">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span>

<span data-ttu-id="ea654-353">当会话配置文件中包含任何 **可见** 参数时，PowerShell 会从会话中删除该 `Import-Module` cmdlet 及其 ipmo 别名。</span><span class="sxs-lookup"><span data-stu-id="ea654-353">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="ea654-354">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="ea654-354">-VisibleProviders</span></span>

<span data-ttu-id="ea654-355">将会话中的 PowerShell 提供程序限制为在此参数的值中指定的提供程序。</span><span class="sxs-lookup"><span data-stu-id="ea654-355">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="ea654-356">支持使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ea654-356">Wildcard characters are supported.</span></span>

<span data-ttu-id="ea654-357">默认情况下，会话中的模块导出的所有提供程序都在该会话中可见。</span><span class="sxs-lookup"><span data-stu-id="ea654-357">By default, all providers that modules in the session export are visible in the session.</span></span> <span data-ttu-id="ea654-358">使用 **SessionType** 和 **ModulesToImport** 参数确定导入到会话中的模块。</span><span class="sxs-lookup"><span data-stu-id="ea654-358">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="ea654-359">当会话配置文件中包含任何 **可见** 参数时，PowerShell 将从会话中删除该 `Import-Module` cmdlet 及其 `ipmo` 别名。</span><span class="sxs-lookup"><span data-stu-id="ea654-359">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="ea654-360">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ea654-360">CommonParameters</span></span>

<span data-ttu-id="ea654-361">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ea654-361">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ea654-362">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ea654-362">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ea654-363">输入</span><span class="sxs-lookup"><span data-stu-id="ea654-363">INPUTS</span></span>

### <span data-ttu-id="ea654-364">无</span><span class="sxs-lookup"><span data-stu-id="ea654-364">None</span></span>

<span data-ttu-id="ea654-365">不能通过管道将任何对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea654-365">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="ea654-366">输出</span><span class="sxs-lookup"><span data-stu-id="ea654-366">OUTPUTS</span></span>

### <span data-ttu-id="ea654-367">无</span><span class="sxs-lookup"><span data-stu-id="ea654-367">None</span></span>

<span data-ttu-id="ea654-368">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ea654-368">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ea654-369">注释</span><span class="sxs-lookup"><span data-stu-id="ea654-369">NOTES</span></span>

- <span data-ttu-id="ea654-370">诸如 **VisibleCmdlets** 和 **VisibleProviders** 的参数不会将项导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="ea654-370">Parameters, such as **VisibleCmdlets** and **VisibleProviders** , do not import items into the session.</span></span> <span data-ttu-id="ea654-371">而会从导入到会话中的项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="ea654-371">Instead, they select from among the items imported into the session.</span></span> <span data-ttu-id="ea654-372">例如，如果 **VisibleProviders** 参数的值是证书提供程序，但 **ModulesToImport** 参数未指定包含证书提供程序的 **模块，** 则该证书提供程序在会话中不可见。</span><span class="sxs-lookup"><span data-stu-id="ea654-372">For example, if the value of the **VisibleProviders** parameter is the Certificate provider, but the **ModulesToImport** parameter does not specify the **Microsoft.PowerShell.Security** module that contains the Certificate provider, the Certificate provider is not visible in the session.</span></span>
- <span data-ttu-id="ea654-373">`New-PSSessionConfigurationFile` 创建会话配置文件 **，该文件在 path 参数中** 指定的路径中具有 .pssc 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="ea654-373">`New-PSSessionConfigurationFile` creates a session configuration file that has a .pssc file name extension in the path that you specify in the **Path** parameter.</span></span> <span data-ttu-id="ea654-374">使用会话配置文件创建会话配置时，该 `Register-PSSessionConfiguration` cmdlet 会复制配置文件，并将该文件的活动副本保存在目录的 **SessionConfig** 子目录中 `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="ea654-374">When you use the session configuration file to create a session configuration, the `Register-PSSessionConfiguration` cmdlet copies the configuration file and saves an active copy of the file in the **SessionConfig** subdirectory of the `$PSHOME` directory.</span></span>

  <span data-ttu-id="ea654-375">会话配置的 **ConfigFilePath** 属性包含活动会话配置文件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="ea654-375">The **ConfigFilePath** property of the session configuration contains the fully qualified path of the active session configuration file.</span></span> <span data-ttu-id="ea654-376">你可以随时 `$PSHOME` 使用任意文本编辑器修改该目录中的活动配置文件。</span><span class="sxs-lookup"><span data-stu-id="ea654-376">You can modify the active configuration file in the `$PSHOME` directory at any time using any text editor.</span></span> <span data-ttu-id="ea654-377">所做的更改会影响使用该会话配置的所有新会话，但不会影响现有会话。</span><span class="sxs-lookup"><span data-stu-id="ea654-377">The changes that you make affect all new sessions that use the session configuration, but not existing sessions.</span></span>

  <span data-ttu-id="ea654-378">使用已编辑的会话配置文件之前，请使用 `Test-PSSessionConfigurationFile` cmdlet 验证配置文件项是否有效。</span><span class="sxs-lookup"><span data-stu-id="ea654-378">Before using an edited session configuration file, use the `Test-PSSessionConfigurationFile` cmdlet to verify that the configuration file entries are valid.</span></span>

## <span data-ttu-id="ea654-379">相关链接</span><span class="sxs-lookup"><span data-stu-id="ea654-379">RELATED LINKS</span></span>

[<span data-ttu-id="ea654-380">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea654-380">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="ea654-381">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea654-381">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="ea654-382">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea654-382">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="ea654-383">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea654-383">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="ea654-384">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea654-384">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="ea654-385">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="ea654-385">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="ea654-386">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea654-386">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="ea654-387">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="ea654-387">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="ea654-388">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="ea654-388">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="ea654-389">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="ea654-389">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
