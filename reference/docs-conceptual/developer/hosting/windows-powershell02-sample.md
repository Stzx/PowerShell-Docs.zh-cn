---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell02 示例
description: Windows PowerShell02 示例
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657351"
---
# <a name="windows-powershell02-sample"></a>Windows PowerShell02 示例

此示例演示如何使用运行空间池的运行空间以异步方式运行命令。 此示例生成命令列表，然后运行这些命令，而 Windows PowerShell 引擎在需要时从池中打开运行空间。

## <a name="requirements"></a>要求

- 此示例需要 Windows PowerShell 2.0。

## <a name="demonstrates"></a>演示

此示例对下列内容进行了说明：

- 创建一个 RunspacePool 对象，该对象具有允许同时打开的最小和最大运行空间。
- 创建命令列表。
- 以异步方式运行命令。
- 调用 [Runspacepool. Getavailablerunspaces *](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) 方法以查看有多少个空闲空间。
- 正在捕获带有 [Endinvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) 方法的命令输出。

## <a name="example"></a>示例

此示例演示如何打开运行空间池的运行空间，以及如何在这些运行空间中以异步方式运行命令。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 主机应用程序](./writing-a-windows-powershell-host-application.md)
