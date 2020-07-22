---
title: 可更新帮助 CAB 文件中允许的文件类型
ms.date: 03/22/2012
ms.openlocfilehash: 2a8e97edf8daaed915ea1a3e04565d996a2e15fd
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893129"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="fabec-102">可更新帮助 CAB 文件中允许的文件类型</span><span class="sxs-lookup"><span data-stu-id="fabec-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="fabec-103">默认情况下，未压缩的 CAB 文件内容限制为 1 GB。</span><span class="sxs-lookup"><span data-stu-id="fabec-103">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="fabec-104">若要绕过此限制，用户必须使用[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)和[Get-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlet 的**Force**参数。</span><span class="sxs-lookup"><span data-stu-id="fabec-104">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="fabec-105">若要确保从 internet 下载的帮助文件的安全性，可更新的 Help CAB 文件只能包含下面列出的文件类型。</span><span class="sxs-lookup"><span data-stu-id="fabec-105">To assure the security of help files that are downloaded from the internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="fabec-106">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet 根据帮助主题架构验证所有文件。</span><span class="sxs-lookup"><span data-stu-id="fabec-106">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="fabec-107">如果此 `Update-Help` cmdlet 遇到无效的文件或不是允许的类型，则它不会安装无效文件，并且不会在用户的计算机上停止从 CAB 安装文件。</span><span class="sxs-lookup"><span data-stu-id="fabec-107">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="fabec-108">基于 XML 的 cmdlet 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fabec-108">XML-based help topics for cmdlets.</span></span>
- <span data-ttu-id="fabec-109">基于 XML 的脚本和函数的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fabec-109">XML-based help topics for scripts and functions.</span></span>
- <span data-ttu-id="fabec-110">针对 PowerShell 提供程序的基于 XML 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="fabec-110">XML-based help topics for PowerShell providers.</span></span>
- <span data-ttu-id="fabec-111">基于文本的帮助主题，如 "关于" 主题。</span><span class="sxs-lookup"><span data-stu-id="fabec-111">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="fabec-112">当解压缩 CAB 时， [update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)会验证 cab 内容。</span><span class="sxs-lookup"><span data-stu-id="fabec-112">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="fabec-113">如果 `Update-Help` 在可更新的 HELP CAB 文件中查找不符合的文件类型，则会生成一个终止错误并停止该操作。</span><span class="sxs-lookup"><span data-stu-id="fabec-113">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="fabec-114">它不会从 CAB 中安装任何帮助文件，甚至不会从兼容的文件类型安装任何帮助文件。</span><span class="sxs-lookup"><span data-stu-id="fabec-114">It does not install any help files from the CAB, even those of compliant file types.</span></span>
