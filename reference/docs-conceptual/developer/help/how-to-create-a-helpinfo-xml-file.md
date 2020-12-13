---
ms.date: 09/13/2016
ms.topic: reference
title: 如何创建 HelpInfo XML 文件
description: 如何创建 HelpInfo XML 文件
ms.openlocfilehash: d5a24306aa6488fdefad0b7b1ea9e2978a93a7b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647710"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a>如何创建 HelpInfo XML 文件

本部分中的主题介绍如何创建和填充帮助信息文件（通常称为 "HelpInfo XML 文件"）以获取 PowerShell 可更新的帮助功能。

## <a name="helpinfo-xml-file-overview"></a>HelpInfo XML 文件概述

HelpInfo XML 文件是有关模块的可更新帮助的主要信息来源。 它包括模块的帮助文件的位置、支持的 UI 区域性以及可更新帮助用于确定用户是否具有最新帮助文件的版本号。

每个模块都只有一个 HelpInfo XML 文件，即使该模块包含多个 UI 区域性的多个帮助文件也是如此。 模块作者创建 HelpInfo XML 文件，并将其放置在由模块清单中的 **HelpInfoUri** 键指定的 internet 位置。 当模块帮助文件更新并上传时，模块作者将更新 HelpInfo XML 文件，并将原始 HelpInfo XML 文件替换为新版本。

仔细维护 HelpInfo XML 文件非常重要。 如果上传新文件，但忘记增加版本号，则可更新帮助不会将新文件下载到用户的计算机。 如果为新的 UI 区域性添加帮助文件，但不更新 HelpInfo XML 文件或将其放在正确的位置，则可更新的帮助将不会下载新文件。

## <a name="in-this-section"></a>在本节中

本部分包括以下主题。

- [HelpInfo XML 架构](./helpinfo-xml-schema.md)

- [HelpInfo XML 示例文件](./helpinfo-xml-sample-file.md)

- [如何命名 HelpInfo XML 文件](./how-to-name-a-helpinfo-xml-file.md)

- [如何设置 HelpInfo XML 版本号](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a>另请参阅

[支持可更新帮助](./supporting-updatable-help.md)
