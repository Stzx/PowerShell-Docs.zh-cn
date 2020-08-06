---
title: 如何创建 Windows PowerShell 管理单元 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- snap-ins [PowerShell SDK], examples
ms.openlocfilehash: 4150ba582544d1daa4a898f0ff20b169c24a0ee0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787319"
---
# <a name="how-to-create-a-windows-powershell-snap-in"></a>如何创建 Windows PowerShell 管理单元

Windows PowerShell 管理单元提供了一种机制，用于向 shell 注册一组 cmdlet 以及另一个 Windows PowerShell 提供程序，从而扩展了 shell 的功能。 Windows PowerShell 管理单元可以将所有 cmdlet 和提供程序注册到单个程序集中，也可以注册特定的 cmdlet 和提供程序列表。

管理单元程序集应安装在受保护的目录中，就像在其他操作系统中一样。 否则，恶意用户可以将程序集替换为不安全代码。

## <a name="windows-powershell-snap-in-classes"></a>Windows PowerShell 管理单元类

所有 Windows PowerShell 管理单元类均从[add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)或[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)类中派生而来的。

## <a name="examples"></a>示例

[编写 Windows PowerShell 管理单元](./writing-a-windows-powershell-snap-in.md)：此示例演示如何创建用于在程序集中注册所有 cmdlet 和提供程序的管理单元。

[编写自定义 Windows PowerShell 管理单元](./writing-a-custom-windows-powershell-snap-in.md)：此示例演示如何创建一个自定义管理单元，该管理单元用于注册一组特定的 cmdlet 和提供程序，它们在单个程序集中可能存在也可能不存在。

## <a name="see-also"></a>另请参阅

[System.web. Add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)

[System.web. Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)

[注册 Cmdlet](./registering-cmdlets.md)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
