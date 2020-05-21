---
title: 可更新的帮助 CAB 文件中允许的文件类型 |Microsoft Docs
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 6e9e51a50226430465726d27874e02e98ee67672
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560978"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>可更新帮助 CAB 文件中允许的文件类型

本主题列出并描述了可更新的帮助 CAB 文件的内容要求。

## <a name="updatable-help-cab-file-requirements"></a>可更新的帮助 CAB 文件要求

默认情况下，未压缩的 CAB 文件内容限制为 1 GB。 若要绕过此限制，用户必须使用[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)和[Get-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 的**Force**参数。

若要确保从 Internet 下载的帮助文件的安全性，可更新的 Help CAB 文件只能包含下面列出的文件类型。 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet 根据帮助主题架构验证所有文件。 如果此 `Update-Help` cmdlet 遇到无效的文件或不是允许的类型，则它不会安装无效文件，并且不会在用户的计算机上停止从 CAB 安装文件。

- 基于 XML 的 cmdlet 帮助主题。

- 基于 XML 的脚本和函数的帮助主题。

- 适用于 Windows PowerShell 提供程序的基于 XML 的帮助主题。

- 基于文本的帮助主题，如 "关于" 主题。

当解压缩 CAB 时， [update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)会验证 cab 内容。 如果 `Update-Help` 在可更新的 HELP CAB 文件中查找不符合的文件类型，则会生成一个终止错误并停止该操作。 它不会从 CAB 中安装任何帮助文件，甚至不会从兼容的文件类型安装任何帮助文件。
