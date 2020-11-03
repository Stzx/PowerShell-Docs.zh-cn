---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 附录 2 - 创建自定义 PowerShell 快捷方式
description: 下面的过程描述如何创建对多个方便的选项进行了自定义的 Windows PowerShell 快捷方式。
ms.openlocfilehash: abdab517dec1357050bf431b6f2e35311ad49976
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500719"
---
# <a name="appendix-2---creating-a-custom-powershell-shortcut"></a><span data-ttu-id="5c036-104">附录 2 - 创建自定义 PowerShell 快捷方式</span><span class="sxs-lookup"><span data-stu-id="5c036-104">Appendix 2 - Creating a Custom PowerShell Shortcut</span></span>

<span data-ttu-id="5c036-105">下面的过程描述如何创建对多个方便的选项进行了自定义的 Windows PowerShell 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="5c036-105">The following procedure describes how to create a shortcut to Windows PowerShell that has several convenient options customized.</span></span>

1. <span data-ttu-id="5c036-106">创建指向 Powershell.exe 的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="5c036-106">Create a shortcut that points to Powershell.exe.</span></span>

1. <span data-ttu-id="5c036-107">右键单击该快捷方式，然后单击“ **属性** ”。</span><span class="sxs-lookup"><span data-stu-id="5c036-107">Right-click the shortcut, and then click **Properties**.</span></span>

1. <span data-ttu-id="5c036-108">单击“ **选项** ”选项卡。</span><span class="sxs-lookup"><span data-stu-id="5c036-108">Click the **Options** tab.</span></span>

1. <span data-ttu-id="5c036-109">在“编辑选项”部分中，选中“QuickEdit”复选框。</span><span class="sxs-lookup"><span data-stu-id="5c036-109">In the **Edit Options** section, select the **QuickEdit** check box.</span></span>

    <span data-ttu-id="5c036-110">此设置让你能够通过拖动鼠标左键在 Windows PowerShell 控制台窗口中选择文本，它还允许你通过按 ENTER 或右键单击鼠标将文本复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="5c036-110">This setting lets you select text in the Windows PowerShell console window by dragging the left  mouse button, and it lets you copy text to the clipboard by pressing ENTER or by right-clicking  the mouse.</span></span>

1. <span data-ttu-id="5c036-111">在“编辑选项”部分中，选中“插入模式”复选框。</span><span class="sxs-lookup"><span data-stu-id="5c036-111">In the **Edit Options** section, select the **Insert Mode** check box.</span></span> <span data-ttu-id="5c036-112">此设置让你能够通过在控制台窗口中右键单击来自动粘贴剪贴板中的文本。</span><span class="sxs-lookup"><span data-stu-id="5c036-112">This setting lets you right-click in the console window to automatically paste text from the clipboard.</span></span>

1. <span data-ttu-id="5c036-113">在“命令历史记录”部分中，在“缓冲区大小”框中键入或选择一个介于 1 和 999 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="5c036-113">In the **Command History** section, type or select a number between 1 and 999 in the **Buffer Size** box.</span></span> <span data-ttu-id="5c036-114">这将设置要保存在控制台缓冲区中的已键入命令数。</span><span class="sxs-lookup"><span data-stu-id="5c036-114">This sets the number of typed commands that will be kept in the console buffer.</span></span>

1. <span data-ttu-id="5c036-115">在“命令历史记录”部分中，选中“丢弃旧的副本”复选框以清除控制台缓存区中的重复命令。</span><span class="sxs-lookup"><span data-stu-id="5c036-115">In the **Command History** section, select the **Discard Old Duplicates** check box to eliminate repeated commands from the console buffer.</span></span>

1. <span data-ttu-id="5c036-116">单击“布局”选项卡。 </span><span class="sxs-lookup"><span data-stu-id="5c036-116">Click the **Layout** tab.</span></span>

1. <span data-ttu-id="5c036-117">在“屏幕缓冲区”部分中，在“高度”框中键入一个介于 1 和 9999 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="5c036-117">In the **Screen Buffer** section, type a number between 1 and 9999 in the **Height** box.</span></span> <span data-ttu-id="5c036-118">该高度表示已缓冲输出的行数。</span><span class="sxs-lookup"><span data-stu-id="5c036-118">The height represents the number of lines of output that are buffered.</span></span> <span data-ttu-id="5c036-119">这是滚过控制台窗口时可查看的最大保留行数。</span><span class="sxs-lookup"><span data-stu-id="5c036-119">This is the maximum number of lines retained for viewing when you scroll through the console window.</span></span> <span data-ttu-id="5c036-120">如果此数字小于“窗口大小”部分中所示的高度，窗口大小高度将自动降低为相同的值。</span><span class="sxs-lookup"><span data-stu-id="5c036-120">If this number is lower than the height shown in the **Window size** section, the window size height will automatically be reduced to the same value.</span></span>

1. <span data-ttu-id="5c036-121">在“窗口大小”部分中，键入一个介于 1 和 9999 之间的数字用作宽度。</span><span class="sxs-lookup"><span data-stu-id="5c036-121">In the **Window Size** section, type a number between 1 and 9999 for the width.</span></span> <span data-ttu-id="5c036-122">这表示在控制台窗口中横向显示的字符数。</span><span class="sxs-lookup"><span data-stu-id="5c036-122">This represents the number of characters that are displayed across the console window.</span></span> <span data-ttu-id="5c036-123">默认宽度为 80，Windows PowerShell 的输出格式就是针对此宽度而设计。</span><span class="sxs-lookup"><span data-stu-id="5c036-123">The default width is 80, and Windows PowerShell's output formatting is designed for this width.</span></span>

1. <span data-ttu-id="5c036-124">如果你想要在控制台打开时将它放置在桌面上的某个特定点上，请清除“窗口位置”部分中的“由系统定位窗口”复选框，然后更改“窗口位置”部分中“左侧”和“顶部”框中的值    。</span><span class="sxs-lookup"><span data-stu-id="5c036-124">If you want to place the console at a particular point on the desktop when it is opened, clear  the **Let system position window** check box in the **Window position** section, and then change  the values in the **Left** and **Top** boxes in the **Window position** section.</span></span>

1. <span data-ttu-id="5c036-125">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="5c036-125">Click **OK**.</span></span>
