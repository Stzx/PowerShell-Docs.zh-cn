---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198281"
---
# <span data-ttu-id="3fda5-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-103">Get-Service</span></span>

## <span data-ttu-id="3fda5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3fda5-104">SYNOPSIS</span></span>
<span data-ttu-id="3fda5-105">获取本地或远程计算机上的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-105">Gets the services on a local or remote computer.</span></span>

## <span data-ttu-id="3fda5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3fda5-106">SYNTAX</span></span>

### <span data-ttu-id="3fda5-107">Default（默认值）</span><span class="sxs-lookup"><span data-stu-id="3fda5-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3fda5-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3fda5-108">DisplayName</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="3fda5-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="3fda5-109">InputObject</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="3fda5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3fda5-110">DESCRIPTION</span></span>

<span data-ttu-id="3fda5-111">**Get-help** cmdlet 获取表示本地计算机或远程计算机上的服务（包括正在运行和已停止的服务）的对象。</span><span class="sxs-lookup"><span data-stu-id="3fda5-111">The **Get-Service** cmdlet gets objects that represent the services on a local computer or on a remote computer, including running and stopped services.</span></span>

<span data-ttu-id="3fda5-112">可以通过指定服务的服务名称或显示名称来指示此 cmdlet 仅获取特定服务，也可以通过管道将服务对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3fda5-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="3fda5-113">示例</span><span class="sxs-lookup"><span data-stu-id="3fda5-113">EXAMPLES</span></span>

### <span data-ttu-id="3fda5-114">示例1：获取计算机上的所有服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-114">Example 1: Get all services on the computer</span></span>

```powershell
Get-Service
```

<span data-ttu-id="3fda5-115">此命令获取计算机上的所有服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-115">This command gets all of the services on the computer.</span></span>
<span data-ttu-id="3fda5-116">它的行为如同你键入 `Get-Service *` 的一样。</span><span class="sxs-lookup"><span data-stu-id="3fda5-116">It behaves as though you typed `Get-Service *`.</span></span>
<span data-ttu-id="3fda5-117">默认显示将显示每个服务的状态、服务名称和显示名称。</span><span class="sxs-lookup"><span data-stu-id="3fda5-117">The default display shows the status, service name, and display name of each service.</span></span>

### <span data-ttu-id="3fda5-118">示例2：获取以搜索字符串开头的服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-118">Example 2: Get services that begin with a search string</span></span>

```powershell
Get-Service "wmi*"
```

<span data-ttu-id="3fda5-119">此命令检索服务名称以 WMI 开头 (Windows Management Instrumentation) 首字母缩写的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-119">This command retrieves services with service names that begin with WMI (the acronym for Windows Management Instrumentation).</span></span>

### <span data-ttu-id="3fda5-120">示例3：显示包含搜索字符串的服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-120">Example 3: Display services that include a search string</span></span>

```powershell
Get-Service -Displayname "*network*"
```

<span data-ttu-id="3fda5-121">此命令显示显示名称包括 "网络" 的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-121">This command displays services with a display name that includes the word network.</span></span>
<span data-ttu-id="3fda5-122">搜索显示名称可以在服务名称不包含“Net”的情况下查找与网络相关的服务，例如 xmlprov（网络提供服务）。</span><span class="sxs-lookup"><span data-stu-id="3fda5-122">Searching the display name finds network-related services even when the service name does not include "Net", such as xmlprov, the Network Provisioning Service.</span></span>

### <span data-ttu-id="3fda5-123">示例4：获取以搜索字符串开头的服务和排除项</span><span class="sxs-lookup"><span data-stu-id="3fda5-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

<span data-ttu-id="3fda5-124">这些命令只获取服务名称以 "win" 开头的服务（WinRM 服务除外）。</span><span class="sxs-lookup"><span data-stu-id="3fda5-124">These commands get only the services with service names that begin with win, except for the WinRM service.</span></span>

### <span data-ttu-id="3fda5-125">示例5：显示当前处于活动状态的服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-125">Example 5: Display services that are currently active</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="3fda5-126">此命令仅显示当前处于活动状态的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-126">This command displays only the services that are currently active.</span></span>
<span data-ttu-id="3fda5-127">它使用 **get-help** cmdlet 获取计算机上的所有服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-127">It uses the **Get-Service** cmdlet to get all of the services on the computer.</span></span>
<span data-ttu-id="3fda5-128">管道运算符 (|) 将结果传递给 Where-Object cmdlet，该 cmdlet 只选择状态属性等于 "正在运行" 的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-128">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects only the services with a Status property that equals Running.</span></span>

<span data-ttu-id="3fda5-129">Status 是服务对象的唯一属性。</span><span class="sxs-lookup"><span data-stu-id="3fda5-129">Status is only one property of service objects.</span></span>
<span data-ttu-id="3fda5-130">若要查看所有属性，请键入 `Get-Service | Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="3fda5-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="3fda5-131">示例6：获取远程计算机上的服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-131">Example 6: Get the services on a remote computer</span></span>

```powershell
Get-Service -ComputerName "Server02"
```

<span data-ttu-id="3fda5-132">此命令获取 Server02 远程计算机上的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-132">This command gets the services on the Server02 remote computer.</span></span>

<span data-ttu-id="3fda5-133">因为 **get-help** 的 *ComputerName* 参数不使用 windows powershell 远程处理，所以即使未将计算机配置为在 Windows powershell 中进行远程处理，也可以使用此参数。</span><span class="sxs-lookup"><span data-stu-id="3fda5-133">Because the *ComputerName* parameter of **Get-Service** does not use Windows PowerShell remoting, you can use this parameter even if the computer is not configured for remoting in Windows PowerShell.</span></span>

### <span data-ttu-id="3fda5-134">示例7：列出本地计算机上具有依赖服务的服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-134">Example 7: List the services on the local computer that have dependent services</span></span>

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

<span data-ttu-id="3fda5-135">第一个命令使用 **get-help** cmdlet 来获取计算机上的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-135">The first command uses the **Get-Service** cmdlet to get the services on the computer.</span></span>
<span data-ttu-id="3fda5-136">管道运算符 (|) 将服务发送到 **对象** cmdlet，后者将选择其 **DependentServices** 属性不为 null 的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-136">A pipeline operator (|) sends the services to the **Where-Object** cmdlet, which selects the services whose **DependentServices** property is not null.</span></span>

<span data-ttu-id="3fda5-137">另一个管道运算符将结果发送给 Format-List cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3fda5-137">Another pipeline operator sends the results to the Format-List cmdlet.</span></span>
<span data-ttu-id="3fda5-138">该命令使用其 *Property* 参数来显示服务名称、依赖服务的名称以及显示每个服务具有的依赖服务数目的计算属性。</span><span class="sxs-lookup"><span data-stu-id="3fda5-138">The command uses its *Property* parameter to display the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services that each service has.</span></span>

### <span data-ttu-id="3fda5-139">示例8：按属性值排序服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-139">Example 8: Sort services by property value</span></span>

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

<span data-ttu-id="3fda5-140">此命令显示当你按其 **Status** 属性值以升序对服务进行排序时，已停止的服务将出现在运行服务之前。</span><span class="sxs-lookup"><span data-stu-id="3fda5-140">This command shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span>
<span data-ttu-id="3fda5-141">出现这种情况的原因是，Status 的值是一个枚举，其中，已停止的值为1，并且运行的值为4。</span><span class="sxs-lookup"><span data-stu-id="3fda5-141">This happens because the value of Status is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span>

<span data-ttu-id="3fda5-142">若要首先列出正在运行的服务，请使用 Sort-Object cmdlet 的 *降序* 参数。</span><span class="sxs-lookup"><span data-stu-id="3fda5-142">To list running services first, use the *Descending* parameter of the Sort-Object cmdlet.</span></span>

### <span data-ttu-id="3fda5-143">示例9：获取多台计算机上的服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-143">Example 9: Get services on multiple computers</span></span>

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

<span data-ttu-id="3fda5-144">此命令使用 **get-help** cmdlet 在两台远程计算机和本地计算机 ( "localhost" ) 上运行 Get-Service Winrm 命令。</span><span class="sxs-lookup"><span data-stu-id="3fda5-144">This command uses the **Get-Service** cmdlet to run a Get-Service Winrm command on two remote computers and the local computer ("localhost").</span></span>

<span data-ttu-id="3fda5-145">此命令在远程计算机上运行，并将结果返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3fda5-145">The command runs on the remote computers, and the results are returned to the local computer.</span></span>
<span data-ttu-id="3fda5-146">管道运算符 (|) 将结果发送到 **格式表** cmdlet，该 cmdlet 将服务格式设置为表。</span><span class="sxs-lookup"><span data-stu-id="3fda5-146">A pipeline operator (|) sends the results to the **Format-Table** cmdlet, which formats the services as a table.</span></span>
<span data-ttu-id="3fda5-147">**Format-Table** 命令使用 *Property* 参数来指定表中显示的属性，包括 **MachineName** 属性。</span><span class="sxs-lookup"><span data-stu-id="3fda5-147">The **Format-Table** command uses the *Property* parameter to specify the properties displayed in the table, including the **MachineName** property.</span></span>

### <span data-ttu-id="3fda5-148">示例10：获取服务的依赖服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-148">Example 10: Get the dependent services of a service</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

<span data-ttu-id="3fda5-149">此命令获取 WinRM 服务所需的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-149">This command gets the services that the WinRM service requires.</span></span>

<span data-ttu-id="3fda5-150">命令返回服务的 **ServicesDependedOn** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3fda5-150">The command returns the value of the **ServicesDependedOn** property of the service.</span></span>

### <span data-ttu-id="3fda5-151">示例11：通过管道运算符获取服务</span><span class="sxs-lookup"><span data-stu-id="3fda5-151">Example 11: Get a service through the pipeline operator</span></span>

```powershell
"WinRM" | Get-Service
```

<span data-ttu-id="3fda5-152">此命令获取本地计算机上的 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-152">This command gets the WinRM service on the local computer.</span></span>
<span data-ttu-id="3fda5-153">此示例显示你可以通过管道将服务名称字符串（ (用引号引起来) 发送到 **服务）** 。</span><span class="sxs-lookup"><span data-stu-id="3fda5-153">This example shows that you can pipe a service name string (enclosed in quotation marks) to **Get-Service** .</span></span>

## <span data-ttu-id="3fda5-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3fda5-154">PARAMETERS</span></span>

### <span data-ttu-id="3fda5-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3fda5-155">-ComputerName</span></span>

<span data-ttu-id="3fda5-156">获取指定计算机上运行的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-156">Gets the services running on the specified computers.</span></span>
<span data-ttu-id="3fda5-157">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="3fda5-157">The default is the local computer.</span></span>

<span data-ttu-id="3fda5-158">键入远程计算机的 FQDN)  (的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="3fda5-158">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="3fda5-159">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="3fda5-159">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="3fda5-160">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="3fda5-160">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="3fda5-161">即使你的计算机未配置为运行远程命令，你也可以使用 **get-help** 的 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="3fda5-161">You can use the *ComputerName* parameter of **Get-Service** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="3fda5-162">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="3fda5-162">-DependentServices</span></span>

<span data-ttu-id="3fda5-163">指示此 cmdlet 仅获取依赖于指定服务的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-163">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

<span data-ttu-id="3fda5-164">默认情况下，此 cmdlet 将获取所有服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-164">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3fda5-165">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="3fda5-165">-DisplayName</span></span>

<span data-ttu-id="3fda5-166">指定作为字符串数组，要检索的服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="3fda5-166">Specifies, as a string array, the display names of services to be retrieved.</span></span>
<span data-ttu-id="3fda5-167">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3fda5-167">Wildcards are permitted.</span></span>
<span data-ttu-id="3fda5-168">默认情况下，此 cmdlet 将获取计算机上的所有服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-168">By default, this cmdlet gets all services on the computer.</span></span>

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

### <span data-ttu-id="3fda5-169">-Exclude</span><span class="sxs-lookup"><span data-stu-id="3fda5-169">-Exclude</span></span>

<span data-ttu-id="3fda5-170">指定为字符串数组、此 cmdlet 从操作中排除的一个或一组服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-170">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="3fda5-171">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="3fda5-171">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="3fda5-172">请输入名称元素或模式，例如“s\*”。</span><span class="sxs-lookup"><span data-stu-id="3fda5-172">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="3fda5-173">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3fda5-173">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="3fda5-174">-Include</span><span class="sxs-lookup"><span data-stu-id="3fda5-174">-Include</span></span>

<span data-ttu-id="3fda5-175">指定为字符串数组、此 cmdlet 包含在操作中的一个或一项服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-175">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="3fda5-176">此参数值使 *Name* 参数有效。</span><span class="sxs-lookup"><span data-stu-id="3fda5-176">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="3fda5-177">请输入名称元素或模式，例如“s\*”。</span><span class="sxs-lookup"><span data-stu-id="3fda5-177">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="3fda5-178">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3fda5-178">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="3fda5-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3fda5-179">-InputObject</span></span>

<span data-ttu-id="3fda5-180">指定表示要检索的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="3fda5-180">Specifies **ServiceController** objects representing the services to be retrieved.</span></span>
<span data-ttu-id="3fda5-181">输入一个包含对象的变量，或键入可获取对象的命令或表达式。</span><span class="sxs-lookup"><span data-stu-id="3fda5-181">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>
<span data-ttu-id="3fda5-182">还可以通过管道将服务对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3fda5-182">You can also pipe a service object to this cmdlet.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3fda5-183">-Name</span><span class="sxs-lookup"><span data-stu-id="3fda5-183">-Name</span></span>

<span data-ttu-id="3fda5-184">指定要检索的服务的名称。</span><span class="sxs-lookup"><span data-stu-id="3fda5-184">Specifies the service names of services to be retrieved.</span></span>
<span data-ttu-id="3fda5-185">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="3fda5-185">Wildcards are permitted.</span></span>
<span data-ttu-id="3fda5-186">默认情况下，此 cmdlet 将获取计算机上的所有服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-186">By default, this cmdlet gets all of the services on the computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="3fda5-187">-RequiredServices</span><span class="sxs-lookup"><span data-stu-id="3fda5-187">-RequiredServices</span></span>

<span data-ttu-id="3fda5-188">指示此 cmdlet 仅获取此服务所需的服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-188">Indicates that this cmdlet gets only the services that this service requires.</span></span>

<span data-ttu-id="3fda5-189">此参数获取服务的 **ServicesDependedOn** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="3fda5-189">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>
<span data-ttu-id="3fda5-190">默认情况下，此 cmdlet 将获取所有服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-190">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3fda5-191">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3fda5-191">CommonParameters</span></span>

<span data-ttu-id="3fda5-192">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3fda5-192">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3fda5-193">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3fda5-193">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3fda5-194">输入</span><span class="sxs-lookup"><span data-stu-id="3fda5-194">INPUTS</span></span>

### <span data-ttu-id="3fda5-195">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="3fda5-195">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="3fda5-196">可以通过管道将服务对象或服务名称传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3fda5-196">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="3fda5-197">输出</span><span class="sxs-lookup"><span data-stu-id="3fda5-197">OUTPUTS</span></span>

### <span data-ttu-id="3fda5-198">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="3fda5-198">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="3fda5-199">此 cmdlet 将返回表示计算机上的服务的对象。</span><span class="sxs-lookup"><span data-stu-id="3fda5-199">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="3fda5-200">注释</span><span class="sxs-lookup"><span data-stu-id="3fda5-200">NOTES</span></span>

<span data-ttu-id="3fda5-201">还可以通过其内置别名 "gsv" 来对 **其进行引用** 。</span><span class="sxs-lookup"><span data-stu-id="3fda5-201">You can also refer to **Get-Service** by its built-in alias, "gsv".</span></span> <span data-ttu-id="3fda5-202">有关详细信息，请参阅 about_Aliases。</span><span class="sxs-lookup"><span data-stu-id="3fda5-202">For more information, see about_Aliases.</span></span>

<span data-ttu-id="3fda5-203">此 cmdlet 只能在当前用户有权查看服务时显示服务。</span><span class="sxs-lookup"><span data-stu-id="3fda5-203">This cmdlet can display services only when the current user has permission to see them.</span></span>
<span data-ttu-id="3fda5-204">如果此 cmdlet 未显示服务，则你可能没有查看它们的权限。</span><span class="sxs-lookup"><span data-stu-id="3fda5-204">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="3fda5-205">若要在系统中查找每个服务的服务名称和显示名称，请键入 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="3fda5-205">To find the service name and display name of each service on your system, type `Get-Service`.</span></span>
<span data-ttu-id="3fda5-206">服务名称显示在 Name 列中，显示名称显示在 DisplayName 列中。</span><span class="sxs-lookup"><span data-stu-id="3fda5-206">The service names appear in the Name column, and the display names appear in the DisplayName column.</span></span>

<span data-ttu-id="3fda5-207">当按状态值以升序排序时，“Stopped”服务将出现在“Running”服务之前。</span><span class="sxs-lookup"><span data-stu-id="3fda5-207">When you sort in ascending order by status value, "Stopped" services appear before "Running" services.</span></span>
<span data-ttu-id="3fda5-208">服务的 Status 属性是一个枚举值，其中状态的名称表示整数值。</span><span class="sxs-lookup"><span data-stu-id="3fda5-208">The Status property of a service is an enumerated value in which the names of the statuses represent integer values.</span></span>
<span data-ttu-id="3fda5-209">该排序是基于整数值进行的，而非名称。</span><span class="sxs-lookup"><span data-stu-id="3fda5-209">The sort is based on the integer value, not the name.</span></span>
<span data-ttu-id="3fda5-210">“Running”出现在“Stopped”之前的原因在于“Stopped”的值为“1”，而“Running”的值为“4”。</span><span class="sxs-lookup"><span data-stu-id="3fda5-210">"Running" appears before "Stopped" because "Stopped" has a value of "1", and "Running" has a value of "4".</span></span>

## <span data-ttu-id="3fda5-211">相关链接</span><span class="sxs-lookup"><span data-stu-id="3fda5-211">RELATED LINKS</span></span>

[<span data-ttu-id="3fda5-212">New-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-212">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="3fda5-213">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-213">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="3fda5-214">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-214">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="3fda5-215">Set-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-215">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="3fda5-216">Start-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-216">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="3fda5-217">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-217">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="3fda5-218">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="3fda5-218">Suspend-Service</span></span>](Suspend-Service.md)
