---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/start-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-DscConfiguration
ms.openlocfilehash: c34754aeb7fce99030cf4ddb235e3e7e8161f3eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198252"
---
# <span data-ttu-id="9c45a-103">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c45a-103">Start-DscConfiguration</span></span>

## <span data-ttu-id="9c45a-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9c45a-104">SYNOPSIS</span></span>
<span data-ttu-id="9c45a-105">将配置应用到节点。</span><span class="sxs-lookup"><span data-stu-id="9c45a-105">Applies configuration to nodes.</span></span>

## <span data-ttu-id="9c45a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9c45a-106">SYNTAX</span></span>

### <span data-ttu-id="9c45a-107">ComputerNameAndPathSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="9c45a-107">ComputerNameAndPathSet (Default)</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-JobName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="9c45a-108">CimSessionAndPathSet</span><span class="sxs-lookup"><span data-stu-id="9c45a-108">CimSessionAndPathSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-Path] <String>] -CimSession <CimSession[]> [-ThrottleLimit <Int32>]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9c45a-109">ComputerNameAndUseExistingSet</span><span class="sxs-lookup"><span data-stu-id="9c45a-109">ComputerNameAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-UseExisting] [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9c45a-110">CimSessionAndUseExistingSet</span><span class="sxs-lookup"><span data-stu-id="9c45a-110">CimSessionAndUseExistingSet</span></span>

```
Start-DscConfiguration [-Wait] [-Force] -CimSession <CimSession[]> [-ThrottleLimit <Int32>] [-UseExisting]
 [-JobName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9c45a-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9c45a-111">DESCRIPTION</span></span>
<span data-ttu-id="9c45a-112">**Start-DscConfiguration** cmdlet 将配置应用到节点。</span><span class="sxs-lookup"><span data-stu-id="9c45a-112">The **Start-DscConfiguration** cmdlet applies configuration to nodes.</span></span>
<span data-ttu-id="9c45a-113">与 *UseExisting* 参数一起使用时，将应用目标计算机上的现有配置。</span><span class="sxs-lookup"><span data-stu-id="9c45a-113">When used with the *UseExisting* parameter, the existing configuration on the target computer is applied.</span></span>
<span data-ttu-id="9c45a-114">通过指定计算机名称或通过使用通用信息模型 (CIM) 会话来指定要将配置应用到的计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-114">Specify which computers that you want to apply configuration to by specifying computer names or by using Common Information Model (CIM) sessions.</span></span>

<span data-ttu-id="9c45a-115">默认情况下，此 cmdlet 会创建一个作业，并返回 **Job** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c45a-115">By default, this cmdlet creates a job and returns a **Job** object.</span></span>
<span data-ttu-id="9c45a-116">有关后台作业的详细信息，请键入 `Get-Help about_Jobs` 。</span><span class="sxs-lookup"><span data-stu-id="9c45a-116">For more information about background jobs, type `Get-Help about_Jobs`.</span></span>
<span data-ttu-id="9c45a-117">若要以交互方式使用此 cmdlet，请指定 *Wait* 参数。</span><span class="sxs-lookup"><span data-stu-id="9c45a-117">To use this cmdlet interactively, specify the *Wait* parameter.</span></span>

<span data-ttu-id="9c45a-118">指定 *Verbose* 参数，以查看该 cmdlet 在应用配置设置时所执行的操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9c45a-118">Specify the *Verbose* parameter to see details of what the cmdlet does when it applies configuration settings.</span></span>

## <span data-ttu-id="9c45a-119">示例</span><span class="sxs-lookup"><span data-stu-id="9c45a-119">EXAMPLES</span></span>

### <span data-ttu-id="9c45a-120">示例1：应用配置设置</span><span class="sxs-lookup"><span data-stu-id="9c45a-120">Example 1: Apply configuration settings</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="9c45a-121">此命令将 C:\DSC\Configurations\ 中的配置设置应用到在该文件夹中具有设置的每台计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-121">This command applies the configuration settings from C:\DSC\Configurations\ to the every computer that has settings in that folder.</span></span>
<span data-ttu-id="9c45a-122">对于部署到的每个目标节点，该命令将返回 **Job** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c45a-122">The command returns **Job** objects for each target node deployed to.</span></span>

### <span data-ttu-id="9c45a-123">示例2：应用配置设置并等待配置完成</span><span class="sxs-lookup"><span data-stu-id="9c45a-123">Example 2: Apply configuration settings and wait for configuration to complete</span></span>

```
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -Wait -Verbose
```

<span data-ttu-id="9c45a-124">此命令将 C:\DSC\Configurations\ 中的配置应用到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-124">This command applies the configuration from C:\DSC\Configurations\ to the local computer.</span></span>
<span data-ttu-id="9c45a-125">对于部署到的每个目标节点（在此示例中，仅为本地计算机），该命令将返回 **Job** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c45a-125">The command returns **Job** objects for each target node deployed to, in this case, just the local computer.</span></span>
<span data-ttu-id="9c45a-126">此示例指定 *详细* 参数。</span><span class="sxs-lookup"><span data-stu-id="9c45a-126">This example specifies the *Verbose* parameter.</span></span>
<span data-ttu-id="9c45a-127">因此，该命令会在控制台继续时向控制台发送消息。</span><span class="sxs-lookup"><span data-stu-id="9c45a-127">Therefore, the command sends messages to the console as it proceeds.</span></span>
<span data-ttu-id="9c45a-128">该命令包括 *Wait* 参数。</span><span class="sxs-lookup"><span data-stu-id="9c45a-128">The command includes the *Wait* parameter.</span></span>
<span data-ttu-id="9c45a-129">因此，只有在命令完成所有配置任务后，才能使用控制台。</span><span class="sxs-lookup"><span data-stu-id="9c45a-129">Therefore, you cannot use the console until the command finishes all configuration tasks.</span></span>

### <span data-ttu-id="9c45a-130">示例3：使用 CIM 会话应用配置设置</span><span class="sxs-lookup"><span data-stu-id="9c45a-130">Example 3: Apply configuration settings by using a CIM session</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Start-DscConfiguration -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="9c45a-131">此示例将配置设置应用到指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-131">This example applies configuration settings to a specified computer.</span></span>
<span data-ttu-id="9c45a-132">该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="9c45a-132">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="9c45a-133">或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-133">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="9c45a-134">第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。</span><span class="sxs-lookup"><span data-stu-id="9c45a-134">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="9c45a-135">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="9c45a-135">The command prompts you for a password.</span></span>
<span data-ttu-id="9c45a-136">要了解详情，请键入 `Get-Help NewCimSession`。</span><span class="sxs-lookup"><span data-stu-id="9c45a-136">For more information, type `Get-Help NewCimSession`.</span></span>

<span data-ttu-id="9c45a-137">第二个命令将 C:\DSC\Configurations\ 中的配置设置应用于存储在 $Session 变量中的 **CimSession** 对象所标识的计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-137">The second command applies the configuration settings from C:\DSC\Configurations\ to the computers identified by the **CimSession** objects stored in the $Session variable.</span></span>
<span data-ttu-id="9c45a-138">在此示例中，$Session 变量包含仅适用于名为 Server01 的计算机的 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="9c45a-138">In this example, the $Session variable contains a CIM session only for the computer named Server01.</span></span>
<span data-ttu-id="9c45a-139">该命令应用此配置。</span><span class="sxs-lookup"><span data-stu-id="9c45a-139">The command applies the configuration.</span></span>
<span data-ttu-id="9c45a-140">该命令为每个已配置的计算机创建 **Job** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c45a-140">The command creates **Job** objects for each configured computer.</span></span>

## <span data-ttu-id="9c45a-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9c45a-141">PARAMETERS</span></span>

### <span data-ttu-id="9c45a-142">-CimSession</span><span class="sxs-lookup"><span data-stu-id="9c45a-142">-CimSession</span></span>
<span data-ttu-id="9c45a-143">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9c45a-143">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="9c45a-144">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="9c45a-144">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="9c45a-145">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="9c45a-145">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9c45a-146">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9c45a-146">-ComputerName</span></span>
<span data-ttu-id="9c45a-147">指定一个计算机名称数组。</span><span class="sxs-lookup"><span data-stu-id="9c45a-147">Specifies an array of computer names.</span></span>
<span data-ttu-id="9c45a-148">此参数将 *路径* 参数中具有配置文档的计算机限制为数组中指定的配置文档。</span><span class="sxs-lookup"><span data-stu-id="9c45a-148">This parameter restricts the computers that have configuration documents in the *Path* parameter to those specified in the array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="9c45a-149">-Credential</span><span class="sxs-lookup"><span data-stu-id="9c45a-149">-Credential</span></span>
<span data-ttu-id="9c45a-150">针对目标计算机，指定用户名和密码作为 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c45a-150">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="9c45a-151">若要获取 **PSCredential** 对象，请使用 Get-Credential cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9c45a-151">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="9c45a-152">要了解详情，请键入 `Get-Help Get-Credential`。</span><span class="sxs-lookup"><span data-stu-id="9c45a-152">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameAndPathSet, ComputerNameAndUseExistingSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c45a-153">-Force</span><span class="sxs-lookup"><span data-stu-id="9c45a-153">-Force</span></span>
<span data-ttu-id="9c45a-154">停止目标计算机上当前正在运行的配置操作并开始新的 Start-Configuration 操作。</span><span class="sxs-lookup"><span data-stu-id="9c45a-154">Stops the configuration operation currently running on the target computer and begins the new Start-Configuration operation.</span></span>
<span data-ttu-id="9c45a-155">如果本地 Configuration Manager 的 **RefreshMode** 属性设置为 **Pull** ，则指定此参数会将其更改为 **Push** 。</span><span class="sxs-lookup"><span data-stu-id="9c45a-155">If the **RefreshMode** property of the Local Configuration Manager is set to **Pull** , specifying this parameter changes it to **Push** .</span></span>

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

### <span data-ttu-id="9c45a-156">-JobName</span><span class="sxs-lookup"><span data-stu-id="9c45a-156">-JobName</span></span>
<span data-ttu-id="9c45a-157">为作业指定一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="9c45a-157">Specifies a friendly name for a job.</span></span>
<span data-ttu-id="9c45a-158">如果指定此参数，则 cmdlet 将作为作业运行，并且它将返回 **Job** 对象。</span><span class="sxs-lookup"><span data-stu-id="9c45a-158">If you specify this parameter, the cmdlet runs as a job, and it returns a **Job** object.</span></span>

<span data-ttu-id="9c45a-159">默认情况下，Windows PowerShell 将名称 JobN，其中 N 为整数。</span><span class="sxs-lookup"><span data-stu-id="9c45a-159">By default, Windows PowerShell assigns the name JobN where N is an integer.</span></span>

<span data-ttu-id="9c45a-160">如果指定 *Wait* 参数，则不指定此参数。</span><span class="sxs-lookup"><span data-stu-id="9c45a-160">If you specify the *Wait* parameter, do not specify this parameter.</span></span>

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

### <span data-ttu-id="9c45a-161">-Path</span><span class="sxs-lookup"><span data-stu-id="9c45a-161">-Path</span></span>
<span data-ttu-id="9c45a-162">指定包含配置设置文件的文件夹的文件路径。</span><span class="sxs-lookup"><span data-stu-id="9c45a-162">Specifies a file path of a folder that contains configuration settings files.</span></span>
<span data-ttu-id="9c45a-163">此 cmdlet 将这些配置设置发布和应用到在指定路径中具有设置文件的计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-163">This cmdlet publishes and applies these configuration settings to computers that have settings files in the specified path.</span></span>
<span data-ttu-id="9c45a-164">每个目标节点必须具有以下格式的设置文件： NetBIOS 名称。</span><span class="sxs-lookup"><span data-stu-id="9c45a-164">Each target node must have a settings file of the following format: NetBIOS Name.mof.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c45a-165">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9c45a-165">-ThrottleLimit</span></span>
<span data-ttu-id="9c45a-166">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="9c45a-166">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="9c45a-167">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="9c45a-167">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="9c45a-168">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="9c45a-168">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="9c45a-169">-UseExisting</span><span class="sxs-lookup"><span data-stu-id="9c45a-169">-UseExisting</span></span>
<span data-ttu-id="9c45a-170">指示此 cmdlet 应用现有的配置。</span><span class="sxs-lookup"><span data-stu-id="9c45a-170">Indicates that this cmdlet applies the existing configuration.</span></span>
<span data-ttu-id="9c45a-171">通过制定使用 **start-dscconfiguration** 或使用 Publish-DscConfiguration cmdlet 的发布，可以在目标计算机上存在配置。</span><span class="sxs-lookup"><span data-stu-id="9c45a-171">The configuration can exist on the target computer by enactment using **Start-DscConfiguration** or by publication using the Publish-DscConfiguration cmdlet.</span></span>

<span data-ttu-id="9c45a-172">为此 cmdlet 指定此参数之前，请查看[Windows PowerShell 5.0 的新增功能](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)中的信息</span><span class="sxs-lookup"><span data-stu-id="9c45a-172">Before you specify this parameter for this cmdlet, review the information in [What's New in Windows PowerShell 5.0](/powershell/scripting/whats-new/what-s-new-in-windows-powershell-50)</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameAndUseExistingSet, CimSessionAndUseExistingSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9c45a-173">-Wait</span><span class="sxs-lookup"><span data-stu-id="9c45a-173">-Wait</span></span>
<span data-ttu-id="9c45a-174">指示该 cmdlet 将阻止控制台，直到它完成所有的配置任务。</span><span class="sxs-lookup"><span data-stu-id="9c45a-174">Indicates that the cmdlet blocks the console until it finishes all configuration tasks.</span></span>

<span data-ttu-id="9c45a-175">如果指定此参数，则不指定 *JobName* 参数。</span><span class="sxs-lookup"><span data-stu-id="9c45a-175">If you specify this parameter, do not specify the *JobName* parameter.</span></span>

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

### <span data-ttu-id="9c45a-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9c45a-176">-Confirm</span></span>
<span data-ttu-id="9c45a-177">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="9c45a-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9c45a-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9c45a-178">-WhatIf</span></span>
<span data-ttu-id="9c45a-179">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="9c45a-179">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9c45a-180">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="9c45a-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9c45a-181">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9c45a-181">CommonParameters</span></span>
<span data-ttu-id="9c45a-182">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9c45a-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9c45a-183">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9c45a-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9c45a-184">输入</span><span class="sxs-lookup"><span data-stu-id="9c45a-184">INPUTS</span></span>

## <span data-ttu-id="9c45a-185">输出</span><span class="sxs-lookup"><span data-stu-id="9c45a-185">OUTPUTS</span></span>

## <span data-ttu-id="9c45a-186">注释</span><span class="sxs-lookup"><span data-stu-id="9c45a-186">NOTES</span></span>

## <span data-ttu-id="9c45a-187">相关链接</span><span class="sxs-lookup"><span data-stu-id="9c45a-187">RELATED LINKS</span></span>

[<span data-ttu-id="9c45a-188">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="9c45a-188">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="9c45a-189">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c45a-189">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="9c45a-190">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="9c45a-190">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="9c45a-191">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c45a-191">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="9c45a-192">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c45a-192">Stop-DscConfiguration</span></span>](Stop-DscConfiguration.md)

[<span data-ttu-id="9c45a-193">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c45a-193">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)

[<span data-ttu-id="9c45a-194">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c45a-194">Update-DscConfiguration</span></span>](Update-DscConfiguration.md)
