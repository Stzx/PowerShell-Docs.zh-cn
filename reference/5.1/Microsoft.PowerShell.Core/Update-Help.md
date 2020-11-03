---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 4ef0865e81e01746fed77b73e265e68086a7a9e1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "93199210"
---
# <span data-ttu-id="46d75-103">Update-Help</span><span class="sxs-lookup"><span data-stu-id="46d75-103">Update-Help</span></span>

## <span data-ttu-id="46d75-104">摘要</span><span class="sxs-lookup"><span data-stu-id="46d75-104">SYNOPSIS</span></span>
<span data-ttu-id="46d75-105">在计算机上下载和安装最新的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-105">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="46d75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="46d75-106">SYNTAX</span></span>

### <span data-ttu-id="46d75-107">Path（默认值）</span><span class="sxs-lookup"><span data-stu-id="46d75-107">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="46d75-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="46d75-108">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="46d75-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="46d75-109">DESCRIPTION</span></span>

<span data-ttu-id="46d75-110">`Update-Help`Cmdlet 可为 PowerShell 模块下载最新的帮助文件，并将其安装在计算机上。</span><span class="sxs-lookup"><span data-stu-id="46d75-110">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="46d75-111">不需要重新启动 PowerShell 即可使更改生效。</span><span class="sxs-lookup"><span data-stu-id="46d75-111">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="46d75-112">可以使用 `Get-Help` cmdlet 立即查看新的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-112">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="46d75-113">`Update-Help` 检查计算机上的帮助文件的版本。</span><span class="sxs-lookup"><span data-stu-id="46d75-113">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="46d75-114">如果没有模块的帮助文件，或者帮助文件已过时，则会 `Update-Help` 下载最新的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-114">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="46d75-115">可从 internet 或文件共享下载和安装帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-115">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="46d75-116">如果没有参数，则将为 `Update-Help` 支持可更新帮助的所有已安装模块更新会话中的模块的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-116">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="46d75-117">包含当前会话中安装但未加载的模块。</span><span class="sxs-lookup"><span data-stu-id="46d75-117">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="46d75-118">PowerShell 模块存储在环境变量中列出的位置 `$env:PSModulePath` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-118">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="46d75-119">有关详细信息，请参阅 [about_Updatable_Help](./About/about_Updatable_Help.md)。</span><span class="sxs-lookup"><span data-stu-id="46d75-119">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="46d75-120">您可以使用 **Module** 参数为特定模块更新帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-120">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="46d75-121">使用 **UICulture** 参数下载多个语言和区域设置的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-121">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="46d75-122">你还可以 `Update-Help` 在未连接到 internet 的计算机上使用。</span><span class="sxs-lookup"><span data-stu-id="46d75-122">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="46d75-123">首先，使用 `Save-Help` cmdlet 从 internet 下载帮助文件，并将其保存在可由未连接到 internet 的系统访问的共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="46d75-123">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="46d75-124">然后，使用 **SourcePath** 参数 `Update-Help` 从共享中下载更新的帮助文件，并将其安装在计算机上。</span><span class="sxs-lookup"><span data-stu-id="46d75-124">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="46d75-125">可以通过将 `Update-Help` cmdlet 添加到 PowerShell 配置文件来自动执行帮助更新。</span><span class="sxs-lookup"><span data-stu-id="46d75-125">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="46d75-126">默认情况下， `Update-Help` 每台计算机上每天仅运行一次。</span><span class="sxs-lookup"><span data-stu-id="46d75-126">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="46d75-127">若要重写每天一次的限制，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="46d75-127">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="46d75-128">`Update-Help`Cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="46d75-128">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46d75-129">`Update-Help` 需要管理特权。</span><span class="sxs-lookup"><span data-stu-id="46d75-129">`Update-Help` requires administrative privileges.</span></span>
>
> <span data-ttu-id="46d75-130">您必须是计算机上 Administrators 组的成员，才能更新 PowerShell Core 模块的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-130">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="46d75-131">若要下载或更新 PowerShell 安装目录中的模块的帮助文件 (`$PSHOME\Modules`) （包括 PowerShell Core 模块），请使用 "以管理员身份运行" 选项启动 powershell。</span><span class="sxs-lookup"><span data-stu-id="46d75-131">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the Run as administrator option.</span></span>
> <span data-ttu-id="46d75-132">例如：`Start-Process powershell.exe -Verb RunAs`。</span><span class="sxs-lookup"><span data-stu-id="46d75-132">For example: `Start-Process powershell.exe -Verb RunAs`.</span></span>
>
> <span data-ttu-id="46d75-133">你还可以使用 Windows PowerShell 集成脚本环境 (ISE) 中的 "更新 Windows PowerShell 帮助" 菜单项来更新帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-133">You can also update help files by using the Update Windows PowerShell Help menu item in the Help menu in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>
>
> <span data-ttu-id="46d75-134">更新 Windows PowerShell 帮助项运行 `Update-Help` 没有参数的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="46d75-134">The Update Windows PowerShell Help item runs an `Update-Help` cmdlet without parameters.</span></span>
> <span data-ttu-id="46d75-135">若要为目录中的模块更新帮助 `$PSHOME` ，请使用 "以管理员身份运行" 选项启动 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="46d75-135">To update help for modules in the `$PSHOME` directory, start Windows PowerShell ISE by using the Run as administrator option.</span></span>

## <span data-ttu-id="46d75-136">示例</span><span class="sxs-lookup"><span data-stu-id="46d75-136">EXAMPLES</span></span>

### <span data-ttu-id="46d75-137">示例1：为所有模块更新帮助文件</span><span class="sxs-lookup"><span data-stu-id="46d75-137">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="46d75-138">`Update-Help`Cmdlet 将为支持可更新帮助的已安装模块更新帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-138">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="46d75-139">用户界面 (UI) 区域性语言是在操作系统中设置的。</span><span class="sxs-lookup"><span data-stu-id="46d75-139">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="46d75-140">示例2：更新指定模块的帮助文件</span><span class="sxs-lookup"><span data-stu-id="46d75-140">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="46d75-141">`Update-Help`Cmdlet 仅更新以 **Microsoft PowerShell** 开头的模块名称的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-141">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell** .</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="46d75-142">示例3：更新不同语言的帮助文件</span><span class="sxs-lookup"><span data-stu-id="46d75-142">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="46d75-143">该 `Update-Help` cmdlet 将为所有模块更新日语 (ja-jp) 和英语 (en-us) 帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-143">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="46d75-144">如果某个模块没有为指定的 UI 区域性提供帮助文件，则会为该模块和 UI 区域性显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="46d75-144">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="46d75-145">在此示例中，错误消息指示找不到模块的 **Microsoft PowerShell\*\*\*\*帮助文件** 。</span><span class="sxs-lookup"><span data-stu-id="46d75-145">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility** .</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="46d75-146">示例4：自动更新帮助文件</span><span class="sxs-lookup"><span data-stu-id="46d75-146">Example 4: Update help files automatically</span></span>

<span data-ttu-id="46d75-147">此示例将创建一个计划作业，该作业将每天凌晨3:00 为所有模块更新帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-147">This example creates a scheduled job that updates help for all modules every day at 3:00 AM.</span></span>

```powershell
$jobParams = @{
  Name = 'UpdateHelpJob'
  Credential = 'Domain01\User01'
  ScriptBlock = '{Update-Help}'
  Trigger = (New-JobTrigger -Daily -At "3 AM")
}
Register-ScheduledJob @jobParams
```

```Output
Id         Name            JobTriggers     Command                                  Enabled
--         ----            -----------     -------                                  -------
1          UpdateHelpJob   1               Update-Help                              True
```

<span data-ttu-id="46d75-148">`Register-ScheduledJob`Cmdlet 可创建运行命令的计划作业 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-148">The `Register-ScheduledJob` cmdlet creates a scheduled job that runs an `Update-Help` command.</span></span> <span data-ttu-id="46d75-149">该命令使用 **Credential** 参数，以便 `Update-Help` 通过使用计算机上 Administrators 组的成员的凭据来运行。</span><span class="sxs-lookup"><span data-stu-id="46d75-149">The command uses the **Credential** parameter to run `Update-Help` by using the credentials of a member of the Administrators group on the computer.</span></span> <span data-ttu-id="46d75-150">**Trigger** 参数的值是一个 `New-JobTrigger` 命令，该命令创建一个作业触发器，该触发器每天凌晨3:00 启动作业。</span><span class="sxs-lookup"><span data-stu-id="46d75-150">The value of the **Trigger** parameter is a `New-JobTrigger` command that creates a job trigger that starts the job every day at 3:00 AM.</span></span>

<span data-ttu-id="46d75-151">若要运行此 `Register-ScheduledJob` 命令，请使用 "以 **管理员身份运行** " 选项启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="46d75-151">To run the `Register-ScheduledJob` command, start PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="46d75-152">PowerShell 会提示你输入 **Credential** 参数中指定的用户的密码。</span><span class="sxs-lookup"><span data-stu-id="46d75-152">PowerShell prompts you for the password of the user specified in the **Credential** parameter.</span></span> <span data-ttu-id="46d75-153">凭据随计划作业一起存储。</span><span class="sxs-lookup"><span data-stu-id="46d75-153">The credentials are stored with the scheduled job.</span></span> <span data-ttu-id="46d75-154">作业运行时，不会出现提示。</span><span class="sxs-lookup"><span data-stu-id="46d75-154">You aren't prompted when the job runs.</span></span>

<span data-ttu-id="46d75-155">你可以使用 `Get-ScheduledJob` cmdlet 来查看计划作业，使用 `Set-ScheduledJob` cmdlet 对其进行更改，并使用 `Unregister-ScheduledJob` cmdlet 将其删除。</span><span class="sxs-lookup"><span data-stu-id="46d75-155">You can use the `Get-ScheduledJob` cmdlet to view the scheduled job, use the `Set-ScheduledJob` cmdlet to change it, and use the `Unregister-ScheduledJob` cmdlet to delete it.</span></span> <span data-ttu-id="46d75-156">你还可以在以下路径中查看和管理任务计划程序内的计划作业：</span><span class="sxs-lookup"><span data-stu-id="46d75-156">You can also view and manage the scheduled job in Task Scheduler in the following path:</span></span>

<span data-ttu-id="46d75-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span><span class="sxs-lookup"><span data-stu-id="46d75-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

### <span data-ttu-id="46d75-158">示例5：从文件共享更新多台计算机上的帮助文件</span><span class="sxs-lookup"><span data-stu-id="46d75-158">Example 5: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="46d75-159">在此示例中，将从 internet 下载更新的帮助文件，并将其保存在文件共享中。</span><span class="sxs-lookup"><span data-stu-id="46d75-159">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="46d75-160">需要用户凭据才能访问文件共享和安装更新。</span><span class="sxs-lookup"><span data-stu-id="46d75-160">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="46d75-161">使用文件共享时，可以更新防火墙后面或未连接到 internet 的计算机。</span><span class="sxs-lookup"><span data-stu-id="46d75-161">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="46d75-162">此 `Save-Help` 命令将为支持可更新帮助的所有模块下载最新的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-162">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="46d75-163">**DestinationPath** 参数将文件保存在 `\\Server01\Share\PSHelp` 文件共享中。</span><span class="sxs-lookup"><span data-stu-id="46d75-163">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="46d75-164">**Credential** 参数指定有权访问该文件共享的用户。</span><span class="sxs-lookup"><span data-stu-id="46d75-164">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="46d75-165">`Invoke-Command`Cmdlet `Update-Help` 在多台计算机上运行远程命令。</span><span class="sxs-lookup"><span data-stu-id="46d75-165">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="46d75-166">**ComputerName** 参数从 **Servers.txt** 文件中获取远程计算机的列表。</span><span class="sxs-lookup"><span data-stu-id="46d75-166">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="46d75-167">**ScriptBlock** 参数运行 `Update-Help` 命令，并使用 **SourcePath** 参数指定包含更新的帮助文件的文件共享。</span><span class="sxs-lookup"><span data-stu-id="46d75-167">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="46d75-168">**Credential** 参数指定可以访问文件共享的用户并运行远程 `Update-Help` 命令。</span><span class="sxs-lookup"><span data-stu-id="46d75-168">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="46d75-169">示例6：获取已更新的帮助文件的列表</span><span class="sxs-lookup"><span data-stu-id="46d75-169">Example 6: Get a list of updated help files</span></span>

<span data-ttu-id="46d75-170">`Update-Help`Cmdlet 可为指定的模块更新帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-170">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="46d75-171">Cmdlet 使用 **Verbose** common 参数显示已更新的帮助文件的列表。</span><span class="sxs-lookup"><span data-stu-id="46d75-171">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="46d75-172">您可以使用 **Verbose** 来查看特定模块的所有帮助文件或帮助文件的输出。</span><span class="sxs-lookup"><span data-stu-id="46d75-172">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="46d75-173">如果没有 **详细** 参数， `Update-Help` 则不会显示命令的结果。</span><span class="sxs-lookup"><span data-stu-id="46d75-173">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="46d75-174">**详细** 参数输出用于验证是否已更新帮助文件或安装了最新版本。</span><span class="sxs-lookup"><span data-stu-id="46d75-174">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="46d75-175">示例 7：查找支持可更新帮助的模块</span><span class="sxs-lookup"><span data-stu-id="46d75-175">Example 7: Find modules that support Updatable Help</span></span>

<span data-ttu-id="46d75-176">此示例列出了支持可更新帮助的模块。</span><span class="sxs-lookup"><span data-stu-id="46d75-176">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="46d75-177">该命令使用模块的 **HelpInfoUri** 属性来标识支持可更新帮助的模块。</span><span class="sxs-lookup"><span data-stu-id="46d75-177">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="46d75-178">**HelpInfoUri** 属性包含在运行 cmdlet 时重定向的地址 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-178">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### <span data-ttu-id="46d75-179">示例 8：更新的帮助文件清单</span><span class="sxs-lookup"><span data-stu-id="46d75-179">Example 8: Inventory updated help files</span></span>

<span data-ttu-id="46d75-180">在此示例中，该脚本将 `Get-UpdateHelpVersion.ps1` 为每个模块的可更新帮助文件及其版本号创建清单。</span><span class="sxs-lookup"><span data-stu-id="46d75-180">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="46d75-181">该脚本通过使用模块的 **HelpInfoUri** 属性来标识支持可更新帮助的模块。</span><span class="sxs-lookup"><span data-stu-id="46d75-181">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="46d75-182">对于支持可更新帮助的模块，该脚本将查找并分析帮助信息文件 ( \* helpinfo.xml) 以查找最新的版本号。</span><span class="sxs-lookup"><span data-stu-id="46d75-182">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="46d75-183">该脚本使用 **PSCustomObject** 类和哈希表来创建自定义输出对象。</span><span class="sxs-lookup"><span data-stu-id="46d75-183">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## <span data-ttu-id="46d75-184">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="46d75-184">PARAMETERS</span></span>

### <span data-ttu-id="46d75-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="46d75-185">-Credential</span></span>

<span data-ttu-id="46d75-186">指定有权访问由 **SourcePath** 指定的文件系统位置的用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="46d75-186">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath** .</span></span> <span data-ttu-id="46d75-187">仅当命令中使用了 **SourcePath** 或 **LiteralPath** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="46d75-187">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="46d75-188">**Credential** 参数使你可以 `Update-Help` 在远程计算机上运行具有 **SourcePath** 参数的命令。</span><span class="sxs-lookup"><span data-stu-id="46d75-188">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="46d75-189">通过提供显式凭据，你可以在远程计算机上运行该命令并访问第三台计算机上的文件共享，而不会遇到 "拒绝访问" 错误或使用 CredSSP 身份验证委派凭据。</span><span class="sxs-lookup"><span data-stu-id="46d75-189">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="46d75-190">键入用户名（如 **User01** 或 **Domain01\User01** ），或输入 cmdlet 生成的 **PSCredential** 对象 `Get-Credential` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-190">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="46d75-191">如果键入用户名，系统会提示输入密码。</span><span class="sxs-lookup"><span data-stu-id="46d75-191">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="46d75-192">凭据存储在 [PSCredential](/dotnet/api/system.management.automation.pscredential) 对象中，密码存储为 [SecureString](/dotnet/api/system.security.securestring)。</span><span class="sxs-lookup"><span data-stu-id="46d75-192">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="46d75-193">有关 **SecureString** 数据保护的详细信息，请参阅 [SecureString 的安全级别？](/dotnet/api/system.security.securestring#how-secure-is-securestring)。</span><span class="sxs-lookup"><span data-stu-id="46d75-193">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-194">-Force</span><span class="sxs-lookup"><span data-stu-id="46d75-194">-Force</span></span>

<span data-ttu-id="46d75-195">指示此 cmdlet 不遵循每日一次的限制，跳过版本检查，并下载超出 1 GB 限制的文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-195">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="46d75-196">如果没有此参数，则 `Update-Help` 每24小时运行一次。</span><span class="sxs-lookup"><span data-stu-id="46d75-196">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="46d75-197">下载内容限制为每个模块 1 GB 的未压缩内容，并且仅当比计算机上的现有文件更新时，才会安装帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-197">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="46d75-198">每日一次限制可以保护托管帮助文件的服务器，并使你能够将 `Update-Help` 命令添加到 PowerShell 配置文件，而不会导致重复连接或下载的资源成本。</span><span class="sxs-lookup"><span data-stu-id="46d75-198">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="46d75-199">若要在没有 **Force** 参数的情况下，为多个 UI 区域性中的模块更新帮助，请将所有 UI 区域性包括在相同的命令中，例如：</span><span class="sxs-lookup"><span data-stu-id="46d75-199">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-200">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="46d75-200">-FullyQualifiedModule</span></span>

<span data-ttu-id="46d75-201">指定名称以 **ModuleSpecification** 对象的形式指定的模块。</span><span class="sxs-lookup"><span data-stu-id="46d75-201">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="46d75-202">ModuleSpecification 构造函数的 "备注" 部分中介绍了这些模块 [ (Hashtable) ](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)。</span><span class="sxs-lookup"><span data-stu-id="46d75-202">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="46d75-203">例如， **FullyQualifiedModule** 参数接受以下格式指定的模块名称：</span><span class="sxs-lookup"><span data-stu-id="46d75-203">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="46d75-204">或</span><span class="sxs-lookup"><span data-stu-id="46d75-204">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="46d75-205">**ModuleName** 和 **ModuleVersion** 是必需的，但 **Guid** 是可选的。</span><span class="sxs-lookup"><span data-stu-id="46d75-205">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="46d75-206">不能在与 **Module** 参数相同的命令中指定 **FullyQualifiedModule** 参数。</span><span class="sxs-lookup"><span data-stu-id="46d75-206">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-207">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="46d75-207">-LiteralPath</span></span>

<span data-ttu-id="46d75-208">指定更新的帮助文件的文件夹，而不是从 internet 下载。</span><span class="sxs-lookup"><span data-stu-id="46d75-208">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="46d75-209">如果已使用 **SourcePath** `Save-Help` cmdlet 将帮助文件下载到目录，请使用此参数或 SourcePath。</span><span class="sxs-lookup"><span data-stu-id="46d75-209">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="46d75-210">你可以通过管道将目录对象（如从 `Get-Item` 或 `Get-ChildItem` cmdlet）通过管道进行管道 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-210">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="46d75-211">与 **SourcePath** 的值不同， **LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="46d75-211">Unlike the value of **SourcePath** , the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="46d75-212">不会将任何字符解释为通配字符。</span><span class="sxs-lookup"><span data-stu-id="46d75-212">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="46d75-213">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="46d75-213">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="46d75-214">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="46d75-214">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-215">-Module</span><span class="sxs-lookup"><span data-stu-id="46d75-215">-Module</span></span>

<span data-ttu-id="46d75-216">为指定模块更新帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-216">Updates help for the specified modules.</span></span> <span data-ttu-id="46d75-217">在以逗号分隔的列表中输入一个或多个模块名称或名称模式，或指定在每行上列出一个模块名称的文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-217">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="46d75-218">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="46d75-218">Wildcard characters are permitted.</span></span> <span data-ttu-id="46d75-219">可以通过管道将模块从 `Get-Module` cmdlet 布线到 `Update-Help` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="46d75-219">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="46d75-220">你指定的模块必须安装在计算机上，但不必导入到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="46d75-220">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="46d75-221">您可以指定会话中的任何模块或在环境变量中列出的位置中安装的任何模块 `$env:PSModulePath` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-221">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="46d75-222">值为 `*` (所有) 尝试为计算机上安装的所有模块更新帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-222">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="46d75-223">包括不支持可更新帮助的模块。</span><span class="sxs-lookup"><span data-stu-id="46d75-223">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="46d75-224">当该命令遇到不支持可更新帮助的模块时，此值可能会生成错误。</span><span class="sxs-lookup"><span data-stu-id="46d75-224">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="46d75-225">而是不 `Update-Help` 带参数运行。</span><span class="sxs-lookup"><span data-stu-id="46d75-225">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="46d75-226">Cmdlet 的 **module** 参数 `Update-Help` 不接受模块文件或模块清单文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="46d75-226">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="46d75-227">若要为不在某个位置的模块更新帮助 `$env:PSModulePath` ，请在运行该命令之前将模块导入到当前会话中 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-227">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="46d75-228">-Recurse</span><span class="sxs-lookup"><span data-stu-id="46d75-228">-Recurse</span></span>

<span data-ttu-id="46d75-229">在指定的目录中执行对帮助文件的递归搜索。</span><span class="sxs-lookup"><span data-stu-id="46d75-229">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="46d75-230">仅当命令使用 **SourcePath** 参数时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="46d75-230">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-231">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="46d75-231">-SourcePath</span></span>

<span data-ttu-id="46d75-232">指定一个文件系统文件夹，在该文件夹中 `Update-Help` 获取更新的帮助文件，而不是从 internet 下载它们。</span><span class="sxs-lookup"><span data-stu-id="46d75-232">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="46d75-233">输入文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="46d75-233">Enter the path of a folder.</span></span> <span data-ttu-id="46d75-234">不要指定文件名或文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="46d75-234">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="46d75-235">你可以通过管道将一个文件夹（例如，一个 `Get-Item` ）从或 `Get-ChildItem` cmdlet 到 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-235">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="46d75-236">默认情况下，会 `Update-Help` 从 internet 下载更新的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-236">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="46d75-237">使用 **SourcePath** 该 `Save-Help` cmdlet 将已更新的帮助文件下载到目录时，请使用 SourcePath。</span><span class="sxs-lookup"><span data-stu-id="46d75-237">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="46d75-238">若要为 **SourcePath** 指定默认值，请参阅 " **组策略** " 和 " **计算机配置** "，并 **设置 update-help 的默认源路径** 。</span><span class="sxs-lookup"><span data-stu-id="46d75-238">To specify a default value for **SourcePath** , go to **Group Policy** , **Computer Configuration** , and **Set the default source path for Update-Help** .</span></span> <span data-ttu-id="46d75-239">此组策略设置可防止用户使用 `Update-Help` 从 internet 下载帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-239">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="46d75-240">有关详细信息，请参阅 [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md)。</span><span class="sxs-lookup"><span data-stu-id="46d75-240">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-241">-UICulture</span><span class="sxs-lookup"><span data-stu-id="46d75-241">-UICulture</span></span>

<span data-ttu-id="46d75-242">指定 `Update-Help` 使用来获取更新的帮助文件的 UI 区域性值。</span><span class="sxs-lookup"><span data-stu-id="46d75-242">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="46d75-243">输入一个或多个语言代码，例如 **es** 、包含区域性对象的变量或用于获取区域性对象的命令，如 `Get-Culture` 或 `Get-UICulture` 命令。</span><span class="sxs-lookup"><span data-stu-id="46d75-243">Enter one or more language codes, such as **es-ES** , a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="46d75-244">不允许使用通配符，并且你不能提交部分语言代码，例如 **de** 。</span><span class="sxs-lookup"><span data-stu-id="46d75-244">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de** .</span></span>

<span data-ttu-id="46d75-245">默认情况下， `Update-Help` 将在为操作系统设置的 UI 区域性中获取帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-245">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="46d75-246">如果指定 **UICulture** 参数，则 `Update-Help` 仅为指定的 UI 区域性查找帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-246">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

<span data-ttu-id="46d75-247">仅当模块为指定的 UI 区域性提供帮助文件时，使用 **UICulture** 参数的命令才会成功。</span><span class="sxs-lookup"><span data-stu-id="46d75-247">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="46d75-248">如果命令由于指定的 UI 区域性不受支持而失败，将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="46d75-248">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-249">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="46d75-249">-UseDefaultCredentials</span></span>

<span data-ttu-id="46d75-250">指示 `Update-Help` 使用当前用户的凭据运行命令，包括 internet 下载。</span><span class="sxs-lookup"><span data-stu-id="46d75-250">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="46d75-251">默认情况下，在没有显式凭据的情况下运行该命令。</span><span class="sxs-lookup"><span data-stu-id="46d75-251">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="46d75-252">仅当 web 下载使用 NT LAN Manager (NTLM) 、协商或基于 Kerberos 的身份验证时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="46d75-252">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-253">-Confirm</span><span class="sxs-lookup"><span data-stu-id="46d75-253">-Confirm</span></span>

<span data-ttu-id="46d75-254">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="46d75-254">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-255">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="46d75-255">-WhatIf</span></span>

<span data-ttu-id="46d75-256">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="46d75-256">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="46d75-257">cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="46d75-257">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="46d75-258">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="46d75-258">CommonParameters</span></span>

<span data-ttu-id="46d75-259">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="46d75-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="46d75-260">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="46d75-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="46d75-261">输入</span><span class="sxs-lookup"><span data-stu-id="46d75-261">INPUTS</span></span>

### <span data-ttu-id="46d75-262">System.IO.DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="46d75-262">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="46d75-263">你可以通过管道将目录路径传递给 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-263">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="46d75-264">System.Management.Automation.PSModuleInfo</span><span class="sxs-lookup"><span data-stu-id="46d75-264">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="46d75-265">可以通过管道将模块对象从 `Get-Module` cmdlet 传递给 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-265">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="46d75-266">输出</span><span class="sxs-lookup"><span data-stu-id="46d75-266">OUTPUTS</span></span>

### <span data-ttu-id="46d75-267">无</span><span class="sxs-lookup"><span data-stu-id="46d75-267">None</span></span>

<span data-ttu-id="46d75-268">`Update-Help` 不会生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="46d75-268">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="46d75-269">注释</span><span class="sxs-lookup"><span data-stu-id="46d75-269">NOTES</span></span>

<span data-ttu-id="46d75-270">若要更新 PowerShell 核心模块的帮助，其中包含与 PowerShell 一起安装的命令或目录中的任何模块 `$PSHOME\Modules` ，请以 **管理员身份运行** 选项来启动 powershell。</span><span class="sxs-lookup"><span data-stu-id="46d75-270">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator** .</span></span>

<span data-ttu-id="46d75-271">只有计算机上 Administrators 组的成员才能为 PowerShell 核心模块、与 PowerShell 一起安装的命令和文件夹中的模块更新帮助 `$PSHOME\Modules` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-271">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="46d75-272">如果你没有更新帮助文件的权限，你可以在线阅读帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-272">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="46d75-273">例如，`Get-Help Update-Help -Online`。</span><span class="sxs-lookup"><span data-stu-id="46d75-273">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="46d75-274">模块是可更新帮助的最小单位。</span><span class="sxs-lookup"><span data-stu-id="46d75-274">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="46d75-275">不能为特定 cmdlet 更新帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-275">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="46d75-276">若要查找包含特定 cmdlet 的模块，请使用该 cmdlet 的 **ModuleName** 属性 `Get-Command` ，例如 `(Get-Command Update-Help).ModuleName` 。</span><span class="sxs-lookup"><span data-stu-id="46d75-276">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="46d75-277">由于帮助文件安装在模块目录中，因此 `Update-Help` cmdlet 只能为计算机上安装的模块安装更新的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-277">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="46d75-278">但是，该 `Save-Help` cmdlet 可以为未安装在计算机上的模块保存帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-278">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="46d75-279">如果找 `Update-Help` 不到模块的更新帮助文件，或者找不到指定语言的更新帮助，它将以无提示方式继续，而不显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="46d75-279">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="46d75-280">若要查看状态和进度的详细信息，请使用 **Verbose** 参数。</span><span class="sxs-lookup"><span data-stu-id="46d75-280">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="46d75-281">`Update-Help`Cmdlet 是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="46d75-281">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="46d75-282">它在早期版本的 PowerShell 中不起作用。</span><span class="sxs-lookup"><span data-stu-id="46d75-282">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="46d75-283">在同时具有 Windows PowerShell 2.0 和 Windows PowerShell 3.0 的计算机上，使用 `Update-Help` Windows powershell 3.0 会话中的 cmdlet 来下载和更新帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-283">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="46d75-284">Windows PowerShell 2.0 和 Windows PowerShell 3.0 都提供帮助文件。</span><span class="sxs-lookup"><span data-stu-id="46d75-284">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="46d75-285">`Update-Help`和 `Save-Help` cmdlet 使用以下端口下载帮助文件：针对 HTTP 使用端口80，为 HTTPS 使用端口443。</span><span class="sxs-lookup"><span data-stu-id="46d75-285">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="46d75-286">`Update-Help` 支持所有模块和 PowerShell Core 管理单元。它不支持任何其他管理单元。</span><span class="sxs-lookup"><span data-stu-id="46d75-286">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="46d75-287">若要为环境变量中未列出的位置的模块更新帮助 `$env:PSModulePath` ，请将模块导入到当前会话中，然后运行 `Update-Help` 命令。</span><span class="sxs-lookup"><span data-stu-id="46d75-287">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="46d75-288">`Update-Help`不带参数运行，或使用 **module** 参数来指定模块名称。</span><span class="sxs-lookup"><span data-stu-id="46d75-288">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="46d75-289">和 cmdlet 的 **module** 参数 `Update-Help` `Save-Help` 不接受模块文件或模块清单文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="46d75-289">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="46d75-290">所有模块都支持可更新帮助。</span><span class="sxs-lookup"><span data-stu-id="46d75-290">Any module can support Updatable Help.</span></span> <span data-ttu-id="46d75-291">有关在创作的模块中支持可更新帮助的说明，请参阅 [支持可更新帮助](/powershell/scripting/developer/module/supporting-updatable-help)。</span><span class="sxs-lookup"><span data-stu-id="46d75-291">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="46d75-292">`Update-Help` `Save-Help` (Windows PE) Windows 预安装环境上不支持和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="46d75-292">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="46d75-293">相关链接</span><span class="sxs-lookup"><span data-stu-id="46d75-293">RELATED LINKS</span></span>

[<span data-ttu-id="46d75-294">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="46d75-294">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="46d75-295">Get-Help</span><span class="sxs-lookup"><span data-stu-id="46d75-295">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="46d75-296">Get-Module</span><span class="sxs-lookup"><span data-stu-id="46d75-296">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="46d75-297">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="46d75-297">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="46d75-298">Start-Job</span><span class="sxs-lookup"><span data-stu-id="46d75-298">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="46d75-299">Save-Help</span><span class="sxs-lookup"><span data-stu-id="46d75-299">Save-Help</span></span>](Save-Help.md)
