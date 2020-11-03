---
description: 描述如何在远程计算机上运行后台作业。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_jobs?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Jobs
ms.openlocfilehash: ad0400c4b4c25c9b0c7133bd916af5056dab1430
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199747"
---
# <a name="about-remote-jobs"></a>关于远程作业

## <a name="short-description"></a>简短说明
描述如何在远程计算机上运行后台作业。

## <a name="detailed-description"></a>详细说明

后台作业是异步运行的命令，不与当前会话交互。 命令提示符会立即返回，你可以在运行作业时继续使用会话。

默认情况下，后台作业在本地计算机上运行。 但是，您可以使用几个不同的过程在远程计算机上运行后台作业。

本主题说明如何在远程计算机上运行后台作业。 有关如何在本地计算机上运行后台作业的信息，请参阅 [about_Jobs](about_Jobs.md)。 有关后台作业的详细信息，请参阅 [about_Job_Details](about_Job_Details.md)。

## <a name="remote-background-jobs"></a>远程后台作业

您可以使用三种不同的方法在远程计算机上运行后台作业。

- 启动与远程计算机的交互式会话，并在交互式会话中启动作业。 尽管所有操作都是在远程计算机上执行的，但过程与运行本地作业相同。

- 在将其结果返回到本地计算机的远程计算机上运行后台作业。 如果要收集后台作业的结果并在本地计算机上的中央位置维护这些作业的结果，请使用此方法。

- 在远程计算机上运行后台作业，以在远程计算机上维护其结果。 在源计算机上更安全地维护作业数据时使用此方法。

### <a name="start-a-background-job-in-an-interactive-session"></a>在交互式会话中启动后台作业

您可以启动与远程计算机的交互式会话，然后在交互式会话过程中启动后台作业。 有关交互式会话的详细信息，请参阅 about_Remote，并参阅 Enter-PSSession。

在交互式会话中启动后台作业的过程与在本地计算机上启动后台作业的过程几乎相同。 但是，所有操作都在远程计算机上执行，而不是在本地计算机上进行。

#### <a name="step-1-enter-pssession"></a>步骤1：输入-PSSESSION

使用 Enter-PSSession cmdlet 来启动与远程计算机的交互式会话。 可以使用 Enter-PSSession 的 ComputerName 参数为交互式会话建立临时连接。 或者，可以使用 Session 参数 (PSSession) 在 PowerShell 会话中运行交互式会话。

以下命令在 Server01 计算机上启动交互式会话。

```powershell
C:\PS> Enter-PSSession -computername Server01
```

命令提示符更改为显示你现在已连接到 Server01 计算机。

```
Server01\C:>
```

#### <a name="step-2-start-job"></a>步骤2：启动-作业

若要在会话中启动后台作业，请使用 Start-Job cmdlet。

以下命令运行一个后台作业，该作业将获取 Server01 计算机上的 Windows PowerShell 事件日志中的事件。 Start-Job cmdlet 返回一个表示作业的对象。

此命令将作业对象保存在 \$ job 变量中。

```powershell
Server01\C:> $job = start-job -scriptblock {
  get-eventlog "Windows PowerShell"
}
```

作业运行时，可以使用交互式会话来运行其他命令，包括其他后台作业。 但是，必须在作业完成之前使交互式会话保持打开状态。 如果结束该会话，则该作业将中断，结果将丢失。

#### <a name="step-3-get-job"></a>步骤3：获取工作

若要查看作业是否已完成，请显示作业变量的值 \$ ，或使用 Get-Job cmdlet 获取作业。 以下命令使用 Get-Job cmdlet 显示作业。

```powershell
Server01\C:> get-job $job

SessionId  Name  State      HasMoreData  Location   Command
---------  ----  -----      -----------  --------   -------
1          Job1  Complete   True         localhost  get-eventlog "Windows...
```

Get-Job 输出显示作业正在 "localhost" 计算机上运行，因为该作业已在同一台计算机上启动并且正在运行 (在这种情况下，Server01) 。

#### <a name="step-4-receive-job"></a>步骤4：接收作业

若要获取作业结果，请使用 Receive-Job cmdlet。 可以在交互式会话中显示结果，也可以将结果保存到远程计算机上的文件中。 下面的命令获取 $job 变量中的作业的结果。 该命令使用重定向运算符 ( # A0) 将作业的结果保存到 Server01 计算机上的 PsLog.txt 文件中。

```powershell
Server01\C:> receive-job $job > c:\logs\PsLog.txt
```

#### <a name="step-5-exit-pssession"></a>步骤5：退出-PSSESSION

若要结束交互式会话，请使用 Exit-PSSession cmdlet。 命令提示符将更改为显示您返回到本地计算机上的原始会话中。

```powershell
Server01\C:> Exit-PSSession
C:\PS>
```

#### <a name="step-6-invoke-command-get-content"></a>步骤6：调用命令：获取内容

若要随时查看 Server01 计算机上的 PsLog.txt 文件的内容，请启动另一交互式会话或运行远程命令。 如果要使用多个命令来调查和管理 PsLog.txt 文件中的数据，这种类型的命令最好在 PSSession (持久性连接) 中运行。 有关 Pssession 的详细信息，请参阅 about_PSSessions。

以下命令使用 New-PSSession cmdlet 来创建连接到 Server01 计算机的 PSSession，并使用 Invoke-Command cmdlet 在 PSSession 中运行 Get-Content 命令以查看文件的内容。

```powershell
$s = new-pssession -computername Server01
invoke-command -session $s -scriptblock {
  get-content c:\logs\pslog.txt}
```

### <a name="start-a-remote-job-that-returns-the-results-to-the-local-computer-asjob"></a>启动将结果返回到本地计算机 ASJOB 的远程作业 \(\)

若要在将命令结果返回到本地计算机的远程计算机上启动后台作业，请使用 cmdlet 的 AsJob 参数，如 Invoke-Command cmdlet。

使用 AsJob 参数时，实际上会在本地计算机上创建作业对象，即使该作业在远程计算机上运行也是如此。 完成作业后，结果将返回到本地计算机。

你可以使用包含 job 名词的 cmdlet (作业 cmdlet) 管理任何 cmdlet 创建的任何作业。 许多具有 AsJob 参数的 cmdlet 不使用 PowerShell 远程处理，因此您甚至可以在未配置为进行远程处理并且不满足远程处理要求的计算机上使用它们。

#### <a name="step-1-invoke-command--asjob"></a>步骤1：调用命令-ASJOB

以下命令使用 Invoke-Command 的 AsJob 参数在 Server01 计算机上启动后台作业。 该作业运行可获取系统日志中的事件的 Get-Eventlog 命令。 可以使用 JobName 参数为作业指定显示名称。

```powershell
invoke-command -computername Server01 -scriptblock {
  get-eventlog system} -asjob
```

命令的结果类似于以下示例输出。

```Output
SessionId   Name   State    HasMoreData   Location   Command
---------   ----   -----    -----------   --------   -------
1           Job1   Running  True          Server01   get-eventlog system
```

使用 AsJob 参数时，Invoke-Command 返回 Start-Job 返回的相同类型的作业对象。 可以将作业对象保存在变量中，也可以使用 Get-Job 命令来获取作业。

请注意，Location 属性的值显示作业在 Server01 计算机上运行。

#### <a name="step-2-get-job"></a>步骤2：获取工作

若要管理使用 Invoke-Command cmdlet 的 AsJob 参数启动的作业，请使用作业 cmdlet。 由于表示远程作业的作业对象位于本地计算机上，因此无需运行远程命令来管理该作业。

若要确定作业是否已完成，请使用 Get-Job 命令。 以下命令将获取在当前会话中启动的所有作业。

```powershell
get-job
```

由于远程作业已在当前会话中启动，因此本地 Get-Job 命令将获取该作业。 作业对象的 State 属性显示该命令已成功完成。

```Output
SessionId   Name   State      HasMoreData   Location   Command
---------   ----   -----      -----------   --------   -------
1           Job1   Completed  True          Server01   get-eventlog system
```

#### <a name="step-3-receive-job"></a>步骤3：接收作业

若要获取作业结果，请使用 Receive-Job cmdlet。 由于作业结果会自动返回到作业对象所在的计算机，因此你可以使用本地 Receive-Job 命令获取结果。

以下命令使用 Receive-Job cmdlet 获取作业的结果。 它使用会话 ID 来标识作业。 此命令将作业结果保存在 $results 变量中。 你还可以将结果重定向到文件。

```powershell
$results = receive-job -id 1
```

### <a name="start-a-remote-job-that-keeps-the-results-on-the-remote-computer"></a>启动远程作业以在远程计算机上保留结果

若要在远程计算机上启动后台作业，以在远程计算机上保留命令结果，请使用 Invoke-Command cmdlet 在远程计算机上运行 Start-Job 命令。 您可以使用此方法在多台计算机上运行后台作业。

远程运行 Start-Job 命令时，将在远程计算机上创建作业对象，并在远程计算机上维护作业结果。
从作业的角度来看，所有操作都是本地的。 你只需远程运行命令来管理远程计算机上的本地作业。

#### <a name="step-1-invoke-command-start-job"></a>步骤1：调用-命令启动-作业

使用 Invoke-Command cmdlet 在远程计算机上运行 Start-Job 命令。

此命令需要 PSSession (持久性连接) 。 如果使用 Invoke-Command 的 ComputerName 参数建立临时连接，则在返回作业对象时，Invoke-Command 命令会被视为已完成。 因此，临时连接将关闭，并且该作业将被取消。

以下命令使用 New-PSSession cmdlet 来创建连接到 Server01 计算机的 PSSession。 该命令将 PSSession 保存在 \$ s 变量中。

```powershell
$s = new-pssession -computername Server01
```

下一个命令使用 Invoke-Command cmdlet 在 PSSession 中运行 Start-Job 命令。 Start-Job 命令和 Get-Eventlog 命令括在大括号中。

```powershell
invoke-command -session $s -scriptblock {
  start-job -scriptblock {get-eventlog system}}
```

结果类似于以下示例输出。

```Output
Id       Name    State      HasMoreData     Location   Command
--       ----    -----      -----------     --------   -------
2        Job2    Running    True            Localhost  get-eventlog system
```

远程运行 Start-Job 命令时，Invoke-Command 返回 Start-Job 返回的相同类型的作业对象。 可以将作业对象保存在变量中，也可以使用 Get-Job 命令来获取作业。

请注意，Location 属性的值显示作业在本地计算机上运行，也称为 "LocalHost"，即使该作业在 Server01 计算机上运行也是如此。 由于作业对象是在 Server01 计算机上创建的，并且作业在同一台计算机上运行，因此将其视为本地后台作业。

#### <a name="step-2-invoke-command-get-job"></a>步骤2：调用-命令获取

若要管理远程后台作业，请使用作业 cmdlet。 由于作业对象位于远程计算机上，因此您需要运行远程命令来获取、停止、等待或检索作业结果。

若要查看作业是否已完成，请使用 Invoke-Command 命令在连接到 Server01 计算机的 PSSession 中运行 Get-Job 命令。

```powershell
invoke-command -session $s -scriptblock {get-job}
```

该命令返回一个作业对象。 作业对象的 State 属性显示该命令已成功完成。

```Output
SessionId   Name  State      HasMoreData   Location   Command
---------   ----  -----      -----------   --------   -------
2           Job2  Completed  True          LocalHost   get-eventlog system
```

#### <a name="step-3-invoke-command-receive-job"></a>步骤3：调用-命令接收-作业

若要获取作业结果，请使用 Invoke-Command cmdlet 在连接到 Server01 计算机的 PSSession 中运行 Receive-Job 命令。

以下命令使用 Receive-Job cmdlet 获取作业的结果。 它使用会话 ID 来标识作业。 此命令将作业结果保存在 \$ 结果变量中。 它使用 Receive-Job 的 Keep 参数将结果保存在远程计算机上的作业缓存中。

```powershell
$results = invoke-command -session $s -scriptblock {
  receive-job -sessionid 2 -keep}
```

你还可以将结果重定向到本地或远程计算机上的文件。
以下命令使用重定向运算符将结果保存到 Server01 计算机上的文件中。

```powershell
invoke-command -session $s -command {
  receive-job -sessionid 2 > c:\logs\pslog.txt}
```

## <a name="see-also"></a>另请参阅

[about_Jobs](about_Jobs.md)

[about_Job_Details](about_Job_Details.md)

[about_Remote](about_Remote.md)

[about_Remote_Variables](about_Remote_Variables.md)

[Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command)

[Start-Job](xref:Microsoft.PowerShell.Core.Start-Job)

[Get-Job](xref:Microsoft.PowerShell.Core.Get-Job)

[Wait-Job](xref:Microsoft.PowerShell.Core.Wait-Job)

[Stop-Job](xref:Microsoft.PowerShell.Core.Stop-Job)

[Remove-Job](xref:Microsoft.PowerShell.Core.Remove-Job)

[New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)

[Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[Exit-PSSession](xref:Microsoft.PowerShell.Core.Exit-PSSession)
