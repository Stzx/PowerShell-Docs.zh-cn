---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: 使用 Windows PowerShell 2.0 引擎
description: Windows PowerShell 2.0 引擎仅在当前脚本或主机程序无法运行时使用，因为必须在进行修改后，为 Windows PowerShell 2.0 编写并通过 CLR 2.0 编译的主机程序才能运行。
ms.openlocfilehash: 214b87b7314f31974801bb07f98ddea3b68008f0
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664001"
---
# <a name="using-the-windows-powershell-20-engine"></a><span data-ttu-id="a24dd-104">使用 Windows PowerShell 2.0 引擎</span><span class="sxs-lookup"><span data-stu-id="a24dd-104">Using the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="a24dd-105">Windows PowerShell 旨在能够与早期版本向后兼容。</span><span class="sxs-lookup"><span data-stu-id="a24dd-105">Windows PowerShell is designed to be backward compatible with previous versions.</span></span> <span data-ttu-id="a24dd-106">为 Windows PowerShell 2.0 编写的 cmdlet、提供程序、管理单元、模块以及脚本无需更改，即可在较新版本 Windows PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="a24dd-106">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 run unchanged in newer versions Windows PowerShell.</span></span> <span data-ttu-id="a24dd-107">但 Microsoft .NET Framework 4 更改了运行时激活策略。</span><span class="sxs-lookup"><span data-stu-id="a24dd-107">However, Microsoft .NET Framework 4 changed the runtime activation policy.</span></span>
<span data-ttu-id="a24dd-108">必须在通过 CLR 4.0（或更高版本）编译的新版本 Windows PowerShell 中进行修改后，为 Windows PowerShell 2.0 编写并通过公共语言运行时 (CLR) 2.0 编译的 Windows PowerShell 主机程序才能运行。</span><span class="sxs-lookup"><span data-stu-id="a24dd-108">Windows PowerShell host programs written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in new versions Windows PowerShell that are compiled with CLR 4.0 (or higher).</span></span>

<span data-ttu-id="a24dd-109">Windows PowerShell 2.0 引擎仅在当前脚本或主机程序无法运行时使用，因为它与 Windows PowerShell 5.1 不兼容。</span><span class="sxs-lookup"><span data-stu-id="a24dd-109">The Windows PowerShell 2.0 Engine is intended to be used only when an existing script or host program cannot run because it is incompatible with Windows PowerShell 5.1.</span></span> <span data-ttu-id="a24dd-110">这种情况的示例包括早期版本的 Exchange 或 SQL Server 模块。</span><span class="sxs-lookup"><span data-stu-id="a24dd-110">Examples of this include older versions of Exchange or SQL Server modules.</span></span> <span data-ttu-id="a24dd-111">这种情况很少见。</span><span class="sxs-lookup"><span data-stu-id="a24dd-111">Such cases are expected to be rare.</span></span>

<span data-ttu-id="a24dd-112">许多需要 Windows PowerShell 2.0 引擎的程序将自动启动。</span><span class="sxs-lookup"><span data-stu-id="a24dd-112">Many programs that require the Windows PowerShell 2.0 Engine start it automatically.</span></span> <span data-ttu-id="a24dd-113">这些说明适用于极少数需要手动启动该引擎的情况。</span><span class="sxs-lookup"><span data-stu-id="a24dd-113">These instructions are included for the rare situations in which you need to start the engine manually.</span></span>

## <a name="deprecation-and-security-concerns"></a><span data-ttu-id="a24dd-114">弃用和安全问题</span><span class="sxs-lookup"><span data-stu-id="a24dd-114">Deprecation and security concerns</span></span>

<span data-ttu-id="a24dd-115">Windows PowerShell 2.0 在 2017 年 8 月已弃用。</span><span class="sxs-lookup"><span data-stu-id="a24dd-115">Windows PowerShell 2.0 was deprecated in August, 2017.</span></span> <span data-ttu-id="a24dd-116">有关详细信息，请参阅 PowerShell 博客上的[公告][]。</span><span class="sxs-lookup"><span data-stu-id="a24dd-116">For more information, see the [announcement][] on the PowerShell blog.</span></span>

<span data-ttu-id="a24dd-117">Windows PowerShell 2.0 缺少版本 3、4 和 5 中新增的大量增强功能和安全功能。</span><span class="sxs-lookup"><span data-stu-id="a24dd-117">Windows PowerShell 2.0 is missing a significant amount of the hardening and security features added in versions 3, 4, and 5.</span></span> <span data-ttu-id="a24dd-118">我们强烈建议用户在可以提供帮助的情况下不要使用它。</span><span class="sxs-lookup"><span data-stu-id="a24dd-118">We highly, highly recommend that users not use it if they can help it.</span></span> <span data-ttu-id="a24dd-119">有关详细信息，请参阅 [Shell 和脚本语言安全性比较][]和 [PowerShell ♥ 蓝队][blueteam]。</span><span class="sxs-lookup"><span data-stu-id="a24dd-119">For more information, see [A Comparison of Shell and Scripting Language Security][] and [PowerShell ♥ the Blue Team][blueteam].</span></span>

## <a name="installing-and-enabling-required-programs"></a><span data-ttu-id="a24dd-120">安装和启用必需程序</span><span class="sxs-lookup"><span data-stu-id="a24dd-120">Installing and Enabling Required Programs</span></span>

<span data-ttu-id="a24dd-121">启动 Windows PowerShell 2.0 引擎之前，请先启用 Windows PowerShell 2.0 引擎和具有 Service Pack 1 的 Microsoft.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="a24dd-121">Before starting the Windows PowerShell 2.0 Engine, enable the Windows PowerShell 2.0 Engine and Microsoft .NET Framework 3.5 with Service Pack 1.</span></span> <span data-ttu-id="a24dd-122">有关说明，请参阅[安装 Windows PowerShell][]。</span><span class="sxs-lookup"><span data-stu-id="a24dd-122">For instructions, see [Installing Windows PowerShell][].</span></span>

<span data-ttu-id="a24dd-123">安装了 Windows Management Framework 3.0 或更高版本的系统上具备所有必需组件。</span><span class="sxs-lookup"><span data-stu-id="a24dd-123">Systems on which Windows Management Framework 3.0 or higher is installed have all of the required components.</span></span> <span data-ttu-id="a24dd-124">无需进行任何其他配置。</span><span class="sxs-lookup"><span data-stu-id="a24dd-124">No further configuration is necessary.</span></span> <span data-ttu-id="a24dd-125">有关安装 Windows Management Framework 的信息，请参阅[安装和配置 WMF][]。</span><span class="sxs-lookup"><span data-stu-id="a24dd-125">For information about installing Windows Management Framework, see [Install and configure WMF][].</span></span>

## <a name="how-to-start-the-windows-powershell-20-engine"></a><span data-ttu-id="a24dd-126">如何启动 Windows PowerShell 2.0 引擎</span><span class="sxs-lookup"><span data-stu-id="a24dd-126">How to start the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="a24dd-127">启动 Windows PowerShell 时，默认启动最新版本。</span><span class="sxs-lookup"><span data-stu-id="a24dd-127">When you start Windows PowerShell the newest version starts by default.</span></span> <span data-ttu-id="a24dd-128">要使用 Windows PowerShell 2.0 引擎启动 Windows PowerShell，请使用 `PowerShell.exe` 的版本参数。</span><span class="sxs-lookup"><span data-stu-id="a24dd-128">To start Windows PowerShell with the Windows PowerShell 2.0 Engine, use the Version parameter of `PowerShell.exe`.</span></span> <span data-ttu-id="a24dd-129">你可以在任何命令提示符（包括 Windows PowerShell 和 Cmd.exe）处运行该命令。</span><span class="sxs-lookup"><span data-stu-id="a24dd-129">You can run the command at any command prompt, including Windows PowerShell and Cmd.exe.</span></span>

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a><span data-ttu-id="a24dd-130">如何使用 Windows PowerShell 2.0 引擎启动远程会话</span><span class="sxs-lookup"><span data-stu-id="a24dd-130">How to start a remote session with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="a24dd-131">要在远程会话中运行 Windows PowerShell 2.0 引擎，请在加载 Windows PowerShell 2.0 引擎的远程计算机上创建会话配置（也称为“终结点”）。</span><span class="sxs-lookup"><span data-stu-id="a24dd-131">To run the Windows PowerShell 2.0 Engine in a remote session, create a session configuration (also known as an _endpoint_ ) on the remote computer that loads the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="a24dd-132">会话配置保存在远程计算机上，并且任何已获得授权的用户都可以将其用于创建使用 Windows PowerShell 2.0 引擎的会话。</span><span class="sxs-lookup"><span data-stu-id="a24dd-132">The session configuration is saved on the remote computer and can be used by any authorized user to create sessions that use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="a24dd-133">这是一项高级任务，通常由系统管理员执行。</span><span class="sxs-lookup"><span data-stu-id="a24dd-133">This is an advanced task that is typically performed by a system administrator.</span></span>

<span data-ttu-id="a24dd-134">以下过程使用 [Register-PSSessionConfiguration][] cmdlet 的 **PSVersion** 参数来创建使用 Windows PowerShell 2.0 引擎的会话配置。</span><span class="sxs-lookup"><span data-stu-id="a24dd-134">The following procedure uses the **PSVersion** parameter of the [Register-PSSessionConfiguration][] cmdlet to create a session configuration that uses the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="a24dd-135">你还可以使用 [New-PSSessionConfigurationFile][] cmdlet 的 **PowerShellVersion** 参数为加载 Windows PowerShell 2.0 引擎的会话创建会话配置文件，此外，你可以使用 [Set-PSSessionConfiguration][] 参数的 **PSVersion** 参数将会话配置更改为使用 Windows PowerShell 2.0 引擎。</span><span class="sxs-lookup"><span data-stu-id="a24dd-135">You can also use the **PowerShellVersion** parameter of the [New-PSSessionConfigurationFile][] cmdlet to create a session configuration file for a session that loads the Windows PowerShell 2.0 Engine and you can use the **PSVersion** parameter of the [Set-PSSessionConfiguration][] parameter to change a session configuration to use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="a24dd-136">有关会话配置文件的详细信息，请参阅 [about_Session_Configuration_Files][]。</span><span class="sxs-lookup"><span data-stu-id="a24dd-136">For more information about session configuration files, see [about_Session_Configuration_Files][].</span></span>
<span data-ttu-id="a24dd-137">有关设置和安全性等会话配置的信息，请参阅 [about_Session_Configurations][]。</span><span class="sxs-lookup"><span data-stu-id="a24dd-137">For information about session configurations, including setup and security, see [about_Session_Configurations][].</span></span>

### <a name="to-start-a-remote-windows-powershell-20-session"></a><span data-ttu-id="a24dd-138">启动远程 Windows PowerShell 2.0 会话</span><span class="sxs-lookup"><span data-stu-id="a24dd-138">To start a remote Windows PowerShell 2.0 session</span></span>

1. <span data-ttu-id="a24dd-139">要创建需要 Windows PowerShell 2.0 引擎的会话配置，请使用 `Register-PSSessionConfiguration` cmdlet 的 PSVersion 参数，其值为 `2.0`。</span><span class="sxs-lookup"><span data-stu-id="a24dd-139">To create a session configuration that requires the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet with a value of `2.0`.</span></span>
   <span data-ttu-id="a24dd-140">在计算机上的连接的“服务器端”或接收端运行此命令。</span><span class="sxs-lookup"><span data-stu-id="a24dd-140">Run this command on the computer at the "server side" or receiving end of the connection.</span></span>

   <span data-ttu-id="a24dd-141">下面的示例命令在 Server01 计算机上创建 PS2 会话配置。</span><span class="sxs-lookup"><span data-stu-id="a24dd-141">The following sample command creates the PS2 session configuration on the Server01 computer.</span></span> <span data-ttu-id="a24dd-142">要运行此命令，请使用“以管理员身份运行”选项启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a24dd-142">To run this command, start Windows PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. <span data-ttu-id="a24dd-143">要在使用 PS2 会话配置的 Server01 计算机上创建会话，请使用创建远程会话的 cmdlet（例如 \`New-PSSession cmdlet）的 ConfigurationName 参数。</span><span class="sxs-lookup"><span data-stu-id="a24dd-143">To create a session on the Server01 computer that uses the PS2 session configuration, use the **ConfigurationName** parameter of cmdlets that create a remote session, such as the \`New-PSSession cmdlet.</span></span>

   <span data-ttu-id="a24dd-144">使用会话配置的会话启动时，Windows PowerShell 2.0 引擎会自动加载到该会话中。</span><span class="sxs-lookup"><span data-stu-id="a24dd-144">When a session that uses the session configuration starts, the Windows PowerShell 2.0 Engine is automatically loaded into the session.</span></span>

   <span data-ttu-id="a24dd-145">下面的命令在使用 PS2 会话配置的 Server01 计算机上启动一个会话。</span><span class="sxs-lookup"><span data-stu-id="a24dd-145">The following command starts a session on the Server01 computer that uses the PS2 session configuration.</span></span> <span data-ttu-id="a24dd-146">该命令将该会话保存在 `$s` 变量中。</span><span class="sxs-lookup"><span data-stu-id="a24dd-146">The command saves the session in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a><span data-ttu-id="a24dd-147">如何使用 Windows PowerShell 2.0 引擎启动后台作业</span><span class="sxs-lookup"><span data-stu-id="a24dd-147">How to start a background job with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="a24dd-148">若要使用 Windows PowerShell 2.0 引擎启动后台作业，请使用 [Start-Job][] cmdlet 的 **PSVersion** 参数。</span><span class="sxs-lookup"><span data-stu-id="a24dd-148">To start a background job with the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the [Start-Job][] cmdlet.</span></span>

<span data-ttu-id="a24dd-149">下面的命令使用 Windows PowerShell 2.0 引擎启动后台作业</span><span class="sxs-lookup"><span data-stu-id="a24dd-149">The following command starts a background job with the Windows PowerShell 2.0 Engine</span></span>

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

<span data-ttu-id="a24dd-150">有关后台作业的详细信息，请参阅 [about_Jobs][]。</span><span class="sxs-lookup"><span data-stu-id="a24dd-150">For more information about background jobs, see [about_Jobs][].</span></span>

<!-- link references -->
[公告]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[announcement]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[Shell 和脚本语言安全性比较]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[A Comparison of Shell and Scripting Language Security]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[安装 Windows PowerShell]: install/Installing-Windows-PowerShell.md
[Installing Windows PowerShell]: install/Installing-Windows-PowerShell.md
[安装和配置 WMF]: wmf/setup/install-configure.md
[Install and configure WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfigurationFile
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
