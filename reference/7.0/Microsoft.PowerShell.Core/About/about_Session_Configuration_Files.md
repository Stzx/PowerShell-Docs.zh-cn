---
description: 介绍会话配置文件，这些文件在会话配置中使用 (也称为 "终结点" ) ，用于定义使用会话配置的会话的环境。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 113c068022f37b22cbcc5dae61a6a5edf26187d8
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93199578"
---
# <a name="about-session-configuration-files"></a><span data-ttu-id="8f62e-104">关于会话配置文件</span><span class="sxs-lookup"><span data-stu-id="8f62e-104">About Session Configuration Files</span></span>

## <a name="short-description"></a><span data-ttu-id="8f62e-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="8f62e-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8f62e-106">介绍会话配置文件，这些文件在会话配置中使用 (也称为 "终结点" ) ，用于定义使用会话配置的会话的环境。</span><span class="sxs-lookup"><span data-stu-id="8f62e-106">Describes session configuration files, which are used in a session configuration (also known as an "endpoint") to define the environment of sessions that use the session configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="8f62e-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="8f62e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8f62e-108">"会话配置文件" 是文件扩展名为 .pssc 的文本文件，其中包含会话配置属性和值的哈希表。</span><span class="sxs-lookup"><span data-stu-id="8f62e-108">A "session configuration file" is a text file with a .pssc file name extension that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="8f62e-109">您可以使用会话配置文件来设置会话配置的属性。</span><span class="sxs-lookup"><span data-stu-id="8f62e-109">You can use a session configuration file to set the properties of a session configuration.</span></span> <span data-ttu-id="8f62e-110">这样做将定义使用该会话配置的任何 PowerShell 会话的环境。</span><span class="sxs-lookup"><span data-stu-id="8f62e-110">Doing so defines the environment of any PowerShell sessions that use that session configuration.</span></span>

<span data-ttu-id="8f62e-111">会话配置文件可以轻松地创建自定义会话配置，而无需使用复杂的 c # 程序集或脚本。</span><span class="sxs-lookup"><span data-stu-id="8f62e-111">Session configuration files make it easy to create custom session configurations without using complex C# assemblies or scripts.</span></span>

<span data-ttu-id="8f62e-112">"会话配置" 或 "终结点" 是本地计算机设置的集合，用于确定用户可以在计算机上创建会话的情况。用户可以在这些会话中运行的命令;会话是否应作为特权虚拟帐户运行。</span><span class="sxs-lookup"><span data-stu-id="8f62e-112">A "session configuration" or "endpoint" is a collection of local computer settings that determine such things as which users can create sessions on the computer; which commands users can run in those sessions; and whether the session should run as a privileged virtual account.</span></span> <span data-ttu-id="8f62e-113">有关会话配置的详细信息，请参阅 [about_Session_Configurations](about_Session_Configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="8f62e-113">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

<span data-ttu-id="8f62e-114">Windows PowerShell 2.0 中引入了会话配置，并且会话配置文件是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8f62e-114">Session configurations were introduced in Windows PowerShell 2.0, and session configuration files were introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="8f62e-115">必须使用 Windows PowerShell 3.0 将会话配置文件包含在会话配置中。</span><span class="sxs-lookup"><span data-stu-id="8f62e-115">You must use Windows PowerShell 3.0 to include a session configuration file in a session configuration.</span></span> <span data-ttu-id="8f62e-116">但是，Windows PowerShell 2.0 (和更高版本的用户) 受会话配置中的设置影响。</span><span class="sxs-lookup"><span data-stu-id="8f62e-116">However, users of Windows PowerShell 2.0 (and later) are affected by the settings in the session configuration.</span></span>

## <a name="creating-custom-sessions"></a><span data-ttu-id="8f62e-117">创建自定义会话</span><span class="sxs-lookup"><span data-stu-id="8f62e-117">Creating Custom Sessions</span></span>

<span data-ttu-id="8f62e-118">通过在会话配置中指定会话属性，可以自定义 PowerShell 会话的许多功能。</span><span class="sxs-lookup"><span data-stu-id="8f62e-118">You can customize many features of a PowerShell session by specifying session properties in a session configuration.</span></span> <span data-ttu-id="8f62e-119">您可以通过编写定义自定义运行空间的 c # 程序自定义会话，也可以使用会话配置文件来定义使用会话配置创建的会话的属性。</span><span class="sxs-lookup"><span data-stu-id="8f62e-119">You can customize a session by writing a C# program that defines a custom runspace, or you can use a session configuration file to define the properties of sessions created by using the session configuration.</span></span> <span data-ttu-id="8f62e-120">通常，使用会话配置文件比编写 c # 程序更容易。</span><span class="sxs-lookup"><span data-stu-id="8f62e-120">As a general rule, it is easier to use the session configuration file than to write a C# program.</span></span>

<span data-ttu-id="8f62e-121">你可以使用会话配置文件为高度可信的用户创建诸如功能齐全的会话等项目;锁定的会话，允许访问最少;为特定而设计的会话，仅包含这些任务所需的模块;和会话，无特权用户只能以特权帐户的身份运行特定命令。</span><span class="sxs-lookup"><span data-stu-id="8f62e-121">You can use a session configuration file to create items such as fully-functioning sessions for highly trusted users; locked-down sessions that allow minimal access; sessions designed for particular and that contain only the modules required for those tasks; and sessions where unprivileged users can only run specific commands as a privileged account.</span></span>

<span data-ttu-id="8f62e-122">除此之外，你还可以管理会话的用户是否可以使用 PowerShell 语言元素（如脚本块）或是否只能运行命令。</span><span class="sxs-lookup"><span data-stu-id="8f62e-122">In addition to that, you can manage whether users of the session can use PowerShell language elements such as script blocks, or whether they can only run commands.</span></span> <span data-ttu-id="8f62e-123">你可以管理可在会话中运行的 PowerShell 用户的版本;管理导入到会话中的模块。并管理用户可运行的 cmdlet、函数和别名。</span><span class="sxs-lookup"><span data-stu-id="8f62e-123">You can manage the version of PowerShell users can run in the session; manage which modules are imported into the session; and manage which cmdlets, functions, and aliases session users can run.</span></span> <span data-ttu-id="8f62e-124">使用 RoleDefinitions 字段时，可以基于组成员身份向用户授予会话中的不同功能。</span><span class="sxs-lookup"><span data-stu-id="8f62e-124">When using the RoleDefinitions field, you can give users different capabilities in the session based on group membership.</span></span>

<span data-ttu-id="8f62e-125">有关 RoleDefinitions 以及如何定义此值的详细信息，请参阅 New-PSRoleCapabilityFile Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="8f62e-125">For more information about RoleDefinitions and how to define this Value, see the help topic for the New-PSRoleCapabilityFile Cmdlet.</span></span>

## <a name="creating-a-session-configuration-file"></a><span data-ttu-id="8f62e-126">创建会话配置文件</span><span class="sxs-lookup"><span data-stu-id="8f62e-126">Creating a Session Configuration File</span></span>

<span data-ttu-id="8f62e-127">创建会话配置文件的最简单方法是使用 New-PSSessionConfigurationFile cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f62e-127">The easiest way to create a session configuration file is by using the New-PSSessionConfigurationFile cmdlet.</span></span> <span data-ttu-id="8f62e-128">此 cmdlet 将生成一个使用正确语法和格式的文件，并自动验证许多配置文件属性值。</span><span class="sxs-lookup"><span data-stu-id="8f62e-128">This cmdlet generates a file that uses the correct syntax and format, and that automatically verifies many of the configuration file property values.</span></span>

<span data-ttu-id="8f62e-129">有关可以在会话配置文件中设置的属性的详细说明，请参阅 New-PSSessionConfigurationFile cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="8f62e-129">For detailed descriptions of the properties that you can set in a session configuration file, see the help topic for the New-PSSessionConfigurationFile cmdlet.</span></span>

<span data-ttu-id="8f62e-130">以下命令将创建一个使用默认值的会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-130">The following command creates a session configuration file that uses the default values.</span></span> <span data-ttu-id="8f62e-131">生成的配置文件仅使用默认值，因为没有路径参数 (指定包含) 文件路径的其他参数：</span><span class="sxs-lookup"><span data-stu-id="8f62e-131">The resulting configuration file uses only the default values because no parameters other than the Path parameter (which specifies the file path) are included:</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

<span data-ttu-id="8f62e-132">若要在默认文本编辑器中查看新的配置文件，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="8f62e-132">To view the new configuration file in your default text editor, use the following command:</span></span>

```powershell
Invoke-Item -Path .\Defaults.pssc
```

<span data-ttu-id="8f62e-133">若要为用户可运行命令的会话创建会话配置，而不是使用 PowerShell 语言的其他元素，请键入：</span><span class="sxs-lookup"><span data-stu-id="8f62e-133">To create a session configuration for sessions in which user can run commands, but not use other elements of the PowerShell language, type:</span></span>

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="8f62e-134">在上述命令中，将 LanguageMode 参数设置为 NoLanguage 可防止用户执行编写或运行脚本或使用变量等操作。</span><span class="sxs-lookup"><span data-stu-id="8f62e-134">In the preceding command, setting the LanguageMode parameter to NoLanguage prevents users from doing such things as writing or running scripts, or using variables.</span></span>

<span data-ttu-id="8f62e-135">若要为用户仅能使用 Get cmdlet 的会话创建会话配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="8f62e-135">To create a session configuration for sessions in which users can use only Get cmdlets, type:</span></span>

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

<span data-ttu-id="8f62e-136">在前面的示例中，将 VisibleCmdlets 参数设置为-\* 可将用户限制为名称以字符串值 "Get-" 开头的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f62e-136">In the preceding example, setting the VisibleCmdlets parameter to Get-\* limits users to cmdlets that have names that start with the string value "Get-".</span></span>

<span data-ttu-id="8f62e-137">若要为使用特权虚拟帐户（而不是用户凭据）运行的会话创建会话配置，请键入：</span><span class="sxs-lookup"><span data-stu-id="8f62e-137">To create a session configuration for sessions that run under a privileged virtual account instead of the user's credentials, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

<span data-ttu-id="8f62e-138">若要为会话创建会话配置，其中在角色功能文件中指定了向用户显示的命令，请键入：</span><span class="sxs-lookup"><span data-stu-id="8f62e-138">To create a session configuration for sessions in which the commands visible to the user are specified in a role capabilities file, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a><span data-ttu-id="8f62e-139">使用会话配置文件</span><span class="sxs-lookup"><span data-stu-id="8f62e-139">Using a Session Configuration File</span></span>

<span data-ttu-id="8f62e-140">你可以在创建会话配置时包括会话配置文件，也可以在添加时将文件添加到会话配置中。</span><span class="sxs-lookup"><span data-stu-id="8f62e-140">You can include a session configuration file when you create a session configuration or add you can add a file to the session configuration at a later time.</span></span>

<span data-ttu-id="8f62e-141">若要在创建会话配置时包括会话配置文件，请使用 Register-PSSessionConfiguration cmdlet 的 Path 参数。</span><span class="sxs-lookup"><span data-stu-id="8f62e-141">To include a session configuration file when creating a session configuration, use the Path parameter of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="8f62e-142">例如，以下命令在创建 NoLanguage 会话配置时使用 .pssc 文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-142">For example, the following command uses the NoLanguage.pssc file when it creates a NoLanguage session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="8f62e-143">启动新的 NoLanguage 会话时，用户将只能访问 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="8f62e-143">When a new NoLanguage session starts, users will only have access to PowerShell commands.</span></span>

<span data-ttu-id="8f62e-144">若要将会话配置文件添加到现有会话配置，请使用 Set-PSSessionConfiguration cmdlet 和 Path 参数。</span><span class="sxs-lookup"><span data-stu-id="8f62e-144">To add a session configuration file to an existing session configuration, use the Set-PSSessionConfiguration cmdlet and the Path parameter.</span></span> <span data-ttu-id="8f62e-145">这会影响通过指定的会话配置创建的任何新会话。</span><span class="sxs-lookup"><span data-stu-id="8f62e-145">This affects any new sessions created with the specified session configuration.</span></span> <span data-ttu-id="8f62e-146">请注意，Set-PSSessionConfiguration cmdlet 将更改会话本身，而不会修改会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-146">Note that the Set-PSSessionConfiguration cmdlet changes the session itself and does not modify the session configuration file.</span></span>

<span data-ttu-id="8f62e-147">例如，以下命令将 NoLanguage 文件添加到 LockedDown 会话配置中。</span><span class="sxs-lookup"><span data-stu-id="8f62e-147">For example, the following command adds the NoLanguage.pssc file to the LockedDown session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

<span data-ttu-id="8f62e-148">当用户使用 LockedDown 会话配置创建会话时，他们将能够运行 cmdlet，但不能创建或使用变量、分配值或使用其他 PowerShell 语言元素。</span><span class="sxs-lookup"><span data-stu-id="8f62e-148">When users use the LockedDown session configuration to create a session, they will be able to run cmdlets but they will not be able to create or use variables, assign values, or use other PowerShell language elements.</span></span>

<span data-ttu-id="8f62e-149">以下命令使用 New-PSSession cmdlet 在计算机 Srv01 上创建一个会话，该会话使用 LockedDown 会话配置，并将对象引用保存到 $s 变量中的会话。</span><span class="sxs-lookup"><span data-stu-id="8f62e-149">The following command uses the New-PSSession cmdlet to create a session on the computer Srv01 that uses the LockedDown session configuration, saving an object reference to the session in the $s variable.</span></span> <span data-ttu-id="8f62e-150">会话配置的 ACL (访问控制列表) 确定哪些用户可以使用它来创建会话。</span><span class="sxs-lookup"><span data-stu-id="8f62e-150">The ACL (access control list) of the session configuration determines who can use it to create a session.</span></span>

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

<span data-ttu-id="8f62e-151">由于已将 NoLanguage 约束添加到 LockedDown 会话配置，因此 LockedDown 会话中的用户将只能运行 PowerShell 命令和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f62e-151">Because the NoLanguage constraints were added to the LockedDown session configuration, users in LockedDown sessions will only be able to run PowerShell commands and cmdlets.</span></span> <span data-ttu-id="8f62e-152">例如，以下两个命令使用 Invoke-Command cmdlet 在 $s 变量中引用的会话中运行命令。</span><span class="sxs-lookup"><span data-stu-id="8f62e-152">For example, the following two commands use the Invoke-Command cmdlet to run commands in the session referenced in the $s variable.</span></span> <span data-ttu-id="8f62e-153">第一个命令将运行 Get-UICulture cmdlet，并且不使用任何变量，因此将成功。</span><span class="sxs-lookup"><span data-stu-id="8f62e-153">The first command, which runs the Get-UICulture cmdlet and does not use any variables, succeeds.</span></span> <span data-ttu-id="8f62e-154">第二个命令获取 $PSUICulture 变量的值失败。</span><span class="sxs-lookup"><span data-stu-id="8f62e-154">The second command, which gets the value of the $PSUICulture variable, fails.</span></span>

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a><span data-ttu-id="8f62e-155">编辑会话配置文件</span><span class="sxs-lookup"><span data-stu-id="8f62e-155">Editing a Session Configuration File</span></span>

<span data-ttu-id="8f62e-156">除了将 runasvirtualaccount 设置和 RunAsVirtualAccountGroups 之外的会话配置中的所有设置都可以通过编辑会话配置使用的会话配置文件进行修改。</span><span class="sxs-lookup"><span data-stu-id="8f62e-156">All settings in a session configuration except for RunAsVirtualAccount and RunAsVirtualAccountGroups can be modified by editing the session configuration file used by the session configuration.</span></span> <span data-ttu-id="8f62e-157">为此，请首先查找会话配置文件的活动副本。</span><span class="sxs-lookup"><span data-stu-id="8f62e-157">To do this, begin by locating the active copy of the session configuration file.</span></span>

<span data-ttu-id="8f62e-158">使用会话配置中的会话配置文件时，PowerShell 会创建会话配置文件的活动副本，并将其存储在 \$ \\ 本地计算机上的 pshome SessionConfig 目录中。</span><span class="sxs-lookup"><span data-stu-id="8f62e-158">When you use a session configuration file in a session configuration, PowerShell creates an active copy of the session configuration file and stores it in the \$pshome\\SessionConfig directory on the local computer.</span></span>

<span data-ttu-id="8f62e-159">会话配置文件的活动副本的位置存储在会话配置对象的 ConfigFilePath 属性中。</span><span class="sxs-lookup"><span data-stu-id="8f62e-159">The location of the active copy of a session configuration file is stored in the ConfigFilePath property of the session configuration object.</span></span>

<span data-ttu-id="8f62e-160">以下命令将获取 NoLanguage 会话配置的会话配置文件的位置。</span><span class="sxs-lookup"><span data-stu-id="8f62e-160">The following command gets the location of the session configuration file for the NoLanguage session configuration.</span></span>

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

<span data-ttu-id="8f62e-161">该命令返回类似于以下内容的文件路径：</span><span class="sxs-lookup"><span data-stu-id="8f62e-161">That command returns a file path similar to the following:</span></span>

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="8f62e-162">可以在任何文本编辑器中编辑 .pssc 文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-162">You can edit the .pssc file in any text editor.</span></span> <span data-ttu-id="8f62e-163">文件保存后，任何使用会话配置的新会话都将使用该文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-163">After the file is saved it will be employed by any new sessions that use the session configuration.</span></span>

<span data-ttu-id="8f62e-164">如果需要修改将 runasvirtualaccount 设置或 RunAsVirtualAccountGroups 设置，则必须取消注册会话配置，并重新注册包含已编辑值的会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-164">If you need to modify the RunAsVirtualAccount or the RunAsVirtualAccountGroups settings, you must un-register the session configuration and re-register a session configuration file that includes the edited values.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="8f62e-165">测试会话配置文件</span><span class="sxs-lookup"><span data-stu-id="8f62e-165">Testing a Session Configuration File</span></span>

<span data-ttu-id="8f62e-166">使用 Test-PSSessionConfigurationFile cmdlet 测试手动编辑的会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-166">Use the Test-PSSessionConfigurationFile cmdlet to test manually edited session configuration files.</span></span> <span data-ttu-id="8f62e-167">这一点很重要：如果文件语法和值无效，用户将无法使用会话配置来创建会话。</span><span class="sxs-lookup"><span data-stu-id="8f62e-167">That's important: if the file syntax and values are not valid users will not be able to use the session configuration to create a session.</span></span>

<span data-ttu-id="8f62e-168">例如，以下命令测试 NoLanguage 会话配置的活动会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-168">For example, the following command tests the active session configuration file of the NoLanguage session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="8f62e-169">如果配置文件中的语法和值有效 Test-PSSessionConfigurationFile 返回 True。</span><span class="sxs-lookup"><span data-stu-id="8f62e-169">If the syntax and values in the configuration file are valid Test-PSSessionConfigurationFile returns True.</span></span> <span data-ttu-id="8f62e-170">如果语法和值无效，则该 cmdlet 将返回 False。</span><span class="sxs-lookup"><span data-stu-id="8f62e-170">If the syntax and values are not valid then the cmdlet returns False.</span></span>

<span data-ttu-id="8f62e-171">你可以使用 Test-PSSessionConfigurationFile 来测试任何会话配置文件，包括 New-PSSessionConfiguration cmdlet 创建的文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-171">You can use Test-PSSessionConfigurationFile to test any session configuration file, including files that the New-PSSessionConfiguration cmdlet creates.</span></span> <span data-ttu-id="8f62e-172">有关详细信息，请参阅 Test-PSSessionConfigurationFile cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="8f62e-172">For more information, see the help topic for the Test-PSSessionConfigurationFile cmdlet.</span></span>

## <a name="removing-a-session-configuration-file"></a><span data-ttu-id="8f62e-173">删除会话配置文件</span><span class="sxs-lookup"><span data-stu-id="8f62e-173">Removing a Session Configuration File</span></span>

<span data-ttu-id="8f62e-174">不能从会话配置中删除会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-174">You cannot remove a session configuration file from a session configuration.</span></span>
<span data-ttu-id="8f62e-175">不过，您可以将该文件替换为使用默认设置的新文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-175">However, you can replace the file with a new file that uses the default settings.</span></span> <span data-ttu-id="8f62e-176">这会有效地取消原始配置文件使用的设置。</span><span class="sxs-lookup"><span data-stu-id="8f62e-176">This effectively cancels the settings used by the original configuration file.</span></span>

<span data-ttu-id="8f62e-177">若要替换会话配置文件，请创建新的会话配置文件，该文件使用默认设置，然后使用 Set-PSSessionConfiguration cmdlet 将自定义会话配置文件替换为新文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-177">To replace a session configuration file, create a new session configuration file that uses the default settings, then use the Set-PSSessionConfiguration cmdlet to replace the custom session configuration file with the new file.</span></span>

<span data-ttu-id="8f62e-178">例如，以下命令将创建一个默认会话配置文件，然后在 NoLanguage 会话配置中替换活动会话配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f62e-178">For example, the following commands create a Default session configuration file and then replace the active session configuration file in the NoLanguage session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

<span data-ttu-id="8f62e-179">完成这些命令后，NoLanguage 会话配置将 (为所有通过该会话配置创建的会话) 默认设置提供完全语言支持。</span><span class="sxs-lookup"><span data-stu-id="8f62e-179">When these commands finish, the NoLanguage session configuration will actually provide full language support (the default setting) for all sessions created with that session configuration.</span></span>

<span data-ttu-id="8f62e-180">查看会话配置的属性使用会话配置文件表示会话配置的会话配置对象具有其他属性，使发现和分析会话配置变得更加容易。</span><span class="sxs-lookup"><span data-stu-id="8f62e-180">Viewing the Properties of a Session Configuration The session configuration objects that represent session configurations using session configuration files have additional properties that make it easy to discover and analyze the session configuration.</span></span> <span data-ttu-id="8f62e-181"> (请注意，下面所示的类型名称包含格式化的视图定义。 ) 可以通过运行 Get-PSSessionConfiguration cmdlet 并将返回的数据通过管道传递给 Get-Member cmdlet 来查看属性：</span><span class="sxs-lookup"><span data-stu-id="8f62e-181">(Note that the type name shown below includes a formatted view definition.) You can view the properties by running the Get-PSSessionConfiguration cmdlet and piping the returned data to the Get-Member cmdlet:</span></span>

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

<span data-ttu-id="8f62e-182">通过这些属性可以轻松地搜索特定的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8f62e-182">These properties make it easy to search for specific session configurations.</span></span>
<span data-ttu-id="8f62e-183">例如，你可以使用 Set-executionpolicy 属性来查找使用 RemoteSigned 执行策略支持会话的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8f62e-183">For example, you can use the ExecutionPolicy property to find a session configuration that supports sessions with the RemoteSigned execution policy.</span></span>
<span data-ttu-id="8f62e-184">请注意，由于 Set-executionpolicy 属性仅存在于使用会话配置文件的会话上，因此该命令可能不会返回所有合格的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8f62e-184">Note that, because the ExecutionPolicy property exists only on sessions that use session configuration files, the command might not return all qualifying session configurations.</span></span>

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

<span data-ttu-id="8f62e-185">以下命令获取 RunAsUser 为 Exchange 管理员的会话配置。</span><span class="sxs-lookup"><span data-stu-id="8f62e-185">The following command gets session configurations in which the RunAsUser is the Exchange administrator.</span></span>

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

<span data-ttu-id="8f62e-186">若要查看与配置关联的角色定义的相关信息，请使用 Get-PSSessionCapability cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f62e-186">To view information about the role definitions associated with a configuration use the Get-PSSessionCapability cmdlet.</span></span> <span data-ttu-id="8f62e-187">此 cmdlet 可用于确定特定用户在特定终结点中可用的命令和环境。</span><span class="sxs-lookup"><span data-stu-id="8f62e-187">This cmdlet enables you to determine the commands and environment available to specific users in specific endpoints.</span></span>

## <a name="notes"></a><span data-ttu-id="8f62e-188">注释</span><span class="sxs-lookup"><span data-stu-id="8f62e-188">NOTES</span></span>

<span data-ttu-id="8f62e-189">会话配置还支持称为 "空" 会话的会话类型。</span><span class="sxs-lookup"><span data-stu-id="8f62e-189">Session configurations also support a type of session known as an "empty" session.</span></span> <span data-ttu-id="8f62e-190">空会话类型使你能够使用选定的命令创建自定义会话。</span><span class="sxs-lookup"><span data-stu-id="8f62e-190">An Empty session type enables you to create custom sessions with selected commands.</span></span> <span data-ttu-id="8f62e-191">如果不将模块、函数或脚本添加到空会话中，则该会话将限于表达式，并且可能不是任何实际使用。</span><span class="sxs-lookup"><span data-stu-id="8f62e-191">If you do not add modules, functions, or scripts to an empty session, the session is limited to expressions and might not be of any practical use.</span></span> <span data-ttu-id="8f62e-192">SessionType 属性告诉你是否正在使用空会话。</span><span class="sxs-lookup"><span data-stu-id="8f62e-192">The SessionType property tells you whether or not you are working with an empty session.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f62e-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f62e-193">SEE ALSO</span></span>

[<span data-ttu-id="8f62e-194">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="8f62e-194">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="8f62e-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="8f62e-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="8f62e-196">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f62e-196">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="8f62e-197">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f62e-197">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="8f62e-198">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f62e-198">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="8f62e-199">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8f62e-199">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="8f62e-200">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f62e-200">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="8f62e-201">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f62e-201">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="8f62e-202">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="8f62e-202">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="8f62e-203">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="8f62e-203">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[<span data-ttu-id="8f62e-204">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="8f62e-204">Get-PSSessionCapability</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[<span data-ttu-id="8f62e-205">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="8f62e-205">New-PSRoleCapabilityFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)
