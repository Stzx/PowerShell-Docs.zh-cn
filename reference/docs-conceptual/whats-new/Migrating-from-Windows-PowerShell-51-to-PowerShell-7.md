---
title: 从 Windows PowerShell 5.1 迁移到 PowerShell 7
description: 为 Windows 平台从 PowerShell 5.1 更新到 PowerShell 7。
ms.date: 03/25/2020
ms.openlocfilehash: e3881b1758f50119444969ad39541aec694cebe5
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500504"
---
# <a name="migrating-from-windows-powershell-51-to-powershell-7"></a>从 Windows PowerShell 5.1 迁移到 PowerShell 7

PowerShell 7 是专为云、本地和混合环境设计的，它包含增强功能和[新功能](What-s-New-in-PowerShell-70.md)。

- 与 Windows PowerShell 并行安装和运行
- 提升了与现有 Windows PowerShell 模块的兼容性
- 新语言功能（如三元运算符和 `ForEach-Object -Parallel`）
- 提高了性能
- 基于 SSH 的远程处理
- 跨平台互操作性
- 支持 Docker 容器

PowerShell 7 与 Windows PowerShell 并行运行，可便于你在部署前轻松地测试和比较各个版本。 迁移简单、快捷、安全， 且不会失败。

以下 Windows 操作系统支持 PowerShell 7：

- Windows 8.1 和 10
- Windows Server 2012、2012 R2、2016 和 2019

PowerShell 7 还在 macOS 和多个 Linux 发行版本上运行。 若要获取受支持操作系统的列表，并了解支持生命周期，请参阅 [PowerShell 支持生命周期](/powershell/scripting/powershell-support-lifecycle)。

## <a name="installing-powershell-7"></a>安装 PowerShell 7

为了实现灵活性并满足 IT、DevOps 工程师和开发人员的需求，有多种 PowerShell 7 安装方法可供选择。 在大多数情况下，可以简化为以下几种安装方法：

- 使用 [MSI 包](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-msi-package)部署 PowerShell
- 使用 [ZIP 包](/powershell/scripting/install/installing-powershell-core-on-windows#installing-the-zip-package)部署 PowerShell

> [!NOTE]
> 可以使用 [System Center Configuration Manager (SCCM)](/configmgr/apps/) 等管理产品来部署和更新 MSI 包。 包是从 [GitHub“发布”页](https://github.com/PowerShell/PowerShell/releases)下载的。

必须有管理员权限，才能部署 MSI 包。 任何用户都可以部署 ZIP 包。 在进行完整安装之前，ZIP 包是安装 PowerShell 7 进行测试的最简单方法。

## <a name="using-powershell-7-side-by-side-with-windows-powershell-51"></a>并行使用 PowerShell 7 与 Windows PowerShell 5.1

根据设计，PowerShell 7 可以与 Windows PowerShell 5.1 共存。 以下功能可确保你的 PowerShell 投资受到保护，并能轻松迁移到 PowerShell 7。

- 独立的安装路径和可执行文件名
- 独立的 PSModulePath
- 每个版本的独立配置文件
- 提升了模块兼容性
- 新增了远程处理终结点
- 组策略支持
- 独立的事件日志

### <a name="separate-installation-path-and-executable-name"></a>独立的安装路径和可执行文件名

PowerShell 7 安装到新目录，这样就能与 Windows PowerShell 5.1 并行执行了。

按版本列出的安装位置：

- Windows PowerShell 5.1：`$env:WINDIR\System32\WindowsPowerShell\v1.0`
- PowerShell Core 6.x：`$env:ProgramFiles\PowerShell\6`
- PowerShell 7：`$env:ProgramFiles\PowerShell\7`

新位置会添加到 PATH 中，这样就能同时运行 Windows PowerShell 5.1 和 PowerShell 7 了。 若要从 PowerShell Core 6.x 迁移到 PowerShell 7，则会删除 PowerShell 6，并替换 PATH。

在 Windows PowerShell 中，PowerShell 可执行文件名为 `powershell.exe`。 在版本 6 及更高版本中，可执行文件名为 `pwsh.exe`。 使用新名称，可以轻松支持两个版本的并行执行。

### <a name="separate-psmodulepath"></a>独立的 PSModulePath

默认情况下，Windows PowerShell 和 PowerShell 7 将模块存储在不同的位置。 PowerShell 7 将这些位置合并到 `$Env:PSModulePath` 环境变量中。 当按名称导入模块时，PowerShell 检查由 `$Env:PSModulePath` 指定的位置。 这样，PowerShell 7 就可以同时加载核心模块和桌面模块了。

|            安装范围            |                Windows PowerShell 5.1                 |             PowerShell 7.0             |
| ----------------------------------- | ----------------------------------------------------- | -------------------------------------- |
| PowerShell 模块                  | `$env:WINDIR\system32\WindowsPowerShell\v1.0\Modules` | `$PSHOME\Modules`                      |
| 用户已安装<br>AllUsers 范围    | `$env:ProgramFiles\WindowsPowerShell\Modules`         | `$env:ProgramFiles\PowerShell\Modules` |
| 用户已安装<br>CurrentUser 范围 | `$HOME\Documents\WindowsPowerShell\Modules`           | `$HOME\Documents\PowerShell\Modules`   |

下面的示例展示了每个版本的 `$Env:PSModulePath` 默认值。

- 对于 Windows PowerShell 5.1：

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\WindowsPowerShell\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

- 对于 PowerShell 7：

  ```powershell
  $Env:PSModulePath -split (';')
  ```

  ```Output
  C:\Users\<user>\Documents\PowerShell\Modules
  C:\Program Files\PowerShell\Modules
  C:\Program Files\PowerShell\7\Modules
  C:\Program Files\WindowsPowerShell\Modules
  C:\WINDOWS\System32\WindowsPowerShell\v1.0\Modules
  ```

请注意，为了提供模块自动加载功能，PowerShell 7 同时包含 Windows PowerShell 路径和 PowerShell 7 路径。

> [!NOTE]
> 如果你更改了 PSModulePath 环境变量或安装了自定义模块或应用程序，可能还存在其他路径。

有关详细信息，请参阅 [about_Environment_Variables](/powershell/module/microsoft.powershell.core/about/about_environment_variables#environment-variables-that-store-preferences) 中的 `PSModulePath`。

若要详细了解模块，请参阅 [about_Modules](/powershell/module/Microsoft.PowerShell.Core/About/about_Modules)。

### <a name="separate-profiles"></a>独立的配置文件

PowerShell 配置文件是在 PowerShell 启动时执行的脚本。 此脚本通过添加命令、别名、函数、变量、模块和 PowerShell 驱动器来自定义环境。 配置文件脚本让这些自定义对每个会话都可用，而不必手动重新创建它们。

在 PowerShell 7 中，配置文件的位置路径发生了更改。

- 在 Windows PowerShell 5.1 中，配置文件的位置为 `$HOME\Documents\WindowsPowerShell`。
- 在 PowerShell 7 中，配置文件的位置为 `$HOME\Documents\PowerShell`。

配置文件的文件名也发生了更改：

   ```powershell
   PS> $PROFILE | Select-Object *Host* | Format-List

   AllUsersAllHosts       : C:\Program Files\PowerShell\7\profile.ps1
   AllUsersCurrentHost    : C:\Program Files\PowerShell\7\Microsoft.PowerShell_profile.ps1
   CurrentUserAllHosts    : C:\Users\<user>\Documents\PowerShell\profile.ps1
   CurrentUserCurrentHost : C:\Users\<user>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
   ```

有关详细信息，请参阅 [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles)。

### <a name="powershell-7-compatibility-with-windows-powershell-51-modules"></a>PowerShell 7 与 Windows PowerShell 5.1 模块的兼容性

你在 Windows PowerShell 5.1 中使用的大多数模块都已与 PowerShell 7 兼容，包括 Azure PowerShell 和 Active Directory。 我们将继续与其他团队合作，共同添加对包括 Microsoft Graph、Office 365 在内的更多模块的本机 PowerShell 7 支持。 有关受支持模块的当前列表，请参阅 [PowerShell 7 模块兼容性](/powershell/scripting/whats-new/module-compatibility)。

> [!NOTE]
> 在 Windows 上，我们还向 `Import-Module` 添加了 UseWindowsPowerShell  开关，为使用不兼容模块的用户简化转换到 PowerShell 7 的过程。 若要详细了解此功能，请参阅 [about_Windows_PowerShell_Compatibility](/powershell/module/Microsoft.PowerShell.Core/About/about_windows_powershell_compatibility)。

### <a name="powershell-remoting"></a>PowerShell 远程处理

使用 PowerShell 远程处理，可以在一台或多台远程计算机上运行任何 PowerShell 命令。 你可以建立持久连接、启动交互会话并在远程计算机上运行脚本。

#### <a name="ws-management-remoting"></a>WS-Management 远程处理

Windows PowerShell 5.1 及更低版本使用 WS-Management (WSMAN) 协议进行连接协商和数据传输。 Windows 远程管理 (WinRM) 使用 WSMAN 协议。 如果 WinRM 已启用，PowerShell 7 使用现有 Windows PowerShell 5.1 终结点 `Microsoft.PowerShell` 进行远程连接。 若要将 PowerShell 7 更新为包含自己的终结点，请运行 `Enable-PSRemoting` cmdlet。 若要了解如何连接到特定终结点，请参阅 [PowerShell Core 中的 WS-Management 远程处理](/powershell/scripting/learn/remoting/wsman-remoting-in-powershell-core)

若要使用 Windows PowerShell 远程处理，必须配置远程计算机以进行远程管理。
有关详细信息（包括说明），请参阅[关于远程要求](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)。

若要详细了解如何使用远程处理，请参阅[关于远程](/powershell/module/microsoft.powershell.core/about/about_remote)

#### <a name="ssh-based-remoting"></a>基于 SSH 的远程处理

基于 SSH 的远程处理是在 PowerShell Core 6.x 中引入，以支持其他无法使用 Windows 本机组件（如 WinRM  ）的操作系统。 SSH 远程处理在目标计算机上创建一个 PowerShell 托管进程作为 SSH 子系统。 有关在 Windows 或 Linux 上设置基于 SSH 的远程处理的详细信息和示例，请参阅：[通过 SSH 进行 PowerShell 远程处理](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core)。

> [!NOTE]
> PowerShell 库 (PSGallery) 包含自动配置基于 SSH 的远程处理的模块和 cmdlet。 安装 [PSGallery](https://www.powershellgallery.com/packages/Microsoft.PowerShell.RemotingTools/0.1.0) 中的 `Microsoft.PowerShell.RemotingTools` 模块，然后运行 `Enable-SSH` cmdlet。

`New-PSSession`、`Enter-PSSession` 和 `Invoke-Command` cmdlet 有支持 SSH 连接的新参数集。

```powershell
[-HostName <string>]  [-UserName <string>]  [-KeyFilePath <string>]
```

若要创建远程会话，请使用 HostName  参数指定目标计算机，并通过 UserName  提供用户名。 当以交互方式运行 cmdlet 时，系统会提示输入密码。

```powershell
Enter-PSSession -HostName <Computer> -UserName <Username>
```

或者，在使用 HostName  参数时，提供用户名信息，后跟 @ 符号和计算机名。

```powershell
Enter-PSSession -HostName <Username>@<Computer>
```

还可以使用包含 KeyFilePath  参数的私钥文件来设置 SSH 密钥身份验证。
有关详细信息，请参阅 [OpenSSH 密钥管理](/windows-server/administration/openssh/openssh_keymanagement)。

### <a name="group-policy-supported"></a>已支持组策略

PowerShell 包含组策略设置，有助于为企业环境中的服务器定义一致的选项值。 这些设置包括：

- 控制台会话配置：设置运行 PowerShell 的配置终结点。
- 启用模块日志记录：设置模块的 LogPipelineExecutionDetails 属性。
- 启用 Power Shell 脚本块日志记录：启用所有 PowerShell 脚本的详细日志记录。
- 启用脚本执行：设置 PowerShell 执行策略。
- 启用 PowerShell 脚本：可便于将 PowerShell 命令输入和输出捕获到基于文本的脚本中。
- 设置 Update-Help 的默认源路径：将“可更新的帮助”的源设置为目录，而不是 Internet。

有关详细信息，请参阅 [about_Group_Policy_Settings](/powershell/module/microsoft.powershell.core/about/about_group_policy_settings)。

PowerShell 7 在 `$PSHOME` 中添加组策略模板和安装脚本。

组策略工具使用管理模板文件（`.admx`、`.adml`），以在用户界面中填充策略设置。 这样，管理员就能管理基于注册表的策略设置。 `InstallPSCorePolicyDefinitions.ps1` 脚本在本地计算机上安装 PowerShell Core 管理模板。

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/27/2020 12:38 AM          15861 InstallPSCorePolicyDefinitions.ps1
-a---           2/27/2020 12:28 AM           9675 PowerShellCoreExecutionPolicy.adml
-a---           2/27/2020 12:28 AM           6201 PowerShellCoreExecutionPolicy.admx
```

### <a name="separate-event-logs"></a>独立的事件日志

Windows PowerShell 和 PowerShell 7 记录事件来分隔事件日志。 若要获取 PowerShell 日志列表，请运行以下命令。

```powershell
Get-WinEvent -ListLog *PowerShell*
```

有关详细信息，请参阅 [about_Logging_Windows](/powershell/module/microsoft.powershell.core/about/about_logging_windows)。

## <a name="improved-editing-experience-with-visual-studio-code"></a>提升了使用 Visual Studio Code 的编辑体验

包含 [PowerShell 扩展](https://code.visualstudio.com/docs/languages/powershell)的 [Visual Studio Code (VSCode)](https://code.visualstudio.com/) 是 PowerShell 7 支持的脚本环境。 Windows PowerShell 集成脚本环境 (ISE) 只支持 Windows PowerShell。

更新后的 PowerShell 扩展包括：

- 新增了 ISE 兼容性模式
- 集成控制台中的 PSReadLine，包括语法突出显示、多行编辑和退回搜索
- 提升了稳定性和性能
- 新增了 CodeLens 集成
- 提升了路径自动完成

若要更轻松地转换到 Visual Studio Code，请使用“命令面板”  中的“启用 ISE 模式”  功能。 此功能将 VSCode 切换为 ISE 样式布局。 借助 ISE 样式布局，可以通过熟悉的用户体验来使用 PowerShell 的所有新特性和功能。

若要切换到新 ISE 布局，请按 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> 打开“命令面板”  ，键入“`PowerShell`”，然后选中“PowerShell:  启用 ISE 模式”。

若要将布局设置为原始布局，请打开“命令面板”  ，然后选中“PowerShell:  禁用 ISE 模式(还原为默认值)”。

若要详细了解如何将 VSCode 布局自定义为 ISE，请参阅[如何在 Visual Studio Code 中复制 ISE 体验](/powershell/scripting/components/vscode/how-to-replicate-the-ise-experience-in-vscode)

> [!NOTE]
> 目前还没有使用新功能来更新 ISE 的计划。 ISE 现在是最新版 Windows 10 和 Windows Server 中的用户不可卸载功能。 目前还没有永久删除 ISE 的计划。 PowerShell 团队及其合作伙伴专注于改进用于 Visual Studio Code 的 PowerShell 扩展中的脚本体验。

## <a name="next-steps"></a>后续步骤

掌握了有效迁移的知识，现在就[安装 PowerShell 7](/powershell/scripting/install/installing-powershell-core-on-windows) 吧！
