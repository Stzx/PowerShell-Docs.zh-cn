---
ms.date: 06/12/2017
title: 库的 ScriptAnazlyer 规则配置文件
description: 介绍如何将 PowerShell ScriptAnalyzer 与 PowerShell 库集成。
ms.openlocfilehash: 3af710e8811f0fabfb02f5317d5b4ff9c320f29a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646765"
---
# <a name="scriptanalyzer-rule-profile-for-gallery"></a>库的 ScriptAnazlyer 规则配置文件

若要确保发布到 PowerShell 库中包的质量，可运行 [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) 规则确定提交的脚本中是否存在任何冲突。

可在 ScriptAnalyzer [GitHub](https://github.com/PowerShell/PSScriptAnalyzer/blob/development/Engine/Settings/PSGallery.psd1) 页面上找到正在运行的规则列表。
如存在任何有关所运行规则的问题，请联系 PowerShell 库管理员或打开问题进行 ScriptAnalyzer 分析。

在即将推出的发布版中，ScriptAnalyzer 结果将显示在库中每个单独包的页面中。 建议包所有者检查包，确保发布包中不存在任何严重错误。
