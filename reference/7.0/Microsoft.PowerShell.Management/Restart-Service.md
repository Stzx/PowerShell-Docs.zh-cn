---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: 06db89e107e7589dcdd4439fff54e04676adcc1c
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342886"
---
# <span data-ttu-id="ed03f-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-103">Restart-Service</span></span>

## <span data-ttu-id="ed03f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ed03f-104">SYNOPSIS</span></span>
<span data-ttu-id="ed03f-105">停止并接着启动一个或更多服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="ed03f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ed03f-106">SYNTAX</span></span>

### <span data-ttu-id="ed03f-107">InputObject（默认值）</span><span class="sxs-lookup"><span data-stu-id="ed03f-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed03f-108">默认</span><span class="sxs-lookup"><span data-stu-id="ed03f-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ed03f-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed03f-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ed03f-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ed03f-110">DESCRIPTION</span></span>

<span data-ttu-id="ed03f-111">`Restart-Service`Cmdlet 向 Windows 服务控制器发送一条停止消息，然后将一条消息发送到指定的服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-111">The `Restart-Service` cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span> <span data-ttu-id="ed03f-112">如果一项服务已经停止，则它将启动而不通知你已发生了错误。</span><span class="sxs-lookup"><span data-stu-id="ed03f-112">If a service was already stopped, it is started without notifying you of an error.</span></span> <span data-ttu-id="ed03f-113">可以通过服务名称或显示名称来指定服务，也可以使用 **InputObject** 参数传递一个对象，该对象表示要重新启动的每个服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="ed03f-114">示例</span><span class="sxs-lookup"><span data-stu-id="ed03f-114">EXAMPLES</span></span>

### <span data-ttu-id="ed03f-115">示例1：在本地计算机上重新启动服务</span><span class="sxs-lookup"><span data-stu-id="ed03f-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="ed03f-116">此命令在本地计算机上重新启动 Windows Management Instrumentation 服务 (WinMgmt)。</span><span class="sxs-lookup"><span data-stu-id="ed03f-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="ed03f-117">示例2：排除服务</span><span class="sxs-lookup"><span data-stu-id="ed03f-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="ed03f-118">此命令重新启动显示名称以 "Net" 开头的服务，"Net Logon" 服务除外。</span><span class="sxs-lookup"><span data-stu-id="ed03f-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="ed03f-119">示例3：启动所有停止的网络服务</span><span class="sxs-lookup"><span data-stu-id="ed03f-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="ed03f-120">此命令启动计算机上所有停止的网络服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="ed03f-121">此命令使用 `Get-Service` cmdlet 来获取对象，这些对象表示服务名称以 "net" 开头的服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-121">This command uses the `Get-Service` cmdlet to get objects that represent the services whose service name starts with net.</span></span> <span data-ttu-id="ed03f-122">管道运算符 (`|`) 将服务对象发送给 `Where-Object` cmdlet，后者仅选择状态为 "已停止" 的服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-122">The pipeline operator (`|`) sends the services object to the `Where-Object` cmdlet, which selects only the services that have a status of stopped.</span></span> <span data-ttu-id="ed03f-123">另一个管道运算符将选定的服务发送到 `Restart-Service` 。</span><span class="sxs-lookup"><span data-stu-id="ed03f-123">Another pipeline operator sends the selected services to `Restart-Service`.</span></span>

<span data-ttu-id="ed03f-124">在实际操作中，你将使用 **WhatIf** 参数来确定该命令的影响，然后再运行该命令。</span><span class="sxs-lookup"><span data-stu-id="ed03f-124">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="ed03f-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ed03f-125">PARAMETERS</span></span>

### <span data-ttu-id="ed03f-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed03f-126">-DisplayName</span></span>

<span data-ttu-id="ed03f-127">指定要重新启动的服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ed03f-127">Specifies the display names of services to restarted.</span></span> <span data-ttu-id="ed03f-128">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ed03f-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ed03f-129">-Exclude</span><span class="sxs-lookup"><span data-stu-id="ed03f-129">-Exclude</span></span>

<span data-ttu-id="ed03f-130">指定此 cmdlet 省略的服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-130">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="ed03f-131">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ed03f-131">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ed03f-132">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="ed03f-132">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="ed03f-133">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ed03f-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ed03f-134">-Force</span><span class="sxs-lookup"><span data-stu-id="ed03f-134">-Force</span></span>

<span data-ttu-id="ed03f-135">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="ed03f-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="ed03f-136">-Include</span><span class="sxs-lookup"><span data-stu-id="ed03f-136">-Include</span></span>

<span data-ttu-id="ed03f-137">指定此 cmdlet 重新启动的服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-137">Specifies services that this cmdlet restarts.</span></span> <span data-ttu-id="ed03f-138">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="ed03f-138">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="ed03f-139">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="ed03f-139">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="ed03f-140">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="ed03f-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="ed03f-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ed03f-141">-InputObject</span></span>

<span data-ttu-id="ed03f-142">指定表示要重新启动的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="ed03f-142">Specifies **ServiceController** objects that represent the services to restart.</span></span> <span data-ttu-id="ed03f-143">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="ed03f-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="ed03f-144">-Name</span><span class="sxs-lookup"><span data-stu-id="ed03f-144">-Name</span></span>

<span data-ttu-id="ed03f-145">指定要重新启动的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="ed03f-145">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="ed03f-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="ed03f-146">-PassThru</span></span>

<span data-ttu-id="ed03f-147">返回一个表示服务的对象。</span><span class="sxs-lookup"><span data-stu-id="ed03f-147">Returns an object that represents the service.</span></span> <span data-ttu-id="ed03f-148">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="ed03f-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="ed03f-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ed03f-149">-Confirm</span></span>

<span data-ttu-id="ed03f-150">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="ed03f-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ed03f-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ed03f-151">-WhatIf</span></span>

<span data-ttu-id="ed03f-152">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ed03f-152">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="ed03f-153">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="ed03f-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ed03f-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ed03f-154">CommonParameters</span></span>

<span data-ttu-id="ed03f-155">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ed03f-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ed03f-156">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ed03f-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ed03f-157">输入</span><span class="sxs-lookup"><span data-stu-id="ed03f-157">INPUTS</span></span>

### <span data-ttu-id="ed03f-158">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="ed03f-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="ed03f-159">可以通过管道将服务对象或包含服务名称的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ed03f-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="ed03f-160">输出</span><span class="sxs-lookup"><span data-stu-id="ed03f-160">OUTPUTS</span></span>

### <span data-ttu-id="ed03f-161">无、System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="ed03f-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="ed03f-162">如果指定 **PassThru** 参数，则此 cmdlet 将生成表示重新启动的服务的 **system.serviceprocess. ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="ed03f-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="ed03f-163">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="ed03f-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ed03f-164">注释</span><span class="sxs-lookup"><span data-stu-id="ed03f-164">NOTES</span></span>

<span data-ttu-id="ed03f-165">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="ed03f-165">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="ed03f-166">`Restart-Service` 仅当当前用户有权执行此操作时，才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="ed03f-166">`Restart-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="ed03f-167">如果某个命令不能正常工作，则可能你不具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ed03f-167">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="ed03f-168">若要在系统中查找服务名称并显示服务名称，请键入 `Get-Service` ""。</span><span class="sxs-lookup"><span data-stu-id="ed03f-168">To find the service names and display names of the services on your system, type `Get-Service`".</span></span>
  <span data-ttu-id="ed03f-169">服务名称显示在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="ed03f-169">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="ed03f-170">相关链接</span><span class="sxs-lookup"><span data-stu-id="ed03f-170">RELATED LINKS</span></span>

[<span data-ttu-id="ed03f-171">Get-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-171">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="ed03f-172">New-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-172">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="ed03f-173">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-173">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="ed03f-174">Set-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-174">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="ed03f-175">Start-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-175">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="ed03f-176">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-176">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="ed03f-177">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-177">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="ed03f-178">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="ed03f-178">Remove-Service</span></span>](Remove-Service.md)
