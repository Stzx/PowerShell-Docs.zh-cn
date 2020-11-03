---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: 50a7dba8c4e9cb1cfabd42f39e9fdfb43f22f9b1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93197331"
---
# <span data-ttu-id="f4e7b-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-103">New-Item</span></span>

## <span data-ttu-id="f4e7b-104">摘要</span><span class="sxs-lookup"><span data-stu-id="f4e7b-104">SYNOPSIS</span></span>
<span data-ttu-id="f4e7b-105">创建新项。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-105">Creates a new item.</span></span>

## <span data-ttu-id="f4e7b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f4e7b-106">SYNTAX</span></span>

### <span data-ttu-id="f4e7b-107">pathSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="f4e7b-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="f4e7b-108">nameSet</span><span class="sxs-lookup"><span data-stu-id="f4e7b-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f4e7b-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f4e7b-109">DESCRIPTION</span></span>

<span data-ttu-id="f4e7b-110">`New-Item`Cmdlet 将创建新项并设置其值。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="f4e7b-111">可以创建的项的类型取决于项的位置。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="f4e7b-112">例如，在文件系统中 `New-Item` 创建文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="f4e7b-113">在注册表中 `New-Item` 创建注册表项和条目。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="f4e7b-114">`New-Item` 还可以设置它创建的项的值。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="f4e7b-115">例如，在创建新文件时， `New-Item` 可以将初始内容添加到文件中。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="f4e7b-116">示例</span><span class="sxs-lookup"><span data-stu-id="f4e7b-116">EXAMPLES</span></span>

### <span data-ttu-id="f4e7b-117">示例1：在当前目录中创建文件</span><span class="sxs-lookup"><span data-stu-id="f4e7b-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="f4e7b-118">此命令将在当前目录中创建一个名为 "testfile1.txt" 的文本文件。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="f4e7b-119">点 ( "." **Path** 参数的值中的 ) 指示当前目录。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="f4e7b-120">在 **值** 参数之后的带引号文本将作为内容添加到文件中。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="f4e7b-121">示例2：创建目录</span><span class="sxs-lookup"><span data-stu-id="f4e7b-121">Example 2: Create a directory</span></span>

<span data-ttu-id="f4e7b-122">此命令在驱动器中创建一个名为 "日志" 的目录 `C:` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="f4e7b-123">**ItemType** 参数指定新项是目录，而不是文件或其他文件系统对象。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="f4e7b-124">示例3：创建配置文件</span><span class="sxs-lookup"><span data-stu-id="f4e7b-124">Example 3: Create a profile</span></span>

<span data-ttu-id="f4e7b-125">此命令在由变量指定的路径中创建 PowerShell 配置文件 `$profile` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="f4e7b-126">可以使用配置文件自定义 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="f4e7b-127">`$profile` 是一个自动 (内置) 变量，用于存储 "CurrentUser/CurrentHost" 配置文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="f4e7b-128">默认情况下，配置文件不存在，即使 PowerShell 为其存储路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="f4e7b-129">在此命令中， `$profile` 变量表示文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="f4e7b-130">**ItemType** 参数指定该命令创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="f4e7b-131">**Force** 参数允许你在配置文件路径中创建文件，即使路径中的目录不存在也是如此。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="f4e7b-132">创建配置文件后，可以在配置文件中输入别名、函数和脚本来自定义 shell。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="f4e7b-133">有关详细信息，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 和 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### <span data-ttu-id="f4e7b-134">示例4：在不同的目录中创建目录</span><span class="sxs-lookup"><span data-stu-id="f4e7b-134">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="f4e7b-135">此示例将在 "C:\PS-Test" 目录中创建新的 Scripts 目录。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-135">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="f4e7b-136">新目录项的名称 "Scripts" 包含在 **Path** 参数的值中，而不是在 **名称** 的值中指定。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-136">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="f4e7b-137">根据语法，任一种命令形式都是有效的。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-137">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="f4e7b-138">示例5：创建多个文件</span><span class="sxs-lookup"><span data-stu-id="f4e7b-138">Example 5: Create multiple files</span></span>

<span data-ttu-id="f4e7b-139">此示例在两个不同的目录中创建文件。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-139">This example creates files in two different directories.</span></span> <span data-ttu-id="f4e7b-140">由于 **路径** 采用多个字符串，因此可以使用它来创建多个项。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-140">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="f4e7b-141">示例6：使用通配符在多个目录中创建文件</span><span class="sxs-lookup"><span data-stu-id="f4e7b-141">Example 6: Use wildcards to create files in multiple directories</span></span>

<span data-ttu-id="f4e7b-142">`New-Item`Cmdlet 支持 **Path** 参数中的通配符。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-142">The `New-Item` cmdlet supports wildcards in the **Path** parameter.</span></span> <span data-ttu-id="f4e7b-143">以下命令 `temp.txt` 在 **Path** 参数中由通配符指定的所有目录中创建文件。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-143">The following command creates a `temp.txt` file in all of the directories specified by the wildcards in the **Path** parameter.</span></span>

```powershell
Get-ChildItem -Path C:\Temp\
```

```Output
    Directory:  C:\Temp

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
d-----        5/15/2019   6:45 AM        1   One
d-----        5/15/2019   6:45 AM        1   Two
d-----        5/15/2019   6:45 AM        1   Three
```

```powershell
New-Item -Path * -Name temp.txt -ItemType File | Select-Object FullName
```

```Output
FullName
--------
C:\Temp\One\temp.txt
C:\Temp\Three\temp.txt
C:\Temp\Two\temp.txt
```

<span data-ttu-id="f4e7b-144">`Get-ChildItem`Cmdlet 在目录下显示三个目录 `C:\Temp` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-144">The `Get-ChildItem` cmdlet shows three directories under the `C:\Temp` directory.</span></span> <span data-ttu-id="f4e7b-145">使用通配符 `New-Item` cmdlet 会 `temp.txt` 在当前目录下的所有目录中创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-145">Using wildcards the `New-Item` cmdlet creates a `temp.txt` file in all of the directories under the current directory.</span></span> <span data-ttu-id="f4e7b-146">该 `New-Item` cmdlet 将输出您创建的项目，该项目将通过管道传递到， `Select-Object` 以验证新创建的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-146">The `New-Item` cmdlet outputs the items you created, which is piped to `Select-Object` to verify the paths of the newly created files.</span></span>

### <span data-ttu-id="f4e7b-147">示例7：创建指向文件或文件夹的符号链接</span><span class="sxs-lookup"><span data-stu-id="f4e7b-147">Example 7: Create a symbolic link to a file or folder</span></span>

<span data-ttu-id="f4e7b-148">此示例将创建指向当前文件夹中 Notice.txt 文件的符号链接。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-148">This example creates a symbolic link to the Notice.txt file in the current folder.</span></span>

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

<span data-ttu-id="f4e7b-149">在此示例中， **Target** 是 **Value** 参数的别名。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-149">In this example, **Target** is an alias for the **Value** parameter.</span></span> <span data-ttu-id="f4e7b-150">符号链接的目标可以是相对路径。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-150">The target of the symbolic link can be a relative path.</span></span> <span data-ttu-id="f4e7b-151">在 PowerShell 6.2 之前，目标必须是完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-151">Prior to PowerShell v6.2, the target must be a fully-qualified path.</span></span>

<span data-ttu-id="f4e7b-152">从 PowerShell 7.1 开始，现在可以使用相对路径在 Windows 上的文件夹中创建 **SymbolicLink** 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-152">Beginning in PowerShell 7.1, you can now create to a **SymbolicLink** to a folder on Windows using a relative path.</span></span>

### <span data-ttu-id="f4e7b-153">示例8：使用-Force 参数尝试重新创建文件夹</span><span class="sxs-lookup"><span data-stu-id="f4e7b-153">Example 8: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="f4e7b-154">此示例创建一个文件夹，其中包含中的文件。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-154">This example creates a folder with a file inside.</span></span> <span data-ttu-id="f4e7b-155">然后，尝试使用创建相同的文件夹 `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-155">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="f4e7b-156">它不会覆盖文件夹，只需返回现有的文件夹对象，文件创建的文件也会原封不动。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-156">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

```powershell
PS> New-Item -Path .\TestFolder -ItemType Directory
PS> New-Item -Path .\TestFolder\TestFile.txt -ItemType File

PS> New-Item -Path .\TestFolder -ItemType Directory -Force

    Directory: C:\
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----         5/1/2020   8:03 AM                TestFolder

PS> Get-ChildItem .\TestFolder\

    Directory: C:\TestFolder
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:03 AM              0 TestFile.txt
```

### <span data-ttu-id="f4e7b-157">示例9：使用-Force 参数覆盖现有文件</span><span class="sxs-lookup"><span data-stu-id="f4e7b-157">Example 9: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="f4e7b-158">此示例创建一个具有值的文件，然后使用重新创建该文件 `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-158">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="f4e7b-159">这将覆盖现有文件，并且它将丢失其内容，正如您可以看到的 "长度" 属性所示</span><span class="sxs-lookup"><span data-stu-id="f4e7b-159">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

```powershell
PS> New-Item ./TestFile.txt -ItemType File -Value 'This is just a test file'

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM             24 TestFile.txt

New-Item ./TestFile.txt -ItemType File -Force

    Directory: C:\Source\Test
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         5/1/2020   8:32 AM              0 TestFile.txt
```

> [!NOTE]
> <span data-ttu-id="f4e7b-160">当使用 `New-Item` 带有 `-Force` 开关的来创建注册表项时，该命令的行为与覆盖文件时的行为相同。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-160">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="f4e7b-161">如果注册表项已存在，则将使用空的注册表项覆盖该项和所有属性和值。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-161">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="f4e7b-162">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f4e7b-162">PARAMETERS</span></span>

### <span data-ttu-id="f4e7b-163">-Credential</span><span class="sxs-lookup"><span data-stu-id="f4e7b-163">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="f4e7b-164">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-164">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="f4e7b-165">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-165">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f4e7b-166">-Force</span><span class="sxs-lookup"><span data-stu-id="f4e7b-166">-Force</span></span>

<span data-ttu-id="f4e7b-167">强制此 cmdlet 创建一个写入现有只读项的项。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-167">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="f4e7b-168">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-168">Implementation varies from provider to provider.</span></span> <span data-ttu-id="f4e7b-169">即使使用 **Force** 参数，该 cmdlet 也无法覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-169">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="f4e7b-170">-ItemType</span><span class="sxs-lookup"><span data-stu-id="f4e7b-170">-ItemType</span></span>

<span data-ttu-id="f4e7b-171">指定提供程序指定的新项的类型。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-171">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="f4e7b-172">此参数的可用值取决于当前使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-172">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="f4e7b-173">如果位置在 `FileSystem` 驱动器中，则允许以下值：</span><span class="sxs-lookup"><span data-stu-id="f4e7b-173">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="f4e7b-174">文件</span><span class="sxs-lookup"><span data-stu-id="f4e7b-174">File</span></span>
- <span data-ttu-id="f4e7b-175">Directory</span><span class="sxs-lookup"><span data-stu-id="f4e7b-175">Directory</span></span>
- <span data-ttu-id="f4e7b-176">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="f4e7b-176">SymbolicLink</span></span>
- <span data-ttu-id="f4e7b-177">交接点</span><span class="sxs-lookup"><span data-stu-id="f4e7b-177">Junction</span></span>
- <span data-ttu-id="f4e7b-178">硬</span><span class="sxs-lookup"><span data-stu-id="f4e7b-178">HardLink</span></span>

> [!NOTE]
> <span data-ttu-id="f4e7b-179">`SymbolicLink`在 Windows 上创建类型要求提升为管理员。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-179">Creating a `SymbolicLink` type on Windows requires elevation as administrator.</span></span> <span data-ttu-id="f4e7b-180">但是，启用开发人员模式的 Windows 10 (生成14972或) 更高版本将不再需要提升创建符号链接。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-180">However, Windows 10 (build 14972 or newer) with Developer Mode enabled no longer requires elevation creating symbolic links.</span></span>

<span data-ttu-id="f4e7b-181">在 `Certificate` 驱动器中，可以指定以下值：</span><span class="sxs-lookup"><span data-stu-id="f4e7b-181">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="f4e7b-182">Certificate 提供程序</span><span class="sxs-lookup"><span data-stu-id="f4e7b-182">Certificate Provider</span></span>
- <span data-ttu-id="f4e7b-183">证书</span><span class="sxs-lookup"><span data-stu-id="f4e7b-183">Certificate</span></span>
- <span data-ttu-id="f4e7b-184">应用商店</span><span class="sxs-lookup"><span data-stu-id="f4e7b-184">Store</span></span>
- <span data-ttu-id="f4e7b-185">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="f4e7b-185">StoreLocation</span></span>

<span data-ttu-id="f4e7b-186">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-186">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Type

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f4e7b-187">-Name</span><span class="sxs-lookup"><span data-stu-id="f4e7b-187">-Name</span></span>

<span data-ttu-id="f4e7b-188">指定新项的名称。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-188">Specifies the name of the new item.</span></span> <span data-ttu-id="f4e7b-189">您可以在 **name** 或 **path** 参数值中指定新项的名称，并且可以在 " **名称** " 或 " **路径** " 值中指定新项的路径。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-189">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="f4e7b-190">使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-190">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: nameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f4e7b-191">-Path</span><span class="sxs-lookup"><span data-stu-id="f4e7b-191">-Path</span></span>

<span data-ttu-id="f4e7b-192">指定新项的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-192">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="f4e7b-193">如果省略 **路径** ，则默认值为当前位置。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-193">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="f4e7b-194">可以在 " **名称** " 中指定新项的名称，也可以将其包含在 " **路径** " 中。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-194">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="f4e7b-195">使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-195">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="f4e7b-196">对于此 cmdlet， **路径** 参数的工作方式类似于其他 Cmdlet 的 **LiteralPath** 参数。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-196">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="f4e7b-197">不解释通配符。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-197">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="f4e7b-198">所有字符将传递到位置的提供程序。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-198">All characters are passed to the location's provider.</span></span> <span data-ttu-id="f4e7b-199">提供程序可能不支持所有字符。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-199">The provider may not support all characters.</span></span> <span data-ttu-id="f4e7b-200">例如，你不能创建包含星号 () 字符的文件名 `*` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-200">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f4e7b-201">-Value</span><span class="sxs-lookup"><span data-stu-id="f4e7b-201">-Value</span></span>

<span data-ttu-id="f4e7b-202">指定新项的值。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-202">Specifies the value of the new item.</span></span> <span data-ttu-id="f4e7b-203">还可以通过管道将值传递给 `New-Item` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-203">You can also pipe a value to `New-Item`.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Target

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f4e7b-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f4e7b-204">-Confirm</span></span>

<span data-ttu-id="f4e7b-205">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-205">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f4e7b-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f4e7b-206">-WhatIf</span></span>

<span data-ttu-id="f4e7b-207">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f4e7b-208">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-208">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f4e7b-209">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f4e7b-209">CommonParameters</span></span>

<span data-ttu-id="f4e7b-210">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-210">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="f4e7b-211">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-211">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="f4e7b-212">输入</span><span class="sxs-lookup"><span data-stu-id="f4e7b-212">INPUTS</span></span>

### <span data-ttu-id="f4e7b-213">System.Object</span><span class="sxs-lookup"><span data-stu-id="f4e7b-213">System.Object</span></span>

<span data-ttu-id="f4e7b-214">可以通过管道将新项的值传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-214">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="f4e7b-215">输出</span><span class="sxs-lookup"><span data-stu-id="f4e7b-215">OUTPUTS</span></span>

### <span data-ttu-id="f4e7b-216">System.Object</span><span class="sxs-lookup"><span data-stu-id="f4e7b-216">System.Object</span></span>

<span data-ttu-id="f4e7b-217">此 cmdlet 将返回它创建的项。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-217">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="f4e7b-218">注释</span><span class="sxs-lookup"><span data-stu-id="f4e7b-218">NOTES</span></span>

<span data-ttu-id="f4e7b-219">`New-Item` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-219">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="f4e7b-220">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-220">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="f4e7b-221">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="f4e7b-221">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="f4e7b-222">相关链接</span><span class="sxs-lookup"><span data-stu-id="f4e7b-222">RELATED LINKS</span></span>

[<span data-ttu-id="f4e7b-223">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-223">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="f4e7b-224">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-224">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="f4e7b-225">Get-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-225">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="f4e7b-226">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-226">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="f4e7b-227">Move-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-227">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="f4e7b-228">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-228">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="f4e7b-229">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-229">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="f4e7b-230">Set-Item</span><span class="sxs-lookup"><span data-stu-id="f4e7b-230">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="f4e7b-231">about_Providers</span><span class="sxs-lookup"><span data-stu-id="f4e7b-231">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

