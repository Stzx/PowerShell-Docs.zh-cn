---
title: 如何命名 HelpInfo XML 文件 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64e85b53-5aeb-4d6c-903c-af4ab62f11c1
caps.latest.revision: 7
ms.openlocfilehash: 45e8a5bb0066f38c82cd3be8ec881383befd9c85
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560570"
---
# <a name="how-to-name-a-helpinfo-xml-file"></a>如何命名 HelpInfo XML 文件

本主题介绍可更新帮助信息文件（通常称为 HelpInfo XML 文件）所需的名称格式。

## <a name="how-to-name-a-helpinfo-xml-file"></a>如何命名 HelpInfo XML 文件

HelpInfo XML 文件必须具有以下格式的名称。

`<ModuleName>_<ModuleGUID>_HelpInfo.xml`

名称的元素如下所示。

ModuleName[获取 Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet 返回的**ModuleInfo**对象的**Name**属性的值。

ModuleGUID 模块清单中**GUID**密钥的值。

例如，如果模块名称为 "TestModule"，并且模块 GUID 为 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9，则该模块的 HelpInfo XML 文件的名称将为：

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_HelpInfo.xml`
