---
title: 显示错误信息 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774569"
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

有关错误类别的详细信息，请参阅[Windows PowerShell 错误记录](./windows-powershell-error-records.md)。

## <a name="see-also"></a>另请参阅

[Windows PowerShell 错误记录](./windows-powershell-error-records.md)

[编写 Windows PowerShell Cmdlet](./writing-a-windows-powershell-cmdlet.md)
