---
title: 后台作业 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 2a1297b8dfe087474564078cca2a5a0526ed0f36
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774841"
---
# <a name="background-jobs"></a>后台作业

Cmdlet 可以在内部执行其操作，也可以用作 Windows PowerShell*后台作业*。 当某个 cmdlet 作为后台作业运行时，将以异步方式在独立于该 cmdlet 使用的管道线程的单独线程中完成工作。 从用户的角度来看，当某个 cmdlet 作为后台作业运行时，命令提示符会立即返回，即使该作业需要很长时间才能完成，并且在运行作业时，用户可以继续而不中断。

## <a name="background-jobs-child-jobs-and-the-job-repository"></a>后台作业、子作业和作业存储库

支持后台作业的 cmdlet 返回的作业对象定义作业。  ([启动作业](/powershell/module/Microsoft.PowerShell.Core/Start-Job)cmdlet 还会返回一个作业对象。 ) 作业的名称、用于指定作业的标识符、状态信息以及子作业包含在此定义中。 作业不执行任何工作。 每个后台作业至少有一个子作业，因为子作业执行实际工作。 当你运行 cmdlet 以便以后台作业的形式执行工作时，该 cmdlet 必须将作业和子作业添加到公共存储库（称为*作业存储库*）。

有关如何在命令行中处理后台作业的详细信息，请参阅以下内容：

- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [about_Job_Details](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [about_Remote_Jobs](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a>编写作为后台作业运行的 Cmdlet

若要编写可作为后台作业运行的 cmdlet，必须完成以下任务：

- 定义 `asJob` 开关参数，使用户可以决定是否将该 cmdlet 作为后台作业运行。

- 创建一个派生自[system.object](/dotnet/api/System.Management.Automation.Job)类的对象。 此对象可以是自定义作业对象，也可以是 Windows PowerShell 提供的作业对象，例如[Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob)对象。

- 在记录处理方法中，添加一个 `if` 语句来检测该 cmdlet 是否应作为后台作业运行。

- 对于自定义作业对象，请实现 job 类。

- 返回相应的对象，具体取决于 cmdlet 是否作为后台作业运行。

有关代码示例，请参阅[如何支持作业](./how-to-support-jobs.md)。

## <a name="background-job-related-apis"></a>与作业相关的后台 Api

Windows PowerShell 提供以下 Api 来管理后台作业。

[System.web](/dotnet/api/System.Management.Automation.Job)派生自定义作业对象。 这是一个抽象类。

[Jobrepository](/dotnet/api/System.Management.Automation.JobRepository)管理并提供有关当前活动的后台作业的信息。

[Jobstate](/dotnet/api/System.Management.Automation.JobState)用于定义后台作业的状态。 状态包括 "已启动"、"正在运行" 和 "已停止"。

[Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo)提供有关后台作业状态的信息，并且，如果上次状态更改是由错误引起的，则该作业进入其当前状态的原因。

[Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs)提供在后台作业更改状态时引发的事件的参数。

## <a name="windows-powershell-job-cmdlets"></a>Windows PowerShell 作业 Cmdlet

Windows PowerShell 提供以下 cmdlet 来管理后台作业。

[Get-Job](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

获取在当前会话中运行的 Windows PowerShell 后台作业。

[Receive-Job](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

获取当前会话中的 Windows PowerShell 后台作业的结果。

[Remove-Job](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

删除 Windows PowerShell 后台作业。

[Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

启动 Windows PowerShell 后台作业。

[Stop-Job](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

停止 Windows PowerShell 后台作业。

[Wait-Job](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

禁止显示命令提示符，直到在会话中运行的一个或全部 Windows PowerShell 后台作业完成。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
