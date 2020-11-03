---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198271"
---
# <span data-ttu-id="ab729-103">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="ab729-103">Get-DscConfigurationStatus</span></span>

## <span data-ttu-id="ab729-104">摘要</span><span class="sxs-lookup"><span data-stu-id="ab729-104">SYNOPSIS</span></span>
<span data-ttu-id="ab729-105">检索有关已完成的配置运行的数据。</span><span class="sxs-lookup"><span data-stu-id="ab729-105">Retrieves data about completed configuration runs.</span></span>

## <span data-ttu-id="ab729-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab729-106">SYNTAX</span></span>

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="ab729-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="ab729-107">DESCRIPTION</span></span>
<span data-ttu-id="ab729-108">**Get-dscconfigurationstatus** cmdlet 将检索有关系统上已完成的配置运行的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ab729-108">The **Get-DscConfigurationStatus** cmdlet retrieves detailed information about completed configuration runs on the system.</span></span>
<span data-ttu-id="ab729-109">默认情况下，它将返回有关上次配置运行的信息。</span><span class="sxs-lookup"><span data-stu-id="ab729-109">By default, it returns the information about the last configuration run.</span></span>
<span data-ttu-id="ab729-110">此 cmdlet 可用于查找有关配置运行的历史信息，如运行配置、运行状态、配置中的资源数，以及成功或失败的资源。</span><span class="sxs-lookup"><span data-stu-id="ab729-110">This cmdlet is useful for finding historical information about configuration runs, such as when the configurations were run, the status of the runs, the number of resources in the configurations, and which resources succeeded or failed.</span></span>

## <span data-ttu-id="ab729-111">示例</span><span class="sxs-lookup"><span data-stu-id="ab729-111">EXAMPLES</span></span>

### <span data-ttu-id="ab729-112">示例1：获取有关上次配置运行的信息</span><span class="sxs-lookup"><span data-stu-id="ab729-112">Example 1: Get information on the last configuration run</span></span>

```
PS C:\> Get-DscConfigurationStatus
```

<span data-ttu-id="ab729-113">此命令获取有关上次配置运行的信息。</span><span class="sxs-lookup"><span data-stu-id="ab729-113">This command gets information on the last configuration run.</span></span>

### <span data-ttu-id="ab729-114">示例2：获取所有配置的信息</span><span class="sxs-lookup"><span data-stu-id="ab729-114">Example 2: Get information on all configurations</span></span>

```
PS C:\> Get-DscConfigurationStatus -All
```

<span data-ttu-id="ab729-115">此命令将获取系统上运行的所有配置的相关信息，包括 Windows PowerShell Desired State Configuration (DSC) 一致性检查。</span><span class="sxs-lookup"><span data-stu-id="ab729-115">This command gets information about all the configurations that were run on the system, including the Windows PowerShell Desired State Configuration (DSC) consistency check.</span></span>

### <span data-ttu-id="ab729-116">示例3：获取有关在远程计算机上运行的配置的信息</span><span class="sxs-lookup"><span data-stu-id="ab729-116">Example 3: Get information on the configuration run on a remote computer</span></span>

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

<span data-ttu-id="ab729-117">此命令获取名为 Server01 的远程计算机的配置运行详细信息。</span><span class="sxs-lookup"><span data-stu-id="ab729-117">This command gets the configuration run details of the remote computer named Server01.</span></span>
<span data-ttu-id="ab729-118">这将使用 WSMan 传输连接到远程计算机，并要求连接用户是远程计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="ab729-118">This uses the WSMan transport to connect to the remote computer and requires that the connecting user be an administrator on the remote computer.</span></span>

## <span data-ttu-id="ab729-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab729-119">PARAMETERS</span></span>

### <span data-ttu-id="ab729-120">-All</span><span class="sxs-lookup"><span data-stu-id="ab729-120">-All</span></span>
<span data-ttu-id="ab729-121">指示此 cmdlet 检索计算机上运行的所有配置的相关信息，包括配置应用程序和一致性检查。</span><span class="sxs-lookup"><span data-stu-id="ab729-121">Indicates that this cmdlet retrieves information about all the configuration runs on the computer, including the configuration application and the consistency check.</span></span>

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

### <span data-ttu-id="ab729-122">-AsJob</span><span class="sxs-lookup"><span data-stu-id="ab729-122">-AsJob</span></span>
<span data-ttu-id="ab729-123">指示此 cmdlet 将命令作为后台作业运行。</span><span class="sxs-lookup"><span data-stu-id="ab729-123">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="ab729-124">-CimSession</span><span class="sxs-lookup"><span data-stu-id="ab729-124">-CimSession</span></span>
<span data-ttu-id="ab729-125">在远程会话中或在远程计算机上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ab729-125">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="ab729-126">输入计算机名或会话对象，例如 [CimSession](/powershell/module/cimcmdlets/new-cimsession) 或 [CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet 的输出。</span><span class="sxs-lookup"><span data-stu-id="ab729-126">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="ab729-127">默认为本地计算机上的当前会话。</span><span class="sxs-lookup"><span data-stu-id="ab729-127">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="ab729-128">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="ab729-128">-ThrottleLimit</span></span>
<span data-ttu-id="ab729-129">指定可为运行 cmdlet 而确立的操作的最大数量。</span><span class="sxs-lookup"><span data-stu-id="ab729-129">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="ab729-130">如果省略此参数或输入的值 `0` ，则 Windows PowerShell 会根据计算机上正在运行的 CIM cmdlet 的数目计算该 cmdlet 的最佳限制。</span><span class="sxs-lookup"><span data-stu-id="ab729-130">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="ab729-131">该限制仅适用于当前 cmdlet，不适用于会话或计算机。</span><span class="sxs-lookup"><span data-stu-id="ab729-131">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="ab729-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="ab729-132">CommonParameters</span></span>
<span data-ttu-id="ab729-133">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="ab729-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab729-134">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="ab729-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab729-135">输入</span><span class="sxs-lookup"><span data-stu-id="ab729-135">INPUTS</span></span>

## <span data-ttu-id="ab729-136">输出</span><span class="sxs-lookup"><span data-stu-id="ab729-136">OUTPUTS</span></span>

## <span data-ttu-id="ab729-137">注释</span><span class="sxs-lookup"><span data-stu-id="ab729-137">NOTES</span></span>

## <span data-ttu-id="ab729-138">相关链接</span><span class="sxs-lookup"><span data-stu-id="ab729-138">RELATED LINKS</span></span>

[<span data-ttu-id="ab729-139">Windows PowerShell Desired State Configuration 概述</span><span class="sxs-lookup"><span data-stu-id="ab729-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="ab729-140">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab729-140">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="ab729-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="ab729-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="ab729-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab729-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="ab729-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab729-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="ab729-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="ab729-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
