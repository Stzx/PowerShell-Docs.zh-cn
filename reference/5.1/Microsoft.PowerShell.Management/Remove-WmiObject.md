---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198066"
---
# <span data-ttu-id="18d8d-103">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="18d8d-103">Remove-WmiObject</span></span>

## <span data-ttu-id="18d8d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="18d8d-104">SYNOPSIS</span></span>
<span data-ttu-id="18d8d-105">删除现有 Windows Management Instrumentation (WMI) 类的实例。</span><span class="sxs-lookup"><span data-stu-id="18d8d-105">Deletes an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="18d8d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="18d8d-106">SYNTAX</span></span>

### <span data-ttu-id="18d8d-107">class（默认值）</span><span class="sxs-lookup"><span data-stu-id="18d8d-107">class (Default)</span></span>

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="18d8d-108">对象 (object)</span><span class="sxs-lookup"><span data-stu-id="18d8d-108">object</span></span>

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="18d8d-109">path</span><span class="sxs-lookup"><span data-stu-id="18d8d-109">path</span></span>

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="18d8d-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="18d8d-110">WQLQuery</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="18d8d-111">query</span><span class="sxs-lookup"><span data-stu-id="18d8d-111">query</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="18d8d-112">list</span><span class="sxs-lookup"><span data-stu-id="18d8d-112">list</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="18d8d-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="18d8d-113">DESCRIPTION</span></span>
<span data-ttu-id="18d8d-114">**Get-wmiobject** cmdlet 删除现有 WINDOWS MANAGEMENT INSTRUMENTATION (WMI) 类的实例。</span><span class="sxs-lookup"><span data-stu-id="18d8d-114">The **Remove-WmiObject** cmdlet deletes an instance of an existing Windows Management Instrumentation (WMI)class.</span></span>

## <span data-ttu-id="18d8d-115">示例</span><span class="sxs-lookup"><span data-stu-id="18d8d-115">EXAMPLES</span></span>

### <span data-ttu-id="18d8d-116">示例1：关闭 Win32 进程的所有实例</span><span class="sxs-lookup"><span data-stu-id="18d8d-116">Example 1: Close all instances of a Win32 process</span></span>

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

<span data-ttu-id="18d8d-117">此示例将关闭 Notepad.exe 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="18d8d-117">This example closes all the instances of Notepad.exe.</span></span>

<span data-ttu-id="18d8d-118">第一条命令启动记事本的实例。</span><span class="sxs-lookup"><span data-stu-id="18d8d-118">The first command starts an instance of Notepad.</span></span>

<span data-ttu-id="18d8d-119">第二个命令使用 Get-WmiObject cmdlet 来检索与 Notepad.exe 对应的 Win32_Process 的实例，然后将它们存储在 $np 变量中。</span><span class="sxs-lookup"><span data-stu-id="18d8d-119">The second command uses the Get-WmiObject cmdlet to retrieve the instances of the Win32_Process that correspond to Notepad.exe, and then stores them in the $np variable.</span></span>

<span data-ttu-id="18d8d-120">第三个命令将 $np 变量中的对象传递给 **get-wmiobject** ，后者将删除 Notepad.exe 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="18d8d-120">The third command passes the object in the $np variable to **Remove-WmiObject** , which deletes all the instances of Notepad.exe.</span></span>

### <span data-ttu-id="18d8d-121">示例2：删除文件夹</span><span class="sxs-lookup"><span data-stu-id="18d8d-121">Example 2: Delete a folder</span></span>

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

<span data-ttu-id="18d8d-122">此命令删除 C:\Test 文件夹。</span><span class="sxs-lookup"><span data-stu-id="18d8d-122">This command deletes the C:\Test folder.</span></span>

<span data-ttu-id="18d8d-123">第一个命令使用 **get-wmiobject** 查询 C:\Test 文件夹，然后将该对象存储在 $a 变量中。</span><span class="sxs-lookup"><span data-stu-id="18d8d-123">The first command uses **Get-WMIObject** to query for the C:\Test folder, and then stores the object in the $a variable.</span></span>

<span data-ttu-id="18d8d-124">第二个命令通过管道将 $a 变量传递给 **get-wmiobject** ，后者将删除该文件夹。</span><span class="sxs-lookup"><span data-stu-id="18d8d-124">The second command pipes the $a variable to **Remove-WMIObject** , which deletes the folder.</span></span>

## <span data-ttu-id="18d8d-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="18d8d-125">PARAMETERS</span></span>

### <span data-ttu-id="18d8d-126">-AsJob</span><span class="sxs-lookup"><span data-stu-id="18d8d-126">-AsJob</span></span>
<span data-ttu-id="18d8d-127">指示此 cmdlet 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="18d8d-127">Indicates that this cmdlet run as a background job.</span></span>
<span data-ttu-id="18d8d-128">使用此参数可运行需要较长时间才能完成的命令。</span><span class="sxs-lookup"><span data-stu-id="18d8d-128">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="18d8d-129">Windows PowerShell 3.0 中引入的新 CIM cmdlet 执行与 WMI cmdlet 相同的任务。</span><span class="sxs-lookup"><span data-stu-id="18d8d-129">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="18d8d-130">CIM cmdlet 符合 WS-Management (WSMan) 标准和通用信息模型 (CIM) 标准，这使 cmdlet 能够使用相同的技术来管理运行 Windows 操作系统的计算机和运行其他操作系统的计算机。</span><span class="sxs-lookup"><span data-stu-id="18d8d-130">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those running other operating systems.</span></span>
<span data-ttu-id="18d8d-131">建议不要使用 **Remove-WmiObject** ，而考虑使用 Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="18d8d-131">Instead of using **Remove-WmiObject** , consider using the Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 cmdlet.</span></span>

<span data-ttu-id="18d8d-132">使用 *AsJob* 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="18d8d-132">When you use the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="18d8d-133">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="18d8d-133">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="18d8d-134">如果将 **Remove-WmiObject** 用于远程计算机，则会在本地计算机上创建相应作业，并且来自远程计算机的结果将自动返回至本地计算机。</span><span class="sxs-lookup"><span data-stu-id="18d8d-134">If **Remove-WmiObject** is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="18d8d-135">若要 **管理作业，** 请使用包含 **job 名词)  (的 cmdlet** 。</span><span class="sxs-lookup"><span data-stu-id="18d8d-135">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="18d8d-136">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="18d8d-136">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="18d8d-137">若要将此参数用于远程计算机，必须为本地和远程计算机配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="18d8d-137">To use this parameter for remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="18d8d-138">使用 "以管理员身份运行" 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="18d8d-138">Start Windows PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="18d8d-139">有关详细信息，请参阅 about_Remote_Requirements。</span><span class="sxs-lookup"><span data-stu-id="18d8d-139">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="18d8d-140">有关 Windows PowerShell 后台作业的详细信息，请参阅 about_Jobs 和 about_Remote_Jobs。</span><span class="sxs-lookup"><span data-stu-id="18d8d-140">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="18d8d-141">-Authentication</span><span class="sxs-lookup"><span data-stu-id="18d8d-141">-Authentication</span></span>
<span data-ttu-id="18d8d-142">指定用于 WMI 连接的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="18d8d-142">Specifies the authentication level to use for the WMI connection.</span></span>
<span data-ttu-id="18d8d-143">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="18d8d-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="18d8d-144">-1：保持不变。</span><span class="sxs-lookup"><span data-stu-id="18d8d-144">-1: Unchanged.</span></span>
- <span data-ttu-id="18d8d-145">0：Default。</span><span class="sxs-lookup"><span data-stu-id="18d8d-145">0: Default.</span></span>
- <span data-ttu-id="18d8d-146">1：无。</span><span class="sxs-lookup"><span data-stu-id="18d8d-146">1: None.</span></span>
<span data-ttu-id="18d8d-147">未执行任何身份验证。</span><span class="sxs-lookup"><span data-stu-id="18d8d-147">No authentication in performed.</span></span>
- <span data-ttu-id="18d8d-148">2：连接。</span><span class="sxs-lookup"><span data-stu-id="18d8d-148">2: Connect.</span></span>
<span data-ttu-id="18d8d-149">仅当客户端与应用程序建立了关系时才执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="18d8d-149">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="18d8d-150">3：调用。</span><span class="sxs-lookup"><span data-stu-id="18d8d-150">3: Call.</span></span>
<span data-ttu-id="18d8d-151">仅当应用程序接收到请求时，才会在每次调用开始时执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="18d8d-151">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="18d8d-152">4：数据包。</span><span class="sxs-lookup"><span data-stu-id="18d8d-152">4: Packet.</span></span>
<span data-ttu-id="18d8d-153">对从客户端收到的所有数据执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="18d8d-153">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="18d8d-154">5： PacketIntegrity。</span><span class="sxs-lookup"><span data-stu-id="18d8d-154">5: PacketIntegrity.</span></span>
<span data-ttu-id="18d8d-155">在客户端和应用程序之间传输的所有数据都经过身份验证和验证。</span><span class="sxs-lookup"><span data-stu-id="18d8d-155">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="18d8d-156">6： PacketPrivacy。</span><span class="sxs-lookup"><span data-stu-id="18d8d-156">6: PacketPrivacy.</span></span>
<span data-ttu-id="18d8d-157">使用其他身份验证级别的属性，并对所有数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="18d8d-157">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-158">-Authority</span><span class="sxs-lookup"><span data-stu-id="18d8d-158">-Authority</span></span>
<span data-ttu-id="18d8d-159">指定用于对 WMI 连接进行身份验证的授权机构。</span><span class="sxs-lookup"><span data-stu-id="18d8d-159">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="18d8d-160">可以指定标准 NTLM 或 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="18d8d-160">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="18d8d-161">若要使用 NTLM，请将授权机构设置设为“ntlmdomain:\<DomainName\>”，其中 \<DomainName\> 标识有效的 NTLM 域名。</span><span class="sxs-lookup"><span data-stu-id="18d8d-161">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="18d8d-162">若要使用 Kerberos，请指定 kerberos： \<DomainName\> \\ \<ServerName\> 。</span><span class="sxs-lookup"><span data-stu-id="18d8d-162">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="18d8d-163">连接到本地计算机时不能包含授权机构设置。</span><span class="sxs-lookup"><span data-stu-id="18d8d-163">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-164">-Class</span><span class="sxs-lookup"><span data-stu-id="18d8d-164">-Class</span></span>
<span data-ttu-id="18d8d-165">指定此 cmdlet 删除的 WMI 类的名称。</span><span class="sxs-lookup"><span data-stu-id="18d8d-165">Specifies the name of a WMI class that this cmdlet deletes.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-166">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="18d8d-166">-ComputerName</span></span>
<span data-ttu-id="18d8d-167">指定在其上运行此 cmdlet 的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="18d8d-167">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="18d8d-168">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="18d8d-168">The default is the local computer.</span></span>

<span data-ttu-id="18d8d-169">键入一台或多台计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="18d8d-169">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="18d8d-170">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="18d8d-170">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="18d8d-171">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="18d8d-171">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="18d8d-172">即使你的计算机未配置为运行远程命令，你也可以使用 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="18d8d-172">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="18d8d-173">-Credential</span></span>
<span data-ttu-id="18d8d-174">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="18d8d-174">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="18d8d-175">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="18d8d-175">The default is the current user.</span></span>

<span data-ttu-id="18d8d-176">键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如 Get-Credential cmdlet 生成的一个 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="18d8d-176">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="18d8d-177">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="18d8d-177">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-178">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="18d8d-178">-EnableAllPrivileges</span></span>
<span data-ttu-id="18d8d-179">指示此 cmdlet 在执行 WMI 调用的命令之前启用当前用户的所有权限。</span><span class="sxs-lookup"><span data-stu-id="18d8d-179">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-180">-Impersonation</span><span class="sxs-lookup"><span data-stu-id="18d8d-180">-Impersonation</span></span>
<span data-ttu-id="18d8d-181">指定要使用的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="18d8d-181">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="18d8d-182">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="18d8d-182">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="18d8d-183">0：Default。</span><span class="sxs-lookup"><span data-stu-id="18d8d-183">0: Default.</span></span>
<span data-ttu-id="18d8d-184">读取默认模拟级别的本地注册表，通常设置为 "3：模拟"。</span><span class="sxs-lookup"><span data-stu-id="18d8d-184">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="18d8d-185">1：Anonymous。</span><span class="sxs-lookup"><span data-stu-id="18d8d-185">1: Anonymous.</span></span>
<span data-ttu-id="18d8d-186">隐藏调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="18d8d-186">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="18d8d-187">2：Identify。</span><span class="sxs-lookup"><span data-stu-id="18d8d-187">2: Identify.</span></span>
<span data-ttu-id="18d8d-188">允许对象查询调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="18d8d-188">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="18d8d-189">3：Impersonate。</span><span class="sxs-lookup"><span data-stu-id="18d8d-189">3: Impersonate.</span></span>
<span data-ttu-id="18d8d-190">允许对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="18d8d-190">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="18d8d-191">4：Delegate。</span><span class="sxs-lookup"><span data-stu-id="18d8d-191">4: Delegate.</span></span>
<span data-ttu-id="18d8d-192">允许对象允许其他对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="18d8d-192">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-193">-InputObject</span><span class="sxs-lookup"><span data-stu-id="18d8d-193">-InputObject</span></span>
<span data-ttu-id="18d8d-194">指定要用作输入的 **system.management.managementobject** 对象。</span><span class="sxs-lookup"><span data-stu-id="18d8d-194">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="18d8d-195">使用此参数时，将忽略所有其他参数。</span><span class="sxs-lookup"><span data-stu-id="18d8d-195">When this parameter is used, all other parameters are ignored.</span></span>

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-196">-Locale</span><span class="sxs-lookup"><span data-stu-id="18d8d-196">-Locale</span></span>
<span data-ttu-id="18d8d-197">指定 WMI 对象的首选区域设置。</span><span class="sxs-lookup"><span data-stu-id="18d8d-197">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="18d8d-198">按首选顺序将 *Locale* 参数指定为 MS_ 格式的数组 \<LCID\> 。</span><span class="sxs-lookup"><span data-stu-id="18d8d-198">The *Locale* parameter is specified as an array in the MS_\<LCID\> format in the preferred order.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-199">-Namespace</span><span class="sxs-lookup"><span data-stu-id="18d8d-199">-Namespace</span></span>
<span data-ttu-id="18d8d-200">指定在与 *class* 参数一起使用时所引用的 wmi 类所在的 wmi 存储库命名空间。</span><span class="sxs-lookup"><span data-stu-id="18d8d-200">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-201">-Path</span><span class="sxs-lookup"><span data-stu-id="18d8d-201">-Path</span></span>
<span data-ttu-id="18d8d-202">指定 WMI 类的 WMI 对象路径，或指定要删除的 WMI 类实例的 WMI 对象路径。</span><span class="sxs-lookup"><span data-stu-id="18d8d-202">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class to delete.</span></span>

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="18d8d-203">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="18d8d-203">-ThrottleLimit</span></span>
<span data-ttu-id="18d8d-204">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="18d8d-204">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="18d8d-205">此参数与 *AsJob* 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="18d8d-205">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="18d8d-206">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="18d8d-206">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="18d8d-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="18d8d-207">-Confirm</span></span>
<span data-ttu-id="18d8d-208">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="18d8d-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="18d8d-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="18d8d-209">-WhatIf</span></span>
<span data-ttu-id="18d8d-210">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="18d8d-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="18d8d-211">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="18d8d-211">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="18d8d-212">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="18d8d-212">CommonParameters</span></span>
<span data-ttu-id="18d8d-213">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="18d8d-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="18d8d-214">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="18d8d-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="18d8d-215">输入</span><span class="sxs-lookup"><span data-stu-id="18d8d-215">INPUTS</span></span>

### <span data-ttu-id="18d8d-216">System.Management.ManagementObject</span><span class="sxs-lookup"><span data-stu-id="18d8d-216">System.Management.ManagementObject</span></span>
<span data-ttu-id="18d8d-217">可以通过管道将管理对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="18d8d-217">You can pipe a management object to this cmdlet.</span></span>

## <span data-ttu-id="18d8d-218">输出</span><span class="sxs-lookup"><span data-stu-id="18d8d-218">OUTPUTS</span></span>

### <span data-ttu-id="18d8d-219">System.management.automation.remotingjob （无）</span><span class="sxs-lookup"><span data-stu-id="18d8d-219">None, System.Management.Automation.RemotingJob</span></span>
<span data-ttu-id="18d8d-220">如果指定 *AsJob* 参数，则此 cmdlet 将返回一个作业对象。</span><span class="sxs-lookup"><span data-stu-id="18d8d-220">This cmdlet returns a job object, if you specify the *AsJob* parameter.</span></span>
<span data-ttu-id="18d8d-221">否则，将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="18d8d-221">Otherwise, it does not generate any output.</span></span>

## <span data-ttu-id="18d8d-222">注释</span><span class="sxs-lookup"><span data-stu-id="18d8d-222">NOTES</span></span>

## <span data-ttu-id="18d8d-223">相关链接</span><span class="sxs-lookup"><span data-stu-id="18d8d-223">RELATED LINKS</span></span>

[<span data-ttu-id="18d8d-224">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="18d8d-224">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="18d8d-225">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="18d8d-225">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="18d8d-226">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="18d8d-226">Set-WmiInstance</span></span>](Set-WmiInstance.md)
