---
description: 介绍如何使用 PowerShell_Ise.exe 命令行工具。
keywords: powershell,cmdlet
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_powershell_ise_exe?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PowerShell_Ise_exe
ms.openlocfilehash: c7500eb6d8586b9dca568edc4e805c577e94bec4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "93200265"
---
# <a name="about-powershell-iseexe"></a><span data-ttu-id="6211e-104">关于 PowerShell Ise.exe</span><span class="sxs-lookup"><span data-stu-id="6211e-104">About PowerShell Ise.exe</span></span>

## <a name="short-description"></a><span data-ttu-id="6211e-105">简短说明</span><span class="sxs-lookup"><span data-stu-id="6211e-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="6211e-106">介绍如何使用 PowerShell_Ise.exe 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="6211e-106">Explains how to use the PowerShell_Ise.exe command-line tool.</span></span>

## <a name="long-description"></a><span data-ttu-id="6211e-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="6211e-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="6211e-108">PowerShell_Ise.exe 在 (ISE) 会话中启动 Windows PowerShell 集成脚本环境。</span><span class="sxs-lookup"><span data-stu-id="6211e-108">PowerShell_Ise.exe starts a Windows PowerShell Integrated Scripting Environment (ISE) session.</span></span> <span data-ttu-id="6211e-109">可以在 Cmd.exe 和 Windows PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="6211e-109">You can run it in Cmd.exe and in Windows PowerShell.</span></span>

<span data-ttu-id="6211e-110">若要运行 PowerShell_ISE.exe，请键入 PowerShell_ISE.exe、PowerShell_ISE 或 ISE。</span><span class="sxs-lookup"><span data-stu-id="6211e-110">To run PowerShell_ISE.exe, type PowerShell_ISE.exe, PowerShell_ISE, or ISE.</span></span>

## <a name="syntax"></a><span data-ttu-id="6211e-111">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6211e-111">SYNTAX</span></span>

```
PowerShell_Ise[.exe]
PowerShell_ISE[.exe]
ISE[.exe]
[-File]<FilePath[]> [-NoProfile] [-MTA]
-Help | ? | -? | /? Displays the syntax and describes the command-line switches.
```

## <a name="parameters"></a><span data-ttu-id="6211e-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6211e-112">PARAMETERS</span></span>

### <a name="-file"></a><span data-ttu-id="6211e-113">-File</span><span class="sxs-lookup"><span data-stu-id="6211e-113">-File</span></span>

<span data-ttu-id="6211e-114">在 Windows PowerShell ISE 中打开指定的文件。</span><span class="sxs-lookup"><span data-stu-id="6211e-114">Opens the specified files in Windows PowerShell ISE.</span></span> <span data-ttu-id="6211e-115">参数名称 ( "-File" ) 是可选的。</span><span class="sxs-lookup"><span data-stu-id="6211e-115">The parameter name ("-File") is optional.</span></span> <span data-ttu-id="6211e-116">若要列出多个文件，请输入一个用引号引起来的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="6211e-116">To list more than one file, enter one text string enclosed in quotation marks.</span></span> <span data-ttu-id="6211e-117">使用逗号分隔字符串中的文件名。</span><span class="sxs-lookup"><span data-stu-id="6211e-117">Use commas to separate the file names within the string.</span></span>

<span data-ttu-id="6211e-118">例如：</span><span class="sxs-lookup"><span data-stu-id="6211e-118">For example:</span></span>

<span data-ttu-id="6211e-119">PowerShell_ISE 文件 "File1.ps1、File2.ps1 File3.xml"。</span><span class="sxs-lookup"><span data-stu-id="6211e-119">PowerShell_ISE -File "File1.ps1,File2.ps1,File3.xml".</span></span>

<span data-ttu-id="6211e-120">文件名称之间的空格允许在 Windows PowerShell 中使用，但可能无法由其他程序（如 Cmd.exe）正确解释。</span><span class="sxs-lookup"><span data-stu-id="6211e-120">Spaces between the file names are permitted in Windows PowerShell, but might not be interpreted correctly by other programs, such as Cmd.exe.</span></span>

<span data-ttu-id="6211e-121">可以使用此参数打开任何文本文件，包括 Windows PowerShell 脚本文件和 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="6211e-121">You can use this parameter to open any text file, including Windows PowerShell script files and XML files.</span></span>

### <a name="-mta"></a><span data-ttu-id="6211e-122">-Mta</span><span class="sxs-lookup"><span data-stu-id="6211e-122">-Mta</span></span>

<span data-ttu-id="6211e-123">使用多线程单元启动 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="6211e-123">Starts Windows PowerShell ISE using a multi-threaded apartment.</span></span> <span data-ttu-id="6211e-124">此参数是在 Windows PowerShell 3.0 中引入的。</span><span class="sxs-lookup"><span data-stu-id="6211e-124">This parameter is introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="6211e-125">单线程单元 (STA) 是默认值。</span><span class="sxs-lookup"><span data-stu-id="6211e-125">Single-threaded apartment (STA) is the default.</span></span>

### <a name="-noprofile"></a><span data-ttu-id="6211e-126">-NoProfile</span><span class="sxs-lookup"><span data-stu-id="6211e-126">-NoProfile</span></span>

<span data-ttu-id="6211e-127">不运行 Windows PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="6211e-127">Does not run Windows PowerShell profiles.</span></span> <span data-ttu-id="6211e-128">默认情况下，Windows PowerShell 配置文件在每个会话中运行。</span><span class="sxs-lookup"><span data-stu-id="6211e-128">By default, Windows PowerShell profiles are run in every session.</span></span>

<span data-ttu-id="6211e-129">编写共享内容（如将在具有不同配置文件的系统上运行的函数和脚本）时，建议使用此参数。</span><span class="sxs-lookup"><span data-stu-id="6211e-129">This parameter is recommended when you are writing shared content, such as functions and scripts that will be run on systems with different profiles.</span></span>
<span data-ttu-id="6211e-130">有关详细信息，请参阅 [about_Profiles](about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="6211e-130">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="-help---"></a><span data-ttu-id="6211e-131">-Help-?,/？</span><span class="sxs-lookup"><span data-stu-id="6211e-131">-Help -?, /?</span></span>

<span data-ttu-id="6211e-132">显示 PowerShell_ISE.exe 的帮助。</span><span class="sxs-lookup"><span data-stu-id="6211e-132">Displays help for PowerShell_ISE.exe.</span></span>

## <a name="examples"></a><span data-ttu-id="6211e-133">示例</span><span class="sxs-lookup"><span data-stu-id="6211e-133">EXAMPLES</span></span>

<span data-ttu-id="6211e-134">这些命令启动 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="6211e-134">These commands start Windows PowerShell ISE.</span></span> <span data-ttu-id="6211e-135">这两个命令是等效的，因此可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="6211e-135">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe
PS C:> PowerShell_ISE
PS C:> ISE
```

<span data-ttu-id="6211e-136">这些命令将在 Windows PowerShell ISE 中打开 Get-Profile.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="6211e-136">These commands open the Get-Profile.ps1 script in Windows PowerShell ISE.</span></span>
<span data-ttu-id="6211e-137">这两个命令是等效的，因此可以互换使用。</span><span class="sxs-lookup"><span data-stu-id="6211e-137">The commands are equivalent and can be used interchangeably.</span></span>

```
PS C:> PowerShell_ISE.exe -File .\Get-Profile.ps1
PS C:> ISE -File .\Get-Profile.ps1
PS C:> ISE .\Get-Profile.ps1
```

<span data-ttu-id="6211e-138">此命令打开 Windows PowerShell ISE 中的 Get-Backups.ps1 和 Get-BackupInstance.ps1 脚本。</span><span class="sxs-lookup"><span data-stu-id="6211e-138">This command opens the Get-Backups.ps1 and Get-BackupInstance.ps1 scripts in Windows PowerShell ISE.</span></span> <span data-ttu-id="6211e-139">若要打开多个文件，请使用逗号分隔文件名，并将整个文件名值用引号引起来。</span><span class="sxs-lookup"><span data-stu-id="6211e-139">To open more than one file, use a comma to separate the file names and enclose the entire file name value in quotation marks.</span></span>

```
PS C:> ISE -File ".\Get-Backups.ps1,Get-BackupInstance.ps1"
```

<span data-ttu-id="6211e-140">此命令启动不带配置文件的 Windows PowerShell ISE。</span><span class="sxs-lookup"><span data-stu-id="6211e-140">This command starts Windows PowerShell ISE with no profiles.</span></span>

```
PS C:> ISE -NoProfile
```

<span data-ttu-id="6211e-141">此命令获取 PowerShell_ISE.exe 的帮助。</span><span class="sxs-lookup"><span data-stu-id="6211e-141">This command gets help for PowerShell_ISE.exe.</span></span>

```
PS C:> ISE -help
```

## <a name="see-also"></a><span data-ttu-id="6211e-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6211e-142">SEE ALSO</span></span>

[<span data-ttu-id="6211e-143">about_PowerShell.exe</span><span class="sxs-lookup"><span data-stu-id="6211e-143">about_PowerShell.exe</span></span>](about_PowerShell_exe.md)

[<span data-ttu-id="6211e-144">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="6211e-144">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)

[<span data-ttu-id="6211e-145">Windows PowerShell 集成脚本环境 (ISE)</span><span class="sxs-lookup"><span data-stu-id="6211e-145">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>](/powershell/scripting/windows-powershell/ise/introducing-the-windows-powershell-ise)
