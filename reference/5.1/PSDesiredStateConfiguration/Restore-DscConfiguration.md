---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198254"
---
# <span data-ttu-id="c9890-103">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c9890-103">Restore-DscConfiguration</span></span>

## <span data-ttu-id="c9890-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c9890-104">SYNOPSIS</span></span>
<span data-ttu-id="c9890-105">重新应用节点以前的配置。</span><span class="sxs-lookup"><span data-stu-id="c9890-105">Reapplies the previous configuration for the node.</span></span>

## <span data-ttu-id="c9890-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c9890-106">SYNTAX</span></span>

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="c9890-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c9890-107">DESCRIPTION</span></span>
<span data-ttu-id="c9890-108">如果以前的配置存在，则 **Restore-DscConfiguration** cmdlet 将重新应用节点以前的配置。</span><span class="sxs-lookup"><span data-stu-id="c9890-108">The **Restore-DscConfiguration** cmdlet reapplies the previous configuration for the node, if a previous configuration exists.</span></span>
<span data-ttu-id="c9890-109">通过使用通用信息模型 (CIM) 会话指定计算机。</span><span class="sxs-lookup"><span data-stu-id="c9890-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="c9890-110">如果不指定目标计算机，则该 cmdlet 将还原本地计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="c9890-110">If you do not specify a target computer, the cmdlet restores the configuration of the local computer.</span></span>
<span data-ttu-id="c9890-111">如果某个特定节点没有以前的配置，此 cmdlet 将返回一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="c9890-111">If there is no previous configuration for a particular node, this cmdlet returns an error message.</span></span>

<span data-ttu-id="c9890-112">此 cmdlet 不支持 Confirm  参数。</span><span class="sxs-lookup"><span data-stu-id="c9890-112">This cmdlet does not support the **Confirm** parameter.</span></span>

## <span data-ttu-id="c9890-113">示例</span><span class="sxs-lookup"><span data-stu-id="c9890-113">EXAMPLES</span></span>

### <span data-ttu-id="c9890-114">示例 1：还原本地计算机的配置</span><span class="sxs-lookup"><span data-stu-id="c9890-114">Example 1: Restore the configuration for the local computer</span></span>

```
PS C:\> Restore-DscConfiguration
```

<span data-ttu-id="c9890-115">此命令将还原本地计算机的配置。</span><span class="sxs-lookup"><span data-stu-id="c9890-115">This command restores the configuration for the local computer.</span></span>

### <span data-ttu-id="c9890-116">示例 2：还原指定计算机的配置</span><span class="sxs-lookup"><span data-stu-id="c9890-116">Example 2: Restore configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

<span data-ttu-id="c9890-117">此示例将还原由 CIM 会话指定的计算机上的配置。</span><span class="sxs-lookup"><span data-stu-id="c9890-117">This example restores configuration on a computer specified by a CIM session.</span></span>
<span data-ttu-id="c9890-118">该示例为名为 Server01 的计算机创建 CIM 会话，以供与 cmdlet 一起使用。</span><span class="sxs-lookup"><span data-stu-id="c9890-118">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="c9890-119">或者，创建一个 CIM 会话数组以将 cmdlet 应用到多个指定的计算机。</span><span class="sxs-lookup"><span data-stu-id="c9890-119">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="c9890-120">第一个命令通过使用 **New-CimSession** cmdlet 创建 CIM 会话，然后将 **CimSession** 对象存储在 $Session 变量中。</span><span class="sxs-lookup"><span data-stu-id="c9890-120">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="c9890-121">该命令会提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="c9890-121">The command prompts you for a password.</span></span>
<span data-ttu-id="c9890-122">要了解详情，请键入 `Get-Help New-CimSession`。</span><span class="sxs-lookup"><span data-stu-id="c9890-122">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="c9890-123">第二个命令将还原由存储在 $Session 变量中的 **CimSession** 对象标识的计算机（在此示例中，为名为 Server01 的计算机）的配置。</span><span class="sxs-lookup"><span data-stu-id="c9890-123">The second command restores the configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="c9890-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c9890-124">PARAMETERS</span></span>

### <span data-ttu-id="c9890-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="c9890-125">-AsJob</span></span>
<span data-ttu-id="c9890-126">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="c9890-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="c9890-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="c9890-127">-CimSession</span></span>
<span data-ttu-id="c9890-128">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c9890-128">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="c9890-129">输入计算机名或会话对象，例如 **CimSession** 或 **CimSession** cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="c9890-129">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="c9890-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="c9890-130">-ThrottleLimit</span></span>
<span data-ttu-id="c9890-131">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="c9890-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

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

### <span data-ttu-id="c9890-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c9890-132">-Confirm</span></span>
<span data-ttu-id="c9890-133">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="c9890-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c9890-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c9890-134">-WhatIf</span></span>
<span data-ttu-id="c9890-135">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="c9890-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c9890-136">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="c9890-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c9890-137">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c9890-137">CommonParameters</span></span>
<span data-ttu-id="c9890-138">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="c9890-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c9890-139">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="c9890-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c9890-140">输入</span><span class="sxs-lookup"><span data-stu-id="c9890-140">INPUTS</span></span>

## <span data-ttu-id="c9890-141">输出</span><span class="sxs-lookup"><span data-stu-id="c9890-141">OUTPUTS</span></span>

## <span data-ttu-id="c9890-142">注释</span><span class="sxs-lookup"><span data-stu-id="c9890-142">NOTES</span></span>

## <span data-ttu-id="c9890-143">相关链接</span><span class="sxs-lookup"><span data-stu-id="c9890-143">RELATED LINKS</span></span>

[<span data-ttu-id="c9890-144">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="c9890-144">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="c9890-145">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c9890-145">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="c9890-146">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="c9890-146">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="c9890-147">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c9890-147">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="c9890-148">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c9890-148">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
