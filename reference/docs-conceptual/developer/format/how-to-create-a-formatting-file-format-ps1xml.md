---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建格式设置文件 (.format.ps1xml)
description: 如何创建格式设置文件 (.format.ps1xml)
ms.openlocfilehash: 5bbc1ba40bfccf13636abc0f0751938aa724b761
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652006"
---
# <a name="how-to-create-a-formatting-file-formatps1xml"></a>如何创建格式设置文件 (.format.ps1xml)

本主题介绍如何创建 ( # B0 xml) 格式的格式化文件。

> [!NOTE]
> 还可以通过复制 Windows PowerShell 提供的文件之一来创建格式化文件。 如果复制现有的文件，请删除现有的数字签名，并将您自己的签名添加到新文件中。

### <a name="to-create-a-formatps1xml-file"></a>创建 .format.ps1xml 文件。

1. 使用文本编辑器（如记事本）创建文本文件 ( .txt) 。

2. 将以下行复制到格式设置文件中。

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <Configuration>
   <ViewDefinitions>
   </ViewDefinitions>
   </Configuration>
   ```

   - `<Configuration></Configuration>`标记定义根 `Configuration` 节点。 所有其他 XML 标记将包含在此节点中。

   - `<ViewDefinitions></ViewDefinitions>`标记定义 `ViewDefinitions` 节点。 所有视图都在此节点中定义。

3. 将该文件保存到 Windows PowerShell 安装文件夹、模块文件夹或模块文件夹的子文件夹。 保存文件时，请使用以下名称格式：  `MyFile.format.ps1xml` 。 格式化文件必须使用 `.format.ps1xml` 扩展名。

   你现在可以将视图添加到格式设置文件。 对于可在格式设置文件中定义的视图数没有限制。 您可以为每个对象添加单个视图、同一个对象的多个视图或多个对象使用的单个视图。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 格式设置和类型文件](./writing-a-powershell-formatting-file.md)
