---
description: 介绍如何使用 "使用 PowerShell 运行" 功能从文件系统驱动器运行脚本。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: c5b1ca5d924c6eddd6371a269f694a5304510b25
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200362"
---
# <a name="about-run-with-powershell"></a><span data-ttu-id="78684-104">关于在 PowerShell 中运行</span><span class="sxs-lookup"><span data-stu-id="78684-104">About Run With PowerShell</span></span>

## <a name="short-description"></a><span data-ttu-id="78684-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="78684-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="78684-106">介绍如何使用 "使用 PowerShell 运行" 功能从文件系统驱动器运行脚本。</span><span class="sxs-lookup"><span data-stu-id="78684-106">Explains how to use the "Run with PowerShell" feature to run a script from a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="78684-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="78684-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="78684-108">从 Windows PowerShell 3.0 开始，你可以使用 "使用 PowerShell 运行" 功能，通过 Windows 8 和 Windows Server 2012 和 windows 资源管理器中的 windows 资源管理器在 windows 的早期版本中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="78684-108">Beginning in Windows PowerShell 3.0, you can use the "Run with PowerShell" feature to run scripts from File Explorer in Windows 8 and Windows Server 2012 and from Windows Explorer in earlier versions of Windows.</span></span>

<span data-ttu-id="78684-109">"使用 PowerShell 运行" 功能旨在运行没有必需参数的脚本，不会将输出返回到命令提示符。</span><span class="sxs-lookup"><span data-stu-id="78684-109">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="78684-110">当你使用 "使用 PowerShell 运行" 功能时，PowerShell 控制台窗口仅出现短暂的情况（如果有）。</span><span class="sxs-lookup"><span data-stu-id="78684-110">When you use the "Run with PowerShell" feature, the PowerShell console window appears only briefly, if at all.</span></span> <span data-ttu-id="78684-111">你无法与它交互。</span><span class="sxs-lookup"><span data-stu-id="78684-111">You cannot interact with it.</span></span>

<span data-ttu-id="78684-112">若要使用 "使用 PowerShell 运行" 功能：</span><span class="sxs-lookup"><span data-stu-id="78684-112">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="78684-113">在文件资源管理器 (或 Windows 资源管理器) 中，右键单击脚本文件名，然后选择 "用 PowerShell 运行"。</span><span class="sxs-lookup"><span data-stu-id="78684-113">In File Explorer (or Windows Explorer), right-click the script file name and then select "Run with PowerShell".</span></span>

<span data-ttu-id="78684-114">"使用 PowerShell 运行" 功能将启动具有 "绕过" 执行策略的 PowerShell 会话，运行该脚本并关闭会话。</span><span class="sxs-lookup"><span data-stu-id="78684-114">The "Run with PowerShell" feature starts a PowerShell session that has an execution policy of Bypass, runs the script, and closes the session.</span></span>

<span data-ttu-id="78684-115">它运行以下格式的命令：</span><span class="sxs-lookup"><span data-stu-id="78684-115">It runs a command that has the following format:</span></span>

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

<span data-ttu-id="78684-116">"使用 PowerShell 运行" 设置仅对会话 () 在其中运行脚本的 PowerShell 进程的当前实例的绕过执行策略。</span><span class="sxs-lookup"><span data-stu-id="78684-116">"Run with PowerShell" sets the Bypass execution policy only for the session (the current instance of the PowerShell process) in which the script runs.</span></span>
<span data-ttu-id="78684-117">此功能不会更改计算机或用户的执行策略。</span><span class="sxs-lookup"><span data-stu-id="78684-117">This feature does not change the execution policy for the computer or the user.</span></span>

<span data-ttu-id="78684-118">"使用 PowerShell 运行" 功能仅受 AllSigned 执行策略的影响。</span><span class="sxs-lookup"><span data-stu-id="78684-118">The "Run with PowerShell" feature is affected only by the AllSigned execution policy.</span></span> <span data-ttu-id="78684-119">如果 AllSigned 执行策略对计算机或用户有效，则 "通过 PowerShell 运行" 仅运行签名脚本。</span><span class="sxs-lookup"><span data-stu-id="78684-119">If the AllSigned execution policy is effective for the computer or the user, "Run with PowerShell" runs only signed scripts.</span></span> <span data-ttu-id="78684-120">任何其他执行策略都不会影响 "使用 PowerShell 运行"。</span><span class="sxs-lookup"><span data-stu-id="78684-120">"Run with PowerShell" is not affected by any other execution policy.</span></span> <span data-ttu-id="78684-121">有关详细信息，请参阅 [about_Execution_Policies](about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="78684-121">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="78684-122">疑难解答说明： "用 PowerShell 运行" 命令可能会提示您确认执行策略更改。</span><span class="sxs-lookup"><span data-stu-id="78684-122">Troubleshooting Note: Run with PowerShell command might prompt you to confirm the execution policy change.</span></span>

## <a name="see-also"></a><span data-ttu-id="78684-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78684-123">SEE ALSO</span></span>

[<span data-ttu-id="78684-124">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="78684-124">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="78684-125">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="78684-125">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="78684-126">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="78684-126">about_Scripts</span></span>](about_Scripts.md)
