---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198269"
---
# <span data-ttu-id="6e22d-103">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e22d-103">Get-DscConfiguration</span></span>

## <span data-ttu-id="6e22d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="6e22d-104">SYNOPSIS</span></span>
<span data-ttu-id="6e22d-105">获取节点的当前配置。</span><span class="sxs-lookup"><span data-stu-id="6e22d-105">Gets the current configuration of the nodes.</span></span>

## <span data-ttu-id="6e22d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e22d-106">SYNTAX</span></span>

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="6e22d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e22d-107">DESCRIPTION</span></span>
<span data-ttu-id="6e22d-108">如果配置存在，则 **start-dscconfiguration** cmdlet 将获取节点的当前配置。</span><span class="sxs-lookup"><span data-stu-id="6e22d-108">The **Get-DscConfiguration** cmdlet gets the current configuration of the nodes, if the configuration exists.</span></span>
<span data-ttu-id="6e22d-109">通过使用通用信息模型 (CIM) 会话指定计算机。</span><span class="sxs-lookup"><span data-stu-id="6e22d-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="6e22d-110">如果不指定目标计算机，则该 cmdlet 将获取本地计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="6e22d-110">If you do not specify a target computer, the cmdlet gets the configuration from the local computer.</span></span>

## <span data-ttu-id="6e22d-111">示例</span><span class="sxs-lookup"><span data-stu-id="6e22d-111">EXAMPLES</span></span>

### <span data-ttu-id="6e22d-112">示例1：获取本地计算机的配置</span><span class="sxs-lookup"><span data-stu-id="6e22d-112">Example 1: Get the configuration for the local computer</span></span>

```
PS C:\> Get-DscConfiguration
```

<span data-ttu-id="6e22d-113">此命令获取本地计算机的当前状态。</span><span class="sxs-lookup"><span data-stu-id="6e22d-113">This command gets the current state for the local computer.</span></span>

### <span data-ttu-id="6e22d-114">示例2：获取指定计算机的配置</span><span class="sxs-lookup"><span data-stu-id="6e22d-114">Example 2: Get the configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

<span data-ttu-id="6e22d-115">此示例获取 CIM 会话指定的计算机的当前状态。</span><span class="sxs-lookup"><span data-stu-id="6e22d-115">This example gets the current state from a computer specified by a CIM session.</span></span>
<span data-ttu-id="6e22d-116">该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="6e22d-116">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="6e22d-117">或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="6e22d-117">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="6e22d-118">第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 **$Session** 变量中。</span><span class="sxs-lookup"><span data-stu-id="6e22d-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the **$Session** variable.</span></span>
<span data-ttu-id="6e22d-119">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="6e22d-119">The command prompts you for a password.</span></span>
<span data-ttu-id="6e22d-120">要了解详情，请键入 `Get-Help New-CimSession`。</span><span class="sxs-lookup"><span data-stu-id="6e22d-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="6e22d-121">第二个命令将获取由存储在 **$Session** 变量中的 **CimSession** 对象标识的计算机（在此示例中，为名为 Server01 的计算机）的当前配置。</span><span class="sxs-lookup"><span data-stu-id="6e22d-121">The second command gets the current configuration for the computers identified by the **CimSession** objects stored in the **$Session** variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="6e22d-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e22d-122">PARAMETERS</span></span>

### <span data-ttu-id="6e22d-123">-AsJob</span><span class="sxs-lookup"><span data-stu-id="6e22d-123">-AsJob</span></span>
<span data-ttu-id="6e22d-124">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="6e22d-124">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="6e22d-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="6e22d-125">-CimSession</span></span>
<span data-ttu-id="6e22d-126">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6e22d-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="6e22d-127">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="6e22d-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="6e22d-128">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="6e22d-128">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="6e22d-129">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="6e22d-129">-ThrottleLimit</span></span>
<span data-ttu-id="6e22d-130">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="6e22d-130">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="6e22d-131">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="6e22d-131">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="6e22d-132">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="6e22d-132">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="6e22d-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6e22d-133">CommonParameters</span></span>
<span data-ttu-id="6e22d-134">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="6e22d-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e22d-135">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="6e22d-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e22d-136">输入</span><span class="sxs-lookup"><span data-stu-id="6e22d-136">INPUTS</span></span>

## <span data-ttu-id="6e22d-137">输出</span><span class="sxs-lookup"><span data-stu-id="6e22d-137">OUTPUTS</span></span>

## <span data-ttu-id="6e22d-138">注释</span><span class="sxs-lookup"><span data-stu-id="6e22d-138">NOTES</span></span>

## <span data-ttu-id="6e22d-139">相关链接</span><span class="sxs-lookup"><span data-stu-id="6e22d-139">RELATED LINKS</span></span>

[<span data-ttu-id="6e22d-140">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="6e22d-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="6e22d-141">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="6e22d-141">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="6e22d-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e22d-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="6e22d-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e22d-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="6e22d-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="6e22d-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
