---
title: 模块和管理单元 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 07cdc55fd6d1462130f1a81deb30056623a525e6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787302"
---
# <a name="modules-and-snap-ins"></a>模块和管理单元

Cmdlet 可以使用 Windows PowerShell 2.0) 或管理单元引入 (模块添加到会话中。将 cmdlet 添加到会话后，它可以通过主机应用程序以编程方式运行，或在命令行中以编程方式运行。

出于以下原因，建议使用模块作为向会话添加 cmdlet 的传递方法：

- 模块允许通过加载定义 cmdlet 的程序集来添加 cmdlet。 无需实现管理单元类。

- 模块允许添加其他资源，例如变量、函数、脚本、类型和格式设置文件等。

- 管理单元只能用于向会话添加 cmdlet 和提供程序。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 模块](writing-a-windows-powershell-module.md)

[编写 Windows PowerShell Cmdlet](../cmdlet/cmdlet-overview.md)
