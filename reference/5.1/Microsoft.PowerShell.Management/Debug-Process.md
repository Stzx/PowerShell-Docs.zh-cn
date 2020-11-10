---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/debug-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Process
ms.openlocfilehash: 98bd72901339d040748fc0d99b14bc1404ea1465
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388308"
---
# <span data-ttu-id="62964-103">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="62964-103">Debug-Process</span></span>

## <span data-ttu-id="62964-104">摘要</span><span class="sxs-lookup"><span data-stu-id="62964-104">SYNOPSIS</span></span>
<span data-ttu-id="62964-105">调试在本地计算机上运行的一个或多个进程。</span><span class="sxs-lookup"><span data-stu-id="62964-105">Debugs one or more processes running on the local computer.</span></span>

## <span data-ttu-id="62964-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="62964-106">SYNTAX</span></span>

### <span data-ttu-id="62964-107">Name（默认值）</span><span class="sxs-lookup"><span data-stu-id="62964-107">Name (Default)</span></span>

```
Debug-Process [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="62964-108">ID</span><span class="sxs-lookup"><span data-stu-id="62964-108">Id</span></span>

```
Debug-Process [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="62964-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="62964-109">InputObject</span></span>

```
Debug-Process -InputObject <Process[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="62964-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="62964-110">DESCRIPTION</span></span>

<span data-ttu-id="62964-111">`Debug-Process`Cmdlet 可将调试程序附加到本地计算机上的一个或多个正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="62964-111">The `Debug-Process` cmdlet attaches a debugger to one or more running processes on a local computer.</span></span>
<span data-ttu-id="62964-112">可以通过进程名称或进程 ID (PID) 来指定进程，也可以将进程对象通过管道传送给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62964-112">You can specify the processes by their process name or process ID (PID), or you can pipe process objects to this cmdlet.</span></span>

<span data-ttu-id="62964-113">此 cmdlet 将附加当前为该进程注册的调试程序。</span><span class="sxs-lookup"><span data-stu-id="62964-113">This cmdlet attaches the debugger that is currently registered for the process.</span></span> <span data-ttu-id="62964-114">使用此 cmdlet 之前，请先验证调试程序是否已下载并正确配置。</span><span class="sxs-lookup"><span data-stu-id="62964-114">Before using this cmdlet, verify that a debugger is downloaded and correctly configured.</span></span>

## <span data-ttu-id="62964-115">示例</span><span class="sxs-lookup"><span data-stu-id="62964-115">EXAMPLES</span></span>

### <span data-ttu-id="62964-116">示例 1：将调试程序附加到计算机上的进程</span><span class="sxs-lookup"><span data-stu-id="62964-116">Example 1: Attach a debugger to a process on the computer</span></span>

```
PS C:\> Debug-Process -Name "Windows Powershell"
```

<span data-ttu-id="62964-117">此命令将调试程序附加到计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-117">This command attaches a debugger to the PowerShell process on the computer.</span></span>

### <span data-ttu-id="62964-118">示例 2：将调试程序附加到以指定字符串开头的所有进程</span><span class="sxs-lookup"><span data-stu-id="62964-118">Example 2: Attach a debugger to all processes that begin with the specified string</span></span>

```
PS C:\> Debug-Process -Name "SQL*"
```

<span data-ttu-id="62964-119">此命令将调试程序附加到名称以 SQL 开头的所有进程。</span><span class="sxs-lookup"><span data-stu-id="62964-119">This command attaches a debugger to all processes that have names that begin with SQL.</span></span>

### <span data-ttu-id="62964-120">示例 3：将调试程序附加到多个进程</span><span class="sxs-lookup"><span data-stu-id="62964-120">Example 3: Attach a debugger to multiple processes</span></span>

```
PS C:\> Debug-Process "Winlogon", "Explorer", "Outlook"
```

<span data-ttu-id="62964-121">此命令将调试程序附加到 Winlogon、Explorer 和 Outlook 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-121">This command attaches a debugger to the Winlogon, Explorer, and Outlook processes.</span></span>

### <span data-ttu-id="62964-122">示例 4：将调试程序附加到多个进程 ID</span><span class="sxs-lookup"><span data-stu-id="62964-122">Example 4: Attach a debugger to multiple process IDs</span></span>

```
PS C:\> Debug-Process -Id 1132, 2028
```

<span data-ttu-id="62964-123">此命令将调试程序附加到进程 ID 为 1132 和 2028 的进程。</span><span class="sxs-lookup"><span data-stu-id="62964-123">This command attaches a debugger to the processes that have process IDs 1132 and 2028.</span></span>

### <span data-ttu-id="62964-124">示例 5：使用 Get-Process 获取进程，然后将调试程序附加到它</span><span class="sxs-lookup"><span data-stu-id="62964-124">Example 5: Use Get-Process to get a process then attach a debugger to it</span></span>

```
PS C:\> Get-Process "Windows PowerShell" | Debug-Process
```

<span data-ttu-id="62964-125">此命令将调试程序附加到计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-125">This command attaches a debugger to the PowerShell processes on the computer.</span></span> <span data-ttu-id="62964-126">它使用 `Get-Process` cmdlet 获取计算机上的 PowerShell 进程，并使用管道操作员 (`|`) 将进程发送到 `Debug-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62964-126">It uses the `Get-Process` cmdlet to get the PowerShell processes on the computer, and it uses a pipeline operator (`|`) to send the processes to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="62964-127">若要指定特定的 PowerShell 进程，请使用的 ID 参数 `Get-Process` 。</span><span class="sxs-lookup"><span data-stu-id="62964-127">To specify a particular PowerShell process, use the ID parameter of `Get-Process`.</span></span>

### <span data-ttu-id="62964-128">示例 6：将调试程序附加到本地计算机上的当前进程</span><span class="sxs-lookup"><span data-stu-id="62964-128">Example 6: Attach a debugger to a current process on the local computer</span></span>

```
PS C:\> $PID | Debug-Process
```

<span data-ttu-id="62964-129">此命令将调试程序附加到计算机上的当前 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-129">This command attaches a debugger to the current PowerShell processes on the computer.</span></span>

<span data-ttu-id="62964-130">该命令使用 `$PID` 自动变量，其中包含当前 PowerShell 进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="62964-130">The command uses the `$PID` automatic variable, which contains the process ID of the current PowerShell process.</span></span> <span data-ttu-id="62964-131">然后，它使用管道运算符 (`|`) 将进程 ID 发送到 `Debug-Process` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62964-131">Then, it uses a pipeline operator (`|`) to send the process ID to the `Debug-Process` cmdlet.</span></span>

<span data-ttu-id="62964-132">有关自动变量的详细信息 `$PID` ，请参阅 about_Automatic_Variables。</span><span class="sxs-lookup"><span data-stu-id="62964-132">For more information about the `$PID` automatic variable, see about_Automatic_Variables.</span></span>

### <span data-ttu-id="62964-133">示例 7：将调试程序附加到多个计算机上的指定进程</span><span class="sxs-lookup"><span data-stu-id="62964-133">Example 7: Attach a debugger to the specified process on multiple computers</span></span>

```
PS C:\> Get-Process -ComputerName "Server01", "Server02" -Name "MyApp" | Debug-Process
```

<span data-ttu-id="62964-134">此命令将调试程序附加到 Server01 和 Server02 计算机上的 MyApp 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-134">This command attaches a debugger to the MyApp processes on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="62964-135">该命令使用 `Get-Process` cmdlet 来获取 Server01 和 Server02 计算机上的 MyApp 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-135">The command uses the `Get-Process` cmdlet to get the MyApp processes on the Server01 and Server02 computers.</span></span> <span data-ttu-id="62964-136">它使用管道运算符将进程发送到 `Debug-Process` cmdlet，后者会附加调试器。</span><span class="sxs-lookup"><span data-stu-id="62964-136">It uses a pipeline operator to send the processes to the `Debug-Process` cmdlet, which attaches the debuggers.</span></span>

### <span data-ttu-id="62964-137">示例 8：将调试程序附加到使用 InputObject 参数的进程</span><span class="sxs-lookup"><span data-stu-id="62964-137">Example 8: Attach a debugger to a process that uses the InputObject parameter</span></span>

```
PS C:\> $P = Get-Process "Windows PowerShell"
PS C:\> Debug-Process -InputObject $P
```

<span data-ttu-id="62964-138">此命令将调试程序附加到本地计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-138">This command attaches a debugger to the PowerShell processes on the local computer.</span></span>

<span data-ttu-id="62964-139">第一个命令使用 `Get-Process` cmdlet 来获取计算机上的 PowerShell 进程。</span><span class="sxs-lookup"><span data-stu-id="62964-139">The first command uses the `Get-Process` cmdlet to get the PowerShell processes on the computer.</span></span> <span data-ttu-id="62964-140">它将生成的进程对象保存在变量中 `$P` 。</span><span class="sxs-lookup"><span data-stu-id="62964-140">It saves the resulting process object in the variable named `$P`.</span></span>

<span data-ttu-id="62964-141">第二个命令使用 cmdlet 的 **InputObject** 参数 `Debug-Process` 来提交变量中的进程对象 `$P` 。</span><span class="sxs-lookup"><span data-stu-id="62964-141">The second command uses the **InputObject** parameter of the `Debug-Process` cmdlet to submit the process object in the `$P` variable.</span></span>

## <span data-ttu-id="62964-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="62964-142">PARAMETERS</span></span>

### <span data-ttu-id="62964-143">-Id</span><span class="sxs-lookup"><span data-stu-id="62964-143">-Id</span></span>

<span data-ttu-id="62964-144">指定要调试的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="62964-144">Specifies the process IDs of the processes to be debugged.</span></span> <span data-ttu-id="62964-145">Id 参数名为可选项。</span><span class="sxs-lookup"><span data-stu-id="62964-145">The **Id** parameter name is optional.</span></span>

<span data-ttu-id="62964-146">要查找进程的进程 ID，请键入 `Get-Process`。</span><span class="sxs-lookup"><span data-stu-id="62964-146">To find the process ID of a process, type `Get-Process`.</span></span>

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

### <span data-ttu-id="62964-147">-InputObject</span><span class="sxs-lookup"><span data-stu-id="62964-147">-InputObject</span></span>

<span data-ttu-id="62964-148">指定表示要调试的进程的进程对象。</span><span class="sxs-lookup"><span data-stu-id="62964-148">Specifies the process objects that represent processes to be debugged.</span></span> <span data-ttu-id="62964-149">输入包含进程对象的变量或获取进程对象的命令（如 `Get-Process` cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="62964-149">Enter a variable that contains the process objects or a command that gets the process objects, such as the `Get-Process` cmdlet.</span></span> <span data-ttu-id="62964-150">还可以将进程对象通过管道传送给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62964-150">You can also pipe process objects to this cmdlet.</span></span>

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

### <span data-ttu-id="62964-151">-Name</span><span class="sxs-lookup"><span data-stu-id="62964-151">-Name</span></span>

<span data-ttu-id="62964-152">指定要调试的进程的名称。</span><span class="sxs-lookup"><span data-stu-id="62964-152">Specifies the names of the processes to be debugged.</span></span> <span data-ttu-id="62964-153">如果存在多个同名进程，则此 cmdlet 会将调试程序附加到所有该名称的进程。</span><span class="sxs-lookup"><span data-stu-id="62964-153">If there is more than one process with the same name, this cmdlet attaches a debugger to all processes with that name.</span></span> <span data-ttu-id="62964-154">**Name** 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="62964-154">The **Name** parameter is optional.</span></span>

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

### <span data-ttu-id="62964-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="62964-155">-Confirm</span></span>

<span data-ttu-id="62964-156">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="62964-156">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="62964-157">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="62964-157">-WhatIf</span></span>

<span data-ttu-id="62964-158">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="62964-158">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="62964-159">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="62964-159">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="62964-160">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="62964-160">CommonParameters</span></span>

<span data-ttu-id="62964-161">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="62964-161">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="62964-162">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="62964-162">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="62964-163">输入</span><span class="sxs-lookup"><span data-stu-id="62964-163">INPUTS</span></span>

### <span data-ttu-id="62964-164">System.Int32、System.Diagnostics.Process、System.String</span><span class="sxs-lookup"><span data-stu-id="62964-164">System.Int32, System.Diagnostics.Process, System.String</span></span>

<span data-ttu-id="62964-165">可以通过管道将进程 ID (Int32)、进程对象 (System.Diagnostics.Process) 或进程名称 (String) 传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="62964-165">You can pipe a process ID (Int32), a process object (System.Diagnostics.Process), or a process name (String) to this cmdlet.</span></span>

## <span data-ttu-id="62964-166">输出</span><span class="sxs-lookup"><span data-stu-id="62964-166">OUTPUTS</span></span>

### <span data-ttu-id="62964-167">无</span><span class="sxs-lookup"><span data-stu-id="62964-167">None</span></span>

<span data-ttu-id="62964-168">此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="62964-168">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="62964-169">注释</span><span class="sxs-lookup"><span data-stu-id="62964-169">NOTES</span></span>

<span data-ttu-id="62964-170">此 cmdlet 使用 Windows Management Instrumentation (WMI) Win32_Process 类的 AttachDebugger 方法。</span><span class="sxs-lookup"><span data-stu-id="62964-170">This cmdlet uses the AttachDebugger method of the Windows Management Instrumentation (WMI) Win32_Process class.</span></span> <span data-ttu-id="62964-171">有关此方法的详细信息，请参阅 MSDN library 中的 [AttachDebugger 方法](https://go.microsoft.com/fwlink/?LinkId=143640) 。</span><span class="sxs-lookup"><span data-stu-id="62964-171">For more information about this method, see [AttachDebugger method](https://go.microsoft.com/fwlink/?LinkId=143640) in the MSDN library.</span></span>

## <span data-ttu-id="62964-172">相关链接</span><span class="sxs-lookup"><span data-stu-id="62964-172">RELATED LINKS</span></span>

[<span data-ttu-id="62964-173">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="62964-173">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="62964-174">Get-Process</span><span class="sxs-lookup"><span data-stu-id="62964-174">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="62964-175">Start-Process</span><span class="sxs-lookup"><span data-stu-id="62964-175">Start-Process</span></span>](Start-Process.md)

[<span data-ttu-id="62964-176">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="62964-176">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="62964-177">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="62964-177">Wait-Process</span></span>](Wait-Process.md)
