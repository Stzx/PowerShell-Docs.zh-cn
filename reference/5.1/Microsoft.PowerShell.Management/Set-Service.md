---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198034"
---
# <span data-ttu-id="03d4b-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-103">Set-Service</span></span>

## <span data-ttu-id="03d4b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="03d4b-104">SYNOPSIS</span></span>
<span data-ttu-id="03d4b-105">启动、停止和挂起服务并更改服务的属性。</span><span class="sxs-lookup"><span data-stu-id="03d4b-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="03d4b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03d4b-106">SYNTAX</span></span>

### <span data-ttu-id="03d4b-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="03d4b-107">Name (Default)</span></span>

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="03d4b-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="03d4b-108">InputObject</span></span>

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="03d4b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="03d4b-109">DESCRIPTION</span></span>

<span data-ttu-id="03d4b-110">`Set-Service`Cmdlet 更改服务的属性，如 **状态** 、 **说明** 、 **DisplayName** 和 **StartupType** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="03d4b-111">`Set-Service` 可以启动、停止、挂起或暂停服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="03d4b-112">若要标识服务，请输入其服务名称或提交服务对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="03d4b-113">或者，将服务名称或服务对象向下发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="03d4b-114">示例</span><span class="sxs-lookup"><span data-stu-id="03d4b-114">EXAMPLES</span></span>

### <span data-ttu-id="03d4b-115">示例1：更改显示名称</span><span class="sxs-lookup"><span data-stu-id="03d4b-115">Example 1: Change a display name</span></span>

<span data-ttu-id="03d4b-116">在此示例中，将更改服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="03d4b-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="03d4b-117">若要查看原始显示名称，请使用 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="03d4b-118">`Set-Service` 使用 **name** 参数来指定服务的名称， **LanmanWorkstation** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="03d4b-119">**DisplayName** 参数指定新的显示名称 " **LanMan Workstation** "。</span><span class="sxs-lookup"><span data-stu-id="03d4b-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="03d4b-120">示例2：更改服务的启动类型</span><span class="sxs-lookup"><span data-stu-id="03d4b-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="03d4b-121">此示例演示如何更改服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="03d4b-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="03d4b-122">`Set-Service` 使用 **name** 参数来指定服务的名称， **位** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="03d4b-123">**StartupType** 参数将服务设置为 **自动** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="03d4b-124">`Get-Service` 使用 **Name** 参数指定 **BITS** 服务，并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="03d4b-125">`Select-Object` 使用 **属性** 参数显示 **BITS** 服务的状态。</span><span class="sxs-lookup"><span data-stu-id="03d4b-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="03d4b-126">示例3：更改服务的描述</span><span class="sxs-lookup"><span data-stu-id="03d4b-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="03d4b-127">此示例更改 BITS 服务的说明并显示结果。</span><span class="sxs-lookup"><span data-stu-id="03d4b-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="03d4b-128">`Get-CimInstance`使用 cmdlet 的原因是它将返回一个包含服务 **说明** 的 **Win32_Service** 对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

<span data-ttu-id="03d4b-129">`Get-CimInstance` 将对象向下发送到管道， `Format-List` 并显示服务的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="03d4b-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="03d4b-130">出于比较目的，将在更新说明之前和之后运行该命令。</span><span class="sxs-lookup"><span data-stu-id="03d4b-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="03d4b-131">`Set-Service` 使用 **Name** 参数指定 **BITS** 服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="03d4b-132">**Description** 参数指定服务说明的更新文本。</span><span class="sxs-lookup"><span data-stu-id="03d4b-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="03d4b-133">示例4：启动服务</span><span class="sxs-lookup"><span data-stu-id="03d4b-133">Example 4: Start a service</span></span>

<span data-ttu-id="03d4b-134">在此示例中，启动了服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="03d4b-135">`Set-Service` 使用 **Name** 参数来指定服务 **WinRM** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="03d4b-136">**Status** 参数使用 **运行** 的值来启动服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="03d4b-137">**PassThru** 参数输出显示结果的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="03d4b-138">示例5：挂起服务</span><span class="sxs-lookup"><span data-stu-id="03d4b-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="03d4b-139">此示例使用管道暂停到服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="03d4b-140">`Get-Service` 使用 **Name** 参数指定 **计划** 服务，并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="03d4b-141">`Set-Service` 使用 **Status** 参数将服务设置为 "已 **暂停** "。</span><span class="sxs-lookup"><span data-stu-id="03d4b-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="03d4b-142">示例6：停止服务</span><span class="sxs-lookup"><span data-stu-id="03d4b-142">Example 6: Stop a service</span></span>

<span data-ttu-id="03d4b-143">此示例使用变量来停止服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="03d4b-144">`Get-Service` 使用 **Name** 参数来指定服务的 **计划** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="03d4b-145">对象存储在变量中 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="03d4b-146">`Set-Service` 使用 **InputObject** 参数，并指定存储的对象 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="03d4b-147">**Status** 参数将服务设置为 " **已停止** "。</span><span class="sxs-lookup"><span data-stu-id="03d4b-147">The **Status** parameter sets the service to **Stopped** .</span></span>

## <span data-ttu-id="03d4b-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03d4b-148">PARAMETERS</span></span>

### <span data-ttu-id="03d4b-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="03d4b-149">-ComputerName</span></span>

<span data-ttu-id="03d4b-150">指定一台或多台计算机。</span><span class="sxs-lookup"><span data-stu-id="03d4b-150">Specifies one or more computers.</span></span> <span data-ttu-id="03d4b-151">对于远程计算机，请键入 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="03d4b-151">For remote computers, type the NetBIOS name, an IP address, or a fully qualified domain name.</span></span> <span data-ttu-id="03d4b-152">如果未指定 **ComputerName** 参数，此命令将在本地计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="03d4b-152">If the **ComputerName** parameter isn't specified, the command runs on the local computer.</span></span>

<span data-ttu-id="03d4b-153">此参数不依赖于 PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="03d4b-153">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="03d4b-154">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="03d4b-154">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="03d4b-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="03d4b-155">-Confirm</span></span>

<span data-ttu-id="03d4b-156">在运行之前提示你进行确认 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-156">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="03d4b-157">-Description</span><span class="sxs-lookup"><span data-stu-id="03d4b-157">-Description</span></span>

<span data-ttu-id="03d4b-158">指定服务的新说明。</span><span class="sxs-lookup"><span data-stu-id="03d4b-158">Specifies a new description for the service.</span></span>

<span data-ttu-id="03d4b-159">服务说明出现在 **"计算机管理，服务** " 中。</span><span class="sxs-lookup"><span data-stu-id="03d4b-159">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="03d4b-160">**说明** 不是 `Get-Service` **ServiceController** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="03d4b-160">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="03d4b-161">若要查看服务说明，请使用 `Get-CimInstance` ，它将返回表示服务的 **Win32_Service** 对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-161">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="03d4b-162">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="03d4b-162">-DisplayName</span></span>

<span data-ttu-id="03d4b-163">指定服务的新显示名称。</span><span class="sxs-lookup"><span data-stu-id="03d4b-163">Specifies a new display name for the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d4b-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="03d4b-164">-InputObject</span></span>

<span data-ttu-id="03d4b-165">指定表示要更改的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-165">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="03d4b-166">输入包含该对象的变量，或键入获取该对象的命令或表达式（如 `Get-Service` 命令）。</span><span class="sxs-lookup"><span data-stu-id="03d4b-166">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="03d4b-167">您可以使用管道将服务对象发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-167">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="03d4b-168">-Name</span><span class="sxs-lookup"><span data-stu-id="03d4b-168">-Name</span></span>

<span data-ttu-id="03d4b-169">指定要更改的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="03d4b-169">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="03d4b-170">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="03d4b-170">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="03d4b-171">您可以使用管道将服务名称发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-171">You can use the pipeline to send a service name to `Set-Service`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="03d4b-172">-PassThru</span><span class="sxs-lookup"><span data-stu-id="03d4b-172">-PassThru</span></span>

<span data-ttu-id="03d4b-173">返回表示已更改的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-173">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="03d4b-174">默认情况下， `Set-Service` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="03d4b-174">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="03d4b-175">-StartupType</span><span class="sxs-lookup"><span data-stu-id="03d4b-175">-StartupType</span></span>

<span data-ttu-id="03d4b-176">设置服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="03d4b-176">Sets the startup type of the service.</span></span> <span data-ttu-id="03d4b-177">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="03d4b-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="03d4b-178">**自动** -服务已启动或由操作系统在系统启动时启动。</span><span class="sxs-lookup"><span data-stu-id="03d4b-178">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="03d4b-179">如果一个自动启动的服务依赖于手动启动的服务，则该手动启动的服务也会在系统启动时自动启动。</span><span class="sxs-lookup"><span data-stu-id="03d4b-179">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="03d4b-180">**已禁用** -服务已禁用，无法由用户或应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="03d4b-180">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="03d4b-181">**手动** -服务仅通过用户、使用服务控制管理器或应用程序手动启动。</span><span class="sxs-lookup"><span data-stu-id="03d4b-181">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="03d4b-182">**启动** -表示服务是由系统加载程序启动的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="03d4b-182">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="03d4b-183">此值仅对设备驱动程序有效。</span><span class="sxs-lookup"><span data-stu-id="03d4b-183">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="03d4b-184">**系统** -指示服务是由 "IOInitSystem ( # A1" 函数启动的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="03d4b-184">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="03d4b-185">此值仅对设备驱动程序有效。</span><span class="sxs-lookup"><span data-stu-id="03d4b-185">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="03d4b-186">默认值为 " **自动** "。</span><span class="sxs-lookup"><span data-stu-id="03d4b-186">The default value is **Automatic** .</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d4b-187">-Status</span><span class="sxs-lookup"><span data-stu-id="03d4b-187">-Status</span></span>

<span data-ttu-id="03d4b-188">指定服务的状态。</span><span class="sxs-lookup"><span data-stu-id="03d4b-188">Specifies the status for the service.</span></span>

<span data-ttu-id="03d4b-189">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="03d4b-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="03d4b-190">已 **暂停** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-190">**Paused** .</span></span> <span data-ttu-id="03d4b-191">挂起服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-191">Suspends the service.</span></span>
- <span data-ttu-id="03d4b-192">**正在运行** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-192">**Running** .</span></span> <span data-ttu-id="03d4b-193">启动服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-193">Starts the service.</span></span>
- <span data-ttu-id="03d4b-194">**已停止** 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-194">**Stopped** .</span></span> <span data-ttu-id="03d4b-195">停止服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-195">Stops the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="03d4b-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="03d4b-196">-WhatIf</span></span>

<span data-ttu-id="03d4b-197">显示运行时将发生 `Set-Service` 的情况。</span><span class="sxs-lookup"><span data-stu-id="03d4b-197">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="03d4b-198">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="03d4b-198">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="03d4b-199">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="03d4b-199">CommonParameters</span></span>

<span data-ttu-id="03d4b-200">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="03d4b-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03d4b-201">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="03d4b-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03d4b-202">输入</span><span class="sxs-lookup"><span data-stu-id="03d4b-202">INPUTS</span></span>

### <span data-ttu-id="03d4b-203">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="03d4b-203">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="03d4b-204">您可以使用管道将服务对象或包含服务名称的字符串发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-204">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="03d4b-205">输出</span><span class="sxs-lookup"><span data-stu-id="03d4b-205">OUTPUTS</span></span>

### <span data-ttu-id="03d4b-206">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="03d4b-206">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="03d4b-207">默认情况下， `Set-Service` 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-207">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="03d4b-208">使用 **PassThru** 参数输出 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="03d4b-208">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="03d4b-209">注释</span><span class="sxs-lookup"><span data-stu-id="03d4b-209">NOTES</span></span>

<span data-ttu-id="03d4b-210">`Set-Service` 需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="03d4b-210">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="03d4b-211">使用 "以 **管理员身份运行** " 选项。</span><span class="sxs-lookup"><span data-stu-id="03d4b-211">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="03d4b-212">`Set-Service` 仅当当前用户有权管理服务时，才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="03d4b-212">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="03d4b-213">如果某个命令不能正常工作，则可能没有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="03d4b-213">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="03d4b-214">若要查找服务的服务名称或显示名称，请使用 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="03d4b-214">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="03d4b-215">服务名称在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="03d4b-215">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="03d4b-216">相关链接</span><span class="sxs-lookup"><span data-stu-id="03d4b-216">RELATED LINKS</span></span>

[<span data-ttu-id="03d4b-217">Get-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-217">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="03d4b-218">New-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-218">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="03d4b-219">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-219">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="03d4b-220">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-220">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="03d4b-221">Start-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-221">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="03d4b-222">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-222">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="03d4b-223">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="03d4b-223">Suspend-Service</span></span>](Suspend-Service.md)
