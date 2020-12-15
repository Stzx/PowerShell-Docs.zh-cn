---
ms.date: 12/01/2020
title: cmdlet 故障排除
description: 本文提供了有关使用 PowerShell 库排查错误的信息和步骤
ms.openlocfilehash: 980da8ea7b8a09513f33a9939d512c437b755d8d
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913312"
---
# <a name="troubleshooting-cmdlets"></a>cmdlet 故障排除

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>如何解决“警告：无法下载包‘你的包名称’”问题

收到 `Install-Module` 或 `Update-Module` 有时在某些计算机上失败的报告。 根据我们的调查，此问题与网络连接有关。 最近，我们更新了 NuGet 提供程序，使其可以可靠地下载包。 你可以按照以下说明安装 NuGet 提供程序的最新版本，然后安装或更新你的模块。 下面，我们使用“Azure”模块作为示例。

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a>所需的网络终结点

安装和更新 cmdlet 需要通过 Internet 访问连接 PowerShell 库使用的网络终结点。 请确保网络访问策略允许连接以下终结点。

- `psg-prod-eastus.azureedge.net` - CDN 主机名
- `az818661.vo.msecnd.net` - CDN 主机名
- `devopsgallerystorage.blob.core.windows.net` - 存储帐户主机名
- `*.powershellgallery.com` - 网站
- `go.microsoft.com` - 重定向服务

> [!NOTE]
> 当 PowerShell 库服务发生中断时，与 PowerShell 库进行交互的 cmdlet 可能会失败，并出现意外错误。 若要查看 PowerShell 库的当前状态，请参阅 GitHub 上的 [PowerShell 库状态](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md)页面。
