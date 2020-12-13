---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet 参数
description: Cmdlet 参数
ms.openlocfilehash: 1ab495cb674f6b2cd769c3f64d899aec67704216
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92668263"
---
# <a name="cmdlet-parameters"></a>Cmdlet 参数

Cmdlet 参数提供允许 cmdlet 接受输入的机制。 参数可以直接从命令行进行输入，也可以从通过管道传递给 cmdlet 的对象中进行输入，参数 (也称为 *值*) 这些参数可以指定 cmdlet 接受的输入、cmdlet 应如何执行其操作以及 cmdlet 返回到管道的数据。

## <a name="in-this-section"></a>本节内容

将[属性声明为参数](./declaring-properties-as-parameters.md)提供在声明 cmdlet 参数之前必须了解的基本信息。

[Cmdlet 参数的类型](./types-of-cmdlet-parameters.md) 描述可在 cmdlet 中声明的不同类型的参数。

[Cmdlet 参数名称和功能指导原则](./standard-cmdlet-parameter-names-and-types.md) 讨论了标准参数的名称、建议的数据类型和功能。

[参数别名](./parameter-aliases.md) 讨论可以为参数定义的别名。

[常见参数名称](./common-parameter-names.md) 本主题介绍 Windows PowerShell 添加到 cmdlet 的参数。

[Cmdlet 参数集](./cmdlet-parameter-sets.md) 讨论如何使用参数集编写单个 cmdlet，该 cmdlet 可以针对不同的方案执行不同的操作。

[Cmdlet 动态参数](./cmdlet-dynamic-parameters.md) 讨论在特殊条件下可用于用户的参数。

[支持 Cmdlet 参数中的通配符](./supporting-wildcard-characters-in-cmdlet-parameters.md) 描述在设计将针对一组资源运行的 cmdlet 时，如何提供对通配符字符的支持。

[正在验证参数输入](./validating-parameter-input.md) 介绍 Windows PowerShell 如何验证传递给 cmdlet 参数的参数。

[输入筛选器参数](./input-filter-parameters.md) 讨论 `Filter` 、 `Include` 和参数， `Exclude` 这些参数用于筛选 cmdlet 影响的输入对象集。

## <a name="related-sections"></a>相关章节

[如何验证参数输入](./how-to-validate-parameter-input.md)

## <a name="see-also"></a>另请参阅

[参数属性声明](./parameter-attribute-declaration.md)

[Windows PowerShell Cmdlet](./cmdlet-overview.md)
