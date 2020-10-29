---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 其他有用的脚本对象
description: 本文介绍提供 Windows PowerShell ISE 中的其他脚本编写功能的对象。
ms.openlocfilehash: c20daa0045bc07b1f21aafa42a80ce7c47ee7331
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500260"
---
# <a name="other-useful-scripting-objects"></a><span data-ttu-id="09da7-104">其他有用的脚本对象</span><span class="sxs-lookup"><span data-stu-id="09da7-104">Other Useful Scripting Objects</span></span>

<span data-ttu-id="09da7-105">以下对象提供 Windows PowerShell ISE 中的其他脚本编写功能。</span><span class="sxs-lookup"><span data-stu-id="09da7-105">The following objects provide additional scripting functionality in Windows PowerShell ISE.</span></span> <span data-ttu-id="09da7-106">它们不属于 **$psISE** 层次结构。</span><span class="sxs-lookup"><span data-stu-id="09da7-106">They are not part of the **$psISE** hierarchy.</span></span>

## <a name="useful-scripting-objects"></a><span data-ttu-id="09da7-107">有用的脚本对象</span><span class="sxs-lookup"><span data-stu-id="09da7-107">Useful Scripting objects</span></span>

### <a name="psunsupportedconsoleapplications"></a><span data-ttu-id="09da7-108">$psUnsupportedConsoleApplications</span><span class="sxs-lookup"><span data-stu-id="09da7-108">$psUnsupportedConsoleApplications</span></span>

<span data-ttu-id="09da7-109">在 Windows PowerShell ISE 如何与控制台应用程序交互方面存在一些限制。</span><span class="sxs-lookup"><span data-stu-id="09da7-109">There are some limitations on how Windows PowerShell ISE interacts with console applications.</span></span> <span data-ttu-id="09da7-110">需要用户干预的命令或自动化脚本可能无法像从 Windows PowerShell 控制台那样工作。</span><span class="sxs-lookup"><span data-stu-id="09da7-110">A command or an automation script that requires user intervention might not work the way it works from the Windows PowerShell console.</span></span> <span data-ttu-id="09da7-111">你可能想阻止这些命令或脚本在 Windows PowerShell ISE 命令窗格中运行。</span><span class="sxs-lookup"><span data-stu-id="09da7-111">You might want to block these commands or scripts from running in the Windows PowerShell ISE Command pane.</span></span> <span data-ttu-id="09da7-112">**$PsUnsupportedConsoleApplications** 对象保留此类命令的列表。</span><span class="sxs-lookup"><span data-stu-id="09da7-112">The **$psUnsupportedConsoleApplications** object keeps a list of such commands.</span></span> <span data-ttu-id="09da7-113">如果你尝试运行此列表中的命令，你将收到它们不受支持的消息。</span><span class="sxs-lookup"><span data-stu-id="09da7-113">If you try to run the commands in this list, you get a message that they are not supported.</span></span> <span data-ttu-id="09da7-114">下面的脚本将向该列表添加一个条目。</span><span class="sxs-lookup"><span data-stu-id="09da7-114">The following script adds an entry to the list.</span></span>

```powershell
# List the unsupported commands
$psUnsupportedConsoleApplications

# Add a command to this list
$psUnsupportedConsoleApplications.Add('Mycommand')

# Show the augmented list of commands
$psUnsupportedConsoleApplications
```

### <a name="pslocalhelp"></a><span data-ttu-id="09da7-115">$psLocalHelp</span><span class="sxs-lookup"><span data-stu-id="09da7-115">$psLocalHelp</span></span>

<span data-ttu-id="09da7-116">这是维护帮助主题和本地已编译的 HTML 帮助文件中和其关联链接之间的上下文相关映射的字典对象。</span><span class="sxs-lookup"><span data-stu-id="09da7-116">This is a dictionary object that maintains a context-sensitive mapping between Help topics and their associated links in the local compiled HTML Help file.</span></span> <span data-ttu-id="09da7-117">它用于查找有关某个特定主题的本地帮助。</span><span class="sxs-lookup"><span data-stu-id="09da7-117">It is used to locate the local Help for a particular topic.</span></span> <span data-ttu-id="09da7-118">你可以添加或删除此列表中的主题。</span><span class="sxs-lookup"><span data-stu-id="09da7-118">You can add or delete topics from this list.</span></span> <span data-ttu-id="09da7-119">下面的代码示例显示了 `$psLocalHelp` 中包含的一些示例键值对。</span><span class="sxs-lookup"><span data-stu-id="09da7-119">The following code example shows some example key-value pairs that are contained in `$psLocalHelp`.</span></span>

```powershell
# See the local help map
$psLocalHelp | Format-List
```

```Output
Key   : Add-Computer
Value : WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm

Key   : Add-Content
Value : WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm
```

<span data-ttu-id="09da7-120">下面的脚本将向该列表添加一个条目。</span><span class="sxs-lookup"><span data-stu-id="09da7-120">The following script adds an entry to the list.</span></span>

```powershell
$psLocalHelp.Add("get-myNoun", "c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a><span data-ttu-id="09da7-121">$psOnlineHelp</span><span class="sxs-lookup"><span data-stu-id="09da7-121">$psOnlineHelp</span></span>

<span data-ttu-id="09da7-122">这是维护帮助主题的主题标题和其关联外部 URL 之间的上下文相关映射的字典对象。</span><span class="sxs-lookup"><span data-stu-id="09da7-122">This is a dictionary object that maintains a context-sensitive mapping between topic titles of Help topics and their associated external URLs.</span></span> <span data-ttu-id="09da7-123">它用于查找 Web 上有关某个特定主题的帮助。</span><span class="sxs-lookup"><span data-stu-id="09da7-123">It is used to locate the Help for a particular topic on the web.</span></span> <span data-ttu-id="09da7-124">你可以添加或删除此列表中的主题。</span><span class="sxs-lookup"><span data-stu-id="09da7-124">You can add or delete topics from this list.</span></span>

```powershell
$psOnlineHelp | Format-List
```

```Output
Key   : Add-Computer
Value : https://go.microsoft.com/fwlink/p/?LinkID=135194

Key   : Add-Content
Value : https://go.microsoft.com/fwlink/p/?LinkID=113278
```

<span data-ttu-id="09da7-125">下面的脚本将向该列表添加一个条目。</span><span class="sxs-lookup"><span data-stu-id="09da7-125">The following script adds an entry to the list.</span></span>

```powershell
$psOnlineHelp.Add("get-myNoun", "https://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a><span data-ttu-id="09da7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09da7-126">See Also</span></span>

[<span data-ttu-id="09da7-127">Windows PowerShell ISE 脚本对象模型的用途</span><span class="sxs-lookup"><span data-stu-id="09da7-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
