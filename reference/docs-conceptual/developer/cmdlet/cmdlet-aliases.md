---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 别名
description: Cmdlet 别名
ms.openlocfilehash: 734553a9911aef256df563afa6abcdb23d7a62e6
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660790"
---
# <a name="cmdlet-aliases"></a>Cmdlet 别名

可以使用 cmdlet 别名来改善 cmdlet 用户体验。 你可以将别名添加到常用的 cmdlet，以减少键入并更轻松地完成任务。 可以在 cmdlet 中包含内置别名，或者用户可以定义自己的自定义别名。

例如， [get-help](/powershell/module/microsoft.powershell.core/get-command) cmdlet 具有内置 `gcm` 别名。 你还可以使用别名来添加其他语言的命令名称，以便用户无需了解新的命令。

## <a name="alias-guidelines"></a>别名指南

为 cmdlet 创建内置别名时，请遵循以下准则：

- 在分配别名之前，请启动 Windows PowerShell，然后运行 [获取别名](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet 以查看已使用的别名。

- 包含一个别名前缀，该前缀引用 cmdlet 名称的谓词和引用 cmdlet 名称名词的别名后缀。 例如，cmdlet 的别名 `Import-Module` 为 "ipmo"。 有关所有谓词及其别名的列表，请参阅 [Cmdlet 谓词](./approved-verbs-for-windows-powershell-commands.md)。

- 对于具有相同谓词的 cmdlet，请包含相同的别名前缀。 例如，其名称中具有 "Get" 谓词的所有 Windows PowerShell cmdlet 的别名均使用 "g" 前缀。

- 对于具有相同名词的 cmdlet，请包含相同的别名后缀。 例如，名称中包含 "Session" 名词的所有 Windows PowerShell cmdlet 的别名均使用 "sn" 后缀。

- 对于等效于其他语言中的命令的 cmdlet，请使用命令的名称。

- 通常，请尽可能缩短别名。 请确保该别名至少具有一个用于该谓词的非重复字符和名词的一个不同字符。 根据需要添加更多字符，使别名唯一。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
