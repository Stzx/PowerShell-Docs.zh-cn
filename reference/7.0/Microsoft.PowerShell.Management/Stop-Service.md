---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/stop-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Service
ms.openlocfilehash: 2ae91494b87b9c4cce13d1a41bcbce72405cd0dd
ms.sourcegitcommit: 69b08b28ee2ef3168065672a23b9b6f0c578c95b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "93199396"
---
# <span data-ttu-id="e84b9-103">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-103">Stop-Service</span></span>

## <span data-ttu-id="e84b9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e84b9-104">SYNOPSIS</span></span>
<span data-ttu-id="e84b9-105">停止一个或多个正在运行的服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-105">Stops one or more running services.</span></span>

## <span data-ttu-id="e84b9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e84b9-106">SYNTAX</span></span>

### <span data-ttu-id="e84b9-107">InputObject（默认值）</span><span class="sxs-lookup"><span data-stu-id="e84b9-107">InputObject (Default)</span></span>

```
Stop-Service [-Force] [-NoWait] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e84b9-108">默认</span><span class="sxs-lookup"><span data-stu-id="e84b9-108">Default</span></span>

```
Stop-Service [-Force] [-NoWait] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e84b9-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="e84b9-109">DisplayName</span></span>

```
Stop-Service [-Force] [-NoWait] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e84b9-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e84b9-110">DESCRIPTION</span></span>

<span data-ttu-id="e84b9-111">对于每个指定的服务， **停止服务** Cmdlet 向 Windows 服务控制器发送一条停止消息。</span><span class="sxs-lookup"><span data-stu-id="e84b9-111">The **Stop-Service** cmdlet sends a stop message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="e84b9-112">你可以通过服务名称或显示名称来指定服务，也可以使用 **InputObject** 参数传递表示要停止的服务的服务对象。</span><span class="sxs-lookup"><span data-stu-id="e84b9-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass a service object that represents the service that you want to stop.</span></span>

## <span data-ttu-id="e84b9-113">示例</span><span class="sxs-lookup"><span data-stu-id="e84b9-113">EXAMPLES</span></span>

### <span data-ttu-id="e84b9-114">示例1：停止本地计算机上的服务</span><span class="sxs-lookup"><span data-stu-id="e84b9-114">Example 1: Stop a service on the local computer</span></span>

```
PS C:\> Stop-Service -Name "sysmonlog"
```

<span data-ttu-id="e84b9-115">此命令停止本地计算机上的性能日志和警报 (SysmonLog) 服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-115">This command stops the Performance Logs and Alerts (SysmonLog) service on the local computer.</span></span>

### <span data-ttu-id="e84b9-116">示例2：使用显示名称停止服务</span><span class="sxs-lookup"><span data-stu-id="e84b9-116">Example 2: Stop a service by using the display name</span></span>

```
PS C:\> Get-Service -DisplayName "telnet" | Stop-Service
```

<span data-ttu-id="e84b9-117">此命令停止本地计算机上的 Telnet 服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-117">This command stops the Telnet service on the local computer.</span></span>
<span data-ttu-id="e84b9-118">该命令使用 **Get 服务** 来获取表示 Telnet 服务的对象。</span><span class="sxs-lookup"><span data-stu-id="e84b9-118">The command uses **Get-Service** to get an object that represents the Telnet service.</span></span>
<span data-ttu-id="e84b9-119">管道运算符 (|) 管道对象 **停止服务** ，停止服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-119">The pipeline operator (|) pipes the object to **Stop-Service** , which stops the service.</span></span>

### <span data-ttu-id="e84b9-120">示例3：停止具有依赖服务的服务</span><span class="sxs-lookup"><span data-stu-id="e84b9-120">Example 3: Stop a service that has dependent services</span></span>

```
PS C:\> Get-Service -Name "iisadmin" | Format-List -Property Name, DependentServices
PS C:\> Stop-Service -Name "iisadmin" -Force -Confirm
```

<span data-ttu-id="e84b9-121">此示例在本地计算机上停止 IISAdmin 服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-121">This example stops the IISAdmin service on the local computer.</span></span>
<span data-ttu-id="e84b9-122">由于停止此服务还会停止依赖于 IISAdmin 服务的服务，因此最好是在 **停止服务** 之前，使用列出依赖于 IISAdmin 服务的服务的命令。</span><span class="sxs-lookup"><span data-stu-id="e84b9-122">Because stopping this service also stops the services that depend on the IISAdmin service, it is best to precede **Stop-Service** with a command that lists the services that depend on the IISAdmin service.</span></span>

<span data-ttu-id="e84b9-123">第一个命令列出依赖于 IISAdmin 的服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-123">The first command lists the services that depend on IISAdmin.</span></span>
<span data-ttu-id="e84b9-124">它使用 **Get 服务** 获取表示 IISAdmin 服务的对象。</span><span class="sxs-lookup"><span data-stu-id="e84b9-124">It uses **Get-Service** to get an object that represents the IISAdmin service.</span></span>
<span data-ttu-id="e84b9-125">管道运算符 (|) 将结果传递给 Format-List cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e84b9-125">The pipeline operator (|) passes the result to the Format-List cmdlet.</span></span>
<span data-ttu-id="e84b9-126">该命令使用 **Format-list** 的 *Property* 参数来仅列出该服务的 **Name** 和 **DependentServices** 属性。</span><span class="sxs-lookup"><span data-stu-id="e84b9-126">The command uses the *Property* parameter of **Format-List** to list only the **Name** and **DependentServices** properties of the service.</span></span>

<span data-ttu-id="e84b9-127">第二个命令停止 IISAdmin 服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-127">The second command stops the IISAdmin service.</span></span>
<span data-ttu-id="e84b9-128">需要使用 *Force* 参数来停止具有依赖服务的服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-128">The *Force* parameter is required to stop a service that has dependent services.</span></span>
<span data-ttu-id="e84b9-129">该命令使用 *Confirm* 参数在停止每个服务之前请求用户确认。</span><span class="sxs-lookup"><span data-stu-id="e84b9-129">The command uses the *Confirm* parameter to request confirmation from the user before it stops each service.</span></span>

## <span data-ttu-id="e84b9-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e84b9-130">PARAMETERS</span></span>

### <span data-ttu-id="e84b9-131">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="e84b9-131">-DisplayName</span></span>

<span data-ttu-id="e84b9-132">指定要停止的服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e84b9-132">Specifies the display names of the services to stop.</span></span>
<span data-ttu-id="e84b9-133">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e84b9-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e84b9-134">-Exclude</span><span class="sxs-lookup"><span data-stu-id="e84b9-134">-Exclude</span></span>

<span data-ttu-id="e84b9-135">指定此 cmdlet 省略的服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-135">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="e84b9-136">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="e84b9-136">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="e84b9-137">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="e84b9-137">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="e84b9-138">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e84b9-138">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e84b9-139">-Force</span><span class="sxs-lookup"><span data-stu-id="e84b9-139">-Force</span></span>

<span data-ttu-id="e84b9-140">强制 cmdlet 停止服务（即使该服务有依赖服务）。</span><span class="sxs-lookup"><span data-stu-id="e84b9-140">Forces the cmdlet to stop a service even if that service has dependent services.</span></span>

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

### <span data-ttu-id="e84b9-141">-Include</span><span class="sxs-lookup"><span data-stu-id="e84b9-141">-Include</span></span>

<span data-ttu-id="e84b9-142">指定此 cmdlet 停止的服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-142">Specifies services that this cmdlet stops.</span></span>
<span data-ttu-id="e84b9-143">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="e84b9-143">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="e84b9-144">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="e84b9-144">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="e84b9-145">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e84b9-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e84b9-146">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e84b9-146">-InputObject</span></span>

<span data-ttu-id="e84b9-147">指定表示要停止的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="e84b9-147">Specifies **ServiceController** objects that represent the services to stop.</span></span>
<span data-ttu-id="e84b9-148">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="e84b9-148">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="e84b9-149">-Name</span><span class="sxs-lookup"><span data-stu-id="e84b9-149">-Name</span></span>

<span data-ttu-id="e84b9-150">指定要停止的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="e84b9-150">Specifies the service names of the services to stop.</span></span>
<span data-ttu-id="e84b9-151">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="e84b9-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="e84b9-152">-NoWait</span><span class="sxs-lookup"><span data-stu-id="e84b9-152">-NoWait</span></span>

<span data-ttu-id="e84b9-153">指示此 cmdlet 使用 "无等待" 选项。</span><span class="sxs-lookup"><span data-stu-id="e84b9-153">Indicates that this cmdlet uses the no wait option.</span></span>

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

### <span data-ttu-id="e84b9-154">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e84b9-154">-PassThru</span></span>

<span data-ttu-id="e84b9-155">返回一个表示服务的对象。</span><span class="sxs-lookup"><span data-stu-id="e84b9-155">Returns an object that represents the service.</span></span>
<span data-ttu-id="e84b9-156">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="e84b9-156">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="e84b9-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e84b9-157">-Confirm</span></span>

<span data-ttu-id="e84b9-158">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e84b9-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e84b9-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e84b9-159">-WhatIf</span></span>

<span data-ttu-id="e84b9-160">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e84b9-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e84b9-161">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e84b9-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e84b9-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e84b9-162">CommonParameters</span></span>

<span data-ttu-id="e84b9-163">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e84b9-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e84b9-164">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e84b9-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e84b9-165">输入</span><span class="sxs-lookup"><span data-stu-id="e84b9-165">INPUTS</span></span>

### <span data-ttu-id="e84b9-166">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="e84b9-166">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="e84b9-167">可以通过管道将服务对象或包含服务名称的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e84b9-167">You can pipe a service object or a string that contains the name of a service to this cmdlet.</span></span>

## <span data-ttu-id="e84b9-168">输出</span><span class="sxs-lookup"><span data-stu-id="e84b9-168">OUTPUTS</span></span>

### <span data-ttu-id="e84b9-169">无、System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="e84b9-169">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="e84b9-170">如果使用 *PassThru* 参数，则此 cmdlet 将生成表示服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="e84b9-170">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you use the *PassThru* parameter.</span></span>
<span data-ttu-id="e84b9-171">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="e84b9-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e84b9-172">注释</span><span class="sxs-lookup"><span data-stu-id="e84b9-172">NOTES</span></span>

* <span data-ttu-id="e84b9-173">还可以通过其内置别名 **spsv** 来引用 **Stop 服务** 。</span><span class="sxs-lookup"><span data-stu-id="e84b9-173">You can also refer to **Stop-Service** by its built-in alias, **spsv** .</span></span> <span data-ttu-id="e84b9-174">有关详细信息，请参阅 about_Aliases。</span><span class="sxs-lookup"><span data-stu-id="e84b9-174">For more information, see about_Aliases.</span></span>

  <span data-ttu-id="e84b9-175">**停止-** 仅当当前用户有权执行此操作时，服务才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="e84b9-175">**Stop-Service** can control services only when the current user has permission to do this.</span></span>
<span data-ttu-id="e84b9-176">如果某个命令不能正常工作，则可能你不具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="e84b9-176">If a command does not work correctly, you might not have the required permissions.</span></span>

  <span data-ttu-id="e84b9-177">若要查找服务名称并显示系统中的服务名称，请键入 `Get-Service`。</span><span class="sxs-lookup"><span data-stu-id="e84b9-177">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
<span data-ttu-id="e84b9-178">服务名称显示在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="e84b9-178">The service names appear in the **Name** column and the display names appear in the **DisplayName** column.</span></span>


## <span data-ttu-id="e84b9-179">相关链接</span><span class="sxs-lookup"><span data-stu-id="e84b9-179">RELATED LINKS</span></span>

[<span data-ttu-id="e84b9-180">Get-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-180">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="e84b9-181">New-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-181">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="e84b9-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="e84b9-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="e84b9-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="e84b9-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="e84b9-186">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-186">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="e84b9-187">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="e84b9-187">Remove-Service</span></span>](Remove-Service.md)
