---
title: 如何向 Cmdlet 帮助主题添加返回值
ms.date: 09/12/2016
ms.openlocfilehash: c164556cd06b332d04857987360c98f740a150b5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893350"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>如何向 Cmdlet 帮助主题添加返回值

本部分介绍如何将输出部分添加到 PowerShell cmdlet 帮助主题。 "**输出**" 部分列出了 cmdlet 返回或沿管道向下传递的对象的 .net 类。

可以添加到 "**输出**" 部分的类的数量没有限制。 Cmdlet 的返回类型包含在一个 `<command:returnValues>` 节点中，其中每个类都包含在一个 `<command:returnValue>` 元素中。

如果 cmdlet 未生成任何输出，请使用此部分来指示没有输出。 例如，若要替代类名称，请写入 "**无**" 并提供简短说明。 如果 cmdlet 按条件生成输出，请使用此节点解释条件并描述条件输出。

架构包括 `<maml:description>` 每个元素中的两个元素 `<command:returnValue>` 。
但是，该 `Get-Help` cmdlet 只显示元素的内容 `<command:returnValue>/<maml:description>` 。

从 PowerShell 3.0 开始， `Get-Help` cmdlet 显示元素的内容 `<maml:uri>` 。
此元素使用户能够将用户定向到描述 .NET 类的主题。

下面的 XML 显示了 `<maml:returnValues>` 节点。

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

下面的 XML 演示使用 `<maml:returnValues>` 节点记录输出类型的示例。

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
