---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198033"
---
# <span data-ttu-id="80f96-103">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="80f96-103">Set-WmiInstance</span></span>

## <span data-ttu-id="80f96-104">摘要</span><span class="sxs-lookup"><span data-stu-id="80f96-104">SYNOPSIS</span></span>
<span data-ttu-id="80f96-105">创建或更新现有 Windows Management Instrumentation (WMI) 类的实例。</span><span class="sxs-lookup"><span data-stu-id="80f96-105">Creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="80f96-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="80f96-106">SYNTAX</span></span>

### <span data-ttu-id="80f96-107">class（默认值）</span><span class="sxs-lookup"><span data-stu-id="80f96-107">class (Default)</span></span>

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80f96-108">对象 (object)</span><span class="sxs-lookup"><span data-stu-id="80f96-108">object</span></span>

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80f96-109">path</span><span class="sxs-lookup"><span data-stu-id="80f96-109">path</span></span>

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80f96-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="80f96-110">WQLQuery</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80f96-111">query</span><span class="sxs-lookup"><span data-stu-id="80f96-111">query</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="80f96-112">list</span><span class="sxs-lookup"><span data-stu-id="80f96-112">list</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="80f96-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="80f96-113">DESCRIPTION</span></span>
<span data-ttu-id="80f96-114">`Set-WmiInstance`Cmdlet 可创建或更新现有 Windows Management Instrumentation (WMI) 类的实例。</span><span class="sxs-lookup"><span data-stu-id="80f96-114">The `Set-WmiInstance` cmdlet creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>
<span data-ttu-id="80f96-115">创建或更新的实例将写入 WMI 存储库。</span><span class="sxs-lookup"><span data-stu-id="80f96-115">The created or updated instance is written to the WMI repository.</span></span>

<span data-ttu-id="80f96-116">Windows PowerShell 3.0 中引入的新 CIM cmdlet 执行与 WMI cmdlet 相同的任务。</span><span class="sxs-lookup"><span data-stu-id="80f96-116">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="80f96-117">CIM cmdlet 符合 WS-Management (WSMan) 标准和通用信息模型 (CIM) 标准。</span><span class="sxs-lookup"><span data-stu-id="80f96-117">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard.</span></span>
<span data-ttu-id="80f96-118">这使 cmdlet 可以使用相同的技术来管理基于 Windows 的计算机和运行其他操作系统的计算机。</span><span class="sxs-lookup"><span data-stu-id="80f96-118">this enables cmdlets to use the same techniques to manage Windows-based computers and those running other operating systems.</span></span>
<span data-ttu-id="80f96-119">请 `Set-WmiInstance` 考虑使用 [CimInstance](/powershell/module/cimcmdlets/set-ciminstance) 或 [CimInstance](/powershell/module/cimcmdlets/new-ciminstance) cmdlet，而不是使用。</span><span class="sxs-lookup"><span data-stu-id="80f96-119">Instead of using `Set-WmiInstance`, consider using the [Set-CimInstance](/powershell/module/cimcmdlets/set-ciminstance) or [New-CimInstance](/powershell/module/cimcmdlets/new-ciminstance) cmdlets.</span></span>

## <span data-ttu-id="80f96-120">示例</span><span class="sxs-lookup"><span data-stu-id="80f96-120">EXAMPLES</span></span>

### <span data-ttu-id="80f96-121">示例1：设置 WMI 日志记录级别</span><span class="sxs-lookup"><span data-stu-id="80f96-121">Example 1: Set WMI logging level</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

<span data-ttu-id="80f96-122">此命令将 WMI 日志记录级别设置为 2。</span><span class="sxs-lookup"><span data-stu-id="80f96-122">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="80f96-123">命令传递要设置的属性，并将值（在参数参数中被视为值对）传递。</span><span class="sxs-lookup"><span data-stu-id="80f96-123">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="80f96-124">此参数接受由 @{property = value} 结构定义的哈希表。</span><span class="sxs-lookup"><span data-stu-id="80f96-124">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="80f96-125">返回的类信息将反映出新值。</span><span class="sxs-lookup"><span data-stu-id="80f96-125">The class information that is returned reflects the new value.</span></span>

### <span data-ttu-id="80f96-126">示例2：创建环境变量及其值</span><span class="sxs-lookup"><span data-stu-id="80f96-126">Example 2: Create an environment variable and its value</span></span>

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

<span data-ttu-id="80f96-127">此命令创建 testvar 环境变量，该变量的值为 testvalue。</span><span class="sxs-lookup"><span data-stu-id="80f96-127">This command creates the testvar environment variable that has the value testvalue.</span></span>
<span data-ttu-id="80f96-128">它通过创建 **Win32_Environment** WMI 类的新实例来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="80f96-128">It does this by creating a new instance of the **Win32_Environment** WMI class.</span></span>
<span data-ttu-id="80f96-129">此操作需要适当的凭据，并且你可能需要重新启动 Windows PowerShell 才能查看新的环境变量。</span><span class="sxs-lookup"><span data-stu-id="80f96-129">This operation requires appropriate credentials and that you may have to restart Windows PowerShell to see the new environment variable.</span></span>

### <span data-ttu-id="80f96-130">示例3：为多台远程计算机设置 WMI 日志记录级别</span><span class="sxs-lookup"><span data-stu-id="80f96-130">Example 3: Set WMI logging level for several remote computers</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

<span data-ttu-id="80f96-131">此命令将 WMI 日志记录级别设置为 2。</span><span class="sxs-lookup"><span data-stu-id="80f96-131">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="80f96-132">命令传递要设置的属性，并将值（在参数参数中被视为值对）传递。</span><span class="sxs-lookup"><span data-stu-id="80f96-132">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="80f96-133">此参数接受由 @{property = value} 结构定义的哈希表。</span><span class="sxs-lookup"><span data-stu-id="80f96-133">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="80f96-134">返回的类信息将反映出新值。</span><span class="sxs-lookup"><span data-stu-id="80f96-134">The returned class information reflects the new value.</span></span>

## <span data-ttu-id="80f96-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="80f96-135">PARAMETERS</span></span>

### <span data-ttu-id="80f96-136">-Arguments</span><span class="sxs-lookup"><span data-stu-id="80f96-136">-Arguments</span></span>
<span data-ttu-id="80f96-137">指定要更改的属性的名称，以及该属性的新值。</span><span class="sxs-lookup"><span data-stu-id="80f96-137">Specifies the name of the property to be changed and the new value for that property.</span></span>
<span data-ttu-id="80f96-138">名称和值必须是名称/值对。</span><span class="sxs-lookup"><span data-stu-id="80f96-138">The name and value must be a name-value pair.</span></span>
<span data-ttu-id="80f96-139">名称-值对作为哈希表传递到命令行。</span><span class="sxs-lookup"><span data-stu-id="80f96-139">The name-value pair is passed on the command line as a hash table.</span></span>
<span data-ttu-id="80f96-140">例如：</span><span class="sxs-lookup"><span data-stu-id="80f96-140">For example:</span></span>

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80f96-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="80f96-141">-AsJob</span></span>
<span data-ttu-id="80f96-142">指示此 cmdket 作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="80f96-142">Indicates that this cmdket runs as a background job.</span></span>
<span data-ttu-id="80f96-143">使用此参数可运行需要较长时间才能完成的命令。</span><span class="sxs-lookup"><span data-stu-id="80f96-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="80f96-144">指定 *AsJob* 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="80f96-144">When you specify the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="80f96-145">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="80f96-145">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="80f96-146">如果 **将 set-wmiinstance** 用于远程计算机，则会在本地计算机上创建作业，远程计算机的结果将自动返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="80f96-146">If **Set-WmiInstance** is used for a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="80f96-147">若要 **管理作业，** 请使用包含 **job 名词)  (的 cmdlet** 。</span><span class="sxs-lookup"><span data-stu-id="80f96-147">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="80f96-148">若要获取作业结果，请使用 Receive-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="80f96-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="80f96-149">若要将此参数与远程计算机一起使用，必须为本地和远程计算机配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="80f96-149">To use this parameter together with remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="80f96-150">此外，您必须使用 Windows Vista 和更高版本的 Windows 操作系统中的 "以管理员身份运行" 选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="80f96-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of the Windows operating system.</span></span>
<span data-ttu-id="80f96-151">有关详细信息，请参阅 about_Remote_Requirements。</span><span class="sxs-lookup"><span data-stu-id="80f96-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="80f96-152">有关 Windows PowerShell 后台作业的详细信息，请参阅 about_Jobs 和 about_Remote_Jobs。</span><span class="sxs-lookup"><span data-stu-id="80f96-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="80f96-153">-Authentication</span><span class="sxs-lookup"><span data-stu-id="80f96-153">-Authentication</span></span>
<span data-ttu-id="80f96-154">指定必须用于 WMI 连接的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="80f96-154">Specifies the authentication level that must be used with the WMI connection.</span></span>
<span data-ttu-id="80f96-155">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="80f96-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="80f96-156">-1：保持不变。</span><span class="sxs-lookup"><span data-stu-id="80f96-156">-1: Unchanged.</span></span>
- <span data-ttu-id="80f96-157">0：Default。</span><span class="sxs-lookup"><span data-stu-id="80f96-157">0: Default.</span></span>
- <span data-ttu-id="80f96-158">1：无。</span><span class="sxs-lookup"><span data-stu-id="80f96-158">1: None.</span></span>
<span data-ttu-id="80f96-159">未执行任何身份验证。</span><span class="sxs-lookup"><span data-stu-id="80f96-159">No authentication in performed.</span></span>
- <span data-ttu-id="80f96-160">2：连接。</span><span class="sxs-lookup"><span data-stu-id="80f96-160">2: Connect.</span></span>
<span data-ttu-id="80f96-161">仅当客户端与应用程序建立了关系时才执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="80f96-161">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="80f96-162">3：调用。</span><span class="sxs-lookup"><span data-stu-id="80f96-162">3: Call.</span></span>
<span data-ttu-id="80f96-163">仅当应用程序接收到请求时，才会在每次调用开始时执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="80f96-163">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="80f96-164">4：数据包。</span><span class="sxs-lookup"><span data-stu-id="80f96-164">4: Packet.</span></span>
<span data-ttu-id="80f96-165">对从客户端收到的所有数据执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="80f96-165">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="80f96-166">5： PacketIntegrity。</span><span class="sxs-lookup"><span data-stu-id="80f96-166">5: PacketIntegrity.</span></span>
<span data-ttu-id="80f96-167">在客户端和应用程序之间传输的所有数据都经过身份验证和验证。</span><span class="sxs-lookup"><span data-stu-id="80f96-167">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="80f96-168">6： PacketPrivacy。</span><span class="sxs-lookup"><span data-stu-id="80f96-168">6: PacketPrivacy.</span></span>
<span data-ttu-id="80f96-169">使用其他身份验证级别的属性，并对所有数据进行加密。</span><span class="sxs-lookup"><span data-stu-id="80f96-169">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

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

### <span data-ttu-id="80f96-170">-Authority</span><span class="sxs-lookup"><span data-stu-id="80f96-170">-Authority</span></span>
<span data-ttu-id="80f96-171">指定用于对 WMI 连接进行身份验证的授权机构。</span><span class="sxs-lookup"><span data-stu-id="80f96-171">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="80f96-172">可以指定标准 NTLM 或 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="80f96-172">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="80f96-173">若要使用 NTLM，请将授权机构设置设为“ntlmdomain:\<DomainName\>”，其中 \<DomainName\> 标识有效的 NTLM 域名。</span><span class="sxs-lookup"><span data-stu-id="80f96-173">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="80f96-174">若要使用 Kerberos，请指定 kerberos： \<DomainName\> \\ \<ServerName\> 。</span><span class="sxs-lookup"><span data-stu-id="80f96-174">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="80f96-175">连接到本地计算机时不能包含授权机构设置。</span><span class="sxs-lookup"><span data-stu-id="80f96-175">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="80f96-176">-Class</span><span class="sxs-lookup"><span data-stu-id="80f96-176">-Class</span></span>
<span data-ttu-id="80f96-177">指定 WMI 类的名称。</span><span class="sxs-lookup"><span data-stu-id="80f96-177">Specifies the name of a WMI class.</span></span>

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

### <span data-ttu-id="80f96-178">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="80f96-178">-ComputerName</span></span>
<span data-ttu-id="80f96-179">指定在其上运行此 cmdlet 的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="80f96-179">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="80f96-180">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="80f96-180">The default is the local computer.</span></span>

<span data-ttu-id="80f96-181">键入一台或多台计算机的 NetBIOS 名称、IP 地址或完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="80f96-181">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="80f96-182">若要指定本地计算机，请键入该计算机名称、句点 (.) 或 localhost。</span><span class="sxs-lookup"><span data-stu-id="80f96-182">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="80f96-183">此参数不依赖于 Windows PowerShell 远程处理。</span><span class="sxs-lookup"><span data-stu-id="80f96-183">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="80f96-184">即使你的计算机未配置为运行远程命令，你也可以使用 *ComputerName* 参数。</span><span class="sxs-lookup"><span data-stu-id="80f96-184">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="80f96-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="80f96-185">-Credential</span></span>
<span data-ttu-id="80f96-186">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="80f96-186">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="80f96-187">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="80f96-187">The default is the current user.</span></span>

<span data-ttu-id="80f96-188">键入用户名（如 User01 或 Domain01\User01）或输入 PSCredential 对象，例如 Get-Credential cmdlet 生成的一个 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="80f96-188">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="80f96-189">如果键入用户名，则此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="80f96-189">If you type a user name, this cmdlet prompts for a password.</span></span>

<span data-ttu-id="80f96-190">随 Windows PowerShell 一起安装的任何提供程序都不支持使用参数安装的任何提供程序支持此参数。</span><span class="sxs-lookup"><span data-stu-id="80f96-190">This parameter is not supported by any providers installed with parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="80f96-191">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="80f96-191">-EnableAllPrivileges</span></span>
<span data-ttu-id="80f96-192">指示此 cmdlet 在执行 WMI 调用的命令之前启用当前用户的所有权限。</span><span class="sxs-lookup"><span data-stu-id="80f96-192">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

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

### <span data-ttu-id="80f96-193">-Impersonation</span><span class="sxs-lookup"><span data-stu-id="80f96-193">-Impersonation</span></span>
<span data-ttu-id="80f96-194">指定要使用的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="80f96-194">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="80f96-195">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="80f96-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="80f96-196">0：Default。</span><span class="sxs-lookup"><span data-stu-id="80f96-196">0: Default.</span></span>
<span data-ttu-id="80f96-197">读取默认模拟级别的本地注册表，通常设置为 "3：模拟"。</span><span class="sxs-lookup"><span data-stu-id="80f96-197">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="80f96-198">1：Anonymous。</span><span class="sxs-lookup"><span data-stu-id="80f96-198">1: Anonymous.</span></span>
<span data-ttu-id="80f96-199">隐藏调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="80f96-199">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="80f96-200">2：Identify。</span><span class="sxs-lookup"><span data-stu-id="80f96-200">2: Identify.</span></span>
<span data-ttu-id="80f96-201">允许对象查询调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="80f96-201">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="80f96-202">3：Impersonate。</span><span class="sxs-lookup"><span data-stu-id="80f96-202">3: Impersonate.</span></span>
<span data-ttu-id="80f96-203">允许对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="80f96-203">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="80f96-204">4：Delegate。</span><span class="sxs-lookup"><span data-stu-id="80f96-204">4: Delegate.</span></span>
<span data-ttu-id="80f96-205">允许对象允许其他对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="80f96-205">Allows objects to permit other objects to use the credentials of the caller.</span></span>

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

### <span data-ttu-id="80f96-206">-InputObject</span><span class="sxs-lookup"><span data-stu-id="80f96-206">-InputObject</span></span>
<span data-ttu-id="80f96-207">指定要用作输入的 **system.management.managementobject** 对象。</span><span class="sxs-lookup"><span data-stu-id="80f96-207">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="80f96-208">使用此参数时，将忽略除 *Arguments* 参数之外的所有其他参数。</span><span class="sxs-lookup"><span data-stu-id="80f96-208">When this parameter is used, all other parameters ,except the *Arguments* parameter, are ignored.</span></span>

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

### <span data-ttu-id="80f96-209">-Locale</span><span class="sxs-lookup"><span data-stu-id="80f96-209">-Locale</span></span>
<span data-ttu-id="80f96-210">指定 WMI 对象的首选区域设置。</span><span class="sxs-lookup"><span data-stu-id="80f96-210">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="80f96-211">*区域设置* 参数在数组中按首选顺序由 MS_ \<LCID\> 格式指定。</span><span class="sxs-lookup"><span data-stu-id="80f96-211">The *Locale* parameter is specified in an array in the MS_\<LCID\> format in the preferred order.</span></span>

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

### <span data-ttu-id="80f96-212">-Namespace</span><span class="sxs-lookup"><span data-stu-id="80f96-212">-Namespace</span></span>
<span data-ttu-id="80f96-213">指定在与 *class* 参数一起使用时所引用的 wmi 类所在的 wmi 存储库命名空间。</span><span class="sxs-lookup"><span data-stu-id="80f96-213">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

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

### <span data-ttu-id="80f96-214">-Path</span><span class="sxs-lookup"><span data-stu-id="80f96-214">-Path</span></span>
<span data-ttu-id="80f96-215">指定要创建或更新的实例的 WMI 对象路径。</span><span class="sxs-lookup"><span data-stu-id="80f96-215">Specifies a WMI object path of the instance that you want to create or update.</span></span>

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

### <span data-ttu-id="80f96-216">-PutType</span><span class="sxs-lookup"><span data-stu-id="80f96-216">-PutType</span></span>
<span data-ttu-id="80f96-217">指示是否创建或更新 WMI 实例。</span><span class="sxs-lookup"><span data-stu-id="80f96-217">Indicates whether to create or update the WMI instance.</span></span>
<span data-ttu-id="80f96-218">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="80f96-218">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="80f96-219">UpdateOnly.</span><span class="sxs-lookup"><span data-stu-id="80f96-219">UpdateOnly.</span></span>
<span data-ttu-id="80f96-220">更新现有的 WMI 实例。</span><span class="sxs-lookup"><span data-stu-id="80f96-220">Updates an existing WMI instance.</span></span>
- <span data-ttu-id="80f96-221">CreateOnly.</span><span class="sxs-lookup"><span data-stu-id="80f96-221">CreateOnly.</span></span>
<span data-ttu-id="80f96-222">创建新的 WMI 实例。</span><span class="sxs-lookup"><span data-stu-id="80f96-222">Creates a new WMI instance.</span></span>
- <span data-ttu-id="80f96-223">UpdateOrCreate.</span><span class="sxs-lookup"><span data-stu-id="80f96-223">UpdateOrCreate.</span></span>
<span data-ttu-id="80f96-224">如果 WMI 实例存在，则更新该实例；如果实例不存在，则创建一个新实例。</span><span class="sxs-lookup"><span data-stu-id="80f96-224">Updates the WMI instance if it exists or creates a new instance if an instance does not exist.</span></span>

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="80f96-225">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="80f96-225">-ThrottleLimit</span></span>
<span data-ttu-id="80f96-226">指定为运行此命令可建立的并发连接的最大数目。</span><span class="sxs-lookup"><span data-stu-id="80f96-226">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="80f96-227">此参数与 *AsJob* 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="80f96-227">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="80f96-228">节流限制仅适用于当前命令，而不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="80f96-228">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="80f96-229">-Confirm</span><span class="sxs-lookup"><span data-stu-id="80f96-229">-Confirm</span></span>
<span data-ttu-id="80f96-230">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="80f96-230">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="80f96-231">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="80f96-231">-WhatIf</span></span>
<span data-ttu-id="80f96-232">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="80f96-232">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="80f96-233">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="80f96-233">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="80f96-234">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="80f96-234">CommonParameters</span></span>
<span data-ttu-id="80f96-235">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="80f96-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="80f96-236">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="80f96-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="80f96-237">输入</span><span class="sxs-lookup"><span data-stu-id="80f96-237">INPUTS</span></span>

### <span data-ttu-id="80f96-238">无</span><span class="sxs-lookup"><span data-stu-id="80f96-238">None</span></span>
<span data-ttu-id="80f96-239">此 cmdlet 不接受输入。</span><span class="sxs-lookup"><span data-stu-id="80f96-239">This cmdlet does not accept input.</span></span>

## <span data-ttu-id="80f96-240">输出</span><span class="sxs-lookup"><span data-stu-id="80f96-240">OUTPUTS</span></span>

### <span data-ttu-id="80f96-241">无</span><span class="sxs-lookup"><span data-stu-id="80f96-241">None</span></span>
<span data-ttu-id="80f96-242">此 cmdlet 将不产生输出。</span><span class="sxs-lookup"><span data-stu-id="80f96-242">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="80f96-243">注释</span><span class="sxs-lookup"><span data-stu-id="80f96-243">NOTES</span></span>

## <span data-ttu-id="80f96-244">相关链接</span><span class="sxs-lookup"><span data-stu-id="80f96-244">RELATED LINKS</span></span>

[<span data-ttu-id="80f96-245">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="80f96-245">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="80f96-246">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="80f96-246">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="80f96-247">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="80f96-247">Remove-WmiObject</span></span>](Remove-WmiObject.md)
