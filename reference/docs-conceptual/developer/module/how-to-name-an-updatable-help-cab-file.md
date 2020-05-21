---
title: 如何为可更新的帮助 CAB 文件命名 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: a253f98d213f797a659affb1560907bb99a045d3
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560553"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a>如何命名可更新帮助 CAB 文件

本主题介绍可更新帮助 cabinet 的必需名称格式（。CAB）文件。

## <a name="how-to-name-an-updatable-help-cab-file"></a>如何命名可更新帮助 CAB 文件

可更新的 cabinet （。CAB）文件必须具有以下格式的名称。

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

名称的元素如下所示。

ModuleName[获取 Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 返回的**ModuleInfo**对象的**Name**属性的值。

ModuleGUID 模块清单中**GUID**密钥的值。

UICulture CAB 文件中的帮助文件的 UI 区域性。 此值必须与模块的 HelpInfo XML 文件中的一个**UICulture**元素的值匹配。

例如，如果模块名称为 "TestModule"，则模块 GUID 为 9cabb9ad-f2ac 4914-a46b-bfc1bebf07f9，而 UI 区域性为 "en-us"，则 CAB 文件的名称将为：

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`
