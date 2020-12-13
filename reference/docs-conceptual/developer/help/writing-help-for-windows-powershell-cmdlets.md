---
ms.date: 09/13/2016
ms.topic: reference
title: 编写针对 PowerShell Cmdlet 的帮助
description: 编写针对 PowerShell Cmdlet 的帮助
ms.openlocfilehash: b1deaa5998dbc54add93764db785d57afcc0a779
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658100"
---
# <a name="writing-help-for-powershell-cmdlets"></a>编写针对 PowerShell Cmdlet 的帮助

PowerShell cmdlet 非常有用，但除非帮助主题清楚地说明了 cmdlet 的作用以及使用方式，否则 cmdlet 可能不会被使用，甚至更糟糕的是，它可能会使用户不快。 基于 XML 的 cmdlet 帮助文件格式增强了一致性，但有很大的帮助需要进一步的帮助。

如果你从未编写过 cmdlet 帮助，请查看以下准则。 以下部分介绍了创作 cmdlet 帮助主题所需的 XML 架构。 首先 [创建 Cmdlet 帮助文件](./how-to-create-the-cmdlet-help-file.md)。 该主题包括顶级 XML 节点的说明。

## <a name="writing-guidelines-for-cmdlet-help"></a>编写 Cmdlet 帮助指南

### <a name="write-well"></a>编写良好

任何内容都不会替代编写良好的主题。 如果您不是专业作者，请找到编写器或编辑器来帮助您。 另一种方法是将帮助文本复制到 Microsoft Word 中，并使用语法和拼写检查来改善您的工作。

### <a name="write-simply"></a>简单编写

使用简单的单词和短语。 避免行业术语。 请注意，许多读者只配有外文字典和帮助主题。

### <a name="write-consistently"></a>一致性写入

相关 cmdlet 的帮助应类似 (例如，x-blade 和集-x) 。 为标准参数（如 **Force** 和 **InputObject**）使用标准说明。  (将其从核心 cmdlet 的帮助中复制。 ) 使用标准术语。 例如，使用 "参数" 而不是 "参数"，并使用 "cmdlet" 而不是 "命令" 或 "命令-let"。

### <a name="start-the-synopsis-with-a-verb"></a>使用谓词启动摘要

"摘要" 字段向用户通知 cmdlet 的功能，而不是它的作用或工作方式。 谓词创建一个基于任务的语句，该语句通知用户此 cmdlet 是否满足其要求。 使用简单的谓词，例如 "get"、"create" 和 "change"。 避免出现 "set"，这可能是个含糊的词，如 "修改"。

### <a name="focus-on-objects"></a>专注于对象

大多数 "get" cmdlet 显示某些内容，但其主要功能是获取对象。 在您的帮助中，将重点放在对象上，以便用户理解默认显示为多个，并可使用以不同方式为其检索的对象的方法和属性。

### <a name="write-detailed-descriptions"></a>编写详细说明

简要列出 cmdlet 可在详细说明中执行的所有操作。 如果主函数是更改一个属性，但该 cmdlet 可以更改所有属性，请在详细说明中列出此项。

### <a name="use-conventional-syntax"></a>使用传统语法

使用 Windows 和 UNIX 命令行帮助中常见的标准 Backus-Naur 格式。

### <a name="use-microsoft-net-types-for-parameter-values"></a>使用 Microsoft .NET 类型作为参数值

语法和参数说明中 (参数值的占位符) 显示参数将接受的对象 .NET Framework 类型。 PowerShell 团队开发了此约定，以帮助用户了解 .NET Framework。

### <a name="write-complete-parameter-descriptions"></a>编写完整的参数说明

参数说明必须向用户通知两个问题：参数的作用 (其效果) 以及必须为参数值键入的内容。

### <a name="write-practical-examples"></a>编写实际示例

这些示例应说明如何使用所有参数，但最重要的一点是说明如何在实际任务中使用 cmdlet。 从一个简单的示例开始，编写越来越复杂的示例。 在最后的示例中，说明如何在管道中使用 cmdlet。

### <a name="use-the-notes-field"></a>使用 "注释" 字段

使用 "注释" 字段来解释用户需要了解 cmdlet 的概念。 你还可以使用注释来帮助用户避免常见错误。 避免更改 Url。 相反，请提供用户搜索搜索条件。

### <a name="test-your-help"></a>测试您的帮助

测试帮助，就像测试代码一样。 让朋友和同事阅读你的帮助内容并提供反馈。 你还可以从新闻组请求反馈。

## <a name="see-also"></a>另请参阅

 [如何创建 Cmdlet 帮助文件](./how-to-create-the-cmdlet-help-file.md)

 [如何向 Cmdlet 帮助主题添加 Cmdlet 名称和摘要](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [如何将详细描述添加到 Cmdlet 帮助主题](./how-to-add-a-cmdlet-description.md)

 [如何向 Cmdlet 帮助主题添加语法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [如何将参数添加到 Cmdlet 帮助主题](./how-to-add-parameter-information.md)

 [如何将输入类型添加到 Cmdlet 帮助主题](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加返回值](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加备注](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加示例](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加相关链接](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Windows PowerShell SDK](../windows-powershell-reference.md)
