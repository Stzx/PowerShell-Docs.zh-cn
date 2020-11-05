---
ms.date: 06/12/2017
title: cmdlet 故障排除
description: 本文提供了有关使用 PowerShell 库排查错误的信息和步骤
ms.openlocfilehash: db9e58c185c6f3bca26ff3639af85fa2dba48909
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661056"
---
# <a name="troubleshooting-cmdlets"></a>cmdlet 故障排除

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>如何解决“警告：无法下载包‘你的包名称’”问题

收到 `Install-Module` 或 `Update-Module` 有时在某些计算机上失败的报告。 根据我们的调查，此问题与网络连接有关。 最近，我们更新了 NuGet 提供程序，使其可以可靠地下载包。 你可以按照以下说明安装 NuGet 提供程序的最新版本，然后安装或更新你的模块。 下面，我们使用“Azure”模块作为示例。

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a>所需的网络终结点

安装和更新 cmdlet 需要通过 Internet 访问连接 PowerShell 库使用的网络终结点。 请确保网络访问策略允许连接以下终结点。

- oneget.org
- go.microsoft.com
- az818661.vo.msecnd.net
- www.powershellgallery.com
- devopsgallerystorage.blob.core.windows.net
