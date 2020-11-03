---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2020
ms.locfileid: "93199304"
---
# Get-Verb

## 摘要
获取已批准的 PowerShell 谓词。

## SYNTAX

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-Verb`函数获取已批准在 PowerShell 命令中使用的谓词。

PowerShell 建议 cmdlet 和函数名称采用 Verb-Noun 格式，并包含已批准的谓词。 这种做法使命令名称更一致、可预测且更易于使用。

使用未经批准的谓词的命令在 PowerShell 中运行。 但是，当导入的模块的名称中包含未批准的谓词的命令时，该 `Import-Module` 命令将显示一条警告消息。

> [!NOTE]
> 返回的谓词列表 `Get-Verb` 可能不完整。 有关包含说明的已批准 PowerShell 动词的更新列表，请参阅 Microsoft Docs 中的 [批准的动词](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) 。

## 示例

### 示例 1-获取所有谓词的列表

```powershell
Get-Verb
```

### 示例 2-获取以 "un" 开头的已批准谓词的列表

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### 示例 3-获取安全组中所有已批准的谓词

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
```

### 示例 4-查找模块中具有未经批准的谓词的所有命令

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## PARAMETERS

### -verb

仅获取指定的谓词。
输入谓词的名称或名称模式。
允许使用通配符。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## 输入

### 无

## 输出

### Selected.Microsoft.PowerShell.Commands.MemberDefinition

## 注释

`Get-Verb` 返回 MemberDefinition 对象的已修改版本。
该对象不具有 MemberDefinition 对象的标准属性。 而是具有 Verb 和 Group 属性。 Verb 属性包含带有谓词名称的字符串。 Group 属性包含带有谓词组的字符串。

根据最常见的用途，将 PowerShell 谓词分配给某个组。 谓词组旨在简化谓词的查找和比较，而不会限制谓词的使用。 对于任意类型的命令，均可使用任何批准的谓词。

每个 PowerShell 谓词分配给以下组之一。

- 常见：定义可应用于几乎任何 cmdlet 的常规操作，例如 Add。
- 通信：定义适用于通信的操作，例如 "连接"。
- 数据：定义适用于数据处理的操作，例如备份。
- 诊断：定义适用于诊断的操作，例如 "调试"。
- 生命周期：定义适用于 cmdlet 生命周期的操作，如 "完成"。
- 安全性：定义适用于安全的操作，例如 Revoke。
- 其他：定义其他类型的操作。

与 PowerShell 一起安装的一些 cmdlet （例如 `Tee-Object` 和 `Where-Object` ）使用未经批准的谓词。 这些 cmdlet 是历史例外，它们的动词归类为 **reserved** 。

## 相关链接

[Import-Module](import-module.md)
