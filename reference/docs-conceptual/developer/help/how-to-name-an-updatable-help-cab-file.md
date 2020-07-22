---
title: 如何命名可更新帮助 CAB 文件
ms.date: 09/12/2016
ms.openlocfilehash: 42486461d92f1f6fcff452a4539edf5be7a66f22
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892993"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>如何命名可更新帮助 CAB 文件

本主题介绍可更新的帮助 cabinet （）文件所需的名称格式 `.CAB` 。

## <a name="how-to-name-an-updatable-help-cab-file"></a>如何命名可更新帮助 CAB 文件

可更新的 cabinet （ `.CAB` ）文件必须具有以下格式的名称。

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

名称的元素如下所示。

- `<ModuleName>`- [Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 返回的**ModuleInfo**对象的**Name**属性的值。
- `<ModuleGUID>`-模块清单中的**GUID**键的值。
- `<UICulture>`-CAB 文件中的帮助文件的 UI 区域性。 此值必须与模块的 HelpInfo XML 文件中的一个**UICulture**元素的值匹配。

例如，如果模块名称为 "TestModule"，则模块 GUID 为 9cabb9ad-f2ac 4914-a46b-bfc1bebf07f9，而 UI 区域性为 "en-us"，则 CAB 文件的名称将为：

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
