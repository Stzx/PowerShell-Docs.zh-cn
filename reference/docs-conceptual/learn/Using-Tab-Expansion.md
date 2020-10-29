---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 使用 Tab 键扩展
description: 介绍如何使用 PowerShell 中的 Tab 键扩展功能。
ms.openlocfilehash: d3408aac8cc9325666082577a7b00bc3362bfca3
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500039"
---
# <a name="using-tab-expansion"></a><span data-ttu-id="17429-104">使用 Tab 键扩展</span><span class="sxs-lookup"><span data-stu-id="17429-104">Using Tab Expansion</span></span>

<span data-ttu-id="17429-105">Command-line Shell 通常提供一种方法来自动完成长文件或命令的名称，从而加快命令输入并给出提示。</span><span class="sxs-lookup"><span data-stu-id="17429-105">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing hints.</span></span> <span data-ttu-id="17429-106">使用 PowerShell，可通过按 Tab 键来填充文件名和 cmdlet 名称<kbd></kbd>。</span><span class="sxs-lookup"><span data-stu-id="17429-106">PowerShell allows you to fill in file names and cmdlet names by pressing the <kbd>Tab</kbd> key.</span></span>

> [!NOTE]
> <span data-ttu-id="17429-107">Tab 键扩展由内部函数 TabExpansion 或 TabExpansion2 控制。</span><span class="sxs-lookup"><span data-stu-id="17429-107">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="17429-108">由于此函数可被修改或覆盖，所以此讨论可用作针对默认 PowerShell 配置的行为的指导。</span><span class="sxs-lookup"><span data-stu-id="17429-108">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="17429-109">若要从可用选择中自动填充文件名或路径，键入部分名称并按下 <kbd>Tab</kbd> 键。</span><span class="sxs-lookup"><span data-stu-id="17429-109">To fill in a filename or path from the available choices automatically, type part of the name and press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="17429-110">PowerShell 会自动将名称扩展至找到的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="17429-110">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="17429-111">重复按下 <kbd>Tab</kbd> 将循环浏览所有可用选择。</span><span class="sxs-lookup"><span data-stu-id="17429-111">Pressing the <kbd>Tab</kbd> key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="17429-112">名称的 Tab 键扩展稍有不同。</span><span class="sxs-lookup"><span data-stu-id="17429-112">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="17429-113">若要在 cmdlet 名称上使用 Tab 键扩充，键入名称的整个第一部分（即谓词），然后是后跟的连字符。</span><span class="sxs-lookup"><span data-stu-id="17429-113">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="17429-114">你可以填入名称的更多内容以进行部分匹配。</span><span class="sxs-lookup"><span data-stu-id="17429-114">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="17429-115">例如，如果键入 `get-co` 然后按 Tab 键，PowerShell 会自动将其扩展为 `Get-Command` cmdlet（注意，还会将字母的大小写改为标准形式）<kbd></kbd>。</span><span class="sxs-lookup"><span data-stu-id="17429-115">For example, if you type `get-co` and then press the <kbd>Tab</kbd> key, PowerShell will automatically expand this to the `Get-Command` cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="17429-116">如果再次按 Tab 键，PowerShell 会将此替换为另一个唯一匹配的 cmdlet 名称 `Get-Content`<kbd></kbd>。</span><span class="sxs-lookup"><span data-stu-id="17429-116">If you press <kbd>Tab</kbd> key again, PowerShell replaces this with the only other matching cmdlet name, `Get-Content`.</span></span>

<span data-ttu-id="17429-117">你可以在同一行上重复使用 Tab 键扩展。</span><span class="sxs-lookup"><span data-stu-id="17429-117">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="17429-118">例如，可以通过输入以下内容在 `Get-Content` cmdlet 的名称上使用 tab 扩展：</span><span class="sxs-lookup"><span data-stu-id="17429-118">For example, you can use tab expansion on the name of the `Get-Content` cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="17429-119">当你按下 <kbd>Tab</kbd> 键时，该命令扩展为：</span><span class="sxs-lookup"><span data-stu-id="17429-119">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="17429-120">然后你可以部分指定“智能安装”日志文件的路径并再次使用选项卡扩展：</span><span class="sxs-lookup"><span data-stu-id="17429-120">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="17429-121">当你按下 <kbd>Tab</kbd> 键时，该命令扩展为：</span><span class="sxs-lookup"><span data-stu-id="17429-121">When you press the <kbd>Tab</kbd> key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="17429-122">Tab 键扩展进程的一个限制是 Tab 键始终解释为尝试完成单词。</span><span class="sxs-lookup"><span data-stu-id="17429-122">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="17429-123">如果将命令示例复制并粘贴到 PowerShell 控制台，请确保该示例不包含 Tab 键；如果包含 Tab 键，则结果将不可预测并且几乎不会得到预期的结果。</span><span class="sxs-lookup"><span data-stu-id="17429-123">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>
