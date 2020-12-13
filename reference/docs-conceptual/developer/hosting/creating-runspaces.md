---
ms.date: 09/13/2016
ms.topic: reference
title: 创建运行空间
description: 创建运行空间
ms.openlocfilehash: c6b2c577e435ec88364b189a0c3d065f54f02525
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649348"
---
# <a name="creating-runspaces"></a>创建运行空间

运行空间是主机应用程序调用的命令的操作环境。 此环境包括当前存在的命令和数据，以及当前适用的任何语言限制。

 主机应用程序可以使用 Windows PowerShell 提供的默认运行空间，其中包括所有可用的核心命令，或创建仅包含可用命令子集的自定义运行空间。 若要创建自定义的运行空间，请创建一个 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) 对象，并将其分配给运行空间。

## <a name="runspace-tasks"></a>运行空间任务

1. [创建 InitialSessionState](./creating-an-initialsessionstate.md)

2. [创建受限运行空间](./creating-a-constrained-runspace.md)

3. [创建多个运行空间](./creating-multiple-runspaces.md)

## <a name="see-also"></a>另请参阅
