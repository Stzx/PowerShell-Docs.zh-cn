---
ms.date: 09/13/2016
ms.topic: reference
title: 安装 PowerShell 模块
description: 安装 PowerShell 模块
ms.openlocfilehash: 3c7a4413168934ca4de1912c9615a6ae0fc45788
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645332"
---
# <a name="installing-a-powershell-module"></a>安装 PowerShell 模块

创建 PowerShell 模块后，你可能需要在系统上安装该模块，以便你或其他人可以使用它。 一般而言，此过程包括将模块文件（即 .psm1 或二进制程序集、模块清单和任何其他相关文件）复制到该计算机的目录中。 对于非常小的项目，此过程很简单，只需要使用 Windows 资源管理器将文件复制并粘贴到单台远程计算机上即可。但是，对于较大的解决方案，你可能需要使用更复杂的安装过程。 无论模块通过何种方式进入系统，PowerShell 都可以通过多种技术使用户能够找到和使用这些模块。 因此，主要的安装问题是确保 PowerShell 能够找到模块。 有关其他信息，请参阅[导入 PowerShell 模块](./importing-a-powershell-module.md)。

## <a name="rules-for-installing-modules"></a>模块安装规则

以下信息适用于所有模块，包括为供自己使用而创建的模块、从其他方获取的模块以及分发给其他人的模块。

### <a name="install-modules-in-psmodulepath"></a>将模块安装在 PSModulePath 中

尽可能将所有模块安装在 PSModulePath 环境变量中列出的路径中，也可以将模块路径添加到 PSModulePath 环境变量值中。

PSModulePath 环境变量 ($Env:PSModulePath) 包含 Windows PowerShell 模块的位置。 Cmdlet 根据此环境变量的值来查找模块。

默认情况下，PSModulePath 环境变量值包含以下系统和用户模块目录，但你可以对此值进行添加和编辑。

- `$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > 此位置专门用于 Windows 附带的模块。 请勿将模块安装到此位置。

- `$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)

- `$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)

  若要获取 PSModulePath 环境变量的值，请使用以下命令之一。

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  若要将模块路径添加到 PSModulePath 环境变量值的值中，请使用以下命令格式。 此格式使用 System.Environment 类的 SetEnvironmentVariable 方法来对 PSModulePath 环境变量执行独立会话更改。

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > 将路径添加到 PSModulePath 后，应广播关于此更改的环境消息。 广播更改后，其他应用程序（如 Shell）将可以获得更改。 若要广播更改，请将 `lParam` 设置为字符串“Environment”并让你的产品安装代码发送“WM_SETTINGCHANGE”消息。 请确保在模块安装代码更新 PSModulePath 后发送此消息。

### <a name="use-the-correct-module-directory-name"></a>使用正确的模块目录名称

格式正确的模块是指存储在目录中并且其名称与模块目录中至少一个文件的基名称相同的模块。 如果模块的格式不正确，Windows PowerShell 将无法将它识别为模块。

文件的“基名称”是不带文件扩展名的名称。 在格式正确的模块中，包含模块文件的目录的名称必须与模块中至少一个文件的基名称匹配。

例如，在示例 Fabrikam 模块中，包含模块文件的目录名称为“Fabrikam”，并且至少有一个文件的基名称为“Fabrikam”。 在此示例中，Fabrikam.psd1 和 Fabrikam.dll 的基名称都为“Fabrikam”。

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>安装错误的影响

如果模块的格式不正确，并且其位置未包含在 PSModulePath 环境变量的值中，则 Windows PowerShell 的基本发现功能（如以下功能）将无法正常运行。

- 模块自动加载功能无法自动导入模块。

- [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 的 `ListAvailable` 参数找不到模块。

- [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet 找不到模块。 若要导入模块，必须提供根模块文件或模块清单文件的完整路径。

  除非将模块导入到会话中，否则其他功能（如以下功能）将无法正常运行。 在 PSModulePath 环境变量中格式正确的模块中，即使模块未导入到会话中，这些功能也可正常运行。

- [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet 无法找到模块中的命令。

- [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) 和 [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 无法更新或保存模块的帮助功能。

- [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet 无法找到并显示模块中的命令。

  Windows PowerShell 集成脚本环境 (ISE) 中的 `Show-Command` 窗口缺少模块中的命令。

## <a name="where-to-install-modules"></a>模块的安装位置

本部分介绍安装 Windows PowerShell 模块的文件系统位置。 位置取决于模块的使用方式。

### <a name="installing-modules-for-a-specific-user"></a>为特定用户安装模块

如果是创建自己的模块或从另一方（如 Windows PowerShell 社区网站）获取模块，并且希望只有你的用户帐户可以获取模块，则将模块安装在特定用户的模块目录中。

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

默认情况下，特定用户的模块目录将添加到 PSModulePath 环境变量的值中。

### <a name="installing-modules-for-all-users-in-program-files"></a>将面向所有人的模块安装在程序文件中

如果希望计算机上的所有用户帐户都可获取模块，请将模块安装在程序文件位置中。

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> 默认情况下，Windows PowerShell 4.0 和更高版本会将程序文件位置添加到 PSModulePath 环境变量的值中。 对于 Windows PowerShell 的早期版本，可以手动创建程序文件位置 (%ProgramFiles%\WindowsPowerShell\Modules)，并按照前文所述方法将此路径添加到 PSModulePath 环境变量中。

### <a name="installing-modules-in-a-product-directory"></a>将模块安装在产品目录中

如果要将模块分发给其他方，请使用上面所述的默认程序文件位置，或在 %ProgramFiles% 目录下创建自己的特定于公司或特定于产品的子目录。

例如，Fabrikam Technologies（虚拟的公司）正在交付其 Fabrikam Manager 产品的 Windows PowerShell 模块。 它们的模块安装程序会在 Fabrikam Manager 产品子目录中创建模块子目录。

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Fabrikam 模块安装程序会将此模块位置添加到 PSModulePath 环境变量中，以便 Windows PowerShell 模块发现功能能够找到 Fabrikam 模块。

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>将模块安装在公共文件目录中

如果某个产品的多个组件或某个产品的多个版本会使用模块，则将模块安装在 %ProgramFiles%\Common Files\Modules 子目录下特定模块的子目录中。

在下面的示例中，Fabrikam 模块安装在 `%ProgramFiles%\Common Files\Modules` 子目录的 Fabrikam 子目录中。 请注意，每个模块都位于模块子目录下各自的子目录中。

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

然后，安装程序将确保 PSModulePath 环境变量的值包含公共文件模块子目录的路径。

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a>安装模块的多个版本

若要安装同一模块的多个版本，请使用以下过程。

1. 为模块的每个版本创建一个目录。 将版本号包含在目录名称中。
2. 为模块的每个版本创建一个模块清单。 在清单的 ModuleVersion 键的值中，输入模块版本号。 将清单文件 (.psd1) 保存在模块的特定版本的目录中。
3. 将模块根文件夹路径添加到 PSModulePath 环境变量的值中，如下面的示例中所示。

若要导入模块的特定版本，最终用户可以使用 [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet 的 `MinimumVersion` 或 `RequiredVersion` 参数。

例如，如果可从版本 8.0 和 9.0 中获取 Fabrikam 模块，则 Fabrikam 模块目录结构可能如下所示。

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

安装程序会将这两个模块路径添加到 PSModulePath 环境变量值中。

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

完成这些步骤后， [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 的 **ListAvailable** 参数将获取这两个 Fabrikam 模块。 若要导入特定模块，则使用 [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet 的 `MinimumVersion` 或 `RequiredVersion` 参数。

如果两个模块都导入到了同一会话中，并且两个模块都包含相同名称的 cmdlet，则最后导入的 cmdlet 将在会话中生效。

## <a name="handling-command-name-conflicts"></a>处理命令名称冲突

当模块导出的命令与用户会话中的命令具有相同名称时，可能会发生命令名称冲突。

当会话包含两个具有相同名称的命令时，Windows PowerShell 将运行优先的命令类型。 当会话包含两个具有相同名称和相同类型的命令时，Windows PowerShell 将运行最近添加到会话中的命令。 若要运行默认情况下不会运行的命令，用户可以使用模块名称限定此命令名称。

例如，如果会话包含 `Get-Date` 函数和 `Get-Date` cmdlet，默认情况下 Windows PowerShell 会运行函数。 若要运行 cmdlet，请在命令前面加上模块名称，例如：

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

若要防止名称冲突，模块作者可以使用模块清单中的 DefaultCommandPrefix 键为从该模块导出的所有命令指定名词前缀。

用户可以利用 `Import-Module` cmdlet 的 Prefix 参数来使用替代前缀。 Prefix 参数的值优先于 DefaultCommandPrefix 键的值。

## <a name="see-also"></a>另请参阅

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[编写 Windows PowerShell 模块](./writing-a-windows-powershell-module.md)
