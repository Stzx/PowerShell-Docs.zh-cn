---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 758b0a8ef9a5f65f0e7cfa7f3633086cf9f0445d
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94891762"
---
# <span data-ttu-id="f1a9d-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-103">New-Service</span></span>

## <span data-ttu-id="f1a9d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f1a9d-104">SYNOPSIS</span></span>
<span data-ttu-id="f1a9d-105">创建新的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="f1a9d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f1a9d-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f1a9d-107">说明</span><span class="sxs-lookup"><span data-stu-id="f1a9d-107">DESCRIPTION</span></span>

<span data-ttu-id="f1a9d-108">`New-Service`Cmdlet 在注册表和服务数据库中为 Windows 服务创建一个新条目。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="f1a9d-109">新服务需要在服务过程中运行的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="f1a9d-110">此 cmdlet 的参数用于设置该服务的显示名称、说明、启动类型和依赖项。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="f1a9d-111">示例</span><span class="sxs-lookup"><span data-stu-id="f1a9d-111">EXAMPLES</span></span>

### <span data-ttu-id="f1a9d-112">示例1：创建服务</span><span class="sxs-lookup"><span data-stu-id="f1a9d-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

<span data-ttu-id="f1a9d-113">此命令创建名为 TestService 的服务。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="f1a9d-114">示例2：创建包含说明、启动类型和显示名称的服务</span><span class="sxs-lookup"><span data-stu-id="f1a9d-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="f1a9d-115">此命令创建名为 TestService 的服务。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-115">This command creates a service named TestService.</span></span> <span data-ttu-id="f1a9d-116">它使用的参数 `New-Service` 来指定新服务的说明、启动类型和显示名称。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="f1a9d-117">示例3：查看新服务</span><span class="sxs-lookup"><span data-stu-id="f1a9d-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="f1a9d-118">此命令使用 `Get-CimInstance` 获取新服务的 **Win32_Service** 对象。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="f1a9d-119">此对象包含启动模式和服务说明。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="f1a9d-120">示例4：删除服务</span><span class="sxs-lookup"><span data-stu-id="f1a9d-120">Example 4: Delete a service</span></span>

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

<span data-ttu-id="f1a9d-121">此示例展示了删除 TestService 服务的两种方法。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-121">This example shows two ways to delete the TestService service.</span></span> <span data-ttu-id="f1a9d-122">第一个命令使用的删除选项 `Sc.exe` 。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-122">The first command uses the delete option of `Sc.exe`.</span></span> <span data-ttu-id="f1a9d-123">第二个命令使用返回的 **Win32_Service** 对象的 **Delete** 方法 `Get-CimInstance` 。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-123">The second command uses the **Delete** method of the **Win32_Service** objects that `Get-CimInstance` returns.</span></span>

## <span data-ttu-id="f1a9d-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f1a9d-124">PARAMETERS</span></span>

### <span data-ttu-id="f1a9d-125">-BinaryPathName</span><span class="sxs-lookup"><span data-stu-id="f1a9d-125">-BinaryPathName</span></span>

<span data-ttu-id="f1a9d-126">指定服务的可执行文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="f1a9d-127">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-127">This parameter is required.</span></span>

<span data-ttu-id="f1a9d-128">服务二进制文件的完全限定路径。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-128">The fully qualified path to the service binary file.</span></span> <span data-ttu-id="f1a9d-129">如果路径包含空格，则必须将其括在引号中，以便对其进行正确解释。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-129">If the path contains a space, it must be quoted so that it is correctly interpreted.</span></span> <span data-ttu-id="f1a9d-130">例如， `d:\my share\myservice.exe` 应将指定为 `'"d:\my share\myservice.exe"'` 。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-130">For example, `d:\my share\myservice.exe` should be specified as `'"d:\my share\myservice.exe"'`.</span></span>

<span data-ttu-id="f1a9d-131">该路径还可以包含自动启动服务的参数。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-131">The path can also include arguments for an auto-start service.</span></span> <span data-ttu-id="f1a9d-132">例如 `'"d:\myshare\myservice.exe arg1 arg2"'`。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-132">For example, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span></span> <span data-ttu-id="f1a9d-133">这些参数将传递到服务入口点。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-133">These arguments are passed to the service entry point.</span></span>

<span data-ttu-id="f1a9d-134">有关详细信息，请参阅 [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API 的 **lpBinaryPathName** 参数。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-134">For more information, see the **lpBinaryPathName** parameter of [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f1a9d-135">-Credential</span><span class="sxs-lookup"><span data-stu-id="f1a9d-135">-Credential</span></span>

<span data-ttu-id="f1a9d-136">将服务使用的帐户指定为 [服务登录帐户](/windows/desktop/ad/about-service-logon-accounts)。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-136">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="f1a9d-137">键入用户名（如 **User01** 或 **Domain01\User01**）或输入 PSCredential 对象，例如由 Cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-137">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f1a9d-138">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-138">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="f1a9d-139">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-139">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="f1a9d-140">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-140">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="f1a9d-141">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="f1a9d-141">-DependsOn</span></span>

<span data-ttu-id="f1a9d-142">指定新服务所依赖的其他服务的名称。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-142">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="f1a9d-143">若要输入多个服务名称，请使用逗号分隔这些名称。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-143">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="f1a9d-144">-Description</span><span class="sxs-lookup"><span data-stu-id="f1a9d-144">-Description</span></span>

<span data-ttu-id="f1a9d-145">指定服务的描述。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-145">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="f1a9d-146">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="f1a9d-146">-DisplayName</span></span>

<span data-ttu-id="f1a9d-147">指定服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-147">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="f1a9d-148">-Name</span><span class="sxs-lookup"><span data-stu-id="f1a9d-148">-Name</span></span>

<span data-ttu-id="f1a9d-149">指定服务的名称。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-149">Specifies the name of the service.</span></span> <span data-ttu-id="f1a9d-150">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-150">This parameter is required.</span></span>

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

### <span data-ttu-id="f1a9d-151">-StartupType</span><span class="sxs-lookup"><span data-stu-id="f1a9d-151">-StartupType</span></span>

<span data-ttu-id="f1a9d-152">设置服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-152">Sets the startup type of the service.</span></span> <span data-ttu-id="f1a9d-153">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="f1a9d-153">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f1a9d-154">**自动** -服务已启动或由操作系统在系统启动时启动。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-154">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="f1a9d-155">如果一个自动启动的服务依赖于手动启动的服务，则该手动启动的服务也会在系统启动时自动启动。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-155">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="f1a9d-156">**已禁用** -服务已禁用，无法由用户或应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-156">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="f1a9d-157">**手动** -服务仅通过用户、使用服务控制管理器或应用程序手动启动。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-157">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="f1a9d-158">**启动** -表示服务是由系统加载程序启动的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-158">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="f1a9d-159">此值仅对设备驱动程序有效。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-159">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="f1a9d-160">**系统** -指示服务是由 "IOInitSystem ( # A1" 函数启动的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-160">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="f1a9d-161">此值仅对设备驱动程序有效。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-161">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="f1a9d-162">默认值为 " **自动**"。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-162">The default value is **Automatic**.</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases:
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f1a9d-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f1a9d-163">-Confirm</span></span>

<span data-ttu-id="f1a9d-164">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f1a9d-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f1a9d-165">-WhatIf</span></span>

<span data-ttu-id="f1a9d-166">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-166">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f1a9d-167">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f1a9d-168">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f1a9d-168">CommonParameters</span></span>

<span data-ttu-id="f1a9d-169">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f1a9d-170">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-170">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f1a9d-171">输入</span><span class="sxs-lookup"><span data-stu-id="f1a9d-171">INPUTS</span></span>

### <span data-ttu-id="f1a9d-172">无</span><span class="sxs-lookup"><span data-stu-id="f1a9d-172">None</span></span>

<span data-ttu-id="f1a9d-173">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-173">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f1a9d-174">输出</span><span class="sxs-lookup"><span data-stu-id="f1a9d-174">OUTPUTS</span></span>

### <span data-ttu-id="f1a9d-175">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="f1a9d-175">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="f1a9d-176">此 cmdlet 将返回一个表示新服务的对象。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-176">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="f1a9d-177">注释</span><span class="sxs-lookup"><span data-stu-id="f1a9d-177">NOTES</span></span>

<span data-ttu-id="f1a9d-178">若要运行此 cmdlet，请使用 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-178">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="f1a9d-179">若要删除服务，请使用 Sc.exe，或使用 `Get-CimInstance` cmdlet 获取表示该服务的 **Win32_Service** 对象，然后使用 **delete** 方法删除该服务。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-179">To delete a service, use Sc.exe, or use the `Get-CimInstance` cmdlet to get the **Win32_Service** object that represents the service and then use the **Delete** method to delete the service.</span></span> <span data-ttu-id="f1a9d-180">返回的对象 `Get-Service` 没有删除方法。</span><span class="sxs-lookup"><span data-stu-id="f1a9d-180">The object that `Get-Service` returns does not have a delete method.</span></span>

## <span data-ttu-id="f1a9d-181">相关链接</span><span class="sxs-lookup"><span data-stu-id="f1a9d-181">RELATED LINKS</span></span>

[<span data-ttu-id="f1a9d-182">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-182">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="f1a9d-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="f1a9d-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="f1a9d-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="f1a9d-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="f1a9d-187">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-187">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="f1a9d-188">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="f1a9d-188">Suspend-Service</span></span>](Suspend-Service.md)
