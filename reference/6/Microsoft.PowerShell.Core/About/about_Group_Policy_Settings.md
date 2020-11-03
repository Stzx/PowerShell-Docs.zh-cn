---
description: 描述 PowerShell 的组策略设置
keywords: powershell,cmdlet
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: 1533908be91703efd8509653b30d30de6b7c4a84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199824"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="96074-104">关于组策略设置</span><span class="sxs-lookup"><span data-stu-id="96074-104">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="96074-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="96074-105">Short description</span></span>
<span data-ttu-id="96074-106">描述 PowerShell 的组策略设置</span><span class="sxs-lookup"><span data-stu-id="96074-106">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="96074-107">长说明</span><span class="sxs-lookup"><span data-stu-id="96074-107">Long description</span></span>

<span data-ttu-id="96074-108">PowerShell 包括组策略设置，可帮助你为企业环境中的 Windows 计算机定义一致的配置值。</span><span class="sxs-lookup"><span data-stu-id="96074-108">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="96074-109">PowerShell 组策略设置如下组策略路径：</span><span class="sxs-lookup"><span data-stu-id="96074-109">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

<span data-ttu-id="96074-110">用户配置路径中的组策略设置优先于计算机配置路径中组策略设置。</span><span class="sxs-lookup"><span data-stu-id="96074-110">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="96074-111">安装模板后，你可以在组策略编辑器 () 中编辑这些设置 `gpedit.msc` 。</span><span class="sxs-lookup"><span data-stu-id="96074-111">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="96074-112">策略如下：</span><span class="sxs-lookup"><span data-stu-id="96074-112">The policies are as follows:</span></span>

- <span data-ttu-id="96074-113">启用模块日志记录：设置模块的 **LogPipelineExecutionDetails** 属性。</span><span class="sxs-lookup"><span data-stu-id="96074-113">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="96074-114">启用 Power Shell 脚本块日志记录：启用所有 PowerShell 脚本的详细日志记录。</span><span class="sxs-lookup"><span data-stu-id="96074-114">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="96074-115">启用脚本执行：设置 PowerShell 执行策略。</span><span class="sxs-lookup"><span data-stu-id="96074-115">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="96074-116">启用 PowerShell 脚本：可便于将 PowerShell 命令输入和输出捕获到基于文本的脚本中。</span><span class="sxs-lookup"><span data-stu-id="96074-116">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="96074-117">设置的默认源路径 `Update-Help` ：将可更新帮助的源设置为目录，而不是 Internet。</span><span class="sxs-lookup"><span data-stu-id="96074-117">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="96074-118">有关获取其他模板和配置组策略的详细信息，请参阅 [如何在 Windows 中为组策略管理模板创建和管理中心存储][gpstore]。</span><span class="sxs-lookup"><span data-stu-id="96074-118">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="96074-119">启用模块日志记录</span><span class="sxs-lookup"><span data-stu-id="96074-119">Turn on module logging</span></span>

<span data-ttu-id="96074-120">" **打开模块日志记录** " 策略设置为所选 PowerShell 模块启用日志记录。</span><span class="sxs-lookup"><span data-stu-id="96074-120">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="96074-121">此设置在所有受影响的计算机上的所有会话中都有效。</span><span class="sxs-lookup"><span data-stu-id="96074-121">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="96074-122">如果启用此策略设置并指定一个或多个模块，则会在事件查看器的 Windows PowerShell 日志中记录指定模块的管道执行事件。</span><span class="sxs-lookup"><span data-stu-id="96074-122">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="96074-123">如果禁用此策略设置，则会为所有 PowerShell 模块禁用执行事件的日志记录。</span><span class="sxs-lookup"><span data-stu-id="96074-123">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="96074-124">如果未配置此策略设置，则每个模块的 **LogPipelineExecutionDetails** 属性将确定是否记录模块的执行事件。</span><span class="sxs-lookup"><span data-stu-id="96074-124">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="96074-125">默认情况下，所有模块的 **LogPipelineExecutionDetails** 属性都设置为 False。</span><span class="sxs-lookup"><span data-stu-id="96074-125">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="96074-126">若要为模块启用模块日志记录，请使用以下命令格式。</span><span class="sxs-lookup"><span data-stu-id="96074-126">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="96074-127">必须将模块导入到会话中，并且该设置仅在当前会话中有效。</span><span class="sxs-lookup"><span data-stu-id="96074-127">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="96074-128">若要为特定计算机上的所有会话启用模块日志记录，请将前面的命令添加到 "所有用户的 PowerShell 配置文件 (`$Profile.AllUsersAllHosts`) 。</span><span class="sxs-lookup"><span data-stu-id="96074-128">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="96074-129">有关模块日志记录的详细信息，请参阅 [about_Modules](about_Modules.md)。</span><span class="sxs-lookup"><span data-stu-id="96074-129">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="96074-130">启用 PowerShell 脚本块日志记录</span><span class="sxs-lookup"><span data-stu-id="96074-130">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="96074-131">" **打开 Powershell 脚本块日志记录** " 策略设置可将所有 PowerShell 脚本输入的日志记录到 Microsoft Windows PowerShell/操作事件日志中。</span><span class="sxs-lookup"><span data-stu-id="96074-131">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="96074-132">如果启用此策略设置，则 PowerShell Core 将记录命令、脚本块、函数和脚本的处理方式，无论是以交互方式调用还是通过自动化来处理。</span><span class="sxs-lookup"><span data-stu-id="96074-132">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="96074-133">如果禁用此策略设置，则将禁止记录 PowerShell 脚本输入。</span><span class="sxs-lookup"><span data-stu-id="96074-133">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="96074-134">如果启用脚本块调用日志记录，则 PowerShell 在调用命令、脚本块、函数或脚本启动或停止时还会记录事件。</span><span class="sxs-lookup"><span data-stu-id="96074-134">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="96074-135">启用调用日志记录时会生成大量事件日志。</span><span class="sxs-lookup"><span data-stu-id="96074-135">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="96074-136">启用脚本执行</span><span class="sxs-lookup"><span data-stu-id="96074-136">Turn on script execution</span></span>

<span data-ttu-id="96074-137">" **打开脚本执行** " 策略设置可为计算机和用户设置执行策略，这将确定允许运行哪些脚本。</span><span class="sxs-lookup"><span data-stu-id="96074-137">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="96074-138">如果启用策略设置，则可以从以下策略设置中进行选择。</span><span class="sxs-lookup"><span data-stu-id="96074-138">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="96074-139">仅 **允许已签名的脚本** 仅允许脚本通过受信任的发布者签名。</span><span class="sxs-lookup"><span data-stu-id="96074-139">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="96074-140">此策略设置等效于 AllSigned 执行策略。</span><span class="sxs-lookup"><span data-stu-id="96074-140">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="96074-141">**允许本地脚本和远程签名的脚本** 允许运行所有本地脚本。</span><span class="sxs-lookup"><span data-stu-id="96074-141">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="96074-142">来自 Internet 的脚本必须由受信任的发布者签名。</span><span class="sxs-lookup"><span data-stu-id="96074-142">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="96074-143">此策略设置等效于 RemoteSigned 执行策略。</span><span class="sxs-lookup"><span data-stu-id="96074-143">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="96074-144">**允许** 所有脚本都允许运行所有脚本。</span><span class="sxs-lookup"><span data-stu-id="96074-144">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="96074-145">此策略设置等效于不受限制的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96074-145">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="96074-146">如果禁用此策略设置，则不允许运行脚本。</span><span class="sxs-lookup"><span data-stu-id="96074-146">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="96074-147">此策略设置等效于受限制的执行策略。</span><span class="sxs-lookup"><span data-stu-id="96074-147">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="96074-148">如果禁用或未配置此策略设置，则由 cmdlet 为计算机或用户设置的执行策略将 `Set-ExecutionPolicy` 确定是否允许运行脚本。</span><span class="sxs-lookup"><span data-stu-id="96074-148">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="96074-149">默认值为 Restricted。</span><span class="sxs-lookup"><span data-stu-id="96074-149">The default value is Restricted.</span></span>

<span data-ttu-id="96074-150">有关详细信息，请参阅 [about_Execution_Policies](about_Execution_Policies.md)。</span><span class="sxs-lookup"><span data-stu-id="96074-150">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="96074-151">启用 powershell 脚本</span><span class="sxs-lookup"><span data-stu-id="96074-151">Turn on powershell transcription</span></span>

<span data-ttu-id="96074-152">" **打开 powershell** 脚本" 策略设置允许你将 PowerShell 核心命令的输入和输出捕获到基于文本的脚本中。</span><span class="sxs-lookup"><span data-stu-id="96074-152">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="96074-153">如果启用此策略设置，则 PowerShell Core 将为 PowerShell Core 和任何其他利用 PowerShell 核心引擎的应用程序启用脚本日志记录。</span><span class="sxs-lookup"><span data-stu-id="96074-153">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="96074-154">默认情况下，PowerShell Core 会将脚本输出记录到每个用户的 "我的文档" 目录中，文件名中包含 "PowerShell_transcript"，以及计算机名称和启动时间。</span><span class="sxs-lookup"><span data-stu-id="96074-154">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="96074-155">启用此策略等效于对每个 PowerShell 核心会话调用 Start-Transcript cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96074-155">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="96074-156">如果禁用此策略设置，则默认情况下将禁用基于 PowerShell 的应用程序的脚本日志记录，不过，脚本之外仍可通过 Start-Transcript cmdlet 启用。</span><span class="sxs-lookup"><span data-stu-id="96074-156">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="96074-157">如果使用 OutputDirectory 设置启用到共享位置的脚本日志记录，请确保限制对该目录的访问，以防止用户查看其他用户或计算机的脚本。</span><span class="sxs-lookup"><span data-stu-id="96074-157">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="96074-158">为 Update-Help 设置默认源路径</span><span class="sxs-lookup"><span data-stu-id="96074-158">Set the default source path for Update-Help</span></span>

<span data-ttu-id="96074-159">" **设置 update-help 的默认源路径** " 策略设置为 Cmdlet 的 **SourcePath** 参数设置默认值 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="96074-159">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="96074-160">此设置可防止用户使用 `Update-Help` cmdlet 从 Internet 下载帮助文件。</span><span class="sxs-lookup"><span data-stu-id="96074-160">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="96074-161">此组策略设置将出现在 " **计算机配置** " 和 " **用户配置** " 下。</span><span class="sxs-lookup"><span data-stu-id="96074-161">This Group Policy setting appears under **Computer Configuration** and **User Configuration** .</span></span> <span data-ttu-id="96074-162">但是，只有 " **计算机配置** " 下的组策略设置才有效。</span><span class="sxs-lookup"><span data-stu-id="96074-162">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="96074-163">" **用户配置** " 下的组策略设置将被忽略。</span><span class="sxs-lookup"><span data-stu-id="96074-163">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="96074-164">`Update-Help`Cmdlet 将下载并安装最新的 PowerShell 模块帮助文件，并将它们安装在计算机上。</span><span class="sxs-lookup"><span data-stu-id="96074-164">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="96074-165">默认情况下， `Update-Help` 从模块指定的 Internet 位置下载新帮助文件。</span><span class="sxs-lookup"><span data-stu-id="96074-165">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="96074-166">但是，可以使用 cmdlet 将 `Save-Help` 最新的帮助文件下载到文件系统位置（如网络共享），然后使用 `Update-Help` cmdlet 从文件系统位置获取帮助文件，并将它们安装在计算机上。</span><span class="sxs-lookup"><span data-stu-id="96074-166">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="96074-167">此 cmdlet 的 **SourcePath** 参数 `Update-Help` 指定文件系统位置。</span><span class="sxs-lookup"><span data-stu-id="96074-167">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="96074-168">通过为 **SourcePath** 参数提供默认值，此组策略设置会将 **sourcepath** 参数隐式添加到所有 `Update-Help` 命令。</span><span class="sxs-lookup"><span data-stu-id="96074-168">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="96074-169">用户可以通过输入其他文件系统位置，替代指定为默认值的特定文件系统位置。</span><span class="sxs-lookup"><span data-stu-id="96074-169">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="96074-170">但不能从命令中删除 **SourcePath** 参数 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="96074-170">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="96074-171">如果启用此策略设置，则可以为 **SourcePath** 参数指定默认值。</span><span class="sxs-lookup"><span data-stu-id="96074-171">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="96074-172">输入文件系统位置。</span><span class="sxs-lookup"><span data-stu-id="96074-172">Enter a file system location.</span></span>

<span data-ttu-id="96074-173">如果禁用或未配置此策略设置，则不会对此 cmdlet 的 **SourcePath** 参数提供默认值 `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="96074-173">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="96074-174">用户可以从 Internet 或任何文件系统位置下载帮助。</span><span class="sxs-lookup"><span data-stu-id="96074-174">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="96074-175">有关详细信息，请参阅 [about_Updatable_Help](about_Updatable_Help.md)。</span><span class="sxs-lookup"><span data-stu-id="96074-175">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="96074-176">Keywords</span><span class="sxs-lookup"><span data-stu-id="96074-176">Keywords</span></span>

<span data-ttu-id="96074-177">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="96074-177">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="96074-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96074-178">See also</span></span>

[<span data-ttu-id="96074-179">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="96074-179">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="96074-180">about_Modules</span><span class="sxs-lookup"><span data-stu-id="96074-180">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="96074-181">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="96074-181">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="96074-182">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="96074-182">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="96074-183">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="96074-183">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="96074-184">Get-Module</span><span class="sxs-lookup"><span data-stu-id="96074-184">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="96074-185">Update-Help</span><span class="sxs-lookup"><span data-stu-id="96074-185">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="96074-186">Save-Help</span><span class="sxs-lookup"><span data-stu-id="96074-186">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759
