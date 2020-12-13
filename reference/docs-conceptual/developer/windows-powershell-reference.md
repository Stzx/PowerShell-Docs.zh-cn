---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell 参考
description: Windows PowerShell 参考
ms.openlocfilehash: 9c1547ac5ec5134c99aa9213e6aaca1af8d5b3e9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390229"
---
# <a name="windows-powershell-reference"></a>Windows PowerShell 参考

Windows PowerShell 是一种用于管理自动化的 Microsoft .NET 框架连接的环境。 Windows PowerShell 提供了一种新的方法，用于生成命令、撰写解决方案以及创建基于图形用户界面的管理工具。

Windows PowerShell 允许系统管理员通过直接或通过脚本执行命令，来自动管理系统资源。

## <a name="developer-audience"></a>面向开发人员

Windows PowerShell 软件开发工具包 (SDK) 专为需要 Windows PowerShell 提供的 Api 参考信息的命令开发人员编写。 命令开发人员使用 Windows PowerShell 来创建命令和提供程序，以扩展可由 Windows PowerShell 执行的任务。

## <a name="windows-powershell-resources"></a>Windows PowerShell 资源

除了 Windows PowerShell SDK 外，以下资源还提供了详细信息。

[Windows PowerShell 入门](/powershell/scripting/getting-started/getting-started-with-windows-powershell) 提供对 Windows PowerShell 的介绍：语言、cmdlet、提供程序和对象的用法。

[编写 Windows PowerShell 模块](./module/writing-a-windows-powershell-module.md) 为需要使用 Windows PowerShell 模块打包和分发其 Windows PowerShell 解决方案的管理员、脚本开发人员和 cmdlet 开发人员提供信息和示例。

[编写 Windows PowerShell Cmdlet](./cmdlet/writing-a-windows-powershell-cmdlet.md) 为正在设计 cmdlet 的程序管理器和实现 cmdlet 代码的开发人员提供信息和代码示例。

[Windows PowerShell 团队博客](https://devblogs.microsoft.com/powershell/) 用于学习和与其他 Windows PowerShell 用户协作的最佳资源。 请阅读 Windows PowerShell 团队博客，然后加入 Windows PowerShell 用户论坛 (microsoft.public.windows.powershell)。
可使用 Windows Live Search 查找其他 Windows PowerShell 博客和资源。 然后，在开发专业知识时，自由地提供您的观点。

[PowerShell 模块浏览器](/powershell/module/) 提供命令行帮助主题的最新版本。

## <a name="class-libraries"></a>类库

[System.web](/dotnet/api/System.Management.Automation) 。此命名空间是 Windows PowerShell 的根命名空间。 它包含实现自定义 cmdlet 所需的类、枚举和接口。 特别是， [system.web](/dotnet/api/System.Management.Automation.Cmdlet) 类是所有 Cmdlet 类必须从其派生的基类。 有关 cmdlet 的详细信息，请参阅。

[System.web](/dotnet/api/System.Management.Automation.Provider) 命名空间包含实现 Windows PowerShell 提供程序所需的类、枚举和接口。 特别是， [Cmdletprovider](/dotnet/api/System.Management.Automation.Provider.CmdletProvider) 类是所有 Windows PowerShell 提供程序类必须从其派生的基类。

[此命名](/dotnet/api/Microsoft.PowerShell.Commands) 空间包含 Windows PowerShell 所实现的 cmdlet 和提供程序的类。 同样，建议你创建一个 *YourName*。你实现的这些 cmdlet 的命令命名空间。

[此命名](/dotnet/api/System.Management.Automation.Host) 空间包含 cmdlet 用来定义用户和 Windows PowerShell 之间的交互的类、枚举和接口。

[System.web](/dotnet/api/System.Management.Automation.Internal) 命名空间包含由其他命名空间类使用的基类。 例如， [Cmdletmetadataattribute](/dotnet/api/System.Management.Automation.Internal.CmdletMetadataAttribute) 类是 [CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) 类的基本类。 "管理类" 的基类为。

[此命名](/dotnet/api/System.Management.Automation.Runspaces) 空间包含用于创建 Windows PowerShell 运行空间的类、枚举和接口。 在此上下文中，Windows PowerShell 运行空间是一个或多个 Windows PowerShell 管道调用 cmdlet 的上下文。 也就是说，cmdlet 在 Windows PowerShell 运行空间的上下文中工作。 AboutWindows PowerShell 运行空间的详细信息，请参阅 [Windows powershell 运行空间](hosting/creating-runspaces.md)。
