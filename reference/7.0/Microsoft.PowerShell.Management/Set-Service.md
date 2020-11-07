---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: c6aa8a16bd5ccbeb00252b872e997018b1997181
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2020
ms.locfileid: "94346694"
---
# <span data-ttu-id="2e769-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-103">Set-Service</span></span>

## <span data-ttu-id="2e769-104">摘要</span><span class="sxs-lookup"><span data-stu-id="2e769-104">SYNOPSIS</span></span>
<span data-ttu-id="2e769-105">启动、停止和挂起服务并更改服务的属性。</span><span class="sxs-lookup"><span data-stu-id="2e769-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="2e769-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e769-106">SYNTAX</span></span>

### <span data-ttu-id="2e769-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="2e769-107">Name (Default)</span></span>

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>]
 [-SecurityDescriptorSddl <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2e769-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="2e769-108">InputObject</span></span>

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-SecurityDescriptorSddl <String>]
 [-Status <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2e769-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="2e769-109">DESCRIPTION</span></span>

<span data-ttu-id="2e769-110">`Set-Service`Cmdlet 更改服务的属性，如 **状态** 、 **说明** 、 **DisplayName** 和 **StartupType** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType**.</span></span> <span data-ttu-id="2e769-111">`Set-Service` 可以启动、停止、挂起或暂停服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="2e769-112">若要标识服务，请输入其服务名称或提交服务对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="2e769-113">或者，将服务名称或服务对象向下发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="2e769-114">示例</span><span class="sxs-lookup"><span data-stu-id="2e769-114">EXAMPLES</span></span>

### <span data-ttu-id="2e769-115">示例1：更改显示名称</span><span class="sxs-lookup"><span data-stu-id="2e769-115">Example 1: Change a display name</span></span>

<span data-ttu-id="2e769-116">在此示例中，将更改服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="2e769-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="2e769-117">若要查看原始显示名称，请使用 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="2e769-118">`Set-Service` 使用 **name** 参数来指定服务的名称， **LanmanWorkstation** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation**.</span></span> <span data-ttu-id="2e769-119">**DisplayName** 参数指定新的显示名称 " **LanMan Workstation** "。</span><span class="sxs-lookup"><span data-stu-id="2e769-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation**.</span></span>

### <span data-ttu-id="2e769-120">示例2：更改服务的启动类型</span><span class="sxs-lookup"><span data-stu-id="2e769-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="2e769-121">此示例演示如何更改服务的启动类型。</span><span class="sxs-lookup"><span data-stu-id="2e769-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="2e769-122">`Set-Service` 使用 **name** 参数来指定服务的名称， **位** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS**.</span></span> <span data-ttu-id="2e769-123">**StartupType** 参数将服务设置为 **自动** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-123">The **StartupType** parameter sets the service to **Automatic**.</span></span>

<span data-ttu-id="2e769-124">`Get-Service` 使用 **Name** 参数指定 **BITS** 服务，并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="2e769-125">`Select-Object` 使用 **属性** 参数显示 **BITS** 服务的状态。</span><span class="sxs-lookup"><span data-stu-id="2e769-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="2e769-126">示例3：更改服务的描述</span><span class="sxs-lookup"><span data-stu-id="2e769-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="2e769-127">此示例更改 BITS 服务的说明并显示结果。</span><span class="sxs-lookup"><span data-stu-id="2e769-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="2e769-128">`Get-CimInstance`使用 cmdlet 的原因是它将返回一个包含服务 **说明** 的 **Win32_Service** 对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description**.</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

<span data-ttu-id="2e769-129">`Get-CimInstance` 将对象向下发送到管道， `Format-List` 并显示服务的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2e769-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="2e769-130">出于比较目的，将在更新说明之前和之后运行该命令。</span><span class="sxs-lookup"><span data-stu-id="2e769-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="2e769-131">`Set-Service` 使用 **Name** 参数指定 **BITS** 服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="2e769-132">**Description** 参数指定服务说明的更新文本。</span><span class="sxs-lookup"><span data-stu-id="2e769-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="2e769-133">示例4：启动服务</span><span class="sxs-lookup"><span data-stu-id="2e769-133">Example 4: Start a service</span></span>

<span data-ttu-id="2e769-134">在此示例中，启动了服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="2e769-135">`Set-Service` 使用 **Name** 参数来指定服务 **WinRM** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM**.</span></span> <span data-ttu-id="2e769-136">**Status** 参数使用 **运行** 的值来启动服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="2e769-137">**PassThru** 参数输出显示结果的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="2e769-138">示例5：挂起服务</span><span class="sxs-lookup"><span data-stu-id="2e769-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="2e769-139">此示例使用管道暂停到服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="2e769-140">`Get-Service` 使用 **Name** 参数指定 **计划** 服务，并沿管道向下发送对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="2e769-141">`Set-Service` 使用 **Status** 参数将服务设置为 "已 **暂停** "。</span><span class="sxs-lookup"><span data-stu-id="2e769-141">`Set-Service` uses the **Status** parameter to set the service to **Paused**.</span></span>

### <span data-ttu-id="2e769-142">示例6：停止服务</span><span class="sxs-lookup"><span data-stu-id="2e769-142">Example 6: Stop a service</span></span>

<span data-ttu-id="2e769-143">此示例使用变量来停止服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="2e769-144">`Get-Service` 使用 **Name** 参数来指定服务的 **计划** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule**.</span></span> <span data-ttu-id="2e769-145">对象存储在变量中 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="2e769-146">`Set-Service` 使用 **InputObject** 参数，并指定存储的对象 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="2e769-147">**Status** 参数将服务设置为 " **已停止** "。</span><span class="sxs-lookup"><span data-stu-id="2e769-147">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="2e769-148">示例7：停止远程系统上的服务</span><span class="sxs-lookup"><span data-stu-id="2e769-148">Example 7: Stop a service on a remote system</span></span>

<span data-ttu-id="2e769-149">此示例将停止远程计算机上的服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-149">This example stops a service on a remote computer.</span></span>
<span data-ttu-id="2e769-150">有关详细信息，请参阅 [调用-命令](../Microsoft.PowerShell.Core/Invoke-Command.md)。</span><span class="sxs-lookup"><span data-stu-id="2e769-150">For more information, see [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

<span data-ttu-id="2e769-151">`Get-Credential` 提示输入用户名和密码，并将凭据存储在变量中 `$Cred` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-151">`Get-Credential` prompts for a username and password, and stores the credentials in the `$Cred` variable.</span></span> <span data-ttu-id="2e769-152">`Get-Service` 使用 **Name** 参数来指定 **计划** 服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-152">`Get-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="2e769-153">对象存储在变量中 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-153">The object is stored in the variable, `$S`.</span></span>

<span data-ttu-id="2e769-154">`Invoke-Command` 使用 **ComputerName** 参数来指定远程计算机。</span><span class="sxs-lookup"><span data-stu-id="2e769-154">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer.</span></span> <span data-ttu-id="2e769-155">**Credential** 参数使用 `$Cred` 变量登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="2e769-155">The **Credential** parameter uses the `$Cred` variable to sign on to the computer.</span></span> <span data-ttu-id="2e769-156">**ScriptBlock** 调用 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-156">The **ScriptBlock** calls `Set-Service`.</span></span> <span data-ttu-id="2e769-157">**InputObject** 参数指定存储的服务对象 `$S` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-157">The **InputObject** parameter specifies the service object stored `$S`.</span></span> <span data-ttu-id="2e769-158">**Status** 参数将服务设置为 " **已停止** "。</span><span class="sxs-lookup"><span data-stu-id="2e769-158">The **Status** parameter sets the service to **Stopped**.</span></span>

### <span data-ttu-id="2e769-159">示例8：更改服务的凭据</span><span class="sxs-lookup"><span data-stu-id="2e769-159">Example 8: Change credential of a service</span></span>

<span data-ttu-id="2e769-160">此示例更改用于管理服务的凭据。</span><span class="sxs-lookup"><span data-stu-id="2e769-160">This example changes the credentials that are used to manage a service.</span></span>

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

<span data-ttu-id="2e769-161">`Get-Credential` 提示输入用户名和密码，并将凭据存储在变量中 `$credential` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-161">`Get-Credential` prompts for a username and password, and stores the credentials in the `$credential` variable.</span></span> <span data-ttu-id="2e769-162">`Set-Service` 使用 **Name** 参数来指定 **计划** 服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-162">`Set-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="2e769-163">**Credential** 参数使用 `$credential` 变量并更新 **计划** 服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-163">The **Credential** parameter uses the `$credential` variable and updates the **Schedule** service.</span></span>

### <span data-ttu-id="2e769-164">示例9：更改服务的 SecurityDescriptor</span><span class="sxs-lookup"><span data-stu-id="2e769-164">Example 9: Change the SecurityDescriptor of a service</span></span>

<span data-ttu-id="2e769-165">此示例将更改服务的 **SecurityDescriptor** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-165">This example changes a service's **SecurityDescriptor**.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
Set-Service -Name "BITS" -SecurityDescriptorSddl $SDDL
```

<span data-ttu-id="2e769-166">**SecurityDescriptor** 存储在 `$SDDL` 变量中。</span><span class="sxs-lookup"><span data-stu-id="2e769-166">The **SecurityDescriptor** is stored in the `$SDDL` variable.</span></span> <span data-ttu-id="2e769-167">`Set-Service` 使用 **Name** 参数指定 **BITS** 服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-167">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="2e769-168">**SecurityDescriptorSddl** 参数用于 `$SDDL` 更改 **BITS** 服务的 **SecurityDescriptor** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-168">The **SecurityDescriptorSddl** parameter uses `$SDDL` to change the **SecurityDescriptor** for the **BITS** service.</span></span>

## <span data-ttu-id="2e769-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e769-169">PARAMETERS</span></span>

### <span data-ttu-id="2e769-170">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2e769-170">-Confirm</span></span>

<span data-ttu-id="2e769-171">在运行之前提示你进行确认 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-171">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="2e769-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="2e769-172">-Credential</span></span>

<span data-ttu-id="2e769-173">将服务使用的帐户指定为 [服务登录帐户](/windows/desktop/ad/about-service-logon-accounts)。</span><span class="sxs-lookup"><span data-stu-id="2e769-173">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="2e769-174">键入用户名（如 **User01** 或 **Domain01\User01** ）或输入 PSCredential 对象，例如由 Cmdlet 生成的一个 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-174">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="2e769-175">键入用户名时，此 cmdlet 会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="2e769-175">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="2e769-176">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="2e769-176">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="2e769-177">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="2e769-177">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="2e769-178">此参数是在 PowerShell 6.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="2e769-178">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="2e769-179">-Description</span><span class="sxs-lookup"><span data-stu-id="2e769-179">-Description</span></span>

<span data-ttu-id="2e769-180">指定服务的新说明。</span><span class="sxs-lookup"><span data-stu-id="2e769-180">Specifies a new description for the service.</span></span>

<span data-ttu-id="2e769-181">服务说明出现在 **"计算机管理，服务** " 中。</span><span class="sxs-lookup"><span data-stu-id="2e769-181">The service description appears in **Computer Management, Services**.</span></span> <span data-ttu-id="2e769-182">**说明** 不是 `Get-Service` **ServiceController** 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="2e769-182">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="2e769-183">若要查看服务说明，请使用 `Get-CimInstance` ，它将返回表示服务的 **Win32_Service** 对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-183">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="2e769-184">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="2e769-184">-DisplayName</span></span>

<span data-ttu-id="2e769-185">指定服务的新显示名称。</span><span class="sxs-lookup"><span data-stu-id="2e769-185">Specifies a new display name for the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-186">-Force</span><span class="sxs-lookup"><span data-stu-id="2e769-186">-Force</span></span>

<span data-ttu-id="2e769-187">指定服务的停止模式。</span><span class="sxs-lookup"><span data-stu-id="2e769-187">Specifies the Stop mode of the service.</span></span> <span data-ttu-id="2e769-188">仅当使用时，此参数才有效 `-Status Stopped` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-188">This parameter only works when `-Status Stopped` is used.</span></span> <span data-ttu-id="2e769-189">如果启用，则在 `Set-Service` 目标服务停止之前停止从属服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-189">If enabled, `Set-Service` stops the dependent services before the target service is stopped.</span></span> <span data-ttu-id="2e769-190">默认情况下，当其他正在运行的服务依赖于目标服务时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="2e769-190">By default, exceptions are raised when other running services depend on the target service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-191">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2e769-191">-InputObject</span></span>

<span data-ttu-id="2e769-192">指定表示要更改的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-192">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="2e769-193">输入包含该对象的变量，或键入获取该对象的命令或表达式（如 `Get-Service` 命令）。</span><span class="sxs-lookup"><span data-stu-id="2e769-193">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="2e769-194">您可以使用管道将服务对象发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-194">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-195">-Name</span><span class="sxs-lookup"><span data-stu-id="2e769-195">-Name</span></span>

<span data-ttu-id="2e769-196">指定要更改的服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="2e769-196">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="2e769-197">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="2e769-197">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="2e769-198">您可以使用管道将服务名称发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-198">You can use the pipeline to send a service name to `Set-Service`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="2e769-199">-PassThru</span></span>

<span data-ttu-id="2e769-200">返回表示已更改的服务的 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-200">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="2e769-201">默认情况下， `Set-Service` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="2e769-201">By default, `Set-Service` doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-202">-StartupType</span><span class="sxs-lookup"><span data-stu-id="2e769-202">-StartupType</span></span>

<span data-ttu-id="2e769-203">指定服务的启动模式。</span><span class="sxs-lookup"><span data-stu-id="2e769-203">Specifies the start mode of the service.</span></span>

<span data-ttu-id="2e769-204">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="2e769-204">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2e769-205">**自动** -服务已启动或由操作系统在系统启动时启动。</span><span class="sxs-lookup"><span data-stu-id="2e769-205">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="2e769-206">如果一个自动启动的服务依赖于手动启动的服务，则该手动启动的服务也会在系统启动时自动启动。</span><span class="sxs-lookup"><span data-stu-id="2e769-206">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="2e769-207">**AutomaticDelayedStart** -系统启动后立即启动。</span><span class="sxs-lookup"><span data-stu-id="2e769-207">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="2e769-208">**已禁用** -服务已禁用，无法由用户或应用程序启动。</span><span class="sxs-lookup"><span data-stu-id="2e769-208">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="2e769-209">**InvalidValue** -不起作用。</span><span class="sxs-lookup"><span data-stu-id="2e769-209">**InvalidValue** - Has no effect.</span></span> <span data-ttu-id="2e769-210">Cmdlet 不会返回错误，但不会更改服务的 StartupType。</span><span class="sxs-lookup"><span data-stu-id="2e769-210">The cmdlet does not return an error but the StartupType of the service is not changed.</span></span>
- <span data-ttu-id="2e769-211">**手动** -服务仅通过用户、使用服务控制管理器或应用程序手动启动。</span><span class="sxs-lookup"><span data-stu-id="2e769-211">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST, StartType
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-212">-Status</span><span class="sxs-lookup"><span data-stu-id="2e769-212">-Status</span></span>

<span data-ttu-id="2e769-213">指定服务的状态。</span><span class="sxs-lookup"><span data-stu-id="2e769-213">Specifies the status for the service.</span></span>

<span data-ttu-id="2e769-214">此参数可接受的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="2e769-214">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="2e769-215">已 **暂停** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-215">**Paused**.</span></span> <span data-ttu-id="2e769-216">挂起服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-216">Suspends the service.</span></span>
- <span data-ttu-id="2e769-217">**正在运行** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-217">**Running**.</span></span> <span data-ttu-id="2e769-218">启动服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-218">Starts the service.</span></span>
- <span data-ttu-id="2e769-219">**已停止** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-219">**Stopped**.</span></span> <span data-ttu-id="2e769-220">停止服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-220">Stops the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-221">-SecurityDescriptorSddl</span><span class="sxs-lookup"><span data-stu-id="2e769-221">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="2e769-222">以 **Sddl** 格式指定服务的 **SecurityDescriptor** 。</span><span class="sxs-lookup"><span data-stu-id="2e769-222">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e769-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2e769-223">-WhatIf</span></span>

<span data-ttu-id="2e769-224">显示运行时将发生 `Set-Service` 的情况。</span><span class="sxs-lookup"><span data-stu-id="2e769-224">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="2e769-225">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="2e769-225">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="2e769-226">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="2e769-226">CommonParameters</span></span>

<span data-ttu-id="2e769-227">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="2e769-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e769-228">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="2e769-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e769-229">输入</span><span class="sxs-lookup"><span data-stu-id="2e769-229">INPUTS</span></span>

### <span data-ttu-id="2e769-230">System.ServiceProcess.ServiceController、System.String</span><span class="sxs-lookup"><span data-stu-id="2e769-230">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="2e769-231">您可以使用管道将服务对象或包含服务名称的字符串发送到 `Set-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-231">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="2e769-232">输出</span><span class="sxs-lookup"><span data-stu-id="2e769-232">OUTPUTS</span></span>

### <span data-ttu-id="2e769-233">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="2e769-233">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="2e769-234">默认情况下， `Set-Service` 不返回任何对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-234">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="2e769-235">使用 **PassThru** 参数输出 **ServiceController** 对象。</span><span class="sxs-lookup"><span data-stu-id="2e769-235">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="2e769-236">注释</span><span class="sxs-lookup"><span data-stu-id="2e769-236">NOTES</span></span>

<span data-ttu-id="2e769-237">此 cmdlet 仅在 Windows 平台上可用。</span><span class="sxs-lookup"><span data-stu-id="2e769-237">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="2e769-238">`Set-Service` 需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="2e769-238">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="2e769-239">使用 "以 **管理员身份运行** " 选项。</span><span class="sxs-lookup"><span data-stu-id="2e769-239">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="2e769-240">`Set-Service` 仅当当前用户有权管理服务时，才能控制服务。</span><span class="sxs-lookup"><span data-stu-id="2e769-240">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="2e769-241">如果某个命令不能正常工作，则可能没有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="2e769-241">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="2e769-242">若要查找服务的服务名称或显示名称，请使用 `Get-Service` 。</span><span class="sxs-lookup"><span data-stu-id="2e769-242">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="2e769-243">服务名称在 " **名称** " 列中，显示名称显示在 **DisplayName** 列中。</span><span class="sxs-lookup"><span data-stu-id="2e769-243">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="2e769-244">相关链接</span><span class="sxs-lookup"><span data-stu-id="2e769-244">RELATED LINKS</span></span>

[<span data-ttu-id="2e769-245">Get-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-245">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="2e769-246">New-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-246">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="2e769-247">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-247">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="2e769-248">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-248">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="2e769-249">Start-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-249">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="2e769-250">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-250">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="2e769-251">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-251">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="2e769-252">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="2e769-252">Remove-Service</span></span>](Remove-Service.md)
