---
description: 介绍如何安装、导入和使用 PowerShell 模块。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 07/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: 2668c722bfc7bb49517054767491a17a716a0720
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200290"
---
# <a name="about-modules"></a><span data-ttu-id="57122-104">关于模块</span><span class="sxs-lookup"><span data-stu-id="57122-104">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="57122-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="57122-105">Short Description</span></span>
<span data-ttu-id="57122-106">介绍如何安装、导入和使用 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="57122-106">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="57122-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="57122-107">Long Description</span></span>

<span data-ttu-id="57122-108">模块是一个包，其中包含 PowerShell 命令，例如 cmdlet、提供程序、函数、工作流、变量和别名。</span><span class="sxs-lookup"><span data-stu-id="57122-108">A module is a package that contains PowerShell commands, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="57122-109">编写命令的人可以使用模块来组织其命令并与他人共享。</span><span class="sxs-lookup"><span data-stu-id="57122-109">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="57122-110">接收模块的人可以将模块中的命令添加到其 PowerShell 会话，并像使用内置命令一样使用它们。</span><span class="sxs-lookup"><span data-stu-id="57122-110">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="57122-111">本主题介绍如何使用 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="57122-111">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="57122-112">有关如何编写 PowerShell 模块的详细信息，请参阅 [编写 Powershell 模块](/powershell/scripting/developer/module/writing-a-windows-powershell-module)。</span><span class="sxs-lookup"><span data-stu-id="57122-112">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="57122-113">什么是模块？</span><span class="sxs-lookup"><span data-stu-id="57122-113">What Is a Module?</span></span>

<span data-ttu-id="57122-114">模块是一个命令包。</span><span class="sxs-lookup"><span data-stu-id="57122-114">A module is a package of commands.</span></span> <span data-ttu-id="57122-115">会话中的所有 cmdlet 和提供程序均由模块或管理单元添加。</span><span class="sxs-lookup"><span data-stu-id="57122-115">All cmdlets and providers in your session are added by a module or a snap-in.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="57122-116">模块自动加载</span><span class="sxs-lookup"><span data-stu-id="57122-116">Module Auto-Loading</span></span>

<span data-ttu-id="57122-117">从 PowerShell 3.0 开始，在已安装的模块中首次运行任何命令时，PowerShell 会自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="57122-117">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="57122-118">现在，你可以在没有任何设置或配置文件配置的情况下使用模块中的命令，因此在计算机上安装模块后，无需再对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="57122-118">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="57122-119">模块中的命令也更易于查找。</span><span class="sxs-lookup"><span data-stu-id="57122-119">The commands in a module are also easier to find.</span></span> <span data-ttu-id="57122-120">该 `Get-Command` cmdlet 现在获取所有已安装模块中的所有命令，即使它们尚未包含在会话中，你也可以在不导入的情况下找到并使用该命令。</span><span class="sxs-lookup"><span data-stu-id="57122-120">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session, so you can find a command and use it without importing.</span></span>

<span data-ttu-id="57122-121">下面的每个示例都将使包含的 CimCmdlets 模块 `Get-CimInstance` 导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="57122-121">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="57122-122">运行命令</span><span class="sxs-lookup"><span data-stu-id="57122-122">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="57122-123">获取命令</span><span class="sxs-lookup"><span data-stu-id="57122-123">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="57122-124">获取有关命令的帮助</span><span class="sxs-lookup"><span data-stu-id="57122-124">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="57122-125">`Get-Command` 包含通配符的命令 (`*`) 视为用于发现，不使用，不导入任何模块。</span><span class="sxs-lookup"><span data-stu-id="57122-125">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="57122-126">仅自动导入存储在由 PSModulePath 环境变量指定的位置中的模块。</span><span class="sxs-lookup"><span data-stu-id="57122-126">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="57122-127">必须通过运行 cmdlet 来导入其他位置中的模块 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="57122-127">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="57122-128">此外，使用 PowerShell 提供程序的命令不会自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="57122-128">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="57122-129">例如，如果你使用需要 WSMan：驱动器的命令（如 `Get-PSSessionConfiguration` cmdlet），则可能需要运行 `Import-Module` cmdlet 以导入包含驱动器的 **Microsoft. 管理** 模块 `WSMan:` 。</span><span class="sxs-lookup"><span data-stu-id="57122-129">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="57122-130">你仍可以运行 `Import-Module` 命令来导入模块，并使用该 `$PSModuleAutoloadingPreference` 变量来启用、禁用和配置模块的自动导入。</span><span class="sxs-lookup"><span data-stu-id="57122-130">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="57122-131">有关详细信息，请参阅 [about_Preference_Variables](about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="57122-131">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="57122-132">如何使用模块</span><span class="sxs-lookup"><span data-stu-id="57122-132">How to Use a Module</span></span>

<span data-ttu-id="57122-133">若要使用模块，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="57122-133">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="57122-134">安装模块。</span><span class="sxs-lookup"><span data-stu-id="57122-134">Install the module.</span></span> <span data-ttu-id="57122-135">（通常已为你完成这一步。）</span><span class="sxs-lookup"><span data-stu-id="57122-135">(This is often done for you.)</span></span>
1. <span data-ttu-id="57122-136">找到模块所添加的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-136">Find the commands that the module added.</span></span>
1. <span data-ttu-id="57122-137">使用模块所添加的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-137">Use the commands that the module added.</span></span>

<span data-ttu-id="57122-138">本主题介绍了如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="57122-138">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="57122-139">它还包括有关管理模块的其他有用信息。</span><span class="sxs-lookup"><span data-stu-id="57122-139">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="57122-140">如何安装模块</span><span class="sxs-lookup"><span data-stu-id="57122-140">How to Install a Module</span></span>

<span data-ttu-id="57122-141">如果接收到的模块中包含文件，则需要将其安装到计算机上，然后才能在 PowerShell 中使用它。</span><span class="sxs-lookup"><span data-stu-id="57122-141">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="57122-142">已为你安装好大多数模块。</span><span class="sxs-lookup"><span data-stu-id="57122-142">Most modules are installed for you.</span></span> <span data-ttu-id="57122-143">PowerShell 附带几个预安装的模块，有时称为 _核心_ 模块。</span><span class="sxs-lookup"><span data-stu-id="57122-143">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="57122-144">在基于 Windows 的计算机上，如果操作系统附带的功能具有用于管理它们的 cmdlet，则会预安装这些模块。</span><span class="sxs-lookup"><span data-stu-id="57122-144">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="57122-145">在安装 Windows 功能时，可以使用服务器管理器中的 "添加角色和功能向导"，或在 "控制面板" 的 "打开或关闭 Windows 功能" 对话框中安装所有作为功能组成部分的 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="57122-145">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="57122-146">许多其他模块随附在用于安装模块的安装程序中。</span><span class="sxs-lookup"><span data-stu-id="57122-146">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="57122-147">使用以下命令为当前用户创建 **模块** 目录：</span><span class="sxs-lookup"><span data-stu-id="57122-147">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\WindowsPowerShell\Modules
```

<span data-ttu-id="57122-148">将整个模块文件夹复制到 Modules 目录中。</span><span class="sxs-lookup"><span data-stu-id="57122-148">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="57122-149">可以使用任何方法复制文件夹，包括 Windows 资源管理器和 Cmd.exe，以及 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="57122-149">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="57122-150">在 PowerShell 中使用 `Copy-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="57122-150">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="57122-151">例如，要将中的 MyModule 文件夹复制 `C:\ps-test\MyModule` 到模块目录，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-151">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\WindowsPowerShell\Modules
```

<span data-ttu-id="57122-152">你可以在任何位置上安装模块，但在默认模块位置中安装模块可使其更易于管理。</span><span class="sxs-lookup"><span data-stu-id="57122-152">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="57122-153">有关默认模块位置的详细信息，请参阅 [module 和 DSC 资源位置和 PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) 部分。</span><span class="sxs-lookup"><span data-stu-id="57122-153">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="57122-154">如何查找已安装的模块</span><span class="sxs-lookup"><span data-stu-id="57122-154">How to Find Installed Modules</span></span>

<span data-ttu-id="57122-155">若要查找已安装在默认模块位置中但尚未导入到会话中的模块，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-155">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="57122-156">若要查找已导入到会话中的模块，请在 PowerShell 提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="57122-156">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="57122-157">有关 cmdlet 的详细信息 `Get-Module` ，请参阅 [get-help](xref:Microsoft.PowerShell.Core.Get-Module)。</span><span class="sxs-lookup"><span data-stu-id="57122-157">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="57122-158">如何查找模块中的命令</span><span class="sxs-lookup"><span data-stu-id="57122-158">How to Find the Commands in a Module</span></span>

<span data-ttu-id="57122-159">使用 `Get-Command` cmdlet 查找所有可用的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-159">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="57122-160">可以使用 cmdlet 的参数 `Get-Command` 按模块、名称和名词来筛选命令。</span><span class="sxs-lookup"><span data-stu-id="57122-160">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="57122-161">若要查找模块中的所有命令，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-161">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="57122-162">例如，若要查找 BitsTransfer 模块中的命令，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-162">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="57122-163">有关 cmdlet 的详细信息 `Get-Command` ，请参阅 [获取-命令](xref:Microsoft.PowerShell.Core.Get-Command)。</span><span class="sxs-lookup"><span data-stu-id="57122-163">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="57122-164">如何获取有关模块中的命令的帮助</span><span class="sxs-lookup"><span data-stu-id="57122-164">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="57122-165">如果模块包含它所导出的命令的帮助文件，则该 `Get-Help` cmdlet 将显示帮助主题。</span><span class="sxs-lookup"><span data-stu-id="57122-165">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="57122-166">使用用于 `Get-Help` 获取 PowerShell 中任何命令的帮助的相同命令格式。</span><span class="sxs-lookup"><span data-stu-id="57122-166">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="57122-167">从 PowerShell 3.0 开始，你可以下载模块的帮助文件，并下载帮助文件的更新，以使它们永远不会过时。</span><span class="sxs-lookup"><span data-stu-id="57122-167">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="57122-168">若要获取有关模块中的命令的帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-168">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="57122-169">若要获取模块中命令的联机帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-169">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="57122-170">若要下载并安装模块中的命令的帮助文件，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-170">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="57122-171">有关详细信息，请参阅 [get-help](xref:Microsoft.PowerShell.Core.Get-Help) 和 [update-help](xref:Microsoft.PowerShell.Core.Update-Help)。</span><span class="sxs-lookup"><span data-stu-id="57122-171">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="57122-172">如何导入模块</span><span class="sxs-lookup"><span data-stu-id="57122-172">How to Import a Module</span></span>

<span data-ttu-id="57122-173">你可能需要导入模块或导入模块文件。</span><span class="sxs-lookup"><span data-stu-id="57122-173">You might have to import a module or import a module file.</span></span> <span data-ttu-id="57122-174">如果模块未安装在由 **PSModulePath** 环境变量指定的位置， `$env:PSModulePath` 或者模块包含文件（例如 .dll 或 hbase-runner.psm1 文件），而不是作为文件夹传递的典型模块，则需要导入。</span><span class="sxs-lookup"><span data-stu-id="57122-174">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="57122-175">你还可以选择导入模块，以便可以使用命令的参数 `Import-Module` ，如 Prefix 参数，该参数可将一个特殊前缀添加到所有已导入命令的名词名称中，或 **NoClobber** 参数，这会阻止模块添加会隐藏或替换会话中的现有命令的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-175">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="57122-176">若要导入模块，请使用 `Import-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="57122-176">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="57122-177">若要将 PSModulePath 位置中的模块导入到当前会话中，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="57122-177">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="57122-178">例如，以下命令将 BitsTransfer 模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="57122-178">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="57122-179">若要导入不在默认模块位置中的模块，请使用指向命令中的模块文件夹的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="57122-179">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="57122-180">例如，若要将目录中的 TestCmdlets 模块添加 `C:\ps-test` 到会话中，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-180">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="57122-181">若要导入未包含在模块文件夹中的模块文件，请使用指向命令中的模块文件的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="57122-181">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="57122-182">例如，若要将目录中的 TestCmdlets.dll 模块添加 `C:\ps-test` 到会话中，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-182">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="57122-183">有关向会话添加模块的详细信息，请参阅 [import-module](xref:Microsoft.PowerShell.Core.Import-Module)。</span><span class="sxs-lookup"><span data-stu-id="57122-183">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="57122-184">如何将模块导入到每个会话中</span><span class="sxs-lookup"><span data-stu-id="57122-184">How to Import a Module into Every Session</span></span>

<span data-ttu-id="57122-185">`Import-Module`命令将模块导入当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="57122-185">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="57122-186">若要将模块导入到启动的每个 PowerShell 会话，请将 `Import-Module` 命令添加到 powershell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="57122-186">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="57122-187">有关配置文件的详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="57122-187">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="57122-188">如何删除模块</span><span class="sxs-lookup"><span data-stu-id="57122-188">How to Remove a Module</span></span>

<span data-ttu-id="57122-189">当你删除模块时，该模块所添加的命令将从会话中删除。</span><span class="sxs-lookup"><span data-stu-id="57122-189">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="57122-190">若要从会话中删除模块，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="57122-190">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="57122-191">例如，以下命令将从当前会话中删除 BitsTransfer 模块。</span><span class="sxs-lookup"><span data-stu-id="57122-191">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="57122-192">删除模块与导入模块的操作相反。</span><span class="sxs-lookup"><span data-stu-id="57122-192">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="57122-193">删除模块不会卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="57122-193">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="57122-194">有关详细信息，请参阅 [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module)。</span><span class="sxs-lookup"><span data-stu-id="57122-194">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="57122-195">模块和 DSC 资源位置以及 PSModulePath</span><span class="sxs-lookup"><span data-stu-id="57122-195">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="57122-196">`$env:PSModulePath`环境变量包含一个文件夹位置列表，将在其中进行搜索以查找模块和资源。</span><span class="sxs-lookup"><span data-stu-id="57122-196">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="57122-197">默认情况下，分配到的有效位置 `$env:PSModulePath` 为：</span><span class="sxs-lookup"><span data-stu-id="57122-197">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="57122-198">系统范围内的位置： `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="57122-198">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="57122-199">这些文件夹包含 Windows 和 PowerShell 附带的模块。</span><span class="sxs-lookup"><span data-stu-id="57122-199">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="57122-200">PowerShell 附带的 DSC 资源存储在 `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="57122-200">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="57122-201">特定于用户的模块：这些是用户在用户范围中安装的模块。</span><span class="sxs-lookup"><span data-stu-id="57122-201">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="57122-202">`Install-Module` 具有 **作用域** 参数，该参数可用于指定是为当前用户还是为所有用户安装该模块。</span><span class="sxs-lookup"><span data-stu-id="57122-202">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="57122-203">有关详细信息，请参阅 [Install-Module](xref:PowerShellGet.Install-Module)。</span><span class="sxs-lookup"><span data-stu-id="57122-203">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="57122-204">Windows 上用户特定的 **CurrentUser** 位置是 `PowerShell\Modules` 位于用户配置文件的 " **文档** " 位置中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="57122-204">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="57122-205">该位置的特定路径因 Windows 版本而异，无论是否正在使用文件夹重定向。</span><span class="sxs-lookup"><span data-stu-id="57122-205">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="57122-206">Microsoft OneDrive 还可以更改 **文档** 文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="57122-206">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="57122-207">默认情况下，在 Windows 10 上，该位置是 `$HOME\Documents\PowerShell\Modules` 。</span><span class="sxs-lookup"><span data-stu-id="57122-207">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="57122-208">在 Linux 或 Mac 上， **CurrentUser** 位置是 `$HOME/.local/share/powershell/Modules` 。</span><span class="sxs-lookup"><span data-stu-id="57122-208">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="57122-209">可以使用以下命令来验证 **Documents** 文件夹的位置： `[Environment]::GetFolderPath('MyDocuments')` 。</span><span class="sxs-lookup"><span data-stu-id="57122-209">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="57122-210">**AllUsers** 位置 `$env:PROGRAMFILES\WindowsPowerShell\Modules` 在 Windows 上。</span><span class="sxs-lookup"><span data-stu-id="57122-210">The **AllUsers** location is `$env:PROGRAMFILES\WindowsPowerShell\Modules` on Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="57122-211">若要在目录中添加或更改文件 `$env:Windir\System32` ，请以 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="57122-211">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="57122-212">可以通过更改 **PSModulePath** 环境变量的值来更改系统上的默认模块位置 `$Env:PSModulePath` 。</span><span class="sxs-lookup"><span data-stu-id="57122-212">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="57122-213">**PSModulePath** 环境变量在 Path 环境变量上建模，具有相同的格式。</span><span class="sxs-lookup"><span data-stu-id="57122-213">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="57122-214">若要查看默认模块位置，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-214">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="57122-215">若要添加默认模块位置，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="57122-215">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="57122-216">命令中的分号 (`;`) 将新路径与列表中其前面的路径分隔开。</span><span class="sxs-lookup"><span data-stu-id="57122-216">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="57122-217">例如，若要添加 `C:\ps-test\Modules` 目录，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-217">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="57122-218">将路径添加到 **PSModulePath** 时， `Get-Module` 和 `Import-Module` 命令包括该路径中的模块。</span><span class="sxs-lookup"><span data-stu-id="57122-218">When you add a path to **PSModulePath** , `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="57122-219">你所设置的值仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="57122-219">The value that you set affects only the current session.</span></span> <span data-ttu-id="57122-220">要使更改保持不变，请将命令添加到 PowerShell 配置文件，或使用控制面板中的 "系统" 来更改注册表中的 **PSModulePath** 环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="57122-220">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="57122-221">此外，若要使更改保持不变，还可以使用 **SetEnvironmentVariable** **类的** 方法将路径添加到 **PSModulePath** 环境变量。</span><span class="sxs-lookup"><span data-stu-id="57122-221">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="57122-222">有关 **PSModulePath** 变量的详细信息，请参阅 [about_Environment_Variables](about_Environment_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="57122-222">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="57122-223">模块和名称冲突</span><span class="sxs-lookup"><span data-stu-id="57122-223">Modules and Name Conflicts</span></span>

<span data-ttu-id="57122-224">当会话中的多个命令具有相同的名称时，会发生名称冲突。</span><span class="sxs-lookup"><span data-stu-id="57122-224">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="57122-225">当模块中的命令与会话中的命令或项具有相同名称时，导入模块将引起名称冲突。</span><span class="sxs-lookup"><span data-stu-id="57122-225">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="57122-226">名称冲突可能会导致命令被隐藏或替换。</span><span class="sxs-lookup"><span data-stu-id="57122-226">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="57122-227">Hidden</span><span class="sxs-lookup"><span data-stu-id="57122-227">Hidden</span></span>

<span data-ttu-id="57122-228">当某个命令不是键入命令名称后所运行的命令时，该命令将隐藏，但你可以使用另一种方法来运行它，例如通过使用模块名称或创建它的管理单元的名称来限定命令名称。</span><span class="sxs-lookup"><span data-stu-id="57122-228">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="57122-229">已替换</span><span class="sxs-lookup"><span data-stu-id="57122-229">Replaced</span></span>

<span data-ttu-id="57122-230">当由于具有相同名称的命令已覆盖某个命令而无法运行该命令时，该命令即被替换。</span><span class="sxs-lookup"><span data-stu-id="57122-230">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="57122-231">即使删除导致冲突的模块，也无法运行替换的命令，除非重新启动该会话。</span><span class="sxs-lookup"><span data-stu-id="57122-231">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="57122-232">`Import-Module` 可以添加用于隐藏和替换当前会话中的命令的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-232">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="57122-233">此外，你的会话中的命令可以隐藏模块所添加的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-233">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="57122-234">若要检测名称冲突，请使用 cmdlet 的 **All** 参数 `Get-Command` 。</span><span class="sxs-lookup"><span data-stu-id="57122-234">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="57122-235">从 PowerShell 3.0 开始， `Get-Command` 仅获取键入命令名称时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-235">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="57122-236">**All** 参数获取会话中具有特定名称的所有命令。</span><span class="sxs-lookup"><span data-stu-id="57122-236">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="57122-237">若要防止名称冲突，请使用 cmdlet 的 **NoClobber** 或 **Prefix** 参数 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="57122-237">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="57122-238">**Prefix** 参数将前缀添加到已导入命令的名称，以便它们在会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="57122-238">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="57122-239">**NoClobber** 参数不会导入任何将隐藏或替换会话中的现有命令的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-239">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="57122-240">你还可以使用的 **Alias** 、 **Cmdlet** 、 **Function** 和 **Variable** 参数 `Import-Module` 来仅选择要导入的命令，并且可以排除在会话中引起名称冲突的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-240">You can also use the **Alias** , **Cmdlet** , **Function** , and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="57122-241">模块作者可以通过使用模块清单的 **DefaultCommandPrefix** 属性来将默认前缀添加到所有命令名称，从而防止名称冲突。</span><span class="sxs-lookup"><span data-stu-id="57122-241">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="57122-242">**Prefix** 参数的值优先于 **DefaultCommandPrefix** 的值。</span><span class="sxs-lookup"><span data-stu-id="57122-242">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix** .</span></span>

<span data-ttu-id="57122-243">即使命令处于隐藏状态，你也可以通过使用模块名称或创建该模块的管理单元名称来限定命令名称，从而运行该命令。</span><span class="sxs-lookup"><span data-stu-id="57122-243">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="57122-244">PowerShell 命令优先规则确定当会话中包含具有相同名称的命令时运行哪个命令。</span><span class="sxs-lookup"><span data-stu-id="57122-244">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="57122-245">例如，当会话中包含具有相同名称的函数和 cmdlet 时，默认情况下，PowerShell 将运行该函数。</span><span class="sxs-lookup"><span data-stu-id="57122-245">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="57122-246">当会话中包含同一类型的同名命令时（例如具有相同名称的两个 cmdlet），它将在默认情况下运行最新添加的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-246">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="57122-247">有关详细信息，包括优先规则的说明和运行隐藏命令的说明，请参阅 [about_Command_Precedence](about_Command_Precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="57122-247">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="57122-248">模块和管理单元</span><span class="sxs-lookup"><span data-stu-id="57122-248">Modules and Snap-ins</span></span>

<span data-ttu-id="57122-249">你可以从模块和管理单元向会话中添加命令。模块可以添加所有类型的命令，包括 cmdlet、提供程序、函数和项（例如变量、别名和 PowerShell 驱动器）。</span><span class="sxs-lookup"><span data-stu-id="57122-249">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="57122-250">管理单元只可以添加 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="57122-250">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="57122-251">在从会话中删除模块或管理单元之前，请使用以下命令来确定将删除哪些命令。</span><span class="sxs-lookup"><span data-stu-id="57122-251">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="57122-252">若要在会话中查找某个 cmdlet 的源，请使用以下命令格式：</span><span class="sxs-lookup"><span data-stu-id="57122-252">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="57122-253">例如，若要查找 cmdlet 的源 `Get-Date` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="57122-253">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

<span data-ttu-id="57122-254">有关 PowerShell 管理单元的详细信息，请参阅 [about_PSSnapins](about_PSSnapins.md)。</span><span class="sxs-lookup"><span data-stu-id="57122-254">For more information about PowerShell snap-ins, see [about_PSSnapins](about_PSSnapins.md).</span></span>

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="57122-255">与模块相关的警告和错误</span><span class="sxs-lookup"><span data-stu-id="57122-255">Module-related Warnings and Errors</span></span>

<span data-ttu-id="57122-256">模块导出的命令应遵循 PowerShell 命令命名规则。</span><span class="sxs-lookup"><span data-stu-id="57122-256">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="57122-257">如果导入的模块导出名称中包含未经批准的谓词的 cmdlet 或函数，则该 `Import-Module` cmdlet 将显示以下警告消息。</span><span class="sxs-lookup"><span data-stu-id="57122-257">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="57122-258">警告：某些导入的命令名称包括未经批准的动词，这可能会使它们更易发现。</span><span class="sxs-lookup"><span data-stu-id="57122-258">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="57122-259">请使用 Verbose 参数获取详细信息或者键入 Get-Verb 以查看批准的谓词列表。</span><span class="sxs-lookup"><span data-stu-id="57122-259">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="57122-260">此消息只是一个警告。</span><span class="sxs-lookup"><span data-stu-id="57122-260">This message is only a warning.</span></span> <span data-ttu-id="57122-261">仍将导入完整的模块，其中包括非一致性的命令。</span><span class="sxs-lookup"><span data-stu-id="57122-261">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="57122-262">尽管会向模块用户显示消息，但是模块作者应修复命名问题。</span><span class="sxs-lookup"><span data-stu-id="57122-262">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="57122-263">若要禁止显示警告消息，请使用 cmdlet 的 **DisableNameChecking** 参数 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="57122-263">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="57122-264">内置模块和管理单元</span><span class="sxs-lookup"><span data-stu-id="57122-264">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="57122-265">在 PowerShell 2.0 和 PowerShell 3.0 和更高版本的旧式主机程序中，随 PowerShell 一起安装的核心命令打包在自动添加到每个 PowerShell 会话的管理单元中。</span><span class="sxs-lookup"><span data-stu-id="57122-265">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="57122-266">从 PowerShell 3.0 开始，对于实现 `InitialSessionState.CreateDefault2` 初始会话状态 API 的主机程序，默认情况下会将 "Microsoft" 管理单元添加到每个会话中。</span><span class="sxs-lookup"><span data-stu-id="57122-266">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="57122-267">首次使用时，模块会自动加载。</span><span class="sxs-lookup"><span data-stu-id="57122-267">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="57122-268">远程会话（包括使用 cmdlet 启动的会话） `New-PSSession` 是旧样式的会话，其中内置命令打包在管理单元中。</span><span class="sxs-lookup"><span data-stu-id="57122-268">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="57122-269">以下模块 (或与 PowerShell 一起安装) 的管理单元。</span><span class="sxs-lookup"><span data-stu-id="57122-269">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="57122-270">CimCmdlet</span><span class="sxs-lookup"><span data-stu-id="57122-270">CimCmdlets</span></span>
- <span data-ttu-id="57122-271">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="57122-271">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="57122-272">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="57122-272">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="57122-273">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="57122-273">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="57122-274">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="57122-274">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="57122-275">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="57122-275">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="57122-276">Microsoft.PowerShell.ODataUtils</span><span class="sxs-lookup"><span data-stu-id="57122-276">Microsoft.PowerShell.ODataUtils</span></span>
- <span data-ttu-id="57122-277">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="57122-277">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="57122-278">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="57122-278">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="57122-279">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="57122-279">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="57122-280">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="57122-280">PackageManagement</span></span>
- <span data-ttu-id="57122-281">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="57122-281">PowerShellGet</span></span>
- <span data-ttu-id="57122-282">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="57122-282">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="57122-283">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="57122-283">PSDiagnostics</span></span>
- <span data-ttu-id="57122-284">PSScheduledJob</span><span class="sxs-lookup"><span data-stu-id="57122-284">PSScheduledJob</span></span>
- <span data-ttu-id="57122-285">PSWorkflow</span><span class="sxs-lookup"><span data-stu-id="57122-285">PSWorkflow</span></span>
- <span data-ttu-id="57122-286">PSWorkflowUtility</span><span class="sxs-lookup"><span data-stu-id="57122-286">PSWorkflowUtility</span></span>
- <span data-ttu-id="57122-287">ISE</span><span class="sxs-lookup"><span data-stu-id="57122-287">ISE</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="57122-288">记录模块事件</span><span class="sxs-lookup"><span data-stu-id="57122-288">Logging Module Events</span></span>

<span data-ttu-id="57122-289">从 PowerShell 3.0 开始，你可以通过将模块和管理单元的 **LogPipelineExecutionDetails** 属性设置为来记录 powershell 模块和管理单元中的 cmdlet 和函数的执行事件 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="57122-289">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="57122-290">你还可以使用组策略设置，启用模块日志记录，以便在所有 PowerShell 会话中启用模块日志记录。</span><span class="sxs-lookup"><span data-stu-id="57122-290">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="57122-291">有关详细信息，请参阅 [about_EventLogs](about_EventLogs.md) 和 [about_Group_Policy_Settings](about_Group_Policy_Settings.md)。</span><span class="sxs-lookup"><span data-stu-id="57122-291">For more information, see [about_EventLogs](about_EventLogs.md) and [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57122-292">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57122-292">See Also</span></span>

[<span data-ttu-id="57122-293">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="57122-293">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="57122-294">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="57122-294">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="57122-295">about_PSSnapins</span><span class="sxs-lookup"><span data-stu-id="57122-295">about_PSSnapins</span></span>](about_PSSnapins.md)

[<span data-ttu-id="57122-296">Get-Command</span><span class="sxs-lookup"><span data-stu-id="57122-296">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="57122-297">Get-Help</span><span class="sxs-lookup"><span data-stu-id="57122-297">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="57122-298">Get-Module</span><span class="sxs-lookup"><span data-stu-id="57122-298">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="57122-299">Import-Module</span><span class="sxs-lookup"><span data-stu-id="57122-299">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="57122-300">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="57122-300">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
