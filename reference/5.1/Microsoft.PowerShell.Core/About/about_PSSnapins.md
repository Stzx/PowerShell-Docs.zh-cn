---
description: 介绍 Windows PowerShell 管理单元，并演示如何使用和管理这些管理单元。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: 494b3275e4fe8a3aacdc358317950542962957cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388886"
---
# <a name="about-pssnapins"></a><span data-ttu-id="cfe94-104">关于 PSSnapins</span><span class="sxs-lookup"><span data-stu-id="cfe94-104">About PSSnapins</span></span>

## <a name="short-description"></a><span data-ttu-id="cfe94-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="cfe94-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="cfe94-106">介绍 Windows PowerShell 管理单元，并演示如何使用和管理这些管理单元。</span><span class="sxs-lookup"><span data-stu-id="cfe94-106">Describes  Windows PowerShell snap-ins and shows how to use and manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="cfe94-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="cfe94-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="cfe94-108">Windows PowerShell 管理单元是包含 Windows PowerShell 提供程序和或 cmdlet 的 Microsoft .NET Framework 程序集 \/ 。</span><span class="sxs-lookup"><span data-stu-id="cfe94-108">A Windows PowerShell snap-in is a Microsoft .NET Framework assembly that contains Windows PowerShell providers and\/or cmdlets.</span></span> <span data-ttu-id="cfe94-109">Windows PowerShell 包括一组基本管理单元，但你可以通过添加包含你所创建的提供程序和 cmdlet 的管理单元来扩展 Windows PowerShell 的功能和价值。</span><span class="sxs-lookup"><span data-stu-id="cfe94-109">Windows PowerShell includes a set of basic snap-ins, but you can extend the power and value of Windows PowerShell by adding snap-ins that contain providers and cmdlets that you create or get from others.</span></span>

<span data-ttu-id="cfe94-110">添加管理单元时，它包含的 cmdlet 和提供程序将立即可用于当前会话，但更改仅影响当前会话。</span><span class="sxs-lookup"><span data-stu-id="cfe94-110">When you add a snap-in, the cmdlets and providers that it contains are immediately available for use in the current session, but the change affects only the current session.</span></span>

<span data-ttu-id="cfe94-111">若要将管理单元添加到将来的所有会话中，请将其保存在你的 Windows PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="cfe94-111">To add the snap-in to all future sessions, save it in your Windows PowerShell profile.</span></span> <span data-ttu-id="cfe94-112">你还可以使用 Export-Console cmdlet 将管理单元名称保存到控制台文件中，然后在将来的会话中使用它。</span><span class="sxs-lookup"><span data-stu-id="cfe94-112">You can also use the Export-Console cmdlet to save the snap-in names to a console file and then use it in future sessions.</span></span> <span data-ttu-id="cfe94-113">你甚至可以保存多个控制台文件，每个文件都有一组不同的管理单元。</span><span class="sxs-lookup"><span data-stu-id="cfe94-113">You can even save multiple console files, each with a different set of snap-ins.</span></span>

<span data-ttu-id="cfe94-114">注意： Windows powershell 管理单元 (PSSnapins) 可在 Windows PowerShell 3.0 和 Windows PowerShell 2.0 中使用。</span><span class="sxs-lookup"><span data-stu-id="cfe94-114">NOTE: Windows PowerShell snap-ins (PSSnapins) are available for use in Windows PowerShell 3.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="cfe94-115">它们可能会在后续版本中更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="cfe94-115">They might be altered or unavailable in subsequent versions.</span></span> <span data-ttu-id="cfe94-116">若要打包 Windows PowerShell cmdlet 和提供程序，请使用模块。</span><span class="sxs-lookup"><span data-stu-id="cfe94-116">To package Windows PowerShell cmdlets and providers, use modules.</span></span> <span data-ttu-id="cfe94-117">若要了解如何创建模块并将管理单元转换为模块，请参阅 [编写 Windows PowerShell 模块](/powershell/scripting/developer/module/writing-a-windows-powershell-module)。</span><span class="sxs-lookup"><span data-stu-id="cfe94-117">For information about creating modules and converting snap-ins to modules, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

### <a name="finding-snap-ins"></a><span data-ttu-id="cfe94-118">查找管理单元</span><span class="sxs-lookup"><span data-stu-id="cfe94-118">FINDING SNAP-INS</span></span>

<span data-ttu-id="cfe94-119">若要获取计算机上的 Windows PowerShell 管理单元的列表，请键入：</span><span class="sxs-lookup"><span data-stu-id="cfe94-119">To get a list of the  Windows PowerShell snap-ins on your computer, type:</span></span>

```powershell
Get-PSSnapin
```

<span data-ttu-id="cfe94-120">若要获取每个 Windows PowerShell 提供程序的管理单元，请键入：</span><span class="sxs-lookup"><span data-stu-id="cfe94-120">To get the snap-in for each  Windows PowerShell provider, type:</span></span>

```powershell
Get-PSProvider | Format-List name, pssnapin
```

<span data-ttu-id="cfe94-121">若要获取 Windows PowerShell 管理单元中的 cmdlet 列表，请键入：</span><span class="sxs-lookup"><span data-stu-id="cfe94-121">To get a list of the cmdlets in a  Windows PowerShell snap-in, type:</span></span>

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a><span data-ttu-id="cfe94-122">安装管理单元</span><span class="sxs-lookup"><span data-stu-id="cfe94-122">INSTALLING A SNAP-IN</span></span>

<span data-ttu-id="cfe94-123">内置的管理单元在系统中注册，并在启动 Windows PowerShell 时添加到默认会话中。</span><span class="sxs-lookup"><span data-stu-id="cfe94-123">The built-in snap-ins are registered in the system and added to the default session when you start Windows PowerShell.</span></span> <span data-ttu-id="cfe94-124">但是，你必须注册你创建的管理单元或从其他设备获取的管理单元，然后将该管理单元添加到你的会话。</span><span class="sxs-lookup"><span data-stu-id="cfe94-124">However, you have to register snap-ins that you create or obtain from others and then add the snap-ins to your session.</span></span>

### <a name="registering-a-snap-in"></a><span data-ttu-id="cfe94-125">注册管理单元</span><span class="sxs-lookup"><span data-stu-id="cfe94-125">REGISTERING A SNAP-IN</span></span>

<span data-ttu-id="cfe94-126">Windows PowerShell 管理单元是用编译到 .dll 文件的 .NET Framework 语言编写的程序。</span><span class="sxs-lookup"><span data-stu-id="cfe94-126">A Windows PowerShell snap-in is a program written in a .NET Framework language that is compiled into a .dll file.</span></span> <span data-ttu-id="cfe94-127">若要在管理单元中使用提供程序和 cmdlet，必须先注册管理单元 (将其添加到注册表) 。</span><span class="sxs-lookup"><span data-stu-id="cfe94-127">To use the providers and cmdlets in a snap-in, you must first register the snap-in (add it to the registry).</span></span>

<span data-ttu-id="cfe94-128">大多数管理单元都包含一个安装程序， (为您注册 .dll 文件的 .exe 或 .msi 文件) 。</span><span class="sxs-lookup"><span data-stu-id="cfe94-128">Most snap-ins include an installation program (an .exe or .msi file) that registers the .dll file for you.</span></span> <span data-ttu-id="cfe94-129">但是，如果您接收到作为 .dll 文件的管理单元，则可以将其注册到您的系统上。</span><span class="sxs-lookup"><span data-stu-id="cfe94-129">However, if you receive a snap-in as a .dll file, you can register it on your system.</span></span> <span data-ttu-id="cfe94-130">有关详细信息，请参阅 [如何注册 cmdlet、提供程序和主机应用程序](/previous-versions//ms714644(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="cfe94-130">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

<span data-ttu-id="cfe94-131">若要获取系统上所有已注册的管理单元，或验证是否注册了管理单元，请键入：</span><span class="sxs-lookup"><span data-stu-id="cfe94-131">To get all the registered snap-ins on your system or to verify that a snap-in is registered, type:</span></span>

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a><span data-ttu-id="cfe94-132">将管理单元添加到当前会话</span><span class="sxs-lookup"><span data-stu-id="cfe94-132">ADDING THE SNAP-IN TO THE CURRENT SESSION</span></span>

<span data-ttu-id="cfe94-133">若要将已注册的管理单元添加到当前会话中，请使用 Add-PsSnapin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfe94-133">To add a registered snap-in to the current session, use the Add-PsSnapin cmdlet.</span></span> <span data-ttu-id="cfe94-134">例如，若要将 Microsoft SQL Server 管理单元添加到会话中，请键入：</span><span class="sxs-lookup"><span data-stu-id="cfe94-134">For example, to add the Microsoft SQL Server snap-in to the session, type:</span></span>

```powershell
Add-PSSnapin sql
```

<span data-ttu-id="cfe94-135">完成该命令后，该管理单元中的提供程序和 cmdlet 将在该会话中可用。</span><span class="sxs-lookup"><span data-stu-id="cfe94-135">After the command is completed, the providers and cmdlets in the snap-in are available in the session.</span></span> <span data-ttu-id="cfe94-136">但是，它们仅在当前会话中可用，除非您保存它们。</span><span class="sxs-lookup"><span data-stu-id="cfe94-136">However, they are available only in the current session unless you save them.</span></span>

### <a name="saving-the-snap-ins"></a><span data-ttu-id="cfe94-137">保存管理单元</span><span class="sxs-lookup"><span data-stu-id="cfe94-137">SAVING THE SNAP-INS</span></span>

<span data-ttu-id="cfe94-138">若要在将来的 Windows PowerShell 会话中使用管理单元，请将 Add-PsSnapin 命令添加到 Windows PowerShell 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="cfe94-138">To use a snap-in in future Windows PowerShell sessions, add the Add-PsSnapin command to your Windows PowerShell profile.</span></span> <span data-ttu-id="cfe94-139">或者将管理单元的名称导出到控制台文件。</span><span class="sxs-lookup"><span data-stu-id="cfe94-139">Or, export the snap-in names to a console file.</span></span>

<span data-ttu-id="cfe94-140">如果将 Add-PSSnapin 命令添加到配置文件，则在将来的所有 Windows PowerShell 会话中都可以使用此命令。</span><span class="sxs-lookup"><span data-stu-id="cfe94-140">If you add the Add-PSSnapin command to your profile, it is available in all future Windows PowerShell sessions.</span></span> <span data-ttu-id="cfe94-141">如果导出会话中的管理单元的名称，则只能在需要管理单元时使用导出文件。</span><span class="sxs-lookup"><span data-stu-id="cfe94-141">If you export the names of the snap-ins in your session, you can use the export file only when you need the snap-ins.</span></span>

<span data-ttu-id="cfe94-142">若要将 Add-PsSnapin 命令添加到 Windows PowerShell 配置文件中，请打开配置文件，粘贴或键入命令，然后保存该配置文件。</span><span class="sxs-lookup"><span data-stu-id="cfe94-142">To add the Add-PsSnapin command to your Windows PowerShell profile, open your profile, paste or type the command, and then save the profile.</span></span> <span data-ttu-id="cfe94-143">有关详细信息，请参阅 about_Profiles。</span><span class="sxs-lookup"><span data-stu-id="cfe94-143">For more information, see about_Profiles.</span></span>

<span data-ttu-id="cfe94-144">若要从控制台文件 () 中的会话保存管理单元，请使用 Export-Console cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfe94-144">To save the snap-ins from a session in console file (.psc1), use the Export-Console cmdlet.</span></span> <span data-ttu-id="cfe94-145">例如，要将当前会话配置中的管理单元保存到当前目录中的 Newconsole.psc1 文件，请键入：</span><span class="sxs-lookup"><span data-stu-id="cfe94-145">For example, to save the snap-ins in the current session configuration to the NewConsole.psc1 file in the current directory, type:</span></span>

```powershell
Export-Console NewConsole
```

<span data-ttu-id="cfe94-146">有关详细信息，请参阅导出-控制台。</span><span class="sxs-lookup"><span data-stu-id="cfe94-146">For more information, see Export-Console.</span></span>

### <a name="opening-windows-powershell-with-a-console-file"></a><span data-ttu-id="cfe94-147">使用控制台文件打开 WINDOWS POWERSHELL</span><span class="sxs-lookup"><span data-stu-id="cfe94-147">OPENING WINDOWS POWERSHELL WITH A CONSOLE FILE</span></span>

<span data-ttu-id="cfe94-148">若要使用包含管理单元的控制台文件，请从 Cmd.exe 或其他 Windows PowerShell 会话的命令提示符下启动 Windows PowerShell ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="cfe94-148">To use a console file that includes the snap-in, start Windows PowerShell (PowerShell.exe) from the command prompt in Cmd.exe or in another Windows PowerShell session.</span></span> <span data-ttu-id="cfe94-149">使用 PsConsoleFile 参数指定包含管理单元的控制台文件。</span><span class="sxs-lookup"><span data-stu-id="cfe94-149">Use the PsConsoleFile parameter to specify the console file that includes the snap-in.</span></span> <span data-ttu-id="cfe94-150">例如，以下命令将启动带有 .psc1 控制台文件的 Windows PowerShell Newconsole.psc1：</span><span class="sxs-lookup"><span data-stu-id="cfe94-150">For example, the following command starts Windows PowerShell with the NewConsole.psc1 console file:</span></span>

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

<span data-ttu-id="cfe94-151">管理单元中的提供程序和 cmdlet 现在可在会话中使用。</span><span class="sxs-lookup"><span data-stu-id="cfe94-151">The providers and cmdlets in the snapin are now available for use in the session.</span></span>

### <a name="removing-a-snap-in"></a><span data-ttu-id="cfe94-152">删除管理单元</span><span class="sxs-lookup"><span data-stu-id="cfe94-152">REMOVING A SNAP-IN</span></span>

<span data-ttu-id="cfe94-153">若要从当前会话中删除 Windows PowerShell 管理单元，请使用 Remove-PsSnapin cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfe94-153">To remove a Windows PowerShell snap-in from the current session, use the Remove-PsSnapin cmdlet.</span></span> <span data-ttu-id="cfe94-154">例如，若要从当前会话中删除 SQL Server 管理单元，请键入：</span><span class="sxs-lookup"><span data-stu-id="cfe94-154">For example, to remove the SQL Server snap-in from the current session, type:</span></span>

```powershell
Remove-PSSnapin sql
```

<span data-ttu-id="cfe94-155">此 cmdlet 将从会话中删除管理单元。</span><span class="sxs-lookup"><span data-stu-id="cfe94-155">This cmdlet removes the snap-in from the session.</span></span> <span data-ttu-id="cfe94-156">仍加载管理单元，但它支持的提供程序和 cmdlet 不再可用。</span><span class="sxs-lookup"><span data-stu-id="cfe94-156">The snap-in is still loaded, but the providers and cmdlets that it supports are no longer available.</span></span>

### <a name="built-in-commands"></a><span data-ttu-id="cfe94-157">内置命令</span><span class="sxs-lookup"><span data-stu-id="cfe94-157">BUILT-IN COMMANDS</span></span>

<span data-ttu-id="cfe94-158">在 Windows PowerShell 2.0 和 windows powershell 3.0 及更高版本的旧式主机程序中，随 Windows PowerShell 一起安装的内置命令会打包在自动添加到每个 Windows PowerShell 会话的管理单元中。</span><span class="sxs-lookup"><span data-stu-id="cfe94-158">In Windows PowerShell 2.0 and in older-style host programs in Windows PowerShell 3.0 and later, the built-in commands that are installed with Windows PowerShell are packaged in snap-ins that are added automatically to every Windows PowerShell session.</span></span>

<span data-ttu-id="cfe94-159">从 Windows PowerShell 3.0 开始，在更新样式的主机程序中（使用 InitialSessionState. CreateDefault2 方法启动会话的程序），内置命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="cfe94-159">Beginning in Windows PowerShell 3.0, in newer-style host programs -- those that start sessions by using the InitialSessionState.CreateDefault2 method -- the built-in commands are packaged in modules.</span></span> <span data-ttu-id="cfe94-160">异常是 Microsoft. Core，它始终显示为管理单元。</span><span class="sxs-lookup"><span data-stu-id="cfe94-160">The exception is Microsoft.PowerShell.Core, which always appears as a snap-in.</span></span> <span data-ttu-id="cfe94-161">默认情况下，每个会话中都包含 "核心" 管理单元。</span><span class="sxs-lookup"><span data-stu-id="cfe94-161">The Core snap-in is included in every session by default.</span></span> <span data-ttu-id="cfe94-162">内置模块将在首次使用时自动加载。</span><span class="sxs-lookup"><span data-stu-id="cfe94-162">The built-in modules are loaded automatically on first-use.</span></span>

<span data-ttu-id="cfe94-163">注意：远程会话（包括使用 New-PSSession cmdlet 启动的会话）是旧样式的会话，其中内置命令打包在管理单元中。</span><span class="sxs-lookup"><span data-stu-id="cfe94-163">NOTE: Remote sessions, including sessions that are started by using the New-PSSession cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="cfe94-164">以下管理单元 (或模块) 随 Windows PowerShell 一起安装。</span><span class="sxs-lookup"><span data-stu-id="cfe94-164">The following snap-ins (or modules) are installed with Windows PowerShell.</span></span>

- <span data-ttu-id="cfe94-165">Microsoft. Core-包含用于管理 Windows PowerShell 的基本功能的提供程序和 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cfe94-165">Microsoft.PowerShell.Core - Contains providers and cmdlets used to manage the basic features of Windows PowerShell.</span></span> <span data-ttu-id="cfe94-166">它包括文件系统、注册表、别名、环境、函数、变量提供程序和基本 cmdlet，如 Get-help、Get 命令和获取历史记录。</span><span class="sxs-lookup"><span data-stu-id="cfe94-166">It includes the FileSystem, Registry, Alias, Environment, Function, and Variable providers and basic cmdlets like Get-Help, Get-Command, and Get-History.</span></span>

- <span data-ttu-id="cfe94-167">Microsoft 包含 Windows PowerShell 主机使用的 cmdlet，例如 Start-Transcript 和停止脚本。</span><span class="sxs-lookup"><span data-stu-id="cfe94-167">Microsoft.PowerShell.Host - Contains cmdlets used by the Windows PowerShell host, such as Start-Transcript and Stop-Transcript.</span></span>

- <span data-ttu-id="cfe94-168">-包含用于管理基于 Windows 的功能的 cmdlet，例如 Get-Service 和 Get-ChildItem。</span><span class="sxs-lookup"><span data-stu-id="cfe94-168">Microsoft.PowerShell.Management - Contains cmdlets such as Get-Service and Get-ChildItem that are used to manage Windows-based features.</span></span>

- <span data-ttu-id="cfe94-169">Get-authenticodesignature-包含用于管理 Windows PowerShell 安全的证书提供程序和 cmdlet，例如获取 Acl、和 Convertto-html-SecureString。</span><span class="sxs-lookup"><span data-stu-id="cfe94-169">Microsoft.PowerShell.Security - Contains the Certificate provider and cmdlets used to manage Windows PowerShell security, such as Get-Acl, Get-AuthenticodeSignature, and ConvertTo-SecureString.</span></span>

- <span data-ttu-id="cfe94-170">Microsoft PowerShell-包含用于操作对象和数据的 cmdlet，如获取成员、写入主机和格式列表。</span><span class="sxs-lookup"><span data-stu-id="cfe94-170">Microsoft.PowerShell.Utility - Contains cmdlets used to manipulate objects and data, such as Get-Member, Write-Host, and Format-List.</span></span>

- <span data-ttu-id="cfe94-171">Enable-wsmancredssp-包含用于管理 Windows 远程管理服务的 WSMan 提供程序和 cmdlet，如 Connect-WSMan 和。</span><span class="sxs-lookup"><span data-stu-id="cfe94-171">Microsoft.WSMan.Management - Contains the WSMan provider and cmdlets that manage the Windows Remote Management service, such as Connect-WSMan and Enable-WSManCredSSP.</span></span>

## <a name="logging-snap-in-events"></a><span data-ttu-id="cfe94-172">记录管理单元事件</span><span class="sxs-lookup"><span data-stu-id="cfe94-172">LOGGING SNAP-IN EVENTS</span></span>

<span data-ttu-id="cfe94-173">从 Windows PowerShell 3.0 开始，可以通过将模块和管理单元的 LogPipelineExecutionDetails 属性设置为 TRUE，在 Windows PowerShell 模块和管理单元中记录 cmdlet 的执行事件。</span><span class="sxs-lookup"><span data-stu-id="cfe94-173">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="cfe94-174">有关详细信息，请参阅 [about_EventLogs](about_EventLogs.md)。</span><span class="sxs-lookup"><span data-stu-id="cfe94-174">For more information, see [about_EventLogs](about_EventLogs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cfe94-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfe94-175">SEE ALSO</span></span>

[<span data-ttu-id="cfe94-176">Add-pssnapin</span><span class="sxs-lookup"><span data-stu-id="cfe94-176">Add-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[<span data-ttu-id="cfe94-177">Add-pssnapin</span><span class="sxs-lookup"><span data-stu-id="cfe94-177">Get-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[<span data-ttu-id="cfe94-178">Add-pssnapin</span><span class="sxs-lookup"><span data-stu-id="cfe94-178">Remove-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[<span data-ttu-id="cfe94-179">Export-Console</span><span class="sxs-lookup"><span data-stu-id="cfe94-179">Export-Console</span></span>](xref:Microsoft.PowerShell.Core.Export-Console)

[<span data-ttu-id="cfe94-180">Get-Command</span><span class="sxs-lookup"><span data-stu-id="cfe94-180">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="cfe94-181">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="cfe94-181">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="cfe94-182">about_Modules</span><span class="sxs-lookup"><span data-stu-id="cfe94-182">about_Modules</span></span>](about_Modules.md)

## <a name="keywords"></a><span data-ttu-id="cfe94-183">字</span><span class="sxs-lookup"><span data-stu-id="cfe94-183">KEYWORDS</span></span>

<span data-ttu-id="cfe94-184">about_Snapins、about_Snap_ins、about_Snap</span><span class="sxs-lookup"><span data-stu-id="cfe94-184">about_Snapins, about_Snap_ins, about_Snap-ins</span></span>
