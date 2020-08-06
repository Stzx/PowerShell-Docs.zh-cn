---
title: Windows PowerShell 错误报告 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7f7afcf5186732734976304c8e58e4d940156e1e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783953"
---
# <a name="windows-powershell-error-reporting"></a>Windows PowerShell 错误报告

本部分中的主题讨论了 cmdlet 报告错误的方式。

## <a name="in-this-section"></a>本节内容

[错误报告概念](./error-reporting-concepts.md)介绍 cmdlet 可用于报告错误的两种机制。

[终止错误](./terminating-errors.md)描述用于报告终止错误的方法，在此方法中，可以从 cmdlet 内调用此方法，并在调用方法时由 Windows PowerShell 运行时返回异常。

[非终止错误](./non-terminating-errors.md)介绍用于报告非终止错误的方法，以及可以从 cmdlet 中调用该方法的位置。

[按类别显示错误信息](./displaying-error-information.md)讨论用户显示错误的方式。

[Windows PowerShell 错误记录](./windows-powershell-error-records.md)说明错误记录的组成部分。

[解释 ErrorRecord 对象](./interpreting-errorrecord-objects.md)讨论如何解释 ErrorRecord 对象。

## <a name="see-also"></a>另请参阅

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
