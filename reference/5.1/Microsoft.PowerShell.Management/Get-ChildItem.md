---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-childitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ChildItem
ms.openlocfilehash: 9c613686765aa735e1e2cc58bfab533d1dc1e89f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "93198302"
---
# <span data-ttu-id="48067-103">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="48067-103">Get-ChildItem</span></span>

## <span data-ttu-id="48067-104">摘要</span><span class="sxs-lookup"><span data-stu-id="48067-104">SYNOPSIS</span></span>

<span data-ttu-id="48067-105">获取一个或多个指定位置中的项和子项。</span><span class="sxs-lookup"><span data-stu-id="48067-105">Gets the items and child items in one or more specified locations.</span></span>

## <span data-ttu-id="48067-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="48067-106">SYNTAX</span></span>

### <span data-ttu-id="48067-107">Items（默认值）</span><span class="sxs-lookup"><span data-stu-id="48067-107">Items (Default)</span></span>

```
Get-ChildItem [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>]
 [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-UseTransaction]
 [-Attributes <FlagsExpression[FileAttributes]>] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
 [<CommonParameters>]
```

### <span data-ttu-id="48067-108">LiteralItems</span><span class="sxs-lookup"><span data-stu-id="48067-108">LiteralItems</span></span>

```
Get-ChildItem [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>]
 [-Exclude <string[]>] [-Recurse] [-Depth <uint32>] [-Force] [-Name] [-UseTransaction]
 [-Attributes <FlagsExpression[FileAttributes]>] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System]
 [<CommonParameters>]
```

## <span data-ttu-id="48067-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="48067-109">DESCRIPTION</span></span>

<span data-ttu-id="48067-110">`Get-ChildItem`Cmdlet 获取一个或多个指定位置中的项。</span><span class="sxs-lookup"><span data-stu-id="48067-110">The `Get-ChildItem` cmdlet gets the items in one or more specified locations.</span></span> <span data-ttu-id="48067-111">如果该项为容器，则此命令将获取容器内的各项（称为子项）。</span><span class="sxs-lookup"><span data-stu-id="48067-111">If the item is a container, it gets the items inside the container, known as child items.</span></span> <span data-ttu-id="48067-112">可以使用 **递归** 参数获取所有子容器中的项，并使用 **Depth** 参数来限制要递归的级别数。</span><span class="sxs-lookup"><span data-stu-id="48067-112">You can use the **Recurse** parameter to get items in all child containers and use the **Depth** parameter to limit the number of levels to recurse.</span></span>

<span data-ttu-id="48067-113">`Get-ChildItem` 不显示空目录。</span><span class="sxs-lookup"><span data-stu-id="48067-113">`Get-ChildItem` doesn't display empty directories.</span></span> <span data-ttu-id="48067-114">当 `Get-ChildItem` 命令包含 **深度** 或 **递归** 参数时，输出中不包括空目录。</span><span class="sxs-lookup"><span data-stu-id="48067-114">When a `Get-ChildItem` command includes the **Depth** or **Recurse** parameters, empty directories aren't included in the output.</span></span>

<span data-ttu-id="48067-115">位置 `Get-ChildItem` 由 PowerShell 提供程序向公开。</span><span class="sxs-lookup"><span data-stu-id="48067-115">Locations are exposed to `Get-ChildItem` by PowerShell providers.</span></span> <span data-ttu-id="48067-116">位置可以是文件系统目录、注册表配置单元或证书存储区。</span><span class="sxs-lookup"><span data-stu-id="48067-116">A location can be a file system directory, registry hive, or a certificate store.</span></span> <span data-ttu-id="48067-117">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-117">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="48067-118">示例</span><span class="sxs-lookup"><span data-stu-id="48067-118">EXAMPLES</span></span>

### <span data-ttu-id="48067-119">示例1：从文件系统目录获取子项目</span><span class="sxs-lookup"><span data-stu-id="48067-119">Example 1: Get child items from a file system directory</span></span>

<span data-ttu-id="48067-120">此示例从文件系统目录中获取子项目。</span><span class="sxs-lookup"><span data-stu-id="48067-120">This example gets the child items from a file system directory.</span></span> <span data-ttu-id="48067-121">将显示文件名和子目录的名称。</span><span class="sxs-lookup"><span data-stu-id="48067-121">The filenames and subdirectory names are displayed.</span></span> <span data-ttu-id="48067-122">对于空位置，该命令不会返回任何输出，并返回到 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="48067-122">For empty locations, the command doesn't return any output and returns to the PowerShell prompt.</span></span>

<span data-ttu-id="48067-123">`Get-ChildItem`Cmdlet 使用 **Path** 参数来指定目录 `C:\Test` 。</span><span class="sxs-lookup"><span data-stu-id="48067-123">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span>
<span data-ttu-id="48067-124">`Get-ChildItem` 显示 PowerShell 控制台中的文件和目录。</span><span class="sxs-lookup"><span data-stu-id="48067-124">`Get-ChildItem` displays the files and directories in the PowerShell console.</span></span>

```powershell
Get-ChildItem -Path C:\Test
```

```Output
   Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     08:29                Logs
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a----         2/1/2019     08:43            183 CreateTestFile.ps1
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="48067-125">默认情况 `Get-ChildItem` 下，会列出模式 ( **特性** ) 、 **LastWriteTime** 、文件大小 ( **长度** ) 和项的 **名称** 。</span><span class="sxs-lookup"><span data-stu-id="48067-125">By default `Get-ChildItem` lists the mode ( **Attributes** ), **LastWriteTime** , file size ( **Length** ), and the **Name** of the item.</span></span> <span data-ttu-id="48067-126">**Mode** 属性中的字母可解释如下：</span><span class="sxs-lookup"><span data-stu-id="48067-126">The letters in the **Mode** property can be interpreted as follows:</span></span>

- <span data-ttu-id="48067-127">`l` (链接) </span><span class="sxs-lookup"><span data-stu-id="48067-127">`l` (link)</span></span>
- <span data-ttu-id="48067-128">`d` (目录) </span><span class="sxs-lookup"><span data-stu-id="48067-128">`d` (directory)</span></span>
- <span data-ttu-id="48067-129">`a` (存档) </span><span class="sxs-lookup"><span data-stu-id="48067-129">`a` (archive)</span></span>
- <span data-ttu-id="48067-130">`r` (只读) </span><span class="sxs-lookup"><span data-stu-id="48067-130">`r` (read-only)</span></span>
- <span data-ttu-id="48067-131">`h` (隐藏) </span><span class="sxs-lookup"><span data-stu-id="48067-131">`h` (hidden)</span></span>
- <span data-ttu-id="48067-132">`s` (系统) 。</span><span class="sxs-lookup"><span data-stu-id="48067-132">`s` (system).</span></span>

<span data-ttu-id="48067-133">有关模式标志的详细信息，请参阅 [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression)。</span><span class="sxs-lookup"><span data-stu-id="48067-133">For more information about the mode flags, see [about_Filesystem_Provider](../microsoft.powershell.core/about/about_filesystem_provider.md#attributes-flagsexpression).</span></span>

### <span data-ttu-id="48067-134">示例2：获取目录中的子项目名称</span><span class="sxs-lookup"><span data-stu-id="48067-134">Example 2: Get child item names in a directory</span></span>

<span data-ttu-id="48067-135">此示例仅列出目录中项的名称。</span><span class="sxs-lookup"><span data-stu-id="48067-135">This example lists only the names of items in a directory.</span></span>

<span data-ttu-id="48067-136">`Get-ChildItem`Cmdlet 使用 **Path** 参数来指定目录 `C:\Test` 。</span><span class="sxs-lookup"><span data-stu-id="48067-136">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test`.</span></span> <span data-ttu-id="48067-137">**Name** 参数仅返回指定路径中的文件名或目录名。</span><span class="sxs-lookup"><span data-stu-id="48067-137">The **Name** parameter returns only the file or directory names from the specified path.</span></span>

```powershell
Get-ChildItem -Path C:\Test -Name
```

```Output
Logs
anotherfile.txt
Command.txt
CreateTestFile.ps1
ReadOnlyFile.txt
```

### <span data-ttu-id="48067-138">示例3：获取当前目录和子目录中的子项</span><span class="sxs-lookup"><span data-stu-id="48067-138">Example 3: Get child items in the current directory and subdirectories</span></span>

<span data-ttu-id="48067-139">此示例显示位于当前目录及其子目录中的 **.txt** 文件。</span><span class="sxs-lookup"><span data-stu-id="48067-139">This example displays **.txt** files that are located in the current directory and its subdirectories.</span></span>

```powershell
Get-ChildItem -Path C:\Test\*.txt -Recurse -Force
```

```Output
    Directory: C:\Test\Logs\Adirectory

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile4.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile4.txt

    Directory: C:\Test\Logs\Backup

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 ATextFile.txt
-a----        2/12/2019     15:50             20 LogFile3.txt

    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/12/2019     16:16             20 Afile.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt

    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-a-h--        2/12/2019     15:52             22 hiddenfile.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="48067-140">`Get-ChildItem`Cmdlet 使用 **Path** 参数指定 `C:\Test\*.txt` 。</span><span class="sxs-lookup"><span data-stu-id="48067-140">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify `C:\Test\*.txt`.</span></span> <span data-ttu-id="48067-141">**Path** 使用 `*`) 通配符 (星号来指定具有文件扩展名的所有文件 `.txt` 。</span><span class="sxs-lookup"><span data-stu-id="48067-141">**Path** uses the asterisk (`*`) wildcard to specify all files with the filename extension `.txt`.</span></span> <span data-ttu-id="48067-142">**递归** 参数会搜索 **Path** 目录的子目录，如 **目录：** 标题中所示。</span><span class="sxs-lookup"><span data-stu-id="48067-142">The **Recurse** parameter searches the **Path** directory its subdirectories, as shown in the **Directory:** headings.</span></span> <span data-ttu-id="48067-143">**Force** 参数显示其模式为 h 的隐藏文件 `hiddenfile.txt` 。 **h**</span><span class="sxs-lookup"><span data-stu-id="48067-143">The **Force** parameter displays hidden files such as `hiddenfile.txt` that have a mode of **h** .</span></span>

### <span data-ttu-id="48067-144">示例4：使用 Include 参数获取子项目</span><span class="sxs-lookup"><span data-stu-id="48067-144">Example 4: Get child items using the Include parameter</span></span>

<span data-ttu-id="48067-145">在此示例中， `Get-ChildItem` 使用 **Include** 参数查找 **Path** 参数所指定的目录中的特定项。</span><span class="sxs-lookup"><span data-stu-id="48067-145">In this example `Get-ChildItem` uses the **Include** parameter to find specific items from the directory specified by the **Path** parameter.</span></span>

```powershell
# When using the -Include parameter, if you don't include an asterisk in the path
# the command returns no output.
Get-ChildItem -Path C:\Test\ -Include *.txt
```

```Output

```

```powershell
Get-ChildItem -Path C:\Test\* -Include *.txt
```

```Output
    Directory: C:\Test

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        2/13/2019     08:55             26 anotherfile.txt
-a----        2/12/2019     15:40         118014 Command.txt
-ar---        2/12/2019     14:31             27 ReadOnlyFile.txt
```

<span data-ttu-id="48067-146">`Get-ChildItem`Cmdlet 使用 **Path** 参数指定目录 **C:\Test** 。</span><span class="sxs-lookup"><span data-stu-id="48067-146">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory **C:\Test** .</span></span> <span data-ttu-id="48067-147">**Path** 参数包含一个尾部星号 (`*`) 通配符，以指定目录的内容。</span><span class="sxs-lookup"><span data-stu-id="48067-147">The **Path** parameter includes a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span>
<span data-ttu-id="48067-148">**Include** 参数使用星号 (`*`) 通配符来指定文件扩展名为 **.txt** 的所有文件。</span><span class="sxs-lookup"><span data-stu-id="48067-148">The **Include** parameter uses an asterisk (`*`) wildcard to specify all files with the file name extension **.txt** .</span></span>

<span data-ttu-id="48067-149">当使用 **Include** 参数时， **Path** 参数需要一个尾部星号 (`*`) 通配符，以指定目录的内容。</span><span class="sxs-lookup"><span data-stu-id="48067-149">When the **Include** parameter is used, the **Path** parameter needs a trailing asterisk (`*`) wildcard to specify the directory's contents.</span></span> <span data-ttu-id="48067-150">例如，`-Path C:\Test\*`。</span><span class="sxs-lookup"><span data-stu-id="48067-150">For example, `-Path C:\Test\*`.</span></span>

- <span data-ttu-id="48067-151">如果将 **递归** 参数添加到命令中，则 `*` **Path** 参数中) 的尾随星号 (是可选的。</span><span class="sxs-lookup"><span data-stu-id="48067-151">If the **Recurse** parameter is added to the command, the trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="48067-152">**递归** 参数从 **路径** 目录及其子目录中获取项。</span><span class="sxs-lookup"><span data-stu-id="48067-152">The **Recurse** parameter gets items from the **Path** directory and its subdirectories.</span></span> <span data-ttu-id="48067-153">例如： `-Path C:\Test\ -Recurse -Include *.txt`</span><span class="sxs-lookup"><span data-stu-id="48067-153">For example, `-Path C:\Test\ -Recurse -Include *.txt`</span></span>
- <span data-ttu-id="48067-154">如果 `*` **Path** 参数中未包含尾随星号 () ，则该命令不会返回任何输出并返回到 PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="48067-154">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the command doesn't return any output and returns to the PowerShell prompt.</span></span> <span data-ttu-id="48067-155">例如，`-Path C:\Test\`。</span><span class="sxs-lookup"><span data-stu-id="48067-155">For example, `-Path C:\Test\`.</span></span>

### <span data-ttu-id="48067-156">示例5：使用 Exclude 参数获取子项目</span><span class="sxs-lookup"><span data-stu-id="48067-156">Example 5: Get child items using the Exclude parameter</span></span>

<span data-ttu-id="48067-157">该示例的输出显示目录 **C:\Test\Logs** 的内容。</span><span class="sxs-lookup"><span data-stu-id="48067-157">The example's output shows the contents of the directory **C:\Test\Logs** .</span></span> <span data-ttu-id="48067-158">输出是对使用 **Exclude** 和 **递归** 参数的其他命令的引用。</span><span class="sxs-lookup"><span data-stu-id="48067-158">The output is a reference for the other commands that use the **Exclude** and **Recurse** parameters.</span></span>

```powershell
Get-ChildItem -Path C:\Test\Logs
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Adirectory
d-----        2/15/2019     08:28                AnEmptyDirectory
d-----        2/15/2019     13:21                Backup
-a----        2/12/2019     16:16             20 Afile.txt
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

```powershell
Get-ChildItem -Path C:\Test\Logs\* -Exclude A*
```

```Output
    Directory: C:\Test\Logs

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/15/2019     13:21                Backup
-a----        2/13/2019     13:26             20 LogFile1.txt
-a----        2/12/2019     16:24             23 systemlog1.log
```

<span data-ttu-id="48067-159">`Get-ChildItem`Cmdlet 使用 **Path** 参数来指定目录 `C:\Test\Logs` 。</span><span class="sxs-lookup"><span data-stu-id="48067-159">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the directory `C:\Test\Logs`.</span></span>
<span data-ttu-id="48067-160">**Exclude** 参数使用星号 (`*`) 通配符来指定以或开头的任何文件或目录， **A** 从输出 **a** 中排除。</span><span class="sxs-lookup"><span data-stu-id="48067-160">The **Exclude** parameter uses the asterisk (`*`) wildcard to specify any files or directories that begin with **A** or **a** are excluded from the output.</span></span>

<span data-ttu-id="48067-161">使用 **Exclude** 参数时， `*` **Path** 参数中)  (后缀星号是可选的。</span><span class="sxs-lookup"><span data-stu-id="48067-161">When the **Exclude** parameter is used, a trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="48067-162">例如，`-Path C:\Test\Logs` 或 `-Path C:\Test\Logs\*`。</span><span class="sxs-lookup"><span data-stu-id="48067-162">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span>

- <span data-ttu-id="48067-163">如果 `*` **path** 参数中未包含尾随星号 () ，则显示 **path** 参数的内容。</span><span class="sxs-lookup"><span data-stu-id="48067-163">If a trailing asterisk (`*`) isn't included in the **Path** parameter, the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="48067-164">例外情况是与 **Exclude** 参数的值匹配的文件名或子目录名称。</span><span class="sxs-lookup"><span data-stu-id="48067-164">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="48067-165">如果 `*` **path** 参数中包含尾随星号 () ，则命令 recurses 到 **path** 参数的子目录中。</span><span class="sxs-lookup"><span data-stu-id="48067-165">If a trailing asterisk (`*`) is included in the **Path** parameter, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="48067-166">例外情况是与 **Exclude** 参数的值匹配的文件名或子目录名称。</span><span class="sxs-lookup"><span data-stu-id="48067-166">The exceptions are filenames or subdirectory names that match the **Exclude** parameter's value.</span></span>
- <span data-ttu-id="48067-167">如果将 **递归** 参数添加到命令中，则无论 **Path** 参数是否包含尾随星号 () ，递归输出都是相同的 `*` 。</span><span class="sxs-lookup"><span data-stu-id="48067-167">If the **Recurse** parameter is added to the command, the recursion output is the same whether or not the **Path** parameter includes a trailing asterisk (`*`).</span></span>

### <span data-ttu-id="48067-168">示例6：从注册表配置单元获取注册表项</span><span class="sxs-lookup"><span data-stu-id="48067-168">Example 6: Get the registry keys from a registry hive</span></span>

<span data-ttu-id="48067-169">此示例从获取中的所有注册表项 `HKEY_LOCAL_MACHINE\HARDWARE` 。</span><span class="sxs-lookup"><span data-stu-id="48067-169">This example gets all the registry keys from `HKEY_LOCAL_MACHINE\HARDWARE`.</span></span>

<span data-ttu-id="48067-170">`Get-ChildItem` 使用 **Path** 参数指定注册表项 `HKLM:\HARDWARE` 。</span><span class="sxs-lookup"><span data-stu-id="48067-170">`Get-ChildItem` uses the **Path** parameter to specify the registry key `HKLM:\HARDWARE`.</span></span> <span data-ttu-id="48067-171">配置单元的路径和顶级注册表项显示在 PowerShell 控制台中。</span><span class="sxs-lookup"><span data-stu-id="48067-171">The hive's path and top level of registry keys are displayed in the PowerShell console.</span></span>

<span data-ttu-id="48067-172">有关详细信息，请参阅 [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-172">For more information, see [about_Registry_Provider](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md).</span></span>

```powershell
Get-ChildItem -Path HKLM:\HARDWARE
```

```Output
    Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name             Property
----             --------
ACPI
DESCRIPTION
DEVICEMAP
RESOURCEMAP
UEFI
```

```powershell
Get-ChildItem -Path HKLM:\HARDWARE -Exclude D*
```

```Output
   Hive: HKEY_LOCAL_MACHINE\HARDWARE

Name                           Property
----                           --------
ACPI
RESOURCEMAP
```

<span data-ttu-id="48067-173">第一个命令显示注册表项的内容 `HKLM:\HARDWARE` 。</span><span class="sxs-lookup"><span data-stu-id="48067-173">The first command shows the contents of the `HKLM:\HARDWARE` registry key.</span></span> <span data-ttu-id="48067-174">**Exclude** 参数指示 `Get-ChildItem` 不返回以开头的任何子项 `D*` 。</span><span class="sxs-lookup"><span data-stu-id="48067-174">The **Exclude** parameter tells `Get-ChildItem` not to return any subkeys that start with `D*`.</span></span> <span data-ttu-id="48067-175">目前， **Exclude** 参数仅适用于子项，而不是项属性。</span><span class="sxs-lookup"><span data-stu-id="48067-175">Currently, the **Exclude** parameter only works on subkeys, not item properties.</span></span>

### <span data-ttu-id="48067-176">示例7：获取具有代码签名颁发机构的所有证书</span><span class="sxs-lookup"><span data-stu-id="48067-176">Example 7: Get all certificates with code-signing authority</span></span>

<span data-ttu-id="48067-177">此示例获取 PowerShell **Cert：** 驱动器中具有代码签名颁发机构的每个证书。</span><span class="sxs-lookup"><span data-stu-id="48067-177">This example gets each certificate in the PowerShell **Cert:** drive that has code-signing authority.</span></span>

<span data-ttu-id="48067-178">`Get-ChildItem`Cmdlet 使用 **Path** 参数指定 **Cert：** provider。</span><span class="sxs-lookup"><span data-stu-id="48067-178">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify the **Cert:** provider.</span></span> <span data-ttu-id="48067-179">**递归** 参数搜索 **路径** 及其子目录指定的目录。</span><span class="sxs-lookup"><span data-stu-id="48067-179">The **Recurse** parameter searches the directory specified by **Path** and its subdirectories.</span></span> <span data-ttu-id="48067-180">**CodeSigningCert** 参数仅获取具有代码签名颁发机构的证书。</span><span class="sxs-lookup"><span data-stu-id="48067-180">The **CodeSigningCert** parameter gets only certificates that have code-signing authority.</span></span>

```powershell
Get-ChildItem -Path Cert:\* -Recurse -CodeSigningCert
```

<span data-ttu-id="48067-181">有关证书提供程序和 Cert：驱动器的详细信息，请参阅 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-181">For more information about the Certificate provider and the Cert: drive, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="48067-182">示例8：使用 Depth 参数获取项</span><span class="sxs-lookup"><span data-stu-id="48067-182">Example 8: Get items using the Depth parameter</span></span>

<span data-ttu-id="48067-183">此示例显示目录及其子目录中的项。</span><span class="sxs-lookup"><span data-stu-id="48067-183">This example displays the items in a directory and its subdirectories.</span></span> <span data-ttu-id="48067-184">**Depth** 参数确定要包括在递归中的子目录级别数。</span><span class="sxs-lookup"><span data-stu-id="48067-184">The **Depth** parameter determines the number of subdirectory levels to include in the recursion.</span></span> <span data-ttu-id="48067-185">空目录将从输出中排除。</span><span class="sxs-lookup"><span data-stu-id="48067-185">Empty directories are excluded from the output.</span></span>

```powershell
Get-ChildItem -Path C:\Parent -Depth 2
```

```Output
    Directory: C:\Parent

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level1
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:24                SubDir_Level2
-a----        2/13/2019     08:55             26 file.txt

    Directory: C:\Parent\SubDir_Level1\SubDir_Level2

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        2/14/2019     10:22                SubDir_Level3
-a----        2/13/2019     08:55             26 file.txt
```

<span data-ttu-id="48067-186">`Get-ChildItem`Cmdlet 使用 **Path** 参数指定 **C:\Parent** 。</span><span class="sxs-lookup"><span data-stu-id="48067-186">The `Get-ChildItem` cmdlet uses the **Path** parameter to specify **C:\Parent** .</span></span> <span data-ttu-id="48067-187">**Depth** 参数指定两个递归级别。</span><span class="sxs-lookup"><span data-stu-id="48067-187">The **Depth** parameter specifies two levels of recursion.</span></span> <span data-ttu-id="48067-188">`Get-ChildItem` 显示 **Path** 参数所指定的目录的内容和两个子目录级别。</span><span class="sxs-lookup"><span data-stu-id="48067-188">`Get-ChildItem` displays the contents of the directory specified by the **Path** parameter and the two levels of subdirectories.</span></span>

## <span data-ttu-id="48067-189">parameters</span><span class="sxs-lookup"><span data-stu-id="48067-189">Parameters</span></span>

### <span data-ttu-id="48067-190">-Attributes</span><span class="sxs-lookup"><span data-stu-id="48067-190">-Attributes</span></span>

<span data-ttu-id="48067-191">获取具有指定属性的文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="48067-191">Gets files and folders with the specified attributes.</span></span> <span data-ttu-id="48067-192">此参数支持所有属性，并且允许你指定复杂的属性组合。</span><span class="sxs-lookup"><span data-stu-id="48067-192">This parameter supports all attributes and lets you specify complex combinations of attributes.</span></span>

<span data-ttu-id="48067-193">例如，若要获取加密或压缩的非系统文件（而不是目录），请键入：</span><span class="sxs-lookup"><span data-stu-id="48067-193">For example, to get non-system files (not directories) that are encrypted or compressed, type:</span></span>

`Get-ChildItem -Attributes !Directory+!System+Encrypted, !Directory+!System+Compressed`

<span data-ttu-id="48067-194">若要查找具有常用属性的文件和文件夹，请使用 **attributes** 参数。</span><span class="sxs-lookup"><span data-stu-id="48067-194">To find files and folders with commonly used attributes, use the **Attributes** parameter.</span></span> <span data-ttu-id="48067-195">或参数 **目录** 、 **文件** 、 **隐藏** 、 **只读** 和 **系统** 。</span><span class="sxs-lookup"><span data-stu-id="48067-195">Or, the parameters **Directory** , **File** , **Hidden** , **ReadOnly** , and **System** .</span></span>

<span data-ttu-id="48067-196">Properties **参数支持** 以下属性：</span><span class="sxs-lookup"><span data-stu-id="48067-196">The **Attributes** parameter supports the following properties:</span></span>

- <span data-ttu-id="48067-197">**存档**</span><span class="sxs-lookup"><span data-stu-id="48067-197">**Archive**</span></span>
- <span data-ttu-id="48067-198">**Compressed**</span><span class="sxs-lookup"><span data-stu-id="48067-198">**Compressed**</span></span>
- <span data-ttu-id="48067-199">**设备**</span><span class="sxs-lookup"><span data-stu-id="48067-199">**Device**</span></span>
- <span data-ttu-id="48067-200">**Directory**</span><span class="sxs-lookup"><span data-stu-id="48067-200">**Directory**</span></span>
- <span data-ttu-id="48067-201">**已加密**</span><span class="sxs-lookup"><span data-stu-id="48067-201">**Encrypted**</span></span>
- <span data-ttu-id="48067-202">**Hidden**</span><span class="sxs-lookup"><span data-stu-id="48067-202">**Hidden**</span></span>
- <span data-ttu-id="48067-203">**IntegrityStream**</span><span class="sxs-lookup"><span data-stu-id="48067-203">**IntegrityStream**</span></span>
- <span data-ttu-id="48067-204">**正常**</span><span class="sxs-lookup"><span data-stu-id="48067-204">**Normal**</span></span>
- <span data-ttu-id="48067-205">**NoScrubData**</span><span class="sxs-lookup"><span data-stu-id="48067-205">**NoScrubData**</span></span>
- <span data-ttu-id="48067-206">**NotContentIndexed**</span><span class="sxs-lookup"><span data-stu-id="48067-206">**NotContentIndexed**</span></span>
- <span data-ttu-id="48067-207">**断开**</span><span class="sxs-lookup"><span data-stu-id="48067-207">**Offline**</span></span>
- <span data-ttu-id="48067-208">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="48067-208">**ReadOnly**</span></span>
- <span data-ttu-id="48067-209">**ReparsePoint**</span><span class="sxs-lookup"><span data-stu-id="48067-209">**ReparsePoint**</span></span>
- <span data-ttu-id="48067-210">**SparseFile**</span><span class="sxs-lookup"><span data-stu-id="48067-210">**SparseFile**</span></span>
- <span data-ttu-id="48067-211">**系统**</span><span class="sxs-lookup"><span data-stu-id="48067-211">**System**</span></span>
- <span data-ttu-id="48067-212">**临时**</span><span class="sxs-lookup"><span data-stu-id="48067-212">**Temporary**</span></span>

<span data-ttu-id="48067-213">有关这些属性的说明，请参阅 [FileAttributes 枚举](/dotnet/api/system.io.fileattributes)。</span><span class="sxs-lookup"><span data-stu-id="48067-213">For a description of these attributes, see the [FileAttributes Enumeration](/dotnet/api/system.io.fileattributes).</span></span>

<span data-ttu-id="48067-214">若要合并属性，请使用以下运算符：</span><span class="sxs-lookup"><span data-stu-id="48067-214">To combine attributes, use the following operators:</span></span>

- <span data-ttu-id="48067-215">`!` (未) </span><span class="sxs-lookup"><span data-stu-id="48067-215">`!` (NOT)</span></span>
- <span data-ttu-id="48067-216">`+` (和) </span><span class="sxs-lookup"><span data-stu-id="48067-216">`+` (AND)</span></span>
- <span data-ttu-id="48067-217">`,` (或) </span><span class="sxs-lookup"><span data-stu-id="48067-217">`,` (OR)</span></span>

<span data-ttu-id="48067-218">运算符与其属性之间不要使用空格。</span><span class="sxs-lookup"><span data-stu-id="48067-218">Don't use spaces between an operator and its attribute.</span></span> <span data-ttu-id="48067-219">逗号后接受空格。</span><span class="sxs-lookup"><span data-stu-id="48067-219">Spaces are accepted after commas.</span></span>

<span data-ttu-id="48067-220">对于常用属性，请使用以下缩写：</span><span class="sxs-lookup"><span data-stu-id="48067-220">For common attributes, use the following abbreviations:</span></span>

- <span data-ttu-id="48067-221">`D` (目录) </span><span class="sxs-lookup"><span data-stu-id="48067-221">`D` (Directory)</span></span>
- <span data-ttu-id="48067-222">`H` (隐藏) </span><span class="sxs-lookup"><span data-stu-id="48067-222">`H` (Hidden)</span></span>
- <span data-ttu-id="48067-223">`R` (只读) </span><span class="sxs-lookup"><span data-stu-id="48067-223">`R` (Read-only)</span></span>
- <span data-ttu-id="48067-224">`S` (系统) </span><span class="sxs-lookup"><span data-stu-id="48067-224">`S` (System)</span></span>

```yaml
Type: System.Management.Automation.FlagsExpression`1[System.IO.FileAttributes]
Parameter Sets: (All)
Aliases:
Accepted values: Archive, Compressed, Device, Directory, Encrypted, Hidden, IntegrityStream, Normal, NoScrubData, NotContentIndexed, Offline, ReadOnly, ReparsePoint, SparseFile, System, Temporary

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-225">-Depth</span><span class="sxs-lookup"><span data-stu-id="48067-225">-Depth</span></span>

<span data-ttu-id="48067-226">此参数是在 PowerShell 5.0 中添加的，使你可以控制递归的深度。</span><span class="sxs-lookup"><span data-stu-id="48067-226">This parameter was added in PowerShell 5.0 and enables you to control the depth of recursion.</span></span> <span data-ttu-id="48067-227">默认情况下， `Get-ChildItem` 显示父目录的内容。</span><span class="sxs-lookup"><span data-stu-id="48067-227">By default, `Get-ChildItem` displays the contents of the parent directory.</span></span> <span data-ttu-id="48067-228">**深度** 参数确定递归中包含的子目录级别数，并显示内容。</span><span class="sxs-lookup"><span data-stu-id="48067-228">The **Depth** parameter determines the number of subdirectory levels that are included in the recursion and displays the contents.</span></span>

<span data-ttu-id="48067-229">例如， `Depth 2` 包括 **Path** 参数的目录、第一级子目录和二级子目录。</span><span class="sxs-lookup"><span data-stu-id="48067-229">For example, `Depth 2` includes the **Path** parameter's directory, first level of subdirectories, and second level of subdirectories.</span></span> <span data-ttu-id="48067-230">默认情况下，输出中包含目录名称和文件名。</span><span class="sxs-lookup"><span data-stu-id="48067-230">By default directory names and filenames are included in the output.</span></span>

> [!NOTE]
> <span data-ttu-id="48067-231">在从 PowerShell 或 **cmd.exe** 的 Windows 计算机上，可以使用 **tree.com** 命令显示目录结构的图形视图。</span><span class="sxs-lookup"><span data-stu-id="48067-231">On a Windows computer from PowerShell or **cmd.exe** , you can display a graphical view of a directory structure with the **tree.com** command.</span></span>

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-232">-Directory</span><span class="sxs-lookup"><span data-stu-id="48067-232">-Directory</span></span>

<span data-ttu-id="48067-233">若要获取目录列表，请使用 **directory** 参数或具有 **Directory** 属性的 **Attributes** 参数。</span><span class="sxs-lookup"><span data-stu-id="48067-233">To get a list of directories, use the **Directory** parameter or the **Attributes** parameter with the **Directory** property.</span></span> <span data-ttu-id="48067-234">可以将 **递归** 参数与 **Directory** 一起使用。</span><span class="sxs-lookup"><span data-stu-id="48067-234">You can use the **Recurse** parameter with **Directory** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ad, d

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-235">-Exclude</span><span class="sxs-lookup"><span data-stu-id="48067-235">-Exclude</span></span>

<span data-ttu-id="48067-236">指定为字符串数组，此 cmdlet 从操作中排除的属性或属性。</span><span class="sxs-lookup"><span data-stu-id="48067-236">Specifies, as a string array, a property or property that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="48067-237">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="48067-237">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="48067-238">输入路径元素或模式，例如 `*.txt` 或 `A*` 。</span><span class="sxs-lookup"><span data-stu-id="48067-238">Enter a path element or pattern, such as `*.txt` or `A*`.</span></span> <span data-ttu-id="48067-239">可接受通配符。</span><span class="sxs-lookup"><span data-stu-id="48067-239">Wildcard characters are accepted.</span></span>

<span data-ttu-id="48067-240">`*` **Path** 参数中)  (后缀星号是可选的。</span><span class="sxs-lookup"><span data-stu-id="48067-240">A trailing asterisk (`*`) in the **Path** parameter is optional.</span></span> <span data-ttu-id="48067-241">例如，`-Path C:\Test\Logs` 或 `-Path C:\Test\Logs\*`。</span><span class="sxs-lookup"><span data-stu-id="48067-241">For example, `-Path C:\Test\Logs` or `-Path C:\Test\Logs\*`.</span></span> <span data-ttu-id="48067-242">如果包含尾随星号 (`*`) ，则命令 recurses 到 **Path** 参数的子目录中。</span><span class="sxs-lookup"><span data-stu-id="48067-242">If a trailing asterisk (`*`) is included, the command recurses into the **Path** parameter's subdirectories.</span></span> <span data-ttu-id="48067-243">如果没有星号 (`*`) ，则显示 **Path** 参数的内容。</span><span class="sxs-lookup"><span data-stu-id="48067-243">Without the asterisk (`*`), the contents of the **Path** parameter are displayed.</span></span> <span data-ttu-id="48067-244">示例5和备注部分中提供了更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="48067-244">More details are included in Example 5 and the Notes section.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48067-245">-File</span><span class="sxs-lookup"><span data-stu-id="48067-245">-File</span></span>

<span data-ttu-id="48067-246">若要获取文件列表，请使用 **File** 参数。</span><span class="sxs-lookup"><span data-stu-id="48067-246">To get a list of files, use the **File** parameter.</span></span> <span data-ttu-id="48067-247">可以将 **递归** 参数用于 **File** 。</span><span class="sxs-lookup"><span data-stu-id="48067-247">You can use the **Recurse** parameter with **File** .</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: af

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-248">-Filter</span><span class="sxs-lookup"><span data-stu-id="48067-248">-Filter</span></span>

<span data-ttu-id="48067-249">指定用于限定 **路径** 参数的筛选器。</span><span class="sxs-lookup"><span data-stu-id="48067-249">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="48067-250">[FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)提供程序是唯一安装的支持筛选器的 PowerShell 提供程序。</span><span class="sxs-lookup"><span data-stu-id="48067-250">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports filters.</span></span> <span data-ttu-id="48067-251">筛选器比其他参数更有效。</span><span class="sxs-lookup"><span data-stu-id="48067-251">Filters are more efficient than other parameters.</span></span> <span data-ttu-id="48067-252">当 cmdlet 获取对象时，提供程序将应用筛选器，而不是在检索对象后再对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="48067-252">The provider applies filter when the cmdlet gets the objects rather than having PowerShell filter the objects after they're retrieved.</span></span> <span data-ttu-id="48067-253">筛选器字符串将传递给 .NET API 以枚举文件。</span><span class="sxs-lookup"><span data-stu-id="48067-253">The filter string is passed to the .NET API to enumerate files.</span></span> <span data-ttu-id="48067-254">API 仅支持 `*` 和 `?` 通配符。</span><span class="sxs-lookup"><span data-stu-id="48067-254">The API only supports `*` and `?` wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48067-255">-Force</span><span class="sxs-lookup"><span data-stu-id="48067-255">-Force</span></span>

<span data-ttu-id="48067-256">允许 cmdlet 获取用户不能访问的项，如隐藏文件或系统文件。</span><span class="sxs-lookup"><span data-stu-id="48067-256">Allows the cmdlet to get items that otherwise can't be accessed by the user, such as hidden or system files.</span></span> <span data-ttu-id="48067-257">**Force** 参数不会覆盖安全限制。</span><span class="sxs-lookup"><span data-stu-id="48067-257">The **Force** parameter doesn't override security restrictions.</span></span> <span data-ttu-id="48067-258">实现提供程序之间的差异。</span><span class="sxs-lookup"><span data-stu-id="48067-258">Implementation varies among providers.</span></span> <span data-ttu-id="48067-259">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-259">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-260">-Hidden</span><span class="sxs-lookup"><span data-stu-id="48067-260">-Hidden</span></span>

<span data-ttu-id="48067-261">若要仅获取隐藏项，请使用 **hidden 参数或** 具有 **Hidden** 属性的 **Attributes** 参数。</span><span class="sxs-lookup"><span data-stu-id="48067-261">To get only hidden items, use the **Hidden** parameter or the **Attributes** parameter with the **Hidden** property.</span></span> <span data-ttu-id="48067-262">默认情况下， `Get-ChildItem` 不会显示隐藏项。</span><span class="sxs-lookup"><span data-stu-id="48067-262">By default, `Get-ChildItem` doesn't display hidden items.</span></span> <span data-ttu-id="48067-263">使用 **Force** 参数可获取隐藏项。</span><span class="sxs-lookup"><span data-stu-id="48067-263">Use the **Force** parameter to get hidden items.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ah, h

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-264">-Include</span><span class="sxs-lookup"><span data-stu-id="48067-264">-Include</span></span>

<span data-ttu-id="48067-265">指定此 cmdlet 将在操作中包含的一个项或多个项（作为一个字符串数组）。</span><span class="sxs-lookup"><span data-stu-id="48067-265">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="48067-266">此参数值使 **Path** 参数有效。</span><span class="sxs-lookup"><span data-stu-id="48067-266">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="48067-267">请输入路径元素或模式，例如 `"*.txt"`。</span><span class="sxs-lookup"><span data-stu-id="48067-267">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="48067-268">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="48067-268">Wildcard characters are permitted.</span></span> <span data-ttu-id="48067-269">仅 **Include** 当命令包括项的内容时（例如 `C:\Windows\*` ，其中的通配符指定目录的内容），Include 参数才有效 `C:\Windows` 。</span><span class="sxs-lookup"><span data-stu-id="48067-269">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48067-270">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="48067-270">-LiteralPath</span></span>

<span data-ttu-id="48067-271">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="48067-271">Specifies a path to one or more locations.</span></span> <span data-ttu-id="48067-272">**LiteralPath** 的值严格按照所键入的形式使用。</span><span class="sxs-lookup"><span data-stu-id="48067-272">The value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="48067-273">不会将任何字符解释为通配符。</span><span class="sxs-lookup"><span data-stu-id="48067-273">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="48067-274">如果路径包括转义符，请将其括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="48067-274">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="48067-275">单引号指示 PowerShell 不要将任何字符解释为转义序列。</span><span class="sxs-lookup"><span data-stu-id="48067-275">Single quotation marks tell PowerShell to not interpret any characters as escape sequences.</span></span>

<span data-ttu-id="48067-276">有关详细信息，请参阅 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-276">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralItems
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="48067-277">-Name</span><span class="sxs-lookup"><span data-stu-id="48067-277">-Name</span></span>

<span data-ttu-id="48067-278">仅获取位置中的项的名称。</span><span class="sxs-lookup"><span data-stu-id="48067-278">Gets only the names of the items in the location.</span></span> <span data-ttu-id="48067-279">输出是一个字符串对象，可将其向下发送到其他命令。</span><span class="sxs-lookup"><span data-stu-id="48067-279">The output is a string object that can be sent down the pipeline to other commands.</span></span> <span data-ttu-id="48067-280">允许使用通配符。</span><span class="sxs-lookup"><span data-stu-id="48067-280">Wildcards are permitted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="48067-281">-Path</span><span class="sxs-lookup"><span data-stu-id="48067-281">-Path</span></span>

<span data-ttu-id="48067-282">指定一个或多个位置的路径。</span><span class="sxs-lookup"><span data-stu-id="48067-282">Specifies a path to one or more locations.</span></span> <span data-ttu-id="48067-283">可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="48067-283">Wildcards are accepted.</span></span> <span data-ttu-id="48067-284">默认位置为当前目录 (`.`) 。</span><span class="sxs-lookup"><span data-stu-id="48067-284">The default location is the current directory (`.`).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Items
Aliases:

Required: False
Position: 0
Default value: Current directory
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="48067-285">-ReadOnly</span><span class="sxs-lookup"><span data-stu-id="48067-285">-ReadOnly</span></span>

<span data-ttu-id="48067-286">若要仅获取只读项，请使用 **readonly** 参数或 **Attributes** 参数 **readonly** 属性。</span><span class="sxs-lookup"><span data-stu-id="48067-286">To get only read-only items, use the **ReadOnly** parameter or the **Attributes** parameter **ReadOnly** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ar

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-287">-Recurse</span><span class="sxs-lookup"><span data-stu-id="48067-287">-Recurse</span></span>

<span data-ttu-id="48067-288">获取指定位置及其所有子项中的项。</span><span class="sxs-lookup"><span data-stu-id="48067-288">Gets the items in the specified locations and in all child items of the locations.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: s

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-289">-System</span><span class="sxs-lookup"><span data-stu-id="48067-289">-System</span></span>

<span data-ttu-id="48067-290">仅获取系统文件和目录。</span><span class="sxs-lookup"><span data-stu-id="48067-290">Gets only system files and directories.</span></span> <span data-ttu-id="48067-291">若要仅获取系统文件和文件夹，请使用 **system** 参数或 **Attributes** 参数 **系统** 属性。</span><span class="sxs-lookup"><span data-stu-id="48067-291">To get only system files and folders, use the **System** parameter or **Attributes** parameter **System** property.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: as

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="48067-292">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="48067-292">-UseTransaction</span></span>

<span data-ttu-id="48067-293">在活动事务中使用该命令。</span><span class="sxs-lookup"><span data-stu-id="48067-293">Includes the command in the active transaction.</span></span> <span data-ttu-id="48067-294">仅当正在执行事务时，此参数才有效。</span><span class="sxs-lookup"><span data-stu-id="48067-294">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="48067-295">有关详细信息，请参阅 [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-295">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

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

### <span data-ttu-id="48067-296">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="48067-296">CommonParameters</span></span>

<span data-ttu-id="48067-297">此 cmdlet 支持以下常见参数：-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction 和 -WarningVariable。</span><span class="sxs-lookup"><span data-stu-id="48067-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="48067-298">有关详细信息，请参阅 [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)。</span><span class="sxs-lookup"><span data-stu-id="48067-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="48067-299">输入</span><span class="sxs-lookup"><span data-stu-id="48067-299">INPUTS</span></span>

### <span data-ttu-id="48067-300">System.String</span><span class="sxs-lookup"><span data-stu-id="48067-300">System.String</span></span>

<span data-ttu-id="48067-301">可以通过管道将包含路径的字符串传递给 `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="48067-301">You can pipe a string that contains a path to `Get-ChildItem`.</span></span>

## <span data-ttu-id="48067-302">输出</span><span class="sxs-lookup"><span data-stu-id="48067-302">OUTPUTS</span></span>

### <span data-ttu-id="48067-303">System.Object</span><span class="sxs-lookup"><span data-stu-id="48067-303">System.Object</span></span>

<span data-ttu-id="48067-304">返回的对象类型由 `Get-ChildItem` 提供程序驱动器路径中的对象确定。</span><span class="sxs-lookup"><span data-stu-id="48067-304">The type of object that `Get-ChildItem` returns is determined by the objects in the provider drive path.</span></span>

### <span data-ttu-id="48067-305">System.String</span><span class="sxs-lookup"><span data-stu-id="48067-305">System.String</span></span>

<span data-ttu-id="48067-306">如果使用 **Name** 参数，则 `Get-ChildItem` 以字符串形式返回对象名称。</span><span class="sxs-lookup"><span data-stu-id="48067-306">If you use the **Name** parameter, `Get-ChildItem` returns the object names as strings.</span></span>

## <span data-ttu-id="48067-307">注释</span><span class="sxs-lookup"><span data-stu-id="48067-307">NOTES</span></span>

- <span data-ttu-id="48067-308">`Get-ChildItem` 可以使用任何内置的别名、、和来运行 `ls` `dir` `gci` 。</span><span class="sxs-lookup"><span data-stu-id="48067-308">`Get-ChildItem` can be run using any of the built-in aliases, `ls`, `dir`, and `gci`.</span></span> <span data-ttu-id="48067-309">有关详细信息，请参阅 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-309">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="48067-310">`Get-ChildItem` 默认情况下不会获取隐藏项。</span><span class="sxs-lookup"><span data-stu-id="48067-310">`Get-ChildItem` doesn't get hidden items by default.</span></span> <span data-ttu-id="48067-311">若要获取隐藏项，请使用 **Force** 参数。</span><span class="sxs-lookup"><span data-stu-id="48067-311">To get hidden items, use the **Force** parameter.</span></span>
- <span data-ttu-id="48067-312">`Get-ChildItem`Cmdlet 设计用于处理由任何提供程序公开的数据。</span><span class="sxs-lookup"><span data-stu-id="48067-312">The `Get-ChildItem` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="48067-313">若要列出会话中可用的提供程序，请键入 `Get-PSProvider`。</span><span class="sxs-lookup"><span data-stu-id="48067-313">To list the providers available in your session, type `Get-PSProvider`.</span></span>
  <span data-ttu-id="48067-314">有关详细信息，请参阅 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)。</span><span class="sxs-lookup"><span data-stu-id="48067-314">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="48067-315">相关链接</span><span class="sxs-lookup"><span data-stu-id="48067-315">RELATED LINKS</span></span>

[<span data-ttu-id="48067-316">about_Certificate_Provider</span><span class="sxs-lookup"><span data-stu-id="48067-316">about_Certificate_Provider</span></span>](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)

[<span data-ttu-id="48067-317">about_Providers</span><span class="sxs-lookup"><span data-stu-id="48067-317">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="48067-318">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="48067-318">about_Quoting_Rules</span></span>](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="48067-319">about_Registry_Provider</span><span class="sxs-lookup"><span data-stu-id="48067-319">about_Registry_Provider</span></span>](../Microsoft.PowerShell.Core/About/about_Registry_Provider.md)

[<span data-ttu-id="48067-320">ForEach-Object</span><span class="sxs-lookup"><span data-stu-id="48067-320">ForEach-Object</span></span>](../Microsoft.PowerShell.Core/ForEach-Object.md)

[<span data-ttu-id="48067-321">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="48067-321">Get-Alias</span></span>](../Microsoft.PowerShell.Utility/Get-Alias.md)

[<span data-ttu-id="48067-322">Get-Item</span><span class="sxs-lookup"><span data-stu-id="48067-322">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="48067-323">Get-Location</span><span class="sxs-lookup"><span data-stu-id="48067-323">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="48067-324">Get-Process</span><span class="sxs-lookup"><span data-stu-id="48067-324">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="48067-325">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="48067-325">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="48067-326">Split-Path</span><span class="sxs-lookup"><span data-stu-id="48067-326">Split-Path</span></span>](Split-Path.md)
