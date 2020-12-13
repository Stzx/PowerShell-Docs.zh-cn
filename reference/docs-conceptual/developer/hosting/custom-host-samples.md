---
ms.date: 09/13/2016
ms.topic: reference
title: 自定义主机示例
description: 自定义主机示例
ms.openlocfilehash: 939b9f5d6bbc3ccf1ac95343e897ecffef0a2f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649315"
---
# <a name="custom-host-samples"></a><span data-ttu-id="d64fa-103">自定义主机示例</span><span class="sxs-lookup"><span data-stu-id="d64fa-103">Custom Host Samples</span></span>

<span data-ttu-id="d64fa-104">本部分包含用于编写自定义主机的示例代码。</span><span class="sxs-lookup"><span data-stu-id="d64fa-104">This section includes sample code for writing a custom host.</span></span> <span data-ttu-id="d64fa-105">你可以使用 Microsoft Visual Studio 来创建控制台应用程序，然后将此部分中的主题中的代码复制到主机应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d64fa-105">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d64fa-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="d64fa-106">In This Section</span></span>

 <span data-ttu-id="d64fa-107">[Host01 示例](./host01-sample.md) 此示例演示如何实现使用基本自定义主机的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="d64fa-107">[Host01 Sample](./host01-sample.md) This sample shows how to implement a host application that uses a basic custom host.</span></span>

 <span data-ttu-id="d64fa-108">[Host02 示例](./host02-sample.md) 此示例演示如何编写使用 Windows PowerShell 运行时以及自定义主机实现的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="d64fa-108">[Host02 Sample](./host02-sample.md) This sample shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span> <span data-ttu-id="d64fa-109">主机应用程序将主机区域性设置为德语，运行 [获取过程](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet，并显示使用 pwrsh.exe 显示的结果，然后输出德语的当前数据和时间。</span><span class="sxs-lookup"><span data-stu-id="d64fa-109">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them using pwrsh.exe, and then prints out the current data and time in German.</span></span>

 <span data-ttu-id="d64fa-110">[Host03 示例](./host03-sample.md) 此示例演示如何生成基于控制台的交互式主机应用程序，该应用程序可从命令行读取命令，执行命令，然后将结果显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="d64fa-110">[Host03 Sample](./host03-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

 <span data-ttu-id="d64fa-111">[Host04 示例](./host04-sample.md) 此示例演示如何生成基于控制台的交互式主机应用程序，该应用程序可从命令行读取命令，执行命令，然后将结果显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="d64fa-111">[Host04 Sample](./host04-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="d64fa-112">此主机应用程序还支持显示允许用户指定多个选项的提示。</span><span class="sxs-lookup"><span data-stu-id="d64fa-112">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

 <span data-ttu-id="d64fa-113">[Host05 示例](./host05-sample.md) 此示例演示如何生成基于控制台的交互式主机应用程序，该应用程序可从命令行读取命令，执行命令，然后将结果显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="d64fa-113">[Host05 Sample](./host05-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="d64fa-114">此主机应用程序还支持通过使用 [Enter-pssession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) 和 [Exit-pssession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlet 对远程计算机进行调用</span><span class="sxs-lookup"><span data-stu-id="d64fa-114">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets</span></span>

 <span data-ttu-id="d64fa-115">[Host06 示例](./host06-sample.md) 此示例演示如何生成基于控制台的交互式主机应用程序，该应用程序可从命令行读取命令，执行命令，然后将结果显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="d64fa-115">[Host06 Sample](./host06-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="d64fa-116">此外，此示例还使用了 Tokenizer API 来指定用户输入的文本颜色。</span><span class="sxs-lookup"><span data-stu-id="d64fa-116">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="d64fa-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d64fa-117">See Also</span></span>
