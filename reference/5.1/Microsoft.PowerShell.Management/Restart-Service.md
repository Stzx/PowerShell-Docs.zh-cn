---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: b5af4f55166993e54048dd76bb8345550718c170
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198050"
---
# <span data-ttu-id="760cd-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-103">Restart-Service</span></span>

## <span data-ttu-id="760cd-104">摘要</span><span class="sxs-lookup"><span data-stu-id="760cd-104">SYNOPSIS</span></span>
<span data-ttu-id="760cd-105">停止并接着启动一个或更多服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="760cd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="760cd-106">SYNTAX</span></span>

### <span data-ttu-id="760cd-107">InputObject（默认值）</span><span class="sxs-lookup"><span data-stu-id="760cd-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="760cd-108">默认</span><span class="sxs-lookup"><span data-stu-id="760cd-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="760cd-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="760cd-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="760cd-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="760cd-110">DESCRIPTION</span></span>

<span data-ttu-id="760cd-111">**重新启动服务** Cmdlet 向 Windows 服务控制器发送一条停止消息，然后将一条消息发送到指定的服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-111">The **Restart-Service** cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span>
<span data-ttu-id="760cd-112">如果一项服务已经停止，则它将启动而不通知你已发生了错误。</span><span class="sxs-lookup"><span data-stu-id="760cd-112">If a service was already stopped, it is started without notifying you of an error.</span></span>
<span data-ttu-id="760cd-113">可以通过服务名称或显示名称来指定服务，也可以使用 *InputObject* 参数传递一个对象，该对象表示要重新启动的每个服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-113">You can specify the services by their service names or display names, or you can use the *InputObject* parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="760cd-114">示例</span><span class="sxs-lookup"><span data-stu-id="760cd-114">EXAMPLES</span></span>

### <span data-ttu-id="760cd-115">示例1：在本地计算机上重新启动服务</span><span class="sxs-lookup"><span data-stu-id="760cd-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="760cd-116">此命令在本地计算机上重新启动 Windows Management Instrumentation 服务 (WinMgmt)。</span><span class="sxs-lookup"><span data-stu-id="760cd-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="760cd-117">示例2：排除服务</span><span class="sxs-lookup"><span data-stu-id="760cd-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="760cd-118">此命令重新启动显示名称以 "Net" 开头的服务，"Net Logon" 服务除外。</span><span class="sxs-lookup"><span data-stu-id="760cd-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="760cd-119">示例3：启动所有停止的网络服务</span><span class="sxs-lookup"><span data-stu-id="760cd-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="760cd-120">此命令启动计算机上所有停止的网络服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="760cd-121">此命令使用 Get-Service cmdlet 获取表示服务名称以 net 开头的服务的对象。</span><span class="sxs-lookup"><span data-stu-id="760cd-121">This command uses the Get-Service cmdlet to get objects that represent the services whose service name starts with net.</span></span>
<span data-ttu-id="760cd-122">管道运算符 (|) 将 services 对象发送到 Where-Object cmdlet，该 cmdlet 只选择状态为 "已停止" 的服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-122">The pipeline operator (|) sends the services object to the Where-Object cmdlet, which selects only the services that have a status of stopped.</span></span>
<span data-ttu-id="760cd-123">另一个管道运算符将选定的服务发送到 **Restart** 。</span><span class="sxs-lookup"><span data-stu-id="760cd-123">Another pipeline operator sends the selected services to **Restart-Service** .</span></span>

<span data-ttu-id="760cd-124">在实际操作中，你将使用 *WhatIf* 参数来确定该命令的影响，然后再运行该命令。</span><span class="sxs-lookup"><span data-stu-id="760cd-124">In practice, you would use the *WhatIf* parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="760cd-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="760cd-125">PARAMETERS</span></span>

### <span data-ttu-id="760cd-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="760cd-126">-DisplayName</span></span>

<span data-ttu-id="760cd-127">指定要重新启动的服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="760cd-127">Specifies the display names of services to restarted.</span></span>
<span data-ttu-id="760cd-128">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="760cd-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="760cd-129">-Exclude</span><span class="sxs-lookup"><span data-stu-id="760cd-129">-Exclude</span></span>

<span data-ttu-id="760cd-130">指定此 cmdlet 省略的服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-130">Specifies services that this cmdlet omits.</span></span>
<span data-ttu-id="760cd-131">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="760cd-131">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="760cd-132">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="760cd-132">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="760cd-133">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="760cd-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="760cd-134">-Force</span><span class="sxs-lookup"><span data-stu-id="760cd-134">-Force</span></span>

<span data-ttu-id="760cd-135">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="760cd-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="760cd-136">-Include</span><span class="sxs-lookup"><span data-stu-id="760cd-136">-Include</span></span>

<span data-ttu-id="760cd-137">指定此 cmdlet 重新启动的服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-137">Specifies services that this cmdlet restarts.</span></span>
<span data-ttu-id="760cd-138">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="760cd-138">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="760cd-139">输入名称元素或模式，例如 "s \*"。</span><span class="sxs-lookup"><span data-stu-id="760cd-139">Enter a name element or pattern, such as s\*.</span></span>
<span data-ttu-id="760cd-140">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="760cd-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="760cd-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="760cd-141">-InputObject</span></span>

<span data-ttu-id="760cd-142">指定表示要重新启动的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="760cd-142">Specifies **ServiceController** objects that represent the services to restart.</span></span>
<span data-ttu-id="760cd-143">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="760cd-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="760cd-144">-Name</span><span class="sxs-lookup"><span data-stu-id="760cd-144">-Name</span></span>

<span data-ttu-id="760cd-145">指定要重新启动的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="760cd-145">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="760cd-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="760cd-146">-PassThru</span></span>

<span data-ttu-id="760cd-147">返回一个表示服务的对象。</span><span class="sxs-lookup"><span data-stu-id="760cd-147">Returns an object that represents the service.</span></span>
<span data-ttu-id="760cd-148">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="760cd-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="760cd-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="760cd-149">-Confirm</span></span>

<span data-ttu-id="760cd-150">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="760cd-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="760cd-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="760cd-151">-WhatIf</span></span>

<span data-ttu-id="760cd-152">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="760cd-152">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="760cd-153">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="760cd-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="760cd-154">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="760cd-154">CommonParameters</span></span>

<span data-ttu-id="760cd-155">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="760cd-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="760cd-156">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="760cd-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="760cd-157">输入</span><span class="sxs-lookup"><span data-stu-id="760cd-157">INPUTS</span></span>

### <span data-ttu-id="760cd-158">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="760cd-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="760cd-159">可以通过管道将服务对象或包含服务名称的字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="760cd-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="760cd-160">输出</span><span class="sxs-lookup"><span data-stu-id="760cd-160">OUTPUTS</span></span>

### <span data-ttu-id="760cd-161">无、System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="760cd-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="760cd-162">如果指定 *PassThru* 参数，则此 cmdlet 将生成表示重新启动的服务的 **system.serviceprocess. ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="760cd-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="760cd-163">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="760cd-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="760cd-164">注释</span><span class="sxs-lookup"><span data-stu-id="760cd-164">NOTES</span></span>

* <span data-ttu-id="760cd-165">**重新启动-** 仅当当前用户有权执行此操作时，服务才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="760cd-165">**Restart-Service** can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="760cd-166">如果某个命令不能正常工作，则可能你不具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="760cd-166">If a command does not work correctly, you might not have the required permissions.</span></span>
* <span data-ttu-id="760cd-167">若要在系统中查找服务名称并显示服务名称，请键入 " **获取服务** "。</span><span class="sxs-lookup"><span data-stu-id="760cd-167">To find the service names and display names of the services on your system, type **Get-Service** ".</span></span> <span data-ttu-id="760cd-168">服务名称显示在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="760cd-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="760cd-169">相关链接</span><span class="sxs-lookup"><span data-stu-id="760cd-169">RELATED LINKS</span></span>

[<span data-ttu-id="760cd-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="760cd-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="760cd-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="760cd-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="760cd-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="760cd-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="760cd-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="760cd-176">Suspend-Service</span></span>](Suspend-Service.md)
