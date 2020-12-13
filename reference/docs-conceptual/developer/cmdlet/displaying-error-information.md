---
ms.date: 09/13/2016
ms.topic: reference
title: 显示错误信息
description: 显示错误信息
ms.openlocfilehash: 37a3adb91d0e616a5c7f27bcab866f8da139f969
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653047"
---
# <a name="displaying-error-information"></a>显示错误信息

本主题讨论用户显示错误信息的方式。

当 cmdlet 遇到错误时，默认情况下，将显示错误信息，这与以下错误输出类似。

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

但是，用户可以通过将变量设置为来按类别查看错误 `$ErrorView` `"CategoryView"` 。 类别视图显示来自错误记录的特定信息，而不是错误的自由文本说明。 如果要扫描的错误的列表很长，此视图会很有用。 在类别视图中，以前的错误消息显示如下。

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

有关错误类别的详细信息，请参阅 [Windows PowerShell 错误记录](./windows-powershell-error-records.md)。

## <a name="see-also"></a>另请参阅

[Windows PowerShell 错误记录](./windows-powershell-error-records.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
