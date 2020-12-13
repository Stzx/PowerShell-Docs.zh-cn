---
ms.date: 09/13/2016
ms.topic: reference
title: GetProc 教程
description: GetProc 教程
ms.openlocfilehash: 9379e791dd5361fcf5b79061bf0a601ebeb84f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652791"
---
# <a name="getproc-tutorial"></a>GetProc 教程

本部分提供的教程介绍了如何创建 Get-Proc cmdlet，该 cmdlet 非常类似于 Windows PowerShell 提供的 [进程](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet。 本教程提供了代码段，阐释了如何实现 cmdlet 以及代码的说明。

## <a name="topics-in-this-tutorial"></a>本教程中的主题

本教程中的主题旨在按顺序阅读，每个主题都按照上一主题中讨论的内容来构建。

[创建不带参数的 Cmdlet](./creating-a-cmdlet-without-parameters.md) 本部分介绍如何创建一个 cmdlet，用于在不使用参数的情况下从本地计算机检索信息，然后将该信息写入管道。

[添加处理 Command-Line 输入的参数](./adding-parameters-that-process-command-line-input.md) 本部分介绍如何将参数添加到 Get-Proc cmdlet，以便该 cmdlet 可以基于传递到 cmdlet 的显式对象处理输入。 此处所述的实现根据名称检索进程，然后将该信息写入管道。

[添加处理管道输入的参数](./adding-parameters-that-process-pipeline-input.md) 本部分介绍如何将参数添加到 Get-Proc cmdlet，以便该 cmdlet 可以处理通过管道传递给它的对象。 此处所述的实现 cmdlet 检索基于传递到 cmdlet 的对象的进程，然后将该信息写入管道。

[将非终止错误报告添加到 Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) 本部分介绍如何将非终止错误报告添加到 cmdlet。 此处所述的实现检测在处理输入时出现的非终止错误，并将错误记录写入错误流。

## <a name="see-also"></a>另请参阅

[创建不具有参数的 Cmdlet](./creating-a-cmdlet-without-parameters.md)

[添加处理 Command-Line 输入的参数](./adding-parameters-that-process-command-line-input.md)

[添加用于处理管道输入的参数](./adding-parameters-that-process-pipeline-input.md)

[将非终止错误报告添加到 Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
