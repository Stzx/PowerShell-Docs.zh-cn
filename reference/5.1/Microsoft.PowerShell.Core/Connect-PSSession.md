---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/15/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/connect-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Connect-PSSession
ms.openlocfilehash: d4f071b4c106735e622281f728b8632c211a813d
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198992"
---
# <span data-ttu-id="37676-103">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-103">Connect-PSSession</span></span>

## <span data-ttu-id="37676-104">摘要</span><span class="sxs-lookup"><span data-stu-id="37676-104">SYNOPSIS</span></span>
<span data-ttu-id="37676-105">重新连接到已断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-105">Reconnects to disconnected sessions.</span></span>

## <span data-ttu-id="37676-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="37676-106">SYNTAX</span></span>

### <span data-ttu-id="37676-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="37676-107">Name (Default)</span></span>

```
Connect-PSSession -Name <String[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="37676-108">会话</span><span class="sxs-lookup"><span data-stu-id="37676-108">Session</span></span>

```
Connect-PSSession [-Session] <PSSession[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="37676-109">计算机名</span><span class="sxs-lookup"><span data-stu-id="37676-109">ComputerName</span></span>

```
Connect-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 [-Name <String[]>] [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="37676-110">ComputerNameGuid</span><span class="sxs-lookup"><span data-stu-id="37676-110">ComputerNameGuid</span></span>

```
Connect-PSSession [-ComputerName] <String[]> [-ApplicationName <String>] [-ConfigurationName <String>]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-Port <Int32>] [-UseSSL] [-SessionOption <PSSessionOption>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="37676-111">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="37676-111">ConnectionUri</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection] [-Name <String[]>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-CertificateThumbprint <String>]
 [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="37676-112">ConnectionUriGuid</span><span class="sxs-lookup"><span data-stu-id="37676-112">ConnectionUriGuid</span></span>

```
Connect-PSSession [-ConfigurationName <String>] [-ConnectionUri] <Uri[]> [-AllowRedirection]
 -InstanceId <Guid[]> [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>]
 [-CertificateThumbprint <String>] [-SessionOption <PSSessionOption>] [-ThrottleLimit <Int32>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="37676-113">InstanceId</span><span class="sxs-lookup"><span data-stu-id="37676-113">InstanceId</span></span>

```
Connect-PSSession -InstanceId <Guid[]> [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="37676-114">ID</span><span class="sxs-lookup"><span data-stu-id="37676-114">Id</span></span>

```
Connect-PSSession [-ThrottleLimit <Int32>] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="37676-115">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="37676-115">DESCRIPTION</span></span>

<span data-ttu-id="37676-116">**Connect-PSSession** cmdlet 可重新连接到已断开连接 ( **pssession** ) 的用户管理的 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="37676-116">The **Connect-PSSession** cmdlet reconnects to user-managed Windows PowerShell sessions ( **PSSessions** ) that were disconnected.</span></span>
<span data-ttu-id="37676-117">它可以在有意断开连接的会话（例如通过使用 Disconnect-PSSession cmdlet 或 Invoke-Command cmdlet 的 *InDisconnectedSession* 参数）和无意断开连接的会话（例如由于临时网络故障）上运行。</span><span class="sxs-lookup"><span data-stu-id="37676-117">It works on sessions that are disconnected intentionally, such as by using the Disconnect-PSSession cmdlet or the *InDisconnectedSession* parameter of the Invoke-Command cmdlet, and those that were disconnected unintentionally, such as by a temporary network outage.</span></span>

<span data-ttu-id="37676-118">**Connect-PSSession** 可以连接到由同一用户启动的任何已断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-118">**Connect-PSSession** can connect to any disconnected session that was started by the same user.</span></span>
<span data-ttu-id="37676-119">其中包括通过其他计算机上的其他会话启动或断开连接。</span><span class="sxs-lookup"><span data-stu-id="37676-119">These include those that were started by or disconnected from other sessions on other computers.</span></span>

<span data-ttu-id="37676-120">但是， **Connect-PSSession** 无法连接到已损坏的或已关闭的会话或者通过使用 Enter-PSSession cmdlet 启动的交互式会话。</span><span class="sxs-lookup"><span data-stu-id="37676-120">However, **Connect-PSSession** cannot connect to broken or closed sessions, or interactive sessions started by using the Enter-PSSession cmdlet.</span></span>
<span data-ttu-id="37676-121">此外，也无法将会话连接到由其他用户启动的会话，除非你能提供创建会话的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="37676-121">Also you cannot connect sessions to sessions started by other users, unless you can provide the credentials of the user who created the session.</span></span>

<span data-ttu-id="37676-122">有关断开连接会话的功能的详细信息，请参阅 [about_Remote_Disconnected_Sessions](About/about_Remote_Disconnected_Sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="37676-122">For more information about the Disconnected Sessions feature, see [about_Remote_Disconnected_Sessions](About/about_Remote_Disconnected_Sessions.md).</span></span>

<span data-ttu-id="37676-123">此 cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="37676-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="37676-124">示例</span><span class="sxs-lookup"><span data-stu-id="37676-124">EXAMPLES</span></span>

### <span data-ttu-id="37676-125">示例1：重新连接到会话</span><span class="sxs-lookup"><span data-stu-id="37676-125">Example 1: Reconnect to a session</span></span>

```
PS C:\> Connect-PSSession -ComputerName Server01 -Name ITTask
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 4 ITTask          Server01        Opened        ITTasks                  Available
```

<span data-ttu-id="37676-126">此命令重新连接到 Server01 计算机上的 ITTask 会话。</span><span class="sxs-lookup"><span data-stu-id="37676-126">This command reconnects to the ITTask session on the Server01 computer.</span></span>

<span data-ttu-id="37676-127">该输出显示此命令已成功。</span><span class="sxs-lookup"><span data-stu-id="37676-127">The output shows that the command was successful.</span></span>
<span data-ttu-id="37676-128">此时将打开会话的 **状态** ，并且 **可用性** 可用，这表示你可以在该会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="37676-128">The **State** of the session is Opened and the **Availability** is Available, which indicates that you can run commands in the session.</span></span>

### <span data-ttu-id="37676-129">示例2：断开连接和重新连接的影响</span><span class="sxs-lookup"><span data-stu-id="37676-129">Example 2: Effect of disconnecting and reconnecting</span></span>

```
PS C:\> Get-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available


PS C:\> Get-PSSession | Disconnect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Disconnected  Microsoft.PowerShell          None


PS C:\> Get-PSSession | Connect-PSSession

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 Backups         Localhost       Opened        Microsoft.PowerShell     Available
```

<span data-ttu-id="37676-130">此示例显示了断开某一会话的连接又重新连接到该会话的效果。</span><span class="sxs-lookup"><span data-stu-id="37676-130">This example shows the effect of disconnecting and then reconnecting to a session.</span></span>

<span data-ttu-id="37676-131">第一个命令使用 Get-PSSession cmdlet。</span><span class="sxs-lookup"><span data-stu-id="37676-131">The first command uses the Get-PSSession cmdlet.</span></span>
<span data-ttu-id="37676-132">在没有 *ComputerName* 参数的情况下，该命令仅获取已在当前会话中创建的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-132">Without the *ComputerName* parameter, the command gets only sessions that were created in the current session.</span></span>

<span data-ttu-id="37676-133">该输出显示此命令可获取本地计算机上的 Backup 会话。</span><span class="sxs-lookup"><span data-stu-id="37676-133">The output shows that the command gets the Backups session on the local computer.</span></span>
<span data-ttu-id="37676-134">会话 **状态** 已打开且 **可用性** 可用。</span><span class="sxs-lookup"><span data-stu-id="37676-134">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="37676-135">第二个命令使用 **get-help** cmdlet 获取在当前会话中创建的 **PSSession** 对象，并使用 **disconnect-pssession** cmdlet 断开这些会话的连接。</span><span class="sxs-lookup"><span data-stu-id="37676-135">The second command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Disconnect-PSSession** cmdlet to disconnect the sessions.</span></span>
<span data-ttu-id="37676-136">该输出显示 Backup 会话已断开连接。</span><span class="sxs-lookup"><span data-stu-id="37676-136">The output shows that the Backups session was disconnected.</span></span>
<span data-ttu-id="37676-137">会话的 **状态** 为 "已断开连接" 且 **可用性** 为 "无"。</span><span class="sxs-lookup"><span data-stu-id="37676-137">The **State** of the session is Disconnected and the **Availability** is None.</span></span>

<span data-ttu-id="37676-138">第三个命令使用 **get-help** cmdlet 获取在当前会话中创建的 **PSSession** 对象，并使用 **Connect-pssession** cmdlet 来重新连接会话。</span><span class="sxs-lookup"><span data-stu-id="37676-138">The third command uses the **Get-PSSession** cmdlet to get the **PSSession** objects that were created in the current session and the **Connect-PSSession** cmdlet to reconnect the sessions.</span></span>
<span data-ttu-id="37676-139">该输出显示 Backup 会话已重新连接。</span><span class="sxs-lookup"><span data-stu-id="37676-139">The output shows that the Backups session was reconnected.</span></span>
<span data-ttu-id="37676-140">会话 **状态** 已打开且 **可用性** 可用。</span><span class="sxs-lookup"><span data-stu-id="37676-140">The **State** of the session is Opened and the **Availability** is Available.</span></span>

<span data-ttu-id="37676-141">如果在未断开连接的会话上使用 **Connect-PSSession** cmdlet，则该命令不会影响会话，并且不会生成任何错误。</span><span class="sxs-lookup"><span data-stu-id="37676-141">If you use the **Connect-PSSession** cmdlet on a session that is not disconnected, the command does not affect the session and it does not generate any errors.</span></span>

### <span data-ttu-id="37676-142">示例3：企业方案中的一系列命令</span><span class="sxs-lookup"><span data-stu-id="37676-142">Example 3: Series of commands in an enterprise scenario</span></span>

```
The administrator starts by creating a sessions on a remote computer and running a script in the session.The first command uses the **New-PSSession** cmdlet to create the ITTask session on the Server01 remote computer. The command uses the *ConfigurationName* parameter to specify the ITTasks session configuration. The command saves the sessions in the $s variable.
PS C:\> $s = New-PSSession -ComputerName Server01 -Name ITTask -ConfigurationName ITTasks

 The second command **Invoke-Command** cmdlet to start a background job in the session in the $s variable. It uses the *FilePath* parameter to run the script in the background job.
PS C:\> Invoke-Command -Session $s {Start-Job -FilePath \\Server30\Scripts\Backup-SQLDatabase.ps1}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Running       True            Server01             \\Server30\Scripts\Backup...

The third command uses the Disconnect-PSSession cmdlet to disconnect from the session in the $s variable. The command uses the *OutputBufferingMode* parameter with a value of Drop to prevent the script from being blocked by having to deliver output to the session. It uses the *IdleTimeoutSec* parameter to extend the session time-out to 15 hours.When the command is completed, the administrator locks her computer and goes home for the evening.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None

Later that evening, the administrator starts her home computer, logs on to the corporate network, and starts Windows PowerShell. The fourth command uses the Get-PSSession cmdlet to get the sessions on the Server01 computer. The command finds the ITTask session.The fifth command uses the **Connect-PSSession** cmdlet to connect to the ITTask session. The command saves the session in the $s variable.
PS C:\> Get-PSSession -ComputerName Server01 -Name ITTask

Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None


PS C:\> $s = Connect-PSSession -ComputerName Server01 -Name ITTask


Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Opened        ITTasks               Available

The sixth command uses the **Invoke-Command** cmdlet to run a Get-Job command in the session in the $s variable. The output shows that the job finished successfully.The seventh command uses the **Invoke-Command** cmdlet to run a Receive-Job command in the session in the $s variable in the session. The command saves the results in the $BackupSpecs variable.The eighth command uses the **Invoke-Command** cmdlet to runs another script in the session. The command uses the value of the $BackupSpecs variable in the session as input to the script.


PS C:\> Invoke-Command -Session $s {Get-Job}

Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
2      Job2            Completed     True            Server01             \\Server30\Scripts\Backup...

PS C:\> Invoke-Command -Session $s {$BackupSpecs = Receive-Job -JobName Job2}

PS C:\> Invoke-Command -Session $s {\\Server30\Scripts\New-SQLDatabase.ps1 -InitData $BackupSpecs.Initialization}

The ninth command disconnects from the session in the $s variable.The administrator closes Windows PowerShell and closes the computer. She can reconnect to the session on the next day and check the script status from her work computer.
PS C:\> Disconnect-PSSession -Session $s -OutputBufferingMode Drop -IdleTimeoutSec 60*60*15
Id Name            ComputerName    State         ConfigurationName     Availability
-- ----            ------------    -----         -----------------     ------------
 1 ITTask          Server01        Disconnected  ITTasks               None
```

<span data-ttu-id="37676-143">这一系列的命令演示 **Connect-PSSession** cmdlet 在企业方案中的可能的使用方式。</span><span class="sxs-lookup"><span data-stu-id="37676-143">This series of commands shows how the **Connect-PSSession** cmdlet might be used in an enterprise scenario.</span></span>
<span data-ttu-id="37676-144">在此示例中，系统管理员将在远程计算机上的会话中启动长时间运行的作业。</span><span class="sxs-lookup"><span data-stu-id="37676-144">In this case, a system administrator starts a long-running job in a session on a remote computer.</span></span>
<span data-ttu-id="37676-145">启动该作业后，管理员将断开与该会话的连接，然后下班回家。</span><span class="sxs-lookup"><span data-stu-id="37676-145">After starting the job, the administrator disconnects from the session and goes home.</span></span>
<span data-ttu-id="37676-146">在晚上晚，管理员登录到她的家庭计算机，并验证作业是否已完成。</span><span class="sxs-lookup"><span data-stu-id="37676-146">Later that evening, the administrator logs on to her home computer and verifies that the job ran until it is completed.</span></span>

## <span data-ttu-id="37676-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="37676-147">PARAMETERS</span></span>

### <span data-ttu-id="37676-148">-AllowRedirection</span><span class="sxs-lookup"><span data-stu-id="37676-148">-AllowRedirection</span></span>

<span data-ttu-id="37676-149">指示此 cmdlet 允许将此连接重定向到备用 URI。</span><span class="sxs-lookup"><span data-stu-id="37676-149">Indicates that this cmdlet allows redirection of this connection to an alternate URI.</span></span>

<span data-ttu-id="37676-150">使用 *ConnectionURI* 参数时，远程目标将返回一个指令，以重定向到不同的 URI。</span><span class="sxs-lookup"><span data-stu-id="37676-150">When you use the *ConnectionURI* parameter, the remote destination can return an instruction to redirect to a different URI.</span></span>
<span data-ttu-id="37676-151">默认情况下，Windows PowerShell 不会重定向连接，但你可以使用此参数允许它重定向连接。</span><span class="sxs-lookup"><span data-stu-id="37676-151">By default, Windows PowerShell does not redirect connections, but you can use this parameter to allow it to redirect the connection.</span></span>

<span data-ttu-id="37676-152">你也可以通过更改 **MaximumConnectionRedirectionCount** 会话选项值，限制重定向连接的次数。</span><span class="sxs-lookup"><span data-stu-id="37676-152">You can also limit the number of times the connection is redirected by changing the **MaximumConnectionRedirectionCount** session option value.</span></span>
<span data-ttu-id="37676-153">使用 New-PSSessionOption cmdlet 的 *MaximumRedirection* 参数或设置 **$PSSessionOption** 首选项变量的 **MaximumConnectionRedirectionCount** 属性。</span><span class="sxs-lookup"><span data-stu-id="37676-153">Use the *MaximumRedirection* parameter of the New-PSSessionOption cmdlet or set the **MaximumConnectionRedirectionCount** property of the **$PSSessionOption** preference variable.</span></span>
<span data-ttu-id="37676-154">默认值为 5。</span><span class="sxs-lookup"><span data-stu-id="37676-154">The default value is 5.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-155">-ApplicationName</span><span class="sxs-lookup"><span data-stu-id="37676-155">-ApplicationName</span></span>

<span data-ttu-id="37676-156">指定应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="37676-156">Specifies the name of an application.</span></span>
<span data-ttu-id="37676-157">此 cmdlet 仅连接到使用指定应用程序的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-157">This cmdlet connects only to sessions that use the specified application.</span></span>

<span data-ttu-id="37676-158">输入连接 URI 的应用程序名称段。</span><span class="sxs-lookup"><span data-stu-id="37676-158">Enter the application name segment of the connection URI.</span></span>
<span data-ttu-id="37676-159">例如，在以下连接 URI 中，应用程序名称为 WSMan：`http://localhost:5985/WSMAN`。</span><span class="sxs-lookup"><span data-stu-id="37676-159">For example, in the following connection URI, the application name is WSMan: `http://localhost:5985/WSMAN`.</span></span>
<span data-ttu-id="37676-160">会话的应用程序名称存储在该会话的 **Runspace.ConnectionInfo.AppName** 属性中。</span><span class="sxs-lookup"><span data-stu-id="37676-160">The application name of a session is stored in the **Runspace.ConnectionInfo.AppName** property of the session.</span></span>

<span data-ttu-id="37676-161">此参数的值用于选择和筛选会话。</span><span class="sxs-lookup"><span data-stu-id="37676-161">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="37676-162">它不会更改会话使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="37676-162">It does not change the application that the session uses.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="37676-163">-Authentication</span><span class="sxs-lookup"><span data-stu-id="37676-163">-Authentication</span></span>

<span data-ttu-id="37676-164">指定用于对命令中的用户凭据进行身份验证的机制，以便重新连接到断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-164">Specifies the mechanism that is used to authenticate user credentials in the command to reconnect to the disconnected session.</span></span> <span data-ttu-id="37676-165">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="37676-165">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="37676-166">默认</span><span class="sxs-lookup"><span data-stu-id="37676-166">Default</span></span>
- <span data-ttu-id="37676-167">基本</span><span class="sxs-lookup"><span data-stu-id="37676-167">Basic</span></span>
- <span data-ttu-id="37676-168">Credssp</span><span class="sxs-lookup"><span data-stu-id="37676-168">Credssp</span></span>
- <span data-ttu-id="37676-169">摘要</span><span class="sxs-lookup"><span data-stu-id="37676-169">Digest</span></span>
- <span data-ttu-id="37676-170">Kerberos</span><span class="sxs-lookup"><span data-stu-id="37676-170">Kerberos</span></span>
- <span data-ttu-id="37676-171">Negotiate</span><span class="sxs-lookup"><span data-stu-id="37676-171">Negotiate</span></span>
- <span data-ttu-id="37676-172">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="37676-172">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="37676-173">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="37676-173">The default value is Default.</span></span>

<span data-ttu-id="37676-174">有关此参数的值的详细信息，请参阅 MSDN 库中的 [System.management.automation.runspaces.authenticationmechanism 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 。</span><span class="sxs-lookup"><span data-stu-id="37676-174">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="37676-175">警告：凭据安全支持提供程序 (CredSSP) 身份验证，其中用户的凭据将传递给要进行身份验证的远程计算机，其适用于需要在多个资源（例如访问远程网络共享）上进行身份验证的命令。</span><span class="sxs-lookup"><span data-stu-id="37676-175">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="37676-176">此机制增加了远程操作的安全风险。</span><span class="sxs-lookup"><span data-stu-id="37676-176">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="37676-177">如果远程计算机的安全受到威胁，则传递给该计算机的凭据可用于控制网络会话。</span><span class="sxs-lookup"><span data-stu-id="37676-177">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-178">-CertificateThumbprint</span><span class="sxs-lookup"><span data-stu-id="37676-178">-CertificateThumbprint</span></span>

<span data-ttu-id="37676-179">指定有权连接到断开连接的会话的用户帐户的数字公钥证书 (X509)。</span><span class="sxs-lookup"><span data-stu-id="37676-179">Specifies the digital public key certificate (X509) of a user account that has permission to connect to the disconnected session.</span></span> <span data-ttu-id="37676-180">输入证书的证书指纹。</span><span class="sxs-lookup"><span data-stu-id="37676-180">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="37676-181">在基于客户端证书的身份验证中使用证书。</span><span class="sxs-lookup"><span data-stu-id="37676-181">Certificates are used in client certificate-based authentication.</span></span>
<span data-ttu-id="37676-182">它们只能映射到本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="37676-182">They can be mapped only to local user accounts.</span></span>
<span data-ttu-id="37676-183">它们不适用于域帐户。</span><span class="sxs-lookup"><span data-stu-id="37676-183">They do not work with domain accounts.</span></span>

<span data-ttu-id="37676-184">若要获取证书指纹，请在 Windows PowerShell Cert: 驱动器中使用 Get-Item 或 Get-ChildItem 命令。</span><span class="sxs-lookup"><span data-stu-id="37676-184">To get a certificate thumbprint, use a Get-Item or Get-ChildItem command in the Windows PowerShell Cert: drive.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-185">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="37676-185">-ComputerName</span></span>

<span data-ttu-id="37676-186">指定在其中存储断开连接的会话的计算机。</span><span class="sxs-lookup"><span data-stu-id="37676-186">Specifies the computers on which the disconnected sessions are stored.</span></span>
<span data-ttu-id="37676-187">会话存储在位于连接的服务器端或接收端的计算机上。</span><span class="sxs-lookup"><span data-stu-id="37676-187">Sessions are stored on the computer that is at the server-side or receiving end of a connection.</span></span>
<span data-ttu-id="37676-188">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="37676-188">The default is the local computer.</span></span>

<span data-ttu-id="37676-189">键入计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="37676-189">Type the NetBIOS name, an IP address, or a fully qualified domain name of one computer.</span></span>
<span data-ttu-id="37676-190">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="37676-190">Wildcard characters are not permitted.</span></span>
<span data-ttu-id="37676-191">若要指定本地计算机，请键入计算机名称、localhost 或点 (。 ) </span><span class="sxs-lookup"><span data-stu-id="37676-191">To specify the local computer, type the computer name, localhost, or a dot (.)</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName, ComputerNameGuid
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-192">-ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="37676-192">-ConfigurationName</span></span>

<span data-ttu-id="37676-193">只连接到使用指定会话配置的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-193">Connects only to sessions that use the specified session configuration.</span></span>

<span data-ttu-id="37676-194">输入会话配置的配置名称或完全限定的资源 URI。</span><span class="sxs-lookup"><span data-stu-id="37676-194">Enter a configuration name or the fully qualified resource URI for a session configuration.</span></span>
<span data-ttu-id="37676-195">如果只指定配置名称，则会预置以下架构 URI： `http://schemas.microsoft.com/powershell` 。</span><span class="sxs-lookup"><span data-stu-id="37676-195">If you specify only the configuration name, the following schema URI is prepended: `http://schemas.microsoft.com/powershell`.</span></span>
<span data-ttu-id="37676-196">会话的配置名称存储在该会话的 **ConfigurationName** 属性中。</span><span class="sxs-lookup"><span data-stu-id="37676-196">The configuration name of a session is stored in the **ConfigurationName** property of the session.</span></span>

<span data-ttu-id="37676-197">此参数的值用于选择和筛选会话。</span><span class="sxs-lookup"><span data-stu-id="37676-197">The value of this parameter is used to select and filter sessions.</span></span>
<span data-ttu-id="37676-198">它不会更改会话使用的会话配置。</span><span class="sxs-lookup"><span data-stu-id="37676-198">It does not change the session configuration that the session uses.</span></span>

<span data-ttu-id="37676-199">有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="37676-199">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="37676-200">-ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="37676-200">-ConnectionUri</span></span>

<span data-ttu-id="37676-201">为断开连接的会话指定连接终结点的 Uri。</span><span class="sxs-lookup"><span data-stu-id="37676-201">Specifies the URIs of the connection endpoints for the disconnected sessions.</span></span>

<span data-ttu-id="37676-202">URI 必须完全限定。</span><span class="sxs-lookup"><span data-stu-id="37676-202">The URI must be fully qualified.</span></span>
<span data-ttu-id="37676-203">此字符串的格式如下：</span><span class="sxs-lookup"><span data-stu-id="37676-203">The format of this string is as follows:</span></span>

`\<Transport\>://\<ComputerName\>:\<Port\>/\<ApplicationName\>`

<span data-ttu-id="37676-204">默认值如下：</span><span class="sxs-lookup"><span data-stu-id="37676-204">The default value is as follows:</span></span>

`http://localhost:5985/WSMAN`

<span data-ttu-id="37676-205">如果未指定连接 URI，则可以使用 *UseSSL* 和 *Port* 参数指定连接 uri 值。</span><span class="sxs-lookup"><span data-stu-id="37676-205">If you do not specify a connection URI, you can use the *UseSSL* and *Port* parameters to specify the connection URI values.</span></span>

<span data-ttu-id="37676-206">URI 的 **Transport** 段的有效值为 HTTP 和 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37676-206">Valid values for the **Transport** segment of the URI are HTTP and HTTPS.</span></span>
<span data-ttu-id="37676-207">如果使用 Transport 段指定连接 URI，但不指定端口，将使用以下标准端口来创建会话：80 用于 HTTP，443 用于 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="37676-207">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span>
<span data-ttu-id="37676-208">若要使用 Windows PowerShell 远程处理的默认端口，请指定 HTTP 端口 5985 或 HTTPS 端口 5986。</span><span class="sxs-lookup"><span data-stu-id="37676-208">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

<span data-ttu-id="37676-209">如果目标计算机将连接重定向到另一个 URI，Windows PowerShell 将阻止重定向，除非你在命令中使用了 *AllowRedirection* 参数。</span><span class="sxs-lookup"><span data-stu-id="37676-209">If the destination computer redirects the connection to a different URI, Windows PowerShell prevents the redirection unless you use the *AllowRedirection* parameter in the command.</span></span>

```yaml
Type: System.Uri[]
Parameter Sets: ConnectionUri, ConnectionUriGuid
Aliases: URI, CU

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="37676-210">-Credential</span><span class="sxs-lookup"><span data-stu-id="37676-210">-Credential</span></span>

<span data-ttu-id="37676-211">指定有权连接到断开连接的会话的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="37676-211">Specifies a user account that has permission to connect to the disconnected session.</span></span>
<span data-ttu-id="37676-212">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="37676-212">The default is the current user.</span></span>

<span data-ttu-id="37676-213">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="37676-213">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="37676-214">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="37676-214">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="37676-215">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="37676-215">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="37676-216">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="37676-216">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-217">-Id</span><span class="sxs-lookup"><span data-stu-id="37676-217">-Id</span></span>

<span data-ttu-id="37676-218">指定断开连接的会话的 ID。</span><span class="sxs-lookup"><span data-stu-id="37676-218">Specifies the IDs of the disconnected sessions.</span></span>
<span data-ttu-id="37676-219">仅当断开连接的会话之前已连接到当前会话时， *Id* 参数才有效。</span><span class="sxs-lookup"><span data-stu-id="37676-219">The *Id* parameter works only when the disconnected session was previously connected to the current session.</span></span>

<span data-ttu-id="37676-220">如果会话存储在本地计算机上，但未连接到当前会话，则此参数是有效的，但并未生效。</span><span class="sxs-lookup"><span data-stu-id="37676-220">This parameter is valid, but not effective, when the session is stored on the local computer, but was not connected to the current session.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="37676-221">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="37676-221">-InstanceId</span></span>

<span data-ttu-id="37676-222">指定断开连接的会话的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="37676-222">Specifies the instance IDs of the disconnected sessions.</span></span>

<span data-ttu-id="37676-223">实例 ID 是一个 GUID，用于在本地或远程计算机上唯一标识 **PSSession** 。</span><span class="sxs-lookup"><span data-stu-id="37676-223">The instance ID is a GUID that uniquely identifies a **PSSession** on a local or remote computer.</span></span>

<span data-ttu-id="37676-224">实例 ID 存储在 **PSSession** 的 **InstanceID** 属性中。</span><span class="sxs-lookup"><span data-stu-id="37676-224">The instance ID is stored in the **InstanceID** property of the **PSSession** .</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: ComputerNameGuid, ConnectionUriGuid, InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-225">-Name</span><span class="sxs-lookup"><span data-stu-id="37676-225">-Name</span></span>

<span data-ttu-id="37676-226">指定断开连接的会话的友好名称。</span><span class="sxs-lookup"><span data-stu-id="37676-226">Specifies the friendly names of the disconnected sessions.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name, ComputerName, ConnectionUri
Aliases:

Required: True (Name), False (ComputerName, ConnectionUri)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-227">-Port</span><span class="sxs-lookup"><span data-stu-id="37676-227">-Port</span></span>

<span data-ttu-id="37676-228">指定远程计算机上用于重新连接到会话的网络端口。</span><span class="sxs-lookup"><span data-stu-id="37676-228">Specifies the network port on the remote computer that is used to reconnect to the session.</span></span>
<span data-ttu-id="37676-229">若要连接到一台远程计算机，则必须在该连接所用的端口上侦听远程计算机。</span><span class="sxs-lookup"><span data-stu-id="37676-229">To connect to a remote computer, the remote computer must be listening on the port that the connection uses.</span></span>
<span data-ttu-id="37676-230">默认端口为 5985（HTTP 的 WinRM 端口）和 5986（HTTPS 的 WinRM 端口）。</span><span class="sxs-lookup"><span data-stu-id="37676-230">The default ports are 5985, which is the WinRM port for HTTP, and 5986, which is the WinRM port for HTTPS.</span></span>

<span data-ttu-id="37676-231">使用备用端口之前，你必须在远程计算机上配置 WinRM 侦听器，才能在该端口上进行侦听。</span><span class="sxs-lookup"><span data-stu-id="37676-231">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>
<span data-ttu-id="37676-232">若要配置侦听器，请在 Windows PowerShell 提示符下键入以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="37676-232">To configure the listener, type the following two commands at the Windows PowerShell prompt:</span></span>

`Remove-Item -Path WSMan:\Localhost\listener\listener* -Recurse`

`New-Item -Path WSMan:\Localhost\listener -Transport http -Address * -Port \<port-number\>`

<span data-ttu-id="37676-233">除非必要，否则不要使用 *Port* 参数。</span><span class="sxs-lookup"><span data-stu-id="37676-233">Do not use the *Port* parameter unless you must.</span></span>
<span data-ttu-id="37676-234">在命令中设置的端口适用于运行该命令的所有计算机或会话。</span><span class="sxs-lookup"><span data-stu-id="37676-234">The port that is set in the command applies to all computers or sessions on which the command runs.</span></span>
<span data-ttu-id="37676-235">备用端口设置可能会阻止在所有计算机上运行该命令。</span><span class="sxs-lookup"><span data-stu-id="37676-235">An alternate port setting might prevent the command from running on all computers.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ComputerName, ComputerNameGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-236">-Session</span><span class="sxs-lookup"><span data-stu-id="37676-236">-Session</span></span>

<span data-ttu-id="37676-237">指定断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-237">Specifies the disconnected sessions.</span></span>
<span data-ttu-id="37676-238">输入包含 **pssession** 对象的变量或创建或获取 **pssession** 对象的命令，如 Get-PSSession 命令。</span><span class="sxs-lookup"><span data-stu-id="37676-238">Enter a variable that contains the **PSSession** objects or a command that creates or gets the **PSSession** objects, such as a Get-PSSession command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="37676-239">-SessionOption</span><span class="sxs-lookup"><span data-stu-id="37676-239">-SessionOption</span></span>

<span data-ttu-id="37676-240">为该会话指定高级选项。</span><span class="sxs-lookup"><span data-stu-id="37676-240">Specifies advanced options for the session.</span></span>
<span data-ttu-id="37676-241">输入 **SessionOption** 对象（例如使用 New-PSSessionOption cmdlet 创建的对象），或输入哈希表，其中的键是会话选项名称，而值是会话选项值。</span><span class="sxs-lookup"><span data-stu-id="37676-241">Enter a **SessionOption** object, such as one that you create by using the New-PSSessionOption cmdlet, or a hash table in which the keys are session option names and the values are session option values.</span></span>

<span data-ttu-id="37676-242">这些选项的默认值由 $PSSessionOption 首选项变量的值（如果已设置）确定。</span><span class="sxs-lookup"><span data-stu-id="37676-242">The default values for the options are determined by the value of the $PSSessionOption preference variable, if it is set.</span></span>
<span data-ttu-id="37676-243">否则，通过在会话配置中设置的选项创建默认值。</span><span class="sxs-lookup"><span data-stu-id="37676-243">Otherwise, the default values are established by options set in the session configuration.</span></span>

<span data-ttu-id="37676-244">会话选项值优先于在 $PSSessionOption 首选项变量和会话配置中设置的会话的默认值。</span><span class="sxs-lookup"><span data-stu-id="37676-244">The session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span>
<span data-ttu-id="37676-245">但是，它们不优先于在会话配置中设置的最大值、配额或限制。</span><span class="sxs-lookup"><span data-stu-id="37676-245">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span>

<span data-ttu-id="37676-246">有关包括默认值的会话选项的说明，请参阅 PSSessionOption。</span><span class="sxs-lookup"><span data-stu-id="37676-246">For a description of the session options that includes the default values, see New-PSSessionOption.</span></span>
<span data-ttu-id="37676-247">有关 **$PSSessionOption** 首选项变量的信息，请参阅 [about_Preference_Variables](About/about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="37676-247">For information about the **$PSSessionOption** preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="37676-248">有关会话配置的详细信息，请参阅 [about_Session_Configurations](About/about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="37676-248">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

```yaml
Type: System.Management.Automation.Remoting.PSSessionOption
Parameter Sets: ComputerName, ComputerNameGuid, ConnectionUri, ConnectionUriGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-249">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="37676-249">-ThrottleLimit</span></span>

<span data-ttu-id="37676-250">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="37676-250">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="37676-251">如果省略此参数或输入 0 值，则使用默认值 32。</span><span class="sxs-lookup"><span data-stu-id="37676-251">If you omit this parameter or enter a value of 0, the default value, 32, is used.</span></span>

<span data-ttu-id="37676-252">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="37676-252">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-253">-UseSSL</span><span class="sxs-lookup"><span data-stu-id="37676-253">-UseSSL</span></span>

<span data-ttu-id="37676-254">指示此 cmdlet 使用安全套接字层 (SSL) 协议连接到断开连接的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-254">Indicates that this cmdlet uses the Secure Sockets Layer (SSL) protocol to connect to the disconnected session.</span></span> <span data-ttu-id="37676-255">默认情况下，不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="37676-255">By default, SSL is not used.</span></span>

<span data-ttu-id="37676-256">WS-Management 对通过网络传输的所有 Windows PowerShell 内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="37676-256">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span>
<span data-ttu-id="37676-257">*UseSSL* 参数是一种额外的保护措施，它通过 HTTPS 连接而不是 HTTP 连接来发送数据。</span><span class="sxs-lookup"><span data-stu-id="37676-257">The *UseSSL* parameter is an additional protection that sends the data across an HTTPS connection instead of an HTTP connection.</span></span>

<span data-ttu-id="37676-258">如果使用此参数，但 SSL 在用于此命令的端口上不可用，则该命令将失败。</span><span class="sxs-lookup"><span data-stu-id="37676-258">If you use this parameter, but SSL is not available on the port that is used for the command, the command fails.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerName, ComputerNameGuid
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="37676-259">-Confirm</span><span class="sxs-lookup"><span data-stu-id="37676-259">-Confirm</span></span>

<span data-ttu-id="37676-260">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="37676-260">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="37676-261">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="37676-261">-WhatIf</span></span>

<span data-ttu-id="37676-262">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="37676-262">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="37676-263">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="37676-263">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="37676-264">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="37676-264">CommonParameters</span></span>

<span data-ttu-id="37676-265">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="37676-265">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="37676-266">有关详细信息，请参阅 about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216) 。</span><span class="sxs-lookup"><span data-stu-id="37676-266">For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="37676-267">输入</span><span class="sxs-lookup"><span data-stu-id="37676-267">INPUTS</span></span>

### <span data-ttu-id="37676-268">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-268">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="37676-269">可以通过管道将会话 ( **PSSession** ) 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="37676-269">You can pipe a session ( **PSSession** ) to this cmdlet.</span></span>

## <span data-ttu-id="37676-270">输出</span><span class="sxs-lookup"><span data-stu-id="37676-270">OUTPUTS</span></span>

### <span data-ttu-id="37676-271">System.Management.Automation.Runspaces.PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-271">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="37676-272">此 cmdlet 将返回一个对象，该对象表示其重新连接到的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-272">This cmdlet returns an object that represents the session to which it reconnected.</span></span>

## <span data-ttu-id="37676-273">注释</span><span class="sxs-lookup"><span data-stu-id="37676-273">NOTES</span></span>

* <span data-ttu-id="37676-274">**Connect-PSSession** 仅重新连接到已断开连接的会话，即， **状态** 属性的值为 "已断开连接" 的会话。</span><span class="sxs-lookup"><span data-stu-id="37676-274">**Connect-PSSession** reconnects only to sessions that are disconnected, that is, sessions that have a value of Disconnected for the **State** property.</span></span> <span data-ttu-id="37676-275">只有连接到或结束运行 Windows PowerShell 3.0 或更高版本的计算机的会话才能断开和重新连接。</span><span class="sxs-lookup"><span data-stu-id="37676-275">Only sessions that are connected to, or end at, computers that run Windows PowerShell 3.0 or later versions can be disconnected and reconnected.</span></span>
* <span data-ttu-id="37676-276">如果在未断开连接的会话上使用 **Connect-PSSession** ，则该命令不会影响会话，并且不会生成错误。</span><span class="sxs-lookup"><span data-stu-id="37676-276">If you use **Connect-PSSession** on a session that is not disconnected, the command does not affect the session and it does not generate errors.</span></span>
* <span data-ttu-id="37676-277">与使用 *EnableNetworkAccess* 参数创建的交互式令牌断开连接的环回会话只能通过创建该会话的计算机重新连接。</span><span class="sxs-lookup"><span data-stu-id="37676-277">Disconnected loopback sessions with interactive tokens, which are created by using the *EnableNetworkAccess* parameter, can be reconnected only from the computer on which the session was created.</span></span> <span data-ttu-id="37676-278">此限制可使计算机免遭恶意访问。</span><span class="sxs-lookup"><span data-stu-id="37676-278">This restriction protects the computer from malicious access.</span></span>
* <span data-ttu-id="37676-279">**PSSession** 的 **State** 属性值相对于当前会话。</span><span class="sxs-lookup"><span data-stu-id="37676-279">The value of the **State** property of a **PSSession** is relative to the current session.</span></span>
<span data-ttu-id="37676-280">因此，值 "已 **断开连接** " 意味着 **PSSession** 未连接到当前会话。</span><span class="sxs-lookup"><span data-stu-id="37676-280">Therefore, a value of **Disconnected** means that the **PSSession** is not connected to the current session.</span></span> <span data-ttu-id="37676-281">但是，它并不意味着 **PSSession** 会与所有会话断开连接。</span><span class="sxs-lookup"><span data-stu-id="37676-281">However, it does not mean that the **PSSession** is disconnected from all sessions.</span></span> <span data-ttu-id="37676-282">它可能连接到另一个会话。</span><span class="sxs-lookup"><span data-stu-id="37676-282">It might be connected to a different session.</span></span> <span data-ttu-id="37676-283">若要确定是否可以连接或重新连接到该会话，请使用 **Availability** 属性。</span><span class="sxs-lookup"><span data-stu-id="37676-283">To determine whether you can connect or reconnect to the session, use the **Availability** property.</span></span>

  <span data-ttu-id="37676-284">**Availability** 的 None 值指示可连接会话。</span><span class="sxs-lookup"><span data-stu-id="37676-284">An **Availability** value of None indicates that you can connect to the session.</span></span>
<span data-ttu-id="37676-285">值为 "忙碌" 指示你无法连接到 **PSSession** ，因为它已连接到另一个会话。</span><span class="sxs-lookup"><span data-stu-id="37676-285">A value of Busy indicates that you cannot connect to the **PSSession** because it is connected to another session.</span></span>

  <span data-ttu-id="37676-286">有关会话 **状态** 属性的值的详细信息，请参阅 MSDN library 中的 [RunspaceState 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) 。</span><span class="sxs-lookup"><span data-stu-id="37676-286">For more information about the values of the **State** property of sessions, see [RunspaceState Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspacestate) in the MSDN library.</span></span>

  <span data-ttu-id="37676-287">有关会话的 **可用性** 属性值的详细信息，请参阅 MSDN 库中的 [runspacestate 枚举](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) 。</span><span class="sxs-lookup"><span data-stu-id="37676-287">For more information about the values of the **Availability** property of sessions, see [RunspaceAvailability Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.runspaceavailability) in the MSDN library.</span></span>

* <span data-ttu-id="37676-288">当你连接到 **pssession** 时，你无法更改 **PSSession** 的空闲超时值。</span><span class="sxs-lookup"><span data-stu-id="37676-288">You cannot change the idle time-out value of a **PSSession** when you connect to the **PSSession** .</span></span> <span data-ttu-id="37676-289">**Connect-PSSession** 的 *SessionOption* 参数采用值为 **IdleTimeout** 的 **SessionOption** 对象。</span><span class="sxs-lookup"><span data-stu-id="37676-289">The *SessionOption* parameter of **Connect-PSSession** takes a **SessionOption** object that has an **IdleTimeout** value.</span></span> <span data-ttu-id="37676-290">但是，在连接到 **PSSession** 时，将忽略 **SessionOption** 对象的 **idletimeout** 值和 $PSSessionOption 变量的 **idletimeout** 值。</span><span class="sxs-lookup"><span data-stu-id="37676-290">However, the **IdleTimeout** value of the **SessionOption** object and the **IdleTimeout** value of the $PSSessionOption variable are ignored when connecting to a **PSSession** .</span></span>

  <span data-ttu-id="37676-291">您可以在创建 **pssession** 时，通过使用 **新的 Pssession** 或 **调用命令** cmdlet 以及从 **PSSession** 断开连接来设置和更改 **pssession** 的空闲超时。</span><span class="sxs-lookup"><span data-stu-id="37676-291">You can set and change the idle time-out of a **PSSession** when you create the **PSSession** , by using the **New-PSSession** or **Invoke-Command** cmdlets, and when you disconnect from the **PSSession** .</span></span>

  <span data-ttu-id="37676-292">**PSSession** 的 **IdleTimeout** 属性对断开连接的会话至关重要，因为它确定断开连接的会话在远程计算机上保留的时间。</span><span class="sxs-lookup"><span data-stu-id="37676-292">The **IdleTimeout** property of a **PSSession** is critical to disconnected sessions, because it determines how long a disconnected session is maintained on the remote computer.</span></span>
<span data-ttu-id="37676-293">断开连接的会话从其断开连接的时刻起就被视为空闲，即使命令正在断开连接的会话中运行也是如此。</span><span class="sxs-lookup"><span data-stu-id="37676-293">Disconnected sessions are considered to be idle from the moment that they are disconnected, even if commands are running in the disconnected session.</span></span>

## <span data-ttu-id="37676-294">相关链接</span><span class="sxs-lookup"><span data-stu-id="37676-294">RELATED LINKS</span></span>

[<span data-ttu-id="37676-295">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-295">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="37676-296">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-296">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="37676-297">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-297">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="37676-298">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-298">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="37676-299">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="37676-299">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="37676-300">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-300">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="37676-301">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="37676-301">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="37676-302">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="37676-302">New-PSTransportOption</span></span>](New-PSTransportOption.md)

[<span data-ttu-id="37676-303">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-303">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="37676-304">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="37676-304">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="37676-305">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="37676-305">Remove-PSSession</span></span>](Remove-PSSession.md)
