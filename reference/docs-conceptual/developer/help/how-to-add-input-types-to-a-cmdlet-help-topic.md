---
ms.date: 09/12/2016
ms.topic: reference
title: 如何向 Cmdlet 帮助主题添加输入类型
description: 如何向 Cmdlet 帮助主题添加输入类型
ms.openlocfilehash: f2ad87c54230bcdd7e0ea708e9a1869daef7495f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391096"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>如何向 Cmdlet 帮助主题添加输入类型

本部分介绍如何将 **输入** 部分添加到 PowerShell cmdlet 帮助主题。 " **输入** " 部分列出了 cmdlet 作为管道的输入接受的对象的 .net 类，可以通过值或按属性名称。

可以添加到 **输入** 部分的类的数量没有限制。 输入类型括在 `<command:inputTypes>` 节点中，每个类都包含在元素中 `<command:inputType>` 。

架构包括 `<maml:description>` 每个元素中的两个元素 `<command:inputType>` 。
但是，该 `Get-Help` cmdlet 只显示元素的内容 `<command:inputType>/<maml:description>` 。

从 PowerShell 3.0 开始， `Get-Help` cmdlet 显示元素的内容 `<maml:uri>` 。
此元素使用户能够将用户定向到描述 .NET 类的主题。

下面的 XML 显示了 `<maml:inputTypes>` 节点。

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

下面的 XML 演示使用 `<maml:inputTypes>` 节点记录输入类型的示例。

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name>System.DateTime</maml:name>
      <maml:uri>https://docs.microsoft.com/dotnet/api/system.datetime</maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
