---
ms.date: 09/12/2016
ms.topic: reference
title: 命名帮助文件
description: 命名帮助文件
ms.openlocfilehash: b77af8f9b9510785a4198fed9da1263184a27b99
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667583"
---
# <a name="naming-help-files"></a>命名帮助文件

本主题说明如何命名基于 XML 的帮助文件，以便 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet 可以找到它。 每个命令类型的名称要求不同。

## <a name="cmdlet-help-files"></a>Cmdlet 帮助文件

必须为在其中定义 cmdlet 的程序集命名 c # cmdlet 的帮助文件。 使用以下文件名格式：

```
<AssemblyName>.dll-help.xml
```

程序集名称格式是必需的，即使程序集是嵌套模块也是如此。

例如， [get-winevent](/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent) cmdlet 是在 Microsoft.PowerShell.Diagnostics.dll 程序集中定义的。 此 `Get-Help` cmdlet `Get-WinEvent` 仅在模块目录的文件中查找有关该 cmdlet 的帮助主题 `Microsoft.PowerShell.Diagnostics.dll-help.xml` 。

## <a name="provider-help-files"></a>提供程序帮助文件

对于在其中定义提供程序的程序集，必须为 PowerShell 提供程序的帮助文件命名。 使用以下文件名格式：

`<AssemblyName>.dll-help.xml`

程序集名称格式是必需的，即使程序集是嵌套模块也是如此。

例如，证书提供程序是在 `Microsoft.PowerShell.Security.dll` 程序集中定义的。 此 `Get-Help` cmdlet 仅在模块目录的文件中查找证书提供程序的帮助主题 `Microsoft.PowerShell.Security.dll-help.xml` 。

## <a name="function-help-files"></a>函数帮助文件

可以通过使用 [基于注释的帮助](/powershell/module/microsoft.powershell.core/about/about_comment_based_help) 或 XML 帮助文件中介绍的方式记录函数。 在 XML 文件中记录函数时，该函数必须有一个 `.ExternalHelp` comment 关键字，该关键字将函数与 XML 文件相关联。 否则，此 `Get-Help` cmdlet 将无法找到帮助文件。

函数帮助文件的名称没有技术要求。 但是，最佳做法是为定义该函数的脚本模块命名帮助文件。 例如，以下函数是在文件中定义的 `MyModule.psm1` 。

```csharp
#.ExternalHelp MyModule.psm1-help.xml
function Test-Function { ... }
```

## <a name="cim-command-help-files"></a>CIM 命令帮助文件

CIM 命令的帮助文件必须为在其中定义 CIM 命令的 CDXML 文件命名。 使用以下文件名格式：

`<FileName>.cdxml-help.xml`

CIM 命令在 CDXML 文件中定义，这些文件可以作为嵌套模块包含在模块中。 如果将 CIM 命令作为函数导入到会话中，则 PowerShell 会将 `.ExternalHelp` comment 关键字添加到函数定义中，该函数将函数与为其定义 CIM 命令的 CDXML 文件命名的 XML 帮助文件相关联。

## <a name="script-workflow-help-files"></a>脚本工作流帮助文件

可在基于 XML 的帮助文件中记录模块中包含的脚本工作流。 帮助文件的名称没有技术要求。 但是，最佳做法是将定义脚本工作流的脚本模块的帮助文件命名为。 例如：

`<ScriptModule>.psm1-help.xml`

与其他脚本化命令不同，脚本工作流不需要 `.ExternalHelp` 使用 comment 关键字将它们与帮助文件相关联。 相反，PowerShell 会在特定于 XML 的帮助文件的模块目录的 UI 区域性特定子目录中搜索，并在所有文件中查找脚本工作流的帮助。 `.ExternalHelp` comment 关键字被忽略。

由于 `.ExternalHelp` 忽略了 comment 关键字，因此， `Get-Help` 仅当模块中包含脚本工作流时，cmdlet 才能找到这些脚本工作流的帮助。
