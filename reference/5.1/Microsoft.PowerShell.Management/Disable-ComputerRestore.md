---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/disable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-ComputerRestore
ms.openlocfilehash: 941829c3caa0f6bb2f5712dda9eb7d8c36908062
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198304"
---
# <span data-ttu-id="07c5d-103">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="07c5d-103">Disable-ComputerRestore</span></span>

## <span data-ttu-id="07c5d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="07c5d-104">SYNOPSIS</span></span>
<span data-ttu-id="07c5d-105">在指定的文件系统驱动器上禁用系统还原功能。</span><span class="sxs-lookup"><span data-stu-id="07c5d-105">Disables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="07c5d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="07c5d-106">SYNTAX</span></span>

```
Disable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="07c5d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="07c5d-107">DESCRIPTION</span></span>
<span data-ttu-id="07c5d-108">**Disable-computerrestore** cmdlet 在一个或多个文件系统驱动器上关闭系统还原功能。</span><span class="sxs-lookup"><span data-stu-id="07c5d-108">The **Disable-ComputerRestore** cmdlet turns off the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="07c5d-109">因此，尝试还原计算机不会影响指定的驱动器。</span><span class="sxs-lookup"><span data-stu-id="07c5d-109">As a result, attempts to restore the computer do not affect the specified drive.</span></span>

<span data-ttu-id="07c5d-110">若要在任何驱动器上禁用系统还原，则必须首先或并行在系统驱动器上禁用系统还原。</span><span class="sxs-lookup"><span data-stu-id="07c5d-110">To disable System Restore on any drive, it must be disabled on the system drive, either first or concurrently.</span></span>

<span data-ttu-id="07c5d-111">若要重新启用系统还原，请使用 Enable-ComputerRestore cmdlet。</span><span class="sxs-lookup"><span data-stu-id="07c5d-111">To re-enable System Restore, use the Enable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="07c5d-112">若要查找每个驱动器的系统还原状态，请使用 Rstrui.exe。</span><span class="sxs-lookup"><span data-stu-id="07c5d-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="07c5d-113">系统还原点和 ComputerRestore cmdlet 仅在客户端操作系统（例如 Windows 7、Windows Vista 和 Windows XP）上受支持。</span><span class="sxs-lookup"><span data-stu-id="07c5d-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="07c5d-114">示例</span><span class="sxs-lookup"><span data-stu-id="07c5d-114">EXAMPLES</span></span>

### <span data-ttu-id="07c5d-115">示例1：在指定驱动器上禁用系统还原</span><span class="sxs-lookup"><span data-stu-id="07c5d-115">Example 1: Disable System Restore on the specified drive</span></span>

```
PS C:\> Disable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="07c5d-116">此命令将在 C: 驱动器上禁用系统还原。</span><span class="sxs-lookup"><span data-stu-id="07c5d-116">This command disables System Restore on the C: drive.</span></span>

### <span data-ttu-id="07c5d-117">示例2：在多个驱动器上禁用系统还原</span><span class="sxs-lookup"><span data-stu-id="07c5d-117">Example 2: Disable System Restore on multiple drives</span></span>

```
PS C:\> Disable-ComputerRestore "C:\", "D:\"
```

<span data-ttu-id="07c5d-118">此命令将在 C: 和 D: 驱动器上禁用系统还原。</span><span class="sxs-lookup"><span data-stu-id="07c5d-118">This command disables System Restore on the C: and D: drives.</span></span>
<span data-ttu-id="07c5d-119">该命令使用 *drive* 参数，但它省略驱动器参数名称。</span><span class="sxs-lookup"><span data-stu-id="07c5d-119">The command uses the *Drive* parameter, but it omits the Drive parameter name.</span></span>

## <span data-ttu-id="07c5d-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="07c5d-120">PARAMETERS</span></span>

### <span data-ttu-id="07c5d-121">-Drive</span><span class="sxs-lookup"><span data-stu-id="07c5d-121">-Drive</span></span>
<span data-ttu-id="07c5d-122">指定文件系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="07c5d-122">Specifies the file system drives.</span></span>
<span data-ttu-id="07c5d-123">输入一个或多个文件系统驱动器号，每个驱动器号后面跟一个冒号和一个反斜杠，并用引号引起来，例如 C：\或 D:\。</span><span class="sxs-lookup"><span data-stu-id="07c5d-123">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="07c5d-124">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="07c5d-124">This parameter is required.</span></span>

<span data-ttu-id="07c5d-125">无法使用此 cmdlet 在远程网络驱动器上禁用系统还原，即使该驱动器映射到本地计算机也是如此，并且无法在不符合系统还原条件的驱动器（如外部驱动器）上禁用系统还原。</span><span class="sxs-lookup"><span data-stu-id="07c5d-125">You cannot use this cmdlet to disable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot disable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="07c5d-126">若要在任何驱动器上禁用系统还原，则必须首先或并行在系统驱动器上禁用系统还原。</span><span class="sxs-lookup"><span data-stu-id="07c5d-126">To disable System Restore on any drive, System Restore must be disabled on the system drive, either before or concurrently.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="07c5d-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="07c5d-127">-Confirm</span></span>
<span data-ttu-id="07c5d-128">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="07c5d-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="07c5d-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="07c5d-129">-WhatIf</span></span>
<span data-ttu-id="07c5d-130">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="07c5d-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="07c5d-131">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="07c5d-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="07c5d-132">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="07c5d-132">CommonParameters</span></span>
<span data-ttu-id="07c5d-133">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="07c5d-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="07c5d-134">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="07c5d-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="07c5d-135">输入</span><span class="sxs-lookup"><span data-stu-id="07c5d-135">INPUTS</span></span>

### <span data-ttu-id="07c5d-136">无</span><span class="sxs-lookup"><span data-stu-id="07c5d-136">None</span></span>
<span data-ttu-id="07c5d-137">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="07c5d-137">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="07c5d-138">输出</span><span class="sxs-lookup"><span data-stu-id="07c5d-138">OUTPUTS</span></span>

### <span data-ttu-id="07c5d-139">无</span><span class="sxs-lookup"><span data-stu-id="07c5d-139">None</span></span>
<span data-ttu-id="07c5d-140">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="07c5d-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="07c5d-141">注释</span><span class="sxs-lookup"><span data-stu-id="07c5d-141">NOTES</span></span>

* <span data-ttu-id="07c5d-142">若要在 Windows Vista 和更高版本的 Windows 上运行此 cmdlet，请通过 "以管理员身份运行" 选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="07c5d-142">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="07c5d-143">若要查找符合系统还原条件的文件系统驱动器，请在 "控制面板" 的 "系统" 中查看 "系统保护" 选项卡。若要在 Windows PowerShell 中打开此选项卡，请键入 `SystemPropertiesProtection` 。</span><span class="sxs-lookup"><span data-stu-id="07c5d-143">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="07c5d-144">此 cmdlet 使用 (WMI) **SystemRestore** 类的 Windows Management Instrumentation。</span><span class="sxs-lookup"><span data-stu-id="07c5d-144">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="07c5d-145">相关链接</span><span class="sxs-lookup"><span data-stu-id="07c5d-145">RELATED LINKS</span></span>

[<span data-ttu-id="07c5d-146">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="07c5d-146">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="07c5d-147">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="07c5d-147">Enable-ComputerRestore</span></span>](Enable-ComputerRestore.md)

[<span data-ttu-id="07c5d-148">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="07c5d-148">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="07c5d-149">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="07c5d-149">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="07c5d-150">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="07c5d-150">Restore-Computer</span></span>](Restore-Computer.md)
