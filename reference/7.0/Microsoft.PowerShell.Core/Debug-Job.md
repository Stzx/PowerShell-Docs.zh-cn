---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/debug-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Job
ms.openlocfilehash: 947fcea58ea32e34bdd0dc0129443ac5bc39c561
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197148"
---
# <span data-ttu-id="fffc8-103">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-103">Debug-Job</span></span>

## <span data-ttu-id="fffc8-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fffc8-104">SYNOPSIS</span></span>
<span data-ttu-id="fffc8-105">调试正在运行的后台工作流作业。</span><span class="sxs-lookup"><span data-stu-id="fffc8-105">Debugs a running background, remote, or PowerShell Workflow job.</span></span>

## <span data-ttu-id="fffc8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fffc8-106">SYNTAX</span></span>

### <span data-ttu-id="fffc8-107">JobParameterSet (默认值) </span><span class="sxs-lookup"><span data-stu-id="fffc8-107">JobParameterSet (Default)</span></span>

```
Debug-Job [-Job] <Job> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fffc8-108">JobNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="fffc8-108">JobNameParameterSet</span></span>

```
Debug-Job [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fffc8-109">JobIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="fffc8-109">JobIdParameterSet</span></span>

```
Debug-Job [-Id] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fffc8-110">JobInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="fffc8-110">JobInstanceIdParameterSet</span></span>

```
Debug-Job [-InstanceId] <Guid> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fffc8-111">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fffc8-111">DESCRIPTION</span></span>
<span data-ttu-id="fffc8-112">**调试-Job** cmdlet 可让你调试在作业中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="fffc8-112">The **Debug-Job** cmdlet lets you debug scripts that are running within jobs.</span></span>
<span data-ttu-id="fffc8-113">该 cmdlet 旨在调试 PowerShell 工作流作业、后台作业和在远程会话中运行的作业。</span><span class="sxs-lookup"><span data-stu-id="fffc8-113">The cmdlet is designed to debug PowerShell Workflow jobs, background jobs, and jobs running in remote sessions.</span></span>
<span data-ttu-id="fffc8-114">**调试-作业** 接受正在运行的作业对象、名称、id 或实例 ID 作为输入，并在其正在运行的脚本上启动调试会话。</span><span class="sxs-lookup"><span data-stu-id="fffc8-114">**Debug-Job** accepts a running job object, name, ID, or instance ID as input, and starts a debugging session on the script it is running.</span></span>
<span data-ttu-id="fffc8-115">调试器 **quit** 命令停止作业并运行脚本。</span><span class="sxs-lookup"><span data-stu-id="fffc8-115">The debugger **quit** command stops the job and running script.</span></span>
<span data-ttu-id="fffc8-116">从 Windows PowerShell 5.0 开始， **exit** 命令将分离调试器，并允许作业继续运行。</span><span class="sxs-lookup"><span data-stu-id="fffc8-116">Starting in Windows PowerShell 5.0, the **exit** command detaches the debugger, and allows the job to continue to run.</span></span>

## <span data-ttu-id="fffc8-117">示例</span><span class="sxs-lookup"><span data-stu-id="fffc8-117">EXAMPLES</span></span>

### <span data-ttu-id="fffc8-118">示例1：按作业 ID 调试作业</span><span class="sxs-lookup"><span data-stu-id="fffc8-118">Example 1: Debug a job by job ID</span></span>

```
PS C:\> Debug-Job -ID 3
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
3      Job3            RemoteJob       Running       True            PowerShellIx         TestWFDemo1.ps1
          Entering debug mode. Use h or ? for help.

          Hit Line breakpoint on 'C:\TestWFDemo1.ps1:8'

          At C:\TestWFDemo1.ps1:8 char:5
          +     Write-Output -InputObject "Now writing output:"
          +     ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
          [DBG:PowerShellIx]: PS C:\> > list

              3:
              4:  workflow SampleWorkflowTest
              5:  {
              6:      param ($MyOutput)
              7:
              8:*     Write-Output -InputObject "Now writing output:"
              9:      Write-Output -Input $MyOutput
             10:
             11:      Write-Output -InputObject "Get PowerShell process:"
             12:      Get-Process -Name powershell
             13:
             14:      Write-Output -InputObject "Workflow function complete."
             15:  }
             16:
             17:  # Call workflow function
             18:  SampleWorkflowTest -MyOutput "Hello"
```

<span data-ttu-id="fffc8-119">此命令中断 ID 为3的正在运行的作业。</span><span class="sxs-lookup"><span data-stu-id="fffc8-119">This command breaks into a running job with an ID of 3.</span></span>

## <span data-ttu-id="fffc8-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fffc8-120">PARAMETERS</span></span>

### <span data-ttu-id="fffc8-121">-Id</span><span class="sxs-lookup"><span data-stu-id="fffc8-121">-Id</span></span>
<span data-ttu-id="fffc8-122">指定正在运行的作业的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="fffc8-122">Specifies the ID number of a running job.</span></span>
<span data-ttu-id="fffc8-123">若要获取作业的 ID 号，请运行 Get-Job cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fffc8-123">To get the ID number of a job, run the Get-Job cmdlet.</span></span>

```yaml
Type: System.Int32
Parameter Sets: JobIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fffc8-124">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="fffc8-124">-InstanceId</span></span>
<span data-ttu-id="fffc8-125">指定正在运行的作业的实例 ID GUID。</span><span class="sxs-lookup"><span data-stu-id="fffc8-125">Specifies the instance ID GUID of a running job.</span></span>
<span data-ttu-id="fffc8-126">若要获取作业的实例 *id* ，请运行 " **获取作业** " cmdlet，将结果传递给 **格式-** \* cmdlet，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="fffc8-126">To get the *InstanceId* of a job, run the **Get-Job** cmdlet, piping the results into a **Format-** \* cmdlet, as shown in the following example:</span></span>

`Get-Job | Format-List -Property Id,Name,InstanceId,State`

```yaml
Type: System.Guid
Parameter Sets: JobInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fffc8-127">-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-127">-Job</span></span>
<span data-ttu-id="fffc8-128">指定正在运行的作业对象。</span><span class="sxs-lookup"><span data-stu-id="fffc8-128">Specifies a running job object.</span></span>
<span data-ttu-id="fffc8-129">使用此参数的最简单方法是保存用于返回要在变量中调试的正在运行的作业的 **Get-job** 命令的结果，然后将该变量指定为此参数的值。</span><span class="sxs-lookup"><span data-stu-id="fffc8-129">The simplest way to use this parameter is to save the results of a **Get-Job** command that returns the running job that you want to debug in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Management.Automation.Job
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fffc8-130">-Name</span><span class="sxs-lookup"><span data-stu-id="fffc8-130">-Name</span></span>
<span data-ttu-id="fffc8-131">指定作业的友好名称。</span><span class="sxs-lookup"><span data-stu-id="fffc8-131">Specifies a job by the friendly name of the job.</span></span>
<span data-ttu-id="fffc8-132">启动作业时，可以通过将 *JobName* 参数添加到 cmdlet （如 Invoke-Command 和 Start-job）中来指定作业名称。</span><span class="sxs-lookup"><span data-stu-id="fffc8-132">When you start a job, you can specify a job name by adding the *JobName* parameter, in cmdlets such as Invoke-Command and Start-Job.</span></span>

```yaml
Type: System.String
Parameter Sets: JobNameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fffc8-133">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fffc8-133">-Confirm</span></span>
<span data-ttu-id="fffc8-134">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="fffc8-134">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fffc8-135">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fffc8-135">-WhatIf</span></span>
<span data-ttu-id="fffc8-136">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="fffc8-136">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fffc8-137">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="fffc8-137">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fffc8-138">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fffc8-138">CommonParameters</span></span>
<span data-ttu-id="fffc8-139">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fffc8-139">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fffc8-140">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fffc8-140">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fffc8-141">输入</span><span class="sxs-lookup"><span data-stu-id="fffc8-141">INPUTS</span></span>

### <span data-ttu-id="fffc8-142">System.Management.Automation.RemotingJob</span><span class="sxs-lookup"><span data-stu-id="fffc8-142">System.Management.Automation.RemotingJob</span></span>

## <span data-ttu-id="fffc8-143">输出</span><span class="sxs-lookup"><span data-stu-id="fffc8-143">OUTPUTS</span></span>

## <span data-ttu-id="fffc8-144">注释</span><span class="sxs-lookup"><span data-stu-id="fffc8-144">NOTES</span></span>

## <span data-ttu-id="fffc8-145">相关链接</span><span class="sxs-lookup"><span data-stu-id="fffc8-145">RELATED LINKS</span></span>

[<span data-ttu-id="fffc8-146">Get-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-146">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="fffc8-147">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-147">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="fffc8-148">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-148">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="fffc8-149">Start-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-149">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="fffc8-150">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-150">Stop-Job</span></span>](Stop-Job.md)

[<span data-ttu-id="fffc8-151">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="fffc8-151">Wait-Job</span></span>](Wait-Job.md)
