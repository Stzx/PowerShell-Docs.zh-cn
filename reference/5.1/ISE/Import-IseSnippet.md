---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/import-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IseSnippet
ms.openlocfilehash: 810be675fc593f665ccc6f3d5b86ac2f6b633863
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197526"
---
# Import-IseSnippet

## 摘要
将 ISE 代码段导入到当前会话中

## SYNTAX

### FromFolder（默认值）

```
Import-IseSnippet [-Path] <String> [-Recurse] [<CommonParameters>]
```

### FromModule

```
Import-IseSnippet [-Recurse] -Module <String> [-ListAvailable] [<CommonParameters>]
```

## DESCRIPTION

该 `Import-IseSnippet` cmdlet 将可重用文本 "代码段" 从模块或目录导入到当前会话中。 代码段将立即可供在 Windows PowerShell ISE 中使用。 此 cmdlet 仅适用于 (ISE) 的 Windows PowerShell 集成脚本环境。

若要查看和使用导入的代码段，请从 Windows PowerShell ISE **编辑** "菜单中，单击" **启动代码段** "或按 <kbd>Ctrl</kbd> + <kbd>J</kbd>。

导入的代码段仅在当前会话中可用。 若要将代码段导入到所有 Windows PowerShell ISE 的会话中，请将 `Import-IseSnippet` 命令添加到 Windows PowerShell 配置文件中，或将代码段文件复制到本地代码段目录 `$home\Documents\WindowsPowershell\Snippets` 。

若要导入代码段，必须在 Windows PowerShell ISE 代码段的代码段 XML 中正确设置代码段格式，并将其保存在 Snippet.ps1xml 文件中。 若要创建符合条件的代码段，请使用 `New-IseSnippet` cmdlet。 `New-IseSnippet``<SnippetTitle>.Snippets.ps1xml`在目录中创建文件 `$home\Documents\WindowsPowerShell\Snippets` 。 你可以将代码段移动或复制到 Windows PowerShell 模块的 Snippets 目录或任何其他目录。

`Get-IseSnippet`Cmdlet 可在本地代码段目录中获取用户创建的代码段，而不会获取导入的代码段。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：从目录中导入代码段

此示例将代码段从目录导入 `\\Server01\Public\Snippets` 到当前会话中。 它使用 **递归** 参数从代码段目录的所有子目录中获取代码片段。

```powershell
Import-IseSnippet -Path \\Server01\Public\Snippets -Recurse
```

### 示例 2：从模块中导入代码段

此示例从 **SnippetModule** 模块导入代码段。 该命令使用 **ListAvailable** 参数导入代码段，即使 **SnippetModule** 模块在命令运行时未导入到用户会话中也是如此。

```powershell
Import-IseSnippet -Module SnippetModule -ListAvailable
```

### 示例 3：查找模块中的代码段

此示例将获取 PSModulePath 环境变量中所有已安装模块中的代码段。

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$_.fullname}
```

### 示例 4：导入所有模块代码段

此示例将所有已安装模块中的所有代码段导入到当前会话中。 通常，不需要运行如下所示的命令，因为在导入模块时，具有代码段的模块将使用 `Import-IseSnippet` cmdlet 导入这些模块。

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    ForEach-Object {$psise.CurrentPowerShellTab.Snippets.Load($_)}
```

### 示例 5：复制所有模块代码段

此示例将所有已安装模块中的代码段文件复制到当前用户的代码段目录。 与仅影响当前会话的导入的代码段不同，复制的代码段在每个 Windows PowerShell ISE 会话中都可用。

```powershell
($env:PSModulePath).split(";") |
  ForEach-Object {dir $_\*\Snippets\*.Snippets.ps1xml -ErrorAction SilentlyContinue} |
    Copy-Item -Destination $home\Documents\WindowsPowerShell\Snippets
```

## PARAMETERS

### -ListAvailable

指示此 cmdlet 从安装在计算机上的模块中获取代码段，即使这些模块未导入到当前会话中也是如此。 如果省略此参数，且 **module** 参数指定的模块未导入到当前会话中，则从该模块获取代码段的尝试将失败。

仅当命令中使用了 **Module** 参数时，此参数才有效。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromModule
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Module

将代码段从指定的模块导入到当前会话中。 不支持通配符。

此参数从模块路径的代码段子目录中 Snippet.ps1xml 文件导入代码段，如 `$home\Documents\WindowsPowerShell\Modules\<ModuleName>\Snippets` 。

此参数旨在供模块作者在启动脚本中使用，例如在模块清单的 **ScriptsToProcess** 项中指定的脚本。 模块中的代码段不会随模块一起自动导入，但你可以使用 `Import-IseSnippet` 命令导入它们。

```yaml
Type: System.String
Parameter Sets: FromModule
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path

指定此 cmdlet 在其中导入代码段的代码段目录的路径。

```yaml
Type: System.String
Parameter Sets: FromFolder
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Recurse

指示此 cmdlet 从 **Path** 参数的值的所有子目录中导入代码段。

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

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

此 cmdlet 不通过管道接受输入。

## 输出

### 无

此 cmdlet 将不产生输出。

## 注释

- 不能使用 `Get-IseSnippet` cmdlet 来获取导入的代码段。 `Get-IseSnippet` 仅获取目录中的代码段 `$home\Documents\WindowsPowerShell\Snippets` 。
- `Import-IseSnippet`使用 " **ISESnippetCollection** " 对象的 **Load** 静态方法。 您还可以在 Windows PowerShell ISE 对象模型中使用代码段的 **Load** 方法： `$psISE.CurrentPowerShellTab.Snippets.Load()`
- `New-IseSnippet`Cmdlet 将新的用户创建的代码段存储在 types.ps1xml 文件中。 因此，Windows PowerShell 无法将其加载到执行策略为 **AllSigned** 或 **Restricted** 的会话中。 在 **Restricted** 或 **AllSigned** 会话中，你可以创建、获取和导入用户创建的未签名代码段，但无法在会话中使用它们。

  若要使用 cmdlet 返回的未签名用户创建的代码段 `Import-IseSnippet` ，请更改执行策略，然后重新启动 Windows PowerShell ISE。

  有关 Windows PowerShell 执行策略的详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)。

## 相关链接

[Get-IseSnippet](Get-IseSnippet.md)

[New-IseSnippet](New-IseSnippet.md)
