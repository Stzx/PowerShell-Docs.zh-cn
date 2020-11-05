---
ms.date: 12/05/2019
keywords: powershell,cmdlet
title: 启动 Windows PowerShell
description: 本文介绍了启动各种版本的 PowerShell 的方式。
ms.openlocfilehash: 47da7d85c9f7e6966a7f7e809c77979cd24cf129
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664017"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="d26bf-104">启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d26bf-104">Starting Windows PowerShell</span></span>

<span data-ttu-id="d26bf-105">Windows PowerShell 是一个嵌入到多个主机中的脚本引擎 `.DLL`。</span><span class="sxs-lookup"><span data-stu-id="d26bf-105">Windows PowerShell is a scripting engine `.DLL` that's embedded into multiple hosts.</span></span> <span data-ttu-id="d26bf-106">启动的最常见主机是交互式命令行 `powershell.exe` 和交互式脚本环境 `powershell_ise.exe`。</span><span class="sxs-lookup"><span data-stu-id="d26bf-106">The most common hosts you'll start are the interactive command-line `powershell.exe` and the Interactive Scripting Environment `powershell_ise.exe`.</span></span>

<span data-ttu-id="d26bf-107">若要在 Windows Server&reg; 2012 R2、Windows&reg; 8.1、Windows Server 2012 和 Windows 8 上启动 Windows PowerShell&reg;，请参阅 [Windows 中的常见管理任务和导航](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="d26bf-107">To start Windows PowerShell&reg; on Windows Server&reg; 2012 R2, Windows&reg; 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation in Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span></span>

## <a name="powershell-core-has-renamed-binary"></a><span data-ttu-id="d26bf-108">PowerShell Core 已重命名二进制文件</span><span class="sxs-lookup"><span data-stu-id="d26bf-108">PowerShell Core has renamed binary</span></span>

<span data-ttu-id="d26bf-109">PowerShell Core（称为 PowerShell）为第 6 版及更高版本，采用开源代码并使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d26bf-109">PowerShell Core, referred to as PowerShell, is version 6 and higher that's open source and uses .NET Core.</span></span> <span data-ttu-id="d26bf-110">受支持的版本在 Windows、macOS 和 Linux 上可用。</span><span class="sxs-lookup"><span data-stu-id="d26bf-110">Supported versions are available on Windows, macOS, and Linux.</span></span>

<span data-ttu-id="d26bf-111">自 PowerShell 6 起，PowerShell 二进制文件已分别重命名为 `pwsh.exe`（适用于 Windows）和 `pwsh`（适用于 macOS 和 Linux）。</span><span class="sxs-lookup"><span data-stu-id="d26bf-111">Beginning in PowerShell 6, the PowerShell binary was renamed `pwsh.exe` for Windows and `pwsh` for macOS and Linux.</span></span> <span data-ttu-id="d26bf-112">可以使用 `pwsh-preview` 启动 PowerShell 预览版。</span><span class="sxs-lookup"><span data-stu-id="d26bf-112">You can start PowerShell preview versions using `pwsh-preview`.</span></span> <span data-ttu-id="d26bf-113">有关详细信息，请参阅 [PowerShell Core 6.0 中的新增功能](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe)和[关于 pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh)。</span><span class="sxs-lookup"><span data-stu-id="d26bf-113">For more information, see [What's New in PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) and [About pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh).</span></span>

<span data-ttu-id="d26bf-114">若要查找 PowerShell 7 的 cmdlet 参考文档和安装文档，请使用以下链接：</span><span class="sxs-lookup"><span data-stu-id="d26bf-114">To find cmdlet reference and installation documentation for PowerShell 7, use the following links:</span></span>

| <span data-ttu-id="d26bf-115">文档</span><span class="sxs-lookup"><span data-stu-id="d26bf-115">Document</span></span> | <span data-ttu-id="d26bf-116">链接</span><span class="sxs-lookup"><span data-stu-id="d26bf-116">Link</span></span> |
| ----- | ----- |
| <span data-ttu-id="d26bf-117">Cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="d26bf-117">Cmdlet reference</span></span> | [<span data-ttu-id="d26bf-118">PowerShell 模块浏览器</span><span class="sxs-lookup"><span data-stu-id="d26bf-118">PowerShell Module Browser</span></span>](/powershell/module/) |
| <span data-ttu-id="d26bf-119">Windows 安装</span><span class="sxs-lookup"><span data-stu-id="d26bf-119">Windows installation</span></span> | [<span data-ttu-id="d26bf-120">在 Windows 上安装 PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="d26bf-120">Installing PowerShell Core on Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows) |
| <span data-ttu-id="d26bf-121">macOS 安装</span><span class="sxs-lookup"><span data-stu-id="d26bf-121">macOS installation</span></span> | [<span data-ttu-id="d26bf-122">在 macOS 上安装 PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="d26bf-122">Installing PowerShell Core on macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos) |
| <span data-ttu-id="d26bf-123">Linux 安装</span><span class="sxs-lookup"><span data-stu-id="d26bf-123">Linux installation</span></span> | [<span data-ttu-id="d26bf-124">在 Linux 上安装 PowerShell Core</span><span class="sxs-lookup"><span data-stu-id="d26bf-124">Installing PowerShell Core on Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux) |

<span data-ttu-id="d26bf-125">若要查看其他 PowerShell 版本的相关内容，请参阅[如何使用 PowerShell 文档](../how-to-use-docs.md)。</span><span class="sxs-lookup"><span data-stu-id="d26bf-125">To view content for other PowerShell versions, see [How to use the PowerShell documentation](../how-to-use-docs.md).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="d26bf-126">如何在早期版本的 Windows 上启动 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d26bf-126">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="d26bf-127">本部分介绍了如何在 Windows&reg; 7、Windows Server&reg; 2008 R2 和 Windows Server&reg; 2008 上启动 Windows PowerShell 和 Windows PowerShell 集成脚本环境 (ISE)。</span><span class="sxs-lookup"><span data-stu-id="d26bf-127">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows&reg; 7, Windows Server&reg; 2008 R2, and Windows Server&reg; 2008.</span></span> <span data-ttu-id="d26bf-128">还介绍了如何在 Windows Server&reg; 2008 R2 和 Windows Server&reg; 2008 上的 Windows PowerShell 2.0 中启用 Windows PowerShell ISE 的可选功能。</span><span class="sxs-lookup"><span data-stu-id="d26bf-128">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server&reg; 2008 R2 and Windows Server&reg; 2008.</span></span>

<span data-ttu-id="d26bf-129">使用以下任一方法来启动已安装的 Windows PowerShell 3.0 或 Windows PowerShell 4.0 版本（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="d26bf-129">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="d26bf-130">在“开始”菜单中</span><span class="sxs-lookup"><span data-stu-id="d26bf-130">From the Start Menu</span></span>

- <span data-ttu-id="d26bf-131">单击“开始”，键入 **PowerShell** ，然后单击“Windows PowerShell”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-131">Click **Start** , type **PowerShell** , and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="d26bf-132">在“开始”菜单中，依次单击“开始”、“所有程序”、“附件”、“Windows PowerShell”文件夹，然后单击“Windows PowerShell”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-132">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="d26bf-133">在命令提示符处</span><span class="sxs-lookup"><span data-stu-id="d26bf-133">At the Command Prompt</span></span>

<span data-ttu-id="d26bf-134">在 cmd.exe、Windows PowerShell 或 Windows PowerShell ISE 中，若要启动 Windows PowerShell，请键入：</span><span class="sxs-lookup"><span data-stu-id="d26bf-134">In **cmd.exe** , Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="d26bf-135">你还可以使用 `powershell.exe` 程序的参数来自定义会话。</span><span class="sxs-lookup"><span data-stu-id="d26bf-135">You can also use the parameters of the `powershell.exe` program to customize the session.</span></span> <span data-ttu-id="d26bf-136">有关详细信息，请参阅 [PowerShell.exe 命令行帮助](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe)。</span><span class="sxs-lookup"><span data-stu-id="d26bf-136">For more information, see [PowerShell.exe Command-Line Help](/powershell/module/Microsoft.PowerShell.Core/About/about_PowerShell_exe).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="d26bf-137">使用管理权限（以管理员身份运行）</span><span class="sxs-lookup"><span data-stu-id="d26bf-137">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="d26bf-138">单击“ **开始** ”，键入 **PowerShell** ，右键单击“ **Windows PowerShell** ”，然后单击“ **以管理员身份运行** ”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-138">Click **Start** , type **PowerShell** , right-click **Windows PowerShell** , and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="d26bf-139">如何在早期版本的 Windows 上启动 Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="d26bf-139">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="d26bf-140">使用以下任一方法启动 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="d26bf-140">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="d26bf-141">在“开始”菜单中</span><span class="sxs-lookup"><span data-stu-id="d26bf-141">From the Start Menu</span></span>

- <span data-ttu-id="d26bf-142">单击“开始”，键入 **ISE** ，然后单击“Windows PowerShell ISE”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-142">Click **Start** , type **ISE** , and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="d26bf-143">在“开始”菜单中，依次单击“开始”、“所有程序”、“附件”、“Windows PowerShell”文件夹，然后单击“Windows PowerShell ISE”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-143">From the **Start** menu, click **Start** , click **All Programs** , click **Accessories** , click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="d26bf-144">在命令提示符处</span><span class="sxs-lookup"><span data-stu-id="d26bf-144">At the Command Prompt</span></span>

<span data-ttu-id="d26bf-145">在 `cmd.exe`、Windows PowerShell 或 Windows PowerShell ISE 中，若要启动 Windows PowerShell，请键入：</span><span class="sxs-lookup"><span data-stu-id="d26bf-145">In `cmd.exe`, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="d26bf-146">或</span><span class="sxs-lookup"><span data-stu-id="d26bf-146">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="d26bf-147">使用管理权限（以管理员身份运行）</span><span class="sxs-lookup"><span data-stu-id="d26bf-147">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="d26bf-148">单击“ **开始** ”，键入 **ISE** ，右键单击“ **Windows PowerShell ISE** ”，然后单击“ **以管理员身份运行** ”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-148">Click **Start** , type **ISE** , right-click **Windows PowerShell ISE** , and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="d26bf-149">如何在早期版本的 Windows 上启用 Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="d26bf-149">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="d26bf-150">在 Windows PowerShell 4.0 和 Windows PowerShell 3.0 中，默认情况下，所有版本的 Windows 上都启用 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="d26bf-150">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="d26bf-151">如果尚未启用，则 Windows Management Framework 4.0 或 Windows Management Framework 3.0 会启用它。</span><span class="sxs-lookup"><span data-stu-id="d26bf-151">If it isn't already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="d26bf-152">在 Windows PowerShell 2.0 中，默认情况下，在 Windows 7 上启用 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="d26bf-152">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="d26bf-153">但是，在 Windows Server 2008 R2 和 Windows Server 2008 上，它是一项可选功能。</span><span class="sxs-lookup"><span data-stu-id="d26bf-153">However, on Windows Server 2008 R2 and Windows Server 2008, it's an optional feature.</span></span>

<span data-ttu-id="d26bf-154">若要启用 Windows Server 2008 R2 或 Windows Server 2008 上的 Windows PowerShell 2.0 中的 Windows PowerShell ISE，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="d26bf-154">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="d26bf-155">启用 Windows PowerShell 集成脚本环境 (ISE)</span><span class="sxs-lookup"><span data-stu-id="d26bf-155">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="d26bf-156">启动服务器管理器。</span><span class="sxs-lookup"><span data-stu-id="d26bf-156">Start Server Manager.</span></span>
2. <span data-ttu-id="d26bf-157">单击“功能”，然后单击“添加功能”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-157">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="d26bf-158">在“选择功能”中，单击“Windows PowerShell 集成脚本环境 (ISE)”</span><span class="sxs-lookup"><span data-stu-id="d26bf-158">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="d26bf-159">启动 32 位版本的 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d26bf-159">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="d26bf-160">在 64 位计算机 ( **Windows PowerShell (x86)** ) 上安装 Windows PowerShell 时，除 64 位版之外，还将安装 32 位版本的 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d26bf-160">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)** , a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="d26bf-161">运行 Windows PowerShell 时，默认运行 64 位版。</span><span class="sxs-lookup"><span data-stu-id="d26bf-161">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="d26bf-162">但是，有时可能需要运行 Windows PowerShell (x86)，例如使用需要 32 位版本的模块时，或者远程连接到 32 位计算机时。</span><span class="sxs-lookup"><span data-stu-id="d26bf-162">However, you might occasionally need to run **Windows PowerShell (x86)** , such as when you're using a module that requires the 32-bit version or when you're connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="d26bf-163">若要启动 32 位版本的 Windows PowerShell，请使用以下任何过程。</span><span class="sxs-lookup"><span data-stu-id="d26bf-163">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-serverreg-2012-r2"></a><span data-ttu-id="d26bf-164">在 Windows Server&reg; 2012 R2 中</span><span class="sxs-lookup"><span data-stu-id="d26bf-164">In Windows Server&reg; 2012 R2</span></span>

- <span data-ttu-id="d26bf-165">在“开始”屏幕上，键入 **Windows PowerShell (x86)** 。</span><span class="sxs-lookup"><span data-stu-id="d26bf-165">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="d26bf-166">单击“Windows PowerShell x86”磁贴。</span><span class="sxs-lookup"><span data-stu-id="d26bf-166">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="d26bf-167">在“服务器管理器”中，从“工具”菜单中选择“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-167">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-168">在桌面上，将光标移动到右上角，单击“搜索”，键入 **PowerShell x86** ，然后单击“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-168">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-169">通过命令行，输入：`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="d26bf-169">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-serverreg-2012"></a><span data-ttu-id="d26bf-170">在 Windows Server&reg; 2012 中</span><span class="sxs-lookup"><span data-stu-id="d26bf-170">In Windows Server&reg; 2012</span></span>

- <span data-ttu-id="d26bf-171">在“开始”屏幕上，键入 **PowerShell** ，然后单击“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-171">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-172">在“服务器管理器”中，从“工具”菜单中选择“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-172">In **Server Manager** , from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-173">在桌面上，将光标移动到右上角，单击“搜索”，键入 **PowerShell** ，然后单击“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-173">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-174">通过命令行，输入：`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="d26bf-174">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-81"></a><span data-ttu-id="d26bf-175">在 Windows&reg; 8.1 中</span><span class="sxs-lookup"><span data-stu-id="d26bf-175">In Windows&reg; 8.1</span></span>

- <span data-ttu-id="d26bf-176">在“开始”屏幕上，键入 **Windows PowerShell (x86)** 。</span><span class="sxs-lookup"><span data-stu-id="d26bf-176">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="d26bf-177">单击“Windows PowerShell x86”磁贴。</span><span class="sxs-lookup"><span data-stu-id="d26bf-177">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="d26bf-178">如果你正在运行 Windows 8.1 的[远程服务器管理工具](https://go.microsoft.com/fwlink/?LinkID=304145)，则也可从“服务器管理器工具”菜单中打开 Windows PowerShell x86。</span><span class="sxs-lookup"><span data-stu-id="d26bf-178">If you're running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="d26bf-179">选择“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-179">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-180">在桌面上，将光标移动到右上角，单击“搜索”，键入 **PowerShell x86** ，然后单击“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-180">On the desktop, move the cursor to the upper right corner, click **Search** , type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-181">通过命令行，输入：`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="d26bf-181">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windowsreg-8"></a><span data-ttu-id="d26bf-182">在 Windows&reg; 8 中</span><span class="sxs-lookup"><span data-stu-id="d26bf-182">In Windows&reg; 8</span></span>

- <span data-ttu-id="d26bf-183">在“开始”屏幕上，将光标移动到右上角，依次单击“设置”、“磁贴”，然后将“显示管理工具”滑块移动到“是”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-183">On the **Start** screen, move the cursor to the upper right corner, click **Settings** , click **Tiles** , and then move the **Show Administrative Tools** slider to **Yes**.</span></span> <span data-ttu-id="d26bf-184">然后，键入 **PowerShell** ，单击“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-184">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-185">如果你正在运行 Windows 8 的[远程服务器管理工具](https://www.microsoft.com/download/details.aspx?id=28972)，则也可从“服务器管理器工具”菜单中打开 Windows PowerShell x86。</span><span class="sxs-lookup"><span data-stu-id="d26bf-185">If you're running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="d26bf-186">选择“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-186">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-187">在“开始”屏幕或桌面上，键入 **PowerShell (x86)** ，然后单击“Windows PowerShell (x86)”。</span><span class="sxs-lookup"><span data-stu-id="d26bf-187">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="d26bf-188">通过命令行，输入：`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="d26bf-188">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>
