---
ms.date: 05/22/2020
keywords: powershell,cmdlet
title: 如何使用 PowerShell 文档
ms.openlocfilehash: 259eb1eea1dc7e8b5ae5730f97c938b838a320bf
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808259"
---
# <a name="how-to-use-the-powershell-documentation"></a>如何使用 PowerShell 文档

欢迎使用 PowerShell 联机文档。 此站点包含以下 PowerShell 版本的 cmdlet 参考：

- PowerShell 7
- PowerShell 6
- PowerShell 5.1

## <a name="finding-articles-and-selecting-a-version"></a>查找文章并选择版本

有两种方法可以搜索 Docs 中的内容。最简单的方法是使用版本选取器下的筛选器框。 只需输入文章标题中出现的字词即可。 该页面显示匹配文章的列表。 还可以从该列表中选择用于搜索整个站点的选项。

默认情况下，此站点显示最新版本的 PowerShell 的文档。 一些 cmdlet 在不同版本的 PowerShell 中的工作方式有所不同。 确保查看所使用的 PowerShell 版本的文档。

使用页面顶部的版本选取器来选择所需的 PowerShell 版本。

![版本选取器](media/how-to-use-docs/version-search.gif)

可以通过查看 `$PSversionTable.PSVersion` 值来验证所使用的 PowerShell 版本。 下面的示例演示 Windows PowerShell v5.1 的输出。

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      18362  145
```

## <a name="finding-articles-for-previous-versions"></a>在文章中查找历史版本

旧版 PowerShell 的相关文档已存档到我们的[历史版本](https://aka.ms/PSLegacyDocs)网站中。

此网站包含下列主题的文档：

- PowerShell 3.0
- PowerShell 4.0
- PowerShell 5.0
- PowerShell 工作流
- PowerShell Web 访问
