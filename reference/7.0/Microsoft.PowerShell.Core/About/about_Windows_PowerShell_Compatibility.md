---
description: 介绍 PowerShell 7 的 Windows PowerShell 兼容性功能。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_compatibility?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_Compatibility
ms.openlocfilehash: 777dab1cce4329958337a7c0857b0d712b4387a9
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200025"
---
# <a name="about-windows-powershell-compatibility"></a><span data-ttu-id="6a263-104">关于 Windows PowerShell 兼容性</span><span class="sxs-lookup"><span data-stu-id="6a263-104">About Windows PowerShell compatibility</span></span>

## <a name="short-description"></a><span data-ttu-id="6a263-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="6a263-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6a263-106">介绍 PowerShell 7 的 Windows PowerShell 兼容性功能。</span><span class="sxs-lookup"><span data-stu-id="6a263-106">Describes the Windows PowerShell Compatibility functionality for PowerShell 7.</span></span>

## <a name="long-description"></a><span data-ttu-id="6a263-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="6a263-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6a263-108">除非模块清单指示模块与 PowerShell Core 兼容，否则，将 `%windir%\system32\WindowsPowerShell\v1.0\Modules` 通过 Windows Powershell 兼容性功能在后台 Windows powershell 5.1 进程中加载文件夹中的模块。</span><span class="sxs-lookup"><span data-stu-id="6a263-108">Unless the module manifest indicates that module is compatible with PowerShell Core, modules in the `%windir%\system32\WindowsPowerShell\v1.0\Modules` folder are loaded in a background Windows PowerShell 5.1 process by Windows PowerShell Compatibility feature.</span></span>

### <a name="using-the-compatibility-feature"></a><span data-ttu-id="6a263-109">使用兼容性功能</span><span class="sxs-lookup"><span data-stu-id="6a263-109">Using the Compatibility feature</span></span>

<span data-ttu-id="6a263-110">使用 Windows PowerShell 兼容性功能导入第一个模块时，PowerShell 会创建一个名为的远程会话， `WinPSCompatSession` 该会话在后台 Windows PowerShell 5.1 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="6a263-110">When the first module is imported using Windows PowerShell Compatibility feature, PowerShell creates a remote session named `WinPSCompatSession` that is running in a background Windows PowerShell 5.1 process.</span></span> <span data-ttu-id="6a263-111">此过程是在兼容性功能导入第一个模块时创建的。</span><span class="sxs-lookup"><span data-stu-id="6a263-111">This process is created when the Compatibility feature imports the first module.</span></span> <span data-ttu-id="6a263-112"> (使用 `Remove-Module`) 或 PowerShell 进程退出时，将关闭上一个此类模块。</span><span class="sxs-lookup"><span data-stu-id="6a263-112">The process is closed when the last such module is removed (using `Remove-Module`) or when PowerShell process exits.</span></span>

<span data-ttu-id="6a263-113">`WinPSCompatSession`通过隐式远程处理使用加载到会话中的模块，并将其反射到当前的 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="6a263-113">The modules loaded in the `WinPSCompatSession` session are used via implicit remoting and reflected into current PowerShell session.</span></span> <span data-ttu-id="6a263-114">这与用于 PowerShell 作业的传输方法相同。</span><span class="sxs-lookup"><span data-stu-id="6a263-114">This is the same transport method used for PowerShell jobs.</span></span>

<span data-ttu-id="6a263-115">当模块导入到会话中时 `WinPSCompatSession` ，隐式远程处理会在用户的目录中生成一个代理模块 `$env:Temp` ，并将此代理模块导入到当前的 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="6a263-115">When a module is imported into the `WinPSCompatSession` session, implicit remoting generates a proxy module in the user's `$env:Temp` directory and imports this proxy module into current PowerShell session.</span></span> <span data-ttu-id="6a263-116">这允许 PowerShell 检测使用 Windows PowerShell 兼容性功能加载的模块。</span><span class="sxs-lookup"><span data-stu-id="6a263-116">This allows PowerShell to detect that the module was loaded using Windows PowerShell Compatibility functionality.</span></span>

<span data-ttu-id="6a263-117">创建会话后，可以将其用于在反序列化的对象上无法正常工作的操作。</span><span class="sxs-lookup"><span data-stu-id="6a263-117">Once the session is created, it can be used for operations that don't work correctly on deserialized objects.</span></span> <span data-ttu-id="6a263-118">整个管道在 Windows PowerShell 中执行，只返回最终结果。</span><span class="sxs-lookup"><span data-stu-id="6a263-118">The entire pipeline is executed in Windows PowerShell and only the final result is returned.</span></span> <span data-ttu-id="6a263-119">例如：</span><span class="sxs-lookup"><span data-stu-id="6a263-119">For example:</span></span>

```powershell
$s = Get-PSSession -Name WinPSCompatSession
Invoke-Command -Session $s -ScriptBlock {
  "Running in Windows PowerShell version $($PSVersionTable.PSVersion)"
}
```

<span data-ttu-id="6a263-120">可以通过两种方法调用兼容性功能：</span><span class="sxs-lookup"><span data-stu-id="6a263-120">The Compatibility feature can be invoked in two ways:</span></span>

- <span data-ttu-id="6a263-121">使用 **UseWindowsPowerShell** 参数通过导入模块显式</span><span class="sxs-lookup"><span data-stu-id="6a263-121">Explicitly by importing a module using the **UseWindowsPowerShell** parameter</span></span>

   ```powershell
   Import-Module -Name ScheduledTasks -UseWindowsPowerShell
   ```

- <span data-ttu-id="6a263-122">通过命令发现以模块名称、路径或自动加载的方式隐式导入 Windows PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="6a263-122">Implicitly by importing a Windows PowerShell module by module name, path, or autoloading via command discovery.</span></span>

   ```powershell
   Import-Module -Name ServerManager
   Get-AppLockerPolicy -Local
   ```

   <span data-ttu-id="6a263-123">如果尚未加载，则在运行时会加载 AppLocker 模块  `Get-AppLockerPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="6a263-123">If not already loaded, the AppLocker module is autoloaded when you run  `Get-AppLockerPolicy`.</span></span>

<span data-ttu-id="6a263-124">Windows PowerShell 兼容性会阻止加载 `WindowsPowerShellCompatibilityModuleDenyList` PowerShell 配置文件中的设置中列出的模块。</span><span class="sxs-lookup"><span data-stu-id="6a263-124">Windows PowerShell Compatibility blocks loading of modules that are listed in the `WindowsPowerShellCompatibilityModuleDenyList` setting in PowerShell configuration file.</span></span>

<span data-ttu-id="6a263-125">此设置的默认值为：</span><span class="sxs-lookup"><span data-stu-id="6a263-125">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityModuleDenyList":  [
   "PSScheduledJob","BestPractices","UpdateServices"
]
```

### <a name="managing-implicit-module-loading"></a><span data-ttu-id="6a263-126">管理隐式模块加载</span><span class="sxs-lookup"><span data-stu-id="6a263-126">Managing implicit module loading</span></span>

<span data-ttu-id="6a263-127">若要禁用 Windows PowerShell 兼容功能的隐式导入行为，请使用 `DisableImplicitWinCompat` PowerShell 配置文件中的设置。</span><span class="sxs-lookup"><span data-stu-id="6a263-127">To disable implicit import behavior of the Windows PowerShell Compatibility feature, use the `DisableImplicitWinCompat` setting in a PowerShell configuration file.</span></span> <span data-ttu-id="6a263-128">此设置可以添加到 `powershell.config.json` 文件中。</span><span class="sxs-lookup"><span data-stu-id="6a263-128">This setting can be added to the `powershell.config.json` file.</span></span> <span data-ttu-id="6a263-129">有关详细信息，请参阅 [about_powershell_config](about_powershell_config.md)。</span><span class="sxs-lookup"><span data-stu-id="6a263-129">For more information, see [about_powershell_config](about_powershell_config.md).</span></span>

<span data-ttu-id="6a263-130">此示例演示如何创建一个配置文件，该文件禁用 Windows PowerShell 兼容性的隐式模块加载功能。</span><span class="sxs-lookup"><span data-stu-id="6a263-130">This example shows how to create a configuration file that disables the implicit module-loading feature of Windows PowerShell Compatibility.</span></span>

```powershell
$ConfigPath = "$PSHOME\DisableWinCompat.powershell.config.json"
$ConfigJSON = ConvertTo-Json -InputObject @{
  "DisableImplicitWinCompat" = $true
  "Microsoft.PowerShell:ExecutionPolicy" = "RemoteSigned"
}
$ConfigJSON | Out-File -Force $ConfigPath
pwsh -settingsFile $ConfigPath
```

<span data-ttu-id="6a263-131">有关模块兼容性的最新信息，请参阅 [PowerShell 7 模块兼容性](https://aka.ms/PSModuleCompat) 列表。</span><span class="sxs-lookup"><span data-stu-id="6a263-131">For more the latest information about module compatibility, see the [PowerShell 7 module compatibility](https://aka.ms/PSModuleCompat) list.</span></span>

### <a name="managing-cmdlet-clobbering"></a><span data-ttu-id="6a263-132">管理 cmdlet clobbering</span><span class="sxs-lookup"><span data-stu-id="6a263-132">Managing cmdlet clobbering</span></span>

<span data-ttu-id="6a263-133">Windows PowerShell 兼容性功能使用隐式远程处理在兼容模式下加载模块。</span><span class="sxs-lookup"><span data-stu-id="6a263-133">The Windows PowerShell Compatibility feature uses implicit remoting to load modules in compatibility mode.</span></span> <span data-ttu-id="6a263-134">结果就是，模块导出的命令优先于当前 PowerShell 7 会话中名称相同的命令。</span><span class="sxs-lookup"><span data-stu-id="6a263-134">The result is that commands exported by the module take precedence over commands of the same name in the current PowerShell 7 session.</span></span> <span data-ttu-id="6a263-135">PowerShell 7.0.0 版包含 PowerShell 随附的核心模块。</span><span class="sxs-lookup"><span data-stu-id="6a263-135">In the PowerShell 7.0.0 release, this included the core modules that ship with PowerShell.</span></span>

<span data-ttu-id="6a263-136">在 PowerShell 7.1 中，此行为已更改，因此不 clobbered 以下核心 PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="6a263-136">In PowerShell 7.1, the behavior was changed so that the following core PowerShell modules are not clobbered:</span></span>

- <span data-ttu-id="6a263-137">ConsoleHost</span><span class="sxs-lookup"><span data-stu-id="6a263-137">Microsoft.PowerShell.ConsoleHost</span></span>
- <span data-ttu-id="6a263-138">Microsoft.PowerShell.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="6a263-138">Microsoft.PowerShell.Diagnostics</span></span>
- <span data-ttu-id="6a263-139">Microsoft.PowerShell.Host</span><span class="sxs-lookup"><span data-stu-id="6a263-139">Microsoft.PowerShell.Host</span></span>
- <span data-ttu-id="6a263-140">Microsoft.PowerShell.Management</span><span class="sxs-lookup"><span data-stu-id="6a263-140">Microsoft.PowerShell.Management</span></span>
- <span data-ttu-id="6a263-141">Microsoft.PowerShell.Security</span><span class="sxs-lookup"><span data-stu-id="6a263-141">Microsoft.PowerShell.Security</span></span>
- <span data-ttu-id="6a263-142">Microsoft.PowerShell.Utility</span><span class="sxs-lookup"><span data-stu-id="6a263-142">Microsoft.PowerShell.Utility</span></span>
- <span data-ttu-id="6a263-143">Microsoft.WSMan.Management</span><span class="sxs-lookup"><span data-stu-id="6a263-143">Microsoft.WSMan.Management</span></span>

<span data-ttu-id="6a263-144">PowerShell 7.1 还添加了列出不应在兼容模式下 clobbered 的其他模块的功能。</span><span class="sxs-lookup"><span data-stu-id="6a263-144">PowerShell 7.1 also added the ability to list additional modules that should not be clobbered by compatibility mode.</span></span>

<span data-ttu-id="6a263-145">你可以将 `WindowsPowerShellCompatibilityNoClobberModuleList` 设置添加到 PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="6a263-145">You can add the `WindowsPowerShellCompatibilityNoClobberModuleList` setting to PowerShell configuration file.</span></span> <span data-ttu-id="6a263-146">此设置的值是以逗号分隔的模块名称列表。</span><span class="sxs-lookup"><span data-stu-id="6a263-146">The value of this setting is a comma-separated list of module names.</span></span> <span data-ttu-id="6a263-147">此设置的默认值为：</span><span class="sxs-lookup"><span data-stu-id="6a263-147">The default value of this setting is:</span></span>

```json
"WindowsPowerShellCompatibilityNoClobberModuleList": [ ]
```

## <a name="limitations"></a><span data-ttu-id="6a263-148">限制</span><span class="sxs-lookup"><span data-stu-id="6a263-148">Limitations</span></span>

<span data-ttu-id="6a263-149">Windows PowerShell 兼容性功能：</span><span class="sxs-lookup"><span data-stu-id="6a263-149">The Windows PowerShell Compatibility functionality:</span></span>

1. <span data-ttu-id="6a263-150">仅在 Windows 计算机上以本地方式运行</span><span class="sxs-lookup"><span data-stu-id="6a263-150">Only works locally on Windows computers</span></span>
1. <span data-ttu-id="6a263-151">要求 Windows PowerShell 5。1</span><span class="sxs-lookup"><span data-stu-id="6a263-151">Requires that Windows PowerShell 5.1</span></span>
1. <span data-ttu-id="6a263-152">对序列化 cmdlet 参数和返回值进行操作，而不是对活动对象进行操作</span><span class="sxs-lookup"><span data-stu-id="6a263-152">Operates on serialized cmdlet parameters and return values, not on live objects</span></span>
1. <span data-ttu-id="6a263-153">导入到 Windows PowerShell 远程处理会话的所有模块共享同一运行空间。</span><span class="sxs-lookup"><span data-stu-id="6a263-153">All modules imported into the Windows PowerShell remoting session share the same runspace.</span></span>

## <a name="keywords"></a><span data-ttu-id="6a263-154">Keywords</span><span class="sxs-lookup"><span data-stu-id="6a263-154">Keywords</span></span>

<span data-ttu-id="6a263-155">about_Windows_PowerShell_Compatibility</span><span class="sxs-lookup"><span data-stu-id="6a263-155">about_Windows_PowerShell_Compatibility</span></span>

## <a name="see-also"></a><span data-ttu-id="6a263-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a263-156">See also</span></span>

[<span data-ttu-id="6a263-157">about_Modules</span><span class="sxs-lookup"><span data-stu-id="6a263-157">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="6a263-158">Import-Module</span><span class="sxs-lookup"><span data-stu-id="6a263-158">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)
