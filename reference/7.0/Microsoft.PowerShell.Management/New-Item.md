---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: f24988833faaf56395b95e08430bbcc9fb6d2746
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "93197173"
---
# <span data-ttu-id="c516d-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-103">New-Item</span></span>

## <span data-ttu-id="c516d-104">摘要</span><span class="sxs-lookup"><span data-stu-id="c516d-104">SYNOPSIS</span></span>
<span data-ttu-id="c516d-105">创建新项。</span><span class="sxs-lookup"><span data-stu-id="c516d-105">Creates a new item.</span></span>

## <span data-ttu-id="c516d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c516d-106">SYNTAX</span></span>

### <span data-ttu-id="c516d-107">pathSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="c516d-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c516d-108">nameSet</span><span class="sxs-lookup"><span data-stu-id="c516d-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c516d-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c516d-109">DESCRIPTION</span></span>

<span data-ttu-id="c516d-110">`New-Item`Cmdlet 将创建新项并设置其值。</span><span class="sxs-lookup"><span data-stu-id="c516d-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="c516d-111">可以创建的项的类型取决于项的位置。</span><span class="sxs-lookup"><span data-stu-id="c516d-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="c516d-112">例如，在文件系统中 `New-Item` 创建文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="c516d-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="c516d-113">在注册表中 `New-Item` 创建注册表项和条目。</span><span class="sxs-lookup"><span data-stu-id="c516d-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="c516d-114">`New-Item` 还可以设置它创建的项的值。</span><span class="sxs-lookup"><span data-stu-id="c516d-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="c516d-115">例如，在创建新文件时， `New-Item` 可以将初始内容添加到文件中。</span><span class="sxs-lookup"><span data-stu-id="c516d-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="c516d-116">示例</span><span class="sxs-lookup"><span data-stu-id="c516d-116">EXAMPLES</span></span>

### <span data-ttu-id="c516d-117">示例1：在当前目录中创建文件</span><span class="sxs-lookup"><span data-stu-id="c516d-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="c516d-118">此命令将在当前目录中创建一个名为 "testfile1.txt" 的文本文件。</span><span class="sxs-lookup"><span data-stu-id="c516d-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="c516d-119">点 ( "." **Path** 参数的值中的 ) 指示当前目录。</span><span class="sxs-lookup"><span data-stu-id="c516d-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="c516d-120">在 **值** 参数之后的带引号文本将作为内容添加到文件中。</span><span class="sxs-lookup"><span data-stu-id="c516d-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="c516d-121">示例2：创建目录</span><span class="sxs-lookup"><span data-stu-id="c516d-121">Example 2: Create a directory</span></span>

<span data-ttu-id="c516d-122">此命令在驱动器中创建一个名为 "日志" 的目录 `C:` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="c516d-123">**ItemType** 参数指定新项是目录，而不是文件或其他文件系统对象。</span><span class="sxs-lookup"><span data-stu-id="c516d-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="c516d-124">示例3：创建配置文件</span><span class="sxs-lookup"><span data-stu-id="c516d-124">Example 3: Create a profile</span></span>

<span data-ttu-id="c516d-125">此命令在由变量指定的路径中创建 PowerShell 配置文件 `$profile` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="c516d-126">可以使用配置文件自定义 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c516d-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="c516d-127">`$profile` 是一个自动 (内置) 变量，用于存储 "CurrentUser/CurrentHost" 配置文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="c516d-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="c516d-128">默认情况下，配置文件不存在，即使 PowerShell 为其存储路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="c516d-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="c516d-129">在此命令中， `$profile` 变量表示文件的路径。</span><span class="sxs-lookup"><span data-stu-id="c516d-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="c516d-130">**ItemType** 参数指定该命令创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="c516d-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="c516d-131">**Force** 参数允许你在配置文件路径中创建文件，即使路径中的目录不存在也是如此。</span><span class="sxs-lookup"><span data-stu-id="c516d-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="c516d-132">创建配置文件后，可以在配置文件中输入别名、函数和脚本来自定义 shell。</span><span class="sxs-lookup"><span data-stu-id="c516d-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="c516d-133">有关详细信息，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 和 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="c516d-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

### <span data-ttu-id="c516d-134">示例4：在不同的目录中创建目录</span><span class="sxs-lookup"><span data-stu-id="c516d-134">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="c516d-135">此示例将在 "C:\PS-Test" 目录中创建新的 Scripts 目录。</span><span class="sxs-lookup"><span data-stu-id="c516d-135">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="c516d-136">新目录项的名称 "Scripts" 包含在 **Path** 参数的值中，而不是在 **名称** 的值中指定。</span><span class="sxs-lookup"><span data-stu-id="c516d-136">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="c516d-137">根据语法，任一种命令形式都是有效的。</span><span class="sxs-lookup"><span data-stu-id="c516d-137">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="c516d-138">示例5：创建多个文件</span><span class="sxs-lookup"><span data-stu-id="c516d-138">Example 5: Create multiple files</span></span>

<span data-ttu-id="c516d-139">此示例在两个不同的目录中创建文件。</span><span class="sxs-lookup"><span data-stu-id="c516d-139">This example creates files in two different directories.</span></span> <span data-ttu-id="c516d-140">由于 **路径** 采用多个字符串，因此可以使用它来创建多个项。</span><span class="sxs-lookup"><span data-stu-id="c516d-140">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="c516d-141">示例6：使用通配符在多个目录中创建文件</span><span class="sxs-lookup"><span data-stu-id="c516d-141">Example 6: Use wildcards to create files in multiple directories</span></span>

<span data-ttu-id="c516d-142">`New-Item`Cmdlet 支持 **Path** 参数中的通配符。</span><span class="sxs-lookup"><span data-stu-id="c516d-142">The `New-Item` cmdlet supports wildcards in the **Path** parameter.</span></span> <span data-ttu-id="c516d-143">以下命令 `temp.txt` 在 **Path** 参数中由通配符指定的所有目录中创建文件。</span><span class="sxs-lookup"><span data-stu-id="c516d-143">The following command creates a `temp.txt` file in all of the directories specified by the wildcards in the **Path** parameter.</span></span>

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

<span data-ttu-id="c516d-144">`Get-ChildItem`Cmdlet 在目录下显示三个目录 `C:\Temp` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-144">The `Get-ChildItem` cmdlet shows three directories under the `C:\Temp` directory.</span></span> <span data-ttu-id="c516d-145">使用通配符 `New-Item` cmdlet 会 `temp.txt` 在当前目录下的所有目录中创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="c516d-145">Using wildcards the `New-Item` cmdlet creates a `temp.txt` file in all of the directories under the current directory.</span></span> <span data-ttu-id="c516d-146">该 `New-Item` cmdlet 将输出您创建的项目，该项目将通过管道传递到， `Select-Object` 以验证新创建的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="c516d-146">The `New-Item` cmdlet outputs the items you created, which is piped to `Select-Object` to verify the paths of the newly created files.</span></span>

### <span data-ttu-id="c516d-147">示例7：创建指向文件或文件夹的符号链接</span><span class="sxs-lookup"><span data-stu-id="c516d-147">Example 7: Create a symbolic link to a file or folder</span></span>

<span data-ttu-id="c516d-148">此示例将创建指向当前文件夹中 Notice.txt 文件的符号链接。</span><span class="sxs-lookup"><span data-stu-id="c516d-148">This example creates a symbolic link to the Notice.txt file in the current folder.</span></span>

```powershell
$link = New-Item -ItemType SymbolicLink -Path .\link -Target .\Notice.txt
$link | Select-Object LinkType, Target
```

```Output
LinkType     Target
--------     ------
SymbolicLink {.\Notice.txt}
```

<span data-ttu-id="c516d-149">在此示例中， **Target** 是 **Value** 参数的别名。</span><span class="sxs-lookup"><span data-stu-id="c516d-149">In this example, **Target** is an alias for the **Value** parameter.</span></span> <span data-ttu-id="c516d-150">符号链接的目标可以是相对路径。</span><span class="sxs-lookup"><span data-stu-id="c516d-150">The target of the symbolic link can be a relative path.</span></span> <span data-ttu-id="c516d-151">在 PowerShell 6.2 之前，目标必须是完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="c516d-151">Prior to PowerShell v6.2, the target must be a fully-qualified path.</span></span>

> [!CAUTION]
> <span data-ttu-id="c516d-152">如果要在 Windows 上的文件夹中创建 **SymbolicLink** ，则必须使用完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="c516d-152">If you are creating a **SymbolicLink** to a folder on Windows, you must use a fully-qualified path.</span></span> <span data-ttu-id="c516d-153">如果使用相对路径，则会将此链接创建为文件类型链接，而不是目录类型的链接。</span><span class="sxs-lookup"><span data-stu-id="c516d-153">If you use a relative path, the link is created as a file-type link instead of a directory-type link.</span></span>

### <span data-ttu-id="c516d-154">示例8：使用-Force 参数尝试重新创建文件夹</span><span class="sxs-lookup"><span data-stu-id="c516d-154">Example 8: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="c516d-155">此示例创建一个文件夹，其中包含中的文件。</span><span class="sxs-lookup"><span data-stu-id="c516d-155">This example creates a folder with a file inside.</span></span> <span data-ttu-id="c516d-156">然后，尝试使用创建相同的文件夹 `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-156">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="c516d-157">它不会覆盖文件夹，只需返回现有的文件夹对象，文件创建的文件也会原封不动。</span><span class="sxs-lookup"><span data-stu-id="c516d-157">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

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

### <span data-ttu-id="c516d-158">示例9：使用-Force 参数覆盖现有文件</span><span class="sxs-lookup"><span data-stu-id="c516d-158">Example 9: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="c516d-159">此示例创建一个具有值的文件，然后使用重新创建该文件 `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-159">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="c516d-160">这将覆盖现有文件，并且它将丢失其内容，正如您可以看到的 "长度" 属性所示</span><span class="sxs-lookup"><span data-stu-id="c516d-160">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

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
> <span data-ttu-id="c516d-161">当使用 `New-Item` 带有 `-Force` 开关的来创建注册表项时，该命令的行为与覆盖文件时的行为相同。</span><span class="sxs-lookup"><span data-stu-id="c516d-161">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="c516d-162">如果注册表项已存在，则将使用空的注册表项覆盖该项和所有属性和值。</span><span class="sxs-lookup"><span data-stu-id="c516d-162">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="c516d-163">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c516d-163">PARAMETERS</span></span>

### <span data-ttu-id="c516d-164">-Credential</span><span class="sxs-lookup"><span data-stu-id="c516d-164">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c516d-165">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="c516d-165">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="c516d-166">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-166">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="c516d-167">-Force</span><span class="sxs-lookup"><span data-stu-id="c516d-167">-Force</span></span>

<span data-ttu-id="c516d-168">强制此 cmdlet 创建一个写入现有只读项的项。</span><span class="sxs-lookup"><span data-stu-id="c516d-168">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="c516d-169">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="c516d-169">Implementation varies from provider to provider.</span></span> <span data-ttu-id="c516d-170">即使使用 **Force** 参数，该 cmdlet 也无法覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="c516d-170">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="c516d-171">-ItemType</span><span class="sxs-lookup"><span data-stu-id="c516d-171">-ItemType</span></span>

<span data-ttu-id="c516d-172">指定提供程序指定的新项的类型。</span><span class="sxs-lookup"><span data-stu-id="c516d-172">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="c516d-173">此参数的可用值取决于当前使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="c516d-173">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="c516d-174">如果位置在 `FileSystem` 驱动器中，则允许以下值：</span><span class="sxs-lookup"><span data-stu-id="c516d-174">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="c516d-175">文件</span><span class="sxs-lookup"><span data-stu-id="c516d-175">File</span></span>
- <span data-ttu-id="c516d-176">Directory</span><span class="sxs-lookup"><span data-stu-id="c516d-176">Directory</span></span>
- <span data-ttu-id="c516d-177">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="c516d-177">SymbolicLink</span></span>
- <span data-ttu-id="c516d-178">交接点</span><span class="sxs-lookup"><span data-stu-id="c516d-178">Junction</span></span>
- <span data-ttu-id="c516d-179">硬</span><span class="sxs-lookup"><span data-stu-id="c516d-179">HardLink</span></span>

> [!NOTE]
> <span data-ttu-id="c516d-180">`SymbolicLink`在 Windows 上创建类型要求提升为管理员。</span><span class="sxs-lookup"><span data-stu-id="c516d-180">Creating a `SymbolicLink` type on Windows requires elevation as administrator.</span></span> <span data-ttu-id="c516d-181">但是，启用开发人员模式的 Windows 10 (生成14972或) 更高版本将不再需要提升创建符号链接。</span><span class="sxs-lookup"><span data-stu-id="c516d-181">However, Windows 10 (build 14972 or newer) with Developer Mode enabled no longer requires elevation creating symbolic links.</span></span>

<span data-ttu-id="c516d-182">在 `Certificate` 驱动器中，可以指定以下值：</span><span class="sxs-lookup"><span data-stu-id="c516d-182">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="c516d-183">Certificate 提供程序</span><span class="sxs-lookup"><span data-stu-id="c516d-183">Certificate Provider</span></span>
- <span data-ttu-id="c516d-184">证书</span><span class="sxs-lookup"><span data-stu-id="c516d-184">Certificate</span></span>
- <span data-ttu-id="c516d-185">应用商店</span><span class="sxs-lookup"><span data-stu-id="c516d-185">Store</span></span>
- <span data-ttu-id="c516d-186">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="c516d-186">StoreLocation</span></span>

<span data-ttu-id="c516d-187">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="c516d-187">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="c516d-188">-Name</span><span class="sxs-lookup"><span data-stu-id="c516d-188">-Name</span></span>

<span data-ttu-id="c516d-189">指定新项的名称。</span><span class="sxs-lookup"><span data-stu-id="c516d-189">Specifies the name of the new item.</span></span> <span data-ttu-id="c516d-190">您可以在 **name** 或 **path** 参数值中指定新项的名称，并且可以在 " **名称** " 或 " **路径** " 值中指定新项的路径。</span><span class="sxs-lookup"><span data-stu-id="c516d-190">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="c516d-191">使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。</span><span class="sxs-lookup"><span data-stu-id="c516d-191">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="c516d-192">-Path</span><span class="sxs-lookup"><span data-stu-id="c516d-192">-Path</span></span>

<span data-ttu-id="c516d-193">指定新项的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="c516d-193">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="c516d-194">如果省略 **路径** ，则默认值为当前位置。</span><span class="sxs-lookup"><span data-stu-id="c516d-194">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="c516d-195">可以在 " **名称** " 中指定新项的名称，也可以将其包含在 " **路径** " 中。</span><span class="sxs-lookup"><span data-stu-id="c516d-195">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="c516d-196">使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。</span><span class="sxs-lookup"><span data-stu-id="c516d-196">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="c516d-197">对于此 cmdlet， **路径** 参数的工作方式类似于其他 Cmdlet 的 **LiteralPath** 参数。</span><span class="sxs-lookup"><span data-stu-id="c516d-197">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="c516d-198">不解释通配符。</span><span class="sxs-lookup"><span data-stu-id="c516d-198">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="c516d-199">所有字符将传递到位置的提供程序。</span><span class="sxs-lookup"><span data-stu-id="c516d-199">All characters are passed to the location's provider.</span></span> <span data-ttu-id="c516d-200">提供程序可能不支持所有字符。</span><span class="sxs-lookup"><span data-stu-id="c516d-200">The provider may not support all characters.</span></span> <span data-ttu-id="c516d-201">例如，你不能创建包含星号 () 字符的文件名 `*` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-201">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: pathSet, nameSet
Aliases:

Required: True (pathSet), False (nameSet)
Position: 0
Default value: Current location
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c516d-202">-Value</span><span class="sxs-lookup"><span data-stu-id="c516d-202">-Value</span></span>

<span data-ttu-id="c516d-203">指定新项的值。</span><span class="sxs-lookup"><span data-stu-id="c516d-203">Specifies the value of the new item.</span></span> <span data-ttu-id="c516d-204">还可以通过管道将值传递给 `New-Item` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-204">You can also pipe a value to `New-Item`.</span></span>

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

### <span data-ttu-id="c516d-205">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c516d-205">-Confirm</span></span>

<span data-ttu-id="c516d-206">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="c516d-206">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c516d-207">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c516d-207">-WhatIf</span></span>

<span data-ttu-id="c516d-208">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="c516d-208">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c516d-209">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="c516d-209">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c516d-210">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c516d-210">CommonParameters</span></span>

<span data-ttu-id="c516d-211">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="c516d-211">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c516d-212">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="c516d-212">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c516d-213">输入</span><span class="sxs-lookup"><span data-stu-id="c516d-213">INPUTS</span></span>

### <span data-ttu-id="c516d-214">System.Object</span><span class="sxs-lookup"><span data-stu-id="c516d-214">System.Object</span></span>

<span data-ttu-id="c516d-215">可以通过管道将新项的值传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c516d-215">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="c516d-216">输出</span><span class="sxs-lookup"><span data-stu-id="c516d-216">OUTPUTS</span></span>

### <span data-ttu-id="c516d-217">System.Object</span><span class="sxs-lookup"><span data-stu-id="c516d-217">System.Object</span></span>

<span data-ttu-id="c516d-218">此 cmdlet 将返回它创建的项。</span><span class="sxs-lookup"><span data-stu-id="c516d-218">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="c516d-219">注释</span><span class="sxs-lookup"><span data-stu-id="c516d-219">NOTES</span></span>

<span data-ttu-id="c516d-220">`New-Item` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="c516d-220">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="c516d-221">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="c516d-221">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="c516d-222">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="c516d-222">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c516d-223">相关链接</span><span class="sxs-lookup"><span data-stu-id="c516d-223">RELATED LINKS</span></span>

[<span data-ttu-id="c516d-224">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-224">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="c516d-225">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-225">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="c516d-226">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-226">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c516d-227">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-227">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="c516d-228">Move-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-228">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="c516d-229">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-229">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="c516d-230">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-230">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="c516d-231">Set-Item</span><span class="sxs-lookup"><span data-stu-id="c516d-231">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="c516d-232">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c516d-232">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
