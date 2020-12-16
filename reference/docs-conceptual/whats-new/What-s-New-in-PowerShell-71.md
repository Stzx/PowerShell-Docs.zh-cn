---
title: PowerShell 7.1 中的新增功能
description: PowerShell 7.1 中发布的新功能和更改
ms.date: 11/11/2020
ms.openlocfilehash: 5596d3ca69f5d8ea47f01ff0915e6fa33c1c463f
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625714"
---
# <a name="whats-new-in-powershell-71"></a>PowerShell 7.1 中的新增功能

PowerShell 7.1 是 PowerShell 一个开源的跨平台（Windows、macOS 和 Linux）版本，为管理异类环境和混合云而构建。

在 PowerShell 7.0 建立的基础上，我们重点关注社区问题，并包括一些改进和修复。 我们致力于确保 PowerShell 仍然是一个稳定的高性能平台。

PowerShell 7.1 还包括 PSReadLine 2.1.0。 此版本包含预测性 IntelliSense。 有关预测性 IntelliSense 功能的详细信息，请参阅 PowerShell 博客中的[公告](https://devblogs.microsoft.com/powershell/announcing-psreadline-2-1-with-predictive-intellisense/)。

## <a name="where-can-i-install-powershell"></a>可将 PowerShell 安装在何处？

<!-- TODO: Update list of OS below - make sure this is consistent across all docs -->

PowerShell 7.1 当前支持 x64 上的以下操作系统，包括：

- Windows 8.1/10（包括 ARM64）
- Windows Server 2012 R2、2016、2019 和半年频道 (SAC)
- Ubuntu 16.04/18.04/20.04（包括 ARM64）
- Ubuntu 19.10（通过 Snap 包）
- Debian 9/10
- CentOS 和 RHEL 7/8
- Fedora 32
- Alpine 3.11+（包括 ARM64）
- macOS 10.13+

我们还针对以下内容提供社区支持：

- Arch Linux
- Raspbian Linux
- Kali Linux

有关支持的操作系统和支持生命周期的最新信息，请参阅 [PowerShell 支持生命周期](/powershell/scripting/powershell-support-lifecycle)

PowerShell 7.1 已发布到 Microsoft Store。 你可以在 [Microsoft Store](https://www.microsoft.com/store/apps/9MZ1SNWT0N5D) 网站上或在 Windows 应用商店应用程序中找到 PowerShell 版本。

Microsoft Store 包的权益：

- 直接内置于 Windows 10 的自动更新
- 与其他软件分发机制（如 Intune 和 SCCM）集成

> [!NOTE]
> 不能修改存储在 `$PSHOME` 中的任何系统级配置设置。 其中包括 WSMAN 配置。 这可以防止远程会话连接到 PowerShell 的基于应用商店的安装。 支持用户级配置和 SSH 远程处理。

查看首选操作系统的安装说明：

- [Windows](/powershell/scripting/install/installing-powershell-core-on-windows)
- [macOS](/powershell/scripting/install/installing-powershell-core-on-macos)
- [Linux](/powershell/scripting/install/installing-powershell-core-on-linux)

此外，PowerShell 7.1 还支持 ARM32 和 ARM64 版的 Debian、Ubuntu 和 ARM64 Alpine Linux。

虽然没有得到正式支持，但社区还提供了 [Arch](https://aur.archlinux.org/packages/powershell/) 和 Kali Linux 的包。

> [!NOTE]
> Debian 10+、CentOS 8+、Ubuntu 20.04、Alpine 和 Arm 目前不支持 WinRM 远程处理。 有关设置基于 SSH 的远程处理的详细信息，请参阅[通过 SSH 进行 PowerShell 远程处理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)。

## <a name="running-powershell-71"></a>运行 PowerShell 7.1

PowerShell 7.1 安装到新目录，并与 Windows PowerShell 5.1 并行运行。
PowerShell 7.1 是就地升级，升级后会替换 PowerShell 6.x 或 PowerShell 7.0。

- PowerShell 7.1 安装到 `%programfiles%\PowerShell\7`
- `%programfiles%\PowerShell\7` 文件夹已添加到 `$env:PATH`

PowerShell 7.1 安装程序包升级以前版本的 PowerShell Core 6.x：

- Windows 上的 PowerShell Core 6.x：`%programfiles%\PowerShell\6` 已替换为 `%programfiles%\PowerShell\7`
- Linux：`/opt/microsoft/powershell/6` 已替换为 `/opt/microsoft/powershell/7`
- macOS：`/usr/local/microsoft/powershell/6` 已替换为 `/usr/local/microsoft/powershell/7`

> [!NOTE]
> 在 Windows PowerShell 中，用于启动 PowerShell 的可执行文件名为 `powershell.exe`。 在版本 6 及更高版本中，可执行文件将更改为支持并行执行。 用于启动 PowerShell 7.1 的新可执行文件为 `pwsh.exe`。 预览版本将就地保留为 `pwsh-preview`，而不是 7 预览目录下的 `pwsh`。

## <a name="breaking-changes-and-improvements"></a>重大更改和改进

有关更改和改进的最新信息，请参阅 GitHub 存储库中的 [CHANGELOG](https://github.com/PowerShell/PowerShell/tree/master/CHANGELOG)。

### <a name="breaking-changes"></a>重大更改

<!-- TODO: Add descriptions for each breaking change - this might need to be a separate article that we link to -->

- 当本机命令写入 `stderr` 时，将 `$?` 修复为非 `$false` (#13395)
- 在 `Get-Date` 上将 `-FromUnixTime` 重命名为 `-UnixTimeSeconds`，以允许 Unix 时间输入 (#13084)（感谢 @aetos382！）
- 使 `$ErrorActionPreference` 不会影响本机命令的 `stderr` 输出 (#13361)
- 允许显式指定的命名参数取代展开的哈希表中的同一个参数 (#13162)
- 使开关参数 `-Qualifier` 不在 `Split-Path` 的位置 (#12960)（感谢 @yecril71pl！）
- 未指定工作目录时，将工作目录解析为 `Start-Process` 的文本路径 (#11946)（感谢 @NoMoreFood！）
- 在 Web cmdlet 中指定 `-OutFile` 参数，使其具有与 `-LiteralPath` 相同的作用 (#11701)（感谢 @iSazonov！）
- 修复 `BigInteger` 数字文本的字符串参数绑定 (#11634)（感谢 @vexx32！）
- 在 Windows 上，`Start-Process` 通过当前会话中的所有环境变量创建进程环境，同时使用 `-UseNewEnvironment` 创建新的默认进程环境 (#10830)（感谢 @iSazonov！）
- 将 ScriptBlock 转换为委托时，不要将返回结果包装为 `PSObject` (#10619)
- 对 `-replace` 运算符使用固定区域性字符串转换 (#10954)（感谢 @iSazonov！）

### <a name="experimental-features"></a>实验性功能

有关实验性功能的详细信息，请参阅[使用实验性功能](../learn/experimental-features.md)。

- 将 `PSNullConditionalOperators` 功能移出实验性功能范围 (#13529)
- 将 `PSUnixFileStat` 功能移出实验性功能范围
- 将 `-Runspace` 参数添加到所有 `*-PSBreakpoint` cmdlet 中 (#10492)（感谢 @KirkMunro！）
- 添加 `PSNativePSPathResolution` 以支持将 `PSPath` 传递到本机命令 (#12386)
- 对 `-replace` 运算符使用固定区域性字符串转换 (#10954)（感谢 @iSazonov！）
- 添加 `PSSubsystemPluginModel` 以支持将来的预测性 IntelliSense 插件

### <a name="general-cmdlet-updates-and-fixes"></a>常规 Cmdlet 更新和修补程序

- `ConvertTo-Json` 超出 `-Depth` 值范围时发出警告 (#13692)
- 修复 Windows 上异常消息只包含 ``"`n"`` 的情况 (#13684)
- 将 `CONOUT$` 和 `CONIN$` 识别为保留设备名称 (#13508)（感谢 @davidreis97！）
- 在写入错误时修复交互式高级函数的 `ConciseView` (#13623)
- 增加对 Web cmdlet 中 `TLS` 1.3 的支持 (#13409)（感谢 @iSazonov！）
- 为 `CommandLineParser` 中的 `args` 添加 null 检查 (#13451)（感谢 @iSazonov！）
- 处理 Microsoft Store 应用程序的重新分析点 (#13481)（感谢 @iSazonov！）
- 使用适用于容器的 PowerShell Direct 时，如果 `ObRoot` 的属性不存在，则使用字段 (#13375)（感谢 @hemisphera！）
- 取消 `UTF-7` 已过时警告 (#13484)
- 避免 `Compiler.cs` 中的 `IEnumerable<Expression>` 实例的多个枚举 (#13491)
- 将 `Add-Type -OutputType` 更改为不支持 `ConsoleApplication` 和 `WindowsApplication` (#13440)
- 将 `UTF-7` 指定为编码时创建警告 (#13430)
- 修复新的符号链接缺少目标的错误消息 (#13085)（感谢 @yecril71pl！）
- 使参数 `args` 在公共 `ConsoleHost` API 中不可为 null (#13429)
- 添加 `CancellationTokenSource` 缺失的处置 (#13420)（感谢 @Youssef1313！）
- 修复在参数支持通配符情况下不能正确显示的 `Get-Help` (#13353)（感谢 @ThomasNieto！）
- 更新 `-InputFormat` 参数的 `pwsh` 帮助 (#13355)（感谢 @sethvs！）
- 为从 Roslyn 复制的文件声明 MIT 许可证 (#13305)（感谢 @xtqqczze！）
- 改进 `BigInteger` 强制转换行为（#12629）（感谢 @vexx32！）
- 修复 `Get-Acl -LiteralPath "HKLM:Software\Classes\*"` 行为 (#13107)（感谢 @Shriram0908！）
- 向访问者接口和类添加 `DefaultVisit` 方法 (#13258)
- 修复 `pwsh` 存在冲突的缩写开关 `-s` (STA)(#13262)（感谢 @iSazonov！）
- 将 `Read-Host -MaskInput` 更改为使用现有的 `SecureString` 路径，但以纯文本形式返回 (#13256)
- .NET 5.0 中现在支持使用 `IEnumerator` 删除 `ComEnumerator` 作为 COM 对象 (#13259)
- 如果未定义“HOME”环境变量，则在运行空间启动时使用临时个人路径 (#13239)
- 修复 `Invoke-Command` 以检测同一历史记录项的递归调用 (#13197)
- 将 `pwsh` 可执行 `-inputformat` 开关前缀 `-in` 更改为 `-inp` 以修复 `-interactive` 冲突 (#13205)（感谢 @iSazonov！）
- 分析文件安全区域时处理 WSL 文件系统路径 (#13120)
- 在 `Split-Path` 中强制使用其他开关 (#13150)（感谢 @kvprasoon！）
- 适用于 PowerShell 7 的全新 Fluent Design 图标 (#13100)（感谢 @sarthakmalik！）
- 修复 `Move-Item` 以支持 Unix 上的交叉装入移动 (#13044)
- 修复 `CommandSearcher.GetNextCmdlet` 中的 `NullReferenceException` (#12659)（感谢 @powercode！）
- 阻止具有活动测试挂钩的 Unix 计算机 cmdlet 中的 `NullReferenceException` (#12651)（感谢 @vexx32！）
- 修复 `Select-Object` 中 `Hashtable` 成员（例如 `Keys`）无法与 `-Property` 或 `-ExpandProperty` 一起使用的问题 (#11097)（感谢 @vexx32！）
- 修复 pwsh 存在冲突的缩写开关 `-w` (#12945)
- 重命名 `CimCmdlet` 资源文件 (#12955)（感谢 @iSazonov！）
- 删除 `ConciseView` 中使用的 `Test-Path` (#12778)
- 标记 `default` 开关语句条件子句作为关键字 (#10487)（感谢 @msftrncs！）
- 将参数 `SchemaFile` 添加到 `Test-Json` cmdlet (#11934)（感谢 @beatcracker！）
- 恢复证书提供程序参数 (#10622)（感谢 @iSazonov！）
- 修复 `New-Item` 以创建相对路径目标的符号链接 (#12797)（感谢 @iSazonov！）
- 将 `CommandLine` 属性添加到进程 (#12288)（感谢 @iSazonov！）
- 将 `-MaskInput` 参数添加到 `Read-Host` (#10908)（感谢 @davinci26！）
- 将 `CimCmdlets` 更改为使用 `AliasAttribute` (#12617)（感谢 @thlac！）
- 修复 ParameterBinderBase 中格式字符串中的不正确索引 (#12630)（感谢 @powercode！）
- 在 `Command.Clone()` 中复制 `CommandInfo` 属性 (#12301)（感谢 @TylerLeonhardt！）
- 指定 `-ExcludeDifferent` 时在 `Compare-Object` 中应用 `-IncludeEqual` (#12317)（感谢 @davidseibel！）
- 将 `Get-FileHash` 更改为在写入输出之前关闭文件句柄 (#12474)（感谢 @HumanEquivalentUnit！）
- 修复 `-replace` 运算符中不一致的异常消息 (#12388)（感谢 @jackdcasey！）
- 修复 `WinCompat` 模块加载，将 PowerShell 7 模块视为具有较高优先级 (#12269)
- 实现 `ForEach-Object -Parallel` 运行空间重用 (#12122)
- 修复 `Get-Service`，在枚举集合时不对其进行修改 (#11851)（感谢 @NextTurn！）
- 在 PowerShell 退出时清理 IPC 命名管道 (#12187)
- 修复 Web cmdlet 中的 `<img />` 检测 regex (#12099)（感谢 @vexx32！）
- 允许在较短的带符号的十六进制文本上加上适当的类型后缀 (#11844)（感谢 @vexx32！）
- 更新 Windows 上 `Start-Process` cmdlet 的 `UseNewEnvironment` 参数行为 (#10830)（感谢 @iSazonov！）
- 将 `-Shuffle` 开关添加到 `Get-Random` 命令 (#11093)（感谢 @eugenesmlv！）
- 使 `GetWindowsPowerShellModulePath` 与多个 PS 安装兼容 (#12280)
- 修复 `Start-Job` 以便在未将 Windows PowerShell 注册为默认 shell 的系统上运行 (#12296)
- 向 `Get-Command` 指定别名和 `-Syntax` 可以返回有别名的命令语法 (#10784)（感谢 @ChrisLGardner！）
- 当使用 `-AsNeeded` 且有不完整行时，使 CSV cmdlet 起作用 (#12281)（感谢 @iSazonov！）
- 在本地调用中，为了查看所有格式数据，不要求 `Get-FormatData` 为 `-PowerShellVersion 5.1`。 (#11270)（感谢 @mklement0！）
- 增加了对 Big Endian `UTF-32` 的支持 (#11947)（感谢 @NoMoreFood！）
- 修复 `ForEach-Object -Parallel` 中可能出现的导致泄漏 PowerShell 对象处置的争用 (#12227)
- 将 `-FromUnixTime` 添加到 `Get-Date` 以允许 Unix 时间输入 (#12179)（感谢 @jackdcasey！）
- 更改默认进度前景色和背景色以提高对比度 (#11455)（感谢 @rkeithhill！）
- 修复当前驱动器不可用情况下的 `foreach -parallel` (#12197)
- 将 `ScriptBlock` 转换为 `delegate` 时，不要将返回结果包装为 `PSObject` (#10619)
- 请勿在 `Test-Connection -Quiet` 上写入 DNS 解析错误 (#12204)（感谢 @vexx32！）
- 使用专用线程从子进程中读取重定向输出和错误流，用于处理进程外的作业 (#11713)
- 修复绑定器代码中的运算符首选项顺序问题 (#12075)（感谢 @DamirAinullin！）
- 修复在绑定 `ActionPreference` 类型的通用参数时的 `NullReferenceException` (#12124)
- 修复反序列化的 `MatchInfo` 的默认格式设置 (#11728)（感谢 @iSazonov！）
- 在 `Invoke-RestMethod` 中使用异步流 (#11095)（感谢 @iSazonov！）
- 解决 `Get-Content -Tail` 中的 UTF-8 检测问题 (#11899)（感谢 @NoMoreFood！）
- 处理 `Get-FileHash` 中的 `IOException` (#11944)（感谢 @iSazonov！）
- 将资源字符串中的 `PowerShell Core` 更改为 `PowerShell` (#11928)（感谢 @alexandair！）
- 恢复 `PSHostProcessInfo` 中的 `MainWindowTitle` (#11885)（感谢 @iSazonov！）
- Windows 兼容性的其他次要更新 (#11980)
- 修复 `ConciseView` 以使用 `[Environment]::NewLine` 拆分 `PositionMessage` (#12010)
- 为交互式会话删除网络跃点限制 (#11920)
- 修复 `SuspendStoppingPipeline()` 和 `RestoreStoppingPipeline()` 中的 `NullReferenceException` (#11870)（感谢 @iSazonov！）
- 如果未提供 `FormatViewDefinition` `InstanceId` 的 GUID，则生成它 (#11896)
- 修复 `ConciseView` 中错误消息宽度超出窗口宽度且没有空格的问题 (#11880)
- 允许跨平台 `CAPI-compatible` 远程密钥交换 (#11185)（感谢 @silijon！）
- 修复错误消息 (#11862)（感谢 @NextTurn！）
- 修复 `ConciseView` 以处理没有可以获取宽度的控制台的情况 (#11784)
- 更新 `CmsCommands` 以使用应用商店与证书提供程序 (#11643)（感谢 @mikeTWC1984！）
- 启用 `pwsh`，使其在无法使用 `mpr.dll` 和 STA 的 Windows 系统上运行 (#11748)
- 重构和实现适用于 `Un*x` 和 macOS 的 `Restart-Computer` (#11319)
- 添加适用于 Linux 和 macOS 的 `Stop-Computer` 的实现 (#11151)
- 修复 `help` 函数，在使用之前确认 `less` 是否可用 (#11737)
- 更新 `certificate_format_ps1.xml` 中的 `PSPath` (#11603)（感谢 @xtqqczze！）
- 更改正则表达式以匹配链接标头中不带引号的关系类型 (#11711)（感谢 @Marusyk！）
- 修复符号链接删除期间的错误消息 (#11331)
- 将自定义 `Selected.*` 类型添加到 `Select-Object` 中的 `PSCustomObject` 且仅添加一次 (#11548)（感谢 @iSazonov!）
- 将 `-AsUTC` 添加到 `Get-Date` cmdlet (#11611)
- 修复 `Format-Hex` 中布尔值的分组行为 (#11587)（感谢 @vexx32！）
- 使 `Test-Connection` 始终使用默认同步上下文发送 ping 请求 (#11517)
- 修正启动错误消息 (#11473)（感谢 @iSazonov！）
- 在 Web cmdlet 中忽略包含 null 值的标头 (#11424)（感谢 @iSazonov！）
- 为 `Invoke-Command` 作业处置重新添加检查。 (#11388)
- 还原“如果内容为空，则更新格式化程序以不写入换行符 (#11193)”(#11342)（感谢 @iSazonov！）
- 当 `AST` 或脚本具有匹配的函数定义时，允许 `CompleteInput` 从 `ArgumentCompleter` 返回结果 (#10574)（感谢 @M1kep！）
- 如果内容为空，则更新格式化程序以不写入换行符 (#11193)

<!-- TODO: add more general contributor thank you listing -->
