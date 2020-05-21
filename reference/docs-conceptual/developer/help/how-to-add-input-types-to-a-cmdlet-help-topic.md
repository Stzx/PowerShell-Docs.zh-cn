---
title: 如何向 Cmdlet 帮助主题添加输入类型 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: 58b908be3149376547b075320b021421351b881e
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557051"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>如何向 Cmdlet 帮助主题添加输入类型

本部分介绍如何将输入部分添加到 Windows PowerShell® cmdlet 帮助主题。 "输入" 部分列出了 cmdlet 作为管道的输入接受的对象的 .NET 类，可以通过值或按属性名称。

可以添加到输入部分的类的数量没有限制。 输入类型括在 \< 命令： inputTypes> node 中，其中每个类都包含在 \< 命令中： inputType> 元素。

架构包括两个 \< maml：说明> 每个命令中的元素 \< ： inputType> 元素。 但是，该 `Get-Help` cmdlet 只显示命令的内容 \< ： inputType>/ \< maml： description>）元素。

从 Windows PowerShell 3.0 开始， `Get-Help` cmdlet 将显示 \< maml： uri> 元素的内容。 此元素使用户能够将用户定向到描述 .NET 类的主题。

以下 XML 显示了 \< maml： inputTypes> 节点。

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> Class name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Brief description </maml:para>
    </maml:description>
  </command:inputType>
</command:inputTypes>
```

下面的 XML 演示使用 \< maml： inputTypes> 节点记录输入类型的示例。

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
