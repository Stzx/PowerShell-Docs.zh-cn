---
title: 如何命名 HelpInfo XML 文件
ms.date: 09/12/2016
ms.openlocfilehash: 9505a7f66852a569d25ac0c1be86e68f870a7930
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892925"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a>如何命名 HelpInfo XML 文件

本主题介绍可更新帮助信息文件（通常称为 HelpInfo XML 文件）所需的名称格式。

## <a name="how-to-name-a-helpinfo-xml-file"></a>如何命名 HelpInfo XML 文件

HelpInfo XML 文件必须具有以下格式的名称。

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

名称的元素如下所示。

- `<ModuleName>`- [Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 返回的**ModuleInfo**对象的**Name**属性的值。

- `<ModuleGUID>`-模块清单中的**GUID**键的值。

例如，如果模块名称为 "TestModule"，并且模块 GUID 为 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9，则该模块的 HelpInfo XML 文件的名称将为：

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
