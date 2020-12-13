---
ms.date: 09/13/2016
ms.topic: reference
title: 如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要
description: 如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要
ms.openlocfilehash: aeeb0cdd1d6d17b88067928ff952dc57a9441917
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659048"
---
# <a name="how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic"></a>如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要

本部分介绍如何添加在 cmdlet 帮助的 " **名称** " 和 " **概要** " 部分中显示的内容。 在帮助文件中，此内容将添加到每个 cmdlet 的命令节点。

> [!NOTE]
> 若要获取帮助文件的完整视图，请打开 `dll-Help.xml` 位于 PowerShell 安装目录中的文件之一。 例如，该 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` 文件包含多个 PowerShell cmdlet 的内容。

## <a name="to-add-the-cmdlet-name-and-a-synopsis"></a>添加 Cmdlet 名称和摘要

- Cmdlet 帮助可以为 cmdlet 显示两个描述。 第一个说明是称为 "摘要" 的简短说明。 第二个说明是在 [将详细描述添加到 Cmdlet 帮助主题](./how-to-add-a-cmdlet-description.md)中所述的更详细说明。
  这两个说明应作为一个段落来编写。

- 在 "摘要" 中，不重复 cmdlet 名称。 通知用户 `Get-Server` cmdlet 获取服务器非常简短，但没有提示信息。 请改用同义词并向说明添加详细信息。

  示例： "获取表示本地或远程计算机的对象。"

- 使用摘要中的简单谓词，例如 "get"、"create" 和 "change"。 避免使用 "set"，因为它不明确，如 "修改"。

  示例： "获取有关文件中 Authenticode 签名的信息。"

- 写入活动的语音。 例如，"使用 TimeSpan 对象 ..."比 "可使用 TimeSpan 对象 ..." 更清晰。

- 描述用于获取对象的 cmdlet 时，应避免出现 "显示" 谓词。 虽然 Windows PowerShell 显示 cmdlet 数据，但向用户介绍 cmdlet 会返回 .NET Framework 对象（这些对象的数据可能不会显示），这一点很重要。 如果您强调显示，用户可能不会意识到该 cmdlet 可能返回了许多其他有用的属性和未显示的方法。

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
