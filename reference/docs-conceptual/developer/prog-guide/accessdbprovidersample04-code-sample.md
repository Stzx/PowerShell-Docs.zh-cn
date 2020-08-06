---
title: AccessDbProviderSample04 代码示例 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 05509c5b36475bcd3f91c9ab7413974994d668d6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787268"
---
# <a name="accessdbprovidersample04-code-sample"></a>AccessDbProviderSample04 代码示例

下面的代码演示了在[创建 Windows Powershell 容器提供程序](./creating-a-windows-powershell-container-provider.md)中所述的 windows powershell 提供程序的实现。
此提供程序适用于多层数据存储区。 对于这种类型的数据存储，存储区的顶层包含根项，而每个后续级别称为子项的节点。 通过允许用户在这些子节点上工作，用户可以通过数据存储区进行分层交互。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell SDK](../windows-powershell-reference.md)
