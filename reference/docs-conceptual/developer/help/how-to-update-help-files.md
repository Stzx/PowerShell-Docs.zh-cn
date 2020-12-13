---
ms.date: 09/12/2016
ms.topic: reference
title: 如何更新帮助文件
description: 如何更新帮助文件
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649583"
---
# <a name="how-to-update-help-files"></a>如何更新帮助文件

本主题说明如何为支持可更新帮助的模块更新帮助文件。

## <a name="updating-help-files"></a>正在更新帮助文件

更新帮助文件的原因有很多，例如，纠正错误、阐明概念、回答经常询问的问题、添加新文件，或者添加更好的更好的示例。

更新帮助文件：

1. 更改文件。
1. 将文件转换为其他 UI 区域性。
1. 对于每个 UI 区域性中的模块，收集所有帮助文件 (新的、更改和未更改的) 。
1. 对照 XML 架构验证文件。
1. 重新生成每个 UI 区域性的 CAB 文件。
1. 在 HelpInfo XML 文件中，为每个 UI 区域性递增 CAB 文件的版本号。
1. 将新的 CAB 文件上传到 HelpInfo XML 文件中的 **HelpContentUri** 元素的值指定的位置。 将较旧的 CAB 文件替换为新的 CAB 文件。
1. 将更新后的 HelpInfo XML 文件上传到模块清单中的 **HelpInfoUri** 键指定的位置。 用新文件替换旧的 HelpInfo XML 文件。
