---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 17b28b14a9610dd48a03cc8c654806e75d3d97e3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197169"
---
# <span data-ttu-id="91008-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="91008-103">New-Service</span></span>

## <span data-ttu-id="91008-104">摘要</span><span class="sxs-lookup"><span data-stu-id="91008-104">SYNOPSIS</span></span>
<span data-ttu-id="91008-105">创建新的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="91008-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="91008-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="91008-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="91008-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="91008-107">DESCRIPTION</span></span>

<span data-ttu-id="91008-108">`New-Service`Cmdlet 在注册表和服务数据库中为 Windows 服务创建一个新条目。</span><span class="sxs-lookup"><span data-stu-id="91008-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="91008-109">新服务需要在服务过程中运行的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="91008-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="91008-110">此 cmdlet 的参数用于设置该服务的显示名称、说明、启动类型和依赖项。</span><span class="sxs-lookup"><span data-stu-id="91008-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="91008-111">示例</span><span class="sxs-lookup"><span data-stu-id="91008-111">EXAMPLES</span></span>

### <span data-ttu-id="91008-112">示例1：创建服务</span><span class="sxs-lookup"><span data-stu-id="91008-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="91008-113">此命令创建名为 TestService 的服务。</span><span class="sxs-lookup"><span data-stu-id="91008-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="91008-114">示例2：创建包含说明、启动类型和显示名称的服务</span><span class="sxs-lookup"><span data-stu-id="91008-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="91008-115">此命令创建名为 TestService 的服务。</span><span class="sxs-lookup"><span data-stu-id="91008-115">This command creates a service named TestService.</span></span> <span data-ttu-id="91008-116">它使用的参数 `New-Service` 来指定新服务的说明、启动类型和显示名称。</span><span class="sxs-lookup"><span data-stu-id="91008-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="91008-117">示例3：查看新服务</span><span class="sxs-lookup"><span data-stu-id="91008-117">Example 3: View the new service</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service -Filter "Name='testservice'"
```

```Output
ExitCode  : 0
Name      : testservice
ProcessId : 0
StartMode : Auto
State     : Stopped
Status    : OK
```

<span data-ttu-id="91008-118">此命令使用 `Get-CimInstance` 获取新服务的 **Win32_Service** 对象。</span><span class="sxs-lookup"><span data-stu-id="91008-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="91008-119">此对象包含启动模式和服务说明。</span><span class="sxs-lookup"><span data-stu-id="91008-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="91008-120">示例4：创建服务时设置服务的 SecurityDescriptor。</span><span class="sxs-lookup"><span data-stu-id="91008-120">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="91008-121">此示例将添加正在创建的服务的 **SecurityDescriptor** 。</span><span class="sxs-lookup"><span data-stu-id="91008-121">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="91008-122">**SecurityDescriptor** 存储在 `$SDDLToSet` 变量中。</span><span class="sxs-lookup"><span data-stu-id="91008-122">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="91008-123">**SecurityDescriptorSddl** 参数用于 `$SDDL` 设置新服务的 **SecurityDescriptor** 。</span><span class="sxs-lookup"><span data-stu-id="91008-123">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="91008-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="91008-124">PARAMETERS</span></span>

### <span data-ttu-id="91008-125">-BinaryPathName</span><span class="sxs-lookup"><span data-stu-id="91008-125">-BinaryPathName</span></span>

<span data-ttu-id="91008-126">指定服务的可执行文件的路径。</span><span class="sxs-lookup"><span data-stu-id="91008-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="91008-127">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="91008-127">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91008-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="91008-128">-Credential</span></span>

<span data-ttu-id="91008-129">将服务使用的帐户指定为 [服务登录帐户](/windows/desktop/ad/about-service-logon-accounts)。</span><span class="sxs-lookup"><span data-stu-id="91008-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="91008-130">键入用户名（如 **User01** 或 **Domain01\User01** ）或输入 PSCredential 对象，例如由 Cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="91008-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="91008-131">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="91008-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="91008-132">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="91008-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="91008-133">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="91008-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="91008-134">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="91008-134">-DependsOn</span></span>

<span data-ttu-id="91008-135">指定新服务所依赖的其他服务的名称。</span><span class="sxs-lookup"><span data-stu-id="91008-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="91008-136">若要输入多个服务名称，请使用逗号分隔这些名称。</span><span class="sxs-lookup"><span data-stu-id="91008-136">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="91008-137">-Description</span><span class="sxs-lookup"><span data-stu-id="91008-137">-Description</span></span>

<span data-ttu-id="91008-138">指定服务的描述。</span><span class="sxs-lookup"><span data-stu-id="91008-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="91008-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="91008-139">-DisplayName</span></span>

<span data-ttu-id="91008-140">指定服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="91008-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="91008-141">-Name</span><span class="sxs-lookup"><span data-stu-id="91008-141">-Name</span></span>

<span data-ttu-id="91008-142">指定服务的名称。</span><span class="sxs-lookup"><span data-stu-id="91008-142">Specifies the name of the service.</span></span>
<span data-ttu-id="91008-143">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="91008-143">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91008-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="91008-144">-StartupType</span></span>

<span data-ttu-id="91008-145">设置服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="91008-145">Sets the startup type of the service.</span></span> <span data-ttu-id="91008-146">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="91008-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="91008-147">**自动** -服务已启动或由操作系统在系统启动时启动。</span><span class="sxs-lookup"><span data-stu-id="91008-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="91008-148">如果一个自动启动的服务依赖于手动启动的服务，则该手动启动的服务也会在系统启动时自动启动。</span><span class="sxs-lookup"><span data-stu-id="91008-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="91008-149">**AutomaticDelayedStart** -系统启动后立即启动。</span><span class="sxs-lookup"><span data-stu-id="91008-149">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="91008-150">**已禁用** -服务已禁用，无法由用户或应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="91008-150">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="91008-151">**InvalidValue** -不支持此值。</span><span class="sxs-lookup"><span data-stu-id="91008-151">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="91008-152">使用此值将导致错误。</span><span class="sxs-lookup"><span data-stu-id="91008-152">Using this value results in an error.</span></span>
- <span data-ttu-id="91008-153">**手动** -服务仅通过用户、使用服务控制管理器或应用程序手动启动。</span><span class="sxs-lookup"><span data-stu-id="91008-153">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="91008-154">默认值为 " **自动** "。</span><span class="sxs-lookup"><span data-stu-id="91008-154">The default value is **Automatic** .</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91008-155">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="91008-155">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="91008-156">以 **Sddl** 格式指定服务的 **SecurityDescriptor** 。</span><span class="sxs-lookup"><span data-stu-id="91008-156">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="91008-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="91008-157">-Confirm</span></span>

<span data-ttu-id="91008-158">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="91008-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="91008-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="91008-159">-WhatIf</span></span>

<span data-ttu-id="91008-160">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="91008-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="91008-161">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="91008-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="91008-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="91008-162">CommonParameters</span></span>

<span data-ttu-id="91008-163">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="91008-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="91008-164">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="91008-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="91008-165">输入</span><span class="sxs-lookup"><span data-stu-id="91008-165">INPUTS</span></span>

### <span data-ttu-id="91008-166">无</span><span class="sxs-lookup"><span data-stu-id="91008-166">None</span></span>

<span data-ttu-id="91008-167">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="91008-167">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="91008-168">输出</span><span class="sxs-lookup"><span data-stu-id="91008-168">OUTPUTS</span></span>

### <span data-ttu-id="91008-169">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="91008-169">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="91008-170">此 cmdlet 将返回一个表示新服务的对象。</span><span class="sxs-lookup"><span data-stu-id="91008-170">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="91008-171">注释</span><span class="sxs-lookup"><span data-stu-id="91008-171">NOTES</span></span>

<span data-ttu-id="91008-172">若要在 Windows Vista 和更高版本的 Windows 操作系统上运行此 cmdlet，请使用 "以管理员身份运行" 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="91008-172">To run this cmdlet on Windows Vista and later versions of the Windows operating system, start PowerShell by using the Run as administrator option.</span></span>

## <span data-ttu-id="91008-173">相关链接</span><span class="sxs-lookup"><span data-stu-id="91008-173">RELATED LINKS</span></span>

[<span data-ttu-id="91008-174">Get-Service</span><span class="sxs-lookup"><span data-stu-id="91008-174">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="91008-175">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="91008-175">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="91008-176">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="91008-176">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="91008-177">Set-Service</span><span class="sxs-lookup"><span data-stu-id="91008-177">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="91008-178">Start-Service</span><span class="sxs-lookup"><span data-stu-id="91008-178">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="91008-179">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="91008-179">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="91008-180">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="91008-180">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="91008-181">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="91008-181">Remove-Service</span></span>](Remove-Service.md)
