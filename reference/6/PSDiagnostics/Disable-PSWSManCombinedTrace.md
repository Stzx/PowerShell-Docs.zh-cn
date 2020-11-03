---
external help file: PSDiagnostics-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pswsmancombinedtrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSWSManCombinedTrace
ms.openlocfilehash: dc817a2f8629744ce4bdcf428530713e76c3d044
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2020
ms.locfileid: "93196713"
---
# Disable-PSWSManCombinedTrace

## 摘要
停止通过 Enable-PSWSManCombinedTrace 启动的日志记录会话。

## SYNTAX

```
Disable-PSWSManCombinedTrace [<CommonParameters>]
```

## DESCRIPTION

此 cmdlet 将停止启动的日志记录会话 `Enable-PSWSManCombinedTrace` 。

此 cmdlet 使用 `Stop-Trace` cmdlet。

必须从提升的 PowerShell 会话中运行此 cmdlet。

## 示例

### 示例1：禁用合并的日志记录会话

```powershell
Disable-PSWSManCombinedTrace
```

## PARAMETERS

### CommonParameters

此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。 有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。

## 输入

### 无

## 输出

### 无

## 注释

## 相关链接

[事件跟踪](/windows/desktop/ETW/event-tracing-portal)

[Stop-Trace](stop-trace.md)

[Enable-PSWSManCombinedTrace](Enable-PSWSManCombinedTrace.md)
