---
external help file: PSReadLine-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/psconsolehostreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: PSConsoleHostReadLine
ms.openlocfilehash: 10e79223801a32a2409de253daabe1019ae1b64b
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "93200690"
---
# PSConsoleHostReadLine

## 摘要
此函数是 PSReadLine 的主要入口点。

## SYNTAX

```
PSConsoleHostReadLine
```

## DESCRIPTION

`PSConsoleHostReadLine` 是 PSReadLine 模块的主入口点。 PowerShell 控制台主机会自动加载 PSReadLine 模块并调用此函数。 在正常操作情况下，不应从命令行使用此函数。

扩展点 `PSConsoleHostReadLine` 对于控制台主机是特殊的。 主机将调用具有此名称的任何别名、函数或脚本。 PSReadLine 定义此函数，使其从控制台主机调用。

## 示例

### 示例 1

不应从命令行使用此函数。

## PARAMETERS

## 输入

### 无

## 输出

### 无

## 注释

## 相关链接

[about_PSReadLine](./About/about_PSReadLine.md)

