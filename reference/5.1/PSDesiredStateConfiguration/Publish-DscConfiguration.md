---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/publish-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-DscConfiguration
ms.openlocfilehash: 139de2bfdb88c443e7bc48d36e37e95644556bf5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198256"
---
# <span data-ttu-id="871bd-103">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="871bd-103">Publish-DscConfiguration</span></span>

## <span data-ttu-id="871bd-104">摘要</span><span class="sxs-lookup"><span data-stu-id="871bd-104">SYNOPSIS</span></span>
<span data-ttu-id="871bd-105">将 DSC 配置发布到一组计算机。</span><span class="sxs-lookup"><span data-stu-id="871bd-105">Publishes a DSC configuration to a set of computers.</span></span>

## <span data-ttu-id="871bd-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="871bd-106">SYNTAX</span></span>

### <span data-ttu-id="871bd-107">ComputerNameSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="871bd-107">ComputerNameSet (Default)</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [[-ComputerName] <String[]>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="871bd-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="871bd-108">CimSessionSet</span></span>

```
Publish-DscConfiguration [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="871bd-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="871bd-109">DESCRIPTION</span></span>
<span data-ttu-id="871bd-110">**Publish-DscConfiguration** cmdlet 在一组计算机上发布 Windows PowerShell Desired State Configuration (DSC) 配置文档。</span><span class="sxs-lookup"><span data-stu-id="871bd-110">The **Publish-DscConfiguration** cmdlet publishes a Windows PowerShell Desired State Configuration (DSC) configuration document on set of computers.</span></span>
<span data-ttu-id="871bd-111">此 cmdlet 不应用配置。</span><span class="sxs-lookup"><span data-stu-id="871bd-111">This cmdlet does not apply the configuration.</span></span>
<span data-ttu-id="871bd-112">配置通过 Start-DscConfiguration cmdlet（在与 UseExisting  参数一起使用时）进行应用，或是在 DSC 引擎运行其一致性周期时进行应用。</span><span class="sxs-lookup"><span data-stu-id="871bd-112">Configurations are applied by either the Start-DscConfiguration cmdlet when it is used with the *UseExisting* parameter or when the DSC engine runs its consistency cycle.</span></span>
<span data-ttu-id="871bd-113">DSC 引擎也称为本地配置管理器 (LCM)。</span><span class="sxs-lookup"><span data-stu-id="871bd-113">The DSC engine is also known as the Local Configuration Manager (LCM).</span></span>

<span data-ttu-id="871bd-114">传递多个配置文档的片段时，此 cmdlet 特别有用。</span><span class="sxs-lookup"><span data-stu-id="871bd-114">This cmdlet is especially useful when fragments of multiple configuration documents are delivered.</span></span>
<span data-ttu-id="871bd-115">传递多个配置文档片段时，它们会覆盖较旧的配置文档片段。</span><span class="sxs-lookup"><span data-stu-id="871bd-115">When multiple configuration documents fragments are delivered, they overwrite the older configuration document fragments.</span></span>

## <span data-ttu-id="871bd-116">示例</span><span class="sxs-lookup"><span data-stu-id="871bd-116">EXAMPLES</span></span>

### <span data-ttu-id="871bd-117">示例 1：将配置发布到远程计算机</span><span class="sxs-lookup"><span data-stu-id="871bd-117">Example 1: Publish a configuration to a remote computer</span></span>

```
PS C:\> Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

<span data-ttu-id="871bd-118">此命令将配置发布到远程计算机。</span><span class="sxs-lookup"><span data-stu-id="871bd-118">This command publishes a configuration to a remote computer.</span></span>
<span data-ttu-id="871bd-119">运行该 cmdlet 的用户应是远程计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="871bd-119">The user who runs the cmdlet should be administrator on the remote computer.</span></span>

## <span data-ttu-id="871bd-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="871bd-120">PARAMETERS</span></span>

### <span data-ttu-id="871bd-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="871bd-121">-CimSession</span></span>
<span data-ttu-id="871bd-122">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="871bd-122">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="871bd-123">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="871bd-123">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="871bd-124">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="871bd-124">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="871bd-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="871bd-125">-ComputerName</span></span>
<span data-ttu-id="871bd-126">指定此 cmdlet 在其上发布配置的一个或多个计算机。</span><span class="sxs-lookup"><span data-stu-id="871bd-126">Specifies one or more computers on which this cmdlet publishes the configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="871bd-127">-Credential</span><span class="sxs-lookup"><span data-stu-id="871bd-127">-Credential</span></span>
<span data-ttu-id="871bd-128">指定用于访问目标设备的凭据。</span><span class="sxs-lookup"><span data-stu-id="871bd-128">Specifies credentials that are used to access the target device.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="871bd-129">-Force</span><span class="sxs-lookup"><span data-stu-id="871bd-129">-Force</span></span>
<span data-ttu-id="871bd-130">强制 cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="871bd-130">Forces the cmdlet to finish.</span></span>
<span data-ttu-id="871bd-131">如果本地配置管理器刷新模式设置为 PULL，则使用此参数会将它更改为 PUSH，并启用 DSC 配置的发布。</span><span class="sxs-lookup"><span data-stu-id="871bd-131">If the Local Configuration Manager refresh mode is set to PULL, usage of this parameter changes it to PUSH and enables publication of the DSC configuration.</span></span>
<span data-ttu-id="871bd-132">此外，如果存在挂起的 DSC 配置，则使用此参数会覆盖该挂起的配置。</span><span class="sxs-lookup"><span data-stu-id="871bd-132">Also, if a pending DSC configuration exists, usage of this parameter overwrites that pending configuration.</span></span>

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

### <span data-ttu-id="871bd-133">-Path</span><span class="sxs-lookup"><span data-stu-id="871bd-133">-Path</span></span>
<span data-ttu-id="871bd-134">指定包含要发布到目标计算机的配置的路径。</span><span class="sxs-lookup"><span data-stu-id="871bd-134">Specifies a path that contains configurations to publish to target computers.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="871bd-135">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="871bd-135">-ThrottleLimit</span></span>
<span data-ttu-id="871bd-136">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="871bd-136">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="871bd-137">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="871bd-137">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="871bd-138">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="871bd-138">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="871bd-139">-Confirm</span><span class="sxs-lookup"><span data-stu-id="871bd-139">-Confirm</span></span>
<span data-ttu-id="871bd-140">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="871bd-140">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="871bd-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="871bd-141">-WhatIf</span></span>
<span data-ttu-id="871bd-142">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="871bd-142">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="871bd-143">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="871bd-143">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="871bd-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="871bd-144">CommonParameters</span></span>
<span data-ttu-id="871bd-145">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="871bd-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="871bd-146">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="871bd-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="871bd-147">输入</span><span class="sxs-lookup"><span data-stu-id="871bd-147">INPUTS</span></span>

## <span data-ttu-id="871bd-148">输出</span><span class="sxs-lookup"><span data-stu-id="871bd-148">OUTPUTS</span></span>

## <span data-ttu-id="871bd-149">注释</span><span class="sxs-lookup"><span data-stu-id="871bd-149">NOTES</span></span>

## <span data-ttu-id="871bd-150">相关链接</span><span class="sxs-lookup"><span data-stu-id="871bd-150">RELATED LINKS</span></span>

[<span data-ttu-id="871bd-151">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="871bd-151">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="871bd-152">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="871bd-152">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="871bd-153">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="871bd-153">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="871bd-154">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="871bd-154">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="871bd-155">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="871bd-155">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="871bd-156">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="871bd-156">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
