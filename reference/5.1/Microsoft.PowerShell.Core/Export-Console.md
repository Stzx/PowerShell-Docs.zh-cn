---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197445"
---
# <span data-ttu-id="b6ee0-103">Export-Console</span><span class="sxs-lookup"><span data-stu-id="b6ee0-103">Export-Console</span></span>

## <span data-ttu-id="b6ee0-104">摘要</span><span class="sxs-lookup"><span data-stu-id="b6ee0-104">SYNOPSIS</span></span>
<span data-ttu-id="b6ee0-105">将当前会话中的管理单元的名称导出到控制台文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-105">Exports the names of snap-ins in the current session to a console file.</span></span>

## <span data-ttu-id="b6ee0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b6ee0-106">SYNTAX</span></span>

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="b6ee0-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b6ee0-107">DESCRIPTION</span></span>
<span data-ttu-id="b6ee0-108">**导出控制台** cmdlet 将当前会话中的 windows powershell 管理单元的名称导出到 ( 的 windows powershell 控制台文件。 .psc1) 。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-108">The **Export-Console** cmdlet exports the names of the Windows PowerShell snap-ins in the current session to a Windows PowerShell console file (.psc1).</span></span>
<span data-ttu-id="b6ee0-109">可以使用此 cmdlet 来保存管理单元，以供在以后的会话中使用。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-109">You can use this cmdlet to save the snap-ins for use in future sessions.</span></span>

<span data-ttu-id="b6ee0-110">若要将 .psc1 控制台文件中的管理单元添加到会话中，请使用 Cmd.exe 或其他 Windows PowerShell 会话在命令行上启动 Windows PowerShell ( # A0) ，然后使用 Powershell.exe 的 *PSConsoleFile* 参数指定控制台文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-110">To add the snap-ins in the .psc1 console file to a session, start Windows PowerShell (Powershell.exe) at the command line by using Cmd.exe or another Windows PowerShell session, and then use the *PSConsoleFile* parameter of Powershell.exe to specify the console file.</span></span>

<span data-ttu-id="b6ee0-111">有关 Windows PowerShell 管理单元的详细信息，请参阅 about_PSSnapins。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-111">For more information about Windows PowerShell snap-ins, see about_PSSnapins.</span></span>

## <span data-ttu-id="b6ee0-112">示例</span><span class="sxs-lookup"><span data-stu-id="b6ee0-112">EXAMPLES</span></span>

### <span data-ttu-id="b6ee0-113">示例1：导出当前会话中的管理单元的名称</span><span class="sxs-lookup"><span data-stu-id="b6ee0-113">Example 1: Export the names of snap-ins in the current session</span></span>

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

<span data-ttu-id="b6ee0-114">此命令将当前会话中的 Windows PowerShell 管理单元的名称导出到 Windows PowerShell 安装文件夹的控制台文件夹中的 Consoles1.psc1 .psc1 文件，$pshome。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-114">This command exports the names of Windows PowerShell snap-ins in the current session to the ConsoleS1.psc1 file in the Consoles folder of the Windows PowerShell installation folder, $pshome.</span></span>

### <span data-ttu-id="b6ee0-115">示例2：将管理单元的名称导出到最近的控制台文件</span><span class="sxs-lookup"><span data-stu-id="b6ee0-115">Example 2: Export the names of snap-ins to the most recent console file</span></span>

```
PS C:\> Export-Console
```

<span data-ttu-id="b6ee0-116">此命令将当前会话中的 Windows PowerShell 管理单元的名称导出到最近在当前会话中使用的 Windows PowerShell 控制台文件中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-116">This command exports the names of Windows PowerShell snap-ins from current session to the Windows PowerShell console file that was most recently used in the current session.</span></span>
<span data-ttu-id="b6ee0-117">它会覆盖以前的文件内容。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-117">It overwrites the previous file contents.</span></span>

<span data-ttu-id="b6ee0-118">如果你尚未在当前会话期间导出控制台文件，则系统将提示你需要相应权限才能继续操作，然后提示你输入文件名。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-118">If you have not exported a console file during the current session, you are prompted for permission to continue and then prompted for a file name.</span></span>

### <span data-ttu-id="b6ee0-119">示例3：添加管理单元并导出管理单元的名称</span><span class="sxs-lookup"><span data-stu-id="b6ee0-119">Example 3: Add a snap-in and export the names of snap-ins</span></span>

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

<span data-ttu-id="b6ee0-120">这些命令将 NewPSSnapin Windows PowerShell 管理单元添加到当前会话中、将当前会话中的 Windows PowerShell 管理单元的名称导出到控制台文件中，然后使用该控制台文件启动 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-120">These commands add the NewPSSnapin Windows PowerShell snap-in to the current session, export the names of Windows PowerShell snap-ins in the current session to a console file, and then start a Windows PowerShell session with the console file.</span></span>

<span data-ttu-id="b6ee0-121">第一个命令使用 **add-pssnapin** Cmdlet 将 NewPSSnapin 管理单元添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-121">The first command uses the **Add-PSSnapin** cmdlet to add the NewPSSnapin snap-in to the current session.</span></span>
<span data-ttu-id="b6ee0-122">你可以仅添加已在你的系统上注册的 Windows PowerShell 管理单元。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-122">You can only add Windows PowerShell snap-ins that are registered on your system.</span></span>

<span data-ttu-id="b6ee0-123">第二个命令将 Windows PowerShell 管理单元名称导出到 NewPSSnapinConsole.psc1 文件中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-123">The second command exports the Windows PowerShell snap-in names to the NewPSSnapinConsole.psc1 file.</span></span>

<span data-ttu-id="b6ee0-124">第三个命令使用 NewPSSnapinConsole.psc1 文件启动 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-124">The third command starts Windows PowerShell with the NewPSSnapinConsole.psc1 file.</span></span>
<span data-ttu-id="b6ee0-125">因为该控制台文件包含 Windows PowerShell 管理单元名称，所以该管理单元中的 cmdlet 和提供程序在当前会话中可用。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-125">Because the console file includes the Windows PowerShell snap-in name, the cmdlets and providers in the snap-in are available in the current session.</span></span>

### <span data-ttu-id="b6ee0-126">示例4：将管理单元的名称导出到指定位置</span><span class="sxs-lookup"><span data-stu-id="b6ee0-126">Example 4: Export names of snap-ins to a specified location</span></span>

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

<span data-ttu-id="b6ee0-127">此命令会将当前会话中的 Windows PowerShell 管理单元的名称导出到当前目录下的 Console01.psc1 文件中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-127">This command exports the names of the Windows PowerShell snap-ins in the current session to the Console01.psc1 file in the current directory.</span></span>

<span data-ttu-id="b6ee0-128">第二个命令将在记事本中显示 Console01.psc1 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-128">The second command displays the contents of the Console01.psc1 file in Notepad.</span></span>

### <span data-ttu-id="b6ee0-129">示例5：确定要更新的控制台文件</span><span class="sxs-lookup"><span data-stu-id="b6ee0-129">Example 5: Determine the console file to update</span></span>

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

<span data-ttu-id="b6ee0-130">此示例演示如何使用 $ConsoleFileName 自动变量来确定在使用不带 *Path* 参数值的 **导出** 时将更新的控制台文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-130">This example shows how to use the $ConsoleFileName automatic variable to determine the console file that will be updated if you use **Export-Console** without a *Path* parameter value.</span></span>

<span data-ttu-id="b6ee0-131">第一个命令使用 PowerShell.exe 的 *PSConsoleFile* 参数来打开包含 .psc1 文件的 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-131">The first command uses the *PSConsoleFile* parameter of PowerShell.exe to open Windows PowerShell with the Console01.psc1 file.</span></span>

<span data-ttu-id="b6ee0-132">第二个命令使用 **add-pssnapin** Cmdlet 将 MySnapin Windows PowerShell 管理单元添加到当前会话中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-132">The second command uses the **Add-PSSnapin** cmdlet to add the MySnapin Windows PowerShell snap-in to the current session.</span></span>

<span data-ttu-id="b6ee0-133">第三个命令使用 **export-Console** cmdlet 将会话中的所有 Windows PowerShell 管理单元的名称导出到 newconsole.psc1. .psc1 文件中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-133">The third command uses the **Export-Console** cmdlet to export the names of all the Windows PowerShell snap-ins in the session to the NewConsole.psc1 file.</span></span>

<span data-ttu-id="b6ee0-134">第四个命令显示 $ConsoleFileName 变量。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-134">The fourth command displays the $ConsoleFileName variable.</span></span>
<span data-ttu-id="b6ee0-135">它包含最近使用过的控制台文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-135">It contains the most recently used console file.</span></span>
<span data-ttu-id="b6ee0-136">示例输出显示 NewConsole.ps1 是最近使用的文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-136">The sample output shows that NewConsole.ps1 is the most recently used file.</span></span>

<span data-ttu-id="b6ee0-137">第五个命令将 SnapIn03 添加到当前控制台中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-137">The fifth command adds SnapIn03 to the current console.</span></span>

<span data-ttu-id="b6ee0-138">第六个命令使用不带 *Path* 参数的 **导出控制台** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-138">The sixth command uses the **Export-Console** cmdlet without a *Path* parameter.</span></span>
<span data-ttu-id="b6ee0-139">此命令会将当前会话中的所有 Windows PowerShell 管理单元的名称导出到最近使用的文件 NewConsole.psc1 中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-139">This command exports the names of all the Windows PowerShell snap-ins in the current session to the most recently used file, NewConsole.psc1.</span></span>

## <span data-ttu-id="b6ee0-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b6ee0-140">PARAMETERS</span></span>

### <span data-ttu-id="b6ee0-141">-Force</span><span class="sxs-lookup"><span data-stu-id="b6ee0-141">-Force</span></span>
<span data-ttu-id="b6ee0-142">指示此 cmdlet 将在不发出警告的情况下覆盖控制台文件中的数据，即使该文件具有只读属性也是如此。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-142">Indicates that this cmdlet overwrites the data in a console file without warning, even if the file has the read-only attribute.</span></span>
<span data-ttu-id="b6ee0-143">只读属性已更改，并且在命令完成时不会重置。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-143">The read-only attribute is changed and is not reset when the command finishes.</span></span>

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

### <span data-ttu-id="b6ee0-144">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="b6ee0-144">-NoClobber</span></span>
<span data-ttu-id="b6ee0-145">指示此 cmdlet 不会覆盖现有的控制台文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-145">Indicates that this cmdlet does not overwrite  an existing console file.</span></span>
<span data-ttu-id="b6ee0-146">默认情况下，如果文件出现在指定的路径中，则 **导出控制台** 将覆盖文件而不发出警告。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-146">By default, if a file occurs in the specified path, **Export-Console** overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b6ee0-147">-Path</span><span class="sxs-lookup"><span data-stu-id="b6ee0-147">-Path</span></span>
<span data-ttu-id="b6ee0-148">指定控制台文件 (\*.psc1） 的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-148">Specifies a path and file name for the console file (\*.psc1).</span></span>
<span data-ttu-id="b6ee0-149">输入可选的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-149">Enter an optional path and name.</span></span>
<span data-ttu-id="b6ee0-150">不允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-150">Wildcard characters are not permitted.</span></span>

<span data-ttu-id="b6ee0-151">如果仅指定文件名，则 **导出控制台** 将在当前目录中创建一个具有该名称的文件和一个 .psc1 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-151">If you specify only a file name, **Export-Console** creates a file that has that name and the .psc1 file name extension in the current directory.</span></span>

<span data-ttu-id="b6ee0-152">除非你已使用 *PSConsoleFile* 参数打开 Windows PowerShell 或在当前会话期间导出了控制台文件，否则此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-152">This parameter is required unless you have opened Windows PowerShell with the *PSConsoleFile* parameter or exported a console file during the current session.</span></span>
<span data-ttu-id="b6ee0-153">当你使用 *NoClobber* 参数以防止覆盖当前控制台文件时，也需要使用该参数。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-153">It is also required when you use the *NoClobber* parameter to prevent the current console file from being overwritten.</span></span>

<span data-ttu-id="b6ee0-154">如果省略此参数，则 **导出控制台** 将覆盖最近在此会话中使用的控制台文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-154">If you omit this parameter, **Export-Console** overwrites the console file that was used most recently in this session.</span></span>
<span data-ttu-id="b6ee0-155">最近使用的控制台文件的路径存储在 $ConsoleFileName 自动变量的值中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-155">The path of the most recently used console file is stored in the value of the $ConsoleFileName automatic variable.</span></span>
<span data-ttu-id="b6ee0-156">有关详细信息，请参阅 about_Automatic_Variables。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-156">For more information, see about_Automatic_Variables.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b6ee0-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b6ee0-157">-Confirm</span></span>
<span data-ttu-id="b6ee0-158">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-158">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="b6ee0-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b6ee0-159">-WhatIf</span></span>
<span data-ttu-id="b6ee0-160">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="b6ee0-161">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-161">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="b6ee0-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b6ee0-162">CommonParameters</span></span>
<span data-ttu-id="b6ee0-163">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b6ee0-164">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b6ee0-165">输入</span><span class="sxs-lookup"><span data-stu-id="b6ee0-165">INPUTS</span></span>

### <span data-ttu-id="b6ee0-166">System.String</span><span class="sxs-lookup"><span data-stu-id="b6ee0-166">System.String</span></span>
<span data-ttu-id="b6ee0-167">可以通过管道将路径字符串传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-167">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="b6ee0-168">输出</span><span class="sxs-lookup"><span data-stu-id="b6ee0-168">OUTPUTS</span></span>

### <span data-ttu-id="b6ee0-169">System.IO.FileInfo</span><span class="sxs-lookup"><span data-stu-id="b6ee0-169">System.IO.FileInfo</span></span>
<span data-ttu-id="b6ee0-170">此 cmdlet 将创建一个包含导出的别名的文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-170">This cmdlet creates a file that contains the exported aliases.</span></span>

## <span data-ttu-id="b6ee0-171">注释</span><span class="sxs-lookup"><span data-stu-id="b6ee0-171">NOTES</span></span>

* <span data-ttu-id="b6ee0-172">当控制台文件 (.psc1) 用于启动会话时，该控制台文件的名称会自动存储在 $ConsoleFileName 自动变量中。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-172">When a console file (.psc1) is used to start the session, the name of the console file is automatically stored in the $ConsoleFileName automatic variable.</span></span> <span data-ttu-id="b6ee0-173">当你使用 **Export** 的 *Path* 参数指定一个新的控制台文件时，将更新 $ConsoleFileName 的值。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-173">The value of $ConsoleFileName is updated when you use the *Path* parameter of **Export-Console** to specify a new console file.</span></span> <span data-ttu-id="b6ee0-174">当没有使用控制台文件时，$ConsoleFileName ($Null) 没有值。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-174">When no console file is used, $ConsoleFileName has no value ($Null).</span></span>

  <span data-ttu-id="b6ee0-175">若要在新会话中使用 Windows PowerShell 控制台文件，请使用以下语法来启动 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="b6ee0-175">To use a Windows PowerShell console file in a new session, use the following syntax to start Windows PowerShell:</span></span>

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  <span data-ttu-id="b6ee0-176">还可以通过将 Add-PSSnapin 命令添加到你的 Windows PowerShell 配置文件中，来保存 Windows PowerShell 管理单元，以供以后的会话使用。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-176">You can also save Windows PowerShell snap-ins for future sessions by adding an Add-PSSnapin command to your Windows PowerShell profile.</span></span>
<span data-ttu-id="b6ee0-177">有关详细信息，请参阅 about_Profiles。</span><span class="sxs-lookup"><span data-stu-id="b6ee0-177">For more information, see about_Profiles.</span></span>


## <span data-ttu-id="b6ee0-178">相关链接</span><span class="sxs-lookup"><span data-stu-id="b6ee0-178">RELATED LINKS</span></span>

[<span data-ttu-id="b6ee0-179">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b6ee0-179">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="b6ee0-180">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b6ee0-180">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="b6ee0-181">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="b6ee0-181">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
