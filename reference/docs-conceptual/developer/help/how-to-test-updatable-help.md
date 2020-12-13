---
ms.date: 09/12/2016
ms.topic: reference
title: 如何测试可更新帮助
description: 如何测试可更新帮助
ms.openlocfilehash: 47873089bfa1b918ea9970915e829a22aa7254c5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667617"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="7c9cd-103">如何测试可更新帮助</span><span class="sxs-lookup"><span data-stu-id="7c9cd-103">How to Test Updatable Help</span></span>

<span data-ttu-id="7c9cd-104">本主题介绍用于测试模块的可更新帮助的方法。</span><span class="sxs-lookup"><span data-stu-id="7c9cd-104">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="7c9cd-105">使用 Verbose 检测错误</span><span class="sxs-lookup"><span data-stu-id="7c9cd-105">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="7c9cd-106">为模块上载 HelpInfo XML 文件和 CAB 文件后，通过运行带有 **Verbose** 参数的 [update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)命令来测试文件。</span><span class="sxs-lookup"><span data-stu-id="7c9cd-106">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="7c9cd-107">**Verbose** 参数 `Update-Help` 用于报告其操作中的关键步骤，从读取模块清单中的 **HelpInfoUri** 键到验证解压缩后的 CAB 文件中的文件类型，并将文件放在特定于语言的模块目录中。</span><span class="sxs-lookup"><span data-stu-id="7c9cd-107">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="7c9cd-108">解析所有详细消息后， `Update-Help` 使用 **Debug** 参数运行命令。</span><span class="sxs-lookup"><span data-stu-id="7c9cd-108">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span>
<span data-ttu-id="7c9cd-109">此参数应检测可更新帮助文件的任何其他问题。</span><span class="sxs-lookup"><span data-stu-id="7c9cd-109">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
