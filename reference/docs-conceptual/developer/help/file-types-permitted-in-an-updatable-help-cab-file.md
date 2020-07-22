---
title: 可更新帮助 CAB 文件中允许的文件类型
ms.date: 03/22/2012
ms.openlocfilehash: 2a8e97edf8daaed915ea1a3e04565d996a2e15fd
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893129"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a>可更新帮助 CAB 文件中允许的文件类型

默认情况下，未压缩的 CAB 文件内容限制为 1 GB。 若要绕过此限制，用户必须使用[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)和[Get-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 的**Force**参数。

若要确保从 internet 下载的帮助文件的安全性，可更新的 Help CAB 文件只能包含下面列出的文件类型。 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet 根据帮助主题架构验证所有文件。 如果此 `Update-Help` cmdlet 遇到无效的文件或不是允许的类型，则它不会安装无效文件，并且不会在用户的计算机上停止从 CAB 安装文件。

- 基于 XML 的 cmdlet 帮助主题。
- 基于 XML 的脚本和函数的帮助主题。
- 针对 PowerShell 提供程序的基于 XML 的帮助主题。
- 基于文本的帮助主题，如 "关于" 主题。

当解压缩 CAB 时， [update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)会验证 cab 内容。 如果 `Update-Help` 在可更新的 HELP CAB 文件中查找不符合的文件类型，则会生成一个终止错误并停止该操作。 它不会从 CAB 中安装任何帮助文件，甚至不会从兼容的文件类型安装任何帮助文件。
