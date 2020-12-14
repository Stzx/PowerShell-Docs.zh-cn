---
description: 介绍如何安装、导入和使用 PowerShell 模块。
Locale: en-US
ms.date: 12/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_modules?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Modules
ms.openlocfilehash: ab4e9658ed4820c3ae84ac1cd9a55b59cc8017ab
ms.sourcegitcommit: 7b376314e7640c39a53aac9f0db8bb935514a960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "96564473"
---
# <a name="about-modules"></a><span data-ttu-id="d7b68-103">关于模块</span><span class="sxs-lookup"><span data-stu-id="d7b68-103">About Modules</span></span>

## <a name="short-description"></a><span data-ttu-id="d7b68-104">简短说明</span><span class="sxs-lookup"><span data-stu-id="d7b68-104">Short Description</span></span>
<span data-ttu-id="d7b68-105">介绍如何安装、导入和使用 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-105">Explains how to install, import, and use PowerShell modules.</span></span>

## <a name="long-description"></a><span data-ttu-id="d7b68-106">详细说明</span><span class="sxs-lookup"><span data-stu-id="d7b68-106">Long Description</span></span>

<span data-ttu-id="d7b68-107">模块是一个包，其中包含 PowerShell 成员，例如 cmdlet、提供程序、函数、工作流、变量和别名。</span><span class="sxs-lookup"><span data-stu-id="d7b68-107">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span>

<span data-ttu-id="d7b68-108">编写命令的人可以使用模块来组织其命令并与他人共享。</span><span class="sxs-lookup"><span data-stu-id="d7b68-108">People who write commands can use modules to organize their commands and share them with others.</span></span> <span data-ttu-id="d7b68-109">接收模块的人可以将模块中的命令添加到其 PowerShell 会话，并像使用内置命令一样使用它们。</span><span class="sxs-lookup"><span data-stu-id="d7b68-109">People who receive modules can add the commands in the modules to their PowerShell sessions and use them just like the built-in commands.</span></span>

<span data-ttu-id="d7b68-110">本主题介绍如何使用 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-110">This topic explains how to use PowerShell modules.</span></span> <span data-ttu-id="d7b68-111">有关如何编写 PowerShell 模块的详细信息，请参阅 [编写 Powershell 模块](/powershell/scripting/developer/module/writing-a-windows-powershell-module)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-111">For information about how to write PowerShell modules, see [Writing a PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="what-is-a-module"></a><span data-ttu-id="d7b68-112">什么是模块？</span><span class="sxs-lookup"><span data-stu-id="d7b68-112">What Is a Module?</span></span>

<span data-ttu-id="d7b68-113">模块是一个包，其中包含 PowerShell 成员，例如 cmdlet、提供程序、函数、工作流、变量和别名。</span><span class="sxs-lookup"><span data-stu-id="d7b68-113">A module is a package that contains PowerShell members, such as cmdlets, providers, functions, workflows, variables, and aliases.</span></span> <span data-ttu-id="d7b68-114">此包的成员可以在 PowerShell 脚本、已编译的 DLL 或二者的组合中实现。</span><span class="sxs-lookup"><span data-stu-id="d7b68-114">The members of this package can be implemented in a PowerShell script, a compiled DLL, or a combination of both.</span></span> <span data-ttu-id="d7b68-115">这些文件通常在单个目录中组合在一起。</span><span class="sxs-lookup"><span data-stu-id="d7b68-115">These files are usually grouped together in a single directory.</span></span> <span data-ttu-id="d7b68-116">有关详细信息，请参阅 SDK 文档中的 [了解 Windows PowerShell 模块](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-116">For more information, see [Understanding a Windows PowerShell Module](/powershell/scripting/developer/module/understanding-a-windows-powershell-module) in the SDK documentation.</span></span>

## <a name="module-auto-loading"></a><span data-ttu-id="d7b68-117">模块自动加载</span><span class="sxs-lookup"><span data-stu-id="d7b68-117">Module Auto-Loading</span></span>

<span data-ttu-id="d7b68-118">从 PowerShell 3.0 开始，在已安装的模块中首次运行任何命令时，PowerShell 会自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-118">Beginning in PowerShell 3.0, PowerShell imports modules automatically the first time that you run any command in an installed module.</span></span> <span data-ttu-id="d7b68-119">现在，你可以在没有任何设置或配置文件配置的情况下使用模块中的命令，因此在计算机上安装模块后，无需再对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="d7b68-119">You can now use the commands in a module without any set-up or profile configuration, so there's no need to manage modules after you install them on your computer.</span></span>

<span data-ttu-id="d7b68-120">模块中的命令也更易于查找。</span><span class="sxs-lookup"><span data-stu-id="d7b68-120">The commands in a module are also easier to find.</span></span> <span data-ttu-id="d7b68-121">该 `Get-Command` cmdlet 现在获取所有已安装模块中的所有命令，即使它们尚未处于会话中也是如此。</span><span class="sxs-lookup"><span data-stu-id="d7b68-121">The `Get-Command` cmdlet now gets all commands in all installed modules, even if they are not yet in the session.</span></span> <span data-ttu-id="d7b68-122">你可以找到命令并使用它，而无需首先导入模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-122">You can find a command and use it without importing needing to import the module first.</span></span>

<span data-ttu-id="d7b68-123">下面的每个示例都将使包含的 CimCmdlets 模块 `Get-CimInstance` 导入到会话中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-123">Each of the following examples cause the CimCmdlets module, which contains `Get-CimInstance`, to be imported into your session.</span></span>

- <span data-ttu-id="d7b68-124">运行命令</span><span class="sxs-lookup"><span data-stu-id="d7b68-124">Run the Command</span></span>

  ```powershell
  Get-CimInstance Win32_OperatingSystem
  ```

- <span data-ttu-id="d7b68-125">获取命令</span><span class="sxs-lookup"><span data-stu-id="d7b68-125">Get the Command</span></span>

  ```powershell
  Get-Command Get-CimInstance
  ```

- <span data-ttu-id="d7b68-126">获取有关命令的帮助</span><span class="sxs-lookup"><span data-stu-id="d7b68-126">Get Help for the Command</span></span>

  ```powershell
  Get-Help Get-CimInstance
  ```

<span data-ttu-id="d7b68-127">`Get-Command` 包含通配符的命令 (`*`) 视为用于发现，不使用，不导入任何模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-127">`Get-Command` commands that include a wildcard character (`*`) are considered to be for discovery, not use, and do not import any modules.</span></span>

<span data-ttu-id="d7b68-128">仅自动导入存储在由 PSModulePath 环境变量指定的位置中的模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-128">Only modules that are stored in the location specified by the PSModulePath environment variable are automatically imported.</span></span> <span data-ttu-id="d7b68-129">必须通过运行 cmdlet 来导入其他位置中的模块 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-129">Modules in other locations must be imported by running the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="d7b68-130">此外，使用 PowerShell 提供程序的命令不会自动导入模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-130">Also, commands that use PowerShell providers do not automatically import a module.</span></span> <span data-ttu-id="d7b68-131">例如，如果你使用需要 WSMan：驱动器的命令（如 `Get-PSSessionConfiguration` cmdlet），则可能需要运行 `Import-Module` cmdlet 以导入包含驱动器的 **Microsoft. 管理** 模块 `WSMan:` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-131">For example, if you use a command that requires the WSMan: drive, such as the `Get-PSSessionConfiguration` cmdlet, you might need to run the `Import-Module` cmdlet to import the **Microsoft.WSMan.Management** module that includes the `WSMan:` drive.</span></span>

<span data-ttu-id="d7b68-132">你仍可以运行 `Import-Module` 命令来导入模块，并使用该 `$PSModuleAutoloadingPreference` 变量来启用、禁用和配置模块的自动导入。</span><span class="sxs-lookup"><span data-stu-id="d7b68-132">You can still run the `Import-Module` command to import a module and use the `$PSModuleAutoloadingPreference` variable to enable, disable and configure automatic importing of modules.</span></span> <span data-ttu-id="d7b68-133">有关详细信息，请参阅 [about_Preference_Variables](about_Preference_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-133">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

## <a name="how-to-use-a-module"></a><span data-ttu-id="d7b68-134">如何使用模块</span><span class="sxs-lookup"><span data-stu-id="d7b68-134">How to Use a Module</span></span>

<span data-ttu-id="d7b68-135">若要使用模块，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d7b68-135">To use a module, perform the following tasks:</span></span>

1. <span data-ttu-id="d7b68-136">安装模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-136">Install the module.</span></span> <span data-ttu-id="d7b68-137">（通常已为你完成这一步。）</span><span class="sxs-lookup"><span data-stu-id="d7b68-137">(This is often done for you.)</span></span>
1. <span data-ttu-id="d7b68-138">找到模块所添加的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-138">Find the commands that the module added.</span></span>
1. <span data-ttu-id="d7b68-139">使用模块所添加的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-139">Use the commands that the module added.</span></span>

<span data-ttu-id="d7b68-140">本主题介绍了如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="d7b68-140">This topic explains how to perform these tasks.</span></span> <span data-ttu-id="d7b68-141">它还包括有关管理模块的其他有用信息。</span><span class="sxs-lookup"><span data-stu-id="d7b68-141">It also includes other useful information about managing modules.</span></span>

## <a name="how-to-install-a-module"></a><span data-ttu-id="d7b68-142">如何安装模块</span><span class="sxs-lookup"><span data-stu-id="d7b68-142">How to Install a Module</span></span>

<span data-ttu-id="d7b68-143">如果接收到的模块中包含文件，则需要将其安装到计算机上，然后才能在 PowerShell 中使用它。</span><span class="sxs-lookup"><span data-stu-id="d7b68-143">If you receive a module as a folder with files in it, you need to install it on your computer before you can use it in PowerShell.</span></span>

<span data-ttu-id="d7b68-144">已为你安装好大多数模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-144">Most modules are installed for you.</span></span> <span data-ttu-id="d7b68-145">PowerShell 附带几个预安装的模块，有时称为 _核心_ 模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-145">PowerShell comes with several preinstalled modules, sometimes called the _core_ modules.</span></span> <span data-ttu-id="d7b68-146">在基于 Windows 的计算机上，如果操作系统附带的功能具有用于管理它们的 cmdlet，则会预安装这些模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-146">On Windows-based computers, if features that are included with the operating system have cmdlets to manage them, those modules are preinstalled.</span></span> <span data-ttu-id="d7b68-147">在安装 Windows 功能时，可以使用服务器管理器中的 "添加角色和功能向导"，或在 "控制面板" 的 "打开或关闭 Windows 功能" 对话框中安装所有作为功能组成部分的 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-147">When you install a Windows feature, by using, for example, the Add Roles and Features Wizard in Server Manager, or the Turn Windows features on or off dialog box in Control Panel, any PowerShell modules that are part of the feature are installed.</span></span> <span data-ttu-id="d7b68-148">许多其他模块随附在用于安装模块的安装程序中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-148">Many other modules come in an installer or Setup program that installs the module.</span></span>

<span data-ttu-id="d7b68-149">使用以下命令为当前用户创建 **模块** 目录：</span><span class="sxs-lookup"><span data-stu-id="d7b68-149">Use the following command to create a **Modules** directory for the current user:</span></span>

```powershell
New-Item -Type Directory -Path $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="d7b68-150">将整个模块文件夹复制到 Modules 目录中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-150">Copy the entire module folder into the Modules directory.</span></span> <span data-ttu-id="d7b68-151">可以使用任何方法复制文件夹，包括 Windows 资源管理器和 Cmd.exe，以及 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d7b68-151">You can use any method to copy the folder, including Windows Explorer and Cmd.exe, as well as PowerShell.</span></span> <span data-ttu-id="d7b68-152">在 PowerShell 中使用 `Copy-Item` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d7b68-152">In PowerShell use the `Copy-Item` cmdlet.</span></span> <span data-ttu-id="d7b68-153">例如，要将中的 MyModule 文件夹复制 `C:\ps-test\MyModule` 到模块目录，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-153">For example, to copy the MyModule folder from `C:\ps-test\MyModule` to the Modules directory, type:</span></span>

```powershell
Copy-Item -Path C:\ps-test\MyModule -Destination `
    $HOME\Documents\PowerShell\Modules
```

<span data-ttu-id="d7b68-154">你可以在任何位置上安装模块，但在默认模块位置中安装模块可使其更易于管理。</span><span class="sxs-lookup"><span data-stu-id="d7b68-154">You can install a module in any location, but installing your modules in a default module location makes them easier to manage.</span></span> <span data-ttu-id="d7b68-155">有关默认模块位置的详细信息，请参阅 [module 和 DSC 资源位置和 PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) 部分。</span><span class="sxs-lookup"><span data-stu-id="d7b68-155">For more information about the default module locations, see the [Module and DSC Resource Locations, and PSModulePath](#module-and-dsc-resource-locations-and-psmodulepath) section.</span></span>

## <a name="how-to-find-installed-modules"></a><span data-ttu-id="d7b68-156">如何查找已安装的模块</span><span class="sxs-lookup"><span data-stu-id="d7b68-156">How to Find Installed Modules</span></span>

<span data-ttu-id="d7b68-157">若要查找已安装在默认模块位置中但尚未导入到会话中的模块，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-157">To find modules that are installed in a default module location, but not yet imported into your session, type:</span></span>

```powershell
Get-Module -ListAvailable
```

<span data-ttu-id="d7b68-158">若要查找已导入到会话中的模块，请在 PowerShell 提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-158">To find the modules that have already been imported into your session, at the PowerShell prompt, type:</span></span>

```powershell
Get-Module
```

<span data-ttu-id="d7b68-159">有关 cmdlet 的详细信息 `Get-Module` ，请参阅 [get-help](xref:Microsoft.PowerShell.Core.Get-Module)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-159">For more information about the `Get-Module` cmdlet, see [Get-Module](xref:Microsoft.PowerShell.Core.Get-Module).</span></span>

## <a name="how-to-find-the-commands-in-a-module"></a><span data-ttu-id="d7b68-160">如何查找模块中的命令</span><span class="sxs-lookup"><span data-stu-id="d7b68-160">How to Find the Commands in a Module</span></span>

<span data-ttu-id="d7b68-161">使用 `Get-Command` cmdlet 查找所有可用的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-161">Use the `Get-Command` cmdlet to find all available commands.</span></span> <span data-ttu-id="d7b68-162">可以使用 cmdlet 的参数 `Get-Command` 按模块、名称和名词来筛选命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-162">You can use the parameters of the `Get-Command` cmdlet to filter commands such as by module, name, and noun.</span></span>

<span data-ttu-id="d7b68-163">若要查找模块中的所有命令，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-163">To find all commands in a module, type:</span></span>

```powershell
Get-Command -Module <module-name>
```

<span data-ttu-id="d7b68-164">例如，若要查找 BitsTransfer 模块中的命令，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-164">For example, to find the commands in the BitsTransfer module, type:</span></span>

```powershell
Get-Command -Module BitsTransfer
```

<span data-ttu-id="d7b68-165">有关 cmdlet 的详细信息 `Get-Command` ，请参阅 [获取-命令](xref:Microsoft.PowerShell.Core.Get-Command)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-165">For more information about the `Get-Command` cmdlet, see [Get-Command](xref:Microsoft.PowerShell.Core.Get-Command).</span></span>

## <a name="how-to-get-help-for-the-commands-in-a-module"></a><span data-ttu-id="d7b68-166">如何获取有关模块中的命令的帮助</span><span class="sxs-lookup"><span data-stu-id="d7b68-166">How to Get Help for the Commands in a Module</span></span>

<span data-ttu-id="d7b68-167">如果模块包含它所导出的命令的帮助文件，则该 `Get-Help` cmdlet 将显示帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d7b68-167">If the module contains Help files for the commands that it exports, the `Get-Help` cmdlet will display the Help topics.</span></span> <span data-ttu-id="d7b68-168">使用用于 `Get-Help` 获取 PowerShell 中任何命令的帮助的相同命令格式。</span><span class="sxs-lookup"><span data-stu-id="d7b68-168">Use the same `Get-Help` command format that you would use to get help for any command in PowerShell.</span></span>

<span data-ttu-id="d7b68-169">从 PowerShell 3.0 开始，你可以下载模块的帮助文件，并下载帮助文件的更新，以使它们永远不会过时。</span><span class="sxs-lookup"><span data-stu-id="d7b68-169">Beginning in PowerShell 3.0, you can download Help files for a module and download updates to the Help files so they are never obsolete.</span></span>

<span data-ttu-id="d7b68-170">若要获取有关模块中的命令的帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-170">To get help for a commands in a module, type:</span></span>

```powershell
Get-Help <command-name>
```

<span data-ttu-id="d7b68-171">若要获取模块中命令的联机帮助，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-171">To get help online for command in a module, type:</span></span>

```powershell
Get-Help <command-name> -Online
```

<span data-ttu-id="d7b68-172">若要下载并安装模块中的命令的帮助文件，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-172">To download and install the help files for the commands in a module, type:</span></span>

```powershell
Update-Help -Module <module-name>
```

<span data-ttu-id="d7b68-173">有关详细信息，请参阅 [get-help](xref:Microsoft.PowerShell.Core.Get-Help) 和 [update-help](xref:Microsoft.PowerShell.Core.Update-Help)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-173">For more information, see [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) and [Update-Help](xref:Microsoft.PowerShell.Core.Update-Help).</span></span>

## <a name="how-to-import-a-module"></a><span data-ttu-id="d7b68-174">如何导入模块</span><span class="sxs-lookup"><span data-stu-id="d7b68-174">How to Import a Module</span></span>

<span data-ttu-id="d7b68-175">你可能需要导入模块或导入模块文件。</span><span class="sxs-lookup"><span data-stu-id="d7b68-175">You might have to import a module or import a module file.</span></span> <span data-ttu-id="d7b68-176">如果模块未安装在由 **PSModulePath** 环境变量指定的位置， `$env:PSModulePath` 或者模块包含文件（例如 .dll 或 hbase-runner.psm1 文件），而不是作为文件夹传递的典型模块，则需要导入。</span><span class="sxs-lookup"><span data-stu-id="d7b68-176">Importing is required when a module is not installed in the locations specified by the **PSModulePath** environment variable, `$env:PSModulePath`, or the module consists of file, such as a .dll or .psm1 file, instead of typical module that is delivered as a folder.</span></span>

<span data-ttu-id="d7b68-177">你还可以选择导入模块，以便可以使用命令的参数 `Import-Module` ，如 Prefix 参数，该参数可将一个特殊前缀添加到所有已导入命令的名词名称中，或 **NoClobber** 参数，这会阻止模块添加会隐藏或替换会话中的现有命令的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-177">You might also choose to import a module so that you can use the parameters of the `Import-Module` command, such as the Prefix parameter, which adds a distinctive prefix to the noun names of all imported commands, or the **NoClobber** parameter, which prevents the module from adding commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="d7b68-178">若要导入模块，请使用 `Import-Module` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d7b68-178">To import modules, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="d7b68-179">若要将 PSModulePath 位置中的模块导入到当前会话中，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="d7b68-179">To import modules in a PSModulePath location into the current session, use the following command format.</span></span>

```powershell
Import-Module <module-name>
```

<span data-ttu-id="d7b68-180">例如，以下命令将 BitsTransfer 模块导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-180">For example, the following command imports the BitsTransfer module into the current session.</span></span>

```powershell
Import-Module BitsTransfer
```

<span data-ttu-id="d7b68-181">若要导入不在默认模块位置中的模块，请使用指向命令中的模块文件夹的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="d7b68-181">To import a module that is not in a default module location, use the fully qualified path to the module folder in the command.</span></span>

<span data-ttu-id="d7b68-182">例如，若要将目录中的 TestCmdlets 模块添加 `C:\ps-test` 到会话中，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-182">For example, to add the TestCmdlets module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets
```

<span data-ttu-id="d7b68-183">若要导入未包含在模块文件夹中的模块文件，请使用指向命令中的模块文件的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="d7b68-183">To import a module file that is not contained in a module folder, use the fully qualified path to the module file in the command.</span></span>

<span data-ttu-id="d7b68-184">例如，若要将目录中的 TestCmdlets.dll 模块添加 `C:\ps-test` 到会话中，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-184">For example, to add the TestCmdlets.dll module in the `C:\ps-test` directory to your session, type:</span></span>

```powershell
Import-Module C:\ps-test\TestCmdlets.dll
```

<span data-ttu-id="d7b68-185">有关向会话添加模块的详细信息，请参阅 [import-module](xref:Microsoft.PowerShell.Core.Import-Module)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-185">For more information about adding modules to your session, see [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module).</span></span>

## <a name="how-to-import-a-module-into-every-session"></a><span data-ttu-id="d7b68-186">如何将模块导入到每个会话中</span><span class="sxs-lookup"><span data-stu-id="d7b68-186">How to Import a Module into Every Session</span></span>

<span data-ttu-id="d7b68-187">`Import-Module`命令将模块导入当前 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="d7b68-187">The `Import-Module` command imports modules into your current PowerShell session.</span></span> <span data-ttu-id="d7b68-188">若要将模块导入到启动的每个 PowerShell 会话，请将 `Import-Module` 命令添加到 powershell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="d7b68-188">To import a module into every PowerShell session that you start, add the `Import-Module` command to your PowerShell profile.</span></span>

<span data-ttu-id="d7b68-189">有关配置文件的详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-189">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="how-to-remove-a-module"></a><span data-ttu-id="d7b68-190">如何删除模块</span><span class="sxs-lookup"><span data-stu-id="d7b68-190">How to Remove a Module</span></span>

<span data-ttu-id="d7b68-191">当你删除模块时，该模块所添加的命令将从会话中删除。</span><span class="sxs-lookup"><span data-stu-id="d7b68-191">When you remove a module, the commands that the module added are deleted from the session.</span></span>

<span data-ttu-id="d7b68-192">若要从会话中删除模块，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="d7b68-192">To remove a module from your session, use the following command format.</span></span>

```powershell
Remove-Module <module-name>
```

<span data-ttu-id="d7b68-193">例如，以下命令将从当前会话中删除 BitsTransfer 模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-193">For example, the following command removes the BitsTransfer module from the current session.</span></span>

```powershell
Remove-Module BitsTransfer
```

<span data-ttu-id="d7b68-194">删除模块与导入模块的操作相反。</span><span class="sxs-lookup"><span data-stu-id="d7b68-194">Removing a module reverses the operation of importing a module.</span></span> <span data-ttu-id="d7b68-195">删除模块不会卸载该模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-195">Removing a module does not uninstall the module.</span></span> <span data-ttu-id="d7b68-196">有关详细信息，请参阅 [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-196">For more information, see [Remove-Module](xref:Microsoft.PowerShell.Core.Remove-Module).</span></span>

## <a name="module-and-dsc-resource-locations-and-psmodulepath"></a><span data-ttu-id="d7b68-197">模块和 DSC 资源位置以及 PSModulePath</span><span class="sxs-lookup"><span data-stu-id="d7b68-197">Module and DSC Resource Locations, and PSModulePath</span></span>

<span data-ttu-id="d7b68-198">`$env:PSModulePath`环境变量包含一个文件夹位置列表，将在其中进行搜索以查找模块和资源。</span><span class="sxs-lookup"><span data-stu-id="d7b68-198">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

<span data-ttu-id="d7b68-199">默认情况下，分配到的有效位置 `$env:PSModulePath` 为：</span><span class="sxs-lookup"><span data-stu-id="d7b68-199">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

- <span data-ttu-id="d7b68-200">系统范围内的位置： `$PSHOME\Modules`</span><span class="sxs-lookup"><span data-stu-id="d7b68-200">System-wide locations: `$PSHOME\Modules`</span></span>

  <span data-ttu-id="d7b68-201">这些文件夹包含 Windows 和 PowerShell 附带的模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-201">These folders contain modules that ship with Windows and PowerShell.</span></span>

  <span data-ttu-id="d7b68-202">PowerShell 附带的 DSC 资源存储在 `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-202">DSC resources that are included with PowerShell are stored in the `$PSHOME\Modules\PSDesiredStateConfiguration\DSCResources` folder.</span></span>

- <span data-ttu-id="d7b68-203">特定于用户的模块：这些是用户在用户范围中安装的模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-203">User-specific modules: These are modules installed by the user in the user's scope.</span></span> <span data-ttu-id="d7b68-204">`Install-Module` 具有 **作用域** 参数，该参数可用于指定是为当前用户还是为所有用户安装该模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-204">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="d7b68-205">有关详细信息，请参阅 [Install-Module](xref:PowerShellGet.Install-Module)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-205">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

  <span data-ttu-id="d7b68-206">Windows 上用户特定的 **CurrentUser** 位置是 `PowerShell\Modules` 位于用户配置文件的 " **文档** " 位置中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d7b68-206">The user-specific **CurrentUser** location on Windows is the `PowerShell\Modules` folder located in the **Documents** location in your user profile.</span></span> <span data-ttu-id="d7b68-207">该位置的特定路径因 Windows 版本而异，无论是否正在使用文件夹重定向。</span><span class="sxs-lookup"><span data-stu-id="d7b68-207">The specific path of that location varies by version of Windows and whether or not you are using folder redirection.</span></span> <span data-ttu-id="d7b68-208">Microsoft OneDrive 还可以更改 **文档** 文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="d7b68-208">Microsoft OneDrive can also change the location of your **Documents** folder.</span></span>

  <span data-ttu-id="d7b68-209">默认情况下，在 Windows 10 上，该位置是 `$HOME\Documents\PowerShell\Modules` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-209">By default, on Windows 10, that location is `$HOME\Documents\PowerShell\Modules`.</span></span> <span data-ttu-id="d7b68-210">在 Linux 或 Mac 上， **CurrentUser** 位置是 `$HOME/.local/share/powershell/Modules` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-210">On Linux or Mac, the **CurrentUser** location is `$HOME/.local/share/powershell/Modules`.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d7b68-211">可以使用以下命令来验证 **Documents** 文件夹的位置： `[Environment]::GetFolderPath('MyDocuments')` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-211">You can verify the location of your **Documents** folder using the following command: `[Environment]::GetFolderPath('MyDocuments')`.</span></span>

- <span data-ttu-id="d7b68-212">**AllUsers** 位置 `$env:PROGRAMFILES\PowerShell\Modules` 在 Windows 上。</span><span class="sxs-lookup"><span data-stu-id="d7b68-212">The **AllUsers** location is `$env:PROGRAMFILES\PowerShell\Modules` on Windows.</span></span> <span data-ttu-id="d7b68-213">在 Linux 或 Mac 上，模块存储在中 `/usr/local/share/powershell/Modules` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-213">On Linux or Mac the modules are stored at `/usr/local/share/powershell/Modules`.</span></span>

> [!NOTE]
> <span data-ttu-id="d7b68-214">若要在目录中添加或更改文件 `$env:Windir\System32` ，请以 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d7b68-214">To add or change files in the `$env:Windir\System32` directory, start PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="d7b68-215">可以通过更改 **PSModulePath** 环境变量的值来更改系统上的默认模块位置 `$Env:PSModulePath` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-215">You can change the default module locations on your system by changing the value of the **PSModulePath** environment variable, `$Env:PSModulePath`.</span></span> <span data-ttu-id="d7b68-216">**PSModulePath** 环境变量在 Path 环境变量上建模，具有相同的格式。</span><span class="sxs-lookup"><span data-stu-id="d7b68-216">The **PSModulePath** environment variable is modeled on the Path environment variable and has the same format.</span></span>

<span data-ttu-id="d7b68-217">若要查看默认模块位置，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-217">To view the default module locations, type:</span></span>

```powershell
$Env:PSModulePath
```

<span data-ttu-id="d7b68-218">若要添加默认模块位置，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="d7b68-218">To add a default module location, use the following command format.</span></span>

```powershell
$Env:PSModulePath = $Env:PSModulePath + ";<path>"
```

<span data-ttu-id="d7b68-219">命令中的分号 (`;`) 将新路径与列表中其前面的路径分隔开。</span><span class="sxs-lookup"><span data-stu-id="d7b68-219">The semi-colon (`;`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="d7b68-220">例如，若要添加 `C:\ps-test\Modules` 目录，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-220">For example, to add the `C:\ps-test\Modules` directory, type:</span></span>

```powershell
$Env:PSModulePath + ";C:\ps-test\Modules"
```

<span data-ttu-id="d7b68-221">若要在 Linux 或 MacOS 上添加默认模块位置，请使用以下命令格式：</span><span class="sxs-lookup"><span data-stu-id="d7b68-221">To add a default module location on Linux or MacOS, use the following command format:</span></span>

```powershell
$Env:PSModulePath += ":<path>"
```

<span data-ttu-id="d7b68-222">例如，若要将 `/usr/local/Fabrikam/Modules` 目录添加到 **PSModulePath** 环境变量的值，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-222">For example, to add the `/usr/local/Fabrikam/Modules` directory to the value of the **PSModulePath** environment variable, type:</span></span>

```powershell
$Env:PSModulePath += ":/usr/local/Fabrikam/Modules"
```

<span data-ttu-id="d7b68-223">在 Linux 或 MacOS 上，命令中的冒号 (`:`) 将新路径与列表中其前面的路径分隔开。</span><span class="sxs-lookup"><span data-stu-id="d7b68-223">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

<span data-ttu-id="d7b68-224">将路径添加到 **PSModulePath** 时， `Get-Module` 和 `Import-Module` 命令包括该路径中的模块。</span><span class="sxs-lookup"><span data-stu-id="d7b68-224">When you add a path to **PSModulePath**, `Get-Module` and `Import-Module` commands include modules in that path.</span></span>

<span data-ttu-id="d7b68-225">你所设置的值仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="d7b68-225">The value that you set affects only the current session.</span></span> <span data-ttu-id="d7b68-226">要使更改保持不变，请将命令添加到 PowerShell 配置文件，或使用控制面板中的 "系统" 来更改注册表中的 **PSModulePath** 环境变量的值。</span><span class="sxs-lookup"><span data-stu-id="d7b68-226">To make the change persistent, add the command to your PowerShell profile or use System in Control Panel to change the value of the **PSModulePath** environment variable in the registry.</span></span>

<span data-ttu-id="d7b68-227">此外，若要使更改保持不变，还可以使用 **SetEnvironmentVariable** **类的** 方法将路径添加到 **PSModulePath** 环境变量。</span><span class="sxs-lookup"><span data-stu-id="d7b68-227">Also, to make the change persistent, you can also use the **SetEnvironmentVariable** method of the **System.Environment** class to add a Path to the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="d7b68-228">有关 **PSModulePath** 变量的详细信息，请参阅 [about_Environment_Variables](about_Environment_Variables.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-228">For more information about the **PSModulePath** variable, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

## <a name="modules-and-name-conflicts"></a><span data-ttu-id="d7b68-229">模块和名称冲突</span><span class="sxs-lookup"><span data-stu-id="d7b68-229">Modules and Name Conflicts</span></span>

<span data-ttu-id="d7b68-230">当会话中的多个命令具有相同的名称时，会发生名称冲突。</span><span class="sxs-lookup"><span data-stu-id="d7b68-230">Name conflicts occur when more than one command in the session has the same name.</span></span> <span data-ttu-id="d7b68-231">当模块中的命令与会话中的命令或项具有相同名称时，导入模块将引起名称冲突。</span><span class="sxs-lookup"><span data-stu-id="d7b68-231">Importing a module causes a name conflict when commands in the module have the same names as commands or items in the session.</span></span>

<span data-ttu-id="d7b68-232">名称冲突可能会导致命令被隐藏或替换。</span><span class="sxs-lookup"><span data-stu-id="d7b68-232">Name conflicts can result in commands being hidden or replaced.</span></span>

### <a name="hidden"></a><span data-ttu-id="d7b68-233">Hidden</span><span class="sxs-lookup"><span data-stu-id="d7b68-233">Hidden</span></span>

<span data-ttu-id="d7b68-234">当某个命令不是键入命令名称后所运行的命令时，该命令将隐藏，但你可以使用另一种方法来运行它，例如通过使用模块名称或创建它的管理单元的名称来限定命令名称。</span><span class="sxs-lookup"><span data-stu-id="d7b68-234">A command is hidden when it is not the command that runs when you type the command name, but you can run it by using another method, such as by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

### <a name="replaced"></a><span data-ttu-id="d7b68-235">已替换</span><span class="sxs-lookup"><span data-stu-id="d7b68-235">Replaced</span></span>

<span data-ttu-id="d7b68-236">当由于具有相同名称的命令已覆盖某个命令而无法运行该命令时，该命令即被替换。</span><span class="sxs-lookup"><span data-stu-id="d7b68-236">A command is replaced when you cannot run it because it has been overwritten by a command with the same name.</span></span> <span data-ttu-id="d7b68-237">即使删除导致冲突的模块，也无法运行替换的命令，除非重新启动该会话。</span><span class="sxs-lookup"><span data-stu-id="d7b68-237">Even when you remove the module that caused the conflict, you cannot run a replaced command unless you restart the session.</span></span>

<span data-ttu-id="d7b68-238">`Import-Module` 可以添加用于隐藏和替换当前会话中的命令的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-238">`Import-Module` might add commands that hide and replace commands in the current session.</span></span> <span data-ttu-id="d7b68-239">此外，你的会话中的命令可以隐藏模块所添加的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-239">Also, commands in your session can hide commands that the module added.</span></span>

<span data-ttu-id="d7b68-240">若要检测名称冲突，请使用 cmdlet 的 **All** 参数 `Get-Command` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-240">To detect name conflicts, use the **All** parameter of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="d7b68-241">从 PowerShell 3.0 开始， `Get-Command` 仅获取键入命令名称时运行的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-241">Beginning in PowerShell 3.0, `Get-Command` gets only that commands that run when you type the command name.</span></span> <span data-ttu-id="d7b68-242">**All** 参数获取会话中具有特定名称的所有命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-242">The **All** parameter gets all commands with the specific name in the session.</span></span>

<span data-ttu-id="d7b68-243">若要防止名称冲突，请使用 cmdlet 的 **NoClobber** 或 **Prefix** 参数 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-243">To prevent name conflicts, use the **NoClobber** or **Prefix** parameters of the `Import-Module` cmdlet.</span></span> <span data-ttu-id="d7b68-244">**Prefix** 参数将前缀添加到已导入命令的名称，以便它们在会话中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="d7b68-244">The **Prefix** parameter adds a prefix to the names of imported commands so that they are unique in the session.</span></span> <span data-ttu-id="d7b68-245">**NoClobber** 参数不会导入任何将隐藏或替换会话中的现有命令的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-245">The **NoClobber** parameter does not import any commands that would hide or replace existing commands in the session.</span></span>

<span data-ttu-id="d7b68-246">你还可以使用的 **Alias**、 **Cmdlet**、 **Function** 和 **Variable** 参数 `Import-Module` 来仅选择要导入的命令，并且可以排除在会话中引起名称冲突的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-246">You can also use the **Alias**, **Cmdlet**, **Function**, and **Variable** parameters of `Import-Module` to select only the commands that you want to import, and you can exclude commands that cause name conflicts in your session.</span></span>

<span data-ttu-id="d7b68-247">模块作者可以通过使用模块清单的 **DefaultCommandPrefix** 属性来将默认前缀添加到所有命令名称，从而防止名称冲突。</span><span class="sxs-lookup"><span data-stu-id="d7b68-247">Module authors can prevent name conflicts by using the **DefaultCommandPrefix** property of the module manifest to add a default prefix to all command names.</span></span>
<span data-ttu-id="d7b68-248">**Prefix** 参数的值优先于 **DefaultCommandPrefix** 的值。</span><span class="sxs-lookup"><span data-stu-id="d7b68-248">The value of the **Prefix** parameter takes precedence over the value of **DefaultCommandPrefix**.</span></span>

<span data-ttu-id="d7b68-249">即使命令处于隐藏状态，你也可以通过使用模块名称或创建该模块的管理单元名称来限定命令名称，从而运行该命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-249">Even if a command is hidden, you can run it by qualifying the command name with the name of the module or snap-in in which it originated.</span></span>

<span data-ttu-id="d7b68-250">PowerShell 命令优先规则确定当会话中包含具有相同名称的命令时运行哪个命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-250">The PowerShell command precedence rules determine which command runs when the session includes commands with the same name.</span></span>

<span data-ttu-id="d7b68-251">例如，当会话中包含具有相同名称的函数和 cmdlet 时，默认情况下，PowerShell 将运行该函数。</span><span class="sxs-lookup"><span data-stu-id="d7b68-251">For example, when a session includes a function and a cmdlet with the same name, PowerShell runs the function by default.</span></span> <span data-ttu-id="d7b68-252">当会话中包含同一类型的同名命令时（例如具有相同名称的两个 cmdlet），它将在默认情况下运行最新添加的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-252">When the session includes commands of the same type with the same name, such as two cmdlets with the same name, by default, it runs the most recently added command.</span></span>

<span data-ttu-id="d7b68-253">有关详细信息，包括优先规则的说明和运行隐藏命令的说明，请参阅 [about_Command_Precedence](about_Command_Precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b68-253">For more information, including an explanation of the precedence rules and instructions for running hidden commands, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

## <a name="modules-and-snap-ins"></a><span data-ttu-id="d7b68-254">模块和管理单元</span><span class="sxs-lookup"><span data-stu-id="d7b68-254">Modules and Snap-ins</span></span>

<span data-ttu-id="d7b68-255">你可以从模块和管理单元向会话中添加命令。模块可以添加所有类型的命令，包括 cmdlet、提供程序、函数和项（例如变量、别名和 PowerShell 驱动器）。</span><span class="sxs-lookup"><span data-stu-id="d7b68-255">You can add commands to your session from modules and snap-ins. Modules can add all types of commands, including cmdlets, providers, and functions, and items, such as variables, aliases, and PowerShell drives.</span></span> <span data-ttu-id="d7b68-256">管理单元只可以添加 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="d7b68-256">Snap-ins can add only cmdlets and providers.</span></span>

<span data-ttu-id="d7b68-257">在从会话中删除模块或管理单元之前，请使用以下命令来确定将删除哪些命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-257">Before removing a module or snap-in from your session, use the following commands to determine which commands will be removed.</span></span>

<span data-ttu-id="d7b68-258">若要在会话中查找某个 cmdlet 的源，请使用以下命令格式：</span><span class="sxs-lookup"><span data-stu-id="d7b68-258">To find the source of a cmdlet in your session, use the following command format:</span></span>

```powershell
Get-Command <cmdlet-name> | Format-List -Property verb,noun,pssnapin,module
```

<span data-ttu-id="d7b68-259">例如，若要查找 cmdlet 的源 `Get-Date` ，请键入：</span><span class="sxs-lookup"><span data-stu-id="d7b68-259">For example, to find the source of the `Get-Date` cmdlet, type:</span></span>

```powershell
Get-Command Get-Date | Format-List -Property verb,noun,module
```

## <a name="module-related-warnings-and-errors"></a><span data-ttu-id="d7b68-260">与模块相关的警告和错误</span><span class="sxs-lookup"><span data-stu-id="d7b68-260">Module-related Warnings and Errors</span></span>

<span data-ttu-id="d7b68-261">模块导出的命令应遵循 PowerShell 命令命名规则。</span><span class="sxs-lookup"><span data-stu-id="d7b68-261">The commands that a module exports should follow the PowerShell command naming rules.</span></span> <span data-ttu-id="d7b68-262">如果导入的模块导出名称中包含未经批准的谓词的 cmdlet 或函数，则该 `Import-Module` cmdlet 将显示以下警告消息。</span><span class="sxs-lookup"><span data-stu-id="d7b68-262">If the module that you import exports cmdlets or functions that have unapproved verbs in their names, the `Import-Module` cmdlet displays the following warning message.</span></span>

> <span data-ttu-id="d7b68-263">警告：某些导入的命令名称包括未经批准的动词，这可能会使它们更易发现。</span><span class="sxs-lookup"><span data-stu-id="d7b68-263">WARNING: Some imported command names include unapproved verbs which might make them less discoverable.</span></span> <span data-ttu-id="d7b68-264">请使用 Verbose 参数获取详细信息或者键入 Get-Verb 以查看批准的谓词列表。</span><span class="sxs-lookup"><span data-stu-id="d7b68-264">Use the Verbose parameter for more detail or type Get-Verb to see the list of approved verbs.</span></span>

<span data-ttu-id="d7b68-265">此消息只是一个警告。</span><span class="sxs-lookup"><span data-stu-id="d7b68-265">This message is only a warning.</span></span> <span data-ttu-id="d7b68-266">仍将导入完整的模块，其中包括非一致性的命令。</span><span class="sxs-lookup"><span data-stu-id="d7b68-266">The complete module is still imported, including the non-conforming commands.</span></span> <span data-ttu-id="d7b68-267">尽管会向模块用户显示消息，但是模块作者应修复命名问题。</span><span class="sxs-lookup"><span data-stu-id="d7b68-267">Although the message is displayed to module users, the naming problem should be fixed by the module author.</span></span>

<span data-ttu-id="d7b68-268">若要禁止显示警告消息，请使用 cmdlet 的 **DisableNameChecking** 参数 `Import-Module` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-268">To suppress the warning message, use the **DisableNameChecking** parameter of the `Import-Module` cmdlet.</span></span>

## <a name="built-in-modules-and-snap-ins"></a><span data-ttu-id="d7b68-269">内置模块和管理单元</span><span class="sxs-lookup"><span data-stu-id="d7b68-269">Built-in Modules and Snap-ins</span></span>

<span data-ttu-id="d7b68-270">在 PowerShell 2.0 和 PowerShell 3.0 和更高版本的旧式主机程序中，随 PowerShell 一起安装的核心命令打包在自动添加到每个 PowerShell 会话的管理单元中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-270">In PowerShell 2.0 and in older-style host programs in PowerShell 3.0 and later, the core commands that are installed with PowerShell are packaged in snap-ins that are added automatically to every PowerShell session.</span></span>

<span data-ttu-id="d7b68-271">从 PowerShell 3.0 开始，对于实现 `InitialSessionState.CreateDefault2` 初始会话状态 API 的主机程序，默认情况下会将 "Microsoft" 管理单元添加到每个会话中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-271">Beginning in PowerShell 3.0, for host programs that implement the `InitialSessionState.CreateDefault2` initial session state API the Microsoft.PowerShell.Core snap-in is added to every session by default.</span></span> <span data-ttu-id="d7b68-272">首次使用时，模块会自动加载。</span><span class="sxs-lookup"><span data-stu-id="d7b68-272">Modules are loaded automatically on first-use.</span></span>

> [!NOTE]
> <span data-ttu-id="d7b68-273">远程会话（包括使用 cmdlet 启动的会话） `New-PSSession` 是旧样式的会话，其中内置命令打包在管理单元中。</span><span class="sxs-lookup"><span data-stu-id="d7b68-273">Remote sessions, including sessions that are started by using the `New-PSSession` cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="d7b68-274">以下模块 (或与 PowerShell 一起安装) 的管理单元。</span><span class="sxs-lookup"><span data-stu-id="d7b68-274">The following modules (or snap-ins) are installed with PowerShell.</span></span>

- <span data-ttu-id="d7b68-275">CimCmdlet</span><span class="sxs-lookup"><span data-stu-id="d7b68-275">CimCmdlets</span></span>
- <span data-ttu-id="d7b68-276">Microsoft.PowerShell.Archive</span><span class="sxs-lookup"><span data-stu-id="d7b68-276">Microsoft.PowerShell.Archive</span></span>
- <span data-ttu-id="d7b68-277">Microsoft.PowerShell.Core</span><span class="sxs-lookup"><span data-stu-id="d7b68-277">Microsoft.PowerShell.Core</span></span>
- <span data-ttu-id="d7b68-278">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="d7b68-278">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="d7b68-279">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="d7b68-279">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="d7b68-280">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="d7b68-280">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="d7b68-281">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="d7b68-281">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="d7b68-282">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="d7b68-282">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="d7b68-283">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="d7b68-283">Microsoft.WSMan.Management</span></span>
- <span data-ttu-id="d7b68-284">PackageManagement</span><span class="sxs-lookup"><span data-stu-id="d7b68-284">PackageManagement</span></span>
- <span data-ttu-id="d7b68-285">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="d7b68-285">PowerShellGet</span></span>
- <span data-ttu-id="d7b68-286">PSDesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d7b68-286">PSDesiredStateConfiguration</span></span>
- <span data-ttu-id="d7b68-287">PSDiagnostics</span><span class="sxs-lookup"><span data-stu-id="d7b68-287">PSDiagnostics</span></span>
- <span data-ttu-id="d7b68-288">PSReadline</span><span class="sxs-lookup"><span data-stu-id="d7b68-288">PSReadline</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="d7b68-289">记录模块事件</span><span class="sxs-lookup"><span data-stu-id="d7b68-289">Logging Module Events</span></span>

<span data-ttu-id="d7b68-290">从 PowerShell 3.0 开始，你可以通过将模块和管理单元的 **LogPipelineExecutionDetails** 属性设置为来记录 powershell 模块和管理单元中的 cmdlet 和函数的执行事件 `$True` 。</span><span class="sxs-lookup"><span data-stu-id="d7b68-290">Beginning in PowerShell 3.0, you can record execution events for the cmdlets and functions in PowerShell modules and snap-ins by setting the **LogPipelineExecutionDetails** property of modules and snap-ins to `$True`.</span></span>
<span data-ttu-id="d7b68-291">你还可以使用组策略设置，启用模块日志记录，以便在所有 PowerShell 会话中启用模块日志记录。</span><span class="sxs-lookup"><span data-stu-id="d7b68-291">You can also use a Group Policy setting, Turn on Module Logging, to enable module logging in all PowerShell sessions.</span></span> <span data-ttu-id="d7b68-292">有关详细信息，请参阅日志记录和组策略文章。</span><span class="sxs-lookup"><span data-stu-id="d7b68-292">For more information, see the logging and group policy articles.</span></span>

## <a name="see-also"></a><span data-ttu-id="d7b68-293">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7b68-293">See Also</span></span>

[<span data-ttu-id="d7b68-294">about_Logging_Windows</span><span class="sxs-lookup"><span data-stu-id="d7b68-294">about_Logging_Windows</span></span>](about_Logging_Windows.md)

[<span data-ttu-id="d7b68-295">about_Logging_Non-Windows</span><span class="sxs-lookup"><span data-stu-id="d7b68-295">about_Logging_Non-Windows</span></span>](about_Logging_Non-Windows.md)

[<span data-ttu-id="d7b68-296">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="d7b68-296">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="d7b68-297">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="d7b68-297">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="d7b68-298">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="d7b68-298">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="d7b68-299">Get-Command</span><span class="sxs-lookup"><span data-stu-id="d7b68-299">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="d7b68-300">Get-Help</span><span class="sxs-lookup"><span data-stu-id="d7b68-300">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="d7b68-301">Get-Module</span><span class="sxs-lookup"><span data-stu-id="d7b68-301">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="d7b68-302">Import-Module</span><span class="sxs-lookup"><span data-stu-id="d7b68-302">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="d7b68-303">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="d7b68-303">Remove-Module</span></span>](xref:Microsoft.PowerShell.Core.Remove-Module)
