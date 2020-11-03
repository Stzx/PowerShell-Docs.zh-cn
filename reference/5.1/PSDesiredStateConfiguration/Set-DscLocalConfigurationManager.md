---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "93198934"
---
# <span data-ttu-id="0bb36-103">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0bb36-103">Set-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="0bb36-104">摘要</span><span class="sxs-lookup"><span data-stu-id="0bb36-104">SYNOPSIS</span></span>

<span data-ttu-id="0bb36-105">向节点应用本地 Configuration Manager (LCM) 设置。</span><span class="sxs-lookup"><span data-stu-id="0bb36-105">Applies Local Configuration Manager (LCM) settings to nodes.</span></span>

## <span data-ttu-id="0bb36-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bb36-106">SYNTAX</span></span>

### <span data-ttu-id="0bb36-107">ComputerNameSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="0bb36-107">ComputerNameSet (Default)</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="0bb36-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="0bb36-108">CimSessionSet</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0bb36-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bb36-109">DESCRIPTION</span></span>

<span data-ttu-id="0bb36-110">`Set-DscLocalConfigurationManager`Cmdlet 可将 LCM 设置或元配置应用到节点。</span><span class="sxs-lookup"><span data-stu-id="0bb36-110">The `Set-DscLocalConfigurationManager` cmdlet applies LCM settings, or meta-configuration, to nodes.</span></span> <span data-ttu-id="0bb36-111">通过指定计算机名称或通过使用通用信息模型 (CIM) 会话来指定计算机。</span><span class="sxs-lookup"><span data-stu-id="0bb36-111">Specify computers by specifying computer names or by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="0bb36-112">如果不指定目标计算机，则该 cmdlet 将设置应用到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="0bb36-112">If you do not specify a target computer, the cmdlet applies settings to the local computer.</span></span>

## <span data-ttu-id="0bb36-113">示例</span><span class="sxs-lookup"><span data-stu-id="0bb36-113">EXAMPLES</span></span>

### <span data-ttu-id="0bb36-114">示例1：应用 LCM 设置</span><span class="sxs-lookup"><span data-stu-id="0bb36-114">Example 1: Apply LCM settings</span></span>

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="0bb36-115">此命令将 LCM 设置从应用 `C:\DSC\Configurations\` 到目标节点。</span><span class="sxs-lookup"><span data-stu-id="0bb36-115">This command applies the LCM settings from `C:\DSC\Configurations\` to the targeted nodes.</span></span> <span data-ttu-id="0bb36-116">收到设置后，LCM 会处理它们。</span><span class="sxs-lookup"><span data-stu-id="0bb36-116">After receiving the settings, LCM processes them.</span></span>

> [!WARNING]
> <span data-ttu-id="0bb36-117">如果指定文件夹中存储的同一台计算机有多个元 mof，则只会应用第一个元 mof。</span><span class="sxs-lookup"><span data-stu-id="0bb36-117">If there are multiple meta mofs for the same computer stored in the specified folder, only the first meta mof will be applied.</span></span>

### <span data-ttu-id="0bb36-118">示例2：使用 CIM 会话应用 LCM 设置</span><span class="sxs-lookup"><span data-stu-id="0bb36-118">Example 2: Apply LCM settings by using a CIM session</span></span>

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="0bb36-119">此示例将 LCM 设置应用到计算机，并应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="0bb36-119">This example applies LCM settings to a computer and applies the settings.</span></span> <span data-ttu-id="0bb36-120">该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="0bb36-120">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span> <span data-ttu-id="0bb36-121">或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="0bb36-121">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="0bb36-122">第一个命令使用 cmdlet 创建 CIM 会话 `New-CimSession` ，然后将 **CimSession** 对象存储在 `$Session` 变量中。</span><span class="sxs-lookup"><span data-stu-id="0bb36-122">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the `$Session` variable.</span></span> <span data-ttu-id="0bb36-123">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="0bb36-123">The command prompts you for a password.</span></span> <span data-ttu-id="0bb36-124">要了解详情，请键入 `Get-Help New-CimSession`。</span><span class="sxs-lookup"><span data-stu-id="0bb36-124">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="0bb36-125">第二个命令将目标节点的 LCM 设置应用于 `C:\DSC\Configurations\` 由变量中存储的 **CimSession** 对象标识的计算机 `$Session` 。</span><span class="sxs-lookup"><span data-stu-id="0bb36-125">The second command applies LCM settings for the targeted node from `C:\DSC\Configurations\` to the computer identified by the **CimSession** objects stored in the `$Session` variable.</span></span> <span data-ttu-id="0bb36-126">在此示例中， `$Session` 变量只包含一个名为 Server01 的计算机的 CIM 会话。</span><span class="sxs-lookup"><span data-stu-id="0bb36-126">In this example, the `$Session` variable contains a CIM session only for the computer named Server01.</span></span> <span data-ttu-id="0bb36-127">该命令将应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="0bb36-127">The command applies the settings.</span></span> <span data-ttu-id="0bb36-128">收到设置后，LCM 会处理它们。</span><span class="sxs-lookup"><span data-stu-id="0bb36-128">After receiving the settings, LCM processes them.</span></span>

## <span data-ttu-id="0bb36-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bb36-129">PARAMETERS</span></span>

### <span data-ttu-id="0bb36-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="0bb36-130">-CimSession</span></span>

<span data-ttu-id="0bb36-131">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0bb36-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="0bb36-132">输入计算机名或会话对象，例如 [CimSession](/powershell/module/CimCmdlets/New-CimSession) 或 [CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="0bb36-132">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) or [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet.</span></span>
<span data-ttu-id="0bb36-133">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="0bb36-133">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="0bb36-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0bb36-134">-ComputerName</span></span>

<span data-ttu-id="0bb36-135">指定一个计算机名称数组。</span><span class="sxs-lookup"><span data-stu-id="0bb36-135">Specifies an array of computer names.</span></span> <span data-ttu-id="0bb36-136">此参数将 **Path** 参数中包含元配置文档的计算机限制为数组中指定的文档。</span><span class="sxs-lookup"><span data-stu-id="0bb36-136">This parameter restricts the computers that have meta-configuration documents in the **Path** parameter to those specified in the array.</span></span>

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

### <span data-ttu-id="0bb36-137">-Credential</span><span class="sxs-lookup"><span data-stu-id="0bb36-137">-Credential</span></span>

<span data-ttu-id="0bb36-138">针对目标计算机，指定用户名和密码作为 **PSCredential** 对象。</span><span class="sxs-lookup"><span data-stu-id="0bb36-138">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span> <span data-ttu-id="0bb36-139">若要获取 **PSCredential** 对象，请使用 Get-Credential cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0bb36-139">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span> <span data-ttu-id="0bb36-140">要了解详情，请键入 `Get-Help Get-Credential`。</span><span class="sxs-lookup"><span data-stu-id="0bb36-140">For more information, type `Get-Help Get-Credential`.</span></span>

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

### <span data-ttu-id="0bb36-141">-Force</span><span class="sxs-lookup"><span data-stu-id="0bb36-141">-Force</span></span>

<span data-ttu-id="0bb36-142">强制运行命令而不要求用户确认。</span><span class="sxs-lookup"><span data-stu-id="0bb36-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="0bb36-143">-Path</span><span class="sxs-lookup"><span data-stu-id="0bb36-143">-Path</span></span>

<span data-ttu-id="0bb36-144">指定包含配置设置文件的文件夹的文件路径。</span><span class="sxs-lookup"><span data-stu-id="0bb36-144">Specifies a file path of a folder that contains configuration settings files.</span></span> <span data-ttu-id="0bb36-145">Cmdlet 将这些 LCM 设置发布并应用到在指定路径中具有设置文件的计算机。</span><span class="sxs-lookup"><span data-stu-id="0bb36-145">The cmdlet publishes and applies these LCM settings to computers that have settings files in the specified path.</span></span> <span data-ttu-id="0bb36-146">每个目标节点必须具有以下格式的设置文件： `NetBIOS Name.meta.mof` 。</span><span class="sxs-lookup"><span data-stu-id="0bb36-146">Each target node must have a settings file of the following format: `NetBIOS Name.meta.mof`.</span></span>

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

### <span data-ttu-id="0bb36-147">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="0bb36-147">-ThrottleLimit</span></span>

<span data-ttu-id="0bb36-148">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="0bb36-148">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span> <span data-ttu-id="0bb36-149">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="0bb36-149">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="0bb36-150">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="0bb36-150">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="0bb36-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0bb36-151">-Confirm</span></span>

<span data-ttu-id="0bb36-152">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="0bb36-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="0bb36-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0bb36-153">-WhatIf</span></span>

<span data-ttu-id="0bb36-154">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="0bb36-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0bb36-155">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="0bb36-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="0bb36-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bb36-156">CommonParameters</span></span>

<span data-ttu-id="0bb36-157">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="0bb36-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bb36-158">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="0bb36-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bb36-159">输入</span><span class="sxs-lookup"><span data-stu-id="0bb36-159">INPUTS</span></span>

## <span data-ttu-id="0bb36-160">输出</span><span class="sxs-lookup"><span data-stu-id="0bb36-160">OUTPUTS</span></span>

## <span data-ttu-id="0bb36-161">注释</span><span class="sxs-lookup"><span data-stu-id="0bb36-161">NOTES</span></span>

## <span data-ttu-id="0bb36-162">相关链接</span><span class="sxs-lookup"><span data-stu-id="0bb36-162">RELATED LINKS</span></span>

[<span data-ttu-id="0bb36-163">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="0bb36-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="0bb36-164">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="0bb36-164">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)
