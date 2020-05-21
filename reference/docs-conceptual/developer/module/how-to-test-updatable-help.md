---
title: 如何测试可更新帮助 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: 8dd3770a60ca56634ad1eb1ac8cf89d96c975c90
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560502"
---
# <a name="how-to-test-updatable-help"></a>如何测试可更新帮助

本主题介绍用于测试模块的可更新帮助的方法。

## <a name="using-verbose-to-detect-errors"></a>使用 Verbose 检测错误

为模块上载 HelpInfo XML 文件和 CAB 文件后，通过运行带有**Verbose**参数的[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)命令来测试文件。 **Verbose**参数 `Update-Help` 用于报告其操作中的关键步骤，从读取模块清单中的**HelpInfoUri**键到验证解压缩后的 CAB 文件中的文件类型，并将文件放在特定于语言的模块目录中。

解析所有详细消息后， `Update-Help` 使用**Debug**参数运行命令。 此参数应检测可更新帮助文件的任何其他问题。
