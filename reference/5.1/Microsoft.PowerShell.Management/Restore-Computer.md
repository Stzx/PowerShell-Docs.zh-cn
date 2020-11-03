---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restore-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-Computer
ms.openlocfilehash: 824e9a24693c7a7de01358a048a0df55be333263
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198049"
---
# <span data-ttu-id="bef6d-103">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="bef6d-103">Restore-Computer</span></span>

## <span data-ttu-id="bef6d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="bef6d-104">SYNOPSIS</span></span>
<span data-ttu-id="bef6d-105">在本地计算机上启动系统还原。</span><span class="sxs-lookup"><span data-stu-id="bef6d-105">Starts a system restore on the local computer.</span></span>

## <span data-ttu-id="bef6d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bef6d-106">SYNTAX</span></span>

```
Restore-Computer [-RestorePoint] <Int32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="bef6d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="bef6d-107">DESCRIPTION</span></span>
<span data-ttu-id="bef6d-108">" **还原-计算机** " cmdlet 将本地计算机还原到指定的系统还原点。</span><span class="sxs-lookup"><span data-stu-id="bef6d-108">The **Restore-Computer** cmdlet restores the local computer to the specified system restore point.</span></span>

<span data-ttu-id="bef6d-109">**还原-计算机** 重启计算机。</span><span class="sxs-lookup"><span data-stu-id="bef6d-109">**Restore-Computer** restarts the computer.</span></span>
<span data-ttu-id="bef6d-110">在重新启动操作期间完成还原。</span><span class="sxs-lookup"><span data-stu-id="bef6d-110">The restore is completed during the restart operation.</span></span>

<span data-ttu-id="bef6d-111">仅在客户端操作系统（例如 Windows 7、Windows Vista 和 Windows XP）上支持系统还原点和 **还原计算机** 。</span><span class="sxs-lookup"><span data-stu-id="bef6d-111">System restore points and **Restore-Computer** are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="bef6d-112">示例</span><span class="sxs-lookup"><span data-stu-id="bef6d-112">EXAMPLES</span></span>

### <span data-ttu-id="bef6d-113">示例1：还原本地计算机</span><span class="sxs-lookup"><span data-stu-id="bef6d-113">Example 1: Restore the local computer</span></span>

```
PS C:\> Restore-Computer -RestorePoint 253
```

<span data-ttu-id="bef6d-114">此命令将本地计算机还原到序列号为253的还原点。</span><span class="sxs-lookup"><span data-stu-id="bef6d-114">This command restores the local computer to the restore point that has sequence number 253.</span></span>

### <span data-ttu-id="bef6d-115">示例2：还原本地计算机的确认</span><span class="sxs-lookup"><span data-stu-id="bef6d-115">Example 2: Restore the local computer with confirmation</span></span>

```
PS C:\> Restore-Computer -RestorePoint 255 -Confirm
Confirm
Are you sure you want to perform this action?
Performing operation "Restore-Computer" .
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="bef6d-116">此命令将本地计算机还原到序列号为255的还原点。</span><span class="sxs-lookup"><span data-stu-id="bef6d-116">This command restores the local computer to the restore point that has sequence number 255.</span></span>
<span data-ttu-id="bef6d-117">它使用 *Confirm* 参数在实际执行操作前提示用户。</span><span class="sxs-lookup"><span data-stu-id="bef6d-117">It uses the *Confirm* parameter to prompt the user before actually performing the operation.</span></span>

### <span data-ttu-id="bef6d-118">示例3：还原计算机并检查状态</span><span class="sxs-lookup"><span data-stu-id="bef6d-118">Example 3: Restore a computer and check the status</span></span>

```
PS C:\> Get-ComputerRestorePoint
PS C:\> Restore-Computer -RestorePoint 255
PS C:\> Get-ComputerRestorePoint -LastStatus
```

<span data-ttu-id="bef6d-119">这些命令运行系统还原，然后检查其状态。</span><span class="sxs-lookup"><span data-stu-id="bef6d-119">These commands run a system restore and then check its status.</span></span>

<span data-ttu-id="bef6d-120">第一个命令使用 **get-computerrestorepoint** 获取本地计算机上的还原点。</span><span class="sxs-lookup"><span data-stu-id="bef6d-120">The first command uses **Get-ComputerRestorePoint** to get the restore points on the local computer.</span></span>

<span data-ttu-id="bef6d-121">第二个命令将计算机还原到序号为255的还原点。</span><span class="sxs-lookup"><span data-stu-id="bef6d-121">The second command restores the computer to the restore point with sequence number 255.</span></span>

<span data-ttu-id="bef6d-122">第三个命令使用 *get-computerrestorepoint* Cmdlet 的 *LastStatus* 参数检查还原操作的状态。</span><span class="sxs-lookup"><span data-stu-id="bef6d-122">The third command uses the *LastStatus* parameter of *Get-ComputerRestorePoint* cmdlet to check the status of the restore operation.</span></span>
<span data-ttu-id="bef6d-123">因为 **还原计算机** 强制重新启动，所以在计算机重新启动后，将会输入此命令。</span><span class="sxs-lookup"><span data-stu-id="bef6d-123">Because **Restore-Computer** forces a restart, this command would be entered after the computer restarts.</span></span>

## <span data-ttu-id="bef6d-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bef6d-124">PARAMETERS</span></span>

### <span data-ttu-id="bef6d-125">-RestorePoint</span><span class="sxs-lookup"><span data-stu-id="bef6d-125">-RestorePoint</span></span>
<span data-ttu-id="bef6d-126">指定还原点的序号。</span><span class="sxs-lookup"><span data-stu-id="bef6d-126">Specifies the sequence number of the restore point.</span></span>
<span data-ttu-id="bef6d-127">若要查找序列号，请使用 Get-ComputerRestorePoint cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bef6d-127">To find the sequence number, use the Get-ComputerRestorePoint cmdlet.</span></span>
<span data-ttu-id="bef6d-128">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="bef6d-128">This parameter is required.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: SequenceNumber, SN, RP

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bef6d-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="bef6d-129">-Confirm</span></span>
<span data-ttu-id="bef6d-130">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="bef6d-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="bef6d-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="bef6d-131">-WhatIf</span></span>
<span data-ttu-id="bef6d-132">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="bef6d-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="bef6d-133">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="bef6d-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="bef6d-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="bef6d-134">CommonParameters</span></span>
<span data-ttu-id="bef6d-135">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="bef6d-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bef6d-136">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="bef6d-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bef6d-137">输入</span><span class="sxs-lookup"><span data-stu-id="bef6d-137">INPUTS</span></span>

### <span data-ttu-id="bef6d-138">无</span><span class="sxs-lookup"><span data-stu-id="bef6d-138">None</span></span>
<span data-ttu-id="bef6d-139">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bef6d-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bef6d-140">输出</span><span class="sxs-lookup"><span data-stu-id="bef6d-140">OUTPUTS</span></span>

### <span data-ttu-id="bef6d-141">无</span><span class="sxs-lookup"><span data-stu-id="bef6d-141">None</span></span>
<span data-ttu-id="bef6d-142">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="bef6d-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="bef6d-143">注释</span><span class="sxs-lookup"><span data-stu-id="bef6d-143">NOTES</span></span>

* <span data-ttu-id="bef6d-144">若要在 Windows Vista 和更高版本的 Windows 操作系统上运行 Restore-Computer 命令，请使用 "以管理员身份运行" 选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="bef6d-144">To run a Restore-Computer command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="bef6d-145">此 cmdlet 使用 (WMI) **SystemRestore** 类的 Windows Management Instrumentation。</span><span class="sxs-lookup"><span data-stu-id="bef6d-145">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

## <span data-ttu-id="bef6d-146">相关链接</span><span class="sxs-lookup"><span data-stu-id="bef6d-146">RELATED LINKS</span></span>

[<span data-ttu-id="bef6d-147">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="bef6d-147">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="bef6d-148">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bef6d-148">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="bef6d-149">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="bef6d-149">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="bef6d-150">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="bef6d-150">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="bef6d-151">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="bef6d-151">Restart-Computer</span></span>](Restart-Computer.md)
