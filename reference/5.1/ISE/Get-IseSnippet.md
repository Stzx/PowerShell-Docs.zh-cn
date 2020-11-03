---
external help file: ISE-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: ISE
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/ise/get-isesnippet?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IseSnippet
ms.openlocfilehash: c43dae3f178ae778d78fe3718fa85fd2635eba86
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "93198956"
---
# Get-IseSnippet

## 摘要
获取用户创建的代码段。

## SYNTAX

```
Get-IseSnippet [<CommonParameters>]
```

## DESCRIPTION

该 `Get-IseSnippet` cmdlet 将获取包含用户创建的可重用文本代码段的 types.ps1xml 文件。 它只能在 Windows PowerShell 集成脚本环境 (ISE) 中正常运行。

使用 `New-IseSnippet` cmdlet 创建代码段时，将 `New-IseSnippet` `<SnippetTitle>.Snippets.ps1xml` 在目录中创建一个文件 `$home\Documents\WindowsPowerShell\Snippets` 。
`Get-IseSnippet` 获取代码段目录中的代码段文件。

此 cmdlet 不会获取内置代码段或通过 cmdlet 从模块导入的代码段 `Import-IseSnippet` 。

此 cmdlet 是在 Windows PowerShell 3.0 中引入的。

## 示例

### 示例 1：获取所有用户定义的代码段

此示例获取代码段目录中所有用户定义的代码段。

```powershell
Get-IseSnippet
```

### 示例 2：将所有用户定义的代码段从远程计算机复制到共享目录

此示例将用户创建的所有代码段从一组远程计算机复制到共享的代码段目录。

```powershell
Invoke-Command -Computer (Get-Content Servers.txt) {Get-IseSnippet | Copy-Item -Destination \\Server01\Share01\Snippets}
```

`Invoke-Command` 在 `Get-IseSnippet` 文件中的计算机上运行 `Servers.txt` 。 管道运算符 (`|`) 将代码段文件发送到 `Copy-Item` cmdlet，这会将这些文件复制到由 **Destination** 参数指定的目录中。

### 示例 3：在本地计算机上显示每个代码段的标题和文本

此示例使用 `Get-IseSnippet` 和 `Select-Xml` cmdlet 在本地计算机上显示每个代码段的标题和文本。

```powershell
#Parse-Snippet Function
function Parse-Snippet {
  $SnippetFiles = Get-IseSnippet
  $SnippetNamespace = @{x="http://schemas.microsoft.com/PowerShell/Snippets"}
  foreach ($SnippetFile in $SnippetFiles) {
     Write-Host ""
     $Title = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Title" |
       ForEach-Object {$_.Node.InnerXML}
     $Text = Select-Xml -Path $SnippetFile.FullName -Namespace $SnippetNamespace -XPath "//x:Script" |
       ForEach-Object {$_.Node.InnerText}
     Write-Host "Title: $Title"
     Write-Host "Text: $Text"
   }
}
```

```Output
Title: Mandatory
Text:
Param
(
  [parameter(Mandatory=True)]
  [String[]]
  $<ParameterName>
)

Title: Copyright
Text:  (c) Fabrikam, Inc. 2012
```

### 示例 4：在会话中显示所有代码段的标题和说明

此示例显示会话中所有代码段的标题和说明，其中包括内置代码段、用户定义的代码段和导入的代码段。

```powershell
$PSISE.CurrentPowerShellTab.Snippets | Format-Table DisplayTitle, Description
```

`$PSISE`变量表示 Windows PowerShell ISE 主机程序。 该变量的 **psise.currentpowershelltab** 属性 `$PSISE` 表示当前会话。 **Snippets** 属性表示当前会话中的代码段。

`$PSISE.CurrentPowerShellTab.Snippets`命令返回一个表示代码段的 **new-isesnippet** 对象，这与 `Get-IseSnippet` cmdlet 不同。 `Get-IseSnippet` 返回表示代码段文件 () 的文件对象。

Cmdlet 将在 `Format-Table` 表中显示代码段的 **DisplayTitle** 和 **Description** 属性。

## PARAMETERS

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

## 输出

### System.IO.FileInfo

此 cmdlet 返回表示代码段文件的文件对象。

## 注释

* `New-IseSnippet`Cmdlet 将新的用户创建的代码段存储在 types.ps1xml 文件中。 因此，Windows PowerShell 无法将其添加到执行策略为 **AllSigned** 或 **Restricted** 的会话中。 在 **Restricted** 或 **AllSigned** 会话中，你可以创建、获取和导入用户创建的未签名代码段，但无法在会话中使用它们。

  若要使用 cmdlet 返回的未签名用户创建的代码段 `Get-IseSnippet` ，请更改执行策略，然后重新启动 Windows PowerShell ISE。

  有关 Windows PowerShell 执行策略的详细信息，请参阅 [about_Execution_Policies](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)。

## 相关链接

[New-IseSnippet](New-IseSnippet.md)

[Import-IseSnippet](Import-IseSnippet.md)
