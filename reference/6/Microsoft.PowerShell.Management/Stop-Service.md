---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: ed62e60e18594624c4c7aa940cc90bd09a1aa83c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345062"
---
# <span data-ttu-id="03f0d-103">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-103">Stop-Service</span></span>

## <span data-ttu-id="03f0d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="03f0d-104">SYNOPSIS</span></span>
<span data-ttu-id="03f0d-105">停止一个或多个正在运行的服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-105">Stops one or more running services.</span></span>

## <span data-ttu-id="03f0d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="03f0d-106">SYNTAX</span></span>

### <span data-ttu-id="03f0d-107">InputObject（默认值）</span><span class="sxs-lookup"><span data-stu-id="03f0d-107">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="03f0d-108">默认</span><span class="sxs-lookup"><span data-stu-id="03f0d-108">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="03f0d-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="03f0d-109">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="03f0d-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="03f0d-110">DESCRIPTION</span></span>

<span data-ttu-id="03f0d-111">`Stop-Service`Cmdlet 为每个指定的服务向 Windows 服务控制器发送一条停止消息。</span><span class="sxs-lookup"><span data-stu-id="03f0d-111">The `Stop-Service` cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="03f0d-112">你可以通过服务名称或显示名称来指定服务，也可以使用 **InputObject** 参数传递表示要停止的服务的服务对象。</span><span class="sxs-lookup"><span data-stu-id="03f0d-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="03f0d-113">示例</span><span class="sxs-lookup"><span data-stu-id="03f0d-113">EXAMPLES</span></span>

### <span data-ttu-id="03f0d-114">示例1：停止本地计算机上的服务</span><span class="sxs-lookup"><span data-stu-id="03f0d-114">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="03f0d-115">此命令停止本地计算机上的性能日志和警报 (SysmonLog) 服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-115">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="03f0d-116">示例2：使用显示名称停止服务</span><span class="sxs-lookup"><span data-stu-id="03f0d-116">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="03f0d-117">此命令停止本地计算机上的 Telnet 服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-117">This command stops the Telnet service on the local computer.</span></span> <span data-ttu-id="03f0d-118">该命令使用 `Get-Service` 来获取表示 Telnet 服务的对象。</span><span class="sxs-lookup"><span data-stu-id="03f0d-118">The command uses `Get-Service` to get an object that represents the Telnet service.</span></span> <span data-ttu-id="03f0d-119">管道运算符 (将 `|` 对象) 管道传输到 `Stop-Service` 停止服务的对象。</span><span class="sxs-lookup"><span data-stu-id="03f0d-119">The pipeline operator (`|`) pipes the object to `Stop-Service`, which stops the service.</span></span>

### <span data-ttu-id="03f0d-120">示例3：停止具有依赖服务的服务</span><span class="sxs-lookup"><span data-stu-id="03f0d-120">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="03f0d-121">此示例在本地计算机上停止 IISAdmin 服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-121">This example stops the IISAdmin service on the local computer.</span></span> <span data-ttu-id="03f0d-122">由于停止此服务还会停止依赖于 IISAdmin 服务的服务，因此最好 `Stop-Service` 在列出依赖于 IISAdmin 服务的服务的命令之前。</span><span class="sxs-lookup"><span data-stu-id="03f0d-122">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede `Stop-Service` with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="03f0d-123">第一个命令列出依赖于 IISAdmin 的服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-123">The first command lists the services that depend on IISAdmin.</span></span> <span data-ttu-id="03f0d-124">它使用 `Get-Service` 获取表示 IISAdmin 服务的对象。</span><span class="sxs-lookup"><span data-stu-id="03f0d-124">It uses `Get-Service` to get an object that represents the IISAdmin service.</span></span> <span data-ttu-id="03f0d-125">管道运算符 (`|`) 将结果传递给 `Format-List` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="03f0d-125">The pipeline operator (`|`) passes the result to the `Format-List` cmdlet.</span></span> <span data-ttu-id="03f0d-126">该命令使用的 **属性** 参数 `Format-List` 来仅列出该服务的 **Name** 和 **DependentServices** 属性。</span><span class="sxs-lookup"><span data-stu-id="03f0d-126">The command uses the **Property** parameter of `Format-List` to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="03f0d-127">第二个命令停止 IISAdmin 服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-127">The second command stops the IISAdmin service.</span></span> <span data-ttu-id="03f0d-128">需要使用 **Force** 参数来停止具有依赖服务的服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-128">The **Force** parameter is required to stop a service that has dependent services.</span></span> <span data-ttu-id="03f0d-129">该命令使用 **Confirm** 参数在停止每个服务之前请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="03f0d-129">The command uses the **Confirm** parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="03f0d-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="03f0d-130">PARAMETERS</span></span>

### <span data-ttu-id="03f0d-131">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="03f0d-131">-DisplayName</span></span>

<span data-ttu-id="03f0d-132">指定要停止的服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="03f0d-132">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="03f0d-133">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="03f0d-133">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="03f0d-134">-Exclude</span><span class="sxs-lookup"><span data-stu-id="03f0d-134">-Exclude</span></span>

<span data-ttu-id="03f0d-135">指定此 cmdlet 省略的服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-135">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="03f0d-136">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="03f0d-136">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="03f0d-137">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="03f0d-137">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="03f0d-138">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="03f0d-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="03f0d-139">-Force</span><span class="sxs-lookup"><span data-stu-id="03f0d-139">-Force</span></span>

<span data-ttu-id="03f0d-140">强制 cmdlet 停止服务（即使该服务有依赖服务）。</span><span class="sxs-lookup"><span data-stu-id="03f0d-140">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="03f0d-141">-Include</span><span class="sxs-lookup"><span data-stu-id="03f0d-141">-Include</span></span>

<span data-ttu-id="03f0d-142">指定此 cmdlet 停止的服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-142">Specifies services that this cmdlet stops.</span></span> <span data-ttu-id="03f0d-143">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="03f0d-143">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="03f0d-144">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="03f0d-144">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="03f0d-145">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="03f0d-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="03f0d-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="03f0d-146">-InputObject</span></span>

<span data-ttu-id="03f0d-147">指定表示要停止的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="03f0d-147">Specifies **ServiceController** objects that represent the services to stop.</span></span> <span data-ttu-id="03f0d-148">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="03f0d-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="03f0d-149">-Name</span><span class="sxs-lookup"><span data-stu-id="03f0d-149">-Name</span></span>

<span data-ttu-id="03f0d-150">指定要停止的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="03f0d-150">Specifies the service names of the services to stop.</span></span> <span data-ttu-id="03f0d-151">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="03f0d-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="03f0d-152">-NoWait</span><span class="sxs-lookup"><span data-stu-id="03f0d-152">-NoWait</span></span>

<span data-ttu-id="03f0d-153">指示此 cmdlet 使用 "无等待" 选项。</span><span class="sxs-lookup"><span data-stu-id="03f0d-153">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="03f0d-154">-PassThru</span><span class="sxs-lookup"><span data-stu-id="03f0d-154">-PassThru</span></span>

<span data-ttu-id="03f0d-155">返回一个表示服务的对象。</span><span class="sxs-lookup"><span data-stu-id="03f0d-155">Returns an object that represents the service.</span></span> <span data-ttu-id="03f0d-156">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="03f0d-156">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="03f0d-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="03f0d-157">-Confirm</span></span>

<span data-ttu-id="03f0d-158">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="03f0d-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="03f0d-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="03f0d-159">-WhatIf</span></span>

<span data-ttu-id="03f0d-160">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="03f0d-160">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="03f0d-161">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="03f0d-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="03f0d-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="03f0d-162">CommonParameters</span></span>

<span data-ttu-id="03f0d-163">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="03f0d-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="03f0d-164">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="03f0d-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="03f0d-165">输入</span><span class="sxs-lookup"><span data-stu-id="03f0d-165">INPUTS</span></span>

### <span data-ttu-id="03f0d-166">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="03f0d-166">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="03f0d-167">可以通过管道将服务对象或包含服务名称的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="03f0d-167">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="03f0d-168">输出</span><span class="sxs-lookup"><span data-stu-id="03f0d-168">OUTPUTS</span></span>

### <span data-ttu-id="03f0d-169">无、System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="03f0d-169">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="03f0d-170">如果使用 **PassThru** 参数，则此 cmdlet 将生成表示服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="03f0d-170">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the **PassThru** parameter.</span></span> <span data-ttu-id="03f0d-171">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="03f0d-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="03f0d-172">注释</span><span class="sxs-lookup"><span data-stu-id="03f0d-172">NOTES</span></span>

<span data-ttu-id="03f0d-173">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="03f0d-173">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="03f0d-174">还可以 `Stop-Service` 通过其内置别名 **spsv** 来引用。</span><span class="sxs-lookup"><span data-stu-id="03f0d-174">You can also refer to `Stop-Service` by its built-in alias, **spsv**.</span></span> <span data-ttu-id="03f0d-175">有关详细信息，请参阅 about_Aliases。</span><span class="sxs-lookup"><span data-stu-id="03f0d-175">For more information, see about_Aliases.</span></span>

<span data-ttu-id="03f0d-176">`Stop-Service` 仅当当前用户有权执行此操作时，才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="03f0d-176">`Stop-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="03f0d-177">如果某个命令不能正常工作，则可能你不具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="03f0d-177">If a command does not work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="03f0d-178">若要查找服务名称并显示系统中的服务名称，请键入 `Get-Service`。</span><span class="sxs-lookup"><span data-stu-id="03f0d-178">To find the service names and display names of the services on your system, type `Get-Service`.</span></span> <span data-ttu-id="03f0d-179">服务名称显示在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="03f0d-179">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="03f0d-180">相关链接</span><span class="sxs-lookup"><span data-stu-id="03f0d-180">RELATED LINKS</span></span>

[<span data-ttu-id="03f0d-181">Get-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-181">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="03f0d-182">New-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-182">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="03f0d-183">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-183">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="03f0d-184">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-184">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="03f0d-185">Set-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-185">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="03f0d-186">Start-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-186">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="03f0d-187">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-187">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="03f0d-188">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="03f0d-188">Remove-Service</span></span>](Remove-Service.md)
