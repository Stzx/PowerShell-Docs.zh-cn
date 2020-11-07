---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: a79bcdaa60c420c4436276749c1b4d298158f8a6
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343005"
---
# <span data-ttu-id="c98c9-103">Start-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-103">Start-Service</span></span>

## <span data-ttu-id="c98c9-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c98c9-104">SYNOPSIS</span></span>
<span data-ttu-id="c98c9-105">启动一个或多个已停止的服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-105">Starts one or more stopped services.</span></span>

## <span data-ttu-id="c98c9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c98c9-106">SYNTAX</span></span>

### <span data-ttu-id="c98c9-107">InputObject（默认值）</span><span class="sxs-lookup"><span data-stu-id="c98c9-107">InputObject (Default)</span></span>

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c98c9-108">默认</span><span class="sxs-lookup"><span data-stu-id="c98c9-108">Default</span></span>

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="c98c9-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c98c9-109">DisplayName</span></span>

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c98c9-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c98c9-110">DESCRIPTION</span></span>

<span data-ttu-id="c98c9-111">`Start-Service`Cmdlet 为每个指定的服务向 Windows 服务控制器发送一条启动消息。</span><span class="sxs-lookup"><span data-stu-id="c98c9-111">The `Start-Service` cmdlet sends a start message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="c98c9-112">如果服务已在运行，则无错误忽略该消息。</span><span class="sxs-lookup"><span data-stu-id="c98c9-112">If a service is already running, the message is ignored without error.</span></span> <span data-ttu-id="c98c9-113">可以通过服务名称或显示名称指定服务，也可使用 InputObject 参数提供一个服务对象，表示要启动的服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to supply a service object that represents the services that you want to start.</span></span>

## <span data-ttu-id="c98c9-114">示例</span><span class="sxs-lookup"><span data-stu-id="c98c9-114">EXAMPLES</span></span>

### <span data-ttu-id="c98c9-115">示例 1：通过使用服务名称启动服务</span><span class="sxs-lookup"><span data-stu-id="c98c9-115">Example 1: Start a service by using its name</span></span>

<span data-ttu-id="c98c9-116">此示例启动本地计算机上的 EventLog 服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-116">This example starts the EventLog service on the local computer.</span></span> <span data-ttu-id="c98c9-117">**Name** 参数通过服务名称来标识服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-117">The **Name** parameter identifies the service by its service name.</span></span>

```powershell
Start-Service -Name "eventlog"
```

### <span data-ttu-id="c98c9-118">示例 2：在不启动服务的情况下显示信息</span><span class="sxs-lookup"><span data-stu-id="c98c9-118">Example 2: Display information without starting a service</span></span>

<span data-ttu-id="c98c9-119">此示例显示了启动显示名称中包含 "remote" 的服务后会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="c98c9-119">This example shows what would occur if you started the services that have a display name that includes "remote".</span></span>

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

<span data-ttu-id="c98c9-120">**DisplayName** 参数通过显示名称而不是服务名称来标识服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-120">The **DisplayName** parameter identifies the services by their display name instead of their service name.</span></span> <span data-ttu-id="c98c9-121">**WhatIf** 参数会使 cmdlet 显示运行命令时所发生的情况，但不会发生更改。</span><span class="sxs-lookup"><span data-stu-id="c98c9-121">The **WhatIf** parameter causes the cmdlet to display what would happen when you run the command but does not make changes.</span></span>

### <span data-ttu-id="c98c9-122">示例 3：启动服务，并将操作记录到文本文件中</span><span class="sxs-lookup"><span data-stu-id="c98c9-122">Example 3: Start a service and record the action in a text file</span></span>

<span data-ttu-id="c98c9-123">此示例启动计算机上的 Windows Management Instrumentation (WMI) 服务，并将操作的记录添加到 services.txt 文件中。</span><span class="sxs-lookup"><span data-stu-id="c98c9-123">This example starts the Windows Management Instrumentation (WMI) service on the computer and adds a record of the action to the services.txt file.</span></span>

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

<span data-ttu-id="c98c9-124">首先，我们使用 `Get-Service` 来获取表示 WMI 服务的对象，并将其存储在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="c98c9-124">First we use `Get-Service` to get an object that represent the WMI service and store it in the `$s` variable.</span></span> <span data-ttu-id="c98c9-125">接下来，我们启动该服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-125">Next, we start the service.</span></span> <span data-ttu-id="c98c9-126">如果没有 **PassThru** 参数，则不 `Start-Service` 会创建任何输出。</span><span class="sxs-lookup"><span data-stu-id="c98c9-126">Without the **PassThru** parameter, `Start-Service` does not create any output.</span></span> <span data-ttu-id="c98c9-127">管道运算符 (|) 将对象输出传递 `Start-Service` 给 cmdlet， `Format-List` 以将对象的格式设置为其属性列表。</span><span class="sxs-lookup"><span data-stu-id="c98c9-127">The pipeline operator (|) passes the object output by `Start-Service` to the `Format-List` cmdlet to format the object as a list of its properties.</span></span> <span data-ttu-id="c98c9-128">追加重定向运算符 (将 \> \> 输出重定向到 services.txt 文件) 。</span><span class="sxs-lookup"><span data-stu-id="c98c9-128">The append redirection operator (\>\>) redirects the output to the services.txt file.</span></span> <span data-ttu-id="c98c9-129">将输出添加到现有文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="c98c9-129">The output is added to the end of the existing file.</span></span>

### <span data-ttu-id="c98c9-130">示例 4：启动禁用的服务</span><span class="sxs-lookup"><span data-stu-id="c98c9-130">Example 4: Start a disabled service</span></span>

<span data-ttu-id="c98c9-131">此示例演示如何在 **禁用** 服务的启动类型时启动服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-131">This example shows how to start a service when the start type of the service is **Disabled**.</span></span>

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

<span data-ttu-id="c98c9-132">第一次尝试启动 Telnet 服务 (tlntsvr) 失败。</span><span class="sxs-lookup"><span data-stu-id="c98c9-132">The first attempt to start the Telnet service (tlntsvr) fails.</span></span> <span data-ttu-id="c98c9-133">该 `Get-CimInstance` 命令显示 Tlntsvr 服务的 **StartMode** 属性已 **禁用** 。</span><span class="sxs-lookup"><span data-stu-id="c98c9-133">The `Get-CimInstance` command shows that the **StartMode** property of the Tlntsvr service is **Disabled**.</span></span> <span data-ttu-id="c98c9-134">`Set-Service`Cmdlet 将启动类型更改为 " **手动** "。</span><span class="sxs-lookup"><span data-stu-id="c98c9-134">The `Set-Service` cmdlet changes the start type to **Manual**.</span></span> <span data-ttu-id="c98c9-135">现在，我们可以重新提交 `Start-Service` 命令。</span><span class="sxs-lookup"><span data-stu-id="c98c9-135">Now, we can resubmit the `Start-Service` command.</span></span> <span data-ttu-id="c98c9-136">这次，该命令执行成功。</span><span class="sxs-lookup"><span data-stu-id="c98c9-136">This time, the command succeeds.</span></span> <span data-ttu-id="c98c9-137">若要验证命令是否成功，请运行 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="c98c9-137">To verify that the command succeeded, run `Get-Service`.</span></span>

## <span data-ttu-id="c98c9-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c98c9-138">PARAMETERS</span></span>

### <span data-ttu-id="c98c9-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="c98c9-139">-DisplayName</span></span>

<span data-ttu-id="c98c9-140">指定要启动的服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="c98c9-140">Specifies the display names of the services to start.</span></span> <span data-ttu-id="c98c9-141">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c98c9-141">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c98c9-142">-Exclude</span><span class="sxs-lookup"><span data-stu-id="c98c9-142">-Exclude</span></span>

<span data-ttu-id="c98c9-143">指定此 cmdlet 省略的服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-143">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="c98c9-144">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="c98c9-144">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="c98c9-145">输入名称元素或模式，例如 `s*` 。</span><span class="sxs-lookup"><span data-stu-id="c98c9-145">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="c98c9-146">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c98c9-146">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c98c9-147">-Include</span><span class="sxs-lookup"><span data-stu-id="c98c9-147">-Include</span></span>

<span data-ttu-id="c98c9-148">指定此 cmdlet 启动的服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-148">Specifies services that this cmdlet starts.</span></span> <span data-ttu-id="c98c9-149">此参数值使 **Name** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="c98c9-149">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="c98c9-150">输入名称元素或模式，例如 `s*` 。</span><span class="sxs-lookup"><span data-stu-id="c98c9-150">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="c98c9-151">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="c98c9-151">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="c98c9-152">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c98c9-152">-InputObject</span></span>

<span data-ttu-id="c98c9-153">指定表示要启动的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="c98c9-153">Specifies **ServiceController** objects representing the services to be started.</span></span> <span data-ttu-id="c98c9-154">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="c98c9-154">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="c98c9-155">-Name</span><span class="sxs-lookup"><span data-stu-id="c98c9-155">-Name</span></span>

<span data-ttu-id="c98c9-156">指定要启动的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="c98c9-156">Specifies the service names for the service to be started.</span></span>

<span data-ttu-id="c98c9-157">参数名为可选项。</span><span class="sxs-lookup"><span data-stu-id="c98c9-157">The parameter name is optional.</span></span> <span data-ttu-id="c98c9-158">您可以使用 **Name** 或其 **别名，也** 可以省略参数名称。</span><span class="sxs-lookup"><span data-stu-id="c98c9-158">You can use **Name** or its alias, **ServiceName** , or you can omit the parameter name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c98c9-159">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c98c9-159">-PassThru</span></span>

<span data-ttu-id="c98c9-160">返回一个表示服务的对象。</span><span class="sxs-lookup"><span data-stu-id="c98c9-160">Returns an object that represents the service.</span></span> <span data-ttu-id="c98c9-161">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="c98c9-161">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c98c9-162">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c98c9-162">-Confirm</span></span>

<span data-ttu-id="c98c9-163">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="c98c9-163">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c98c9-164">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c98c9-164">-WhatIf</span></span>

<span data-ttu-id="c98c9-165">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="c98c9-165">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c98c9-166">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="c98c9-166">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c98c9-167">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c98c9-167">CommonParameters</span></span>

<span data-ttu-id="c98c9-168">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c98c9-168">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c98c9-169">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c98c9-169">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c98c9-170">输入</span><span class="sxs-lookup"><span data-stu-id="c98c9-170">INPUTS</span></span>

### <span data-ttu-id="c98c9-171">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="c98c9-171">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="c98c9-172">可以通过管道将对象（该对象表示包含服务名称的服务或字符串）传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c98c9-172">You can pipe objects that represent the services or strings that contain the service names to this cmdlet.</span></span>

## <span data-ttu-id="c98c9-173">输出</span><span class="sxs-lookup"><span data-stu-id="c98c9-173">OUTPUTS</span></span>

### <span data-ttu-id="c98c9-174">无、System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="c98c9-174">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="c98c9-175">如果指定 PassThru，此 cmdlet 会生成表示服务的 **System.ServiceProcess.ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="c98c9-175">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify **PassThru**.</span></span> <span data-ttu-id="c98c9-176">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="c98c9-176">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c98c9-177">注释</span><span class="sxs-lookup"><span data-stu-id="c98c9-177">NOTES</span></span>

<span data-ttu-id="c98c9-178">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="c98c9-178">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="c98c9-179">还可以 `Start-Service` 通过其内置别名来引用 `sasv` 。</span><span class="sxs-lookup"><span data-stu-id="c98c9-179">You can also refer to `Start-Service` by its built-in alias, `sasv`.</span></span> <span data-ttu-id="c98c9-180">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="c98c9-180">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="c98c9-181">`Start-Service` 只有在当前用户有权执行此操作的情况下，才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-181">`Start-Service` can control services only if the current user has permission to do this.</span></span> <span data-ttu-id="c98c9-182">如果某个命令不能正常工作，则可能你不具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="c98c9-182">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="c98c9-183">若要查找服务名称并显示系统中的服务名称，请键入 `Get-Service`。</span><span class="sxs-lookup"><span data-stu-id="c98c9-183">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="c98c9-184">服务名称显示在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="c98c9-184">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>
- <span data-ttu-id="c98c9-185">只能启动启动类型为 "手动"、"自动" 或 "自动" (延迟启动) 的服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-185">You can start only the services that have a start type of Manual, Automatic, or Automatic (Delayed Start).</span></span> <span data-ttu-id="c98c9-186">无法启动启动类型为 Disabled 的服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-186">You cannot start the services that have a start type of Disabled.</span></span> <span data-ttu-id="c98c9-187">如果 `Start-Service` 命令失败，并出现消息 `Cannot start service \<service-name\> on computer` ，请使用 `Get-CimInstance` 查找服务的启动类型，如果需要，请使用 `Set-Service` cmdlet 更改服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="c98c9-187">If a `Start-Service` command fails with the message `Cannot start service \<service-name\> on computer`, use `Get-CimInstance` to find the start type of the service and, if you have to, use the `Set-Service` cmdlet to change the start type of the service.</span></span>
- <span data-ttu-id="c98c9-188">某些服务在没有工作时将自动停止，例如性能日志和警报 (SysmonLog) 服务。</span><span class="sxs-lookup"><span data-stu-id="c98c9-188">Some services, such as Performance Logs and Alerts (SysmonLog) stop automatically if they have no work to do.</span></span> <span data-ttu-id="c98c9-189">当 PowerShell 启动一项几乎立即停止的服务时，它会显示以下消息： `Service \<display-name\> start failed.`</span><span class="sxs-lookup"><span data-stu-id="c98c9-189">When PowerShell starts a service that stops itself almost immediately, it displays the following message: `Service \<display-name\> start failed.`</span></span>

## <span data-ttu-id="c98c9-190">相关链接</span><span class="sxs-lookup"><span data-stu-id="c98c9-190">RELATED LINKS</span></span>

[<span data-ttu-id="c98c9-191">Get-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-191">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="c98c9-192">New-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-192">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="c98c9-193">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-193">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="c98c9-194">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-194">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="c98c9-195">Set-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-195">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="c98c9-196">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-196">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="c98c9-197">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-197">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="c98c9-198">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="c98c9-198">Remove-Service</span></span>](Remove-Service.md)
