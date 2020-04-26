---
title: 编辑参考文章
description: 本文说明编辑 PowerShell 文档中的 cmdlet 参考和“关于”主题的特定要求。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: e135f6cc81ba7537a535a08421e1ca9b2b2af573
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "81624765"
---
# <a name="editing-reference-articles"></a>编辑参考文章

Cmdlet 参考文章具有特定结构。 此结构是由 [PlatyPS][] 定义的。
PlatyPS 在 Markdown 中为 PowerShell 模块生成 cmdlet 帮助。 编辑 Markdown 文件后，使用 PlatyPS 创建 `Get-Help` cmdlet 使用的 MAML 帮助文件。

PlatyPS 拥有针对 cmdlet 参考的硬编码架构，该架构已写入代码。 [platyPS.schema.md][] 文档尝试描述此结构。 架构冲突会导致生成错误，必须先修复这些错误，我们才能接受你参与撰写。

## <a name="general-guidelines"></a>一般性指导

- 不要删除任何标头结构。 PlatyPS 需要一组特定的标头。
- “输入类型”和“输出类型”标头必须包含一种类型。   若 cmdlet 不接受输入或不返回值，则使用值 `None`。
- 仅[示例](#structuring-examples)部分允许隔离代码块。
- 内联代码跨度可用于任何段落。

## <a name="formatting-about_-files"></a>设置 About_ 文件的格式

`About_*` 文件是使用 Markdown 编写的，但以纯文本文件的形式提供。 我们使用 [Pandoc][] 将 Markdown 转换为纯文本。 设置 `About_*` 文件的格式，以使其在 PowerShell 的所有版本上均可与发布工具良好兼容。

格式设置基本准则：

- 将行限制为 80 个字符。 Pandoc 会缩进一些 Markdown 块，因此必须调整这些块。
  - 将代码块限制为 76 个字符
  - 将表限制为 76 个字符
  - 将块引用（和通知）限制为 78 个字符

- 使用 Pandoc 的特殊元字符 `\`、`$` 和 `<`
  - 在标题中，必须使用前导 `\` 字符对这些字符进行转义，或者使用反引号 (`` ` ``) 括在代码范围中
  - 在段落中，应将这些字符置于代码跨度内。 例如：

    ~~~markdown
    ### The purpose of the \$foo variable

    The `$foo` variable is used to store ...
    ~~~

- 表需要在 76 个字符内
  - 手动包装多个行中单元格的内容
  - 在每行上使用开始和结束 `|` 字符
  - 下面的示例展示了如何正确构造一个表，该表包含在单元内的多个行上换行的信息。

    ~~~markdown
    ```
    |Operator|Description                |Example                          |
    |--------|---------------------------|---------------------------------|
    |`-is`   |Returns TRUE when the input|`(get-date) -is [DateTime]`      |
    |        |is an instance of the      |`True`                           |
    |        |specified .NET type.       |                                 |
    |`-isNot`|Returns TRUE when the input|`(get-date) -isNot [DateTime]`   |
    |        |not an instance of the     |`False`                          |
    |        |specified.NET type.        |                                 |
    |`-as`   |Converts the input to the  |`"5/7/07" -as [DateTime]`        |
    |        |specified .NET type.       |`Monday, May 7, 2007 12:00:00 AM`|
    ```
    ~~~

    > [!NOTE]
    > 76 列的限制仅适用于 `About_*` 主题。 可以在概念性文章或 cmdlet 参考文章中使用宽列。

## <a name="structuring-examples"></a>结构示例

在 PlatyPS 架构中，EXAMPLES 标头是 H2 标头，每个示例是 H3 标头。 

在示例中，此架构不允许通过段落来分隔代码块。 支持的架构为：

```
### Example #X title

0 or more paragraphs
1 or more code blocks
0 or more paragraphs.
```

为每个示例编号，并添加简短标题。

例如：

### <a name="example-1-get-cmdlets-functions-and-aliases"></a>示例 1：获取 cmdlet、函数和别名

此命令将获取安装在计算机上的 PowerShell cmdlet、函数和别名。

```powershell
Get-Command
```

### <a name="example-2-get-commands-in-the-current-session"></a>示例 2：获取当前会话中的命令

```powershell
Get-Command -ListImported
```

## <a name="next-steps"></a>后续步骤

[编辑清单](editorial-checklist.md)

<!-- link references -->
[PlatyPS]: https://github.com/powershell/platyps
[platyPS.schema.md]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[issue1806]: https://github.com/MicrosoftDocs/PowerShell-Docs/issues/1806
[about-example]: /PowerShell/module/Microsoft.PowerShell.Core/About/about_Comparison_Operators
[Pandoc]: https://pandoc.org
