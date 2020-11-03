---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmiObject
ms.openlocfilehash: ed759ff3d0dd35cd55f9dac5a2d76e36eac4dc6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198278"
---
# <span data-ttu-id="e4b24-103">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="e4b24-103">Get-WmiObject</span></span>

## <span data-ttu-id="e4b24-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e4b24-104">SYNOPSIS</span></span>
<span data-ttu-id="e4b24-105">获取 Windows Management Instrumentation (WMI) 类的实例或可用类的相关信息。</span><span class="sxs-lookup"><span data-stu-id="e4b24-105">Gets instances of Windows Management Instrumentation (WMI) classes or information about the available classes.</span></span>

## <span data-ttu-id="e4b24-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4b24-106">SYNTAX</span></span>

### <span data-ttu-id="e4b24-107">query（默认值）</span><span class="sxs-lookup"><span data-stu-id="e4b24-107">query (Default)</span></span>

```
Get-WmiObject [-Class] <String> [[-Property] <String[]>] [-Filter <String>] [-Amended] [-DirectRead]
 [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="e4b24-108">list</span><span class="sxs-lookup"><span data-stu-id="e4b24-108">list</span></span>

```
Get-WmiObject [[-Class] <String>] [-Recurse] [-Amended] [-List] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="e4b24-109">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="e4b24-109">WQLQuery</span></span>

```
Get-WmiObject [-Amended] [-DirectRead] -Query <String> [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="e4b24-110">class</span><span class="sxs-lookup"><span data-stu-id="e4b24-110">class</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

### <span data-ttu-id="e4b24-111">path</span><span class="sxs-lookup"><span data-stu-id="e4b24-111">path</span></span>

```
Get-WmiObject [-Amended] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges]
 [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [<CommonParameters>]
```

## <span data-ttu-id="e4b24-112">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e4b24-112">DESCRIPTION</span></span>

<span data-ttu-id="e4b24-113">从 PowerShell 3.0 开始，此 cmdlet 已被取代 `Get-CimInstance` 。</span><span class="sxs-lookup"><span data-stu-id="e4b24-113">Starting in PowerShell 3.0, this cmdlet has been superseded by `Get-CimInstance`.</span></span>

<span data-ttu-id="e4b24-114">`Get-WmiObject`Cmdlet 可获取 wmi 类的实例或有关可用 wmi 类的信息。</span><span class="sxs-lookup"><span data-stu-id="e4b24-114">The `Get-WmiObject` cmdlet gets instances of WMI classes or information about the available WMI classes.</span></span> <span data-ttu-id="e4b24-115">若要指定远程计算机，请使用 **ComputerName** 参数。</span><span class="sxs-lookup"><span data-stu-id="e4b24-115">To specify a remote computer, use the **ComputerName** parameter.</span></span> <span data-ttu-id="e4b24-116">如果指定了 **List** 参数，则 cmdlet 将获取有关指定的命名空间中可用的 WMI 类的信息。</span><span class="sxs-lookup"><span data-stu-id="e4b24-116">If the **List** parameter is specified, the cmdlet gets information about the WMI classes that are available in a specified namespace.</span></span> <span data-ttu-id="e4b24-117">如果指定了 **Query** 参数，则 cmdlet 将运行 WMI 查询语言 (WQL) 语句。</span><span class="sxs-lookup"><span data-stu-id="e4b24-117">If the **Query** parameter is specified, the cmdlet runs a WMI query language (WQL) statement.</span></span>

<span data-ttu-id="e4b24-118">`Get-WmiObject`Cmdlet 不使用 Windows PowerShell 远程处理来执行远程操作。</span><span class="sxs-lookup"><span data-stu-id="e4b24-118">The `Get-WmiObject` cmdlet does not use Windows PowerShell remoting to perform remote operations.</span></span>
<span data-ttu-id="e4b24-119">**ComputerName** `Get-WmiObject` 即使你的计算机不符合 windows powershell 远程处理的要求，或者没有为 windows powershell 中的远程处理配置，你也可以使用该 cmdlet 的 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="e4b24-119">You can use the **ComputerName** parameter of the `Get-WmiObject` cmdlet even if your computer does not meet the requirements for Windows PowerShell remoting or is not configured for remoting in Windows PowerShell.</span></span>

<span data-ttu-id="e4b24-120">从 Windows PowerShell 3.0 开始，返回的对象的 **__Server** 属性 `Get-WmiObject` 具有 **PSComputerName** 的别名。</span><span class="sxs-lookup"><span data-stu-id="e4b24-120">Beginning in Windows PowerShell 3.0, the **__Server** property of the object that `Get-WmiObject` returns has a **PSComputerName** alias.</span></span> <span data-ttu-id="e4b24-121">从而可以更轻松地在输出和报告中包含源计算机名称。</span><span class="sxs-lookup"><span data-stu-id="e4b24-121">This makes it easier to include the source computer name in output and reports.</span></span>

## <span data-ttu-id="e4b24-122">示例</span><span class="sxs-lookup"><span data-stu-id="e4b24-122">EXAMPLES</span></span>

### <span data-ttu-id="e4b24-123">示例1：获取本地计算机上的进程</span><span class="sxs-lookup"><span data-stu-id="e4b24-123">Example 1: Get processes on the local computer</span></span>

<span data-ttu-id="e4b24-124">此示例将获取本地计算机上的进程。</span><span class="sxs-lookup"><span data-stu-id="e4b24-124">This example get the processes on the local computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Process
```

### <span data-ttu-id="e4b24-125">示例2：获取远程计算机上的服务</span><span class="sxs-lookup"><span data-stu-id="e4b24-125">Example 2: Gets services on a remote computer</span></span>

<span data-ttu-id="e4b24-126">此示例获取远程计算机上的服务。</span><span class="sxs-lookup"><span data-stu-id="e4b24-126">This example gets the services on a remote computer.</span></span> <span data-ttu-id="e4b24-127">**ComputerName** 参数指定远程计算机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e4b24-127">The **ComputerName** parameter specifies the IP address of a remote computer.</span></span> <span data-ttu-id="e4b24-128">默认情况下，当前用户帐户必须是远程计算机上 **Administrators** 组的成员。</span><span class="sxs-lookup"><span data-stu-id="e4b24-128">By default, the current user account must be a member of the **Administrators** group on the remote computer.</span></span>

```powershell
Get-WmiObject -Class Win32_Service -ComputerName 10.1.4.62
```

### <span data-ttu-id="e4b24-129">示例3：获取本地计算机的根或默认命名空间中的 WMI 类</span><span class="sxs-lookup"><span data-stu-id="e4b24-129">Example 3: Get WMI classes in the root or default namespace of the local computer</span></span>

<span data-ttu-id="e4b24-130">此示例将获取本地计算机的根或默认命名空间中的 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="e4b24-130">This example gets the WMI classes in the root or default namespace of the local computer.</span></span>

```powershell
Get-WmiObject -Namespace "root/default" -List
```

### <span data-ttu-id="e4b24-131">示例4：在多台计算机上获取命名服务</span><span class="sxs-lookup"><span data-stu-id="e4b24-131">Example 4: Get a named service on multiple computers</span></span>

<span data-ttu-id="e4b24-132">此示例获取 **ComputerName** 参数值指定的计算机上的 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="e4b24-132">This example gets the WinRM service on the computers specified by the value of the **ComputerName** parameter.</span></span>

```powershell
Get-WmiObject -Query "select * from win32_service where name='WinRM'" -ComputerName Server01, Server02 |
  Format-List -Property PSComputerName, Name, ExitCode, Name, ProcessID, StartMode, State, Status
```

```Output
PSComputerName : SERVER01
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 844
StartMode      : Auto
State          : Running
Status         : OK

PSComputerName : SERVER02
Name           : WinRM
ExitCode       : 0
Name           : WinRM
ProcessID      : 932
StartMode      : Auto
State          : Running
Status         : OK
```

<span data-ttu-id="e4b24-133">管道运算符 (|) 将输出发送给 `Format-List` cmdlet，这会将 **PSComputerName** 属性添加到默认的输出。</span><span class="sxs-lookup"><span data-stu-id="e4b24-133">A pipeline operator (|) sends the output to the `Format-List` cmdlet, which adds the **PSComputerName** property to the default output.</span></span> <span data-ttu-id="e4b24-134">**PSComputerName** 是返回的对象的 **__Server** 属性的别名 `Get-WmiObject` 。</span><span class="sxs-lookup"><span data-stu-id="e4b24-134">**PSComputerName** is an alias of the **__Server** property of the objects that `Get-WmiObject` returns.</span></span> <span data-ttu-id="e4b24-135">此别名是在 PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e4b24-135">This alias was introduced in PowerShell 3.0.</span></span>

### <span data-ttu-id="e4b24-136">示例5：停止远程计算机上的服务</span><span class="sxs-lookup"><span data-stu-id="e4b24-136">Example 5: Stop a service on a remote computer</span></span>

<span data-ttu-id="e4b24-137">此示例将停止远程计算机上的 WinRM 服务。</span><span class="sxs-lookup"><span data-stu-id="e4b24-137">This example stops the WinRM service on a remote computer.</span></span> <span data-ttu-id="e4b24-138">`Get-WmiObject` 获取 Server01 上的 WinRM 服务对象的实例。</span><span class="sxs-lookup"><span data-stu-id="e4b24-138">`Get-WmiObject` gets the instance of the WinRM service object on Server01.</span></span> <span data-ttu-id="e4b24-139">然后，它调用该对象上 **Win32_Service** WMI 类的 **StopService** 方法。</span><span class="sxs-lookup"><span data-stu-id="e4b24-139">Then, it invokes the **StopService** method of the **Win32_Service** WMI class on that object.</span></span>

```powershell
(Get-WmiObject -Class Win32_Service -Filter "name='WinRM'" -ComputerName Server01).StopService()
```

<span data-ttu-id="e4b24-140">这等效于使用 `Stop-Service` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e4b24-140">This is equivalent to using the `Stop-Service` cmdlet.</span></span>

### <span data-ttu-id="e4b24-141">示例6：获取本地计算机上的 BIOS</span><span class="sxs-lookup"><span data-stu-id="e4b24-141">Example 6: Get the BIOS on the local computer</span></span>

<span data-ttu-id="e4b24-142">此示例从本地计算机中获取 BIOS 信息。</span><span class="sxs-lookup"><span data-stu-id="e4b24-142">This example gets the BIOS information from the local computer.</span></span> <span data-ttu-id="e4b24-143">Cmdlet 的 **Property** 参数 `Format-List` 用于显示列表中返回的对象的所有属性。</span><span class="sxs-lookup"><span data-stu-id="e4b24-143">The **Property** parameter of the `Format-List` cmdlet is used to display all properties of the returned object in a list.</span></span> <span data-ttu-id="e4b24-144">默认情况下，仅显示在配置文件中定义的属性的子集 `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="e4b24-144">By default, only the subset of properties defined in the `Types.ps1xml` configuration file are displayed.</span></span>

```powershell
Get-WmiObject -Class Win32_Bios | Format-List -Property *
```

```Output
Status                : OK
Name                  : Phoenix ROM BIOS PLUS Version 1.10 A05
Caption               : Phoenix ROM BIOS PLUS Version 1.10 A05
SMBIOSPresent         : True
__GENUS               : 2
__CLASS               : Win32_BIOS
__SUPERCLASS          : CIM_BIOSElement
__DYNASTY             : CIM_ManagedSystemElement
__RELPATH             : Win32_BIOS.Name="Phoenix ROM BIOS PLUS Version 1.10
__PROPERTY_COUNT      : 27
__DERIVATION          : {CIM_BIOSElement, CIM_SoftwareElement, CIM_LogicalElement,
__SERVER              : Server01
__NAMESPACE           : root\cimv2
__PATH                : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
BiosCharacteristics   : {7, 9, 10, 11...}
BIOSVersion           : {DELL   - 15, Phoenix ROM BIOS PLUS Version 1.10 A05}
BuildNumber           :
CodeSet               :
CurrentLanguage       : en|US|iso8859-1
Description           : Phoenix ROM BIOS PLUS Version 1.10 A05
IdentificationCode    :
InstallableLanguages  : 1
InstallDate           :
LanguageEdition       :
ListOfLanguages       : {en|US|iso8859-1}
Manufacturer          : Dell Inc.
OtherTargetOS         :
PrimaryBIOS           : True
ReleaseDate           : 20101103000000.000000+000
SerialNumber          : 8VDM9P1
SMBIOSBIOSVersion     : A05
SMBIOSMajorVersion    : 2
SMBIOSMinorVersion    : 6
SoftwareElementID     : Phoenix ROM BIOS PLUS Version 1.10 A05
SoftwareElementState  : 3
TargetOperatingSystem : 0
Version               : DELL   - 15
Scope                 : System.Management.ManagementScope
Path                  : \\SERVER01\root\cimv2:Win32_BIOS.Name="Phoenix ROM BIOS
Options               : System.Management.ObjectGetOptions
ClassPath             : \\JUNE-PC\root\cimv2:Win32_BIOS
Properties            : {BiosCharacteristics, BIOSVersion, BuildNumber, Caption...}
SystemProperties      : {__GENUS, __CLASS, __SUPERCLASS, __DYNASTY...}
Qualifiers            : {dynamic, Locale, provider, UUID}
Site                  :
Container             :
```

### <span data-ttu-id="e4b24-145">示例7：获取远程计算机上的服务</span><span class="sxs-lookup"><span data-stu-id="e4b24-145">Example 7: Get the services on a remote computer</span></span>

<span data-ttu-id="e4b24-146">此示例使用 cmdlet 的 **Credential** 参数 `Get-WmiObject` 获取远程计算机上的服务。</span><span class="sxs-lookup"><span data-stu-id="e4b24-146">This example uses the **Credential** parameter of the `Get-WmiObject` cmdlet to get the services on a remote computer.</span></span> <span data-ttu-id="e4b24-147">**Credential** 参数的值为用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="e4b24-147">The value of the **Credential** parameter is a user account name.</span></span> <span data-ttu-id="e4b24-148">将提示用户输入密码。</span><span class="sxs-lookup"><span data-stu-id="e4b24-148">The user is prompted for a password.</span></span>

```powershell
Get-WmiObject Win32_Service -Credential FABRIKAM\administrator -ComputerName Fabrikam
```

> [!NOTE]
> <span data-ttu-id="e4b24-149">在以本地计算机为目标时不能使用凭据。</span><span class="sxs-lookup"><span data-stu-id="e4b24-149">Credentials cannot be used when targeting the local computer.</span></span>

## <span data-ttu-id="e4b24-150">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4b24-150">PARAMETERS</span></span>

### <span data-ttu-id="e4b24-151">-Amended</span><span class="sxs-lookup"><span data-stu-id="e4b24-151">-Amended</span></span>

<span data-ttu-id="e4b24-152">获取或设置一个值，该值指示从 WMI 返回的对象是否应包含修正信息。</span><span class="sxs-lookup"><span data-stu-id="e4b24-152">Gets or sets a value that indicates whether the objects that are returned from WMI should contain amended information.</span></span> <span data-ttu-id="e4b24-153">通常，修正信息是附加到 WMI 对象的可本地化信息，如对象和属性说明。</span><span class="sxs-lookup"><span data-stu-id="e4b24-153">Typically, amended information is localizable information, such as object and property descriptions, that is attached to the WMI object.</span></span>

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

### <span data-ttu-id="e4b24-154">-AsJob</span><span class="sxs-lookup"><span data-stu-id="e4b24-154">-AsJob</span></span>

<span data-ttu-id="e4b24-155">将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="e4b24-155">Runs the command as a background job.</span></span> <span data-ttu-id="e4b24-156">使用此参数可运行需要较长时间才能完成的命令。</span><span class="sxs-lookup"><span data-stu-id="e4b24-156">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="e4b24-157">使用 **AsJob** 参数时，该命令将返回表示后台作业的对象，然后显示命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e4b24-157">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="e4b24-158">当作业完成时，你可以继续在此会话中工作。</span><span class="sxs-lookup"><span data-stu-id="e4b24-158">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="e4b24-159">如果 `Get-WmiObject` 在远程计算机上使用，则在本地计算机上创建作业，远程计算机的结果将自动返回到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="e4b24-159">If `Get-WmiObject` is used on a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="e4b24-160">若要管理作业，请使用包含 Job cmdlet 的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e4b24-160">To manage the job, use the cmdlets that contain the Job cmdlets.</span></span> <span data-ttu-id="e4b24-161">若要获取作业结果，请使用 `Receive-Job` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e4b24-161">To get the job results, use the `Receive-Job` cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="e4b24-162">若要将此参数用于远程计算机，必须为本地和远程计算机配置远程处理。</span><span class="sxs-lookup"><span data-stu-id="e4b24-162">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="e4b24-163">此外，在 Windows Vista 和更高版本的 Windows 中，必须使用“以管理员身份运行”选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e4b24-163">Additionally, you must start Windows PowerShell by using the "Run as administrator" option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="e4b24-164">有关详细信息，请参阅 [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b24-164">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/about/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="e4b24-165">有关 Windows PowerShell 后台作业的详细信息，请参阅 [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) 和 [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b24-165">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/about/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/about/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="e4b24-166">-Authentication</span><span class="sxs-lookup"><span data-stu-id="e4b24-166">-Authentication</span></span>

<span data-ttu-id="e4b24-167">指定用于 WMI 连接的身份验证级别。</span><span class="sxs-lookup"><span data-stu-id="e4b24-167">Specifies the authentication level to be used with the WMI connection.</span></span>
<span data-ttu-id="e4b24-168">有效值是：</span><span class="sxs-lookup"><span data-stu-id="e4b24-168">Valid values are:</span></span>

- <span data-ttu-id="e4b24-169">-1：Unchanged</span><span class="sxs-lookup"><span data-stu-id="e4b24-169">-1: Unchanged</span></span>
- <span data-ttu-id="e4b24-170">0：Default</span><span class="sxs-lookup"><span data-stu-id="e4b24-170">0: Default</span></span>
- <span data-ttu-id="e4b24-171">1：None（不执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="e4b24-171">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="e4b24-172">2：Connect（仅当客户端与应用程序建立了关系时才执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="e4b24-172">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="e4b24-173">3：Call（应用程序收到请求时只在每次调用的开始执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="e4b24-173">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="e4b24-174">4：Packet（对从客户端收到的所有数据执行身份验证。）</span><span class="sxs-lookup"><span data-stu-id="e4b24-174">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="e4b24-175">5： PacketIntegrity (在客户端和应用程序之间传输的所有数据都经过身份验证和验证。 ) </span><span class="sxs-lookup"><span data-stu-id="e4b24-175">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="e4b24-176">6：PacketPrivacy（使用其他身份验证等级的属性，并且所有数据都加密。）</span><span class="sxs-lookup"><span data-stu-id="e4b24-176">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-177">-Authority</span><span class="sxs-lookup"><span data-stu-id="e4b24-177">-Authority</span></span>

<span data-ttu-id="e4b24-178">指定用于对 WMI 连接进行身份验证的授权机构。</span><span class="sxs-lookup"><span data-stu-id="e4b24-178">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="e4b24-179">可以指定标准 NTLM 或 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="e4b24-179">You can specify standard NTLM or Kerberos authentication.</span></span> <span data-ttu-id="e4b24-180">若要使用 NTLM，请将权限设置设置为 `ntlmdomain:<DomainName>` ，其中 `<DomainName>` 标识有效的 NTLM 域名。</span><span class="sxs-lookup"><span data-stu-id="e4b24-180">To use NTLM, set the authority setting to `ntlmdomain:<DomainName>`, where `<DomainName>` identifies a valid NTLM domain name.</span></span> <span data-ttu-id="e4b24-181">若要使用 Kerberos，请指定 `kerberos:<DomainName>\<ServerName>` 。</span><span class="sxs-lookup"><span data-stu-id="e4b24-181">To use Kerberos, specify `kerberos:<DomainName>\<ServerName>`.</span></span> <span data-ttu-id="e4b24-182">连接到本地计算机时不能包含授权机构设置。</span><span class="sxs-lookup"><span data-stu-id="e4b24-182">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-183">-Class</span><span class="sxs-lookup"><span data-stu-id="e4b24-183">-Class</span></span>

<span data-ttu-id="e4b24-184">指定 WMI 类的名称。</span><span class="sxs-lookup"><span data-stu-id="e4b24-184">Specifies the name of a WMI class.</span></span> <span data-ttu-id="e4b24-185">如果使用此参数，则 cmdlet 将检索 WMI 类的实例。</span><span class="sxs-lookup"><span data-stu-id="e4b24-185">When this parameter is used, the cmdlet retrieves instances of the WMI class.</span></span>

```yaml
Type: System.String
Parameter Sets: query, list
Aliases: ClassName

Required: True (query), False (list)
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-186">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e4b24-186">-ComputerName</span></span>

<span data-ttu-id="e4b24-187">指定用于管理操作的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="e4b24-187">Specifies the target computer for the management operation.</span></span> <span data-ttu-id="e4b24-188">输入完全限定的域名 (FQDN) 、NetBIOS 名称或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e4b24-188">Enter a fully qualified domain name (FQDN), a NetBIOS name, or an IP address.</span></span> <span data-ttu-id="e4b24-189">当远程计算机与本地计算机处于不同的域中时，必须使用完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="e4b24-189">When the remote computer is in a different domain than the local computer, the fully qualified domain name is required.</span></span>

<span data-ttu-id="e4b24-190">默认为本地计算机。</span><span class="sxs-lookup"><span data-stu-id="e4b24-190">The default is the local computer.</span></span> <span data-ttu-id="e4b24-191">若要指定本地计算机，例如在计算机名称的列表中，请使用“localhost”、本地计算机名称或句点 (.)。</span><span class="sxs-lookup"><span data-stu-id="e4b24-191">To specify the local computer, such as in a list of computer names, use "localhost", the local computer name, or a dot (.).</span></span>

<span data-ttu-id="e4b24-192">此参数不依赖于 Windows PowerShell 远程处理，该远程处理使用 WS-Management。</span><span class="sxs-lookup"><span data-stu-id="e4b24-192">This parameter does not rely on Windows PowerShell remoting, which uses WS-Management.</span></span> <span data-ttu-id="e4b24-193">**ComputerName** `Get-WmiObject` 即使你的计算机未配置为运行 WS-Management 远程命令，你也可以使用 ComputerName 参数。</span><span class="sxs-lookup"><span data-stu-id="e4b24-193">You can use the **ComputerName** parameter of `Get-WmiObject` even if your computer is not configured to run WS-Management remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-194">-Credential</span><span class="sxs-lookup"><span data-stu-id="e4b24-194">-Credential</span></span>

<span data-ttu-id="e4b24-195">指定有权执行此操作的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e4b24-195">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="e4b24-196">默认为当前用户。</span><span class="sxs-lookup"><span data-stu-id="e4b24-196">The default is the current user.</span></span> <span data-ttu-id="e4b24-197">键入用户名，如 "User01"、"Domain01\User01" 或 User@Contoso.com 。</span><span class="sxs-lookup"><span data-stu-id="e4b24-197">Type a user name, such as "User01", "Domain01\User01", or User@Contoso.com.</span></span> <span data-ttu-id="e4b24-198">或者输入 **PSCredential** 对象，例如 `Get-Credential` cmdlet 返回的对象。</span><span class="sxs-lookup"><span data-stu-id="e4b24-198">Or, enter a **PSCredential** object, such as an object that is returned by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="e4b24-199">如果键入用户名，则将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="e4b24-199">When you type a user name, you are prompted for a password.</span></span> <span data-ttu-id="e4b24-200">在以本地计算机为目标时不能使用凭据。</span><span class="sxs-lookup"><span data-stu-id="e4b24-200">Credentials cannot be used when targeting the local computer.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-201">-DirectRead</span><span class="sxs-lookup"><span data-stu-id="e4b24-201">-DirectRead</span></span>

<span data-ttu-id="e4b24-202">指定无论其基类或派生类如何，是否都要求指定类直接访问 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="e4b24-202">Specifies whether direct access to the WMI provider is requested for the specified class without any regard to its base class or to its derived classes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: query, WQLQuery
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-203">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="e4b24-203">-EnableAllPrivileges</span></span>

<span data-ttu-id="e4b24-204">在命令进行 WMI 调用之前，启用当前用户的所有权限。</span><span class="sxs-lookup"><span data-stu-id="e4b24-204">Enables all the privileges of the current user before the command makes the WMI call.</span></span>

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

### <span data-ttu-id="e4b24-205">-Filter</span><span class="sxs-lookup"><span data-stu-id="e4b24-205">-Filter</span></span>

<span data-ttu-id="e4b24-206">指定要用作筛选器的 **Where** 子句。</span><span class="sxs-lookup"><span data-stu-id="e4b24-206">Specifies a **Where** clause to use as a filter.</span></span> <span data-ttu-id="e4b24-207">使用 WMI 查询语言 (WQL) 的语法。</span><span class="sxs-lookup"><span data-stu-id="e4b24-207">Uses the syntax of the WMI Query Language (WQL).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4b24-208">请不要在参数的值中包含 **Where** 关键字。</span><span class="sxs-lookup"><span data-stu-id="e4b24-208">Do not include the **Where** keyword in the value of the parameter.</span></span> <span data-ttu-id="e4b24-209">例如，以下命令不使用 **Where** 关键字，仅返回 **DeviceID** 为“c:”的逻辑磁盘和名称为 “WinRM”的服务。</span><span class="sxs-lookup"><span data-stu-id="e4b24-209">For example, the following commands return only the logical disks that have a **DeviceID** of 'c:' and services that have the name 'WinRM' without using the **Where** keyword.</span></span>

`Get-WmiObject Win32_LogicalDisk -filter "DeviceID = 'c:' "`

`Get-WmiObject win32_service -filter "name='WinRM'"`

```yaml
Type: System.String
Parameter Sets: query
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-210">-Impersonation</span><span class="sxs-lookup"><span data-stu-id="e4b24-210">-Impersonation</span></span>

<span data-ttu-id="e4b24-211">指定要使用的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="e4b24-211">Specifies the impersonation level to use.</span></span>

<span data-ttu-id="e4b24-212">此参数的可接受值为：</span><span class="sxs-lookup"><span data-stu-id="e4b24-212">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e4b24-213">0：Default。</span><span class="sxs-lookup"><span data-stu-id="e4b24-213">0: Default.</span></span> <span data-ttu-id="e4b24-214">读取默认模拟级别的本地注册表。</span><span class="sxs-lookup"><span data-stu-id="e4b24-214">Reads the local registry for the default impersonation level.</span></span> <span data-ttu-id="e4b24-215">通常将默认设置为 " **模拟** "。</span><span class="sxs-lookup"><span data-stu-id="e4b24-215">The default is usually set to **Impersonate** .</span></span>
- <span data-ttu-id="e4b24-216">1：Anonymous。</span><span class="sxs-lookup"><span data-stu-id="e4b24-216">1: Anonymous.</span></span> <span data-ttu-id="e4b24-217">隐藏调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="e4b24-217">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="e4b24-218">2：Identify。</span><span class="sxs-lookup"><span data-stu-id="e4b24-218">2: Identify.</span></span> <span data-ttu-id="e4b24-219">允许对象查询调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="e4b24-219">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="e4b24-220">3：Impersonate。</span><span class="sxs-lookup"><span data-stu-id="e4b24-220">3: Impersonate.</span></span> <span data-ttu-id="e4b24-221">允许对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="e4b24-221">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="e4b24-222">4：Delegate。</span><span class="sxs-lookup"><span data-stu-id="e4b24-222">4: Delegate.</span></span> <span data-ttu-id="e4b24-223">允许对象允许其他对象使用调用方的凭据。</span><span class="sxs-lookup"><span data-stu-id="e4b24-223">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: (All)
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-224">-List</span><span class="sxs-lookup"><span data-stu-id="e4b24-224">-List</span></span>

<span data-ttu-id="e4b24-225">获取由 **Namespace** 参数指定的 WMI 存储库命名空间中的 WMI 类的名称。</span><span class="sxs-lookup"><span data-stu-id="e4b24-225">Gets the names of the WMI classes in the WMI repository namespace that is specified by the **Namespace** parameter.</span></span>

<span data-ttu-id="e4b24-226">如果指定 **列表** 参数，而不是 **命名空间** 参数，则 `Get-WmiObject` 默认情况下使用 **Root\Cimv2** 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e4b24-226">If you specify the **List** parameter, but not the **Namespace** parameter, `Get-WmiObject` uses the **Root\Cimv2** namespace by default.</span></span> <span data-ttu-id="e4b24-227">此 cmdlet 不使用注册表项中的 **默认命名空间** 注册表项 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` 来确定默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="e4b24-227">This cmdlet does not use the **Default Namespace** registry entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WBEM\Scripting` registry key to determine the default namespace.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-228">-Locale</span><span class="sxs-lookup"><span data-stu-id="e4b24-228">-Locale</span></span>

<span data-ttu-id="e4b24-229">指定 WMI 对象的首选区域设置。</span><span class="sxs-lookup"><span data-stu-id="e4b24-229">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="e4b24-230">按 MS_\<LCID\> 格式输入一个值。</span><span class="sxs-lookup"><span data-stu-id="e4b24-230">Enter a value in MS_\<LCID\> format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-231">-Namespace</span><span class="sxs-lookup"><span data-stu-id="e4b24-231">-Namespace</span></span>

<span data-ttu-id="e4b24-232">当 **Namespace** 参数与 **Class** 参数一起使用时，它将指定指定的 WMI 类所在的 WMI 存储库命名空间。</span><span class="sxs-lookup"><span data-stu-id="e4b24-232">When used with the **Class** parameter, the **Namespace** parameter specifies the WMI repository namespace where the specified WMI class is located.</span></span> <span data-ttu-id="e4b24-233">当此参数与 **List** 参数一起使用时，它将指定所收集 WMI 类信息的来源命名空间。</span><span class="sxs-lookup"><span data-stu-id="e4b24-233">When used with the **List** parameter, it specifies the namespace from which to gather WMI class information.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-234">-Property</span><span class="sxs-lookup"><span data-stu-id="e4b24-234">-Property</span></span>

<span data-ttu-id="e4b24-235">指定此 cmdlet 从中获取信息的 WMI 类属性。</span><span class="sxs-lookup"><span data-stu-id="e4b24-235">Specifies the WMI class properties that this cmdlet gets information from.</span></span> <span data-ttu-id="e4b24-236">输入属性名称。</span><span class="sxs-lookup"><span data-stu-id="e4b24-236">Enter the property names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: query
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-237">-Query</span><span class="sxs-lookup"><span data-stu-id="e4b24-237">-Query</span></span>

<span data-ttu-id="e4b24-238">运行指定的 WMI 查询语言 (WQL) 语句。</span><span class="sxs-lookup"><span data-stu-id="e4b24-238">Runs the specified WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="e4b24-239">此参数不支持事件查询。</span><span class="sxs-lookup"><span data-stu-id="e4b24-239">This parameter does not support event queries.</span></span>

```yaml
Type: System.String
Parameter Sets: WQLQuery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-240">-Recurse</span><span class="sxs-lookup"><span data-stu-id="e4b24-240">-Recurse</span></span>

<span data-ttu-id="e4b24-241">在当前命名空间和所有其他命名空间中搜索 **Class** 参数指定的类名。</span><span class="sxs-lookup"><span data-stu-id="e4b24-241">Searches the current namespace and all other namespaces for the class name that is specified by the **Class** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e4b24-242">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="e4b24-242">-ThrottleLimit</span></span>

<span data-ttu-id="e4b24-243">指定可同时执行的最大 WMI 操作数。</span><span class="sxs-lookup"><span data-stu-id="e4b24-243">Specifies the maximum number of WMI operations that can be executed simultaneously.</span></span> <span data-ttu-id="e4b24-244">仅当命令中使用了 **AsJob** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="e4b24-244">This parameter is valid only when the **AsJob** parameter is used in the command.</span></span>

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

### <span data-ttu-id="e4b24-245">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e4b24-245">CommonParameters</span></span>

<span data-ttu-id="e4b24-246">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="e4b24-246">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4b24-247">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="e4b24-247">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4b24-248">输入</span><span class="sxs-lookup"><span data-stu-id="e4b24-248">INPUTS</span></span>

### <span data-ttu-id="e4b24-249">无</span><span class="sxs-lookup"><span data-stu-id="e4b24-249">None</span></span>

<span data-ttu-id="e4b24-250">不能通过管道将输入传递给 `Get-WmiObject` 。</span><span class="sxs-lookup"><span data-stu-id="e4b24-250">You cannot pipe input to `Get-WmiObject`.</span></span>

## <span data-ttu-id="e4b24-251">输出</span><span class="sxs-lookup"><span data-stu-id="e4b24-251">OUTPUTS</span></span>

### <span data-ttu-id="e4b24-252">PSObject 或 System.Management.Automation.RemotingJob</span><span class="sxs-lookup"><span data-stu-id="e4b24-252">PSObject or System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="e4b24-253">如果使用的是 **AsJob** 参数，则该 cmdlet 返回作业对象。</span><span class="sxs-lookup"><span data-stu-id="e4b24-253">When you use the **AsJob** parameter, the cmdlet returns a job object.</span></span> <span data-ttu-id="e4b24-254">否则，返回的对象 `Get-WmiObject` 取决于 **Class** 参数的值。</span><span class="sxs-lookup"><span data-stu-id="e4b24-254">Otherwise, the object that `Get-WmiObject` returns depends on the value of the **Class** parameter.</span></span>

## <span data-ttu-id="e4b24-255">注释</span><span class="sxs-lookup"><span data-stu-id="e4b24-255">NOTES</span></span>

<span data-ttu-id="e4b24-256">若要访问远程计算机上的 WMI 的信息，则 cmdlet 必须在远程计算机上的本地管理员组的成员帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="e4b24-256">To access WMI information on a remote computer, the cmdlet must run under an account that is a member of the local administrators group on the remote computer.</span></span> <span data-ttu-id="e4b24-257">或者，可以更改远程存储库的 WMI 命名空间上的默认访问控制，以授予其他帐户访问权限。</span><span class="sxs-lookup"><span data-stu-id="e4b24-257">Or, the default access control on the WMI namespace of the remote repository can be changed to give access rights to other accounts.</span></span>

<span data-ttu-id="e4b24-258">默认情况下，只显示每个 WMI 类的部分属性。</span><span class="sxs-lookup"><span data-stu-id="e4b24-258">Only some of the properties of each WMI class are displayed by default.</span></span> <span data-ttu-id="e4b24-259">在 Types.ps1xml 配置文件中指定将为每个 WMI 类显示的属性组。</span><span class="sxs-lookup"><span data-stu-id="e4b24-259">The set of properties that is displayed for each WMI class is specified in the Types.ps1xml configuration file.</span></span> <span data-ttu-id="e4b24-260">若要获取 WMI 对象的所有属性，请使用 `Get-Member` 或 `Format-List` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e4b24-260">To get all properties of a WMI object, use the `Get-Member` or `Format-List` cmdlets.</span></span>

## <span data-ttu-id="e4b24-261">相关链接</span><span class="sxs-lookup"><span data-stu-id="e4b24-261">RELATED LINKS</span></span>

[<span data-ttu-id="e4b24-262">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="e4b24-262">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="e4b24-263">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="e4b24-263">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="e4b24-264">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="e4b24-264">Set-WmiInstance</span></span>](Set-WmiInstance.md)

[<span data-ttu-id="e4b24-265">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e4b24-265">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="e4b24-266">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="e4b24-266">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="e4b24-267">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e4b24-267">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="e4b24-268">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="e4b24-268">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)
