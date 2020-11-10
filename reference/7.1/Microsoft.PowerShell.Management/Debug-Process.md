---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: ea2f18017f6e65d2dd712f24acec4f3a50c9408d
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390484"
---
# <span data-ttu-id="fd6c5-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="fd6c5-103">Debug-Process</span></span>

## <span data-ttu-id="fd6c5-104">摘要</span><span class="sxs-lookup"><span data-stu-id="fd6c5-104">SYNOPSIS</span></span>
<span data-ttu-id="fd6c5-105">调试在本地计算机上运行的一个或多个进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="fd6c5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fd6c5-106">SYNTAX</span></span>

### <span data-ttu-id="fd6c5-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="fd6c5-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fd6c5-108">ID</span><span class="sxs-lookup"><span data-stu-id="fd6c5-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="fd6c5-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="fd6c5-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fd6c5-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="fd6c5-110">DESCRIPTION</span></span>

<span data-ttu-id="fd6c5-111">`Debug-Process`Cmdlet 可将调试程序附加到本地计算机上的一个或多个正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-111">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="fd6c5-112">可以通过进程名称或进程 ID (PID) 来指定进程，也可以将进程对象通过管道传送给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="fd6c5-113">此 cmdlet 将附加当前为该进程注册的调试程序。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="fd6c5-114">使用此 cmdlet 之前，请先验证调试程序是否已下载并正确配置。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="fd6c5-115">示例</span><span class="sxs-lookup"><span data-stu-id="fd6c5-115">EXAMPLES</span></span>

### <span data-ttu-id="fd6c5-116">示例 1：将调试程序附加到计算机上的进程</span><span class="sxs-lookup"><span data-stu-id="fd6c5-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="fd6c5-117">此命令将调试程序附加到计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="fd6c5-118">示例 2：将调试程序附加到以指定字符串开头的所有进程</span><span class="sxs-lookup"><span data-stu-id="fd6c5-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="fd6c5-119">此命令将调试程序附加到名称以 SQL 开头的所有进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="fd6c5-120">示例 3：将调试程序附加到多个进程</span><span class="sxs-lookup"><span data-stu-id="fd6c5-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="fd6c5-121">此命令将调试程序附加到 Winlogon、Explorer 和 Outlook 进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="fd6c5-122">示例 4：将调试程序附加到多个进程 ID</span><span class="sxs-lookup"><span data-stu-id="fd6c5-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="fd6c5-123">此命令将调试程序附加到进程 ID 为 1132 和 2028 的进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="fd6c5-124">示例 5：使用 Get-Process 获取进程，然后将调试程序附加到它</span><span class="sxs-lookup"><span data-stu-id="fd6c5-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="fd6c5-125">此命令将调试程序附加到计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="fd6c5-126">它使用 `Get-Process` cmdlet 获取计算机上的 PowerShell 进程，并使用管道操作员 (`|`) 将进程发送到 `Debug-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-126">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="fd6c5-127">若要指定特定的 PowerShell 进程，请使用的 ID 参数 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-127">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="fd6c5-128">示例 6：将调试程序附加到本地计算机上的当前进程</span><span class="sxs-lookup"><span data-stu-id="fd6c5-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="fd6c5-129">此命令将调试程序附加到计算机上的当前 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="fd6c5-130">该命令使用 `$PID` 自动变量，其中包含当前 PowerShell 进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-130">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="fd6c5-131">然后，它使用管道运算符 (`|`) 将进程 ID 发送到 `Debug-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-131">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="fd6c5-132">有关自动变量的详细信息 `$PID` ，请参阅 about_Automatic_Variables。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-132">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="fd6c5-133">示例7：将调试程序附加到使用 InputObject 参数的进程</span><span class="sxs-lookup"><span data-stu-id="fd6c5-133">Example 7: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="fd6c5-134">此命令将调试程序附加到本地计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-134">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="fd6c5-135">第一个命令使用 `Get-Process` cmdlet 来获取计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-135">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="fd6c5-136">它将生成的进程对象保存在变量中 `$P` 。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-136">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="fd6c5-137">第二个命令使用 cmdlet 的 **InputObject** 参数 `Debug-Process` 来提交变量中的进程对象 `$P` 。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-137">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="fd6c5-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fd6c5-138">PARAMETERS</span></span>

### <span data-ttu-id="fd6c5-139">-Id</span><span class="sxs-lookup"><span data-stu-id="fd6c5-139">-Id</span></span>

<span data-ttu-id="fd6c5-140">指定要调试的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-140">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="fd6c5-141">Id 参数名为可选项。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-141">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="fd6c5-142">要查找进程的进程 ID，请键入 `Get-Process`。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-142">To find the process ID of a process, type `Get-Process`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases: PID, ProcessId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6c5-143">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fd6c5-143">-InputObject</span></span>

<span data-ttu-id="fd6c5-144">指定表示要调试的进程的进程对象。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-144">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="fd6c5-145">输入包含进程对象的变量或获取进程对象的命令（如 `Get-Process` cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-145">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="fd6c5-146">还可以将进程对象通过管道传送给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-146">You can also pipe process objects to this cmdlet.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6c5-147">-Name</span><span class="sxs-lookup"><span data-stu-id="fd6c5-147">-Name</span></span>

<span data-ttu-id="fd6c5-148">指定要调试的进程的名称。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-148">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="fd6c5-149">如果存在多个同名进程，则此 cmdlet 会将调试程序附加到所有该名称的进程。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-149">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="fd6c5-150">**Name** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-150">The **Name** parameter is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases: ProcessName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fd6c5-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fd6c5-151">-Confirm</span></span>

<span data-ttu-id="fd6c5-152">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fd6c5-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fd6c5-153">-WhatIf</span></span>

<span data-ttu-id="fd6c5-154">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-154">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="fd6c5-155">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fd6c5-156">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="fd6c5-156">CommonParameters</span></span>

<span data-ttu-id="fd6c5-157">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fd6c5-158">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fd6c5-159">输入</span><span class="sxs-lookup"><span data-stu-id="fd6c5-159">INPUTS</span></span>

### <span data-ttu-id="fd6c5-160">System.Int32、System.Diagnostics.Process、System.String</span><span class="sxs-lookup"><span data-stu-id="fd6c5-160">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="fd6c5-161">可以通过管道将进程 ID (Int32)、进程对象 (System.Diagnostics.Process) 或进程名称 (String) 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-161">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="fd6c5-162">输出</span><span class="sxs-lookup"><span data-stu-id="fd6c5-162">OUTPUTS</span></span>

### <span data-ttu-id="fd6c5-163">无</span><span class="sxs-lookup"><span data-stu-id="fd6c5-163">None</span></span>

<span data-ttu-id="fd6c5-164">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-164">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fd6c5-165">注释</span><span class="sxs-lookup"><span data-stu-id="fd6c5-165">NOTES</span></span>

<span data-ttu-id="fd6c5-166">此 cmdlet 使用 Windows Management Instrumentation (WMI) Win32_Process 类的 AttachDebugger 方法。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-166">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="fd6c5-167">有关此方法的详细信息，请参阅 MSDN library 中的 [AttachDebugger 方法](https://go.microsoft.com/fwlink/?LinkId=143640) 。</span><span class="sxs-lookup"><span data-stu-id="fd6c5-167">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="fd6c5-168">相关链接</span><span class="sxs-lookup"><span data-stu-id="fd6c5-168">RELATED LINKS</span></span>

[<span data-ttu-id="fd6c5-169">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="fd6c5-169">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="fd6c5-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="fd6c5-170">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="fd6c5-171">Start-Process</span><span class="sxs-lookup"><span data-stu-id="fd6c5-171">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="fd6c5-172">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="fd6c5-172">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="fd6c5-173">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="fd6c5-173">Wait-Process</span></span>](Wait-Process.md)
