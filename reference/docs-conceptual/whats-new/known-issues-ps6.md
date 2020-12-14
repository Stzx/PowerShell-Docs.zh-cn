---
ms.date: 02/03/2020
keywords: powershell, 核心
title: PowerShell 6.0 的已知问题
description: 这是对 PowerShell 6 中的已知问题或限制的总结
ms.openlocfilehash: 288bd664d511ebfd18408ce80ec3481333dbba37
ms.sourcegitcommit: f9d855dd73b916559a22e337672dea3fbb11c634
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "96833750"
---
# <a name="known-issues-for-powershell-60"></a>PowerShell 6.0 的已知问题

## <a name="known-issues-for-powershell-on-non-windows-platforms"></a>非 Windows 平台上 PowerShell 的已知问题

Linux 和 macOS 上的 PowerShell 的 Alpha 版本通常能正常运行，但确实存在一些明显的限制和可用性问题。 Linux 和 macOS 上的 PowerShell 的 Beta 版本比 alpha 版本功能更加强大且稳定，但仍可能缺少一些功能，并可能包含 bug。 在某些情况下，这些问题只是尚未得到修复的 bug。 在其他情况下（对于 ls、cp 等的默认别名），我们正在寻求社区对我们所做选择的反馈。

注意：由于许多基础子系统的相似性，Linux 和 macOS 上的 PowerShell 倾向于在功能和 bug 方面共享相同的成熟度级别。 除下文所述，本部分中的问题适用于这两个操作系统。

### <a name="case-sensitivity-in-powershell"></a>PowerShell 中的区分大小写

PowerShell 一直以来均区分大小写，只有少数例外情况。 在类似于 UNIX 的操作系统上，文件系统基本都区分大小写，并且 PowerShell 遵守文件系统的标准；这通过多种方式显示，明显和非明显的方式。

#### <a name="directly"></a>直接

- 在 PowerShell 中指定一个文件时，必须使用正确的大小写。

#### <a name="indirectly"></a>间接

- 如果脚本尝试加载模块，而模块名称的大小写不正确，则模块加载失败。 如果引用模块所依据的名称与实际文件名不一致，这可能会导致现有脚本出现问题。
- 如果文件名的大小写不正确，Tab 键补全不会自动完成。 要完成的片段必须采用正确的大小写。 （对于类型名称和类型成员完成，完成是不区分大小写的。）

### <a name="ps1-file-extensions"></a>.PS1 文件扩展名

PowerShell 脚本必须以 `.ps1` 结尾，以便解释器了解如何在当前进程中加载并运行它们。 在当前进程中运行脚本是 PowerShell 的预期常见行为。 可以将 `#!` 幻数添加到没有 `.ps1` 扩展名的脚本中，但这会导致脚本在新的 PowerShell 实例中运行，进而导致脚本无法在交换对象时正常运行。 （注意：这可能是从 `bash` 或其他 shell 执行 PowerShell 脚本时所期望的行为。）

### <a name="missing-command-aliases"></a>缺少命令别名

在 Linux/macOS 上，已删除基本命令 `ls`、`cp`、`mv`、`rm`、`cat`、`man`、`mount`、`ps` 的“方便别名”。 在 Windows 上，为了方便用户，PowerShell 提供一组映射到 Linux 命令名的别名。 已从 Linux/macOS 分发上的默认 PowerShell 中删除这些别名，以允许在不指定路径的情况下运行本机可执行文件。

执行此操作既有优点，又有缺点。 删除别名会向 PowerShell 用户公开本机命令体验，但会降低 shell 中的功能，因为本机命令会返回字符串，而不是对象。

> [!NOTE]
> PowerShell 团队正在寻求此方面的反馈。 首选解决方案是什么？
> 我们应保持原样还是重新添加方便别名？ 请参阅[问题 #929](https://github.com/PowerShell/PowerShell/issues/929)。

### <a name="missing-wildcard-globbing-support"></a>缺少通配符（通配）支持

目前，PowerShell 只对 Windows 上的内置 cmdlet 和 Linux 上的外部命令或二进制文件及 cmdlet 做通配符扩展（通配）。 也就是说，诸如 `ls
*.txt` 之类的命令会失败，因为星号不会展开来匹配文件名。 可以通过执行 `ls (gci *.txt | % name)` ，或更简单地使用等效于 `ls` 的 PowerShell 内置项来执行 `gci *.txt` 以解决此问题。

请参阅 [#954](https://github.com/PowerShell/PowerShell/issues/954) 提供有关如何改进 Linux/macOS 上通配体验的反馈。

### <a name="net-framework-vs-net-core-framework"></a>.NET Framework 和 .NET Core Framework

Linux/macOS 上的 PowerShell 使用 .NET Core，即 Microsoft Windows 上的完整 .NET Framework 的子集。 这非常重要，因为 PowerShell 提供对基础框架类型、方法等的直接访问。因此，在 Windows 上运行的脚本可能无法在非 Windows 平台上运行，因为框架之间存在差异。 有关 .NET Core Framework 的详细信息，请参阅 [dotnetfoundation.org](https://dotnetfoundation.org/)。

随着 [.NET Standard 2.0](https://devblogs.microsoft.com/dotnet/introducing-net-standard/) 推出，.NET Core 2.0 恢复了完整 .NET Framework 中的许多传统类型和方法。 也就是说，PowerShell Core 能够加载许多传统 Windows PowerShell 模块，而无需修改。 可以在[此处](https://github.com/PowerShell/PowerShell/projects/4)了解我们有关 .NET Standard 2.0 的工作。

### <a name="redirection-issues"></a>重定向问题

任何平台上的 PowerShell 中均不支持输入重定向。
[问题 #1629](https://github.com/PowerShell/PowerShell/issues/1629)

使用 `Get-Content` 将文件内容写入管道。

如果使用的是默认 UTF-8 编码，重定向的输出包含 Unicode 字节顺序标记 (BOM)。 在与不应出现的实用工具配合使用或附加到文件时，BOM 会导致问题出现。 使用 `-Encoding Ascii` 编写不包含 BOM 的 ASCII 文本。

> [!Note]
> 请参阅 [RFC0020](https://github.com/PowerShell/PowerShell-RFC/issues/71)，向我们提供有关在所有平台上改进 PowerShell Core 编码体验的反馈。 我们致力于支持不带 BOM 的 UTF-8，以及可能不断变化的各种跨平台的 cmdlet 的编码默认值。

### <a name="job-control"></a>作业控制

Linux/macOS 上的 PowerShell 中不支持作业控制。
`fg` 和 `bg` 命令不可用。

目前，可以使用跨所有平台执行操作的 [PowerShell 作业](/powershell/module/microsoft.powershell.core/about/about_jobs)。

### <a name="remoting-support"></a>远程处理支持

目前，PowerShell Core 支持在 macOS 和 Linux 上经过基本身份验证以及在 Linux 上经过基于 NTLM 的身份验证的通过 WSMan 的 PowerShell 远程处理 (PSRP)。 （不支持基于 Kerberos 的身份验证。）

在 [psl-omi-provider](https://github.com/PowerShell/psl-omi-provider) 存储库中完成基于 WSMan 的远程处理工作。

PowerShell Core 还支持所有平台（Windows、macOS 和 Linux）上通过 SSH 的 PowerShell 远程处理 (PSRP)。 虽然目前在生产中不支持此功能，但可以在[此处](/powershell/scripting/learn/remoting/SSH-Remoting-in-PowerShell-Core)了解有关此设置的详细信息。

### <a name="just-enough-administration-jea-support"></a>Just-Enough-Administration (JEA) 支持

Linux/macOS 上的 PowerShell 目前无法创建约束管理 (JEA) 远程处理终结点。 此功能目前不在 6.0 的范围内，我们将在后 6.0 中考虑此功能，因为它需要大量的设计工作。

### <a name="sudo-exec-and-powershell"></a>`sudo`、`exec` 和 PowerShell

由于 PowerShell 在内存（如 Python 或 Ruby）中运行大多数命令，不能直接将 sudo 与 PowerShell 内置项一起使用。（当然，可以从 sudo 运行 `pwsh`。）如果需要使用 sudo（例如，`sudo Set-Date 8/18/2016`）从 PowerShell 内运行 PowerShell cmdlet，则要执行 `sudo pwsh Set-Date 8/18/2016`。 同样，不能直接执行 PowerShell 内置项。 而必须执行 `exec pwsh item_to_exec`。

此问题正作为 [#3232](https://github.com/PowerShell/PowerShell/issues/3232) 的一部分进行跟踪。

### <a name="missing-cmdlets"></a>缺少 Cmdlet

通常可用于 PowerShell 的大多数命令 (cmdlet) 在 Linux/macOS 上不可用。 在许多情况下，这些命令在这些平台（例如，类似于注册表的 Windows 特定的功能）上没有意义。 类似于服务控制命令 (Get/Start/Stop-Service) 的其他命令存在，但不起作用。 将来发布的版本可能会纠正这些问题，具体方法是修复损坏的 cmdlet，并随时间推移添加新 cmdlet。

### <a name="command-availability"></a>命令可用性

下表列出了 Linux/macOS 上的 PowerShell 中已知不起作用的命令。

|命令|操作状态|说明|
|--------|-----------------|-----|
|`Get-Service`, `New-Service`, `Restart-Service`, `Resume-Service`, `Set-Service`, `Start-Service`, `Stop-Service`, `Suspend-Service`|不可用。|这些命令无法识别。 应在将来的版本中解决此问题。|
|`Get-Acl`, `Get-AuthenticodeSignature`, `Get-CmsMessage`, `New-FileCatalog`, `Protect-CmsMessage`, `Set-Acl`, `Set-AuthenticodeSignature`, `Test-FileCatalog`, `Unprotect-CmsMessage`|不可用。|这些命令无法识别。 应在将来的版本中解决此问题。|
|`Wait-Process`|可用，无法正常工作。 |例如，`Start-Process gvim -PassThru | Wait-Process` 无效；它无法等待进程。|
|`Connect-PSSession`, `Disable-PSRemoting`, `Disable-PSSessionConfiguration`, `Disconnect-PSSession`, `Enable-PSRemoting`, `Enable-PSSessionConfiguration`, `Get-PSSessionCapability`, `Get-PSSessionConfiguration`, `New-PSSessionConfigurationFile`, `Receive-PSSession`, `Register-PSSessionConfiguration`, `Set-PSSessionConfiguration`, `Test-PSSessionConfigurationFile`, `Unregister-PSSessionConfiguration`|不可用。|这些命令无法识别。 应在将来的版本中解决此问题。|
|`Get-Event`, `New-Event`, `Register-EngineEvent`, `Remove-Event`, `Unregister-Event`|可用，但没有可用的事件源。|PowerShell 事件命令存在，但与命令一起使用的大部分事件源（例如 System.Timers.Timer）在 Linux 上不可用，使得 Alpha 版本中的命令无效。|
|`Set-ExecutionPolicy`|可用，但不起作用。|返回消息，指示在此平台上不受支持。 执行策略是以用户为中心的“安全带”，有助于防止用户犯下代价昂贵的错误。 这不是安全边界。|
|`New-PSSessionOption`, `New-PSTransportOption`|可用，但 `New-PSSession` 不起作用。|在 `New-PSSession` 起作用时，`New-PSSessionOption` 和 `New-PSTransportOption` 当前未被验证起作用。|
