---
author: sdwheeler
ms.author: sewhee
ms.date: 11/18/2020
ms.topic: include
ms.prod: powershell
ms.openlocfilehash: 700021715729254f5704abca16c0e18f598efaec
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "96913265"
---
> [!IMPORTANT]
> 自 2020 年 4 月起，PowerShell 库已不再支持传输层安全性 (TLS) 版本 1.0 和 1.1。 如果你使用的不是 TLS 1.2 或更高版本，那么，在尝试访问 PowerShell 库时，将会收到错误。 使用以下命令可以确定使用的是 TLS 1.2：
>
> ```powershell
> [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
> ```
>
> 有关详细信息，请参阅 PowerShell 博客中的[公告](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/)。
