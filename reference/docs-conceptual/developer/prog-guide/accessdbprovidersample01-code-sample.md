---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample01 代码示例
description: AccessDbProviderSample01 代码示例
ms.openlocfilehash: 5be593b9e86347b2f55de156fe4d9b44cfab5b78
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659416"
---
# <a name="accessdbprovidersample01-code-sample"></a>AccessDbProviderSample01 代码示例

下面的代码演示了在 [创建基本 Windows Powershell 提供程序](./creating-a-basic-windows-powershell-provider.md)中所述的 Windows powershell 提供程序的实现。
此实现提供了启动和停止提供程序的方法，但它并不提供访问数据存储或获取或设置数据存储中数据的方法，但它提供了所有提供程序所需的基本功能。

> [!NOTE]
> 您可以使用适用于 Windows Vista 的 Windows 软件开发工具包和 Microsoft .NET Framework 3.0 运行时组件，为此提供程序 (AccessDBSampleProvider01.cs) 下载 c # 源文件。 有关下载说明，请参阅 [如何安装 Windows powershell 和下载 Windows POWERSHELL SDK](/powershell/scripting/developer/installing-the-windows-powershell-sdk)。
> 下载的源文件在目录中提供 **\<PowerShell Samples>** 。 有关其他 Windows PowerShell 提供程序实现的详细信息，请参阅 [设计 Windows Powershell 提供程序](./designing-your-windows-powershell-provider.md)。

## <a name="code-sample"></a>代码示例

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample01/AccessDBProviderSample01.cs" range="11-30":::

## <a name="see-also"></a>另请参阅

[Windows PowerShell 程序员指南](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
