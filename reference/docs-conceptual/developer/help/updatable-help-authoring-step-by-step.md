---
title: 可更新的帮助创作-分步
ms.date: 09/13/2016
ms.openlocfilehash: c9214be3c3363a4e6354595b50cf76a17d49aa67
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893112"
---
# <a name="updatable-help-authoring-step-by-step"></a>可更新帮助创作：分步指南

此文档列出了创作可更新帮助的过程中的步骤。

## <a name="authoring-updatable-help-step-by-step"></a>创作可更新帮助：分步

可更新的帮助是为最终用户设计的，但它还为模块作者和帮助编写人员提供了极大的优势，包括添加内容、修复错误、在多个 UI 区域性中交付以及响应用户注释和请求的能力，长时间已发送到模块。 本主题介绍如何打包和上传帮助文件，以便用户可以使用[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)和[get-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 下载和安装帮助文件。

以下步骤概述了支持可更新帮助的过程。

### <a name="step-1-find-an-internet-site-for-your-help-files"></a>步骤1：查找帮助文件的 internet 站点

创建可更新帮助的第一步是在 internet 位置查找模块的帮助文件。 实际上，可以使用两个不同的位置。 可以在一个 internet 位置将模块的帮助信息文件（HelpInfo XML）保存在一个 internet 位置，并将帮助内容 CAB 文件保留在另一个 internet 位置。 模块的所有帮助内容 CAB 文件都必须位于同一位置。 可以将不同模块的帮助内容 CAB 文件放置在同一位置。

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a>步骤2：将 HelpInfoURI 键添加到模块清单

将**HelpInfoURI**键添加到模块清单中。 键的值是模块的 HelpInfo XML 信息文件位置的统一资源标识符（URI）。 为安全，该地址必须以 "http" 或 "https" 开头。 URI 应指定 internet 位置，但不得包含 HelpInfo XML 文件名。

例如：

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'https://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a>步骤3：创建 HelpInfo XML 文件

HelpInfo XML 信息文件包含帮助文件的 internet 位置的 URI，以及每个受支持的 UI 区域性中的模块的最新帮助文件的版本号。 每个 Windows PowerShell 模块都有一个 HelpInfo XML 文件。 更新帮助文件时，请编辑或替换 HelpInfo XML 文件;不添加另一个。 有关详细信息，请参阅[如何创建 HELPINFO XML 文件](./how-to-create-a-helpinfo-xml-file.md)。

### <a name="step-4-create-cab-files"></a>步骤4：创建 CAB 文件

使用创建 cabinet 文件（）的工具（ `.cab` 如） `MakeCab.exe` 创建包含模块帮助文件的 cab 文件。 为每个支持的 UI 区域性中的帮助文件创建单独的 CAB 文件。 有关详细信息，请参阅[如何准备可更新的帮助 CAB 文件](./how-to-prepare-updatable-help-cab-files.md)。

### <a name="step-5-upload-your-files"></a>步骤5：上传文件

若要发布新的或更新的帮助文件，请将 CAB 文件上传到 HelpInfo XML 文件中的**HelpContentUri**元素所指定的 internet 位置。 然后，将 HelpInfo XML 文件上传到由模块清单中的**HelpInfoUri**键的值指定的 internet 位置。
