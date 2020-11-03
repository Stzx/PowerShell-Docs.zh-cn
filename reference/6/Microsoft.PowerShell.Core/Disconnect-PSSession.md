---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disconnect-pssession?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disconnect-PSSession
ms.openlocfilehash: c0eed3d571cfb243c3f0ba4d0a4b7ddfaf4f04fb
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93199050"
---
# <span data-ttu-id="71887-103">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-103">Disconnect-PSSession</span></span>

## <span data-ttu-id="71887-104">摘要</span><span class="sxs-lookup"><span data-stu-id="71887-104">SYNOPSIS</span></span>
<span data-ttu-id="71887-105">断开与会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-105">Disconnects from a session.</span></span>

## <span data-ttu-id="71887-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="71887-106">SYNTAX</span></span>

### <span data-ttu-id="71887-107">会话（默认）</span><span class="sxs-lookup"><span data-stu-id="71887-107">Session (Default)</span></span>

```
Disconnect-PSSession [-Session] <PSSession[]> [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="71887-108">名称</span><span class="sxs-lookup"><span data-stu-id="71887-108">Name</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71887-109">InstanceId</span><span class="sxs-lookup"><span data-stu-id="71887-109">InstanceId</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="71887-110">ID</span><span class="sxs-lookup"><span data-stu-id="71887-110">Id</span></span>

```
Disconnect-PSSession [-IdleTimeoutSec <Int32>] [-OutputBufferingMode <OutputBufferingMode>]
 [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="71887-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="71887-111">DESCRIPTION</span></span>

<span data-ttu-id="71887-112">`Disconnect-PSSession`Cmdlet `New-PSSession` 从当前会话将 PowerShell 会话 ( "PSSession" ) （如使用 cmdlet 启动的会话）断开连接。</span><span class="sxs-lookup"><span data-stu-id="71887-112">The `Disconnect-PSSession` cmdlet disconnects a PowerShell session ("PSSession"), such as one started by using the `New-PSSession` cmdlet, from the current session.</span></span> <span data-ttu-id="71887-113">因此，PSSession 将处于已断开连接状态。</span><span class="sxs-lookup"><span data-stu-id="71887-113">As a result, the PSSession is in a disconnected state.</span></span> <span data-ttu-id="71887-114">可以从当前会话或者本地计算机或另一台计算机上的另一个会话连接已断开的 PSSession。</span><span class="sxs-lookup"><span data-stu-id="71887-114">You can connect to the disconnected PSSession from the current session or from another session on the local computer or a different computer.</span></span>

<span data-ttu-id="71887-115">该 `Disconnect-PSSession` cmdlet 仅断开连接到当前会话的打开的 pssession。</span><span class="sxs-lookup"><span data-stu-id="71887-115">The `Disconnect-PSSession` cmdlet disconnects only open PSSessions that are connected to the current session.</span></span> <span data-ttu-id="71887-116">`Disconnect-PSSession` 无法断开中断或关闭的 Pssession 或使用 cmdlet 启动的交互式 Pssession，也 `Enter-PSSession` 无法断开连接到其他会话的 pssession。</span><span class="sxs-lookup"><span data-stu-id="71887-116">`Disconnect-PSSession` cannot disconnect broken or closed PSSessions, or interactive PSSessions started by using the `Enter-PSSession` cmdlet, and it cannot disconnect PSSessions that are connected to other sessions.</span></span>

<span data-ttu-id="71887-117">若要重新连接到已断开连接的 PSSession，请使用 `Connect-PSSession` 或 `Receive-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71887-117">To reconnect to a disconnected PSSession, use the `Connect-PSSession` or `Receive-PSSession` cmdlets.</span></span>

<span data-ttu-id="71887-118">当断开与 PSSession 的连接时，PSSession 中的命令将继续运行直到完成，除非 PSSession 超时或完整输出缓冲区阻止了 PSSession 中的命令。</span><span class="sxs-lookup"><span data-stu-id="71887-118">When a PSSession is disconnected, the commands in the PSSession continue to run until they complete, unless the PSSession times out or the commands in the PSSession are blocked by a full output buffer.</span></span> <span data-ttu-id="71887-119">若要更改空闲超时，请使用 **IdleTimeoutSec** 参数。</span><span class="sxs-lookup"><span data-stu-id="71887-119">To change the idle timeout, use the **IdleTimeoutSec** parameter.</span></span> <span data-ttu-id="71887-120">若要更改输出缓冲模式，请使用 **OutputBufferingMode** 参数，还可以使用 Cmdlet 的 **InDisconnectedSession** 参数 `Invoke-Command` 在断开连接的会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="71887-120">To change the output buffering mode, use the **OutputBufferingMode** parameter You can also use the **InDisconnectedSession** parameter of the `Invoke-Command` cmdlet to run a command in a disconnected session.</span></span>

<span data-ttu-id="71887-121">有关断开连接会话的功能的详细信息，请参阅 [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="71887-121">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](./About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="71887-122">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="71887-122">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="71887-123">示例</span><span class="sxs-lookup"><span data-stu-id="71887-123">EXAMPLES</span></span>

### <span data-ttu-id="71887-124">示例 1-按名称断开会话连接</span><span class="sxs-lookup"><span data-stu-id="71887-124">Example 1 - Disconnect a session by name</span></span>

<span data-ttu-id="71887-125">此命令将断开 Server01 计算机上的 UpdateSession PSSession 与当前会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-125">This command disconnects the UpdateSession PSSession on the Server01 computer from the current session.</span></span> <span data-ttu-id="71887-126">该命令使用 **Name** 参数来标识 PSSession。</span><span class="sxs-lookup"><span data-stu-id="71887-126">The command uses the **Name** parameter to identify the PSSession.</span></span>

```
PS> Disconnect-PSSession -Name UpdateSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  UpdateSession   Server01        Disconnected  Microsoft.PowerShell          None
```

<span data-ttu-id="71887-127">输出显示断开连接的尝试已成功。</span><span class="sxs-lookup"><span data-stu-id="71887-127">The output shows that the attempt to disconnect was successful.</span></span> <span data-ttu-id="71887-128">会话状态为 Disconnected，可用性为 None，它表示会话不处于忙碌状态，可以重新连接该回话。</span><span class="sxs-lookup"><span data-stu-id="71887-128">The session state is Disconnected and the Availability is None, which indicates that the session is not busy and can be reconnected.</span></span>

### <span data-ttu-id="71887-129">示例 2-从特定计算机断开会话连接</span><span class="sxs-lookup"><span data-stu-id="71887-129">Example 2 - Disconnect a session from a specific computer</span></span>

<span data-ttu-id="71887-130">此命令将断开 Server12 计算机上的 ITTask PSSession 与当前会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-130">This command disconnects the ITTask PSSession on the Server12 computer from the current session.</span></span>
<span data-ttu-id="71887-131">在当前会话中创建 ITTask 会话并将其连接到 Server12 计算机。</span><span class="sxs-lookup"><span data-stu-id="71887-131">The ITTask session was created in the current session and connects to the Server12 computer.</span></span> <span data-ttu-id="71887-132">该命令使用 `Get-PSSession` cmdlet 来获取会话，并使用 `Disconnect-PSSession` cmdlet 断开连接。</span><span class="sxs-lookup"><span data-stu-id="71887-132">The command uses the `Get-PSSession` cmdlet to get the session and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span>

```
PS> Get-PSSession -ComputerName Server12 -Name ITTask |
  Disconnect-PSSession -OutputBufferingMode Drop -IdleTimeoutSec 86400
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1  ITTask          Server12        Disconnected  ITTasks               None
```

<span data-ttu-id="71887-133">该 `Disconnect-PSSession` 命令使用 **OutputBufferingMode** 参数将输出模式设置为 **Drop** 。</span><span class="sxs-lookup"><span data-stu-id="71887-133">The `Disconnect-PSSession` command uses the **OutputBufferingMode** parameter to set the output mode to **Drop** .</span></span> <span data-ttu-id="71887-134">此设置确保会话中运行的脚本可以继续运行，即使会话输出缓冲区已满也是如此。</span><span class="sxs-lookup"><span data-stu-id="71887-134">This setting ensures that the script that is running in the session can continue to run even if the session output buffer is full.</span></span> <span data-ttu-id="71887-135">因为该脚本将其输出写入文件共享上的报告，所以其他输出可能在不产生后果的情况下丢失。</span><span class="sxs-lookup"><span data-stu-id="71887-135">Because the script writes its output to a report on a file share, other output can be lost without consequence.</span></span>

<span data-ttu-id="71887-136">该命令还使用 **IdleTimeoutSec** 参数来将会话的空闲超时扩展到 24 小时。</span><span class="sxs-lookup"><span data-stu-id="71887-136">The command also uses the **IdleTimeoutSec** parameter to extend the idle timeout of the session to 24 hours.</span></span> <span data-ttu-id="71887-137">此设置为此管理员或其他管理员重新连接到会话，以验证脚本是否已运行和解决问题（如果需要）提供了时间。</span><span class="sxs-lookup"><span data-stu-id="71887-137">This setting allows time for this administrator or other administrators to reconnect to the session to verify that the script ran and troubleshoot if needed.</span></span>

### <span data-ttu-id="71887-138">示例 3-在多台计算机上使用多个 Pssession</span><span class="sxs-lookup"><span data-stu-id="71887-138">Example 3 - Using multiple PSSessions on multiple computers</span></span>

<span data-ttu-id="71887-139">这一系列命令显示了如何 `Disconnect-PSSession` 在企业方案中使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71887-139">This series of commands shows how the `Disconnect-PSSession` cmdlet might be used in an enterprise scenario.</span></span> <span data-ttu-id="71887-140">在这种情况下，新的技术人员在远程计算机上的会话中启动一个脚本并遇到了问题。</span><span class="sxs-lookup"><span data-stu-id="71887-140">In this case, a new technician starts a script in a session on a remote computer and runs into a problem.</span></span> <span data-ttu-id="71887-141">该技术人员将断开到该会话的连接，以便更有经验的经理可以连接到该会话并解决该问题。</span><span class="sxs-lookup"><span data-stu-id="71887-141">The technician disconnects from the session so that a more experienced manager can connect to the session and resolve the problem.</span></span>

```
PS> $s = New-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
PS> Invoke-Command $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Get-PSSession -Name ITTask -ComputerName Srv1 | Disconnect-PSSession
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
1 ITTask           Srv1            Disconnected  Microsoft.PowerShell          None

PS> Get-PSSession -ComputerName Srv1, Srv2, Srv30 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None
 2 ITTask          Srv2            Opened        Microsoft.PowerShell     Available
 3 ITTask          Srv30           Opened        Microsoft.PowerShell     Available

PS> Get-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Srv1            Disconnected  Microsoft.PowerShell          None

PS> $s = Connect-PSSession -ComputerName Srv1 -Name ITTask -Credential Domain01\User01
PS> Invoke-Command -Session $s {dir $home\Scripts\PatchStatusOutput.ps1}
PS> Invoke-Command -Session $s {mkdir $home\Scripts\PatchStatusOutput}
PS> Invoke-Command -Session $s -FilePath \\Server01\Scripts\Get-PatchStatus.ps1
PS> Disconnect-PSSession -Session $s
```

<span data-ttu-id="71887-142">该技术人员首先在多台远程计算机上创建会话并在每个会话中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="71887-142">The technician begins by creating sessions on several remote computers and running a script in each session.</span></span> <span data-ttu-id="71887-143">第一个命令使用 `New-PSSession` cmdlet 在三台远程计算机上创建 ITTask 会话。</span><span class="sxs-lookup"><span data-stu-id="71887-143">The first command uses the `New-PSSession` cmdlet to create the ITTask session on three remote computers.</span></span> <span data-ttu-id="71887-144">该命令将会话保存在 $s 变量中。</span><span class="sxs-lookup"><span data-stu-id="71887-144">The command saves the sessions in the $s variable.</span></span> <span data-ttu-id="71887-145">第二个命令使用 cmdlet 的 **FilePath** 参数在 `Invoke-Command` $s 变量的会话中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="71887-145">The second command uses the **FilePath** parameter of the `Invoke-Command` cmdlet to run a script in the sessions in the $s variable.</span></span>

<span data-ttu-id="71887-146">在 Srv1 计算机上运行的脚本生成了意外的错误。</span><span class="sxs-lookup"><span data-stu-id="71887-146">The script running on the Srv1 computer generates unexpected errors.</span></span> <span data-ttu-id="71887-147">技术人员联系经理并请求协助。</span><span class="sxs-lookup"><span data-stu-id="71887-147">The technician contacts his manager and asks for assistance.</span></span> <span data-ttu-id="71887-148">经理指示技术人员断开与会话的连接，以便他可以进行调查。第二个命令使用 `Get-PSSession` cmdlet 来获取 Srv1 计算机上的 ITTask 会话，并使用 `Disconnect-PSSession` cmdlet 断开它的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-148">The manager directs the technician to disconnect from the session so he can investigate.The second command uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer and the `Disconnect-PSSession` cmdlet to disconnect it.</span></span> <span data-ttu-id="71887-149">此命令不会影响其他计算机上的 ITTask 会话。</span><span class="sxs-lookup"><span data-stu-id="71887-149">This command does not affect the ITTask sessions on the other computers.</span></span>

<span data-ttu-id="71887-150">第三个命令使用 `Get-PSSession` cmdlet 来获取 ITTask 会话。</span><span class="sxs-lookup"><span data-stu-id="71887-150">The third command uses the `Get-PSSession` cmdlet to get the ITTask sessions.</span></span> <span data-ttu-id="71887-151">输出显示 Srv2 和 Srv30 计算机上的 ITTask 会话并未受用于断开连接的命令的影响。</span><span class="sxs-lookup"><span data-stu-id="71887-151">The output shows that the ITTask sessions on the Srv2 and Srv30 computers were not affected by the command to disconnect.</span></span>

<span data-ttu-id="71887-152">管理器登录到他的家庭计算机，连接到其公司网络，启动 PowerShell，并使用 `Get-PSSession` cmdlet 来获取 Srv1 计算机上的 ITTask 会话。</span><span class="sxs-lookup"><span data-stu-id="71887-152">The manager logs on to his home computer, connects to his corporate network, starts PowerShell, and uses the `Get-PSSession` cmdlet to get the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="71887-153">他使用技术人员的凭据来访问该会话。</span><span class="sxs-lookup"><span data-stu-id="71887-153">He uses the credentials of the technician to access the session.</span></span>

<span data-ttu-id="71887-154">接下来，管理器使用 `Connect-PSSession` cmdlet 连接到 Srv1 计算机上的 ITTask 会话。</span><span class="sxs-lookup"><span data-stu-id="71887-154">Next, the manager uses the `Connect-PSSession` cmdlet to connect to the ITTask session on the Srv1 computer.</span></span> <span data-ttu-id="71887-155">该命令将该会话保存在 $s 变量中。</span><span class="sxs-lookup"><span data-stu-id="71887-155">The command saves the session in the $s variable.</span></span>

<span data-ttu-id="71887-156">管理器使用 `Invoke-Command` cmdlet 在变量中的会话中运行一些诊断命令 `$s` 。</span><span class="sxs-lookup"><span data-stu-id="71887-156">The manager uses the `Invoke-Command` cmdlet to run some diagnostic commands in the session in the `$s` variable.</span></span> <span data-ttu-id="71887-157">他认识到脚本失败是因为脚本找不到所需目录。</span><span class="sxs-lookup"><span data-stu-id="71887-157">He recognizes that the script failed because it did not find a required directory.</span></span>
<span data-ttu-id="71887-158">管理器使用 `MkDir` 函数创建目录，然后重新启动 `Get-PatchStatus.ps1` 脚本并断开与会话的连接。Manager 向技术人员报告他的调查结果，建议他重新连接到该会话以完成任务，并要求他向脚本添加一个命令，以 `Get-PatchStatus.ps1` 创建所需的目录（如果不存在）。</span><span class="sxs-lookup"><span data-stu-id="71887-158">The manager uses the `MkDir` function to create the directory, and then he restarts the `Get-PatchStatus.ps1` script and disconnects from the session.The manager reports his findings to the technician, suggests that he reconnect to the session to complete the tasks, and asks him to add a command to the `Get-PatchStatus.ps1` script that creates the required directory if it does not exist.</span></span>

### <span data-ttu-id="71887-159">示例 4-更改 PSSession 的超时值</span><span class="sxs-lookup"><span data-stu-id="71887-159">Example 4 - Change the timeout value for a PSSession</span></span>

<span data-ttu-id="71887-160">此示例演示如何更正会话的 **IdleTimeout** 属性的值，以便可以断开到它的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-160">This example shows how to correct the value of the **IdleTimeout** property of a session so that it can be disconnected.</span></span>

<span data-ttu-id="71887-161">会话的空闲超时属性对已断开连接的会话至关重要，因为它将确定在删除已断开连接的会话之前维护该会话多长时间。</span><span class="sxs-lookup"><span data-stu-id="71887-161">The idle timeout property of a session is critical to disconnected sessions, because it determines how long a disconnected session is maintained before it is deleted.</span></span> <span data-ttu-id="71887-162">当你创建会话以及断开到它的连接时，可以设置空闲超时选项。</span><span class="sxs-lookup"><span data-stu-id="71887-162">You can set the idle timeout option when you create a session and when you disconnect it.</span></span> <span data-ttu-id="71887-163">会话空闲超时的默认值是在 `$PSSessionOption` 本地计算机上的首选项变量和远程计算机上的会话配置中设置的。</span><span class="sxs-lookup"><span data-stu-id="71887-163">The default values for the idle timeout of a session are set in the `$PSSessionOption` preference variable on the local computer and in the session configuration on the remote computer.</span></span> <span data-ttu-id="71887-164">为会话设置的值优先于在会话配置中设置的值，但会话值不能超过会话配置中的配额设置，如 **MaxIdleTimeoutMs** 值。</span><span class="sxs-lookup"><span data-stu-id="71887-164">Values set for the session take precedence over values set in the session configuration, but session values cannot exceed quotas set in the session configuration, such as the **MaxIdleTimeoutMs** value.</span></span>

```
PS> $Timeout = New-PSSessionOption -IdleTimeout 172800000
PS> $s = New-PSSession -Computer Server01 -Name ITTask -SessionOption $Timeout
PS> Disconnect-PSSession -Session $s
Disconnect-PSSession : The session ITTask cannot be disconnected because the specified
idle timeout value 172800(seconds) is either greater than the server maximum allowed
43200 (seconds) or less that the minimum allowed60(seconds).  Choose an idle time out
value that is within the allowed range and try again.

PS> Invoke-Command -ComputerName Server01 {Get-PSSessionConfiguration Microsoft.PowerShell} |
 Format-List -Property *

Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/microsoft.powershell
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
SecurityDescriptorSddl        : O:NSG:BAD:P(A;;GA;;;BA)S:P(AU;FA;GA;;;WD)(AU;SA;GXGW;;;WD)
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 2147483647
Uri                           : http://schemas.microsoft.com/powershell/microsoft.powershell
SDKVersion                    : 2
Name                          : microsoft.powershell
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
ParentResourceUri             : http://schemas.microsoft.com/powershell/microsoft.powershell
Enabled                       : true
MaxShells                     : 25
MaxShellsPerUser              : 25
Permission                    : BUILTIN\Administrators AccessAllowed
PSComputerName                : localhost
RunspaceId                    : aea84310-6dbf-4c21-90ac-13980039925a
PSShowComputerName            : True


PS> $s.Runspace.ConnectionInfo
ConnectionUri                     : http://Server01/wsman
ComputerName                      : Server01
Scheme                            : http
Port                              : 80
AppName                           : /wsman
Credential                        :
ShellUri                          : http://schemas.microsoft.com/powershell/Microsoft.PowerShell
AuthenticationMechanism           : Default
CertificateThumbprint             :
MaximumConnectionRedirectionCount : 5
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
UseCompression                    : True
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
NoEncryption                      : False
UseUTF16                          : False
OutputBufferingMode               : Drop
IncludePortInSPN                  : False
Culture                           : en-US
UICulture                         : en-US
OpenTimeout                       : 180000
CancelTimeout                     : 60000
OperationTimeout                  : 180000
IdleTimeout                       : 172800000

PS> Disconnect-PSSession $s -IdleTimeoutSec 43200
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Disconnected  Microsoft.PowerShell          None

PS> $s.Runspace.ConnectionInfo.IdleTimeout
43200000
```

<span data-ttu-id="71887-165">第一个命令使用 `New-PSSessionOption` cmdlet 来创建会话选项对象。</span><span class="sxs-lookup"><span data-stu-id="71887-165">The first command uses the `New-PSSessionOption` cmdlet to create a session option object.</span></span> <span data-ttu-id="71887-166">它使用 **IdleTimeout** 参数将空闲超时设置为 48 小时（172800000 毫秒）。</span><span class="sxs-lookup"><span data-stu-id="71887-166">It uses the **IdleTimeout** parameter to set an idle timeout of 48 hours (172800000 milliseconds).</span></span> <span data-ttu-id="71887-167">该命令将会话选项对象保存在 $Timeout 变量中。</span><span class="sxs-lookup"><span data-stu-id="71887-167">The command saves the session option object in the $Timeout variable.</span></span>

<span data-ttu-id="71887-168">第二个命令使用 `New-PSSession` cmdlet 在 Server01 计算机上创建 ITTask 会话。</span><span class="sxs-lookup"><span data-stu-id="71887-168">The second command uses the `New-PSSession` cmdlet to create the ITTask session on the Server01 computer.</span></span> <span data-ttu-id="71887-169">该命令将会话保存在 $s 变量中。</span><span class="sxs-lookup"><span data-stu-id="71887-169">The command save the session in the $s variable.</span></span> <span data-ttu-id="71887-170">**SessionOption** 参数的值是 $Timeout 变量中的 48 小时空闲超时。</span><span class="sxs-lookup"><span data-stu-id="71887-170">The value of the **SessionOption** parameter is the 48-hour idle timeout in the $Timeout variable.</span></span>

<span data-ttu-id="71887-171">第三个命令将断开与 $s 变量中的 ITTask 会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-171">The third command disconnects the ITTask session in the $s variable.</span></span> <span data-ttu-id="71887-172">该命令失败是因为会话的空闲超时值超出会话配置中的 **MaxIdleTimeoutMs** 配额。</span><span class="sxs-lookup"><span data-stu-id="71887-172">The command fails because the idle timeout value of the session exceeds the **MaxIdleTimeoutMs** quota in the session configuration.</span></span> <span data-ttu-id="71887-173">由于断开此会话之前未使用空闲超时，因此当会话在使用中时可能检测不到此超额行为。</span><span class="sxs-lookup"><span data-stu-id="71887-173">Because the idle timeout is not used until the session is disconnected, this violation can go undetected while the session is in use.</span></span>

<span data-ttu-id="71887-174">第四个命令使用 `Invoke-Command` cmdlet `Get-PSSessionConfiguration` 在 Server01 计算机上为 Microsoft PowerShell 会话配置运行命令。</span><span class="sxs-lookup"><span data-stu-id="71887-174">The fourth command uses the `Invoke-Command` cmdlet to run a `Get-PSSessionConfiguration` command for the Microsoft.PowerShell session configuration on the Server01 computer.</span></span> <span data-ttu-id="71887-175">该命令使用 `Format-List` cmdlet 来显示列表中会话配置的所有属性。输出显示了 **MaxIdleTimeoutMS** 属性，该属性为使用会话配置的会话建立最大允许的 **IdleTimeout** 值43200000，)  (12 小时。</span><span class="sxs-lookup"><span data-stu-id="71887-175">The command uses the `Format-List` cmdlet to display all properties of the session configuration in a list.The output shows that the **MaxIdleTimeoutMS** property, which establishes the maximum permitted **IdleTimeout** value for sessions that use the session configuration, is 43200000 milliseconds (12 hours).</span></span>

<span data-ttu-id="71887-176">第五个命令将获取 $s 变量中的会话的会话选项值。</span><span class="sxs-lookup"><span data-stu-id="71887-176">The fifth command gets the session option values of the session in the $s variable.</span></span> <span data-ttu-id="71887-177">许多会话选项的值是会话的 **运行空间** 属性的 **ConnectionInfo** 属性的属性。此输出显示会话的 **IdleTimeout** 属性值为172800000毫秒 (48 小时) ，这违反了会话配置中的 **MaxIdleTimeoutMs** 配额（12小时）。若要解决此冲突，可以使用 **ConfigurationName** 参数来选择不同的会话配置，或使用 **IdleTimeout** 参数来减小会话的空闲超时。</span><span class="sxs-lookup"><span data-stu-id="71887-177">The values of many session options are properties of the **ConnectionInfo** property of the **Runspace** property of the session.The output shows that the value of the **IdleTimeout** property of the session is 172800000 milliseconds (48 hours), which violates the **MaxIdleTimeoutMs** quota of 12 hours in the session configuration.To resolve this conflict, you can use the **ConfigurationName** parameter to select a different session configuration or use the **IdleTimeout** parameter to reduce the idle timeout of the session.</span></span>

<span data-ttu-id="71887-178">第六个命令将断开到会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-178">The sixth command disconnects the session.</span></span> <span data-ttu-id="71887-179">该命令使用 **IdleTimeoutSec** 参数将最大空闲超时设置为 12 小时。</span><span class="sxs-lookup"><span data-stu-id="71887-179">It uses the **IdleTimeoutSec** parameter to set the idle timeout to the 12-hour maximum.</span></span>

<span data-ttu-id="71887-180">第七个命令将获取已断开连接的会话的 **IdleTimeout** 属性的值（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="71887-180">The seventh command gets the value of the **IdleTimeout** property of the disconnected session, which is measured in milliseconds.</span></span> <span data-ttu-id="71887-181">输出确认命令已成功。</span><span class="sxs-lookup"><span data-stu-id="71887-181">The output confirms that the command was successful.</span></span>

## <span data-ttu-id="71887-182">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="71887-182">PARAMETERS</span></span>

### <span data-ttu-id="71887-183">-Id</span><span class="sxs-lookup"><span data-stu-id="71887-183">-Id</span></span>

<span data-ttu-id="71887-184">断开与具有指定会话 ID 的会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-184">Disconnects from sessions with the specified session ID.</span></span> <span data-ttu-id="71887-185">键入一个或多个 ID（以逗号分隔），或使用范围运算符 (..) 来指定 ID 的范围。</span><span class="sxs-lookup"><span data-stu-id="71887-185">Type one or more IDs (separated by commas), or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="71887-186">若要获取会话的 ID，请使用 `Get-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71887-186">To get the ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="71887-187">将实例 ID 存储在会话的 **ID** 属性中。</span><span class="sxs-lookup"><span data-stu-id="71887-187">The instance ID is stored in the **ID** property of the session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71887-188">-IdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="71887-188">-IdleTimeoutSec</span></span>

<span data-ttu-id="71887-189">更改已断开连接的 PSSession 的空闲超时值。</span><span class="sxs-lookup"><span data-stu-id="71887-189">Changes the idle timeout value of the disconnected PSSession.</span></span> <span data-ttu-id="71887-190">输入一个值（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="71887-190">Enter a value in seconds.</span></span> <span data-ttu-id="71887-191">最小值为 60（1 分钟）。</span><span class="sxs-lookup"><span data-stu-id="71887-191">The minimum value is 60 (1 minute).</span></span>

<span data-ttu-id="71887-192">空闲超时确定已断开连接的 PSSession 在远程计算机上保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="71887-192">The idle timeout determines how long the disconnected PSSession is maintained on the remote computer.</span></span> <span data-ttu-id="71887-193">当超时到期时，将删除 PSSession。</span><span class="sxs-lookup"><span data-stu-id="71887-193">When the timeout expires, the PSSession is deleted.</span></span>

<span data-ttu-id="71887-194">从已断开连接的 PSSession 断开连接那一刻起，就将其视为空闲，即使命令是在已断开连接的会话中运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="71887-194">Disconnected PSSessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

<span data-ttu-id="71887-195">会话的空闲超时默认值由会话配置的 **IdleTimeoutMs** 属性的值设置。</span><span class="sxs-lookup"><span data-stu-id="71887-195">The default value for the idle timeout of a session is set by the value of the **IdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="71887-196">默认值为 7200000 毫秒（2 小时）。</span><span class="sxs-lookup"><span data-stu-id="71887-196">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="71887-197">此参数的值优先于 $PSSessionOption 首选项变量的 **IdleTimeout** 属性的值和会话配置中的默认空闲超时值。</span><span class="sxs-lookup"><span data-stu-id="71887-197">The value of this parameter takes precedence over the value of the **IdleTimeout** property of the $PSSessionOption preference variable and the default idle timeout value in the session configuration.</span></span> <span data-ttu-id="71887-198">但是，此值不能超过会话配置的 **MaxIdleTimeoutMs** 属性的值。</span><span class="sxs-lookup"><span data-stu-id="71887-198">However, this value cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span> <span data-ttu-id="71887-199">**MaxIdleTimeoutMs** 的默认值为 12 小时（43200000 毫秒）。</span><span class="sxs-lookup"><span data-stu-id="71887-199">The default value of **MaxIdleTimeoutMs** is 12 hours (43200000 milliseconds).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71887-200">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="71887-200">-InstanceId</span></span>

<span data-ttu-id="71887-201">断开与具有指定实例 ID 的会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-201">Disconnects from sessions with the specified instance IDs.</span></span>

<span data-ttu-id="71887-202">实例 ID 是一个 GUID，用于在本地或远程计算机上唯一标识某个会话。</span><span class="sxs-lookup"><span data-stu-id="71887-202">The instance ID is a GUID that uniquely identifies a session on a local or remote computer.</span></span> <span data-ttu-id="71887-203">实例 ID 是唯一的，即使在多台计算机上跨多个会话也是如此。</span><span class="sxs-lookup"><span data-stu-id="71887-203">The instance ID is unique, even across multiple sessions on multiple computers.</span></span>

<span data-ttu-id="71887-204">若要获取会话的实例 ID，请使用 `Get-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71887-204">To get the instance ID of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="71887-205">实例 ID 存储在会话的 **InstanceID** 属性中。</span><span class="sxs-lookup"><span data-stu-id="71887-205">The instance ID is stored in the **InstanceID** property of the session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="71887-206">-Name</span><span class="sxs-lookup"><span data-stu-id="71887-206">-Name</span></span>

<span data-ttu-id="71887-207">断开与具有指定友好名称的会话的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-207">Disconnects from sessions with the specified friendly names.</span></span> <span data-ttu-id="71887-208">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="71887-208">Wildcards are permitted.</span></span>

<span data-ttu-id="71887-209">若要获取会话的友好名称，请使用 `Get-PSSession` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="71887-209">To get the friendly name of a session, use the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="71887-210">友好名称存储在会话的 **Name** 属性中。</span><span class="sxs-lookup"><span data-stu-id="71887-210">The friendly name is stored in the **Name** property of the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="71887-211">-Session</span><span class="sxs-lookup"><span data-stu-id="71887-211">-Session</span></span>

<span data-ttu-id="71887-212">断开与指定的 PSSession 的连接。</span><span class="sxs-lookup"><span data-stu-id="71887-212">Disconnects from the specified PSSessions.</span></span> <span data-ttu-id="71887-213">输入 PSSession 对象，例如 cmdlet 返回的对象 `New-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="71887-213">Enter PSSession objects, such as those that the `New-PSSession` cmdlet returns.</span></span> <span data-ttu-id="71887-214">还可以通过管道将 PSSession 对象传递给 `Disconnect-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="71887-214">You can also pipe a PSSession object to `Disconnect-PSSession`.</span></span>

<span data-ttu-id="71887-215">`Get-PSSession`Cmdlet 可以获取在远程计算机上终止的所有 pssession，包括已断开连接的 pssession 和连接到其他计算机上其他会话的 pssession。</span><span class="sxs-lookup"><span data-stu-id="71887-215">The `Get-PSSession` cmdlet can get all PSSessions that terminate at a remote computer, including PSSessions that are disconnected and PSSessions that are connected to other sessions on other computers.</span></span> <span data-ttu-id="71887-216">`Disconnect-PSSession` 仅断开连接到当前会话的 PSSession。</span><span class="sxs-lookup"><span data-stu-id="71887-216">`Disconnect-PSSession` disconnects only PSSession that are connected to the current session.</span></span> <span data-ttu-id="71887-217">如果通过管道将其他 Pssession 传递给 `Disconnect-PSSession` ，则该 `Disconnect-PSSession` 命令将失败。</span><span class="sxs-lookup"><span data-stu-id="71887-217">If you pipe other PSSessions to `Disconnect-PSSession`, the `Disconnect-PSSession` command fails.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="71887-218">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="71887-218">-ThrottleLimit</span></span>

<span data-ttu-id="71887-219">设置命令的限制 `Disconnect-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="71887-219">Sets the throttle limit for the `Disconnect-PSSession` command.</span></span>

<span data-ttu-id="71887-220">中止值为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="71887-220">The throttle limit is the maximum number of concurrent connections that can be established to run this command.</span></span> <span data-ttu-id="71887-221">如果省略此参数或输入 0 值，则使用默认值 32。</span><span class="sxs-lookup"><span data-stu-id="71887-221">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="71887-222">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="71887-222">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 32
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71887-223">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="71887-223">-OutputBufferingMode</span></span>

<span data-ttu-id="71887-224">确定输出缓冲区已满时如何在已断开连接的会话中管理命令输出。</span><span class="sxs-lookup"><span data-stu-id="71887-224">Determines how command output is managed in the disconnected session when the output buffer is full.</span></span> <span data-ttu-id="71887-225">默认值为 **Block** 。</span><span class="sxs-lookup"><span data-stu-id="71887-225">The default value is **Block** .</span></span>

<span data-ttu-id="71887-226">如果已断开连接的会话中的命令返回输出时输出缓冲区已满，则此参数的值将有效地确定当会话已断开连接时该命令是否继续运行。</span><span class="sxs-lookup"><span data-stu-id="71887-226">If the command in the disconnected session is returning output and the output buffer fills, the value of this parameter effectively determines whether the command continues to run while the session is disconnected.</span></span> <span data-ttu-id="71887-227">值 **Block** 将挂起命令，直到重新连接会话。</span><span class="sxs-lookup"><span data-stu-id="71887-227">A value of **Block** suspends the command until the session is reconnected.</span></span> <span data-ttu-id="71887-228">值 **Drop** 允许命令完成，但是可能会丢失数据。</span><span class="sxs-lookup"><span data-stu-id="71887-228">A value of **Drop** allows the command to complete, although data might be lost.</span></span> <span data-ttu-id="71887-229">当使用 **Drop** 值时，请将命令输出重定向到磁盘上的文件。</span><span class="sxs-lookup"><span data-stu-id="71887-229">When using the **Drop** value, redirect the command output to a file on disk.</span></span>

<span data-ttu-id="71887-230">有效值是：</span><span class="sxs-lookup"><span data-stu-id="71887-230">Valid values are:</span></span>

- <span data-ttu-id="71887-231">**Block** ：当输出缓冲区已满时，将挂起执行，直到清除此缓冲区。</span><span class="sxs-lookup"><span data-stu-id="71887-231">**Block** : When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="71887-232">**Drop** ：当输出缓冲区已满时，执行将继续。</span><span class="sxs-lookup"><span data-stu-id="71887-232">**Drop** : When the output buffer is full, execution continues.</span></span> <span data-ttu-id="71887-233">由于已保存新的输出，因此将丢弃最早的输出。</span><span class="sxs-lookup"><span data-stu-id="71887-233">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="71887-234">**None** ：未指定任何输出缓冲模式。</span><span class="sxs-lookup"><span data-stu-id="71887-234">**None** : No output buffering mode is specified.</span></span> <span data-ttu-id="71887-235">会话配置的 **OutputBufferingMode** 属性的值用于已断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="71887-235">The value of the **OutputBufferingMode** property of the session configuration is used for the disconnected session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Block
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="71887-236">-Confirm</span><span class="sxs-lookup"><span data-stu-id="71887-236">-Confirm</span></span>

<span data-ttu-id="71887-237">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="71887-237">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="71887-238">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="71887-238">-WhatIf</span></span>

<span data-ttu-id="71887-239">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="71887-239">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="71887-240">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="71887-240">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="71887-241">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="71887-241">CommonParameters</span></span>

<span data-ttu-id="71887-242">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="71887-242">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="71887-243">有关详细信息，请参阅 [about_CommonParameters](./About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="71887-243">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="71887-244">输入</span><span class="sxs-lookup"><span data-stu-id="71887-244">INPUTS</span></span>

### <span data-ttu-id="71887-245">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-245">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="71887-246">可以通过管道将会话传递给 `Disconnect-PSSession` 。</span><span class="sxs-lookup"><span data-stu-id="71887-246">You can pipe a session to `Disconnect-PSSession`.</span></span>

## <span data-ttu-id="71887-247">输出</span><span class="sxs-lookup"><span data-stu-id="71887-247">OUTPUTS</span></span>

### <span data-ttu-id="71887-248">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-248">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="71887-249">`Disconnect-PSSession` 返回一个对象，该对象表示其已断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="71887-249">`Disconnect-PSSession` returns an object that represents the session that it disconnected.</span></span>

## <span data-ttu-id="71887-250">注释</span><span class="sxs-lookup"><span data-stu-id="71887-250">NOTES</span></span>

- <span data-ttu-id="71887-251">`Disconnect-PSSession`仅当本地计算机和远程计算机运行 PowerShell 3.0 或更高版本时，此 cmdlet 才有效。</span><span class="sxs-lookup"><span data-stu-id="71887-251">The `Disconnect-PSSession` cmdlet works only when the local and remote computers are running PowerShell 3.0 or later.</span></span>
- <span data-ttu-id="71887-252">如果在 `Disconnect-PSSession` 断开连接的会话上使用 cmdlet，则该命令对该会话不起作用，并且不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="71887-252">If you use the `Disconnect-PSSession` cmdlet on a disconnected session, the command has no effect on the session and it does not generate errors.</span></span>
- <span data-ttu-id="71887-253">对于具有交互式安全令牌（使用 **EnableNetworkAccess** 参数创建的安全令牌）的已断开连接的环回会话，只可以从创建该会话的计算机上重新连接该会话。</span><span class="sxs-lookup"><span data-stu-id="71887-253">Disconnected loopback sessions with interactive security tokens (those created with the **EnableNetworkAccess** parameter) can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="71887-254">此限制可使计算机免遭恶意访问。</span><span class="sxs-lookup"><span data-stu-id="71887-254">This restriction protects the computer from malicious access.</span></span>
- <span data-ttu-id="71887-255">断开到 PSSession 的连接后，会话状态为 **Disconnected** ，可用性为 **None** 。</span><span class="sxs-lookup"><span data-stu-id="71887-255">When you disconnect a PSSession, the session state is **Disconnected** and the availability is **None** .</span></span>

  <span data-ttu-id="71887-256">**State** 属性的值是相对于当前会话的。</span><span class="sxs-lookup"><span data-stu-id="71887-256">The value of the **State** property is relative to the current session.</span></span> <span data-ttu-id="71887-257">因此，值 **Disconnected** 意味着 PSSession 未连接到当前会话。</span><span class="sxs-lookup"><span data-stu-id="71887-257">Therefore, a value of **Disconnected** means that the PSSession is not connected to the current session.</span></span> <span data-ttu-id="71887-258">但是，它并不意味着 PSSession 会与所有会话断开连接。</span><span class="sxs-lookup"><span data-stu-id="71887-258">However, it does not mean that the PSSession is disconnected from all sessions.</span></span> <span data-ttu-id="71887-259">它可能连接到另一个会话。</span><span class="sxs-lookup"><span data-stu-id="71887-259">It might be connected to a different session.</span></span> <span data-ttu-id="71887-260">若要确定是否可以连接或重新连接到该会话，请使用 **Availability** 属性。</span><span class="sxs-lookup"><span data-stu-id="71887-260">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="71887-261">**Availability** 的 **None** 值指示可连接到 PSSession。</span><span class="sxs-lookup"><span data-stu-id="71887-261">An **Availability** value of **None** indicates that you can connect to the session.</span></span> <span data-ttu-id="71887-262">值 **Busy** 指示你无法连接到 PSSession，因为它已连接到另一个会话。</span><span class="sxs-lookup"><span data-stu-id="71887-262">A value of **Busy** indicates that you cannot connect to the PSSession because it is connected to another session.</span></span>

  <span data-ttu-id="71887-263">有关会话的 **State** 属性的值的详细信息，请参阅 [RunspaceState 枚举](/dotnet/api/system.management.automation.runspaces.runspacestate)。</span><span class="sxs-lookup"><span data-stu-id="71887-263">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](/dotnet/api/system.management.automation.runspaces.runspacestate).</span></span>

  <span data-ttu-id="71887-264">有关会话的 **可用性** 属性值的详细信息，请参阅 [runspacestate 枚举](/dotnet/api/system.management.automation.runspaces.runspaceavailability)。</span><span class="sxs-lookup"><span data-stu-id="71887-264">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](/dotnet/api/system.management.automation.runspaces.runspaceavailability).</span></span>

## <span data-ttu-id="71887-265">相关链接</span><span class="sxs-lookup"><span data-stu-id="71887-265">RELATED LINKS</span></span>

[<span data-ttu-id="71887-266">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-266">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="71887-267">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-267">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="71887-268">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-268">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="71887-269">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-269">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="71887-270">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="71887-270">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="71887-271">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-271">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="71887-272">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="71887-272">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="71887-273">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="71887-273">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="71887-274">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-274">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="71887-275">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="71887-275">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="71887-276">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="71887-276">Remove-PSSession</span></span>](Remove-PSSession.md)

[<span data-ttu-id="71887-277">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="71887-277">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="71887-278">about_Remote</span><span class="sxs-lookup"><span data-stu-id="71887-278">about_Remote</span></span>](About/about_Remote.md)

[<span data-ttu-id="71887-279">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="71887-279">about_Remote_Disconnected_Sessions</span></span>](About/about_Remote_Disconnected_Sessions.md)