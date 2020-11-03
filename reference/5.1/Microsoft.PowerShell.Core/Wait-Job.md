---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/wait-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Job
ms.openlocfilehash: acf01415c9722b6da95e70a8db1b558c3e14662b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197608"
---
# Wait-Job

## 摘要
禁止显示命令提示符，直到在会话中运行的一个或全部 Windows PowerShell 后台作业完成。

## SYNTAX

### SessionIdParameterSet（默认值）

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Id] <Int32[]> [<CommonParameters>]
```

### JobParameterSet

```
Wait-Job [-Job] <Job[]> [-Any] [-Timeout <Int32>] [-Force] [<CommonParameters>]
```

### NameParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Name] <String[]> [<CommonParameters>]
```

### InstanceIdParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### StateParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-State] <JobState> [<CommonParameters>]
```

### FilterParameterSet

```
Wait-Job [-Any] [-Timeout <Int32>] [-Force] [-Filter] <Hashtable> [<CommonParameters>]
```

## DESCRIPTION
**Wait** Cmdlet 等待 Windows PowerShell 后台作业完成，然后显示命令提示符。
可以等待某一个后台作业完成或所有后台作业完成，并可为作业设置最长等待时间。

当作业中的命令完成时， **Wait-Job** 将显示命令提示符并返回作业对象，以便你可以通过管道将该对象传递给另一个命令。

可以使用 **Wait-Job** cmdlet 等待后台作业，例如使用 Start-Job cmdlet 或 Invoke-Command cmdlet 的 *AsJob* 参数启动的后台作业。
有关 Windows PowerShell 后台作业的详细信息，请参阅 about_Jobs。

从 Windows PowerShell 3.0 开始， **等待** cmdlet 还会等待自定义作业类型，例如工作流作业和计划作业的实例。
若要使 **等待作业** 等待特定类型的作业，请在运行 Get-Job cmdlet 之前将支持自定义作业类型的模块导入到会话中，方法是使用 Import-Module cmdlet，或者使用或在模块中获取 cmdlet。
有关特定的自定义作业类型的信息，请参阅自定义作业类型功能的文档。

## 示例

### 示例1：等待所有作业

```
PS C:\> Get-Job | Wait-Job
```

此命令等待在会话中运行的所有后台作业完成。

### 示例2：使用 Start-Job 等待远程计算机上启动的作业

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -Name Date1 -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -Command {Wait-Job -Name Date1}
PS C:\> $done.Count
3
```

此示例演示如何通过使用 **启动作业** cmdlet，将 **Wait** cmdlet 用于远程计算机上启动的作业。
**启动作业** 和 **等待作业** 命令都使用 **命令调用** cmdlet 提交到远程计算机。

此示例使用 **Wait** 来确定在三台不同计算机上作为后台作业运行的 Get-Date 命令是否完成。

第一个命令在三台远程计算机的每台计算机上创建一个 ( **PSSession** ) 的 Windows PowerShell 会话，并将它们存储在 $s 变量中。

第二个命令使用 **Invoke 命令** 在 $s 的三个会话中的每个会话中运行 **Start-Job** 。
所有作业都命名为 Date1。

第三个命令使用 **Invoke 命令** 来运行 **等待作业** 。
此命令等待每台计算机上的 Date1 作业完成。
它将生成的作业对象集合（数组）存储在 $done 变量中。

第四个命令使用 $done 变量中的作业对象数组的 **Count** 属性来确定完成的作业数。

### 示例3：确定第一次后台作业何时完成

```
PS C:\> $s = New-PSSession (Get-Content Machines.txt)
PS C:\> $c = 'Get-EventLog -LogName System | where {$_.EntryType -eq "error" --and $_.Source -eq "LSASRV"} | Out-File Errors.txt'
PS C:\> Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {$Using:c}
PS C:\> Invoke-Command -Session $s -ScriptBlock {Wait-Job -Any}
```

此示例使用 **Wait** 的 *Any* 参数来确定在当前会话中运行的多个后台作业中的第一个作业完成的时间。
它还演示了如何使用 **wait** cmdlet 等待远程作业完成。

第一个命令在 Machines.txt 文件中列出的每台计算机上创建 **pssession** ，并将 **pssession** 对象存储在 $s 变量中。
该命令使用 Get-Content cmdlet 获取文件的内容。
**Get Content** 命令括在括号中，以确保它在 New-PSSession 命令之前运行。

第二个命令在 $c 变量中存储 **Get-EventLog** 命令字符串，用引号引起来。

第三个命令使用 Invoke-Command cmdlet 在 $s 中的每个会话中运行 **启动作业** 。
**Start-Job** 命令启动一个运行 $c 变量中的 **Get-EventLog** 命令的后台作业。

该命令使用 **Using** 作用域修饰符以指示已在本地计算机上定义 $c 变量。
在 Windows PowerShell 3.0 中引入了 **Using** 作用域修饰符。
有关 **Using** 作用域修饰符的详细信息，请参阅 about_Remote_Variables (https://go.microsoft.com/fwlink/?LinkID=252653) 。

第四个命令使用 **Invoke** 命令在会话中运行 **等待作业** 命令。
它使用 *Any* 参数等待，直到远程计算机上的第一个作业完成。

### 示例4：设置远程计算机上的作业的等待时间

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $jobs = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-Date}}
PS C:\> $done = Invoke-Command -Session $s -ScriptBlock {Wait-Job -Timeout 30}
```

此示例演示如何使用 **Wait** 的 *Timeout* 参数设置在远程计算机上运行的作业的最长等待时间。

第一个命令在 (Server01、Server02 和 Server03) 的三台远程计算机上创建 **pssession** ，然后在 $s 变量中存储 **pssession** 对象。

第二个命令使用 **Invoke 命令** 在 $s 中的每个 **PSSession** 对象中运行 **Start-Job** 。
它将生成的作业对象存储在 $jobs 的变量中。

第三个命令使用 **Invoke 命令** 在 $s 中的每个会话中运行 **等待作业** 。
**Wait** 命令确定所有命令是否在30秒内完成。
它使用值为30的 *Timeout* 参数来建立最长等待时间，然后将命令的结果存储在 $done 的变量中。

在此示例中，30 秒后，只有 Server02 计算机上的命令完成。
**Wait** 结束等待，显示命令提示符，并返回表示已完成作业的对象。

$done 变量包含一个表示在 Server02 上运行的作业的作业对象。

### 示例5：等待多个作业中的一个完成

```
PS C:\> Wait-Job -id 1,2,5 -Any
```

此命令通过 Id 标识三个作业，并等待其中任何一个作业完成。
当第一个作业完成时，将返回命令提示符。

### 示例6：等待一段时间，然后允许作业在后台继续

```
PS C:\> Wait-Job -Name "DailyLog" -Timeout 120
```

此命令120等待 DailyLog 作业 (两分钟) ，直到完成。
如果作业未在接下来的两分钟内完成，则命令提示符仍返回，并且作业继续在后台运行。

### 示例7：按名称等待作业

```
PS C:\> Wait-Job -Name "Job3"
```

此命令使用作业名称来标识要等待的作业。

### 示例8：等待本地计算机上的作业开始 Start-Job

```
PS C:\> $j = Start-Job -ScriptBlock {Get-ChildItem *.ps1| where {$_lastwritetime -gt ((Get-Date) - (New-TimeSpan -Days 7))}}
PS C:\> $j | Wait-Job
```

此示例演示如何通过使用 " **启动-作业** " 将 **Wait** cmdlet 用于本地计算机上启动的作业。

这些命令启动一个可获取在上一周添加或更新的 Windows PowerShell 脚本文件的作业。

第一个命令使用 **start-job** 在本地计算机上启动后台作业。
作业运行 Get-ChildItem 命令，该命令获取在上周添加或更新的文件扩展名为 ps1 的所有文件。

第三个命令使用 **wait** 等待等待作业完成。
作业完成后，该命令将显示作业对象，该对象包含有关作业的信息。

### 示例9：使用 Invoke-Command 等待远程计算机上启动的作业

```
PS C:\> $s = New-PSSession Server01, Server02, Server03
PS C:\> $j = Invoke-Command -Session $s -ScriptBlock {Get-Process} -AsJob
PS C:\> $j | Wait-Job
```

此示例演示如何通过使用 **命令调用-Command** 的 *AsJob* 参数，将 **等待作业** 与远程计算机上启动的作业一起使用。
使用 *AsJob* 时，将在本地计算机上创建作业，并自动将结果返回到本地计算机，即使作业运行在远程计算机上也是如此。

此示例使用 **Wait** 来确定是否完成了三台远程计算机上的会话中运行的 **进程** 内命令。

第一个命令在三台计算机上创建 **PSSession** 对象，并将它们存储在 $s 变量中。

第二个命令使用 **Invoke 命令** 在 $s 中的三个会话中的每个会话中运行 **Get 进程** 。
该命令使用 *AsJob* 参数将命令作为后台作业异步运行。
该命令返回一个作业对象，就像使用 **Start-job** 启动的作业一样，该作业对象存储在 $j 的变量中。

第三个命令使用管道运算符 (|) 将 $j 中的作业对象发送到 **Wait** cmdlet。
在这种情况下，不需要 **调用命令** 命令，因为作业驻留在本地计算机上。

### 示例10：等待 ID 为的作业

```
PS C:\> Get-Job

Id   Name     State      HasMoreData     Location             Command
--   ----     -----      -----------     --------             -------
1    Job1     Completed  True            localhost,Server01.. get-service
4    Job4     Completed  True            localhost            dir | where

PS C:\> Wait-Job -Id 1
```

此命令等待 ID 值为 1 的作业。

## PARAMETERS

### -Any
指示此 cmdlet 显示命令提示符，并在任何作业完成时返回作业对象。
默认情况下， **等待作业** 将等待，直到所有指定的作业都完成后才显示提示。

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

### -Filter
指定条件的哈希表。
此 cmdlet 将等待满足哈希表中所有条件的作业。
输入一个哈希表，其中的键为作业属性，其中的值为作业属性值。

此参数仅适用于自定义作业类型，例如工作流作业和计划作业。
它不适用于标准后台作业，如使用 **Start-Job** cmdlet 创建的作业。
有关支持此参数的信息，请参阅作业类型的帮助主题。

已在 Windows PowerShell 3.0 中引入了此参数。

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
指示此 cmdlet 继续等待处于 "挂起" 或 "已断开连接" 状态的作业。
默认情况下，当作业处于以下状态之一时， **等待作业** 返回或结束等待：

- 已完成
- 已失败
- 已停止
- Suspended
- 已断开连接

已在 Windows PowerShell 3.0 中引入了此参数。

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

### -Id
指定此 cmdlet 等待的作业的 Id 的数组。

ID 是一个整数，用于唯一标识当前会话中的作业。
它比实例 ID 更容易记住和键入，但它仅在当前会话中是唯一的。
你可以键入一个或多个 Id （以逗号分隔）。
若要查找作业的 ID，请键入 `Get-Job` 。

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId
指定此 cmdlet 等待的作业的实例 Id 的数组。
默认值为所有作业。

实例 ID 是一个 GUID，用于在计算机上唯一标识作业。
若要查找作业的实例 ID，请使用 **Get-Job** 。

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Job
指定此 cmdlet 要等待的作业。
输入一个包含作业对象的变量或可获取作业对象的命令。
你还可以使用管道运算符将作业对象发送到 **Wait** cmdlet。
默认情况下， **等待** 时间等待在当前会话中创建的所有作业。

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
指定此 cmdlet 等待的作业的友好名称。

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -State
指定作业状态。
此 cmdlet 仅等待处于指定状态的作业。
此参数的可接受值为：

- NotStarted
- 正在运行
- 已完成
- 已失败
- 已停止
- 已阻止
- Suspended
- 已断开连接
- 正在暂停
- 正在停止

有关作业状态的详细信息，请参阅 MSDN 库中的 [JobState 枚举](https://msdn.microsoft.com/library/system.management.automation.jobstate) 。

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timeout
指定每个后台作业的最长等待时间（以秒为单位）。
默认值为-1，指示该 cmdlet 将等待直到作业完成。
当你提交 **等待作业** 命令时，将开始计时，而不是 **启动作业** 命令。

如果超过此时间，则等待结束，并返回命令提示符，即使作业仍在运行也是如此。
此命令不会显示任何错误消息。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### System.Management.Automation.RemotingJob
可以通过管道将作业对象传递给此 cmdlet。

## 输出

### System.Management.Automation.PSRemotingJob
此 cmdlet 将返回表示已完成作业的作业对象。
如果由于超过 *Timeout* 参数的值而导致等待结束，则 **等待作业** 不返回任何对象。

## 注释

* 默认情况下，当作业处于以下状态之一时， **等待作业** 返回或结束等待：

- 已完成
- 已失败
- 已停止
- 已挂起
- 断开连接以继续等待挂起和断开 **连接的作业** ，请使用 *Force* 参数。

## 相关链接

[Get-Job](Get-Job.md)

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)
