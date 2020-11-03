---
external help file: Get-DSCLocalConfigurationManager.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscLocalConfigurationManager
ms.openlocfilehash: 162770d8eb3a8953dcfaeb31f30742a46353b33b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198259"
---
# <span data-ttu-id="9de91-103">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="9de91-103">Get-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="9de91-104">摘要</span><span class="sxs-lookup"><span data-stu-id="9de91-104">SYNOPSIS</span></span>

<span data-ttu-id="9de91-105">获取节点的本地 Configuration Manager (LCM) 设置和状态。</span><span class="sxs-lookup"><span data-stu-id="9de91-105">Gets Local Configuration Manager (LCM) settings and states for the node.</span></span>

## <span data-ttu-id="9de91-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9de91-106">SYNTAX</span></span>

```
Get-DscLocalConfigurationManager [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="9de91-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="9de91-107">DESCRIPTION</span></span>

<span data-ttu-id="9de91-108">该 `Get-DscLocalConfigurationManager` cmdlet 将获取用于节点的 lcm 设置、元配置和 lcm 的状态。</span><span class="sxs-lookup"><span data-stu-id="9de91-108">The `Get-DscLocalConfigurationManager` cmdlet gets LCM settings, or meta-configuration, and the states of LCM for the node.</span></span> <span data-ttu-id="9de91-109">通过使用通用信息模型 (CIM) 会话指定计算机。</span><span class="sxs-lookup"><span data-stu-id="9de91-109">Specify computers by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="9de91-110">如果不指定目标计算机，则该 cmdlet 将获取本地计算机的配置设置。</span><span class="sxs-lookup"><span data-stu-id="9de91-110">If you do not specify a target computer, the cmdlet gets the configuration settings from the local computer.</span></span>

## <span data-ttu-id="9de91-111">示例</span><span class="sxs-lookup"><span data-stu-id="9de91-111">EXAMPLES</span></span>

### <span data-ttu-id="9de91-112">示例1：获取本地计算机的 LCM 设置</span><span class="sxs-lookup"><span data-stu-id="9de91-112">Example 1: Get LCM settings for the local computer</span></span>

```powershell
Get-DscLocalConfigurationManager
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 47edd8c9-2798-4827-839a-b35cc87e69fb
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName
```

<span data-ttu-id="9de91-113">此命令获取本地计算机的 LCM 设置。</span><span class="sxs-lookup"><span data-stu-id="9de91-113">This command gets LCM settings for the local computer.</span></span>

<span data-ttu-id="9de91-114">有关输出的各个属性的详细信息，请参阅 [配置本地 Configuration Manager](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) 文档。</span><span class="sxs-lookup"><span data-stu-id="9de91-114">For more information on the individual attributes of the output, see the [Configuring the Local Configuration Manager](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) documentation.</span></span>

### <span data-ttu-id="9de91-115">示例2：获取指定计算机的 LCM 设置</span><span class="sxs-lookup"><span data-stu-id="9de91-115">Example 2: Get LCM settings for a specified computer</span></span>

```powershell
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Get-DscLocalConfigurationManager -CimSession $Session
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 169dfa57-a7f9-43be-a7a5-9dd06587e052
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName                 : Server01
PSComputerName                 : Server01
```

<span data-ttu-id="9de91-116">此示例将获取由 CIM 会话指定的计算机的 LCM 设置。</span><span class="sxs-lookup"><span data-stu-id="9de91-116">This example gets LCM settings for a computer specified by a CIM session.</span></span>
<span data-ttu-id="9de91-117">该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="9de91-117">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="9de91-118">或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="9de91-118">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="9de91-119">第一个命令使用 cmdlet 创建 CIM 会话 `New-CimSession` ，然后将 **CimSession** 对象存储在 $Session 变量中。</span><span class="sxs-lookup"><span data-stu-id="9de91-119">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span> <span data-ttu-id="9de91-120">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="9de91-120">The command prompts you for a password.</span></span> <span data-ttu-id="9de91-121">要了解详情，请键入 `Get-Help New-CimSession`。</span><span class="sxs-lookup"><span data-stu-id="9de91-121">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="9de91-122">第二个命令获取 $Session 变量中存储的 **CimSession** 对象标识的计算机的本地 Configuration Manager 设置。</span><span class="sxs-lookup"><span data-stu-id="9de91-122">The second command gets Local Configuration Manager settings for the computers identified by the **CimSession** objects stored in the $Session variable.</span></span> <span data-ttu-id="9de91-123">在这种情况下，计算机名为 Server01。</span><span class="sxs-lookup"><span data-stu-id="9de91-123">In this case, the computer named Server01.</span></span>

## <span data-ttu-id="9de91-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9de91-124">PARAMETERS</span></span>

### <span data-ttu-id="9de91-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="9de91-125">-AsJob</span></span>

<span data-ttu-id="9de91-126">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="9de91-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="9de91-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="9de91-127">-CimSession</span></span>

<span data-ttu-id="9de91-128">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9de91-128">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="9de91-129">输入计算机名或会话对象，例如 `New-CimSession` 或 cmdlet 的输出 `Get-CimSession` 。</span><span class="sxs-lookup"><span data-stu-id="9de91-129">Enter a computer name or a session object, such as the output of a `New-CimSession` or `Get-CimSession` cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9de91-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9de91-130">-ThrottleLimit</span></span>

<span data-ttu-id="9de91-131">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="9de91-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

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

### <span data-ttu-id="9de91-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="9de91-132">CommonParameters</span></span>

<span data-ttu-id="9de91-133">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="9de91-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9de91-134">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="9de91-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9de91-135">输入</span><span class="sxs-lookup"><span data-stu-id="9de91-135">INPUTS</span></span>

## <span data-ttu-id="9de91-136">输出</span><span class="sxs-lookup"><span data-stu-id="9de91-136">OUTPUTS</span></span>

## <span data-ttu-id="9de91-137">注释</span><span class="sxs-lookup"><span data-stu-id="9de91-137">NOTES</span></span>

## <span data-ttu-id="9de91-138">相关链接</span><span class="sxs-lookup"><span data-stu-id="9de91-138">RELATED LINKS</span></span>

[<span data-ttu-id="9de91-139">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="9de91-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="9de91-140">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="9de91-140">Set-DscLocalConfigurationManager</span></span>](Set-DscLocalConfigurationManager.md)
