---
title: 如何测试可更新帮助 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: 8dd3770a60ca56634ad1eb1ac8cf89d96c975c90
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560502"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="8be3d-102">如何测试可更新帮助</span><span class="sxs-lookup"><span data-stu-id="8be3d-102">How to Test Updatable Help</span></span>

<span data-ttu-id="8be3d-103">本主题介绍用于测试模块的可更新帮助的方法。</span><span class="sxs-lookup"><span data-stu-id="8be3d-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="8be3d-104">使用 Verbose 检测错误</span><span class="sxs-lookup"><span data-stu-id="8be3d-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="8be3d-105">为模块上载 HelpInfo XML 文件和 CAB 文件后，通过运行带有**Verbose**参数的[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)命令来测试文件。</span><span class="sxs-lookup"><span data-stu-id="8be3d-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="8be3d-106">**Verbose**参数 `Update-Help` 用于报告其操作中的关键步骤，从读取模块清单中的**HelpInfoUri**键到验证解压缩后的 CAB 文件中的文件类型，并将文件放在特定于语言的模块目录中。</span><span class="sxs-lookup"><span data-stu-id="8be3d-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="8be3d-107">解析所有详细消息后， `Update-Help` 使用**Debug**参数运行命令。</span><span class="sxs-lookup"><span data-stu-id="8be3d-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span> <span data-ttu-id="8be3d-108">此参数应检测可更新帮助文件的任何其他问题。</span><span class="sxs-lookup"><span data-stu-id="8be3d-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
