---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/import-pssession?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-PSSession
ms.openlocfilehash: 2fe48f90b020d0566364f4f24554cb3442880ab5
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197897"
---
# Import-PSSession

## 摘要
将另一个会话中的命令导入当前会话中。

## SYNTAX

```
Import-PSSession [-Prefix <String>] [-DisableNameChecking] [[-CommandName] <String[]>] [-AllowClobber]
 [-ArgumentList <Object[]>] [-CommandType <CommandTypes>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-FormatTypeName] <String[]>]
 [-Certificate <X509Certificate2>] [-Session] <PSSession> [<CommonParameters>]
```

## DESCRIPTION
**Import-module** cmdlet 从本地或远程计算机上的 PSSession 导入到当前会话中的命令，例如 cmdlet、函数和别名。
可以导入 Get-Command cmdlet 可在 PSSession 中找到的任何命令。

使用 **Import-PSSession** 命令来导入命令，这些命令来自自定义 shell（如 Microsoft Exchange Server shell），或者来自包括 Windows PowerShell 模块和管理单元或不在当前会话中的其他元素的会话。

若要导入命令，请先使用 New-PSSession cmdlet 来创建 PSSession。
然后，使用 **Import-PSSession** cmdlet 导入命令。
默认情况下， **Import-PSSession** 导入所有命令，与当前会话中的命令具有相同的名称的命令除外。
若要导入所有命令，请使用 *AllowClobber* 参数。

你可以使用导入的命令，如同你在会话中使用的任何命令一样。
当使用导入的命令时，命令的导入部分将在导出该命令的会话中隐式运行。
但是，远程操作完全由 Windows PowerShell 处理。
你甚至不需要注意它们，只不过必须使与另一个会话 （PSSession) 的连接保持打开状态。
如果关闭该链接，则导入的命令将不再可用。

由于导入的命令可能比本地命令需要更长的运行时间，因此 **Import-PSSession** 将 *AsJob* 参数添加到每个导入的命令中。
此参数使你可以将该命令作为 Windows PowerShell 后台作业运行。
有关详细信息，请参阅 about_Jobs。

当你使用 **Import-PSSession** 时，Windows PowerShell 将导入的命令添加到仅在你的会话中存在的临时模块中，并返回一个表示该模块的对象。
若要创建可在将来的会话中使用的持久性模块，请使用 Export-PSSession cmdlet。

**Import-PSSession** cmdlet 使用 Windows PowerShell 的隐式远程处理功能。
将命令导入到当前会话中时，它们将在原始会话或原始计算机上的类似会话中隐式运行。

从 Windows PowerShell 3.0 开始，可以使用 Import-Module cmdlet 将模块从远程会话导入到当前会话中。
此功能使用隐式远程处理。
它相当于使用 **Import-PSSession** 将选定的模块从远程会话导入到当前会话中。

## 示例

### 示例1：从 PSSession 导入所有命令

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S
```

此命令将所有命令从 Server01 计算机上的 PSSession 导入到当前会话中，与当前会话中的命令具有相同名称的命令除外。

因为此命令不使用 *CommandName* 参数，所以它还会导入已导入命令所需的所有格式设置数据。

### 示例2：导入以特定字符串结尾的命令

```
PS C:\> $S = New-PSSession https://ps.testlabs.com/powershell
PS C:\> Import-PSSession -Session $S -CommandName *-test -FormatTypeName *
PS C:\> New-Test -Name Test1
PS C:\> Get-Test test1 | Run-Test
```

这些命令会将 PSSession 中名称以“-test”结尾的命令导入本地会话，然后显示如何使用导入的 cmdlet。

第一个命令使用 New-PSSession cmdlet 来创建 PSSession。
它将 PSSession 保存在 $S 的变量中。

第二个命令使用 **import-module** cmdlet 将命令从 $S 中的 PSSession 导入到当前会话中。
它使用 *CommandName* 参数指定带有名词 Test 的命令，使用 *FormatTypeName* 参数来导入这些命令的格式设置数据。

第三个和第四个命令使用当前会话中导入的命令。
由于导入的命令实际添加到当前会话中，因此你将使用本地语法来运行它们。
无需使用 Invoke-Command cmdlet 即可运行导入的命令。

### 示例3：从 PSSession 导入 cmdlet

```
PS C:\> $S1 = New-PSSession -ComputerName s1
PS C:\> $S2 = New-PSSession -ComputerName s2
PS C:\> Import-PSSession -Session s1 -Type cmdlet -Name New-Test, Get-Test -FormatTypeName *
PS C:\> Import-PSSession -Session s2 -Type Cmdlet -Name Set-Test -FormatTypeName *
PS C:\> New-Test Test1 | Set-Test -RunType Full
```

此示例演示可以像使用本地 cmdlet 一样使用导入的 cmdlet。

这些命令从 Server01 计算机上的 PSSession 中导入 New-Test 和 Get-Test cmdlet，从 Server02 计算机上的 PSSession 中导入 Set-Test cmdlet。

尽管这些 cmdlet 从不同的 PSSession 中导入，但是可以通过管道将来自一个 cmdlet 的对象无误地传递到另一个 cmdlet。

### 示例4：将导入的命令作为后台作业运行

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Import-PSSession -Session $S -CommandName *-test* -FormatTypeName *
PS C:\> $batch = New-Test -Name Batch -AsJob
PS C:\> Receive-Job $batch
```

此示例演示了如何将导入的命令作为后台作业运行。

由于导入的命令可能比本地命令需要更长的运行时间，因此 **Import-PSSession** 将 *AsJob* 参数添加到每个导入的命令中。
*AsJob* 参数允许你将该命令作为后台作业运行。

第一个命令在 Server01 计算机上创建 PSSession，并将 PSSession 对象保存在 $S 的变量中。

第二个命令使用 **import-module** 将 $S 中的 PSSession 的测试 cmdlet 导入到当前会话中。

第三个命令使用导入的 New-Test cmdlet 的 *AsJob* 参数，将 New-Test 命令作为后台作业运行。
该命令将 New-Test 返回的作业对象保存在 $batch 变量中。

第四个命令使用 Receive-Job cmdlet 获取 $batch 变量中的作业的结果。

### 示例5：从 Windows PowerShell 模块导入 cmdlet 和函数

```
PS C:\> $S = New-PSSession -ComputerName Server01
PS C:\> Invoke-Command -Session $S {Import-Module TestManagement}
PS C:\> Import-PSSession -Session $S -Module TestManagement
```

此示例演示如何将远程计算机上的 Windows PowerShell 模块中的 cmdlet 和函数导入当前会话。

第一个命令在 Server01 计算机上创建 PSSession，并将其保存在 $S 变量中。

第二个命令使用 **调用-command** cmdlet 在 $S 中的 PSSession 中运行 Import-Module 命令。

通常情况下，通过 Windows PowerShell 配置文件中的 **Import-Module** 命令将该模块添加到所有会话中，但配置文件不会在 PSSession 中运行。

第三个命令使用 **import-module** 的 *module* 参数将模块中的 cmdlet 和函数导入到当前会话中。

### 示例6：在临时文件中创建模块

```
PS C:\> Import-PSSession $S -CommandName Get-Date, SearchHelp -FormatTypeName * -AllowClobber

Name              : tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
Path              : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf\tmp_79468106-4e1d-4d90-af97-1154f9317239_
tcw1zunz.ttf.psm1
Description       : Implicit remoting for http://server01.corp.fabrikam.com/wsman
Guid              : 79468106-4e1d-4d90-af97-1154f9317239
Version           : 1.0
ModuleBase        : C:\Users\User01\AppData\Local\Temp\tmp_79468106-4e1d-4d90-af97-1154f9317239_tcw1zunz.ttf
ModuleType        : Script
PrivateData       : {ImplicitRemoting}
AccessMode        : ReadWrite
ExportedAliases   : {}
ExportedCmdlets   : {}
ExportedFunctions : {[Get-Date, Get-Date], [SearchHelp, SearchHelp]}
ExportedVariables : {}
NestedModules     : {}
```

此示例显示 **Import-PSSession** 在磁盘上的临时文件中创建一个模块。
它还显示所有命令在导入当前会话之前都已转换为函数。

该命令使用 **import-module** cmdlet 将 Get-Date Cmdlet 和 SearchHelp 函数导入到当前会话中。

**Import-PSSession** cmdlet 将返回表示临时模块的 **PSModuleInfo** 对象。
**Path** 属性的值显示 **Import-PSSession** 在一个临时位置上创建了脚本模块 (.psm1) 文件。
**ExportedFunctions** 属性显示 **Get-Date** cmdlet 和 SearchHelp 函数都已作为函数导入。

### 示例7：运行由导入的命令隐藏的命令

```
PS C:\> Import-PSSession $S -CommandName Get-Date -FormatTypeName * -AllowClobber

PS C:\> Get-Command Get-Date -All

CommandType   Name       Definition
-----------   ----       ----------
Function      Get-Date   ...
Cmdlet        Get-Date   Get-Date [[-Date] <DateTime>] [-Year <Int32>] [-Month <Int32>]

PS C:\> Get-Date
09074

PS C:\> (Get-Command -Type Cmdlet -Name Get-Date).PSSnapin.Name
Microsoft.PowerShell.Utility

PS C:\> Microsoft.PowerShell.Utility\Get-Date
Sunday, March 15, 2009 2:08:26 PM
```

此示例演示如何运行导入的命令隐藏的命令。

第一个命令从 $S 变量的 PSSession 中导入 Get-Date cmdlet。
因为当前会话包括 **Get-Date** cmdlet，所以在该命令中 *AllowClobber* 参数是必需的。

第二个命令使用 Get-Command cmdlet 的 **all** 参数获取当前会话中的所有 **获取日期** 命令。
输出显示会话包括原始 **Get-Date** cmdlet 和一个 **Get-Date** 函数。
**获取日期** 函数在 $S 的 PSSession 中运行导入的 **获取日期** cmdlet。

第三个命令将运行 **Get-Date** 命令。
由于函数的优先级高于 cmdlet，因此 Windows PowerShell 将运行导入的 **Get-Date** 函数，它会返回一个儒略日期。

第四个和第五个命令显示如何使用限定的名称来运行由导入的命令隐藏的命令。

第四个命令将获取已将原始的 **Get-Date** cmdlet 添加到当前会话的 Windows PowerShell 管理单元的名称。

第五个命令使用 **Get-Date** cmdlet 的管理单元限定的名称来运行 **Get-Date** 命令。

有关命令优先级和隐藏的命令的详细信息，请参阅 about_Command_Precedence。

### 示例8：导入名称中包含特定字符串的命令

```
PS C:\> Import-PSSession -Session $S -CommandName *Item* -AllowClobber
```

此命令从 $S 中的 PSSession 中导入其名称包含项的命令。
由于该命令包含 *CommandName* 参数而不是 *FormatTypeData* 参数，因此只会导入该命令。

当你要在远程计算机上使用 **Import-PSSession** 运行命令，而且已经具有当前会话中的命令的格式设置数据时，请使用此命令。

### 示例9：使用 Module 参数来发现已导入到会话中的命令

```
PS C:\> $M = Import-PSSession -Session $S -CommandName *bits* -FormatTypeName *bits*
PS C:\> Get-Command -Module $M
CommandType     Name
-----------     ----
Function        Add-BitsFile
Function        Complete-BitsTransfer
Function        Get-BitsTransfer
Function        Remove-BitsTransfer
Function        Resume-BitsTransfer
Function        Set-BitsTransfer
Function        Start-BitsTransfer
Function        Suspend-BitsTransfer
```

此命令演示如何使用 **Get-command** 的 *Module* 参数来找出通过 **import-module** 命令导入到会话中的命令。

第一个命令使用 **import-module** cmdlet 从 $S 变量的 PSSession 中导入其名称包含 "bits" 的命令。
**Import-PSSession** 命令将返回一个临时模块并将该模块保存在 $m 变量中。

第二个命令使用 Get-Command cmdlet 获取 $M 变量中的模块导出的命令。

*Module* 参数采用字符串值，这是为模块名称而设计的。
但是，当你提交模块对象时，Windows PowerShell 将对该模块对象使用 **ToString** 方法，然后返回模块名称。

**Get command** 命令等效于 `Get-Command $M.Name` "。

## PARAMETERS

### -AllowClobber
指示此 cmdlet 将导入指定的命令，即使它们与当前会话中的命令具有相同的名称。

如果导入与当前会话中的命令同名的命令，则导入的命令会隐藏或替换原始命令。
有关详细信息，请参阅 about_Command_Precedence。

默认情况下， **Import-PSSession** 不导入与当前会话中的命令具有相同名称的命令。

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

### -ArgumentList
指定通过使用指定参数 (参数值) 导致的命令数组。

例如，若要在 $S 的 PSSession 中导入证书中的 Get-Item 命令的变体 (Cert： ) 驱动器，请键入 `Import-PSSession -Session $S -Command Get-Item -ArgumentList cert:` 。

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificate
指定用于对格式文件 (*.Format.ps1xml) 或 **Import-PSSession** 创建的临时模块中的脚本模块文件 (.psm1) 进行签名的客户端证书。

输入一个包含证书的变量，或可获取该证书的命令或表达式。

若要查找证书，请使用 Get-PfxCertificate cmdlet，或在证书 (Cert： ) 驱动器中使用 Get-ChildItem cmdlet。
如果证书无效或不具有足够的权限，则该命令将失败。

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate2
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandName
指定带有指定名称或名称模式的命令。
允许使用通配符。
使用 *CommandName* 或其 *别名。*

默认情况下， **Import-PSSession** 导入会话中的所有命令，与当前会话中的命令具有相同名称的命令除外。
这样可以防止导入的命令隐藏或替换会话中的命令。
若要导入所有命令，甚至那些隐藏或替换其他命令的命令，请使用 *AllowClobber* 参数。

如果使用 *CommandName* 参数，则不导入这些命令的格式设置文件，除非使用 *FormatTypeName* 参数。
同样，如果使用 *FormatTypeName* 参数，则不导入任何命令，除非使用 *CommandName* 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommandType
指定命令对象的类型。
默认值为 Cmdlet。
使用 *CommandType* 或其别名 *Type* 。
此参数的可接受值为：

- A.
远程会话中的 Windows PowerShell 别名。
- 全部。
远程会话中的 cmdlet 和函数。
- 应用程序。
除远程会话的 Path 环境变量 ($env:path) 中列出的路径中的 Windows PowerShell 文件以外的所有文件，包括 .txt、.exe 和 .dll 文件。
- Cmdlet.
远程会话中的 cmdlet。
默认值为“Cmdlet”。
- ExternalScript.
在远程会话中的 Path 环境变量 ($env:path) 中列出的路径中的 .ps1 文件。
- Filter 和 Function。
远程会话中的 Windows PowerShell 函数。
- 脚本。
远程会话中的脚本块。

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableNameChecking
指示当你导入的 cmdlet 或函数名称包括未经批准的动词或禁止的字符时，此 cmdlet 将禁止显示警告你的消息。

默认情况下，当导入的模块导出名称中包含未经批准的谓词的 cmdlet 或函数时，Windows PowerShell 将显示以下警告消息：

"警告：某些导入的命令名称包括未经批准的动词，这可能会使它们的发现性更小。
请使用 Verbose 参数获取详细信息或者键入 Get-Verb 以查看批准的动词列表。”

此消息只是一个警告。
仍将导入完整的模块，其中包括非一致性的命令。
尽管会向模块用户显示消息，但是模块作者应修复命名问题。

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

### -FormatTypeName
指定指定 Microsoft .NET 框架类型的格式设置说明。
输入类型名称。
允许使用通配符。

此参数的值必须是一个类型的名称，该类型由导出这些命令的会话中的 Get-FormatData 命令返回。
若要获取远程会话中的所有格式数据，请键入 *。

如果此命令不包括 *CommandName* 或 *FormatTypeName* 参数，则将 **导入远程** 会话中 **update-formatdata** 命令返回的所有 .NET Framework 类型的格式说明。

如果使用 *FormatTypeName* 参数，则不导入任何命令，除非使用 *CommandName* 参数。

同样，如果使用 *CommandName* 参数，则不导入这些命令的格式设置文件，除非使用 *FormatTypeName* 参数。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullyQualifiedModule
指定名称以 **ModuleSpecification** 对象的形式指定的模块 (在 MSDN) library 中的 [ModuleSpecification 构造函数 (哈希表)](https://msdn.microsoft.com/library/jj136290) 的 "备注" 部分中进行说明。
例如， *FullyQualifiedModule* 参数接受以 @ {ModuleName = "ModuleName" 格式指定的模块名称;ModuleVersion = "version_number"} 或 @ {ModuleName = "ModuleName";ModuleVersion = "version_number";Guid = "GUID"}。
**ModuleName** 和 **ModuleVersion** 是必需的，但 **Guid** 是可选的。

不能在与 *Module* 参数相同的命令中指定 *FullyQualifiedModule* 参数;这两个参数是互斥的。

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Module
指定 Windows PowerShell 管理单元和模块中的命令的数组。
输入管理单元和模块的名称。
不允许使用通配符。

**Import-PSSession** 无法从管理单元导入提供程序。

有关详细信息，请参阅 about_PSSnapins 和 [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prefix
为导入的命令的名称中的名词指定前缀。

使用此参数可避免会话中的不同命令具有相同名称时可能出现的名称冲突。

例如，如果你指定前缀 "远程"，然后导入 Get-Date cmdlet，则该 cmdlet 在会话中是 RemoteDate 的，并且不会与原始的 **获取日期** cmdlet 混淆。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Session
指定从中导入 cmdlet 的 **PSSession** 。
输入包含会话对象的变量或获取会话对象的命令，如 New-PSSession 或 Get-PSSession 命令。
仅可以指定一个会话。
此参数是必需的。

```yaml
Type: System.Management.Automation.Runspaces.PSSession
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无
不能通过管道将对象传递给此 cmdlet。

## 输出

### System.Management.Automation.PSModuleInfo
**Import-module** 返回 New-Module 和 Get-Module cmdlet 返回的相同模块对象。
但是，导入的模块是临时的并且仅在当前会话中存在。
若要在磁盘上创建永久模块，请使用 Export-PSSession cmdlet。

## 注释

* **Import-module** 依赖于 Windows PowerShell 远程处理基础结构。 若要使用此 cmdlet，必须为 WS-Management 远程处理配置计算机。 有关详细信息，请参阅 about_Remote 和 about_Remote_Requirements。
* **Import-module** 不会导入变量或 Windows PowerShell 提供程序。
* 当你导入与当前会话中的命令具有相同名称的命令时，导入的命令可以隐藏会话中的别名、函数和 cmdlet，并且可以替换会话中的函数和变量。 若要防止名称冲突，请使用 *Prefix* 参数。 有关详细信息，请参阅 about_Command_Precedence。
* **Import-module** 在导入前将所有命令转换为函数。 这样，导入的命令的行为与保留其原始命令类型时的行为稍有不同。 例如，如果从 PSSession 中导入一个 cmdlet，然后从模块或管理单元中导入具有相同名称的 cmdlet，则从 PSSession 中导入的 cmdlet 默认始终运行，因为函数优先于 cmdlet。 相反，如果将别名导入到具有相同名称的别名的会话，则始终使用原来的别名，因为别名优先于函数。 有关详细信息，请参阅 about_Command_Precedence。
* **Import-module** 使用 Write-Progress cmdlet 来显示该命令的进度。 该命令正在运行时，你可能会看到进度条。
* 为了查找要导入的命令， **import-module** 使用 Invoke-Command Cmdlet 在 PSSession 中运行 Get-Command 命令。 若要获取命令的格式设置数据，请使用 Get-FormatData cmdlet。 运行 **import-module** 命令时，可能会看到来自这些 cmdlet 的错误消息。 此外， **import-module** 不能从不包含 get 命令、Update-formatdata、Select-Object 和 Get-Help Cmdlet 的 PSSession 中导入命令。
* 导入的命令与其他远程命令具有相同的限制，包括无法通过用户界面（如“记事本”）启动程序。
* 由于 Windows PowerShell 配置文件不在 Pssession 中运行，因此将配置文件添加到会话的命令对 **Import-PSSession** 不可用。 若要从配置文件中导入命令，请使用 Invoke-Command 命令，以在导入命令之前，在 PSSession 中手动运行该配置文件。
* **Import-PSSession** 创建的临时模块可能包括格式设置文件，即使该命令不导入格式设置数据也是如此。 如果该命令不导入格式数据，则创建的任何格式设置文件都不包含格式数据。
* 若要使用 **Import-PSSession** ，当前会话中的执行策略不能为 Restricted 或 AllSigned，因为 **Import-PSSession** 创建的临时模块包含这些策略禁止的未签名脚本文件。 若要在不更改本地计算机的执行策略的情况下使用 **import-module** ，请使用 Set-ExecutionPolicy 的 *作用域* 参数为单个进程设置限制性较低的执行策略。
* 在 Windows PowerShell 2.0 中，从另一个会话中导入的命令的帮助主题不包括通过使用 *Prefix* 参数分配的前缀。 若要获得 Windows PowerShell 2.0 中导入命令的帮助，请使用原始（无前缀）的命令名称。

## 相关链接

[Export-PSSession](Export-PSSession.md)
