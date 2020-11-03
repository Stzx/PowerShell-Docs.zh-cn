---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: d01de5a438ef0a3692ad9452fd4c16ac7e0bdce9
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199094"
---
# <span data-ttu-id="8a15f-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a15f-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="8a15f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="8a15f-104">SYNOPSIS</span></span>
<span data-ttu-id="8a15f-105">更改已注册会话配置的属性。</span><span class="sxs-lookup"><span data-stu-id="8a15f-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="8a15f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a15f-106">SYNTAX</span></span>

### <span data-ttu-id="8a15f-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="8a15f-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8a15f-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="8a15f-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="8a15f-109">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8a15f-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="8a15f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8a15f-110">DESCRIPTION</span></span>

<span data-ttu-id="8a15f-111">`Set-PSSessionConfiguration`Cmdlet 更改本地计算机上的会话配置的属性。</span><span class="sxs-lookup"><span data-stu-id="8a15f-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="8a15f-112">使用 **Name** 参数标识要更改的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="8a15f-113">使用其他参数为会话配置的属性指定新值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="8a15f-114">若要从配置中删除属性值并使用默认值，请输入空字符串 ( "" ) 或 `$Null` 相应参数的值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="8a15f-115">从 PowerShell 3.0 开始，你可以使用会话配置文件来定义会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="8a15f-116">此功能提供了一种简单且易于发现的方法，可用于设置和更改使用会话配置的会话的属性。</span><span class="sxs-lookup"><span data-stu-id="8a15f-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="8a15f-117">若要指定会话配置文件，请使用的 **Path** 参数 `Set-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="8a15f-118">有关会话配置文件的信息，请参阅 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)。</span><span class="sxs-lookup"><span data-stu-id="8a15f-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="8a15f-119">有关如何创建和修改会话配置文件的信息，请参阅 `New-PSSessionConfigurationFile` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8a15f-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="8a15f-120">会话配置定义连接到本地计算机 ( **pssession** ) 的远程会话的环境。</span><span class="sxs-lookup"><span data-stu-id="8a15f-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="8a15f-121">每个 **PSSession** 都使用会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="8a15f-122">会话配置确定 **PSSession** 的功能，例如会话中可用的模块、允许运行的 cmdlet、语言模式、配额和超时。</span><span class="sxs-lookup"><span data-stu-id="8a15f-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="8a15f-123">会话配置的安全描述符确定哪些用户可以使用会话配置连接到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="8a15f-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="8a15f-124">有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="8a15f-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="8a15f-125">若要查看会话配置的属性，请使用 `Get-PSSessionConfiguration` cmdlet 或 WSMan 提供程序。</span><span class="sxs-lookup"><span data-stu-id="8a15f-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="8a15f-126">有关 WSMan 提供程序的详细信息，请键入 `Get-Help WSMan` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="8a15f-127">示例</span><span class="sxs-lookup"><span data-stu-id="8a15f-127">EXAMPLES</span></span>

### <span data-ttu-id="8a15f-128">示例1：创建和更改会话配置</span><span class="sxs-lookup"><span data-stu-id="8a15f-128">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="8a15f-129">此示例演示如何从配置中添加和删除启动脚本。</span><span class="sxs-lookup"><span data-stu-id="8a15f-129">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="8a15f-130">第一个命令创建 **AdminShell** 配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-130">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="8a15f-131">第二个命令将此 `AdminConfig.ps1` 脚本添加到配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-131">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="8a15f-132">重新启动 **WinRM** 后，更改才有效。</span><span class="sxs-lookup"><span data-stu-id="8a15f-132">The change is effective when you restart **WinRM** .</span></span>
<span data-ttu-id="8a15f-133">第三个命令 `AdminConfig.ps1` 从配置中删除该脚本。</span><span class="sxs-lookup"><span data-stu-id="8a15f-133">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="8a15f-134">示例2：显示结果</span><span class="sxs-lookup"><span data-stu-id="8a15f-134">Example 2: Display results</span></span>

<span data-ttu-id="8a15f-135">此示例将 **MaximumReceivedObjectSizeMB** 属性的值增加到20。</span><span class="sxs-lookup"><span data-stu-id="8a15f-135">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="8a15f-136">此命令还会提示你重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="8a15f-136">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="8a15f-137">在重新启动 **WinRM** 服务之前，更改不会生效。</span><span class="sxs-lookup"><span data-stu-id="8a15f-137">The change is not effective until the **WinRM** service is restarted.</span></span>

```powershell
Set-PSSessionConfiguration -Name "IncObj" -MaximumReceivedObjectSizeMB 20
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\IncObj\InitializationParameters

ParamName                       ParamValue
---------                       ----------
psmaximumreceivedobjectsizemb   20

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

### <span data-ttu-id="8a15f-138">示例3：以不同的方式显示结果</span><span class="sxs-lookup"><span data-stu-id="8a15f-138">Example 3: Display results in different ways</span></span>

<span data-ttu-id="8a15f-139">在此示例中，将 `Set-PSSessionConfiguration` **MaintenanceShell** 会话配置中的启动脚本更改为 `Maintenance.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-139">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="8a15f-140">输出显示更改并提示你重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="8a15f-140">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="8a15f-141">响应是“y”（是）。</span><span class="sxs-lookup"><span data-stu-id="8a15f-141">The response is "y" (yes).</span></span>

<span data-ttu-id="8a15f-142">`Get-PSSessionConfiguration` 获取 **MaintenanceShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-142">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="8a15f-143">管道运算符 (|) 将命令的结果发送到 `Format-List` ，后者将在列表中显示配置对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="8a15f-143">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="8a15f-144">接下来，使用 WSMan 提供程序查看 **MaintenanceShell** 配置的初始化参数。</span><span class="sxs-lookup"><span data-stu-id="8a15f-144">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="8a15f-145">`Get-ChildItem` (别名 `dir`) 获取 **MaintenanceShell** 插件的 **InitializationParameters** 节点中的子项目。</span><span class="sxs-lookup"><span data-stu-id="8a15f-145">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="8a15f-146">有关 WSMan 提供程序的详细信息，请键入 `Get-Help wsman` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-146">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

```powershell
Set-PSSessionConfiguration -Name "MaintenanceShell" -StartupScript "C:\ps-test\Maintenance.ps1"
```

```Output
WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin\MaintenanceShell\InitializationParameters

ParamName            ParamValue
---------            ----------
startupscript        c:\ps-test\Mainte...

"Restart WinRM service"
WinRM service need to be restarted to make the changes effective. Do you want to run
the command "restart-service winrm"?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y

```

```powershell
Get-PSSessionConfiguration MaintenanceShell | Format-List -Property *
```

```Output
xmlns            : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
Name             : MaintenanceShell
Filename         : %windir%\system32\pwrshplugin.dll
SDKVersion       : 1
XmlRenderingType : text
lang             : en-US
PSVersion        : 2.0
startupscript    : c:\ps-test\Maintenance.ps1
ResourceUri      : http://schemas.microsoft.com/powershell/MaintenanceShell
SupportsOptions  : true
ExactMatch       : true
Capability       : {Shell}
Permission       :
```

```powershell
dir WSMan:\localhost\Plugin\MaintenanceShell\InitializationParameters
```

```Output
ParamName     ParamValue
---------     ----------
PSVersion     2.0
startupscript c:\ps-test\Maintenance.ps1
```

## <span data-ttu-id="8a15f-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a15f-147">PARAMETERS</span></span>

### <span data-ttu-id="8a15f-148">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="8a15f-148">-AccessMode</span></span>

<span data-ttu-id="8a15f-149">启用和禁用会话配置，并确定它是否可以用于计算机上的远程或本地会话。</span><span class="sxs-lookup"><span data-stu-id="8a15f-149">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="8a15f-150">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="8a15f-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8a15f-151">已禁用。</span><span class="sxs-lookup"><span data-stu-id="8a15f-151">Disabled.</span></span> <span data-ttu-id="8a15f-152">禁用会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-152">Disables the session configuration.</span></span> <span data-ttu-id="8a15f-153">它不能用于对计算机的远程或本地访问。</span><span class="sxs-lookup"><span data-stu-id="8a15f-153">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="8a15f-154">此值将会话配置的 **Enabled** 属性设置 (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) 设置为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-154">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False** .</span></span>
- <span data-ttu-id="8a15f-155">Local。</span><span class="sxs-lookup"><span data-stu-id="8a15f-155">Local.</span></span> <span data-ttu-id="8a15f-156">将 **Network_Deny_All** 条目添加到会话配置的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="8a15f-156">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="8a15f-157">本地计算机的用户可以使用会话配置在同一台计算机上创建本地环回会话，但会拒绝远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="8a15f-157">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="8a15f-158">远程.</span><span class="sxs-lookup"><span data-stu-id="8a15f-158">Remote.</span></span> <span data-ttu-id="8a15f-159">从会话配置的安全描述符中删除 **Deny_All** 和 **Network_Deny_All** 条目。</span><span class="sxs-lookup"><span data-stu-id="8a15f-159">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="8a15f-160">本地和远程计算机的用户都可以使用会话配置来创建会话，并在此计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="8a15f-160">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="8a15f-161">默认值为 " **远程** "。</span><span class="sxs-lookup"><span data-stu-id="8a15f-161">The default value is **Remote** .</span></span>

<span data-ttu-id="8a15f-162">其他 cmdlet 稍后可以重写此参数的值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-162">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="8a15f-163">例如，该 `Enable-PSRemoting` cmdlet 将启用计算机上的所有会话配置并允许远程访问这些配置，并且该 `Disable-PSRemoting` cmdlet 只允许对计算机上的所有会话配置进行本地访问。</span><span class="sxs-lookup"><span data-stu-id="8a15f-163">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="8a15f-164">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-164">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSessionConfigurationAccessMode
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Local, Remote

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-165">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="8a15f-165">-ApplicationBase</span></span>

<span data-ttu-id="8a15f-166">指定 \* 在 **AssemblyName** 参数的值中指定的程序集文件 () 的路径。</span><span class="sxs-lookup"><span data-stu-id="8a15f-166">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-167">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="8a15f-167">-AssemblyName</span></span>

<span data-ttu-id="8a15f-168">指定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="8a15f-168">Specifies the assembly name.</span></span> <span data-ttu-id="8a15f-169">此 cmdlet 将基于在程序集中定义的类来创建会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-169">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="8a15f-170">输入定义会话配置的程序集 .dll 文件的文件名或完整路径。</span><span class="sxs-lookup"><span data-stu-id="8a15f-170">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="8a15f-171">如果只输入文件名，则可以在 **ApplicationBase** 参数的值中输入路径。</span><span class="sxs-lookup"><span data-stu-id="8a15f-171">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-172">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="8a15f-172">-ConfigurationTypeName</span></span>

<span data-ttu-id="8a15f-173">指定在 **AssemblyName** 参数的程序集中定义的会话配置的类型。</span><span class="sxs-lookup"><span data-stu-id="8a15f-173">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="8a15f-174">指定的类型必须实现 **System.Management.Automation.Remoting.PSSessionConfiguration** 类。</span><span class="sxs-lookup"><span data-stu-id="8a15f-174">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="8a15f-175">在指定程序集名称时需要此参数。</span><span class="sxs-lookup"><span data-stu-id="8a15f-175">This parameter is required when you specify an assembly name.</span></span>

```yaml
Type: System.String
Parameter Sets: AssemblyNameParameterSet
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-176">-Force</span><span class="sxs-lookup"><span data-stu-id="8a15f-176">-Force</span></span>

<span data-ttu-id="8a15f-177">禁止显示所有用户提示，并在不提示的情况下重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="8a15f-177">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="8a15f-178">重新启动服务可使配置更改生效。</span><span class="sxs-lookup"><span data-stu-id="8a15f-178">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="8a15f-179">若要阻止重新启动并取消重新启动提示，请使用 **NoServiceRestart** 参数。</span><span class="sxs-lookup"><span data-stu-id="8a15f-179">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="8a15f-180">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="8a15f-180">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="8a15f-181">指定在任何单个远程命令中可以发送到此计算机的数据量限制。</span><span class="sxs-lookup"><span data-stu-id="8a15f-181">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="8a15f-182">输入数据大小（以兆字节 (MB) 为单位）。</span><span class="sxs-lookup"><span data-stu-id="8a15f-182">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="8a15f-183">默认值为 50 MB。</span><span class="sxs-lookup"><span data-stu-id="8a15f-183">The default is 50 MB.</span></span>

<span data-ttu-id="8a15f-184">如果在 **ConfigurationTypeName** 参数中指定的配置类型中定义了数据大小限制，则使用配置类型中的限制。</span><span class="sxs-lookup"><span data-stu-id="8a15f-184">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="8a15f-185">忽略此参数的值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-185">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-186">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="8a15f-186">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="8a15f-187">指定在任何单个对象中可以发送到此计算机的数据量的限制。</span><span class="sxs-lookup"><span data-stu-id="8a15f-187">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="8a15f-188">输入数据大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="8a15f-188">Enter the data size in megabytes.</span></span> <span data-ttu-id="8a15f-189">默认值为 10 MB。</span><span class="sxs-lookup"><span data-stu-id="8a15f-189">The default is 10 MB.</span></span>

<span data-ttu-id="8a15f-190">如果在 **ConfigurationTypeName** 参数中指定的配置类型中定义了对象大小限制，则使用配置类型中的限制。</span><span class="sxs-lookup"><span data-stu-id="8a15f-190">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="8a15f-191">忽略此参数的值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-191">The value of this parameter is ignored.</span></span>

```yaml
Type: System.Nullable`1[System.Double]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-192">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="8a15f-192">-ModulesToImport</span></span>

<span data-ttu-id="8a15f-193">指定自动导入使用该会话配置的会话的模块和管理单元。</span><span class="sxs-lookup"><span data-stu-id="8a15f-193">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="8a15f-194">输入模块和管理单元名称。</span><span class="sxs-lookup"><span data-stu-id="8a15f-194">Enter the module and snap-in names.</span></span>

<span data-ttu-id="8a15f-195">默认情况下，只会将 **Microsoft. Core** 管理单元导入到会话中，但除非排除 cmdlet，否则可以使用 `Import-Module` 和 Add-PSSnapin cmdlet 将模块和管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="8a15f-195">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="8a15f-196">此参数值中指定的模块将导入到会话配置文件 () 中指定的模块中 `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-196">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="8a15f-197">但是，会话配置文件中的设置可以隐藏模块所导出的命令或阻止用户使用它们。</span><span class="sxs-lookup"><span data-stu-id="8a15f-197">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="8a15f-198">此参数值中指定的模块将替换使用 cmdlet 的 **ModulesToImport** 参数指定的模块列表 `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-198">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="8a15f-199">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-199">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-200">-Name</span><span class="sxs-lookup"><span data-stu-id="8a15f-200">-Name</span></span>

<span data-ttu-id="8a15f-201">指定要更改的会话配置的名称。</span><span class="sxs-lookup"><span data-stu-id="8a15f-201">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="8a15f-202">不能使用此参数更改会话配置的名称。</span><span class="sxs-lookup"><span data-stu-id="8a15f-202">You cannot use this parameter to change the name of the session configuration.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-203">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="8a15f-203">-NoServiceRestart</span></span>

<span data-ttu-id="8a15f-204">不会重新启动 **WinRM** 服务，而会禁止提示重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="8a15f-204">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="8a15f-205">默认情况下，当你运行时 `Set-PSSessionConfiguration` ，系统将提示你重新启动 **WinRM** 服务以使新的会话配置生效。</span><span class="sxs-lookup"><span data-stu-id="8a15f-205">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="8a15f-206">在重新启动 **WinRM** 服务之前，新的会话配置不会生效。</span><span class="sxs-lookup"><span data-stu-id="8a15f-206">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="8a15f-207">若要在不提示的情况下重新启动 **WinRM** 服务，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="8a15f-207">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="8a15f-208">若要手动重新启动 **WinRM** 服务，请使用 `Restart-Service` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8a15f-208">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="8a15f-209">-Path</span><span class="sxs-lookup"><span data-stu-id="8a15f-209">-Path</span></span>

<span data-ttu-id="8a15f-210">指定会话配置文件的路径 ( .pssc) ，如 cmdlet 创建的文件。 `New-PSSessionConfigurationFile`</span><span class="sxs-lookup"><span data-stu-id="8a15f-210">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="8a15f-211">如果省略路径，则默认路径为当前目录。</span><span class="sxs-lookup"><span data-stu-id="8a15f-211">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="8a15f-212">有关如何修改会话配置文件的信息，请参阅 cmdlet 的帮助主题 `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-212">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="8a15f-213">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-213">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: SessionConfigurationFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-214">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="8a15f-214">-PSVersion</span></span>

<span data-ttu-id="8a15f-215">指定使用此会话配置的会话中的 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="8a15f-215">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="8a15f-216">此参数的值优先于会话配置文件中 **PowerShellVersion** 键的值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-216">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="8a15f-217">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-217">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Version
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases: PowerShellVersion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-218">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="8a15f-218">-RunAsCredential</span></span>

<span data-ttu-id="8a15f-219">指定会话中的命令的凭据。</span><span class="sxs-lookup"><span data-stu-id="8a15f-219">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="8a15f-220">默认情况下，在当前用户授权下运行命令。</span><span class="sxs-lookup"><span data-stu-id="8a15f-220">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="8a15f-221">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-221">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-222">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="8a15f-222">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="8a15f-223">为配置指定其他安全描述符定义语言 (SDDL) 字符串。</span><span class="sxs-lookup"><span data-stu-id="8a15f-223">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="8a15f-224">此字符串确定使用新的会话配置所需的权限。</span><span class="sxs-lookup"><span data-stu-id="8a15f-224">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="8a15f-225">若要在会话中使用会话配置，用户必须至少对配置执行 (调用) 权限。</span><span class="sxs-lookup"><span data-stu-id="8a15f-225">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="8a15f-226">若要使用配置的默认安全描述符，请输入空字符串 ( "" ) 或值 `$Null` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-226">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="8a15f-227">默认为 WSMan: 驱动器中的根 SDDL。</span><span class="sxs-lookup"><span data-stu-id="8a15f-227">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="8a15f-228">如果安全描述符很复杂，请考虑使用 **ShowSecurityDescriptorUI** 参数而不是此描述符。</span><span class="sxs-lookup"><span data-stu-id="8a15f-228">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="8a15f-229">不能在同一命令中同时使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="8a15f-229">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="8a15f-230">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="8a15f-230">-SessionTypeOption</span></span>

<span data-ttu-id="8a15f-231">指定会话配置的特定于类型的选项。</span><span class="sxs-lookup"><span data-stu-id="8a15f-231">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="8a15f-232">输入会话类型选项对象，如 cmdlet 返回的 **new-psworkflowexecutionoption** 对象 `New-PSWorkflowExecutionOption` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-232">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="8a15f-233">使用会话配置的会话选项由会话选项和会话配置选项的值确定。</span><span class="sxs-lookup"><span data-stu-id="8a15f-233">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="8a15f-234">除非指定，否则在会话中设置的选项（如使用 `New-PSSessionOption` cmdlet）优先于在会话配置中设置的选项。</span><span class="sxs-lookup"><span data-stu-id="8a15f-234">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="8a15f-235">但是，会话选项的值不能超过在会话配置中设置的最大值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-235">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="8a15f-236">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-236">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSSessionTypeOption
Parameter Sets: NameParameterSet, AssemblyNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-237">-ShowSecurityDescriptorUI</span><span class="sxs-lookup"><span data-stu-id="8a15f-237">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="8a15f-238">指示此 cmdlet 是可帮助你为会话配置创建新 SDDL 的属性表。</span><span class="sxs-lookup"><span data-stu-id="8a15f-238">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="8a15f-239">运行该命令后，将显示属性表 `Set-PSSessionConfiguration` ，然后重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="8a15f-239">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="8a15f-240">在设置配置的权限时，请记住，用户必须至少具有 "执行 (调用") 权限才能使用会话中的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-240">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="8a15f-241">不能在同一命令中使用 **SecurityDescriptorSDDL** 参数和此参数。</span><span class="sxs-lookup"><span data-stu-id="8a15f-241">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="8a15f-242">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="8a15f-242">-StartupScript</span></span>

<span data-ttu-id="8a15f-243">指定配置的启动脚本。</span><span class="sxs-lookup"><span data-stu-id="8a15f-243">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="8a15f-244">输入 PowerShell 脚本的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="8a15f-244">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="8a15f-245">指定的脚本在使用会话配置的新会话中运行。</span><span class="sxs-lookup"><span data-stu-id="8a15f-245">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="8a15f-246">若要从会话配置中删除启动脚本，请输入空字符串 ( "" ) 或值 `$Null` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-246">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="8a15f-247">你可以使用启动脚本进一步配置用户会话。</span><span class="sxs-lookup"><span data-stu-id="8a15f-247">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="8a15f-248">如果脚本生成错误，甚至是一个非终止错误，则不会创建会话，并且该 `New-PSSession` 命令将失败。</span><span class="sxs-lookup"><span data-stu-id="8a15f-248">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="8a15f-249">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="8a15f-249">-ThreadOptions</span></span>

<span data-ttu-id="8a15f-250">指定配置中的线程选项设置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-250">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="8a15f-251">此设置定义在会话中执行命令时如何创建和使用线程。</span><span class="sxs-lookup"><span data-stu-id="8a15f-251">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="8a15f-252">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="8a15f-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="8a15f-253">默认</span><span class="sxs-lookup"><span data-stu-id="8a15f-253">Default</span></span>
- <span data-ttu-id="8a15f-254">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="8a15f-254">ReuseThread</span></span>
- <span data-ttu-id="8a15f-255">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="8a15f-255">UseCurrentThread</span></span>
- <span data-ttu-id="8a15f-256">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="8a15f-256">UseNewThread</span></span>

<span data-ttu-id="8a15f-257">默认值为 **UseCurrentThread** 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-257">The default value is **UseCurrentThread** .</span></span>

<span data-ttu-id="8a15f-258">有关详细信息，请参阅 [PSThreadOptions 枚举](/dotnet/api/system.management.automation.runspaces.psthreadoptions)。</span><span class="sxs-lookup"><span data-stu-id="8a15f-258">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSThreadOptions
Parameter Sets: (All)
Aliases:
Accepted values: Default, UseNewThread, ReuseThread, UseCurrentThread

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-259">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="8a15f-259">-TransportOption</span></span>

<span data-ttu-id="8a15f-260">指定会话配置的传输选项。</span><span class="sxs-lookup"><span data-stu-id="8a15f-260">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="8a15f-261">输入传输选项对象，如 cmdlet 返回的 **WSManConfigurationOption** 对象 `New-PSTransportOption` 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-261">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="8a15f-262">使用会话配置的会话选项由会话选项和会话配置选项的值确定。</span><span class="sxs-lookup"><span data-stu-id="8a15f-262">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="8a15f-263">除非指定，否则在会话中设置的选项（如使用 `New-PSSessionOption` cmdlet）优先于在会话配置中设置的选项。</span><span class="sxs-lookup"><span data-stu-id="8a15f-263">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="8a15f-264">但是，会话选项的值不能超过在会话配置中设置的最大值。</span><span class="sxs-lookup"><span data-stu-id="8a15f-264">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="8a15f-265">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-265">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTransportOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-266">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="8a15f-266">-UseSharedProcess</span></span>

<span data-ttu-id="8a15f-267">仅使用一个进程来托管由同一用户启动的所有会话，并使用相同的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-267">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="8a15f-268">默认情况下，每个会话都托管在其自身进程中。</span><span class="sxs-lookup"><span data-stu-id="8a15f-268">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="8a15f-269">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="8a15f-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8a15f-270">-Confirm</span></span>

<span data-ttu-id="8a15f-271">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="8a15f-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8a15f-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8a15f-272">-WhatIf</span></span>

<span data-ttu-id="8a15f-273">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="8a15f-273">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8a15f-274">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="8a15f-274">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8a15f-275">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="8a15f-275">-ThreadApartmentState</span></span>

<span data-ttu-id="8a15f-276">指定要使用的线程模块的单元状态。</span><span class="sxs-lookup"><span data-stu-id="8a15f-276">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="8a15f-277">可接受的值为：</span><span class="sxs-lookup"><span data-stu-id="8a15f-277">Acceptable values are:</span></span>

- <span data-ttu-id="8a15f-278">未知</span><span class="sxs-lookup"><span data-stu-id="8a15f-278">Unknown</span></span>
- <span data-ttu-id="8a15f-279">MTA</span><span class="sxs-lookup"><span data-stu-id="8a15f-279">MTA</span></span>
- <span data-ttu-id="8a15f-280">STA</span><span class="sxs-lookup"><span data-stu-id="8a15f-280">STA</span></span>

```yaml
Type: System.Threading.ApartmentState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8a15f-281">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="8a15f-281">CommonParameters</span></span>

<span data-ttu-id="8a15f-282">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="8a15f-282">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8a15f-283">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="8a15f-283">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8a15f-284">输入</span><span class="sxs-lookup"><span data-stu-id="8a15f-284">INPUTS</span></span>

### <span data-ttu-id="8a15f-285">无</span><span class="sxs-lookup"><span data-stu-id="8a15f-285">None</span></span>

<span data-ttu-id="8a15f-286">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8a15f-286">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8a15f-287">输出</span><span class="sxs-lookup"><span data-stu-id="8a15f-287">OUTPUTS</span></span>

### <span data-ttu-id="8a15f-288">WSManConfigLeafElement。</span><span class="sxs-lookup"><span data-stu-id="8a15f-288">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="8a15f-289">注释</span><span class="sxs-lookup"><span data-stu-id="8a15f-289">NOTES</span></span>

<span data-ttu-id="8a15f-290">若要运行此 cmdlet，请使用 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8a15f-290">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="8a15f-291">`Set-PSSessionConfiguration`Cmdlet 不会更改配置名称，并且 **WSMan** 提供程序不支持 `Rename-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8a15f-291">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="8a15f-292">若要更改会话配置的名称，请使用 `Unregister-PSSessionConfiguration` cmdlet 删除该配置，然后使用 `Register-PSSessionConfiguration` cmdlet 创建并注册新的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-292">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="8a15f-293">你可以使用 `Set-PSSessionConfiguration` cmdlet 更改默认的 microsoft.powershell32 会话配置。</span><span class="sxs-lookup"><span data-stu-id="8a15f-293">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="8a15f-294">这些会话配置不受保护。</span><span class="sxs-lookup"><span data-stu-id="8a15f-294">They are not protected.</span></span> <span data-ttu-id="8a15f-295">要恢复为默认会话配置的原始版本，请使用 `Unregister-PSSessionConfiguration` cmdlet 删除默认会话配置，然后使用 `Enable-PSRemoting` cmdlet 将其还原。</span><span class="sxs-lookup"><span data-stu-id="8a15f-295">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="8a15f-296">会话配置对象的属性会根据为会话配置设置的选项以及这些选项的值而有所不同。</span><span class="sxs-lookup"><span data-stu-id="8a15f-296">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="8a15f-297">此外，使用会话配置文件的会话配置还具有其他属性。</span><span class="sxs-lookup"><span data-stu-id="8a15f-297">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="8a15f-298">你可以使用 WSMan: 驱动器中的命令来更改会话配置的属性。</span><span class="sxs-lookup"><span data-stu-id="8a15f-298">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="8a15f-299">但是，不能使用 PowerShell 2.0 中的 WSMan：驱动器来更改 PowerShell 3.0 中引入的会话配置属性，如 **OutputBufferingMode** 。</span><span class="sxs-lookup"><span data-stu-id="8a15f-299">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode** .</span></span> <span data-ttu-id="8a15f-300">Windows PowerShell 2.0 命令不会生成错误，但它们是无效的。</span><span class="sxs-lookup"><span data-stu-id="8a15f-300">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="8a15f-301">若要更改 PowerShell 3.0 中引入的属性，请使用 PowerShell 3.0 中的 WSMan：驱动器。</span><span class="sxs-lookup"><span data-stu-id="8a15f-301">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="8a15f-302">相关链接</span><span class="sxs-lookup"><span data-stu-id="8a15f-302">RELATED LINKS</span></span>

[<span data-ttu-id="8a15f-303">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a15f-303">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="8a15f-304">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a15f-304">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="8a15f-305">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a15f-305">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="8a15f-306">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8a15f-306">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="8a15f-307">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="8a15f-307">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="8a15f-308">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="8a15f-308">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="8a15f-309">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a15f-309">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="8a15f-310">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8a15f-310">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="8a15f-311">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a15f-311">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="8a15f-312">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="8a15f-312">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="8a15f-313">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="8a15f-313">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="8a15f-314">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="8a15f-314">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
