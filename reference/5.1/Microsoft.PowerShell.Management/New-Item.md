---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/23/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-item?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Item
ms.openlocfilehash: b1657d369d44d575ee7bed8b76d36224ea2748f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198084"
---
# <span data-ttu-id="e741f-103">New-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-103">New-Item</span></span>

## <span data-ttu-id="e741f-104">摘要</span><span class="sxs-lookup"><span data-stu-id="e741f-104">SYNOPSIS</span></span>
<span data-ttu-id="e741f-105">创建新项。</span><span class="sxs-lookup"><span data-stu-id="e741f-105">Creates a new item.</span></span>

## <span data-ttu-id="e741f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e741f-106">SYNTAX</span></span>

### <span data-ttu-id="e741f-107">pathSet（默认值）</span><span class="sxs-lookup"><span data-stu-id="e741f-107">pathSet (Default)</span></span>

```
New-Item [-Path] <String[]> [-ItemType <String>] [-Value <Object>] [-Force] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="e741f-108">nameSet</span><span class="sxs-lookup"><span data-stu-id="e741f-108">nameSet</span></span>

```
New-Item [[-Path] <String[]>] -Name <String> [-ItemType <String>] [-Value <Object>] [-Force]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="e741f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="e741f-109">DESCRIPTION</span></span>

<span data-ttu-id="e741f-110">`New-Item`Cmdlet 将创建新项并设置其值。</span><span class="sxs-lookup"><span data-stu-id="e741f-110">The `New-Item` cmdlet creates a new item and sets its value.</span></span> <span data-ttu-id="e741f-111">可以创建的项的类型取决于项的位置。</span><span class="sxs-lookup"><span data-stu-id="e741f-111">The types of items that can be created depend on the location of the item.</span></span> <span data-ttu-id="e741f-112">例如，在文件系统中 `New-Item` 创建文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="e741f-112">For example, in the file system, `New-Item` creates files and folders.</span></span> <span data-ttu-id="e741f-113">在注册表中 `New-Item` 创建注册表项和条目。</span><span class="sxs-lookup"><span data-stu-id="e741f-113">In the registry, `New-Item` creates registry keys and entries.</span></span>

<span data-ttu-id="e741f-114">`New-Item` 还可以设置它创建的项的值。</span><span class="sxs-lookup"><span data-stu-id="e741f-114">`New-Item` can also set the value of the items that it creates.</span></span> <span data-ttu-id="e741f-115">例如，在创建新文件时， `New-Item` 可以将初始内容添加到文件中。</span><span class="sxs-lookup"><span data-stu-id="e741f-115">For example, when it creates a new file, `New-Item` can add initial content to the file.</span></span>

## <span data-ttu-id="e741f-116">示例</span><span class="sxs-lookup"><span data-stu-id="e741f-116">EXAMPLES</span></span>

### <span data-ttu-id="e741f-117">示例1：在当前目录中创建文件</span><span class="sxs-lookup"><span data-stu-id="e741f-117">Example 1: Create a file in the current directory</span></span>

<span data-ttu-id="e741f-118">此命令将在当前目录中创建一个名为 "testfile1.txt" 的文本文件。</span><span class="sxs-lookup"><span data-stu-id="e741f-118">This command creates a text file that is named "testfile1.txt" in the current directory.</span></span> <span data-ttu-id="e741f-119">点 ( "." **Path** 参数的值中的 ) 指示当前目录。</span><span class="sxs-lookup"><span data-stu-id="e741f-119">The dot ('.') in the value of the **Path** parameter indicates the current directory.</span></span> <span data-ttu-id="e741f-120">在 **值** 参数之后的带引号文本将作为内容添加到文件中。</span><span class="sxs-lookup"><span data-stu-id="e741f-120">The quoted text that follows the **Value** parameter is added to the file as content.</span></span>

```powershell
New-Item -Path . -Name "testfile1.txt" -ItemType "file" -Value "This is a text string."
```

### <span data-ttu-id="e741f-121">示例2：创建目录</span><span class="sxs-lookup"><span data-stu-id="e741f-121">Example 2: Create a directory</span></span>

<span data-ttu-id="e741f-122">此命令在驱动器中创建一个名为 "日志" 的目录 `C:` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-122">This command creates a directory named "Logfiles" in the `C:` drive.</span></span> <span data-ttu-id="e741f-123">**ItemType** 参数指定新项是目录，而不是文件或其他文件系统对象。</span><span class="sxs-lookup"><span data-stu-id="e741f-123">The **ItemType** parameter specifies that the new item is a directory, not a file or other file system object.</span></span>

```powershell
New-Item -Path "c:\" -Name "logfiles" -ItemType "directory"
```

### <span data-ttu-id="e741f-124">示例3：创建配置文件</span><span class="sxs-lookup"><span data-stu-id="e741f-124">Example 3: Create a profile</span></span>

<span data-ttu-id="e741f-125">此命令在由变量指定的路径中创建 PowerShell 配置文件 `$profile` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-125">This command creates a PowerShell profile in the path that is specified by the `$profile` variable.</span></span>

<span data-ttu-id="e741f-126">可以使用配置文件自定义 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e741f-126">You can use profiles to customize PowerShell.</span></span> <span data-ttu-id="e741f-127">`$profile` 是一个自动 (内置) 变量，用于存储 "CurrentUser/CurrentHost" 配置文件的路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="e741f-127">`$profile` is an automatic (built-in) variable that stores the path and file name of the "CurrentUser/CurrentHost" profile.</span></span> <span data-ttu-id="e741f-128">默认情况下，配置文件不存在，即使 PowerShell 为其存储路径和文件名。</span><span class="sxs-lookup"><span data-stu-id="e741f-128">By default, the profile does not exist, even though PowerShell stores a path and file name for it.</span></span>

<span data-ttu-id="e741f-129">在此命令中， `$profile` 变量表示文件的路径。</span><span class="sxs-lookup"><span data-stu-id="e741f-129">In this command, the `$profile` variable represents the path of the file.</span></span> <span data-ttu-id="e741f-130">**ItemType** 参数指定该命令创建一个文件。</span><span class="sxs-lookup"><span data-stu-id="e741f-130">**ItemType** parameter specifies that the command creates a file.</span></span> <span data-ttu-id="e741f-131">**Force** 参数允许你在配置文件路径中创建文件，即使路径中的目录不存在也是如此。</span><span class="sxs-lookup"><span data-stu-id="e741f-131">The **Force** parameter lets you create a file in the profile path, even when the directories in the path do not exist.</span></span>

<span data-ttu-id="e741f-132">创建配置文件后，可以在配置文件中输入别名、函数和脚本来自定义 shell。</span><span class="sxs-lookup"><span data-stu-id="e741f-132">After you create a profile, you can enter aliases, functions, and scripts in the profile to customize your shell.</span></span>

<span data-ttu-id="e741f-133">有关详细信息，请参阅 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) 和 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="e741f-133">For more information, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md) and [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```powershell
New-Item -Path $profile -ItemType "file" -Force
```

> [!NOTE]
> <span data-ttu-id="e741f-134">使用此方法创建文件时，会将生成的文件编码为 UTF-8，而不会将字节顺序标记 (BOM) 。</span><span class="sxs-lookup"><span data-stu-id="e741f-134">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

### <span data-ttu-id="e741f-135">示例4：在不同的目录中创建目录</span><span class="sxs-lookup"><span data-stu-id="e741f-135">Example 4: Create a directory in a different directory</span></span>

<span data-ttu-id="e741f-136">此示例将在 "C:\PS-Test" 目录中创建新的 Scripts 目录。</span><span class="sxs-lookup"><span data-stu-id="e741f-136">This example creates a new Scripts directory in the "C:\PS-Test" directory.</span></span>

<span data-ttu-id="e741f-137">新目录项的名称 "Scripts" 包含在 **Path** 参数的值中，而不是在 **名称** 的值中指定。</span><span class="sxs-lookup"><span data-stu-id="e741f-137">The name of the new directory item, "Scripts", is included in the value of **Path** parameter, instead of being specified in the value of **Name** .</span></span> <span data-ttu-id="e741f-138">根据语法，任一种命令形式都是有效的。</span><span class="sxs-lookup"><span data-stu-id="e741f-138">As indicated by the syntax, either command form is valid.</span></span>

```powershell
New-Item -ItemType "directory" -Path "c:\ps-test\scripts"
```

### <span data-ttu-id="e741f-139">示例5：创建多个文件</span><span class="sxs-lookup"><span data-stu-id="e741f-139">Example 5: Create multiple files</span></span>

<span data-ttu-id="e741f-140">此示例在两个不同的目录中创建文件。</span><span class="sxs-lookup"><span data-stu-id="e741f-140">This example creates files in two different directories.</span></span> <span data-ttu-id="e741f-141">由于 **路径** 采用多个字符串，因此可以使用它来创建多个项。</span><span class="sxs-lookup"><span data-stu-id="e741f-141">Because **Path** takes multiple strings, you can use it to create multiple items.</span></span>

```powershell
New-Item -ItemType "file" -Path "c:\ps-test\test.txt", "c:\ps-test\Logs\test.log"
```

### <span data-ttu-id="e741f-142">示例6：使用-Force 参数尝试重新创建文件夹</span><span class="sxs-lookup"><span data-stu-id="e741f-142">Example 6: Use the -Force parameter to attempt to recreate folders</span></span>

<span data-ttu-id="e741f-143">此示例创建一个文件夹，其中包含中的文件。</span><span class="sxs-lookup"><span data-stu-id="e741f-143">This example creates a folder with a file inside.</span></span> <span data-ttu-id="e741f-144">然后，尝试使用创建相同的文件夹 `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-144">Then, attempts to create the same folder using `-Force`.</span></span> <span data-ttu-id="e741f-145">它不会覆盖文件夹，只需返回现有的文件夹对象，文件创建的文件也会原封不动。</span><span class="sxs-lookup"><span data-stu-id="e741f-145">It will not overwrite the folder but simply return the existing folder object with the file created intact.</span></span>

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

### <span data-ttu-id="e741f-146">示例7：使用-Force 参数覆盖现有文件</span><span class="sxs-lookup"><span data-stu-id="e741f-146">Example 7: Use the -Force parameter to overwrite existing files</span></span>

<span data-ttu-id="e741f-147">此示例创建一个具有值的文件，然后使用重新创建该文件 `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-147">This example creates a file with a value and then recreates the file using `-Force`.</span></span> <span data-ttu-id="e741f-148">这将覆盖现有文件，并且它将丢失其内容，正如您可以看到的 "长度" 属性所示</span><span class="sxs-lookup"><span data-stu-id="e741f-148">This overwrites The existing file and it will lose it's content as you can see by the length property</span></span>

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
> <span data-ttu-id="e741f-149">当使用 `New-Item` 带有 `-Force` 开关的来创建注册表项时，该命令的行为与覆盖文件时的行为相同。</span><span class="sxs-lookup"><span data-stu-id="e741f-149">When using `New-Item` with the `-Force` switch to create registry keys, the command will behave the same as when overwriting a file.</span></span> <span data-ttu-id="e741f-150">如果注册表项已存在，则将使用空的注册表项覆盖该项和所有属性和值。</span><span class="sxs-lookup"><span data-stu-id="e741f-150">If the registry key already exists, the key and all properties and values will be overwritten with an empty registry key.</span></span>

## <span data-ttu-id="e741f-151">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e741f-151">PARAMETERS</span></span>

### <span data-ttu-id="e741f-152">-Credential</span><span class="sxs-lookup"><span data-stu-id="e741f-152">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="e741f-153">随 PowerShell 一起安装的任何提供程序都不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="e741f-153">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="e741f-154">若要在运行此 cmdlet 时模拟其他用户或提升凭据，请使用 `Invoke-Command` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-154">To impersonate another user or elevate your credentials when running this cmdlet, use `Invoke-Command`.</span></span>

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

### <span data-ttu-id="e741f-155">-Force</span><span class="sxs-lookup"><span data-stu-id="e741f-155">-Force</span></span>

<span data-ttu-id="e741f-156">强制此 cmdlet 创建一个写入现有只读项的项。</span><span class="sxs-lookup"><span data-stu-id="e741f-156">Forces this cmdlet to create an item that writes over an existing read-only item.</span></span> <span data-ttu-id="e741f-157">不同提供程序有不同的实现。</span><span class="sxs-lookup"><span data-stu-id="e741f-157">Implementation varies from provider to provider.</span></span> <span data-ttu-id="e741f-158">即使使用 **Force** 参数，该 cmdlet 也无法覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="e741f-158">Even using the **Force** parameter, the cmdlet cannot override security restrictions.</span></span>

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

### <span data-ttu-id="e741f-159">-ItemType</span><span class="sxs-lookup"><span data-stu-id="e741f-159">-ItemType</span></span>

<span data-ttu-id="e741f-160">指定提供程序指定的新项的类型。</span><span class="sxs-lookup"><span data-stu-id="e741f-160">Specifies the provider-specified type of the new item.</span></span> <span data-ttu-id="e741f-161">此参数的可用值取决于当前使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="e741f-161">The available values of this parameter depend on the current provider you are using.</span></span>

<span data-ttu-id="e741f-162">如果位置在 `FileSystem` 驱动器中，则允许以下值：</span><span class="sxs-lookup"><span data-stu-id="e741f-162">If your location is in a `FileSystem` drive, the following values are allowed:</span></span>

- <span data-ttu-id="e741f-163">文件</span><span class="sxs-lookup"><span data-stu-id="e741f-163">File</span></span>
- <span data-ttu-id="e741f-164">Directory</span><span class="sxs-lookup"><span data-stu-id="e741f-164">Directory</span></span>
- <span data-ttu-id="e741f-165">SymbolicLink</span><span class="sxs-lookup"><span data-stu-id="e741f-165">SymbolicLink</span></span>
- <span data-ttu-id="e741f-166">交接点</span><span class="sxs-lookup"><span data-stu-id="e741f-166">Junction</span></span>
- <span data-ttu-id="e741f-167">硬</span><span class="sxs-lookup"><span data-stu-id="e741f-167">HardLink</span></span>

<span data-ttu-id="e741f-168">使用此方法创建文件时，会将生成的文件编码为 UTF-8，而不会将字节顺序标记 (BOM) 。</span><span class="sxs-lookup"><span data-stu-id="e741f-168">When you create a file using this method, the resulting file is encoded as UTF-8 without a byte-order-mark (BOM).</span></span>

<span data-ttu-id="e741f-169">在 `Certificate` 驱动器中，可以指定以下值：</span><span class="sxs-lookup"><span data-stu-id="e741f-169">In a `Certificate` drive, these are the values you can specify:</span></span>

- <span data-ttu-id="e741f-170">Certificate 提供程序</span><span class="sxs-lookup"><span data-stu-id="e741f-170">Certificate Provider</span></span>
- <span data-ttu-id="e741f-171">证书</span><span class="sxs-lookup"><span data-stu-id="e741f-171">Certificate</span></span>
- <span data-ttu-id="e741f-172">应用商店</span><span class="sxs-lookup"><span data-stu-id="e741f-172">Store</span></span>
- <span data-ttu-id="e741f-173">StoreLocation</span><span class="sxs-lookup"><span data-stu-id="e741f-173">StoreLocation</span></span>

<span data-ttu-id="e741f-174">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="e741f-174">For more information see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

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

### <span data-ttu-id="e741f-175">-Name</span><span class="sxs-lookup"><span data-stu-id="e741f-175">-Name</span></span>

<span data-ttu-id="e741f-176">指定新项的名称。</span><span class="sxs-lookup"><span data-stu-id="e741f-176">Specifies the name of the new item.</span></span> <span data-ttu-id="e741f-177">您可以在 **name** 或 **path** 参数值中指定新项的名称，并且可以在 " **名称** " 或 " **路径** " 值中指定新项的路径。</span><span class="sxs-lookup"><span data-stu-id="e741f-177">You can specify the name of the new item in the **Name** or **Path** parameter value, and you can specify the path of the new item in **Name** or **Path** value.</span></span> <span data-ttu-id="e741f-178">使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。</span><span class="sxs-lookup"><span data-stu-id="e741f-178">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

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

### <span data-ttu-id="e741f-179">-Path</span><span class="sxs-lookup"><span data-stu-id="e741f-179">-Path</span></span>

<span data-ttu-id="e741f-180">指定新项的位置的路径。</span><span class="sxs-lookup"><span data-stu-id="e741f-180">Specifies the path of the location of the new item.</span></span> <span data-ttu-id="e741f-181">如果省略 **路径** ，则默认值为当前位置。</span><span class="sxs-lookup"><span data-stu-id="e741f-181">The default is the current location when **Path** is omitted.</span></span> <span data-ttu-id="e741f-182">可以在 " **名称** " 中指定新项的名称，也可以将其包含在 " **路径** " 中。</span><span class="sxs-lookup"><span data-stu-id="e741f-182">You can specify the name of the new item in **Name** , or include it in **Path** .</span></span> <span data-ttu-id="e741f-183">使用 **Name** 参数传递的项名称是相对于 **Path** 参数的值创建的。</span><span class="sxs-lookup"><span data-stu-id="e741f-183">Items names passed using the **Name** parameter are created relative to the value of the **Path** parameter.</span></span>

<span data-ttu-id="e741f-184">对于此 cmdlet， **路径** 参数的工作方式类似于其他 Cmdlet 的 **LiteralPath** 参数。</span><span class="sxs-lookup"><span data-stu-id="e741f-184">For this cmdlet, the **Path** parameter works like the **LiteralPath** parameter of other cmdlets.</span></span>
<span data-ttu-id="e741f-185">不解释通配符。</span><span class="sxs-lookup"><span data-stu-id="e741f-185">Wildcard characters are not interpreted.</span></span> <span data-ttu-id="e741f-186">所有字符将传递到位置的提供程序。</span><span class="sxs-lookup"><span data-stu-id="e741f-186">All characters are passed to the location's provider.</span></span> <span data-ttu-id="e741f-187">提供程序可能不支持所有字符。</span><span class="sxs-lookup"><span data-stu-id="e741f-187">The provider may not support all characters.</span></span> <span data-ttu-id="e741f-188">例如，你不能创建包含星号 () 字符的文件名 `*` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-188">For example, you cannot create a filename that contains an asterisk (`*`) character.</span></span>

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

### <span data-ttu-id="e741f-189">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="e741f-189">-UseTransaction</span></span>

<span data-ttu-id="e741f-190">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="e741f-190">Includes the command in the active transaction.</span></span> <span data-ttu-id="e741f-191">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="e741f-191">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="e741f-192">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="e741f-192">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e741f-193">-Value</span><span class="sxs-lookup"><span data-stu-id="e741f-193">-Value</span></span>

<span data-ttu-id="e741f-194">指定新项的值。</span><span class="sxs-lookup"><span data-stu-id="e741f-194">Specifies the value of the new item.</span></span> <span data-ttu-id="e741f-195">还可以通过管道将值传递给 `New-Item` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-195">You can also pipe a value to `New-Item`.</span></span>

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

### <span data-ttu-id="e741f-196">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e741f-196">-Confirm</span></span>

<span data-ttu-id="e741f-197">提示你在运行 cmdlet 之前进行确认。</span><span class="sxs-lookup"><span data-stu-id="e741f-197">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e741f-198">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e741f-198">-WhatIf</span></span>

<span data-ttu-id="e741f-199">显示运行该 cmdlet 时会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="e741f-199">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e741f-200">此 cmdlet 未运行。</span><span class="sxs-lookup"><span data-stu-id="e741f-200">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e741f-201">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="e741f-201">CommonParameters</span></span>

<span data-ttu-id="e741f-202">此 cmdlet 支持通用参数： `-Debug` 、 `-ErrorAction` 、 `-ErrorVariable` 、、、、、、、 `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` 和 `-WarningVariable` 。</span><span class="sxs-lookup"><span data-stu-id="e741f-202">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="e741f-203">有关详细信息，请参阅 [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e741f-203">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e741f-204">输入</span><span class="sxs-lookup"><span data-stu-id="e741f-204">INPUTS</span></span>

### <span data-ttu-id="e741f-205">System.Object</span><span class="sxs-lookup"><span data-stu-id="e741f-205">System.Object</span></span>

<span data-ttu-id="e741f-206">可以通过管道将新项的值传递给此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e741f-206">You can pipe a value for the new item to this cmdlet.</span></span>

## <span data-ttu-id="e741f-207">输出</span><span class="sxs-lookup"><span data-stu-id="e741f-207">OUTPUTS</span></span>

### <span data-ttu-id="e741f-208">System.Object</span><span class="sxs-lookup"><span data-stu-id="e741f-208">System.Object</span></span>

<span data-ttu-id="e741f-209">此 cmdlet 将返回它创建的项。</span><span class="sxs-lookup"><span data-stu-id="e741f-209">This cmdlet returns the item that it creates.</span></span>

## <span data-ttu-id="e741f-210">注释</span><span class="sxs-lookup"><span data-stu-id="e741f-210">NOTES</span></span>

<span data-ttu-id="e741f-211">`New-Item` 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="e741f-211">`New-Item` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="e741f-212">若要列出会话中可用的提供程序，请键入 `Get-PsProvider`。</span><span class="sxs-lookup"><span data-stu-id="e741f-212">To list the providers available in your session, type `Get-PsProvider`.</span></span> <span data-ttu-id="e741f-213">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="e741f-213">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="e741f-214">相关链接</span><span class="sxs-lookup"><span data-stu-id="e741f-214">RELATED LINKS</span></span>

[<span data-ttu-id="e741f-215">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-215">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="e741f-216">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-216">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="e741f-217">Get-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-217">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="e741f-218">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-218">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="e741f-219">Move-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-219">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="e741f-220">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-220">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="e741f-221">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-221">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="e741f-222">Set-Item</span><span class="sxs-lookup"><span data-stu-id="e741f-222">Set-Item</span></span>](Set-Item.md)

[<span data-ttu-id="e741f-223">about_Providers</span><span class="sxs-lookup"><span data-stu-id="e741f-223">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
