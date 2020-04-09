---
title: Windows PowerShell02 示例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: 4d697e73ff4ab4cc4b88593f814d589f89005663
ms.sourcegitcommit: 7f2479edd329dfdc55726afff7019d45e45f9156
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2020
ms.locfileid: "80978638"
---
# <a name="windows-powershell02-sample"></a>Windows PowerShell02 示例

此示例演示如何使用运行空间池的运行空间以异步方式运行命令。 此示例生成命令列表，然后运行这些命令，而 Windows PowerShell 引擎在需要时从池中打开运行空间。

## <a name="requirements"></a>要求

- 此示例需要 Windows PowerShell 2.0。

## <a name="demonstrates"></a>演示

本示例演示下面几点：

- 创建一个 RunspacePool 对象，该对象具有允许同时打开的最小和最大运行空间。
- 创建命令列表。
- 以异步方式运行命令。
- 调用[Runspacepool. Getavailablerunspaces *](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces)方法以查看有多少个空闲空间。
- 正在捕获带有[Endinvoke *](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)方法的命令输出。

## <a name="example"></a>示例

此示例演示如何打开运行空间池的运行空间，以及如何在这些运行空间中以异步方式运行命令。

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell 主机应用程序](./writing-a-windows-powershell-host-application.md)
