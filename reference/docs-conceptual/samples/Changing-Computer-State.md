---
ms.date: 12/23/2019
keywords: powershell,cmdlet
title: 更改计算机状态
description: 本示例演示如何使用 PowerShell 中的外部命令管理计算机的配置。
ms.openlocfilehash: 341f29f24d7e4bd341ccc0954b16d4b75880678b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500668"
---
# <a name="changing-computer-state"></a><span data-ttu-id="77214-104">更改计算机状态</span><span class="sxs-lookup"><span data-stu-id="77214-104">Changing Computer State</span></span>

<span data-ttu-id="77214-105">若要在 PowerShell 中重置计算机，请使用标准命令行工具、WMI 或 CIM 类。</span><span class="sxs-lookup"><span data-stu-id="77214-105">To reset a computer in PowerShell, use either a standard command-line tool, WMI, or a CIM class.</span></span>
<span data-ttu-id="77214-106">尽管你使用 PowerShell 仅仅是为了运行该工具，但了解如何在 PowerShell 中更改计算机的电源状态将阐明有关在 PowerShell 中使用外部工具的一些重要详细信息。</span><span class="sxs-lookup"><span data-stu-id="77214-106">Although you are using PowerShell only to run the tool, learning how to change a computer's power state in PowerShell illustrates some of the important details about working with external tools in PowerShell.</span></span>

## <a name="locking-a-computer"></a><span data-ttu-id="77214-107">锁定计算机</span><span class="sxs-lookup"><span data-stu-id="77214-107">Locking a Computer</span></span>

<span data-ttu-id="77214-108">使用标准可用工具直接锁定计算机的唯一方法是调用 **user32.dll** 中的 **LockWorkstation()** 函数：</span><span class="sxs-lookup"><span data-stu-id="77214-108">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll** :</span></span>

```powershell
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="77214-109">此命令将立即锁定工作站。</span><span class="sxs-lookup"><span data-stu-id="77214-109">This command immediately locks the workstation.</span></span> <span data-ttu-id="77214-110">它使用 rundll32.exe，后者运行 Windows DLL（并保存其库以便重复使用）以运行 `user32.dll`（Windows 管理函数的库）。</span><span class="sxs-lookup"><span data-stu-id="77214-110">It uses **rundll32.exe** , which runs Windows DLLs (and saves their libraries for repeated use) to run `user32.dll`, a library of Windows management functions.</span></span>

<span data-ttu-id="77214-111">如果在启用了“快速用户切换”时锁定工作站（例如在 Windows XP 中），则计算机将显示用户登录屏幕，而不会启动当前用户的屏幕保护程序。</span><span class="sxs-lookup"><span data-stu-id="77214-111">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="77214-112">若要关闭终端服务器上的特定会话，请使用 **tsshutdn.exe** 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="77214-112">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

## <a name="logging-off-the-current-session"></a><span data-ttu-id="77214-113">注销当前会话</span><span class="sxs-lookup"><span data-stu-id="77214-113">Logging Off the Current Session</span></span>

<span data-ttu-id="77214-114">可以使用多种不同的方法来注销本地系统上的会话。</span><span class="sxs-lookup"><span data-stu-id="77214-114">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="77214-115">最简单的方法是使用远程桌面/终端服务命令行工具 logoff.exe（若要了解有关详细信息，请在 PowerShell 提示符处键入 `logoff /?`）。</span><span class="sxs-lookup"><span data-stu-id="77214-115">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the PowerShell prompt, type `logoff /?`).</span></span> <span data-ttu-id="77214-116">若要注销当前活动会话，请键入 `logoff` 而不带参数。</span><span class="sxs-lookup"><span data-stu-id="77214-116">To log off the current active session, type `logoff` with no arguments.</span></span>

<span data-ttu-id="77214-117">你还可以使用具 **shutdown.exe** 工具及其 logoff 选项：</span><span class="sxs-lookup"><span data-stu-id="77214-117">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```powershell
shutdown.exe -l
```

<span data-ttu-id="77214-118">另一种方法是使用 WMI。</span><span class="sxs-lookup"><span data-stu-id="77214-118">Another option is to use WMI.</span></span> <span data-ttu-id="77214-119">Win32_OperatingSystem 类具有 Shutdown 方法。</span><span class="sxs-lookup"><span data-stu-id="77214-119">The **Win32_OperatingSystem** class has a **Shutdown** method.</span></span>
<span data-ttu-id="77214-120">调用具有 0 标志的方法将启动注销：</span><span class="sxs-lookup"><span data-stu-id="77214-120">Invoking the method with the 0 flag initiates logoff:</span></span>

<span data-ttu-id="77214-121">有关 Shutdown 方法的详细信息，请参阅 [Win32_OperatingSystem 类的 Shutdown 方法](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)</span><span class="sxs-lookup"><span data-stu-id="77214-121">For more information about the **Shutdown** method, see [Shutdown method of the Win32_OperatingSystem class](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)</span></span>

```powershell
Get-CimInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="77214-122">关闭或重启计算机</span><span class="sxs-lookup"><span data-stu-id="77214-122">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="77214-123">关闭和重启计算机通常是相同类型的任务。</span><span class="sxs-lookup"><span data-stu-id="77214-123">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="77214-124">关闭计算机的工具通常也可以重启计算机，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="77214-124">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="77214-125">从 PowerShell 重启计算机有两个直接的选项。</span><span class="sxs-lookup"><span data-stu-id="77214-125">There are two straightforward options for restarting a computer from PowerShell.</span></span> <span data-ttu-id="77214-126">使用 tsshutdn.exe 或 shutdown.exe 及其相应参数。</span><span class="sxs-lookup"><span data-stu-id="77214-126">Use either **tsshutdn.exe** or **shutdown.exe** with appropriate arguments.</span></span> <span data-ttu-id="77214-127">你可以从 `tsshutdn.exe /?` 或 `shutdown.exe /?` 获取详细的使用信息。</span><span class="sxs-lookup"><span data-stu-id="77214-127">You can get detailed usage information from `tsshutdn.exe /?` or `shutdown.exe /?`.</span></span>

<span data-ttu-id="77214-128">也可以直接从 PowerShell 执行关闭和重启操作。</span><span class="sxs-lookup"><span data-stu-id="77214-128">You can also perform shutdown and restart operations directly from PowerShell as well.</span></span>

<span data-ttu-id="77214-129">要关闭计算机，请使用 Stop-Computer 命令</span><span class="sxs-lookup"><span data-stu-id="77214-129">To shut down the computer, use the Stop-Computer command</span></span>

```powershell
Stop-Computer
```

<span data-ttu-id="77214-130">要重启操作系统，请使用 Restart-Computer 命令</span><span class="sxs-lookup"><span data-stu-id="77214-130">To restart the operating system, use the Restart-Computer command</span></span>

```powershell
Restart-Computer
```

<span data-ttu-id="77214-131">要强制立即重新启动计算机，请使用 -Force 参数。</span><span class="sxs-lookup"><span data-stu-id="77214-131">To force an immediate restart of the computer, use the -Force parameter.</span></span>

```powershell
Restart-Computer -Force
```
