---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "93198928"
---
# <span data-ttu-id="78555-103">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="78555-103">Invoke-WmiMethod</span></span>

## <span data-ttu-id="78555-104">摘要</span><span class="sxs-lookup"><span data-stu-id="78555-104">SYNOPSIS</span></span>
<span data-ttu-id="78555-105">调用 WMI 方法。</span><span class="sxs-lookup"><span data-stu-id="78555-105">Calls WMI methods.</span></span>

## <span data-ttu-id="78555-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="78555-106">SYNTAX</span></span>

### <span data-ttu-id="78555-107">class（默认值）</span><span class="sxs-lookup"><span data-stu-id="78555-107">class (Default)</span></span>

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="78555-108">对象 (object)</span><span class="sxs-lookup"><span data-stu-id="78555-108">object</span></span>

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="78555-109">path</span><span class="sxs-lookup"><span data-stu-id="78555-109">path</span></span>

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="78555-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="78555-110">WQLQuery</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="78555-111">query</span><span class="sxs-lookup"><span data-stu-id="78555-111">query</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="78555-112">list</span><span class="sxs-lookup"><span data-stu-id="78555-112">list</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="78555-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78555-113">DESCRIPTION</span></span>

<span data-ttu-id="78555-114">`Invoke-WmiMethod`Cmdlet 将调用 Windows Management Instrumentation 的方法 (WMI) 对象。</span><span class="sxs-lookup"><span data-stu-id="78555-114">The `Invoke-WmiMethod` cmdlet calls the methods of Windows Management Instrumentation (WMI) objects.</span></span>

<span data-ttu-id="78555-115">Windows PowerShell 3.0 中引入的新通用信息模型 (CIM) cmdlet 执行与 WMI cmdlet 相同的任务。</span><span class="sxs-lookup"><span data-stu-id="78555-115">New Common Information Model (CIM) cmdlets, introduced in Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="78555-116">CIM cmdlet 符合 WS-Management (WSMan) 标准以及 CIM 标准，这使 cmdlet 能够使用相同的技术来管理 Windows 计算机和运行其他操作系统的计算机。</span><span class="sxs-lookup"><span data-stu-id="78555-116">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage Windows computers and those running other operating systems.</span></span> <span data-ttu-id="78555-117">请不要使用 `Invoke-WmiMethod` ，而应考虑使用 [invoke-cimmethod](../cimcmdlets/invoke-cimmethod.md)。</span><span class="sxs-lookup"><span data-stu-id="78555-117">Instead of using `Invoke-WmiMethod`, consider using [Invoke-CimMethod](../cimcmdlets/invoke-cimmethod.md).</span></span>

## <span data-ttu-id="78555-118">示例</span><span class="sxs-lookup"><span data-stu-id="78555-118">EXAMPLES</span></span>

### <span data-ttu-id="78555-119">示例1：列出 WMI 对象的所需顺序</span><span class="sxs-lookup"><span data-stu-id="78555-119">Example 1: List the required order of WMI objects</span></span>

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

<span data-ttu-id="78555-120">此命令按所需的顺序列出对象。</span><span class="sxs-lookup"><span data-stu-id="78555-120">This command lists the required order of the objects.</span></span> <span data-ttu-id="78555-121">若要在 PowerShell 3.0 中调用 WMI，则与备用方法不同，并要求对象值以特定的顺序输入。</span><span class="sxs-lookup"><span data-stu-id="78555-121">To invoke WMI in PowerShell 3.0 differs from alternate methods, and requires that object values are entered in a specific order.</span></span>

### <span data-ttu-id="78555-122">示例2：启动应用程序的实例</span><span class="sxs-lookup"><span data-stu-id="78555-122">Example 2: Start an instance of an application</span></span>

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

<span data-ttu-id="78555-123">此命令通过调用 Win32_Process 类的方法来启动记事本的实例 `Create` 。 **Win32_Process**</span><span class="sxs-lookup"><span data-stu-id="78555-123">This command starts an instance of Notepad by calling the `Create` method of the **Win32_Process** class.</span></span>

<span data-ttu-id="78555-124">使用0填充 **ReturnValue** 属性，并使用一个 (整数填充 **ProcessId** 属性，如果该命令已完成，则) 下一个进程 ID 号。</span><span class="sxs-lookup"><span data-stu-id="78555-124">The **ReturnValue** property is populated with a 0, and the **ProcessId** property is populated with an integer (the next process ID number) if the command is completed.</span></span>

### <span data-ttu-id="78555-125">示例3：重命名文件</span><span class="sxs-lookup"><span data-stu-id="78555-125">Example 3: Rename a file</span></span>

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

<span data-ttu-id="78555-126">此命令重命名文件。</span><span class="sxs-lookup"><span data-stu-id="78555-126">This command renames a file.</span></span> <span data-ttu-id="78555-127">它使用 **Path** 参数来引用 **CIM_DataFile** 类的实例。</span><span class="sxs-lookup"><span data-stu-id="78555-127">It uses the **Path** parameter to reference an instance of the **CIM_DataFile** class.</span></span> <span data-ttu-id="78555-128">然后，它将 Rename 方法应用于该特定实例。</span><span class="sxs-lookup"><span data-stu-id="78555-128">Then, it applies the Rename method to that particular instance.</span></span>

<span data-ttu-id="78555-129">如果命令完成，则使用0填充 **ReturnValue** 属性。</span><span class="sxs-lookup"><span data-stu-id="78555-129">The **ReturnValue** property is populated with a 0 if the command is completed.</span></span>

### <span data-ttu-id="78555-130">示例4：使用传递值数组 `-ArgumentList`</span><span class="sxs-lookup"><span data-stu-id="78555-130">Example 4: Passing an array of values using `-ArgumentList`</span></span>

<span data-ttu-id="78555-131">使用后跟值的对象数组的示例 `$binSD` `$null` 。</span><span class="sxs-lookup"><span data-stu-id="78555-131">An example using an array of objects `$binSD` followed by a `$null` value.</span></span>

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## <span data-ttu-id="78555-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="78555-132">PARAMETERS</span></span>

### <span data-ttu-id="78555-133">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="78555-133">-ArgumentList</span></span>

<span data-ttu-id="78555-134">指定要传递给被调用方法的参数。</span><span class="sxs-lookup"><span data-stu-id="78555-134">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="78555-135">此参数的值必须是对象的数组，并且必须以所调用方法所需的顺序出现。</span><span class="sxs-lookup"><span data-stu-id="78555-135">The value of this parameter must be an array of objects, and they must appear in the order required by the called method.</span></span> <span data-ttu-id="78555-136">`Invoke-CimCommand`Cmdlet 没有这些限制。</span><span class="sxs-lookup"><span data-stu-id="78555-136">The `Invoke-CimCommand` cmdlet does not have these limitations.</span></span>

<span data-ttu-id="78555-137">若要确定这些对象的列出顺序，请运行 `GetMethodParameters()` WMI 类上的方法，如本主题末尾附近的示例1中所示。</span><span class="sxs-lookup"><span data-stu-id="78555-137">To determine the order in which to list those objects, run the `GetMethodParameters()` method on the WMI class, as illustrated in Example 1, near the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78555-138">如果第一个值为包含多个元素的数组，则要求第二个值为 $null。</span><span class="sxs-lookup"><span data-stu-id="78555-138">If the first value is an array that contains more than one element, a second value of $null is required.</span></span> <span data-ttu-id="78555-139">否则，该命令将生成一个错误，例如“Unable to cast object of type 'System.Byte' to type 'System.Array'.”。</span><span class="sxs-lookup"><span data-stu-id="78555-139">Otherwise, the command generates an error, such as "Unable to cast object of type 'System.Byte' to type 'System.Array'.".</span></span> <span data-ttu-id="78555-140">请参阅上面的示例4。</span><span class="sxs-lookup"><span data-stu-id="78555-140">See example 4 above.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="78555-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="78555-141">-AsJob</span></span>

<span data-ttu-id="78555-142">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="78555-142">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="78555-143">使用此参数可运行需要较长时间才能完成的命令。</span><span class="sxs-lookup"><span data-stu-id="78555-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="78555-144">使用 **AsJob** 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="78555-144">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="78555-145">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="78555-145">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="78555-146">如果 `Invoke-WmiMethod` 对远程计算机使用，则在本地计算机上创建作业，远程计算机的结果将自动返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="78555-146">If `Invoke-WmiMethod` is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="78555-147">若要管理作业，请使用包含 Job 名词的 cmdlet (Job cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="78555-147">To manage the job, use the cmdlets that contain the Job noun (the Job cmdlets).</span></span> <span data-ttu-id="78555-148">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78555-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="78555-149">若要将此参数用于远程计算机，必须为本地和远程计算机配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="78555-149">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="78555-150">此外，您必须使用 Windows Vista 和更高版本的 Windows 中的 "以管理员身份运行" 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="78555-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="78555-151">有关详细信息，请参阅 about_Remote_Requirements。</span><span class="sxs-lookup"><span data-stu-id="78555-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="78555-152">有关 Windows PowerShell 后台作业的详细信息，请参阅 about_Jobs 和 about_Remote_Jobs。</span><span class="sxs-lookup"><span data-stu-id="78555-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="78555-153">-Authentication</span><span class="sxs-lookup"><span data-stu-id="78555-153">-Authentication</span></span>

<span data-ttu-id="78555-154">指定用于 WMI 连接的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="78555-154">Specifies the authentication level to be used with the WMI connection.</span></span> <span data-ttu-id="78555-155">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="78555-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="78555-156">-1：Unchanged</span><span class="sxs-lookup"><span data-stu-id="78555-156">-1: Unchanged</span></span>
- <span data-ttu-id="78555-157">0：Default</span><span class="sxs-lookup"><span data-stu-id="78555-157">0: Default</span></span>
- <span data-ttu-id="78555-158">1：None（不执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="78555-158">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="78555-159">2：Connect（仅当客户端与应用程序建立了关系时才执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="78555-159">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="78555-160">3：Call（应用程序收到请求时只在每次调用的开始执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="78555-160">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="78555-161">4：Packet（对从客户端收到的所有数据执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="78555-161">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="78555-162">5： PacketIntegrity (在客户端和应用程序之间传输的所有数据都经过身份验证和验证。 ) </span><span class="sxs-lookup"><span data-stu-id="78555-162">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="78555-163">6：PacketPrivacy（使用其他身份验证等级的属性，并且所有数据都加密。）</span><span class="sxs-lookup"><span data-stu-id="78555-163">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

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

### <span data-ttu-id="78555-164">-Authority</span><span class="sxs-lookup"><span data-stu-id="78555-164">-Authority</span></span>

<span data-ttu-id="78555-165">指定用于对 WMI 连接进行身份验证的授权机构。</span><span class="sxs-lookup"><span data-stu-id="78555-165">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="78555-166">可以指定标准的 Windows NT LAN 管理器 (NTLM) 或 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="78555-166">You can specify standard Windows NT LAN Manager (NTLM) or Kerberos authentication.</span></span> <span data-ttu-id="78555-167">若要使用 NTLM，请将授权机构设置设为“ntlmdomain:\<DomainName\>”，其中 \<DomainName\> 标识有效的 NTLM 域名。</span><span class="sxs-lookup"><span data-stu-id="78555-167">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span> <span data-ttu-id="78555-168">若要使用 Kerberos，请指定 kerberos:\<DomainName\ServerName\>。</span><span class="sxs-lookup"><span data-stu-id="78555-168">To use Kerberos, specify kerberos:\<DomainName\ServerName\>.</span></span> <span data-ttu-id="78555-169">连接到本地计算机时不能包含授权机构设置。</span><span class="sxs-lookup"><span data-stu-id="78555-169">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="78555-170">-Class</span><span class="sxs-lookup"><span data-stu-id="78555-170">-Class</span></span>

<span data-ttu-id="78555-171">指定包含要调用的静态方法的 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="78555-171">Specifies the WMI class that contains a static method to call.</span></span>

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

### <span data-ttu-id="78555-172">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="78555-172">-ComputerName</span></span>

<span data-ttu-id="78555-173">以字符串数组的形式指定此 cmdlet 在其上运行命令的计算机。</span><span class="sxs-lookup"><span data-stu-id="78555-173">Specifies, as a string array, the computers that this cmdlet runs the command on.</span></span> <span data-ttu-id="78555-174">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="78555-174">The default is the local computer.</span></span>

<span data-ttu-id="78555-175">键入一台或多台计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="78555-175">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span> <span data-ttu-id="78555-176">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="78555-176">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="78555-177">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="78555-177">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="78555-178">即使你的计算机未配置为运行远程命令，你也可以使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="78555-178">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="78555-179">-Credential</span><span class="sxs-lookup"><span data-stu-id="78555-179">-Credential</span></span>

<span data-ttu-id="78555-180">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="78555-180">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="78555-181">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="78555-181">The default is the current user.</span></span> <span data-ttu-id="78555-182">键入用户名，如 `User01` 、 `Domain01\User01` 或 `User@Contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="78555-182">Type a user name, such as `User01`, `Domain01\User01`, or `User@Contoso.com`.</span></span> <span data-ttu-id="78555-183">或者输入 **PSCredential** 对象，例如 Get-Credential cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="78555-183">Or, enter a **PSCredential** object, such as an object that is returned by the Get-Credential cmdlet.</span></span> <span data-ttu-id="78555-184">键入用户名时，将会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="78555-184">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="78555-185">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="78555-185">-EnableAllPrivileges</span></span>

<span data-ttu-id="78555-186">指示在命令进行 WMI 调用之前，此 cmdlet 将启用当前用户的所有权限。</span><span class="sxs-lookup"><span data-stu-id="78555-186">Indicates that this cmdlet enables all the privileges of the current user before the command makes the WMI call.</span></span>

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

### <span data-ttu-id="78555-187">-Impersonation</span><span class="sxs-lookup"><span data-stu-id="78555-187">-Impersonation</span></span>

<span data-ttu-id="78555-188">指定要使用的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="78555-188">Specifies the impersonation level to use.</span></span> <span data-ttu-id="78555-189">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="78555-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="78555-190">0：Default（读取本地注册表的默认模拟级别，通常设置为“3：模拟”。）</span><span class="sxs-lookup"><span data-stu-id="78555-190">0: Default (Reads the local registry for the default impersonation level, which is usually set to "3: Impersonate".)</span></span>
- <span data-ttu-id="78555-191">1：Anonymous（隐藏调用方的凭据。）</span><span class="sxs-lookup"><span data-stu-id="78555-191">1: Anonymous (Hides the credentials of the caller.)</span></span>
- <span data-ttu-id="78555-192">2：Identify（允许对象查询调用方的凭据。）</span><span class="sxs-lookup"><span data-stu-id="78555-192">2: Identify (Allows objects to query the credentials of the caller.)</span></span>
- <span data-ttu-id="78555-193">3：Impersonate（允许对象使用调用方的凭据。）</span><span class="sxs-lookup"><span data-stu-id="78555-193">3: Impersonate (Allows objects to use the credentials of the caller.)</span></span>
- <span data-ttu-id="78555-194">4：Delegate（允许对象允许其他对象使用调用方的凭据。）</span><span class="sxs-lookup"><span data-stu-id="78555-194">4: Delegate (Allows objects to permit other objects to use the credentials of the caller.)</span></span>

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

### <span data-ttu-id="78555-195">-InputObject</span><span class="sxs-lookup"><span data-stu-id="78555-195">-InputObject</span></span>

<span data-ttu-id="78555-196">指定要用作输入的 **system.management.managementobject** 对象。</span><span class="sxs-lookup"><span data-stu-id="78555-196">Specifies a **ManagementObject** object to use as input.</span></span> <span data-ttu-id="78555-197">使用此参数时，将忽略除 **Flag** 和 **Argument** 参数之外的所有其他参数。</span><span class="sxs-lookup"><span data-stu-id="78555-197">When this parameter is used, all other parameters except the **Flag** and **Argument** parameters are ignored.</span></span>

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

### <span data-ttu-id="78555-198">-Locale</span><span class="sxs-lookup"><span data-stu-id="78555-198">-Locale</span></span>

<span data-ttu-id="78555-199">指定 WMI 对象的首选区域设置。</span><span class="sxs-lookup"><span data-stu-id="78555-199">Specifies the preferred locale for WMI objects.</span></span> <span data-ttu-id="78555-200">按首选顺序将 **Locale** 参数的值指定为格式的数组 `MS_<LCID>` 。</span><span class="sxs-lookup"><span data-stu-id="78555-200">Specify the value of the **Locale** parameter as an array in the `MS_<LCID>` format in the preferred order.</span></span>

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

### <span data-ttu-id="78555-201">-Name</span><span class="sxs-lookup"><span data-stu-id="78555-201">-Name</span></span>

<span data-ttu-id="78555-202">指定要调用的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="78555-202">Specifies the name of the method to be invoked.</span></span> <span data-ttu-id="78555-203">此参数是必需的，不能为 null 或为空。</span><span class="sxs-lookup"><span data-stu-id="78555-203">This parameter is mandatory and cannot be null or empty.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="78555-204">-Namespace</span><span class="sxs-lookup"><span data-stu-id="78555-204">-Namespace</span></span>

<span data-ttu-id="78555-205">与 **Class** 参数一起使用时，此参数将指定引用的 wmi 类或对象所在的 wmi 存储库命名空间。</span><span class="sxs-lookup"><span data-stu-id="78555-205">When used with the **Class** parameter, this parameter specifies the WMI repository namespace where the referenced WMI class or object is located.</span></span>

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

### <span data-ttu-id="78555-206">-Path</span><span class="sxs-lookup"><span data-stu-id="78555-206">-Path</span></span>

<span data-ttu-id="78555-207">指定 WMI 类的 WMI 对象路径，或指定 WMI 类实例的 WMI 对象路径。</span><span class="sxs-lookup"><span data-stu-id="78555-207">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class.</span></span> <span data-ttu-id="78555-208">指定的类或实例必须包含 **Name** 参数中指定的方法。</span><span class="sxs-lookup"><span data-stu-id="78555-208">The class or the instance that you specify must contain the method that is specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="78555-209">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="78555-209">-ThrottleLimit</span></span>

<span data-ttu-id="78555-210">指定可同时执行的 WMI 操作数的限制值。</span><span class="sxs-lookup"><span data-stu-id="78555-210">Specifies a throttle value for the number of WMI operations that can be executed simultaneously.</span></span>
<span data-ttu-id="78555-211">此参数与 **AsJob** 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="78555-211">This parameter is used together with the **AsJob** parameter.</span></span> <span data-ttu-id="78555-212">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="78555-212">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="78555-213">-Confirm</span><span class="sxs-lookup"><span data-stu-id="78555-213">-Confirm</span></span>

<span data-ttu-id="78555-214">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="78555-214">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="78555-215">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="78555-215">-WhatIf</span></span>

<span data-ttu-id="78555-216">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="78555-216">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="78555-217">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="78555-217">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="78555-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="78555-218">CommonParameters</span></span>

<span data-ttu-id="78555-219">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="78555-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="78555-220">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="78555-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="78555-221">输入</span><span class="sxs-lookup"><span data-stu-id="78555-221">INPUTS</span></span>

### <span data-ttu-id="78555-222">无</span><span class="sxs-lookup"><span data-stu-id="78555-222">None</span></span>

<span data-ttu-id="78555-223">此 cmdlet 不接受任何输入。</span><span class="sxs-lookup"><span data-stu-id="78555-223">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="78555-224">输出</span><span class="sxs-lookup"><span data-stu-id="78555-224">OUTPUTS</span></span>

### <span data-ttu-id="78555-225">无</span><span class="sxs-lookup"><span data-stu-id="78555-225">None</span></span>

<span data-ttu-id="78555-226">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="78555-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="78555-227">注释</span><span class="sxs-lookup"><span data-stu-id="78555-227">NOTES</span></span>

## <span data-ttu-id="78555-228">相关链接</span><span class="sxs-lookup"><span data-stu-id="78555-228">RELATED LINKS</span></span>

[<span data-ttu-id="78555-229">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="78555-229">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="78555-230">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="78555-230">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="78555-231">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="78555-231">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="78555-232">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="78555-232">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[<span data-ttu-id="78555-233">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="78555-233">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="78555-234">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="78555-234">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="78555-235">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="78555-235">Set-WmiInstance</span></span>](Set-WmiInstance.md)
