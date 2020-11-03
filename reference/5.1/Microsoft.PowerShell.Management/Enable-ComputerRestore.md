---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/enable-computerrestore?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-ComputerRestore
ms.openlocfilehash: f9616a7f9af4dd2fa45e150bb64eef65427b4947
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198303"
---
# <span data-ttu-id="3a090-103">Enable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="3a090-103">Enable-ComputerRestore</span></span>

## <span data-ttu-id="3a090-104">摘要</span><span class="sxs-lookup"><span data-stu-id="3a090-104">SYNOPSIS</span></span>
<span data-ttu-id="3a090-105">在指定的文件系统驱动器上启用系统还原功能。</span><span class="sxs-lookup"><span data-stu-id="3a090-105">Enables the System Restore feature on the specified file system drive.</span></span>

## <span data-ttu-id="3a090-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3a090-106">SYNTAX</span></span>

```
Enable-ComputerRestore [-Drive] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3a090-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3a090-107">DESCRIPTION</span></span>
<span data-ttu-id="3a090-108">**Disable-computerrestore** cmdlet 将在一个或多个文件系统驱动器上启用系统还原功能。</span><span class="sxs-lookup"><span data-stu-id="3a090-108">The **Enable-ComputerRestore** cmdlet turns on the System Restore feature on one or more file system drives.</span></span>
<span data-ttu-id="3a090-109">因此，可以使用工具（如 Restore-Computer cmdlet）将计算机还原到先前的状态。</span><span class="sxs-lookup"><span data-stu-id="3a090-109">As a result, you can use tools, such as the Restore-Computer cmdlet, to restore the computer to a previous state.</span></span>

<span data-ttu-id="3a090-110">默认情况下，系统还原在符合条件的所有驱动器上都处于启用状态，不过你可以禁用系统还原，例如使用 Disable-ComputerRestore cmdlet 来禁用。</span><span class="sxs-lookup"><span data-stu-id="3a090-110">By default, System Restore is enabled on all eligible drives, but you can disable it, such as by using the Disable-ComputerRestore cmdlet.</span></span>
<span data-ttu-id="3a090-111">若要在任何驱动器上启用（或重新启用）系统还原，则必须首先或同时在系统驱动器上启用系统还原。</span><span class="sxs-lookup"><span data-stu-id="3a090-111">To enable (or re-enable) System Restore on any drive, it must be enabled on the system drive, either first or concurrently.</span></span>
<span data-ttu-id="3a090-112">若要查找每个驱动器的系统还原状态，请使用 Rstrui.exe。</span><span class="sxs-lookup"><span data-stu-id="3a090-112">To find the state of System Restore for each drive, use Rstrui.exe.</span></span>

<span data-ttu-id="3a090-113">系统还原点和 ComputerRestore cmdlet 仅在客户端操作系统（例如 Windows 7、Windows Vista 和 Windows XP）上受支持。</span><span class="sxs-lookup"><span data-stu-id="3a090-113">System restore points and the ComputerRestore cmdlets are supported only on client operating systems, such as Windows 7, Windows Vista, and Windows XP.</span></span>

## <span data-ttu-id="3a090-114">示例</span><span class="sxs-lookup"><span data-stu-id="3a090-114">EXAMPLES</span></span>

### <span data-ttu-id="3a090-115">示例1：在指定的驱动器上启用系统还原</span><span class="sxs-lookup"><span data-stu-id="3a090-115">Example 1: Enable System Restore on the specified drive</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\"
```

<span data-ttu-id="3a090-116">此命令在本地计算机的 C: 驱动器上启用系统还原。</span><span class="sxs-lookup"><span data-stu-id="3a090-116">This command enables System Restore on the C: drive of the local computer.</span></span>

### <span data-ttu-id="3a090-117">示例2：在多个驱动器上启用系统还原</span><span class="sxs-lookup"><span data-stu-id="3a090-117">Example 2: Enable System Restore on multiple drives</span></span>

```
PS C:\> Enable-ComputerRestore -Drive "C:\", "D:\"
```

<span data-ttu-id="3a090-118">此命令在本地计算机的 C: 和 D: 驱动器上启用系统还原。</span><span class="sxs-lookup"><span data-stu-id="3a090-118">This command enables System Restore on the C: and D: drives of the local computer.</span></span>

## <span data-ttu-id="3a090-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3a090-119">PARAMETERS</span></span>

### <span data-ttu-id="3a090-120">-Drive</span><span class="sxs-lookup"><span data-stu-id="3a090-120">-Drive</span></span>
<span data-ttu-id="3a090-121">指定文件系统驱动器。</span><span class="sxs-lookup"><span data-stu-id="3a090-121">Specifies the file system drives.</span></span>
<span data-ttu-id="3a090-122">输入一个或多个文件系统驱动器号，每个驱动器号后面跟一个冒号和一个反斜杠，并用引号引起来，例如 C：\或 D:\。</span><span class="sxs-lookup"><span data-stu-id="3a090-122">Enter one or more file system drive letters, each followed by a colon and a backslash and enclosed in quotation marks, such as C:\ or D:\.</span></span>
<span data-ttu-id="3a090-123">此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="3a090-123">This parameter is required.</span></span>

<span data-ttu-id="3a090-124">无法使用此 cmdlet 在远程网络驱动器上启用系统还原，即使该驱动器映射到本地计算机也是如此，并且无法在不符合系统还原条件的驱动器（如外部驱动器）上启用系统还原。</span><span class="sxs-lookup"><span data-stu-id="3a090-124">You cannot use this cmdlet to enable System Restore on a remote network drive, even if the drive is mapped to the local computer, and you cannot enable System Restore on drives that are not eligible for System Restore, such as external drives.</span></span>

<span data-ttu-id="3a090-125">若要在任何驱动器上启用系统还原，则必须首先或同时在系统驱动器上启用系统还原。</span><span class="sxs-lookup"><span data-stu-id="3a090-125">To enable System Restore on any drive, System Restore must be enabled on the system drive, either before or concurrently.</span></span>

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

### <span data-ttu-id="3a090-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3a090-126">-Confirm</span></span>
<span data-ttu-id="3a090-127">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="3a090-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3a090-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3a090-128">-WhatIf</span></span>
<span data-ttu-id="3a090-129">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="3a090-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="3a090-130">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="3a090-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3a090-131">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3a090-131">CommonParameters</span></span>
<span data-ttu-id="3a090-132">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="3a090-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3a090-133">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="3a090-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3a090-134">输入</span><span class="sxs-lookup"><span data-stu-id="3a090-134">INPUTS</span></span>

### <span data-ttu-id="3a090-135">无</span><span class="sxs-lookup"><span data-stu-id="3a090-135">None</span></span>
<span data-ttu-id="3a090-136">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a090-136">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="3a090-137">输出</span><span class="sxs-lookup"><span data-stu-id="3a090-137">OUTPUTS</span></span>

### <span data-ttu-id="3a090-138">无</span><span class="sxs-lookup"><span data-stu-id="3a090-138">None</span></span>
<span data-ttu-id="3a090-139">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="3a090-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3a090-140">注释</span><span class="sxs-lookup"><span data-stu-id="3a090-140">NOTES</span></span>

* <span data-ttu-id="3a090-141">若要在 Windows Vista 和更高版本的 Windows 上运行此 cmdlet，请通过 "以管理员身份运行" 选项打开 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3a090-141">To run this cmdlet on Windows Vista and later versions of Windows, open Windows PowerShell with the Run as administrator option.</span></span>

  <span data-ttu-id="3a090-142">若要查找符合系统还原条件的文件系统驱动器，请在 "控制面板" 的 "系统" 中查看 "系统保护" 选项卡。若要在 Windows PowerShell 中打开此选项卡，请键入 `SystemPropertiesProtection` 。</span><span class="sxs-lookup"><span data-stu-id="3a090-142">To find the file system drives that are eligible for system restore, in System in Control Panel, see the System Protection tab. To open this tab in Windows PowerShell, type `SystemPropertiesProtection`.</span></span>

  <span data-ttu-id="3a090-143">此 cmdlet 使用 (WMI) **SystemRestore** 类的 Windows Management Instrumentation。</span><span class="sxs-lookup"><span data-stu-id="3a090-143">This cmdlet uses the Windows Management Instrumentation (WMI) **SystemRestore** class.</span></span>

*

## <span data-ttu-id="3a090-144">相关链接</span><span class="sxs-lookup"><span data-stu-id="3a090-144">RELATED LINKS</span></span>

[<span data-ttu-id="3a090-145">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="3a090-145">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="3a090-146">Disable-ComputerRestore</span><span class="sxs-lookup"><span data-stu-id="3a090-146">Disable-ComputerRestore</span></span>](Disable-ComputerRestore.md)

[<span data-ttu-id="3a090-147">Get-ComputerRestorePoint</span><span class="sxs-lookup"><span data-stu-id="3a090-147">Get-ComputerRestorePoint</span></span>](Get-ComputerRestorePoint.md)

[<span data-ttu-id="3a090-148">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="3a090-148">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="3a090-149">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="3a090-149">Restore-Computer</span></span>](Restore-Computer.md)
