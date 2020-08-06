---
title: 如何创建 Cmdlet 帮助文件 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7ab0404e5d0122a64483883e6e2d4760dfa5038d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87779822"
---
# <a name="how-to-create-the-cmdlet-help-file"></a>如何创建 Cmdlet 帮助文件

本部分介绍如何创建包含 Windows PowerShell cmdlet 帮助主题内容的有效 XML 文件。 本部分讨论如何命名帮助文件，如何添加相应的 XML 标头，以及如何添加将包含 cmdlet 帮助内容的不同部分的节点。

> [!NOTE]
> 若要获取帮助文件的完整视图，请打开 `dll-Help.xml` 位于 Windows PowerShell 安装目录中的文件之一。 例如，该 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` 文件包含多个 PowerShell cmdlet 的内容。

### <a name="how-to-create-a-cmdlet-help-file"></a>如何创建 Cmdlet 帮助文件

1. 创建一个文本文件，并使用 UTF8 编码保存该文件。 文件名必须具有以下格式，以便 Windows PowerShell 能够将其作为 cmdlet 帮助文件进行检测。

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. 将以下 XML 标头添加到文本文件。 请注意，将根据 Microsoft 协助标记语言 (MAML) 架构来验证该文件。 目前，PowerShell 不提供任何用于验证文件的工具。

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. 将**命令**节点添加到程序集中每个 cmdlet 的 cmdlet 帮助文件。 **命令**节点内的每个节点都与 cmdlet 帮助主题的不同部分相关。

   下表列出了每个节点的 XML 元素，后跟每个节点的说明。

   |           节点           |                                                                                                     说明                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | 为 cmdlet 帮助主题的名称和摘要部分添加内容。 有关详细信息，请参阅[如何添加 Cmdlet 名称和摘要](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)。 |
   | `<maml:description>`     | 添加 cmdlet 帮助主题的 "描述" 部分的内容。 有关详细信息，请参阅[如何将详细描述添加到 Cmdlet 的帮助主题](./how-to-add-a-cmdlet-description.md)。                    |
   | `<command:syntax>`       | 为 cmdlet 帮助主题的语法部分添加内容。 有关详细信息，请参阅[如何将语法添加到 Cmdlet 的帮助主题](./how-to-add-syntax-to-a-cmdlet-help-topic.md)。                                  |
   | `<command:parameters>`   | 添加 cmdlet 帮助主题的参数部分的内容。 有关详细信息，请参阅[如何将参数添加到 Cmdlet 的帮助主题](./how-to-add-parameter-information.md)。                                  |
   | `<command:inputTypes>`   | 添加 cmdlet 帮助主题的 "输入" 部分的内容。 有关详细信息，请参阅[如何将输入类型添加到 Cmdlet 的帮助主题](./how-to-add-input-types-to-a-cmdlet-help-topic.md)。                        |
   | `<command:returnValues>` | 添加 cmdlet 帮助主题的 "输出" 部分的内容。 有关详细信息，请参阅[如何将返回值添加到 Cmdlet 的帮助主题](./how-to-add-return-values-to-a-cmdlet-help-topic.md)。                   |
   | `<maml:alertset>`        | 添加 cmdlet 帮助主题的 "注释" 部分的内容。 有关详细信息，请参阅[如何向 Cmdlet 帮助主题添加注释](./how-to-add-notes-to-a-cmdlet-help-topic.md)。                                      |
   | `<command:examples>`     | 添加 cmdlet 帮助主题的 "示例" 部分的内容。 有关详细信息，请参阅[如何将示例添加到 Cmdlet 的帮助主题](./how-to-add-examples-to-a-cmdlet-help-topic.md)。                            |
   | `<maml:relatedLinks>`    | 添加 cmdlet 帮助主题的 "相关链接" 部分的内容。 有关详细信息，请参阅[如何将相关链接添加到 Cmdlet 的帮助主题](./how-to-add-related-links-to-a-cmdlet-help-topic.md)。             |

## <a name="example"></a>示例

 下面是一个**命令**节点示例，其中包含 cmdlet 帮助主题各个部分的节点。

```xml
<command:command
  xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
  xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a>另请参阅

 [如何添加 Cmdlet 名称和摘要](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [如何将详细描述添加到 Cmdlet 帮助主题](./how-to-add-a-cmdlet-description.md)

 [如何向 Cmdlet 帮助主题添加语法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [如何将参数添加到 Cmdlet 帮助主题](./how-to-add-parameter-information.md)

 [如何向 Cmdlet 帮助主题添加输入类型](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加返回值](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加注释](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加示例](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [如何向 Cmdlet 帮助主题添加相关链接](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [Windows PowerShell SDK](../windows-powershell-reference.md)
