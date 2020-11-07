---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 03/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/set-pssessionconfiguration?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSSessionConfiguration
ms.openlocfilehash: 788e7b9d261a862658f4cf7453f35228dd3ffab6
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345844"
---
# <span data-ttu-id="77480-103">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="77480-103">Set-PSSessionConfiguration</span></span>

## <span data-ttu-id="77480-104">摘要</span><span class="sxs-lookup"><span data-stu-id="77480-104">SYNOPSIS</span></span>
<span data-ttu-id="77480-105">更改已注册会话配置的属性。</span><span class="sxs-lookup"><span data-stu-id="77480-105">Changes the properties of a registered session configuration.</span></span>

## <span data-ttu-id="77480-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="77480-106">SYNTAX</span></span>

### <span data-ttu-id="77480-107">NameParameterSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="77480-107">NameParameterSet (Default)</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-ApplicationBase <String>] [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>]
 [-TransportOption <PSTransportOption>] [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="77480-108">AssemblyNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="77480-108">AssemblyNameParameterSet</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-AssemblyName] <String> [-ApplicationBase <String>]
 [-ConfigurationTypeName] <String> [-RunAsCredential <PSCredential>] [-ThreadOptions <PSThreadOptions>]
 [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess] [-StartupScript <String>]
 [-MaximumReceivedDataSizePerCommandMB <Double>] [-MaximumReceivedObjectSizeMB <Double>]
 [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI] [-Force] [-NoServiceRestart]
 [-PSVersion <Version>] [-SessionTypeOption <PSSessionTypeOption>] [-TransportOption <PSTransportOption>]
 [-ModulesToImport <Object[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="77480-109">SessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="77480-109">SessionConfigurationFile</span></span>

```
Set-PSSessionConfiguration [-Name] <String> [-RunAsCredential <PSCredential>]
 [-ThreadOptions <PSThreadOptions>] [-AccessMode <PSSessionConfigurationAccessMode>] [-UseSharedProcess]
 [-StartupScript <String>] [-MaximumReceivedDataSizePerCommandMB <Double>]
 [-MaximumReceivedObjectSizeMB <Double>] [-SecurityDescriptorSddl <String>] [-ShowSecurityDescriptorUI]
 [-Force] [-NoServiceRestart] [-TransportOption <PSTransportOption>] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="77480-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="77480-110">DESCRIPTION</span></span>

<span data-ttu-id="77480-111">`Set-PSSessionConfiguration`Cmdlet 更改本地计算机上的会话配置的属性。</span><span class="sxs-lookup"><span data-stu-id="77480-111">The `Set-PSSessionConfiguration` cmdlet changes the properties of the session configurations on the local computer.</span></span>

<span data-ttu-id="77480-112">使用 **Name** 参数标识要更改的会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-112">Use the **Name** parameter to identify the session configuration that you want to change.</span></span> <span data-ttu-id="77480-113">使用其他参数为会话配置的属性指定新值。</span><span class="sxs-lookup"><span data-stu-id="77480-113">Use the other parameters to specify new values for the properties of the session configuration.</span></span> <span data-ttu-id="77480-114">若要从配置中删除属性值并使用默认值，请输入空字符串 ( "" ) 或 `$Null` 相应参数的值。</span><span class="sxs-lookup"><span data-stu-id="77480-114">To delete a property value from the configuration, and use the default value, enter an empty string ("") or a value of `$Null` for the corresponding parameter.</span></span>

<span data-ttu-id="77480-115">从 PowerShell 3.0 开始，你可以使用会话配置文件来定义会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-115">Starting in PowerShell 3.0, you can use a session configuration file to define a session configuration.</span></span> <span data-ttu-id="77480-116">此功能提供了一种简单且易于发现的方法，可用于设置和更改使用会话配置的会话的属性。</span><span class="sxs-lookup"><span data-stu-id="77480-116">This feature provides a simple and discoverable method for setting and changing the properties of sessions that use the session configuration.</span></span> <span data-ttu-id="77480-117">若要指定会话配置文件，请使用的 **Path** 参数 `Set-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="77480-117">To specify a session configuration file, use the **Path** parameter of `Set-PSSessionConfiguration`.</span></span> <span data-ttu-id="77480-118">有关会话配置文件的信息，请参阅 [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md)。</span><span class="sxs-lookup"><span data-stu-id="77480-118">For information about session configuration files, see [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>
<span data-ttu-id="77480-119">有关如何创建和修改会话配置文件的信息，请参阅 `New-PSSessionConfigurationFile` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77480-119">For information about how to create and modify a session configuration file, see the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="77480-120">会话配置定义连接到本地计算机 ( **pssession** ) 的远程会话的环境。</span><span class="sxs-lookup"><span data-stu-id="77480-120">Session configurations define the environment of remote sessions ( **PSSessions** ) that connect to the local computer.</span></span> <span data-ttu-id="77480-121">每个 **PSSession** 都使用会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-121">Every **PSSession** uses a session configuration.</span></span> <span data-ttu-id="77480-122">会话配置确定 **PSSession** 的功能，例如会话中可用的模块、允许运行的 cmdlet、语言模式、配额和超时。</span><span class="sxs-lookup"><span data-stu-id="77480-122">The session configuration determines the features of the **PSSession** , such as the modules that are available in the session, the cmdlets that are permitted to run, the language mode, quotas, and timeouts.</span></span> <span data-ttu-id="77480-123">会话配置的安全描述符确定哪些用户可以使用会话配置连接到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="77480-123">The security descriptor of the session configuration determines who can use the session configuration to connect to the local computer.</span></span> <span data-ttu-id="77480-124">有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="77480-124">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="77480-125">若要查看会话配置的属性，请使用 `Get-PSSessionConfiguration` cmdlet 或 WSMan 提供程序。</span><span class="sxs-lookup"><span data-stu-id="77480-125">To see the properties of a session configuration, use the `Get-PSSessionConfiguration` cmdlet or the WSMan Provider.</span></span> <span data-ttu-id="77480-126">有关 WSMan 提供程序的详细信息，请键入 `Get-Help WSMan` 。</span><span class="sxs-lookup"><span data-stu-id="77480-126">For more information about the WSMan Provider, type `Get-Help WSMan`.</span></span>

## <span data-ttu-id="77480-127">示例</span><span class="sxs-lookup"><span data-stu-id="77480-127">EXAMPLES</span></span>

### <span data-ttu-id="77480-128">示例1：创建和更改会话配置</span><span class="sxs-lookup"><span data-stu-id="77480-128">Example 1: Create and change a session configuration</span></span>

<span data-ttu-id="77480-129">此示例演示如何从配置中添加和删除启动脚本。</span><span class="sxs-lookup"><span data-stu-id="77480-129">This example shows how to add and remove a startup script from a configuration.</span></span>

<span data-ttu-id="77480-130">第一个命令创建 **AdminShell** 配置。</span><span class="sxs-lookup"><span data-stu-id="77480-130">The first command creates the **AdminShell** configuration.</span></span> <span data-ttu-id="77480-131">第二个命令将此 `AdminConfig.ps1` 脚本添加到配置。</span><span class="sxs-lookup"><span data-stu-id="77480-131">The second command adds the `AdminConfig.ps1` script to the configuration.</span></span> <span data-ttu-id="77480-132">重新启动 **WinRM** 后，更改才有效。</span><span class="sxs-lookup"><span data-stu-id="77480-132">The change is effective when you restart **WinRM**.</span></span>
<span data-ttu-id="77480-133">第三个命令 `AdminConfig.ps1` 从配置中删除该脚本。</span><span class="sxs-lookup"><span data-stu-id="77480-133">The third command removes the `AdminConfig.ps1` script from the configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name "AdminShell" -AssemblyName "C:\Shells\AdminShell.dll" -ConfigurationTypeName "AdminClass"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript "AdminConfig.ps1"
Set-PSSessionConfiguration -Name "AdminShell" -StartupScript $Null
```

### <span data-ttu-id="77480-134">示例2：显示结果</span><span class="sxs-lookup"><span data-stu-id="77480-134">Example 2: Display results</span></span>

<span data-ttu-id="77480-135">此示例将 **MaximumReceivedObjectSizeMB** 属性的值增加到20。</span><span class="sxs-lookup"><span data-stu-id="77480-135">This example increases the value of the **MaximumReceivedObjectSizeMB** property to 20.</span></span> <span data-ttu-id="77480-136">此命令还会提示你重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="77480-136">This command also prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="77480-137">在重新启动 **WinRM** 服务之前，更改不会生效。</span><span class="sxs-lookup"><span data-stu-id="77480-137">The change is not effective until the **WinRM** service is restarted.</span></span>

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

### <span data-ttu-id="77480-138">示例3：以不同的方式显示结果</span><span class="sxs-lookup"><span data-stu-id="77480-138">Example 3: Display results in different ways</span></span>

<span data-ttu-id="77480-139">在此示例中，将 `Set-PSSessionConfiguration` **MaintenanceShell** 会话配置中的启动脚本更改为 `Maintenance.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="77480-139">In this example, `Set-PSSessionConfiguration` changes the startup script in the **MaintenanceShell** session configuration to `Maintenance.ps1`.</span></span> <span data-ttu-id="77480-140">输出显示更改并提示你重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="77480-140">The output shows the change and prompts you to restart the **WinRM** service.</span></span> <span data-ttu-id="77480-141">响应是“y”（是）。</span><span class="sxs-lookup"><span data-stu-id="77480-141">The response is "y" (yes).</span></span>

<span data-ttu-id="77480-142">`Get-PSSessionConfiguration` 获取 **MaintenanceShell** 会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-142">`Get-PSSessionConfiguration` gets the **MaintenanceShell** session configuration.</span></span> <span data-ttu-id="77480-143">管道运算符 (|) 将命令的结果发送到 `Format-List` ，后者将在列表中显示配置对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="77480-143">The pipeline operator (|) sends the results of the command to `Format-List`, which displays all the properties of the configuration object in a list.</span></span> <span data-ttu-id="77480-144">接下来，使用 WSMan 提供程序查看 **MaintenanceShell** 配置的初始化参数。</span><span class="sxs-lookup"><span data-stu-id="77480-144">Next, using the WSMan provider, we view the initialization parameters for the **MaintenanceShell** configuration.</span></span> <span data-ttu-id="77480-145">`Get-ChildItem` (别名 `dir`) 获取 **MaintenanceShell** 插件的 **InitializationParameters** 节点中的子项目。</span><span class="sxs-lookup"><span data-stu-id="77480-145">`Get-ChildItem` (alias `dir`) gets the child items in the **InitializationParameters** node for the **MaintenanceShell** plug-in.</span></span> <span data-ttu-id="77480-146">有关 WSMan 提供程序的详细信息，请键入 `Get-Help wsman` 。</span><span class="sxs-lookup"><span data-stu-id="77480-146">For more information about the WSMan provider, type `Get-Help wsman`.</span></span>

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

## <span data-ttu-id="77480-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="77480-147">PARAMETERS</span></span>

### <span data-ttu-id="77480-148">-AccessMode</span><span class="sxs-lookup"><span data-stu-id="77480-148">-AccessMode</span></span>

<span data-ttu-id="77480-149">启用和禁用会话配置，并确定它是否可以用于计算机上的远程或本地会话。</span><span class="sxs-lookup"><span data-stu-id="77480-149">Enables and disables the session configuration and determines whether it can be used for remote or local sessions on the computer.</span></span> <span data-ttu-id="77480-150">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="77480-150">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="77480-151">已禁用。</span><span class="sxs-lookup"><span data-stu-id="77480-151">Disabled.</span></span> <span data-ttu-id="77480-152">禁用会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-152">Disables the session configuration.</span></span> <span data-ttu-id="77480-153">它不能用于对计算机的远程或本地访问。</span><span class="sxs-lookup"><span data-stu-id="77480-153">It cannot be used for remote or local access to the computer.</span></span> <span data-ttu-id="77480-154">此值将会话配置的 **Enabled** 属性设置 (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) 设置为 **False** 。</span><span class="sxs-lookup"><span data-stu-id="77480-154">This value sets the **Enabled** property of the session configuration (`WSMan:\<ComputerName>\PlugIn\<SessionConfigurationName>\Enabled`) to **False**.</span></span>
- <span data-ttu-id="77480-155">Local。</span><span class="sxs-lookup"><span data-stu-id="77480-155">Local.</span></span> <span data-ttu-id="77480-156">将 **Network_Deny_All** 条目添加到会话配置的安全描述符。</span><span class="sxs-lookup"><span data-stu-id="77480-156">Adds a **Network_Deny_All** entry to security descriptor of the session configuration.</span></span>
  <span data-ttu-id="77480-157">本地计算机的用户可以使用会话配置在同一台计算机上创建本地环回会话，但会拒绝远程用户访问。</span><span class="sxs-lookup"><span data-stu-id="77480-157">Users of the local computer can use the session configuration to create a local loopback session on the same computer, but remote users are denied access.</span></span>
- <span data-ttu-id="77480-158">远程.</span><span class="sxs-lookup"><span data-stu-id="77480-158">Remote.</span></span> <span data-ttu-id="77480-159">从会话配置的安全描述符中删除 **Deny_All** 和 **Network_Deny_All** 条目。</span><span class="sxs-lookup"><span data-stu-id="77480-159">Removes **Deny_All** and **Network_Deny_All** entries from the security descriptors of the session configuration.</span></span> <span data-ttu-id="77480-160">本地和远程计算机的用户都可以使用会话配置来创建会话，并在此计算机上运行命令。</span><span class="sxs-lookup"><span data-stu-id="77480-160">Users of local and remote computers can use the session configuration to create sessions and run commands on this computer.</span></span>

<span data-ttu-id="77480-161">默认值为 " **远程** "。</span><span class="sxs-lookup"><span data-stu-id="77480-161">The default value is **Remote**.</span></span>

<span data-ttu-id="77480-162">其他 cmdlet 稍后可以重写此参数的值。</span><span class="sxs-lookup"><span data-stu-id="77480-162">Other cmdlets can override the value of this parameter later.</span></span> <span data-ttu-id="77480-163">例如，该 `Enable-PSRemoting` cmdlet 将启用计算机上的所有会话配置并允许远程访问这些配置，并且该 `Disable-PSRemoting` cmdlet 只允许对计算机上的所有会话配置进行本地访问。</span><span class="sxs-lookup"><span data-stu-id="77480-163">For example, the `Enable-PSRemoting` cmdlet enables all session configurations on the computer and permits remote access to them, and the `Disable-PSRemoting` cmdlet permits only local access to all session configurations on the computer.</span></span>

<span data-ttu-id="77480-164">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-164">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-165">-ApplicationBase</span><span class="sxs-lookup"><span data-stu-id="77480-165">-ApplicationBase</span></span>

<span data-ttu-id="77480-166">指定 \* 在 **AssemblyName** 参数的值中指定的程序集文件 () 的路径。</span><span class="sxs-lookup"><span data-stu-id="77480-166">Specifies the path of the assembly file (\*.dll) that is specified in the value of the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="77480-167">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="77480-167">-AssemblyName</span></span>

<span data-ttu-id="77480-168">指定程序集名称。</span><span class="sxs-lookup"><span data-stu-id="77480-168">Specifies the assembly name.</span></span> <span data-ttu-id="77480-169">此 cmdlet 将基于在程序集中定义的类来创建会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-169">This cmdlet creates a session configuration based on a class that is defined in an assembly.</span></span>

<span data-ttu-id="77480-170">输入定义会话配置的程序集 .dll 文件的文件名或完整路径。</span><span class="sxs-lookup"><span data-stu-id="77480-170">Enter the filename or full path of an assembly .dll file that defines a session configuration.</span></span> <span data-ttu-id="77480-171">如果只输入文件名，则可以在 **ApplicationBase** 参数的值中输入路径。</span><span class="sxs-lookup"><span data-stu-id="77480-171">If you enter only the file name, you can enter the path in the value of the **ApplicationBase** parameter.</span></span>

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

### <span data-ttu-id="77480-172">-ConfigurationTypeName</span><span class="sxs-lookup"><span data-stu-id="77480-172">-ConfigurationTypeName</span></span>

<span data-ttu-id="77480-173">指定在 **AssemblyName** 参数的程序集中定义的会话配置的类型。</span><span class="sxs-lookup"><span data-stu-id="77480-173">Specifies the type of the session configuration that is defined in the assembly in the **AssemblyName** parameter.</span></span> <span data-ttu-id="77480-174">指定的类型必须实现 **System.Management.Automation.Remoting.PSSessionConfiguration** 类。</span><span class="sxs-lookup"><span data-stu-id="77480-174">The type that you specify must implement the **System.Management.Automation.Remoting.PSSessionConfiguration** class.</span></span>

<span data-ttu-id="77480-175">在指定程序集名称时需要此参数。</span><span class="sxs-lookup"><span data-stu-id="77480-175">This parameter is required when you specify an assembly name.</span></span>

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

### <span data-ttu-id="77480-176">-Force</span><span class="sxs-lookup"><span data-stu-id="77480-176">-Force</span></span>

<span data-ttu-id="77480-177">禁止显示所有用户提示，并在不提示的情况下重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="77480-177">Suppresses all user prompts, and restarts the **WinRM** service without prompting.</span></span> <span data-ttu-id="77480-178">重新启动服务可使配置更改生效。</span><span class="sxs-lookup"><span data-stu-id="77480-178">Restarting the service makes the configuration change effective.</span></span>

<span data-ttu-id="77480-179">若要阻止重新启动并取消重新启动提示，请使用 **NoServiceRestart** 参数。</span><span class="sxs-lookup"><span data-stu-id="77480-179">To prevent a restart and suppress the restart prompt, use the **NoServiceRestart** parameter.</span></span>

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

### <span data-ttu-id="77480-180">-MaximumReceivedDataSizePerCommandMB</span><span class="sxs-lookup"><span data-stu-id="77480-180">-MaximumReceivedDataSizePerCommandMB</span></span>

<span data-ttu-id="77480-181">指定在任何单个远程命令中可以发送到此计算机的数据量限制。</span><span class="sxs-lookup"><span data-stu-id="77480-181">Specifies the limit on the amount of data that can be sent to this computer in any single remote command.</span></span> <span data-ttu-id="77480-182">输入数据大小（以兆字节 (MB) 为单位）。</span><span class="sxs-lookup"><span data-stu-id="77480-182">Enter the data size in megabytes (MB).</span></span> <span data-ttu-id="77480-183">默认值为 50 MB。</span><span class="sxs-lookup"><span data-stu-id="77480-183">The default is 50 MB.</span></span>

<span data-ttu-id="77480-184">如果在 **ConfigurationTypeName** 参数中指定的配置类型中定义了数据大小限制，则使用配置类型中的限制。</span><span class="sxs-lookup"><span data-stu-id="77480-184">If a data size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="77480-185">忽略此参数的值。</span><span class="sxs-lookup"><span data-stu-id="77480-185">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="77480-186">-MaximumReceivedObjectSizeMB</span><span class="sxs-lookup"><span data-stu-id="77480-186">-MaximumReceivedObjectSizeMB</span></span>

<span data-ttu-id="77480-187">指定在任何单个对象中可以发送到此计算机的数据量的限制。</span><span class="sxs-lookup"><span data-stu-id="77480-187">Specifies the limits on the amount of data that can be sent to this computer in any single object.</span></span>
<span data-ttu-id="77480-188">输入数据大小（以 mb 为单位）。</span><span class="sxs-lookup"><span data-stu-id="77480-188">Enter the data size in megabytes.</span></span> <span data-ttu-id="77480-189">默认值为 10 MB。</span><span class="sxs-lookup"><span data-stu-id="77480-189">The default is 10 MB.</span></span>

<span data-ttu-id="77480-190">如果在 **ConfigurationTypeName** 参数中指定的配置类型中定义了对象大小限制，则使用配置类型中的限制。</span><span class="sxs-lookup"><span data-stu-id="77480-190">If an object size limit is defined in the configuration type that is specified in the **ConfigurationTypeName** parameter, the limit in the configuration type is used.</span></span> <span data-ttu-id="77480-191">忽略此参数的值。</span><span class="sxs-lookup"><span data-stu-id="77480-191">The value of this parameter is ignored.</span></span>

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

### <span data-ttu-id="77480-192">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="77480-192">-ModulesToImport</span></span>

<span data-ttu-id="77480-193">指定自动导入使用该会话配置的会话的模块和管理单元。</span><span class="sxs-lookup"><span data-stu-id="77480-193">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span> <span data-ttu-id="77480-194">输入模块和管理单元名称。</span><span class="sxs-lookup"><span data-stu-id="77480-194">Enter the module and snap-in names.</span></span>

<span data-ttu-id="77480-195">默认情况下，只会将 **Microsoft. Core** 管理单元导入到会话中，但除非排除 cmdlet，否则可以使用 `Import-Module` 和 Add-PSSnapin cmdlet 将模块和管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="77480-195">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into sessions, but unless the cmdlets are excluded, you can use the `Import-Module` and Add-PSSnapin cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="77480-196">此参数值中指定的模块将导入到会话配置文件 () 中指定的模块中 `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="77480-196">The modules specified in this parameter value are imported in additions to modules specified in the session configuration file (`New-PSSessionConfigurationFile`).</span></span> <span data-ttu-id="77480-197">但是，会话配置文件中的设置可以隐藏模块所导出的命令或阻止用户使用它们。</span><span class="sxs-lookup"><span data-stu-id="77480-197">However, settings in the session configuration file can hide the commands exported by modules or prevent users from using them.</span></span>

<span data-ttu-id="77480-198">此参数值中指定的模块将替换使用 cmdlet 的 **ModulesToImport** 参数指定的模块列表 `Register-PSSessionConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="77480-198">The modules specified in this parameter value replace the list of modules specified by using the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="77480-199">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-199">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-200">-Name</span><span class="sxs-lookup"><span data-stu-id="77480-200">-Name</span></span>

<span data-ttu-id="77480-201">指定要更改的会话配置的名称。</span><span class="sxs-lookup"><span data-stu-id="77480-201">Specifies the name of the session configuration that you want to change.</span></span>

<span data-ttu-id="77480-202">不能使用此参数更改会话配置的名称。</span><span class="sxs-lookup"><span data-stu-id="77480-202">You cannot use this parameter to change the name of the session configuration.</span></span>

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

### <span data-ttu-id="77480-203">-NoServiceRestart</span><span class="sxs-lookup"><span data-stu-id="77480-203">-NoServiceRestart</span></span>

<span data-ttu-id="77480-204">不会重新启动 **WinRM** 服务，而会禁止提示重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="77480-204">Does not restart the **WinRM** service, and suppresses the prompt to restart the service.</span></span>

<span data-ttu-id="77480-205">默认情况下，当你运行时 `Set-PSSessionConfiguration` ，系统将提示你重新启动 **WinRM** 服务以使新的会话配置生效。</span><span class="sxs-lookup"><span data-stu-id="77480-205">By default, when you run `Set-PSSessionConfiguration`, you are prompted to restart the **WinRM** service to make the new session configuration effective.</span></span> <span data-ttu-id="77480-206">在重新启动 **WinRM** 服务之前，新的会话配置不会生效。</span><span class="sxs-lookup"><span data-stu-id="77480-206">Until the **WinRM** service is restarted, the new session configuration is not effective.</span></span>

<span data-ttu-id="77480-207">若要在不提示的情况下重新启动 **WinRM** 服务，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="77480-207">To restart the **WinRM** service without prompting, use the **Force** parameter.</span></span> <span data-ttu-id="77480-208">若要手动重新启动 **WinRM** 服务，请使用 `Restart-Service` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77480-208">To restart the **WinRM** service manually, use the `Restart-Service` cmdlet.</span></span>

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

### <span data-ttu-id="77480-209">-Path</span><span class="sxs-lookup"><span data-stu-id="77480-209">-Path</span></span>

<span data-ttu-id="77480-210">指定会话配置文件的路径 ( .pssc) ，如 cmdlet 创建的文件。 `New-PSSessionConfigurationFile`</span><span class="sxs-lookup"><span data-stu-id="77480-210">Specifies the path of a session configuration file (.pssc), such as one created by the `New-PSSessionConfigurationFile` cmdlet.</span></span> <span data-ttu-id="77480-211">如果省略路径，则默认路径为当前目录。</span><span class="sxs-lookup"><span data-stu-id="77480-211">If you omit the path, the default is the current directory.</span></span>

<span data-ttu-id="77480-212">有关如何修改会话配置文件的信息，请参阅 cmdlet 的帮助主题 `New-PSSessionConfigurationFile` 。</span><span class="sxs-lookup"><span data-stu-id="77480-212">For information about how to modify a session configuration file, see the help topic for the `New-PSSessionConfigurationFile` cmdlet.</span></span>

<span data-ttu-id="77480-213">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-213">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-214">-PSVersion</span><span class="sxs-lookup"><span data-stu-id="77480-214">-PSVersion</span></span>

<span data-ttu-id="77480-215">指定使用此会话配置的会话中的 PowerShell 版本。</span><span class="sxs-lookup"><span data-stu-id="77480-215">Specifies the version of PowerShell in sessions that use this session configuration.</span></span>

<span data-ttu-id="77480-216">此参数的值优先于会话配置文件中 **PowerShellVersion** 键的值。</span><span class="sxs-lookup"><span data-stu-id="77480-216">The value of this parameter takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

<span data-ttu-id="77480-217">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-217">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-218">-RunAsCredential</span><span class="sxs-lookup"><span data-stu-id="77480-218">-RunAsCredential</span></span>

<span data-ttu-id="77480-219">指定会话中的命令的凭据。</span><span class="sxs-lookup"><span data-stu-id="77480-219">Specifies credentials for commands in the session.</span></span> <span data-ttu-id="77480-220">默认情况下，在当前用户授权下运行命令。</span><span class="sxs-lookup"><span data-stu-id="77480-220">By default, commands run with the permissions of the current user.</span></span>

<span data-ttu-id="77480-221">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-221">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-222">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="77480-222">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="77480-223">为配置指定其他安全描述符定义语言 (SDDL) 字符串。</span><span class="sxs-lookup"><span data-stu-id="77480-223">Specifies a different Security Descriptor Definition Language (SDDL) string for the configuration.</span></span>

<span data-ttu-id="77480-224">此字符串确定使用新的会话配置所需的权限。</span><span class="sxs-lookup"><span data-stu-id="77480-224">This string determines the permissions that are required to use the new session configuration.</span></span> <span data-ttu-id="77480-225">若要在会话中使用会话配置，用户必须至少对配置执行 (调用) 权限。</span><span class="sxs-lookup"><span data-stu-id="77480-225">To use a session configuration in a session, users must have at least Execute(Invoke) permission for the configuration.</span></span>

<span data-ttu-id="77480-226">若要使用配置的默认安全描述符，请输入空字符串 ( "" ) 或值 `$Null` 。</span><span class="sxs-lookup"><span data-stu-id="77480-226">To use the default security descriptor for the configuration, enter an empty string ("") or a value of `$Null`.</span></span> <span data-ttu-id="77480-227">默认为 WSMan: 驱动器中的根 SDDL。</span><span class="sxs-lookup"><span data-stu-id="77480-227">The default is the root SDDL in the WSMan: drive.</span></span>

<span data-ttu-id="77480-228">如果安全描述符很复杂，请考虑使用 **ShowSecurityDescriptorUI** 参数而不是此描述符。</span><span class="sxs-lookup"><span data-stu-id="77480-228">If the security descriptor is complex, consider using the **ShowSecurityDescriptorUI** parameter instead of this one.</span></span> <span data-ttu-id="77480-229">不能在同一命令中同时使用这两个参数。</span><span class="sxs-lookup"><span data-stu-id="77480-229">You cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="77480-230">-SessionTypeOption</span><span class="sxs-lookup"><span data-stu-id="77480-230">-SessionTypeOption</span></span>

<span data-ttu-id="77480-231">指定会话配置的特定于类型的选项。</span><span class="sxs-lookup"><span data-stu-id="77480-231">Specifies type-specific options for the session configuration.</span></span> <span data-ttu-id="77480-232">输入会话类型选项对象，如 cmdlet 返回的 **new-psworkflowexecutionoption** 对象 `New-PSWorkflowExecutionOption` 。</span><span class="sxs-lookup"><span data-stu-id="77480-232">Enter a session type options object, such as the **PSWorkflowExecutionOption** object that the `New-PSWorkflowExecutionOption` cmdlet returns.</span></span>

<span data-ttu-id="77480-233">使用会话配置的会话选项由会话选项和会话配置选项的值确定。</span><span class="sxs-lookup"><span data-stu-id="77480-233">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="77480-234">除非指定，否则在会话中设置的选项（如使用 `New-PSSessionOption` cmdlet）优先于在会话配置中设置的选项。</span><span class="sxs-lookup"><span data-stu-id="77480-234">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="77480-235">但是，会话选项的值不能超过在会话配置中设置的最大值。</span><span class="sxs-lookup"><span data-stu-id="77480-235">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="77480-236">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-236">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-237">-ShowSecurityDescriptorUI</span><span class="sxs-lookup"><span data-stu-id="77480-237">-ShowSecurityDescriptorUI</span></span>

<span data-ttu-id="77480-238">指示此 cmdlet 是可帮助你为会话配置创建新 SDDL 的属性表。</span><span class="sxs-lookup"><span data-stu-id="77480-238">Indicates that this cmdlet a property sheet that helps you create a new SDDL for the session configuration.</span></span> <span data-ttu-id="77480-239">运行该命令后，将显示属性表 `Set-PSSessionConfiguration` ，然后重新启动 **WinRM** 服务。</span><span class="sxs-lookup"><span data-stu-id="77480-239">The property sheet appears after you run the `Set-PSSessionConfiguration` command and then restart the **WinRM** service.</span></span>

<span data-ttu-id="77480-240">在设置配置的权限时，请记住，用户必须至少具有 "执行 (调用") 权限才能使用会话中的会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-240">When you set permissions to the configuration, remember that users must have at least Execute(Invoke) permission to use the session configuration in a session.</span></span>

<span data-ttu-id="77480-241">不能在同一命令中使用 **SecurityDescriptorSDDL** 参数和此参数。</span><span class="sxs-lookup"><span data-stu-id="77480-241">You cannot use the **SecurityDescriptorSDDL** parameter and this parameter in the same command.</span></span>

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

### <span data-ttu-id="77480-242">-StartupScript</span><span class="sxs-lookup"><span data-stu-id="77480-242">-StartupScript</span></span>

<span data-ttu-id="77480-243">指定配置的启动脚本。</span><span class="sxs-lookup"><span data-stu-id="77480-243">Specifies the startup script for the configuration.</span></span> <span data-ttu-id="77480-244">输入 PowerShell 脚本的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="77480-244">Enter the fully qualified path of a PowerShell script.</span></span> <span data-ttu-id="77480-245">指定的脚本在使用会话配置的新会话中运行。</span><span class="sxs-lookup"><span data-stu-id="77480-245">The specified script runs in the new session that uses the session configuration.</span></span>

<span data-ttu-id="77480-246">若要从会话配置中删除启动脚本，请输入空字符串 ( "" ) 或值 `$Null` 。</span><span class="sxs-lookup"><span data-stu-id="77480-246">To delete a startup script from a session configuration, enter an empty string ("") or a value of `$Null`.</span></span>

<span data-ttu-id="77480-247">你可以使用启动脚本进一步配置用户会话。</span><span class="sxs-lookup"><span data-stu-id="77480-247">You can use a startup script to further configure the user session.</span></span> <span data-ttu-id="77480-248">如果脚本生成错误，甚至是一个非终止错误，则不会创建会话，并且该 `New-PSSession` 命令将失败。</span><span class="sxs-lookup"><span data-stu-id="77480-248">If the script generates an error, even a non-terminating error, the session is not created and the `New-PSSession` command fails.</span></span>

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

### <span data-ttu-id="77480-249">-ThreadOptions</span><span class="sxs-lookup"><span data-stu-id="77480-249">-ThreadOptions</span></span>

<span data-ttu-id="77480-250">指定配置中的线程选项设置。</span><span class="sxs-lookup"><span data-stu-id="77480-250">Specifies the thread options setting in the configuration.</span></span> <span data-ttu-id="77480-251">此设置定义在会话中执行命令时如何创建和使用线程。</span><span class="sxs-lookup"><span data-stu-id="77480-251">This setting defines how threads are created and used when a command is executed in the session.</span></span> <span data-ttu-id="77480-252">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="77480-252">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="77480-253">默认</span><span class="sxs-lookup"><span data-stu-id="77480-253">Default</span></span>
- <span data-ttu-id="77480-254">ReuseThread</span><span class="sxs-lookup"><span data-stu-id="77480-254">ReuseThread</span></span>
- <span data-ttu-id="77480-255">UseCurrentThread</span><span class="sxs-lookup"><span data-stu-id="77480-255">UseCurrentThread</span></span>
- <span data-ttu-id="77480-256">UseNewThread</span><span class="sxs-lookup"><span data-stu-id="77480-256">UseNewThread</span></span>

<span data-ttu-id="77480-257">默认值为 **UseCurrentThread** 。</span><span class="sxs-lookup"><span data-stu-id="77480-257">The default value is **UseCurrentThread**.</span></span>

<span data-ttu-id="77480-258">有关详细信息，请参阅 [PSThreadOptions 枚举](/dotnet/api/system.management.automation.runspaces.psthreadoptions)。</span><span class="sxs-lookup"><span data-stu-id="77480-258">For more information, see [PSThreadOptions Enumeration](/dotnet/api/system.management.automation.runspaces.psthreadoptions).</span></span>

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

### <span data-ttu-id="77480-259">-TransportOption</span><span class="sxs-lookup"><span data-stu-id="77480-259">-TransportOption</span></span>

<span data-ttu-id="77480-260">指定会话配置的传输选项。</span><span class="sxs-lookup"><span data-stu-id="77480-260">Specifies the transport options for the session configuration.</span></span> <span data-ttu-id="77480-261">输入传输选项对象，如 cmdlet 返回的 **WSManConfigurationOption** 对象 `New-PSTransportOption` 。</span><span class="sxs-lookup"><span data-stu-id="77480-261">Enter a transport options object, such as the **WSManConfigurationOption** object that the `New-PSTransportOption` cmdlet returns.</span></span>

<span data-ttu-id="77480-262">使用会话配置的会话选项由会话选项和会话配置选项的值确定。</span><span class="sxs-lookup"><span data-stu-id="77480-262">The options of sessions that use the session configuration are determined by the values of session options and the session configuration options.</span></span> <span data-ttu-id="77480-263">除非指定，否则在会话中设置的选项（如使用 `New-PSSessionOption` cmdlet）优先于在会话配置中设置的选项。</span><span class="sxs-lookup"><span data-stu-id="77480-263">Unless specified, options set in the session, such as by using the `New-PSSessionOption` cmdlet, take precedence over options set in the session configuration.</span></span> <span data-ttu-id="77480-264">但是，会话选项的值不能超过在会话配置中设置的最大值。</span><span class="sxs-lookup"><span data-stu-id="77480-264">However, session option values cannot exceed maximum values set in the session configuration.</span></span>

<span data-ttu-id="77480-265">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-265">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-266">-UseSharedProcess</span><span class="sxs-lookup"><span data-stu-id="77480-266">-UseSharedProcess</span></span>

<span data-ttu-id="77480-267">仅使用一个进程来托管由同一用户启动的所有会话，并使用相同的会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-267">Use only one process to host all sessions that are started by the same user and use the same session configuration.</span></span> <span data-ttu-id="77480-268">默认情况下，每个会话都托管在其自身进程中。</span><span class="sxs-lookup"><span data-stu-id="77480-268">By default, each session is hosted in its own process.</span></span>

<span data-ttu-id="77480-269">此参数是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="77480-269">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="77480-270">-Confirm</span><span class="sxs-lookup"><span data-stu-id="77480-270">-Confirm</span></span>

<span data-ttu-id="77480-271">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="77480-271">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="77480-272">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="77480-272">-WhatIf</span></span>

<span data-ttu-id="77480-273">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="77480-273">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="77480-274">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="77480-274">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="77480-275">-ThreadApartmentState</span><span class="sxs-lookup"><span data-stu-id="77480-275">-ThreadApartmentState</span></span>

<span data-ttu-id="77480-276">指定要使用的线程模块的单元状态。</span><span class="sxs-lookup"><span data-stu-id="77480-276">Specifies the apartment state of the threading module to be used.</span></span> <span data-ttu-id="77480-277">可接受的值为：</span><span class="sxs-lookup"><span data-stu-id="77480-277">Acceptable values are:</span></span>

- <span data-ttu-id="77480-278">未知</span><span class="sxs-lookup"><span data-stu-id="77480-278">Unknown</span></span>
- <span data-ttu-id="77480-279">MTA</span><span class="sxs-lookup"><span data-stu-id="77480-279">MTA</span></span>
- <span data-ttu-id="77480-280">STA</span><span class="sxs-lookup"><span data-stu-id="77480-280">STA</span></span>

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

### <span data-ttu-id="77480-281">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="77480-281">CommonParameters</span></span>

<span data-ttu-id="77480-282">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="77480-282">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="77480-283">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="77480-283">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="77480-284">输入</span><span class="sxs-lookup"><span data-stu-id="77480-284">INPUTS</span></span>

### <span data-ttu-id="77480-285">None</span><span class="sxs-lookup"><span data-stu-id="77480-285">None</span></span>

<span data-ttu-id="77480-286">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77480-286">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="77480-287">输出</span><span class="sxs-lookup"><span data-stu-id="77480-287">OUTPUTS</span></span>

### <span data-ttu-id="77480-288">WSManConfigLeafElement。</span><span class="sxs-lookup"><span data-stu-id="77480-288">Microsoft.WSMan.Management.WSManConfigLeafElement</span></span>

## <span data-ttu-id="77480-289">注释</span><span class="sxs-lookup"><span data-stu-id="77480-289">NOTES</span></span>

<span data-ttu-id="77480-290">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="77480-290">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="77480-291">若要运行此 cmdlet，请使用 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="77480-291">To run this cmdlet, start PowerShell by using the Run as administrator option.</span></span>

<span data-ttu-id="77480-292">`Set-PSSessionConfiguration`Cmdlet 不会更改配置名称，并且 **WSMan** 提供程序不支持 `Rename-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77480-292">The `Set-PSSessionConfiguration` cmdlet does not change the configuration name and the **WSMan** provider does not support the `Rename-Item` cmdlet.</span></span> <span data-ttu-id="77480-293">若要更改会话配置的名称，请使用 `Unregister-PSSessionConfiguration` cmdlet 删除该配置，然后使用 `Register-PSSessionConfiguration` cmdlet 创建并注册新的会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-293">To change the name of a session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the configuration and then use the `Register-PSSessionConfiguration` cmdlet to create and register a new session configuration.</span></span>

<span data-ttu-id="77480-294">你可以使用 `Set-PSSessionConfiguration` cmdlet 更改默认的 microsoft.powershell32 会话配置。</span><span class="sxs-lookup"><span data-stu-id="77480-294">You can use the `Set-PSSessionConfiguration` cmdlet to change the default Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span> <span data-ttu-id="77480-295">这些会话配置不受保护。</span><span class="sxs-lookup"><span data-stu-id="77480-295">They are not protected.</span></span> <span data-ttu-id="77480-296">要恢复为默认会话配置的原始版本，请使用 `Unregister-PSSessionConfiguration` cmdlet 删除默认会话配置，然后使用 `Enable-PSRemoting` cmdlet 将其还原。</span><span class="sxs-lookup"><span data-stu-id="77480-296">To revert to the original version of a default session configuration, use the `Unregister-PSSessionConfiguration` cmdlet to delete the default session configuration and then use the `Enable-PSRemoting` cmdlet to restore it.</span></span>

<span data-ttu-id="77480-297">会话配置对象的属性会根据为会话配置设置的选项以及这些选项的值而有所不同。</span><span class="sxs-lookup"><span data-stu-id="77480-297">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="77480-298">此外，使用会话配置文件的会话配置还具有其他属性。</span><span class="sxs-lookup"><span data-stu-id="77480-298">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="77480-299">你可以使用 WSMan: 驱动器中的命令来更改会话配置的属性。</span><span class="sxs-lookup"><span data-stu-id="77480-299">You can use commands in the WSMan: drive to change the properties of session configurations.</span></span>
<span data-ttu-id="77480-300">但是，不能使用 PowerShell 2.0 中的 WSMan：驱动器来更改 PowerShell 3.0 中引入的会话配置属性，如 **OutputBufferingMode** 。</span><span class="sxs-lookup"><span data-stu-id="77480-300">However, you cannot use the WSMan: drive in PowerShell 2.0 to change session configuration properties that are introduced in PowerShell 3.0, such as **OutputBufferingMode**.</span></span> <span data-ttu-id="77480-301">Windows PowerShell 2.0 命令不会生成错误，但它们是无效的。</span><span class="sxs-lookup"><span data-stu-id="77480-301">Windows PowerShell 2.0 commands do not generate an error, but they are ineffective.</span></span> <span data-ttu-id="77480-302">若要更改 PowerShell 3.0 中引入的属性，请使用 PowerShell 3.0 中的 WSMan：驱动器。</span><span class="sxs-lookup"><span data-stu-id="77480-302">To change properties introduced in PowerShell 3.0, use the WSMan: drive in PowerShell 3.0.</span></span>

## <span data-ttu-id="77480-303">相关链接</span><span class="sxs-lookup"><span data-stu-id="77480-303">RELATED LINKS</span></span>

[<span data-ttu-id="77480-304">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="77480-304">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="77480-305">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="77480-305">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="77480-306">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="77480-306">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="77480-307">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="77480-307">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="77480-308">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="77480-308">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="77480-309">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="77480-309">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="77480-310">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="77480-310">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="77480-311">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="77480-311">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="77480-312">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="77480-312">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="77480-313">WSMan 提供程序</span><span class="sxs-lookup"><span data-stu-id="77480-313">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="77480-314">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="77480-314">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="77480-315">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="77480-315">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)
