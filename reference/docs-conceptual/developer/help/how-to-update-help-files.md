---
title: 如何更新帮助文件 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 35b3fd696419d0135fd6f662223e6c8586df443a
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811646"
---
# <a name="how-to-update-help-files"></a>如何更新帮助文件

本主题说明如何为支持可更新帮助的模块更新帮助文件。

## <a name="updating-help-files"></a>正在更新帮助文件

更新帮助文件的原因有很多，例如，纠正错误、阐明概念、回答经常询问的问题、添加新文件，或者添加更好的更好的示例。

更新帮助文件：

1. 更改文件。

2. 将文件转换为其他 UI 区域性。

3. 收集每个 UI 区域性中的模块的所有帮助文件（新增、更改和未更改）。

4. 对照 XML 架构验证文件。

5. 重新生成每个 UI 区域性的 CAB 文件。

6. 在 HelpInfo XML 文件中，为每个 UI 区域性递增 CAB 文件的版本号。

7. 将新的 CAB 文件上传到 HelpInfo XML 文件中的**HelpContentUri**元素的值指定的位置。 将较旧的 CAB 文件替换为新的 CAB 文件。

8. 将更新后的 HelpInfo XML 文件上传到模块清单中的**HelpInfoUri**键指定的位置。 用新文件替换旧的 HelpInfo XML 文件。
