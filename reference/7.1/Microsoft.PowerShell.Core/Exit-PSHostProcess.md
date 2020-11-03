---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: b7e2bf7cff84e92f4c174ef01861ee5c0a822bea
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196765"
---
# Exit-PSHostProcess

## 摘要
关闭包含本地进程的交互式会话。

## SYNTAX

```
Exit-PSHostProcess [<CommonParameters>]
```

## DESCRIPTION

**Enter-pshostprocess** cmdlet 会关闭一个交互式会话，其中包含通过运行 Enter-PSHostProcess cmdlet 打开的本地进程。 完成调试或排查进程内运行的脚本时，可以从进程内运行 **enter-pshostprocess** cmdlet。

## 示例

### 示例1：退出进程

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

在此示例中，你一直在活动进程中，调试在进程的运行空间中运行的脚本，如 Enter-pshostprocess 中所述。 键入 **exit** 命令退出调试程序后，请运行 **enter-pshostprocess** cmdlet 以关闭与此进程的交互式会话。
Cmdlet 可在进程中关闭会话，并返回到 PS C： \\ \> prompt。

## PARAMETERS

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

## 输出

## 注释

## 相关链接

[Enter-PSHostProcess](Enter-PSHostProcess.md)

