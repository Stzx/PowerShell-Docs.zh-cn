---
ms.date: 12/31/2019
title: ISESnippetCollection 对象
description: ISESnippetCollection 对象是 ISESnippet 对象的集合。 与 PowerShellTab 对象关联的文件集合是此类的成员。
ms.openlocfilehash: e6170ddf72d5ead840aa3015d4de1dcb21dbfeff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655972"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="25b72-104">ISESnippetCollection 对象</span><span class="sxs-lookup"><span data-stu-id="25b72-104">The ISESnippetCollection Object</span></span>

<span data-ttu-id="25b72-105">**ISESnippetCollection** 对象是 **ISESnippet** 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="25b72-105">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="25b72-106">与 **PowerShellTab** 对象关联的文件集合是此类的成员。</span><span class="sxs-lookup"><span data-stu-id="25b72-106">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="25b72-107">`$psISE.CurrentPowerShellTab.Files` 集合就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="25b72-107">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="25b72-108">方法</span><span class="sxs-lookup"><span data-stu-id="25b72-108">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="25b72-109">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="25b72-109">Load\( FilePathName \)</span></span>

<span data-ttu-id="25b72-110">在 Windows PowerShell ISE 3.0 和更高版本中受支持，但不存在于早期版本中。</span><span class="sxs-lookup"><span data-stu-id="25b72-110">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="25b72-111">加载包含用户定义的代码段的 `.snippets.ps1xml` 文件。</span><span class="sxs-lookup"><span data-stu-id="25b72-111">Loads a `.snippets.ps1xml` file that contains user-defined snippets.</span></span> <span data-ttu-id="25b72-112">创建代码段最简单的方法就是使用 `New-IseSnippet` cmdlet，后者会自动将它们存储在配置文件文件夹中，以便你每次启动 Windows PowerShell ISE 时进行加载。</span><span class="sxs-lookup"><span data-stu-id="25b72-112">The easiest way to create snippets is to use the `New-IseSnippet` cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="25b72-113">**FilePathName** - 字符串，包含代码段定义的 .snippets.ps1xml 文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="25b72-113">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="25b72-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25b72-114">See Also</span></span>

- [<span data-ttu-id="25b72-115">ISESnippet 对象</span><span class="sxs-lookup"><span data-stu-id="25b72-115">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="25b72-116">Windows PowerShell ISE 脚本对象模型的用途</span><span class="sxs-lookup"><span data-stu-id="25b72-116">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="25b72-117">ISE 对象模型层次结构</span><span class="sxs-lookup"><span data-stu-id="25b72-117">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
