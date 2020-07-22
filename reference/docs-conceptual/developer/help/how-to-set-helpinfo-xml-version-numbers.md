---
title: 如何设置 HelpInfo XML 版本号
ms.date: 09/12/2016
ms.openlocfilehash: 42164f98414da0b6f1a0021e9d860c57a63a9eec
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892976"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a>如何设置 HelpInfo XML 版本号

本主题说明如何设置和增加可更新帮助信息文件（通常称为 "HelpInfo XML 文件"）中的版本号。

## <a name="how-to-set-helpinfo-xml-version-numbers"></a>如何设置 HelpInfo XML 版本号

HelpInfo XML 文件中的版本号对于可更新帮助的操作至关重要。 只有当远程 HelpInfo XML 文件中的 UI 区域性的版本号大于本地 HelpInfo XML 中该 UI 区域性的版本号时，或没有本地 HelpInfo XML 文件时， [update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)和[get-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 才会下载新的帮助文件。

HelpInfo XML 文件使用由四个部分构成的版本号，该版本号在 Microsoft .NET Framework 的**system.web**类中定义。 格式为 `N1.N2.N3.N4`。 模块作者可以使用**System**类允许的任何版本编号方案。 仅当将该 UI 区域性的新版本的 CAB 文件上传到 HelpInfo XML 文件中的**HelpContentURI**元素所指定的位置时，可更新帮助才需要增加 ui 区域性的版本号。

下面的示例演示了德语（de） UI 区域性的 HelpInfo XML 文件的元素（在版本为2.15.0.10 时）。

```xml
<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

UI 区域性的版本号反映了该 UI 区域性的 CAB 文件的版本。 版本号适用于整个 CAB 文件。 不能为 CAB 文件中的不同文件设置不同的版本号。 每个 UI 区域性的版本号是独立计算的，无需与模块支持的其他 UI 区域性的版本号相关。
