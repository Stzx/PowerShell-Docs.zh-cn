---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSSnapin
ms.openlocfilehash: 472a4c8fbb9eb0d37827aff4fcfd6bb9a67f4743
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197430"
---
# <span data-ttu-id="78b4d-103">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="78b4d-103">Get-PSSnapin</span></span>

## <span data-ttu-id="78b4d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="78b4d-104">SYNOPSIS</span></span>
<span data-ttu-id="78b4d-105">获取计算机上的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-105">Gets the Windows PowerShell snap-ins on the computer.</span></span>

## <span data-ttu-id="78b4d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="78b4d-106">SYNTAX</span></span>

```
Get-PSSnapin [[-Name] <String[]>] [-Registered] [<CommonParameters>]
```

## <span data-ttu-id="78b4d-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="78b4d-107">DESCRIPTION</span></span>
<span data-ttu-id="78b4d-108">**Add-pssnapin** cmdlet 将获取已添加到当前会话中或已在系统上注册的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-108">The **Get-PSSnapin** cmdlet gets the Windows PowerShell snap-ins that have been added to the current session or that have been registered on the system.</span></span>
<span data-ttu-id="78b4d-109">此 cmdlet 按照检测到的顺序列出这些管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-109">This cmdlet lists the snap-ins in the order in which they are detected.</span></span>

<span data-ttu-id="78b4d-110">**Add-pssnapin** 仅获取已注册的管理单元。若要注册 Windows PowerShell 管理单元，请使用 Microsoft .NET Framework 2.0 附带的 Installutil.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="78b4d-110">**Get-PSSnapin** gets only registered snap-ins. To register a Windows PowerShell snap-in, use the InstallUtil tool included with the Microsoft .NET Framework 2.0.</span></span>
<span data-ttu-id="78b4d-111">有关详细信息，请参阅 MSDN library 中的 " [如何注册 cmdlet、提供程序和主机应用程序](https://go.microsoft.com/fwlink/?LinkID=143619) "。</span><span class="sxs-lookup"><span data-stu-id="78b4d-111">For more information, see [How to Register Cmdlets, Providers, and Host Applications](https://go.microsoft.com/fwlink/?LinkID=143619) in the MSDN library.</span></span>

<span data-ttu-id="78b4d-112">从 Windows PowerShell 3.0 开始，Windows PowerShell 中包含的核心命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="78b4d-112">Starting in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span>
<span data-ttu-id="78b4d-113">例外情况是 **Microsoft.PowerShell.Core** ，它是一个管理单元 (PSSnapin)。</span><span class="sxs-lookup"><span data-stu-id="78b4d-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="78b4d-114">默认情况下，仅将 **Microsoft.PowerShell.Core** 管理单元添加到会话中。</span><span class="sxs-lookup"><span data-stu-id="78b4d-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span>
<span data-ttu-id="78b4d-115">首次使用时自动导入模块，而且可以使用 Import-Module cmdlet 导入它们。</span><span class="sxs-lookup"><span data-stu-id="78b4d-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="78b4d-116">示例</span><span class="sxs-lookup"><span data-stu-id="78b4d-116">EXAMPLES</span></span>

### <span data-ttu-id="78b4d-117">示例1：获取当前加载的管理单元</span><span class="sxs-lookup"><span data-stu-id="78b4d-117">Example 1: Get snap-ins that are currently loaded</span></span>

```
PS C:\> Get-PSSnapIn
```

<span data-ttu-id="78b4d-118">此命令获取当前在会话中加载的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-118">This command gets the Windows PowerShell snap-ins that are currently loaded in the session.</span></span>
<span data-ttu-id="78b4d-119">这包括与 Windows PowerShell 一起安装的以及添加到此会话的那些管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-119">This includes the snap-ins that are installed with Windows PowerShell and those that have been added to the session.</span></span>

### <span data-ttu-id="78b4d-120">示例2：获取已注册的管理单元</span><span class="sxs-lookup"><span data-stu-id="78b4d-120">Example 2: Get snap-ins that have been registered</span></span>

```
PS C:\> get-PSSnapIn -Registered
```

<span data-ttu-id="78b4d-121">此命令获取已在计算机上注册的 Windows PowerShell 管理单元，包括那些已添加到会话的管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-121">This command gets the Windows PowerShell snap-ins that have been registered on the computer, including those that have already been added to the session.</span></span>
<span data-ttu-id="78b4d-122">输出不包括与 Windows PowerShell 或 Windows PowerShell 管理单元动态链接库 (DLL) 一起安装的管理单元，它们尚未在系统上注册。</span><span class="sxs-lookup"><span data-stu-id="78b4d-122">The output does not include snap-ins that are installed with Windows PowerShell or Windows PowerShell snap-in dynamic-link libraries (DLLs) that have not yet been registered on the system.</span></span>

### <span data-ttu-id="78b4d-123">示例3：获取与字符串匹配的当前管理单元</span><span class="sxs-lookup"><span data-stu-id="78b4d-123">Example 3: Get current snap-ins that match a string</span></span>

```
PS C:\> Get-PSSnapIn -Name smp*
```

<span data-ttu-id="78b4d-124">此命令将获取当前会话中名称以 smp 开头的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-124">This command gets the Windows PowerShell snap-ins in the current session that have names that begin with smp.</span></span>

## <span data-ttu-id="78b4d-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="78b4d-125">PARAMETERS</span></span>

### <span data-ttu-id="78b4d-126">-Name</span><span class="sxs-lookup"><span data-stu-id="78b4d-126">-Name</span></span>
<span data-ttu-id="78b4d-127">指定管理单元名称的数组。</span><span class="sxs-lookup"><span data-stu-id="78b4d-127">Specifies an array of snap-in names.</span></span>
<span data-ttu-id="78b4d-128">此 cmdlet 仅获取指定的 Windows PowerShell 管理单元。允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="78b4d-128">This cmdlet gets only the specified Windows PowerShell snap-ins. Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="78b4d-129">-Registered</span><span class="sxs-lookup"><span data-stu-id="78b4d-129">-Registered</span></span>
<span data-ttu-id="78b4d-130">指示此 cmdlet 获取已在系统上注册的 Windows PowerShell 管理单元，即使尚未将它们添加到会话中也是如此。</span><span class="sxs-lookup"><span data-stu-id="78b4d-130">Indicates that this cmdlet gets the Windows PowerShell snap-ins that have been registered on the system even if they have not yet been added to the session.</span></span>

<span data-ttu-id="78b4d-131">与 Windows PowerShell 一起安装的管理单元不会出现在此列表中。</span><span class="sxs-lookup"><span data-stu-id="78b4d-131">The snap-ins that are installed with Windows PowerShell do not appear in this list.</span></span>

<span data-ttu-id="78b4d-132">如果没有此参数， **add-pssnapin** 将获取已添加到会话中的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-132">Without this parameter, **Get-PSSnapin** gets the Windows PowerShell snap-ins that have been added to the session.</span></span>

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

### <span data-ttu-id="78b4d-133">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="78b4d-133">CommonParameters</span></span>
<span data-ttu-id="78b4d-134">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="78b4d-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="78b4d-135">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="78b4d-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="78b4d-136">输入</span><span class="sxs-lookup"><span data-stu-id="78b4d-136">INPUTS</span></span>

### <span data-ttu-id="78b4d-137">无</span><span class="sxs-lookup"><span data-stu-id="78b4d-137">None</span></span>
<span data-ttu-id="78b4d-138">不能通过管道将输入传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78b4d-138">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="78b4d-139">输出</span><span class="sxs-lookup"><span data-stu-id="78b4d-139">OUTPUTS</span></span>

### <span data-ttu-id="78b4d-140">System.Management.Automation.PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="78b4d-140">System.Management.Automation.PSSnapInInfo</span></span>
<span data-ttu-id="78b4d-141">Get-PSSnapin 将返回它所获取的每个管理单元的对象。</span><span class="sxs-lookup"><span data-stu-id="78b4d-141">Get-PSSnapin returns an object for each snap-in that it gets.</span></span>

## <span data-ttu-id="78b4d-142">注释</span><span class="sxs-lookup"><span data-stu-id="78b4d-142">NOTES</span></span>

* <span data-ttu-id="78b4d-143">从 Windows PowerShell 3.0 开始，随 Windows PowerShell 一起安装的核心命令打包在模块中。</span><span class="sxs-lookup"><span data-stu-id="78b4d-143">Starting in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="78b4d-144">在 Windows PowerShell 2.0 和在更高版本的 Windows PowerShell 中创建旧样式会话的主机程序中，核心命令打包在 ( **add-pssnapin** ) 的管理单元中。</span><span class="sxs-lookup"><span data-stu-id="78b4d-144">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins ( **PSSnapin** ).</span></span> <span data-ttu-id="78b4d-145">**Microsoft.PowerShell.Core** 是例外情况，它始终是一个管理单元。</span><span class="sxs-lookup"><span data-stu-id="78b4d-145">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="78b4d-146">此外，远程会话（如 New-PSSession cmdlet 启动的会话）是包括核心管理单元的旧样式会话。</span><span class="sxs-lookup"><span data-stu-id="78b4d-146">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="78b4d-147">有关 **CreateDefault2** 方法的详细信息，请参阅 MSDN library 中的 [CreateDefault2 方法](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) 。</span><span class="sxs-lookup"><span data-stu-id="78b4d-147">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

## <span data-ttu-id="78b4d-148">相关链接</span><span class="sxs-lookup"><span data-stu-id="78b4d-148">RELATED LINKS</span></span>

[<span data-ttu-id="78b4d-149">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="78b4d-149">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="78b4d-150">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="78b4d-150">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
