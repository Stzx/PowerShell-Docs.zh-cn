---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/new-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-IseSnippet
ms.openlocfilehash: 0ed1c2913fc7531574bfbdd435a002d60931d24a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197525"
---
# New-IseSnippet

## 摘要
创建 Windows PowerShell ISE 代码段。

## SYNTAX

```
New-IseSnippet [-Title] <String> [-Description] <String> [-Text] <String> [-Author <String>]
 [-CaretOffset <Int32>] [-Force] [<CommonParameters>]
```

## DESCRIPTION

`New-ISESnippet`Cmdlet 可为 Windows PowerShell ISE 创建可重用文本 "代码段"。 你可以使用代码段将文本添加到 Windows PowerShell ISE 中的“脚本”窗格或“命令”窗格。 此 cmdlet 仅在 Windows PowerShell ISE 中可用。

从 Windows PowerShell 3.0 开始，Windows PowerShell ISE 包括内置代码段集合。 `New-ISESnippet`Cmdlet 可让你创建自己的代码段以添加到内置集合。 你可以查看、更改、添加、删除和共享代码段文件，并将其包含在 Windows PowerShell 模块中。 若要查看 Windows PowerShell ISE 中的代码段，请在 " **编辑** " 菜单中选择 " **启动代码段** " 或按 <kbd>CTRL</kbd> + <kbd>J</kbd>。

`New-ISESnippet`Cmdlet `<Title>.Snippets.ps1xml` 在目录中创建一个文件，该文件 `$home\Documents\WindowsPowerShell\Snippets` 具有你指定的标题。 若要将代码段文件包含在你创作的模块中，请将代码段文件添加到模块目录的代码段子目录。

不能在执行策略受到 **限制** 或 **AllSigned** 的会话中使用用户创建的代码段。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例1：创建 Comment-Based 帮助代码段

```
New-IseSnippet -Title Comment-BasedHelp -Description "A template for comment-based help." -Text "<#
    .SYNOPSIS

    .DESCRIPTION
    .PARAMETER  <Parameter-Name>
    .INPUTS
    .OUTPUTS
    .EXAMPLE
    .LINK
#>"
```

此命令将为 Windows PowerShell ISE 创建一个 Comment-BasedHelp 代码段。 它 `Comment-BasedHelp.snippets.ps1xml` 在用户的代码段目录中创建名为的文件 `$home\Documents\WindowsPowerShell\Snippets` 。

### 示例2：创建必需的代码段

```
$M = @'
Param
(
  [parameter(Mandatory=$true)]
  [String[]]
  $<ParameterName>
)
'@

New-ISESnippet -Text $M -Title Mandatory -Description "Adds a mandatory function parameter." -Author "Patti Fuller, Fabrikam Corp." -Force
```

此示例将创建一个名为 " **强制** " Windows PowerShell ISE 的代码段。 第一个命令将代码段文本保存在 `$M` 变量中。 第二个命令使用 `New-ISESnippet` cmdlet 创建代码片段。 该命令使用 **Force** 参数来采用相同名称重写上一个代码段。

### 示例3：将必需的代码片段从文件夹复制到目标文件夹

```
Copy-Item "$Home\Documents\WindowsPowerShell\Snippets\Mandatory.Snippets.ps1xml" -Destination "\\Server\Share"
```

此命令使用 `Copy-Item` cmdlet 从文件夹中将 **强制** 代码段复制 `New-ISESnippet` 到 Server\Share 文件共享。

## PARAMETERS

### -作者

指定代码段的作者。 作者字段将显示在代码段文件中，但当你在 Windows PowerShell ISE 中单击代码段名称时，不会显示该字段。

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

### -CaretOffset

指定此 cmdlet 将光标置于其上的代码段文本的字符。 输入一个表示光标位置的整数，其中“1”表示文本的第一个字符。 默认值 0（零）将光标紧接在文本的第一个字符之前。 此参数不会缩进代码段文本。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description

指定代码段的说明。 当你在 Windows PowerShell ISE 中单击代码段名称时，将显示说明值。 此参数是必需的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

指示此 cmdlet 将覆盖同一位置中具有相同名称的代码段文件。 默认情况下，不 `New-ISESnippet` 会覆盖文件。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -文本

指定在选择代码段时添加的文本值。 当你在 Windows PowerShell ISE 中单击代码段名称时，将显示代码段文本。 此参数是必需的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title

指定代码段的标题或名称。 标题还可命名代码段文件。 此参数是必需的。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

此 cmdlet 将不生成任何输出。

## 注释

`New-IseSnippet` 在 types.ps1xml 文件中存储新的用户创建的代码段。 因此，Windows PowerShell 无法将其添加到执行策略为 **AllSigned** 或 **Restricted** 的会话中。 在 **Restricted** 或 **AllSigned** 会话中，你可以创建、获取和导入用户创建的未签名代码段，但无法在会话中使用它们。

如果 `New-IseSnippet` 在 **受限** 或 **AllSigned** 会话中使用 cmdlet，则会创建代码段，但当 Windows PowerShell 尝试将新创建的代码段添加到会话时，将显示一条错误消息。 若要使用新代码段（以及用户创建的其他未签名代码段），请更改执行策略，然后重新启动 Windows PowerShell ISE。

有关 Windows PowerShell 执行策略的详细信息，请参阅 about_Execution_Policies。

- 若要更改代码段，请编辑代码段文件。 可以在 Windows PowerShell ISE 的脚本窗格中编辑代码段文件。
- 若要删除已添加的代码段，请删除该代码段文件。
- 不能删除内置代码段，但可以使用 "$psise 隐藏所有内置代码段。ShowDefaultSnippets = $false "命令。
- 你可以创建与内置代码段同名的代码段。 这两个代码段均显示在 Windows PowerShell ISE 的代码段菜单中。

## 相关链接

[Get-IseSnippet](Get-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
