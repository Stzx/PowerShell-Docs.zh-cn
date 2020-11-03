---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/suspend-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Service
ms.openlocfilehash: 8455592f6b919da04603470262c134593f74877c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197476"
---
# <span data-ttu-id="4facf-103">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-103">Suspend-Service</span></span>

## <span data-ttu-id="4facf-104">摘要</span><span class="sxs-lookup"><span data-stu-id="4facf-104">SYNOPSIS</span></span>
<span data-ttu-id="4facf-105">挂起（暂停）一个或多个正在运行的服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-105">Suspends (pauses) one or more running services.</span></span>

## <span data-ttu-id="4facf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4facf-106">SYNTAX</span></span>

### <span data-ttu-id="4facf-107">InputObject（默认值）</span><span class="sxs-lookup"><span data-stu-id="4facf-107">InputObject (Default)</span></span>

```
Suspend-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4facf-108">默认</span><span class="sxs-lookup"><span data-stu-id="4facf-108">Default</span></span>

```
Suspend-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="4facf-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4facf-109">DisplayName</span></span>

```
Suspend-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4facf-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4facf-110">DESCRIPTION</span></span>

<span data-ttu-id="4facf-111">对于每个指定的服务， **挂服务** Cmdlet 向 Windows 服务控制器发送一条挂起消息。</span><span class="sxs-lookup"><span data-stu-id="4facf-111">The **Suspend-Service** cmdlet sends a suspend message to the Windows Service Controller for each of the specified services.</span></span>
<span data-ttu-id="4facf-112">挂起时，服务仍在运行，但其操作将停止，直到恢复，如使用 Resume-Service cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4facf-112">While suspended, the service is still running, but its action is stopped until resumed, such as by usingthe Resume-Service cmdlet.</span></span>
<span data-ttu-id="4facf-113">可以通过服务名称或显示名称来指定服务，也可以使用 *InputObject* 参数传递一个服务对象来表示要挂起的服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass a service object that represents the services that you want to suspend.</span></span>

## <span data-ttu-id="4facf-114">示例</span><span class="sxs-lookup"><span data-stu-id="4facf-114">EXAMPLES</span></span>

### <span data-ttu-id="4facf-115">示例1：挂起服务</span><span class="sxs-lookup"><span data-stu-id="4facf-115">Example 1: Suspend a service</span></span>

```
PS C:\> Suspend-Service -DisplayName "Telnet"
```

<span data-ttu-id="4facf-116">此命令挂起本地计算机上的 Telnet 服务 (Tlntsvr)。</span><span class="sxs-lookup"><span data-stu-id="4facf-116">This command suspends the Telnet service (Tlntsvr) service on the local computer.</span></span>

### <span data-ttu-id="4facf-117">示例2：显示挂起服务后会发生的情况</span><span class="sxs-lookup"><span data-stu-id="4facf-117">Example 2: Display what would happen if you suspend services</span></span>

```
PS C:\> Suspend-Service -Name lanman* -WhatIf
```

<span data-ttu-id="4facf-118">此命令会告诉你挂起服务名称以 lanman 开头的服务后会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="4facf-118">This command tells what would happen if you suspended the services that have a service name that starts with lanman.</span></span>
<span data-ttu-id="4facf-119">若要挂起服务，请在不带 *WhatIf* 参数的情况下重新运行该命令。</span><span class="sxs-lookup"><span data-stu-id="4facf-119">To suspend the services, rerun the command without the *WhatIf* parameter.</span></span>

### <span data-ttu-id="4facf-120">示例3：获取和暂停服务</span><span class="sxs-lookup"><span data-stu-id="4facf-120">Example 3: Get and suspend a service</span></span>

```
PS C:\> Get-Service schedule | Suspend-Service
```

<span data-ttu-id="4facf-121">此命令使用 **get-help** cmdlet 来获取一个对象，该对象表示计算机上的任务计划程序 (计划) 服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-121">This command uses the **Get-Service** cmdlet to get an object that represents the Task Scheduler (Schedule) service on the computer.</span></span>
<span data-ttu-id="4facf-122">管道运算符 (|) 将结果传递给 **挂起** 服务，这会挂起服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-122">The pipeline operator (|) passes the result to **Suspend-Service** , which suspends the service.</span></span>

### <span data-ttu-id="4facf-123">示例4：挂起所有可挂起的服务</span><span class="sxs-lookup"><span data-stu-id="4facf-123">Example 4: Suspend all services that can be suspended</span></span>

```
PS C:\> Get-Service | Where-Object {$_.CanPauseAndContinue -eq "True"} | Suspend-Service -Confirm
```

<span data-ttu-id="4facf-124">此命令挂起计算机上所有可挂起的服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-124">This command suspends all of the services on the computer that can be suspended.</span></span>
<span data-ttu-id="4facf-125">它使用 **Get 服务** 获取代表计算机上的服务的对象。</span><span class="sxs-lookup"><span data-stu-id="4facf-125">It uses **Get-Service** to get objects that represent the services on the computer.</span></span>
<span data-ttu-id="4facf-126">管道运算符将结果传递给 Where-Object cmdlet，该 cmdlet 只选择 **CanPauseAndContinue** 属性值为 $True 的服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-126">The pipeline operator passes the results to the Where-Object cmdlet, which selects only the services that have a value of $True for the **CanPauseAndContinue** property.</span></span>
<span data-ttu-id="4facf-127">另一个管道运算符将结果传递给 **挂起的服务** 。</span><span class="sxs-lookup"><span data-stu-id="4facf-127">Another pipeline operator passes the results to **Suspend-Service** .</span></span>
<span data-ttu-id="4facf-128">*Confirm* 参数会提示您进行确认，然后再挂起每个服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-128">The *Confirm* parameter prompts you for confirmation before suspending each of the services.</span></span>

## <span data-ttu-id="4facf-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4facf-129">PARAMETERS</span></span>

### <span data-ttu-id="4facf-130">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="4facf-130">-DisplayName</span></span>

<span data-ttu-id="4facf-131">指定要挂起的服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4facf-131">Specifies the display names of the services to be suspended.</span></span>
<span data-ttu-id="4facf-132">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="4facf-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4facf-133">-Exclude</span><span class="sxs-lookup"><span data-stu-id="4facf-133">-Exclude</span></span>

<span data-ttu-id="4facf-134">指定要从指定服务中省略的服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-134">Specifies services to omit from the specified services.</span></span>
<span data-ttu-id="4facf-135">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="4facf-135">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="4facf-136">请输入名称元素或模式，例如“s\*”。</span><span class="sxs-lookup"><span data-stu-id="4facf-136">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="4facf-137">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="4facf-137">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4facf-138">-Include</span><span class="sxs-lookup"><span data-stu-id="4facf-138">-Include</span></span>

<span data-ttu-id="4facf-139">指定要挂起的服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-139">Specifies services to suspend.</span></span>
<span data-ttu-id="4facf-140">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="4facf-140">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="4facf-141">请输入名称元素或模式，例如“s\*”。</span><span class="sxs-lookup"><span data-stu-id="4facf-141">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="4facf-142">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="4facf-142">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="4facf-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4facf-143">-InputObject</span></span>

<span data-ttu-id="4facf-144">指定表示要挂起的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="4facf-144">Specifies **ServiceController** objects that represent the services to suspend.</span></span>
<span data-ttu-id="4facf-145">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="4facf-145">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="4facf-146">-Name</span><span class="sxs-lookup"><span data-stu-id="4facf-146">-Name</span></span>

<span data-ttu-id="4facf-147">指定要挂起的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="4facf-147">Specifies the service names of the services to suspend.</span></span>
<span data-ttu-id="4facf-148">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="4facf-148">Wildcard characters are permitted.</span></span>

<span data-ttu-id="4facf-149">参数名为可选项。</span><span class="sxs-lookup"><span data-stu-id="4facf-149">The parameter name is optional.</span></span>
<span data-ttu-id="4facf-150">您可以使用 *Name* 或其 *别名，也* 可以省略参数名称。</span><span class="sxs-lookup"><span data-stu-id="4facf-150">You can use *Name* or its alias, *ServiceName* , or you can omit the parameter name.</span></span>

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

### <span data-ttu-id="4facf-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="4facf-151">-PassThru</span></span>

<span data-ttu-id="4facf-152">返回一个代表你所处理的项目的对象。</span><span class="sxs-lookup"><span data-stu-id="4facf-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="4facf-153">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="4facf-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="4facf-154">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4facf-154">-Confirm</span></span>

<span data-ttu-id="4facf-155">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="4facf-155">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4facf-156">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4facf-156">-WhatIf</span></span>

<span data-ttu-id="4facf-157">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="4facf-157">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4facf-158">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="4facf-158">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4facf-159">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4facf-159">CommonParameters</span></span>

<span data-ttu-id="4facf-160">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="4facf-160">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4facf-161">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="4facf-161">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4facf-162">输入</span><span class="sxs-lookup"><span data-stu-id="4facf-162">INPUTS</span></span>

### <span data-ttu-id="4facf-163">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="4facf-163">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="4facf-164">可以通过管道将服务对象或包含服务名称的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4facf-164">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="4facf-165">输出</span><span class="sxs-lookup"><span data-stu-id="4facf-165">OUTPUTS</span></span>

### <span data-ttu-id="4facf-166">无、System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="4facf-166">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="4facf-167">如果指定 *PassThru* 参数，则此 cmdlet 将生成表示该服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="4facf-167">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="4facf-168">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="4facf-168">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4facf-169">注释</span><span class="sxs-lookup"><span data-stu-id="4facf-169">NOTES</span></span>

* <span data-ttu-id="4facf-170">**挂起-** 只有在当前用户有权执行此操作的情况下，服务才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-170">**Suspend-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="4facf-171">如果某个命令不能正常工作，则可能你不具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="4facf-171">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="4facf-172">**挂起-服务** 只能挂起支持被挂起和恢复的服务。</span><span class="sxs-lookup"><span data-stu-id="4facf-172">**Suspend-Service** can suspend only services that support being suspended and resumed.</span></span> <span data-ttu-id="4facf-173">若要确定是否可以挂起特定服务，请将 Get-Service cmdlet 与 **CanPauseAndContinue** 属性一起使用。</span><span class="sxs-lookup"><span data-stu-id="4facf-173">To determine whether a particular service can be suspended, use the Get-Service cmdlet together with the **CanPauseAndContinue** property.</span></span> <span data-ttu-id="4facf-174">例如，`Get-Service wmi | Format-List Name, CanPauseAndContinue`。</span><span class="sxs-lookup"><span data-stu-id="4facf-174">For example, `Get-Service wmi | Format-List Name, CanPauseAndContinue`.</span></span> <span data-ttu-id="4facf-175">若要查找计算机上可以挂起的所有服务，请键入 `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}` 。</span><span class="sxs-lookup"><span data-stu-id="4facf-175">To find all services on the computer that can be suspended, type `Get-Service | Where-Object {$_.CanPauseAndContinue -eq $true}`.</span></span>
* <span data-ttu-id="4facf-176">若要在系统中查找服务名称并显示服务名称，请键入 **get-help** 。</span><span class="sxs-lookup"><span data-stu-id="4facf-176">To find the service names and display names of the services on your system, type **Get-Service** .</span></span> <span data-ttu-id="4facf-177">服务名称显示在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="4facf-177">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="4facf-178">相关链接</span><span class="sxs-lookup"><span data-stu-id="4facf-178">RELATED LINKS</span></span>

[<span data-ttu-id="4facf-179">Get-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-179">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="4facf-180">New-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-180">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="4facf-181">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-181">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="4facf-182">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-182">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="4facf-183">Set-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-183">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="4facf-184">Start-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-184">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="4facf-185">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-185">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="4facf-186">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="4facf-186">Remove-Service</span></span>](Remove-Service.md)

