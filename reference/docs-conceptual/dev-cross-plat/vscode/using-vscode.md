---
title: 使用 Visual Studio Code 进行 PowerShell 开发
description: 使用 Visual Studio Code 进行 PowerShell 开发
ms.date: 11/07/2019
ms.openlocfilehash: 8a4ceb3da669716915449af2d211aaf2ae61bb4f
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94390282"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="4bdb3-103">使用 Visual Studio Code 进行 PowerShell 开发</span><span class="sxs-lookup"><span data-stu-id="4bdb3-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="4bdb3-104">[Visual Studio Code][vscode] 是 Microsoft 开发的跨平台脚本编辑器。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-104">[Visual Studio Code][vscode] is a cross-platform script editor by Microsoft.</span></span> <span data-ttu-id="4bdb3-105">它与 [PowerShell 扩展][psext]相结合，提供了丰富的交互式脚本编辑体验，从而可以更轻松地编写可靠的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-105">Together with the [PowerShell extension][psext], it provides a rich and interactive script editing experience, making it easier to write reliable PowerShell scripts.</span></span> <span data-ttu-id="4bdb3-106">建议使用带有 PowerShell 扩展的 Visual Studio Code 编辑器来编写 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-106">Visual Studio Code with the PowerShell extension is the recommended editor for writing PowerShell scripts.</span></span>

<span data-ttu-id="4bdb3-107">它支持以下 PowerShell 版本：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-107">It supports the following PowerShell versions:</span></span>

- <span data-ttu-id="4bdb3-108">PowerShell 7 及更高版本（Windows、macOS 和 Linux）</span><span class="sxs-lookup"><span data-stu-id="4bdb3-108">PowerShell 7 and up (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="4bdb3-109">PowerShell Core 6（Windows、macOS 和 Linux）</span><span class="sxs-lookup"><span data-stu-id="4bdb3-109">PowerShell Core 6 (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="4bdb3-110">Windows PowerShell 5.1（仅限 Windows）</span><span class="sxs-lookup"><span data-stu-id="4bdb3-110">Windows PowerShell 5.1 (Windows-only)</span></span>

> [!NOTE]
> <span data-ttu-id="4bdb3-111">Visual Studio Code 与 [Visual Studio][] 不同。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-111">Visual Studio Code is not the same as [Visual Studio][].</span></span>

## <a name="getting-started"></a><span data-ttu-id="4bdb3-112">入门</span><span class="sxs-lookup"><span data-stu-id="4bdb3-112">Getting started</span></span>

<span data-ttu-id="4bdb3-113">开始前，请确保系统上安装有 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-113">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="4bdb3-114">有关 Windows、macOS 和 Linux 上的新式工作负荷，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-114">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="4bdb3-115">[在 Linux 上安装 PowerShell][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-115">[Installing PowerShell on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="4bdb3-116">[在 macOS 上安装 PowerShell][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-116">[Installing PowerShell on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="4bdb3-117">[在 Windows 上安装 PowerShell][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-117">[Installing PowerShell on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="4bdb3-118">有关传统 Windows PowerShell 工作负载，请参阅[安装 Windows PowerShell][install-winps]。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-118">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bdb3-119">[Windows PowerShell ISE][ise] 仍适用于 Windows。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-119">The [Windows PowerShell ISE][ise] is still available for Windows.</span></span> <span data-ttu-id="4bdb3-120">但是，它不再处于主动功能开发状态。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-120">However, it is no longer in active feature development.</span></span> <span data-ttu-id="4bdb3-121">ISE 不适用于 PowerShell 6 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-121">The ISE does not work with PowerShell 6 and higher.</span></span> <span data-ttu-id="4bdb3-122">作为 Windows 的一个组件，它仍会获得安全性和高优先级服务修补程序的官方支持。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-122">As a component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="4bdb3-123">我们没有从 Windows 中删除 ISE 的计划。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-123">We have no plans to remove the ISE from Windows.</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="4bdb3-124">使用 Visual Studio Code 进行编辑</span><span class="sxs-lookup"><span data-stu-id="4bdb3-124">Editing with Visual Studio Code</span></span>

1. <span data-ttu-id="4bdb3-125">安装 Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-125">Install Visual Studio Code.</span></span> <span data-ttu-id="4bdb3-126">有关详细信息，请参阅[设置 Visual Studio Code][vsc-setup] 概述。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-126">For more information, see the overview [Setting up Visual Studio Code][vsc-setup].</span></span>

   <span data-ttu-id="4bdb3-127">每个平台都有安装说明：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-127">There are installation instructions for each platform:</span></span>

   - <span data-ttu-id="4bdb3-128">**Windows**：按照 [在 Windows 上运行 Visual Studio Code][vsc-setup-win] 页面上的安装说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-128">**Windows**: follow the installation instructions on the [Running Visual Studio Code on Windows][vsc-setup-win] page.</span></span>
   - <span data-ttu-id="4bdb3-129">**macOS**：请按照 [在 macOS 上运行 Visual Studio Code][vsc-setup-macOS] 页面上的安装说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-129">**macOS**: follow the installation instructions on the [Running Visual Studio Code on macOS][vsc-setup-macOS] page.</span></span>
   - <span data-ttu-id="4bdb3-130">**Linux**：请按照 [在 Linux 上运行 Visual Studio Code][vsc-setup-linux] 页面上的安装说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-130">**Linux**: follow the installation instructions on the [Running Visual Studio Code on Linux][vsc-setup-linux] page.</span></span>

1. <span data-ttu-id="4bdb3-131">安装 PowerShell 扩展。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-131">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="4bdb3-132">通过在控制台中键入 `code` 或键入`code-insiders`（在安装 Visual Studio Code 预览体验成员的情况下）来启动 Visual Studio Code 应用。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-132">Launch the Visual Studio Code app by typing `code` in a console or `code-insiders` if you installed Visual Studio Code Insiders.</span></span>
   1. <span data-ttu-id="4bdb3-133">通过按 <kbd>Ctrl</kbd>+<kbd>P</kbd>，在 Windows 或 Linux 上启动“Quick Open”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-133">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="4bdb3-134">在 macOS 上，按 <kbd>Cmd</kbd>+<kbd>P</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-134">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="4bdb3-135">在“Quick Open”中，键入 `ext install powershell`，然后按 ENTER  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-135">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="4bdb3-136">“扩展”视图随即在侧边栏上打开  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-136">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="4bdb3-137">从 Microsoft 中选择 PowerShell 扩展。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-137">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="4bdb3-138">应会看到类似于下图的 Visual Studio Code 屏幕：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-138">You should see a Visual Studio Code screen similar to the following image:</span></span>

      ![Visual Studio Code - PowerShell 扩展的视图](media/using-vscode/vscode.png)

   1. <span data-ttu-id="4bdb3-140">在 Microsoft 下单击 PowerShell 扩展上的“安装”按钮  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-140">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="4bdb3-141">安装后，如果看到“安装”按钮变为“重载”   ，则单击“重载”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-141">After the install, if you see the **Install** button turn into **Reload**, Click on **Reload**.</span></span>
   1. <span data-ttu-id="4bdb3-142">重载 Visual Studio Code 后即可开始编辑。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-142">After Visual Studio Code has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="4bdb3-143">例如，若要创建新文件，请单击“文件”>“新建”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-143">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="4bdb3-144">若要保存，请单击“文件”>“保存”  ，然后提供文件名，例如 `HelloWorld.ps1`。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-144">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="4bdb3-145">若要关闭文件，请单击文件名旁的 `X`。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-145">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="4bdb3-146">若要退出 Visual Studio Code，请单击“文件”>“退出”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-146">To exit Visual Studio Code, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="4bdb3-147">在受限制的系统上安装 PowerShell 扩展</span><span class="sxs-lookup"><span data-stu-id="4bdb3-147">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="4bdb3-148">某些系统设置为要求验证所有代码签名。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-148">Some systems are set up to require validation of all code signatures.</span></span> <span data-ttu-id="4bdb3-149">可能看到以下错误：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-149">You may receive the following error:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="4bdb3-150">当 Windows 组策略设置 PowerShell 的执行策略时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-150">This problem can occur when PowerShell's execution policy is set by Windows Group Policy.</span></span> <span data-ttu-id="4bdb3-151">若要手动批准 PowerShell 编辑器服务和适用于 Visual Studio Code 的 PowerShell 扩展，则打开 PowerShell 提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-151">To manually approve PowerShell Editor Services and the PowerShell extension for Visual Studio Code, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="4bdb3-152">系统会提示你“是否要运行来自此不可信发布者的软件？” </span><span class="sxs-lookup"><span data-stu-id="4bdb3-152">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span> <span data-ttu-id="4bdb3-153">键入 `A` 以运行该文件。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-153">Type `A` to run the file.</span></span> <span data-ttu-id="4bdb3-154">然后打开 Visual Studio Code，并检查 PowerShell 扩展是否工作正常。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-154">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="4bdb3-155">如果在开始使用时仍有问题，请在 [GitHub 问题][]上告诉我们。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-155">If you still have problems getting started, let us know on [GitHub issues][].</span></span>

> [!NOTE]
> <span data-ttu-id="4bdb3-156">适用于 Visual Studio Code 的 PowerShell 扩展不支持在约束语言模式下运行。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-156">The PowerShell extension for Visual Studio Code does not support running in constrained language mode.</span></span> <span data-ttu-id="4bdb3-157">有关详细信息，请参阅 [GitHub 问题 #606][i606]。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-157">For more information, see [GitHub issue #606][i606].</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="4bdb3-158">选择要与扩展一起使用的 PowerShell 版本</span><span class="sxs-lookup"><span data-stu-id="4bdb3-158">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="4bdb3-159">将 PowerShell Core 与 Windows PowerShell 并行安装后，现在可以将特定版本的 PowerShell 与 PowerShell 扩展一起使用。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-159">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a specific version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="4bdb3-160">此功能通过不同操作系统上的几个已知路径来发现安装的 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-160">This feature looks at a few well-known paths on different operating systems to discover installations of PowerShell.</span></span>

<span data-ttu-id="4bdb3-161">使用以下步骤选择版本：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-161">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="4bdb3-162">在 Windows 或 Linux 上，使用 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> 打开“命令面板”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-162">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="4bdb3-163">在 macOS 上，使用 <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-163">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="4bdb3-164">搜索“会话”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-164">Search for **Session**.</span></span>
1. <span data-ttu-id="4bdb3-165">单击“PowerShell:  显示会话菜单”。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-165">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="4bdb3-166">选择要从列表中使用的 PowerShell 版本，例如：PowerShell Core  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-166">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

<span data-ttu-id="4bdb3-167">如果已将 PowerShell 安装到非典型位置，则最初可能不会显示在会话菜单中。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-167">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="4bdb3-168">可以按如下所述[添加你自己的自定义路径](#adding-your-own-powershell-paths-to-the-session-menu)来扩展会话菜单。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-168">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

> [!NOTE]
> <span data-ttu-id="4bdb3-169">还可以从状态栏右下角的绿色版本号访问 PowerShell 会话菜单。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-169">The PowerShell session menu can also be accessed from the green version number in the bottom right corner of status bar.</span></span> <span data-ttu-id="4bdb3-170">单击此版本号将打开会话菜单。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-170">Clicking this version number opens the session menu.</span></span>

## <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="4bdb3-171">Visual Studio Code 的配置设置</span><span class="sxs-lookup"><span data-stu-id="4bdb3-171">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="4bdb3-172">首先，如果不熟悉如何更改 Visual Studio Code 中的设置，建议阅读 [Visual Studio Code 的设置][vsc-settings]文档。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-172">First, if you're not familiar with how to change settings in Visual Studio Code, we recommend reading [Visual Studio Code's settings][vsc-settings] documentation.</span></span>

<span data-ttu-id="4bdb3-173">阅读此文档后，可以在 `settings.json`中添加配置设置。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-173">After reading the documentation, you can add configuration settings in `settings.json`.</span></span>

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="4bdb3-174">如果不希望这些设置影响所有文件类型，则 Visual Studio Code 还允许按语言进行配置。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-174">If you don't want these settings to affect all files types, Visual Studio Code also allows per-language configurations.</span></span> <span data-ttu-id="4bdb3-175">创建在 `[<language-name>]` 字段中放置设置，可以配置特定于语言的设置。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-175">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="4bdb3-176">例如：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-176">For example:</span></span>

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> <span data-ttu-id="4bdb3-177">有关 Visual Studio Code 中文件编码的详细信息，请参阅[了解文件编码][file-encoding]。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-177">For more information about file encoding in Visual Studio Code, see [Understanding file encoding][file-encoding].</span></span>
>
> <span data-ttu-id="4bdb3-178">另外，请查看[如何在 Visual Studio Code 中复制 ISE 体验][vsc-ise]，以获取有关如何配置 Visual Studio Code 以进行 PowerShell 编辑的其他提示。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-178">Also, check out [How to replicate the ISE experience in Visual Studio Code][vsc-ise] for other tips on how to configure Visual Studio Code for PowerShell editing.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="4bdb3-179">将你自己的 PowerShell 路径添加到会话菜单</span><span class="sxs-lookup"><span data-stu-id="4bdb3-179">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="4bdb3-180">可以通过 [Visual Studio Code 设置](https://code.visualstudio.com/docs/getstarted/settings)将其他 PowerShell 可执行文件路径添加到会话菜单：`powershell.powerShellAdditionalExePaths`。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-180">You can add other PowerShell executable paths to the session menu through the [Visual Studio Code setting](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span></span>

<span data-ttu-id="4bdb3-181">向列表 `powershell.powerShellAdditionalExePaths` 添加项或创建该列表（如果它不存在于 `settings.json` 中）：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-181">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    // other settings...
}
```

<span data-ttu-id="4bdb3-182">每个项必须具有：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-182">Each item must have:</span></span>

- <span data-ttu-id="4bdb3-183">`exePath`设置用户帐户 ：`pwsh` 或 `powershell` 可执行文件的路径。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-183">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
- <span data-ttu-id="4bdb3-184">`versionName`设置用户帐户 ：将显示在会话菜单中的文本。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-184">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="4bdb3-185">若要设置默认的 PowerShell 版本，请将值 `powershell.powerShellDefaultVersion` 设置为会话菜单中显示的文本（即 `versionName`）：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-185">To set the default PowerShell version, set the value `powershell.powerShellDefaultVersion` to the text displayed in the session menu (also known as the `versionName`):</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    "powershell.powerShellDefaultVersion": "Downloaded PowerShell",

    // other settings...
}
```

<span data-ttu-id="4bdb3-186">配置此设置后，请重启 Visual Studio Code 或从“命令面板”  中重载当前 Visual Studio Code 窗口，键入“开发人员:  重载窗口”。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-186">After you've configured this setting, restart Visual Studio Code or to reload the current Visual Studio Code window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="4bdb3-187">如果打开会话菜单，你现在会看到其他 PowerShell 版本！</span><span class="sxs-lookup"><span data-stu-id="4bdb3-187">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="4bdb3-188">如果从源生成 PowerShell，则这是测试 PowerShell 的本地生成的好办法。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-188">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a><span data-ttu-id="4bdb3-189">对 Windows PowerShell v3 和 v4 使用旧版 PowerShell 扩展</span><span class="sxs-lookup"><span data-stu-id="4bdb3-189">Using an older version of the PowerShell Extension for Windows PowerShell v3 and v4</span></span>

<span data-ttu-id="4bdb3-190">目前的 PowerShell 扩展不支持 [PowerShell v3 和 v4][i1310]。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-190">The current PowerShell extension doesn't support [PowerShell v3 and v4][i1310].</span></span> <span data-ttu-id="4bdb3-191">但是，可以使用支持 PowerShell v3 和 v4 的最新版本的扩展。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-191">However, you can use the last version of the extension that supports PowerShell v3 and v4.</span></span>

> [!CAUTION]
> <span data-ttu-id="4bdb3-192">将不会为此扩展的较旧版本提供其他修补程序。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-192">There will be no additional fixes to this older version of the extension.</span></span> <span data-ttu-id="4bdb3-193">它“按原样”提供，但如果你仍在使用 Windows PowerShell v3 和 Windows PowerShell v4，则可以使用它。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-193">It's provided "AS IS" but is available for you if you are still using Windows PowerShell v3 and Windows PowerShell v4.</span></span>

<span data-ttu-id="4bdb3-194">首先，打开“扩展”窗格并搜索 `PowerShell`。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-194">First, open the Extension pane and search for `PowerShell`.</span></span> <span data-ttu-id="4bdb3-195">然后单击齿轮，选择“安装其他版本...”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-195">Then click the gear and select **Install another version...**.</span></span>

![菜单项 - 安装其他版本版本…](media/using-vscode/install-another-version.png)

<span data-ttu-id="4bdb3-197">然后选择“2020.1.0”  版本。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-197">Then select the **2020.1.0** version.</span></span> <span data-ttu-id="4bdb3-198">此版本的扩展是支持 v3 和 v4 的最新版本。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-198">This version of the extension was the last version to support v3 and v4.</span></span> <span data-ttu-id="4bdb3-199">请务必添加以下设置，以便不会自动更新扩展版本：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-199">Be sure to add the following setting so that your extension version doesn't update automatically:</span></span>

```json
{
    "extensions.autoUpdate": false
}
```

<span data-ttu-id="4bdb3-200">版本 2020.1.0 在可预见的将来是可行的  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-200">Version **2020.1.0** will work for the foreseeable future.</span></span> <span data-ttu-id="4bdb3-201">但是，Visual Studio Code 可以实现一个中断此扩展版本的更改。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-201">However, Visual Studio Code could implement a change that breaks this version of the extension.</span></span> <span data-ttu-id="4bdb3-202">因此，由于缺乏支持，我们建议：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-202">Because of this, and lack of support, we recommend:</span></span>

- <span data-ttu-id="4bdb3-203">升级到 Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="4bdb3-203">Upgrading to Windows PowerShell 5.1</span></span>
- <span data-ttu-id="4bdb3-204">安装 PowerShell 7，这是 Windows PowerShell 的并行安装，与 PowerShell 扩展配合使用效果最佳</span><span class="sxs-lookup"><span data-stu-id="4bdb3-204">Install PowerShell 7, which is a side-by-side install to Windows PowerShell and works the best with the PowerShell extension</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="4bdb3-205">使用 Visual Studio Code 进行调试</span><span class="sxs-lookup"><span data-stu-id="4bdb3-205">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="4bdb3-206">无工作区调试</span><span class="sxs-lookup"><span data-stu-id="4bdb3-206">No-workspace debugging</span></span>

<span data-ttu-id="4bdb3-207">在 Visual Studio Code 版本 1.9（或更高版本）中，无需打开包含 PowerShell 脚本的文件夹即可调试 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-207">In Visual Studio Code version 1.9 (or higher), you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span>

1. <span data-ttu-id="4bdb3-208">选择“文件”>“打开文件...”打开 PowerShell 脚本文件 </span><span class="sxs-lookup"><span data-stu-id="4bdb3-208">Open the PowerShell script file with **File > Open File...**</span></span>
1. <span data-ttu-id="4bdb3-209">设置断点 - 选择一行，然后按 <kbd>F9</kbd></span><span class="sxs-lookup"><span data-stu-id="4bdb3-209">Set a breakpoint - select a line then press <kbd>F9</kbd></span></span>
1. <span data-ttu-id="4bdb3-210">按 <kbd>F5</kbd> 开始调试</span><span class="sxs-lookup"><span data-stu-id="4bdb3-210">Press <kbd>F5</kbd> to start debugging</span></span>

<span data-ttu-id="4bdb3-211">此时应出现“调试”操作窗格，通过该窗格可以中断调试器、执行、继续和停止调试。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-211">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="4bdb3-212">工作区调试</span><span class="sxs-lookup"><span data-stu-id="4bdb3-212">Workspace debugging</span></span>

<span data-ttu-id="4bdb3-213">工作区调试是指文件夹上下文中的调试，该文件夹是从“文件”  菜单使用“打开文件夹...”  打开的。打开的文件夹通常是 PowerShell 项目文件夹或 Git 存储库的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-213">Workspace debugging refers to debugging in the context of a folder that you've opened from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder or the root of your Git repository.</span></span> <span data-ttu-id="4bdb3-214">通过工作区调试可以定义多个调试配置，而不是只调试当前打开的文件。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-214">Workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>

<span data-ttu-id="4bdb3-215">按照以下步骤创建调试配置文件：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-215">Follow these steps to create a debug configuration file:</span></span>

1. <span data-ttu-id="4bdb3-216">通过按 <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>，在 Windows 或 Linux 上打开“调试”  视图。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-216">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="4bdb3-217">在 macOS 上，按 <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-217">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
1. <span data-ttu-id="4bdb3-218">单击“创建 launch.json 文件”  链接。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-218">Click the **create a launch.json file** link.</span></span>
1. <span data-ttu-id="4bdb3-219">在“选择环境”  提示框中，选择“PowerShell”  。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-219">From the **Select Environment** prompt, choose **PowerShell**.</span></span>
1. <span data-ttu-id="4bdb3-220">选择要使用的调试类型：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-220">Choose the type of debugging you'd like to use:</span></span>

   - <span data-ttu-id="4bdb3-221">**启动当前文件** - 在当前活动的编辑器窗口中启动和调试文件</span><span class="sxs-lookup"><span data-stu-id="4bdb3-221">**Launch Current File** - Launch and debug the file in the currently active editor window</span></span>
   - <span data-ttu-id="4bdb3-222">**启动脚本** - 启动和调试指定的文件或命令</span><span class="sxs-lookup"><span data-stu-id="4bdb3-222">**Launch Script** - Launch and debug the specified file or command</span></span>
   - <span data-ttu-id="4bdb3-223">**交互式会话** - 从集成控制台执行的调试命令</span><span class="sxs-lookup"><span data-stu-id="4bdb3-223">**Interactive Session** - Debug commands executed from the Integrated Console</span></span>
   - <span data-ttu-id="4bdb3-224">**附加** - 将调试器附加到正在运行的 PowerShell 主机进程</span><span class="sxs-lookup"><span data-stu-id="4bdb3-224">**Attach** - Attach the debugger to a running PowerShell Host Process</span></span>

<span data-ttu-id="4bdb3-225">Visual Studio Code 会在工作区文件夹的根目录中创建一个目录和一个 `.vscode\launch.json` 文件，用来存储调试配置。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-225">Visual Studio Code creates a directory and a file `.vscode\launch.json` in the root of your workspace folder to store the debug configuration.</span></span> <span data-ttu-id="4bdb3-226">如果文件位于 Git 存储库中，则通常需要提交 `launch.json` 文件。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-226">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="4bdb3-227">`launch.json` 文件的内容为：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-227">The contents of the `launch.json` file are:</span></span>

```json
{
  "version": "0.2.0",
  "configurations": [
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Launch (current file)",
          "script": "${file}",
          "args": [],
          "cwd": "${file}"
      },
      {
          "type": "PowerShell",
          "request": "attach",
          "name": "PowerShell Attach to Host Process",
          "processId": "${command.PickPSHostProcess}",
          "runspaceId": 1
      },
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Interactive Session",
          "cwd": "${workspaceRoot}"
      }
  ]
}
```

<span data-ttu-id="4bdb3-228">此文件表示常见调试方案。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-228">This file represents the common debug scenarios.</span></span> <span data-ttu-id="4bdb3-229">在编辑器中打开此文件时，会显示“添加配置...”  按钮。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-229">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="4bdb3-230">单击此按钮可添加更多 PowerShell 调试配置。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-230">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="4bdb3-231">其中可添加的一个有用配置是“PowerShell:**Launch Script**。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-231">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="4bdb3-232">使用此配置，可以指定一个文件，无论编辑器中哪个文件处于活动状态，在每次按下 <kbd>F5</kbd> 时，都使用该文件中包含的可选参数。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-232">With this configuration, you can specify a file containing optional arguments that are used whenever you press <kbd>F5</kbd> no matter which file is active in the editor.</span></span>

<span data-ttu-id="4bdb3-233">建立调试配置后，可以选择要在调试会话期间使用的配置。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-233">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="4bdb3-234">从“调试”  视图工具栏的调试配置下拉菜单中选择配置。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-234">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a><span data-ttu-id="4bdb3-235">适用于 Visual Studio Code 的 PowerShell 扩展故障排除</span><span class="sxs-lookup"><span data-stu-id="4bdb3-235">Troubleshooting the PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="4bdb3-236">如果在使用 Visual Studio Code 进行 PowerShell 脚本开发时遇到任何问题，请参阅 GitHub 上的[故障排除指南][troubleshooting]。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-236">If you experience any issues using Visual Studio Code for PowerShell script development, see the [troubleshooting guide][troubleshooting] on GitHub.</span></span>

## <a name="useful-resources"></a><span data-ttu-id="4bdb3-237">有用的资源</span><span class="sxs-lookup"><span data-stu-id="4bdb3-237">Useful resources</span></span>

<span data-ttu-id="4bdb3-238">有一些视频和博客文章可能对你开始使用用于 Visual Studio Code 的 PowerShell 扩展很有帮助：</span><span class="sxs-lookup"><span data-stu-id="4bdb3-238">There are a few videos and blog posts that may be helpful to get you started using the PowerShell extension for Visual Studio Code:</span></span>

### <a name="videos"></a><span data-ttu-id="4bdb3-239">视频</span><span class="sxs-lookup"><span data-stu-id="4bdb3-239">Videos</span></span>

- [<span data-ttu-id="4bdb3-240">使用 Visual Studio Code 作为默认 PowerShell 编辑器</span><span class="sxs-lookup"><span data-stu-id="4bdb3-240">Using Visual Studio Code as Your Default PowerShell Editor</span></span>](https://youtu.be/bGn45vIeAMM)
- [<span data-ttu-id="4bdb3-241">Visual Studio Code：深入了解如何调试 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="4bdb3-241">Visual Studio Code: deep dive into debugging your PowerShell scripts</span></span>](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a><span data-ttu-id="4bdb3-242">博客文章</span><span class="sxs-lookup"><span data-stu-id="4bdb3-242">Blog posts</span></span>

- <span data-ttu-id="4bdb3-243">[PowerShell 扩展][pscdn]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-243">[PowerShell Extension][pscdn]</span></span>
- <span data-ttu-id="4bdb3-244">[在 Visual Studio Code 中编写和调试 PowerShell 脚本][debug]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-244">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="4bdb3-245">[Visual Studio Code 调试指南][psdbgblog]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-245">[Debugging Visual Studio Code Guidance][psdbgblog]</span></span>
- <span data-ttu-id="4bdb3-246">[在 Visual Studio Code 中调试 PowerShell][psdbg-gh]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-246">[Debugging PowerShell in Visual Studio Code][psdbg-gh]</span></span>
- <span data-ttu-id="4bdb3-247">[Visual Studio Code 中的 PowerShell 开发入门][getting-started]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-247">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="4bdb3-248">[面向 PowerShell 开发的 Visual Studio Code 编辑功能 - 第 1 部分][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-248">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="4bdb3-249">[面向 PowerShell 开发的 Visual Studio Code 编辑功能 - 第 2 部分][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-249">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="4bdb3-250">[在 Visual Studio Code 中调试 PowerShell 脚本 - 第 1 部分][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-250">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="4bdb3-251">[在 Visual Studio Code 中调试 PowerShell 脚本 - 第 2 部分][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="4bdb3-251">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

## <a name="powershell-extension-project-source-code"></a><span data-ttu-id="4bdb3-252">PowerShell 扩展项目源代码</span><span class="sxs-lookup"><span data-stu-id="4bdb3-252">PowerShell extension project source code</span></span>

<span data-ttu-id="4bdb3-253">可以在 [GitHub][psext-src] 上找到 PowerShell 扩展的源代码。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-253">The PowerShell extension's source code can be found on [GitHub][psext-src].</span></span>

<span data-ttu-id="4bdb3-254">如果你有兴趣参与，将极大改进拉取请求。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-254">If you're interested in contributing, Pull Requests are greatly appreciated.</span></span> <span data-ttu-id="4bdb3-255">请遵循 GitHub 上的[开发人员文档][dev-docs]来开始使用。</span><span class="sxs-lookup"><span data-stu-id="4bdb3-255">Follow along with the [developer documentation][dev-docs] on GitHub to get started.</span></span>

<!-- related articles -->
[ise]:                    ../../windows-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:   ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:   ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]:          ../../install/Installing-Windows-PowerShell.md
[file-encoding]:          understanding-file-encoding.md
[vsc-ise]:                How-To-Replicate-the-ISE-Experience-In-VSCode.md

<!-- blogs -->
[debug]:                  https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[debugging-part1]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/
[editing-part1]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[getting-started]:        https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[psdbgblog]:              https://johnpapa.net/debugging-with-visual-studio-code/
[psdbg-gh]:               https://github.com/PowerShell/vscode-powershell/tree/master/examples
[pscdn]:                  https://docs.microsoft.com/archive/blogs/cdndevs/visual-studio-code-powershell-extension

<!-- issues -->
[GitHub 问题]:          https://github.com/PowerShell/vscode-powershell/issues
[GitHub issues]:          https://github.com/PowerShell/vscode-powershell/issues
[i1310]:                  https://github.com/PowerShell/vscode-powershell/issues/1310
[i606]:                   https://github.com/PowerShell/vscode-powershell/issues/606

<!-- product links -->
[Visual Studio]:          https://visualstudio.microsoft.com/
[vscode]:                 https://code.visualstudio.com/
[psext]:                  https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[vsc-settings]:           https://code.visualstudio.com/docs/getstarted/settings
[vsc-setup]:              https://code.visualstudio.com/Docs/setup/setup-overview
[vsc-setup-win]:          https://code.visualstudio.com/docs/setup/windows
[vsc-setup-macos]:        https://code.visualstudio.com/docs/setup/mac
[vsc-setup-linux]:        https://code.visualstudio.com/docs/setup/linux
[psext-src]:              https://github.com/PowerShell/vscode-powershell
[troubleshooting]:        https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md
[dev-docs]:               https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md
