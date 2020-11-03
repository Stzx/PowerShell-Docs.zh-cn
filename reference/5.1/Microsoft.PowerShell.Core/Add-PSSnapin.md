---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: 5adba912d91369250ee9891ee2bb2ca0f8cba796
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197461"
---
# <span data-ttu-id="b4251-103">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b4251-103">Add-PSSnapin</span></span>

## <span data-ttu-id="b4251-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b4251-104">SYNOPSIS</span></span>
<span data-ttu-id="b4251-105">将一个或多个 Windows PowerShell 管理单元添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-105">Adds one or more Windows PowerShell snap-ins to the current session.</span></span>

## <span data-ttu-id="b4251-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4251-106">SYNTAX</span></span>

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="b4251-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b4251-107">DESCRIPTION</span></span>

<span data-ttu-id="b4251-108">`Add-PSSnapin`Cmdlet 可将已注册的 Windows PowerShell 管理单元添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-108">The `Add-PSSnapin` cmdlet adds registered Windows PowerShell snap-ins to the current session.</span></span> <span data-ttu-id="b4251-109">添加了管理单元之后，就可以使用当前会话中的管理单元支持的 cmdlet 和提供程序。</span><span class="sxs-lookup"><span data-stu-id="b4251-109">After the snap-ins are added, you can use the cmdlets and providers that the snap-ins support in the current session.</span></span>

<span data-ttu-id="b4251-110">若要将管理单元添加到所有未来的 Windows PowerShell 会话中，请将 `Add-PSSnapin` 命令添加到 Windows powershell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="b4251-110">To add the snap-in to all future Windows PowerShell sessions, add an `Add-PSSnapin` command to your Windows PowerShell profile.</span></span> <span data-ttu-id="b4251-111">有关详细信息，请参阅 [about_Profiles](about/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b4251-111">For more information, see [about_Profiles](about/about_Profiles.md).</span></span>

<span data-ttu-id="b4251-112">从 Windows PowerShell 3.0 开始，将 Windows PowerShell 中包含的核心命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="b4251-112">Beginning in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="b4251-113">例外情况是 **Microsoft.PowerShell.Core** ，它是一个管理单元 (PSSnapin)。</span><span class="sxs-lookup"><span data-stu-id="b4251-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="b4251-114">默认情况下，仅将 **Microsoft.PowerShell.Core** 管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="b4251-115">首次使用时自动导入模块，而且可以使用 Import-Module cmdlet 导入它们。</span><span class="sxs-lookup"><span data-stu-id="b4251-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="b4251-116">示例</span><span class="sxs-lookup"><span data-stu-id="b4251-116">EXAMPLES</span></span>

### <span data-ttu-id="b4251-117">示例1：添加管理单元</span><span class="sxs-lookup"><span data-stu-id="b4251-117">Example 1: Add snap-ins</span></span>

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

<span data-ttu-id="b4251-118">此命令会将 Microsoft Exchange 和 Active Directory 管理单元添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-118">This command adds the Microsoft Exchange and Active Directory snap-ins to the current session.</span></span>

### <span data-ttu-id="b4251-119">示例2：添加所有已注册的管理单元</span><span class="sxs-lookup"><span data-stu-id="b4251-119">Example 2: Add all the registered snap-ins</span></span>

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

<span data-ttu-id="b4251-120">此命令会将所有已注册 Windows PowerShell 管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-120">This command adds all of the registered Windows PowerShell snap-ins to the session.</span></span> <span data-ttu-id="b4251-121">它使用带有 **已注册** 参数的 Get-PSSnapin cmdlet 来获取表示每个已注册管理单元的对象。管道运算符 (|) 将结果传递给 `Add-PSSnapin` ，这会将其添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-121">It uses the Get-PSSnapin cmdlet with the **Registered** parameter to get objects representing each of the registered snap-ins. The pipeline operator (|) passes the result to `Add-PSSnapin`, which adds them to the session.</span></span> <span data-ttu-id="b4251-122">**PassThru** 参数将返回表示每个已添加管理单元的对象。</span><span class="sxs-lookup"><span data-stu-id="b4251-122">The **PassThru** parameter returns objects that represent each of the added snap-ins.</span></span>

### <span data-ttu-id="b4251-123">示例3：注册管理单元并添加它</span><span class="sxs-lookup"><span data-stu-id="b4251-123">Example 3: Register a snap-in and add it</span></span>

<span data-ttu-id="b4251-124">第一个命令将获取已添加到当前会话中的管理单元，其中包括随 Windows PowerShell 一起安装的管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-124">The first command gets snap-ins that have been added to the current session that include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="b4251-125">此示例中，不返回 ManagementFeatures。</span><span class="sxs-lookup"><span data-stu-id="b4251-125">In this example, ManagementFeatures is not returned.</span></span> <span data-ttu-id="b4251-126">这指示尚未将其添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-126">This indicates that it has not been added to the session.</span></span>

<span data-ttu-id="b4251-127">第二个命令获取已在系统上注册的管理单元，包括那些已添加到会话的管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-127">The second command gets snap-ins that have been registered on your system, which includes those that have already been added to the session.</span></span> <span data-ttu-id="b4251-128">它不包括随 Windows PowerShell 一起安装的管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-128">It does not include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="b4251-129">在这种情况下，该命令不返回任何管理单元。这表示未在系统上注册 ManagementFeatures 管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-129">In this case, the command does not return any snap-ins. This indicates that the ManagementFeatures snapin has not been registered on the system.</span></span>

<span data-ttu-id="b4251-130">第三个命令为 .NET Framework 中的 Installutil.exe 工具的路径创建一个别名 installutil.exe。</span><span class="sxs-lookup"><span data-stu-id="b4251-130">The third command creates an alias, installutil, for the path of the InstallUtil tool in .NET Framework.</span></span>

<span data-ttu-id="b4251-131">第四个命令使用 Installutil.exe 工具注册管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-131">The fourth command uses the InstallUtil tool to register the snap-in.</span></span> <span data-ttu-id="b4251-132">命令指定管理单元的 ManagementCmdlets.dll 路径、文件名或模块名称。</span><span class="sxs-lookup"><span data-stu-id="b4251-132">The command specifies the path of ManagementCmdlets.dll, the filename or module name of the snap-in.</span></span>

<span data-ttu-id="b4251-133">第五个命令与第二个命令相同。</span><span class="sxs-lookup"><span data-stu-id="b4251-133">The fifth command is the same as the second command.</span></span> <span data-ttu-id="b4251-134">这一次，你可以使用它来验证 ManagementCmdlets 管理单元是否已注册。</span><span class="sxs-lookup"><span data-stu-id="b4251-134">This time, you use it to verify that the ManagementCmdlets snap-in is registered.</span></span>

<span data-ttu-id="b4251-135">第六个命令使用 `Add-PSSnapin` cmdlet 将 ManagementFeatures 管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="b4251-135">The sixth command uses the `Add-PSSnapin` cmdlet to add the ManagementFeatures snap-in to the session.</span></span> <span data-ttu-id="b4251-136">该命令指定了管理单元的名称 ManagementFeatures，而不是文件名。</span><span class="sxs-lookup"><span data-stu-id="b4251-136">It specifies the name of the snap-in, ManagementFeatures, not the file name.</span></span>

<span data-ttu-id="b4251-137">若要验证管理单元是否已添加到会话中，第七个命令使用 Get-Command cmdlet 的 **Module** 参数。</span><span class="sxs-lookup"><span data-stu-id="b4251-137">To verify that the snap-in is added to the session, the seventh command uses the **Module** parameter of the Get-Command cmdlet.</span></span> <span data-ttu-id="b4251-138">它将显示已由管理单元或模块添加到会话中的项。</span><span class="sxs-lookup"><span data-stu-id="b4251-138">It displays the items that were added to the session by a snap-in or module.</span></span>

<span data-ttu-id="b4251-139">你还可以使用 cmdlet 返回的对象的 **add-pssnapin** 属性 `Get-Command` 来查找生成 cmdlet 的管理单元或模块。</span><span class="sxs-lookup"><span data-stu-id="b4251-139">You can also use the **PSSnapin** property of the object that the `Get-Command` cmdlet returns to find the snap-in or module in which a cmdlet originated.</span></span> <span data-ttu-id="b4251-140">第八个命令使用点表示法查找 Set-Alias cmdlet 的 Add-pssnapin 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b4251-140">The eighth command uses dot notation to find the value of the PSSnapin property of the Set-Alias cmdlet.</span></span>

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

<span data-ttu-id="b4251-141">此示例将演示了在你的系统上注册管理单元，然后再将其添加到会话中的过程。</span><span class="sxs-lookup"><span data-stu-id="b4251-141">This example demonstrates the process of registering a snap-in on your system and then adding it to your session.</span></span> <span data-ttu-id="b4251-142">它使用 ManagementFeatures，它是在名为 ManagementCmdlets.dll 的文件中实现的虚拟管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-142">It uses ManagementFeatures, a fictitious snap-in implemented in a file that is named ManagementCmdlets.dll.</span></span>

## <span data-ttu-id="b4251-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4251-143">PARAMETERS</span></span>

### <span data-ttu-id="b4251-144">-Name</span><span class="sxs-lookup"><span data-stu-id="b4251-144">-Name</span></span>

<span data-ttu-id="b4251-145">指定管理单元的名称。</span><span class="sxs-lookup"><span data-stu-id="b4251-145">Specifies the name of the snap-in.</span></span> <span data-ttu-id="b4251-146">这是名称，而不是 AssemblyName 或 ModuleName。</span><span class="sxs-lookup"><span data-stu-id="b4251-146">This is the Name, not the AssemblyName or ModuleName.</span></span> <span data-ttu-id="b4251-147">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b4251-147">Wildcards are permitted.</span></span>

<span data-ttu-id="b4251-148">若要在系统上查找已注册的管理单元的名称，请键入 `Get-PSSnapin -Registered` 。</span><span class="sxs-lookup"><span data-stu-id="b4251-148">To find the names of the registered snap-ins on your system, type `Get-PSSnapin -Registered`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="b4251-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b4251-149">-PassThru</span></span>

<span data-ttu-id="b4251-150">指示此 cmdlet 返回表示每个已添加管理单元的对象。</span><span class="sxs-lookup"><span data-stu-id="b4251-150">Indicates that this cmdlet returns an object that represents each added snap-in.</span></span> <span data-ttu-id="b4251-151">默认情况下，此 cmdlet 将不产生任何输出。</span><span class="sxs-lookup"><span data-stu-id="b4251-151">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b4251-152">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b4251-152">CommonParameters</span></span>

<span data-ttu-id="b4251-153">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b4251-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4251-154">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b4251-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4251-155">输入</span><span class="sxs-lookup"><span data-stu-id="b4251-155">INPUTS</span></span>

### <span data-ttu-id="b4251-156">无</span><span class="sxs-lookup"><span data-stu-id="b4251-156">None</span></span>
<span data-ttu-id="b4251-157">不能通过管道将对象传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b4251-157">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="b4251-158">输出</span><span class="sxs-lookup"><span data-stu-id="b4251-158">OUTPUTS</span></span>

### <span data-ttu-id="b4251-159">无或 System.Management.Automation.PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="b4251-159">None or System.Management.Automation.PSSnapInInfo</span></span>

<span data-ttu-id="b4251-160">如果指定 **PassThru** 参数，则此 cmdlet 将返回表示该管理单元的 PSSnapInInfo 对象。</span><span class="sxs-lookup"><span data-stu-id="b4251-160">This cmdlet returns a PSSnapInInfo object that represents the snap-in if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="b4251-161">否则，此 cmdlet 将不生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="b4251-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="b4251-162">注释</span><span class="sxs-lookup"><span data-stu-id="b4251-162">NOTES</span></span>

* <span data-ttu-id="b4251-163">从 Windows PowerShell 3.0 开始，将与 Windows PowerShell 一起安装的核心命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="b4251-163">Beginning in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="b4251-164">在 Windows PowerShell 2.0 和在更高版本的 Windows PowerShell 中创建旧样式会话的主机程序中，核心命令打包在 (PSSnapins) 的管理单元中。</span><span class="sxs-lookup"><span data-stu-id="b4251-164">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins (PSSnapins).</span></span> <span data-ttu-id="b4251-165">**Microsoft.PowerShell.Core** 是例外情况，它始终是一个管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-165">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="b4251-166">此外，远程会话（如 New-PSSession cmdlet 启动的会话）是包括核心管理单元的旧样式会话。</span><span class="sxs-lookup"><span data-stu-id="b4251-166">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="b4251-167">有关 **CreateDefault2** 方法的详细信息，请参阅 MSDN library 中的 [CreateDefault2 方法](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) 。</span><span class="sxs-lookup"><span data-stu-id="b4251-167">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

* <span data-ttu-id="b4251-168">有关管理单元的详细信息，请参阅 [about_PSSnapins](About/about_PSSnapins.md) 和 [如何创建 Windows PowerShell 管理单元](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in)。</span><span class="sxs-lookup"><span data-stu-id="b4251-168">For more information about snap-ins, see [about_PSSnapins](About/about_PSSnapins.md) and [How to Create a Windows PowerShell Snap-in](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).</span></span>
* <span data-ttu-id="b4251-169">`Add-PSSnapin` 仅将管理单元添加到当前会话。</span><span class="sxs-lookup"><span data-stu-id="b4251-169">`Add-PSSnapin` adds the snap-in only to the current session.</span></span> <span data-ttu-id="b4251-170">若要将管理单元添加到所有 Windows PowerShell 会话中，请将该管理单元添加到你的 Windows PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="b4251-170">To add the snap-in to all Windows PowerShell sessions, add it to your Windows PowerShell profile.</span></span> <span data-ttu-id="b4251-171">有关详细信息，请参阅 about_Profiles。</span><span class="sxs-lookup"><span data-stu-id="b4251-171">For more information, see about_Profiles.</span></span>
* <span data-ttu-id="b4251-172">你可以添加已使用 Microsoft .NET Framework 安装实用工具注册的任何管理单元。</span><span class="sxs-lookup"><span data-stu-id="b4251-172">You can add any snap-in that has been registered using the Microsoft .NET Framework install utility.</span></span> <span data-ttu-id="b4251-173">有关详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="b4251-173">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>
* <span data-ttu-id="b4251-174">若要获取在你的计算机上注册的管理单元的列表，请键入 `Get-PSSnapin -Registered` 。</span><span class="sxs-lookup"><span data-stu-id="b4251-174">To get a list of snap-ins that are registered on your computer, type `Get-PSSnapin -Registered`.</span></span>
* <span data-ttu-id="b4251-175">在添加管理单元之前， `Add-PSSnapin` 检查管理单元的版本，以验证它是否与 Windows PowerShell 的当前版本兼容。</span><span class="sxs-lookup"><span data-stu-id="b4251-175">Before adding a snap-in, `Add-PSSnapin` checks the version of the snap-in to verify that it is compatible with the current version of Windows PowerShell.</span></span> <span data-ttu-id="b4251-176">如果管理单元未通过版本检查，则 Windows PowerShell 将报告错误。</span><span class="sxs-lookup"><span data-stu-id="b4251-176">If the snap-in fails the version check, Windows PowerShell reports an error.</span></span>

## <span data-ttu-id="b4251-177">相关链接</span><span class="sxs-lookup"><span data-stu-id="b4251-177">RELATED LINKS</span></span>

[<span data-ttu-id="b4251-178">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b4251-178">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="b4251-179">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b4251-179">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
